# RefreshNgcReadersWorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18002c2e0`
- end: `0x18002c3be`
- name: `?RefreshNgcReadersWorkCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `222`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800075d0`
- `0x18002ac04`
- `0x18002b68c`
- `0x18002ba94`
- `0x18002c2e0`
- `0x1800316ec`
- `0x1800326d0`

## string_xrefs

- `0x18002c308`: `RefreshNgcReadersWorkCallback`

## pseudocode

```c
void __fastcall RefreshNgcReadersWorkCallback(struct _TP_CALLBACK_INSTANCE *a1, void *a2, struct _TP_WORK *a3)
{
  __int64 v3; // rcx
  int v4; // r9d
  int refreshed; // [rsp+30h] [rbp-50h] BYREF
  int v6; // [rsp+34h] [rbp-4Ch] BYREF
  _QWORD *v7; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v8[3]; // [rsp+40h] [rbp-40h] BYREF
  char v9[32]; // [rsp+58h] [rbp-28h] BYREF

  refreshed = 0;
  v6 = 0;
  strcpy(v9, "RefreshNgcReadersWorkCallback");
  v8[0] = v9;
  v8[1] = &v6;
  v8[2] = &refreshed;
  lambda_856a491d998011380f5c2b94645666e8_::operator()(v8, a2, a3);
  v6 = 1;
  v7 = v8;
  refreshed = GidsHandlerRpcRefreshContainerNodes();
  if ( refreshed < 0 )
  {
    WppTraceIndent(v3, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_e4afa8abd0dc3368f31b1529e373d2c2_Traceguids,
        v4,
        refreshed);
    }
  }
  WppTraceUnwinder__lambda_856a491d998011380f5c2b94645666e8____::_WppTraceUnwinder__lambda_856a491d998011380f5c2b94645666e8____(&v7);
}

```

## disassembly

```asm
0x18002c2e0  push    rbp
0x18002c2e2  mov     rbp, rsp
0x18002c2e5  sub     rsp, 80h
0x18002c2ec  mov     rax, cs:__security_cookie
0x18002c2f3  xor     rax, rsp
0x18002c2f6  mov     [rbp+var_8], rax
0x18002c2fa  mov     [rbp+var_50], 0
0x18002c301  mov     [rbp+var_4C], 0
0x18002c308  movups  xmm0, xmmword ptr cs:aRefreshngcread; "RefreshNgcReadersWorkCallback"
0x18002c30f  movups  xmmword ptr [rbp+var_28], xmm0
0x18002c313  movups  xmm1, xmmword ptr cs:aRefreshngcread+0Eh; "ersWorkCallback"
0x18002c31a  movups  xmmword ptr [rbp+var_28+0Eh], xmm1
0x18002c31e  lea     rax, [rbp+var_28]
0x18002c322  mov     [rbp+var_40], rax
0x18002c326  lea     rax, [rbp+var_4C]
0x18002c32a  mov     [rbp+var_38], rax
0x18002c32e  lea     rax, [rbp+var_50]
0x18002c332  mov     [rbp+var_30], rax
0x18002c336  lea     rcx, [rbp+var_40]
0x18002c33a  call    _lambda_856a491d998011380f5c2b94645666e8___operator__
0x18002c33f  mov     [rbp+var_4C], 1
0x18002c346  lea     rax, [rbp+var_40]
0x18002c34a  mov     [rbp+var_48], rax
0x18002c34e  call    ?GidsHandlerRpcRefreshContainerNodes@@YAJXZ; GidsHandlerRpcRefreshContainerNodes(void)
0x18002c353  mov     [rbp+var_50], eax
0x18002c356  test    eax, eax
0x18002c358  jns     short loc_18002C3A0
0x18002c35a  mov     edx, 2
0x18002c35f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c364  lea     rax, WPP_GLOBAL_Control
0x18002c36b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c372  cmp     rcx, rax
0x18002c375  jz      short loc_18002C3A0
0x18002c377  test    byte ptr [rcx+1Ch], 1
0x18002c37b  jz      short loc_18002C3A0
0x18002c37d  cmp     byte ptr [rcx+19h], 3
0x18002c381  jb      short loc_18002C3A0
0x18002c383  mov     edx, 0Bh
0x18002c388  mov     eax, [rbp+var_50]
0x18002c38b  mov     [rsp+80h+var_60], eax
0x18002c38f  lea     r8, WPP_e4afa8abd0dc3368f31b1529e373d2c2_Traceguids
0x18002c396  mov     rcx, [rcx+10h]
0x18002c39a  call    WPP_SF_sd
0x18002c39f  nop
0x18002c3a0  lea     rcx, [rbp+var_48]
0x18002c3a4  call    WppTraceUnwinder__lambda_856a491d998011380f5c2b94645666e8_______WppTraceUnwinder__lambda_856a491d998011380f5c2b94645666e8____
0x18002c3a9  mov     rcx, [rbp+var_8]
0x18002c3ad  xor     rcx, rsp; StackCookie
0x18002c3b0  call    __security_check_cookie
0x18002c3b5  add     rsp, 80h
0x18002c3bc  pop     rbp
0x18002c3bd  retn
```
