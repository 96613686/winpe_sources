# CNetworkExplorerFolder::GetDetailsEx(_ITEMID_CHILD const *,_tagpropertykey const *,tagVARIANT *)

- ea: `0x180006030`
- end: `0x180006453`
- name: `?GetDetailsEx@CNetworkExplorerFolder@@UEAAJPEFBU_ITEMID_CHILD@@PEBU_tagpropertykey@@PEAUtagVARIANT@@@Z`
- size: `1059`
- prototype: `int(CNetworkExplorerFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _tagpropertykey *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002874`
- `0x180004cf4`
- `0x180006030`
- `0x18000645c`
- `0x180006d88`
- `0x180006df0`
- `0x18000c728`
- `0x18000cb58`
- `0x18000e018`
- `0x18000e4b4`
- `0x18000f0a0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800063f3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800063f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006209`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006438`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006209`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006438`
- `OLEAUT32!__imp_SysAllocString` at `0x1800061f8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800062cf`
- `OLEAUT32!__imp_SysAllocString` at `0x18000632c`
- `OLEAUT32!__imp_SysAllocString` at `0x180006427`
- `OLEAUT32!__imp_SysAllocString` at `0x1800061f8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800062cf`
- `OLEAUT32!__imp_SysAllocString` at `0x18000632c`
- `OLEAUT32!__imp_SysAllocString` at `0x180006427`
- `OLEAUT32!__imp_VariantInit` at `0x18000605d`
- `OLEAUT32!__imp_VariantInit` at `0x18000605d`

## string_xrefs

- `0x180006322`: `prop:System.Category;System.Computer.Workgroup;System.NetworkLocation`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::GetDetailsEx(
        CNetworkExplorerFolder *this,
        const struct _ITEMID_CHILD *a2,
        const struct _tagpropertykey *a3,
        struct tagVARIANT *a4)
{
  CNetworkExplorerFolder *v8; // rcx
  DWORD pid; // edx
  signed int Factory; // ebx
  __int64 v13; // rax
  CNetworkExplorerFolder *v14; // rsi
  OLECHAR *v15; // r14
  HINSTANCE v16; // rcx
  OLECHAR *v17; // rcx
  BSTR v18; // rax
  OLECHAR *v19; // rcx
  BSTR v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rax
  OLECHAR *v23; // rcx
  BSTR v24; // rax
  OLECHAR *v25; // rcx
  BSTR v26; // rbx
  __int64 v27; // rax
  BSTR v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  CNetworkExplorerFolder *v31; // rcx
  __int64 v32; // rax
  OLECHAR *v33; // rcx
  BSTR v34; // rax
  OLECHAR *v35; // rcx
  BSTR v36; // rbx
  OLECHAR *v37; // [rsp+20h] [rbp-48h] BYREF
  OLECHAR *psz; // [rsp+28h] [rbp-40h] BYREF
  int v39; // [rsp+30h] [rbp-38h] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-30h] BYREF

  VariantInit(a4);
  pid = a3->pid;
  if ( pid == 4 )
  {
    v13 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_NetworkLocation;
    if ( *(_QWORD *)&a3->fmtid.Data1 == PKEY_NetworkLocation )
      v13 = *(_QWORD *)a3->fmtid.Data4 + 0x2FE726B03FFF294BLL;
    if ( !v13 )
    {
      v14 = (CNetworkExplorerFolder *)((char *)this - 32);
      v37 = 0;
      Factory = CNetworkExplorerFolder::GetFactory(
                  (CNetworkExplorerFolder *)((char *)this - 32),
                  (struct INetworkItemFactory **)&v37);
      if ( Factory >= 0 )
      {
        v15 = v37;
        v39 = 0;
        Factory = (*(__int64 (__fastcall **)(OLECHAR *, int *))(*(_QWORD *)v37 + 80LL))(v37, &v39);
        if ( Factory >= 0 )
        {
          v37 = 0;
          if ( v39 )
          {
            Factory = CNetworkExplorerFolder::_GetNetworkItem(v14, a2, (struct INetworkItem **)&v37);
            if ( Factory >= 0 )
            {
              *(_OWORD *)&pvar.vt = 0;
              Factory = (*(__int64 (__fastcall **)(OLECHAR *, PROPVARIANT *))(*(_QWORD *)v37 + 72LL))(v37, &pvar);
              if ( Factory >= 0 )
              {
                psz = 0;
                Factory = (*(__int64 (__fastcall **)(OLECHAR *, PROPVARIANT *, OLECHAR **))(*(_QWORD *)v15 + 64LL))(
                            v15,
                            &pvar,
                            &psz);
                if ( Factory >= 0 )
                {
                  v17 = psz;
                  a4->vt = 8;
                  v18 = SysAllocString(v17);
                  v19 = psz;
                  v20 = v18;
                  a4->llVal = (LONGLONG)v18;
                  CoTaskMemFree(v19);
                  Factory = v20 == 0 ? 0x8007000E : 0;
                }
              }
              (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v37 + 16LL))(v37);
            }
          }
          else
          {
            Factory = LoadStringFromResource(v16, 0x3F1u, &v37);
            if ( Factory >= 0 )
            {
              v33 = v37;
              a4->vt = 8;
              v34 = SysAllocString(v33);
              v35 = v37;
              v36 = v34;
              a4->llVal = (LONGLONG)v34;
              CoTaskMemFree(v35);
              Factory = v36 == 0 ? 0x8007000E : 0;
            }
          }
        }
        v32 = *(_QWORD *)v15;
        goto LABEL_52;
      }
      return (unsigned int)Factory;
    }
  }
  if ( pid == 14 )
  {
    v21 = *(_QWORD *)&a3->fmtid.Data1 - 0x4FAD43BE0AE54373LL;
    if ( *(_QWORD *)&a3->fmtid.Data1 == 0x4FAD43BE0AE54373LL )
      v21 = *(_QWORD *)a3->fmtid.Data4 - 0x6E983386DC69E485LL;
  }
  else
  {
    if ( pid != 1 )
      goto LABEL_4;
    v21 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_FunctionInstance.fmtid.Data1;
    if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_FunctionInstance.fmtid.Data1 )
      v21 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_FunctionInstance.fmtid.Data4;
  }
  if ( !v21 )
  {
    v37 = 0;
    Factory = CNetworkExplorerFolder::_GetFunctionInstance(
                (CNetworkExplorerFolder *)((char *)this - 32),
                a2,
                (struct IFunctionInstance **)&v37);
    if ( Factory >= 0 )
    {
      a4->llVal = (LONGLONG)v37;
      a4->vt = 13;
    }
    return (unsigned int)Factory;
  }
LABEL_4:
  if ( pid == PKEY_NetworkProvider.pid )
  {
    v22 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_NetworkProvider.fmtid.Data1;
    if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_NetworkProvider.fmtid.Data1 )
      v22 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_NetworkProvider.fmtid.Data4;
    if ( !v22 )
    {
      psz = 0;
      Factory = CNetworkExplorerFolder::_GetFIID(v8, a2, &psz);
      if ( Factory >= 0 )
      {
        v37 = 0;
        Factory = GetFDProviderFromFIID(psz, &v37);
        if ( Factory >= 0 )
        {
          v23 = v37;
          a4->vt = 8;
          v24 = SysAllocString(v23);
          v25 = v37;
          v26 = v24;
          a4->llVal = (LONGLONG)v24;
          CoTaskMemFree(v25);
          Factory = v26 == 0 ? 0x8007000E : 0;
        }
        CoTaskMemFree(psz);
      }
      return (unsigned int)Factory;
    }
  }
  if ( pid == 8 )
  {
    v27 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1;
    if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1 )
      v27 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_PreviewDetails.fmtid.Data4;
    if ( !v27 )
    {
      a4->vt = 8;
      v28 = SysAllocString(L"prop:System.Category;System.Computer.Workgroup;System.NetworkLocation");
      a4->llVal = (LONGLONG)v28;
      return v28 == 0 ? 0x8007000E : 0;
    }
  }
  if ( pid == 1 )
  {
    v29 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_NetworkResource;
    if ( *(_QWORD *)&a3->fmtid.Data1 == (_QWORD)PKEY_NetworkResource )
      v29 = *(_QWORD *)a3->fmtid.Data4 - *((_QWORD *)&PKEY_NetworkResource + 1);
    if ( !v29 )
      return (unsigned int)CNetworkExplorerFolder::_GetNetResource(v8, a2, a4);
  }
  if ( pid != 12294 )
    return (unsigned int)CItemIDFactory<DSPROFILEITEM,999534523>::GetPropertyFromIDList(a2, a3, a4);
  v30 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PNPX_PhysicalAddress.fmtid.Data1;
  if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PNPX_PhysicalAddress.fmtid.Data1 )
    v30 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PNPX_PhysicalAddress.fmtid.Data4;
  if ( v30 )
    return (unsigned int)CItemIDFactory<DSPROFILEITEM,999534523>::GetPropertyFromIDList(a2, a3, a4);
  v37 = 0;
  Factory = CNetworkExplorerFolder::_GetNetworkItem(
              (CNetworkExplorerFolder *)((char *)this - 32),
              a2,
              (struct INetworkItem **)&v37);
  if ( Factory >= 0 )
  {
    memset(&pvar, 0, sizeof(pvar));
    Factory = (*(__int64 (__fastcall **)(OLECHAR *, PROPVARIANT *))(*(_QWORD *)v37 + 80LL))(v37, &pvar);
    if ( Factory >= 0 )
    {
      a4->vt = 8;
      Factory = CNetworkExplorerFolder::_PropVariantMACAddressToBSTR(v31, &pvar, &a4->bstrVal);
      PropVariantClear(&pvar);
    }
    v32 = *(_QWORD *)v37;
LABEL_52:
    (*(void (**)(void))(v32 + 16))();
  }
  return (unsigned int)Factory;
}

```

