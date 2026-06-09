# _OutputStreamComAdapter::Write_::_1_::catch$1

- ea: `0x18002a8d8`
- end: `0x18002a964`
- name: `_OutputStreamComAdapter::Write_::_1_::catch$1`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000b29c`
- `0x1800196e4`
- `0x18002a8d8`

## pseudocode

```c
__int64 __fastcall OutputStreamComAdapter::Write_::_1_::catch_1(__int64 a1, __int64 a2)
{
  _DWORD *v3; // rax
  unsigned int v4; // eax

  v3 = *(_DWORD **)(a2 + 152);
  if ( v3 )
    *v3 = 0;
  *(_QWORD *)(a2 + 40) = &std::_Func_impl_no_alloc<_lambda_1f8670639bf19b12790a4956937d33a2_,void,>::`vftable';
  *(_QWORD *)(a2 + 48) = *(_QWORD *)(a2 + 32);
  *(_QWORD *)(a2 + 96) = a2 + 40;
  v4 = ErrorCodeFromCaughtExceptionInternal(a2 + 40);
  *(_DWORD *)(a2 + 144) = v4;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_1ee6ef310d5d3d7d4c053f70ad053783_Traceguids, v4);
  return 0;
}

```

## disassembly

```asm
0x18002a8d8  mov     [rsp+arg_8], rdx
0x18002a8dd  push    rbp
0x18002a8de  sub     rsp, 20h
0x18002a8e2  mov     rbp, rdx
0x18002a8e5  mov     rax, [rbp+98h]
0x18002a8ec  test    rax, rax
0x18002a8ef  jz      short loc_18002A8F7
0x18002a8f1  mov     dword ptr [rax], 0
0x18002a8f7  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1f8670639bf19b12790a4956937d33a2_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_1f8670639bf19b12790a4956937d33a2_,void,>::`vftable'
0x18002a8fe  mov     [rbp+28h], rax
0x18002a902  mov     rax, [rbp+20h]
0x18002a906  mov     [rbp+30h], rax
0x18002a90a  lea     rax, [rbp+28h]
0x18002a90e  mov     [rbp+60h], rax
0x18002a912  lea     rcx, [rbp+28h]
0x18002a916  call    ?ErrorCodeFromCaughtExceptionInternal@@YAJV?$function@$$A6AXXZ@std@@@Z; ErrorCodeFromCaughtExceptionInternal(std::function<void (void)>)
0x18002a91b  mov     [rbp+90h], eax
0x18002a921  lea     rdx, WPP_GLOBAL_Control
0x18002a928  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a92f  cmp     rcx, rdx
0x18002a932  jz      short loc_18002A953
0x18002a934  test    byte ptr [rcx+1Ch], 1
0x18002a938  jz      short loc_18002A953
0x18002a93a  mov     edx, 17h
0x18002a93f  mov     r9d, eax
0x18002a942  lea     r8, WPP_1ee6ef310d5d3d7d4c053f70ad053783_Traceguids
0x18002a949  mov     rcx, [rcx+10h]
0x18002a94d  call    WPP_SF_d
0x18002a952  nop
0x18002a953  mov     rax, 0
0x18002a95d  add     rsp, 20h
0x18002a961  pop     rbp
0x18002a962  retn
```
