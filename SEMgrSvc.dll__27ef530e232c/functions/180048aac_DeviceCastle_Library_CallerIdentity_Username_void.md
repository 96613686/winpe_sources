# DeviceCastle::Library::CallerIdentity::Username(void)

- ea: `0x180048aac`
- end: `0x180048d26`
- name: `?Username@CallerIdentity@Library@DeviceCastle@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `634`
- prototype: ``
- caller_count: `13`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004bf9c`
- `0x18004e650`
- `0x18005069c`
- `0x180050934`
- `0x180066d50`
- `0x1800692f0`
- `0x180069550`
- `0x180069780`
- `0x18006a000`
- `0x18006abb0`
- `0x18006ae30`
- `0x18006b050`
- `0x18006bc20`

## callees

- `0x1800049a0`
- `0x18000584c`
- `0x180013014`
- `0x180013274`
- `0x18003c35c`
- `0x1800474d8`
- `0x180048060`
- `0x180048aac`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048c83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048c83`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180048bc8`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180048c79`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180048bc8`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180048c79`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
_QWORD *__fastcall DeviceCastle::Library::CallerIdentity::Username(_QWORD *a1)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // r15
  signed int v4; // esi
  __int64 v5; // r8
  _WORD *v6; // rbx
  PSID *v7; // rax
  signed int v8; // eax
  WCHAR *ReferencedDomainName; // r12
  WCHAR *v10; // r13
  PSID *v11; // rax
  signed int LastError; // eax
  _WORD *v13; // rax
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-78h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-74h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-70h] BYREF
  _QWORD *v18; // [rsp+50h] [rbp-68h]
  _QWORD *v19; // [rsp+58h] [rbp-60h]
  LPWSTR Name[2]; // [rsp+60h] [rbp-58h] BYREF
  __m128i si128; // [rsp+70h] [rbp-48h]

  v2 = a1 + 16;
  v18 = a1 + 16;
  v3 = a1 + 18;
  v19 = a1 + 18;
  if ( a1[18] || !(*(__int64 (__fastcall **)(_QWORD *))(*a1 + 96LL))(a1) )
    return v2;
  v4 = 0;
  if ( (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 96LL))(a1) )
  {
    cchName = 0;
    cchReferencedDomainName = 0;
    *(_OWORD *)Name = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Name[0]) = 0;
    peUse = 0;
    v7 = (PSID *)(*(__int64 (__fastcall **)(_QWORD *))(*a1 + 16LL))(a1);
    if ( LookupAccountSidW(0, *v7, 0, &cchName, 0, &cchReferencedDomainName, &peUse)
      || (v8 = GetLastError(), v4 = v8, v8 == 122) )
    {
      if ( cchName )
        std::wstring::resize(Name);
      if ( cchReferencedDomainName )
        std::wstring::resize(v2);
      if ( v2[3] <= 7u )
        ReferencedDomainName = (WCHAR *)v2;
      else
        ReferencedDomainName = (WCHAR *)*v2;
      v10 = (WCHAR *)Name;
      if ( si128.m128i_i64[1] > 7uLL )
        v10 = Name[0];
      v11 = (PSID *)(*(__int64 (__fastcall **)(_QWORD *))(*a1 + 16LL))(a1);
      if ( LookupAccountSidW(0, *v11, v10, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
      {
        std::wstring::append(v2, (void *)L"\\");
        std::wstring::operator+=(v2);
        std::wstring::~wstring(Name);
        goto LABEL_26;
      }
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else if ( v8 > 0 )
    {
      v4 = (unsigned __int16)v8 | 0x80070000;
    }
    std::wstring::~wstring(Name);
    goto LABEL_26;
  }
  if ( v2[3] < 0x18u )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      v2,
      24,
      v5,
      L"_Device Castle Internal_");
  }
  else
  {
    v6 = (_WORD *)*v2;
    *v3 = 24;
    memmove_0(v6, L"_Device Castle Internal_", 0x30u);
    v6[24] = 0;
  }
LABEL_26:
  if ( v4 < 0 )
  {
    *v3 = 0;
    if ( v2[3] <= 7u )
      v13 = v2;
    else
      v13 = (_WORD *)*v2;
    *v13 = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180048aac  mov     [rsp+arg_8], rbx
0x180048ab1  mov     [rsp+arg_10], rsi
0x180048ab6  push    rdi
0x180048ab7  push    r12
0x180048ab9  push    r13
0x180048abb  push    r14
0x180048abd  push    r15
0x180048abf  sub     rsp, 90h
0x180048ac6  mov     rax, cs:__security_cookie
0x180048acd  xor     rax, rsp
0x180048ad0  mov     [rsp+0B8h+var_38], rax
0x180048ad8  mov     rbx, rcx
0x180048adb  lea     rdi, [rcx+80h]
0x180048ae2  mov     [rsp+0B8h+var_68], rdi
0x180048ae7  lea     r15, [rdi+10h]
0x180048aeb  mov     [rsp+0B8h+var_60], r15
0x180048af0  xor     r14d, r14d
0x180048af3  cmp     [r15], r14
0x180048af6  jnz     loc_180048CF6
0x180048afc  mov     rax, [rcx]
0x180048aff  mov     rax, [rax+60h]
0x180048b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b08  test    rax, rax
0x180048b0b  jz      loc_180048CF6
0x180048b11  mov     esi, r14d
0x180048b14  mov     rax, [rbx]
0x180048b17  mov     rcx, rbx
0x180048b1a  mov     rax, [rax+60h]
0x180048b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b23  test    rax, rax
0x180048b26  jnz     short loc_180048B68
0x180048b28  lea     edx, [rax+18h]
0x180048b2b  cmp     [rdi+18h], rdx
0x180048b2f  jb      short loc_180048B54
0x180048b31  mov     rbx, [rdi]
0x180048b34  mov     [r15], rdx
0x180048b37  lea     r8d, [r14+30h]; Size
0x180048b3b  lea     rdx, aDeviceCastleIn; "_Device Castle Internal_"
0x180048b42  mov     rcx, rbx; void *
0x180048b45  call    memmove_0
0x180048b4a  mov     [rbx+30h], r14w
0x180048b4f  jmp     loc_180048CCD
0x180048b54  lea     r9, aDeviceCastleIn; "_Device Castle Internal_"
0x180048b5b  mov     rcx, rdi
0x180048b5e  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180048b63  jmp     loc_180048CCD
0x180048b68  mov     [rsp+0B8h+cchName], r14d
0x180048b6d  mov     [rsp+0B8h+var_78], r14d
0x180048b72  xorps   xmm0, xmm0
0x180048b75  movups  xmmword ptr [rsp+0B8h+Name], xmm0
0x180048b7a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180048b82  movdqu  [rsp+0B8h+var_48], xmm1
0x180048b88  mov     word ptr [rsp+0B8h+Name], r14w
0x180048b8e  mov     [rsp+0B8h+var_70], r14d
0x180048b93  mov     rax, [rbx]
0x180048b96  mov     rcx, rbx
0x180048b99  mov     rax, [rax+10h]
0x180048b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ba2  lea     rcx, [rsp+0B8h+var_70]
0x180048ba7  mov     [rsp+0B8h+peUse], rcx; peUse
0x180048bac  lea     rcx, [rsp+0B8h+var_78]
0x180048bb1  mov     [rsp+0B8h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180048bb6  mov     [rsp+0B8h+ReferencedDomainName], r14; ReferencedDomainName
0x180048bbb  lea     r9, [rsp+0B8h+cchName]; cchName
0x180048bc0  xor     r8d, r8d; Name
0x180048bc3  mov     rdx, [rax]; Sid
0x180048bc6  xor     ecx, ecx; lpSystemName
0x180048bc8  call    cs:__imp_LookupAccountSidW
0x180048bce  test    eax, eax
0x180048bd0  jnz     short loc_180048BFC
0x180048bd2  call    cs:__imp_GetLastError
0x180048bd8  mov     esi, eax
0x180048bda  cmp     eax, 7Ah ; 'z'
0x180048bdd  jz      short loc_180048BFC
0x180048bdf  test    eax, eax
0x180048be1  jle     short loc_180048BEC
0x180048be3  movzx   esi, ax
0x180048be6  or      esi, 80070000h
0x180048bec  lea     rcx, [rsp+0B8h+Name]
0x180048bf1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048bf6  nop
0x180048bf7  jmp     loc_180048CCD
0x180048bfc  mov     eax, [rsp+0B8h+cchName]
0x180048c00  test    eax, eax
0x180048c02  jz      short loc_180048C11
0x180048c04  lea     edx, [rax-1]
0x180048c07  lea     rcx, [rsp+0B8h+Name]; Src
0x180048c0c  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180048c11  mov     eax, [rsp+0B8h+var_78]
0x180048c15  test    eax, eax
0x180048c17  jz      short loc_180048C24
0x180048c19  lea     edx, [rax-1]
0x180048c1c  mov     rcx, rdi; Src
0x180048c1f  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180048c24  cmp     qword ptr [rdi+18h], 7
0x180048c29  jbe     short loc_180048C30
0x180048c2b  mov     r12, [rdi]
0x180048c2e  jmp     short loc_180048C33
0x180048c30  mov     r12, rdi
0x180048c33  lea     r13, [rsp+0B8h+Name]
0x180048c38  cmp     qword ptr [rsp+0B8h+var_48+8], 7
0x180048c3e  cmova   r13, [rsp+0B8h+Name]
0x180048c44  mov     rax, [rbx]
0x180048c47  mov     rcx, rbx
0x180048c4a  mov     rax, [rax+10h]
0x180048c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c53  lea     rcx, [rsp+0B8h+var_70]
0x180048c58  mov     [rsp+0B8h+peUse], rcx; peUse
0x180048c5d  lea     rcx, [rsp+0B8h+var_78]
0x180048c62  mov     [rsp+0B8h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180048c67  mov     [rsp+0B8h+ReferencedDomainName], r12; ReferencedDomainName
0x180048c6c  lea     r9, [rsp+0B8h+cchName]; cchName
0x180048c71  mov     r8, r13; Name
0x180048c74  mov     rdx, [rax]; Sid
0x180048c77  xor     ecx, ecx; lpSystemName
0x180048c79  call    cs:__imp_LookupAccountSidW
0x180048c7f  test    eax, eax
0x180048c81  jnz     short loc_180048CA5
0x180048c83  call    cs:__imp_GetLastError
0x180048c89  mov     esi, eax
0x180048c8b  test    eax, eax
0x180048c8d  jle     short loc_180048C98
0x180048c8f  movzx   esi, ax
0x180048c92  or      esi, 80070000h
0x180048c98  lea     rcx, [rsp+0B8h+Name]
0x180048c9d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048ca2  nop
0x180048ca3  jmp     short loc_180048CCD
0x180048ca5  lea     rdx, StringValue; "\\"
0x180048cac  mov     rcx, rdi; Src
0x180048caf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180048cb4  lea     rdx, [rsp+0B8h+Name]
0x180048cb9  mov     rcx, rdi; Src
0x180048cbc  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x180048cc1  nop
0x180048cc2  lea     rcx, [rsp+0B8h+Name]
0x180048cc7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048ccc  nop
0x180048ccd  test    esi, esi
0x180048ccf  jns     short loc_180048CF6
0x180048cd1  jmp     short loc_180048CE0
0x180048cd3  xor     r14d, r14d
0x180048cd6  mov     rdi, [rsp+0B8h+var_68]
0x180048cdb  mov     r15, [rsp+0B8h+var_60]
0x180048ce0  mov     [r15], r14
0x180048ce3  cmp     qword ptr [rdi+18h], 7
0x180048ce8  jbe     short loc_180048CEF
0x180048cea  mov     rax, [rdi]
0x180048ced  jmp     short loc_180048CF2
0x180048cef  mov     rax, rdi
0x180048cf2  mov     [rax], r14w
0x180048cf6  mov     rax, rdi
0x180048cf9  mov     rcx, [rsp+0B8h+var_38]
0x180048d01  xor     rcx, rsp; StackCookie
0x180048d04  call    __security_check_cookie
0x180048d09  lea     r11, [rsp+0B8h+var_28]
0x180048d11  mov     rbx, [r11+38h]
0x180048d15  mov     rsi, [r11+40h]
0x180048d19  mov     rsp, r11
0x180048d1c  pop     r15
0x180048d1e  pop     r14
0x180048d20  pop     r13
0x180048d22  pop     r12
0x180048d24  pop     rdi
0x180048d25  retn
```
