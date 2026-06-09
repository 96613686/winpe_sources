# CreateMidiPortsForKsFilter(IMMDevice *,ulong,ushort const *)

- ea: `0x1800381a8`
- end: `0x180038684`
- name: `?CreateMidiPortsForKsFilter@@YA_NPEAUIMMDevice@@KPEBG@Z`
- size: `1244`
- prototype: `char __fastcall(struct IMMDevice *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180049b30`

## callees

- `0x180006b0c`
- `0x180024208`
- `0x180025f5c`
- `0x1800328d4`
- `0x1800351f0`
- `0x1800381a8`
- `0x18003868c`
- `0x18003e920`
- `0x18003f780`
- `0x18003f7a4`
- `0x180049040`
- `0x180068010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180038438`
- `ntdll!RtlInitUnicodeString` at `0x180038438`
- `ntdll!RtlNtStatusToDosError` at `0x180038454`
- `ntdll!RtlNtStatusToDosError` at `0x180038454`
- `ntdll!RtlHashUnicodeString` at `0x18003844c`
- `ntdll!RtlHashUnicodeString` at `0x18003844c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180038551`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800385df`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180038551`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800385df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003862c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038637`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038646`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003862c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038637`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038646`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800383e1`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800383e1`

## pseudocode

```c
char __fastcall CreateMidiPortsForKsFilter(struct IMMDevice *a1, unsigned int a2, const unsigned __int16 *a3)
{
  unsigned __int16 *v6; // rbx
  char v7; // di
  unsigned int i; // esi
  const unsigned __int16 *v9; // rdx
  NTSTATUS v10; // eax
  signed int v11; // eax
  bool v12; // sf
  int v13; // eax
  unsigned int v14; // r11d
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // r9
  unsigned __int64 v18; // rdx
  const unsigned __int16 *v19; // rax
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v22; // [rsp+48h] [rbp-B8h] BYREF
  int Val[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v24; // [rsp+58h] [rbp-A8h] BYREF
  int v25; // [rsp+5Ch] [rbp-A4h] BYREF
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  ULONG HashValue; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  __int64 v31; // [rsp+80h] [rbp-80h] BYREF
  PWSTR ppszOut; // [rsp+88h] [rbp-78h] BYREF
  __int64 v33; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v34; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v35; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v36; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v37; // [rsp+B0h] [rbp-50h] BYREF
  PROPVARIANT propvar[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v39; // [rsp+C8h] [rbp-38h]
  _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-30h] BYREF
  int v41; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v42; // [rsp+E4h] [rbp-1Ch]
  int v43; // [rsp+ECh] [rbp-14h]
  GUID v44; // [rsp+F0h] [rbp-10h]
  GUID v45; // [rsp+100h] [rbp+0h]
  GUID v46; // [rsp+110h] [rbp+10h]
  _BYTE v47[48]; // [rsp+120h] [rbp+20h] BYREF
  IID Buf1[2]; // [rsp+150h] [rbp+50h] BYREF

  v33 = 0;
  v24 = 0;
  *(_QWORD *)Val = 0;
  ppszOut = 0;
  v6 = 0;
  v36 = 0;
  HashValue = 0;
  v42 = 0;
  v43 = 0;
  v41 = 64;
  v44 = GUID_e725d360_62cc_11cf_a5d6_28db04c10000;
  v45 = GUID_1d262760_e957_11cf_a5d6_28db04c10000;
  v46 = GUID_0f6417d6_c318_11d0_a43f_00a0c9223196;
  if ( ((int (__fastcall *)(struct IMMDevice *, GUID *, __int64, _QWORD, __int64 *))a1->lpVtbl->Activate)(
         a1,
         &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
         1,
         0,
         &v33) < 0
    || (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 24LL))(v33, &v24) < 0 )
  {
LABEL_40:
    v7 = 0;
  }
  else
  {
    v7 = 0;
    v34 = 0;
    for ( i = 0; i < v24; ++i )
    {
      v21 = 0;
      v25 = 0;
      if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 32LL))(v33, i, &v21) < 0
        || (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 24LL))(v21, &v25) < 0 )
      {
        goto LABEL_39;
      }
      if ( v25 == 3 )
      {
        v22 = 0;
        ATL::CComPtr<IPart>::operator=<IConnector>(&v22);
        v28 = 0;
        if ( ((int (__fastcall *)(struct IUnknown *, __int64, GUID *, __int64 *))v22->lpVtbl[4].AddRef)(
               v22,
               1,
               &GUID_3cb4a69d_bb6f_4d2b_95b7_452d2c155db5,
               &v28) < 0 )
          goto LABEL_38;
        v26 = 0;
        if ( (*(int (__fastcall **)(__int64, int *, __int64, int *))(*(_QWORD *)v28 + 24LL))(v28, &v41, 64, &v26) < 0 )
          goto LABEL_38;
        if ( v26 )
        {
          v9 = *(const unsigned __int16 **)Val;
          if ( !*(_QWORD *)Val )
          {
            v31 = 0;
            v30 = 0;
            v29 = 0;
            memset_0(v47, 0, 0x48u);
            *(_OWORD *)propvar = 0;
            v39 = 0;
            DestinationString = 0;
            v37 = 0;
            if ( ((int (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))a1->lpVtbl->OpenPropertyStore)(a1, 0, &v31) < 0
              || (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v31 + 40LL))(
                   v31,
                   &PKEY_Device_InstanceId,
                   propvar) < 0
              || PropVariantToStringAlloc(propvar, &ppszOut) < 0
              || ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
                   a1,
                   &GUID_3ade56af_4375_4413_9c91_4c652595ab07,
                   &v30) < 0
              || (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 32LL))(v30, Val) < 0 )
            {
              goto LABEL_37;
            }
            RtlInitUnicodeString(&DestinationString, *(PCWSTR *)Val);
            v10 = RtlHashUnicodeString(&DestinationString, 1u, 0, &HashValue);
            v11 = RtlNtStatusToDosError(v10);
            v12 = v11 < 0;
            if ( v11 > 0 )
              v12 = 1;
            if ( v12 )
              goto LABEL_37;
            if ( ((int (__fastcall *)(struct IMMDevice *, GUID *, __int64))a1->lpVtbl->Activate)(
                   a1,
                   &GUID_1136a91a_2bef_45b3_91d9_0a58472ee8a7,
                   23) >= 0
              && (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v29 + 24LL))(v29, v47) >= 0 )
            {
              if ( memcmp_0(Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
              {
                v35 = 0;
                if ( (int)ReadProductNameFromMediaCategories(Buf1, &v35) >= 0 )
                {
                  v13 = StringCchLengthW(v35, 0x7FFFFFFFu, &v37);
                  if ( v13 == -2147024809 )
                  {
                    v15 = v14;
                  }
                  else
                  {
                    if ( v13 < 0 )
                      goto LABEL_37;
                    v15 = v37;
                  }
                  v16 = v15 + 1;
                  if ( !(unsigned __int8)ATL::CHeapPtrBase<unsigned short,ATL::CComAllocator>::AllocateBytes(
                                           &v36,
                                           2 * v16) )
                  {
                    v6 = v36;
LABEL_37:
                    PropVariantClear(propvar);
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
LABEL_38:
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
LABEL_39:
                    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
                    goto LABEL_40;
                  }
                  v17 = v16;
                  v18 = v16;
                  v6 = v36;
                  if ( (int)StringCchCopyNW(v36, v18, v35, v17) < 0 )
                    goto LABEL_37;
                }
              }
            }
            PropVariantClear(propvar);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
            v9 = *(const unsigned __int16 **)Val;
          }
          v7 = 1;
          v19 = a3;
          if ( v6 )
            v19 = v6;
          CreateMidiPortForKsPin((struct IPart *)v22, v9, HashValue, ppszOut, a2, v19, &v34);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
    }
  }
  CoTaskMemFree(v6);
  CoTaskMemFree(ppszOut);
  ppszOut = 0;
  CoTaskMemFree(*(LPVOID *)Val);
  *(_QWORD *)Val = 0;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
  return v7;
}

```

