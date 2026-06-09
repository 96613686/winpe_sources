# CMidiBuilder::CreateMidiPortsForKsFilter(IMMDevice *,ulong,ushort const *)

- ea: `0x18003ce28`
- end: `0x18003d30b`
- name: `?CreateMidiPortsForKsFilter@CMidiBuilder@@AEAA_NPEAUIMMDevice@@KPEBG@Z`
- size: `1251`
- prototype: `char __fastcall(CMidiBuilder *this, struct IMMDevice *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18005713c`

## callees

- `0x180006b0c`
- `0x180024208`
- `0x180025f5c`
- `0x180032b38`
- `0x1800351f0`
- `0x18003ce28`
- `0x18003d314`
- `0x18003e920`
- `0x18003f780`
- `0x18003f7a4`
- `0x180049040`
- `0x180068010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18003d0ba`
- `ntdll!RtlInitUnicodeString` at `0x18003d0ba`
- `ntdll!RtlNtStatusToDosError` at `0x18003d0d6`
- `ntdll!RtlNtStatusToDosError` at `0x18003d0d6`
- `ntdll!RtlHashUnicodeString` at `0x18003d0ce`
- `ntdll!RtlHashUnicodeString` at `0x18003d0ce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d1d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d266`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d1d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d266`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d2b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d2be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d2cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d2b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d2be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d2cd`
- `PROPSYS!PropVariantToStringAlloc` at `0x18003d063`
- `PROPSYS!PropVariantToStringAlloc` at `0x18003d063`

## pseudocode

