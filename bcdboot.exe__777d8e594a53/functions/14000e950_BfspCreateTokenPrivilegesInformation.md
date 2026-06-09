# BfspCreateTokenPrivilegesInformation

- ea: `0x14000e950`
- end: `0x14000ea44`
- name: `BfspCreateTokenPrivilegesInformation`
- size: `244`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, unsigned int **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140002928`
- `0x140009fd4`
- `0x14000c5e0`

## callees

- `0x14000e628`
- `0x14000e950`
- `0x1400265fa`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000ea3c`
- `KERNEL32!SetLastError` at `0x14000ea3c`
- `KERNEL32!GetLastError` at `0x14000ea0a`
- `KERNEL32!GetLastError` at `0x14000ea0a`
- `KERNEL32!HeapFree` at `0x14000ea34`
- `KERNEL32!HeapFree` at `0x14000ea34`
- `KERNEL32!HeapAlloc` at `0x14000e992`
- `KERNEL32!HeapAlloc` at `0x14000e992`
- `KERNEL32!GetProcessHeap` at `0x14000e97f`
- `KERNEL32!GetProcessHeap` at `0x14000ea26`
- `KERNEL32!GetProcessHeap` at `0x14000e97f`
- `KERNEL32!GetProcessHeap` at `0x14000ea26`
- `ADVAPI32!LookupPrivilegeValueW` at `0x14000e9d4`
- `ADVAPI32!LookupPrivilegeValueW` at `0x14000e9d4`

## pseudocode

```c
__int64 __fastcall BfspCreateTokenPrivilegesInformation(__int64 a1, unsigned int a2, int a3, unsigned int **a4)
{
  SIZE_T v8; // r14
  HANDLE ProcessHeap; // rax
  __int64 LastError; // rsi
  unsigned int *v11; // rax
  unsigned int *v12; // rdi
  unsigned int v13; // ebx
  __int64 v14; // rsi
  HANDLE v16; // rax

  v8 = 12LL * a2 + 4;
  ProcessHeap = GetProcessHeap();
  LODWORD(LastError) = 8;
  v11 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, v8);
  v12 = v11;
  if ( !v11 )
  {
    v13 = 0;
LABEL_11:
    SetLastError(LastError);
    return v13;
  }
  v13 = 1;
  memset_0(v11, 0, v8);
  v14 = 0;
  *v12 = a2;
  if ( a2 )
  {
    while ( 1 )
    {
      v13 = LookupPrivilegeValueW(0, *(LPCWSTR *)(a1 + 8 * v14), (PLUID)&v12[3 * v14 + 1]);
      if ( !v13 )
        break;
      if ( a3 )
        v12[3 * v14 + 3] = 2;
      v14 = (unsigned int)(v14 + 1);
      if ( (unsigned int)v14 >= a2 )
        goto LABEL_8;
    }
    LastError = GetLastError();
    BfspLogMessage(4, L"Failed to lookup privelege! Error code = %#x", LastError);
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v12);
    goto LABEL_11;
  }
LABEL_8:
  *a4 = v12;
  return v13;
}

```

## disassembly

```asm
0x14000e950  push    rbx
0x14000e952  push    rbp
0x14000e953  push    rsi
0x14000e954  push    rdi
0x14000e955  push    r12
0x14000e957  push    r13
0x14000e959  push    r14
0x14000e95b  push    r15
0x14000e95d  sub     rsp, 28h
0x14000e961  mov     ebp, edx
0x14000e963  mov     r15, r9
0x14000e966  mov     r12d, r8d
0x14000e969  mov     r13, rcx
0x14000e96c  lea     r10, ds:0[rbp*2]
0x14000e974  add     r10, rbp
0x14000e977  lea     r14, ds:4[r10*4]
0x14000e97f  call    cs:__imp_GetProcessHeap
0x14000e985  mov     esi, 8
0x14000e98a  mov     r8, r14; dwBytes
0x14000e98d  mov     rcx, rax; hHeap
0x14000e990  mov     edx, esi; dwFlags
0x14000e992  call    cs:__imp_HeapAlloc
0x14000e998  mov     rdi, rax
0x14000e99b  test    rax, rax
0x14000e99e  jnz     short loc_14000E9A7
0x14000e9a0  xor     ebx, ebx
0x14000e9a2  jmp     loc_14000EA3A
0x14000e9a7  mov     r8, r14; Size
0x14000e9aa  xor     edx, edx; Val
0x14000e9ac  mov     rcx, rdi; void *
0x14000e9af  mov     ebx, 1
0x14000e9b4  call    memset_0
0x14000e9b9  xor     esi, esi
0x14000e9bb  mov     [rdi], ebp
0x14000e9bd  test    ebp, ebp
0x14000e9bf  jz      short loc_14000E9F4
0x14000e9c1  mov     rdx, [r13+rsi*8+0]; lpName
0x14000e9c6  lea     r14, [rsi+rsi*2]
0x14000e9ca  lea     r8, [rdi+4]
0x14000e9ce  xor     ecx, ecx; lpSystemName
0x14000e9d0  lea     r8, [r8+r14*4]; lpLuid
0x14000e9d4  call    cs:__imp_LookupPrivilegeValueW
0x14000e9da  mov     ebx, eax
0x14000e9dc  test    eax, eax
0x14000e9de  jz      short loc_14000EA0A
0x14000e9e0  test    r12d, r12d
0x14000e9e3  jz      short loc_14000E9EE
0x14000e9e5  mov     dword ptr [rdi+r14*4+0Ch], 2
0x14000e9ee  inc     esi
0x14000e9f0  cmp     esi, ebp
0x14000e9f2  jb      short loc_14000E9C1
0x14000e9f4  mov     [r15], rdi
0x14000e9f7  mov     eax, ebx
0x14000e9f9  add     rsp, 28h
0x14000e9fd  pop     r15
0x14000e9ff  pop     r14
0x14000ea01  pop     r13
0x14000ea03  pop     r12
0x14000ea05  pop     rdi
0x14000ea06  pop     rsi
0x14000ea07  pop     rbp
0x14000ea08  pop     rbx
0x14000ea09  retn
0x14000ea0a  call    cs:__imp_GetLastError
0x14000ea10  lea     rdx, aFailedToLookup; "Failed to lookup privelege! Error code "...
0x14000ea17  mov     ecx, 4
0x14000ea1c  mov     r8d, eax
0x14000ea1f  mov     esi, eax
0x14000ea21  call    BfspLogMessage
0x14000ea26  call    cs:__imp_GetProcessHeap
0x14000ea2c  mov     r8, rdi; lpMem
0x14000ea2f  xor     edx, edx; dwFlags
0x14000ea31  mov     rcx, rax; hHeap
0x14000ea34  call    cs:__imp_HeapFree
0x14000ea3a  mov     ecx, esi; dwErrCode
0x14000ea3c  call    cs:__imp_SetLastError
0x14000ea42  jmp     short loc_14000E9F7
```
