# LoadPerfDll(HKEY__ *,wchar_t const *,ulong)

- ea: `0x180003220`
- end: `0x18000348f`
- name: `?LoadPerfDll@@YAXPEAUHKEY__@@PEB_WK@Z`
- size: `623`
- prototype: `void __fastcall(HKEY hKey, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800031c4`

## callees

- `0x180003220`
- `0x180055b26`
- `0x180056ee0`
- `0x1800573f0`
- `0x1801826f8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180003371`
- `KERNEL32!GetProcAddress` at `0x18000339b`
- `KERNEL32!GetProcAddress` at `0x1800033af`
- `KERNEL32!GetProcAddress` at `0x1800033d2`
- `KERNEL32!GetProcAddress` at `0x1800033e6`
- `KERNEL32!GetProcAddress` at `0x1800033fa`
- `KERNEL32!GetProcAddress` at `0x180003371`
- `KERNEL32!GetProcAddress` at `0x18000339b`
- `KERNEL32!GetProcAddress` at `0x1800033af`
- `KERNEL32!GetProcAddress` at `0x1800033d2`
- `KERNEL32!GetProcAddress` at `0x1800033e6`
- `KERNEL32!GetProcAddress` at `0x1800033fa`
- `KERNEL32!FreeLibrary` at `0x180003452`
- `KERNEL32!FreeLibrary` at `0x180003452`
- `KERNEL32!LoadLibraryExW` at `0x180003355`
- `KERNEL32!LoadLibraryExW` at `0x180003355`
- `ADVAPI32!RegQueryValueExW` at `0x1800032d4`
- `ADVAPI32!RegQueryValueExW` at `0x1800032d4`

## pseudocode

```c
void __fastcall LoadPerfDll(HKEY hKey, const wchar_t *a2)
{
  int v3; // ecx
  __int64 *i; // rax
  __int64 *v5; // rbx
  WCHAR v6; // cx
  DWORD v7; // eax
  DWORD v8; // edx
  HMODULE Library; // rax
  __int64 (*ProcAddress)(void); // rax
  int v11; // eax
  FARPROC v12; // rax
  HMODULE v13; // rcx
  FARPROC v14; // rax
  const CHAR *v15; // rdx
  FARPROC v16; // rax
  HMODULE v17; // rcx
  HMODULE v18; // rcx
  void (__fastcall *v19)(_QWORD); // rax
  int v20; // eax
  DWORD cbData; // [rsp+38h] [rbp-D0h] BYREF
  DWORD Type[3]; // [rsp+3Ch] [rbp-CCh] BYREF
  WCHAR Data[259]; // [rsp+48h] [rbp-C0h] BYREF
  __int16 v24; // [rsp+24Eh] [rbp+146h]

  Type[0] = 1;
  memset_0(Data, 0, 0x208u);
  cbData = 520;
  v3 = 0;
  for ( i = qword_18051EA30; ; i += 5 )
  {
    if ( (__int64)i >= (__int64)&dword_18051EA80 )
      return;
    if ( !*i )
      break;
    ++v3;
  }
  v5 = &qword_18051EA30[5 * v3];
  if ( !v5 )
    return;
  if ( RegQueryValueExW(hKey, 0, 0, Type, (LPBYTE)Data, &cbData) )
    goto LABEL_37;
  if ( Type[0] != 1 )
    goto LABEL_37;
  v6 = Data[0];
  if ( !Data[0] )
    goto LABEL_37;
  v7 = cbData;
  if ( !cbData )
    goto LABEL_37;
  v8 = cbData >> 1;
  cbData >>= 1;
  if ( v7 >> 1 >= 0x104 )
  {
    v24 = 0;
  }
  else
  {
    if ( 2 * (unsigned __int64)v8 >= 0x208 )
      _report_rangecheckfailure();
    Data[v8] = 0;
    v6 = Data[0];
  }
  if ( !v6 )
    __fastfail(5u);
  Library = LoadLibraryExW(Data, 0, 0x1000u);
  *v5 = (__int64)Library;
  if ( !Library )
  {
LABEL_37:
    if ( *v5 )
      FreeLibrary((HMODULE)*v5);
    *v5 = 0;
    v5[2] = 0;
    v5[3] = 0;
    v5[4] = 0;
    return;
  }
  ProcAddress = GetProcAddress(Library, "GetPerfhostHookVersion");
  if ( ProcAddress )
    v11 = ProcAddress();
  else
    v11 = 1;
  *((_DWORD *)v5 + 2) = v11;
  if ( v11 == 1 || v11 == 2 )
  {
    v12 = GetProcAddress((HMODULE)*v5, "InitPerf");
    v13 = (HMODULE)*v5;
    v5[2] = (__int64)v12;
    v14 = GetProcAddress(v13, "PerfCodeMarker");
    v15 = "UnInitPerf";
  }
  else
  {
    if ( v11 != 3 )
      goto LABEL_27;
    v16 = GetProcAddress((HMODULE)*v5, "InitPerf_v3");
    v17 = (HMODULE)*v5;
    v5[2] = (__int64)v16;
    v14 = GetProcAddress(v17, "PerfCodeMarker_v3");
    v15 = "UnInitPerf_v3";
  }
  v18 = (HMODULE)*v5;
  v5[4] = (__int64)v14;
  v5[3] = (__int64)GetProcAddress(v18, v15);
LABEL_27:
  v19 = (void (__fastcall *)(_QWORD))v5[2];
  if ( !v19 || !v5[4] || !v5[3] )
    goto LABEL_37;
  if ( *((_DWORD *)v5 + 2) == 1 )
  {
    v19((unsigned int)dword_18051FC30);
    return;
  }
  v20 = *((_DWORD *)v5 + 2) == 2 || *((_DWORD *)v5 + 2) == 3
      ? ((__int64 (__fastcall *)(_QWORD))v19)((unsigned int)dword_18051FC30)
      : -2147467259;
  if ( v20 < 0 )
    goto LABEL_37;
}

```