## disassembly

```asm
0x180006030  push    rbp
0x180006032  push    rbx
0x180006033  push    rsi
0x180006034  push    rdi
0x180006035  push    r14
0x180006037  push    r15
0x180006039  mov     rbp, rsp
0x18000603c  sub     rsp, 68h
0x180006040  mov     rax, cs:__security_cookie
0x180006047  xor     rax, rsp
0x18000604a  mov     [rbp+var_18], rax
0x18000604e  mov     r14, rcx
0x180006051  mov     rdi, r9
0x180006054  mov     rcx, r9; pvarg
0x180006057  mov     rbx, r8
0x18000605a  mov     r15, rdx
0x18000605d  call    cs:__imp_VariantInit
0x180006063  mov     edx, [rbx+10h]
0x180006066  cmp     edx, cs:dword_180012FE8
0x18000606c  jz      loc_180006118
0x180006072  cmp     edx, 0Eh
0x180006075  jz      loc_180006231
0x18000607b  cmp     edx, 1
0x18000607e  jz      loc_180006251
0x180006084  cmp     edx, cs:PKEY_NetworkProvider.pid
0x18000608a  jz      loc_180006271
0x180006090  mov     esi, 8
0x180006095  cmp     edx, esi
0x180006097  jz      loc_180006302
0x18000609d  cmp     edx, cs:dword_180013AB8
0x1800060a3  jz      loc_180006348
0x1800060a9  cmp     edx, 3006h
0x1800060af  jz      loc_180006378
0x1800060b5  mov     r8, rdi
0x1800060b8  mov     rdx, rbx
0x1800060bb  mov     rcx, r15
0x1800060be  call    ?GetPropertyFromIDList@?$CItemIDFactory@UDSPROFILEITEM@@$0DLJDKPLL@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@PEAUtagVARIANT@@@Z; CItemIDFactory<DSPROFILEITEM,999534523>::GetPropertyFromIDList(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,tagVARIANT *)
0x1800060c3  mov     ebx, eax
0x1800060c5  mov     eax, ebx
0x1800060c7  mov     rcx, [rbp+var_18]
0x1800060cb  xor     rcx, rsp; StackCookie
0x1800060ce  call    __security_check_cookie
0x1800060d3  add     rsp, 68h
0x1800060d7  pop     r15
0x1800060d9  pop     r14
0x1800060db  pop     rdi
0x1800060dc  pop     rsi
0x1800060dd  pop     rbx
0x1800060de  pop     rbp
0x1800060df  retn
0x1800060e0  lea     rcx, [r14-20h]; this
0x1800060e4  mov     [rbp+var_48], 0
0x1800060ec  lea     r8, [rbp+var_48]; struct IFunctionInstance **
0x1800060f0  mov     rdx, r15; struct _ITEMID_CHILD *
0x1800060f3  call    ?_GetFunctionInstance@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAPEAUIFunctionInstance@@@Z; CNetworkExplorerFolder::_GetFunctionInstance(_ITEMID_CHILD const *,IFunctionInstance * *)
0x1800060f8  mov     ebx, eax
0x1800060fa  test    eax, eax
0x1800060fc  js      short loc_1800060C5
0x1800060fe  mov     rax, [rbp+var_48]
0x180006102  mov     [rdi+8], rax
0x180006106  mov     word ptr [rdi], 0Dh
0x18000610b  jmp     short loc_1800060C5
0x18000610d  test    rax, rax
0x180006110  jnz     loc_180006084
0x180006116  jmp     short loc_1800060E0
0x180006118  mov     rax, [rbx]
0x18000611b  sub     rax, cs:PKEY_NetworkLocation
0x180006122  jnz     short loc_18000612F
0x180006124  mov     rax, [rbx+8]
0x180006128  sub     rax, cs:qword_180012FE0
0x18000612f  test    rax, rax
0x180006132  jnz     loc_180006072
0x180006138  lea     rsi, [r14-20h]
0x18000613c  mov     [rbp+var_48], rax
0x180006140  mov     rcx, rsi; this
0x180006143  lea     rdx, [rbp+var_48]; struct INetworkItemFactory **
0x180006147  call    ?GetFactory@CNetworkExplorerFolder@@QEAAJPEAPEAUINetworkItemFactory@@@Z; CNetworkExplorerFolder::GetFactory(INetworkItemFactory * *)
0x18000614c  mov     ebx, eax
0x18000614e  test    eax, eax
0x180006150  js      loc_1800060C5
0x180006156  mov     r14, [rbp+var_48]
0x18000615a  lea     rdx, [rbp+var_38]
0x18000615e  mov     [rbp+var_38], 0
0x180006165  mov     rcx, r14
0x180006168  mov     rax, [r14]
0x18000616b  mov     rax, [rax+50h]
0x18000616f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006174  mov     ebx, eax
0x180006176  test    eax, eax
0x180006178  js      loc_18000644B
0x18000617e  cmp     [rbp+var_38], 0
0x180006182  lea     r8, [rbp+var_48]; unsigned __int16 **
0x180006186  mov     [rbp+var_48], 0
0x18000618e  jz      loc_18000640E
0x180006194  mov     rdx, r15; struct _ITEMID_CHILD *
0x180006197  mov     rcx, rsi; this
0x18000619a  call    ?_GetNetworkItem@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAPEAUINetworkItem@@@Z; CNetworkExplorerFolder::_GetNetworkItem(_ITEMID_CHILD const *,INetworkItem * *)
0x18000619f  mov     ebx, eax
0x1800061a1  test    eax, eax
0x1800061a3  js      loc_18000644B
0x1800061a9  mov     rcx, [rbp+var_48]
0x1800061ad  lea     rdx, [rbp+pvar]
0x1800061b1  xorps   xmm0, xmm0
0x1800061b4  movups  xmmword ptr [rbp+pvar], xmm0
0x1800061b8  mov     rax, [rcx]
0x1800061bb  mov     rax, [rax+48h]
0x1800061bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061c4  mov     ebx, eax
0x1800061c6  test    eax, eax
0x1800061c8  js      short loc_18000621C
0x1800061ca  mov     [rbp+psz], 0
0x1800061d2  lea     r8, [rbp+psz]
0x1800061d6  mov     rax, [r14]
0x1800061d9  lea     rdx, [rbp+pvar]
0x1800061dd  mov     rcx, r14
0x1800061e0  mov     rax, [rax+40h]
0x1800061e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061e9  mov     ebx, eax
0x1800061eb  test    eax, eax
0x1800061ed  js      short loc_18000621C
0x1800061ef  mov     rcx, [rbp+psz]; psz
0x1800061f3  mov     word ptr [rdi], 8
0x1800061f8  call    cs:__imp_SysAllocString
0x1800061fe  mov     rcx, [rbp+psz]; pv
0x180006202  mov     rbx, rax
0x180006205  mov     [rdi+8], rax
0x180006209  call    cs:__imp_CoTaskMemFree
0x18000620f  neg     rbx
0x180006212  sbb     ebx, ebx
0x180006214  not     ebx
0x180006216  and     ebx, 8007000Eh
0x18000621c  mov     rcx, [rbp+var_48]
0x180006220  mov     rax, [rcx]
0x180006223  mov     rax, [rax+10h]
0x180006227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000622c  jmp     loc_18000644B
0x180006231  mov     rax, [rbx]
0x180006234  sub     rax, cs:qword_180012F60
0x18000623b  jnz     loc_18000610D
0x180006241  mov     rax, [rbx+8]
0x180006245  sub     rax, cs:qword_180012F68
0x18000624c  jmp     loc_18000610D
0x180006251  mov     rax, [rbx]
0x180006254  sub     rax, qword ptr cs:PKEY_FunctionInstance.fmtid.Data1
0x18000625b  jnz     loc_18000610D
0x180006261  mov     rax, [rbx+8]
0x180006265  sub     rax, qword ptr cs:PKEY_FunctionInstance.fmtid.Data4
0x18000626c  jmp     loc_18000610D
0x180006271  mov     rax, [rbx]
0x180006274  sub     rax, qword ptr cs:PKEY_NetworkProvider.fmtid.Data1
0x18000627b  jnz     short loc_180006288
0x18000627d  mov     rax, [rbx+8]
0x180006281  sub     rax, qword ptr cs:PKEY_NetworkProvider.fmtid.Data4
0x180006288  test    rax, rax
0x18000628b  jnz     loc_180006090
0x180006291  lea     r8, [rbp+psz]; unsigned __int16 **
0x180006295  mov     [rbp+psz], rax
0x180006299  mov     rdx, r15; struct _ITEMIDLIST_RELATIVE *
0x18000629c  call    ?_GetFIID@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAG@Z; CNetworkExplorerFolder::_GetFIID(_ITEMIDLIST_RELATIVE const *,ushort * *)
0x1800062a1  mov     ebx, eax
0x1800062a3  test    eax, eax
0x1800062a5  js      loc_1800060C5
0x1800062ab  mov     rcx, [rbp+psz]; unsigned __int16 *
0x1800062af  lea     rdx, [rbp+var_48]; unsigned __int16 **
0x1800062b3  mov     [rbp+var_48], 0
0x1800062bb  call    ?GetFDProviderFromFIID@@YAJPEBGPEAPEAG@Z; GetFDProviderFromFIID(ushort const *,ushort * *)
0x1800062c0  mov     ebx, eax
0x1800062c2  test    eax, eax
0x1800062c4  js      short loc_1800062F3
0x1800062c6  mov     rcx, [rbp+var_48]; psz
0x1800062ca  mov     word ptr [rdi], 8
0x1800062cf  call    cs:__imp_SysAllocString
0x1800062d5  mov     rcx, [rbp+var_48]; pv
0x1800062d9  mov     rbx, rax
0x1800062dc  mov     [rdi+8], rax
0x1800062e0  call    cs:__imp_CoTaskMemFree
0x1800062e6  neg     rbx
0x1800062e9  sbb     ebx, ebx
0x1800062eb  not     ebx
0x1800062ed  and     ebx, 8007000Eh
0x1800062f3  mov     rcx, [rbp+psz]; pv
0x1800062f7  call    cs:__imp_CoTaskMemFree
0x1800062fd  jmp     loc_1800060C5
0x180006302  mov     rax, [rbx]
0x180006305  sub     rax, qword ptr cs:PKEY_PropList_PreviewDetails.fmtid.Data1
0x18000630c  jnz     short loc_180006319
0x18000630e  mov     rax, [rbx+8]
0x180006312  sub     rax, qword ptr cs:PKEY_PropList_PreviewDetails.fmtid.Data4
0x180006319  test    rax, rax
0x18000631c  jnz     loc_18000609D
0x180006322  lea     rcx, aPropSystemCate; "prop:System.Category;System.Computer.Wo"...
0x180006329  mov     [rdi], si
0x18000632c  call    cs:__imp_SysAllocString
0x180006332  mov     [rdi+8], rax
0x180006336  neg     rax
0x180006339  sbb     ebx, ebx
0x18000633b  not     ebx
0x18000633d  and     ebx, 8007000Eh
0x180006343  jmp     loc_1800060C5
0x180006348  mov     rax, [rbx]
0x18000634b  sub     rax, qword ptr cs:PKEY_NetworkResource
0x180006352  jnz     short loc_18000635F
0x180006354  mov     rax, [rbx+8]
0x180006358  sub     rax, qword ptr cs:PKEY_NetworkResource+8
0x18000635f  test    rax, rax
0x180006362  jnz     loc_1800060A9
0x180006368  mov     r8, rdi; struct tagVARIANT *
0x18000636b  mov     rdx, r15; struct _ITEMID_CHILD *
0x18000636e  call    ?_GetNetResource@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAUtagVARIANT@@@Z; CNetworkExplorerFolder::_GetNetResource(_ITEMID_CHILD const *,tagVARIANT *)
0x180006373  jmp     loc_1800060C3
0x180006378  mov     rax, [rbx]
0x18000637b  sub     rax, qword ptr cs:PKEY_PNPX_PhysicalAddress.fmtid.Data1
0x180006382  jnz     short loc_18000638F
0x180006384  mov     rax, [rbx+8]
0x180006388  sub     rax, qword ptr cs:PKEY_PNPX_PhysicalAddress.fmtid.Data4
0x18000638f  test    rax, rax
0x180006392  jnz     loc_1800060B5
0x180006398  lea     rcx, [r14-20h]; this
0x18000639c  mov     [rbp+var_48], rax
0x1800063a0  lea     r8, [rbp+var_48]; struct INetworkItem **
0x1800063a4  mov     rdx, r15; struct _ITEMID_CHILD *
0x1800063a7  call    ?_GetNetworkItem@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAPEAUINetworkItem@@@Z; CNetworkExplorerFolder::_GetNetworkItem(_ITEMID_CHILD const *,INetworkItem * *)
0x1800063ac  mov     ebx, eax
0x1800063ae  test    eax, eax
0x1800063b0  js      loc_1800060C5
0x1800063b6  mov     rcx, [rbp+var_48]
0x1800063ba  lea     rdx, [rbp+pvar]
0x1800063be  xor     eax, eax
0x1800063c0  xorps   xmm0, xmm0
0x1800063c3  mov     qword ptr [rbp+pvar+10h], rax
0x1800063c7  movups  xmmword ptr [rbp+pvar], xmm0
0x1800063cb  mov     rax, [rcx]
0x1800063ce  mov     rax, [rax+50h]
0x1800063d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d7  mov     ebx, eax
0x1800063d9  test    eax, eax
0x1800063db  js      short loc_1800063F9
0x1800063dd  lea     r8, [rdi+8]; unsigned __int16 **
0x1800063e1  mov     [rdi], si
0x1800063e4  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x1800063e8  call    ?_PropVariantMACAddressToBSTR@CNetworkExplorerFolder@@AEAAJAEBUtagPROPVARIANT@@PEAPEAG@Z; CNetworkExplorerFolder::_PropVariantMACAddressToBSTR(tagPROPVARIANT const &,ushort * *)
0x1800063ed  lea     rcx, [rbp+pvar]; pvar
0x1800063f1  mov     ebx, eax
0x1800063f3  call    cs:__imp_PropVariantClear
0x1800063f9  mov     rcx, [rbp+var_48]
0x1800063fd  mov     rax, [rcx]
0x180006400  mov     rax, [rax+10h]
0x180006404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006409  jmp     loc_1800060C5
0x18000640e  mov     edx, 3F1h; unsigned int
0x180006413  call    ?LoadStringFromResource@@YAJPEAUHINSTANCE__@@IPEAPEAG@Z; LoadStringFromResource(HINSTANCE__ *,uint,ushort * *)
0x180006418  mov     ebx, eax
0x18000641a  test    eax, eax
0x18000641c  js      short loc_18000644B
0x18000641e  mov     rcx, [rbp+var_48]; psz
0x180006422  mov     word ptr [rdi], 8
0x180006427  call    cs:__imp_SysAllocString
0x18000642d  mov     rcx, [rbp+var_48]; pv
0x180006431  mov     rbx, rax
0x180006434  mov     [rdi+8], rax
0x180006438  call    cs:__imp_CoTaskMemFree
0x18000643e  neg     rbx
0x180006441  sbb     ebx, ebx
0x180006443  not     ebx
0x180006445  and     ebx, 8007000Eh
0x18000644b  mov     rax, [r14]
0x18000644e  mov     rcx, r14
0x180006451  jmp     short loc_180006400
```
