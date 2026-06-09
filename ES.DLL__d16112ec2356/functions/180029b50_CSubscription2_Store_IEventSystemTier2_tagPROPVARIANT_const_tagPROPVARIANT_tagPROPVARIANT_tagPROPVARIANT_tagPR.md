# CSubscription2::Store(IEventSystemTier2 *,tagPROPVARIANT * const,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagBLOB *,int,int,int)

- ea: `0x180029b50`
- end: `0x18002a4b1`
- name: `?Store@CSubscription2@@UEAAJPEAUIEventSystemTier2@@QEAUtagPROPVARIANT@@PEAU3@222PEAUtagBLOB@@HHH@Z`
- size: `2401`
- prototype: `int(CSubscription2 *__hidden this, struct IEventSystemTier2 *, struct tagPROPVARIANT *const, struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagBLOB *, int, int, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180014600`
- `0x180015850`
- `0x180017ef4`
- `0x18001c8f0`
- `0x180022778`
- `0x180024fac`
- `0x180025040`
- `0x180029b50`
- `0x18003ed70`
- `0x18003efe8`
- `0x18003f608`
- `0x1800434ea`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ec0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a47f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ec0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a47f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180029e63`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180029e63`
- `OLEAUT32!__imp_SysStringLen` at `0x180029d04`
- `OLEAUT32!__imp_SysStringLen` at `0x180029f7c`
- `OLEAUT32!__imp_SysStringLen` at `0x180029fbf`
- `OLEAUT32!__imp_SysStringLen` at `0x180029d04`
- `OLEAUT32!__imp_SysStringLen` at `0x180029f7c`
- `OLEAUT32!__imp_SysStringLen` at `0x180029fbf`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x180029ed8`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x180029ed8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a0bb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a3be`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a3cc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a0bb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a3be`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a3cc`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002a3dd`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18004589b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002a3dd`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18004589b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180029efd`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180029efd`

## pseudocode

