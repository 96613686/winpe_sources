# AggregateWaitHandle::GetSignaledHandle(void * *)

- ea: `0x1800298c8`
- end: `0x1800299b6`
- name: `?GetSignaledHandle@AggregateWaitHandle@@QEAAJPEAPEAX@Z`
- size: `238`
- prototype: `__int64 __fastcall(AggregateWaitHandle *__hidden this, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028500`
- `0x180028810`

## callees

- `0x18000c11c`
- `0x1800298c8`
- `0x18002bbd0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002993c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002993c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029983`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180029904`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180029904`

## pseudocode

```c
signed int __fastcall AggregateWaitHandle::GetSignaledHandle(AggregateWaitHandle *this, void **a2)
{
  void *v4; // rcx
  AggregateWaitHandle *v5; // rbx
  AggregateWaitHandle *i; // rax
  void *v7; // rcx
  const struct std::nothrow_t *v8; // rdx
  AggregateWaitHandle *v9; // rcx
  AggregateWaitHandle **v10; // rax
  signed int result; // eax
  DWORD v12; // [rsp+50h] [rbp+8h] BYREF
  AggregateWaitHandle *v13; // [rsp+60h] [rbp+18h] BYREF
  LPOVERLAPPED v14; // [rsp+68h] [rbp+20h] BYREF

  if ( !*((_QWORD *)this + 1) )
  {
LABEL_17:
    SipcFailFast(2147549183LL);
    JUMPOUT(0x1800299B5LL);
  }
  v4 = *(void **)this;
  *a2 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  if ( GetQueuedCompletionStatus(v4, &v12, (PULONG_PTR)&v13, &v14, 0) )
  {
    v5 = v13;
    for ( i = (AggregateWaitHandle *)*((_QWORD *)this + 3); ; i = *(AggregateWaitHandle **)i )
    {
      if ( i == (AggregateWaitHandle *)((char *)this + 24) )
        goto LABEL_17;
      if ( i == v13 )
        break;
    }
    v7 = (void *)*((_QWORD *)v13 + 3);
    *a2 = (void *)*((_QWORD *)v13 + 2);
    CloseHandle(v7);
    operator delete(*((PVOID *)this + 2), v8);
    v9 = *(AggregateWaitHandle **)v5;
    if ( *(AggregateWaitHandle **)(*(_QWORD *)v5 + 8LL) != v5
      || (v10 = (AggregateWaitHandle **)*((_QWORD *)v5 + 1), *v10 != v5) )
    {
      __fastfail(3u);
    }
    *v10 = v9;
    *((_QWORD *)v9 + 1) = v10;
    --*((_DWORD *)this + 10);
    result = 0;
    *((_QWORD *)this + 2) = v5;
  }
  else
  {
    result = GetLastError();
    if ( result == 258 )
    {
      return 1;
    }
    else if ( result > 0 )
    {
      return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800298c8  mov     rax, rsp
0x1800298cb  push    rbx
0x1800298cc  push    rsi
0x1800298cd  push    rdi
0x1800298ce  sub     rsp, 30h
0x1800298d2  xor     ebx, ebx
0x1800298d4  mov     rsi, rdx
0x1800298d7  mov     rdi, rcx
0x1800298da  cmp     [rcx+8], rbx
0x1800298de  jz      loc_1800299AB
0x1800298e4  mov     rcx, [rcx]; CompletionPort
0x1800298e7  lea     r9, [rax+20h]; lpOverlapped
0x1800298eb  mov     [rdx], rbx
0x1800298ee  lea     r8, [rax+18h]; lpCompletionKey
0x1800298f2  lea     rdx, [rax+8]; lpNumberOfBytesTransferred
0x1800298f6  mov     [rax+8], ebx
0x1800298f9  mov     [rax+18h], rbx
0x1800298fd  mov     [rax+20h], rbx
0x180029901  mov     [rax-28h], ebx
0x180029904  call    cs:__imp_GetQueuedCompletionStatus
0x18002990b  nop     dword ptr [rax+rax+00h]
0x180029910  test    eax, eax
0x180029912  jz      short loc_180029983
0x180029914  mov     rbx, [rsp+48h+arg_10]
0x180029919  lea     rcx, [rdi+18h]
0x18002991d  mov     rax, [rcx]
0x180029920  jmp     short loc_18002992A
0x180029922  cmp     rax, rbx
0x180029925  jz      short loc_180029931
0x180029927  mov     rax, [rax]
0x18002992a  cmp     rax, rcx
0x18002992d  jz      short loc_1800299AB
0x18002992f  jmp     short loc_180029922
0x180029931  mov     rax, [rbx+10h]
0x180029935  mov     rcx, [rbx+18h]; hObject
0x180029939  mov     [rsi], rax
0x18002993c  call    cs:__imp_CloseHandle
0x180029943  nop     dword ptr [rax+rax+00h]
0x180029948  mov     rcx, [rdi+10h]; P
0x18002994c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029951  mov     rcx, [rbx]
0x180029954  cmp     [rcx+8], rbx
0x180029958  jnz     short loc_18002997C
0x18002995a  mov     rax, [rbx+8]
0x18002995e  cmp     [rax], rbx
0x180029961  jnz     short loc_18002997C
0x180029963  mov     [rax], rcx
0x180029966  mov     [rcx+8], rax
0x18002996a  dec     dword ptr [rdi+28h]
0x18002996d  xor     eax, eax
0x18002996f  mov     [rdi+10h], rbx
0x180029973  add     rsp, 30h
0x180029977  pop     rdi
0x180029978  pop     rsi
0x180029979  pop     rbx
0x18002997a  retn
0x18002997c  mov     ecx, 3
0x180029981  int     29h; Win8: RtlFailFast(ecx)
0x180029983  call    cs:__imp_GetLastError
0x18002998a  nop     dword ptr [rax+rax+00h]
0x18002998f  cmp     eax, 102h
0x180029994  jnz     short loc_18002999D
0x180029996  mov     eax, 1
0x18002999b  jmp     short loc_180029973
0x18002999d  test    eax, eax
0x18002999f  jle     short loc_180029973
0x1800299a1  movzx   eax, ax
0x1800299a4  or      eax, 80070000h
0x1800299a9  jmp     short loc_180029973
0x1800299ab  mov     ecx, 8000FFFFh
0x1800299b0  call    SipcFailFast
```
