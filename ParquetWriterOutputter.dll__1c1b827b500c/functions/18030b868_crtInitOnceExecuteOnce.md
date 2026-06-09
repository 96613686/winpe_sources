# __crtInitOnceExecuteOnce

- ea: `0x18030b868`
- end: `0x18030b931`
- name: `__crtInitOnceExecuteOnce`
- size: `201`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1803072ac`
- `0x180307310`
- `0x1803073b4`
- `0x1803075dc`

## callees

- `0x18030b868`
- `0x180358070`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18030b927`
- `KERNEL32!SetLastError` at `0x18030b927`
- `KERNEL32!SwitchToThread` at `0x18030b8c5`
- `KERNEL32!SwitchToThread` at `0x18030b8c5`

## pseudocode

```c
__int64 __fastcall _crtInitOnceExecuteOnce(
        volatile signed __int64 *a1,
        unsigned int (__fastcall *a2)(volatile signed __int64 *, __int64, __int64),
        __int64 a3,
        __int64 a4)
{
  signed __int64 v9; // rax
  __int64 v10; // rdi
  unsigned int v11; // esi

  if ( _security_cookie != qword_1804C6728 )
    return ((__int64 (*)(void))(_security_cookie ^ qword_1804C6728))();
  v9 = _InterlockedCompareExchange64(a1, 1, 0);
  v10 = 2;
  while ( 1 )
  {
    if ( v9 == 2 )
      return 1;
    if ( !v9 )
      break;
    if ( v9 != 1 )
      goto LABEL_13;
    SwitchToThread();
    v9 = _InterlockedCompareExchange64(a1, 1, 0);
  }
  v11 = 1;
  if ( !a2(a1, a3, a4) )
  {
    v10 = 0;
    v11 = 0;
  }
  if ( _InterlockedExchange64(a1, v10) == 1 )
    return v11;
LABEL_13:
  SetLastError(0xDu);
  return 0;
}

```

## disassembly

```asm
0x18030b868  mov     rax, rsp
0x18030b86b  mov     [rax+8], rbx
0x18030b86f  mov     [rax+10h], rbp
0x18030b873  mov     [rax+18h], rsi
0x18030b877  mov     [rax+20h], rdi
0x18030b87b  push    r12
0x18030b87d  push    r14
0x18030b87f  push    r15
0x18030b881  sub     rsp, 30h
0x18030b885  mov     rax, cs:qword_1804C6728
0x18030b88c  mov     rbp, r9
0x18030b88f  xor     rax, cs:__security_cookie
0x18030b896  mov     r14, r8
0x18030b899  mov     r15, rdx
0x18030b89c  mov     rbx, rcx
0x18030b89f  jz      short loc_18030B8A9
0x18030b8a1  call    cs:__guard_dispatch_icall_fptr
0x18030b8a7  jmp     short loc_18030B8DA
0x18030b8a9  xor     eax, eax
0x18030b8ab  lea     r12d, [rax+1]
0x18030b8af  lock cmpxchg [rcx], r12
0x18030b8b4  lea     edi, [r12+1]
0x18030b8b9  jmp     short loc_18030B8D2
0x18030b8bb  test    rax, rax
0x18030b8be  jz      short loc_18030B8F9
0x18030b8c0  cmp     rax, r12
0x18030b8c3  jnz     short loc_18030B922
0x18030b8c5  call    cs:__imp_SwitchToThread
0x18030b8cb  xor     eax, eax
0x18030b8cd  lock cmpxchg [rbx], r12
0x18030b8d2  cmp     rax, rdi
0x18030b8d5  jnz     short loc_18030B8BB
0x18030b8d7  mov     eax, r12d
0x18030b8da  mov     rbx, [rsp+48h+arg_0]
0x18030b8df  mov     rbp, [rsp+48h+arg_8]
0x18030b8e4  mov     rsi, [rsp+48h+arg_10]
0x18030b8e9  mov     rdi, [rsp+48h+arg_18]
0x18030b8ee  add     rsp, 30h
0x18030b8f2  pop     r15
0x18030b8f4  pop     r14
0x18030b8f6  pop     r12
0x18030b8f8  retn
0x18030b8f9  mov     r8, rbp
0x18030b8fc  mov     rdx, r14
0x18030b8ff  mov     rcx, rbx
0x18030b902  mov     rax, r15
0x18030b905  mov     esi, r12d
0x18030b908  call    cs:__guard_dispatch_icall_fptr
0x18030b90e  test    eax, eax
0x18030b910  jnz     short loc_18030B916
0x18030b912  xor     edi, edi
0x18030b914  xor     esi, esi
0x18030b916  xchg    rdi, [rbx]
0x18030b919  cmp     rdi, r12
0x18030b91c  jnz     short loc_18030B922
0x18030b91e  mov     eax, esi
0x18030b920  jmp     short loc_18030B8DA
0x18030b922  mov     ecx, 0Dh; dwErrCode
0x18030b927  call    cs:__imp_SetLastError
0x18030b92d  xor     eax, eax
0x18030b92f  jmp     short loc_18030B8DA
```