```c
char __fastcall CMidiBuilder::CreateMidiPortsForKsFilter(
        CMidiBuilder *this,
        struct IMMDevice *a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  unsigned __int16 *v7; // rbx
  char v8; // di
  unsigned int i; // esi
  const unsigned __int16 *v10; // r8
  NTSTATUS v11; // eax
  signed int v12; // eax
  bool v13; // sf
  CMidiBuilder *v14; // rcx
  int v15; // eax
  unsigned int v16; // r11d
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // r9
  unsigned __int64 v20; // rdx
  const unsigned __int16 *v21; // rax
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v24; // [rsp+48h] [rbp-B8h] BYREF
  PCWSTR SourceString; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v26; // [rsp+58h] [rbp-A8h] BYREF
  int v27; // [rsp+5Ch] [rbp-A4h] BYREF
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  ULONG HashValue; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h] BYREF
  __int64 v33; // [rsp+80h] [rbp-80h] BYREF
  PWSTR ppszOut; // [rsp+88h] [rbp-78h] BYREF
  __int64 v35; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v36; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v37; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v38; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v39; // [rsp+B0h] [rbp-50h] BYREF
  PROPVARIANT propvar[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-38h]
  struct _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-30h] BYREF
  int v43; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v44; // [rsp+E4h] [rbp-1Ch]
  int v45; // [rsp+ECh] [rbp-14h]
  GUID v46; // [rsp+F0h] [rbp-10h]
  GUID v47; // [rsp+100h] [rbp+0h]
  GUID v48; // [rsp+110h] [rbp+10h]
  _BYTE v49[48]; // [rsp+120h] [rbp+20h] BYREF
  struct _GUID Buf1[2]; // [rsp+150h] [rbp+50h] BYREF

  v35 = 0;
  v26 = 0;
  SourceString = 0;
  ppszOut = 0;
  v7 = 0;
  v38 = 0;
  HashValue = 0;
  v44 = 0;
  v45 = 0;
  v43 = 64;
  v46 = GUID_e725d360_62cc_11cf_a5d6_28db04c10000;
  v47 = GUID_1d262760_e957_11cf_a5d6_28db04c10000;
  v48 = GUID_0f6417d6_c318_11d0_a43f_00a0c9223196;
  if ( ((int (__fastcall *)(struct IMMDevice *, GUID *, __int64, _QWORD, __int64 *))a2->lpVtbl->Activate)(
         a2,
         &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
         1,
         0,
         &v35) < 0
    || (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v35 + 24LL))(v35, &v26) < 0 )
  {
LABEL_40:
    v8 = 0;
  }
  else
  {
    v8 = 0;
    v36 = 0;
    for ( i = 0; i < v26; ++i )
    {
      v23 = 0;
      v27 = 0;
      if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v35 + 32LL))(v35, i, &v23) < 0
        || (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 24LL))(v23, &v27) < 0 )
      {
        goto LABEL_39;
      }
      if ( v27 == 3 )
      {
        v24 = 0;
        ATL::CComPtr<IPart>::operator=<IConnector>(&v24);
        v30 = 0;
        if ( ((int (__fastcall *)(struct IUnknown *, __int64, GUID *, __int64 *))v24->lpVtbl[4].AddRef)(
               v24,
               1,
               &GUID_3cb4a69d_bb6f_4d2b_95b7_452d2c155db5,
               &v30) < 0 )
          goto LABEL_38;
        v28 = 0;
        if ( (*(int (__fastcall **)(__int64, int *, __int64, int *))(*(_QWORD *)v30 + 24LL))(v30, &v43, 64, &v28) < 0 )
          goto LABEL_38;
        if ( v28 )
        {
          v10 = SourceString;
          if ( !SourceString )
          {
            v33 = 0;
            v32 = 0;
            v31 = 0;
            memset_0(v49, 0, 0x48u);
            *(_OWORD *)propvar = 0;
            v41 = 0;
            DestinationString = 0;
            v39 = 0;
            if ( ((int (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))a2->lpVtbl->OpenPropertyStore)(a2, 0, &v33) < 0
              || (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v33 + 40LL))(
                   v33,
                   &PKEY_Device_InstanceId,
                   propvar) < 0
              || PropVariantToStringAlloc(propvar, &ppszOut) < 0
              || ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                   a2,
                   &GUID_3ade56af_4375_4413_9c91_4c652595ab07,
                   &v32) < 0
              || (*(int (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v32 + 32LL))(v32, &SourceString) < 0 )
            {
              goto LABEL_37;
            }
            RtlInitUnicodeString(&DestinationString, SourceString);
            v11 = RtlHashUnicodeString(&DestinationString, 1u, 0, &HashValue);
            v12 = RtlNtStatusToDosError(v11);
            v13 = v12 < 0;
            if ( v12 > 0 )
              v13 = 1;
            if ( v13 )
              goto LABEL_37;
            if ( ((int (__fastcall *)(struct IMMDevice *, GUID *, __int64))a2->lpVtbl->Activate)(
                   a2,
                   &GUID_1136a91a_2bef_45b3_91d9_0a58472ee8a7,
                   23) >= 0
              && (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v31 + 24LL))(v31, v49) >= 0 )
            {
              if ( memcmp_0(Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
              {
                v37 = 0;
                if ( CMidiBuilder::ReadProductNameFromMediaCategories(v14, Buf1, &v37) >= 0 )
                {
                  v15 = StringCchLengthW(v37, 0x7FFFFFFFu, &v39);
                  if ( v15 == -2147024809 )
                  {
                    v17 = v16;
                  }
                  else
                  {
                    if ( v15 < 0 )
                      goto LABEL_37;
                    v17 = v39;
                  }
                  v18 = v17 + 1;
                  if ( !(unsigned __int8)ATL::CHeapPtrBase<unsigned short,ATL::CComAllocator>::AllocateBytes(
                                           &v38,
                                           2 * v18) )
                  {
                    v7 = v38;
LABEL_37:
                    PropVariantClear(propvar);
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
LABEL_38:
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
LABEL_39:
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
                    goto LABEL_40;
                  }
                  v19 = v18;
                  v20 = v18;
                  v7 = v38;
                  if ( (int)StringCchCopyNW(v38, v20, v37, v19) < 0 )
                    goto LABEL_37;
                }
              }
            }
            PropVariantClear(propvar);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
            v10 = SourceString;
          }
          v8 = 1;
          v21 = a4;
          if ( v7 )
            v21 = v7;
          CMidiBuilder::CreateMidiPortForKsPin(
            (CMidiBuilder *)&v36,
            (struct IPart *)v24,
            v10,
            HashValue,
            ppszOut,
            a3,
            v21,
            &v36);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
    }
  }
  CoTaskMemFree(v7);
  CoTaskMemFree(ppszOut);
  ppszOut = 0;
  CoTaskMemFree((LPVOID)SourceString);
  SourceString = 0;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
  return v8;
}

```

## disassembly

