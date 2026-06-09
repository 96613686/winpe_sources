# CFCAcquirerLocalRepository::CopyDeploymentBinaries(ushort const *)

- ea: `0x180296520`
- end: `0x1802968fa`
- name: `?CopyDeploymentBinaries@CFCAcquirerLocalRepository@@UEAAJPEBG@Z`
- size: `986`
- prototype: `__int64 __fastcall(CFCAcquirerLocalRepository *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18003f950`
- `0x1800d986c`
- `0x1800eb920`
- `0x1801f15e4`
- `0x1801f17f8`
- `0x1802960ec`
- `0x180296168`
- `0x180296520`
- `0x180297084`
- `0x180298470`
- `0x180299100`
- `0x1802997dc`
- `0x18029a754`
- `0x1802b8548`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1802966e6`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1802966e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802966f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180296734`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180296869`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802966f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180296734`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180296869`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x180296859`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x180296859`

## string_xrefs

- `0x180296610`: `UpdateAgent.dll`
- `0x180296638`: `UpdateAgent.dll`
- `0x1802966b2`: `UpdateAgent.dll`
- `0x1802967a5`: `UpdateAgent.dll`
- `0x180296802`: `UpdateAgent.dll`
- `0x180296833`: `UpdateAgent.dll`
- `0x180296764`: `FCAcquirerLocalRepository: Module DLL Path: %ws`
- `0x180296688`: `FCAcquirerLocalRepository: Couldn't find media UpdateAgent path: %ws`
- `0x18029683a`: `FCAcquirerLocalRepository: Copying %ws from [%ws] to [%ws]`
- `0x180296617`: `FCAcquirerLocalRepository: Searching %ws in local UpdateAgent path [%ws]`
- `0x1802968a0`: `CFCAcquirerLocalRepository::CopyDeploymentBinaries`

## pseudocode

