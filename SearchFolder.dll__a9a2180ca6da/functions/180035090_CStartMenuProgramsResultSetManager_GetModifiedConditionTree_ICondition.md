# CStartMenuProgramsResultSetManager::_GetModifiedConditionTree(ICondition * *)

- ea: `0x180035090`
- end: `0x18003531f`
- name: `?_GetModifiedConditionTree@CStartMenuProgramsResultSetManager@@AEAAJPEAPEAUICondition@@@Z`
- size: `655`
- prototype: `__int64 __fastcall(CStartMenuProgramsResultSetManager *__hidden this, struct ICondition **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033838`

## callees

- `0x1800054b0`
- `0x180005c74`
- `0x180005c88`
- `0x180006900`
- `0x1800076dc`
- `0x18000e3b0`
- `0x18000e4fc`
- `0x180022104`
- `0x1800295f4`
- `0x180035090`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800351b1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800351b1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800352f0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800352f0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035162`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035162`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStartMenuProgramsResultSetManager::_GetModifiedConditionTree(
        CStartMenuProgramsResultSetManager *this,
        struct ICondition **a2)
{
  __int64 v3; // r10
  HRESULT Instance; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  struct IRichChunk *v7; // [rsp+28h] [rbp-D8h]
  struct IRichChunk *v8; // [rsp+30h] [rbp-D0h]
  struct ICondition **v9; // [rsp+38h] [rbp-C8h]
  const struct _GUID *v10; // [rsp+48h] [rbp-B8h]
  void *v11; // [rsp+60h] [rbp-A0h] BYREF
  struct IConditionFactory2 *v12; // [rsp+68h] [rbp-98h] BYREF
  struct ICondition *v13; // [rsp+70h] [rbp-90h] BYREF
  struct ICondition *v14; // [rsp+78h] [rbp-88h] BYREF
  IRichChunk v15; // [rsp+80h] [rbp-80h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+88h] [rbp-78h] BYREF
  struct tagPROPVARIANT v17; // [rsp+A0h] [rbp-60h] BYREF
  struct ICondition *v18[3]; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR Buffer[264]; // [rsp+D0h] [rbp-30h] BYREF

  *a2 = 0;
  memset(&pvar, 0, sizeof(pvar));
  pvar.vt = 19;
  pvar.lVal = 0x20000000;
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v15);
  Instance = ConstructPropVariantConditionTree(
               *(struct ICondition **)(v3 + 64),
               &PKEY_SFGAOFlags,
               COP_APPLICATION_SPECIFIC,
               CT_AND_CONDITION,
               1,
               &pvar,
               L"System.StructuredQueryType.AllBitsSet",
               (struct ICondition **)&v15);
  if ( Instance >= 0 )
  {
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v12);
    Instance = CoCreateInstance(
                 &GUID_934d4698_6a59_48f8_9f29_9fb30670320e,
                 0,
                 1u,
                 &GUID_71d222e1_432f_429e_8c13_b6dafde5077a,
                 (LPVOID *)&v12);
    if ( Instance >= 0 )
    {
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v14);
      memset_0(Buffer, 0, 0x208u);
      memset(&v17, 0, sizeof(v17));
      LoadStringW(g_hinst, 0x2347u, Buffer, 260);
      v17.vt = 31;
      v17.hVal.QuadPart = (LONGLONG)Buffer;
      Instance = SHCreateLeafConditionEx(
                   &PKEY_ItemNameDisplay,
                   COP_VALUE_STARTSWITH,
                   &v17,
                   L"System.StructuredQueryType.String",
                   &psz,
                   v7,
                   v8,
                   (struct IRichChunk *)v9,
                   v12,
                   v10,
                   (void **)&v14);
      if ( Instance >= 0 )
      {
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v13);
        Instance = ConstructPropVariantConditionTree(
                     v14,
                     &PKEY_Link_TargetSFGAOFlags,
                     COP_APPLICATION_SPECIFIC,
                     CT_OR_CONDITION,
                     1,
                     &pvar,
                     L"System.StructuredQueryType.AllBitsSet",
                     &v13);
        if ( Instance >= 0 )
        {
          v18[0] = (struct ICondition *)v15.lpVtbl;
          v18[1] = v13;
          ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v11);
          Instance = SHCombineMultipleConditionsEx(CT_AND_CONDITION, v18, 2u, v12, (const struct _GUID *)ppv, &v11);
          if ( Instance >= 0 )
          {
            Instance = SetEvalStateEx(v11, L"StartMenuCondition", 1);
            if ( Instance >= 0 )
              *a2 = (struct ICondition *)ATL::CComPtrBase<IScope>::Detach(&v11);
          }
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v11);
        }
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v13);
      }
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v14);
    }
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v12);
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v15);
  PropVariantClear((PROPVARIANT *)&pvar);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180035090  mov     [rsp-8+arg_10], rbx
