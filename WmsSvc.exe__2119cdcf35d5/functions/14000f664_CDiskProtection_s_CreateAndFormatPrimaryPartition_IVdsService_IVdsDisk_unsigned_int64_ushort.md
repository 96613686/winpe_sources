# CDiskProtection::s_CreateAndFormatPrimaryPartition(IVdsService *,IVdsDisk *,unsigned __int64,ushort)

- ea: `0x14000f664`
- end: `0x14000fb7b`
- name: `?s_CreateAndFormatPrimaryPartition@CDiskProtection@@KAJPEAUIVdsService@@PEAUIVdsDisk@@_KG@Z`
- size: `1303`
- prototype: `__int64 __fastcall(struct IVdsService *, struct IVdsDisk *, unsigned __int64, unsigned __int16)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x140012eb4`

## callees

- `0x14000e6b0`
- `0x14000f664`
- `0x140010ef0`
- `0x140011d3c`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14000f7b3`
- `KERNEL32!IsDebuggerPresent` at `0x14000f967`
- `KERNEL32!IsDebuggerPresent` at `0x14000f9da`
- `KERNEL32!IsDebuggerPresent` at `0x14000f7b3`
- `KERNEL32!IsDebuggerPresent` at `0x14000f967`
- `KERNEL32!IsDebuggerPresent` at `0x14000f9da`
- `ole32!CoTaskMemFree` at `0x14000faab`
- `ole32!CoTaskMemFree` at `0x14000fab8`
- `ole32!CoTaskMemFree` at `0x14000fac5`
- `ole32!CoTaskMemFree` at `0x14000fad2`
- `ole32!CoTaskMemFree` at `0x14000fadf`
- `ole32!CoTaskMemFree` at `0x14000faab`
- `ole32!CoTaskMemFree` at `0x14000fab8`
- `ole32!CoTaskMemFree` at `0x14000fac5`
- `ole32!CoTaskMemFree` at `0x14000fad2`
- `ole32!CoTaskMemFree` at `0x14000fadf`

## string_xrefs

- `0x14000f706`: `CDiskProtection::s_CreateAndFormatPrimaryPartition - cbSize = %I64u GB (%I64u bytes)\n`
- `0x14000f77d`: `CDiskProtection::s_CreateAndFormatPrimaryPartition`
- `0x14000f936`: `CDiskProtection::s_CreateAndFormatPrimaryPartition`
- `0x14000f9a5`: `CDiskProtection::s_CreateAndFormatPrimaryPartition`
- `0x14000f8d9`: `CDiskProtection::s_CreateAndFormatPrimaryPartition - About to call pAsync->Wait.\n`
- `0x14000f904`: `CDiskProtection::s_CreateAndFormatPrimaryPartition - pAsync->Wait has returned, hr = 0x%08x, hrAsync = 0x%08x.\n`
- `0x14000f9bd`: `sAsyncOutput.type == VDS_ASYNCOUT_CREATEPARTITION`
- `0x14000fa14`: `CDiskProtection::s_CreateAndFormatPrimaryPartition - Created a partition at offset %I64u\n`

## pseudocode

```c
__int64 __fastcall CDiskProtection::s_CreateAndFormatPrimaryPartition(
        struct IVdsService *a1,
        struct IVdsDisk *a2,
        unsigned __int64 a3,
        unsigned __int16 a4)
{
  __int64 v8; // rbx
  unsigned int v9; // r12d
  __int64 v10; // r9
  __int64 v11; // r8
  HRESULT (__stdcall *GetObjectA)(IVdsService *, VDS_OBJECT_ID, VDS_OBJECT_TYPE, IUnknown **); // rax
  const unsigned __int16 *v14; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v15; // [rsp+30h] [rbp-D0h]
  int v16; // [rsp+30h] [rbp-D0h]
  int v17; // [rsp+38h] [rbp-C8h]
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  struct IVdsVolume *v19; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v23[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v24; // [rsp+80h] [rbp-80h] BYREF
  __int128 v25; // [rsp+90h] [rbp-70h]
  int v26; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v27; // [rsp+A8h] [rbp-58h]
  __int64 v28; // [rsp+AAh] [rbp-56h]
  int v29; // [rsp+B2h] [rbp-4Eh]
  __int16 v30; // [rsp+B6h] [rbp-4Ah]
  GUID v31; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v32; // [rsp+C8h] [rbp-38h]
  __int16 v33; // [rsp+D0h] [rbp-30h]
  _BYTE v34[68]; // [rsp+120h] [rbp+20h] BYREF
  int v35; // [rsp+164h] [rbp+64h]
  LPVOID pv; // [rsp+178h] [rbp+78h]
  LPVOID v37; // [rsp+180h] [rbp+80h]
  LPVOID v38; // [rsp+188h] [rbp+88h]
  LPVOID v39; // [rsp+190h] [rbp+90h]
  LPVOID v40; // [rsp+198h] [rbp+98h]

  v18 = 0;
  v23[0] = 0;
  v20 = 0;
  v21 = 0;
  v19 = 0;
  v22 = 0;
  memset_0(&v26, 0, 0x78u);
  memset_0(v34, 0, 0x80u);
  DEBUGMSG(L"CDiskProtection::s_CreateAndFormatPrimaryPartition - cbSize = %I64u GB (%I64u bytes)\n", a3 >> 30, a3);
  memset_0(&v26, 0, 0x78u);
  v24 = 0;
  v25 = 0;
  memset_0(v34, 0, 0x80u);
  LODWORD(v8) = CDiskProtection::s_GetPartitionOffset(a2, a3, v23);
  if ( (int)v8 >= 0 )
  {
    LODWORD(v8) = ((__int64 (__fastcall *)(struct IVdsDisk *, _BYTE *))a2->lpVtbl->GetProperties)(a2, v34);
    if ( (int)v8 < 0 )
    {
      v9 = 5882;
LABEL_4:
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v9,
        L"CDiskProtection::s_CreateAndFormatPrimaryPartition",
        L"CHRA",
        L"hr",
        v8);
      if ( IsDebuggerPresent() )
      {
        v17 = v8;
        v10 = v9;
        v15 = L"hr";
LABEL_6:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          v10,
          L"CDiskProtection::s_CreateAndFormatPrimaryPartition",
          L"CHRA",
          v15,
          v17);
        goto LABEL_34;
      }
      v16 = v8;
      v11 = v9;
      v14 = L"hr";
LABEL_9:
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v11,
        L"CDiskProtection::s_CreateAndFormatPrimaryPartition",
        L"CHRA",
        v14,
        v16);
      goto LABEL_34;
    }
    v26 = v35;
    if ( v35 == 1 )
    {
      v27 = 6;
    }
    else
    {
      v27 = -24414;
      v32 = 0x8000000000000000uLL;
      v29 = *(_DWORD *)&PARTITION_BASIC_DATA_GUID.Data4[2];
      v30 = *(_WORD *)&PARTITION_BASIC_DATA_GUID.Data4[6];
      v31 = GUID_NULL;
      v33 = 0;
      v28 = *(_QWORD *)((char *)&PARTITION_BASIC_DATA_GUID.Data1 + 2);
    }
    LODWORD(v8) = ((__int64 (__fastcall *)(struct IVdsDisk *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                    a2,
                    &GUID_9882f547_cfc3_420b_9750_00dfbec50662,
                    &v20);
    if ( (int)v8 < 0 )
    {
      v9 = 5907;
      goto LABEL_4;
    }
    LODWORD(v8) = (*(__int64 (__fastcall **)(__int64, unsigned __int64, unsigned __int64, _QWORD, int *, __int64 *))(*(_QWORD *)v20 + 24LL))(
                    v20,
                    v23[0],
                    a3,
                    0,
                    &v26,
                    &v21);
    if ( (int)v8 < 0 )
    {
      v9 = 5910;
      goto LABEL_4;
    }
    DEBUGMSG(L"CDiskProtection::s_CreateAndFormatPrimaryPartition - About to call pAsync->Wait.\n");
    v8 = (*(unsigned int (__fastcall **)(__int64, int *, __int128 *))(*(_QWORD *)v21 + 32LL))(v21, &v18, &v24);
    DEBUGMSG(
      L"CDiskProtection::s_CreateAndFormatPrimaryPartition - pAsync->Wait has returned, hr = 0x%08x, hrAsync = 0x%08x.\n",
      v8,
      (unsigned int)v18);
    if ( (int)v8 < 0 )
    {
      v9 = 5916;
      goto LABEL_4;
    }
    LODWORD(v8) = v18;
    if ( v18 < 0 )
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        0x171Du,
        L"CDiskProtection::s_CreateAndFormatPrimaryPartition",
        L"CHRA",
        L"hrAsync",
        v18);
      if ( IsDebuggerPresent() )
      {
        v17 = v8;
        v10 = 5917;
        v15 = L"hrAsync";
        goto LABEL_6;
      }
      v16 = v8;
      v11 = 5917;
      v14 = L"hrAsync";
      goto LABEL_9;
    }
    if ( (_DWORD)v24 == 10 )
    {
      DEBUGMSG(
        L"CDiskProtection::s_CreateAndFormatPrimaryPartition - Created a partition at offset %I64u\n",
        *((_QWORD *)&v24 + 1));
      GetObjectA = a1->lpVtbl->GetObjectA;
      *(_OWORD *)v23 = v25;
      LODWORD(v8) = ((__int64 (__fastcall *)(struct IVdsService *, unsigned __int64 *, __int64, __int64 *))GetObjectA)(
                      a1,
                      v23,
                      11,
                      &v22);
      if ( (int)v8 < 0 )
      {
        v9 = 5926;
        goto LABEL_4;
      }
      LODWORD(v8) = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IVdsVolume **))v22)(
                      v22,
                      &GUID_88306bb2_e71f_478c_86a2_79da200a0f11,
                      &v19);
      if ( (int)v8 < 0 )
      {
        v9 = 5929;
        goto LABEL_4;
      }
      LODWORD(v8) = CDiskProtection::s_AssignDriveLetter(v19, a4);
      if ( (int)v8 >= 0 )
        LODWORD(v8) = CDiskProtection::s_FormatVolume(v19);
    }
    else
    {
      LODWORD(v8) = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        0x171Eu,
        L"CDiskProtection::s_CreateAndFormatPrimaryPartition",
        L"CBRA",
        L"sAsyncOutput.type == VDS_ASYNCOUT_CREATEPARTITION",
        -2147467259);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          5918,
          L"CDiskProtection::s_CreateAndFormatPrimaryPartition",
          L"CBRA",
          L"sAsyncOutput.type == VDS_ASYNCOUT_CREATEPARTITION",
          -2147467259);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          5918,
          L"CDiskProtection::s_CreateAndFormatPrimaryPartition",
          L"CBRA",
          L"sAsyncOutput.type == VDS_ASYNCOUT_CREATEPARTITION",
          -2147467259);
    }
  }