```c
__int64 __fastcall CFCAcquirerLocalRepository::CopyDeploymentBinaries(
        CFCAcquirerLocalRepository *this,
        const unsigned __int16 *a2)
{
  bool v3; // zf
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // eax
  __int64 v10; // rcx
  const WCHAR *v11; // rsi
  __int64 v12; // rcx
  DWORD LastError; // eax
  unsigned __int16 *v14; // rbx
  DWORD v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  const WCHAR *v18; // rbx
  DWORD v19; // eax
  int v21; // [rsp+30h] [rbp-40h] BYREF
  int v22; // [rsp+34h] [rbp-3Ch] BYREF
  LPCWSTR lpNewFileName; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int16 *v24; // [rsp+40h] [rbp-30h] BYREF
  HMODULE phModule; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+50h] [rbp-20h] BYREF
  __int64 v27; // [rsp+58h] [rbp-18h] BYREF

  v3 = (*((_BYTE *)this - 68) & 8) == 0;
  phModule = 0;
  v24 = 0;
  v27 = 0;
  lpExistingFileName = 0;
  lpNewFileName = 0;
  v21 = 0;
  v22 = 0;
  if ( v3 )
  {
    if ( !a2 )
    {
      v6 = *((_QWORD *)this - 1);
      v5 = -2147024809;
      v7 = 2147942487LL;
      v8 = 228;
LABEL_50:
      CFCLogLiteT<CEmptyType>::LogError(v6, v7, L"CFCAcquirerLocalRepository::CopyDeploymentBinaries", v8);
      goto LABEL_51;
    }
    v9 = CMiscHelpersT<CEmptyType>::DirectoryExists(a2, &v21);
    v5 = v9;
    if ( v9 < 0 )
    {
      v8 = 229;
LABEL_48:
      v7 = (unsigned int)v9;
      goto LABEL_49;
    }
    if ( !v21 )
    {
      v7 = 2147942403LL;
      v8 = 230;
      v5 = -2147024893;
LABEL_49:
      v6 = *((_QWORD *)this - 1);
      goto LABEL_50;
    }
    v10 = *((_QWORD *)this + 2);
    if ( v10 )
    {
      v9 = CMiscHelpersT<CEmptyType>::DirectoryExists(v10, &v21);
      v5 = v9;
      if ( v9 < 0 )
      {
        v8 = 236;
        goto LABEL_48;
      }
      v6 = *((_QWORD *)this - 1);
      if ( !v21 )
      {
        v7 = 2147942403LL;
        v8 = 237;
        v5 = -2147024893;
        goto LABEL_50;
      }
      if ( v6 )
        CFCLogLiteT<CEmptyType>::LogFormat(
          v6,
          2,
          L"FCAcquirerLocalRepository: Searching %ws in local UpdateAgent path [%ws]",
          L"UpdateAgent.dll",
          *((_QWORD *)this + 2));
      v9 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 2), L"UpdateAgent.dll", 0, &lpExistingFileName);
      v5 = v9;
      if ( v9 < 0 )
      {
        v8 = 241;
        goto LABEL_48;
      }
      v11 = lpExistingFileName;
      v9 = CMiscHelpersT<CEmptyType>::FileExists(lpExistingFileName, &v22);
      v5 = v9;
      if ( v9 < 0 )
      {
        v8 = 242;
        goto LABEL_48;
      }
      if ( !v22 )
      {
        v12 = *((_QWORD *)this - 1);
        if ( v12 )
          CFCLogLiteT<CEmptyType>::LogFormat(
            v12,
            4,
            L"FCAcquirerLocalRepository: Couldn't find media UpdateAgent path: %ws",
            v11);
        v7 = 2147942402LL;
        v8 = 247;
        v5 = -2147024894;
        goto LABEL_49;
      }
      v9 = CMiscHelpersT<CEmptyType>::CombinePath(a2, L"UpdateAgent.dll", 0, &lpNewFileName);
      v5 = v9;
      if ( v9 < 0 )
      {
        v8 = 250;
        goto LABEL_48;
      }
    }
    else
    {
      if ( !GetModuleHandleExW(6u, (LPCWSTR)CFCAcquirerLocalRepository::Create, &phModule) )
      {
        LastError = GetLastError();
        v9 = SErrorConverter::C_LR2HR(LastError);
        v5 = v9;
        v8 = 258;
        goto LABEL_48;
      }
      v14 = (unsigned __int16 *)FormModuleFullPathName(phModule);
      SP<unsigned short,SP_WDS<unsigned short>>::Reset(&v24);
      if ( !v14 )
      {
        v24 = 0;
        v15 = GetLastError();
        v9 = SErrorConverter::C_LR2HR(v15);
        v5 = v9;
        v8 = 263;
        goto LABEL_48;
      }
      v16 = *((_QWORD *)this - 1);
      v24 = v14;
      if ( v16 )
        CFCLogLiteT<CEmptyType>::LogFormat(v16, 2, L"FCAcquirerLocalRepository: Module DLL Path: %ws", v14);
      v9 = CMiscHelpersT<CEmptyType>::ParseFileName(v14, 0);
      v5 = v9;
      if ( v9 < 0 )
      {
        v8 = 268;
        goto LABEL_48;
      }
      v9 = CMiscHelpersT<CEmptyType>::CombinePath(v27, L"UpdateAgent.dll", 0, &lpExistingFileName);
      v5 = v9;
      if ( v9 < 0 )
      {
        v8 = 269;
        goto LABEL_48;
      }
      v11 = lpExistingFileName;
      v9 = CMiscHelpersT<CEmptyType>::FileExists(lpExistingFileName, &v22);
      v5 = v9;
      if ( v9 < 0 )
      {
        v8 = 270;
        goto LABEL_48;
      }
      if ( !v22 )
      {
        v7 = 2147942402LL;
        v8 = 271;
        v5 = -2147024894;
        goto LABEL_49;
      }
    }
    v17 = CMiscHelpersT<CEmptyType>::CombinePath(a2, L"UpdateAgent.dll", 0, &lpNewFileName);
    v6 = *((_QWORD *)this - 1);
    v5 = v17;
    if ( v17 < 0 )
    {
      v8 = 274;
      v7 = (unsigned int)v17;
      goto LABEL_50;
    }
    v18 = lpNewFileName;
    if ( v6 )
      CFCLogLiteT<CEmptyType>::LogFormat(
        v6,
        2,
        L"FCAcquirerLocalRepository: Copying %ws from [%ws] to [%ws]",
        L"UpdateAgent.dll",
        v11,
        lpNewFileName);
    if ( CopyFileW(v11, v18, 0) )
    {
      v9 = CMiscHelpersT<CEmptyType>::CheckAndClearFileAttribute(v18);
      v5 = v9;
      if ( v9 >= 0 )
        goto LABEL_51;
      v8 = 279;
    }
    else
    {
      v19 = GetLastError();
      v9 = SErrorConverter::C_LR2HR(v19);
      v5 = v9;
      v8 = 278;
    }
    goto LABEL_48;
  }
  v5 = 0;
LABEL_51:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  SH<unsigned short *,SH_SSTRING>::Reset(&lpNewFileName);
  SH<unsigned short *,SH_SSTRING>::Reset(&lpExistingFileName);
  SH<unsigned short *,SH_SSTRING>::Reset(&v27);
  SP<unsigned short,SP_WDS<unsigned short>>::Reset(&v24);
  return v5;
}

```

