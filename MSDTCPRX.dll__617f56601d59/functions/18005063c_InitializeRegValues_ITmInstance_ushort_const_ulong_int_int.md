# InitializeRegValues(ITmInstance *,ushort const *,ulong,int,int)

- ea: `0x18005063c`
- end: `0x1800508ac`
- name: `?InitializeRegValues@@YAJPEAUITmInstance@@PEBGKHH@Z`
- size: `624`
- prototype: `int(struct ITmInstance *, const unsigned __int16 *, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180050564`

## callees

- `0x180006764`
- `0x18000d5f4`
- `0x18001040c`
- `0x18001156c`
- `0x180011ac0`
- `0x180050274`
- `0x18005063c`
- `0x180081daa`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005075f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050767`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005075f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050767`
- `msvcrt!_wtoi` at `0x180050783`
- `msvcrt!_wtoi` at `0x180050783`
- `msvcrt!_errno` at `0x180050790`
- `msvcrt!_errno` at `0x180050790`

## string_xrefs

- `0x180050745`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x180050872`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x18005089f`: `InitializeRegValues (com\complus\dtc\dtc\adme\deployment.cpp@645): InitializeRegValues: pTmInstance != NULL`
- `0x180050892`: `InitializeRegValues (com\complus\dtc\dtc\adme\deployment.cpp@648): InitializeRegValues: NULL != pwszRegHivePrefix`
- `0x180050885`: `InitializeRegValues (com\complus\dtc\dtc\adme\deployment.cpp@649): InitializeRegValues: NULL != s_registryData[i].pwszKeyName`
- `0x180050808`: `InitializeRegValues (com\complus\dtc\dtc\adme\deployment.cpp@655): InitializeRegValues: Invalid data type for the registry value`
- `0x18005082f`: `InitializeRegValues (com\complus\dtc\dtc\adme\deployment.cpp@674): InitializeRegValues: NULL != s_registryData[i].pwszValueName`
- `0x180050822`: `InitializeRegValues (com\complus\dtc\dtc\adme\deployment.cpp@675): InitializeRegValues: NULL != s_registryData[i].pwszValue`
- `0x180050815`: `InitializeRegValues (com\complus\dtc\dtc\adme\deployment.cpp@695): The DWORD value is out of range`
- `0x180050858`: `InitializeRegValues (com\complus\dtc\dtc\adme\deployment.cpp@703): InitializeRegValues: NULL != s_registryData[i].pwszValueName`
- `0x18005084b`: `InitializeRegValues (com\complus\dtc\dtc\adme\deployment.cpp@704): InitializeRegValues: NULL != s_registryData[i].pwszValue`
- `0x180050842`: `InitializeRegValues: CreateAndSetHKLMRegistryKey failed`

## pseudocode