```c
__int64 __fastcall CSubscription2::Store(
        CSubscription2 *this,
        struct IUnknown *a2,
        struct tagPROPVARIANT *const a3,
        struct tagPROPVARIANT *a4,
        struct tagPROPVARIANT *a5,
        struct tagPROPVARIANT *a6,
        struct tagPROPVARIANT *a7,
        struct tagBLOB *a8,
        unsigned int a9,
        int a10,
        int a11)
{
  bool v14; // r15
  __int64 result; // rax
  unsigned int v16; // r9d
  HRESULT v17; // ebx
  int v18; // eax
  LARGE_INTEGER hVal; // rbx
  unsigned __int16 *v20; // rdx
  char v21; // r13
  signed int IsAdministrator; // edi
  OLECHAR *bstrVal; // rbx
  UINT v24; // eax
  bool v25; // bl
  int v26; // eax
  unsigned int v27; // r8d
  int v28; // eax
  int v29; // ebx
  unsigned __int16 *v30; // rcx
  unsigned __int16 *v31; // rax
  int v32; // edx
  int v33; // r8d
  int TerminalServicesSessionId; // eax
  bool v35; // [rsp+44h] [rbp-4A4h] BYREF
  bool v36; // [rsp+45h] [rbp-4A3h] BYREF
  bool v37; // [rsp+46h] [rbp-4A2h]
  struct IUnknown *v38; // [rsp+48h] [rbp-4A0h] BYREF
  BOOL v39; // [rsp+50h] [rbp-498h] BYREF
  bool v40; // [rsp+54h] [rbp-494h]
  __int64 v41; // [rsp+58h] [rbp-490h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-488h] BYREF
  int v43[2]; // [rsp+68h] [rbp-480h] BYREF
  unsigned __int16 *p_vt; // [rsp+70h] [rbp-478h] BYREF
  int v45; // [rsp+78h] [rbp-470h]
  struct tagPROPVARIANT pvar; // [rsp+80h] [rbp-468h] BYREF
  struct tagPROPVARIANT v47; // [rsp+A0h] [rbp-448h] BYREF
  int v48; // [rsp+C0h] [rbp-428h] BYREF
  HLOCAL v49; // [rsp+C8h] [rbp-420h]
  wchar_t *String1; // [rsp+D0h] [rbp-418h] BYREF
  struct tagPROPVARIANT *v51; // [rsp+D8h] [rbp-410h]
  struct tagPROPVARIANT *v52; // [rsp+E0h] [rbp-408h]
  CSubscription2 *v53; // [rsp+E8h] [rbp-400h]
  struct tagPROPVARIANT v54; // [rsp+F0h] [rbp-3F8h] BYREF
  PROPVARIANT rgvars[48]; // [rsp+110h] [rbp-3D8h] BYREF
  __int16 v56; // [rsp+290h] [rbp-258h]
  __int16 v57; // [rsp+298h] [rbp-250h]
  unsigned __int16 v58[120]; // [rsp+2C0h] [rbp-228h] BYREF
  unsigned __int16 v59[120]; // [rsp+3B0h] [rbp-138h] BYREF

  p_vt = &a4->vt;
  v53 = this;
  *(_QWORD *)v43 = a5;
  v51 = a6;
  v52 = a7;
  v14 = 0;
  v41 = 0;
  v48 = 0;
  v49 = 0;
  v39 = 0;
  if ( !a2 )
    return 2147500035LL;
  if ( (a3[4].vt & 0xFFF7) != 0 || (a3[3].vt & 0xFFF7) != 0 || (a3[14].vt & 0xFFF7) != 0 )
    return 2147942487LL;
  v47 = a3[17];
  pvar = a3[16];
  v54 = *a3;
  result = ConcatenateECID_PARTID_APPID(&v54, &pvar, &v47, (unsigned int)a4, v58);
  if ( (int)result >= 0 )
  {
    result = CheckInterfaceIsProcessLocal(a2);
    if ( (int)result >= 0 )
    {
      result = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                 a2,
                 &GUID_dc7c5ccc_34e1_4531_941d_035e29ff8257,
                 &v41);
      if ( (int)result >= 0 )
      {
        if ( a3[6].iVal == -1 && !a8 && a3[13].vt == 8 && SysStringLen(a3[13].bstrVal) && a3[3].vt )
        {
          v38 = 0;
          memset(&v54, 0, sizeof(v54));
          v47 = a3[14];
          pvar = a3[3];
          v17 = ConcatenateECID_PARTID_APPID(&pvar, &v47, &v54, v16, v59);
          if ( v17 < 0 )
          {
LABEL_27:
            if ( v17 < 0 )
              goto LABEL_28;
            goto LABEL_29;
          }
          v18 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, unsigned __int16 *, GUID *, struct IUnknown **))a2->lpVtbl[3].QueryInterface)(
                  a2,
                  0,
                  v59,
                  &IID_IEventClassTier2,
                  &v38);
          v17 = v18;
          if ( v18 != -2147024894 )
          {
            if ( v18 >= 0 )
            {
              v17 = ((__int64 (__fastcall *)(struct IUnknown *, PROPVARIANT *))v38->lpVtbl[1].AddRef)(v38, rgvars);
              ((void (__fastcall *)(struct IUnknown *))v38->lpVtbl->Release)(v38);
              v38 = 0;
              if ( v17 < 0 )
              {
LABEL_28:
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                return (unsigned int)v17;
              }
              if ( v56 != 11 || v57 != -1 )
              {
                hMem = 0;
                hVal = a3[13].hVal;
                v20 = qword_180064628;
                if ( qword_180064628
                  || (InitOnceExecuteOnce(&InitOnce, (PINIT_ONCE_FN)InitResourceStringsCallback, 0, 0),
                      (v20 = qword_180064628) != 0) )
                {
                  FormatMessageFromString((unsigned __int16 **)&hMem, v20, hVal.QuadPart);
                }
                LogMessage(0x11u, 0x80001214, 3u, rgvars[1], rgvars[34], hMem);
                if ( hMem )
                  LocalFree(hMem);
                v17 = -2147024891;
              }
              FreePropVariantArray(0x12u, rgvars);
            }
            goto LABEL_27;
          }
        }
LABEL_29:
        v21 = 0;
        v17 = CoImpersonateClient();
        if ( v17 == -2147417833 )
        {
          v37 = 0;
        }
        else
        {
          v14 = v17 >= 0;
          v37 = v17 >= 0;
          if ( v17 < 0 )
            goto LABEL_28;
        }
        v35 = 0;
        IsAdministrator = CallerTokenProperties::IsAdministrator((CallerTokenProperties *)&v48, &v35);
        if ( IsAdministrator < 0 )
          goto LABEL_96;
        if ( !v35 )
        {
          if ( a3[6].vt != 11 || a3[6].iVal != -1 )
            goto LABEL_40;
          if ( a3[7].vt != 8 || !SysStringLen(a3[7].bstrVal) )
          {
            IsAdministrator = -2147024809;
            goto LABEL_96;
          }
          String1 = 0;
          IsAdministrator = CallerTokenProperties::GetSid((CallerTokenProperties *)&v48, &String1);
          if ( IsAdministrator < 0 )
          {
LABEL_96:
            if ( v14 )
              CoRevertToSelf();
            if ( IsAdministrator < 0 )
            {
              if ( v21 )
                LogMessage_HR(0x10u, 0xC000120B, IsAdministrator, 2u, v58, a3[7].hVal.QuadPart);
            }
            else
            {
              IsAdministrator = (*(__int64 (__fastcall **)(__int64, bool, unsigned __int16 *, LARGE_INTEGER, LARGE_INTEGER, LARGE_INTEGER))(*(_QWORD *)v41 + 32LL))(
                                  v41,
                                  !v39,
                                  v58,
                                  a3[4].hVal,
                                  a3[3].hVal,
                                  a3[14].hVal);
            }
            if ( v41 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
            if ( v49 )
              LocalFree(v49);
            return (unsigned int)IsAdministrator;
          }
          bstrVal = a3[7].bstrVal;
          v24 = SysStringLen(bstrVal);
          if ( wcsncmp_0(String1, bstrVal, v24) )
          {
LABEL_40:
            IsAdministrator = -2147024891;
            goto LABEL_96;
          }
        }
        v38 = 0;
        if ( a8 )
        {
          IsAdministrator = UnmarshalIUnknownFromBlob(a8, &v38);
          if ( IsAdministrator < 0 )
            goto LABEL_96;
        }
        v25 = 0;
        memset(&v47, 0, sizeof(v47));
        memset(&pvar, 0, sizeof(pvar));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 112LL))(*((_QWORD *)this + 3));
        v26 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 136LL))(*((_QWORD *)this + 3));
        v39 = v26 == 0;
        if ( v26 )
        {
          v25 = !(*(unsigned int (__fastcall **)(_QWORD, __int64, struct tagPROPVARIANT *))(**((_QWORD **)this + 3)
                                                                                          + 24LL))(
                   *((_QWORD *)this + 3),
                   6,
                   &pvar)
             && pvar.iVal == -1;
          v40 = v25;
          PropVariantClear((PROPVARIANT *)&pvar);
          IsAdministrator = (*(__int64 (__fastcall **)(_QWORD, __int64, struct tagPROPVARIANT *))(**((_QWORD **)this + 3)
                                                                                                + 24LL))(
                              *((_QWORD *)this + 3),
                              7,
                              &v47);
          if ( !IsAdministrator )
          {
            v36 = 0;
            IsAdministrator = CheckCallerAccessToEventObject(
                                v47.bstrVal,
                                (struct CallerTokenProperties *)&v48,
                                v27,
                                &v36);
            if ( IsAdministrator < 0 )
            {
LABEL_91:
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 120LL))(*((_QWORD *)this + 3));
              if ( IsAdministrator < 0 )
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 88LL))(*((_QWORD *)this + 3));
              if ( v38 )
                ((void (__fastcall *)(struct IUnknown *))v38->lpVtbl->Release)(v38);
              PropVariantClear((PROPVARIANT *)&pvar);
              PropVariantClear((PROPVARIANT *)&v47);
              goto LABEL_96;
            }
            if ( !v36 )
            {
              IsAdministrator = -2147024891;
              goto LABEL_91;
            }
          }
        }
        if ( (a3[6].iVal == -1 || v25) && !v38 )
        {
          v28 = (*(__int64 (__fastcall **)(_QWORD, LARGE_INTEGER, BOOL *))(**((_QWORD **)this + 3) + 144LL))(
                  *((_QWORD *)this + 3),
                  a3[7].hVal,
                  &v39);
          IsAdministrator = v28;
          if ( v28 < 0 )
          {
            if ( v28 == -2147024894 )
              IsAdministrator = -2147220985;
            else
              v21 = 1;
            goto LABEL_91;
          }
        }
        if ( !v39 )
        {
          IsAdministrator = (*(__int64 (__fastcall **)(_QWORD, bool))(**((_QWORD **)this + 3) + 128LL))(
                              *((_QWORD *)this + 3),
                              a11 == 0);
          if ( IsAdministrator < 0 )
            goto LABEL_91;
        }
        v29 = 0;
        while ( 1 )
        {
          v45 = v29;
          if ( v29 >= 18 )
            break;
          if ( a3[v29].vt )
          {
            IsAdministrator = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 3) + 32LL))(
                                *((_QWORD *)this + 3),
                                (unsigned int)v29);
            if ( IsAdministrator < 0 )
              goto LABEL_91;
            ++v29;
          }
          else
          {
            ++v29;
          }
        }
        if ( p_vt && *(_QWORD *)v43 )
          IsAdministrator = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 3) + 48LL))(
                              *((_QWORD *)this + 3),
                              L"PublisherProperties");
        if ( IsAdministrator < 0 )
          goto LABEL_91;
        if ( v51 && v52 )
          IsAdministrator = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 3) + 48LL))(
                              *((_QWORD *)this + 3),
                              L"SubscriberProperties");
        if ( IsAdministrator < 0 )
          goto LABEL_91;
        if ( a3[6].iVal != -1 || v38 )
          goto LABEL_87;
        p_vt = 0;
        IsAdministrator = CallerTokenProperties::GetSid((CallerTokenProperties *)&v48, &p_vt);
        if ( IsAdministrator < 0 )
          goto LABEL_91;
        v30 = a3[7].bstrVal;
        v31 = p_vt;
        do
        {
          v32 = *(unsigned __int16 *)((char *)v31 + a3[7].hVal.QuadPart - (_QWORD)p_vt);
          v33 = *v31 - v32;
          if ( v33 )
            break;
          ++v31;
        }
        while ( v32 );
        if ( !v33 )
          goto LABEL_87;
        v43[0] = 0;
        LODWORD(hMem) = -1;
        TerminalServicesSessionId = GetTerminalServicesSessionId(v30, 1, v43, (unsigned int *)&hMem);
        IsAdministrator = TerminalServicesSessionId;
        if ( TerminalServicesSessionId == -2147220976 )
        {
          IsAdministrator = 0;
        }
        else if ( TerminalServicesSessionId < 0 )
        {
          goto LABEL_91;
        }
        if ( v43[0] )
LABEL_87:
          IsAdministrator = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 3) + 72LL))(
                              *((_QWORD *)this + 3),
                              1);
        if ( IsAdministrator >= 0 && v38 )
          IsAdministrator = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, struct IUnknown *, _QWORD))(*(_QWORD *)v41 + 40LL))(
                              v41,
                              v58,
                              v38,
                              a9);
        goto LABEL_91;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180029b50  push    rbx
0x180029b52  push    rsi
0x180029b53  push    rdi
0x180029b54  push    r12
0x180029b56  push    r13
0x180029b58  push    r14
0x180029b5a  push    r15
0x180029b5c  sub     rsp, 4B0h
0x180029b63  mov     rax, cs:__security_cookie
0x180029b6a  xor     rax, rsp
0x180029b6d  mov     [rsp+4E8h+var_48], rax
0x180029b75  mov     [rsp+4E8h+var_478], r9
0x180029b7a  mov     rsi, r8
0x180029b7d  mov     rdi, rdx
0x180029b80  mov     r14, rcx
0x180029b83  mov     [rsp+4E8h+var_400], rcx
0x180029b8b  mov     rax, [rsp+4E8h+arg_20]
0x180029b93  mov     qword ptr [rsp+4E8h+var_480], rax
0x180029b98  mov     rax, [rsp+4E8h+arg_28]
0x180029ba0  mov     [rsp+4E8h+var_410], rax
0x180029ba8  mov     rax, [rsp+4E8h+arg_30]
0x180029bb0  mov     [rsp+4E8h+var_408], rax
0x180029bb8  mov     r12, [rsp+4E8h+arg_38]
0x180029bc0  xor     r15d, r15d
0x180029bc3  mov     [rsp+4E8h+var_490], r15
0x180029bc8  mov     [rsp+4E8h+var_428], r15d
0x180029bd0  mov     [rsp+4E8h+var_420], r15
0x180029bd8  mov     [rsp+4E8h+var_498], r15d
0x180029bdd  test    rdx, rdx
0x180029be0  jnz     short loc_180029BEC
0x180029be2  mov     eax, 80004003h
0x180029be7  jmp     loc_18002A48E
0x180029bec  mov     eax, 0FFF7h
0x180029bf1  test    [r8+60h], ax
0x180029bf6  jnz     loc_18002A489
0x180029bfc  test    [r8+48h], ax
0x180029c01  jnz     loc_18002A489
0x180029c07  test    [r8+150h], ax
0x180029c0f  jnz     loc_18002A489
0x180029c15  movups  xmm0, xmmword ptr [r8+198h]
0x180029c1d  movaps  xmmword ptr [rsp+4E8h+var_448], xmm0
0x180029c25  movsd   xmm1, qword ptr [r8+1A8h]
0x180029c2e  movsd   [rsp+4E8h+var_438], xmm1
0x180029c37  movups  xmm0, xmmword ptr [r8+180h]
0x180029c3f  movaps  xmmword ptr [rsp+4E8h+pvar], xmm0
0x180029c47  movsd   xmm1, qword ptr [r8+190h]
0x180029c50  movsd   [rsp+4E8h+var_458], xmm1
0x180029c59  movups  xmm0, xmmword ptr [r8]
0x180029c5d  movaps  xmmword ptr [rsp+4E8h+var_3F8], xmm0
0x180029c65  movsd   xmm1, qword ptr [r8+10h]
0x180029c6b  movsd   qword ptr [rsp+4E8h+var_3F8+10h], xmm1
0x180029c74  lea     rax, [rsp+4E8h+var_228]
0x180029c7c  mov     [rsp+4E8h+var_4C8], rax; unsigned __int16 *
0x180029c81  lea     r8, [rsp+4E8h+var_448]; struct tagPROPVARIANT *
0x180029c89  lea     rdx, [rsp+4E8h+pvar]; struct tagPROPVARIANT *
0x180029c91  lea     rcx, [rsp+4E8h+var_3F8]; struct tagPROPVARIANT *
0x180029c99  call    ?ConcatenateECID_PARTID_APPID@@YAJUtagPROPVARIANT@@00KPEAG@Z; ConcatenateECID_PARTID_APPID(tagPROPVARIANT,tagPROPVARIANT,tagPROPVARIANT,ulong,ushort *)
0x180029c9e  test    eax, eax
0x180029ca0  js      loc_18002A48E
0x180029ca6  mov     rcx, rdi; struct IUnknown *
0x180029ca9  call    ?CheckInterfaceIsProcessLocal@@YAJPEAUIUnknown@@@Z; CheckInterfaceIsProcessLocal(IUnknown *)
0x180029cae  test    eax, eax
0x180029cb0  js      loc_18002A48E
0x180029cb6  mov     rax, [rdi]
0x180029cb9  lea     r8, [rsp+4E8h+var_490]
0x180029cbe  lea     rdx, _GUID_dc7c5ccc_34e1_4531_941d_035e29ff8257
0x180029cc5  mov     rcx, rdi
0x180029cc8  mov     rax, [rax]
0x180029ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cd0  test    eax, eax
0x180029cd2  js      loc_18002A48E
0x180029cd8  cmp     word ptr [rsi+98h], 0FFFFh
0x180029ce0  jnz     loc_180029EFA
0x180029ce6  test    r12, r12
0x180029ce9  jnz     loc_180029EFA
0x180029cef  cmp     word ptr [rsi+138h], 8
0x180029cf7  jnz     loc_180029EFA
0x180029cfd  mov     rcx, [rsi+140h]; pbstr
0x180029d04  call    cs:__imp_SysStringLen
0x180029d0a  test    eax, eax
0x180029d0c  jz      loc_180029EFA
0x180029d12  cmp     [rsi+48h], r15w
0x180029d17  jz      loc_180029EFA
0x180029d1d  mov     [rsp+4E8h+var_4A0], r15
0x180029d22  xorps   xmm0, xmm0
0x180029d25  xor     eax, eax
0x180029d27  movaps  xmmword ptr [rsp+4E8h+var_3F8], xmm0
0x180029d2f  mov     qword ptr [rsp+4E8h+var_3F8+10h], rax
0x180029d37  movups  xmm0, xmmword ptr [rsi+150h]
0x180029d3e  movaps  xmmword ptr [rsp+4E8h+var_448], xmm0
0x180029d46  movsd   xmm1, qword ptr [rsi+160h]
0x180029d4e  movsd   [rsp+4E8h+var_438], xmm1
0x180029d57  movups  xmm0, xmmword ptr [rsi+48h]
0x180029d5b  movaps  xmmword ptr [rsp+4E8h+pvar], xmm0
0x180029d63  movsd   xmm1, qword ptr [rsi+58h]
0x180029d68  movsd   [rsp+4E8h+var_458], xmm1
0x180029d71  lea     rax, [rsp+4E8h+var_138]
0x180029d79  mov     [rsp+4E8h+var_4C8], rax; unsigned __int16 *
0x180029d7e  lea     r8, [rsp+4E8h+var_3F8]; struct tagPROPVARIANT *
0x180029d86  lea     rdx, [rsp+4E8h+var_448]; struct tagPROPVARIANT *
0x180029d8e  lea     rcx, [rsp+4E8h+pvar]; struct tagPROPVARIANT *
0x180029d96  call    ?ConcatenateECID_PARTID_APPID@@YAJUtagPROPVARIANT@@00KPEAG@Z; ConcatenateECID_PARTID_APPID(tagPROPVARIANT,tagPROPVARIANT,tagPROPVARIANT,ulong,ushort *)
0x180029d9b  mov     ebx, eax
0x180029d9d  test    eax, eax
0x180029d9f  js      loc_180029EDE
0x180029da5  mov     rax, [rdi]
0x180029da8  lea     rcx, [rsp+4E8h+var_4A0]
0x180029dad  mov     [rsp+4E8h+var_4C8], rcx
0x180029db2  lea     r9, IID_IEventClassTier2
0x180029db9  lea     r8, [rsp+4E8h+var_138]
0x180029dc1  xor     edx, edx
0x180029dc3  mov     rcx, rdi
0x180029dc6  mov     rax, [rax+48h]
0x180029dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dcf  mov     ebx, eax
0x180029dd1  cmp     eax, 80070002h
0x180029dd6  jz      loc_180029EFA
0x180029ddc  test    eax, eax
0x180029dde  js      loc_180029EDE
0x180029de4  mov     rcx, [rsp+4E8h+var_4A0]
0x180029de9  mov     rax, [rcx]
0x180029dec  lea     rdx, [rsp+4E8h+rgvars]
0x180029df4  mov     rax, [rax+20h]
0x180029df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dfd  mov     ebx, eax
0x180029dff  mov     rcx, [rsp+4E8h+var_4A0]
0x180029e04  mov     rax, [rcx]
0x180029e07  mov     rax, [rax+10h]
0x180029e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e10  mov     [rsp+4E8h+var_4A0], r15
0x180029e15  test    ebx, ebx
0x180029e17  js      loc_180029EE2
0x180029e1d  cmp     [rsp+4E8h+var_258], 0Bh
0x180029e26  jnz     short loc_180029E37
0x180029e28  cmp     [rsp+4E8h+var_250], 0FFFFh
0x180029e31  jz      loc_180029ECB
0x180029e37  mov     [rsp+4E8h+hMem], r15
0x180029e3c  mov     rbx, [rsi+140h]
0x180029e43  mov     rdx, cs:qword_180064628
0x180029e4a  test    rdx, rdx
0x180029e4d  jnz     short loc_180029E75
0x180029e4f  xor     r9d, r9d; Context
0x180029e52  xor     r8d, r8d; Parameter
0x180029e55  lea     rdx, ?InitResourceStringsCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180029e5c  lea     rcx, InitOnce; InitOnce
0x180029e63  call    cs:__imp_InitOnceExecuteOnce
0x180029e69  mov     rdx, cs:qword_180064628; unsigned __int16 *
0x180029e70  test    rdx, rdx
0x180029e73  jz      short loc_180029E82
0x180029e75  mov     r8, rbx
0x180029e78  lea     rcx, [rsp+4E8h+hMem]; unsigned __int16 **
0x180029e7d  call    ?FormatMessageFromString@@YAXPEAPEAGPEAGZZ; FormatMessageFromString(ushort * *,ushort *,...)
0x180029e82  mov     ecx, 11h; unsigned __int16
0x180029e87  mov     rax, [rsp+4E8h+hMem]
0x180029e8c  mov     [rsp+4E8h+var_4C0], rax
0x180029e91  mov     rax, [rsp+4E8h+var_2C8]
0x180029e99  mov     [rsp+4E8h+var_4C8], rax
0x180029e9e  mov     r9, [rsp+4E8h+var_3D0]
0x180029ea6  mov     edx, 80001214h; unsigned int
0x180029eab  mov     r8d, 3; unsigned int
0x180029eb1  call    ?LogMessage@@YAXGKKZZ; LogMessage(ushort,ulong,ulong,...)
0x180029eb6  mov     rcx, [rsp+4E8h+hMem]; hMem
0x180029ebb  test    rcx, rcx
0x180029ebe  jz      short loc_180029EC6
0x180029ec0  call    cs:__imp_LocalFree
0x180029ec6  mov     ebx, 80070005h
0x180029ecb  lea     rdx, [rsp+4E8h+rgvars]; rgvars
0x180029ed3  mov     ecx, 12h; cVariants
0x180029ed8  call    cs:__imp_FreePropVariantArray
0x180029ede  test    ebx, ebx
0x180029ee0  jns     short loc_180029EFA
0x180029ee2  mov     rcx, [rsp+4E8h+var_490]
0x180029ee7  mov     rax, [rcx]
0x180029eea  mov     rax, [rax+10h]
0x180029eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ef3  mov     eax, ebx
0x180029ef5  jmp     loc_18002A48E
0x180029efa  xor     r13b, r13b
0x180029efd  call    cs:__imp_CoImpersonateClient
0x180029f03  mov     ebx, eax
0x180029f05  cmp     eax, 80010117h
0x180029f0a  jnz     short loc_180029F13
0x180029f0c  mov     [rsp+4E8h+var_4A2], r15b
0x180029f11  jmp     short loc_180029F27
0x180029f13  mov     r15d, ebx
0x180029f16  shr     r15d, 1Fh
0x180029f1a  xor     r15b, 1
0x180029f1e  mov     [rsp+4E8h+var_4A2], r15b
0x180029f23  test    ebx, ebx
0x180029f25  js      short loc_180029EE2
0x180029f27  mov     [rsp+4E8h+var_4A4], 0
0x180029f2c  lea     rdx, [rsp+4E8h+var_4A4]; bool *
0x180029f31  lea     rcx, [rsp+4E8h+var_428]; this
0x180029f39  call    ?IsAdministrator@CallerTokenProperties@@QEAAJAEA_N@Z; CallerTokenProperties::IsAdministrator(bool &)
0x180029f3e  mov     edi, eax
0x180029f40  mov     [rsp+4E8h+var_4A8], eax
0x180029f44  test    eax, eax
0x180029f46  js      loc_18002A3D8
0x180029f4c  cmp     [rsp+4E8h+var_4A4], 0
0x180029f51  jnz     loc_180029FF0
0x180029f57  cmp     word ptr [rsi+90h], 0Bh
0x180029f5f  jnz     short loc_180029FDC
0x180029f61  cmp     word ptr [rsi+98h], 0FFFFh
0x180029f69  jnz     short loc_180029FDC
0x180029f6b  cmp     word ptr [rsi+0A8h], 8
0x180029f73  jnz     short loc_180029FE6
0x180029f75  mov     rcx, [rsi+0B0h]; pbstr
0x180029f7c  call    cs:__imp_SysStringLen
0x180029f82  test    eax, eax
0x180029f84  jz      short loc_180029FE6
0x180029f86  mov     [rsp+4E8h+String1], 0
0x180029f92  lea     rdx, [rsp+4E8h+String1]; unsigned __int16 **
0x180029f9a  lea     rcx, [rsp+4E8h+var_428]; this
0x180029fa2  call    ?GetSid@CallerTokenProperties@@QEAAJAEAPEAG@Z; CallerTokenProperties::GetSid(ushort * &)
0x180029fa7  mov     edi, eax
0x180029fa9  mov     [rsp+4E8h+var_4A8], eax
0x180029fad  test    eax, eax
0x180029faf  js      loc_18002A3D8
0x180029fb5  mov     rbx, [rsi+0B0h]
0x180029fbc  mov     rcx, rbx; pbstr
0x180029fbf  call    cs:__imp_SysStringLen
0x180029fc5  mov     r8d, eax; MaxCount
0x180029fc8  mov     rdx, rbx; String2
0x180029fcb  mov     rcx, [rsp+4E8h+String1]; String1
0x180029fd3  call    wcsncmp_0
0x180029fd8  test    eax, eax
0x180029fda  jz      short loc_180029FF0
0x180029fdc  mov     edi, 80070005h
0x180029fe1  jmp     loc_18002A3D4
0x180029fe6  mov     edi, 80070057h
0x180029feb  jmp     loc_18002A3D4
0x180029ff0  mov     [rsp+4E8h+var_4A0], 0
0x180029ff9  test    r12, r12
0x180029ffc  jz      short loc_18002A019
0x180029ffe  lea     rdx, [rsp+4E8h+var_4A0]; struct IUnknown **
0x18002a003  mov     rcx, r12; struct tagBLOB *
0x18002a006  call    ?UnmarshalIUnknownFromBlob@@YAJAEBUtagBLOB@@AEAPEAUIUnknown@@@Z; UnmarshalIUnknownFromBlob(tagBLOB const &,IUnknown * &)
0x18002a00b  mov     edi, eax
0x18002a00d  mov     [rsp+4E8h+var_4A8], eax
0x18002a011  test    eax, eax
0x18002a013  js      loc_18002A3D8
0x18002a019  xor     bl, bl
0x18002a01b  xorps   xmm0, xmm0
0x18002a01e  xor     eax, eax
0x18002a020  movups  xmmword ptr [rsp+4E8h+var_448], xmm0
0x18002a028  mov     [rsp+4E8h+var_438], rax
0x18002a030  xorps   xmm1, xmm1
0x18002a033  movups  xmmword ptr [rsp+4E8h+pvar], xmm1
0x18002a03b  mov     [rsp+4E8h+var_458], rax
0x18002a043  mov     rcx, [r14+18h]
0x18002a047  mov     rax, [rcx]
0x18002a04a  mov     rax, [rax+70h]
0x18002a04e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a053  mov     rcx, [r14+18h]
0x18002a057  mov     rax, [rcx]
0x18002a05a  mov     rax, [rax+88h]
0x18002a061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a066  xor     ecx, ecx
0x18002a068  test    eax, eax
0x18002a06a  setz    cl
0x18002a06d  mov     [rsp+4E8h+var_498], ecx
0x18002a071  test    eax, eax
0x18002a073  jz      loc_18002A129
0x18002a079  mov     rcx, [r14+18h]
0x18002a07d  mov     rax, [rcx]
0x18002a080  lea     r8, [rsp+4E8h+pvar]
0x18002a088  mov     edx, 6
0x18002a08d  mov     rax, [rax+18h]
0x18002a091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a096  mov     [rsp+4E8h+var_4A8], eax
0x18002a09a  test    eax, eax
0x18002a09c  jnz     short loc_18002A0AD
0x18002a09e  cmp     word ptr [rsp+4E8h+pvar+8], 0FFFFh
0x18002a0a7  jnz     short loc_18002A0AD
0x18002a0a9  mov     bl, 1
0x18002a0ab  jmp     short loc_18002A0AF
0x18002a0ad  xor     bl, bl
0x18002a0af  mov     [rsp+4E8h+var_494], bl
0x18002a0b3  lea     rcx, [rsp+4E8h+pvar]; pvar
0x18002a0bb  call    cs:__imp_PropVariantClear
0x18002a0c1  mov     rcx, [r14+18h]
0x18002a0c5  mov     rax, [rcx]
0x18002a0c8  lea     r8, [rsp+4E8h+var_448]
0x18002a0d0  mov     edx, 7
0x18002a0d5  mov     rax, [rax+18h]
0x18002a0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0de  mov     edi, eax
0x18002a0e0  mov     [rsp+4E8h+var_4A8], eax
0x18002a0e4  test    eax, eax
0x18002a0e6  jnz     short loc_18002A129
0x18002a0e8  mov     [rsp+4E8h+var_4A3], al
0x18002a0ec  lea     r9, [rsp+4E8h+var_4A3]; bool *
0x18002a0f1  lea     rdx, [rsp+4E8h+var_428]; struct CallerTokenProperties *
0x18002a0f9  mov     rcx, [rsp+4E8h+var_448+8]; unsigned __int16 *
0x18002a101  call    ?CheckCallerAccessToEventObject@@YAJPEBGAEAVCallerTokenProperties@@KAEA_N@Z; CheckCallerAccessToEventObject(ushort const *,CallerTokenProperties &,ulong,bool &)
0x18002a106  mov     edi, eax
0x18002a108  mov     [rsp+4E8h+var_4A8], eax
0x18002a10c  test    eax, eax
0x18002a10e  js      loc_18002A37C
0x18002a114  cmp     [rsp+4E8h+var_4A3], 0
  ... truncated ...
```
