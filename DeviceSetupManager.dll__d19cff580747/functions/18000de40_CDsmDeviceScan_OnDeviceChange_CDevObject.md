# CDsmDeviceScan::OnDeviceChange(CDevObject *)

- ea: `0x18000de40`
- end: `0x18000e034`
- name: `?OnDeviceChange@CDsmDeviceScan@@UEAAXPEAVCDevObject@@@Z`
- size: `500`
- prototype: `void(CDsmDeviceScan *__hidden this, struct CDevObject *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180004520`
- `0x180004b40`
- `0x18000de40`
- `0x18000e8e4`
- `0x1800112a4`
- `0x180020aa4`
- `0x180022070`
- `0x180027ba8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsupr` at `0x18000decf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsupr` at `0x18000decf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dfa4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dfa4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000df69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000df69`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000dfb8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000dfb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dea3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dea3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e01e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e01e`

## string_xrefs

- `0x18000de6c`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CDsmDeviceScan::OnDeviceChange(CDsmDeviceScan *this, struct CDevObject *a2, __int64 a3, const char *a4)
{
  void *v6; // rbx
  __int64 v7; // rax
  _BYTE *v8; // rsi
  __int64 v9; // rcx
  char *v10; // rax
  rsize_t v11; // r14
  char *v12; // rax
  char *v13; // r12
  const struct _tagpropertykey *v14; // rdx
  int Property; // r14d
  RTL_SRWLOCK *v16; // r15
  ATL::CAtlException *v17; // [rsp+20h] [rbp-58h] BYREF
  struct tagPROPVARIANT pvar[3]; // [rsp+28h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v6 = 0;
  v7 = *((_QWORD *)a2 + 2);
  v8 = *(_BYTE **)(v7 + 8);
  if ( !v8 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      a4);
  v9 = 0x7FFFFFFF;
  v10 = *(char **)(v7 + 8);
  do
  {
    if ( !*(_WORD *)v10 )
      break;
    v10 += 2;
    --v9;
  }
  while ( v9 );
  v11 = 2 * ((v10 - v8) >> 1);
  v12 = (char *)CoTaskMemAlloc(v11 + 2);
  v13 = v12;
  if ( v12 )
  {
    memcpy_s(v12, v11 + 2, v8, v11);
    *(_WORD *)&v13[v11] = 0;
    _o__wcsupr(v13);
    v6 = v13;
    if ( *((_DWORD *)this + 40) != 3 )
      goto LABEL_22;
    memset(pvar, 0, 24);
    Property = CDevObject::GetProperty(a2, v14, pvar);
    if ( Property >= 0 && (pvar[0].vt != 11 || pvar[0].iVal != -1) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_43d4499022663c6448c6fdf63854fbee_Traceguids, v13);
      v16 = (RTL_SRWLOCK *)((char *)this + 32);
      AcquireSRWLockExclusive((PSRWLOCK)this + 4);
      try
      {
        ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::SetAt(
          (char *)this + 88,
          v13,
          0);
      }
      catch ( ATL::CAtlException *v17 )
      {
        v6 = v13;
        Property = *(_DWORD *)v17;
        v16 = (RTL_SRWLOCK *)((char *)this + 32);
      }
      ReleaseSRWLockExclusive(v16);
    }
    PropVariantClear((PROPVARIANT *)pvar);
  }
  else
  {
    Property = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\base\\Devices\\Setup\\Dsm\\inc\\DevObjectQuery.h",
      (const char *)0x8007000ELL,
      (int)v17);
  }
  if ( Property < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      &WPP_43d4499022663c6448c6fdf63854fbee_Traceguids,
      (unsigned int)Property);
LABEL_22:
  if ( v6 )
    CoTaskMemFree(v6);
}

```

## disassembly

