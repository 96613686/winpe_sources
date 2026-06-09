# MOCloudCorrelation::SaveMOCloudMessageBody(MOCloudMessageBody const *,ushort const *)

- ea: `0x18002ab50`
- end: `0x18002b232`
- name: `?SaveMOCloudMessageBody@MOCloudCorrelation@@UEAAJPEBUMOCloudMessageBody@@PEBG@Z`
- size: `1762`
- prototype: `int(MOCloudCorrelation *__hidden this, const struct MOCloudMessageBody *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005c50`
- `0x180026704`
- `0x1800281e4`
- `0x180028b58`
- `0x180029c38`
- `0x18002ab50`
- `0x180049118`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002ad0e`
- `msvcrt!wcsrchr` at `0x18002ad0e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002acb7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002acb7`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002ae1d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002ae1d`
- `UserDataTypeHelperUtil!CreateWrapFileStreamFromDssToken` at `0x18002b017`
- `UserDataTypeHelperUtil!CreateWrapFileStreamFromDssToken` at `0x18002b017`
- `UserDataTypeHelperUtil!CopyStream` at `0x18002b053`
- `UserDataTypeHelperUtil!CopyStream` at `0x18002b053`

## pseudocode

```c
__int64 __fastcall MOCloudCorrelation::SaveMOCloudMessageBody(
        MOCloudChangeTracker **this,
        const struct MOCloudMessageBody *a2,
        const unsigned __int16 *a3)
{
  unsigned int v3; // r15d
  int ExternalIdEnumerator; // eax
  unsigned int v9; // ebx
  struct ISmMessageEnumerator *v10; // rbx
  int v11; // eax
  int v12; // ecx
  HRESULT v13; // eax
  __int64 v14; // r8
  unsigned int v15; // r14d
  __int64 v16; // rbx
  wchar_t *v17; // rax
  MOCloudChangeTracker *v18; // rcx
  int v19; // eax
  bool v20; // cf
  int v21; // eax
  int v22; // ecx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rax
  unsigned int v26; // r14d
  int v27; // eax
  __int64 v28; // rcx
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int updated; // eax
  __int64 *v33; // [rsp+40h] [rbp-49h] BYREF
  char v34; // [rsp+48h] [rbp-41h]
  struct ISmMessageEnumerator *v35; // [rsp+50h] [rbp-39h] BYREF
  __int64 v36; // [rsp+58h] [rbp-31h] BYREF
  __int64 v37; // [rsp+60h] [rbp-29h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-21h] BYREF
  __int64 v39; // [rsp+70h] [rbp-19h] BYREF
  __int64 v40; // [rsp+78h] [rbp-11h] BYREF
  __int64 v41; // [rsp+80h] [rbp-9h] BYREF
  __int64 v42; // [rsp+88h] [rbp-1h] BYREF
  __int64 v43; // [rsp+90h] [rbp+7h] BYREF
  struct ISmEntryId *v44; // [rsp+98h] [rbp+Fh] BYREF
  struct _FILETIME FileTime; // [rsp+A0h] [rbp+17h] BYREF

  v3 = 0;
  if ( !*((_DWORD *)a2 + 1) )
    return 2147942450LL;
  v35 = 0;
  ExternalIdEnumerator = MOCloudCorrelation::GetExternalIdEnumerator((MOCloudCorrelation *)this, a3, 0x81070102, &v35);
  v9 = ExternalIdEnumerator;
  if ( ExternalIdEnumerator >= 0 )
  {
    v10 = v35;
    v37 = 0;
    if ( !(*(unsigned int (__fastcall **)(struct ISmMessageEnumerator *))(*(_QWORD *)v35 + 24LL))(v35) )
    {
      v11 = (*(__int64 (__fastcall **)(struct ISmMessageEnumerator *, __int64 *))(*(_QWORD *)v10 + 32LL))(v10, &v37);
      v9 = v11;
      if ( v11 < 0 )
      {
        v12 = v11;
LABEL_8:
        Log_HREvent_10(v12);
LABEL_9:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
        goto LABEL_63;
      }
    }
    if ( !v37 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
      v9 = -2147467259;
      goto LABEL_63;
    }
    if ( *(_DWORD *)a2 == 1 )
    {
      if ( *((_QWORD *)a2 + 6) - *((_QWORD *)a2 + 5) != 32 || *((_QWORD *)a2 + 19) != *((_QWORD *)a2 + 18) )
        goto LABEL_15;
    }
    else if ( *((_QWORD *)a2 + 14) == *((_QWORD *)a2 + 15) )
    {
LABEL_15:
      v9 = -2147024809;
      v12 = -2147024809;
      goto LABEL_8;
    }
    ppv = 0;
    v13 = CoCreateInstance(
            &GUID_630bb917_aa3b_4cf5_9d24_aad1f7d4297a,
            0,
            0x17u,
            &GUID_7fe02dbd_7d62_419f_9e37_87c89b8799e6,
            &ppv);
    v9 = v13;
    if ( v13 < 0 )
      goto LABEL_18;
    v14 = *((_QWORD *)a2 + 5);
    if ( (*((_QWORD *)a2 + 6) - v14) >> 5 )
    {
      v15 = 0;
      while ( 1 )
      {
        v16 = 32LL * v15;
        v17 = wcsrchr(*(const wchar_t **)(v14 + v16), 0x40u);
        v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)ppv + 24LL))(
                ppv,
                *(_QWORD *)(v16 + *((_QWORD *)a2 + 5)),
                (unsigned int)(v17 != 0) + 1,
                0,
                0);
        v9 = v13;
        if ( v13 < 0 )
          break;
        v14 = *((_QWORD *)a2 + 5);
        if ( ++v15 >= (unsigned __int64)((*((_QWORD *)a2 + 6) - v14) >> 5) )
          goto LABEL_24;
      }
LABEL_18:
      Log_HREvent_10(v13);
LABEL_19:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
      goto LABEL_9;
    }
LABEL_24:
    v18 = this[8];
    v39 = 0;
    v19 = (*(__int64 (__fastcall **)(MOCloudChangeTracker *, LPVOID, __int64 *))(*(_QWORD *)v18 + 48LL))(v18, ppv, &v39);
    v9 = v19;
    if ( v19 < 0 )
    {
      Log_HREvent_10(v19);
LABEL_26:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
      goto LABEL_19;
    }
    v20 = *(_DWORD *)a2 != 0;
    v36 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, LPVOID, __int64 *))(*(_QWORD *)v39 + 120LL))(
            v39,
            1,
            2 - (unsigned int)v20,
            0,
            ppv,
            &v36);
    v9 = v21;
    if ( v21 >= 0 )
    {
      FileTime = 0;
      SystemTimeToFileTime((const SYSTEMTIME *)a2 + 6, &FileTime);
      v21 = (*(__int64 (__fastcall **)(__int64, struct _FILETIME))(*(_QWORD *)v36 + 144LL))(v36, FileTime);
      v9 = v21;
      if ( v21 >= 0 )
      {
        v21 = (*(__int64 (__fastcall **)(__int64, struct _FILETIME))(*(_QWORD *)v36 + 160LL))(v36, FileTime);
        v9 = v21;
        if ( v21 >= 0 )
        {
          if ( !*(_DWORD *)a2 )
          {
            v42 = 0;
            ATL::CComQIPtr<ISmMessageMMS,&__s_GUID const _GUID_32a5998a_e6dc_4e8b_9a7d_74673f2c3388>::CComQIPtr<ISmMessageMMS,&__s_GUID const _GUID_32a5998a_e6dc_4e8b_9a7d_74673f2c3388>(
              &v42,
              v36);
            if ( !v42 )
            {
              v9 = -2147467262;
              v22 = -2147467262;
LABEL_36:
              Log_HREvent_10(v22);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
              goto LABEL_30;
            }
            v23 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v42 + 992LL))(v42, *((_QWORD *)a2 + 14));
            v9 = v23;
            if ( v23 < 0 )
            {
              v22 = v23;
              goto LABEL_36;
            }
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
          }
          v21 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v36 + 32LL))(v36, 0);
          v9 = v21;
          if ( v21 >= 0 )
          {
            v21 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v36 + 120LL))(v36, *((_QWORD *)a2 + 8));
            v9 = v21;
            if ( v21 >= 0 )
            {
              v21 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v36 + 328LL))(v36, a3);
              v9 = v21;
              if ( v21 >= 0 )
              {
                v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 232LL))(v36);
                v9 = v21;
                if ( v21 >= 0 )
                {
                  v24 = *((_QWORD *)a2 + 18);
                  v33 = &v36;
                  v25 = *((_QWORD *)a2 + 19) - v24;
                  v34 = 1;
                  if ( 0xCCCCCCCCCCCCCCCDuLL * (v25 >> 3) )
                  {
                    v26 = 0;
                    while ( 1 )
                    {
                      v40 = 0;
                      v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v36 + 456LL))(
                              v36,
                              *(_QWORD *)(v24 + 40LL * v26 + 8),
                              *(_QWORD *)(v24 + 40LL * v26 + 24),
                              *(_QWORD *)(v24 + 40LL * v26 + 32),
                              *(_QWORD *)(v24 + 40LL * v26 + 16),
                              &v40);
                      v3 = v27;
                      if ( v27 < 0 )
                        break;
                      v28 = *((_QWORD *)a2 + 18);
                      v3 = 0;
                      v41 = 0;
                      v29 = CreateWrapFileStreamFromDssToken(*(_QWORD *)(v28 + 40LL * v26), 0, &v41);
                      v9 = v29;
                      if ( v29 < 0 )
                      {
                        Log_HREvent_10(v29);
                        goto LABEL_55;
                      }
                      v43 = 0;
                      v30 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v40 + 24LL))(
                              v40,
                              1,
                              &v43);
                      v9 = v30;
                      if ( v30 < 0 || (v30 = CopyStream(v41, v43), v9 = v30, v30 < 0) )
                      {
                        Log_HREvent_10(v30);
                        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
LABEL_55:
                        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
                        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
                        goto LABEL_56;
                      }
                      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
                      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
                      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
                      v24 = *((_QWORD *)a2 + 18);
                      if ( ++v26 >= 0xCCCCCCCCCCCCCCCDuLL * ((*((_QWORD *)a2 + 19) - v24) >> 3) )
                        goto LABEL_51;
                    }
                    Log_HREvent_10(v27);
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
                  }
                  else
                  {
LABEL_51:
                    v44 = 0;
                    v34 = 0;
                    v31 = (*(__int64 (__fastcall **)(__int64, struct ISmEntryId **))(*(_QWORD *)v36 + 184LL))(v36, &v44);
                    v9 = v31;
                    if ( v31 < 0 )
                      goto LABEL_52;
                    updated = MOCloudChangeTracker::UpdateMetadataExternalId(this[9], v44, a3);
                    if ( updated < 0 )
                      Log_HREvent_10(updated);
                    v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 200LL))(v37);
                    v9 = v31;
                    if ( v31 < 0 )
                    {
LABEL_52:
                      Log_HREvent_10(v31);
                      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v44);
LABEL_56:
                      tlx::_UndoSolo__lambda_f4526d047837275af7c9cd1f5f435e91___::__UndoSolo__lambda_f4526d047837275af7c9cd1f5f435e91___(&v33);
                      goto LABEL_30;
                    }
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v44);
                  }
                  tlx::_UndoSolo__lambda_f4526d047837275af7c9cd1f5f435e91___::__UndoSolo__lambda_f4526d047837275af7c9cd1f5f435e91___(&v33);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
                  v9 = v3;
                  goto LABEL_63;
                }
              }
            }
          }
        }
      }
    }
    Log_HREvent_10(v21);
LABEL_30:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
    goto LABEL_26;
  }
  Log_HREvent_10(ExternalIdEnumerator);
LABEL_63:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
  return v9;
}

```

