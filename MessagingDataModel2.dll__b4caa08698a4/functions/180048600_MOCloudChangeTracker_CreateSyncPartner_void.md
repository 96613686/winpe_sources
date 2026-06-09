# MOCloudChangeTracker::CreateSyncPartner(void)

- ea: `0x180048600`
- end: `0x180048a86`
- name: `?CreateSyncPartner@MOCloudChangeTracker@@IEAAJXZ`
- size: `1158`
- prototype: `__int64 __fastcall(MOCloudChangeTracker *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180048ae0`

## callees

- `0x180005c50`
- `0x1800065c8`
- `0x18000c46c`
- `0x18000c4a8`
- `0x180012f08`
- `0x180048600`
- `0x180048b28`
- `0x180048b58`
- `0x1800c50ec`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180048724`
- `msvcrt!memcpy_s` at `0x180048724`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004864b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004864b`
- `CEMAPI!MAPIFreeBuffer` at `0x1800486bb`
- `CEMAPI!MAPIFreeBuffer` at `0x180048860`
- `CEMAPI!MAPIFreeBuffer` at `0x1800488cf`
- `CEMAPI!MAPIFreeBuffer` at `0x180048a31`
- `CEMAPI!MAPIFreeBuffer` at `0x180048a3b`
- `CEMAPI!MAPIFreeBuffer` at `0x180048a52`
- `CEMAPI!MAPIFreeBuffer` at `0x1800486bb`
- `CEMAPI!MAPIFreeBuffer` at `0x180048860`
- `CEMAPI!MAPIFreeBuffer` at `0x1800488cf`
- `CEMAPI!MAPIFreeBuffer` at `0x180048a31`
- `CEMAPI!MAPIFreeBuffer` at `0x180048a3b`
- `CEMAPI!MAPIFreeBuffer` at `0x180048a52`
- `CEMAPI!HrGetOneProp` at `0x18004869b`
- `CEMAPI!HrGetOneProp` at `0x180048841`
- `CEMAPI!HrGetOneProp` at `0x18004869b`
- `CEMAPI!HrGetOneProp` at `0x180048841`

## pseudocode

