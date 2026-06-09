# s_NgcCtnrEnumCreateNode

- ea: `0x18000fae0`
- end: `0x18000fc53`
- name: `s_NgcCtnrEnumCreateNode`
- size: `371`
- prototype: `__int64 __fastcall(__int64, GUID *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x180006d40`
- `0x180007178`
- `0x180007bb4`
- `0x180007d34`
- `0x18000f9bc`
- `0x18000f9f4`
- `0x18000fae0`
- `0x180011ebc`
- `0x18001e020`

## string_xrefs

- `0x18000fb22`: `s_NgcCtnrEnumCreateNode`

## pseudocode

```c
__int64 __fastcall s_NgcCtnrEnumCreateNode(
        __int64 a1,
        GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  int v13; // [rsp+20h] [rbp-78h] BYREF
  int v14; // [rsp+24h] [rbp-74h] BYREF
  _QWORD *v15; // [rsp+28h] [rbp-70h] BYREF
  unsigned int v16; // [rsp+30h] [rbp-68h]
  _QWORD v17[3]; // [rsp+38h] [rbp-60h] BYREF
  char v18[32]; // [rsp+50h] [rbp-48h] BYREF

  v13 = 0;
  v14 = 0;
  strcpy(v18, "s_NgcCtnrEnumCreateNode");
  v17[0] = v18;
  v17[1] = &v14;
  v17[2] = &v13;
  lambda_0810e8e972dcfe4a5421cd3c076eb0ff_::operator()(v17);
  v14 = 1;
  v15 = v17;
  CTaskCounter::Increment();
  if ( a3 && a4 )
  {
    try
    {
      v9 = CNgcNode::Create(a2, a3, a4, a5);
    }
    catch ( std::bad_alloc )
    {
      v13 = -2147024882;
      WppTraceIndent(v10, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_0ac9f56a02303572f4a1c923568694e4_Traceguids,
          WPP_pszIndent);
      }
      v16 = v13;
      CTaskCounter::Decrement();
      WppTraceUnwinder__lambda_0810e8e972dcfe4a5421cd3c076eb0ff____::_WppTraceUnwinder__lambda_0810e8e972dcfe4a5421cd3c076eb0ff____(&v15);
      return v16;
    }
    v11 = v9;
    v13 = v9;
    if ( v9 < 0 )
    {
      CTaskCounter::Decrement();
      WppTraceUnwinder__lambda_0810e8e972dcfe4a5421cd3c076eb0ff____::_WppTraceUnwinder__lambda_0810e8e972dcfe4a5421cd3c076eb0ff____(&v15);
      return v11;
    }
    CTaskCounter::Decrement();
  }
  else
  {
    v13 = -2147024809;
    WppTraceIndent(v8, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_0ac9f56a02303572f4a1c923568694e4_Traceguids, WPP_pszIndent);
    }
    v11 = v13;
    CTaskCounter::Decrement();
  }
  WppTraceUnwinder__lambda_0810e8e972dcfe4a5421cd3c076eb0ff____::_WppTraceUnwinder__lambda_0810e8e972dcfe4a5421cd3c076eb0ff____(&v15);
  return v11;
}

```

## disassembly