## disassembly

```asm
0x18002ab50  mov     [rsp-8+arg_18], rbx
0x18002ab55  push    rbp
0x18002ab56  push    rsi
0x18002ab57  push    rdi
0x18002ab58  push    r12
0x18002ab5a  push    r13
0x18002ab5c  push    r14
0x18002ab5e  push    r15
0x18002ab60  lea     rbp, [rsp-27h]
0x18002ab65  sub     rsp, 0B0h
0x18002ab6c  mov     rax, cs:__security_cookie
0x18002ab73  xor     rax, rsp
0x18002ab76  mov     [rbp+57h+var_38], rax
0x18002ab7a  xor     r15d, r15d
0x18002ab7d  mov     r12, r8
0x18002ab80  mov     rsi, rdx
0x18002ab83  mov     r13, rcx
0x18002ab86  cmp     [rdx+4], r15d
0x18002ab8a  jnz     short loc_18002AB96
0x18002ab8c  mov     eax, 80070032h
0x18002ab91  jmp     loc_18002B20B
0x18002ab96  lea     r9, [rbp+57h+var_90]; struct ISmMessageEnumerator **
0x18002ab9a  mov     [rbp+57h+var_90], r15
0x18002ab9e  mov     r8d, 81070102h; unsigned int
0x18002aba4  mov     rdx, r12; unsigned __int16 *
0x18002aba7  call    ?GetExternalIdEnumerator@MOCloudCorrelation@@IEAAJPEBGKPEAPEAUISmMessageEnumerator@@@Z; MOCloudCorrelation::GetExternalIdEnumerator(ushort const *,ulong,ISmMessageEnumerator * *)
0x18002abac  mov     ebx, eax
0x18002abae  test    eax, eax
0x18002abb0  jns     short loc_18002ABD0
0x18002abb2  mov     r9d, 222h
0x18002abb8  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\messagingom"...
0x18002abbf  mov     edx, 1
0x18002abc4  mov     ecx, eax; int
0x18002abc6  call    Log_HREvent_10
0x18002abcb  jmp     loc_18002B200
0x18002abd0  mov     rbx, [rbp+57h+var_90]
0x18002abd4  mov     [rbp+57h+var_80], r15
0x18002abd8  mov     rcx, rbx
0x18002abdb  mov     rax, [rbx]
0x18002abde  mov     rax, [rax+18h]
0x18002abe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abe7  test    eax, eax
0x18002abe9  jnz     short loc_18002AC2B
0x18002abeb  mov     rax, [rbx]
0x18002abee  lea     rdx, [rbp+57h+var_80]
0x18002abf2  mov     rcx, rbx
0x18002abf5  mov     rax, [rax+20h]
0x18002abf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abfe  mov     ebx, eax
0x18002ac00  test    eax, eax
0x18002ac02  jns     short loc_18002AC2B
0x18002ac04  mov     r9d, 228h
0x18002ac0a  mov     edx, 1
0x18002ac0f  mov     ecx, eax; int
0x18002ac11  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\messagingom"...
0x18002ac18  call    Log_HREvent_10
0x18002ac1d  lea     rcx, [rbp+57h+var_80]
0x18002ac21  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ac26  jmp     loc_18002B200
0x18002ac2b  cmp     [rbp+57h+var_80], r15
0x18002ac2f  jnz     short loc_18002AC44
0x18002ac31  lea     rcx, [rbp+57h+var_80]
0x18002ac35  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ac3a  mov     ebx, 80004005h
0x18002ac3f  jmp     loc_18002B200
0x18002ac44  mov     edi, 1
0x18002ac49  cmp     [rsi], edi
0x18002ac4b  jnz     short loc_18002AC84
0x18002ac4d  mov     rax, [rsi+30h]
0x18002ac51  sub     rax, [rsi+28h]
0x18002ac55  cmp     rax, 20h ; ' '
0x18002ac59  jnz     short loc_18002AC73
0x18002ac5b  mov     rax, [rsi+98h]
0x18002ac62  cmp     rax, [rsi+90h]
0x18002ac69  jz      short loc_18002AC96
0x18002ac6b  mov     r9d, 236h
0x18002ac71  jmp     short loc_18002AC79
0x18002ac73  mov     r9d, 235h
0x18002ac79  mov     ebx, 80070057h
0x18002ac7e  xor     edx, edx
0x18002ac80  mov     ecx, ebx
0x18002ac82  jmp     short loc_18002AC11
0x18002ac84  mov     rax, [rsi+78h]
0x18002ac88  cmp     [rsi+70h], rax
0x18002ac8c  jnz     short loc_18002AC96
0x18002ac8e  mov     r9d, 23Bh
0x18002ac94  jmp     short loc_18002AC79
0x18002ac96  xor     edx, edx; pUnkOuter
0x18002ac98  mov     [rbp+57h+var_78], r15
0x18002ac9c  lea     rax, [rbp+57h+var_78]
0x18002aca0  lea     r9, _GUID_7fe02dbd_7d62_419f_9e37_87c89b8799e6; riid
0x18002aca7  mov     [rsp+0E0h+ppv], rax; ppv
0x18002acac  lea     rcx, _GUID_630bb917_aa3b_4cf5_9d24_aad1f7d4297a; rclsid
0x18002acb3  lea     r8d, [rdx+17h]; dwClsContext
0x18002acb7  call    cs:__imp_CoCreateInstance
0x18002acbd  mov     ebx, eax
0x18002acbf  test    eax, eax
0x18002acc1  jns     short loc_18002ACE7
0x18002acc3  mov     r9d, 23Fh
0x18002acc9  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\messagingom"...
0x18002acd0  mov     edx, edi
0x18002acd2  mov     ecx, eax; int
0x18002acd4  call    Log_HREvent_10
0x18002acd9  lea     rcx, [rbp+57h+var_78]
0x18002acdd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ace2  jmp     loc_18002AC1D
0x18002ace7  mov     r8, [rsi+28h]
0x18002aceb  mov     rax, [rsi+30h]
0x18002acef  sub     rax, r8
0x18002acf2  sar     rax, 5
0x18002acf6  test    rax, rax
0x18002acf9  jz      short loc_18002AD60
0x18002acfb  mov     r14d, r15d
0x18002acfe  mov     ebx, r14d
0x18002ad01  mov     edx, 40h ; '@'; Ch
0x18002ad06  shl     rbx, 5
0x18002ad0a  mov     rcx, [r8+rbx]; Str
0x18002ad0e  call    cs:__imp_wcsrchr
0x18002ad14  mov     rcx, [rbp+57h+var_78]
0x18002ad18  neg     rax
0x18002ad1b  mov     rdx, [rsi+28h]
0x18002ad1f  sbb     r8d, r8d
0x18002ad22  mov     dword ptr [rsp+0E0h+ppv], r15d
0x18002ad27  neg     r8d
0x18002ad2a  xor     r9d, r9d
0x18002ad2d  mov     rax, [rcx]
0x18002ad30  add     r8d, edi
0x18002ad33  mov     rdx, [rbx+rdx]
0x18002ad37  mov     rax, [rax+18h]
0x18002ad3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad40  mov     ebx, eax
0x18002ad42  test    eax, eax
0x18002ad44  js      short loc_18002ADA6
0x18002ad46  mov     r8, [rsi+28h]
0x18002ad4a  add     r14d, edi
0x18002ad4d  mov     rcx, [rsi+30h]
0x18002ad51  sub     rcx, r8
0x18002ad54  mov     eax, r14d
0x18002ad57  sar     rcx, 5
0x18002ad5b  cmp     rax, rcx
0x18002ad5e  jb      short loc_18002ACFE
0x18002ad60  mov     rcx, [r13+40h]
0x18002ad64  lea     r8, [rbp+57h+var_70]
0x18002ad68  mov     rdx, [rbp+57h+var_78]
0x18002ad6c  mov     [rbp+57h+var_70], r15
0x18002ad70  mov     rax, [rcx]
0x18002ad73  mov     rax, [rax+30h]
0x18002ad77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad7c  mov     ebx, eax
0x18002ad7e  test    eax, eax
0x18002ad80  jns     short loc_18002ADB1
0x18002ad82  mov     r9d, 24Fh
0x18002ad88  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\messagingom"...
0x18002ad8f  mov     edx, edi
0x18002ad91  mov     ecx, eax; int
0x18002ad93  call    Log_HREvent_10
0x18002ad98  lea     rcx, [rbp+57h+var_70]
0x18002ad9c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ada1  jmp     loc_18002ACD9
0x18002ada6  mov     r9d, 24Bh
0x18002adac  jmp     loc_18002ACC9
0x18002adb1  mov     r10, [rbp+57h+var_70]
0x18002adb5  mov     eax, [rsi]
0x18002adb7  mov     rdx, [rbp+57h+var_78]
0x18002adbb  neg     eax
0x18002adbd  mov     [rbp+57h+var_88], r15
0x18002adc1  mov     rcx, [r10]
0x18002adc4  sbb     r8d, r8d
0x18002adc7  add     r8d, 2
0x18002adcb  xor     r9d, r9d
0x18002adce  mov     rax, [rcx+78h]
0x18002add2  lea     rcx, [rbp+57h+var_88]
0x18002add6  mov     [rsp+0E0h+var_B8], rcx
0x18002addb  mov     rcx, r10
0x18002adde  mov     [rsp+0E0h+ppv], rdx
0x18002ade3  mov     edx, edi
0x18002ade5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adea  mov     ebx, eax
0x18002adec  test    eax, eax
0x18002adee  jns     short loc_18002AE11
0x18002adf0  mov     r9d, 253h
0x18002adf6  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\messagingom"...
0x18002adfd  mov     edx, edi
0x18002adff  mov     ecx, eax; int
0x18002ae01  call    Log_HREvent_10
0x18002ae06  lea     rcx, [rbp+57h+var_88]
0x18002ae0a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ae0f  jmp     short loc_18002AD98
0x18002ae11  lea     rcx, [rsi+60h]; lpSystemTime
0x18002ae15  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r15
0x18002ae19  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x18002ae1d  call    cs:__imp_SystemTimeToFileTime
0x18002ae23  mov     rcx, [rbp+57h+var_88]
0x18002ae27  mov     rdx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x18002ae2b  mov     rax, [rcx]
0x18002ae2e  mov     rax, [rax+90h]
0x18002ae35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae3a  mov     ebx, eax
0x18002ae3c  test    eax, eax
0x18002ae3e  jns     short loc_18002AE48
0x18002ae40  mov     r9d, 257h
0x18002ae46  jmp     short loc_18002ADF6
0x18002ae48  mov     rcx, [rbp+57h+var_88]
0x18002ae4c  mov     rdx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x18002ae50  mov     rax, [rcx]
0x18002ae53  mov     rax, [rax+0A0h]
0x18002ae5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae5f  mov     ebx, eax
0x18002ae61  test    eax, eax
0x18002ae63  jns     short loc_18002AE6D
0x18002ae65  mov     r9d, 258h
0x18002ae6b  jmp     short loc_18002ADF6
0x18002ae6d  cmp     [rsi], r15d
0x18002ae70  jnz     short loc_18002AEE3
0x18002ae72  mov     rdx, [rbp+57h+var_88]
0x18002ae76  lea     rcx, [rbp+57h+var_58]
0x18002ae7a  mov     [rbp+57h+var_58], r15
0x18002ae7e  call    ??0?$CComQIPtr@UISmMessageMMS@@$1?_GUID_32a5998a_e6dc_4e8b_9a7d_74673f2c3388@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ISmMessageMMS,&__s_GUID const _GUID_32a5998a_e6dc_4e8b_9a7d_74673f2c3388>::CComQIPtr<ISmMessageMMS,&__s_GUID const _GUID_32a5998a_e6dc_4e8b_9a7d_74673f2c3388>(IUnknown *)
0x18002ae83  mov     rcx, [rbp+57h+var_58]
0x18002ae87  test    rcx, rcx
0x18002ae8a  jnz     short loc_18002AEB5
0x18002ae8c  mov     ebx, 80004002h
0x18002ae91  mov     r9d, 25Eh
0x18002ae97  mov     ecx, ebx; int
0x18002ae99  xor     edx, edx
0x18002ae9b  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\messagingom"...
0x18002aea2  call    Log_HREvent_10
0x18002aea7  lea     rcx, [rbp+57h+var_58]
0x18002aeab  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002aeb0  jmp     loc_18002AE06
0x18002aeb5  mov     rax, [rcx]
0x18002aeb8  mov     rdx, [rsi+70h]
0x18002aebc  mov     rax, [rax+3E0h]
0x18002aec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aec8  mov     ebx, eax
0x18002aeca  test    eax, eax
0x18002aecc  jns     short loc_18002AEDA
0x18002aece  mov     r9d, 25Fh
0x18002aed4  mov     edx, edi
0x18002aed6  mov     ecx, eax
0x18002aed8  jmp     short loc_18002AE9B
0x18002aeda  lea     rcx, [rbp+57h+var_58]
0x18002aede  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002aee3  mov     rcx, [rbp+57h+var_88]
0x18002aee7  xor     edx, edx
0x18002aee9  mov     rax, [rcx]
0x18002aeec  mov     rax, [rax+20h]
0x18002aef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aef5  mov     ebx, eax
0x18002aef7  test    eax, eax
0x18002aef9  jns     short loc_18002AF06
0x18002aefb  mov     r9d, 263h
0x18002af01  jmp     loc_18002ADF6
0x18002af06  mov     rcx, [rbp+57h+var_88]
0x18002af0a  mov     rdx, [rsi+40h]
0x18002af0e  mov     rax, [rcx]
0x18002af11  mov     rax, [rax+78h]
0x18002af15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af1a  mov     ebx, eax
0x18002af1c  test    eax, eax
0x18002af1e  jns     short loc_18002AF2B
0x18002af20  mov     r9d, 264h
0x18002af26  jmp     loc_18002ADF6
0x18002af2b  mov     rcx, [rbp+57h+var_88]
0x18002af2f  mov     rdx, r12
0x18002af32  mov     rax, [rcx]
0x18002af35  mov     rax, [rax+148h]
0x18002af3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af41  mov     ebx, eax
0x18002af43  test    eax, eax
0x18002af45  jns     short loc_18002AF52
0x18002af47  mov     r9d, 265h
0x18002af4d  jmp     loc_18002ADF6
0x18002af52  mov     rcx, [rbp+57h+var_88]
0x18002af56  mov     rax, [rcx]
0x18002af59  mov     rax, [rax+0E8h]
0x18002af60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af65  mov     ebx, eax
0x18002af67  test    eax, eax
0x18002af69  jns     short loc_18002AF76
0x18002af6b  mov     r9d, 268h
0x18002af71  jmp     loc_18002ADF6
0x18002af76  mov     rdx, [rsi+90h]
0x18002af7d  lea     rax, [rbp+57h+var_88]
0x18002af81  mov     [rbp+57h+var_A0], rax
0x18002af85  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x18002af8f  mov     rax, [rsi+98h]
0x18002af96  sub     rax, rdx
0x18002af99  mov     [rbp+57h+var_98], dil
0x18002af9d  sar     rax, 3
0x18002afa1  imul    rax, rcx
0x18002afa5  test    rax, rax
0x18002afa8  jz      loc_18002B0B0
0x18002afae  mov     r14d, r15d
0x18002afb1  mov     r10, [rbp+57h+var_88]
0x18002afb5  lea     rcx, [rbp+57h+var_68]
0x18002afb9  mov     [rbp+57h+var_68], r15
0x18002afbd  mov     [rsp+0E0h+var_B8], rcx
0x18002afc2  mov     eax, r14d
0x18002afc5  lea     rbx, [rax+rax*4]
  ... truncated ...
```
