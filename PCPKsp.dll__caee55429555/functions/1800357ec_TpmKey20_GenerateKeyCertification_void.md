# TpmKey20::GenerateKeyCertification(void)

- ea: `0x1800357ec`
- end: `0x1800361fc`
- name: `?GenerateKeyCertification@TpmKey20@@IEAAXXZ`
- size: `2576`
- prototype: `void __fastcall(TpmKey20 *__hidden this)`
- caller_count: `3`
- callee_count: `27`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005c2c0`
- `0x18008bb60`
- `0x18008f310`

## callees

- `0x18000dc90`
- `0x18000eda0`
- `0x18000f000`
- `0x18000fea0`
- `0x180010c90`
- `0x180015660`
- `0x1800157c0`
- `0x180029260`
- `0x18002e380`
- `0x18002f774`
- `0x18002fd54`
- `0x180032110`
- `0x18003335c`
- `0x1800334a0`
- `0x1800335b0`
- `0x1800340bc`
- `0x1800357ec`
- `0x1800365f8`
- `0x180040850`
- `0x1800412bc`
- `0x180049ab0`
- `0x180056d5c`
- `0x1800764d0`
- `0x1800768a0`
- `0x180076998`
- `0x18007704c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800359d2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180035a93`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800359d2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180035a93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800361b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800361b1`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800358f3`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800358f3`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180035979`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180035979`

## string_xrefs

