# CStartMenuTopRowset::_InitializeConditionTrees(void)

- ea: `0x18003659c`
- end: `0x1800368df`
- name: `?_InitializeConditionTrees@CStartMenuTopRowset@@AEAAJXZ`
- size: `835`
- prototype: `__int64 __fastcall(CStartMenuTopRowset *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003974c`

## callees

- `0x1800054b0`
- `0x180005c74`
- `0x180005c88`
- `0x180006900`
- `0x180023c78`
- `0x1800284e0`
- `0x18002850c`
- `0x180028ebc`
- `0x180031760`
- `0x18003659c`
- `0x180038110`
- `0x180041520`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800367f7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800367f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800367d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800367d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036692`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036692`

## pseudocode

```c
__int64 __fastcall CStartMenuTopRowset::_InitializeConditionTrees(CStartMenuTopRowset *this)
{
  int String; // ebx
  _QWORD *v3; // r14
  __int64 v4; // r10
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // r9
  _QWORD *v6; // rsi
  struct ICondition *v7; // rdx
  const struct _tagpropertykey *v8; // r8
  __int64 v9; // rax
  void *v10; // rcx
  enum tagCONDITION_TYPE v11; // edx
  __int64 v12; // rax
  GUID *ppv; // [rsp+20h] [rbp-69h]
  __int64 v15; // [rsp+60h] [rbp-29h] BYREF
  struct ICondition *v16; // [rsp+68h] [rbp-21h] BYREF
  int v17; // [rsp+70h] [rbp-19h]
  LPVOID v18; // [rsp+78h] [rbp-11h] BYREF
  __int64 v19; // [rsp+80h] [rbp-9h] BYREF
  struct _GUID v20; // [rsp+88h] [rbp-1h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+98h] [rbp+Fh] BYREF
  struct _tagpropertykey v22; // [rsp+B0h] [rbp+27h] BYREF

  String = 1;
  v3 = (_QWORD *)((char *)this + 128);
  if ( !*((_QWORD *)this + 16) )
    goto LABEL_30;
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v15);
  String = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v4 + 32LL))(
             v4,
             0,
             &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
             &v15);
  if ( String >= 0 )
    String = IPropertyStore_GetString(v15, &PKEY_StartMenu_Group, (char *)this + 152);
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v15);
  if ( String >= 0 )
  {
LABEL_30:
    if ( *((_QWORD *)this + 10) )
    {
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v19);
      String = (**v5)(v5, &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7, &v19);
      if ( String >= 0 )
      {
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v18);
        String = CoCreateInstance(
                   &GUID_934d4698_6a59_48f8_9f29_9fb30670320e,
                   0,
                   1u,
                   &GUID_db73aa13_3375_4c76_884a_a6116590c15b,
                   &v18);
        if ( String >= 0 )
        {
          ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v15);
          v17 = 0;
          v6 = (_QWORD *)((char *)this + 88);
          ppv = &GUID_0fc988d4_c935_4b97_a973_46282ea175c8;
          String = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v18 + 96LL))(v18, v19, 2);
          if ( String >= 0 && v15 )
          {
            if ( !ATL::CComPtrBase<IResultSetManager>::operator!(v3) )
              goto LABEL_31;
            ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v16);
            ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v20);
            String = CStartMenuTopRowset::_RemoveConditionWithPropertyKey(
                       this,
                       v7,
                       v8,
                       &v16,
                       (struct ICondition **)&v20);
            if ( !String )
            {
              v9 = ATL::CComPtrBase<IScope>::Detach(&v20);
              ATL::CComPtrBase<IObjectCollection>::Attach(&v15, v9);
              memset(&v22, 0, sizeof(v22));
              memset(&pvar, 0, sizeof(pvar));
              String = SHGetComparisonInfo(v16, &v22, 0, &pvar);
              if ( String >= 0 )
              {
                if ( pvar.vt == 31 )
                {
                  v10 = (void *)*((_QWORD *)this + 19);
                  *((_QWORD *)this + 19) = 0;
                  CoTaskMemFree(v10);
                  *((_QWORD *)this + 19) = pvar.hVal.QuadPart;
                  pvar.vt = 0;
                }
                else
                {
                  String = -2147418113;
                }
              }
              PropVariantClear((PROPVARIANT *)&pvar);
            }
            ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v20);
            ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v16);
            if ( String >= 0 )
            {
LABEL_31:
              if ( *v6 )
              {
                String = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v6 + 112LL))(*v6, (char *)this + 96);
                if ( String >= 0 )
                {
                  v16 = 0;
                  *(_QWORD *)&v20.Data1 = v15;
                  *(_QWORD *)v20.Data4 = *v6;
                  String = CStartMenuTopRowset::_CombineMultipleConditions(
                             this,
                             v11,
                             (struct ICondition **)&v20,
                             2u,
                             ppv,
                             (void **)&v16);
                  if ( String >= 0 )
                    ATL::CComPtr<CPropertyMapPair>::operator=((struct IUnknown **)this + 11, (struct IUnknown **)&v16);
                  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v16);
                }
              }
              else
              {
                v12 = ATL::CComPtrBase<IScope>::Detach(&v15);
                ATL::CComPtrBase<IObjectCollection>::Attach((char *)this + 88, v12);
              }
            }
          }
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v15);
        }
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v18);
      }
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v19);
    }
  }
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18003659c  mov     [rsp-8+arg_8], rbx
0x1800365a1  mov     [rsp-8+arg_10], rsi
0x1800365a6  push    rbp
0x1800365a7  push    rdi
0x1800365a8  push    r14
0x1800365aa  lea     rbp, [rsp-47h]
0x1800365af  sub     rsp, 0D0h
0x1800365b6  mov     rax, cs:__security_cookie
0x1800365bd  xor     rax, rsp
0x1800365c0  mov     [rbp+57h+var_18], rax
0x1800365c4  mov     rdi, rcx
0x1800365c7  mov     ebx, 1
0x1800365cc  lea     r14, [rcx+80h]
0x1800365d3  mov     r10, [r14]
0x1800365d6  test    r10, r10
0x1800365d9  jz      short loc_180036631
0x1800365db  lea     rcx, [rbp+57h+var_80]; void *
0x1800365df  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800365e4  nop
0x1800365e5  mov     rax, [r10]
0x1800365e8  lea     r9, [rbp+57h+var_80]
0x1800365ec  lea     r8, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x1800365f3  xor     edx, edx
0x1800365f5  mov     rcx, r10
0x1800365f8  mov     rax, [rax+20h]
0x1800365fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036601  mov     ebx, eax
0x180036603  test    eax, eax
0x180036605  js      short loc_180036620
0x180036607  lea     r8, [rdi+98h]
0x18003660e  lea     rdx, PKEY_StartMenu_Group
0x180036615  mov     rcx, [rbp+57h+var_80]
0x180036619  call    IPropertyStore_GetString
0x18003661e  mov     ebx, eax
0x180036620  lea     rcx, [rbp+57h+var_80]
0x180036624  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180036629  test    ebx, ebx
0x18003662b  js      loc_1800368B9
0x180036631  mov     r9, [rdi+50h]
0x180036635  test    r9, r9
0x180036638  jz      loc_1800368B9
0x18003663e  lea     rcx, [rbp+57h+var_60]; void *
0x180036642  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180036647  nop
0x180036648  mov     rax, [r9]
0x18003664b  lea     r8, [rbp+57h+var_60]
0x18003664f  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x180036656  mov     rcx, r9
0x180036659  mov     rax, [rax]
0x18003665c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036661  mov     ebx, eax
0x180036663  test    eax, eax
0x180036665  js      loc_1800368B0
0x18003666b  lea     rcx, [rbp+57h+var_68]; void *
0x18003666f  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180036674  nop
0x180036675  lea     rax, [rbp+57h+var_68]
0x180036679  mov     [rsp+0E0h+ppv], rax; ppv
0x18003667e  lea     r9, _GUID_db73aa13_3375_4c76_884a_a6116590c15b; riid
0x180036685  xor     edx, edx; pUnkOuter
0x180036687  lea     r8d, [rdx+1]; dwClsContext
0x18003668b  lea     rcx, _GUID_934d4698_6a59_48f8_9f29_9fb30670320e; rclsid
0x180036692  call    cs:__imp_CoCreateInstance
0x180036698  mov     ebx, eax
0x18003669a  test    eax, eax
0x18003669c  js      loc_1800368A6
0x1800366a2  lea     rcx, [rbp+57h+var_80]; void *
0x1800366a6  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800366ab  nop
0x1800366ac  mov     [rbp+57h+var_70], 0
0x1800366b3  mov     r10, [rbp+57h+var_68]
0x1800366b7  lea     rsi, [rdi+58h]
0x1800366bb  mov     rax, [r10]
0x1800366be  lea     rcx, [rdi+90h]
0x1800366c5  lea     r8, [rdi+88h]
0x1800366cc  lea     rdx, [rbp+57h+var_80]
0x1800366d0  mov     [rsp+0E0h+var_90], rdx
0x1800366d5  lea     r11, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x1800366dc  mov     [rsp+0E0h+var_98], r11
0x1800366e1  lea     rdx, [rbp+57h+var_70]
0x1800366e5  mov     [rsp+0E0h+var_A0], rdx
0x1800366ea  mov     [rsp+0E0h+var_A8], rcx
0x1800366ef  mov     [rsp+0E0h+var_B0], r8
0x1800366f4  mov     [rsp+0E0h+var_B8], rsi
0x1800366f9  mov     [rsp+0E0h+ppv], r11
0x1800366fe  mov     r9d, 1
0x180036704  lea     r8d, [r9+1]
0x180036708  mov     rdx, [rbp+57h+var_60]
0x18003670c  mov     rcx, r10
0x18003670f  mov     rax, [rax+60h]
0x180036713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036718  mov     ebx, eax
0x18003671a  test    eax, eax
0x18003671c  js      loc_18003689C
0x180036722  mov     rdx, [rbp+57h+var_80]
0x180036726  test    rdx, rdx
0x180036729  jz      loc_18003689C
0x18003672f  mov     rcx, r14
0x180036732  call    ??7?$CComPtrBase@UIResultSetManager@@@ATL@@QEBA_NXZ; ATL::CComPtrBase<IResultSetManager>::operator!(void)
0x180036737  test    al, al
0x180036739  jz      loc_180036819
0x18003673f  lea     rcx, [rbp+57h+var_78]; void *
0x180036743  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180036748  nop
0x180036749  lea     rcx, [rbp+57h+var_58]; void *
0x18003674d  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180036752  nop
0x180036753  lea     rax, [rbp+57h+var_58]
0x180036757  mov     [rsp+0E0h+ppv], rax; struct _GUID *
0x18003675c  lea     r9, [rbp+57h+var_78]; struct ICondition **
0x180036760  mov     rcx, rdi; this
0x180036763  call    ?_RemoveConditionWithPropertyKey@CStartMenuTopRowset@@AEAAJPEAUICondition@@AEBU_tagpropertykey@@PEAPEAU2@2@Z; CStartMenuTopRowset::_RemoveConditionWithPropertyKey(ICondition *,_tagpropertykey const &,ICondition * *,ICondition * *)
0x180036768  mov     ebx, eax
0x18003676a  test    eax, eax
0x18003676c  jnz     loc_1800367FE
0x180036772  lea     rcx, [rbp+57h+var_58]
0x180036776  call    ?Detach@?$CComPtrBase@UIScope@@@ATL@@QEAAPEAUIScope@@XZ; ATL::CComPtrBase<IScope>::Detach(void)
0x18003677b  mov     rdx, rax
0x18003677e  lea     rcx, [rbp+57h+var_80]
0x180036782  call    ?Attach@?$CComPtrBase@UIObjectCollection@@@ATL@@QEAAXPEAUIObjectCollection@@@Z; ATL::CComPtrBase<IObjectCollection>::Attach(IObjectCollection *)
0x180036787  xorps   xmm0, xmm0
0x18003678a  xor     eax, eax
0x18003678c  movups  xmmword ptr [rbp+57h+var_30.fmtid.Data1], xmm0
0x180036790  mov     [rbp+57h+var_30.pid], eax
0x180036793  xorps   xmm1, xmm1
0x180036796  movups  xmmword ptr [rbp+57h+pvar], xmm1
0x18003679a  mov     [rbp+57h+var_38], rax
0x18003679e  lea     r9, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x1800367a2  xor     r8d, r8d; enum tagCONDITION_OPERATION *
0x1800367a5  lea     rdx, [rbp+57h+var_30]; struct _tagpropertykey *
0x1800367a9  mov     rcx, [rbp+57h+var_78]; struct ICondition *
0x1800367ad  call    ?SHGetComparisonInfo@@YAJPEAUICondition@@PEAU_tagpropertykey@@PEAW4tagCONDITION_OPERATION@@PEAUtagPROPVARIANT@@@Z; SHGetComparisonInfo(ICondition *,_tagpropertykey *,tagCONDITION_OPERATION *,tagPROPVARIANT *)
0x1800367b2  mov     ebx, eax
0x1800367b4  test    eax, eax
0x1800367b6  js      short loc_1800367F3
0x1800367b8  mov     eax, 1Fh
0x1800367bd  cmp     ax, word ptr [rbp+57h+pvar]
0x1800367c1  jnz     short loc_1800367EE
0x1800367c3  mov     rcx, [rdi+98h]; pv
0x1800367ca  mov     qword ptr [rdi+98h], 0
0x1800367d5  call    cs:__imp_CoTaskMemFree
0x1800367db  mov     rax, [rbp+57h+pvar+8]
0x1800367df  mov     [rdi+98h], rax
0x1800367e6  xor     eax, eax
0x1800367e8  mov     word ptr [rbp+57h+pvar], ax
0x1800367ec  jmp     short loc_1800367F3
0x1800367ee  mov     ebx, 8000FFFFh
0x1800367f3  lea     rcx, [rbp+57h+pvar]; pvar
0x1800367f7  call    cs:__imp_PropVariantClear
0x1800367fd  nop
0x1800367fe  lea     rcx, [rbp+57h+var_58]
0x180036802  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180036807  nop
0x180036808  lea     rcx, [rbp+57h+var_78]
0x18003680c  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180036811  test    ebx, ebx
0x180036813  js      loc_18003689C
0x180036819  mov     rcx, [rsi]
0x18003681c  test    rcx, rcx
0x18003681f  jz      short loc_180036887
0x180036821  mov     rax, [rcx]
0x180036824  lea     rdx, [rdi+60h]
0x180036828  mov     rax, [rax+70h]
0x18003682c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036831  mov     ebx, eax
0x180036833  test    eax, eax
0x180036835  js      short loc_18003689C
0x180036837  mov     [rbp+57h+var_78], 0
0x18003683f  mov     rax, [rbp+57h+var_80]
0x180036843  mov     qword ptr [rbp+57h+var_58.Data1], rax
0x180036847  mov     rax, [rsi]
0x18003684a  mov     qword ptr [rbp+57h+var_58.Data4], rax
0x18003684e  lea     rax, [rbp+57h+var_78]
0x180036852  mov     [rsp+0E0h+var_B8], rax; void **
0x180036857  mov     r9d, 2; unsigned int
0x18003685d  lea     r8, [rbp+57h+var_58]; struct ICondition **
0x180036861  mov     rcx, rdi; this
0x180036864  call    ?_CombineMultipleConditions@CStartMenuTopRowset@@AEAAJW4tagCONDITION_TYPE@@PEAPEAUICondition@@IAEBU_GUID@@PEAPEAX@Z; CStartMenuTopRowset::_CombineMultipleConditions(tagCONDITION_TYPE,ICondition * *,uint,_GUID const &,void * *)
0x180036869  mov     ebx, eax
0x18003686b  test    eax, eax
0x18003686d  js      short loc_18003687C
0x18003686f  lea     rdx, [rbp+57h+var_78]
0x180036873  mov     rcx, rsi
0x180036876  call    ??4?$CComPtr@VCPropertyMapPair@@@ATL@@QEAAPEAVCPropertyMapPair@@AEBV01@@Z; ATL::CComPtr<CPropertyMapPair>::operator=(ATL::CComPtr<CPropertyMapPair> const &)
0x18003687b  nop
0x18003687c  lea     rcx, [rbp+57h+var_78]
0x180036880  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180036885  jmp     short loc_18003689C
0x180036887  lea     rcx, [rbp+57h+var_80]
0x18003688b  call    ?Detach@?$CComPtrBase@UIScope@@@ATL@@QEAAPEAUIScope@@XZ; ATL::CComPtrBase<IScope>::Detach(void)
0x180036890  mov     rdx, rax
0x180036893  mov     rcx, rsi
0x180036896  call    ?Attach@?$CComPtrBase@UIObjectCollection@@@ATL@@QEAAXPEAUIObjectCollection@@@Z; ATL::CComPtrBase<IObjectCollection>::Attach(IObjectCollection *)
0x18003689b  nop
0x18003689c  lea     rcx, [rbp+57h+var_80]
0x1800368a0  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800368a5  nop
0x1800368a6  lea     rcx, [rbp+57h+var_68]
0x1800368aa  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800368af  nop
0x1800368b0  lea     rcx, [rbp+57h+var_60]
0x1800368b4  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800368b9  mov     eax, ebx
0x1800368bb  mov     rcx, [rbp+57h+var_18]
0x1800368bf  xor     rcx, rsp; StackCookie
0x1800368c2  call    __security_check_cookie
0x1800368c7  lea     r11, [rsp+0E0h+var_10]
0x1800368cf  mov     rbx, [r11+28h]
0x1800368d3  mov     rsi, [r11+30h]
0x1800368d7  mov     rsp, r11
0x1800368da  pop     r14
0x1800368dc  pop     rdi
0x1800368dd  pop     rbp
0x1800368de  retn
```
