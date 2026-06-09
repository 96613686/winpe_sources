# s_TaskSchedulerFindScheduleClose

- ea: `0x180017710`
- end: `0x180017793`
- name: `s_TaskSchedulerFindScheduleClose`
- size: `131`
- prototype: `__int64 __fastcall(__int64, void ***, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000ea40`
- `0x180017710`
- `0x180020c30`

## import_xrefs

- `msvcrt!free` at `0x18001776a`
- `msvcrt!free` at `0x180017773`
- `msvcrt!free` at `0x18001776a`
- `msvcrt!free` at `0x180017773`

## pseudocode

```c
__int64 __fastcall s_TaskSchedulerFindScheduleClose(__int64 a1, void ***a2, __int64 a3)
{
  void **v4; // rbx
  _BYTE v6[16]; // [rsp+30h] [rbp-28h] BYREF

  if ( (byte_180030D03 & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, APIFindScheduleClose, a3, 1, v6);
  v4 = *a2;
  if ( !*a2 )
    return 2147942406LL;
  *a2 = 0;
  free(*v4);
  free(v4);
  return 0;
}

```

## disassembly

```asm
0x180017710  mov     [rsp+arg_0], rbx
0x180017715  push    rdi
0x180017716  sub     rsp, 50h
0x18001771a  mov     rax, cs:__security_cookie
0x180017721  xor     rax, rsp
0x180017724  mov     [rsp+58h+var_18], rax
0x180017729  test    cs:byte_180030D03, 10h
0x180017730  mov     rdi, rdx
0x180017733  jz      short loc_180017751
0x180017735  lea     rax, [rsp+58h+var_28]
0x18001773a  mov     r9d, 1
0x180017740  lea     rdx, APIFindScheduleClose
0x180017747  mov     [rsp+58h+var_38], rax
0x18001774c  call    McGenEventWrite_EventWriteTransfer
0x180017751  mov     rbx, [rdi]
0x180017754  test    rbx, rbx
0x180017757  jnz     short loc_180017760
0x180017759  mov     eax, 80070006h
0x18001775e  jmp     short loc_18001777B
0x180017760  mov     qword ptr [rdi], 0
0x180017767  mov     rcx, [rbx]; Block
0x18001776a  call    cs:__imp_free
0x180017770  mov     rcx, rbx; Block
0x180017773  call    cs:__imp_free
0x180017779  xor     eax, eax
0x18001777b  mov     rcx, [rsp+58h+var_18]
0x180017780  xor     rcx, rsp; StackCookie
0x180017783  call    __security_check_cookie
0x180017788  mov     rbx, [rsp+58h+arg_0]
0x18001778d  add     rsp, 50h
0x180017791  pop     rdi
0x180017792  retn
```