```asm
0x18000de40  push    rbx
0x18000de42  push    rsi
0x18000de43  push    rdi
0x18000de44  push    r12
0x18000de46  push    r13
0x18000de48  push    r14
0x18000de4a  push    r15
0x18000de4c  sub     rsp, 40h
0x18000de50  mov     r15, rdx
0x18000de53  mov     r13, rcx
0x18000de56  xor     edi, edi
0x18000de58  mov     ebx, edi
0x18000de5a  mov     rax, [rdx+10h]
0x18000de5e  mov     rsi, [rax+8]
0x18000de62  mov     rcx, [rsp+78h]; this
0x18000de67  test    rsi, rsi
0x18000de6a  jnz     short loc_18000DE7E
0x18000de6c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000de73  mov     edx, 0F89h; void *
0x18000de78  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000de7e  mov     ecx, 7FFFFFFFh
0x18000de83  mov     rax, rsi
0x18000de86  cmp     [rax], di
0x18000de89  jz      short loc_18000DE95
0x18000de8b  add     rax, 2
0x18000de8f  sub     rcx, 1
0x18000de93  jnz     short loc_18000DE86
0x18000de95  sub     rax, rsi
0x18000de98  sar     rax, 1
0x18000de9b  lea     r14, [rax+rax]
0x18000de9f  lea     rcx, [r14+2]; cb
0x18000dea3  call    cs:__imp_CoTaskMemAlloc
0x18000dea9  mov     r12, rax
0x18000deac  test    rax, rax
0x18000deaf  jz      loc_18000DFC0
0x18000deb5  mov     r9, r14; SourceSize
0x18000deb8  mov     r8, rsi; Source
0x18000debb  lea     rdx, [r14+2]; DestinationSize
0x18000debf  mov     rcx, rax; Destination
0x18000dec2  call    memcpy_s
0x18000dec7  mov     [r14+r12], di
0x18000decc  mov     rcx, r12
0x18000decf  call    cs:__imp__o__wcsupr
0x18000ded5  mov     rbx, r12
0x18000ded8  mov     [rsp+78h+arg_10], rbx
0x18000dee0  cmp     dword ptr [r13+0A0h], 3
0x18000dee8  jnz     loc_18000E016
0x18000deee  xorps   xmm0, xmm0
0x18000def1  xor     eax, eax
0x18000def3  movups  xmmword ptr [rsp+78h+pvar], xmm0
0x18000def8  mov     [rsp+78h+var_40], rax
0x18000defd  lea     r8, [rsp+78h+pvar]; struct tagPROPVARIANT *
0x18000df02  mov     rcx, r15; this
0x18000df05  call    ?GetProperty@CDevObject@@QEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CDevObject::GetProperty(_tagpropertykey const &,tagPROPVARIANT *)
0x18000df0a  mov     r14d, eax
0x18000df0d  test    eax, eax
0x18000df0f  js      loc_18000DFAC
0x18000df15  cmp     word ptr [rsp+78h+pvar], 0Bh
0x18000df1b  jnz     short loc_18000DF29
0x18000df1d  cmp     word ptr [rsp+78h+pvar+8], 0FFFFh
0x18000df23  jz      loc_18000DFAC
0x18000df29  lea     rsi, WPP_GLOBAL_Control
0x18000df30  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df37  cmp     rcx, rsi
0x18000df3a  jz      short loc_18000DF5A
0x18000df3c  test    byte ptr [rcx+1Ch], 1
0x18000df40  jz      short loc_18000DF5A
0x18000df42  mov     edx, 21h ; '!'
0x18000df47  mov     r9, r12
0x18000df4a  lea     r8, WPP_43d4499022663c6448c6fdf63854fbee_Traceguids
0x18000df51  mov     rcx, [rcx+10h]
0x18000df55  call    WPP_SF_S
0x18000df5a  lea     r15, [r13+20h]
0x18000df5e  mov     [rsp+78h+arg_18], r15
0x18000df66  mov     rcx, r15; SRWLock
0x18000df69  call    cs:__imp_AcquireSRWLockExclusive
0x18000df6f  nop
0x18000df70  lea     rcx, [r13+58h]
0x18000df74  xor     r8d, r8d
0x18000df77  mov     rdx, r12
0x18000df7a  call    ?SetAt@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_NV?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@_N@2@@ATL@@QEAAPEAU__POSITION@@PEBG_N@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,bool,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<bool>>::SetAt(ushort const *,bool)
0x18000df7f  nop
0x18000df80  jmp     short loc_18000DFA1
0x18000df82  lea     rsi, WPP_GLOBAL_Control
0x18000df89  mov     rbx, [rsp+78h+arg_10]
0x18000df91  mov     r14d, [rsp+78h+arg_8]
0x18000df99  mov     r15, [rsp+78h+arg_18]
0x18000dfa1  mov     rcx, r15; SRWLock
0x18000dfa4  call    cs:__imp_ReleaseSRWLockExclusive
0x18000dfaa  jmp     short loc_18000DFB3
0x18000dfac  lea     rsi, WPP_GLOBAL_Control
0x18000dfb3  lea     rcx, [rsp+78h+pvar]; pvar
0x18000dfb8  call    cs:__imp_PropVariantClear
0x18000dfbe  jmp     short loc_18000DFE6
0x18000dfc0  mov     rcx, [rsp+78h]; this
0x18000dfc5  mov     r14d, 8007000Eh
0x18000dfcb  mov     r9d, r14d; char *
0x18000dfce  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\Devices\\Setup\\Dsm\\"...
0x18000dfd5  mov     edx, 18h; void *
0x18000dfda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dfdf  lea     rsi, WPP_GLOBAL_Control
0x18000dfe6  test    r14d, r14d
0x18000dfe9  jns     short loc_18000E016
0x18000dfeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dff2  cmp     rcx, rsi
0x18000dff5  jz      short loc_18000E016
0x18000dff7  test    byte ptr [rcx+1Ch], 4
0x18000dffb  jz      short loc_18000E016
0x18000dffd  mov     edx, 22h ; '"'
0x18000e002  mov     r9d, r14d
0x18000e005  lea     r8, WPP_43d4499022663c6448c6fdf63854fbee_Traceguids
0x18000e00c  mov     rcx, [rcx+10h]
0x18000e010  call    WPP_SF_d
0x18000e015  nop
0x18000e016  test    rbx, rbx
0x18000e019  jz      short loc_18000E024
0x18000e01b  mov     rcx, rbx; pv
0x18000e01e  call    cs:__imp_CoTaskMemFree
0x18000e024  add     rsp, 40h
0x18000e028  pop     r15
0x18000e02a  pop     r14
0x18000e02c  pop     r13
0x18000e02e  pop     r12
0x18000e030  pop     rdi
0x18000e031  pop     rsi
0x18000e032  pop     rbx
0x18000e033  retn
```
