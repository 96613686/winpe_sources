# FwProfile::put_FirewallEnabled(short)

- ea: `0x180027060`
- end: `0x180027238`
- name: `?put_FirewallEnabled@FwProfile@@UEAAJF@Z`
- size: `472`
- prototype: `__int64 __fastcall(FwProfile *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800236f0`
- `0x180027060`
- `0x180027240`
- `0x1800294b0`
- `0x18002a1f4`
- `0x180046b08`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002710c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002710c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002711a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002711a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027147`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027147`
- `fwbase!FwBaseAlloc` at `0x1800270ec`
- `fwbase!FwBaseAlloc` at `0x1800270ec`
- `fwbase!FwBaseFree` at `0x18002712e`
- `fwbase!FwBaseFree` at `0x1800271d7`
- `fwbase!FwBaseFree` at `0x18002712e`
- `fwbase!FwBaseFree` at `0x1800271d7`
- `fwbase!FwSizeTMultiply` at `0x1800270ca`
- `fwbase!FwSizeTMultiply` at `0x1800270ca`
- `fwbase!FwReportErrorAsWinError` at `0x1800271b3`
- `fwbase!FwReportErrorAsWinError` at `0x1800271b3`
- `fwbase!FwReportReturnError` at `0x1800271c8`
- `fwbase!FwReportReturnError` at `0x1800271ec`
- `fwbase!FwReportReturnError` at `0x1800271c8`
- `fwbase!FwReportReturnError` at `0x1800271ec`

## string_xrefs

- `0x18002715e`: `CompanyName`

## pseudocode