- `0x1800358e3`: `SYSTEM\CurrentControlSet\Services\Tpm\KeyAttestationKeys`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall TpmKey20::GenerateKeyCertification(void **this)
{
  int PersistedStateLocation; // eax
  int v3; // ecx
  BYTE *lpData; // rdi
  unsigned int v5; // r12d
  _DWORD *v6; // rsi
  DWORD v7; // ebx
  int v8; // eax
  int v9; // eax
  const struct std::nothrow_t *v10; // rdx
  BYTE *v11; // rax
  DWORD v12; // ecx
  int v13; // eax
  int v14; // ecx
  int v15; // ecx
  unsigned int v16; // r15d
  _DWORD *v17; // rax
  const void *v18; // r8
  unsigned int v19; // edx
  __int64 v20; // rdx
  unsigned int v21; // ebx
  __int64 v22; // rdx
  unsigned int v23; // ebx
  unsigned int v24; // ebx
  int v25; // r15d
  unsigned __int8 *v26; // rbx
  __int64 v27; // rdx
  _BYTE *v28; // rax
  __int64 v29; // rcx
  const struct std::nothrow_t *v30; // rdx
  BYTE *v31; // rax
  __int64 v32; // rax
  _BYTE *v33; // rcx
  const struct std::nothrow_t *v34; // rdx
  __int64 v35; // rax
  BYTE *v36; // rcx
  int KeyInTpm; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cchValueName; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int SourceSize; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int SourceSize_4; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v42; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD v43; // [rsp+68h] [rbp-98h]
  DWORD Type[3]; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v46[24]; // [rsp+80h] [rbp-80h] BYREF
  int v47; // [rsp+140h] [rbp+40h]
  _BYTE v48[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v49[168]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v50; // [rsp+218h] [rbp+118h]
  int v51; // [rsp+234h] [rbp+134h]
  char v52[72]; // [rsp+238h] [rbp+138h] BYREF
  char v53[72]; // [rsp+280h] [rbp+180h] BYREF
  tpm12class::TpmDataObject *v54; // [rsp+2C8h] [rbp+1C8h]
  int v55; // [rsp+2D0h] [rbp+1D0h]
  char v56[72]; // [rsp+2D8h] [rbp+1D8h] BYREF
  _BYTE v57[196]; // [rsp+320h] [rbp+220h] BYREF
  int v58; // [rsp+3E4h] [rbp+2E4h]
  char v59[144]; // [rsp+3F0h] [rbp+2F0h] BYREF
  _BYTE v60[160]; // [rsp+480h] [rbp+380h] BYREF
  unsigned int v61; // [rsp+520h] [rbp+420h]
  tpm12class::TPMW8_SESSION *v62; // [rsp+528h] [rbp+428h]
  int v63; // [rsp+540h] [rbp+440h]
  char v64[72]; // [rsp+548h] [rbp+448h] BYREF
  int v65; // [rsp+590h] [rbp+490h]
  char v66[208]; // [rsp+598h] [rbp+498h] BYREF
  _BYTE v67[136]; // [rsp+668h] [rbp+568h] BYREF
  _BYTE v68[352]; // [rsp+6F0h] [rbp+5F0h] BYREF
  _OWORD Source[2]; // [rsp+850h] [rbp+750h] BYREF
  WCHAR ValueName; // [rsp+870h] [rbp+770h] BYREF
  char v71[526]; // [rsp+872h] [rbp+772h] BYREF
  WCHAR SubKey[264]; // [rsp+A80h] [rbp+980h] BYREF

  KeyInTpm = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v48, L"TpmKey20::GenerateKeyCertification", &KeyInTpm);
  phkResult = 0;
  ValueName = 0;
  memset_0(v71, 0, 0x206u);
  cchValueName = 260;
  Type[0] = 0;
  cbData = 0;
  SourceSize_4 = 0;
  v42 = 0;
  tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v57);
  memset_0(SubKey, 0, 0x208u);
  Type[1] = 520;
  v58 = -2130706431;
  KeyInTpm = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v57, 0);
  if ( KeyInTpm < 0 )
    goto LABEL_85;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"TpmRegKeyAttestationKeys",
                             0,
                             L"SYSTEM\\CurrentControlSet\\Services\\Tpm\\KeyAttestationKeys",
                             0);
  if ( PersistedStateLocation )
  {
    if ( (PersistedStateLocation & 0xFFFF000) == 0x290000 )
    {
      v3 = PersistedStateLocation & 0xFFF | 0x80280000;
    }
    else if ( (PersistedStateLocation & 0xFFF0000) == 0x70000 )
    {
      v3 = (unsigned __int16)PersistedStateLocation;
      if ( (_WORD)PersistedStateLocation )
        v3 = (unsigned __int16)PersistedStateLocation | 0x80070000;
    }
    else
    {
      v3 = PersistedStateLocation | 0x10000000;
    }
    KeyInTpm = v3;
    if ( v3 < 0 )
      goto LABEL_85;
  }
  else
  {
    KeyInTpm = 0;
  }
  lpData = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v43 = 0;
  v8 = RegOpenKeyW(HKEY_LOCAL_MACHINE, SubKey, &phkResult);
  if ( v8 > 0 )
    v8 = (unsigned __int16)v8 | 0x80070000;
  KeyInTpm = v8;
  if ( v8 >= 0 )
  {
    while ( 1 )
    {
      v9 = RegEnumValueW(phkResult, v7, &ValueName, &cchValueName, 0, Type, 0, &cbData);
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      KeyInTpm = v9;
      if ( v9 < 0 )
      {
        if ( v9 == -2147024637 )
          KeyInTpm = 0;
        goto LABEL_85;
      }
      tpm12class::TPMW8_Load::TPMW8_Load((tpm12class::TPMW8_Load *)v49);
      tpm12class::TPMW8_Certify::TPMW8_Certify((tpm12class::TPMW8_Certify *)v60);
      tpm12class::TPMW8_FlushContext::TPMW8_FlushContext((tpm12class::TPMW8_FlushContext *)v46);
      if ( Type[0] != 3 )
        goto LABEL_66;
      v11 = (BYTE *)operator new[](cbData, (const struct std::nothrow_t *)&std::nothrow);
      lpData = v11;
      if ( !v11 )
      {
        KeyInTpm = -2147024888;
        v46[0] = &tpm12class::TPMW8_FlushContext::`vftable';
        v47 = 1073741831;
        tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND((tpm12class::TPMW8_COMMAND *)v46);
        tpm12class::TPMW8_Certify::~TPMW8_Certify((tpm12class::TPMW8_Certify *)v60);
        tpm12class::TPMW8_Load::~TPMW8_Load((tpm12class::TPMW8_Load *)v49);
        goto LABEL_85;
      }
      memset_0(v11, 0, cbData);
      cchValueName = 260;
      if ( RegEnumValueW(phkResult, v7, &ValueName, &cchValueName, 0, Type, lpData, &cbData) )
        goto LABEL_66;
      v12 = cbData;
      if ( cbData >= 0x34
        && *(_DWORD *)lpData == 1297105744
        && *((_DWORD *)lpData + 1) >= 0x34u
        && *((_DWORD *)lpData + 2) == 2
        && (lpData[12] & 1) == 0
        && cbData >= *((_DWORD *)lpData + 1)
                   + *((_DWORD *)lpData + 4)
                   + *((_DWORD *)lpData + 5)
                   + *((_DWORD *)lpData + 6)
                   + *((_DWORD *)lpData + 7)
                   + *((_DWORD *)lpData + 8)
                   + *((_DWORD *)lpData + 9)
                   + *((_DWORD *)lpData + 10)
                   + *((_DWORD *)lpData + 11)
                   + *((_DWORD *)lpData + 12) )
      {
        break;
      }
LABEL_67:
      cchValueName = 260;
      v43 = ++v7;
      if ( lpData )
      {
        v30 = (const struct std::nothrow_t *)v12;
        v31 = lpData;
        if ( v12 )
        {
          do
          {
            *v31++ = 0;
            v30 = (const struct std::nothrow_t *)((char *)v30 - 1);
          }
          while ( v30 );
        }
        operator delete(lpData, v30);
        lpData = 0;
      }
      if ( v6 )
      {
        v32 = v5;
        v33 = v6;
        if ( v5 )
        {
          do
          {
            *v33++ = 0;
            --v32;
          }
          while ( v32 );
        }
        operator delete(v6, v10);
        v6 = 0;
      }
      cbData = 0;
      v46[0] = &tpm12class::TPMW8_FlushContext::`vftable';
      v47 = 1073741831;
      tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND((tpm12class::TPMW8_COMMAND *)v46);
      tpm12class::TPMW8_Certify::~TPMW8_Certify((tpm12class::TPMW8_Certify *)v60);
      tpm12class::TPMW8_Load::~TPMW8_Load((tpm12class::TPMW8_Load *)v49);
    }
    KeyInTpm = TpmKey20::LoadKeyInTpm((TpmKey20 *)this);
    if ( KeyInTpm < 0 )
      goto LABEL_77;
    v63 = *((_DWORD *)this + 116);
    KeyInTpm = tpm12class::TPMW82B_BUFFER::CopyFrom(
                 (tpm12class::TPMW82B_BUFFER *)v64,
                 (const struct tpm12class::TPMW82B_BUFFER *)(this + 40));
    if ( KeyInTpm >= 0 )
    {
      if ( (*((unsigned __int8 (__fastcall **)(void **))*this + 150))(this) )
      {
        KeyInTpm = tpm12class::TPMW8_SESSION::SetAuthProvider(
                     v62,
                     (const struct tpm12class::TPMW82B_BUFFER *)(this + 61),
                     *((_WORD *)v62 + 381));
        if ( KeyInTpm < 0 )
          goto LABEL_77;
      }
      if ( *((char *)this[12] + 60) < 0 )
      {
        *((_WORD *)v62 + 381) = 11;
        *((_BYTE *)v62 + 761) = 1;
        KeyInTpm = tpm12class::TPMW8_SESSION::Create(v62, 0);
        if ( KeyInTpm < 0 )
          goto LABEL_77;
        KeyInTpm = TpmKey20::ExecutePolicy((TpmKey20 *)this, *((_DWORD *)v62 + 4), v61);
        if ( KeyInTpm < 0 )
          goto LABEL_77;
      }
      *(_WORD *)(v50 + 762) = 11;
      v51 = v58;
      KeyInTpm = tpm12class::TPMW82B_BUFFER::CopyFrom(
                   (tpm12class::TPMW82B_BUFFER *)v52,
                   (const struct tpm12class::TPMW82B_BUFFER *)v59);
      if ( KeyInTpm >= 0 )
      {
        KeyInTpm = tpm12class::TpmDataObject::Set(
                     (tpm12class::TpmDataObject *)v53,
                     &lpData[*((_DWORD *)lpData + 1) + *((_DWORD *)lpData + 4)],
                     *((_DWORD *)lpData + 5),
                     0,
                     0);
        if ( KeyInTpm >= 0 )
        {
          KeyInTpm = tpm12class::TpmDataObject::Set(
                       v54,
                       &lpData[*((unsigned int *)lpData + 1) + 2],
                       *((_DWORD *)lpData + 4) - 2,
                       0,
                       0);
          if ( KeyInTpm >= 0 )
          {
            KeyInTpm = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v49, 0);
            if ( KeyInTpm >= 0 )
            {
              v65 = v55;
              KeyInTpm = tpm12class::TPMW82B_BUFFER::CopyFrom(
                           (tpm12class::TPMW82B_BUFFER *)v66,
                           (const struct tpm12class::TPMW82B_BUFFER *)v56);
              if ( KeyInTpm >= 0 )
              {
                memset(Source, 0, sizeof(Source));
                SourceSize = 0;
                v13 = PlatformHash(
                        L"SHA256",
                        *((unsigned __int8 **)v54 + 103),
                        *((unsigned __int16 *)v54 + 408),
                        0,
                        0,
                        (unsigned __int8 *)Source,
                        0x20u,
                        &SourceSize,
                        0);
                if ( v13 )
                {
                  if ( (v13 & 0xFFFF000) == 0x290000 )
                  {
                    v14 = v13 & 0xFFF | 0x80280000;
                  }
                  else if ( (v13 & 0xFFF0000) == 0x70000 )
                  {
                    v14 = (unsigned __int16)v13;
                    if ( (_WORD)v13 )
                      v14 = (unsigned __int16)v13 | 0x80070000;
                  }
                  else
                  {
                    v14 = v13 | 0x10000000;
                  }
                  KeyInTpm = v14;
                  if ( v14 < 0 )
                  {
LABEL_77:
                    v46[0] = &tpm12class::TPMW8_FlushContext::`vftable';
                    v47 = 1073741831;
                    tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND((tpm12class::TPMW8_COMMAND *)v46);
                    tpm12class::TPMW8_Certify::~TPMW8_Certify((tpm12class::TPMW8_Certify *)v60);
                    tpm12class::TPMW8_Load::~TPMW8_Load((tpm12class::TPMW8_Load *)v49);
                    goto LABEL_82;
                  }
                }
                else
                {
                  KeyInTpm = 0;
                }
                KeyInTpm = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v60, 0);
                if ( KeyInTpm >= 0 )
                {
                  KeyInTpm = tpm12class::TpmDataObject::Get((tpm12class::TpmDataObject *)v67, 0, 0, &SourceSize_4);
                  if ( KeyInTpm >= 0 )
                  {
                    KeyInTpm = tpm12class::TpmDataObject::Get((tpm12class::TpmDataObject *)v68, 0, 0, &v42);
                    if ( KeyInTpm >= 0 )
                    {
                      v15 = *((_DWORD *)this + 171);
                      if ( !v15 || !this[86] )
                      {
                        *((_DWORD *)this + 171) = 4;
                        v15 = 4;
                      }
                      v16 = SourceSize_4;
                      v5 = SourceSize_4 + v42 + SourceSize + v15 + 2 * (cchValueName + 5);
                      v17 = operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
                      v6 = v17;
                      if ( !v17 )
                      {
                        KeyInTpm = -2147024888;
                        v46[0] = &tpm12class::TPMW8_FlushContext::`vftable';
                        v47 = 1073741831;
                        tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND((tpm12class::TPMW8_COMMAND *)v46);
                        tpm12class::TPMW8_Certify::~TPMW8_Certify((tpm12class::TPMW8_Certify *)v60);
                        tpm12class::TPMW8_Load::~TPMW8_Load((tpm12class::TPMW8_Load *)v49);
LABEL_82:
                        v35 = cbData;
                        v36 = lpData;
                        if ( cbData )
                        {
                          do
                          {
                            *v36++ = 0;
                            --v35;
                          }
                          while ( v35 );
                        }
                        operator delete(lpData, v34);
                        goto LABEL_85;
                      }
                      memset_0(v17, 0, v5);
                      v18 = this[86];
                      if ( v18 )
                      {
                        memcpy_s(v6, v5, v18, *((unsigned int *)this + 171));
                        v19 = *((_DWORD *)this + 171);
                      }
                      else
                      {
                        *v6 = 1095447124;
                        v19 = 4;
                      }
                      *(_DWORD *)((char *)v6 + v19) = v5 - *((_DWORD *)this + 171) - 4;
                      v20 = v19 + 4;
                      *(_WORD *)((char *)v6 + v20) = 2 * (cchValueName + 1);
                      v21 = v20 + 2;
                      memcpy_s((char *)v6 + v21, v5 - v21, &ValueName, 2LL * (cchValueName + 1));
                      v22 = v21 + 2 * (cchValueName + 1);
                      *(_WORD *)((char *)v6 + v22) = SourceSize;
                      v23 = v22 + 2;
                      memcpy_s((char *)v6 + v23, v5 - v23, Source, SourceSize);
                      v24 = SourceSize + v23;
                      KeyInTpm = tpm12class::TpmDataObject::Get(
                                   (tpm12class::TpmDataObject *)v67,
                                   (unsigned __int8 *)v6 + v24,
                                   v16,
                                   &SourceSize_4);
                      if ( KeyInTpm >= 0 )
                      {
                        *(_WORD *)((char *)v6 + v24) = (*((unsigned __int8 *)v6 + v24) << 8)
                                                     + *((unsigned __int8 *)v6 + v24 + 1);
                        v25 = v24 + SourceSize_4;
                        v26 = (unsigned __int8 *)v6 + v24 + SourceSize_4;
                        KeyInTpm = tpm12class::TpmDataObject::Get((tpm12class::TpmDataObject *)v68, v26, v42, &v42);
                        if ( KeyInTpm >= 0 )
                        {
                          v27 = *v26 << 8;
                          *(_WORD *)v26 = (*v26 << 8) + *((unsigned __int8 *)v6 + (unsigned int)(v25 + 1));
                          v28 = this[86];
                          if ( v28 )
                          {
                            v29 = *((unsigned int *)this + 171);
                            if ( *((_DWORD *)this + 171) )
                            {
                              v27 = 1;
                              do
                              {
                                *v28++ = 0;
                                --v29;
                              }
                              while ( v29 );
                            }
                            operator delete(this[86], (const struct std::nothrow_t *)v27);
                          }
                          this[86] = v6;
                          *((_DWORD *)this + 171) = v5;
                          v6 = 0;
                          v5 = 0;
                          v47 = v55;
                          KeyInTpm = tpm12class::TPMW8_FlushContext::Execute((tpm12class::TPMW8_FlushContext *)v46, 0);
                        }
                      }
                      v7 = v43;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_66:
    v12 = cbData;
    goto LABEL_67;
  }
LABEL_85:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v57);
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v48);
}

```

## disassembly

```asm
0x1800357ec  push    rbp
0x1800357ee  push    rbx
0x1800357ef  push    rsi
0x1800357f0  push    rdi
0x1800357f1  push    r12
0x1800357f3  push    r13
0x1800357f5  push    r14
0x1800357f7  push    r15
0x1800357f9  lea     rbp, [rsp-0BA8h]
0x180035801  sub     rsp, 0CA8h
0x180035808  mov     rax, cs:__security_cookie
0x18003580f  xor     rax, rsp
0x180035812  mov     [rbp+0BE0h+var_50], rax
0x180035819  mov     r14, rcx
0x18003581c  xor     r13d, r13d
0x18003581f  mov     [rsp+0CE0h+var_C90], r13d
0x180035824  lea     r8, [rsp+0CE0h+var_C90]; int *
0x180035829  lea     rdx, aTpmkey20Genera; "TpmKey20::GenerateKeyCertification"
0x180035830  lea     rcx, [rbp+0BE0h+var_B90]; this
0x180035834  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x180035839  nop
0x18003583a  mov     [rsp+0CE0h+phkResult], r13
0x18003583f  mov     [rbp+0BE0h+ValueName], r13w
0x180035847  xor     edx, edx; Val
0x180035849  mov     r8d, 206h; Size
0x18003584f  lea     rcx, [rbp+0BE0h+var_46E]; void *
0x180035856  call    memset_0
0x18003585b  mov     [rsp+0CE0h+cchValueName], 104h
0x180035863  mov     [rsp+0CE0h+Type], r13d
0x180035868  mov     [rsp+0CE0h+cbData], r13d
0x18003586d  mov     dword ptr [rsp+0CE0h+SourceSize+4], r13d
0x180035872  mov     [rsp+0CE0h+var_C7C], r13d
0x180035877  lea     rcx, [rbp+0BE0h+var_9C0]; this
0x18003587e  call    ??0TPMW8_ReadPublic@tpm12class@@QEAA@XZ; tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic(void)
0x180035883  nop
0x180035884  mov     ebx, 208h
0x180035889  mov     r8d, ebx; Size
0x18003588c  xor     edx, edx; Val
0x18003588e  lea     rcx, [rbp+0BE0h+SubKey]; void *
0x180035895  call    memset_0
0x18003589a  mov     [rsp+0CE0h+var_C70], ebx
0x18003589e  mov     [rbp+0BE0h+var_8FC], 81000001h
0x1800358a8  xor     edx, edx; void *
0x1800358aa  lea     rcx, [rbp+0BE0h+var_9C0]; this
0x1800358b1  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x1800358b6  mov     [rsp+0CE0h+var_C90], eax
0x1800358ba  test    eax, eax
0x1800358bc  js      loc_1800361A7
0x1800358c2  lea     rax, [rsp+0CE0h+var_C70]
0x1800358c7  mov     [rsp+0CE0h+lpData], rax
0x1800358cc  mov     eax, [rsp+0CE0h+var_C70]
0x1800358d0  mov     dword ptr [rsp+0CE0h+lpType], eax
0x1800358d4  lea     rax, [rbp+0BE0h+SubKey]
0x1800358db  mov     [rsp+0CE0h+lpReserved], rax
0x1800358e0  xor     r9d, r9d
0x1800358e3  lea     r8, aSystemCurrentc_18; "SYSTEM\\CurrentControlSet\\Services\\Tp"...
0x1800358ea  xor     edx, edx
0x1800358ec  lea     rcx, aTpmregkeyattes; "TpmRegKeyAttestationKeys"
0x1800358f3  call    cs:__imp_RtlGetPersistedStateLocation
0x1800358fa  nop     dword ptr [rax+rax+00h]
0x1800358ff  mov     ecx, eax
0x180035901  mov     r15d, 80070000h
0x180035907  test    eax, eax
0x180035909  jnz     short loc_180035912
0x18003590b  mov     [rsp+0CE0h+var_C90], r13d
0x180035910  jmp     short loc_180035956
0x180035912  and     eax, 0FFFF000h
0x180035917  cmp     eax, 290000h
0x18003591c  jnz     short loc_18003592C
0x18003591e  and     ecx, 0FFFh
0x180035924  or      ecx, 80280000h
0x18003592a  jmp     short loc_18003594A
0x18003592c  mov     eax, ecx
0x18003592e  and     eax, 0FFF0000h
0x180035933  cmp     eax, 70000h
0x180035938  jnz     short loc_180035946
0x18003593a  movzx   ecx, cx
0x18003593d  test    ecx, ecx
0x18003593f  jz      short loc_18003594A
0x180035941  or      ecx, r15d
0x180035944  jmp     short loc_18003594A
0x180035946  bts     ecx, 1Ch
0x18003594a  mov     [rsp+0CE0h+var_C90], ecx
0x18003594e  test    ecx, ecx
0x180035950  js      loc_1800361A7
0x180035956  mov     rdi, r13
0x180035959  mov     r12d, r13d
0x18003595c  mov     rsi, r13
0x18003595f  mov     ebx, r13d
0x180035962  mov     [rsp+0CE0h+var_C78], ebx
0x180035966  lea     r8, [rsp+0CE0h+phkResult]; phkResult
0x18003596b  lea     rdx, [rbp+0BE0h+SubKey]; lpSubKey
0x180035972  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035979  call    cs:__imp_RegOpenKeyW
0x180035980  nop     dword ptr [rax+rax+00h]
0x180035985  test    eax, eax
0x180035987  jle     short loc_18003598F
0x180035989  movzx   eax, ax
0x18003598c  or      eax, r15d
0x18003598f  mov     [rsp+0CE0h+var_C90], eax
0x180035993  test    eax, eax
0x180035995  js      loc_1800361A7
0x18003599b  mov     r15d, 1
0x1800359a1  lea     rax, [rsp+0CE0h+cbData]
0x1800359a6  mov     [rsp+0CE0h+lpcbData], rax; lpcbData
0x1800359ab  mov     [rsp+0CE0h+lpData], r13; lpData
0x1800359b0  lea     rax, [rsp+0CE0h+Type]
0x1800359b5  mov     [rsp+0CE0h+lpType], rax; lpType
0x1800359ba  mov     [rsp+0CE0h+lpReserved], r13; lpReserved
0x1800359bf  lea     r9, [rsp+0CE0h+cchValueName]; lpcchValueName
0x1800359c4  lea     r8, [rbp+0BE0h+ValueName]; lpValueName
0x1800359cb  mov     edx, ebx; dwIndex
0x1800359cd  mov     rcx, [rsp+0CE0h+phkResult]; hKey
0x1800359d2  call    cs:__imp_RegEnumValueW
0x1800359d9  nop     dword ptr [rax+rax+00h]
0x1800359de  test    eax, eax
0x1800359e0  jle     short loc_1800359EA
0x1800359e2  movzx   eax, ax
0x1800359e5  or      eax, 80070000h
0x1800359ea  mov     [rsp+0CE0h+var_C90], eax
0x1800359ee  test    eax, eax
0x1800359f0  js      loc_180036154
0x1800359f6  lea     rcx, [rbp+0BE0h+var_B70]; this
0x1800359fa  call    ??0TPMW8_Load@tpm12class@@QEAA@XZ; tpm12class::TPMW8_Load::TPMW8_Load(void)
0x1800359ff  nop
0x180035a00  lea     rcx, [rbp+0BE0h+var_860]; this
0x180035a07  call    ??0TPMW8_Certify@tpm12class@@QEAA@XZ; tpm12class::TPMW8_Certify::TPMW8_Certify(void)
0x180035a0c  nop
0x180035a0d  lea     rcx, [rbp+0BE0h+var_C60]; this
0x180035a11  call    ??0TPMW8_FlushContext@tpm12class@@QEAA@XZ; tpm12class::TPMW8_FlushContext::TPMW8_FlushContext(void)
0x180035a16  nop
0x180035a17  cmp     [rsp+0CE0h+Type], 3
0x180035a1c  jnz     loc_180036006
0x180035a22  test    rdi, rdi
0x180035a25  jz      short loc_180035A2F
0x180035a27  mov     rcx, rdi; void *
0x180035a2a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180035a2f  mov     ecx, [rsp+0CE0h+cbData]; unsigned __int64
0x180035a33  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180035a3a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180035a3f  mov     rdi, rax
0x180035a42  test    rax, rax
0x180035a45  jz      loc_180036118
0x180035a4b  mov     r8d, [rsp+0CE0h+cbData]; Size
0x180035a50  xor     edx, edx; Val
0x180035a52  mov     rcx, rax; void *
0x180035a55  call    memset_0
0x180035a5a  mov     [rsp+0CE0h+cchValueName], 104h
0x180035a62  lea     rax, [rsp+0CE0h+cbData]
0x180035a67  mov     [rsp+0CE0h+lpcbData], rax; lpcbData
0x180035a6c  mov     [rsp+0CE0h+lpData], rdi; lpData
0x180035a71  lea     rax, [rsp+0CE0h+Type]
0x180035a76  mov     [rsp+0CE0h+lpType], rax; lpType
0x180035a7b  mov     [rsp+0CE0h+lpReserved], r13; lpReserved
0x180035a80  lea     r9, [rsp+0CE0h+cchValueName]; lpcchValueName
0x180035a85  lea     r8, [rbp+0BE0h+ValueName]; lpValueName
0x180035a8c  mov     edx, ebx; dwIndex
0x180035a8e  mov     rcx, [rsp+0CE0h+phkResult]; hKey
0x180035a93  call    cs:__imp_RegEnumValueW
0x180035a9a  nop     dword ptr [rax+rax+00h]
0x180035a9f  test    eax, eax
0x180035aa1  jnz     loc_180036006
0x180035aa7  mov     ecx, [rsp+0CE0h+cbData]
0x180035aab  cmp     ecx, 34h ; '4'
0x180035aae  jb      loc_18003600A
0x180035ab4  cmp     dword ptr [rdi], 4D504350h
0x180035aba  jnz     loc_18003600A
0x180035ac0  cmp     dword ptr [rdi+4], 34h ; '4'
0x180035ac4  jb      loc_18003600A
0x180035aca  cmp     dword ptr [rdi+8], 2
0x180035ace  jnz     loc_18003600A
0x180035ad4  test    [rdi+0Ch], r15b
0x180035ad8  jnz     loc_18003600A
0x180035ade  mov     eax, [rdi+30h]
0x180035ae1  add     eax, [rdi+2Ch]
0x180035ae4  add     eax, [rdi+28h]
0x180035ae7  add     eax, [rdi+24h]
0x180035aea  add     eax, [rdi+20h]
0x180035aed  add     eax, [rdi+1Ch]
0x180035af0  add     eax, [rdi+18h]
0x180035af3  add     eax, [rdi+14h]
0x180035af6  add     eax, [rdi+10h]
0x180035af9  add     eax, [rdi+4]
0x180035afc  cmp     ecx, eax
0x180035afe  jb      loc_18003600A
0x180035b04  mov     rcx, r14; this
0x180035b07  call    ?LoadKeyInTpm@TpmKey20@@IEAAJXZ; TpmKey20::LoadKeyInTpm(void)
0x180035b0c  mov     [rsp+0CE0h+var_C90], eax
0x180035b10  test    eax, eax
0x180035b12  js      loc_1800360E4
0x180035b18  mov     eax, [r14+1D0h]
0x180035b1f  mov     [rbp+0BE0h+var_7A0], eax
0x180035b25  lea     rdx, [r14+140h]; struct tpm12class::TPMW82B_BUFFER *
0x180035b2c  lea     rcx, [rbp+0BE0h+var_798]; this
0x180035b33  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x180035b38  mov     [rsp+0CE0h+var_C90], eax
0x180035b3c  test    eax, eax
0x180035b3e  js      loc_180036006
0x180035b44  mov     rax, [r14]
0x180035b47  mov     rcx, r14
0x180035b4a  mov     rax, [rax+4B0h]
0x180035b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b56  test    al, al
0x180035b58  jz      short loc_180035B81
0x180035b5a  mov     rcx, [rbp+0BE0h+var_7B8]; this
0x180035b61  lea     rdx, [r14+1E8h]; struct tpm12class::TPMW82B_BUFFER *
0x180035b68  movzx   r8d, word ptr [rcx+2FAh]; unsigned __int16
0x180035b70  call    ?SetAuthProvider@TPMW8_SESSION@tpm12class@@QEAAJAEBVTPMW82B_BUFFER@2@G@Z; tpm12class::TPMW8_SESSION::SetAuthProvider(tpm12class::TPMW82B_BUFFER const &,ushort)
0x180035b75  mov     [rsp+0CE0h+var_C90], eax
0x180035b79  test    eax, eax
0x180035b7b  js      loc_1800360E4
0x180035b81  mov     rax, [r14+60h]
0x180035b85  test    byte ptr [rax+3Ch], 80h
0x180035b89  jz      short loc_180035BE8
0x180035b8b  mov     rax, [rbp+0BE0h+var_7B8]
0x180035b92  mov     word ptr [rax+2FAh], 0Bh
0x180035b9b  mov     rax, [rbp+0BE0h+var_7B8]
0x180035ba2  mov     [rax+2F9h], r15b
0x180035ba9  xor     edx, edx; void *
0x180035bab  mov     rcx, [rbp+0BE0h+var_7B8]; this
0x180035bb2  call    ?Create@TPMW8_SESSION@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_SESSION::Create(void *)
0x180035bb7  mov     [rsp+0CE0h+var_C90], eax
0x180035bbb  test    eax, eax
0x180035bbd  js      loc_1800360E4
0x180035bc3  mov     r8d, [rbp+0BE0h+var_7C0]; unsigned int
0x180035bca  mov     rdx, [rbp+0BE0h+var_7B8]
0x180035bd1  mov     edx, [rdx+10h]; unsigned int
0x180035bd4  mov     rcx, r14; this
0x180035bd7  call    ?ExecutePolicy@TpmKey20@@IEAAJII@Z; TpmKey20::ExecutePolicy(uint,uint)
0x180035bdc  mov     [rsp+0CE0h+var_C90], eax
0x180035be0  test    eax, eax
0x180035be2  js      loc_1800360E4
0x180035be8  mov     rax, [rbp+0BE0h+var_AC8]
0x180035bef  mov     word ptr [rax+2FAh], 0Bh
0x180035bf8  mov     eax, [rbp+0BE0h+var_8FC]
0x180035bfe  mov     [rbp+0BE0h+var_AAC], eax
0x180035c04  lea     rdx, [rbp+0BE0h+var_8F0]; struct tpm12class::TPMW82B_BUFFER *
0x180035c0b  lea     rcx, [rbp+0BE0h+var_AA8]; this
0x180035c12  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x180035c17  mov     [rsp+0CE0h+var_C90], eax
0x180035c1b  test    eax, eax
0x180035c1d  js      loc_180036006
0x180035c23  mov     edx, [rdi+10h]
0x180035c26  add     edx, [rdi+4]
0x180035c29  add     rdx, rdi; unsigned __int8 *
0x180035c2c  mov     [rsp+0CE0h+lpReserved], r13; unsigned int *
0x180035c31  xor     r9d, r9d; unsigned __int8 **
0x180035c34  mov     r8d, [rdi+14h]; unsigned int
0x180035c38  lea     rcx, [rbp+0BE0h+var_A60]; this
0x180035c3f  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEBEIPEAPEBEPEAI@Z; tpm12class::TpmDataObject::Set(uchar const *,uint,uchar const * *,uint *)
0x180035c44  mov     [rsp+0CE0h+var_C90], eax
0x180035c48  test    eax, eax
0x180035c4a  js      loc_180036006
0x180035c50  mov     r8d, [rdi+10h]
0x180035c54  sub     r8d, 2; unsigned int
0x180035c58  mov     edx, [rdi+4]
0x180035c5b  add     rdx, 2
0x180035c5f  add     rdx, rdi; unsigned __int8 *
0x180035c62  mov     [rsp+0CE0h+lpReserved], r13; unsigned int *
0x180035c67  xor     r9d, r9d; unsigned __int8 **
0x180035c6a  mov     rcx, [rbp+0BE0h+var_A18]; this
0x180035c71  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEBEIPEAPEBEPEAI@Z; tpm12class::TpmDataObject::Set(uchar const *,uint,uchar const * *,uint *)
0x180035c76  mov     [rsp+0CE0h+var_C90], eax
0x180035c7a  test    eax, eax
0x180035c7c  js      loc_180036006
0x180035c82  xor     edx, edx; void *
0x180035c84  lea     rcx, [rbp+0BE0h+var_B70]; this
0x180035c88  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x180035c8d  mov     [rsp+0CE0h+var_C90], eax
0x180035c91  test    eax, eax
0x180035c93  js      loc_180036006
0x180035c99  mov     eax, [rbp+0BE0h+var_A10]
0x180035c9f  mov     [rbp+0BE0h+var_750], eax
0x180035ca5  lea     rdx, [rbp+0BE0h+var_A08]; struct tpm12class::TPMW82B_BUFFER *
0x180035cac  lea     rcx, [rbp+0BE0h+var_748]; this
0x180035cb3  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x180035cb8  mov     [rsp+0CE0h+var_C90], eax
0x180035cbc  test    eax, eax
0x180035cbe  js      loc_180036006
0x180035cc4  xorps   xmm0, xmm0
0x180035cc7  movups  [rbp+0BE0h+Source], xmm0
0x180035cce  movups  [rbp+0BE0h+var_480], xmm0
0x180035cd5  mov     dword ptr [rsp+0CE0h+SourceSize], r13d
0x180035cda  mov     rdx, [rbp+0BE0h+var_A18]
0x180035ce1  movzx   r8d, word ptr [rdx+330h]; unsigned int
0x180035ce9  mov     [rsp+0CE0h+var_CA0], r13d; unsigned int
0x180035cee  lea     rax, [rsp+0CE0h+SourceSize]
0x180035cf3  mov     [rsp+0CE0h+lpcbData], rax; unsigned int *
0x180035cf8  mov     dword ptr [rsp+0CE0h+lpData], 20h ; ' '; unsigned int
0x180035d00  lea     rax, [rbp+0BE0h+Source]
0x180035d07  mov     [rsp+0CE0h+lpType], rax; unsigned __int8 *
0x180035d0c  mov     dword ptr [rsp+0CE0h+lpReserved], r13d; unsigned int
0x180035d11  xor     r9d, r9d; unsigned __int8 *
0x180035d14  mov     rdx, [rdx+338h]; unsigned __int8 *
0x180035d1b  lea     rcx, aSha256_0; "SHA256"
0x180035d22  call    ?PlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z; PlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x180035d27  mov     ecx, eax
0x180035d29  test    eax, eax
0x180035d2b  jnz     short loc_180035D34
0x180035d2d  mov     [rsp+0CE0h+var_C90], r13d
  ... truncated ...
```