```c
__int64 __fastcall InitializeRegValues(
        struct ITmInstance *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        int a4,
        int a5)
{
  unsigned int v5; // ebx
  int v6; // r15d
  int i; // esi
  __int64 v11; // rdi
  int StringW; // eax
  int v13; // ecx
  DWORD v14; // r9d
  unsigned int *v15; // r8
  wchar_t *v16; // rax
  const wchar_t *v17; // rbx
  int MajorVersionInfo; // eax
  __int64 v20; // rax
  unsigned int v21; // r9d
  unsigned __int16 *v22; // rdx
  LPVOID pv; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v24; // [rsp+A8h] [rbp+20h] BYREF

  v5 = 0;
  pv = 0;
  v24 = 0;
  v6 = a4 + a5;
  for ( i = a4; i < v6; ++i )
  {
    if ( !a1 )
      DtcInternalErrorW(
        L"InitializeRegValues (com\\complus\\dtc\\dtc\\adme\\deployment.cpp@645): InitializeRegValues: pTmInstance != NULL");
    if ( !a2 )
      DtcInternalErrorW(
        L"InitializeRegValues (com\\complus\\dtc\\dtc\\adme\\deployment.cpp@648): InitializeRegValues: NULL != pwszRegHivePrefix");
    v11 = 4LL * i;
    if ( !off_18008AA40[v11] )
      DtcInternalErrorW(
        L"InitializeRegValues (com\\complus\\dtc\\dtc\\adme\\deployment.cpp@649): InitializeRegValues: NULL != s_registryD"
         "ata[i].pwszKeyName");
    if ( LODWORD(off_18008AA40[v11 + 3]) > 2 && LODWORD(off_18008AA40[v11 + 3]) != 4 )
      DtcInternalErrorW(
        L"InitializeRegValues (com\\complus\\dtc\\dtc\\adme\\deployment.cpp@655): InitializeRegValues: Invalid data type f"
         "or the registry value");
    StringW = MakeStringW((unsigned __int16 **)&pv, L"%s\\%s", a2);
    v5 = StringW;
    if ( StringW < 0 )
    {
      v21 = 662;
      v22 = L"InitializeRegValues: MakeStringW failed";
      goto LABEL_35;
    }
    v13 = (int)off_18008AA40[v11 + 3];
    if ( v13 )
    {
      v16 = off_18008AA40[v11 + 1];
      if ( v13 == 4 )
      {
        if ( !v16 )
          DtcInternalErrorW(
            L"InitializeRegValues (com\\complus\\dtc\\dtc\\adme\\deployment.cpp@674): InitializeRegValues: NULL != s_regis"
             "tryData[i].pwszValueName");
        v17 = off_18008AA40[v11 + 2];
        if ( !v17 )
          DtcInternalErrorW(
            L"InitializeRegValues (com\\complus\\dtc\\dtc\\adme\\deployment.cpp@675): InitializeRegValues: NULL != s_regis"
             "tryData[i].pwszValue");
        if ( !wcscmp_0(L"MajorVersion", off_18008AA40[v11 + 1]) )
        {
          MajorVersionInfo = GetMajorVersionInfo(&v24);
          v5 = MajorVersionInfo;
          if ( MajorVersionInfo < 0 )
          {
            TraceFile(
              MajorVersionInfo,
              "GetMajorVersionInfo failed",
              "com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
              0x2AFu);
            break;
          }
        }
        else
        {
          v24 = _wtoi(v17);
          if ( *_errno() == 34 )
            DtcInternalErrorW(L"InitializeRegValues (com\\complus\\dtc\\dtc\\adme\\deployment.cpp@695): The DWORD value is out of range");
        }
        v14 = 4;
        v15 = &v24;
      }
      else
      {
        if ( !v16 )
          DtcInternalErrorW(
            L"InitializeRegValues (com\\complus\\dtc\\dtc\\adme\\deployment.cpp@703): InitializeRegValues: NULL != s_regis"
             "tryData[i].pwszValueName");
        v15 = (unsigned int *)off_18008AA40[v11 + 2];
        if ( !v15 )
          DtcInternalErrorW(
            L"InitializeRegValues (com\\complus\\dtc\\dtc\\adme\\deployment.cpp@704): InitializeRegValues: NULL != s_regis"
             "tryData[i].pwszValue");
        v20 = -1;
        do
          ++v20;
        while ( *((_WORD *)v15 + v20) );
        v14 = 2 * v20 + 2;
      }
    }
    else
    {
      v14 = 0;
      v15 = 0;
    }
    StringW = CreateAndSetHKLMRegistryKey(
                (LPCWSTR)pv,
                off_18008AA40[v11 + 1],
                (BYTE *)v15,
                v14,
                (DWORD)off_18008AA40[v11 + 3],
                a3);
    v5 = StringW;
    if ( StringW < 0 )
    {
      v21 = 713;
      v22 = L"InitializeRegValues: CreateAndSetHKLMRegistryKey failed";
LABEL_35:
      TraceFileW(StringW, v22, L"com\\complus\\dtc\\dtc\\adme\\deployment.cpp", v21);
      break;
    }
  }
  CoTaskMemFree(pv);
  CoTaskMemFree(0);
  return v5;
}

```

