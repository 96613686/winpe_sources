# LoadPerfDll(HKEY__ *,wchar_t const *,ulong)

- ea: `0x180003290`
- end: `0x1800034ff`
- name: `?LoadPerfDll@@YAXPEAUHKEY__@@PEB_WK@Z`
- size: `623`
- prototype: `void __fastcall(HKEY hKey, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180003234`

## callees

- `0x180003290`
- `0x1800565ba`
- `0x1800578b0`
- `0x180057e70`
- `0x180186288`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800033e1`
- `KERNEL32!GetProcAddress` at `0x18000340b`
- `KERNEL32!GetProcAddress` at `0x18000341f`
- `KERNEL32!GetProcAddress` at `0x180003442`
- `KERNEL32!GetProcAddress` at `0x180003456`
- `KERNEL32!GetProcAddress` at `0x18000346a`
- `KERNEL32!GetProcAddress` at `0x1800033e1`
- `KERNEL32!GetProcAddress` at `0x18000340b`
- `KERNEL32!GetProcAddress` at `0x18000341f`
- `KERNEL32!GetProcAddress` at `0x180003442`
- `KERNEL32!GetProcAddress` at `0x180003456`
- `KERNEL32!GetProcAddress` at `0x18000346a`
- `KERNEL32!FreeLibrary` at `0x1800034c2`
- `KERNEL32!FreeLibrary` at `0x1800034c2`
- `KERNEL32!LoadLibraryExW` at `0x1800033c5`
- `KERNEL32!LoadLibraryExW` at `0x1800033c5`
- `ADVAPI32!RegQueryValueExW` at `0x180003344`
- `ADVAPI32!RegQueryValueExW` at `0x180003344`

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
  for ( i = qword_180523C90; ; i += 5 )
  {
    if ( (__int64)i >= (__int64)&dword_180523CE0 )
      return;
    if ( !*i )
      break;
    ++v3;
  }
  v5 = &qword_180523C90[5 * v3];
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
    v19((unsigned int)dword_180523BF0);
    return;
  }
  v20 = *((_DWORD *)v5 + 2) == 2 || *((_DWORD *)v5 + 2) == 3
      ? ((__int64 (__fastcall *)(_QWORD))v19)((unsigned int)dword_180523BF0)
      : -2147467259;
  if ( v20 < 0 )
    goto LABEL_37;
}

```

## disassembly