0x180035095  mov     [rsp-8+arg_18], rsi
0x18003509a  push    rbp
0x18003509b  push    rdi
0x18003509c  push    r15
0x18003509e  lea     rbp, [rsp-1F0h]
0x1800350a6  sub     rsp, 2F0h
0x1800350ad  mov     rax, cs:__security_cookie
0x1800350b4  xor     rax, rsp
0x1800350b7  mov     [rbp+200h+var_20], rax
0x1800350be  mov     rdi, rdx
0x1800350c1  mov     r10, rcx
0x1800350c4  mov     qword ptr [rdx], 0
0x1800350cb  xorps   xmm0, xmm0
0x1800350ce  xor     eax, eax
0x1800350d0  movups  xmmword ptr [rbp+200h+pvar], xmm0
0x1800350d4  mov     [rbp+200h+var_268], rax
0x1800350d8  mov     eax, 13h
0x1800350dd  mov     word ptr [rbp+200h+pvar], ax
0x1800350e1  mov     dword ptr [rbp+200h+pvar+8], 20000000h
0x1800350e8  lea     rcx, [rbp+200h+var_280]; void *
0x1800350ec  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800350f1  nop
0x1800350f2  lea     rax, [rbp+200h+var_280]
0x1800350f6  mov     [rsp+300h+var_2C8], rax; struct IRichChunk *
0x1800350fb  lea     r15, aSystemStructur_0; "System.StructuredQueryType.AllBitsSet"
0x180035102  mov     [rsp+300h+var_2D0], r15; struct IRichChunk *
0x180035107  lea     rax, [rbp+200h+pvar]
0x18003510b  mov     [rsp+300h+var_2D8], rax; struct IRichChunk *
0x180035110  mov     esi, 1
0x180035115  mov     dword ptr [rsp+300h+ppv], esi; int
0x180035119  xor     r9d, r9d; enum tagCONDITION_TYPE
0x18003511c  lea     r8d, [rsi+0Dh]; enum tagCONDITION_OPERATION
0x180035120  lea     rdx, PKEY_SFGAOFlags; struct _tagpropertykey *
0x180035127  mov     rcx, [r10+40h]; struct ICondition *
0x18003512b  call    ?ConstructPropVariantConditionTree@@YAJPEAUICondition@@AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@W4tagCONDITION_TYPE@@HAEBUtagPROPVARIANT@@PEBGPEAPEAU1@@Z; ConstructPropVariantConditionTree(ICondition *,_tagpropertykey const &,tagCONDITION_OPERATION,tagCONDITION_TYPE,int,tagPROPVARIANT const &,ushort const *,ICondition * *)
0x180035130  mov     ebx, eax
0x180035132  test    eax, eax
0x180035134  js      loc_1800352E2
0x18003513a  lea     rcx, [rsp+300h+var_298]; void *
0x18003513f  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180035144  nop
0x180035145  lea     rax, [rsp+300h+var_298]
0x18003514a  mov     [rsp+300h+ppv], rax; ppv
0x18003514f  lea     r9, _GUID_71d222e1_432f_429e_8c13_b6dafde5077a; riid
0x180035156  mov     r8d, esi; dwClsContext
0x180035159  xor     edx, edx; pUnkOuter
0x18003515b  lea     rcx, _GUID_934d4698_6a59_48f8_9f29_9fb30670320e; rclsid
0x180035162  call    cs:__imp_CoCreateInstance
0x180035168  mov     ebx, eax
0x18003516a  test    eax, eax
0x18003516c  js      loc_1800352D7
0x180035172  lea     rcx, [rsp+300h+var_288]; void *
0x180035177  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003517c  nop
0x18003517d  xor     edx, edx; Val
0x18003517f  mov     r8d, 208h; Size
0x180035185  lea     rcx, [rbp+200h+Buffer]; void *
0x180035189  call    memset_0
0x18003518e  xorps   xmm0, xmm0
0x180035191  xor     eax, eax
0x180035193  movups  xmmword ptr [rbp+200h+var_260], xmm0
0x180035197  mov     qword ptr [rbp+200h+var_260+10h], rax
0x18003519b  mov     r9d, 104h; cchBufferMax
0x1800351a1  lea     r8, [rbp+200h+Buffer]; lpBuffer
0x1800351a5  mov     edx, 2347h; uID
0x1800351aa  mov     rcx, cs:g_hinst; hInstance
0x1800351b1  call    cs:__imp_LoadStringW
0x1800351b7  lea     eax, [rsi+1Eh]
0x1800351ba  mov     word ptr [rbp+200h+var_260], ax
0x1800351be  lea     rax, [rbp+200h+Buffer]
0x1800351c2  mov     qword ptr [rbp+200h+var_260+8], rax
0x1800351c6  mov     rax, [rsp+300h+var_298]
0x1800351cb  lea     rcx, [rsp+300h+var_288]
0x1800351d0  mov     [rsp+300h+var_2B0], rcx; void **
0x1800351d5  mov     [rsp+300h+var_2C0], rax; struct IConditionFactory2 *
0x1800351da  lea     rax, psz
0x1800351e1  mov     [rsp+300h+ppv], rax; unsigned __int16 *
0x1800351e6  lea     r9, aSystemStructur_2; "System.StructuredQueryType.String"
0x1800351ed  lea     r8, [rbp+200h+var_260]; struct tagPROPVARIANT *
0x1800351f1  lea     edx, [rsi+6]; enum tagCONDITION_OPERATION
0x1800351f4  lea     rcx, PKEY_ItemNameDisplay; struct _tagpropertykey *
0x1800351fb  call    ?SHCreateLeafConditionEx@@YAJAEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@AEBUtagPROPVARIANT@@PEBG3PEAUIRichChunk@@44PEAUIConditionFactory2@@AEBU_GUID@@PEAPEAX@Z; SHCreateLeafConditionEx(_tagpropertykey const &,tagCONDITION_OPERATION,tagPROPVARIANT const &,ushort const *,ushort const *,IRichChunk *,IRichChunk *,IRichChunk *,IConditionFactory2 *,_GUID const &,void * *)
0x180035200  mov     ebx, eax
0x180035202  test    eax, eax
0x180035204  js      loc_1800352CC
0x18003520a  lea     rcx, [rsp+300h+var_290]; void *
0x18003520f  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180035214  nop
0x180035215  lea     rax, [rsp+300h+var_290]
0x18003521a  mov     [rsp+300h+var_2C8], rax; struct ICondition **
0x18003521f  mov     [rsp+300h+var_2D0], r15; unsigned __int16 *
0x180035224  lea     rax, [rbp+200h+pvar]
0x180035228  mov     [rsp+300h+var_2D8], rax; struct tagPROPVARIANT *
0x18003522d  mov     dword ptr [rsp+300h+ppv], esi; struct _GUID *
0x180035231  mov     r9d, esi; enum tagCONDITION_TYPE
0x180035234  lea     r8d, [rsi+0Dh]; enum tagCONDITION_OPERATION
0x180035238  lea     rdx, PKEY_Link_TargetSFGAOFlags; struct _tagpropertykey *
0x18003523f  mov     rcx, [rsp+300h+var_288]; struct ICondition *
0x180035244  call    ?ConstructPropVariantConditionTree@@YAJPEAUICondition@@AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@W4tagCONDITION_TYPE@@HAEBUtagPROPVARIANT@@PEBGPEAPEAU1@@Z; ConstructPropVariantConditionTree(ICondition *,_tagpropertykey const &,tagCONDITION_OPERATION,tagCONDITION_TYPE,int,tagPROPVARIANT const &,ushort const *,ICondition * *)
0x180035249  mov     ebx, eax
0x18003524b  test    eax, eax
0x18003524d  js      short loc_1800352C1
0x18003524f  mov     rax, [rbp+200h+var_280.lpVtbl]
0x180035253  mov     [rbp+200h+var_248], rax
0x180035257  mov     rax, [rsp+300h+var_290]
0x18003525c  mov     [rbp+200h+var_240], rax
0x180035260  lea     rcx, [rsp+300h+var_2A0]; void *
0x180035265  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003526a  nop
0x18003526b  lea     rax, [rsp+300h+var_2A0]
0x180035270  mov     [rsp+300h+var_2D8], rax; void **
0x180035275  mov     r9, [rsp+300h+var_298]; struct IConditionFactory2 *
0x18003527a  lea     r8d, [rsi+1]; unsigned int
0x18003527e  lea     rdx, [rbp+200h+var_248]; struct ICondition **
0x180035282  xor     ecx, ecx; enum tagCONDITION_TYPE
0x180035284  call    ?SHCombineMultipleConditionsEx@@YAJW4tagCONDITION_TYPE@@PEAPEAUICondition@@IPEAUIConditionFactory2@@AEBU_GUID@@PEAPEAX@Z; SHCombineMultipleConditionsEx(tagCONDITION_TYPE,ICondition * *,uint,IConditionFactory2 *,_GUID const &,void * *)
0x180035289  mov     ebx, eax
0x18003528b  test    eax, eax
0x18003528d  js      short loc_1800352B6
0x18003528f  mov     r8d, esi
0x180035292  lea     rdx, aStartmenucondi; "StartMenuCondition"
0x180035299  mov     rcx, [rsp+300h+var_2A0]
0x18003529e  call    SetEvalStateEx
0x1800352a3  mov     ebx, eax
0x1800352a5  test    eax, eax
0x1800352a7  js      short loc_1800352B6
0x1800352a9  lea     rcx, [rsp+300h+var_2A0]
0x1800352ae  call    ?Detach@?$CComPtrBase@UIScope@@@ATL@@QEAAPEAUIScope@@XZ; ATL::CComPtrBase<IScope>::Detach(void)
0x1800352b3  mov     [rdi], rax
0x1800352b6  lea     rcx, [rsp+300h+var_2A0]
0x1800352bb  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800352c0  nop
0x1800352c1  lea     rcx, [rsp+300h+var_290]
0x1800352c6  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800352cb  nop
0x1800352cc  lea     rcx, [rsp+300h+var_288]
0x1800352d1  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800352d6  nop
0x1800352d7  lea     rcx, [rsp+300h+var_298]
0x1800352dc  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800352e1  nop
0x1800352e2  lea     rcx, [rbp+200h+var_280]
0x1800352e6  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800352eb  nop
0x1800352ec  lea     rcx, [rbp+200h+pvar]; pvar
0x1800352f0  call    cs:__imp_PropVariantClear
0x1800352f6  mov     eax, ebx
0x1800352f8  mov     rcx, [rbp+200h+var_20]
0x1800352ff  xor     rcx, rsp; StackCookie
0x180035302  call    __security_check_cookie
0x180035307  lea     r11, [rsp+300h+var_10]
0x18003530f  mov     rbx, [r11+30h]
0x180035313  mov     rsi, [r11+38h]
0x180035317  mov     rsp, r11
0x18003531a  pop     r15
0x18003531c  pop     rdi
0x18003531d  pop     rbp
0x18003531e  retn
```
