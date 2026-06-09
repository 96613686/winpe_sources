# BiUnloadHiveByName

- ea: `0x14001fe24`
- end: `0x14001ff6f`
- name: `BiUnloadHiveByName`
- size: `331`
- prototype: `__int64 __fastcall(__int64, int, char)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001af00`
- `0x14001fd7c`

## callees

- `0x14001fe24`
- `0x140020678`
- `0x14002166c`
- `0x140021888`
- `0x140027010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x14001fea6`
- `msvcrt!swprintf_s` at `0x14001fea6`
- `ntdll!ZwUnloadKey` at `0x14001fefc`
- `ntdll!ZwUnloadKey` at `0x14001fefc`
- `ntdll!RtlAllocateHeap` at `0x14001fe72`
- `ntdll!RtlAllocateHeap` at `0x14001fe72`
- `ntdll!RtlFreeHeap` at `0x14001ff4f`
- `ntdll!RtlFreeHeap` at `0x14001ff4f`
- `ntdll!RtlInitUnicodeString` at `0x14001feb3`
- `ntdll!RtlInitUnicodeString` at `0x14001feb3`

## string_xrefs

- `0x14001fe8d`: `\Registry\Machine`

## pseudocode

```c
__int64 __fastcall BiUnloadHiveByName(__int64 a1, int a2, char a3)
{
  SIZE_T v5; // rbx
  wchar_t *Heap; // rax
  WCHAR *v7; // rdi
  NTSTATUS v8; // ebx
  NTSTATUS v9; // eax
  __int64 v11; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES KeyObjectAttributes; // [rsp+48h] [rbp-38h] BYREF
  __int64 (__fastcall *v14)(struct _OBJECT_ATTRIBUTES *, __int64); // [rsp+B8h] [rbp+38h] BYREF

  v11 = 0;
  memset(&KeyObjectAttributes, 0, 44);
  DestinationString = 0;
  v5 = (unsigned int)(a2 + 38);
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  v7 = Heap;
  if ( Heap )
  {
    swprintf_s(Heap, v5 >> 1, L"%s\\%s", L"\\Registry\\Machine", a1);
    RtlInitUnicodeString(&DestinationString, v7);
    KeyObjectAttributes.Length = 48;
    KeyObjectAttributes.ObjectName = &DestinationString;
    KeyObjectAttributes.RootDirectory = 0;
    KeyObjectAttributes.Attributes = 64;
    *(_OWORD *)&KeyObjectAttributes.SecurityDescriptor = 0;
    v8 = BiAcquirePrivilege(0x12u, (__int64)&v11);
    if ( v8 >= 0 )
    {
      if ( a3 && (v14 = 0, (int)BiLookupNtdllProcedureAddress("ZwUnloadKey2", (PVOID *)&v14) >= 0) )
        v9 = v14(&KeyObjectAttributes, 1);
      else
        v9 = ZwUnloadKey(&KeyObjectAttributes);
      v8 = v9;
      BiReleasePrivilege((__int64)&v11);
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14001fe24  mov     [rsp-18h+arg_0], rbx
0x14001fe29  mov     [rsp-18h+arg_8], rsi
0x14001fe2e  push    rbp
0x14001fe2f  push    rdi
0x14001fe30  push    r14
0x14001fe32  mov     rbp, rsp
0x14001fe35  sub     rsp, 80h
0x14001fe3c  xorps   xmm0, xmm0
0x14001fe3f  mov     r14, rcx
0x14001fe42  movups  xmmword ptr [rbp+KeyObjectAttributes.ObjectName], xmm0
0x14001fe46  xor     eax, eax
0x14001fe48  mov     sil, r8b
0x14001fe4b  movups  xmmword ptr [rbp+KeyObjectAttributes+1Ch], xmm0
0x14001fe4f  mov     [rbp+var_50], rax
0x14001fe53  lea     eax, [rdx+26h]
0x14001fe56  movups  xmmword ptr [rbp+KeyObjectAttributes.Length], xmm0
0x14001fe5a  mov     r8d, eax; Size
0x14001fe5d  xor     edx, edx; Flags
0x14001fe5f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001fe63  mov     rcx, gs:60h
0x14001fe6c  mov     ebx, eax
0x14001fe6e  mov     rcx, [rcx+30h]; HeapHandle
0x14001fe72  call    cs:__imp_RtlAllocateHeap
0x14001fe78  mov     rdi, rax
0x14001fe7b  test    rax, rax
0x14001fe7e  jnz     short loc_14001FE8A
0x14001fe80  mov     ebx, 0C000009Ah
0x14001fe85  jmp     loc_14001FF55
0x14001fe8a  shr     rbx, 1
0x14001fe8d  lea     r9, aRegistryMachin_2; "\\Registry\\Machine"
0x14001fe94  mov     rdx, rbx; BufferCount
0x14001fe97  mov     [rsp+80h+var_60], r14
0x14001fe9c  lea     r8, aSS; "%s\\%s"
0x14001fea3  mov     rcx, rdi; Buffer
0x14001fea6  call    cs:__imp_swprintf_s
0x14001feac  mov     rdx, rdi; SourceString
0x14001feaf  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001feb3  call    cs:__imp_RtlInitUnicodeString
0x14001feb9  lea     rax, [rbp+DestinationString]
0x14001febd  mov     [rbp+KeyObjectAttributes.Length], 30h ; '0'
0x14001fec4  xorps   xmm0, xmm0
0x14001fec7  mov     [rbp+KeyObjectAttributes.ObjectName], rax
0x14001fecb  lea     rdx, [rbp+var_50]
0x14001fecf  mov     [rbp+KeyObjectAttributes.RootDirectory], 0
0x14001fed7  mov     ecx, 12h
0x14001fedc  mov     [rbp+KeyObjectAttributes.Attributes], 40h ; '@'
0x14001fee3  movdqu  xmmword ptr [rbp+KeyObjectAttributes.SecurityDescriptor], xmm0
0x14001fee8  call    BiAcquirePrivilege
0x14001feed  mov     ebx, eax
0x14001feef  test    eax, eax
0x14001fef1  js      short loc_14001FF3D
0x14001fef3  test    sil, sil
0x14001fef6  jnz     short loc_14001FF04
0x14001fef8  lea     rcx, [rbp+KeyObjectAttributes]; KeyObjectAttributes
0x14001fefc  call    cs:__imp_ZwUnloadKey
0x14001ff02  jmp     short loc_14001FF32
0x14001ff04  lea     rdx, [rbp+arg_18]
0x14001ff08  mov     [rbp+arg_18], 0
0x14001ff10  lea     rcx, aZwunloadkey2; "ZwUnloadKey2"
0x14001ff17  call    BiLookupNtdllProcedureAddress
0x14001ff1c  lea     rcx, [rbp+KeyObjectAttributes]
0x14001ff20  test    eax, eax
0x14001ff22  js      short loc_14001FEFC
0x14001ff24  mov     rax, [rbp+arg_18]
0x14001ff28  mov     edx, 1
0x14001ff2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ff32  lea     rcx, [rbp+var_50]
0x14001ff36  mov     ebx, eax
0x14001ff38  call    BiReleasePrivilege
0x14001ff3d  mov     rcx, gs:60h
0x14001ff46  mov     r8, rdi; P
0x14001ff49  xor     edx, edx; Flags
0x14001ff4b  mov     rcx, [rcx+30h]; HeapHandle
0x14001ff4f  call    cs:__imp_RtlFreeHeap
0x14001ff55  lea     r11, [rsp+80h+var_s0]
0x14001ff5d  mov     eax, ebx
0x14001ff5f  mov     rbx, [r11+20h]
0x14001ff63  mov     rsi, [r11+28h]
0x14001ff67  mov     rsp, r11
0x14001ff6a  pop     r14
0x14001ff6c  pop     rdi
0x14001ff6d  pop     rbp
0x14001ff6e  retn
```
