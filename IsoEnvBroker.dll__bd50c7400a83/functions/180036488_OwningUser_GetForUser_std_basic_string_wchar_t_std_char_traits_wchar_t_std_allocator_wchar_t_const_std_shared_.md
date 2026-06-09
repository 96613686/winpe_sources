# OwningUser::GetForUser(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::shared_ptr<OwningUser> &)

- ea: `0x180036488`
- end: `0x1800366ac`
- name: `?GetForUser@OwningUser@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$shared_ptr@VOwningUser@@@3@@Z`
- size: `548`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028ac0`
- `0x180029ad0`
- `0x18003a79c`

## callees

- `0x180002520`
- `0x1800030d0`
- `0x18000a464`
- `0x180036178`
- `0x180036254`
- `0x180036488`
- `0x1800366b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036545`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036545`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036558`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036558`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180036523`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180036523`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036550`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800365a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003667a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036550`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800365a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003667a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180036618`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180036618`

## string_xrefs

- `0x1800364e3`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\owninguser.cpp`
- `0x18003657f`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\owninguser.cpp`
- `0x18003665a`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\owninguser.cpp`
- `0x18003662c`: `Invalid SID '%ws' to lookup user.`
- `0x180036573`: `Invalid SID '%ws' for user.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OwningUser::GetForUser(char *a1, __int64 a2)
{
  char *v2; // rdi
  int v3; // eax
  unsigned int LastErrorMsg; // ebx
  BOOL v6; // r13d
  PSID v7; // r12
  HLOCAL *v8; // r14
  HLOCAL v9; // r15
  DWORD LastError; // ebx
  const char *v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  int ReferencedDomainName; // [rsp+20h] [rbp-E0h]
  int ReferencedDomainNamea; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL *p_hMem; // [rsp+58h] [rbp-A8h]
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  char v22; // [rsp+68h] [rbp-98h]
  WCHAR v23[8]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v24; // [rsp+80h] [rbp-80h]
  __int16 v25; // [rsp+90h] [rbp-70h]
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v2 = a1;
  if ( *((_QWORD *)a1 + 2) )
  {
    hMem = 0;
    p_hMem = &hMem;
    Sid = 0;
    v22 = 1;
    if ( *((_QWORD *)a1 + 3) > 7u )
      a1 = *(char **)a1;
    v6 = ConvertStringSidToSidW((LPCWSTR)a1, &Sid);
    if ( v22 )
    {
      v7 = Sid;
      v8 = p_hMem;
      v9 = *p_hMem;
      if ( *p_hMem )
      {
        LastError = GetLastError();
        LocalFree(v9);
        SetLastError(LastError);
      }
      *v8 = v7;
    }
    if ( v6 )
    {
      memset_0(Name, 0, 0x204u);
      cchName = 257;
      *(_OWORD *)v23 = 0;
      v24 = 0;
      v25 = 0;
      cchReferencedDomainName = 16;
      peUse = 0;
      if ( LookupAccountSidW(0, hMem, Name, &cchName, v23, &cchReferencedDomainName, &peUse) )
      {
        v13 = OwningUser::GetForSid(hMem);
        LastErrorMsg = v13;
        if ( v13 >= 0 )
        {
          if ( hMem )
            LocalFree(hMem);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x105,
          (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\owninguser.cpp",
          (const char *)(unsigned int)v13,
          ReferencedDomainNamea);
LABEL_16:
        if ( hMem )
          LocalFree(hMem);
        return LastErrorMsg;
      }
      if ( *((_QWORD *)v2 + 3) > 7u )
        v2 = *(char **)v2;
      v11 = "Invalid SID '%ws' to lookup user.";
      v12 = 259;
    }
    else
    {
      if ( *((_QWORD *)v2 + 3) > 7u )
        v2 = *(char **)v2;
      v11 = "Invalid SID '%ws' for user.";
      v12 = 241;
    }
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)v12,
                     (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\owninguser.cpp",
                     v11,
                     v2);
    goto LABEL_16;
  }
  v3 = OwningUser::GetForCallingProcess(a2);
  LastErrorMsg = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE4,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\owninguser.cpp",
      (const char *)(unsigned int)v3,
      ReferencedDomainName);
    return LastErrorMsg;
  }
  return 0;
}

