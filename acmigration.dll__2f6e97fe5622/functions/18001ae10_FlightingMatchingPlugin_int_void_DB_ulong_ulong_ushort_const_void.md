# FlightingMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x18001ae10`
- end: `0x18001b5f5`
- name: `?FlightingMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `2021`
- prototype: `__int64 __usercall@<rax>(AppCompatUtility *this@<rcx>, void *@<rdx>, struct _DB *@<r8>, unsigned int@<r9d>, unsigned int, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001cf0`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000c190`
- `0x18000e064`
- `0x18001ae10`
- `0x18001b5fc`
- `0x18003f0b0`
- `0x18003fa7c`
- `0x180040148`
- `0x1800543c0`
- `0x180065120`
- `0x180065150`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001b516`
- `KERNEL32!LocalFree` at `0x18001b516`
- `KERNEL32!GetLastError` at `0x18001b4ad`
- `KERNEL32!GetLastError` at `0x18001b4ad`
- `ole32!CoTaskMemFree` at `0x18001b526`
- `ole32!CoTaskMemFree` at `0x18001b53b`
- `ole32!CoTaskMemFree` at `0x18001b526`
- `ole32!CoTaskMemFree` at `0x18001b53b`
- `SHELL32!CommandLineToArgvW` at `0x18001aff0`
- `SHELL32!CommandLineToArgvW` at `0x18001aff0`

## string_xrefs

- `0x18001b59b`: `CommandLine is null/empty`
- `0x18001b4c0`: `CommandLineToArgvW failed %d, %ws, numArgs=%d`
- `0x18001ae8a`: `Enter FlightingMatchingPlugin`
- `0x18001ae97`: `FlightingMatchingPlugin`
- `0x18001b4fd`: `FlightingMatchingPlugin`
- `0x18001aecb`: `Commandline: %ws`
- `0x18001af52`: `FlightingMatchingPlugin `
- `0x18001af67`: `FlightingMatchingPlugin `
- `0x18001b236`: `GetFlightingConfigValues failed 0x%x`
- `0x18001b57f`: `FlightingMatchingPlugin Matched = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall FlightingMatchingPlugin(
        AppCompatUtility *this,
        void *a2,
        struct _DB *a3,
        __int64 a4,
        unsigned int a5,
        WCHAR *lpCmdLine,
        void *a7)
{
  unsigned int v8; // r9d
  int *v9; // rdx
  LPWSTR *v11; // r13
  int v12; // ebx
  AppCompatUtility *v13; // rbx
  int v14; // r14d
  __int64 v15; // r12
  const wchar_t *v16; // rbx
  LPWSTR v17; // r9
  unsigned __int64 v18; // rdx
  void **v19; // rdi
  __int64 v20; // rbx
  __int128 *v21; // rcx
  void **v22; // rax
  unsigned __int16 **v23; // rdx
  unsigned __int16 **p_pv; // rcx
  int FlightingConfigValues; // eax
  const OLECHAR *v26; // rbx
  const OLECHAR *v27; // rdx
  __int64 v28; // r8
  int v29; // edi
  int v30; // ebx
  unsigned int v31; // r9d
  void **v32; // rdx
  __int64 v33; // [rsp+20h] [rbp-128h]
  int v34; // [rsp+30h] [rbp-118h]
  int pNumArgs; // [rsp+40h] [rbp-108h] BYREF
  AppCompatUtility *v36; // [rsp+48h] [rbp-100h]
  LPVOID pv; // [rsp+50h] [rbp-F8h] BYREF
  LPVOID v38; // [rsp+58h] [rbp-F0h] BYREF
  LPWSTR *v39; // [rsp+60h] [rbp-E8h]
  AppCompatUtility *v40; // [rsp+68h] [rbp-E0h]
  __int64 v41; // [rsp+70h] [rbp-D8h]
  __int128 v42; // [rsp+78h] [rbp-D0h] BYREF
  unsigned __int64 v43; // [rsp+88h] [rbp-C0h]
  unsigned __int64 v44; // [rsp+90h] [rbp-B8h]
  void *v45[2]; // [rsp+98h] [rbp-B0h] BYREF
  unsigned __int64 v46; // [rsp+A8h] [rbp-A0h]
  unsigned __int64 v47; // [rsp+B0h] [rbp-98h]
  void *Src[2]; // [rsp+B8h] [rbp-90h] BYREF
  __int64 v49; // [rsp+C8h] [rbp-80h]
  unsigned __int64 v50; // [rsp+D0h] [rbp-78h]
  __int128 v51; // [rsp+D8h] [rbp-70h] BYREF
  __int128 v52; // [rsp+E8h] [rbp-60h]
  __int128 v53; // [rsp+F8h] [rbp-50h] BYREF
  __int128 v54; // [rsp+108h] [rbp-40h]

  v41 = -2;
  v36 = this;
  v40 = this;
  pv = 0;
  v38 = 0;
  pNumArgs = 0;
  *(_OWORD *)Src = 0;
  v49 = 0;
  v50 = 7;
  LOWORD(Src[0]) = 0;
  AslLogCallPrintf(3, "FlightingMatchingPlugin", 163, "Enter FlightingMatchingPlugin");
  *(_DWORD *)this = 0;
  if ( !lpCmdLine || !*lpCmdLine )
  {
    AslLogCallPrintf(1, "FlightingMatchingPlugin", 168, "CommandLine is null/empty");
    goto LABEL_73;
  }
  v39 = 0;
  AslLogCallPrintf(3, "FlightingMatchingPlugin", 172, "Commandline: %ws", lpCmdLine);
  *(_OWORD *)v45 = 0;
  v46 = 0;
  v47 = 7;
  LOWORD(v45[0]) = 0;
  v42 = 0;
  v43 = 0;
  v44 = 7;
  LOWORD(v42) = 0;
  if ( v50 < 0x18 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(Src);
  }
  else
  {
    v49 = 24;
    memmove_0(Src[0], L"FlightingMatchingPlugin ", 0x30u);
    *((_WORD *)Src[0] + 24) = 0;
  }
  std::wstring::append(Src, lpCmdLine);
  v9 = (int *)Src;
  if ( v50 > 7 )
    v9 = (int *)Src[0];
  if ( (unsigned int)AppCompatUtility::CheckCacheMatchingPlugin(this, v9, (const unsigned __int16 *)a5, v8) )
  {
    std::wstring::~wstring(&v42);
    std::wstring::~wstring(v45);
    std::wstring::~wstring(Src);
    return 1;
  }
  v11 = CommandLineToArgvW(lpCmdLine, &pNumArgs);
  v39 = v11;
  v12 = pNumArgs;
  if ( !v11 || pNumArgs < 2 )
  {
    v34 = pNumArgs;
    LODWORD(v33) = GetLastError();
    AslLogCallPrintf(
      1,
      "FlightingMatchingPlugin",
      194,
      "CommandLineToArgvW failed %d, %ws, numArgs=%d",
      v33,
      lpCmdLine,
      v34);
    std::wstring::~wstring(&v42);
    std::wstring::~wstring(v45);
    v13 = v36;
    if ( v11 )
      goto LABEL_62;
    goto LABEL_63;
  }
  if ( (pNumArgs & 1) != 0 )
  {
    AslLogCallPrintf(1, "FlightingMatchingPlugin", 200, "Wrong arguments number: %d", pNumArgs);
    std::wstring::~wstring(&v42);
    std::wstring::~wstring(v45);
    v13 = v36;
    goto LABEL_62;
  }
  v14 = 0;
  v15 = -1;
  while ( v14 < v12 - 1 )
  {
    v16 = v11[v14];
    if ( !wcscmp_0(L"-FlightingRing", v16) )
    {
      v17 = v11[v14 + 1];
      v18 = -1;
      do
        ++v18;
      while ( v17[v18] );
      if ( v18 > v47 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v45);
        goto LABEL_33;
      }
      v19 = v45;
      if ( v47 > 7 )
        v19 = (void **)v45[0];
      v46 = v18;
      goto LABEL_31;
    }
    if ( wcscmp_0(L"-FlightingBranch", v16) )
    {
      AslLogCallPrintf(1, "FlightingMatchingPlugin", 216, "Unknown switch: %ws", v16);
      std::wstring::~wstring(&v42);
      std::wstring::~wstring(v45);
      v13 = v36;
      goto LABEL_62;
    }
    v17 = v11[v14 + 1];
    v18 = -1;
    do
      ++v18;
    while ( v17[v18] );
    if ( v18 <= v44 )
    {
      v19 = (void **)&v42;
      if ( v44 > 7 )
        v19 = (void **)v42;
      v43 = v18;
LABEL_31:
      v20 = 2 * v18;
      memmove_0(v19, v17, 2 * v18);
      *(_WORD *)((char *)v19 + v20) = 0;
      goto LABEL_33;
    }
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(&v42);
LABEL_33:
    v14 += 2;
    v12 = pNumArgs;
  }
  v21 = &v42;
  if ( v44 > 7 )
    v21 = (__int128 *)v42;
  v22 = v45;
  if ( v47 > 7 )
    v22 = (void **)v45[0];
  AslLogCallPrintf(3, "FlightingMatchingPlugin", 220, "Ring:%ws; Branch:%ws", v22, v21);
  v23 = (unsigned __int16 **)&v38;
  if ( !v43 )
    v23 = 0;
  p_pv = (unsigned __int16 **)&pv;
  if ( !v46 )
    p_pv = 0;
  FlightingConfigValues = GetFlightingConfigValues(p_pv, v23);
  if ( FlightingConfigValues )
  {
    AslLogCallPrintf(3, "FlightingMatchingPlugin", 225, "GetFlightingConfigValues failed 0x%x", FlightingConfigValues);
    std::wstring::~wstring(&v42);
    std::wstring::~wstring(v45);
    v13 = v36;
    goto LABEL_62;
  }
  if ( v46 )
  {
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v53, L"eq", 2);
    v26 = &psz;
    v27 = &psz;
    if ( pv )
      v27 = (const OLECHAR *)pv;
    v51 = 0;
    v52 = 0;
    v28 = -1;
    do
      ++v28;
    while ( v27[v28] );
    std::wstring::_Construct<1,unsigned short const *>(&v51, v27, v28);
    v29 = AppCompatUtility::CompareStr(&v51, v45, &v53);
    std::wstring::~wstring(&v51);
    std::wstring::~wstring(&v53);
    if ( !v29 )
    {
      AslLogCallPrintf(3, "FlightingMatchingPlugin", 233, "Ring does not match, actual ring: %ws", pv);
      std::wstring::~wstring(&v42);
      std::wstring::~wstring(v45);
      v13 = v36;
      goto LABEL_62;
    }
  }
  else
  {
    v26 = &psz;
  }
  if ( !v43 )
    goto LABEL_60;
  v51 = 0;
  v52 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v51, L"eq", 2);
  if ( v38 )
    v26 = (const OLECHAR *)v38;
  v53 = 0;
  v54 = 0;
  do
    ++v15;
  while ( v26[v15] );
  std::wstring::_Construct<1,unsigned short const *>(&v53, v26, v15);
  v30 = AppCompatUtility::CompareStr(&v53, &v42, &v51);
  std::wstring::~wstring(&v53);
  std::wstring::~wstring(&v51);
  if ( v30 )
  {
LABEL_60:
    v13 = v36;
    *(_DWORD *)v36 = 1;
    std::wstring::~wstring(&v42);
    std::wstring::~wstring(v45);
  }
  else
  {
    AslLogCallPrintf(3, "FlightingMatchingPlugin", 242, "Branch does not match, actual branch: %ws", v38);
    std::wstring::~wstring(&v42);
    std::wstring::~wstring(v45);
    v13 = v36;
  }
