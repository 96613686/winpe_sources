# winreGetWimPathFromBCDEntry(void *,ushort *,ushort *,unsigned __int64)

- ea: `0x180033a90`
- end: `0x180033caf`
- name: `?winreGetWimPathFromBCDEntry@@YAKPEAXPEAG1_K@Z`
- size: `543`
- prototype: `unsigned int(void *, unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1800338fc`
- `0x1800361ac`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x180033a90`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180033afa`
- `ntdll!RtlNtStatusToDosError` at `0x180033b75`
- `ntdll!RtlNtStatusToDosError` at `0x180033be8`
- `ntdll!RtlNtStatusToDosError` at `0x180033afa`
- `ntdll!RtlNtStatusToDosError` at `0x180033b75`
- `ntdll!RtlNtStatusToDosError` at `0x180033be8`
- `KERNEL32!HeapFree` at `0x180033c8f`
- `KERNEL32!HeapFree` at `0x180033c8f`
- `KERNEL32!HeapAlloc` at `0x180033b19`
- `KERNEL32!HeapAlloc` at `0x180033b19`
- `KERNEL32!GetProcessHeap` at `0x180033b0b`
- `KERNEL32!GetProcessHeap` at `0x180033c81`
- `KERNEL32!GetProcessHeap` at `0x180033b0b`
- `KERNEL32!GetProcessHeap` at `0x180033c81`
- `bcd!SyspartGetSystemPartition` at `0x180033c2c`
- `bcd!SyspartGetSystemPartition` at `0x180033c2c`
- `bcd!BcdGetElementData` at `0x180033ac8`
- `bcd!BcdGetElementData` at `0x180033b53`
- `bcd!BcdGetElementData` at `0x180033ac8`
- `bcd!BcdGetElementData` at `0x180033b53`

## string_xrefs

- `0x180033b5f`: `Couldn't read OS device from BCD object: 0x%x`
- `0x180033bcc`: `Failed to copy partition path to output parameter: 0x%x`
- `0x180033c38`: `SyspartGetSystemPartition failed: 0x%x`
- `0x180033c5b`: `Failed to copy WIM path to output parameter: 0x%x`

## pseudocode

```c
__int64 __fastcall winreGetWimPathFromBCDEntry(void *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int ElementData; // ebx
  NTSTATUS SystemPartition; // ebx
  unsigned int v8; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rdi
  __int64 v12; // rax
  int v13; // r8d
  HANDLE v14; // rax
  unsigned int dwBytes; // [rsp+20h] [rbp-38h] BYREF
  int dwBytes_4; // [rsp+24h] [rbp-34h] BYREF

  dwBytes = 0;
  ElementData = BcdGetElementData(a1, 553648129, 0, &dwBytes);
  if ( (int)(ElementData + 0x80000000) < 0 || ElementData == -1073741789 )
  {
    v8 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v10 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, v8);
    v11 = v10;
    if ( !v10 )
    {
      UnattendLogW(1, L"Failed to allocate BCDE_DEVICE (%u bytes)", dwBytes);
      return 14;
    }
    SystemPartition = BcdGetElementData(a1, 553648129, v10, &dwBytes);
    if ( SystemPartition < 0 )
    {
      UnattendLogW(1, L"Couldn't read OS device from BCD object: 0x%x", (unsigned int)SystemPartition);
      goto LABEL_8;
    }
    if ( *(_DWORD *)v11 != 4 )
    {
      UnattendLogW(1, L"Expected a ramdisk device, found device type %u instead", *(unsigned int *)v11);
      SystemPartition = 13;
      goto LABEL_26;
    }
    v12 = *((unsigned int *)v11 + 5);
    v13 = *(_DWORD *)((char *)v11 + v12);
    if ( v13 == 2 )
    {
      SystemPartition = StringCchCopyW(a2, 0x208u, (unsigned __int16 *)((char *)v11 + v12 + 20));
      if ( SystemPartition < 0 )
      {
        UnattendLogW(1, L"Failed to copy partition path to output parameter: 0x%x", (unsigned int)SystemPartition);
        goto LABEL_14;
      }
    }
    else
    {
      if ( v13 != 1 )
      {
        UnattendLogW(1, L"Parent device has unsupported type %u");
        SystemPartition = 50;
        goto LABEL_26;
      }
      dwBytes_4 = 0;
      SystemPartition = SyspartGetSystemPartition(a2, 520, &dwBytes_4);
      if ( SystemPartition < 0 )
      {
        UnattendLogW(1, L"SyspartGetSystemPartition failed: 0x%x", (unsigned int)SystemPartition);
        goto LABEL_8;
      }
    }
    SystemPartition = StringCchCopyW(a3, 0x208u, v11 + 12);
    if ( SystemPartition >= 0 )
    {
      SystemPartition = 0;
      goto LABEL_26;
    }
    UnattendLogW(1, L"Failed to copy WIM path to output parameter: 0x%x", (unsigned int)SystemPartition);
LABEL_14:
    if ( (SystemPartition & 0x10000000) == 0 )
    {
      if ( (SystemPartition & 0x1FFF0000) == 0x70000 )
        SystemPartition = (unsigned __int16)SystemPartition;
      goto LABEL_26;
    }
    if ( RtlNtStatusToDosError(SystemPartition) == 317 )
    {
LABEL_26:
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v11);
      return (unsigned int)SystemPartition;
    }
LABEL_8:
    SystemPartition = RtlNtStatusToDosError(SystemPartition);
    goto LABEL_26;
  }
  UnattendLogW(1, L" Couldn't get size of OS device from BCD object: 0x%x", ElementData);
  return RtlNtStatusToDosError(ElementData);
}

```

