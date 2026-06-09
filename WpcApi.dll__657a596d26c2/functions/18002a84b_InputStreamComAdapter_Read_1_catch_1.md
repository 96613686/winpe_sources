# _InputStreamComAdapter::Read_::_1_::catch$1

- ea: `0x18002a84b`
- end: `0x18002a8d2`
- name: `_InputStreamComAdapter::Read_::_1_::catch$1`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000b29c`
- `0x1800196e4`
- `0x18002a84b`

## pseudocode

```c
__int64 __fastcall InputStreamComAdapter::Read_::_1_::catch_1(__int64 a1, __int64 a2)
{
  unsigned int v3; // eax

  **(_DWORD **)(a2 + 152) = 0;
  *(_QWORD *)(a2 + 40) = &std::_Func_impl_no_alloc<_lambda_1f8670639bf19b12790a4956937d33a2_,void,>::`vftable';
  *(_QWORD *)(a2 + 48) = *(_QWORD *)(a2 + 32);
  *(_QWORD *)(a2 + 96) = a2 + 40;
  v3 = ErrorCodeFromCaughtExceptionInternal(a2 + 40);
  *(_DWORD *)(a2 + 144) = v3;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, WPP_1ee6ef310d5d3d7d4c053f70ad053783_Traceguids, v3);
  return 0;
}

```

## disassembly

```asm
0x18002a84b  mov     [rsp+arg_8], rdx
0x18002a850  push    rbp
0x18002a851  sub     rsp, 20h
0x18002a855  mov     rbp, rdx
0x18002a858  mov     rax, [rbp+98h]
0x18002a85f  mov     dword ptr [rax], 0
0x18002a865  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1f8670639bf19b12790a4956937d33a2_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_1f8670639bf19b12790a4956937d33a2_,void,>::`vftable'
0x18002a86c  mov     [rbp+28h], rax
0x18002a870  mov     rax, [rbp+20h]
0x18002a874  mov     [rbp+30h], rax
0x18002a878  lea     rax, [rbp+28h]
0x18002a87c  mov     [rbp+60h], rax
0x18002a880  lea     rcx, [rbp+28h]
0x18002a884  call    ?ErrorCodeFromCaughtExceptionInternal@@YAJV?$function@$$A6AXXZ@std@@@Z; ErrorCodeFromCaughtExceptionInternal(std::function<void (void)>)
0x18002a889  mov     [rbp+90h], eax
0x18002a88f  lea     rdx, WPP_GLOBAL_Control
0x18002a896  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a89d  cmp     rcx, rdx
0x18002a8a0  jz      short loc_18002A8C1
0x18002a8a2  test    byte ptr [rcx+1Ch], 1
0x18002a8a6  jz      short loc_18002A8C1
0x18002a8a8  mov     edx, 18h
0x18002a8ad  mov     r9d, eax
0x18002a8b0  lea     r8, WPP_1ee6ef310d5d3d7d4c053f70ad053783_Traceguids
0x18002a8b7  mov     rcx, [rcx+10h]
0x18002a8bb  call    WPP_SF_d
0x18002a8c0  nop
0x18002a8c1  mov     rax, 0
0x18002a8cb  add     rsp, 20h
0x18002a8cf  pop     rbp
0x18002a8d0  retn
```
