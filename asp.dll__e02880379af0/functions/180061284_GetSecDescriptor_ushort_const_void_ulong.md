# GetSecDescriptor(ushort const *,void * *,ulong *)

- ea: `0x180061284`
- end: `0x1800613a9`
- name: `?GetSecDescriptor@@YAKPEBGPEAPEAXPEAK@Z`
- size: `293`
- prototype: `unsigned int __fastcall(LPCWSTR lpFileName, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005b984`

## callees

- `0x180023d86`
- `0x180061284`

## import_xrefs

- `ADVAPI32!GetFileSecurityW` at `0x18006133b`
- `ADVAPI32!GetFileSecurityW` at `0x18006133b`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180061348`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180061348`
- `KERNEL32!HeapReAlloc` at `0x180061313`
- `KERNEL32!HeapReAlloc` at `0x180061313`
- `KERNEL32!HeapFree` at `0x180061367`
- `KERNEL32!HeapFree` at `0x18006139a`
- `KERNEL32!HeapFree` at `0x180061367`
- `KERNEL32!HeapFree` at `0x18006139a`
- `KERNEL32!HeapAlloc` at `0x1800612b3`
- `KERNEL32!HeapAlloc` at `0x1800612b3`
- `KERNEL32!GetLastError` at `0x1800612ee`
- `KERNEL32!GetLastError` at `0x1800612ee`

## pseudocode

```c
__int64 __fastcall GetSecDescriptor(LPCWSTR lpFileName, void **a2, unsigned int *a3)
{
  void *v6; // rax
  void *v7; // rbp
  DWORD v8; // ebx
  BOOL i; // eax
  DWORD LastError; // eax
  DWORD v11; // ebx
  PSECURITY_DESCRIPTOR v12; // rbx
  void *v13; // rax
  DWORD v14; // r9d
  SIZE_T dwBytes; // [rsp+58h] [rbp+10h] BYREF

  LODWORD(dwBytes) = 0;
  v6 = HeapAlloc(g_hDenaliHeap, 0, *a3);
  *a2 = v6;
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  v8 = *a3;
  memset_0(v6, 0, *a3);
  for ( i = GetFileSecurityW(lpFileName, 7u, v7, v8, (LPDWORD)&dwBytes);
        ;
        i = GetFileSecurityW(lpFileName, 7u, v13, v14, (LPDWORD)&dwBytes) )
  {
    if ( i )
    {
      *a3 = GetSecurityDescriptorLength(*a2);
      return 0;
    }
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError != 122 )
    {
      if ( LastError && *a2 )
      {
        HeapFree(g_hDenaliHeap, 0, *a2);
        *a2 = 0;
      }
      return v11;
    }
    v12 = *a2;
    v13 = HeapReAlloc(g_hDenaliHeap, 0, *a2, (unsigned int)dwBytes);
    *a2 = v13;
    if ( !v13 )
      break;
    v14 = dwBytes;
    *a3 = dwBytes;
  }
  if ( v12 )
    HeapFree(g_hDenaliHeap, 0, v12);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180061284  mov     [rsp+arg_0], rbx
0x180061289  mov     [rsp+arg_10], rbp
0x18006128e  push    rsi
0x18006128f  push    rdi
0x180061290  push    r14
0x180061292  sub     rsp, 30h
0x180061296  mov     rsi, r8
0x180061299  mov     dword ptr [rsp+48h+dwBytes], 0
0x1800612a1  mov     r8d, [r8]; dwBytes
0x1800612a4  mov     rdi, rdx
0x1800612a7  mov     r14, rcx
0x1800612aa  xor     edx, edx; dwFlags
0x1800612ac  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x1800612b3  call    cs:__imp_HeapAlloc
0x1800612b9  mov     [rdi], rax
0x1800612bc  mov     rbp, rax
0x1800612bf  test    rax, rax
0x1800612c2  jz      loc_18006136D
0x1800612c8  mov     ebx, [rsi]
0x1800612ca  xor     edx, edx; Val
0x1800612cc  mov     r8d, ebx; Size
0x1800612cf  mov     rcx, rax; void *
0x1800612d2  call    memset_0
0x1800612d7  lea     rax, [rsp+48h+dwBytes]
0x1800612dc  mov     r8, rbp
0x1800612df  mov     [rsp+48h+lpnLengthNeeded], rax
0x1800612e4  mov     r9d, ebx
0x1800612e7  mov     ebp, 7
0x1800612ec  jmp     short loc_180061336
0x1800612ee  call    cs:__imp_GetLastError
0x1800612f4  mov     ebx, eax
0x1800612f6  cmp     eax, 7Ah ; 'z'
0x1800612f9  jnz     loc_180061385
0x1800612ff  mov     rbx, [rdi]
0x180061302  xor     edx, edx; dwFlags
0x180061304  mov     r9d, dword ptr [rsp+48h+dwBytes]; dwBytes
0x180061309  mov     r8, rbx; lpMem
0x18006130c  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180061313  call    cs:__imp_HeapReAlloc
0x180061319  mov     [rdi], rax
0x18006131c  test    rax, rax
0x18006131f  jz      short loc_180061356
0x180061321  mov     r9d, dword ptr [rsp+48h+dwBytes]; nLength
0x180061326  lea     rcx, [rsp+48h+dwBytes]
0x18006132b  mov     [rsp+48h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x180061330  mov     r8, rax; pSecurityDescriptor
0x180061333  mov     [rsi], r9d
0x180061336  mov     edx, ebp; RequestedInformation
0x180061338  mov     rcx, r14; lpFileName
0x18006133b  call    cs:__imp_GetFileSecurityW
0x180061341  test    eax, eax
0x180061343  jz      short loc_1800612EE
0x180061345  mov     rcx, [rdi]; pSecurityDescriptor
0x180061348  call    cs:__imp_GetSecurityDescriptorLength
0x18006134e  mov     [rsi], eax
0x180061350  xor     ebx, ebx
0x180061352  mov     eax, ebx
0x180061354  jmp     short loc_180061372
0x180061356  test    rbx, rbx
0x180061359  jz      short loc_18006136D
0x18006135b  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180061362  mov     r8, rbx; lpMem
0x180061365  xor     edx, edx; dwFlags
0x180061367  call    cs:__imp_HeapFree
0x18006136d  mov     eax, 8007000Eh
0x180061372  mov     rbx, [rsp+48h+arg_0]
0x180061377  mov     rbp, [rsp+48h+arg_10]
0x18006137c  add     rsp, 30h
0x180061380  pop     r14
0x180061382  pop     rdi
0x180061383  pop     rsi
0x180061384  retn
0x180061385  test    eax, eax
0x180061387  jz      short loc_180061352
0x180061389  mov     r8, [rdi]; lpMem
0x18006138c  test    r8, r8
0x18006138f  jz      short loc_180061352
0x180061391  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180061398  xor     edx, edx; dwFlags
0x18006139a  call    cs:__imp_HeapFree
0x1800613a0  mov     qword ptr [rdi], 0
0x1800613a7  jmp     short loc_180061352
```