## disassembly

```asm
0x180033a90  push    rbx
0x180033a92  push    rbp
0x180033a93  push    rsi
0x180033a94  push    rdi
0x180033a95  push    r14
0x180033a97  sub     rsp, 30h
0x180033a9b  mov     rax, cs:__security_cookie
0x180033aa2  xor     rax, rsp
0x180033aa5  mov     [rsp+58h+var_30], rax
0x180033aaa  mov     r14, r8
0x180033aad  mov     dword ptr [rsp+58h+dwBytes], 0
0x180033ab5  mov     rsi, rdx
0x180033ab8  lea     r9, [rsp+58h+dwBytes]
0x180033abd  xor     r8d, r8d
0x180033ac0  mov     edx, 21000001h
0x180033ac5  mov     rbp, rcx
0x180033ac8  call    cs:__imp_BcdGetElementData
0x180033ace  mov     ebx, eax
0x180033ad0  mov     eax, 80000000h
0x180033ad5  lea     ecx, [rbx+rax]
0x180033ad8  test    eax, ecx
0x180033ada  jnz     short loc_180033B07
0x180033adc  cmp     ebx, 0C0000023h
0x180033ae2  jz      short loc_180033B07
0x180033ae4  mov     r8d, ebx
0x180033ae7  lea     rdx, aCouldnTGetSize; " Couldn't get size of OS device from BC"...
0x180033aee  mov     ecx, 1
0x180033af3  call    UnattendLogW
0x180033af8  mov     ecx, ebx; Status
0x180033afa  call    cs:__imp_RtlNtStatusToDosError
0x180033b00  mov     ebx, eax
0x180033b02  jmp     loc_180033C95
0x180033b07  mov     ebx, dword ptr [rsp+58h+dwBytes]
0x180033b0b  call    cs:__imp_GetProcessHeap
0x180033b11  mov     r8d, ebx; dwBytes
0x180033b14  xor     edx, edx; dwFlags
0x180033b16  mov     rcx, rax; hHeap
0x180033b19  call    cs:__imp_HeapAlloc
0x180033b1f  mov     rdi, rax
0x180033b22  test    rax, rax
0x180033b25  jnz     short loc_180033B43
0x180033b27  mov     r8d, dword ptr [rsp+58h+dwBytes]
0x180033b2c  lea     rdx, aFailedToAlloca_5; "Failed to allocate BCDE_DEVICE (%u byte"...
0x180033b33  lea     ecx, [rax+1]
0x180033b36  call    UnattendLogW
0x180033b3b  lea     ebx, [rdi+0Eh]
0x180033b3e  jmp     loc_180033C95
0x180033b43  lea     r9, [rsp+58h+dwBytes]
0x180033b48  mov     r8, rdi
0x180033b4b  mov     edx, 21000001h
0x180033b50  mov     rcx, rbp
0x180033b53  call    cs:__imp_BcdGetElementData
0x180033b59  mov     ebx, eax
0x180033b5b  test    eax, eax
0x180033b5d  jns     short loc_180033B82
0x180033b5f  lea     rdx, aCouldnTReadOsD; "Couldn't read OS device from BCD object"...
0x180033b66  mov     r8d, ebx
0x180033b69  mov     ecx, 1
0x180033b6e  call    UnattendLogW
0x180033b73  mov     ecx, ebx; Status
0x180033b75  call    cs:__imp_RtlNtStatusToDosError
0x180033b7b  mov     ebx, eax
0x180033b7d  jmp     loc_180033C81
0x180033b82  cmp     dword ptr [rdi], 4
0x180033b85  jz      short loc_180033BA5
0x180033b87  mov     r8d, [rdi]
0x180033b8a  lea     rdx, aExpectedARamdi; "Expected a ramdisk device, found device"...
0x180033b91  mov     ecx, 1
0x180033b96  call    UnattendLogW
0x180033b9b  mov     ebx, 0Dh
0x180033ba0  jmp     loc_180033C81
0x180033ba5  mov     eax, [rdi+14h]
0x180033ba8  mov     r8d, [rax+rdi]
0x180033bac  cmp     r8d, 2
0x180033bb0  jnz     short loc_180033C11
0x180033bb2  lea     r8, [rax+14h]
0x180033bb6  mov     edx, 208h; unsigned __int64
0x180033bbb  add     r8, rdi; unsigned __int16 *
0x180033bbe  mov     rcx, rsi; unsigned __int16 *
0x180033bc1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033bc6  mov     ebx, eax
0x180033bc8  test    eax, eax
0x180033bca  jns     short loc_180033C44
0x180033bcc  lea     rdx, aFailedToCopyPa_1; "Failed to copy partition path to output"...
0x180033bd3  mov     r8d, ebx
0x180033bd6  mov     ecx, 1
0x180033bdb  call    UnattendLogW
0x180033be0  bt      ebx, 1Ch
0x180033be4  jnb     short loc_180033BFE
0x180033be6  mov     ecx, ebx; Status
0x180033be8  call    cs:__imp_RtlNtStatusToDosError
0x180033bee  cmp     eax, 13Dh
0x180033bf3  jz      loc_180033C81
0x180033bf9  jmp     loc_180033B73
0x180033bfe  mov     eax, ebx
0x180033c00  and     eax, 1FFF0000h
0x180033c05  cmp     eax, 70000h
0x180033c0a  jnz     short loc_180033C81
0x180033c0c  movzx   ebx, bx
0x180033c0f  jmp     short loc_180033C81
0x180033c11  cmp     r8d, 1
0x180033c15  jnz     short loc_180033C6B
0x180033c17  lea     r8, [rsp+58h+dwBytes+4]
0x180033c1c  mov     dword ptr [rsp+58h+dwBytes+4], 0
0x180033c24  mov     edx, 208h
0x180033c29  mov     rcx, rsi
0x180033c2c  call    cs:__imp_SyspartGetSystemPartition
0x180033c32  mov     ebx, eax
0x180033c34  test    eax, eax
0x180033c36  jns     short loc_180033C44
0x180033c38  lea     rdx, aSyspartgetsyst_0; "SyspartGetSystemPartition failed: 0x%x"
0x180033c3f  jmp     loc_180033B66
0x180033c44  lea     r8, [rdi+18h]; unsigned __int16 *
0x180033c48  mov     edx, 208h; unsigned __int64
0x180033c4d  mov     rcx, r14; unsigned __int16 *
0x180033c50  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033c55  mov     ebx, eax
0x180033c57  test    eax, eax
0x180033c59  jns     short loc_180033C67
0x180033c5b  lea     rdx, aFailedToCopyWi_0; "Failed to copy WIM path to output param"...
0x180033c62  jmp     loc_180033BD3
0x180033c67  xor     ebx, ebx
0x180033c69  jmp     short loc_180033C81
0x180033c6b  lea     rdx, aParentDeviceHa; "Parent device has unsupported type %u"
0x180033c72  mov     ecx, 1
0x180033c77  call    UnattendLogW
0x180033c7c  mov     ebx, 32h ; '2'
0x180033c81  call    cs:__imp_GetProcessHeap
0x180033c87  mov     r8, rdi; lpMem
0x180033c8a  xor     edx, edx; dwFlags
0x180033c8c  mov     rcx, rax; hHeap
0x180033c8f  call    cs:__imp_HeapFree
0x180033c95  mov     eax, ebx
0x180033c97  mov     rcx, [rsp+58h+var_30]
0x180033c9c  xor     rcx, rsp; StackCookie
0x180033c9f  call    __security_check_cookie
0x180033ca4  add     rsp, 30h
0x180033ca8  pop     r14
0x180033caa  pop     rdi
0x180033cab  pop     rsi
0x180033cac  pop     rbp
0x180033cad  pop     rbx
0x180033cae  retn
```
