# Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadHandler(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002a1f4`
- end: `0x18002a42f`
- name: `?ReadHandler@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA?AV?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z`
- size: `571`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a438`

## callees

- `0x180003c80`
- `0x18000a248`
- `0x18000f9e4`
- `0x18001b444`
- `0x18001b5ac`
- `0x1800207a4`
- `0x180025080`
- `0x18002960c`
- `0x18002a1f4`
- `0x18002f800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002a246`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002a246`

## string_xrefs

- `0x18002a346`: `AccessCheckSupported`
- `0x18002a310`: `AccessChangeSupported`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadHandler(
        __int64 a1,
        __int64 a2,
        Windows::Internal::CapabilityAccess::Private **a3,
        __int64 a4)
{
  char v7; // di
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  const OLECHAR *v11; // rax
  HRESULT v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  HKEY v23; // rax
  unsigned int Uint32Value; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  HKEY v28; // rax
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  bool v33; // cl
  HKEY v34; // rax
  unsigned int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  bool v39; // cl
  HKEY v40; // rax
  unsigned int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  bool v45; // cl
  HKEY v46; // rax
  unsigned int v47; // eax
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  bool v51; // cl
  HKEY v52; // rax
  unsigned int v53; // eax
  bool *v55; // [rsp+20h] [rbp-40h] BYREF
  __int64 v56; // [rsp+28h] [rbp-38h]
  _BYTE Src[16]; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v58; // [rsp+40h] [rbp-20h]
  unsigned __int64 v59; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v56 = a2;
  Windows::Internal::CapabilityAccess::Private::CapabilityHandler::Create(a2);
  v7 = 1;
  HIDWORD(v55) = 1;
  v11 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4, v8, v9, v10);
  v12 = CLSIDFromString(v11, (LPCLSID)(*(_QWORD *)a2 + 20LL));
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6AB,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilitypolicystore.cpp",
      (const char *)(unsigned int)v12,
      (int)v55);
  std::wstring::wstring((__int64)Src, (__int64)L"CapabilityHandlers");
  v15 = v58;
  if ( v58 >= v59 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
  }
  else
  {
    ++v58;
    v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src, v13, v15, v14);
    *(_WORD *)(v16 + 2 * v17) = 92;
    *(_WORD *)(v16 + 2 * v17 + 2) = 0;
  }
  v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4, v16, v17, v18);
  std::wstring::_Append<unsigned short>(Src, v19, *(_QWORD *)(a4 + 16));
  LOBYTE(v55) = 0;
  v23 = (HKEY)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src, v20, v21, v22);
  Uint32Value = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
                  *a3,
                  v23,
                  L"Rank",
                  (const unsigned __int16 *)&v55,
                  v55);
  v25 = (_BYTE)v55 != 0 ? Uint32Value : 0;
  *(_DWORD *)(*(_QWORD *)a2 + 8LL) = v25;
  v28 = (HKEY)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src, v25, v26, v27);
  v29 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
          *a3,
          v28,
          L"AccessChangeSupported",
          (const unsigned __int16 *)&v55,
          v55);
  v33 = (_BYTE)v55 && v29;
  *(_BYTE *)(*(_QWORD *)a2 + 12LL) = v33;
  v34 = (HKEY)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src, v30, v31, v32);
  v35 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
          *a3,
          v34,
          L"AccessCheckSupported",
          (const unsigned __int16 *)&v55,
          v55);
  v39 = (_BYTE)v55 && v35;
  *(_BYTE *)(*(_QWORD *)a2 + 13LL) = v39;
  v40 = (HKEY)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src, v36, v37, v38);
  v41 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
          *a3,
          v40,
          L"CustomConsentSupported",
          (const unsigned __int16 *)&v55,
          v55);
  v45 = (_BYTE)v55 && v41;
  *(_BYTE *)(*(_QWORD *)a2 + 14LL) = v45;
  v46 = (HKEY)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src, v42, v43, v44);
  v47 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
          *a3,
          v46,
          L"PolicySupported",
          (const unsigned __int16 *)&v55,
          v55);
  v51 = (_BYTE)v55 && v47;
  *(_BYTE *)(*(_QWORD *)a2 + 15LL) = v51;
  v52 = (HKEY)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src, v48, v49, v50);
  v53 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
          *a3,
          v52,
          L"ProvisionSupported",
          (const unsigned __int16 *)&v55,
          v55);
  if ( !(_BYTE)v55 || !v53 )
    v7 = 0;
  *(_BYTE *)(*(_QWORD *)a2 + 16LL) = v7;
  std::wstring::_Tidy_deallocate(Src);
  return a2;
}

