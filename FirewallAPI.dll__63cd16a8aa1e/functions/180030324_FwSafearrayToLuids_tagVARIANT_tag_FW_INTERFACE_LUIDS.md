# FwSafearrayToLuids(tagVARIANT,_tag_FW_INTERFACE_LUIDS *)

- ea: `0x180030324`
- end: `0x180030634`
- name: `?FwSafearrayToLuids@@YAJUtagVARIANT@@PEAU_tag_FW_INTERFACE_LUIDS@@@Z`
- size: `784`
- prototype: `__int64 __fastcall(struct tagVARIANT *__struct_ptr, struct _tag_FW_INTERFACE_LUIDS *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180026b00`
- `0x18003ec90`

## callees

- `0x180005954`
- `0x1800277b0`
- `0x18002f8dc`
- `0x18002fa00`
- `0x180030324`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180030450`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180030450`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18003040a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18003040a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003049b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003049b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800305af`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800305af`
- `fwbase!FwBaseFree` at `0x1800305ee`
- `fwbase!FwBaseFree` at `0x180030603`
- `fwbase!FwBaseFree` at `0x1800305ee`
- `fwbase!FwBaseFree` at `0x180030603`
- `fwbase!FwArrayAppend` at `0x180030558`
- `fwbase!FwArrayAppend` at `0x180030558`
- `FWPolicyIOMgr!FwCopyLUID` at `0x180030545`

## pseudocode

```c
__int64 __fastcall FwSafearrayToLuids(struct tagVARIANT *a1, struct _tag_FW_INTERFACE_LUIDS *a2)
{
  int Adapters; // ebx
  __int64 v4; // r9
  FwPolicy2 *v5; // rcx
  __int64 v6; // rdx
  SAFEARRAY *parray; // r14
  HRESULT LBound; // eax
  FwPolicy2 *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  LONG i; // r15d
  int v13; // eax
  HRESULT v14; // eax
  struct _IP_ADAPTER_ADDRESSES_LH *v16; // [rsp+20h] [rbp-30h] BYREF
  void *ppvData; // [rsp+28h] [rbp-28h] BYREF
  LONG plLbound; // [rsp+30h] [rbp-20h] BYREF
  LONG plUbound; // [rsp+34h] [rbp-1Ch] BYREF
  struct _GUID v20; // [rsp+38h] [rbp-18h] BYREF

  v16 = 0;
  v20 = GUID_NULL;
  plLbound = 0;
  plUbound = 0;
  ppvData = 0;
  *(_OWORD *)a2 = 0;
  if ( !a1->vt )
    return 0;
  if ( a1->vt != 8204 )
  {
    v4 = 2147942487LL;
    Adapters = -2147024809;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_50;
    v6 = 37;
LABEL_7:
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, v4);
LABEL_50:
    if ( *((_QWORD *)a2 + 1) )
      FwBaseFree(a2);
    *(_OWORD *)a2 = 0;
    return (unsigned int)Adapters;
  }
  parray = a1->parray;
  if ( !parray )
  {
    v4 = 2147942487LL;
    Adapters = -2147024809;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_50;
    v6 = 38;
    goto LABEL_7;
  }
  LBound = SafeArrayGetLBound(a1->parray, 1u, &plLbound);
  Adapters = LBound;
  if ( LBound < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_50;
    v6 = 39;
    goto LABEL_16;
  }
  LBound = SafeArrayGetUBound(parray, 1u, &plUbound);
  Adapters = LBound;
  if ( LBound < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_50;
    v6 = 40;
    goto LABEL_16;
  }
  if ( plUbound - plLbound + 1 <= 0 )
    return 0;
  LBound = SafeArrayAccessData(parray, &ppvData);
  Adapters = LBound;
  if ( LBound < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_50;
    v6 = 41;
LABEL_16:
    v4 = (unsigned int)LBound;
    goto LABEL_7;
  }
  Adapters = FwGetAdapters(&v16);
  if ( Adapters >= 0 )
  {
    for ( i = plLbound; ; ++i )
    {
      if ( i > plUbound )
        goto LABEL_43;
      v13 = FwInterfaceNameToLuid(v16, *((unsigned __int16 *const *)ppvData + 3 * i + 1), &v20);
      Adapters = v13;
      if ( v13 < 0 )
        break;
      v13 = FwArrayAppend(16, FwCopyLUID, a2, &v20);
      Adapters = v13;
      if ( v13 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 44;
LABEL_41:
          v11 = (unsigned int)v13;
          goto LABEL_42;
        }
        goto LABEL_43;
      }
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 43;
      goto LABEL_41;
    }
  }
  else
  {
    Adapters = -2147418113;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 42;
      v11 = 2147549183LL;
LABEL_42:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, v11);
    }
  }
LABEL_43:
  v14 = SafeArrayUnaccessData(parray);
  if ( v14 < 0
    && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids,
      (unsigned int)v14);
  }
  if ( v16 )
    FwBaseFree(v16);
  if ( Adapters < 0 )
    goto LABEL_50;
  return (unsigned int)Adapters;
}

```

## disassembly