## disassembly

```asm
0x1800381a8  mov     [rsp-8+arg_8], rbx
0x1800381ad  push    rbp
0x1800381ae  push    rsi
0x1800381af  push    rdi
0x1800381b0  push    r12
0x1800381b2  push    r13
0x1800381b4  push    r14
0x1800381b6  push    r15
0x1800381b8  lea     rbp, [rsp-80h]
0x1800381bd  sub     rsp, 180h
0x1800381c4  mov     rax, cs:__security_cookie
0x1800381cb  xor     rax, rsp
0x1800381ce  mov     [rbp+0B0h+var_40], rax
0x1800381d2  mov     r12, r8
0x1800381d5  mov     r15d, edx
0x1800381d8  mov     r14, rcx
0x1800381db  xor     r13d, r13d
0x1800381de  mov     [rbp+0B0h+var_120], r13
0x1800381e2  mov     [rsp+1B0h+var_158], r13d
0x1800381e7  mov     qword ptr [rsp+1B0h+Val], r13
0x1800381ec  mov     [rbp+0B0h+ppszOut], r13
0x1800381f0  mov     ebx, r13d
0x1800381f3  mov     [rbp+0B0h+var_108], rbx
0x1800381f7  mov     [rsp+1B0h+HashValue], r13d
0x1800381fc  mov     [rbp+0B0h+var_CC], r13
0x180038200  mov     [rbp+0B0h+var_C4], r13d
0x180038204  mov     [rbp+0B0h+var_D0], 40h ; '@'
0x18003820b  movups  xmm0, xmmword ptr cs:_GUID_e725d360_62cc_11cf_a5d6_28db04c10000.Data1
0x180038212  movdqu  [rbp+0B0h+var_C0], xmm0
0x180038217  movups  xmm1, xmmword ptr cs:_GUID_1d262760_e957_11cf_a5d6_28db04c10000.Data1
0x18003821e  movdqu  [rbp+0B0h+var_B0], xmm1
0x180038223  movups  xmm0, xmmword ptr cs:_GUID_0f6417d6_c318_11d0_a43f_00a0c9223196.Data1
0x18003822a  movdqu  [rbp+0B0h+var_A0], xmm0
0x18003822f  mov     rax, [rcx]
0x180038232  lea     rcx, [rbp+0B0h+var_120]
0x180038236  mov     qword ptr [rsp+1B0h+var_190], rcx
0x18003823b  xor     r9d, r9d
0x18003823e  lea     r8d, [r13+1]
0x180038242  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x180038249  mov     rcx, r14
0x18003824c  mov     rax, [rax+18h]
0x180038250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038255  test    eax, eax
0x180038257  js      loc_180038626
0x18003825d  mov     rcx, [rbp+0B0h+var_120]
0x180038261  mov     rax, [rcx]
0x180038264  lea     rdx, [rsp+1B0h+var_158]
0x180038269  mov     rax, [rax+18h]
0x18003826d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038272  test    eax, eax
0x180038274  js      loc_180038626
0x18003827a  mov     dil, r13b
0x18003827d  mov     [rbp+0B0h+var_118], r13d
0x180038281  mov     esi, r13d
0x180038284  cmp     esi, [rsp+1B0h+var_158]
0x180038288  jnb     loc_180038629
0x18003828e  mov     [rsp+1B0h+var_170], r13
0x180038293  mov     [rsp+1B0h+var_154], r13d
0x180038298  mov     rcx, [rbp+0B0h+var_120]
0x18003829c  mov     rax, [rcx]
0x18003829f  lea     r8, [rsp+1B0h+var_170]
0x1800382a4  mov     edx, esi
0x1800382a6  mov     rax, [rax+20h]
0x1800382aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382af  test    eax, eax
0x1800382b1  js      loc_18003861C
0x1800382b7  mov     rcx, [rsp+1B0h+var_170]
0x1800382bc  mov     rax, [rcx]
0x1800382bf  lea     rdx, [rsp+1B0h+var_154]
0x1800382c4  mov     rax, [rax+18h]
0x1800382c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382cd  test    eax, eax
0x1800382cf  js      loc_18003861C
0x1800382d5  cmp     [rsp+1B0h+var_154], 3
0x1800382da  jnz     loc_1800385C6
0x1800382e0  mov     [rsp+1B0h+var_168], r13
0x1800382e5  lea     rdx, [rsp+1B0h+var_170]
0x1800382ea  lea     rcx, [rsp+1B0h+var_168]; struct IUnknown **
0x1800382ef  call    ??$?4UIConnector@@@?$CComPtr@UIPart@@@ATL@@QEAAPEAUIPart@@AEBV?$CComPtr@UIConnector@@@1@@Z; ATL::CComPtr<IPart>::operator=<IConnector>(ATL::CComPtr<IConnector> const &)
0x1800382f4  mov     [rsp+1B0h+var_148], r13
0x1800382f9  mov     rcx, [rsp+1B0h+var_168]
0x1800382fe  mov     rax, [rcx]
0x180038301  lea     r9, [rsp+1B0h+var_148]
0x180038306  lea     r8, _GUID_3cb4a69d_bb6f_4d2b_95b7_452d2c155db5
0x18003830d  mov     edx, 1
0x180038312  mov     rax, [rax+68h]
0x180038316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003831b  test    eax, eax
0x18003831d  js      loc_180038606
0x180038323  mov     [rsp+1B0h+var_150], r13d
0x180038328  mov     rcx, [rsp+1B0h+var_148]
0x18003832d  mov     rax, [rcx]
0x180038330  lea     r9, [rsp+1B0h+var_150]
0x180038335  mov     r8d, 40h ; '@'
0x18003833b  lea     rdx, [rbp+0B0h+var_D0]
0x18003833f  mov     rax, [rax+18h]
0x180038343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038348  test    eax, eax
0x18003834a  js      loc_180038606
0x180038350  cmp     [rsp+1B0h+var_150], r13d
0x180038355  jz      loc_1800385B0
0x18003835b  mov     rdx, qword ptr [rsp+1B0h+Val]; Val
0x180038360  test    rdx, rdx
0x180038363  jnz     loc_18003857C
0x180038369  mov     [rbp+0B0h+var_130], r13
0x18003836d  mov     [rsp+1B0h+var_138], r13
0x180038372  mov     [rsp+1B0h+var_140], r13
0x180038377  lea     r8d, [rdx+48h]; Size
0x18003837b  lea     rcx, [rbp+0B0h+var_90]; void *
0x18003837f  call    memset_0
0x180038384  xorps   xmm0, xmm0
0x180038387  xor     eax, eax
0x180038389  movups  xmmword ptr [rbp+0B0h+propvar], xmm0
0x18003838d  mov     [rbp+0B0h+var_E8], rax
0x180038391  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x180038395  mov     [rbp+0B0h+var_100], r13
0x180038399  mov     rax, [r14]
0x18003839c  lea     r8, [rbp+0B0h+var_130]
0x1800383a0  xor     edx, edx
0x1800383a2  mov     rcx, r14
0x1800383a5  mov     rax, [rax+20h]
0x1800383a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383ae  test    eax, eax
0x1800383b0  js      loc_1800385DB
0x1800383b6  mov     rcx, [rbp+0B0h+var_130]
0x1800383ba  mov     rax, [rcx]
0x1800383bd  lea     r8, [rbp+0B0h+propvar]
0x1800383c1  lea     rdx, PKEY_Device_InstanceId
0x1800383c8  mov     rax, [rax+28h]
0x1800383cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383d1  test    eax, eax
0x1800383d3  js      loc_1800385DB
0x1800383d9  lea     rdx, [rbp+0B0h+ppszOut]; ppszOut
0x1800383dd  lea     rcx, [rbp+0B0h+propvar]; propvar
0x1800383e1  call    cs:__imp_PropVariantToStringAlloc
0x1800383e7  test    eax, eax
0x1800383e9  js      loc_1800385DB
0x1800383ef  mov     rax, [r14]
0x1800383f2  lea     r8, [rsp+1B0h+var_138]
0x1800383f7  lea     rdx, _GUID_3ade56af_4375_4413_9c91_4c652595ab07
0x1800383fe  mov     rcx, r14
0x180038401  mov     rax, [rax]
0x180038404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038409  test    eax, eax
0x18003840b  js      loc_1800385DB
0x180038411  mov     rcx, [rsp+1B0h+var_138]
0x180038416  mov     rax, [rcx]
0x180038419  lea     rdx, [rsp+1B0h+Val]
0x18003841e  mov     rax, [rax+20h]
0x180038422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038427  test    eax, eax
0x180038429  js      loc_1800385DB
0x18003842f  mov     rdx, qword ptr [rsp+1B0h+Val]; SourceString
0x180038434  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x180038438  call    cs:__imp_RtlInitUnicodeString
0x18003843e  lea     r9, [rsp+1B0h+HashValue]; HashValue
0x180038443  xor     r8d, r8d; HashAlgorithm
0x180038446  mov     dl, 1; CaseInSensitive
0x180038448  lea     rcx, [rbp+0B0h+DestinationString]; String
0x18003844c  call    cs:__imp_RtlHashUnicodeString
0x180038452  mov     ecx, eax; Status
0x180038454  call    cs:__imp_RtlNtStatusToDosError
0x18003845a  test    eax, eax
0x18003845c  jle     short loc_180038468
0x18003845e  movzx   eax, ax
0x180038461  or      eax, 80070000h
0x180038466  test    eax, eax
0x180038468  js      loc_1800385DB
0x18003846e  mov     rax, [r14]
0x180038471  lea     rcx, [rsp+1B0h+var_140]
0x180038476  mov     qword ptr [rsp+1B0h+var_190], rcx
0x18003847b  xor     r9d, r9d
0x18003847e  lea     r8d, [r9+17h]
0x180038482  lea     rdx, _GUID_1136a91a_2bef_45b3_91d9_0a58472ee8a7
0x180038489  mov     rcx, r14
0x18003848c  mov     rax, [rax+18h]
0x180038490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038495  test    eax, eax
0x180038497  js      loc_18003854D
0x18003849d  mov     rcx, [rsp+1B0h+var_140]
0x1800384a2  mov     rax, [rcx]
0x1800384a5  lea     rdx, [rbp+0B0h+var_90]
0x1800384a9  mov     rax, [rax+18h]
0x1800384ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384b2  test    eax, eax
0x1800384b4  js      loc_18003854D
0x1800384ba  mov     r8d, 10h; Size
0x1800384c0  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x1800384c7  lea     rcx, [rbp+0B0h+Buf1]; Buf1
0x1800384cb  call    memcmp_0
0x1800384d0  test    eax, eax
0x1800384d2  jz      short loc_18003854D
0x1800384d4  mov     [rbp+0B0h+var_110], r13
0x1800384d8  lea     rdx, [rbp+0B0h+var_110]; unsigned __int16 **
0x1800384dc  lea     rcx, [rbp+0B0h+Buf1]; rclsid
0x1800384e0  call    ?ReadProductNameFromMediaCategories@@YAJAEBU_GUID@@PEAPEAG@Z; ReadProductNameFromMediaCategories(_GUID const &,ushort * *)
0x1800384e5  test    eax, eax
0x1800384e7  js      short loc_18003854D
0x1800384e9  lea     r8, [rbp+0B0h+var_100]; unsigned __int64 *
0x1800384ed  mov     r11d, 7FFFFFFFh
0x1800384f3  mov     edx, r11d; unsigned __int64
0x1800384f6  mov     rcx, [rbp+0B0h+var_110]; unsigned __int16 *
0x1800384fa  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800384ff  cmp     eax, 80070057h
0x180038504  jnz     short loc_18003850B
0x180038506  mov     ebx, r11d
0x180038509  jmp     short loc_180038517
0x18003850b  test    eax, eax
0x18003850d  js      loc_1800385DB
0x180038513  mov     rbx, [rbp+0B0h+var_100]
0x180038517  inc     rbx
0x18003851a  lea     rdx, [rbx+rbx]
0x18003851e  lea     rcx, [rbp+0B0h+var_108]
0x180038522  call    ?AllocateBytes@?$CHeapPtrBase@GVCComAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<ushort,ATL::CComAllocator>::AllocateBytes(unsigned __int64)
0x180038527  test    al, al
0x180038529  jz      loc_1800385D7
0x18003852f  mov     r9, rbx; unsigned __int64
0x180038532  mov     r8, [rbp+0B0h+var_110]; unsigned __int16 *
0x180038536  mov     rdx, rbx; unsigned __int64
0x180038539  mov     rbx, [rbp+0B0h+var_108]
0x18003853d  mov     rcx, rbx; unsigned __int16 *
0x180038540  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180038545  test    eax, eax
0x180038547  js      loc_1800385DB
0x18003854d  lea     rcx, [rbp+0B0h+propvar]; pvar
0x180038551  call    cs:__imp_PropVariantClear
0x180038557  nop
0x180038558  lea     rcx, [rsp+1B0h+var_140]
0x18003855d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180038562  nop
0x180038563  lea     rcx, [rsp+1B0h+var_138]
0x180038568  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003856d  nop
0x18003856e  lea     rcx, [rbp+0B0h+var_130]
0x180038572  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180038577  mov     rdx, qword ptr [rsp+1B0h+Val]; unsigned __int16 *
0x18003857c  mov     dil, 1
0x18003857f  mov     rax, r12
0x180038582  test    rbx, rbx
0x180038585  cmovnz  rax, rbx
0x180038589  lea     rcx, [rbp+0B0h+var_118]
0x18003858d  mov     [rsp+1B0h+var_180], rcx; unsigned int *
0x180038592  mov     [rsp+1B0h+var_188], rax; unsigned __int16 *
0x180038597  mov     [rsp+1B0h+var_190], r15d; unsigned int
0x18003859c  mov     r9, [rbp+0B0h+ppszOut]; unsigned __int16 *
0x1800385a0  mov     r8d, [rsp+1B0h+HashValue]; unsigned int
0x1800385a5  mov     rcx, [rsp+1B0h+var_168]; struct IPart *
0x1800385aa  call    ?CreateMidiPortForKsPin@@YAXPEAUIPart@@PEBGK1I1PEAI@Z; CreateMidiPortForKsPin(IPart *,ushort const *,ulong,ushort const *,uint,ushort const *,uint *)
0x1800385af  nop
0x1800385b0  lea     rcx, [rsp+1B0h+var_148]
0x1800385b5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800385ba  nop
0x1800385bb  lea     rcx, [rsp+1B0h+var_168]
0x1800385c0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800385c5  nop
0x1800385c6  lea     rcx, [rsp+1B0h+var_170]
0x1800385cb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800385d0  inc     esi
0x1800385d2  jmp     loc_180038284
0x1800385d7  mov     rbx, [rbp+0B0h+var_108]
0x1800385db  lea     rcx, [rbp+0B0h+propvar]; pvar
0x1800385df  call    cs:__imp_PropVariantClear
0x1800385e5  nop
0x1800385e6  lea     rcx, [rsp+1B0h+var_140]
0x1800385eb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800385f0  nop
0x1800385f1  lea     rcx, [rsp+1B0h+var_138]
0x1800385f6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800385fb  nop
0x1800385fc  lea     rcx, [rbp+0B0h+var_130]
0x180038600  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180038605  nop
0x180038606  lea     rcx, [rsp+1B0h+var_148]
0x18003860b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180038610  nop
0x180038611  lea     rcx, [rsp+1B0h+var_168]
0x180038616  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003861b  nop
0x18003861c  lea     rcx, [rsp+1B0h+var_170]
0x180038621  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180038626  mov     dil, r13b
0x180038629  mov     rcx, rbx; pv
0x18003862c  call    cs:__imp_CoTaskMemFree
0x180038632  nop
0x180038633  mov     rcx, [rbp+0B0h+ppszOut]; pv
0x180038637  call    cs:__imp_CoTaskMemFree
0x18003863d  mov     [rbp+0B0h+ppszOut], r13
0x180038641  mov     rcx, qword ptr [rsp+1B0h+Val]; pv
0x180038646  call    cs:__imp_CoTaskMemFree
0x18003864c  mov     qword ptr [rsp+1B0h+Val], r13
0x180038651  lea     rcx, [rbp+0B0h+var_120]
0x180038655  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003865a  mov     al, dil
0x18003865d  mov     rcx, [rbp+0B0h+var_40]
0x180038661  xor     rcx, rsp; StackCookie
0x180038664  call    __security_check_cookie
0x180038669  mov     rbx, [rsp+1B0h+arg_8]
0x180038671  add     rsp, 180h
0x180038678  pop     r15
0x18003867a  pop     r14
  ... truncated ...
```
