# _anonymous_namespace_::_CopyExceptionObject

- ea: `0x180017abc`
- end: `0x180017b55`
- name: `_anonymous_namespace_::_CopyExceptionObject`
- size: `153`
- prototype: `void __fastcall(void *, _QWORD *, __int64, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180017788`
- `0x180017d9c`
- `0x18001f209`

## callees

- `0x180017aa0`
- `0x180017aac`
- `0x180017abc`
- `0x180019a84`
- `0x18001cdf0`
- `0x18001cf40`

## pseudocode

```c
void __fastcall anonymous_namespace_::_CopyExceptionObject(void *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  void *v7; // rsi
  void *v8; // r8

  if ( (*(_BYTE *)a3 & 1) != 0 || !*(_DWORD *)(a3 + 24) )
  {
    memmove(a1, a2, *(int *)(a3 + 20));
    if ( (*(_BYTE *)a3 & 8) != 0 && *a2 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 8LL))(*a2);
  }
  else
  {
    v7 = (void *)(a4 + *(int *)(a3 + 24));
    v8 = (void *)_AdjustPointer(a2, a3 + 8);
    if ( (*(_BYTE *)a3 & 4) != 0 )
      _CallMemberFunction2(a1, v7, v8, 1);
    else
      _CallMemberFunction1(a1, v7, v8);
  }
}

```

## disassembly

```asm
0x180017abc  mov     [rsp+arg_0], rbx
0x180017ac1  mov     [rsp+arg_8], rsi
0x180017ac6  mov     [rsp+arg_10], rdi
0x180017acb  push    r14
0x180017acd  sub     rsp, 20h
0x180017ad1  test    byte ptr [r8], 1
0x180017ad5  mov     rbx, r8
0x180017ad8  mov     r14, rdx
0x180017adb  mov     rdi, rcx
0x180017ade  jnz     short loc_180017B1C
0x180017ae0  cmp     dword ptr [r8+18h], 0
0x180017ae5  jz      short loc_180017B1C
0x180017ae7  movsxd  rsi, dword ptr [r8+18h]
0x180017aeb  lea     rdx, [r8+8]
0x180017aef  mov     rcx, r14
0x180017af2  add     rsi, r9
0x180017af5  call    __AdjustPointer
0x180017afa  test    byte ptr [rbx], 4
0x180017afd  mov     r8, rax; void *
0x180017b00  mov     rdx, rsi; void *
0x180017b03  mov     rcx, rdi; void *
0x180017b06  jz      short loc_180017B15
0x180017b08  mov     r9d, 1; int
0x180017b0e  call    ?_CallMemberFunction2@@YAXQEAX00H@Z; _CallMemberFunction2(void * const,void * const,void * const,int)
0x180017b13  jmp     short loc_180017B3F
0x180017b15  call    ?_CallMemberFunction1@@YAXQEAX00@Z; _CallMemberFunction1(void * const,void * const,void * const)
0x180017b1a  jmp     short loc_180017B3F
0x180017b1c  movsxd  r8, dword ptr [r8+14h]; Size
0x180017b20  call    memmove
0x180017b25  test    byte ptr [rbx], 8
0x180017b28  jz      short loc_180017B3F
0x180017b2a  mov     rcx, [r14]
0x180017b2d  test    rcx, rcx
0x180017b30  jz      short loc_180017B3F
0x180017b32  mov     rax, [rcx]
0x180017b35  mov     rax, [rax+8]
0x180017b39  call    cs:__guard_dispatch_icall_fptr
0x180017b3f  mov     rbx, [rsp+28h+arg_0]
0x180017b44  mov     rsi, [rsp+28h+arg_8]
0x180017b49  mov     rdi, [rsp+28h+arg_10]
0x180017b4e  add     rsp, 20h
0x180017b52  pop     r14
0x180017b54  retn
```