LABEL_62:
  LocalFree(v11);
LABEL_63:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v38 )
  {
    CoTaskMemFree(v38);
    v38 = 0;
  }
  if ( v49 )
  {
    v32 = Src;
    if ( v50 > 7 )
      LODWORD(v32) = Src[0];
    AppCompatUtility::AddCacheMatchingPlugin(
      (AppCompatUtility *)*(unsigned int *)v13,
      (int)v32,
      (const unsigned __int16 *)a5,
      v31);
  }
  AslLogCallPrintf(3, "FlightingMatchingPlugin", 279, "FlightingMatchingPlugin Matched = %d", *(_DWORD *)v13);
LABEL_73:
  std::wstring::~wstring(Src);
  return 1;
}

```

## disassembly

```asm
0x18001ae10  mov     r11, rsp
0x18001ae13  push    rdi
0x18001ae14  push    r12
0x18001ae16  push    r13
0x18001ae18  push    r14
0x18001ae1a  push    r15
0x18001ae1c  sub     rsp, 120h
0x18001ae23  mov     [rsp+148h+var_D8], 0FFFFFFFFFFFFFFFEh
0x18001ae2c  mov     [r11+10h], rbx
0x18001ae30  mov     [r11+18h], rsi
0x18001ae34  mov     rax, cs:__security_cookie
0x18001ae3b  xor     rax, rsp
0x18001ae3e  mov     [rsp+148h+var_30], rax
0x18001ae46  mov     r12, rcx
0x18001ae49  mov     [rsp+148h+var_100], rcx
0x18001ae4e  mov     [rsp+148h+var_E0], rcx
0x18001ae53  mov     rdi, [rsp+148h+lpCmdLine]
0x18001ae5b  xor     esi, esi
0x18001ae5d  mov     [rsp+148h+pv], rsi
0x18001ae62  mov     [rsp+148h+var_F0], rsi
0x18001ae67  mov     [rsp+148h+pNumArgs], esi
0x18001ae6b  xorps   xmm0, xmm0
0x18001ae6e  movups  xmmword ptr [rsp+148h+Src], xmm0
0x18001ae76  mov     [r11-80h], rsi
0x18001ae7a  lea     r14d, [rsi+7]
0x18001ae7e  mov     [r11-78h], r14
0x18001ae82  mov     word ptr [rsp+148h+Src], si
0x18001ae8a  lea     r9, aEnterFlighting; "Enter FlightingMatchingPlugin"
0x18001ae91  mov     r8d, 0A3h
0x18001ae97  lea     r15, aFlightingmatch_1; "FlightingMatchingPlugin"
0x18001ae9e  mov     rdx, r15
0x18001aea1  lea     ebx, [rsi+3]
0x18001aea4  mov     ecx, ebx
0x18001aea6  call    AslLogCallPrintf
0x18001aeab  mov     [r12], esi
0x18001aeaf  test    rdi, rdi
0x18001aeb2  jz      loc_18001B59B
0x18001aeb8  cmp     si, [rdi]
0x18001aebb  jz      loc_18001B59B
0x18001aec1  mov     [rsp+148h+var_E8], rsi
0x18001aec6  mov     [rsp+148h+var_128], rdi
0x18001aecb  lea     r9, aCommandlineWs; "Commandline: %ws"
0x18001aed2  mov     r8d, 0ACh
0x18001aed8  mov     rdx, r15
0x18001aedb  mov     ecx, ebx
0x18001aedd  call    AslLogCallPrintf
0x18001aee2  nop
0x18001aee3  xorps   xmm0, xmm0
0x18001aee6  movups  xmmword ptr [rsp+148h+var_B0], xmm0
0x18001aeee  mov     [rsp+148h+var_A0], rsi
0x18001aef6  mov     [rsp+148h+var_98], r14
0x18001aefe  mov     word ptr [rsp+148h+var_B0], si
0x18001af06  movups  [rsp+148h+var_D0], xmm0
0x18001af0b  mov     [rsp+148h+var_C0], rsi
0x18001af13  mov     [rsp+148h+var_B8], r14
0x18001af1b  mov     word ptr [rsp+148h+var_D0], si
0x18001af20  lea     edx, [rsi+18h]
0x18001af23  cmp     [rsp+148h+var_78], rdx
0x18001af2b  jb      short loc_18001AF67
0x18001af2d  lea     rbx, [rsp+148h+Src]
0x18001af35  cmp     [rsp+148h+var_78], r14
0x18001af3d  cmova   rbx, [rsp+148h+Src]
0x18001af46  mov     [rsp+148h+var_80], rdx
0x18001af4e  lea     r8d, [rsi+30h]; Size
0x18001af52  lea     rdx, aFlightingmatch_2; "FlightingMatchingPlugin "
0x18001af59  mov     rcx, rbx; void *
0x18001af5c  call    memmove_0
0x18001af61  mov     [rbx+30h], si
0x18001af65  jmp     short loc_18001AF7B
0x18001af67  lea     r9, aFlightingmatch_2; "FlightingMatchingPlugin "
0x18001af6e  lea     rcx, [rsp+148h+Src]
0x18001af76  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001af7b  mov     rdx, rdi; void *
0x18001af7e  lea     rcx, [rsp+148h+Src]; Src
0x18001af86  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001af8b  lea     rdx, [rsp+148h+Src]
0x18001af93  cmp     [rsp+148h+var_78], r14
0x18001af9b  cmova   rdx, [rsp+148h+Src]; int *
0x18001afa4  mov     r8d, dword ptr [rsp+148h+arg_20]; unsigned __int16 *
0x18001afac  mov     rcx, r12; this
0x18001afaf  call    ?CheckCacheMatchingPlugin@AppCompatUtility@@YAHPEAHPEBGK@Z; AppCompatUtility::CheckCacheMatchingPlugin(int *,ushort const *,ulong)
0x18001afb4  test    eax, eax
0x18001afb6  jz      short loc_18001AFE8
0x18001afb8  lea     rcx, [rsp+148h+var_D0]; void *
0x18001afbd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001afc2  nop
0x18001afc3  lea     rcx, [rsp+148h+var_B0]; void *
0x18001afcb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001afd0  nop
0x18001afd1  lea     rcx, [rsp+148h+Src]; void *
0x18001afd9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001afde  mov     eax, 1
0x18001afe3  jmp     loc_18001B5C8
0x18001afe8  lea     rdx, [rsp+148h+pNumArgs]; pNumArgs
0x18001afed  mov     rcx, rdi; lpCmdLine
0x18001aff0  call    cs:__imp_CommandLineToArgvW
0x18001aff6  mov     r13, rax
0x18001aff9  mov     [rsp+148h+var_E8], rax
0x18001affe  mov     ebx, [rsp+148h+pNumArgs]
0x18001b002  test    rax, rax
0x18001b005  jz      loc_18001B4AD
0x18001b00b  cmp     ebx, 2
0x18001b00e  jl      loc_18001B4AD
0x18001b014  mov     ecx, ebx
0x18001b016  and     ecx, 80000001h
0x18001b01c  jge     short loc_18001B025
0x18001b01e  dec     ecx
0x18001b020  or      ecx, 0FFFFFFFEh
0x18001b023  inc     ecx
0x18001b025  test    ecx, ecx
0x18001b027  jz      short loc_18001B06B
0x18001b029  mov     dword ptr [rsp+148h+var_128], ebx
0x18001b02d  lea     r9, aWrongArguments; "Wrong arguments number: %d"
0x18001b034  mov     r8d, 0C8h
0x18001b03a  mov     rdx, r15
0x18001b03d  mov     ecx, 1
0x18001b042  call    AslLogCallPrintf
0x18001b047  nop
0x18001b048  lea     rcx, [rsp+148h+var_D0]; void *
0x18001b04d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b052  nop
0x18001b053  lea     rcx, [rsp+148h+var_B0]; void *
0x18001b05b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b060  nop
0x18001b061  mov     rbx, [rsp+148h+var_100]
0x18001b066  jmp     loc_18001B513
0x18001b06b  mov     r14d, esi
0x18001b06e  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001b072  lea     eax, [rbx-1]
0x18001b075  cmp     r14d, eax
0x18001b078  jge     loc_18001B1AB
0x18001b07e  movsxd  rax, r14d
0x18001b081  mov     rbx, [r13+rax*8+0]
0x18001b086  mov     rdx, rbx; String2
0x18001b089  lea     rcx, aFlightingring; "-FlightingRing"
0x18001b090  call    wcscmp_0
0x18001b095  test    eax, eax
0x18001b097  jnz     short loc_18001B0EB
0x18001b099  movsxd  rax, r14d
0x18001b09c  mov     r9, [r13+rax*8+8]
0x18001b0a1  mov     rdx, r12
0x18001b0a4  inc     rdx
0x18001b0a7  cmp     [r9+rdx*2], si
0x18001b0ac  jnz     short loc_18001B0A4
0x18001b0ae  cmp     rdx, [rsp+148h+var_98]
0x18001b0b6  ja      short loc_18001B0DC
0x18001b0b8  lea     rdi, [rsp+148h+var_B0]
0x18001b0c0  cmp     [rsp+148h+var_98], 7
0x18001b0c9  cmova   rdi, [rsp+148h+var_B0]
0x18001b0d2  mov     [rsp+148h+var_A0], rdx
0x18001b0da  jmp     short loc_18001B139
0x18001b0dc  lea     rcx, [rsp+148h+var_B0]
0x18001b0e4  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001b0e9  jmp     short loc_18001B15B
0x18001b0eb  mov     rdx, rbx; String2
0x18001b0ee  lea     rcx, aFlightingbranc; "-FlightingBranch"
0x18001b0f5  call    wcscmp_0
0x18001b0fa  test    eax, eax
0x18001b0fc  jnz     short loc_18001B168
0x18001b0fe  movsxd  rax, r14d
0x18001b101  mov     r9, [r13+rax*8+8]
0x18001b106  mov     rdx, r12
0x18001b109  inc     rdx
0x18001b10c  cmp     [r9+rdx*2], si
0x18001b111  jnz     short loc_18001B109
0x18001b113  cmp     rdx, [rsp+148h+var_B8]
0x18001b11b  ja      short loc_18001B151
0x18001b11d  lea     rdi, [rsp+148h+var_D0]
0x18001b122  cmp     [rsp+148h+var_B8], 7
0x18001b12b  cmova   rdi, qword ptr [rsp+148h+var_D0]
0x18001b131  mov     [rsp+148h+var_C0], rdx
0x18001b139  lea     rbx, [rdx+rdx]
0x18001b13d  mov     r8, rbx; Size
0x18001b140  mov     rdx, r9; Src
0x18001b143  mov     rcx, rdi; void *
0x18001b146  call    memmove_0
0x18001b14b  mov     [rdi+rbx], si
0x18001b14f  jmp     short loc_18001B15B
0x18001b151  lea     rcx, [rsp+148h+var_D0]
0x18001b156  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001b15b  add     r14d, 2
0x18001b15f  mov     ebx, [rsp+148h+pNumArgs]
0x18001b163  jmp     loc_18001B072
0x18001b168  mov     [rsp+148h+var_128], rbx
0x18001b16d  lea     r9, aUnknownSwitchW; "Unknown switch: %ws"
0x18001b174  mov     r8d, 0D8h
0x18001b17a  mov     rdx, r15
0x18001b17d  mov     ecx, 1
0x18001b182  call    AslLogCallPrintf
0x18001b187  nop
0x18001b188  lea     rcx, [rsp+148h+var_D0]; void *
0x18001b18d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b192  nop
0x18001b193  lea     rcx, [rsp+148h+var_B0]; void *
0x18001b19b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b1a0  nop
0x18001b1a1  mov     rbx, [rsp+148h+var_100]
0x18001b1a6  jmp     loc_18001B513
0x18001b1ab  lea     rcx, [rsp+148h+var_D0]
0x18001b1b0  cmp     [rsp+148h+var_B8], 7
0x18001b1b9  cmova   rcx, qword ptr [rsp+148h+var_D0]
0x18001b1bf  lea     rax, [rsp+148h+var_B0]
0x18001b1c7  cmp     [rsp+148h+var_98], 7
0x18001b1d0  cmova   rax, [rsp+148h+var_B0]
0x18001b1d9  mov     [rsp+148h+var_120], rcx
0x18001b1de  mov     [rsp+148h+var_128], rax
0x18001b1e3  lea     r9, aRingWsBranchWs; "Ring:%ws; Branch:%ws"
0x18001b1ea  mov     r8d, 0DCh
0x18001b1f0  mov     rdx, r15
0x18001b1f3  mov     ecx, 3
0x18001b1f8  call    AslLogCallPrintf
0x18001b1fd  cmp     [rsp+148h+var_C0], rsi
0x18001b205  setz    al
0x18001b208  lea     rdx, [rsp+148h+var_F0]
0x18001b20d  test    al, al
0x18001b20f  cmovnz  rdx, rsi; unsigned __int16 **
0x18001b213  cmp     [rsp+148h+var_A0], rsi
0x18001b21b  setz    al
0x18001b21e  lea     rcx, [rsp+148h+pv]
0x18001b223  test    al, al
0x18001b225  cmovnz  rcx, rsi; unsigned __int16 **
0x18001b229  call    ?GetFlightingConfigValues@@YAJPEAPEAG0@Z; GetFlightingConfigValues(ushort * *,ushort * *)
0x18001b22e  test    eax, eax
0x18001b230  jz      short loc_18001B274
0x18001b232  mov     dword ptr [rsp+148h+var_128], eax
0x18001b236  lea     r9, aGetflightingco_0; "GetFlightingConfigValues failed 0x%x"
0x18001b23d  mov     r8d, 0E1h
0x18001b243  mov     rdx, r15
0x18001b246  mov     ecx, 3
0x18001b24b  call    AslLogCallPrintf
0x18001b250  nop
0x18001b251  lea     rcx, [rsp+148h+var_D0]; void *
0x18001b256  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b25b  nop
0x18001b25c  lea     rcx, [rsp+148h+var_B0]; void *
0x18001b264  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b269  nop
0x18001b26a  mov     rbx, [rsp+148h+var_100]
0x18001b26f  jmp     loc_18001B513
0x18001b274  cmp     [rsp+148h+var_A0], rsi
0x18001b27c  jz      loc_18001B37F
0x18001b282  xorps   xmm0, xmm0
0x18001b285  movups  [rsp+148h+var_50], xmm0
0x18001b28d  xorps   xmm1, xmm1
0x18001b290  movdqu  [rsp+148h+var_40], xmm1
0x18001b299  mov     r8d, 2
0x18001b29f  lea     rdx, aEq; "eq"
0x18001b2a6  lea     rcx, [rsp+148h+var_50]
0x18001b2ae  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001b2b3  nop
0x18001b2b4  lea     rbx, psz
0x18001b2bb  mov     rdx, rbx
0x18001b2be  cmp     [rsp+148h+pv], rsi
0x18001b2c3  cmovnz  rdx, [rsp+148h+pv]
0x18001b2c9  xorps   xmm0, xmm0
0x18001b2cc  movups  [rsp+148h+var_70], xmm0
0x18001b2d4  xorps   xmm1, xmm1
0x18001b2d7  movdqu  [rsp+148h+var_60], xmm1
0x18001b2e0  mov     r8, r12
0x18001b2e3  inc     r8
0x18001b2e6  cmp     [rdx+r8*2], si
0x18001b2eb  jnz     short loc_18001B2E3
0x18001b2ed  lea     rcx, [rsp+148h+var_70]
0x18001b2f5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001b2fa  nop
0x18001b2fb  lea     r8, [rsp+148h+var_50]
0x18001b303  lea     rdx, [rsp+148h+var_B0]
0x18001b30b  lea     rcx, [rsp+148h+var_70]
0x18001b313  call    ?CompareStr@AppCompatUtility@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; AppCompatUtility::CompareStr(std::wstring const &,std::wstring const &,std::wstring const &)
0x18001b318  mov     edi, eax
0x18001b31a  lea     rcx, [rsp+148h+var_70]; void *
0x18001b322  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b327  nop
0x18001b328  lea     rcx, [rsp+148h+var_50]; void *
0x18001b330  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b335  test    edi, edi
0x18001b337  jnz     short loc_18001B386
0x18001b339  mov     rax, [rsp+148h+pv]
0x18001b33e  mov     [rsp+148h+var_128], rax
0x18001b343  lea     r9, aRingDoesNotMat; "Ring does not match, actual ring: %ws"
0x18001b34a  mov     r8d, 0E9h
0x18001b350  mov     rdx, r15
0x18001b353  lea     ecx, [rdi+3]
0x18001b356  call    AslLogCallPrintf
0x18001b35b  nop
0x18001b35c  lea     rcx, [rsp+148h+var_D0]; void *
0x18001b361  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b366  nop
0x18001b367  lea     rcx, [rsp+148h+var_B0]; void *
0x18001b36f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b374  nop
0x18001b375  mov     rbx, [rsp+148h+var_100]
0x18001b37a  jmp     loc_18001B513
0x18001b37f  lea     rbx, psz
0x18001b386  cmp     [rsp+148h+var_C0], rsi
0x18001b38e  jz      loc_18001B487
0x18001b394  xorps   xmm0, xmm0
0x18001b397  movups  [rsp+148h+var_70], xmm0
0x18001b39f  xorps   xmm1, xmm1
0x18001b3a2  movdqu  [rsp+148h+var_60], xmm1
  ... truncated ...
```
