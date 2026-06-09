# MakeActiveUserLocalAdmin

- ea: `0x140013650`
- end: `0x14001397f`
- name: `MakeActiveUserLocalAdmin`
- size: `815`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x1400045a8`
- `0x140004660`
- `0x140004e28`
- `0x140009594`
- `0x1400095b4`
- `0x140013494`
- `0x140013650`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400138a1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400138a1`
- `DMCmnUtils!DmGetActiveUserSid` at `0x14001366a`
- `DMCmnUtils!DmGetActiveUserSid` at `0x14001366a`
- `DMCmnUtils!DmDeleteTask` at `0x140013933`
- `DMCmnUtils!DmDeleteTask` at `0x140013933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001393e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001393e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140013706`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x14001383f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140013706`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x14001383f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400137fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001380b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001387a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001388a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400138c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400138d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001395c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001396c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400137fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001380b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001387a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001388a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400138c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400138d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001395c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001396c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1400136a3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1400136a3`

## string_xrefs

- `0x140013923`: `Login Schedule created by enrollment client`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 MakeActiveUserLocalAdmin()
{
  int ActiveUserSid; // eax
  unsigned int v1; // ebx
  const char *v2; // r9
  unsigned int LastError; // eax
  unsigned __int64 v4; // rbx
  void *v5; // rax
  void *v6; // rdi
  unsigned __int64 v7; // rsi
  void *v8; // rax
  void *v9; // rbx
  void *v10; // rcx
  const char *v12; // r9
  unsigned int v13; // esi
  int AUserLocalAdmin; // eax
  signed int v15; // eax
  int ReferencedDomainName; // [rsp+20h] [rbp-30h]
  int ReferencedDomainNamea; // [rsp+20h] [rbp-30h]
  int ReferencedDomainNameb; // [rsp+20h] [rbp-30h]
  LPCWSTR StringSid; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  DWORD cchReferencedDomainName; // [rsp+80h] [rbp+30h] BYREF
  DWORD cchName; // [rsp+88h] [rbp+38h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+90h] [rbp+40h] BYREF
  PSID Sid; // [rsp+98h] [rbp+48h] BYREF

  StringSid = 0;
  ActiveUserSid = DmGetActiveUserSid((unsigned __int16 **)&StringSid);
  v1 = ActiveUserSid;
  if ( ActiveUserSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5CA,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
      (const char *)(unsigned int)ActiveUserSid,
      ReferencedDomainName);
LABEL_49:
    if ( StringSid )
      LocalFree((HLOCAL)StringSid);
    return v1;
  }
  Sid = 0;
  if ( !ConvertStringSidToSidW(StringSid, &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x5CE,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
                  v2);
LABEL_5:
    v1 = LastError;
LABEL_47:
    if ( Sid )
      LocalFree(Sid);
    goto LABEL_49;
  }
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) || GetLastError() != 122 )
  {
    v15 = GetLastError();
    v1 = v15;
    if ( v15 > 0 )
      v1 = (unsigned __int16)v15 | 0x80070000;
    goto LABEL_47;
  }
  v4 = 2LL * (cchName + 1);
  if ( !is_mul_ok(cchName + 1, 2u) )
    v4 = -1;
  v5 = operator new[](v4, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( v5 )
    memset_0(v5, 0, v4);
  else
    v6 = 0;
  v7 = 2LL * (cchReferencedDomainName + 1);
  if ( !is_mul_ok(cchReferencedDomainName + 1, 2u) )
    v7 = -1;
  v8 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( v8 )
    memset_0(v8, 0, v7);
  else
    v9 = 0;
  if ( !v6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
      (const char *)0x8007000ELL,
      ReferencedDomainNamea);
    if ( !v9 )
    {
LABEL_24:
      if ( Sid )
        LocalFree(Sid);
      if ( StringSid )
        LocalFree((HLOCAL)StringSid);
      return 2147942414LL;
    }
    v10 = v9;
LABEL_23:
    operator delete(v10);
    goto LABEL_24;
  }
  if ( !v9 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E1,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
      (const char *)0x8007000ELL,
      ReferencedDomainNamea);
    v10 = v6;
    goto LABEL_23;
  }
  if ( !LookupAccountSidW(0, Sid, (LPWSTR)v6, &cchName, (LPWSTR)v9, &cchReferencedDomainName, &peUse) )
  {
    v13 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x5EC,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
            v12);