```c
__int64 __fastcall MOCloudChangeTracker::CreateSyncPartner(MOCloudChangeTracker *this)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  LPSPropValue *v4; // rbx
  struct IMAPIProp *v5; // rax
  HRESULT OneProp; // eax
  int v7; // ecx
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rax
  int v12; // eax
  int v13; // ecx
  LPSPropValue *v14; // rbx
  struct IMAPIProp *v15; // rax
  HRESULT v16; // eax
  int v17; // ecx
  struct ENTRYID *v18; // rbx
  __int64 v19; // rax
  int v20; // eax
  struct ENTRYID *v21; // rcx
  int v22; // eax
  struct ENTRYID *v23; // rsi
  int v24; // eax
  int v25; // ecx
  struct IUnknown *v26; // rdx
  unsigned int v28[2]; // [rsp+40h] [rbp-49h] BYREF
  struct ENTRYID *v29; // [rsp+48h] [rbp-41h]
  LPVOID pv; // [rsp+50h] [rbp-39h] BYREF
  LPVOID v31; // [rsp+58h] [rbp-31h] BYREF
  struct IUnknown *v32; // [rsp+60h] [rbp-29h] BYREF
  struct IUnknown *v33; // [rsp+68h] [rbp-21h] BYREF
  unsigned int v34; // [rsp+70h] [rbp-19h] BYREF
  __int64 v35; // [rsp+78h] [rbp-11h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp-9h] BYREF
  __int128 Destination; // [rsp+88h] [rbp-1h] BYREF
  int v38; // [rsp+98h] [rbp+Fh]

  ppv = 0;
  v2 = CoCreateInstance(
         &GUID_40b47a8f_c442_4f06_8304_aa1058edeea0,
         0,
         0x17u,
         &GUID_21e1b5a4_0010_437a_bfa7_9d1455238f39,
         &ppv);
  v3 = v2;
  if ( v2 >= 0 )
  {
    pv = 0;
    v4 = (LPSPropValue *)CMapiProps::operator&(&pv);
    v5 = (struct IMAPIProp *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 512LL))(*((_QWORD *)this + 8));
    OneProp = HrGetOneProp(v5, 0xFFF0102u, v4);
    v3 = OneProp;
    if ( OneProp < 0 )
      goto LABEL_4;
    Destination = 0;
    v38 = 0;
    if ( *(_DWORD *)(CMapiProps::operator->(&pv) + 8) != 20 )
    {
      Log_AssertionEvent_21(v9, v8, 81);
      if ( *(_DWORD *)(CMapiProps::operator->(&pv) + 8) != 20 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    v10 = *(_DWORD *)(CMapiProps::operator->(&pv) + 8);
    v11 = CMapiProps::operator->(&pv);
    if ( memcpy_s(&Destination, 0x14u, *(const void *const *)(v11 + 16), v10) )
    {
      v3 = -2147467259;
      v7 = -2147467259;
      goto LABEL_5;
    }
    v34 = -1;
    OneProp = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int128 *, unsigned int *))(*(_QWORD *)ppv + 56LL))(
                ppv,
                1,
                20,
                &Destination,
                &v34);
    v3 = OneProp;
    if ( OneProp < 0 )
    {
LABEL_4:
      v7 = OneProp;
LABEL_5:
      Log_HREvent_22(v7);
LABEL_6:
      MAPIFreeBuffer(pv);
LABEL_45:
      pv = 0;
      goto LABEL_46;
    }
    v32 = 0;
    if ( (*(int (__fastcall **)(LPVOID, _QWORD, __int64 *, struct IUnknown **))(*(_QWORD *)ppv + 96LL))(
           ppv,
           v34,
           qword_1800D9960,
           &v32) < 0 )
    {
      v12 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *, const wchar_t *, __int64 *, struct IUnknown **))(*(_QWORD *)ppv + 88LL))(
              ppv,
              v34,
              qword_1800D9960,
              L"MOCloudMessageSyncPartner",
              qword_1800D9870,
              &v32);
      v3 = v12;
      if ( v12 < 0 )
      {
        v13 = v12;
LABEL_16:
        Log_HREvent_22(v13);
LABEL_17:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
        goto LABEL_6;
      }
    }
    if ( !v32 )
    {
      v3 = -2147467259;
      v13 = -2147467259;
      goto LABEL_16;
    }
    v31 = 0;
    v14 = (LPSPropValue *)CMapiProps::operator&(&v31);
    v15 = (struct IMAPIProp *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 512LL))(*((_QWORD *)this + 8));
    v16 = HrGetOneProp(v15, 0x81060102, v14);
    v3 = v16;
    if ( v16 < 0 )
    {
      v17 = v16;
LABEL_22:
      Log_HREvent_22(v17);
LABEL_23:
      MAPIFreeBuffer(v31);
      v31 = 0;
      goto LABEL_17;
    }
    if ( *(_DWORD *)(CMapiProps::operator->(&v31) + 8) != 20 )
    {
      v3 = -2147467259;
      v17 = -2147467259;
      goto LABEL_22;
    }
    *(_QWORD *)v28 = 0;
    v29 = 0;
    v18 = *(struct ENTRYID **)(CMapiProps::operator->(&v31) + 16);
    v19 = CMapiProps::operator->(&v31);
    v20 = CEntryId::Set((CEntryId *)v28, *(_DWORD *)(v19 + 8), v18);
    v3 = v20;
    if ( v20 < 0 )
    {
      Log_HREvent_22(v20);
LABEL_28:
      v21 = v29;
LABEL_29:
      MAPIFreeBuffer(v21);
      goto LABEL_23;
    }
    v35 = 0;
    v22 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))v32->lpVtbl[7].AddRef)(v32, &v35);
    v3 = v22;
    if ( v22 < 0 )
    {
      Log_HREvent_22(v22);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
      goto LABEL_28;
    }
    v23 = v29;
    v33 = 0;
    v24 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _QWORD, struct ENTRYID *, struct IUnknown **))v32->lpVtbl[7].Release)(
            v32,
            1,
            v28[0],
            v29,
            &v33);
    v3 = v24;
    if ( v24 < 0 )
      goto LABEL_33;
    v26 = v33;
    if ( !v33 )
    {
      v24 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct ENTRYID *, const wchar_t *, struct IUnknown **))(*(_QWORD *)v35 + 176LL))(
              v35,
              1,
              v28[0],
              v23,
              L"SmsStoreInbox",
              &v33);
      v3 = v24;
      if ( v24 < 0 )
      {
LABEL_33:
        v25 = v24;
LABEL_34:
        Log_HREvent_22(v25);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
        v21 = v23;
        goto LABEL_29;
      }
      v26 = v33;
      if ( !v33 )
      {
        v3 = -2147467259;
        v25 = -2147467259;
        goto LABEL_34;
      }
    }
    *((_DWORD *)this + 18) = v34;
    if ( *((struct IUnknown **)this + 10) != v32 )
    {
      ATL::AtlComPtrAssign((struct IUnknown **)this + 10, v32);
      v26 = v33;
    }
    if ( *((struct IUnknown **)this + 11) != v26 )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 11, v26);
    v24 = CEntryId::Set((MOCloudChangeTracker *)((char *)this + 104), v28[0], v23);
    v3 = v24;
    if ( v24 >= 0 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
      MAPIFreeBuffer(v23);
      MAPIFreeBuffer(v31);
      v31 = 0;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
      MAPIFreeBuffer(pv);
      v3 = 0;
      goto LABEL_45;
    }
    goto LABEL_33;
  }
  Log_HREvent_22(v2);
LABEL_46:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return v3;
}

```

