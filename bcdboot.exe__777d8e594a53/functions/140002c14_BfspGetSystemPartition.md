# BfspGetSystemPartition

- ea: `0x140002c14`
- end: `0x140002ec0`
- name: `BfspGetSystemPartition`
- size: `684`
- prototype: `wchar_t *__fastcall(char)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400032d0`
- `0x140006cd8`
- `0x140009bdc`
- `0x14000c024`

## callees

- `0x140002c14`
- `0x14000e628`
- `0x140011588`
- `0x140011670`
- `0x140013ac0`
- `0x1400265e2`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140002e9b`
- `KERNEL32!SetLastError` at `0x140002e9b`
- `KERNEL32!HeapFree` at `0x140002e0e`
- `KERNEL32!HeapFree` at `0x140002e72`
- `KERNEL32!HeapFree` at `0x140002e8b`
- `KERNEL32!HeapFree` at `0x140002e0e`
- `KERNEL32!HeapFree` at `0x140002e72`
- `KERNEL32!HeapFree` at `0x140002e8b`
- `KERNEL32!HeapAlloc` at `0x140002c6f`
- `KERNEL32!HeapAlloc` at `0x140002cd4`
- `KERNEL32!HeapAlloc` at `0x140002c6f`
- `KERNEL32!HeapAlloc` at `0x140002cd4`
- `KERNEL32!GetProcessHeap` at `0x140002c5e`
- `KERNEL32!GetProcessHeap` at `0x140002cc3`
- `KERNEL32!GetProcessHeap` at `0x140002e00`
- `KERNEL32!GetProcessHeap` at `0x140002e64`
- `KERNEL32!GetProcessHeap` at `0x140002e7d`
- `KERNEL32!GetProcessHeap` at `0x140002c5e`
- `KERNEL32!GetProcessHeap` at `0x140002cc3`
- `KERNEL32!GetProcessHeap` at `0x140002e00`
- `KERNEL32!GetProcessHeap` at `0x140002e64`
- `KERNEL32!GetProcessHeap` at `0x140002e7d`
- `ntdll!RtlAllocateHeap` at `0x140002d4a`
- `ntdll!RtlAllocateHeap` at `0x140002d4a`
- `ntdll!RtlFreeHeap` at `0x140002e2e`
- `ntdll!RtlFreeHeap` at `0x140002e2e`
- `ntdll!RtlNtStatusToDosError` at `0x140002e93`
- `ntdll!RtlNtStatusToDosError` at `0x140002e93`

## pseudocode

```c
wchar_t *__fastcall BfspGetSystemPartition(char a1)
{
  __int64 v1; // rsi
  __int64 v3; // rax
  unsigned int v4; // edi
  HANDLE ProcessHeap; // rax
  wchar_t *v6; // rax
  wchar_t *v7; // rbx
  int SystemPartition; // eax
  NTSTATUS v9; // edi
  unsigned int v10; // ebx
  HANDLE v11; // rax
  wchar_t *v12; // rax
  wchar_t v13; // r12
  __int64 v14; // rax
  size_t v15; // rdi
  wchar_t *Heap; // r14
  HRESULT v17; // eax
  unsigned __int16 v18; // di
  HRESULT v19; // eax
  HRESULT v20; // eax
  HANDLE v21; // rax
  HANDLE v22; // rax
  ULONG v23; // eax
  DWORD v25; // [rsp+30h] [rbp-10h]
  DWORD v26; // [rsp+30h] [rbp-10h]
  SIZE_T dwBytes; // [rsp+78h] [rbp+38h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+80h] [rbp+40h] BYREF

  v1 = -1;
  LODWORD(dwBytes) = 0;
  if ( BfspSystemPartitionName )
  {
    v3 = -1;
    do
      ++v3;
    while ( *((_WORD *)BfspSystemPartitionName + v3) );
    v4 = 2 * v3 + 2;
    ProcessHeap = GetProcessHeap();
    v6 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, v4);
    v7 = v6;
    if ( !v6 )
    {
LABEL_22:
      v9 = -1073741670;
      goto LABEL_23;
    }
    memcpy_0(v6, BfspSystemPartitionName, v4);
LABEL_11:
    if ( !a1 )
      return v7;
    pszDest = 0;
    dwBytes = 0;
    do
      ++v1;
    while ( v7[v1] );
    v13 = *v7;
    v14 = (unsigned int)v1 + (*v7 != 92) + 15;
    v15 = (unsigned int)v14;
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v14);
    if ( Heap )
    {
      v17 = StringCchCopyNExW(Heap, v15, L"\\\\?\\GLOBALROOT", 0xEu, &pszDest, &dwBytes, v25);
      v18 = v17;
      if ( v17 >= 0 )
      {
        if ( v13 == 92
          || (v19 = StringCchCopyNExW(pszDest, dwBytes, L"\\", 1u, &pszDest, &dwBytes, v26), v18 = v19, v19 >= 0) )
        {
          v20 = StringCchCopyNW(pszDest, dwBytes, v7, (unsigned int)v1);
          v18 = v20;
          if ( v20 >= 0 )
          {
            NtCurrentTeb()->LastErrorValue = 0;
            v21 = GetProcessHeap();
            HeapFree(v21, 0, v7);
            return Heap;
          }
        }
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      NtCurrentTeb()->LastErrorValue = v18;
    }
    else
    {
      NtCurrentTeb()->LastErrorValue = 8;
    }
    goto LABEL_22;
  }
  SystemPartition = SyspartGetSystemPartition(0);
  v9 = SystemPartition;
  if ( SystemPartition != -1073741789 )
  {
    v7 = 0;
    if ( SystemPartition >= 0 )
      v9 = -1073741823;
    goto LABEL_23;
  }
  v10 = dwBytes;
  v11 = GetProcessHeap();
  v12 = (wchar_t *)HeapAlloc(v11, 8u, v10);
  v7 = v12;
  if ( !v12 )
    goto LABEL_22;
  v9 = SyspartGetSystemPartition(v12);
  if ( v9 >= 0 )
    goto LABEL_11;