LABEL_31:
    operator delete(v9);
    operator delete(v6);
    if ( Sid )
      LocalFree(Sid);
    if ( StringSid )
      LocalFree((HLOCAL)StringSid);
    return v13;
  }
  if ( (unsigned int)_o__wcsicmp(v6, L"defaultuser0") )
  {
    AUserLocalAdmin = MakeAUserLocalAdmin((unsigned __int16 *)v6, (unsigned __int16 *)v9);
    v13 = AUserLocalAdmin;
    if ( AUserLocalAdmin >= 0 )
    {
      operator delete(v9);
      operator delete(v6);
      LastError = DmDeleteTask(
                    L"\\Microsoft\\Windows\\EnterpriseMgmt",
                    0,
                    L"Login Schedule created by enrollment client");
      goto LABEL_5;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
      (const char *)(unsigned int)AUserLocalAdmin,
      ReferencedDomainNameb);
    goto LABEL_31;
  }
  operator delete(v9);
  operator delete(v6);
  if ( Sid )
    LocalFree(Sid);
  if ( StringSid )
    LocalFree((HLOCAL)StringSid);
  return 1;
}

```

## disassembly

```asm
0x140013650  push    rbp
0x140013652  push    rbx
0x140013653  push    rsi
0x140013654  push    rdi
0x140013655  push    r15
0x140013657  mov     rbp, rsp
0x14001365a  sub     rsp, 50h
0x14001365e  mov     [rbp+StringSid], 0
0x140013666  lea     rcx, [rbp+StringSid]
0x14001366a  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x140013670  mov     ebx, eax
0x140013672  test    eax, eax
0x140013674  jns     short loc_140013693
0x140013676  mov     rcx, [rbp+28h]; this
0x14001367a  mov     r9d, eax; char *
0x14001367d  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140013684  mov     edx, 5CAh; void *
0x140013689  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001368e  jmp     loc_140013963
0x140013693  mov     [rbp+Sid], 0
0x14001369b  lea     rdx, [rbp+Sid]; Sid
0x14001369f  mov     rcx, [rbp+StringSid]; StringSid
0x1400136a3  call    cs:__imp_ConvertStringSidToSidW
0x1400136a9  test    eax, eax
0x1400136ab  jnz     short loc_1400136C9
0x1400136ad  mov     rcx, [rbp+28h]; this
0x1400136b1  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1400136b8  mov     edx, 5CEh; void *
0x1400136bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400136c2  mov     ebx, eax
0x1400136c4  jmp     loc_140013953
0x1400136c9  mov     [rbp+cchName], 0
0x1400136d0  mov     [rbp+arg_0], 0
0x1400136d7  mov     [rbp+arg_10], 0
0x1400136de  lea     rax, [rbp+arg_10]
0x1400136e2  mov     [rsp+50h+peUse], rax; peUse
0x1400136e7  lea     rax, [rbp+arg_0]
0x1400136eb  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1400136f0  mov     [rsp+50h+ReferencedDomainName], 0; int
0x1400136f9  lea     r9, [rbp+cchName]; cchName
0x1400136fd  xor     r8d, r8d; Name
0x140013700  mov     rdx, [rbp+Sid]; Sid
0x140013704  xor     ecx, ecx; lpSystemName
0x140013706  call    cs:__imp_LookupAccountSidW
0x14001370c  test    eax, eax
0x14001370e  jnz     loc_14001393E
0x140013714  call    cs:__imp_GetLastError
0x14001371a  cmp     eax, 7Ah ; 'z'
0x14001371d  jnz     loc_14001393E
0x140013723  mov     ecx, [rbp+cchName]
0x140013726  inc     ecx
0x140013728  lea     esi, [rax-78h]
0x14001372b  mov     eax, esi
0x14001372d  mul     rcx
0x140013730  mov     rbx, rax
0x140013733  lea     r15, [rsi-3]
0x140013737  cmovb   rbx, r15
0x14001373b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140013742  mov     rcx, rbx; unsigned __int64
0x140013745  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14001374a  mov     rdi, rax
0x14001374d  test    rax, rax
0x140013750  jz      short loc_140013761
0x140013752  mov     r8, rbx; Size
0x140013755  xor     edx, edx; Val
0x140013757  mov     rcx, rax; void *
0x14001375a  call    memset_0
0x14001375f  jmp     short loc_140013763
0x140013761  xor     edi, edi
0x140013763  mov     r8d, [rbp+arg_0]
0x140013767  inc     r8d
0x14001376a  mov     rax, rsi
0x14001376d  mul     r8
0x140013770  mov     rsi, rax
0x140013773  cmovb   rsi, r15
0x140013777  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001377e  mov     rcx, rsi; unsigned __int64
0x140013781  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140013786  mov     rbx, rax
0x140013789  test    rax, rax
0x14001378c  jz      short loc_14001379D
0x14001378e  mov     r8, rsi; Size
0x140013791  xor     edx, edx; Val
0x140013793  mov     rcx, rax; void *
0x140013796  call    memset_0
0x14001379b  jmp     short loc_14001379F
0x14001379d  xor     ebx, ebx
0x14001379f  test    rdi, rdi
0x1400137a2  jnz     short loc_1400137C9
0x1400137a4  mov     rcx, [rbp+28h]; this
0x1400137a8  mov     r9d, 8007000Eh; char *
0x1400137ae  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1400137b5  mov     edx, 5E0h; void *
0x1400137ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400137bf  test    rbx, rbx
0x1400137c2  jz      short loc_1400137F2
0x1400137c4  mov     rcx, rbx
0x1400137c7  jmp     short loc_1400137EC
0x1400137c9  test    rbx, rbx
0x1400137cc  jnz     short loc_14001381B
0x1400137ce  mov     rcx, [rbp+28h]; this
0x1400137d2  mov     r9d, 8007000Eh; char *
0x1400137d8  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1400137df  mov     edx, 5E1h; void *
0x1400137e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400137e9  mov     rcx, rdi; Block
0x1400137ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400137f1  nop
0x1400137f2  mov     rcx, [rbp+Sid]; hMem
0x1400137f6  test    rcx, rcx
0x1400137f9  jz      short loc_140013802
0x1400137fb  call    cs:__imp_LocalFree
0x140013801  nop
0x140013802  mov     rcx, [rbp+StringSid]; hMem
0x140013806  test    rcx, rcx
0x140013809  jz      short loc_140013811
0x14001380b  call    cs:__imp_LocalFree
0x140013811  mov     eax, 8007000Eh
0x140013816  jmp     loc_140013974
0x14001381b  lea     rax, [rbp+arg_10]
0x14001381f  mov     [rsp+50h+peUse], rax; peUse
0x140013824  lea     rax, [rbp+arg_0]
0x140013828  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14001382d  mov     [rsp+50h+ReferencedDomainName], rbx; int
0x140013832  lea     r9, [rbp+cchName]; cchName
0x140013836  mov     r8, rdi; Name
0x140013839  mov     rdx, [rbp+Sid]; Sid
0x14001383d  xor     ecx, ecx; lpSystemName
0x14001383f  call    cs:__imp_LookupAccountSidW
0x140013845  test    eax, eax
0x140013847  jnz     short loc_140013897
0x140013849  mov     rcx, [rbp+28h]; this
0x14001384d  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140013854  mov     edx, 5ECh; void *
0x140013859  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001385e  mov     esi, eax
0x140013860  mov     rcx, rbx; Block
0x140013863  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140013868  mov     rcx, rdi; Block
0x14001386b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140013870  nop
0x140013871  mov     rcx, [rbp+Sid]; hMem
0x140013875  test    rcx, rcx
0x140013878  jz      short loc_140013881
0x14001387a  call    cs:__imp_LocalFree
0x140013880  nop
0x140013881  mov     rcx, [rbp+StringSid]; hMem
0x140013885  test    rcx, rcx
0x140013888  jz      short loc_140013890
0x14001388a  call    cs:__imp_LocalFree
0x140013890  mov     eax, esi
0x140013892  jmp     loc_140013974
0x140013897  lea     rdx, aDefaultuser0; "defaultuser0"
0x14001389e  mov     rcx, rdi
0x1400138a1  call    cs:__imp__o__wcsicmp
0x1400138a7  test    eax, eax
0x1400138a9  jnz     short loc_1400138E5
0x1400138ab  mov     rcx, rbx; Block
0x1400138ae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400138b3  mov     rcx, rdi; Block
0x1400138b6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400138bb  nop
0x1400138bc  mov     rcx, [rbp+Sid]; hMem
0x1400138c0  test    rcx, rcx
0x1400138c3  jz      short loc_1400138CC
0x1400138c5  call    cs:__imp_LocalFree
0x1400138cb  nop
0x1400138cc  mov     rcx, [rbp+StringSid]; hMem
0x1400138d0  test    rcx, rcx
0x1400138d3  jz      short loc_1400138DB
0x1400138d5  call    cs:__imp_LocalFree
0x1400138db  mov     eax, 1
0x1400138e0  jmp     loc_140013974
0x1400138e5  mov     rdx, rbx; unsigned __int16 *
0x1400138e8  mov     rcx, rdi; unsigned __int16 *
0x1400138eb  call    MakeAUserLocalAdmin
0x1400138f0  mov     esi, eax
0x1400138f2  test    eax, eax
0x1400138f4  jns     short loc_140013913
0x1400138f6  mov     rcx, [rbp+28h]; this
0x1400138fa  mov     r9d, eax; char *
0x1400138fd  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140013904  mov     edx, 5F5h; void *
0x140013909  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001390e  jmp     loc_140013860
0x140013913  mov     rcx, rbx; Block
0x140013916  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001391b  mov     rcx, rdi; Block
0x14001391e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140013923  lea     r8, aLoginScheduleC_0; "Login Schedule created by enrollment cl"...
0x14001392a  xor     edx, edx
0x14001392c  lea     rcx, aMicrosoftWindo_4; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x140013933  call    cs:__imp_?DmDeleteTask@@YAJPEBG00@Z; DmDeleteTask(ushort const *,ushort const *,ushort const *)
0x140013939  jmp     loc_1400136C2
0x14001393e  call    cs:__imp_GetLastError
0x140013944  mov     ebx, eax
0x140013946  test    eax, eax
0x140013948  jle     short loc_140013953
0x14001394a  movzx   ebx, ax
0x14001394d  or      ebx, 80070000h
0x140013953  mov     rcx, [rbp+Sid]; hMem
0x140013957  test    rcx, rcx
0x14001395a  jz      short loc_140013963
0x14001395c  call    cs:__imp_LocalFree
0x140013962  nop
0x140013963  mov     rcx, [rbp+StringSid]; hMem
0x140013967  test    rcx, rcx
0x14001396a  jz      short loc_140013972
0x14001396c  call    cs:__imp_LocalFree
0x140013972  mov     eax, ebx
0x140013974  add     rsp, 50h
0x140013978  pop     r15
0x14001397a  pop     rdi
0x14001397b  pop     rsi
0x14001397c  pop     rbx
0x14001397d  pop     rbp
0x14001397e  retn
```
