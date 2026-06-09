# _CNgcNode::_DeviceCreateCallback_::_1_::catch$3

- ea: `0x18001f2d3`
- end: `0x18001f345`
- name: `_CNgcNode::_DeviceCreateCallback_::_1_::catch$3`
- size: `114`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006d40`
- `0x1800071d4`
- `0x18001f2d3`

## pseudocode

```c
__int64 __fastcall CNgcNode::_DeviceCreateCallback_::_1_::catch_3(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = -2147024882;
  WppTraceIndent(a1, 2u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      (unsigned int)&WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids,
      (_DWORD)WPP_pszIndent,
      *(_DWORD *)(a2 + 48));
  }
  return 0;
}

```

## disassembly

```asm
0x18001f2d3  mov     [rsp+arg_8], rdx
0x18001f2d8  push    rbp
0x18001f2d9  sub     rsp, 30h
0x18001f2dd  mov     rbp, rdx
0x18001f2e0  mov     dword ptr [rbp+30h], 8007000Eh
0x18001f2e7  mov     edx, 2
0x18001f2ec  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001f2f1  lea     rax, WPP_GLOBAL_Control
0x18001f2f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2ff  cmp     rcx, rax
0x18001f302  jz      short loc_18001F334
0x18001f304  test    byte ptr [rcx+1Ch], 1
0x18001f308  jz      short loc_18001F334
0x18001f30a  cmp     byte ptr [rcx+19h], 2
0x18001f30e  jb      short loc_18001F334
0x18001f310  mov     edx, 1Fh
0x18001f315  mov     eax, [rbp+30h]
0x18001f318  mov     [rsp+38h+var_18], eax
0x18001f31c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001f323  lea     r8, WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids
0x18001f32a  mov     rcx, [rcx+10h]
0x18001f32e  call    WPP_SF_sd
0x18001f333  nop
0x18001f334  mov     rax, 0
0x18001f33e  add     rsp, 30h
0x18001f342  pop     rbp
0x18001f343  retn
```
