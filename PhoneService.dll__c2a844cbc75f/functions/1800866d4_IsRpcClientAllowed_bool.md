# IsRpcClientAllowed(bool *)

- ea: `0x1800866d4`
- end: `0x180086afc`
- name: `?IsRpcClientAllowed@@YAJPEA_N@Z`
- size: `1064`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18008c3f0`

## callees

- `0x1800011fc`
- `0x1800045b4`
- `0x1800056a0`
- `0x180006e94`
- `0x180007750`
- `0x180009094`
- `0x180086394`
- `0x1800866d4`
- `0x180086b10`
- `0x180086d78`
- `0x18008d95a`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086771`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008680f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086771`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008680f`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180086888`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180086888`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x1800867a3`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x1800867a3`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x18008673a`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x18008673a`
- `WINTRUST!WinVerifyTrust` at `0x180086a35`
- `WINTRUST!WinVerifyTrust` at `0x180086a6b`
- `WINTRUST!WinVerifyTrust` at `0x180086a35`
- `WINTRUST!WinVerifyTrust` at `0x180086a6b`

## pseudocode

```c
__int64 __fastcall IsRpcClientAllowed(bool *a1)
{
  void **v2; // rax
  int RpcClientThreadToken; // eax
  BackTraceCollection *v4; // rcx
  __int64 v5; // rdi
  signed int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // r8d
  int v11; // r9d
  BackTraceCollection *v12; // rcx
  LONG PackageFamilyNameFromToken; // eax
  BackTraceCollection *v14; // rcx
  __int64 v15; // r8
  BackTraceCollection *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  RPC_STATUS v19; // eax
  BackTraceCollection *v20; // rcx
  signed int RpcClientProcessPathNameFromProcessId; // eax
  BackTraceCollection *v22; // rcx
  WCHAR *v23; // rax
  DWORD v24; // edi
  __int64 v25; // r8
  __int64 v26; // r9
  LONG v27; // eax
  BackTraceCollection *v28; // rcx
  __int16 *v29; // rcx
  _QWORD v31[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v32; // [rsp+40h] [rbp-C0h]
  UINT32 packageFamilyNameLength; // [rsp+50h] [rbp-B0h] BYREF
  GUID hObject; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int Pid; // [rsp+68h] [rbp-98h] BYREF
  void *v36[2]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v37; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+82h] [rbp-7Eh]
  int v39; // [rsp+8Ah] [rbp-76h]
  __int16 v40; // [rsp+8Eh] [rbp-72h]
  void *Block; // [rsp+90h] [rbp-70h]
  __int16 *v42; // [rsp+98h] [rbp-68h]
  __int16 v43; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v44; // [rsp+A2h] [rbp-5Eh]
  int v45; // [rsp+AAh] [rbp-56h]
  __int16 v46; // [rsp+AEh] [rbp-52h]
  struct _WINTRUST_DATA packageFamilyName; // [rsp+B0h] [rbp-50h] BYREF

  v36[0] = &v37;
  *a1 = 0;
  v36[1] = &v37;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v37 = 0;
  *(_QWORD *)&hObject.Data1 = 0;
  v2 = (void **)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&hObject);
  RpcClientThreadToken = GetRpcClientThreadToken(8u, v2);
  v5 = -1;
  v6 = RpcClientThreadToken;
  if ( RpcClientThreadToken < 0 )
  {
    BackTraceCollection::Capture(v4, RpcClientThreadToken);
    v8 = 101;
LABEL_3:
    v9 = 1;
    goto LABEL_4;
  }
  memset_0(&packageFamilyName, 0, 0x82u);
  packageFamilyNameLength = 65;
  PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(
                                 *(HANDLE *)&hObject.Data1,
                                 &packageFamilyNameLength,
                                 (PWSTR)&packageFamilyName);
  v6 = PackageFamilyNameFromToken;
  if ( PackageFamilyNameFromToken > 0 )
    v6 = (unsigned __int16)PackageFamilyNameFromToken | 0x80070000;
  if ( v6 < 0 )
  {
    BackTraceCollection::Capture(v14, v6);
    v8 = 105;
    goto LABEL_3;
  }
  v15 = -1;
  do
    ++v15;
  while ( *((_WORD *)&packageFamilyName.cbStruct + v15) );
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v36,
                           &packageFamilyName) )
  {
    v6 = -2147024882;
    BackTraceCollection::Capture(v16, -2147024882);
    v9 = 0;
    v8 = 107;
LABEL_4:
    Log_HREvent_31((unsigned int)v6, v9, v7, v8);
    v12 = *(BackTraceCollection **)&hObject.Data1;
    if ( *(_QWORD *)&hObject.Data1 )
      CloseHandle(*(HANDLE *)&hObject.Data1);
    goto LABEL_17;
  }
  v12 = *(BackTraceCollection **)&hObject.Data1;
  if ( *(_QWORD *)&hObject.Data1 )
    CloseHandle(*(HANDLE *)&hObject.Data1);
  v6 = 0;
LABEL_17:
  if ( (unsigned int)dword_1800B3200 > 4 )
  {
    *(void **)&hObject.Data1 = v36[0];
    packageFamilyNameLength = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v12,
      (unsigned int)&word_1800AB5AE,
      v10,
      v11,
      (__int64)&packageFamilyNameLength,
      (__int64)&hObject);
  }
  if ( v6 >= 0 )
  {
    *a1 = 1;
    goto LABEL_49;
  }
  if ( v6 != -2147009196 )
  {
    BackTraceCollection::Capture(v12, v6);
    v18 = 606;
LABEL_22:
    Log_HREvent_31((unsigned int)v6, 0, v17, v18);
LABEL_49:
    if ( v36[0] != &v37 )
      operator delete(v36[0]);
    return (unsigned int)v6;
  }
  Pid = 0;
  v19 = I_RpcBindingInqLocalClientPID(0, &Pid);
  v6 = v19;
  if ( v19 )
  {
    if ( v19 > 0 )
      v6 = (unsigned __int16)v19 | 0x80070000;
    BackTraceCollection::Capture(v20, v6);
    v18 = 615;
    goto LABEL_22;
  }
  Block = &v43;
  v44 = 0;
  v42 = &v43;
  v45 = 0;
  v46 = 0;
  v43 = 0;
  RpcClientProcessPathNameFromProcessId = GetRpcClientProcessPathNameFromProcessId(Pid);
  v22 = (BackTraceCollection *)(unsigned int)dword_1800B3200;
  v6 = RpcClientProcessPathNameFromProcessId;
  if ( (unsigned int)dword_1800B3200 > 4 )
  {
    v23 = (WCHAR *)Block;
    packageFamilyNameLength = Pid;
    hObject.Data1 = v6;
    if ( Block )
    {
      do
        ++v5;
      while ( *((_WORD *)Block + v5) );
      v24 = 2 * v5 + 2;
    }
    else
    {
      v23 = (WCHAR *)&qword_18009A460;
      v24 = 2;
    }
    packageFamilyName.pwszURLReference = v23;
    packageFamilyName.dwProvFlags = v24;
    *(_QWORD *)&packageFamilyName.dwStateAction = &packageFamilyNameLength;
    packageFamilyName.dwUIContext = 0;
    *(_QWORD *)&packageFamilyName.dwUnionChoice = &hObject;
    packageFamilyName.hWVTStateData = (HANDLE)4;
    packageFamilyName.pFile = (struct WINTRUST_FILE_INFO_ *)4;
    tlgWriteTransfer_EventWriteTransfer(
      (int)&dword_1800B3200,
      (int)&word_1800AB612,
      0,
      0,
      5u,
      (PEVENT_DATA_DESCRIPTOR)&packageFamilyName);
  }
  if ( v6 < 0 )
  {
    BackTraceCollection::Capture(v22, v6);
    v26 = 627;
    goto LABEL_35;
  }
  v31[0] = 32;
  v32 = 0;
  memset_0(&packageFamilyName, 0, 0x58u);
  v31[1] = Block;
  *(_QWORD *)&hObject.Data1 = 0x11D0CD4400AAC56BLL;
  packageFamilyName.pFile = (struct WINTRUST_FILE_INFO_ *)v31;
  *(_DWORD *)hObject.Data4 = -1073692020;
  *(_DWORD *)&hObject.Data4[4] = -292175281;
  wcscpy((wchar_t *)&packageFamilyName, L"X");
  packageFamilyName.dwUIChoice = 2;
  packageFamilyName.dwStateAction = 1;
  packageFamilyName.fdwRevocationChecks = 1;
  packageFamilyName.dwProvFlags = 4160;
  packageFamilyName.dwUnionChoice = 1;
  v27 = WinVerifyTrust(0, &hObject, &packageFamilyName);
  v6 = v27;
  if ( v27 > 0 )
    v6 = (unsigned __int16)v27 | 0x80070000;
  if ( v6 >= 0 )
    v6 = ValidateSignedByMicrosoft(&packageFamilyName);
  packageFamilyName.dwStateAction = 2;
  WinVerifyTrust(0, &hObject, &packageFamilyName);
  if ( v6 < 0 )
  {
    BackTraceCollection::Capture(v28, v6);
    v26 = 629;
LABEL_35:
    Log_HREvent_31((unsigned int)v6, 1, v25, v26);
    if ( Block != &v43 )
      operator delete(Block);
    goto LABEL_49;
  }
  v29 = (__int16 *)Block;
  *a1 = 1;
  if ( v29 != &v43 )
    operator delete(v29);
  if ( v36[0] != &v37 )
    operator delete(v36[0]);
  return 0;
}

```