LABEL_23:
  BfspLogMessage(4, L"Failed to get partition name. Status = %#x", (unsigned int)v9);
  if ( v7 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v7);
  }
  v23 = RtlNtStatusToDosError(v9);
  SetLastError(v23);
  return 0;
}

```

## disassembly

```asm
0x140002c14  mov     [rsp-28h+arg_0], rbx
0x140002c19  mov     [rsp-28h+arg_18], rsi
0x140002c1e  push    rbp
0x140002c1f  push    rdi
0x140002c20  push    r12
0x140002c22  push    r13
0x140002c24  push    r14
0x140002c26  mov     rbp, rsp
0x140002c29  sub     rsp, 40h
0x140002c2d  mov     rdx, cs:BfspSystemPartitionName
0x140002c34  xor     r13d, r13d
0x140002c37  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140002c3b  mov     dword ptr [rbp+dwBytes], r13d
0x140002c3f  mov     r12b, cl
0x140002c42  mov     r14d, r13d
0x140002c45  test    rdx, rdx
0x140002c48  jz      short loc_140002C95
0x140002c4a  mov     rax, rsi
0x140002c4d  inc     rax
0x140002c50  cmp     [rdx+rax*2], r13w
0x140002c55  jnz     short loc_140002C4D
0x140002c57  lea     edi, ds:2[rax*2]
0x140002c5e  call    cs:__imp_GetProcessHeap
0x140002c64  mov     r8d, edi; dwBytes
0x140002c67  mov     edx, 8; dwFlags
0x140002c6c  mov     rcx, rax; hHeap
0x140002c6f  call    cs:__imp_HeapAlloc
0x140002c75  mov     rbx, rax
0x140002c78  test    rax, rax
0x140002c7b  jz      loc_140002E46
0x140002c81  mov     rdx, cs:BfspSystemPartitionName; Src
0x140002c88  mov     r8d, edi; Size
0x140002c8b  mov     rcx, rax; void *
0x140002c8e  call    memcpy_0
0x140002c93  jmp     short loc_140002CFF
0x140002c95  lea     r8, [rbp+dwBytes]
0x140002c99  xor     edx, edx
0x140002c9b  xor     ecx, ecx; void *
0x140002c9d  call    SyspartGetSystemPartition
0x140002ca2  mov     edi, eax
0x140002ca4  cmp     eax, 0C0000023h
0x140002ca9  jz      short loc_140002CC0
0x140002cab  mov     rbx, r13
0x140002cae  test    eax, eax
0x140002cb0  js      loc_140002E4B
0x140002cb6  mov     edi, 0C0000001h
0x140002cbb  jmp     loc_140002E4B
0x140002cc0  mov     ebx, dword ptr [rbp+dwBytes]
0x140002cc3  call    cs:__imp_GetProcessHeap
0x140002cc9  mov     r8d, ebx; dwBytes
0x140002ccc  mov     edx, 8; dwFlags
0x140002cd1  mov     rcx, rax; hHeap
0x140002cd4  call    cs:__imp_HeapAlloc
0x140002cda  mov     rbx, rax
0x140002cdd  test    rax, rax
0x140002ce0  jz      loc_140002E46
0x140002ce6  mov     edx, dword ptr [rbp+dwBytes]
0x140002ce9  lea     r8, [rbp+dwBytes]
0x140002ced  mov     rcx, rax; void *
0x140002cf0  call    SyspartGetSystemPartition
0x140002cf5  mov     edi, eax
0x140002cf7  test    eax, eax
0x140002cf9  js      loc_140002E4B
0x140002cff  test    r12b, r12b
0x140002d02  jz      loc_140002EA4
0x140002d08  mov     [rbp+pszDest], r13
0x140002d0c  mov     [rbp+dwBytes], r13
0x140002d10  inc     rsi
0x140002d13  cmp     [rbx+rsi*2], r13w
0x140002d18  jnz     short loc_140002D10
0x140002d1a  movzx   r12d, word ptr [rbx]
0x140002d1e  mov     eax, r13d
0x140002d21  mov     ecx, 5Ch ; '\'
0x140002d26  mov     edx, 8; Flags
0x140002d2b  cmp     cx, r12w
0x140002d2f  mov     rcx, gs:60h
0x140002d38  setnz   al
0x140002d3b  add     eax, 0Fh
0x140002d3e  mov     rcx, [rcx+30h]; HeapHandle
0x140002d42  add     eax, esi
0x140002d44  mov     edi, eax
0x140002d46  lea     r8, [rax+rax]; Size
0x140002d4a  call    cs:__imp_RtlAllocateHeap
0x140002d50  mov     r14, rax
0x140002d53  test    rax, rax
0x140002d56  jnz     short loc_140002D6D
0x140002d58  mov     rax, gs:30h
0x140002d61  mov     dword ptr [rax+68h], 8
0x140002d68  jmp     loc_140002E43
0x140002d6d  lea     rax, [rbp+dwBytes]
0x140002d71  mov     r9d, 0Eh; cchToCopy
0x140002d77  mov     [rsp+40h+pcchRemaining], rax; pcchRemaining
0x140002d7c  lea     r8, aGlobalroot; "\\\\?\\GLOBALROOT"
0x140002d83  lea     rax, [rbp+pszDest]
0x140002d87  mov     rdx, rdi; cchDest
0x140002d8a  mov     rcx, r14; pszDest
0x140002d8d  mov     [rsp+40h+ppszDestEnd], rax; ppszDestEnd
0x140002d92  call    StringCchCopyNExW
0x140002d97  mov     edi, eax
0x140002d99  test    eax, eax
0x140002d9b  js      short loc_140002E1C
0x140002d9d  mov     eax, 5Ch ; '\'
0x140002da2  cmp     ax, r12w
0x140002da6  jz      short loc_140002DDA
0x140002da8  mov     rdx, [rbp+dwBytes]; cchDest
0x140002dac  lea     rax, [rbp+dwBytes]
0x140002db0  mov     rcx, [rbp+pszDest]; pszDest
0x140002db4  lea     r8, pszSrc; "\\"
0x140002dbb  mov     [rsp+40h+pcchRemaining], rax; pcchRemaining
0x140002dc0  mov     r9d, 1; cchToCopy
0x140002dc6  lea     rax, [rbp+pszDest]
0x140002dca  mov     [rsp+40h+ppszDestEnd], rax; ppszDestEnd
0x140002dcf  call    StringCchCopyNExW
0x140002dd4  mov     edi, eax
0x140002dd6  test    eax, eax
0x140002dd8  js      short loc_140002E1C
0x140002dda  mov     rdx, [rbp+dwBytes]; cchDest
0x140002dde  mov     r8, rbx; pszSrc
0x140002de1  mov     rcx, [rbp+pszDest]; pszDest
0x140002de5  mov     r9d, esi; cchToCopy
0x140002de8  call    StringCchCopyNW
0x140002ded  mov     edi, eax
0x140002def  test    eax, eax
0x140002df1  js      short loc_140002E1C
0x140002df3  mov     rax, gs:30h
0x140002dfc  mov     [rax+68h], r13d
0x140002e00  call    cs:__imp_GetProcessHeap
0x140002e06  mov     r8, rbx; lpMem
0x140002e09  xor     edx, edx; dwFlags
0x140002e0b  mov     rcx, rax; hHeap
0x140002e0e  call    cs:__imp_HeapFree
0x140002e14  mov     rbx, r14
0x140002e17  jmp     loc_140002EA4
0x140002e1c  mov     rcx, gs:60h
0x140002e25  mov     r8, r14; P
0x140002e28  xor     edx, edx; Flags
0x140002e2a  mov     rcx, [rcx+30h]; HeapHandle
0x140002e2e  call    cs:__imp_RtlFreeHeap
0x140002e34  mov     rax, gs:30h
0x140002e3d  movzx   ecx, di
0x140002e40  mov     [rax+68h], ecx
0x140002e43  mov     r14, r13
0x140002e46  mov     edi, 0C000009Ah
0x140002e4b  mov     r8d, edi
0x140002e4e  lea     rdx, aFailedToGetPar; "Failed to get partition name. Status = "...
0x140002e55  mov     ecx, 4
0x140002e5a  call    BfspLogMessage
0x140002e5f  test    r14, r14
0x140002e62  jz      short loc_140002E78
0x140002e64  call    cs:__imp_GetProcessHeap
0x140002e6a  mov     r8, r14; lpMem
0x140002e6d  xor     edx, edx; dwFlags
0x140002e6f  mov     rcx, rax; hHeap
0x140002e72  call    cs:__imp_HeapFree
0x140002e78  test    rbx, rbx
0x140002e7b  jz      short loc_140002E91
0x140002e7d  call    cs:__imp_GetProcessHeap
0x140002e83  mov     r8, rbx; lpMem
0x140002e86  xor     edx, edx; dwFlags
0x140002e88  mov     rcx, rax; hHeap
0x140002e8b  call    cs:__imp_HeapFree
0x140002e91  mov     ecx, edi; Status
0x140002e93  call    cs:__imp_RtlNtStatusToDosError
0x140002e99  mov     ecx, eax; dwErrCode
0x140002e9b  call    cs:__imp_SetLastError
0x140002ea1  mov     rbx, r13
0x140002ea4  lea     r11, [rsp+40h+var_s0]
0x140002ea9  mov     rax, rbx
0x140002eac  mov     rbx, [r11+30h]
0x140002eb0  mov     rsi, [r11+48h]
0x140002eb4  mov     rsp, r11
0x140002eb7  pop     r14
0x140002eb9  pop     r13
0x140002ebb  pop     r12
0x140002ebd  pop     rdi
0x140002ebe  pop     rbp
0x140002ebf  retn
```