## disassembly

```asm
0x18005063c  mov     rax, rsp
0x18005063f  push    rbx
0x180050640  push    rbp
0x180050641  push    rsi
0x180050642  push    rdi
0x180050643  push    r12
0x180050645  push    r13
0x180050647  push    r14
0x180050649  push    r15
0x18005064b  sub     rsp, 48h
0x18005064f  mov     r15d, [rsp+88h+arg_20]
0x180050657  xor     r13d, r13d
0x18005065a  mov     ebx, r13d
0x18005065d  mov     [rax-58h], r13
0x180050661  mov     [rax+20h], r13d
0x180050665  add     r15d, r9d
0x180050668  mov     esi, r9d
0x18005066b  mov     r12d, r8d
0x18005066e  mov     rbp, rdx
0x180050671  mov     r14, rcx
0x180050674  lea     rax, off_18008AA40; "Microsoft\\MSDTC"
0x18005067b  cmp     esi, r15d
0x18005067e  jge     loc_18005075A
0x180050684  test    r14, r14
0x180050687  jz      loc_18005089F
0x18005068d  test    rbp, rbp
0x180050690  jz      loc_180050892
0x180050696  movsxd  rdi, esi
0x180050699  shl     rdi, 5
0x18005069d  mov     r9, [rdi+rax]
0x1800506a1  test    r9, r9
0x1800506a4  jz      loc_180050885
0x1800506aa  cmp     dword ptr [rdi+rax+18h], 2
0x1800506af  jbe     short loc_1800506BC
0x1800506b1  cmp     dword ptr [rdi+rax+18h], 4
0x1800506b6  jnz     loc_180050808
0x1800506bc  mov     r8, rbp
0x1800506bf  lea     rdx, aSS_1; "%s\\%s"
0x1800506c6  lea     rcx, [rsp+88h+pv]; unsigned __int16 **
0x1800506cb  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x1800506d0  mov     ebx, eax
0x1800506d2  test    eax, eax
0x1800506d4  js      loc_180050865
0x1800506da  lea     rdx, off_18008AA40; "Microsoft\\MSDTC"
0x1800506e1  mov     ecx, [rdi+rdx+18h]
0x1800506e5  test    ecx, ecx
0x1800506e7  jnz     short loc_1800506F4
0x1800506e9  mov     r9d, r13d
0x1800506ec  mov     r8, r13
0x1800506ef  jmp     loc_1800507DF
0x1800506f4  mov     rax, [rdi+rdx+8]
0x1800506f9  cmp     ecx, 4
0x1800506fc  jnz     loc_1800507B2
0x180050702  test    rax, rax
0x180050705  jz      loc_18005082F
0x18005070b  mov     rbx, [rdi+rdx+10h]
0x180050710  test    rbx, rbx
0x180050713  jz      loc_180050822
0x180050719  mov     rdx, rax; String2
0x18005071c  lea     rcx, aMajorversion; "MajorVersion"
0x180050723  call    wcscmp_0
0x180050728  test    eax, eax
0x18005072a  jnz     short loc_180050780
0x18005072c  lea     rcx, [rsp+88h+arg_18]; unsigned int *
0x180050734  call    ?GetMajorVersionInfo@@YAJAEAK@Z; GetMajorVersionInfo(ulong &)
0x180050739  mov     ebx, eax
0x18005073b  test    eax, eax
0x18005073d  jns     short loc_18005079B
0x18005073f  mov     r9d, 2AFh; unsigned int
0x180050745  lea     r8, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x18005074c  lea     rdx, aGetmajorversio; "GetMajorVersionInfo failed"
0x180050753  mov     ecx, eax; int
0x180050755  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18005075a  mov     rcx, [rsp+88h+pv]; pv
0x18005075f  call    cs:__imp_CoTaskMemFree
0x180050765  xor     ecx, ecx; pv
0x180050767  call    cs:__imp_CoTaskMemFree
0x18005076d  mov     eax, ebx
0x18005076f  add     rsp, 48h
0x180050773  pop     r15
0x180050775  pop     r14
0x180050777  pop     r13
0x180050779  pop     r12
0x18005077b  pop     rdi
0x18005077c  pop     rsi
0x18005077d  pop     rbp
0x18005077e  pop     rbx
0x18005077f  retn
0x180050780  mov     rcx, rbx; String
0x180050783  call    cs:__imp__wtoi
0x180050789  mov     [rsp+88h+arg_18], eax
0x180050790  call    cs:__imp__errno
0x180050796  cmp     dword ptr [rax], 22h ; '"'
0x180050799  jz      short loc_180050815
0x18005079b  mov     r9d, 4
0x1800507a1  lea     r8, [rsp+88h+arg_18]
0x1800507a9  lea     rdx, off_18008AA40; "Microsoft\\MSDTC"
0x1800507b0  jmp     short loc_1800507DF
0x1800507b2  test    rax, rax
0x1800507b5  jz      loc_180050858
0x1800507bb  mov     r8, [rdi+rdx+10h]; lpData
0x1800507c0  test    r8, r8
0x1800507c3  jz      loc_18005084B
0x1800507c9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800507cd  inc     rax
0x1800507d0  cmp     [r8+rax*2], r13w
0x1800507d5  jnz     short loc_1800507CD
0x1800507d7  lea     r9d, ds:2[rax*2]; cbData
0x1800507df  mov     eax, [rdi+rdx+18h]
0x1800507e3  mov     rdx, [rdi+rdx+8]; lpValueName
0x1800507e8  mov     rcx, [rsp+88h+pv]; lpSubKey
0x1800507ed  mov     [rsp+88h+var_60], r12d; unsigned int
0x1800507f2  mov     [rsp+88h+dwType], eax; dwType
0x1800507f6  call    ?CreateAndSetHKLMRegistryKey@@YAJPEBG0PEAEKKK@Z; CreateAndSetHKLMRegistryKey(ushort const *,ushort const *,uchar *,ulong,ulong,ulong)
0x1800507fb  mov     ebx, eax
0x1800507fd  test    eax, eax
0x1800507ff  js      short loc_18005083C
0x180050801  inc     esi
0x180050803  jmp     loc_180050674
0x180050808  lea     rcx, aInitializeregv_7; "InitializeRegValues (com\\complus\\dtc"...
0x18005080f  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180050815  lea     rcx, aInitializeregv; "InitializeRegValues (com\\complus\\dtc"...
0x18005081c  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180050822  lea     rcx, aInitializeregv_6; "InitializeRegValues (com\\complus\\dtc"...
0x180050829  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18005082f  lea     rcx, aInitializeregv_0; "InitializeRegValues (com\\complus\\dtc"...
0x180050836  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18005083c  mov     r9d, 2C9h
0x180050842  lea     rdx, aInitializeregv_4; "InitializeRegValues: CreateAndSetHKLMRe"...
0x180050849  jmp     short loc_180050872
0x18005084b  lea     rcx, aInitializeregv_5; "InitializeRegValues (com\\complus\\dtc"...
0x180050852  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180050858  lea     rcx, aInitializeregv_9; "InitializeRegValues (com\\complus\\dtc"...
0x18005085f  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180050865  mov     r9d, 296h; unsigned int
0x18005086b  lea     rdx, aInitializeregv_1; "InitializeRegValues: MakeStringW failed"
0x180050872  lea     r8, aComComplusDtcD_8; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x180050879  mov     ecx, eax; int
0x18005087b  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180050880  jmp     loc_18005075A
0x180050885  lea     rcx, aInitializeregv_2; "InitializeRegValues (com\\complus\\dtc"...
0x18005088c  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180050892  lea     rcx, aInitializeregv_8; "InitializeRegValues (com\\complus\\dtc"...
0x180050899  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18005089f  lea     rcx, aInitializeregv_3; "InitializeRegValues (com\\complus\\dtc"...
0x1800508a6  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
```