```asm
0x18000fae0  mov     r11, rsp
0x18000fae3  mov     [r11+8], rbx
0x18000fae7  push    rsi
0x18000fae8  push    rdi
0x18000fae9  push    r14
0x18000faeb  sub     rsp, 80h
0x18000faf2  mov     rax, cs:__security_cookie
0x18000faf9  xor     rax, rsp
0x18000fafc  mov     [rsp+98h+var_28], rax
0x18000fb01  mov     rbx, r9
0x18000fb04  mov     rdi, r8
0x18000fb07  mov     rsi, rdx
0x18000fb0a  mov     r14, [rsp+98h+arg_20]
0x18000fb12  mov     [rsp+98h+var_78], 0
0x18000fb1a  mov     [rsp+98h+var_74], 0
0x18000fb22  movups  xmm0, xmmword ptr cs:aSNgcctnrenumcr; "s_NgcCtnrEnumCreateNode"
0x18000fb29  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x18000fb2e  movsd   xmm1, qword ptr cs:aSNgcctnrenumcr+10h; "ateNode"
0x18000fb36  movsd   qword ptr [rsp+98h+var_48+10h], xmm1
0x18000fb3c  lea     rax, [r11-48h]
0x18000fb40  mov     [r11-60h], rax
0x18000fb44  lea     rax, [r11-74h]
0x18000fb48  mov     [r11-58h], rax
0x18000fb4c  lea     rax, [r11-78h]
0x18000fb50  mov     [r11-50h], rax
0x18000fb54  lea     rcx, [r11-60h]
0x18000fb58  call    _lambda_0810e8e972dcfe4a5421cd3c076eb0ff___operator__
0x18000fb5d  mov     [rsp+98h+var_74], 1
0x18000fb65  lea     rax, [rsp+98h+var_60]
0x18000fb6a  mov     [rsp+98h+var_70], rax
0x18000fb6f  call    ?Increment@CTaskCounter@@SAJXZ; CTaskCounter::Increment(void)
0x18000fb74  nop
0x18000fb75  test    rdi, rdi
0x18000fb78  jz      short loc_18000FBCF
0x18000fb7a  test    rbx, rbx
0x18000fb7d  jz      short loc_18000FBCF
0x18000fb7f  mov     r9, r14; unsigned __int16 *
0x18000fb82  mov     r8, rbx; unsigned __int16 *
0x18000fb85  mov     rdx, rdi; unsigned __int16 *
0x18000fb88  mov     rcx, rsi; rguid
0x18000fb8b  call    ?Create@CNgcNode@@SAJAEBU_GUID@@PEBG11@Z; CNgcNode::Create(_GUID const &,ushort const *,ushort const *,ushort const *)
0x18000fb90  mov     ebx, eax
0x18000fb92  mov     [rsp+98h+var_78], eax
0x18000fb96  test    eax, eax
0x18000fb98  jns     short loc_18000FBB1
0x18000fb9a  call    ?Decrement@CTaskCounter@@SAJXZ; CTaskCounter::Decrement(void)
0x18000fb9f  nop
0x18000fba0  lea     rcx, [rsp+98h+var_70]
0x18000fba5  call    WppTraceUnwinder__lambda_0810e8e972dcfe4a5421cd3c076eb0ff_______WppTraceUnwinder__lambda_0810e8e972dcfe4a5421cd3c076eb0ff____
0x18000fbaa  mov     eax, ebx
0x18000fbac  jmp     loc_18000FC32
0x18000fbb1  call    ?Decrement@CTaskCounter@@SAJXZ; CTaskCounter::Decrement(void)
0x18000fbb6  nop
0x18000fbb7  jmp     short loc_18000FC26
0x18000fbb9  call    ?Decrement@CTaskCounter@@SAJXZ; CTaskCounter::Decrement(void)
0x18000fbbe  nop
0x18000fbbf  lea     rcx, [rsp+98h+var_70]
0x18000fbc4  call    WppTraceUnwinder__lambda_0810e8e972dcfe4a5421cd3c076eb0ff_______WppTraceUnwinder__lambda_0810e8e972dcfe4a5421cd3c076eb0ff____
0x18000fbc9  mov     eax, [rsp+98h+var_68]
0x18000fbcd  jmp     short loc_18000FC32
0x18000fbcf  mov     [rsp+98h+var_78], 80070057h
0x18000fbd7  mov     edx, 2
0x18000fbdc  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000fbe1  lea     rax, WPP_GLOBAL_Control
0x18000fbe8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbef  cmp     rcx, rax
0x18000fbf2  jz      short loc_18000FC1C
0x18000fbf4  test    byte ptr [rcx+1Ch], 1
0x18000fbf8  jz      short loc_18000FC1C
0x18000fbfa  cmp     byte ptr [rcx+19h], 2
0x18000fbfe  jb      short loc_18000FC1C
0x18000fc00  mov     edx, 0Bh
0x18000fc05  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000fc0c  lea     r8, WPP_0ac9f56a02303572f4a1c923568694e4_Traceguids
0x18000fc13  mov     rcx, [rcx+10h]
0x18000fc17  call    WPP_SF_s
0x18000fc1c  mov     ebx, [rsp+98h+var_78]
0x18000fc20  call    ?Decrement@CTaskCounter@@SAJXZ; CTaskCounter::Decrement(void)
0x18000fc25  nop
0x18000fc26  lea     rcx, [rsp+98h+var_70]
0x18000fc2b  call    WppTraceUnwinder__lambda_0810e8e972dcfe4a5421cd3c076eb0ff_______WppTraceUnwinder__lambda_0810e8e972dcfe4a5421cd3c076eb0ff____
0x18000fc30  mov     eax, ebx
0x18000fc32  mov     rcx, [rsp+98h+var_28]
0x18000fc37  xor     rcx, rsp; StackCookie
0x18000fc3a  call    __security_check_cookie
0x18000fc3f  mov     rbx, [rsp+98h+arg_0]
0x18000fc47  add     rsp, 80h
0x18000fc4e  pop     r14
0x18000fc50  pop     rdi
0x18000fc51  pop     rsi
0x18000fc52  retn
```
