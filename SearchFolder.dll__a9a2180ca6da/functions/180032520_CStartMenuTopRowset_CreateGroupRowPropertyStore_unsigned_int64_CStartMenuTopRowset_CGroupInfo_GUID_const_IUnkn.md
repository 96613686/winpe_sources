# CStartMenuTopRowset::_CreateGroupRowPropertyStore(unsigned __int64,CStartMenuTopRowset::CGroupInfo *,_GUID const &,IUnknown * *)

- ea: `0x180032520`
- end: `0x1800327eb`
- name: `?_CreateGroupRowPropertyStore@CStartMenuTopRowset@@AEAAJ_KPEAVCGroupInfo@1@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `715`
- prototype: `__int64 __fastcall(CStartMenuTopRowset *this, __int64, LARGE_INTEGER *, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c860`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x18000e4fc`
- `0x180032520`
- `0x18003d8ec`
- `0x180040ff8`
- `0x180041618`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032688`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032688`
- `PROPSYS!PSFormatForDisplay` at `0x180032613`
- `PROPSYS!PSFormatForDisplay` at `0x180032613`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180032579`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180032579`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CStartMenuTopRowset::_CreateGroupRowPropertyStore(
        CStartMenuTopRowset *this,
        __int64 a2,
        LARGE_INTEGER *a3,
        const struct _GUID *a4,
        struct IUnknown **a5)
{
  HRESULT Instance; // ebx
  __int64 v9; // r9
  __int64 v10; // r9
  struct IRichChunk *v12; // [rsp+28h] [rbp-D8h]
  struct IRichChunk *v13; // [rsp+30h] [rbp-D0h]
  struct IRichChunk *v14; // [rsp+38h] [rbp-C8h]
  const struct _GUID *v15; // [rsp+48h] [rbp-B8h]
  void *ppv; // [rsp+60h] [rbp-A0h] BYREF
  struct tagPROPVARIANT propvar; // [rsp+68h] [rbp-98h] BYREF
  void *v18; // [rsp+80h] [rbp-80h] BYREF
  struct IConditionFactory2 *v19; // [rsp+88h] [rbp-78h] BYREF
  WCHAR pwszText[264]; // [rsp+90h] [rbp-70h] BYREF

  *a5 = 0;
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
  Instance = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  if ( Instance >= 0 )
  {
    Instance = IPropertyStore_SetUInt64(ppv, &PKEY_DefaultGroupOrder, a2, v9);
    if ( Instance >= 0 )
    {
      Instance = IPropertyStore_SetUInt64(ppv, PKEY_ChapterId, a2, v10);
      if ( Instance >= 0 )
      {
        Instance = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))IPropertyStore_SetString)(
                     ppv,
                     &PKEY_StartMenu_Group,
                     (LARGE_INTEGER)a3[2].QuadPart);
        if ( Instance >= 0 )
        {
          propvar.vt = 31;
          propvar.hVal = a3[1];
          Instance = PSFormatForDisplay(
                       &PKEY_StartMenu_Group,
                       (const PROPVARIANT *const)&propvar,
                       PDFF_DEFAULT,
                       pwszText,
                       0x104u);
          if ( Instance >= 0 )
          {
            Instance = IPropertyStore_SetString(ppv, &PKEY_ItemNameDisplay, pwszText);
            if ( Instance >= 0 )
            {
              Instance = IPropertyStore_SetString(ppv, &PKEY_ItemId, pwszText);
              if ( Instance >= 0 )
              {
                ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v19);
                Instance = CoCreateInstance(
                             &GUID_934d4698_6a59_48f8_9f29_9fb30670320e,
                             0,
                             1u,
                             &GUID_71d222e1_432f_429e_8c13_b6dafde5077a,
                             (LPVOID *)&v19);
                if ( Instance >= 0 )
                {
                  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v18);
                  propvar.vt = 31;
                  propvar.hVal = a3[2];
                  Instance = SHCreateLeafConditionEx(
                               &PKEY_StartMenu_Group,
                               COP_EQUAL,
                               &propvar,
                               0,
                               &psz,
                               v12,
                               v13,
                               v14,
                               v19,
                               v15,
                               &v18);
                  if ( Instance >= 0 )
                  {
                    *(_QWORD *)&propvar.vt = 13;
                    *(_OWORD *)&propvar.decVal.Lo32 = (unsigned __int64)v18;
                    Instance = (*(__int64 (__fastcall **)(void *, __int64 *, struct tagPROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                 ppv,
                                 PKEY_Condition,
                                 &propvar);
                    if ( Instance >= 0 )
                    {
                      if ( !a3->QuadPart
                        || (Instance = IPropertyStore_SetIDList(ppv, PKEY_StartMenu_GroupItem), Instance >= 0) )
                      {
                        *(_OWORD *)&propvar.vt = 0;
                        propvar.vt = 65;
                        propvar.lVal = 20;
                        propvar.bstrblobVal.pData = (BYTE *)&PKEY_StartMenu_Group;
                        Instance = (*(__int64 (__fastcall **)(void *, __int64 *, struct tagPROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                     ppv,
                                     PKEY_ConditionKey,
                                     &propvar);
                        if ( Instance >= 0 )
                          Instance = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, struct IUnknown **))ppv)(
                                       ppv,
                                       a4,
                                       a5);
                      }
                    }
                  }
                  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v18);
                }
                ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v19);
              }
            }
          }
        }
      }
    }
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180032520  push    rbp
0x180032522  push    rbx
0x180032523  push    rsi
0x180032524  push    rdi
0x180032525  push    r13
0x180032527  push    r14
0x180032529  push    r15
0x18003252b  lea     rbp, [rsp-1B0h]
0x180032533  sub     rsp, 2B0h
0x18003253a  mov     rax, cs:__security_cookie
0x180032541  xor     rax, rsp
0x180032544  mov     [rbp+1E0h+var_40], rax
0x18003254b  mov     r15, r9
0x18003254e  mov     rdi, r8
0x180032551  mov     rsi, rdx
0x180032554  mov     r14, [rbp+1E0h+arg_20]
0x18003255b  mov     qword ptr [r14], 0
0x180032562  lea     rcx, [rsp+2E0h+ppv]; void *
0x180032567  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003256c  nop
0x18003256d  lea     rdx, [rsp+2E0h+ppv]; ppv
0x180032572  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180032579  call    cs:__imp_PSCreateMemoryPropertyStore
0x18003257f  mov     ebx, eax
0x180032581  test    eax, eax
0x180032583  js      loc_1800327BE
0x180032589  mov     r8, rsi
0x18003258c  lea     rdx, PKEY_DefaultGroupOrder
0x180032593  mov     rcx, [rsp+2E0h+ppv]
0x180032598  call    IPropertyStore_SetUInt64
0x18003259d  mov     ebx, eax
0x18003259f  test    eax, eax
0x1800325a1  js      loc_1800327BE
0x1800325a7  mov     r8, rsi
0x1800325aa  lea     rdx, PKEY_ChapterId
0x1800325b1  mov     rcx, [rsp+2E0h+ppv]
0x1800325b6  call    IPropertyStore_SetUInt64
0x1800325bb  mov     ebx, eax
0x1800325bd  test    eax, eax
0x1800325bf  js      loc_1800327BE
0x1800325c5  mov     r8, [rdi+10h]
0x1800325c9  lea     rsi, PKEY_StartMenu_Group
0x1800325d0  mov     rdx, rsi
0x1800325d3  mov     rcx, [rsp+2E0h+ppv]
0x1800325d8  call    IPropertyStore_SetString
0x1800325dd  mov     ebx, eax
0x1800325df  test    eax, eax
0x1800325e1  js      loc_1800327BE
0x1800325e7  mov     r13d, 1Fh
0x1800325ed  mov     word ptr [rsp+2E0h+propvar], r13w
0x1800325f3  mov     rax, [rdi+8]
0x1800325f7  mov     [rsp+2E0h+propvar+8], rax
0x1800325fc  mov     [rsp+2E0h+cchText], 104h; cchText
0x180032604  lea     r9, [rbp+1E0h+pwszText]; pwszText
0x180032608  xor     r8d, r8d; pdfFlags
0x18003260b  lea     rdx, [rsp+2E0h+propvar]; propvar
0x180032610  mov     rcx, rsi; propkey
0x180032613  call    cs:__imp_PSFormatForDisplay
0x180032619  mov     ebx, eax
0x18003261b  test    eax, eax
0x18003261d  js      loc_1800327BE
0x180032623  lea     r8, [rbp+1E0h+pwszText]
0x180032627  lea     rdx, PKEY_ItemNameDisplay
0x18003262e  mov     rcx, [rsp+2E0h+ppv]
0x180032633  call    IPropertyStore_SetString
0x180032638  mov     ebx, eax
0x18003263a  test    eax, eax
0x18003263c  js      loc_1800327BE
0x180032642  lea     r8, [rbp+1E0h+pwszText]
0x180032646  lea     rdx, PKEY_ItemId
0x18003264d  mov     rcx, [rsp+2E0h+ppv]
0x180032652  call    IPropertyStore_SetString
0x180032657  mov     ebx, eax
0x180032659  test    eax, eax
0x18003265b  js      loc_1800327BE
0x180032661  lea     rcx, [rbp+1E0h+var_258]; void *
0x180032665  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003266a  nop
0x18003266b  lea     rax, [rbp+1E0h+var_258]
0x18003266f  mov     qword ptr [rsp+2E0h+cchText], rax; ppv
0x180032674  lea     r9, _GUID_71d222e1_432f_429e_8c13_b6dafde5077a; riid
0x18003267b  xor     edx, edx; pUnkOuter
0x18003267d  lea     r8d, [r13-1Eh]; dwClsContext
0x180032681  lea     rcx, _GUID_934d4698_6a59_48f8_9f29_9fb30670320e; rclsid
0x180032688  call    cs:__imp_CoCreateInstance
0x18003268e  mov     ebx, eax
0x180032690  test    eax, eax
0x180032692  js      loc_1800327B4
0x180032698  lea     rcx, [rbp+1E0h+var_260]; void *
0x18003269c  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800326a1  nop
0x1800326a2  mov     rcx, [rbp+1E0h+var_258]
0x1800326a6  mov     word ptr [rsp+2E0h+propvar], r13w
0x1800326ac  mov     rax, [rdi+10h]
0x1800326b0  mov     [rsp+2E0h+propvar+8], rax
0x1800326b5  lea     rax, [rbp+1E0h+var_260]
0x1800326b9  mov     [rsp+2E0h+var_290], rax; void **
0x1800326be  mov     [rsp+2E0h+var_2A0], rcx; struct IConditionFactory2 *
0x1800326c3  lea     rax, psz
0x1800326ca  mov     qword ptr [rsp+2E0h+cchText], rax; unsigned __int16 *
0x1800326cf  xor     r9d, r9d; unsigned __int16 *
0x1800326d2  lea     r8, [rsp+2E0h+propvar]; struct tagPROPVARIANT *
0x1800326d7  lea     edx, [r13-1Eh]; enum tagCONDITION_OPERATION
0x1800326db  mov     rcx, rsi; struct _tagpropertykey *
0x1800326de  call    ?SHCreateLeafConditionEx@@YAJAEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@AEBUtagPROPVARIANT@@PEBG3PEAUIRichChunk@@44PEAUIConditionFactory2@@AEBU_GUID@@PEAPEAX@Z; SHCreateLeafConditionEx(_tagpropertykey const &,tagCONDITION_OPERATION,tagPROPVARIANT const &,ushort const *,ushort const *,IRichChunk *,IRichChunk *,IRichChunk *,IConditionFactory2 *,_GUID const &,void * *)
0x1800326e3  mov     ebx, eax
0x1800326e5  test    eax, eax
0x1800326e7  js      loc_1800327AA
0x1800326ed  mov     rcx, [rsp+2E0h+ppv]
0x1800326f2  xorps   xmm0, xmm0
0x1800326f5  xor     eax, eax
0x1800326f7  movups  xmmword ptr [rsp+2E0h+propvar], xmm0
0x1800326fc  mov     [rsp+2E0h+var_268], rax
0x180032701  lea     eax, [r13-12h]
0x180032705  mov     word ptr [rsp+2E0h+propvar], ax
0x18003270a  mov     rax, [rbp+1E0h+var_260]
0x18003270e  mov     [rsp+2E0h+propvar+8], rax
0x180032713  mov     rax, [rcx]
0x180032716  lea     r8, [rsp+2E0h+propvar]
0x18003271b  lea     rdx, PKEY_Condition
0x180032722  mov     rax, [rax+30h]
0x180032726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003272b  mov     ebx, eax
0x18003272d  test    eax, eax
0x18003272f  js      short loc_1800327AA
0x180032731  mov     r8, [rdi]
0x180032734  test    r8, r8
0x180032737  jz      short loc_180032750
0x180032739  lea     rdx, PKEY_StartMenu_GroupItem
0x180032740  mov     rcx, [rsp+2E0h+ppv]
0x180032745  call    IPropertyStore_SetIDList
0x18003274a  mov     ebx, eax
0x18003274c  test    eax, eax
0x18003274e  js      short loc_1800327AA
0x180032750  mov     rcx, [rsp+2E0h+ppv]
0x180032755  xorps   xmm0, xmm0
0x180032758  movups  xmmword ptr [rsp+2E0h+propvar], xmm0
0x18003275d  mov     eax, 41h ; 'A'
0x180032762  mov     word ptr [rsp+2E0h+propvar], ax
0x180032767  mov     dword ptr [rsp+2E0h+propvar+8], 14h
0x18003276f  mov     [rsp+2E0h+var_268], rsi
0x180032774  mov     rax, [rcx]
0x180032777  lea     r8, [rsp+2E0h+propvar]
0x18003277c  lea     rdx, PKEY_ConditionKey
0x180032783  mov     rax, [rax+30h]
0x180032787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003278c  mov     ebx, eax
0x18003278e  test    eax, eax
0x180032790  js      short loc_1800327AA
0x180032792  mov     rcx, [rsp+2E0h+ppv]
0x180032797  mov     rax, [rcx]
0x18003279a  mov     r8, r14
0x18003279d  mov     rdx, r15
0x1800327a0  mov     rax, [rax]
0x1800327a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327a8  mov     ebx, eax
0x1800327aa  lea     rcx, [rbp+1E0h+var_260]
0x1800327ae  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800327b3  nop
0x1800327b4  lea     rcx, [rbp+1E0h+var_258]
0x1800327b8  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800327bd  nop
0x1800327be  lea     rcx, [rsp+2E0h+ppv]
0x1800327c3  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800327c8  mov     eax, ebx
0x1800327ca  mov     rcx, [rbp+1E0h+var_40]
0x1800327d1  xor     rcx, rsp; StackCookie
0x1800327d4  call    __security_check_cookie
0x1800327d9  add     rsp, 2B0h
0x1800327e0  pop     r15
0x1800327e2  pop     r14
0x1800327e4  pop     r13
0x1800327e6  pop     rdi
0x1800327e7  pop     rsi
0x1800327e8  pop     rbx
0x1800327e9  pop     rbp
0x1800327ea  retn
```