## disassembly

```asm
0x1800866d4  push    rbp
0x1800866d6  push    rbx
0x1800866d7  push    rsi
0x1800866d8  push    rdi
0x1800866d9  push    r14
0x1800866db  push    r15
0x1800866dd  lea     rbp, [rsp-58h]
0x1800866e2  sub     rsp, 158h
0x1800866e9  mov     rax, cs:__security_cookie
0x1800866f0  xor     rax, rsp
0x1800866f3  mov     [rbp+80h+var_40], rax
0x1800866f7  xor     r14d, r14d
0x1800866fa  lea     rax, [rbp+80h+var_100]
0x1800866fe  mov     [rsp+180h+var_110], rax
0x180086703  mov     rsi, rcx
0x180086706  lea     rax, [rbp+80h+var_100]
0x18008670a  mov     [rcx], r14b
0x18008670d  lea     rcx, [rsp+180h+hObject]
0x180086712  mov     [rsp+180h+var_108], rax
0x180086717  mov     [rbp+80h+var_FE], r14
0x18008671b  mov     [rbp+80h+var_F6], r14d
0x18008671f  mov     [rbp+80h+var_F2], r14w
0x180086724  mov     [rbp+80h+var_100], r14w
0x180086729  mov     [rsp+180h+hObject], r14
0x18008672e  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x180086733  mov     rdx, rax
0x180086736  lea     ecx, [r14+8]
0x18008673a  call    cs:__imp_?GetRpcClientThreadToken@@YAJKPEAPEAX@Z; GetRpcClientThreadToken(ulong,void * *)
0x180086740  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180086744  lea     r15d, [r14+1]
0x180086748  mov     ebx, eax
0x18008674a  test    eax, eax
0x18008674c  jns     short loc_18008677C
0x18008674e  mov     edx, eax; int
0x180086750  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180086755  lea     r9d, [r14+65h]
0x180086759  mov     edx, r15d
0x18008675c  mov     ecx, ebx
0x18008675e  call    Log_HREvent_31
0x180086763  mov     rcx, [rsp+180h+hObject]; hObject
0x180086768  test    rcx, rcx
0x18008676b  jz      loc_180086818
0x180086771  call    cs:__imp_CloseHandle
0x180086777  jmp     loc_180086818
0x18008677c  xor     edx, edx; Val
0x18008677e  lea     rcx, [rbp+80h+packageFamilyName]; void *
0x180086782  mov     r8d, 82h; Size
0x180086788  call    memset_0
0x18008678d  mov     rcx, [rsp+180h+hObject]; token
0x180086792  lea     r8, [rbp+80h+packageFamilyName]; packageFamilyName
0x180086796  lea     rdx, [rsp+180h+packageFamilyNameLength]; packageFamilyNameLength
0x18008679b  mov     [rsp+180h+packageFamilyNameLength], 41h ; 'A'
0x1800867a3  call    cs:__imp_GetPackageFamilyNameFromToken
0x1800867a9  mov     ebx, eax
0x1800867ab  test    eax, eax
0x1800867ad  jle     short loc_1800867B8
0x1800867af  movzx   ebx, ax
0x1800867b2  or      ebx, 80070000h
0x1800867b8  test    ebx, ebx
0x1800867ba  jns     short loc_1800867CB
0x1800867bc  mov     edx, ebx; int
0x1800867be  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800867c3  mov     r9d, 69h ; 'i'
0x1800867c9  jmp     short loc_180086759
0x1800867cb  lea     rax, [rbp+80h+packageFamilyName]
0x1800867cf  mov     r8, rdi
0x1800867d2  inc     r8
0x1800867d5  cmp     [rax+r8*2], r14w
0x1800867da  jnz     short loc_1800867D2
0x1800867dc  lea     rdx, [rbp+80h+packageFamilyName]
0x1800867e0  lea     rcx, [rsp+180h+var_110]
0x1800867e5  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800867ea  test    al, al
0x1800867ec  jnz     short loc_180086805
0x1800867ee  mov     ebx, 8007000Eh
0x1800867f3  mov     edx, ebx; int
0x1800867f5  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800867fa  xor     edx, edx
0x1800867fc  lea     r9d, [rdx+6Bh]
0x180086800  jmp     loc_18008675C
0x180086805  mov     rcx, [rsp+180h+hObject]; hObject
0x18008680a  test    rcx, rcx
0x18008680d  jz      short loc_180086815
0x18008680f  call    cs:__imp_CloseHandle
0x180086815  mov     ebx, r14d
0x180086818  mov     eax, cs:dword_1800B3200
0x18008681e  cmp     eax, 4
0x180086821  jbe     short loc_180086851
0x180086823  mov     rax, [rsp+180h+var_110]
0x180086828  lea     rdx, word_1800AB5AE
0x18008682f  mov     [rsp+180h+hObject], rax
0x180086834  lea     rax, [rsp+180h+hObject]
0x180086839  mov     [rsp+180h+var_158], rax
0x18008683e  lea     rax, [rsp+180h+packageFamilyNameLength]
0x180086843  mov     qword ptr [rsp+180h+var_160], rax
0x180086848  mov     [rsp+180h+packageFamilyNameLength], ebx
0x18008684c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180086851  test    ebx, ebx
0x180086853  jns     loc_180086AC1
0x180086859  cmp     ebx, 80073D54h
0x18008685f  jz      short loc_18008687C
0x180086861  mov     edx, ebx; int
0x180086863  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180086868  mov     r9d, 25Eh
0x18008686e  xor     edx, edx
0x180086870  mov     ecx, ebx
0x180086872  call    Log_HREvent_31
0x180086877  jmp     loc_180086AC4
0x18008687c  lea     rdx, [rsp+180h+Pid]; Pid
0x180086881  mov     [rsp+180h+Pid], r14d
0x180086886  xor     ecx, ecx; Binding
0x180086888  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18008688e  mov     ebx, eax
0x180086890  test    eax, eax
0x180086892  jz      short loc_1800868AE
0x180086894  jle     short loc_18008689F
0x180086896  movzx   ebx, ax
0x180086899  or      ebx, 80070000h
0x18008689f  mov     edx, ebx; int
0x1800868a1  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800868a6  mov     r9d, 267h
0x1800868ac  jmp     short loc_18008686E
0x1800868ae  mov     ecx, [rsp+180h+Pid]; dwProcessId
0x1800868b2  lea     rax, [rbp+80h+var_E0]
0x1800868b6  mov     [rbp+80h+Block], rax
0x1800868ba  lea     rdx, [rbp+80h+Block]
0x1800868be  lea     rax, [rbp+80h+var_E0]
0x1800868c2  mov     [rbp+80h+var_DE], r14
0x1800868c6  mov     [rbp+80h+var_E8], rax
0x1800868ca  mov     [rbp+80h+var_D6], r14d
0x1800868ce  mov     [rbp+80h+var_D2], r14w
0x1800868d3  mov     [rbp+80h+var_E0], r14w
0x1800868d8  call    ?GetRpcClientProcessPathNameFromProcessId@@YAJKPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetRpcClientProcessPathNameFromProcessId(ulong,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x1800868dd  mov     ecx, cs:dword_1800B3200
0x1800868e3  mov     ebx, eax
0x1800868e5  cmp     ecx, 4
0x1800868e8  jbe     loc_180086979
0x1800868ee  mov     rax, [rbp+80h+Block]
0x1800868f2  mov     ecx, [rsp+180h+Pid]
0x1800868f6  mov     [rsp+180h+packageFamilyNameLength], ecx
0x1800868fa  mov     dword ptr [rsp+180h+hObject], ebx
0x1800868fe  test    rax, rax
0x180086901  jz      short loc_180086916
0x180086903  inc     rdi
0x180086906  cmp     [rax+rdi*2], r14w
0x18008690b  jnz     short loc_180086903
0x18008690d  lea     edi, ds:2[rdi*2]
0x180086914  jmp     short loc_180086922
0x180086916  lea     rax, qword_18009A460
0x18008691d  mov     edi, 2
0x180086922  mov     [rbp+80h+var_90], rax
0x180086926  lea     rdx, word_1800AB612; int
0x18008692d  lea     rax, [rsp+180h+packageFamilyNameLength]
0x180086932  mov     [rbp+80h+var_88], edi
0x180086935  mov     [rbp+80h+var_A0], rax
0x180086939  lea     rcx, dword_1800B3200; int
0x180086940  lea     rax, [rsp+180h+hObject]
0x180086945  mov     [rbp+80h+var_84], r14d
0x180086949  mov     [rbp+80h+var_B0], rax
0x18008694d  xor     r9d, r9d; int
0x180086950  lea     rax, [rbp+80h+packageFamilyName]
0x180086954  mov     [rbp+80h+var_98], 4
0x18008695c  mov     [rsp+180h+var_158], rax; PEVENT_DATA_DESCRIPTOR
0x180086961  xor     r8d, r8d; int
0x180086964  mov     [rsp+180h+var_160], 5; ULONG
0x18008696c  mov     [rbp+80h+var_A8], 4
0x180086974  call    _tlgWriteTransfer_EventWriteTransfer
0x180086979  test    ebx, ebx
0x18008697b  jns     short loc_1800869B6
0x18008697d  mov     edx, ebx; int
0x18008697f  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180086984  mov     r9d, 273h
0x18008698a  mov     edx, r15d
0x18008698d  mov     ecx, ebx
0x18008698f  call    Log_HREvent_31
0x180086994  mov     rcx, [rbp+80h+Block]; Block
0x180086998  lea     rax, [rbp+80h+var_E0]
0x18008699c  cmp     rcx, rax
0x18008699f  jz      loc_180086AC4
0x1800869a5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800869ac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800869b1  jmp     loc_180086AC4
0x1800869b6  xorps   xmm0, xmm0
0x1800869b9  mov     [rsp+180h+var_150], 20h ; ' '
0x1800869c2  mov     ebx, 58h ; 'X'
0x1800869c7  lea     rcx, [rbp+80h+packageFamilyName]; void *
0x1800869cb  mov     r8d, ebx; Size
0x1800869ce  xor     edx, edx; Val
0x1800869d0  movdqu  [rsp+180h+var_140], xmm0
0x1800869d6  call    memset_0
0x1800869db  mov     rax, [rbp+80h+Block]
0x1800869df  lea     r8, [rbp+80h+packageFamilyName]; pWVTData
0x1800869e3  mov     [rsp+180h+var_148], rax
0x1800869e8  lea     rdx, [rsp+180h+hObject]; pgActionID
0x1800869ed  lea     rax, [rsp+180h+var_150]
0x1800869f2  mov     dword ptr [rsp+180h+hObject], 0AAC56Bh
0x1800869fa  xor     ecx, ecx; hwnd
0x1800869fc  mov     [rbp+80h+var_A8], rax
0x180086a00  mov     dword ptr [rsp+180h+hObject+4], 11D0CD44h
0x180086a08  mov     [rsp+180h+var_120], 0C000C28Ch
0x180086a10  mov     [rsp+180h+var_11C], 0EE95C24Fh
0x180086a18  mov     dword ptr [rbp+80h+packageFamilyName], ebx
0x180086a1b  mov     [rbp+80h+var_B8], 2
0x180086a22  mov     dword ptr [rbp+80h+var_A0], r15d
0x180086a26  mov     [rbp+80h+var_B4], r15d
0x180086a2a  mov     [rbp+80h+var_88], 1040h
0x180086a31  mov     dword ptr [rbp+80h+var_B0], r15d
0x180086a35  call    cs:__imp_WinVerifyTrust
0x180086a3b  mov     ebx, eax
0x180086a3d  test    eax, eax
0x180086a3f  jle     short loc_180086A4A
0x180086a41  movzx   ebx, ax
0x180086a44  or      ebx, 80070000h
0x180086a4a  test    ebx, ebx
0x180086a4c  js      short loc_180086A59
0x180086a4e  lea     rcx, [rbp+80h+packageFamilyName]; struct _WINTRUST_DATA *
0x180086a52  call    ?ValidateSignedByMicrosoft@@YAJAEAU_WINTRUST_DATA@@@Z; ValidateSignedByMicrosoft(_WINTRUST_DATA &)
0x180086a57  mov     ebx, eax
0x180086a59  lea     r8, [rbp+80h+packageFamilyName]; pWVTData
0x180086a5d  mov     dword ptr [rbp+80h+var_A0], 2
0x180086a64  lea     rdx, [rsp+180h+hObject]; pgActionID
0x180086a69  xor     ecx, ecx; hwnd
0x180086a6b  call    cs:__imp_WinVerifyTrust
0x180086a71  test    ebx, ebx
0x180086a73  jns     short loc_180086A87
0x180086a75  mov     edx, ebx; int
0x180086a77  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180086a7c  mov     r9d, 275h
0x180086a82  jmp     loc_18008698A
0x180086a87  mov     rcx, [rbp+80h+Block]; Block
0x180086a8b  lea     rax, [rbp+80h+var_E0]
0x180086a8f  mov     [rsi], r15b
0x180086a92  cmp     rcx, rax
0x180086a95  jz      short loc_180086AA3
0x180086a97  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180086a9e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180086aa3  mov     rcx, [rsp+180h+var_110]; Block
0x180086aa8  lea     rax, [rbp+80h+var_100]
0x180086aac  cmp     rcx, rax
0x180086aaf  jz      short loc_180086ABD
0x180086ab1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180086ab8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180086abd  xor     eax, eax
0x180086abf  jmp     short loc_180086AE0
0x180086ac1  mov     [rsi], r15b
0x180086ac4  mov     rcx, [rsp+180h+var_110]; Block
0x180086ac9  lea     rax, [rbp+80h+var_100]
0x180086acd  cmp     rcx, rax
0x180086ad0  jz      short loc_180086ADE
0x180086ad2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180086ad9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180086ade  mov     eax, ebx
0x180086ae0  mov     rcx, [rbp+80h+var_40]
0x180086ae4  xor     rcx, rsp; StackCookie
0x180086ae7  call    __security_check_cookie
0x180086aec  add     rsp, 158h
0x180086af3  pop     r15
0x180086af5  pop     r14
0x180086af7  pop     rdi
0x180086af8  pop     rsi
0x180086af9  pop     rbx
0x180086afa  pop     rbp
0x180086afb  retn
```
