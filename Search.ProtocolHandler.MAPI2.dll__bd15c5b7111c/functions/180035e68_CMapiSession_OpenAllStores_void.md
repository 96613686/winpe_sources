# CMapiSession::OpenAllStores(void)

- ea: `0x180035e68`
- end: `0x1800361eb`
- name: `?OpenAllStores@CMapiSession@@QEAAJXZ`
- size: `899`
- prototype: `__int64 __fastcall(CMapiSession *__hidden this)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180035898`
- `0x1800361f4`

## callees

- `0x180002300`
- `0x18000ad14`
- `0x18000e0d0`
- `0x18000e658`
- `0x18000e684`
- `0x18000e6e0`
- `0x18000f1c4`
- `0x180011884`
- `0x1800122d8`
- `0x180018970`
- `0x180030754`
- `0x180030a10`
- `0x180031310`
- `0x180035e68`
- `0x18003664c`
- `0x180036f0c`
- `0x180036f80`
- `0x180037480`
- `0x18003f010`

## import_xrefs

- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x1800361a4`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x1800361a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMapiSession::OpenAllStores(CMapiSession *this)
{
  int v2; // ebx
  __int64 v3; // rdx
  ULONG v4; // r15d
  struct _SRowSet *v5; // rbx
  struct _SPropValue *lpProps; // rsi
  struct _MAPIUID *v7; // r14
  LPSPropValue v8; // rcx
  unsigned int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  struct CMapiStore *v12; // rcx
  BOOL v13; // ebx
  _QWORD *v14; // rax
  volatile signed __int32 *v15; // rcx
  int *v16; // rbx
  volatile signed __int32 *v17; // rdi
  unsigned int v19; // [rsp+30h] [rbp-F8h] BYREF
  struct CMapiStore *v20; // [rsp+38h] [rbp-F0h] BYREF
  __int64 v21; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v22; // [rsp+48h] [rbp-E0h] BYREF
  LPSRowSet lpRows; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v24; // [rsp+58h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+60h] [rbp-C8h] BYREF
  ATL::CAtlException *v26; // [rsp+68h] [rbp-C0h] BYREF
  unsigned int v27[13]; // [rsp+70h] [rbp-B8h] BYREF
  int v28; // [rsp+A4h] [rbp-84h]
  volatile signed __int32 *v29; // [rsp+C0h] [rbp-68h] BYREF
  __int64 v30; // [rsp+C8h] [rbp-60h]
  _DWORD v31[6]; // [rsp+D0h] [rbp-58h] BYREF

  try
  {
    v31[0] = 5;
    v31[1] = 268370178;
    v31[2] = 805896195;
    v31[3] = 873726210;
    v31[4] = 805371935;
    v31[5] = 805371934;
    v22 = 0;
    v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 3) + 32LL))(
           *((_QWORD *)this + 3),
           0,
           &v22);
    if ( v2 >= 0 )
      v2 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v22 + 56LL))(v22, v31, 2);
    v3 = 0;
    v19 = 0;
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v22 + 72LL))(v22, 0, &v19);
      v3 = v19;
      if ( v19 > 0x64 )
      {
        v3 = 100;
        v19 = 100;
      }
    }
    lpRows = 0;
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPSRowSet *))(*(_QWORD *)v22 + 152LL))(
             v22,
             v3,
             0,
             &lpRows);
      if ( v2 >= 0 )
      {
        v4 = 0;
        v5 = lpRows;
        while ( 1 )
        {
          if ( v4 >= v5->cRows )
          {
            FreeProws(v5);
            lpRows = 0;
            v2 = 0;
            goto LABEL_39;
          }
          lpProps = v5->aRow[v4].lpProps;
          v7 = lpProps[2].ulPropTag == 873726210 ? (struct _MAPIUID *)lpProps[2].Value.bin.lpb : 0LL;
          if ( lpProps->ulPropTag == 268370178 )
            break;
LABEL_37:
          ++v4;
        }
        CStoreEntryId::CStoreEntryId((CStoreEntryId *)v27);
        if ( (int)CStoreEntryId::Initialize((CStoreEntryId *)v27, *((struct IMAPISession **)this + 3), v7, lpProps) < 0 )
        {
LABEL_36:
          CStoreEntryId::~CStoreEntryId((CStoreEntryId *)v27);
          v5 = lpRows;
          goto LABEL_37;
        }
        v20 = 0;
        ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
          (__int64)&v21,
          (const wchar_t *)&dword_1800444C4);
        v8 = v5->aRow[v4].lpProps;
        if ( LOWORD(v8[3].ulPropTag) == 10 )
        {
          if ( LOWORD(v8[4].ulPropTag) == 10 )
          {
LABEL_35:
            ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
            goto LABEL_36;
          }
          ((void (__fastcall *)(_QWORD, _QWORD))ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=)(
            &v21,
            (CURRENCY)v8[4].Value.cur.int64);
        }
        else
        {
          v9 = ocslen(v8[3].Value.lpszW);
          ATL::CSimpleStringT<wchar_t,0>::SetString(&v21, v10, v9);
        }
        v11 = CMapiSession::OpenStoreInternal((__int64)this, v27, &v20, (__int64)&v21, 1);
        v12 = v20;
        if ( (!v20 || v11 >= 0) && v28 )
        {
          if ( !v20 )
            goto LABEL_29;
          LODWORD(v20) = 0;
          if ( (int)CMapiSupport::CheckPolicyOnStore(v12, (int *)&v20, 0) < 0 || !(_DWORD)v20 )
            goto LABEL_29;
          v13 = 1;
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v24);
          if ( !(unsigned int)CMapiSupport::GetInstalledOutlookVersion(&v24) )
          {
            v14 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
                    &v25,
                    &v24);
            v13 = CMapiSupport::ConvertToIntVersion(v14) > 0xB000000000000LL;
          }
          ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
          if ( v13 )
          {
LABEL_29:
            v20 = 0;
            v27[10] = 1;
            v28 = 1;
            v15 = (volatile signed __int32 *)(v30 - 24);
            v16 = (int *)(v29 - 6);
            if ( (volatile signed __int32 *)(v30 - 24) != v29 - 6 )
            {
              if ( v16[4] >= 0 && *(_QWORD *)v15 == *(_QWORD *)v16 )
              {
                v17 = ATL::CSimpleStringT<wchar_t,0>::CloneData(v15);
                ATL::CStringData::Release((ATL::CStringData *)v16);
                v29 = v17 + 6;
              }
              else
              {
                ATL::CSimpleStringT<wchar_t,0>::SetString(&v29, v30, *(unsigned int *)(v30 - 16));
              }
            }
            CMapiSession::OpenStoreInternal((__int64)this, v27, &v20, (__int64)&v21, 1);
          }
        }
        goto LABEL_35;
      }
    }
LABEL_39:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
  }
  catch ( ATL::CAtlException *v26 )
  {
    v19 = *(_DWORD *)v26;
    CLogger::Error(v19, L"CMapiSession::OpenAllStores threw an exception");
    return v19;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<0>();
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180035e68  mov     r11, rsp
0x180035e6b  push    rbx
0x180035e6c  push    rsi
0x180035e6d  push    rdi
0x180035e6e  push    r13
0x180035e70  push    r14
0x180035e72  push    r15
0x180035e74  sub     rsp, 0F8h
0x180035e7b  mov     rax, cs:__security_cookie
0x180035e82  xor     rax, rsp
0x180035e85  mov     [rsp+128h+var_40], rax
0x180035e8d  mov     r13, rcx
0x180035e90  mov     dword ptr [r11-58h], 5
0x180035e98  mov     dword ptr [r11-54h], 0FFF0102h
0x180035ea0  mov     dword ptr [r11-50h], 30090003h
0x180035ea8  mov     dword ptr [r11-4Ch], 34140102h
0x180035eb0  mov     dword ptr [r11-48h], 3001001Fh
0x180035eb8  mov     dword ptr [r11-44h], 3001001Eh
0x180035ec0  mov     [rsp+128h+var_E0], 0
0x180035ec9  mov     rcx, [rcx+18h]
0x180035ecd  mov     rax, [rcx]
0x180035ed0  lea     r8, [rsp+128h+var_E0]
0x180035ed5  xor     edx, edx
0x180035ed7  mov     rax, [rax+20h]
0x180035edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ee0  mov     ebx, eax
0x180035ee2  test    eax, eax
0x180035ee4  js      short loc_180035F07
0x180035ee6  mov     rcx, [rsp+128h+var_E0]
0x180035eeb  mov     rax, [rcx]
0x180035eee  mov     r8d, 2
0x180035ef4  lea     rdx, [rsp+128h+var_58]
0x180035efc  mov     rax, [rax+38h]
0x180035f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f05  mov     ebx, eax
0x180035f07  xor     edx, edx
0x180035f09  mov     [rsp+128h+var_F8], edx
0x180035f0d  test    ebx, ebx
0x180035f0f  js      short loc_180035F3B
0x180035f11  mov     rcx, [rsp+128h+var_E0]
0x180035f16  mov     rax, [rcx]
0x180035f19  lea     r8, [rsp+128h+var_F8]
0x180035f1e  mov     rax, [rax+48h]
0x180035f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f27  mov     ebx, eax
0x180035f29  mov     edx, [rsp+128h+var_F8]
0x180035f2d  cmp     edx, 64h ; 'd'
0x180035f30  jbe     short loc_180035F3B
0x180035f32  mov     edx, 64h ; 'd'
0x180035f37  mov     [rsp+128h+var_F8], edx
0x180035f3b  mov     [rsp+128h+lpRows], 0
0x180035f44  test    ebx, ebx
0x180035f46  js      loc_1800361B5
0x180035f4c  mov     rcx, [rsp+128h+var_E0]
0x180035f51  mov     rax, [rcx]
0x180035f54  lea     r9, [rsp+128h+lpRows]
0x180035f59  xor     r8d, r8d
0x180035f5c  mov     rax, [rax+98h]
0x180035f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f68  mov     ebx, eax
0x180035f6a  test    eax, eax
0x180035f6c  js      loc_1800361B5
0x180035f72  xor     r15d, r15d
0x180035f75  mov     rbx, [rsp+128h+lpRows]
0x180035f7a  cmp     r15d, [rbx]
0x180035f7d  jnb     loc_1800361A1
0x180035f83  mov     edi, r15d
0x180035f86  inc     rdi
0x180035f89  add     rdi, rdi
0x180035f8c  mov     rsi, [rbx+rdi*8]
0x180035f90  cmp     dword ptr [rsi+30h], 34140102h
0x180035f97  jnz     short loc_180035F9F
0x180035f99  mov     r14, [rsi+40h]
0x180035f9d  jmp     short loc_180035FA2
0x180035f9f  xor     r14d, r14d
0x180035fa2  cmp     dword ptr [rsi], 0FFF0102h
0x180035fa8  jnz     loc_180036199
0x180035fae  lea     rcx, [rsp+128h+var_B8]; this
0x180035fb3  call    ??0CStoreEntryId@@QEAA@XZ; CStoreEntryId::CStoreEntryId(void)
0x180035fb8  nop
0x180035fb9  mov     r9, rsi; struct _SPropValue *
0x180035fbc  mov     r8, r14; struct _MAPIUID *
0x180035fbf  mov     rdx, [r13+18h]; struct IMAPISession *
0x180035fc3  lea     rcx, [rsp+128h+var_B8]; this
0x180035fc8  call    ?Initialize@CStoreEntryId@@QEAAJPEAUIMAPISession@@PEAU_MAPIUID@@PEAU_SPropValue@@@Z; CStoreEntryId::Initialize(IMAPISession *,_MAPIUID *,_SPropValue *)
0x180035fcd  test    eax, eax
0x180035fcf  js      loc_18003618A
0x180035fd5  mov     [rsp+128h+var_F0], 0
0x180035fde  lea     rdx, dword_1800444C4
0x180035fe5  lea     rcx, [rsp+128h+var_E8]
0x180035fea  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x180035fef  nop
0x180035ff0  mov     rcx, [rbx+rdi*8]
0x180035ff4  cmp     word ptr [rcx+48h], 0Ah
0x180035ff9  jnz     short loc_180036016
0x180035ffb  cmp     word ptr [rcx+60h], 0Ah
0x180036000  jz      loc_18003617B
0x180036006  mov     rdx, [rcx+68h]
0x18003600a  lea     rcx, [rsp+128h+var_E8]
0x18003600f  call    ??4?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(char const *)
0x180036014  jmp     short loc_18003602F
0x180036016  mov     rcx, [rcx+50h]; wchar_t *
0x18003601a  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x18003601f  mov     r8d, eax
0x180036022  mov     rdx, rcx
0x180036025  lea     rcx, [rsp+128h+var_E8]
0x18003602a  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18003602f  mov     esi, 1
0x180036034  mov     [rsp+128h+var_108], esi
0x180036038  lea     r9, [rsp+128h+var_E8]
0x18003603d  lea     r8, [rsp+128h+var_F0]
0x180036042  lea     rdx, [rsp+128h+var_B8]
0x180036047  mov     rcx, r13
0x18003604a  call    ?OpenStoreInternal@CMapiSession@@AEAAJAEAVCStoreEntryId@@PEAPEAVCMapiStore@@PEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@H@Z; CMapiSession::OpenStoreInternal(CStoreEntryId &,CMapiStore * *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> *,int)
0x18003604f  mov     rcx, [rsp+128h+var_F0]; struct CMapiStore *
0x180036054  test    rcx, rcx
0x180036057  jz      short loc_180036061
0x180036059  test    eax, eax
0x18003605b  js      loc_18003617B
0x180036061  cmp     [rsp+128h+var_84], 0
0x180036069  jz      loc_18003617B
0x18003606f  test    rcx, rcx
0x180036072  jz      short loc_1800360EE
0x180036074  mov     dword ptr [rsp+128h+var_F0], 0
0x18003607c  xor     r8d, r8d; enum POLICY_RESULT_ID *
0x18003607f  lea     rdx, [rsp+128h+var_F0]; int *
0x180036084  call    ?CheckPolicyOnStore@CMapiSupport@@SAJPEAVCMapiStore@@PEAHPEAW4POLICY_RESULT_ID@@@Z; CMapiSupport::CheckPolicyOnStore(CMapiStore *,int *,POLICY_RESULT_ID *)
0x180036089  test    eax, eax
0x18003608b  js      short loc_1800360EE
0x18003608d  cmp     dword ptr [rsp+128h+var_F0], 0
0x180036092  jz      short loc_1800360EE
0x180036094  mov     ebx, esi
0x180036096  lea     rcx, [rsp+128h+var_D0]
0x18003609b  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x1800360a0  nop
0x1800360a1  lea     rcx, [rsp+128h+var_D0]
0x1800360a6  call    ?GetInstalledOutlookVersion@CMapiSupport@@SAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::GetInstalledOutlookVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x1800360ab  test    eax, eax
0x1800360ad  jnz     short loc_1800360D8
0x1800360af  lea     rdx, [rsp+128h+var_D0]
0x1800360b4  lea     rcx, [rsp+128h+var_C8]
0x1800360b9  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x1800360be  mov     rcx, rax
0x1800360c1  call    ?ConvertToIntVersion@CMapiSupport@@SA_JV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::ConvertToIntVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>)
0x1800360c6  xor     ebx, ebx
0x1800360c8  mov     rcx, 0B000000000000h
0x1800360d2  cmp     rax, rcx
0x1800360d5  setnle  bl
0x1800360d8  mov     rcx, [rsp+128h+var_D0]
0x1800360dd  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800360e1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800360e6  test    ebx, ebx
0x1800360e8  jz      loc_18003617B
0x1800360ee  mov     [rsp+128h+var_F0], 0
0x1800360f7  mov     [rsp+128h+var_90], esi
0x1800360fe  mov     [rsp+128h+var_84], esi
0x180036105  mov     rdx, [rsp+128h+var_60]
0x18003610d  lea     rcx, [rdx-18h]
0x180036111  mov     rbx, [rsp+128h+var_68]
0x180036119  add     rbx, 0FFFFFFFFFFFFFFE8h
0x18003611d  cmp     rcx, rbx
0x180036120  jz      short loc_18003615F
0x180036122  cmp     dword ptr [rbx+10h], 0
0x180036126  jl      short loc_18003614E
0x180036128  mov     rax, [rbx]
0x18003612b  cmp     [rcx], rax
0x18003612e  jnz     short loc_18003614E
0x180036130  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x180036135  mov     rdi, rax
0x180036138  mov     rcx, rbx; this
0x18003613b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180036140  lea     rax, [rdi+18h]
0x180036144  mov     [rsp+128h+var_68], rax
0x18003614c  jmp     short loc_18003615F
0x18003614e  mov     r8d, [rdx-10h]
0x180036152  lea     rcx, [rsp+128h+var_68]
0x18003615a  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18003615f  mov     [rsp+128h+var_108], esi
0x180036163  lea     r9, [rsp+128h+var_E8]
0x180036168  lea     r8, [rsp+128h+var_F0]
0x18003616d  lea     rdx, [rsp+128h+var_B8]
0x180036172  mov     rcx, r13
0x180036175  call    ?OpenStoreInternal@CMapiSession@@AEAAJAEAVCStoreEntryId@@PEAPEAVCMapiStore@@PEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@H@Z; CMapiSession::OpenStoreInternal(CStoreEntryId &,CMapiStore * *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> *,int)
0x18003617a  nop
0x18003617b  mov     rcx, [rsp+128h+var_E8]
0x180036180  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180036184  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180036189  nop
0x18003618a  lea     rcx, [rsp+128h+var_B8]; this
0x18003618f  call    ??1CStoreEntryId@@QEAA@XZ; CStoreEntryId::~CStoreEntryId(void)
0x180036194  mov     rbx, [rsp+128h+lpRows]
0x180036199  inc     r15d
0x18003619c  jmp     loc_180035F7A
0x1800361a1  mov     rcx, rbx; lpRows
0x1800361a4  call    cs:__imp_FreeProws
0x1800361aa  mov     [rsp+128h+lpRows], 0
0x1800361b3  xor     ebx, ebx
0x1800361b5  lea     rcx, [rsp+128h+var_E0]
0x1800361ba  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800361bf  nop
0x1800361c0  jmp     short loc_1800361C8
0x1800361c2  jmp     short $+2
0x1800361c4  mov     ebx, [rsp+128h+var_F8]
0x1800361c8  mov     eax, ebx
0x1800361ca  mov     rcx, [rsp+128h+var_40]
0x1800361d2  xor     rcx, rsp; StackCookie
0x1800361d5  call    __security_check_cookie
0x1800361da  add     rsp, 0F8h
0x1800361e1  pop     r15
0x1800361e3  pop     r14
0x1800361e5  pop     r13
0x1800361e7  pop     rdi
0x1800361e8  pop     rsi
0x1800361e9  pop     rbx
0x1800361ea  retn
```
