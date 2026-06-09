# GetLinkedEnrollmentStringRegistry(ushort const *,ushort const *,ulong,ushort *)

- ea: `0x1400300d4`
- end: `0x14003040a`
- name: `?GetLinkedEnrollmentStringRegistry@@YAJPEBG0KPEAG@Z`
- size: `822`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x140009fc4`
- `0x14000a088`
- `0x1400300d4`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x14003011c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14003011c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400303cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400303cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003035e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003035e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003034d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400303bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003034d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400303bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030263`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140030276`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140030276`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400302a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400302a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030191`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400301c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400301ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003021d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003024d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003026e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400302c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003031b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030338`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030376`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400303de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030191`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400301c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400301ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003021d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003024d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003026e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400302c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003031b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030338`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030376`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400303de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400302fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400303a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400302fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400303a7`

## string_xrefs

- `0x1400302f2`: `LinkedEnrollmentId`
- `0x14003039b`: `LinkedEnrollmentId`
- `0x140030229`: `LinkedEnrollment`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetLinkedEnrollmentStringRegistry(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  signed int v6; // ebx
  __int64 v7; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // r8
  wchar_t v12; // ax
  WCHAR *v13; // rcx
  DWORD LastError; // ebx
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  DWORD v18; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v20; // rdi
  HANDLE v21; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-C4h] BYREF
  WCHAR SubKey[104]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    goto LABEL_54;
  }
  v7 = 2147483646;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1, a2);
  v9 = L"OSData\\";
  if ( !IsStateSeparationEnabled )
    v9 = &::SubKey;
  v10 = 97;
  v11 = SubKey;
  do
  {
    if ( !v7 )
      break;
    v12 = *v9;
    if ( !*v9 )
      break;
    ++v9;
    *v11++ = v12;
    --v7;
    --v10;
  }
  while ( v10 );
  v6 = v10 == 0 ? 0x8007007A : 0;
  v13 = v11 - 1;
  if ( v10 )
    v13 = v11;
  *v13 = 0;
  if ( !v10 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v6;
  }
  v6 = StringCchCatW(SubKey, 0x61u, c_szEnrollmentsDB);
  if ( v6 < 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v6;
  }
  v6 = StringCchCatW(SubKey, 0x61u, a1);
  if ( v6 < 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v6;
  }
  v6 = StringCchCatW(SubKey, 0x61u, L"\\");
  if ( v6 < 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v6;
  }
  v6 = StringCchCatW(SubKey, 0x61u, c_szEnrollmentsDBLinkedEnrollment);
  if ( v6 < 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v6;
  }
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(hKey);
    SetLastError(LastError);
  }
  hKey = 0;
  v15 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
  v6 = v15;
  if ( v15 > 0 )
    v6 = (unsigned __int16)v15 | 0x80070000;
  if ( v6 < 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v6;
  }
  Type = 0;
  cbData = 0;
  v16 = RegQueryValueExW(hKey, L"LinkedEnrollmentId", 0, &Type, 0, &cbData);
  v6 = v16;
  if ( v16 )
  {
    if ( v16 > 0 )
      v6 = (unsigned __int16)v16 | 0x80070000;
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v6;
  }
  if ( Type == 1 )
  {
    v18 = cbData;
    ProcessHeap = GetProcessHeap();
    v20 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v18);
    if ( v20 )
    {
      RegQueryValueExW(hKey, L"LinkedEnrollmentId", 0, &Type, v20, &cbData);
      v6 = StringCchCopyW(a4, 0x32u, (const unsigned __int16 *)v20);
      v21 = GetProcessHeap();
      HeapFree(v21, 0, v20);
LABEL_54:
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v6;
    }
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942414LL;
  }
  else
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1400300d4  mov     [rsp-8+arg_8], rbx
0x1400300d9  push    rbp
0x1400300da  push    rsi
0x1400300db  push    rdi
0x1400300dc  push    r14
0x1400300de  push    r15
0x1400300e0  lea     rbp, [rsp-20h]
0x1400300e5  sub     rsp, 120h
0x1400300ec  mov     rax, cs:__security_cookie
0x1400300f3  xor     rax, rsp
0x1400300f6  mov     [rbp+40h+var_30], rax
0x1400300fa  mov     rsi, r9
0x1400300fd  mov     rdi, rcx
0x140030100  xor     r14d, r14d
0x140030103  mov     [rsp+140h+hKey], r14
0x140030108  test    rcx, rcx
0x14003010b  jnz     short loc_140030117
0x14003010d  mov     ebx, 80070057h
0x140030112  jmp     loc_1400303D4
0x140030117  mov     ebx, 7FFFFFFEh
0x14003011c  call    cs:__imp_RtlIsStateSeparationEnabled
0x140030122  lea     rdx, SubKey
0x140030129  lea     rcx, aOsdata; "OSData\\"
0x140030130  test    al, al
0x140030132  cmovz   rcx, rdx
0x140030136  mov     r15d, 61h ; 'a'
0x14003013c  mov     edx, r15d
0x14003013f  lea     r8, [rsp+140h+SubKey]
0x140030144  test    rbx, rbx
0x140030147  jz      short loc_140030166
0x140030149  movzx   eax, word ptr [rcx]
0x14003014c  test    ax, ax
0x14003014f  jz      short loc_140030166
0x140030151  add     rcx, 2
0x140030155  mov     [r8], ax
0x140030159  add     r8, 2
0x14003015d  dec     rbx
0x140030160  sub     rdx, 1
0x140030164  jnz     short loc_140030144
0x140030166  mov     rax, rdx
0x140030169  neg     rax
0x14003016c  sbb     ebx, ebx
0x14003016e  not     ebx
0x140030170  and     ebx, 8007007Ah
0x140030176  lea     rcx, [r8-2]
0x14003017a  test    rdx, rdx
0x14003017d  cmovnz  rcx, r8
0x140030181  mov     [rcx], r14w
0x140030185  jnz     short loc_14003019D
0x140030187  mov     rcx, [rsp+140h+hKey]; hKey
0x14003018c  test    rcx, rcx
0x14003018f  jz      short loc_140030198
0x140030191  call    cs:__imp_RegCloseKey
0x140030197  nop
0x140030198  jmp     loc_1400303E5
0x14003019d  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x1400301a4  mov     rdx, r15; unsigned __int64
0x1400301a7  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x1400301ac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400301b1  mov     ebx, eax
0x1400301b3  test    eax, eax
0x1400301b5  jns     short loc_1400301CD
0x1400301b7  mov     rcx, [rsp+140h+hKey]; hKey
0x1400301bc  test    rcx, rcx
0x1400301bf  jz      short loc_1400301C8
0x1400301c1  call    cs:__imp_RegCloseKey
0x1400301c7  nop
0x1400301c8  jmp     loc_1400303E5
0x1400301cd  mov     r8, rdi; unsigned __int16 *
0x1400301d0  mov     rdx, r15; unsigned __int64
0x1400301d3  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x1400301d8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400301dd  mov     ebx, eax
0x1400301df  test    eax, eax
0x1400301e1  jns     short loc_1400301F9
0x1400301e3  mov     rcx, [rsp+140h+hKey]; hKey
0x1400301e8  test    rcx, rcx
0x1400301eb  jz      short loc_1400301F4
0x1400301ed  call    cs:__imp_RegCloseKey
0x1400301f3  nop
0x1400301f4  jmp     loc_1400303E5
0x1400301f9  lea     r8, asc_140061150; "\\"
0x140030200  mov     rdx, r15; unsigned __int64
0x140030203  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x140030208  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003020d  mov     ebx, eax
0x14003020f  test    eax, eax
0x140030211  jns     short loc_140030229
0x140030213  mov     rcx, [rsp+140h+hKey]; hKey
0x140030218  test    rcx, rcx
0x14003021b  jz      short loc_140030224
0x14003021d  call    cs:__imp_RegCloseKey
0x140030223  nop
0x140030224  jmp     loc_1400303E5
0x140030229  lea     r8, ?c_szEnrollmentsDBLinkedEnrollment@@3PAGA; "LinkedEnrollment"
0x140030230  mov     rdx, r15; unsigned __int64
0x140030233  lea     rcx, [rsp+140h+SubKey]; unsigned __int16 *
0x140030238  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003023d  mov     ebx, eax
0x14003023f  test    eax, eax
0x140030241  jns     short loc_140030259
0x140030243  mov     rcx, [rsp+140h+hKey]; hKey
0x140030248  test    rcx, rcx
0x14003024b  jz      short loc_140030254
0x14003024d  call    cs:__imp_RegCloseKey
0x140030253  nop
0x140030254  jmp     loc_1400303E5
0x140030259  mov     rdi, [rsp+140h+hKey]
0x14003025e  test    rdi, rdi
0x140030261  jz      short loc_14003027D
0x140030263  call    cs:__imp_GetLastError
0x140030269  mov     ebx, eax
0x14003026b  mov     rcx, rdi; hKey
0x14003026e  call    cs:__imp_RegCloseKey
0x140030274  mov     ecx, ebx; dwErrCode
0x140030276  call    cs:__imp_SetLastError
0x14003027c  nop
0x14003027d  mov     [rsp+140h+hKey], r14
0x140030282  lea     rax, [rsp+140h+hKey]
0x140030287  mov     [rsp+140h+phkResult], rax; phkResult
0x14003028c  mov     r9d, 1; samDesired
0x140030292  xor     r8d, r8d; ulOptions
0x140030295  lea     rdx, [rsp+140h+SubKey]; lpSubKey
0x14003029a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400302a1  call    cs:__imp_RegOpenKeyExW
0x1400302a7  mov     ebx, eax
0x1400302a9  mov     edi, 80070000h
0x1400302ae  test    eax, eax
0x1400302b0  jle     short loc_1400302B7
0x1400302b2  movzx   ebx, ax
0x1400302b5  or      ebx, edi
0x1400302b7  test    ebx, ebx
0x1400302b9  jns     short loc_1400302D1
0x1400302bb  mov     rcx, [rsp+140h+hKey]; hKey
0x1400302c0  test    rcx, rcx
0x1400302c3  jz      short loc_1400302CC
0x1400302c5  call    cs:__imp_RegCloseKey
0x1400302cb  nop
0x1400302cc  jmp     loc_1400303E5
0x1400302d1  mov     [rsp+140h+Type], r14d
0x1400302d6  mov     [rsp+140h+cbData], r14d
0x1400302db  lea     rax, [rsp+140h+cbData]
0x1400302e0  mov     [rsp+140h+lpcbData], rax; lpcbData
0x1400302e5  mov     [rsp+140h+phkResult], r14; lpData
0x1400302ea  lea     r9, [rsp+140h+Type]; lpType
0x1400302ef  xor     r8d, r8d; lpReserved
0x1400302f2  lea     rdx, aLinkedenrollme; "LinkedEnrollmentId"
0x1400302f9  mov     rcx, [rsp+140h+hKey]; hKey
0x1400302fe  call    cs:__imp_RegQueryValueExW
0x140030304  mov     ebx, eax
0x140030306  test    eax, eax
0x140030308  jz      short loc_140030327
0x14003030a  jle     short loc_140030311
0x14003030c  movzx   ebx, ax
0x14003030f  or      ebx, edi
0x140030311  mov     rcx, [rsp+140h+hKey]; hKey
0x140030316  test    rcx, rcx
0x140030319  jz      short loc_140030322
0x14003031b  call    cs:__imp_RegCloseKey
0x140030321  nop
0x140030322  jmp     loc_1400303E5
0x140030327  cmp     [rsp+140h+Type], 1
0x14003032c  jz      short loc_140030349
0x14003032e  mov     rcx, [rsp+140h+hKey]; hKey
0x140030333  test    rcx, rcx
0x140030336  jz      short loc_14003033F
0x140030338  call    cs:__imp_RegCloseKey
0x14003033e  nop
0x14003033f  mov     eax, 80070057h
0x140030344  jmp     loc_1400303E7
0x140030349  mov     ebx, [rsp+140h+cbData]
0x14003034d  call    cs:__imp_GetProcessHeap
0x140030353  mov     r8d, ebx; dwBytes
0x140030356  mov     edx, 8; dwFlags
0x14003035b  mov     rcx, rax; hHeap
0x14003035e  call    cs:__imp_HeapAlloc
0x140030364  mov     rdi, rax
0x140030367  test    rax, rax
0x14003036a  jnz     short loc_140030384
0x14003036c  mov     rcx, [rsp+140h+hKey]; hKey
0x140030371  test    rcx, rcx
0x140030374  jz      short loc_14003037D
0x140030376  call    cs:__imp_RegCloseKey
0x14003037c  nop
0x14003037d  mov     eax, 8007000Eh
0x140030382  jmp     short loc_1400303E7
0x140030384  lea     rax, [rsp+140h+cbData]
0x140030389  mov     [rsp+140h+lpcbData], rax; lpcbData
0x14003038e  mov     [rsp+140h+phkResult], rdi; lpData
0x140030393  lea     r9, [rsp+140h+Type]; lpType
0x140030398  xor     r8d, r8d; lpReserved
0x14003039b  lea     rdx, aLinkedenrollme; "LinkedEnrollmentId"
0x1400303a2  mov     rcx, [rsp+140h+hKey]; hKey
0x1400303a7  call    cs:__imp_RegQueryValueExW
0x1400303ad  mov     r8, rdi; unsigned __int16 *
0x1400303b0  mov     edx, 32h ; '2'; unsigned __int64
0x1400303b5  mov     rcx, rsi; unsigned __int16 *
0x1400303b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400303bd  mov     ebx, eax
0x1400303bf  call    cs:__imp_GetProcessHeap
0x1400303c5  mov     rcx, rax; hHeap
0x1400303c8  mov     r8, rdi; lpMem
0x1400303cb  xor     edx, edx; dwFlags
0x1400303cd  call    cs:__imp_HeapFree
0x1400303d3  nop
0x1400303d4  mov     rcx, [rsp+140h+hKey]; hKey
0x1400303d9  test    rcx, rcx
0x1400303dc  jz      short loc_1400303E5
0x1400303de  call    cs:__imp_RegCloseKey
0x1400303e4  nop
0x1400303e5  mov     eax, ebx
0x1400303e7  mov     rcx, [rbp+40h+var_30]
0x1400303eb  xor     rcx, rsp; StackCookie
0x1400303ee  call    __security_check_cookie
0x1400303f3  mov     rbx, [rsp+140h+arg_8]
0x1400303fb  add     rsp, 120h
0x140030402  pop     r15
0x140030404  pop     r14
0x140030406  pop     rdi
0x140030407  pop     rsi
0x140030408  pop     rbp
0x140030409  retn
```