```c
__int64 __fastcall FwProfile::put_FirewallEnabled(FwProfile *this, unsigned __int16 a2)
{
  const WCHAR *v4; // rdi
  DWORD v5; // esi
  int v6; // eax
  signed int v7; // ebx
  WCHAR *v8; // rax
  DWORD ModuleFileNameW; // ebx
  DWORD CurrentProcessId; // ebx
  int v11; // eax
  __int64 v13; // [rsp+20h] [rbp-248h] BYREF
  unsigned __int16 v14; // [rsp+30h] [rbp-238h] BYREF
  _BYTE v15[526]; // [rsp+32h] [rbp-236h] BYREF

  v13 = 0;
  v14 = 0;
  v4 = 0;
  v5 = 260;
  memset_0(v15, 0, 0x206u);
  if ( a2 )
    return FwProfile::PutBool(this, 1, a2);
  do
  {
    v6 = FwSizeTMultiply(v5, 2, &v13);
    v7 = v6;
    if ( v6 < 0 )
    {
      FwReportReturnError("FwProfile::put_FirewallEnabled", (unsigned int)v6);
      goto LABEL_16;
    }
    v8 = (WCHAR *)FwBaseAlloc(v13);
    v4 = v8;
    if ( !v8 )
    {
      v7 = FwReportErrorAsWinError("FwProfile::put_FirewallEnabled", "FwAlloc", 8);
      goto LABEL_16;
    }
    ModuleFileNameW = GetModuleFileNameW(0, v8, v5);
    if ( GetLastError() == 122 )
    {
      FwBaseFree(v4);
      v4 = 0;
      v5 = ModuleFileNameW;
    }
  }
  while ( !ModuleFileNameW );
  CurrentProcessId = GetCurrentProcessId();
  if ( (int)FwGetVersionField(v4, L"CompanyName", &v14, 0x104u) < 0 )
    v14 = 0;
  v11 = FWNotifyUnsupportedAttempt(v4, CurrentProcessId, &v14);
  v7 = v11;
  if ( v11 > 0 )
    v7 = (unsigned __int16)v11 | 0x80070000;
  if ( v7 >= 0 )
    v7 = -2147467263;
LABEL_16:
  FwBaseFree(v4);
  if ( v7 < 0 )
    return (unsigned int)FwReportReturnError("FwProfile::put_FirewallEnabled", (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180027060  mov     [rsp+arg_10], rbx
0x180027065  mov     [rsp+arg_18], rbp
0x18002706a  push    rsi
0x18002706b  push    rdi
0x18002706c  push    r14
0x18002706e  sub     rsp, 250h
0x180027075  mov     rax, cs:__security_cookie
0x18002707c  xor     rax, rsp
0x18002707f  mov     [rsp+268h+var_28], rax
0x180027087  xor     r14d, r14d
0x18002708a  movzx   ebx, dx
0x18002708d  mov     rbp, rcx
0x180027090  mov     [rsp+268h+var_248], r14
0x180027095  xor     edx, edx; Val
0x180027097  mov     [rsp+268h+var_238], r14w
0x18002709d  lea     rcx, [rsp+268h+var_236]; void *
0x1800270a2  mov     r8d, 206h; Size
0x1800270a8  mov     edi, r14d
0x1800270ab  mov     esi, 104h
0x1800270b0  call    memset_0
0x1800270b5  test    bx, bx
0x1800270b8  jnz     loc_1800271FE
0x1800270be  mov     ecx, esi
0x1800270c0  lea     r8, [rsp+268h+var_248]
0x1800270c5  mov     edx, 2
0x1800270ca  call    cs:__imp_FwSizeTMultiply
0x1800270d1  nop     dword ptr [rax+rax+00h]
0x1800270d6  lea     rbp, aFwprofilePutFi; "FwProfile::put_FirewallEnabled"
0x1800270dd  mov     ebx, eax
0x1800270df  test    eax, eax
0x1800270e1  js      loc_1800271C3
0x1800270e7  mov     rcx, [rsp+268h+var_248]
0x1800270ec  call    cs:__imp_FwBaseAlloc
0x1800270f3  nop     dword ptr [rax+rax+00h]
0x1800270f8  mov     rdi, rax
0x1800270fb  test    rax, rax
0x1800270fe  jz      loc_1800271A3
0x180027104  mov     r8d, esi; nSize
0x180027107  mov     rdx, rax; lpFilename
0x18002710a  xor     ecx, ecx; hModule
0x18002710c  call    cs:__imp_GetModuleFileNameW
0x180027113  nop     dword ptr [rax+rax+00h]
0x180027118  mov     ebx, eax
0x18002711a  call    cs:__imp_GetLastError
0x180027121  nop     dword ptr [rax+rax+00h]
0x180027126  cmp     eax, 7Ah ; 'z'
0x180027129  jnz     short loc_18002713F
0x18002712b  mov     rcx, rdi
0x18002712e  call    cs:__imp_FwBaseFree
0x180027135  nop     dword ptr [rax+rax+00h]
0x18002713a  mov     rdi, r14
0x18002713d  mov     esi, ebx
0x18002713f  test    ebx, ebx
0x180027141  jz      loc_1800270BE
0x180027147  call    cs:__imp_GetCurrentProcessId
0x18002714e  nop     dword ptr [rax+rax+00h]
0x180027153  mov     r9d, 104h; unsigned int
0x180027159  lea     r8, [rsp+268h+var_238]; unsigned __int16 *
0x18002715e  lea     rdx, aCompanyname; "CompanyName"
0x180027165  mov     rcx, rdi; lpwstrFilename
0x180027168  mov     ebx, eax
0x18002716a  call    ?FwGetVersionField@@YAJPEBG0PEAGI@Z; FwGetVersionField(ushort const *,ushort const *,ushort *,uint)
0x18002716f  test    eax, eax
0x180027171  jns     short loc_180027179
0x180027173  mov     [rsp+268h+var_238], r14w
0x180027179  lea     r8, [rsp+268h+var_238]
0x18002717e  mov     edx, ebx
0x180027180  mov     rcx, rdi
0x180027183  call    FWNotifyUnsupportedAttempt
0x180027188  mov     ebx, eax
0x18002718a  test    eax, eax
0x18002718c  jle     short loc_180027197
0x18002718e  movzx   ebx, ax
0x180027191  or      ebx, 80070000h
0x180027197  test    ebx, ebx
0x180027199  mov     eax, 80004001h
0x18002719e  cmovns  ebx, eax
0x1800271a1  jmp     short loc_1800271D4
0x1800271a3  mov     r8d, 8
0x1800271a9  lea     rdx, aFwalloc_0; "FwAlloc"
0x1800271b0  mov     rcx, rbp
0x1800271b3  call    cs:__imp_FwReportErrorAsWinError
0x1800271ba  nop     dword ptr [rax+rax+00h]
0x1800271bf  mov     ebx, eax
0x1800271c1  jmp     short loc_1800271D4
0x1800271c3  mov     edx, eax
0x1800271c5  mov     rcx, rbp
0x1800271c8  call    cs:__imp_FwReportReturnError
0x1800271cf  nop     dword ptr [rax+rax+00h]
0x1800271d4  mov     rcx, rdi
0x1800271d7  call    cs:__imp_FwBaseFree
0x1800271de  nop     dword ptr [rax+rax+00h]
0x1800271e3  test    ebx, ebx
0x1800271e5  jns     short loc_1800271FA
0x1800271e7  mov     edx, ebx
0x1800271e9  mov     rcx, rbp
0x1800271ec  call    cs:__imp_FwReportReturnError
0x1800271f3  nop     dword ptr [rax+rax+00h]
0x1800271f8  mov     ebx, eax
0x1800271fa  mov     eax, ebx
0x1800271fc  jmp     short loc_18002720F
0x1800271fe  movzx   r8d, bx
0x180027202  mov     edx, 1
0x180027207  mov     rcx, rbp
0x18002720a  call    ?PutBool@FwProfile@@AEAAJW4_tag_FW_PROFILE_CONFIG@@F@Z; FwProfile::PutBool(_tag_FW_PROFILE_CONFIG,short)
0x18002720f  mov     rcx, [rsp+268h+var_28]
0x180027217  xor     rcx, rsp; StackCookie
0x18002721a  call    __security_check_cookie
0x18002721f  lea     r11, [rsp+268h+var_18]
0x180027227  mov     rbx, [r11+30h]
0x18002722b  mov     rbp, [r11+38h]
0x18002722f  mov     rsp, r11
0x180027232  pop     r14
0x180027234  pop     rdi
0x180027235  pop     rsi
0x180027236  retn
```