```asm
0x180030324  mov     [rsp-28h+arg_10], rbx
0x180030329  push    rbp
0x18003032a  push    rsi
0x18003032b  push    r12
0x18003032d  push    r14
0x18003032f  push    r15
0x180030331  mov     rbp, rsp
0x180030334  sub     rsp, 50h
0x180030338  mov     rax, cs:__security_cookie
0x18003033f  xor     rax, rsp
0x180030342  mov     [rbp+var_8], rax
0x180030346  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003034d  xor     esi, esi
0x18003034f  mov     r12, rdx
0x180030352  xorps   xmm1, xmm1
0x180030355  mov     [rbp+var_30], rsi
0x180030359  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x18003035e  mov     [rbp+plLbound], esi
0x180030361  mov     [rbp+plUbound], esi
0x180030364  mov     [rbp+ppvData], rsi
0x180030368  movups  xmmword ptr [rdx], xmm1
0x18003036b  cmp     [rcx], si
0x18003036e  jnz     short loc_180030377
0x180030370  mov     ebx, esi
0x180030372  jmp     loc_180030611
0x180030377  mov     eax, 200Ch
0x18003037c  cmp     [rcx], ax
0x18003037f  jz      short loc_1800303C5
0x180030381  mov     r9d, 80070057h
0x180030387  mov     ebx, r9d
0x18003038a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030391  lea     rsi, WPP_GLOBAL_Control
0x180030398  cmp     rcx, rsi
0x18003039b  jz      loc_1800305F8
0x1800303a1  test    byte ptr [rcx+1Ch], 1
0x1800303a5  jz      loc_1800305F8
0x1800303ab  mov     edx, 25h ; '%'
0x1800303b0  mov     rcx, [rcx+10h]
0x1800303b4  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x1800303bb  call    WPP_SF_d
0x1800303c0  jmp     loc_1800305F8
0x1800303c5  mov     r14, [rcx+8]
0x1800303c9  test    r14, r14
0x1800303cc  jnz     short loc_1800303FE
0x1800303ce  mov     r9d, 80070057h
0x1800303d4  mov     ebx, r9d
0x1800303d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800303de  lea     rsi, WPP_GLOBAL_Control
0x1800303e5  cmp     rcx, rsi
0x1800303e8  jz      loc_1800305F8
0x1800303ee  test    byte ptr [rcx+1Ch], 1
0x1800303f2  jz      loc_1800305F8
0x1800303f8  lea     edx, [r14+26h]
0x1800303fc  jmp     short loc_1800303B0
0x1800303fe  lea     r8, [rbp+plLbound]; plLbound
0x180030402  mov     edx, 1; nDim
0x180030407  mov     rcx, r14; psa
0x18003040a  call    cs:__imp_SafeArrayGetLBound
0x180030410  mov     ebx, eax
0x180030412  test    eax, eax
0x180030414  jns     short loc_180030444
0x180030416  mov     rcx, cs:WPP_GLOBAL_Control
0x18003041d  lea     rsi, WPP_GLOBAL_Control
0x180030424  cmp     rcx, rsi
0x180030427  jz      loc_1800305F8
0x18003042d  test    byte ptr [rcx+1Ch], 1
0x180030431  jz      loc_1800305F8
0x180030437  mov     edx, 27h ; '''
0x18003043c  mov     r9d, eax
0x18003043f  jmp     loc_1800303B0
0x180030444  lea     r8, [rbp+plUbound]; plUbound
0x180030448  mov     edx, 1; nDim
0x18003044d  mov     rcx, r14; psa
0x180030450  call    cs:__imp_SafeArrayGetUBound
0x180030456  mov     ebx, eax
0x180030458  test    eax, eax
0x18003045a  jns     short loc_180030484
0x18003045c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030463  lea     rsi, WPP_GLOBAL_Control
0x18003046a  cmp     rcx, rsi
0x18003046d  jz      loc_1800305F8
0x180030473  test    byte ptr [rcx+1Ch], 1
0x180030477  jz      loc_1800305F8
0x18003047d  mov     edx, 28h ; '('
0x180030482  jmp     short loc_18003043C
0x180030484  mov     eax, [rbp+plUbound]
0x180030487  sub     eax, [rbp+plLbound]
0x18003048a  inc     eax
0x18003048c  test    eax, eax
0x18003048e  jle     loc_180030370
0x180030494  lea     rdx, [rbp+ppvData]; ppvData
0x180030498  mov     rcx, r14; psa
0x18003049b  call    cs:__imp_SafeArrayAccessData
0x1800304a1  mov     ebx, eax
0x1800304a3  test    eax, eax
0x1800304a5  jns     short loc_1800304D2
0x1800304a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800304ae  lea     rsi, WPP_GLOBAL_Control
0x1800304b5  cmp     rcx, rsi
0x1800304b8  jz      loc_1800305F8
0x1800304be  test    byte ptr [rcx+1Ch], 1
0x1800304c2  jz      loc_1800305F8
0x1800304c8  mov     edx, 29h ; ')'
0x1800304cd  jmp     loc_18003043C
0x1800304d2  lea     rcx, [rbp+var_30]; struct _IP_ADAPTER_ADDRESSES_LH **
0x1800304d6  call    ?FwGetAdapters@@YAJPEAPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z; FwGetAdapters(_IP_ADAPTER_ADDRESSES_LH * *)
0x1800304db  lea     rsi, WPP_GLOBAL_Control
0x1800304e2  mov     ebx, eax
0x1800304e4  test    eax, eax
0x1800304e6  jns     short loc_180030514
0x1800304e8  mov     ebx, 8000FFFFh
0x1800304ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800304f4  cmp     rcx, rsi
0x1800304f7  jz      loc_1800305AC
0x1800304fd  test    byte ptr [rcx+1Ch], 1
0x180030501  jz      loc_1800305AC
0x180030507  mov     edx, 2Ah ; '*'
0x18003050c  mov     r9d, ebx
0x18003050f  jmp     loc_18003059C
0x180030514  mov     r15d, [rbp+plLbound]
0x180030518  cmp     r15d, [rbp+plUbound]
0x18003051c  jg      loc_1800305AC
0x180030522  mov     rdx, [rbp+ppvData]
0x180030526  lea     r8, [rbp+var_18]; struct _GUID *
0x18003052a  movsxd  rax, r15d
0x18003052d  lea     rcx, [rax+rax*2]
0x180030531  mov     rdx, [rdx+rcx*8+8]; unsigned __int16 *
0x180030536  mov     rcx, [rbp+var_30]; struct _IP_ADAPTER_ADDRESSES_LH *
0x18003053a  call    ?FwInterfaceNameToLuid@@YAJPEAU_IP_ADAPTER_ADDRESSES_LH@@QEAGPEAU_GUID@@@Z; FwInterfaceNameToLuid(_IP_ADAPTER_ADDRESSES_LH *,ushort * const,_GUID *)
0x18003053f  mov     ebx, eax
0x180030541  test    eax, eax
0x180030543  js      short loc_180030582
0x180030545  mov     rdx, cs:__imp_FwCopyLUID
0x18003054c  lea     r9, [rbp+var_18]
0x180030550  mov     r8, r12
0x180030553  mov     ecx, 10h
0x180030558  call    cs:__imp_FwArrayAppend
0x18003055e  mov     ebx, eax
0x180030560  test    eax, eax
0x180030562  js      short loc_180030569
0x180030564  inc     r15d
0x180030567  jmp     short loc_180030518
0x180030569  mov     rcx, cs:WPP_GLOBAL_Control
0x180030570  cmp     rcx, rsi
0x180030573  jz      short loc_1800305AC
0x180030575  test    byte ptr [rcx+1Ch], 1
0x180030579  jz      short loc_1800305AC
0x18003057b  mov     edx, 2Ch ; ','
0x180030580  jmp     short loc_180030599
0x180030582  mov     rcx, cs:WPP_GLOBAL_Control
0x180030589  cmp     rcx, rsi
0x18003058c  jz      short loc_1800305AC
0x18003058e  test    byte ptr [rcx+1Ch], 1
0x180030592  jz      short loc_1800305AC
0x180030594  mov     edx, 2Bh ; '+'
0x180030599  mov     r9d, eax
0x18003059c  mov     rcx, [rcx+10h]
0x1800305a0  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x1800305a7  call    WPP_SF_d
0x1800305ac  mov     rcx, r14; psa
0x1800305af  call    cs:__imp_SafeArrayUnaccessData
0x1800305b5  test    eax, eax
0x1800305b7  jns     short loc_1800305E3
0x1800305b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800305c0  cmp     rcx, rsi
0x1800305c3  jz      short loc_1800305E3
0x1800305c5  test    byte ptr [rcx+1Ch], 1
0x1800305c9  jz      short loc_1800305E3
0x1800305cb  mov     rcx, [rcx+10h]
0x1800305cf  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x1800305d6  mov     edx, 2Dh ; '-'
0x1800305db  mov     r9d, eax
0x1800305de  call    WPP_SF_d
0x1800305e3  cmp     [rbp+var_30], 0
0x1800305e8  jz      short loc_1800305F4
0x1800305ea  mov     rcx, [rbp+var_30]
0x1800305ee  call    cs:__imp_FwBaseFree
0x1800305f4  test    ebx, ebx
0x1800305f6  jns     short loc_180030611
0x1800305f8  cmp     qword ptr [r12+8], 0
0x1800305fe  jz      short loc_180030609
0x180030600  mov     rcx, r12
0x180030603  call    cs:__imp_FwBaseFree
0x180030609  xorps   xmm0, xmm0
0x18003060c  movups  xmmword ptr [r12], xmm0
0x180030611  mov     eax, ebx
0x180030613  mov     rcx, [rbp+var_8]
0x180030617  xor     rcx, rsp; StackCookie
0x18003061a  call    __security_check_cookie
0x18003061f  mov     rbx, [rsp+50h+arg_10]
0x180030627  add     rsp, 50h
0x18003062b  pop     r15
0x18003062d  pop     r14
0x18003062f  pop     r12
0x180030631  pop     rsi
0x180030632  pop     rbp
0x180030633  retn
```
