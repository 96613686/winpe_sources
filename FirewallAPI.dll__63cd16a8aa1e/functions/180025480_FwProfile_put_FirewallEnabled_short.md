# FwProfile::put_FirewallEnabled(short)

- ea: `0x180025480`
- end: `0x180025617`
- name: `?put_FirewallEnabled@FwProfile@@UEAAJF@Z`
- size: `407`
- prototype: `__int64 __fastcall(FwProfile *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180021e90`
- `0x180025480`
- `0x180025620`
- `0x1800277b0`
- `0x1800284c4`
- `0x1800436d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180025520`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180025520`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025528`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180025545`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180025545`
- `fwbase!FwBaseAlloc` at `0x180025506`
- `fwbase!FwBaseAlloc` at `0x180025506`
- `fwbase!FwBaseFree` at `0x180025536`
- `fwbase!FwBaseFree` at `0x1800255c3`
- `fwbase!FwBaseFree` at `0x180025536`
- `fwbase!FwBaseFree` at `0x1800255c3`
- `fwbase!FwSizeTMultiply` at `0x1800254ea`
- `fwbase!FwSizeTMultiply` at `0x1800254ea`
- `fwbase!FwReportErrorAsWinError` at `0x1800255ab`
- `fwbase!FwReportErrorAsWinError` at `0x1800255ab`
- `fwbase!FwReportReturnError` at `0x1800255ba`
- `fwbase!FwReportReturnError` at `0x1800255d2`
- `fwbase!FwReportReturnError` at `0x1800255ba`
- `fwbase!FwReportReturnError` at `0x1800255d2`

## string_xrefs

- `0x180025556`: `CompanyName`

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
0x180025480  mov     [rsp+arg_10], rbx
0x180025485  mov     [rsp+arg_18], rbp
0x18002548a  push    rsi
0x18002548b  push    rdi
0x18002548c  push    r14
0x18002548e  sub     rsp, 250h
0x180025495  mov     rax, cs:__security_cookie
0x18002549c  xor     rax, rsp
0x18002549f  mov     [rsp+268h+var_28], rax
0x1800254a7  xor     r14d, r14d
0x1800254aa  movzx   ebx, dx
0x1800254ad  mov     rbp, rcx
0x1800254b0  mov     [rsp+268h+var_248], r14
0x1800254b5  xor     edx, edx; Val
0x1800254b7  mov     [rsp+268h+var_238], r14w
0x1800254bd  lea     rcx, [rsp+268h+var_236]; void *
0x1800254c2  mov     r8d, 206h; Size
0x1800254c8  mov     edi, r14d
0x1800254cb  mov     esi, 104h
0x1800254d0  call    memset_0
0x1800254d5  test    bx, bx
0x1800254d8  jnz     loc_1800255DE
0x1800254de  mov     ecx, esi
0x1800254e0  lea     r8, [rsp+268h+var_248]
0x1800254e5  mov     edx, 2
0x1800254ea  call    cs:__imp_FwSizeTMultiply
0x1800254f0  lea     rbp, aFwprofilePutFi; "FwProfile::put_FirewallEnabled"
0x1800254f7  mov     ebx, eax
0x1800254f9  test    eax, eax
0x1800254fb  js      loc_1800255B5
0x180025501  mov     rcx, [rsp+268h+var_248]
0x180025506  call    cs:__imp_FwBaseAlloc
0x18002550c  mov     rdi, rax
0x18002550f  test    rax, rax
0x180025512  jz      loc_18002559B
0x180025518  mov     r8d, esi; nSize
0x18002551b  mov     rdx, rax; lpFilename
0x18002551e  xor     ecx, ecx; hModule
0x180025520  call    cs:__imp_GetModuleFileNameW
0x180025526  mov     ebx, eax
0x180025528  call    cs:__imp_GetLastError
0x18002552e  cmp     eax, 7Ah ; 'z'
0x180025531  jnz     short loc_180025541
0x180025533  mov     rcx, rdi
0x180025536  call    cs:__imp_FwBaseFree
0x18002553c  mov     rdi, r14
0x18002553f  mov     esi, ebx
0x180025541  test    ebx, ebx
0x180025543  jz      short loc_1800254DE
0x180025545  call    cs:__imp_GetCurrentProcessId
0x18002554b  mov     r9d, 104h; unsigned int
0x180025551  lea     r8, [rsp+268h+var_238]; unsigned __int16 *
0x180025556  lea     rdx, aCompanyname; "CompanyName"
0x18002555d  mov     rcx, rdi; lpwstrFilename
0x180025560  mov     ebx, eax
0x180025562  call    ?FwGetVersionField@@YAJPEBG0PEAGI@Z; FwGetVersionField(ushort const *,ushort const *,ushort *,uint)
0x180025567  test    eax, eax
0x180025569  jns     short loc_180025571
0x18002556b  mov     [rsp+268h+var_238], r14w
0x180025571  lea     r8, [rsp+268h+var_238]
0x180025576  mov     edx, ebx
0x180025578  mov     rcx, rdi
0x18002557b  call    FWNotifyUnsupportedAttempt
0x180025580  mov     ebx, eax
0x180025582  test    eax, eax
0x180025584  jle     short loc_18002558F
0x180025586  movzx   ebx, ax
0x180025589  or      ebx, 80070000h
0x18002558f  test    ebx, ebx
0x180025591  mov     eax, 80004001h
0x180025596  cmovns  ebx, eax
0x180025599  jmp     short loc_1800255C0
0x18002559b  mov     r8d, 8
0x1800255a1  lea     rdx, aFwalloc_0; "FwAlloc"
0x1800255a8  mov     rcx, rbp
0x1800255ab  call    cs:__imp_FwReportErrorAsWinError
0x1800255b1  mov     ebx, eax
0x1800255b3  jmp     short loc_1800255C0
0x1800255b5  mov     edx, eax
0x1800255b7  mov     rcx, rbp
0x1800255ba  call    cs:__imp_FwReportReturnError
0x1800255c0  mov     rcx, rdi
0x1800255c3  call    cs:__imp_FwBaseFree
0x1800255c9  test    ebx, ebx
0x1800255cb  jns     short loc_1800255DA
0x1800255cd  mov     edx, ebx
0x1800255cf  mov     rcx, rbp
0x1800255d2  call    cs:__imp_FwReportReturnError
0x1800255d8  mov     ebx, eax
0x1800255da  mov     eax, ebx
0x1800255dc  jmp     short loc_1800255EF
0x1800255de  movzx   r8d, bx
0x1800255e2  mov     edx, 1
0x1800255e7  mov     rcx, rbp
0x1800255ea  call    ?PutBool@FwProfile@@AEAAJW4_tag_FW_PROFILE_CONFIG@@F@Z; FwProfile::PutBool(_tag_FW_PROFILE_CONFIG,short)
0x1800255ef  mov     rcx, [rsp+268h+var_28]
0x1800255f7  xor     rcx, rsp; StackCookie
0x1800255fa  call    __security_check_cookie
0x1800255ff  lea     r11, [rsp+268h+var_18]
0x180025607  mov     rbx, [r11+30h]
0x18002560b  mov     rbp, [r11+38h]
0x18002560f  mov     rsp, r11
0x180025612  pop     r14
0x180025614  pop     rdi
0x180025615  pop     rsi
0x180025616  retn
```