## disassembly

```asm
0x180296520  mov     [rsp-28h+arg_10], rbx
0x180296525  push    rbp
0x180296526  push    rsi
0x180296527  push    rdi
0x180296528  push    r12
0x18029652a  push    r15
0x18029652c  mov     rbp, rsp
0x18029652f  sub     rsp, 70h
0x180296533  mov     rax, cs:__security_cookie
0x18029653a  xor     rax, rsp
0x18029653d  mov     [rbp+var_10], rax
0x180296541  xor     r12d, r12d
0x180296544  mov     r15, rdx
0x180296547  test    byte ptr [rcx-44h], 8
0x18029654b  mov     rdi, rcx
0x18029654e  mov     [rbp+phModule], r12
0x180296552  mov     [rbp+var_30], r12
0x180296556  mov     [rbp+var_18], r12
0x18029655a  mov     [rbp+lpExistingFileName], r12
0x18029655e  mov     [rbp+lpNewFileName], r12
0x180296562  mov     [rbp+var_40], r12d
0x180296566  mov     [rbp+var_3C], r12d
0x18029656a  jz      short loc_180296574
0x18029656c  mov     ebx, r12d
0x18029656f  jmp     loc_1802968AC
0x180296574  test    r15, r15
0x180296577  jnz     short loc_18029658F
0x180296579  mov     rcx, [rcx-8]
0x18029657d  mov     ebx, 80070057h
0x180296582  mov     edx, ebx
0x180296584  mov     r9d, 0E4h
0x18029658a  jmp     loc_1802968A0
0x18029658f  lea     rdx, [rbp+var_40]
0x180296593  mov     rcx, r15
0x180296596  call    ?DirectoryExists@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAH@Z; CMiscHelpersT<CEmptyType>::DirectoryExists(ushort const *,int *)
0x18029659b  mov     ebx, eax
0x18029659d  test    eax, eax
0x18029659f  jns     short loc_1802965AC
0x1802965a1  mov     r9d, 0E5h
0x1802965a7  jmp     loc_18029689A
0x1802965ac  cmp     [rbp+var_40], r12d
0x1802965b0  jnz     short loc_1802965C4
0x1802965b2  mov     edx, 80070003h
0x1802965b7  mov     r9d, 0E6h
0x1802965bd  mov     ebx, edx
0x1802965bf  jmp     loc_18029689C
0x1802965c4  mov     rcx, [rdi+10h]
0x1802965c8  test    rcx, rcx
0x1802965cb  jz      loc_1802966D6
0x1802965d1  lea     rdx, [rbp+var_40]
0x1802965d5  call    ?DirectoryExists@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAH@Z; CMiscHelpersT<CEmptyType>::DirectoryExists(ushort const *,int *)
0x1802965da  mov     ebx, eax
0x1802965dc  test    eax, eax
0x1802965de  jns     short loc_1802965EB
0x1802965e0  mov     r9d, 0ECh
0x1802965e6  jmp     loc_18029689A
0x1802965eb  mov     rcx, [rdi-8]
0x1802965ef  cmp     [rbp+var_40], r12d
0x1802965f3  jnz     short loc_180296607
0x1802965f5  mov     edx, 80070003h
0x1802965fa  mov     r9d, 0EDh
0x180296600  mov     ebx, edx
0x180296602  jmp     loc_1802968A0
0x180296607  test    rcx, rcx
0x18029660a  jz      short loc_18029662D
0x18029660c  mov     rax, [rdi+10h]
0x180296610  lea     r9, aUpdateagentDll_1; "UpdateAgent.dll"
0x180296617  lea     r8, aFcacquirerloca_1; "FCAcquirerLocalRepository: Searching %w"...
0x18029661e  mov     [rsp+70h+var_50], rax
0x180296623  mov     edx, 2
0x180296628  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x18029662d  mov     rcx, [rdi+10h]
0x180296631  lea     r9, [rbp+lpExistingFileName]
0x180296635  xor     r8d, r8d
0x180296638  lea     rdx, aUpdateagentDll_1; "UpdateAgent.dll"
0x18029663f  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180296644  mov     ebx, eax
0x180296646  test    eax, eax
0x180296648  jns     short loc_180296655
0x18029664a  mov     r9d, 0F1h
0x180296650  jmp     loc_18029689A
0x180296655  mov     rsi, [rbp+lpExistingFileName]
0x180296659  lea     rdx, [rbp+var_3C]
0x18029665d  mov     rcx, rsi
0x180296660  call    ?FileExists@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAH@Z; CMiscHelpersT<CEmptyType>::FileExists(ushort const *,int *)
0x180296665  mov     ebx, eax
0x180296667  test    eax, eax
0x180296669  jns     short loc_180296676
0x18029666b  mov     r9d, 0F2h
0x180296671  jmp     loc_18029689A
0x180296676  cmp     [rbp+var_3C], r12d
0x18029667a  jnz     short loc_1802966AB
0x18029667c  mov     rcx, [rdi-8]
0x180296680  test    rcx, rcx
0x180296683  jz      short loc_180296699
0x180296685  mov     r9, rsi
0x180296688  lea     r8, aFcacquirerloca; "FCAcquirerLocalRepository: Couldn't fin"...
0x18029668f  mov     edx, 4
0x180296694  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180296699  mov     edx, 80070002h
0x18029669e  mov     r9d, 0F7h
0x1802966a4  mov     ebx, edx
0x1802966a6  jmp     loc_18029689C
0x1802966ab  lea     r9, [rbp+lpNewFileName]
0x1802966af  xor     r8d, r8d
0x1802966b2  lea     rdx, aUpdateagentDll_1; "UpdateAgent.dll"
0x1802966b9  mov     rcx, r15
0x1802966bc  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x1802966c1  mov     ebx, eax
0x1802966c3  test    eax, eax
0x1802966c5  jns     loc_1802967FB
0x1802966cb  mov     r9d, 0FAh
0x1802966d1  jmp     loc_18029689A
0x1802966d6  lea     r8, [rbp+phModule]; phModule
0x1802966da  mov     ecx, 6; dwFlags
0x1802966df  lea     rdx, ?Create@CFCAcquirerLocalRepository@@SAJPEAPEAVIFCAcquirerLocalRepository@@@Z; lpModuleName
0x1802966e6  call    cs:__imp_GetModuleHandleExW
0x1802966ed  nop     dword ptr [rax+rax+00h]
0x1802966f2  test    eax, eax
0x1802966f4  jnz     short loc_180296716
0x1802966f6  call    cs:__imp_GetLastError
0x1802966fd  nop     dword ptr [rax+rax+00h]
0x180296702  mov     ecx, eax; unsigned int
0x180296704  call    ?C_LR2HR@SErrorConverter@@SAJK@Z; SErrorConverter::C_LR2HR(ulong)
0x180296709  mov     ebx, eax
0x18029670b  mov     r9d, 102h
0x180296711  jmp     loc_18029689A
0x180296716  mov     rcx, [rbp+phModule]; hModule
0x18029671a  call    FormModuleFullPathName
0x18029671f  lea     rcx, [rbp+var_30]
0x180296723  mov     rbx, rax
0x180296726  call    ?Reset@?$SP@GV?$SP_WDS@G@@@@QEAAXXZ; SP<ushort,SP_WDS<ushort>>::Reset(void)
0x18029672b  test    rbx, rbx
0x18029672e  jnz     short loc_180296754
0x180296730  mov     [rbp+var_30], r12
0x180296734  call    cs:__imp_GetLastError
0x18029673b  nop     dword ptr [rax+rax+00h]
0x180296740  mov     ecx, eax; unsigned int
0x180296742  call    ?C_LR2HR@SErrorConverter@@SAJK@Z; SErrorConverter::C_LR2HR(ulong)
0x180296747  mov     ebx, eax
0x180296749  mov     r9d, 107h
0x18029674f  jmp     loc_18029689A
0x180296754  mov     rcx, [rdi-8]
0x180296758  mov     [rbp+var_30], rbx
0x18029675c  test    rcx, rcx
0x18029675f  jz      short loc_180296775
0x180296761  mov     r9, rbx
0x180296764  lea     r8, aFcacquirerloca_4; "FCAcquirerLocalRepository: Module DLL P"...
0x18029676b  mov     edx, 2
0x180296770  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180296775  xor     r9d, r9d
0x180296778  mov     [rsp+70h+var_50], r12; __int64
0x18029677d  lea     r8, [rbp+var_18]
0x180296781  mov     rcx, rbx; Src
0x180296784  call    ?ParseFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAHPEAPEAG22@Z; CMiscHelpersT<CEmptyType>::ParseFileName(ushort const *,int *,ushort * *,ushort * *,ushort * *)
0x180296789  mov     ebx, eax
0x18029678b  test    eax, eax
0x18029678d  jns     short loc_18029679A
0x18029678f  mov     r9d, 10Ch
0x180296795  jmp     loc_18029689A
0x18029679a  mov     rcx, [rbp+var_18]
0x18029679e  lea     r9, [rbp+lpExistingFileName]
0x1802967a2  xor     r8d, r8d
0x1802967a5  lea     rdx, aUpdateagentDll_1; "UpdateAgent.dll"
0x1802967ac  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x1802967b1  mov     ebx, eax
0x1802967b3  test    eax, eax
0x1802967b5  jns     short loc_1802967C2
0x1802967b7  mov     r9d, 10Dh
0x1802967bd  jmp     loc_18029689A
0x1802967c2  mov     rsi, [rbp+lpExistingFileName]
0x1802967c6  lea     rdx, [rbp+var_3C]
0x1802967ca  mov     rcx, rsi
0x1802967cd  call    ?FileExists@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAH@Z; CMiscHelpersT<CEmptyType>::FileExists(ushort const *,int *)
0x1802967d2  mov     ebx, eax
0x1802967d4  test    eax, eax
0x1802967d6  jns     short loc_1802967E3
0x1802967d8  mov     r9d, 10Eh
0x1802967de  jmp     loc_18029689A
0x1802967e3  cmp     [rbp+var_3C], r12d
0x1802967e7  jnz     short loc_1802967FB
0x1802967e9  mov     edx, 80070002h
0x1802967ee  mov     r9d, 10Fh
0x1802967f4  mov     ebx, edx
0x1802967f6  jmp     loc_18029689C
0x1802967fb  lea     r9, [rbp+lpNewFileName]
0x1802967ff  xor     r8d, r8d
0x180296802  lea     rdx, aUpdateagentDll_1; "UpdateAgent.dll"
0x180296809  mov     rcx, r15
0x18029680c  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180296811  mov     rcx, [rdi-8]
0x180296815  mov     ebx, eax
0x180296817  test    eax, eax
0x180296819  jns     short loc_180296825
0x18029681b  mov     r9d, 112h
0x180296821  mov     edx, eax
0x180296823  jmp     short loc_1802968A0
0x180296825  mov     rbx, [rbp+lpNewFileName]
0x180296829  test    rcx, rcx
0x18029682c  jz      short loc_180296850
0x18029682e  mov     [rsp+70h+var_48], rbx
0x180296833  lea     r9, aUpdateagentDll_1; "UpdateAgent.dll"
0x18029683a  lea     r8, aFcacquirerloca_7; "FCAcquirerLocalRepository: Copying %ws "...
0x180296841  mov     [rsp+70h+var_50], rsi
0x180296846  mov     edx, 2
0x18029684b  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180296850  xor     r8d, r8d; bFailIfExists
0x180296853  mov     rdx, rbx; lpNewFileName
0x180296856  mov     rcx, rsi; lpExistingFileName
0x180296859  call    cs:__imp_CopyFileW
0x180296860  nop     dword ptr [rax+rax+00h]
0x180296865  test    eax, eax
0x180296867  jnz     short loc_180296886
0x180296869  call    cs:__imp_GetLastError
0x180296870  nop     dword ptr [rax+rax+00h]
0x180296875  mov     ecx, eax; unsigned int
0x180296877  call    ?C_LR2HR@SErrorConverter@@SAJK@Z; SErrorConverter::C_LR2HR(ulong)
0x18029687c  mov     ebx, eax
0x18029687e  mov     r9d, 116h
0x180296884  jmp     short loc_18029689A
0x180296886  mov     rcx, rbx; lpFileName
0x180296889  call    ?CheckAndClearFileAttribute@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGK@Z; CMiscHelpersT<CEmptyType>::CheckAndClearFileAttribute(ushort const *,ulong)
0x18029688e  mov     ebx, eax
0x180296890  test    eax, eax
0x180296892  jns     short loc_1802968AC
0x180296894  mov     r9d, 117h
0x18029689a  mov     edx, eax
0x18029689c  mov     rcx, [rdi-8]
0x1802968a0  lea     r8, aCfcacquirerloc_4; "CFCAcquirerLocalRepository::CopyDeploym"...
0x1802968a7  call    ?LogError@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@JPEBGK@Z; CFCLogLiteT<CEmptyType>::LogError(IFCDiagnosticsLite *,long,ushort const *,ulong)
0x1802968ac  mov     ecx, ebx
0x1802968ae  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1802968b3  lea     rcx, [rbp+lpNewFileName]
0x1802968b7  call    ?Reset@?$SH@PEAGVSH_SSTRING@@@@QEAAXXZ; SH<ushort *,SH_SSTRING>::Reset(void)
0x1802968bc  lea     rcx, [rbp+lpExistingFileName]
0x1802968c0  call    ?Reset@?$SH@PEAGVSH_SSTRING@@@@QEAAXXZ; SH<ushort *,SH_SSTRING>::Reset(void)
0x1802968c5  lea     rcx, [rbp+var_18]
0x1802968c9  call    ?Reset@?$SH@PEAGVSH_SSTRING@@@@QEAAXXZ; SH<ushort *,SH_SSTRING>::Reset(void)
0x1802968ce  lea     rcx, [rbp+var_30]
0x1802968d2  call    ?Reset@?$SP@GV?$SP_WDS@G@@@@QEAAXXZ; SP<ushort,SP_WDS<ushort>>::Reset(void)
0x1802968d7  mov     eax, ebx
0x1802968d9  mov     rcx, [rbp+var_10]
0x1802968dd  xor     rcx, rsp; StackCookie
0x1802968e0  call    __security_check_cookie
0x1802968e5  mov     rbx, [rsp+70h+arg_10]
0x1802968ed  add     rsp, 70h
0x1802968f1  pop     r15
0x1802968f3  pop     r12
0x1802968f5  pop     rdi
0x1802968f6  pop     rsi
0x1802968f7  pop     rbp
0x1802968f8  retn
```
