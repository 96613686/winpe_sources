# winreCreateRecoveryEntryInBCD

- ea: `0x180034aa4`
- end: `0x180034c85`
- name: `winreCreateRecoveryEntryInBCD`
- size: `481`
- prototype: `__int64 __fastcall(struct PartitionNode *)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1800174a0`
- `0x180018870`
- `0x180019a90`
- `0x180024a10`
- `0x18002cab4`

## callees

- `0x1800059fc`
- `0x180034aa4`
- `0x180034c8c`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180034b14`
- `ntdll!RtlNtStatusToDosError` at `0x180034b14`
- `KERNEL32!HeapFree` at `0x180034c40`
- `KERNEL32!HeapFree` at `0x180034c40`
- `KERNEL32!HeapAlloc` at `0x180034bae`
- `KERNEL32!HeapAlloc` at `0x180034bae`
- `KERNEL32!GetProcessHeap` at `0x180034b9d`
- `KERNEL32!GetProcessHeap` at `0x180034c32`
- `KERNEL32!GetProcessHeap` at `0x180034b9d`
- `KERNEL32!GetProcessHeap` at `0x180034c32`
- `bcd!BcdCloseStore` at `0x180034c66`
- `bcd!BcdCloseStore` at `0x180034c66`
- `bcd!BcdCloseObject` at `0x180034c4f`
- `bcd!BcdCloseObject` at `0x180034c4f`
- `bcd!BcdGetElementData` at `0x180034b78`
- `bcd!BcdGetElementData` at `0x180034bfe`
- `bcd!BcdGetElementData` at `0x180034b78`
- `bcd!BcdGetElementData` at `0x180034bfe`
- `bcd!BcdOpenObject` at `0x180034b45`
- `bcd!BcdOpenObject` at `0x180034b45`
- `bcd!BcdOpenStore` at `0x180034af2`
- `bcd!BcdOpenStore` at `0x180034af2`

## string_xrefs

- `0x180034b4f`: `BcdOpenObject failed: 0x%x`
- `0x180034bc7`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x180034b01`: `open store failed: 0x%x`
- `0x180034bdd`: `winreCreateRecoveryEntryInBCD %s (0x%x) in file %S line %d`

## pseudocode

```c
__int64 __fastcall winreCreateRecoveryEntryInBCD(struct PartitionNode *a1, _OWORD *a2, GUID *a3)
{
  int v6; // eax
  NTSTATUS v7; // edi
  unsigned int RecoveryEntryInBCDEx; // edi
  GUID v9; // xmm0
  int v10; // eax
  unsigned int ElementData; // eax
  unsigned int v12; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID v14; // rax
  void *v15; // rbx
  int v16; // eax
  HANDLE v17; // rax
  __int64 v19; // [rsp+30h] [rbp-30h] BYREF
  void *v20; // [rsp+38h] [rbp-28h] BYREF
  SIZE_T dwBytes; // [rsp+40h] [rbp-20h] BYREF
  GUID v22; // [rsp+48h] [rbp-18h] BYREF

  v20 = 0;
  *a2 = 0;
  v19 = 0;
  LODWORD(dwBytes) = 0;
  v22 = 0;
  v6 = BcdOpenStore(0, 0, &v20);
  v7 = v6;
  if ( v6 >= 0 )
  {
    RecoveryEntryInBCDEx = 0;
    if ( a3 )
      v9 = *a3;
    else
      v9 = GUID_CURRENT_BOOT_ENTRY;
    v22 = v9;
    v10 = BcdOpenObject(v20, &v22, &v19);
    if ( v10 >= 0 )
    {
      ElementData = BcdGetElementData(v19, 301989893, 0, &dwBytes);
      if ( (int)(ElementData + 0x80000000) < 0 || ElementData == -1073741789 )
      {
        v12 = dwBytes;
        ProcessHeap = GetProcessHeap();
        v14 = HeapAlloc(ProcessHeap, 8u, v12);
        v15 = v14;
        if ( v14 )
        {
          v16 = BcdGetElementData(v19, 301989893, v14, &dwBytes);
          if ( v16 >= 0 )
            RecoveryEntryInBCDEx = winreCreateRecoveryEntryInBCDEx(v20, a1, (__int64)v15, a2);
          else
            UnattendLogW(1, L"BcdGetElementData failed: 0x%x", (unsigned int)v16);
          v17 = GetProcessHeap();
          HeapFree(v17, 0, v15);
        }
        else
        {
          RecoveryEntryInBCDEx = 8;
          UnattendLogW(
            2,
            L"winreCreateRecoveryEntryInBCD %s (0x%x) in file %S line %d",
            L"failed to allocate memory",
            8,
            "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
            1127);
        }
      }
      else
      {
        UnattendLogW(1, L"BcdGetElementData failed: 0x%x", ElementData);
      }
    }
    else
    {
      UnattendLogW(1, L"BcdOpenObject failed: 0x%x", (unsigned int)v10);
    }
  }
  else
  {
    UnattendLogW(1, L"open store failed: 0x%x", (unsigned int)v6);
    RecoveryEntryInBCDEx = RtlNtStatusToDosError(v7);
  }
  if ( v19 )
  {
    BcdCloseObject();
    v19 = 0;
  }
  if ( v20 )
    BcdCloseStore(v20);
  return RecoveryEntryInBCDEx;
}

```

