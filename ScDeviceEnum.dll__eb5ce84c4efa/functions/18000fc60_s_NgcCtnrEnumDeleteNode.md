# s_NgcCtnrEnumDeleteNode

- ea: `0x18000fc60`
- end: `0x18000fd44`
- name: `s_NgcCtnrEnumDeleteNode`
- size: `228`
- prototype: `__int64 __fastcall(__int64, GUID *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update`

## callees

- `0x180007bb4`
- `0x180007d34`
- `0x18000f9d8`
- `0x18000fa64`
- `0x18000fc60`
- `0x180012044`
- `0x18001e020`

## string_xrefs

- `0x18000fc8d`: `s_NgcCtnrEnumDeleteNode`

## pseudocode

```c
__int64 __fastcall s_NgcCtnrEnumDeleteNode(__int64 a1, GUID *a2)
{
  int v3; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-68h] BYREF
  int v8; // [rsp+24h] [rbp-64h] BYREF
  unsigned int v9; // [rsp+28h] [rbp-60h]
  _QWORD *v10; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v11[3]; // [rsp+38h] [rbp-50h] BYREF
  char v12[32]; // [rsp+50h] [rbp-38h] BYREF

  v7 = 0;
  v8 = 0;
  strcpy(v12, "s_NgcCtnrEnumDeleteNode");
  v11[0] = v12;
  v11[1] = &v8;
  v11[2] = &v7;
  lambda_130d449a869097cbd37301eaf37487bd_::operator()(v11);
  v8 = 1;
  v10 = v11;
  CTaskCounter::Increment();
  try
  {
    v3 = CNgcNode::Uninstall(a2);
  }
  catch ( std::bad_alloc )
  {
    v7 = -2147024882;
    WppTraceIndent(v4, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0ac9f56a02303572f4a1c923568694e4_Traceguids, WPP_pszIndent);
    }
    v9 = v7;
    CTaskCounter::Decrement();
    WppTraceUnwinder__lambda_130d449a869097cbd37301eaf37487bd____::_WppTraceUnwinder__lambda_130d449a869097cbd37301eaf37487bd____(&v10);
    return v9;
  }
  v3 = CNgcNode::Uninstall(a2);
  v7 = -2147024882;
  WppTraceIndent(v4, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0ac9f56a02303572f4a1c923568694e4_Traceguids, WPP_pszIndent);
  }
  v9 = v7;
}

```

## disassembly

```asm
0x18000fc60  mov     r11, rsp
0x18000fc63  push    rbx
0x18000fc64  sub     rsp, 80h
0x18000fc6b  mov     rax, cs:__security_cookie
0x18000fc72  xor     rax, rsp
0x18000fc75  mov     [rsp+88h+var_18], rax
0x18000fc7a  mov     rbx, rdx
0x18000fc7d  mov     [rsp+88h+var_68], 0
0x18000fc85  mov     [rsp+88h+var_64], 0
0x18000fc8d  movups  xmm0, xmmword ptr cs:aSNgcctnrenumde; "s_NgcCtnrEnumDeleteNode"
0x18000fc94  movups  xmmword ptr [rsp+88h+var_38], xmm0
0x18000fc99  movsd   xmm1, qword ptr cs:aSNgcctnrenumde+10h; "eteNode"
0x18000fca1  movsd   qword ptr [rsp+88h+var_38+10h], xmm1
0x18000fca7  lea     rax, [r11-38h]
0x18000fcab  mov     [r11-50h], rax
0x18000fcaf  lea     rax, [r11-64h]
0x18000fcb3  mov     [r11-48h], rax
0x18000fcb7  lea     rax, [r11-68h]
0x18000fcbb  mov     [r11-40h], rax
0x18000fcbf  lea     rcx, [r11-50h]
0x18000fcc3  call    _lambda_130d449a869097cbd37301eaf37487bd___operator__
0x18000fcc8  mov     [rsp+88h+var_64], 1
0x18000fcd0  lea     rax, [rsp+88h+var_50]
0x18000fcd5  mov     [rsp+88h+var_58], rax
0x18000fcda  call    ?Increment@CTaskCounter@@SAJXZ; CTaskCounter::Increment(void)
0x18000fcdf  nop
0x18000fce0  mov     rcx, rbx; rguid
0x18000fce3  call    ?Uninstall@CNgcNode@@SAJAEBU_GUID@@@Z; CNgcNode::Uninstall(_GUID const &)
0x18000fce8  mov     ebx, eax
0x18000fcea  mov     [rsp+88h+var_68], eax
0x18000fcee  test    eax, eax
0x18000fcf0  jns     short loc_18000FD06
0x18000fcf2  call    ?Decrement@CTaskCounter@@SAJXZ; CTaskCounter::Decrement(void)
0x18000fcf7  nop
0x18000fcf8  lea     rcx, [rsp+88h+var_58]
0x18000fcfd  call    WppTraceUnwinder__lambda_130d449a869097cbd37301eaf37487bd_______WppTraceUnwinder__lambda_130d449a869097cbd37301eaf37487bd____
0x18000fd02  mov     eax, ebx
0x18000fd04  jmp     short loc_18000FD2E
0x18000fd06  call    ?Decrement@CTaskCounter@@SAJXZ; CTaskCounter::Decrement(void)
0x18000fd0b  nop
0x18000fd0c  lea     rcx, [rsp+88h+var_58]
0x18000fd11  call    WppTraceUnwinder__lambda_130d449a869097cbd37301eaf37487bd_______WppTraceUnwinder__lambda_130d449a869097cbd37301eaf37487bd____
0x18000fd16  mov     eax, ebx
0x18000fd18  jmp     short loc_18000FD2E
0x18000fd1a  call    ?Decrement@CTaskCounter@@SAJXZ; CTaskCounter::Decrement(void)
0x18000fd1f  nop
0x18000fd20  lea     rcx, [rsp+88h+var_58]
0x18000fd25  call    WppTraceUnwinder__lambda_130d449a869097cbd37301eaf37487bd_______WppTraceUnwinder__lambda_130d449a869097cbd37301eaf37487bd____
0x18000fd2a  mov     eax, [rsp+88h+var_60]
0x18000fd2e  mov     rcx, [rsp+88h+var_18]
0x18000fd33  xor     rcx, rsp; StackCookie
0x18000fd36  call    __security_check_cookie
0x18000fd3b  add     rsp, 80h
0x18000fd42  pop     rbx
0x18000fd43  retn
```
