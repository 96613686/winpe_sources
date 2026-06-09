# GetUserSid

- ea: `0x18007240c`
- end: `0x180072655`
- name: `GetUserSid`
- size: `585`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002a2f0`
- `0x18002a70c`
- `0x18004ed4c`
- `0x180072b8c`

## callees

- `0x180006640`
- `0x1800070f4`
- `0x180008da1`
- `0x18000b694`
- `0x18000b6b4`
- `0x180010c98`
- `0x18002001c`
- `0x18002074c`
- `0x1800221e0`
- `0x180022930`
- `0x180022e34`
- `0x18002613c`
- `0x18004b930`
- `0x18004c19c`
- `0x18004eca0`
- `0x18007240c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800725d9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800725d9`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18007257d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18007257d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180072481`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180072481`

## pseudocode

```c
__int64 __fastcall GetUserSid(__int64 a1, __int64 a2)
{
  _WORD *v3; // rax
  const char *v4; // r9
  unsigned int LastError; // ebx
  __int64 v6; // rbx
  char *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // rax
  const WCHAR *v11; // rax
  const char *v12; // r9
  const char *v13; // r9
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  int ReferencedDomainName; // [rsp+20h] [rbp-E0h]
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-B8h] BYREF
  DWORD nSize; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cbSid; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR lpBuffer[3]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[16]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v25; // [rsp+88h] [rbp-78h]
  _BYTE v26[32]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR v27[8]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v28; // [rsp+C8h] [rbp-38h]
  _BYTE Sid[80]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  std::wstring::wstring(v24, a1);
  v3 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
  if ( *v3 == 46 && v3[1] == 92 )
  {
    nSize = 16;
    std::vector<unsigned short>::vector<unsigned short>(lpBuffer, 16);
    if ( !GetComputerNameW(lpBuffer[0], &nSize) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x15,
                    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\utils.cpp",
                    v4);
      std::vector<unsigned short>::_Tidy(lpBuffer);
      goto LABEL_13;
    }
    v6 = v25;
    v7 = (char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
    v9 = v6 - v8;
    memmove_0(v7, &v7[2 * v8], 2 * v9 + 2);
    v25 = v9;
    v10 = std::operator+<unsigned short>(v26, lpBuffer[0], v24);
    std::wstring::operator=(v24, v10);
    std::wstring::_Tidy_deallocate(v26);
    std::vector<unsigned short>::_Tidy(lpBuffer);
  }
  cbSid = 68;
  memset_0(Sid, 0, 0x44u);
  cchReferencedDomainName = 16;
  peUse = 0;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
  if ( LookupAccountNameW(0, v11, Sid, &cbSid, v27, &cchReferencedDomainName, &peUse) )
  {
    if ( peUse == SidTypeUser )
    {
      StringSid = 0;
      if ( ConvertSidToStringSidW(Sid, &StringSid) )
      {
        v14 = std::_WChar_traits<unsigned short>::length(StringSid);
        std::wstring::_Assign<unsigned short>(a2, v15, v14);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
        LastError = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x28,
                      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\utils.cpp",
                      v13);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      }
    }
    else
    {
      LastError = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\utils.cpp",
        (const char *)0x80070057LL,
        ReferencedDomainName);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x21,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\utils.cpp",
                  v12);
  }
LABEL_13:
  std::wstring::_Tidy_deallocate(v24);
  return LastError;
}