## disassembly

```asm
0x180048600  push    rbp
0x180048602  push    rbx
0x180048603  push    rsi
0x180048604  push    rdi
0x180048605  push    r12
0x180048607  push    r14
0x180048609  lea     rbp, [rsp-2Fh]
0x18004860e  sub     rsp, 0B8h
0x180048615  mov     rax, cs:__security_cookie
0x18004861c  xor     rax, rsp
0x18004861f  mov     [rbp+57h+var_40], rax
0x180048623  xor     r12d, r12d
0x180048626  lea     rax, [rbp+57h+var_60]
0x18004862a  mov     r14, rcx
0x18004862d  mov     [rbp+57h+var_60], r12
0x180048631  lea     r9, _GUID_21e1b5a4_0010_437a_bfa7_9d1455238f39; riid
0x180048638  mov     [rsp+0E0h+ppv], rax; ppv
0x18004863d  xor     edx, edx; pUnkOuter
0x18004863f  lea     rcx, _GUID_40b47a8f_c442_4f06_8304_aa1058edeea0; rclsid
0x180048646  lea     r8d, [r12+17h]; dwClsContext
0x18004864b  call    cs:__imp_CoCreateInstance
0x180048651  mov     ebx, eax
0x180048653  test    eax, eax
0x180048655  jns     short loc_18004866D
0x180048657  lea     edx, [r12+1]
0x18004865c  mov     ecx, eax; int
0x18004865e  lea     r9d, [r12+4Bh]
0x180048663  call    Log_HREvent_22
0x180048668  jmp     loc_180048A5F
0x18004866d  lea     rcx, [rbp+57h+pv]
0x180048671  mov     [rbp+57h+pv], r12
0x180048675  call    ??ICMapiProps@@QEAAPEAPEAU_SPropValue@@XZ; CMapiProps::operator&(void)
0x18004867a  mov     rcx, [r14+40h]
0x18004867e  mov     rbx, rax
0x180048681  mov     rdx, [rcx]
0x180048684  mov     rax, [rdx+200h]
0x18004868b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048690  mov     r8, rbx; lppProp
0x180048693  mov     edx, 0FFF0102h; ulPropTag
0x180048698  mov     rcx, rax; lpMapiProp
0x18004869b  call    cs:__imp_HrGetOneProp
0x1800486a1  mov     ebx, eax
0x1800486a3  test    eax, eax
0x1800486a5  jns     short loc_1800486C6
0x1800486a7  mov     edx, 1
0x1800486ac  lea     r9d, [rdx+4Dh]
0x1800486b0  mov     ecx, eax; int
0x1800486b2  call    Log_HREvent_22
0x1800486b7  mov     rcx, [rbp+57h+pv]; pv
0x1800486bb  call    cs:__imp_MAPIFreeBuffer
0x1800486c1  jmp     loc_180048A5B
0x1800486c6  xorps   xmm0, xmm0
0x1800486c9  lea     rcx, [rbp+57h+pv]
0x1800486cd  xor     eax, eax
0x1800486cf  movups  [rbp+57h+Destination], xmm0
0x1800486d3  mov     [rbp+57h+var_48], eax
0x1800486d6  call    ??CCMapiProps@@QEAAPEAU_SPropValue@@XZ; CMapiProps::operator->(void)
0x1800486db  mov     esi, 14h
0x1800486e0  cmp     [rax+8], esi
0x1800486e3  jz      short loc_180048701
0x1800486e5  lea     r8d, [rsi+3Dh]
0x1800486e9  call    Log_AssertionEvent_21
0x1800486ee  lea     rcx, [rbp+57h+pv]
0x1800486f2  call    ??CCMapiProps@@QEAAPEAU_SPropValue@@XZ; CMapiProps::operator->(void)
0x1800486f7  cmp     [rax+8], esi
0x1800486fa  jz      short loc_180048701
0x1800486fc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180048701  lea     rcx, [rbp+57h+pv]
0x180048705  call    ??CCMapiProps@@QEAAPEAU_SPropValue@@XZ; CMapiProps::operator->(void)
0x18004870a  lea     rcx, [rbp+57h+pv]
0x18004870e  mov     ebx, [rax+8]
0x180048711  call    ??CCMapiProps@@QEAAPEAU_SPropValue@@XZ; CMapiProps::operator->(void)
0x180048716  mov     r9d, ebx; SourceSize
0x180048719  lea     rcx, [rbp+57h+Destination]; Destination
0x18004871d  mov     rdx, rsi; DestinationSize
0x180048720  mov     r8, [rax+10h]; Source
0x180048724  call    cs:__imp_memcpy_s
0x18004872a  test    eax, eax
0x18004872c  jz      short loc_180048740
0x18004872e  xor     edx, edx
0x180048730  mov     ebx, 80004005h
0x180048735  mov     ecx, ebx
0x180048737  lea     r9d, [rdx+53h]
0x18004873b  jmp     loc_1800486B2
0x180048740  mov     rcx, [rbp+57h+var_60]
0x180048744  lea     rdx, [rbp+57h+var_70]
0x180048748  mov     [rbp+57h+var_70], 0FFFFFFFFh
0x18004874f  lea     r9, [rbp+57h+Destination]
0x180048753  mov     [rsp+0E0h+ppv], rdx
0x180048758  mov     edi, 1
0x18004875d  mov     r8d, esi
0x180048760  mov     edx, edi
0x180048762  mov     rax, [rcx]
0x180048765  mov     rax, [rax+38h]
0x180048769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004876e  mov     ebx, eax
0x180048770  test    eax, eax
0x180048772  jns     short loc_18004877F
0x180048774  lea     r9d, [rdi+56h]
0x180048778  mov     edx, edi
0x18004877a  jmp     loc_1800486B0
0x18004877f  mov     rcx, [rbp+57h+var_60]
0x180048783  lea     r9, [rbp+57h+var_80]
0x180048787  mov     edx, [rbp+57h+var_70]
0x18004878a  lea     r8, qword_1800D9960
0x180048791  mov     [rbp+57h+var_80], r12
0x180048795  mov     rax, [rcx]
0x180048798  mov     rax, [rax+60h]
0x18004879c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800487a1  test    eax, eax
0x1800487a3  jns     short loc_1800487FE
0x1800487a5  mov     rcx, [rbp+57h+var_60]
0x1800487a9  lea     rdx, [rbp+57h+var_80]
0x1800487ad  mov     [rsp+0E0h+var_B8], rdx
0x1800487b2  lea     r9, aMocloudmessage; "MOCloudMessageSyncPartner"
0x1800487b9  lea     rdx, qword_1800D9870
0x1800487c0  mov     [rsp+0E0h+ppv], rdx
0x1800487c5  lea     r8, qword_1800D9960
0x1800487cc  mov     rax, [rcx]
0x1800487cf  mov     edx, [rbp+57h+var_70]
0x1800487d2  mov     rax, [rax+58h]
0x1800487d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800487db  mov     ebx, eax
0x1800487dd  test    eax, eax
0x1800487df  jns     short loc_1800487FE
0x1800487e1  mov     r9d, 5Fh ; '_'
0x1800487e7  mov     edx, edi
0x1800487e9  mov     ecx, eax; int
0x1800487eb  call    Log_HREvent_22
0x1800487f0  lea     rcx, [rbp+57h+var_80]
0x1800487f4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800487f9  jmp     loc_1800486B7
0x1800487fe  cmp     [rbp+57h+var_80], r12
0x180048802  jnz     short loc_180048813
0x180048804  xor     edx, edx
0x180048806  mov     ebx, 80004005h
0x18004880b  mov     ecx, ebx
0x18004880d  lea     r9d, [rdx+61h]
0x180048811  jmp     short loc_1800487EB
0x180048813  lea     rcx, [rbp+57h+var_88]
0x180048817  mov     [rbp+57h+var_88], r12
0x18004881b  call    ??ICMapiProps@@QEAAPEAPEAU_SPropValue@@XZ; CMapiProps::operator&(void)
0x180048820  mov     rcx, [r14+40h]
0x180048824  mov     rbx, rax
0x180048827  mov     rdx, [rcx]
0x18004882a  mov     rax, [rdx+200h]
0x180048831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048836  mov     r8, rbx; lppProp
0x180048839  mov     edx, 81060102h; ulPropTag
0x18004883e  mov     rcx, rax; lpMapiProp
0x180048841  call    cs:__imp_HrGetOneProp
0x180048847  mov     ebx, eax
0x180048849  test    eax, eax
0x18004884b  jns     short loc_18004886C
0x18004884d  mov     r9d, 64h ; 'd'
0x180048853  mov     edx, edi
0x180048855  mov     ecx, eax; int
0x180048857  call    Log_HREvent_22
0x18004885c  mov     rcx, [rbp+57h+var_88]; pv
0x180048860  call    cs:__imp_MAPIFreeBuffer
0x180048866  mov     [rbp+57h+var_88], r12
0x18004886a  jmp     short loc_1800487F0
0x18004886c  lea     rcx, [rbp+57h+var_88]
0x180048870  call    ??CCMapiProps@@QEAAPEAU_SPropValue@@XZ; CMapiProps::operator->(void)
0x180048875  cmp     [rax+8], esi
0x180048878  jz      short loc_180048889
0x18004887a  xor     edx, edx
0x18004887c  mov     ebx, 80004005h
0x180048881  mov     ecx, ebx
0x180048883  lea     r9d, [rdx+65h]
0x180048887  jmp     short loc_180048857
0x180048889  lea     rcx, [rbp+57h+var_88]
0x18004888d  mov     qword ptr [rbp+57h+var_A0], r12
0x180048891  mov     [rbp+57h+var_98], r12
0x180048895  call    ??CCMapiProps@@QEAAPEAU_SPropValue@@XZ; CMapiProps::operator->(void)
0x18004889a  lea     rcx, [rbp+57h+var_88]
0x18004889e  mov     rbx, [rax+10h]
0x1800488a2  call    ??CCMapiProps@@QEAAPEAU_SPropValue@@XZ; CMapiProps::operator->(void)
0x1800488a7  mov     r8, rbx; struct ENTRYID *
0x1800488aa  lea     rcx, [rbp+57h+var_A0]; this
0x1800488ae  mov     edx, [rax+8]; unsigned int
0x1800488b1  call    ?Set@CEntryId@@QEAAJKPEAUENTRYID@@@Z; CEntryId::Set(ulong,ENTRYID *)
0x1800488b6  mov     ebx, eax
0x1800488b8  test    eax, eax
0x1800488ba  jns     short loc_1800488D7
0x1800488bc  mov     r9d, 68h ; 'h'
0x1800488c2  mov     edx, edi
0x1800488c4  mov     ecx, eax; int
0x1800488c6  call    Log_HREvent_22
0x1800488cb  mov     rcx, [rbp+57h+var_98]; pv
0x1800488cf  call    cs:__imp_MAPIFreeBuffer
0x1800488d5  jmp     short loc_18004885C
0x1800488d7  mov     rcx, [rbp+57h+var_80]
0x1800488db  lea     rdx, [rbp+57h+var_68]
0x1800488df  mov     [rbp+57h+var_68], r12
0x1800488e3  mov     rax, [rcx]
0x1800488e6  mov     rax, [rax+0B0h]
0x1800488ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488f2  mov     ebx, eax
0x1800488f4  test    eax, eax
0x1800488f6  jns     short loc_180048912
0x1800488f8  mov     r9d, 6Ch ; 'l'
0x1800488fe  mov     edx, edi
0x180048900  mov     ecx, eax; int
0x180048902  call    Log_HREvent_22
0x180048907  lea     rcx, [rbp+57h+var_68]
0x18004890b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048910  jmp     short loc_1800488CB
0x180048912  mov     rcx, [rbp+57h+var_80]
0x180048916  lea     rdx, [rbp+57h+var_78]
0x18004891a  mov     rsi, [rbp+57h+var_98]
0x18004891e  mov     r8d, [rbp+57h+var_A0]
0x180048922  mov     r9, rsi
0x180048925  mov     [rbp+57h+var_78], r12
0x180048929  mov     rax, [rcx]
0x18004892c  mov     [rsp+0E0h+ppv], rdx
0x180048931  mov     edx, edi
0x180048933  mov     rax, [rax+0B8h]
0x18004893a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004893f  mov     ebx, eax
0x180048941  test    eax, eax
0x180048943  jns     short loc_18004896E
0x180048945  mov     r9d, 70h ; 'p'
0x18004894b  mov     edx, edi
0x18004894d  mov     ecx, eax; int
0x18004894f  call    Log_HREvent_22
0x180048954  lea     rcx, [rbp+57h+var_78]
0x180048958  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004895d  lea     rcx, [rbp+57h+var_68]
0x180048961  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048966  mov     rcx, rsi
0x180048969  jmp     loc_1800488CF
0x18004896e  mov     rdx, [rbp+57h+var_78]
0x180048972  test    rdx, rdx
0x180048975  jnz     short loc_1800489CE
0x180048977  mov     rcx, [rbp+57h+var_68]
0x18004897b  lea     rdx, [rbp+57h+var_78]
0x18004897f  mov     r8d, [rbp+57h+var_A0]
0x180048983  mov     r9, rsi
0x180048986  mov     [rsp+0E0h+var_B8], rdx
0x18004898b  lea     rdx, aSmsstoreinbox; "SmsStoreInbox"
0x180048992  mov     [rsp+0E0h+ppv], rdx
0x180048997  mov     edx, edi
0x180048999  mov     rax, [rcx]
0x18004899c  mov     rax, [rax+0B0h]
0x1800489a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489a8  mov     ebx, eax
0x1800489aa  test    eax, eax
0x1800489ac  jns     short loc_1800489B6
0x1800489ae  mov     r9d, 75h ; 'u'
0x1800489b4  jmp     short loc_18004894B
0x1800489b6  mov     rdx, [rbp+57h+var_78]
0x1800489ba  test    rdx, rdx
0x1800489bd  jnz     short loc_1800489CE
0x1800489bf  mov     ebx, 80004005h
0x1800489c4  mov     r9d, 77h ; 'w'
0x1800489ca  mov     ecx, ebx
0x1800489cc  jmp     short loc_18004894F
0x1800489ce  mov     eax, [rbp+57h+var_70]
0x1800489d1  lea     rcx, [r14+50h]; struct IUnknown **
0x1800489d5  mov     [r14+48h], eax
0x1800489d9  mov     rax, [rbp+57h+var_80]
0x1800489dd  cmp     [rcx], rax
0x1800489e0  jz      short loc_1800489EE
0x1800489e2  mov     rdx, rax; struct IUnknown *
0x1800489e5  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800489ea  mov     rdx, [rbp+57h+var_78]; struct IUnknown *
0x1800489ee  lea     rcx, [r14+58h]; struct IUnknown **
0x1800489f2  cmp     [rcx], rdx
0x1800489f5  jz      short loc_1800489FC
0x1800489f7  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800489fc  mov     edx, [rbp+57h+var_A0]; unsigned int
0x1800489ff  lea     rcx, [r14+68h]; this
0x180048a03  mov     r8, rsi; struct ENTRYID *
0x180048a06  call    ?Set@CEntryId@@QEAAJKPEAUENTRYID@@@Z; CEntryId::Set(ulong,ENTRYID *)
0x180048a0b  mov     ebx, eax
0x180048a0d  test    eax, eax
0x180048a0f  jns     short loc_180048A1C
0x180048a11  mov     r9d, 7Dh ; '}'
0x180048a17  jmp     loc_18004894B
0x180048a1c  lea     rcx, [rbp+57h+var_78]
0x180048a20  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048a25  lea     rcx, [rbp+57h+var_68]
0x180048a29  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048a2e  mov     rcx, rsi; pv
0x180048a31  call    cs:__imp_MAPIFreeBuffer
0x180048a37  mov     rcx, [rbp+57h+var_88]; pv
0x180048a3b  call    cs:__imp_MAPIFreeBuffer
0x180048a41  lea     rcx, [rbp+57h+var_80]
0x180048a45  mov     [rbp+57h+var_88], r12
0x180048a49  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048a4e  mov     rcx, [rbp+57h+pv]; pv
0x180048a52  call    cs:__imp_MAPIFreeBuffer
0x180048a58  mov     ebx, r12d
0x180048a5b  mov     [rbp+57h+pv], r12
0x180048a5f  lea     rcx, [rbp+57h+var_60]
0x180048a63  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048a68  mov     eax, ebx
0x180048a6a  mov     rcx, [rbp+57h+var_40]
0x180048a6e  xor     rcx, rsp; StackCookie
  ... truncated ...
```