```asm
0x18003ce28  mov     [rsp-8+arg_0], rbx
0x18003ce2d  push    rbp
0x18003ce2e  push    rsi
0x18003ce2f  push    rdi
0x18003ce30  push    r12
0x18003ce32  push    r13
0x18003ce34  push    r14
0x18003ce36  push    r15
0x18003ce38  lea     rbp, [rsp-80h]
0x18003ce3d  sub     rsp, 180h
0x18003ce44  mov     rax, cs:__security_cookie
0x18003ce4b  xor     rax, rsp
0x18003ce4e  mov     [rbp+0B0h+var_40], rax
0x18003ce52  mov     r12, r9
0x18003ce55  mov     r15d, r8d
0x18003ce58  mov     r14, rdx
0x18003ce5b  xor     r13d, r13d
0x18003ce5e  mov     [rbp+0B0h+var_120], r13
0x18003ce62  mov     [rsp+1B0h+var_158], r13d
0x18003ce67  mov     [rsp+1B0h+SourceString], r13
0x18003ce6c  mov     [rbp+0B0h+ppszOut], r13
0x18003ce70  mov     ebx, r13d
0x18003ce73  mov     [rbp+0B0h+var_108], rbx
0x18003ce77  mov     [rsp+1B0h+HashValue], r13d
0x18003ce7c  mov     [rbp+0B0h+var_CC], r13
0x18003ce80  mov     [rbp+0B0h+var_C4], r13d
0x18003ce84  mov     [rbp+0B0h+var_D0], 40h ; '@'
0x18003ce8b  movups  xmm0, xmmword ptr cs:_GUID_e725d360_62cc_11cf_a5d6_28db04c10000.Data1
0x18003ce92  movdqu  [rbp+0B0h+var_C0], xmm0
0x18003ce97  movups  xmm1, xmmword ptr cs:_GUID_1d262760_e957_11cf_a5d6_28db04c10000.Data1
0x18003ce9e  movdqu  [rbp+0B0h+var_B0], xmm1
0x18003cea3  movups  xmm0, xmmword ptr cs:_GUID_0f6417d6_c318_11d0_a43f_00a0c9223196.Data1
0x18003ceaa  movdqu  [rbp+0B0h+var_A0], xmm0
0x18003ceaf  mov     rax, [rdx]
0x18003ceb2  lea     rcx, [rbp+0B0h+var_120]
0x18003ceb6  mov     [rsp+1B0h+var_190], rcx
0x18003cebb  xor     r9d, r9d
0x18003cebe  lea     r8d, [r13+1]
0x18003cec2  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x18003cec9  mov     rcx, r14
0x18003cecc  mov     rax, [rax+18h]
0x18003ced0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ced5  test    eax, eax
0x18003ced7  js      loc_18003D2AD
0x18003cedd  mov     rcx, [rbp+0B0h+var_120]
0x18003cee1  mov     rax, [rcx]
0x18003cee4  lea     rdx, [rsp+1B0h+var_158]
0x18003cee9  mov     rax, [rax+18h]
0x18003ceed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cef2  test    eax, eax
0x18003cef4  js      loc_18003D2AD
0x18003cefa  mov     dil, r13b
0x18003cefd  mov     [rbp+0B0h+var_118], r13d
0x18003cf01  mov     esi, r13d
0x18003cf04  cmp     esi, [rsp+1B0h+var_158]
0x18003cf08  jnb     loc_18003D2B0
0x18003cf0e  mov     [rsp+1B0h+var_170], r13
0x18003cf13  mov     [rsp+1B0h+var_154], r13d
0x18003cf18  mov     rcx, [rbp+0B0h+var_120]
0x18003cf1c  mov     rax, [rcx]
0x18003cf1f  lea     r8, [rsp+1B0h+var_170]
0x18003cf24  mov     edx, esi
0x18003cf26  mov     rax, [rax+20h]
0x18003cf2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf2f  test    eax, eax
0x18003cf31  js      loc_18003D2A3
0x18003cf37  mov     rcx, [rsp+1B0h+var_170]
0x18003cf3c  mov     rax, [rcx]
0x18003cf3f  lea     rdx, [rsp+1B0h+var_154]
0x18003cf44  mov     rax, [rax+18h]
0x18003cf48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf4d  test    eax, eax
0x18003cf4f  js      loc_18003D2A3
0x18003cf55  cmp     [rsp+1B0h+var_154], 3
0x18003cf5a  jnz     loc_18003D24D
0x18003cf60  mov     [rsp+1B0h+var_168], r13
0x18003cf65  lea     rdx, [rsp+1B0h+var_170]
0x18003cf6a  lea     rcx, [rsp+1B0h+var_168]; struct IUnknown **
0x18003cf6f  call    ??$?4UIConnector@@@?$CComPtr@UIPart@@@ATL@@QEAAPEAUIPart@@AEBV?$CComPtr@UIConnector@@@1@@Z; ATL::CComPtr<IPart>::operator=<IConnector>(ATL::CComPtr<IConnector> const &)
0x18003cf74  mov     [rsp+1B0h+var_148], r13
0x18003cf79  mov     rcx, [rsp+1B0h+var_168]
0x18003cf7e  mov     rax, [rcx]
0x18003cf81  lea     r9, [rsp+1B0h+var_148]
0x18003cf86  lea     r8, _GUID_3cb4a69d_bb6f_4d2b_95b7_452d2c155db5
0x18003cf8d  mov     edx, 1
0x18003cf92  mov     rax, [rax+68h]
0x18003cf96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf9b  test    eax, eax
0x18003cf9d  js      loc_18003D28D
0x18003cfa3  mov     [rsp+1B0h+var_150], r13d
0x18003cfa8  mov     rcx, [rsp+1B0h+var_148]
0x18003cfad  mov     rax, [rcx]
0x18003cfb0  lea     r9, [rsp+1B0h+var_150]
0x18003cfb5  mov     r8d, 40h ; '@'
0x18003cfbb  lea     rdx, [rbp+0B0h+var_D0]
0x18003cfbf  mov     rax, [rax+18h]
0x18003cfc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfc8  test    eax, eax
0x18003cfca  js      loc_18003D28D
0x18003cfd0  cmp     [rsp+1B0h+var_150], r13d
0x18003cfd5  jz      loc_18003D237
0x18003cfdb  mov     r8, [rsp+1B0h+SourceString]
0x18003cfe0  test    r8, r8
0x18003cfe3  jnz     loc_18003D1FE
0x18003cfe9  mov     [rbp+0B0h+var_130], r13
0x18003cfed  mov     [rsp+1B0h+var_138], r13
0x18003cff2  mov     [rsp+1B0h+var_140], r13
0x18003cff7  xor     edx, edx; Val
0x18003cff9  lea     r8d, [rdx+48h]; Size
0x18003cffd  lea     rcx, [rbp+0B0h+var_90]; void *
0x18003d001  call    memset_0
0x18003d006  xorps   xmm0, xmm0
0x18003d009  xor     eax, eax
0x18003d00b  movups  xmmword ptr [rbp+0B0h+propvar], xmm0
0x18003d00f  mov     [rbp+0B0h+var_E8], rax
0x18003d013  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x18003d017  mov     [rbp+0B0h+var_100], r13
0x18003d01b  mov     rax, [r14]
0x18003d01e  lea     r8, [rbp+0B0h+var_130]
0x18003d022  xor     edx, edx
0x18003d024  mov     rcx, r14
0x18003d027  mov     rax, [rax+20h]
0x18003d02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d030  test    eax, eax
0x18003d032  js      loc_18003D262
0x18003d038  mov     rcx, [rbp+0B0h+var_130]
0x18003d03c  mov     rax, [rcx]
0x18003d03f  lea     r8, [rbp+0B0h+propvar]
0x18003d043  lea     rdx, PKEY_Device_InstanceId
0x18003d04a  mov     rax, [rax+28h]
0x18003d04e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d053  test    eax, eax
0x18003d055  js      loc_18003D262
0x18003d05b  lea     rdx, [rbp+0B0h+ppszOut]; ppszOut
0x18003d05f  lea     rcx, [rbp+0B0h+propvar]; propvar
0x18003d063  call    cs:__imp_PropVariantToStringAlloc
0x18003d069  test    eax, eax
0x18003d06b  js      loc_18003D262
0x18003d071  mov     rax, [r14]
0x18003d074  lea     r8, [rsp+1B0h+var_138]
0x18003d079  lea     rdx, _GUID_3ade56af_4375_4413_9c91_4c652595ab07
0x18003d080  mov     rcx, r14
0x18003d083  mov     rax, [rax]
0x18003d086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d08b  test    eax, eax
0x18003d08d  js      loc_18003D262
0x18003d093  mov     rcx, [rsp+1B0h+var_138]
0x18003d098  mov     rax, [rcx]
0x18003d09b  lea     rdx, [rsp+1B0h+SourceString]
0x18003d0a0  mov     rax, [rax+20h]
0x18003d0a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0a9  test    eax, eax
0x18003d0ab  js      loc_18003D262
0x18003d0b1  mov     rdx, [rsp+1B0h+SourceString]; SourceString
0x18003d0b6  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x18003d0ba  call    cs:__imp_RtlInitUnicodeString
0x18003d0c0  lea     r9, [rsp+1B0h+HashValue]; HashValue
0x18003d0c5  xor     r8d, r8d; HashAlgorithm
0x18003d0c8  mov     dl, 1; CaseInSensitive
0x18003d0ca  lea     rcx, [rbp+0B0h+DestinationString]; String
0x18003d0ce  call    cs:__imp_RtlHashUnicodeString
0x18003d0d4  mov     ecx, eax; Status
0x18003d0d6  call    cs:__imp_RtlNtStatusToDosError
0x18003d0dc  test    eax, eax
0x18003d0de  jle     short loc_18003D0EA
0x18003d0e0  movzx   eax, ax
0x18003d0e3  or      eax, 80070000h
0x18003d0e8  test    eax, eax
0x18003d0ea  js      loc_18003D262
0x18003d0f0  mov     rax, [r14]
0x18003d0f3  lea     rcx, [rsp+1B0h+var_140]
0x18003d0f8  mov     [rsp+1B0h+var_190], rcx
0x18003d0fd  xor     r9d, r9d
0x18003d100  lea     r8d, [r9+17h]
0x18003d104  lea     rdx, _GUID_1136a91a_2bef_45b3_91d9_0a58472ee8a7
0x18003d10b  mov     rcx, r14
0x18003d10e  mov     rax, [rax+18h]
0x18003d112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d117  test    eax, eax
0x18003d119  js      loc_18003D1CF
0x18003d11f  mov     rcx, [rsp+1B0h+var_140]
0x18003d124  mov     rax, [rcx]
0x18003d127  lea     rdx, [rbp+0B0h+var_90]
0x18003d12b  mov     rax, [rax+18h]
0x18003d12f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d134  test    eax, eax
0x18003d136  js      loc_18003D1CF
0x18003d13c  mov     r8d, 10h; Size
0x18003d142  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x18003d149  lea     rcx, [rbp+0B0h+Buf1]; Buf1
0x18003d14d  call    memcmp_0
0x18003d152  test    eax, eax
0x18003d154  jz      short loc_18003D1CF
0x18003d156  mov     [rbp+0B0h+var_110], r13
0x18003d15a  lea     r8, [rbp+0B0h+var_110]; unsigned __int16 **
0x18003d15e  lea     rdx, [rbp+0B0h+Buf1]; struct _GUID *
0x18003d162  call    ?ReadProductNameFromMediaCategories@CMidiBuilder@@AEAAJAEBU_GUID@@PEAPEAG@Z; CMidiBuilder::ReadProductNameFromMediaCategories(_GUID const &,ushort * *)
0x18003d167  test    eax, eax
0x18003d169  js      short loc_18003D1CF
0x18003d16b  lea     r8, [rbp+0B0h+var_100]; unsigned __int64 *
0x18003d16f  mov     r11d, 7FFFFFFFh
0x18003d175  mov     edx, r11d; unsigned __int64
0x18003d178  mov     rcx, [rbp+0B0h+var_110]; unsigned __int16 *
0x18003d17c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003d181  cmp     eax, 80070057h
0x18003d186  jnz     short loc_18003D18D
0x18003d188  mov     ebx, r11d
0x18003d18b  jmp     short loc_18003D199
0x18003d18d  test    eax, eax
0x18003d18f  js      loc_18003D262
0x18003d195  mov     rbx, [rbp+0B0h+var_100]
0x18003d199  inc     rbx
0x18003d19c  lea     rdx, [rbx+rbx]
0x18003d1a0  lea     rcx, [rbp+0B0h+var_108]
0x18003d1a4  call    ?AllocateBytes@?$CHeapPtrBase@GVCComAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<ushort,ATL::CComAllocator>::AllocateBytes(unsigned __int64)
0x18003d1a9  test    al, al
0x18003d1ab  jz      loc_18003D25E
0x18003d1b1  mov     r9, rbx; unsigned __int64
0x18003d1b4  mov     r8, [rbp+0B0h+var_110]; unsigned __int16 *
0x18003d1b8  mov     rdx, rbx; unsigned __int64
0x18003d1bb  mov     rbx, [rbp+0B0h+var_108]
0x18003d1bf  mov     rcx, rbx; unsigned __int16 *
0x18003d1c2  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18003d1c7  test    eax, eax
0x18003d1c9  js      loc_18003D262
0x18003d1cf  lea     rcx, [rbp+0B0h+propvar]; pvar
0x18003d1d3  call    cs:__imp_PropVariantClear
0x18003d1d9  nop
0x18003d1da  lea     rcx, [rsp+1B0h+var_140]
0x18003d1df  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d1e4  nop
0x18003d1e5  lea     rcx, [rsp+1B0h+var_138]
0x18003d1ea  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d1ef  nop
0x18003d1f0  lea     rcx, [rbp+0B0h+var_130]
0x18003d1f4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d1f9  mov     r8, [rsp+1B0h+SourceString]; unsigned __int16 *
0x18003d1fe  mov     dil, 1
0x18003d201  mov     rax, r12
0x18003d204  test    rbx, rbx
0x18003d207  cmovnz  rax, rbx
0x18003d20b  lea     rcx, [rbp+0B0h+var_118]; this
0x18003d20f  mov     [rsp+1B0h+var_178], rcx; unsigned int *
0x18003d214  mov     [rsp+1B0h+var_180], rax; unsigned __int16 *
0x18003d219  mov     [rsp+1B0h+var_188], r15d; unsigned int
0x18003d21e  mov     rax, [rbp+0B0h+ppszOut]
0x18003d222  mov     [rsp+1B0h+var_190], rax; unsigned __int16 *
0x18003d227  mov     r9d, [rsp+1B0h+HashValue]; unsigned int
0x18003d22c  mov     rdx, [rsp+1B0h+var_168]; struct IPart *
0x18003d231  call    ?CreateMidiPortForKsPin@CMidiBuilder@@AEAAXPEAUIPart@@PEBGK1I1PEAI@Z; CMidiBuilder::CreateMidiPortForKsPin(IPart *,ushort const *,ulong,ushort const *,uint,ushort const *,uint *)
0x18003d236  nop
0x18003d237  lea     rcx, [rsp+1B0h+var_148]
0x18003d23c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d241  nop
0x18003d242  lea     rcx, [rsp+1B0h+var_168]
0x18003d247  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d24c  nop
0x18003d24d  lea     rcx, [rsp+1B0h+var_170]
0x18003d252  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d257  inc     esi
0x18003d259  jmp     loc_18003CF04
0x18003d25e  mov     rbx, [rbp+0B0h+var_108]
0x18003d262  lea     rcx, [rbp+0B0h+propvar]; pvar
0x18003d266  call    cs:__imp_PropVariantClear
0x18003d26c  nop
0x18003d26d  lea     rcx, [rsp+1B0h+var_140]
0x18003d272  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d277  nop
0x18003d278  lea     rcx, [rsp+1B0h+var_138]
0x18003d27d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d282  nop
0x18003d283  lea     rcx, [rbp+0B0h+var_130]
0x18003d287  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d28c  nop
0x18003d28d  lea     rcx, [rsp+1B0h+var_148]
0x18003d292  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d297  nop
0x18003d298  lea     rcx, [rsp+1B0h+var_168]
0x18003d29d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d2a2  nop
0x18003d2a3  lea     rcx, [rsp+1B0h+var_170]
0x18003d2a8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d2ad  mov     dil, r13b
0x18003d2b0  mov     rcx, rbx; pv
0x18003d2b3  call    cs:__imp_CoTaskMemFree
0x18003d2b9  nop
0x18003d2ba  mov     rcx, [rbp+0B0h+ppszOut]; pv
0x18003d2be  call    cs:__imp_CoTaskMemFree
0x18003d2c4  mov     [rbp+0B0h+ppszOut], r13
0x18003d2c8  mov     rcx, [rsp+1B0h+SourceString]; pv
0x18003d2cd  call    cs:__imp_CoTaskMemFree
0x18003d2d3  mov     [rsp+1B0h+SourceString], r13
0x18003d2d8  lea     rcx, [rbp+0B0h+var_120]
0x18003d2dc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d2e1  mov     al, dil
0x18003d2e4  mov     rcx, [rbp+0B0h+var_40]
0x18003d2e8  xor     rcx, rsp; StackCookie
0x18003d2eb  call    __security_check_cookie
0x18003d2f0  mov     rbx, [rsp+1B0h+arg_0]
0x18003d2f8  add     rsp, 180h
  ... truncated ...
```