## disassembly

```asm
0x180003220  mov     rax, rsp
0x180003223  mov     [rax+10h], rbx
0x180003227  mov     [rax+18h], rsi
0x18000322b  mov     [rax+20h], rdi
0x18000322f  push    rbp
0x180003230  lea     rbp, [rax-168h]
0x180003237  sub     rsp, 260h
0x18000323e  mov     rax, cs:__security_cookie
0x180003245  xor     rax, rsp
0x180003248  mov     [rbp+160h+var_10], rax
0x18000324f  mov     rdi, rcx
0x180003252  mov     [rsp+260h+Type], 1
0x18000325a  lea     rcx, [rsp+260h+Data]; void *
0x18000325f  xor     edx, edx; Val
0x180003261  mov     r8d, 208h; Size
0x180003267  call    memset_0
0x18000326c  xor     esi, esi
0x18000326e  mov     [rsp+260h+cbData], 208h
0x180003276  lea     r8, qword_18051EA30
0x18000327d  mov     ecx, esi
0x18000327f  mov     rax, r8
0x180003282  lea     rdx, dword_18051EA80
0x180003289  cmp     rax, rdx
0x18000328c  jge     loc_180003467
0x180003292  cmp     [rax], rsi
0x180003295  jz      short loc_18000329F
0x180003297  inc     ecx
0x180003299  add     rax, 28h ; '('
0x18000329d  jmp     short loc_180003289
0x18000329f  movsxd  rax, ecx
0x1800032a2  lea     rdx, [rax+rax*4]
0x1800032a6  lea     rbx, [r8+rdx*8]
0x1800032aa  test    rbx, rbx
0x1800032ad  jz      loc_180003467
0x1800032b3  lea     rax, [rsp+260h+cbData]
0x1800032b8  xor     r8d, r8d; lpReserved
0x1800032bb  mov     [rsp+260h+lpcbData], rax; lpcbData
0x1800032c0  lea     r9, [rsp+260h+Type]; lpType
0x1800032c5  lea     rax, [rsp+260h+Data]
0x1800032ca  xor     edx, edx; lpValueName
0x1800032cc  mov     rcx, rdi; hKey
0x1800032cf  mov     [rsp+260h+lpData], rax; lpData
0x1800032d4  call    cs:__imp_RegQueryValueExW
0x1800032da  test    eax, eax
0x1800032dc  jnz     loc_18000344A
0x1800032e2  cmp     [rsp+260h+Type], 1
0x1800032e7  jnz     loc_18000344A
0x1800032ed  movzx   ecx, [rsp+260h+Data]
0x1800032f2  test    cx, cx
0x1800032f5  jz      loc_18000344A
0x1800032fb  mov     eax, [rsp+260h+cbData]
0x1800032ff  test    eax, eax
0x180003301  jz      loc_18000344A
0x180003307  shr     eax, 1
0x180003309  mov     edx, eax
0x18000330b  mov     [rsp+260h+cbData], eax
0x18000330f  cmp     eax, 104h
0x180003314  jnb     short loc_180003335
0x180003316  mov     eax, edx
0x180003318  add     rax, rax
0x18000331b  cmp     rax, 208h
0x180003321  jnb     short loc_18000332F
0x180003323  mov     [rsp+rax+260h+Data], si
0x180003328  movzx   ecx, [rsp+260h+Data]
0x18000332d  jmp     short loc_18000333C
0x18000332f  call    __report_rangecheckfailure
0x180003335  mov     [rbp+160h+var_1A], si
0x18000333c  test    cx, cx
0x18000333f  jnz     short loc_180003348
0x180003341  mov     ecx, 5
0x180003346  int     29h; Win8: RtlFailFast(ecx)
0x180003348  xor     edx, edx; hFile
0x18000334a  lea     rcx, [rsp+260h+Data]; lpLibFileName
0x18000334f  mov     r8d, 1000h; dwFlags
0x180003355  call    cs:__imp_LoadLibraryExW
0x18000335b  mov     [rbx], rax
0x18000335e  test    rax, rax
0x180003361  jz      loc_18000344A
0x180003367  lea     rdx, ProcName; "GetPerfhostHookVersion"
0x18000336e  mov     rcx, rax; hModule
0x180003371  call    cs:__imp_GetProcAddress
0x180003377  test    rax, rax
0x18000337a  jnz     short loc_180003383
0x18000337c  mov     eax, 1
0x180003381  jmp     short loc_180003389
0x180003383  call    cs:__guard_dispatch_icall_fptr
0x180003389  mov     [rbx+8], eax
0x18000338c  cmp     eax, 1
0x18000338f  jnz     short loc_1800033BE
0x180003391  mov     rcx, [rbx]; hModule
0x180003394  lea     rdx, aInitperf; "InitPerf"
0x18000339b  call    cs:__imp_GetProcAddress
0x1800033a1  mov     rcx, [rbx]; hModule
0x1800033a4  lea     rdx, aPerfcodemarker; "PerfCodeMarker"
0x1800033ab  mov     [rbx+10h], rax
0x1800033af  call    cs:__imp_GetProcAddress
0x1800033b5  lea     rdx, aUninitperf; "UnInitPerf"
0x1800033bc  jmp     short loc_1800033F3
0x1800033be  cmp     eax, 2
0x1800033c1  jz      short loc_180003391
0x1800033c3  cmp     eax, 3
0x1800033c6  jnz     short loc_180003404
0x1800033c8  mov     rcx, [rbx]; hModule
0x1800033cb  lea     rdx, aInitperfV3; "InitPerf_v3"
0x1800033d2  call    cs:__imp_GetProcAddress
0x1800033d8  mov     rcx, [rbx]; hModule
0x1800033db  lea     rdx, aPerfcodemarker_0; "PerfCodeMarker_v3"
0x1800033e2  mov     [rbx+10h], rax
0x1800033e6  call    cs:__imp_GetProcAddress
0x1800033ec  lea     rdx, aUninitperfV3; "UnInitPerf_v3"
0x1800033f3  mov     rcx, [rbx]; hModule
0x1800033f6  mov     [rbx+20h], rax
0x1800033fa  call    cs:__imp_GetProcAddress
0x180003400  mov     [rbx+18h], rax
0x180003404  mov     rax, [rbx+10h]
0x180003408  test    rax, rax
0x18000340b  jz      short loc_18000344A
0x18000340d  cmp     [rbx+20h], rsi
0x180003411  jz      short loc_18000344A
0x180003413  cmp     [rbx+18h], rsi
0x180003417  jz      short loc_18000344A
0x180003419  cmp     dword ptr [rbx+8], 1
0x18000341d  mov     ecx, cs:dword_18051FC30
0x180003423  jnz     short loc_18000342D
0x180003425  call    cs:__guard_dispatch_icall_fptr
0x18000342b  jmp     short loc_180003467
0x18000342d  cmp     dword ptr [rbx+8], 2
0x180003431  jnz     short loc_18000343B
0x180003433  call    cs:__guard_dispatch_icall_fptr
0x180003439  jmp     short loc_180003446
0x18000343b  cmp     dword ptr [rbx+8], 3
0x18000343f  jz      short loc_180003433
0x180003441  mov     eax, 80004005h
0x180003446  test    eax, eax
0x180003448  jns     short loc_180003467
0x18000344a  mov     rcx, [rbx]; hLibModule
0x18000344d  test    rcx, rcx
0x180003450  jz      short loc_180003458
0x180003452  call    cs:__imp_FreeLibrary
0x180003458  mov     [rbx], rsi
0x18000345b  mov     [rbx+10h], rsi
0x18000345f  mov     [rbx+18h], rsi
0x180003463  mov     [rbx+20h], rsi
0x180003467  mov     rcx, [rbp+160h+var_10]
0x18000346e  xor     rcx, rsp; StackCookie
0x180003471  call    __security_check_cookie
0x180003476  lea     r11, [rsp+260h+var_s0]
0x18000347e  mov     rbx, [r11+18h]
0x180003482  mov     rsi, [r11+20h]
0x180003486  mov     rdi, [r11+28h]
0x18000348a  mov     rsp, r11
0x18000348d  pop     rbp
0x18000348e  retn
```