```

## disassembly

```asm
0x180036488  mov     [rsp-8+arg_10], rbx
0x18003648d  push    rbp
0x18003648e  push    rsi
0x18003648f  push    rdi
0x180036490  push    r12
0x180036492  push    r13
0x180036494  push    r14
0x180036496  push    r15
0x180036498  lea     rbp, [rsp-1C0h]
0x1800364a0  sub     rsp, 2C0h
0x1800364a7  mov     rax, cs:__security_cookie
0x1800364ae  xor     rax, rsp
0x1800364b1  mov     [rbp+1F0h+var_40], rax
0x1800364b8  mov     rsi, rdx
0x1800364bb  mov     rdi, rcx
0x1800364be  xor     r14d, r14d
0x1800364c1  cmp     [rcx+10h], r14
0x1800364c5  jnz     short loc_1800364FB
0x1800364c7  mov     rcx, rdx
0x1800364ca  call    ?GetForCallingProcess@OwningUser@@SAJAEAV?$shared_ptr@VOwningUser@@@std@@@Z; OwningUser::GetForCallingProcess(std::shared_ptr<OwningUser> &)
0x1800364cf  mov     ebx, eax
0x1800364d1  test    eax, eax
0x1800364d3  jns     loc_180036680
0x1800364d9  mov     rcx, [rbp+1F8h]; this
0x1800364e0  mov     r9d, eax; char *
0x1800364e3  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800364ea  mov     edx, 0E4h; void *
0x1800364ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800364f4  mov     eax, ebx
0x1800364f6  jmp     loc_180036682
0x1800364fb  mov     [rsp+2F0h+hMem], r14
0x180036500  lea     rax, [rsp+2F0h+hMem]
0x180036505  mov     [rsp+2F0h+var_298], rax
0x18003650a  mov     [rsp+2F0h+Sid], r14
0x18003650f  mov     [rsp+2F0h+var_288], 1
0x180036514  cmp     qword ptr [rcx+18h], 7
0x180036519  jbe     short loc_18003651E
0x18003651b  mov     rcx, [rcx]; StringSid
0x18003651e  lea     rdx, [rsp+2F0h+Sid]; Sid
0x180036523  call    cs:__imp_ConvertStringSidToSidW
0x180036529  mov     r13d, eax
0x18003652c  cmp     [rsp+2F0h+var_288], r14b
0x180036531  jz      short loc_180036564
0x180036533  mov     r12, [rsp+2F0h+Sid]
0x180036538  mov     r14, [rsp+2F0h+var_298]
0x18003653d  mov     r15, [r14]
0x180036540  test    r15, r15
0x180036543  jz      short loc_18003655E
0x180036545  call    cs:__imp_GetLastError
0x18003654b  mov     ebx, eax
0x18003654d  mov     rcx, r15; hMem
0x180036550  call    cs:__imp_LocalFree
0x180036556  mov     ecx, ebx; dwErrCode
0x180036558  call    cs:__imp_SetLastError
0x18003655e  mov     [r14], r12
0x180036561  xor     r14d, r14d
0x180036564  test    r13d, r13d
0x180036567  jnz     short loc_1800365B2
0x180036569  cmp     qword ptr [rdi+18h], 7
0x18003656e  jbe     short loc_180036573
0x180036570  mov     rdi, [rdi]
0x180036573  lea     r9, aInvalidSidWsFo; "Invalid SID '%ws' for user."
0x18003657a  mov     edx, 0F1h; void *
0x18003657f  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180036586  mov     [rsp+2F0h+ReferencedDomainName], rdi; char *
0x18003658b  mov     rcx, [rbp+1F8h]; this
0x180036592  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180036597  mov     ebx, eax
0x180036599  mov     rcx, [rsp+2F0h+hMem]; hMem
0x18003659e  test    rcx, rcx
0x1800365a1  jz      loc_1800364F4
0x1800365a7  call    cs:__imp_LocalFree
0x1800365ad  jmp     loc_1800364F4
0x1800365b2  xor     edx, edx; Val
0x1800365b4  mov     r8d, 204h; Size
0x1800365ba  lea     rcx, [rbp+1F0h+Name]; void *
0x1800365be  call    memset_0
0x1800365c3  mov     [rsp+2F0h+cchName], 101h
0x1800365cb  xorps   xmm0, xmm0
0x1800365ce  xor     eax, eax
0x1800365d0  movups  xmmword ptr [rsp+2F0h+var_280], xmm0
0x1800365d5  movups  [rbp+1F0h+var_270], xmm0
0x1800365d9  mov     [rbp+1F0h+var_260], ax
0x1800365dd  mov     [rsp+2F0h+var_2A4], 10h
0x1800365e5  mov     [rsp+2F0h+var_2A8], r14d
0x1800365ea  lea     rax, [rsp+2F0h+var_2A8]
0x1800365ef  mov     [rsp+2F0h+peUse], rax; peUse
0x1800365f4  lea     rax, [rsp+2F0h+var_2A4]
0x1800365f9  mov     [rsp+2F0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800365fe  lea     rax, [rsp+2F0h+var_280]
0x180036603  mov     [rsp+2F0h+ReferencedDomainName], rax; int
0x180036608  lea     r9, [rsp+2F0h+cchName]; cchName
0x18003660d  lea     r8, [rbp+1F0h+Name]; Name
0x180036611  mov     rdx, [rsp+2F0h+hMem]; Sid
0x180036616  xor     ecx, ecx; lpSystemName
0x180036618  call    cs:__imp_LookupAccountSidW
0x18003661e  test    eax, eax
0x180036620  jnz     short loc_18003663D
0x180036622  cmp     qword ptr [rdi+18h], 7
0x180036627  jbe     short loc_18003662C
0x180036629  mov     rdi, [rdi]
0x18003662c  lea     r9, aInvalidSidWsTo; "Invalid SID '%ws' to lookup user."
0x180036633  mov     edx, 103h
0x180036638  jmp     loc_18003657F
0x18003663d  mov     rdx, rsi
0x180036640  mov     rcx, [rsp+2F0h+hMem]; void *
0x180036645  call    ?GetForSid@OwningUser@@SAJPEAXAEAV?$shared_ptr@VOwningUser@@@std@@@Z; OwningUser::GetForSid(void *,std::shared_ptr<OwningUser> &)
0x18003664a  mov     ebx, eax
0x18003664c  test    eax, eax
0x18003664e  jns     short loc_180036670
0x180036650  mov     rcx, [rbp+1F8h]; this
0x180036657  mov     r9d, eax; char *
0x18003665a  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180036661  mov     edx, 105h; void *
0x180036666  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003666b  jmp     loc_180036599
0x180036670  mov     rcx, [rsp+2F0h+hMem]; hMem
0x180036675  test    rcx, rcx
0x180036678  jz      short loc_180036680
0x18003667a  call    cs:__imp_LocalFree
0x180036680  xor     eax, eax
0x180036682  mov     rcx, [rbp+1F0h+var_40]
0x180036689  xor     rcx, rsp; StackCookie
0x18003668c  call    __security_check_cookie
0x180036691  mov     rbx, [rsp+2F0h+arg_10]
0x180036699  add     rsp, 2C0h
0x1800366a0  pop     r15
0x1800366a2  pop     r14
0x1800366a4  pop     r13
0x1800366a6  pop     r12
0x1800366a8  pop     rdi
0x1800366a9  pop     rsi
0x1800366aa  pop     rbp
0x1800366ab  retn
```