```

## disassembly

```asm
0x18007240c  mov     [rsp-8+arg_10], rbx
0x180072411  mov     [rsp-8+arg_18], rdi
0x180072416  push    rbp
0x180072417  lea     rbp, [rsp-40h]
0x18007241c  sub     rsp, 140h
0x180072423  mov     rax, cs:__security_cookie
0x18007242a  xor     rax, rsp
0x18007242d  mov     [rbp+40h+var_10], rax
0x180072431  mov     rdi, rdx
0x180072434  mov     rdx, rcx
0x180072437  lea     rcx, [rsp+140h+var_C8]
0x18007243c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180072441  lea     rcx, [rsp+140h+var_C8]
0x180072446  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007244b  cmp     word ptr [rax], 2Eh ; '.'
0x18007244f  jnz     loc_180072517
0x180072455  cmp     word ptr [rax+2], 5Ch ; '\'
0x18007245a  jnz     loc_180072517
0x180072460  mov     edx, 10h
0x180072465  mov     [rsp+140h+nSize], 10h
0x18007246d  lea     rcx, [rsp+140h+lpBuffer]
0x180072472  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180072477  mov     rcx, [rsp+140h+lpBuffer]; lpBuffer
0x18007247c  lea     rdx, [rsp+140h+nSize]; nSize
0x180072481  call    cs:__imp_GetComputerNameW
0x180072487  test    eax, eax
0x180072489  jnz     short loc_1800724AF
0x18007248b  mov     rcx, [rbp+48h]; this
0x18007248f  lea     r8, aOnecoreuapBase_48; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180072496  lea     edx, [rax+15h]; void *
0x180072499  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007249e  lea     rcx, [rsp+140h+lpBuffer]
0x1800724a3  mov     ebx, eax
0x1800724a5  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800724aa  jmp     loc_180072628
0x1800724af  mov     rbx, [rbp+40h+var_B8]
0x1800724b3  lea     rcx, [rsp+140h+var_C8]
0x1800724b8  mov     edx, 1
0x1800724bd  cmp     rbx, rdx
0x1800724c0  cmovb   rdx, rbx
0x1800724c4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800724c9  sub     rbx, rdx
0x1800724cc  mov     rcx, rax; void *
0x1800724cf  lea     rdx, [rax+rdx*2]; Src
0x1800724d3  lea     r8, ds:2[rbx*2]; Size
0x1800724db  call    memmove_0
0x1800724e0  mov     rdx, [rsp+140h+lpBuffer]
0x1800724e5  lea     r8, [rsp+140h+var_C8]
0x1800724ea  lea     rcx, [rbp+40h+var_A8]
0x1800724ee  mov     [rbp+40h+var_B8], rbx
0x1800724f2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1800724f7  mov     rdx, rax
0x1800724fa  lea     rcx, [rsp+140h+var_C8]
0x1800724ff  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180072504  lea     rcx, [rbp+40h+var_A8]
0x180072508  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007250d  lea     rcx, [rsp+140h+lpBuffer]
0x180072512  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180072517  mov     r8d, 44h ; 'D'; Size
0x18007251d  lea     rcx, [rbp+40h+Sid]; void *
0x180072521  xor     edx, edx; Val
0x180072523  mov     [rsp+140h+cbSid], r8d
0x180072528  call    memset_0
0x18007252d  xorps   xmm0, xmm0
0x180072530  mov     [rsp+140h+var_EC], 10h
0x180072538  lea     rcx, [rsp+140h+var_C8]
0x18007253d  mov     [rsp+140h+var_100], 0
0x180072545  movups  xmmword ptr [rbp+40h+var_88], xmm0
0x180072549  movups  [rbp+40h+var_78], xmm0
0x18007254d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180072552  mov     rdx, rax; lpAccountName
0x180072555  lea     r9, [rsp+140h+cbSid]; cbSid
0x18007255a  lea     rax, [rsp+140h+var_100]
0x18007255f  xor     ecx, ecx; lpSystemName
0x180072561  mov     [rsp+140h+peUse], rax; peUse
0x180072566  lea     r8, [rbp+40h+Sid]; Sid
0x18007256a  lea     rax, [rsp+140h+var_EC]
0x18007256f  mov     [rsp+140h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180072574  lea     rax, [rbp+40h+var_88]
0x180072578  mov     [rsp+140h+ReferencedDomainName], rax; int
0x18007257d  call    cs:__imp_LookupAccountNameW
0x180072583  test    eax, eax
0x180072585  jnz     short loc_1800725A1
0x180072587  mov     rcx, [rbp+48h]; this
0x18007258b  lea     r8, aOnecoreuapBase_48; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180072592  lea     edx, [rax+21h]; void *
0x180072595  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007259a  mov     ebx, eax
0x18007259c  jmp     loc_180072628
0x1800725a1  cmp     [rsp+140h+var_100], 1
0x1800725a6  jz      short loc_1800725C7
0x1800725a8  mov     rcx, [rbp+48h]; this
0x1800725ac  lea     r8, aOnecoreuapBase_48; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800725b3  mov     ebx, 80070057h
0x1800725b8  mov     edx, 23h ; '#'; void *
0x1800725bd  mov     r9d, ebx; char *
0x1800725c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800725c5  jmp     short loc_180072628
0x1800725c7  lea     rdx, [rsp+140h+StringSid]; StringSid
0x1800725cc  mov     [rsp+140h+StringSid], 0
0x1800725d5  lea     rcx, [rbp+40h+Sid]; Sid
0x1800725d9  call    cs:__imp_ConvertSidToStringSidW
0x1800725df  test    eax, eax
0x1800725e1  jnz     short loc_180072604
0x1800725e3  mov     rcx, [rbp+48h]; this
0x1800725e7  lea     r8, aOnecoreuapBase_48; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800725ee  lea     edx, [rax+28h]; void *
0x1800725f1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800725f6  lea     rcx, [rsp+140h+StringSid]
0x1800725fb  mov     ebx, eax
0x1800725fd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180072602  jmp     short loc_180072628
0x180072604  mov     rcx, [rsp+140h+StringSid]
0x180072609  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18007260e  mov     rdx, rcx
0x180072611  mov     r8, rax
0x180072614  mov     rcx, rdi
0x180072617  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18007261c  lea     rcx, [rsp+140h+StringSid]
0x180072621  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180072626  xor     ebx, ebx
0x180072628  lea     rcx, [rsp+140h+var_C8]
0x18007262d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180072632  mov     eax, ebx
0x180072634  mov     rcx, [rbp+40h+var_10]
0x180072638  xor     rcx, rsp; StackCookie
0x18007263b  call    __security_check_cookie
0x180072640  lea     r11, [rsp+140h+var_s0]
0x180072648  mov     rbx, [r11+20h]
0x18007264c  mov     rdi, [r11+28h]
0x180072650  mov     rsp, r11
0x180072653  pop     rbp
0x180072654  retn
```