## disassembly

```asm
0x180034aa4  push    rbp
0x180034aa6  push    rbx
0x180034aa7  push    rsi
0x180034aa8  push    rdi
0x180034aa9  push    r14
0x180034aab  mov     rbp, rsp
0x180034aae  sub     rsp, 60h
0x180034ab2  mov     rax, cs:__security_cookie
0x180034ab9  xor     rax, rsp
0x180034abc  mov     [rbp+var_8], rax
0x180034ac0  xorps   xmm0, xmm0
0x180034ac3  mov     [rbp+var_28], 0
0x180034acb  movups  xmmword ptr [rdx], xmm0
0x180034ace  mov     rbx, r8
0x180034ad1  mov     [rbp+var_30], 0
0x180034ad9  mov     rsi, rdx
0x180034adc  mov     dword ptr [rbp+dwBytes], 0
0x180034ae3  mov     r14, rcx
0x180034ae6  lea     r8, [rbp+var_28]
0x180034aea  xor     edx, edx
0x180034aec  xor     ecx, ecx
0x180034aee  movups  [rbp+var_18], xmm0
0x180034af2  call    cs:__imp_BcdOpenStore
0x180034af8  mov     edi, eax
0x180034afa  test    eax, eax
0x180034afc  jns     short loc_180034B21
0x180034afe  mov     r8d, eax
0x180034b01  lea     rdx, aOpenStoreFaile_1; "open store failed: 0x%x"
0x180034b08  mov     ecx, 1
0x180034b0d  call    UnattendLogW
0x180034b12  mov     ecx, edi; Status
0x180034b14  call    cs:__imp_RtlNtStatusToDosError
0x180034b1a  mov     edi, eax
0x180034b1c  jmp     loc_180034C46
0x180034b21  xor     edi, edi
0x180034b23  test    rbx, rbx
0x180034b26  jz      short loc_180034B2D
0x180034b28  movups  xmm0, xmmword ptr [rbx]
0x180034b2b  jmp     short loc_180034B34
0x180034b2d  movups  xmm0, xmmword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data1
0x180034b34  mov     rcx, [rbp+var_28]
0x180034b38  lea     r8, [rbp+var_30]
0x180034b3c  lea     rdx, [rbp+var_18]
0x180034b40  movdqu  [rbp+var_18], xmm0
0x180034b45  call    cs:__imp_BcdOpenObject
0x180034b4b  test    eax, eax
0x180034b4d  jns     short loc_180034B68
0x180034b4f  lea     rdx, aBcdopenobjectF_0; "BcdOpenObject failed: 0x%x"
0x180034b56  mov     r8d, eax
0x180034b59  mov     ecx, 1
0x180034b5e  call    UnattendLogW
0x180034b63  jmp     loc_180034C46
0x180034b68  mov     rcx, [rbp+var_30]
0x180034b6c  lea     r9, [rbp+dwBytes]
0x180034b70  xor     r8d, r8d
0x180034b73  mov     edx, 12000005h
0x180034b78  call    cs:__imp_BcdGetElementData
0x180034b7e  mov     edx, 80000000h
0x180034b83  lea     ecx, [rax+rdx]
0x180034b86  test    edx, ecx
0x180034b88  jnz     short loc_180034B9A
0x180034b8a  cmp     eax, 0C0000023h
0x180034b8f  jz      short loc_180034B9A
0x180034b91  lea     rdx, aBcdgetelementd_2; "BcdGetElementData failed: 0x%x"
0x180034b98  jmp     short loc_180034B56
0x180034b9a  mov     ebx, dword ptr [rbp+dwBytes]
0x180034b9d  call    cs:__imp_GetProcessHeap
0x180034ba3  mov     r8d, ebx; dwBytes
0x180034ba6  mov     edx, 8; dwFlags
0x180034bab  mov     rcx, rax; hHeap
0x180034bae  call    cs:__imp_HeapAlloc
0x180034bb4  mov     rbx, rax
0x180034bb7  test    rax, rax
0x180034bba  jnz     short loc_180034BEE
0x180034bbc  lea     edi, [rax+8]
0x180034bbf  mov     [rsp+60h+var_38], 467h
0x180034bc7  lea     rax, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180034bce  mov     r9d, edi
0x180034bd1  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x180034bd8  mov     [rsp+60h+var_40], rax
0x180034bdd  lea     rdx, aWinrecreaterec_1; "winreCreateRecoveryEntryInBCD %s (0x%x)"...
0x180034be4  lea     ecx, [rbx+2]
0x180034be7  call    UnattendLogW
0x180034bec  jmp     short loc_180034C46
0x180034bee  mov     rcx, [rbp+var_30]
0x180034bf2  lea     r9, [rbp+dwBytes]
0x180034bf6  mov     r8, rbx
0x180034bf9  mov     edx, 12000005h
0x180034bfe  call    cs:__imp_BcdGetElementData
0x180034c04  test    eax, eax
0x180034c06  jns     short loc_180034C1E
0x180034c08  mov     r8d, eax
0x180034c0b  lea     rdx, aBcdgetelementd_2; "BcdGetElementData failed: 0x%x"
0x180034c12  mov     ecx, 1
0x180034c17  call    UnattendLogW
0x180034c1c  jmp     short loc_180034C32
0x180034c1e  mov     rcx, [rbp+var_28]; void *
0x180034c22  mov     r9, rsi
0x180034c25  mov     r8, rbx
0x180034c28  mov     rdx, r14; struct PartitionNode *
0x180034c2b  call    winreCreateRecoveryEntryInBCDEx
0x180034c30  mov     edi, eax
0x180034c32  call    cs:__imp_GetProcessHeap
0x180034c38  mov     r8, rbx; lpMem
0x180034c3b  xor     edx, edx; dwFlags
0x180034c3d  mov     rcx, rax; hHeap
0x180034c40  call    cs:__imp_HeapFree
0x180034c46  mov     rcx, [rbp+var_30]
0x180034c4a  test    rcx, rcx
0x180034c4d  jz      short loc_180034C5D
0x180034c4f  call    cs:__imp_BcdCloseObject
0x180034c55  mov     [rbp+var_30], 0
0x180034c5d  mov     rcx, [rbp+var_28]
0x180034c61  test    rcx, rcx
0x180034c64  jz      short loc_180034C6C
0x180034c66  call    cs:__imp_BcdCloseStore
0x180034c6c  mov     eax, edi
0x180034c6e  mov     rcx, [rbp+var_8]
0x180034c72  xor     rcx, rsp; StackCookie
0x180034c75  call    __security_check_cookie
0x180034c7a  add     rsp, 60h
0x180034c7e  pop     r14
0x180034c80  pop     rdi
0x180034c81  pop     rsi
0x180034c82  pop     rbx
0x180034c83  pop     rbp
0x180034c84  retn
```