```asm
0x180003290  mov     rax, rsp
0x180003293  mov     [rax+10h], rbx
0x180003297  mov     [rax+18h], rsi
0x18000329b  mov     [rax+20h], rdi
0x18000329f  push    rbp
0x1800032a0  lea     rbp, [rax-168h]
0x1800032a7  sub     rsp, 260h
0x1800032ae  mov     rax, cs:__security_cookie
0x1800032b5  xor     rax, rsp
0x1800032b8  mov     [rbp+160h+var_10], rax
0x1800032bf  mov     rdi, rcx
0x1800032c2  mov     [rsp+260h+Type], 1
0x1800032ca  lea     rcx, [rsp+260h+Data]; void *
0x1800032cf  xor     edx, edx; Val
0x1800032d1  mov     r8d, 208h; Size
0x1800032d7  call    memset_0
0x1800032dc  xor     esi, esi
0x1800032de  mov     [rsp+260h+cbData], 208h
0x1800032e6  lea     r8, qword_180523C90
0x1800032ed  mov     ecx, esi
0x1800032ef  mov     rax, r8
0x1800032f2  lea     rdx, dword_180523CE0
0x1800032f9  cmp     rax, rdx
0x1800032fc  jge     loc_1800034D7
0x180003302  cmp     [rax], rsi
0x180003305  jz      short loc_18000330F
0x180003307  inc     ecx
0x180003309  add     rax, 28h ; '('
0x18000330d  jmp     short loc_1800032F9
0x18000330f  movsxd  rax, ecx
0x180003312  lea     rdx, [rax+rax*4]
0x180003316  lea     rbx, [r8+rdx*8]
0x18000331a  test    rbx, rbx
0x18000331d  jz      loc_1800034D7
0x180003323  lea     rax, [rsp+260h+cbData]
0x180003328  xor     r8d, r8d; lpReserved
0x18000332b  mov     [rsp+260h+lpcbData], rax; lpcbData
0x180003330  lea     r9, [rsp+260h+Type]; lpType
0x180003335  lea     rax, [rsp+260h+Data]
0x18000333a  xor     edx, edx; lpValueName
0x18000333c  mov     rcx, rdi; hKey
0x18000333f  mov     [rsp+260h+lpData], rax; lpData
0x180003344  call    cs:__imp_RegQueryValueExW
0x18000334a  test    eax, eax
0x18000334c  jnz     loc_1800034BA
0x180003352  cmp     [rsp+260h+Type], 1
0x180003357  jnz     loc_1800034BA
0x18000335d  movzx   ecx, [rsp+260h+Data]
0x180003362  test    cx, cx
0x180003365  jz      loc_1800034BA
0x18000336b  mov     eax, [rsp+260h+cbData]
0x18000336f  test    eax, eax
0x180003371  jz      loc_1800034BA
0x180003377  shr     eax, 1
0x180003379  mov     edx, eax
0x18000337b  mov     [rsp+260h+cbData], eax
0x18000337f  cmp     eax, 104h
0x180003384  jnb     short loc_1800033A5
0x180003386  mov     eax, edx
0x180003388  add     rax, rax
0x18000338b  cmp     rax, 208h
0x180003391  jnb     short loc_18000339F
0x180003393  mov     [rsp+rax+260h+Data], si
0x180003398  movzx   ecx, [rsp+260h+Data]
0x18000339d  jmp     short loc_1800033AC
0x18000339f  call    __report_rangecheckfailure
0x1800033a5  mov     [rbp+160h+var_1A], si
0x1800033ac  test    cx, cx
0x1800033af  jnz     short loc_1800033B8
0x1800033b1  mov     ecx, 5
0x1800033b6  int     29h; Win8: RtlFailFast(ecx)
0x1800033b8  xor     edx, edx; hFile
0x1800033ba  lea     rcx, [rsp+260h+Data]; lpLibFileName
0x1800033bf  mov     r8d, 1000h; dwFlags
0x1800033c5  call    cs:__imp_LoadLibraryExW
0x1800033cb  mov     [rbx], rax
0x1800033ce  test    rax, rax
0x1800033d1  jz      loc_1800034BA
0x1800033d7  lea     rdx, ProcName; "GetPerfhostHookVersion"
0x1800033de  mov     rcx, rax; hModule
0x1800033e1  call    cs:__imp_GetProcAddress
0x1800033e7  test    rax, rax
0x1800033ea  jnz     short loc_1800033F3
0x1800033ec  mov     eax, 1
0x1800033f1  jmp     short loc_1800033F9
0x1800033f3  call    cs:__guard_dispatch_icall_fptr
0x1800033f9  mov     [rbx+8], eax
0x1800033fc  cmp     eax, 1
0x1800033ff  jnz     short loc_18000342E
0x180003401  mov     rcx, [rbx]; hModule
0x180003404  lea     rdx, aInitperf; "InitPerf"
0x18000340b  call    cs:__imp_GetProcAddress
0x180003411  mov     rcx, [rbx]; hModule
0x180003414  lea     rdx, aPerfcodemarker; "PerfCodeMarker"
0x18000341b  mov     [rbx+10h], rax
0x18000341f  call    cs:__imp_GetProcAddress
0x180003425  lea     rdx, aUninitperf; "UnInitPerf"
0x18000342c  jmp     short loc_180003463
0x18000342e  cmp     eax, 2
0x180003431  jz      short loc_180003401
0x180003433  cmp     eax, 3
0x180003436  jnz     short loc_180003474
0x180003438  mov     rcx, [rbx]; hModule
0x18000343b  lea     rdx, aInitperfV3; "InitPerf_v3"
0x180003442  call    cs:__imp_GetProcAddress
0x180003448  mov     rcx, [rbx]; hModule
0x18000344b  lea     rdx, aPerfcodemarker_0; "PerfCodeMarker_v3"
0x180003452  mov     [rbx+10h], rax
0x180003456  call    cs:__imp_GetProcAddress
0x18000345c  lea     rdx, aUninitperfV3; "UnInitPerf_v3"
0x180003463  mov     rcx, [rbx]; hModule
0x180003466  mov     [rbx+20h], rax
0x18000346a  call    cs:__imp_GetProcAddress
0x180003470  mov     [rbx+18h], rax
0x180003474  mov     rax, [rbx+10h]
0x180003478  test    rax, rax
0x18000347b  jz      short loc_1800034BA
0x18000347d  cmp     [rbx+20h], rsi
0x180003481  jz      short loc_1800034BA
0x180003483  cmp     [rbx+18h], rsi
0x180003487  jz      short loc_1800034BA
0x180003489  cmp     dword ptr [rbx+8], 1
0x18000348d  mov     ecx, cs:dword_180523BF0
0x180003493  jnz     short loc_18000349D
0x180003495  call    cs:__guard_dispatch_icall_fptr
0x18000349b  jmp     short loc_1800034D7
0x18000349d  cmp     dword ptr [rbx+8], 2
0x1800034a1  jnz     short loc_1800034AB
0x1800034a3  call    cs:__guard_dispatch_icall_fptr
0x1800034a9  jmp     short loc_1800034B6
0x1800034ab  cmp     dword ptr [rbx+8], 3
0x1800034af  jz      short loc_1800034A3
0x1800034b1  mov     eax, 80004005h
0x1800034b6  test    eax, eax
0x1800034b8  jns     short loc_1800034D7
0x1800034ba  mov     rcx, [rbx]; hLibModule
0x1800034bd  test    rcx, rcx
0x1800034c0  jz      short loc_1800034C8
0x1800034c2  call    cs:__imp_FreeLibrary
0x1800034c8  mov     [rbx], rsi
0x1800034cb  mov     [rbx+10h], rsi
0x1800034cf  mov     [rbx+18h], rsi
0x1800034d3  mov     [rbx+20h], rsi
0x1800034d7  mov     rcx, [rbp+160h+var_10]
0x1800034de  xor     rcx, rsp; StackCookie
0x1800034e1  call    __security_check_cookie
0x1800034e6  lea     r11, [rsp+260h+var_s0]
0x1800034ee  mov     rbx, [r11+18h]
0x1800034f2  mov     rsi, [r11+20h]
0x1800034f6  mov     rdi, [r11+28h]
0x1800034fa  mov     rsp, r11
0x1800034fd  pop     rbp
0x1800034fe  retn
```