LABEL_34:
  CoTaskMemFree(pv);
  CoTaskMemFree(v37);
  CoTaskMemFree(v38);
  CoTaskMemFree(v39);
  CoTaskMemFree(v40);
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v19 )
  {
    ((void (__fastcall *)(struct IVdsVolume *))v19->lpVtbl->Release)(v19);
    v19 = 0;
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000f664  push    rbp
0x14000f666  push    rbx
0x14000f667  push    rsi
0x14000f668  push    rdi
0x14000f669  push    r12
0x14000f66b  push    r14
0x14000f66d  push    r15
0x14000f66f  lea     rbp, [rsp-0B0h]
0x14000f677  sub     rsp, 1B0h
0x14000f67e  mov     rax, cs:__security_cookie
0x14000f685  xor     rax, rsp
0x14000f688  mov     [rbp+0E0h+var_40], rax
0x14000f68f  mov     r14, r8
0x14000f692  mov     [rsp+1E0h+var_1A0], 0
0x14000f69a  mov     rdi, rdx
0x14000f69d  mov     [rsp+1E0h+var_170], 0
0x14000f6a6  mov     rsi, rcx
0x14000f6a9  mov     [rsp+1E0h+var_190], 0
0x14000f6b2  mov     r12d, 78h ; 'x'
0x14000f6b8  mov     [rsp+1E0h+var_188], 0
0x14000f6c1  mov     r8d, r12d; Size
0x14000f6c4  mov     [rsp+1E0h+var_198], 0
0x14000f6cd  xor     edx, edx; Val
0x14000f6cf  mov     [rsp+1E0h+var_180], 0
0x14000f6d8  lea     rcx, [rbp+0E0h+var_140]; void *
0x14000f6dc  movzx   r15d, r9w
0x14000f6e0  call    memset_0
0x14000f6e5  xorps   xmm0, xmm0
0x14000f6e8  lea     ebx, [r12+8]
0x14000f6ed  mov     r8d, ebx; Size
0x14000f6f0  lea     rcx, [rbp+0E0h+var_C0]; void *
0x14000f6f4  xor     edx, edx; Val
0x14000f6f6  movups  [rbp+0E0h+var_160], xmm0
0x14000f6fa  movups  [rbp+0E0h+var_150], xmm0
0x14000f6fe  call    memset_0
0x14000f703  mov     rdx, r14
0x14000f706  lea     rcx, aCdiskprotectio_183; "CDiskProtection::s_CreateAndFormatPrima"...
0x14000f70d  shr     rdx, 1Eh
0x14000f711  mov     r8, r14
0x14000f714  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000f719  mov     r8d, r12d; Size
0x14000f71c  lea     rcx, [rbp+0E0h+var_140]; void *
0x14000f720  xor     edx, edx; Val
0x14000f722  call    memset_0
0x14000f727  xorps   xmm0, xmm0
0x14000f72a  lea     rcx, [rbp+0E0h+var_C0]; void *
0x14000f72e  mov     r8d, ebx; Size
0x14000f731  xor     edx, edx; Val
0x14000f733  movups  [rbp+0E0h+var_160], xmm0
0x14000f737  movups  [rbp+0E0h+var_150], xmm0
0x14000f73b  call    memset_0
0x14000f740  lea     r8, [rsp+1E0h+var_170]; unsigned __int64 *
0x14000f745  mov     rdx, r14; unsigned __int64
0x14000f748  mov     rcx, rdi; struct IVdsDisk *
0x14000f74b  call    ?s_GetPartitionOffset@CDiskProtection@@KAJPEAUIVdsDisk@@_KPEA_K@Z; CDiskProtection::s_GetPartitionOffset(IVdsDisk *,unsigned __int64,unsigned __int64 *)
0x14000f750  mov     ebx, eax
0x14000f752  test    eax, eax
0x14000f754  js      loc_14000FAA7
0x14000f75a  mov     rax, [rdi]
0x14000f75d  lea     rdx, [rbp+0E0h+var_C0]
0x14000f761  mov     rcx, rdi
0x14000f764  mov     rax, [rax+18h]
0x14000f768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f76d  mov     ebx, eax
0x14000f76f  test    eax, eax
0x14000f771  jns     loc_14000F814
0x14000f777  mov     r12d, 16FAh
0x14000f77d  lea     rsi, aCdiskprotectio_159; "CDiskProtection::s_CreateAndFormatPrima"...
0x14000f784  mov     [rsp+1E0h+var_1B8], ebx; int
0x14000f788  lea     r14, aChra; "CHRA"
0x14000f78f  mov     r8, rsi; unsigned __int16 *
0x14000f792  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000f799  mov     r9, r14; unsigned __int16 *
0x14000f79c  lea     r15, aHr; "hr"
0x14000f7a3  mov     rcx, rdi; unsigned __int16 *
0x14000f7a6  mov     edx, r12d; unsigned int
0x14000f7a9  mov     [rsp+1E0h+var_1C0], r15; unsigned __int16 *
0x14000f7ae  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000f7b3  call    cs:__imp_IsDebuggerPresent
0x14000f7b9  test    eax, eax
0x14000f7bb  jz      short loc_14000F7EC
0x14000f7bd  mov     [rsp+1E0h+var_1A8], ebx
0x14000f7c1  mov     r9d, r12d
0x14000f7c4  mov     [rsp+1E0h+var_1B0], r15
0x14000f7c9  mov     qword ptr [rsp+1E0h+var_1B8], r14
0x14000f7ce  mov     r8, rdi
0x14000f7d1  mov     [rsp+1E0h+var_1C0], rsi
0x14000f7d6  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000f7dd  mov     ecx, 2; unsigned __int8
0x14000f7e2  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000f7e7  jmp     loc_14000FAA7
0x14000f7ec  mov     dword ptr [rsp+1E0h+var_1B0], ebx
0x14000f7f0  mov     r8d, r12d
0x14000f7f3  mov     qword ptr [rsp+1E0h+var_1B8], r15
0x14000f7f8  mov     [rsp+1E0h+var_1C0], r14
0x14000f7fd  mov     r9, rsi
0x14000f800  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000f807  mov     rdx, rdi
0x14000f80a  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000f80f  jmp     loc_14000FAA7
0x14000f814  mov     eax, [rbp+0E0h+var_7C]
0x14000f817  mov     [rbp+0E0h+var_140], eax
0x14000f81a  cmp     eax, 1
0x14000f81d  jnz     short loc_14000F827
0x14000f81f  mov     [rbp+0E0h+var_138], 6
0x14000f825  jmp     short loc_14000F86E
0x14000f827  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14000f82e  mov     rax, 8000000000000000h
0x14000f838  mov     [rbp+0E0h+var_138], 0A0A2h
0x14000f83e  mov     [rbp+0E0h+var_118], rax
0x14000f842  mov     eax, dword ptr cs:PARTITION_BASIC_DATA_GUID.Data4+2
0x14000f848  mov     [rbp+0E0h+var_12E], eax
0x14000f84b  movzx   eax, word ptr cs:PARTITION_BASIC_DATA_GUID.Data4+6
0x14000f852  mov     [rbp+0E0h+var_12A], ax
0x14000f856  xor     eax, eax
0x14000f858  movdqu  [rbp+0E0h+var_128], xmm0
0x14000f85d  mov     [rbp+0E0h+var_110], ax
0x14000f861  movsd   xmm0, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data1+2
0x14000f869  movsd   [rbp+0E0h+var_136], xmm0
0x14000f86e  mov     rax, [rdi]
0x14000f871  lea     r8, [rsp+1E0h+var_190]
0x14000f876  lea     rdx, _GUID_9882f547_cfc3_420b_9750_00dfbec50662
0x14000f87d  mov     rcx, rdi
0x14000f880  mov     rax, [rax]
0x14000f883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f888  mov     ebx, eax
0x14000f88a  test    eax, eax
0x14000f88c  jns     short loc_14000F899
0x14000f88e  mov     r12d, 1713h
0x14000f894  jmp     loc_14000F77D
0x14000f899  mov     rcx, [rsp+1E0h+var_190]
0x14000f89e  lea     rdx, [rsp+1E0h+var_188]
0x14000f8a3  mov     qword ptr [rsp+1E0h+var_1B8], rdx
0x14000f8a8  xor     r9d, r9d
0x14000f8ab  lea     rdx, [rbp+0E0h+var_140]
0x14000f8af  mov     r8, r14
0x14000f8b2  mov     [rsp+1E0h+var_1C0], rdx
0x14000f8b7  mov     rax, [rcx]
0x14000f8ba  mov     rdx, [rsp+1E0h+var_170]
0x14000f8bf  mov     rax, [rax+18h]
0x14000f8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f8c8  mov     ebx, eax
0x14000f8ca  test    eax, eax
0x14000f8cc  jns     short loc_14000F8D9
0x14000f8ce  mov     r12d, 1716h
0x14000f8d4  jmp     loc_14000F77D
0x14000f8d9  lea     rcx, aCdiskprotectio_61; "CDiskProtection::s_CreateAndFormatPrima"...
0x14000f8e0  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000f8e5  mov     rcx, [rsp+1E0h+var_188]
0x14000f8ea  lea     r8, [rbp+0E0h+var_160]
0x14000f8ee  lea     rdx, [rsp+1E0h+var_1A0]
0x14000f8f3  mov     rax, [rcx]
0x14000f8f6  mov     rax, [rax+20h]
0x14000f8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f8ff  mov     r8d, [rsp+1E0h+var_1A0]
0x14000f904  lea     rcx, aCdiskprotectio_179; "CDiskProtection::s_CreateAndFormatPrima"...
0x14000f90b  mov     edx, eax
0x14000f90d  mov     ebx, eax
0x14000f90f  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000f914  test    ebx, ebx
0x14000f916  jns     short loc_14000F923
0x14000f918  mov     r12d, 171Ch
0x14000f91e  jmp     loc_14000F77D
0x14000f923  mov     ebx, [rsp+1E0h+var_1A0]
0x14000f927  test    ebx, ebx
0x14000f929  jns     short loc_14000F993
0x14000f92b  lea     r14, aChra; "CHRA"
0x14000f932  mov     [rsp+1E0h+var_1B8], ebx; int
0x14000f936  lea     rsi, aCdiskprotectio_159; "CDiskProtection::s_CreateAndFormatPrima"...
0x14000f93d  mov     r15d, 171Dh
0x14000f943  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000f94a  mov     r9, r14; unsigned __int16 *
0x14000f94d  lea     r12, aHrasync; "hrAsync"
0x14000f954  mov     r8, rsi; unsigned __int16 *
0x14000f957  mov     edx, r15d; unsigned int
0x14000f95a  mov     [rsp+1E0h+var_1C0], r12; unsigned __int16 *
0x14000f95f  mov     rcx, rdi; unsigned __int16 *
0x14000f962  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000f967  call    cs:__imp_IsDebuggerPresent
0x14000f96d  test    eax, eax
0x14000f96f  jz      short loc_14000F982
0x14000f971  mov     [rsp+1E0h+var_1A8], ebx
0x14000f975  mov     r9d, r15d
0x14000f978  mov     [rsp+1E0h+var_1B0], r12
0x14000f97d  jmp     loc_14000F7C9
0x14000f982  mov     dword ptr [rsp+1E0h+var_1B0], ebx
0x14000f986  mov     r8d, r15d
0x14000f989  mov     qword ptr [rsp+1E0h+var_1B8], r12
0x14000f98e  jmp     loc_14000F7F8
0x14000f993  cmp     dword ptr [rbp+0E0h+var_160], 0Ah
0x14000f997  jz      short loc_14000FA10
0x14000f999  mov     ebx, 80004005h
0x14000f99e  lea     r12, aCbra; "CBRA"
0x14000f9a5  lea     rsi, aCdiskprotectio_159; "CDiskProtection::s_CreateAndFormatPrima"...
0x14000f9ac  mov     [rsp+1E0h+var_1B8], ebx; int
0x14000f9b0  mov     r14d, 171Eh
0x14000f9b6  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000f9bd  lea     r15, aSasyncoutputTy; "sAsyncOutput.type == VDS_ASYNCOUT_CREAT"...
0x14000f9c4  mov     r9, r12; unsigned __int16 *
0x14000f9c7  mov     r8, rsi; unsigned __int16 *
0x14000f9ca  mov     [rsp+1E0h+var_1C0], r15; unsigned __int16 *
0x14000f9cf  mov     edx, r14d; unsigned int
0x14000f9d2  mov     rcx, rdi; unsigned __int16 *
0x14000f9d5  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000f9da  call    cs:__imp_IsDebuggerPresent
0x14000f9e0  test    eax, eax
0x14000f9e2  jz      short loc_14000F9FA
0x14000f9e4  mov     [rsp+1E0h+var_1A8], ebx
0x14000f9e8  mov     r9d, r14d
0x14000f9eb  mov     [rsp+1E0h+var_1B0], r15
0x14000f9f0  mov     qword ptr [rsp+1E0h+var_1B8], r12
0x14000f9f5  jmp     loc_14000F7CE
0x14000f9fa  mov     dword ptr [rsp+1E0h+var_1B0], ebx
0x14000f9fe  mov     r8d, r14d
0x14000fa01  mov     qword ptr [rsp+1E0h+var_1B8], r15
0x14000fa06  mov     [rsp+1E0h+var_1C0], r12
0x14000fa0b  jmp     loc_14000F7FD
0x14000fa10  mov     rdx, qword ptr [rbp+0E0h+var_160+8]
0x14000fa14  lea     rcx, aCdiskprotectio_83; "CDiskProtection::s_CreateAndFormatPrima"...
0x14000fa1b  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000fa20  mov     rax, [rsi]
0x14000fa23  lea     r9, [rsp+1E0h+var_180]
0x14000fa28  movups  xmm0, [rbp+0E0h+var_150]
0x14000fa2c  mov     r8d, 0Bh
0x14000fa32  lea     rdx, [rsp+1E0h+var_170]
0x14000fa37  mov     rcx, rsi
0x14000fa3a  mov     rax, [rax+48h]
0x14000fa3e  movdqu  xmmword ptr [rsp+1E0h+var_170], xmm0
0x14000fa44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fa49  mov     ebx, eax
0x14000fa4b  test    eax, eax
0x14000fa4d  jns     short loc_14000FA5A
0x14000fa4f  mov     r12d, 1726h
0x14000fa55  jmp     loc_14000F77D
0x14000fa5a  mov     rcx, [rsp+1E0h+var_180]
0x14000fa5f  lea     r8, [rsp+1E0h+var_198]
0x14000fa64  lea     rdx, _GUID_88306bb2_e71f_478c_86a2_79da200a0f11
0x14000fa6b  mov     rax, [rcx]
0x14000fa6e  mov     rax, [rax]
0x14000fa71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fa76  mov     ebx, eax
0x14000fa78  test    eax, eax
0x14000fa7a  jns     short loc_14000FA87
0x14000fa7c  mov     r12d, 1729h
0x14000fa82  jmp     loc_14000F77D
0x14000fa87  mov     rcx, [rsp+1E0h+var_198]; struct IVdsVolume *
0x14000fa8c  movzx   edx, r15w; unsigned __int16
0x14000fa90  call    ?s_AssignDriveLetter@CDiskProtection@@KAJPEAUIVdsVolume@@G@Z; CDiskProtection::s_AssignDriveLetter(IVdsVolume *,ushort)
0x14000fa95  mov     ebx, eax
0x14000fa97  test    eax, eax
0x14000fa99  js      short loc_14000FAA7
0x14000fa9b  mov     rcx, [rsp+1E0h+var_198]; struct IVdsVolume *
0x14000faa0  call    ?s_FormatVolume@CDiskProtection@@KAJPEAUIVdsVolume@@@Z; CDiskProtection::s_FormatVolume(IVdsVolume *)
0x14000faa5  mov     ebx, eax
0x14000faa7  mov     rcx, [rbp+0E0h+pv]; pv
0x14000faab  call    cs:__imp_CoTaskMemFree
0x14000fab1  mov     rcx, [rbp+0E0h+var_60]; pv
0x14000fab8  call    cs:__imp_CoTaskMemFree
0x14000fabe  mov     rcx, [rbp+0E0h+var_58]; pv
0x14000fac5  call    cs:__imp_CoTaskMemFree
0x14000facb  mov     rcx, [rbp+0E0h+var_50]; pv
0x14000fad2  call    cs:__imp_CoTaskMemFree
0x14000fad8  mov     rcx, [rbp+0E0h+var_48]; pv
0x14000fadf  call    cs:__imp_CoTaskMemFree
0x14000fae5  mov     rcx, [rsp+1E0h+var_190]
0x14000faea  test    rcx, rcx
0x14000faed  jz      short loc_14000FB04
0x14000faef  mov     rax, [rcx]
0x14000faf2  mov     rax, [rax+10h]
0x14000faf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fafb  mov     [rsp+1E0h+var_190], 0
0x14000fb04  mov     rcx, [rsp+1E0h+var_188]
0x14000fb09  test    rcx, rcx
0x14000fb0c  jz      short loc_14000FB23
0x14000fb0e  mov     rax, [rcx]
0x14000fb11  mov     rax, [rax+10h]
0x14000fb15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fb1a  mov     [rsp+1E0h+var_188], 0
0x14000fb23  mov     rcx, [rsp+1E0h+var_198]
0x14000fb28  test    rcx, rcx
0x14000fb2b  jz      short loc_14000FB42
0x14000fb2d  mov     rax, [rcx]
0x14000fb30  mov     rax, [rax+10h]
0x14000fb34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fb39  mov     [rsp+1E0h+var_198], 0
0x14000fb42  mov     rcx, [rsp+1E0h+var_180]
0x14000fb47  test    rcx, rcx
0x14000fb4a  jz      short loc_14000FB58
0x14000fb4c  mov     rax, [rcx]
0x14000fb4f  mov     rax, [rax+10h]
0x14000fb53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fb58  mov     eax, ebx
0x14000fb5a  mov     rcx, [rbp+0E0h+var_40]
0x14000fb61  xor     rcx, rsp; StackCookie
0x14000fb64  call    __security_check_cookie
0x14000fb69  add     rsp, 1B0h
0x14000fb70  pop     r15
0x14000fb72  pop     r14
0x14000fb74  pop     r12
0x14000fb76  pop     rdi
  ... truncated ...
```