```

## disassembly

```asm
0x18002a1f4  push    rbp
0x18002a1f6  push    rbx
0x18002a1f7  push    rsi
0x18002a1f8  push    rdi
0x18002a1f9  push    r14
0x18002a1fb  mov     rbp, rsp
0x18002a1fe  sub     rsp, 60h
0x18002a202  mov     rax, cs:__security_cookie
0x18002a209  xor     rax, rsp
0x18002a20c  mov     [rbp+var_10], rax
0x18002a210  mov     r14, r9
0x18002a213  mov     rsi, r8
0x18002a216  mov     rbx, rdx
0x18002a219  mov     [rbp+var_38], rdx
0x18002a21d  mov     [rbp+var_3C], 0
0x18002a224  mov     rcx, rdx
0x18002a227  call    ?Create@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::Create(void)
0x18002a22c  mov     edi, 1
0x18002a231  mov     [rbp+var_3C], edi
0x18002a234  mov     rcx, r14
0x18002a237  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a23c  mov     rdx, [rbx]
0x18002a23f  add     rdx, 14h; pclsid
0x18002a243  mov     rcx, rax; lpsz
0x18002a246  call    cs:__imp_CLSIDFromString
0x18002a24c  mov     rcx, [rbp+28h]; this
0x18002a250  test    eax, eax
0x18002a252  jns     short loc_18002A269
0x18002a254  mov     r9d, eax; char *
0x18002a257  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\cam\\core\\capa"...
0x18002a25e  mov     edx, 6ABh; void *
0x18002a263  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a269  lea     rdx, aCapabilityhand; "CapabilityHandlers"
0x18002a270  lea     rcx, [rbp+Src]
0x18002a274  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a279  nop
0x18002a27a  mov     r8, [rbp+var_20]
0x18002a27e  lea     rcx, [rbp+Src]; Src
0x18002a282  cmp     r8, [rbp+var_18]
0x18002a286  jnb     short loc_18002A2A9
0x18002a288  lea     rax, [r8+1]
0x18002a28c  mov     [rbp+var_20], rax
0x18002a290  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a295  mov     rdx, rax
0x18002a298  mov     word ptr [rax+r8*2], 5Ch ; '\'
0x18002a29f  xor     eax, eax
0x18002a2a1  mov     [rdx+r8*2+2], ax
0x18002a2a7  jmp     short loc_18002A2B4
0x18002a2a9  mov     r9d, 5Ch ; '\'
0x18002a2af  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18002a2b4  mov     rcx, r14
0x18002a2b7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a2bc  mov     r8, [r14+10h]
0x18002a2c0  mov     rdx, rax
0x18002a2c3  lea     rcx, [rbp+Src]
0x18002a2c7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002a2cc  mov     byte ptr [rbp+var_40], 0
0x18002a2d0  lea     rcx, [rbp+Src]
0x18002a2d4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a2d9  mov     rdx, rax; HKEY
0x18002a2dc  lea     r9, [rbp+var_40]; unsigned __int16 *
0x18002a2e0  lea     r8, aRank; "Rank"
0x18002a2e7  mov     rcx, [rsi]; this
0x18002a2ea  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x18002a2ef  mov     ecx, eax
0x18002a2f1  mov     al, byte ptr [rbp+var_40]
0x18002a2f4  neg     al
0x18002a2f6  sbb     edx, edx
0x18002a2f8  and     edx, ecx
0x18002a2fa  mov     rax, [rbx]
0x18002a2fd  mov     [rax+8], edx
0x18002a300  lea     rcx, [rbp+Src]
0x18002a304  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a309  mov     rdx, rax; HKEY
0x18002a30c  lea     r9, [rbp+var_40]; unsigned __int16 *
0x18002a310  lea     r8, aAccesschangesu; "AccessChangeSupported"
0x18002a317  mov     rcx, [rsi]; this
0x18002a31a  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x18002a31f  cmp     byte ptr [rbp+var_40], 0
0x18002a323  jz      short loc_18002A32E
0x18002a325  test    eax, eax
0x18002a327  jz      short loc_18002A32E
0x18002a329  mov     cl, dil
0x18002a32c  jmp     short loc_18002A330
0x18002a32e  xor     cl, cl
0x18002a330  mov     rax, [rbx]
0x18002a333  mov     [rax+0Ch], cl
0x18002a336  lea     rcx, [rbp+Src]
0x18002a33a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a33f  mov     rdx, rax; HKEY
0x18002a342  lea     r9, [rbp+var_40]; unsigned __int16 *
0x18002a346  lea     r8, aAccesschecksup; "AccessCheckSupported"
0x18002a34d  mov     rcx, [rsi]; this
0x18002a350  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x18002a355  cmp     byte ptr [rbp+var_40], 0
0x18002a359  jz      short loc_18002A364
0x18002a35b  test    eax, eax
0x18002a35d  jz      short loc_18002A364
0x18002a35f  mov     cl, dil
0x18002a362  jmp     short loc_18002A366
0x18002a364  xor     cl, cl
0x18002a366  mov     rax, [rbx]
0x18002a369  mov     [rax+0Dh], cl
0x18002a36c  lea     rcx, [rbp+Src]
0x18002a370  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a375  mov     rdx, rax; HKEY
0x18002a378  lea     r9, [rbp+var_40]; unsigned __int16 *
0x18002a37c  lea     r8, aCustomconsents; "CustomConsentSupported"
0x18002a383  mov     rcx, [rsi]; this
0x18002a386  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x18002a38b  cmp     byte ptr [rbp+var_40], 0
0x18002a38f  jz      short loc_18002A39A
0x18002a391  test    eax, eax
0x18002a393  jz      short loc_18002A39A
0x18002a395  mov     cl, dil
0x18002a398  jmp     short loc_18002A39C
0x18002a39a  xor     cl, cl
0x18002a39c  mov     rax, [rbx]
0x18002a39f  mov     [rax+0Eh], cl
0x18002a3a2  lea     rcx, [rbp+Src]
0x18002a3a6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a3ab  mov     rdx, rax; HKEY
0x18002a3ae  lea     r9, [rbp+var_40]; unsigned __int16 *
0x18002a3b2  lea     r8, aPolicysupporte; "PolicySupported"
0x18002a3b9  mov     rcx, [rsi]; this
0x18002a3bc  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x18002a3c1  cmp     byte ptr [rbp+var_40], 0
0x18002a3c5  jz      short loc_18002A3D0
0x18002a3c7  test    eax, eax
0x18002a3c9  jz      short loc_18002A3D0
0x18002a3cb  mov     cl, dil
0x18002a3ce  jmp     short loc_18002A3D2
0x18002a3d0  xor     cl, cl
0x18002a3d2  mov     rax, [rbx]
0x18002a3d5  mov     [rax+0Fh], cl
0x18002a3d8  lea     rcx, [rbp+Src]
0x18002a3dc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a3e1  mov     rdx, rax; HKEY
0x18002a3e4  lea     r9, [rbp+var_40]; unsigned __int16 *
0x18002a3e8  lea     r8, aProvisionsuppo; "ProvisionSupported"
0x18002a3ef  mov     rcx, [rsi]; this
0x18002a3f2  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x18002a3f7  cmp     byte ptr [rbp+var_40], 0
0x18002a3fb  jz      short loc_18002A401
0x18002a3fd  test    eax, eax
0x18002a3ff  jnz     short loc_18002A404
0x18002a401  xor     dil, dil
0x18002a404  mov     rcx, [rbx]
0x18002a407  mov     [rcx+10h], dil
0x18002a40b  lea     rcx, [rbp+Src]
0x18002a40f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a414  mov     rax, rbx
0x18002a417  mov     rcx, [rbp+var_10]
0x18002a41b  xor     rcx, rsp; StackCookie
0x18002a41e  call    __security_check_cookie
0x18002a423  add     rsp, 60h
0x18002a427  pop     r14
0x18002a429  pop     rdi
0x18002a42a  pop     rsi
0x18002a42b  pop     rbx
0x18002a42c  pop     rbp
0x18002a42d  retn
```
