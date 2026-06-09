# LicenseManagerCore::FindOrCreateLeaseForKey(Microsoft::WRL::ComPtr<IKeyForLease> const &,Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &,Microsoft::WRL::ComPtr<IStoredLeaseDocument> const &)

- ea: `0x180017e70`
- end: `0x1800182fa`
- name: `?FindOrCreateLeaseForKey@LicenseManagerCore@@UEAA?AV?$ComPtr@UILeaseForKey@@@WRL@Microsoft@@AEBV?$ComPtr@UIKeyForLease@@@34@AEBV?$ComPtr@UILicenseIdentityContext@@@34@AEBV?$ComPtr@UIStoredLeaseDocument@@@34@@Z`
- size: `1162`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004738`
- `0x1800171b0`
- `0x180017200`
- `0x1800174bc`
- `0x180017e70`
- `0x180038720`
- `0x180039e8c`
- `0x180041ccc`
- `0x180054a54`
- `0x1800593bc`
- `0x180075e60`
- `0x1800767e0`
- `0x18008251f`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017fbf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017fbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001820e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001820e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017f34`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800180c9`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017f34`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800180c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800182d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800182d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
_QWORD *__fastcall LicenseManagerCore::FindOrCreateLeaseForKey(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  _QWORD *v5; // r12
  int v6; // eax
  void *v7; // r15
  size_t v8; // rsi
  __int64 v9; // rbx
  wchar_t *v10; // rdi
  __int64 (__fastcall ***v11)(_QWORD, GUID *, _QWORD *); // rbx
  struct _RTL_CRITICAL_SECTION *v12; // r13
  _QWORD *v13; // r14
  __int64 inserted; // rsi
  __int64 v15; // rdi
  const wchar_t *v16; // rcx
  size_t v17; // r12
  const wchar_t *v18; // rdx
  size_t v19; // r15
  size_t v20; // r8
  int v21; // eax
  const wchar_t *v22; // rdx
  size_t v23; // rdi
  size_t v24; // r15
  const wchar_t *v25; // rcx
  size_t v26; // r8
  int v27; // eax
  __int64 v28; // rsi
  _QWORD *v29; // rdi
  __int64 v30; // rdx
  _QWORD *v31; // rcx
  _QWORD *v32; // rax
  char *v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 (__fastcall ***v37)(_QWORD, GUID *, _QWORD *); // rdi
  _QWORD *v38; // rsi
  __int64 (__fastcall *v39)(_QWORD, GUID *, _QWORD *); // rdi
  int v40; // eax
  void *Src; // [rsp+20h] [rbp-B1h] BYREF
  _QWORD *v43; // [rsp+28h] [rbp-A9h] BYREF
  _QWORD *v44; // [rsp+30h] [rbp-A1h]
  __int128 v45; // [rsp+40h] [rbp-91h] BYREF
  int v46; // [rsp+50h] [rbp-81h]
  __int128 v47; // [rsp+58h] [rbp-79h]
  __int64 v48; // [rsp+70h] [rbp-61h]
  __int64 (__fastcall ***v49)(_QWORD, _QWORD, _QWORD); // [rsp+78h] [rbp-59h]
  _QWORD *v50; // [rsp+80h] [rbp-51h]
  __int64 v51; // [rsp+88h] [rbp-49h]
  _QWORD *v52; // [rsp+90h] [rbp-41h]
  _QWORD *v53; // [rsp+98h] [rbp-39h]
  _QWORD *v54; // [rsp+A0h] [rbp-31h]
  char v55; // [rsp+A8h] [rbp-29h] BYREF
  wchar_t *S2[2]; // [rsp+B0h] [rbp-21h] BYREF
  size_t N; // [rsp+C0h] [rbp-11h]
  unsigned __int64 v58; // [rsp+C8h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  v48 = a4;
  v51 = a3;
  v52 = a2;
  v5 = a1;
  v43 = a1;
  v53 = a2;
  v50 = a5;
  v46 = 0;
  Src = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)*a5 + 24LL))(*a5, &Src);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
      (const char *)(unsigned int)v6,
      (int)Src);
  v7 = Src;
  *(_OWORD *)S2 = 0;
  N = 0;
  v58 = 0;
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)Src + v8) );
  if ( v8 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v8 > 7 )
  {
    v9 = std::wstring::_Calculate_growth(v8, 7);
    v10 = (wchar_t *)std::allocator<unsigned short>::allocate(S2, v9 + 1);
    S2[0] = v10;
    N = v8;
    v58 = v9;
    memcpy_0(v10, v7, 2 * v8);
    v10[v8] = 0;
  }
  else
  {
    N = v8;
    v58 = 7;
    memcpy_0(S2, Src, 2 * v8);
    *((_WORD *)S2 + v8) = 0;
  }
  v11 = 0;
  v49 = 0;
  v12 = (struct _RTL_CRITICAL_SECTION *)(v5 + 8);
  *(_QWORD *)&v45 = v5 + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  v54 = v5 + 8;
  v13 = v5 + 20;
  inserted = v5[20];
  v15 = *(_QWORD *)(inserted + 8);
  v47 = (unsigned __int64)v15;
  if ( !*(_BYTE *)(v15 + 25) )
  {
    while ( 1 )
    {
      *(_QWORD *)&v47 = v15;
      v16 = (const wchar_t *)(v15 + 32);
      v17 = N;
      v18 = (const wchar_t *)S2;
      if ( v58 > 7 )
        v18 = S2[0];
      v19 = *(_QWORD *)(v15 + 48);
      if ( *(_QWORD *)(v15 + 56) > 7u )
        v16 = *(const wchar_t **)v16;
      v20 = *(_QWORD *)(v15 + 48);
      if ( N < v19 )
        v20 = N;
      v21 = wmemcmp(v16, v18, v20);
      if ( v21 )
      {
        if ( v21 < 0 )
          goto LABEL_33;
      }
      else if ( v19 < v17 )
      {
LABEL_33:
        DWORD2(v47) = 0;
        v15 += 16;
        goto LABEL_20;
      }
      DWORD2(v47) = 1;
      inserted = v15;
LABEL_20:
      v15 = *(_QWORD *)v15;
      if ( *(_BYTE *)(v15 + 25) )
      {
        v12 = (struct _RTL_CRITICAL_SECTION *)v45;
        v5 = v43;
        break;
      }
    }
  }
  if ( !*(_BYTE *)(inserted + 25) )
  {
    v22 = (const wchar_t *)(inserted + 32);
    v23 = *(_QWORD *)(inserted + 48);
    if ( *(_QWORD *)(inserted + 56) > 7u )
      v22 = *(const wchar_t **)v22;
    v24 = N;
    v25 = (const wchar_t *)S2;
    if ( v58 > 7 )
      v25 = S2[0];
    v26 = N;
    if ( v23 < N )
      v26 = *(_QWORD *)(inserted + 48);
    v27 = wmemcmp(v25, v22, v26);
    if ( v27 )
    {
      if ( v27 >= 0 )
        goto LABEL_38;
    }
    else if ( v24 >= v23 )
    {
      goto LABEL_38;
    }
  }
  if ( v13[1] == 0x333333333333333LL )
    std::_Xlength_error("map/set too long");
  v28 = *v13;
  v43 = v13;
  v44 = 0;
  v29 = operator new(0x50u);
  v44 = v29;
  *(_QWORD *)&v45 = S2;
  ____0AEBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std____Z__V___pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__ULeaseEntry___std__QEAA_Upiecewise_construct_t_1_V__tuple_AEBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___1_V__tuple___V_1__Z(
    v29 + 4,
    v30,
    &v45);
  *v29 = v28;
  v29[1] = v28;
  v29[2] = v28;
  *((_WORD *)v29 + 12) = 0;
  v45 = v47;
  inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,LeaseEntry>>>::_Insert_node(
               v13,
               &v45,
               v29);
LABEL_38:
  if ( !*(_QWORD *)(inserted + 72) )
  {
    if ( v5 )
    {
      v31 = v5 + 1;
      v32 = v5 + 1;
    }
    else
    {
      v31 = 0;
      v32 = 0;
    }
    v43 = v31;
    if ( v32 )
      (*(void (__fastcall **)(_QWORD *))(*v31 + 8LL))(v31);
    v33 = (char *)CreateLease(&v45, S2, v48, &v43);
    v34 = 0;
    if ( &v55 != v33 )
    {
      v34 = *(_QWORD *)v33;
      *(_QWORD *)v33 = 0;
    }
    v35 = *(_QWORD *)(inserted + 72);
    *(_QWORD *)(inserted + 72) = v34;
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v36 = v45;
    if ( (_QWORD)v45 )
    {
      *(_QWORD *)&v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    if ( v43 )
      (*(void (__fastcall **)(_QWORD *))(*v43 + 16LL))(v43);
  }
  ++*(_DWORD *)(inserted + 64);
  v37 = *(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))(inserted + 72);
  if ( v37 )
  {
    ((void (__fastcall *)(_QWORD))(*v37)[1])(*(_QWORD *)(inserted + 72));
    v11 = v37;
    v49 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v37;
  }
  if ( v12 )
    LeaveCriticalSection(v12);
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), _QWORD *))(*v11)[4])(v11, v50);
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), __int64))(*v11)[5])(v11, v51);
  v38 = v52;
  *v52 = 0;
  v46 = 1;
  v39 = **v11;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v38);
  v40 = v39(v11, &GUID_6f8d9846_4642_463f_ab03_4d6773d00157, v38);
  if ( v40 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
      (const char *)(unsigned int)v40,
      (int)Src);
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v11)[2])(v11);
  if ( v58 > 7 )
    std::_Deallocate<16>(S2[0], 2 * v58 + 2);
  N = 0;
  v58 = 7;
  LOWORD(S2[0]) = 0;
  if ( Src )
    CoTaskMemFree(Src);
  return v38;
}

```

## disassembly

```asm
0x180017e70  mov     [rsp-8+arg_8], rdx
0x180017e75  push    rbp
0x180017e76  push    rbx
0x180017e77  push    rsi
0x180017e78  push    rdi
0x180017e79  push    r12
0x180017e7b  push    r13
0x180017e7d  push    r14
0x180017e7f  push    r15
0x180017e81  lea     rbp, [rsp-17h]
0x180017e86  sub     rsp, 0E8h
0x180017e8d  mov     rax, cs:__security_cookie
0x180017e94  xor     rax, rsp
0x180017e97  mov     [rbp+4Fh+var_50], rax
0x180017e9b  mov     [rbp+4Fh+var_B0], r9
0x180017e9f  mov     [rbp+4Fh+var_98], r8
0x180017ea3  mov     [rbp+4Fh+var_90], rdx
0x180017ea7  mov     r12, rcx
0x180017eaa  mov     [rsp+120h+var_F8], rcx
0x180017eaf  mov     [rbp+4Fh+var_88], rdx
0x180017eb3  mov     rax, [rbp+4Fh+arg_20]
0x180017eb7  mov     [rbp+4Fh+var_A0], rax
0x180017ebb  xor     ebx, ebx
0x180017ebd  mov     [rsp+120h+var_D0], ebx
0x180017ec1  mov     [rsp+120h+Src], rbx
0x180017ec6  mov     rcx, [rax]
0x180017ec9  mov     rax, [rcx]
0x180017ecc  mov     [rsp+120h+Src], rbx; int
0x180017ed1  lea     rdx, [rsp+120h+Src]
0x180017ed6  mov     rax, [rax+18h]
0x180017eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017edf  mov     rcx, [rbp+57h]; this
0x180017ee3  test    eax, eax
0x180017ee5  jns     short loc_180017EFC
0x180017ee7  mov     r9d, eax; char *
0x180017eea  lea     r8, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x180017ef1  mov     edx, 13Dh; void *
0x180017ef6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017efc  mov     r15, [rsp+120h+Src]
0x180017f01  xorps   xmm0, xmm0
0x180017f04  movups  xmmword ptr [rbp+4Fh+S2], xmm0
0x180017f08  mov     [rbp+4Fh+N], rbx
0x180017f0c  mov     [rbp+4Fh+var_58], rbx
0x180017f10  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180017f14  inc     rsi
0x180017f17  cmp     [r15+rsi*2], bx
0x180017f1c  jnz     short loc_180017F14
0x180017f1e  mov     r8, 7FFFFFFFFFFFFFFEh
0x180017f28  cmp     rsi, r8
0x180017f2b  jbe     short loc_180017F3B
0x180017f2d  lea     rcx, aStringTooLong; "string too long"
0x180017f34  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180017f3b  lea     r14, [rsi+rsi]
0x180017f3f  mov     eax, 7
0x180017f44  cmp     rsi, rax
0x180017f47  ja      short loc_180017F6B
0x180017f49  mov     [rbp+4Fh+N], rsi
0x180017f4d  mov     [rbp+4Fh+var_58], rax
0x180017f51  mov     r8, r14; Size
0x180017f54  mov     rdx, r15; Src
0x180017f57  lea     rcx, [rbp+4Fh+S2]; void *
0x180017f5b  call    memcpy_0
0x180017f60  xor     r15d, r15d
0x180017f63  mov     word ptr [rbp+r14+4Fh+S2], r15w
0x180017f69  jmp     short loc_180017FAB
0x180017f6b  mov     rdx, rax
0x180017f6e  mov     rcx, rsi
0x180017f71  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x180017f76  mov     rbx, rax
0x180017f79  lea     rdx, [rax+1]
0x180017f7d  lea     rcx, [rbp+4Fh+S2]
0x180017f81  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x180017f86  mov     rdi, rax
0x180017f89  mov     [rbp+4Fh+S2], rax
0x180017f8d  mov     [rbp+4Fh+N], rsi
0x180017f91  mov     [rbp+4Fh+var_58], rbx
0x180017f95  mov     r8, r14; Size
0x180017f98  mov     rdx, r15; Src
0x180017f9b  mov     rcx, rax; void *
0x180017f9e  call    memcpy_0
0x180017fa3  xor     r15d, r15d
0x180017fa6  mov     [r14+rdi], r15w
0x180017fab  mov     rbx, r15
0x180017fae  mov     [rbp+4Fh+var_A8], rbx
0x180017fb2  lea     r13, [r12+40h]
0x180017fb7  mov     qword ptr [rsp+120h+var_E0], r13
0x180017fbc  mov     rcx, r13; lpCriticalSection
0x180017fbf  call    cs:__imp_EnterCriticalSection
0x180017fc5  mov     [rbp+4Fh+var_80], r13
0x180017fc9  lea     r14, [r12+0A0h]
0x180017fd1  mov     rsi, [r14]
0x180017fd4  mov     rdi, [rsi+8]
0x180017fd8  mov     qword ptr [rbp+4Fh+var_C8], rdi
0x180017fdc  mov     qword ptr [rbp+4Fh+var_C8+8], 0
0x180017fe4  cmp     [rdi+19h], r15b
0x180017fe8  jnz     short loc_18001804A
0x180017fea  xor     r13d, r13d
0x180017fed  mov     qword ptr [rbp+4Fh+var_C8], rdi
0x180017ff1  lea     rcx, [rdi+20h]
0x180017ff5  mov     r12, [rbp+4Fh+N]
0x180017ff9  lea     rdx, [rbp+4Fh+S2]
0x180017ffd  cmp     [rbp+4Fh+var_58], 7
0x180018002  cmova   rdx, [rbp+4Fh+S2]; S2
0x180018007  mov     r15, [rdi+30h]
0x18001800b  cmp     qword ptr [rcx+18h], 7
0x180018010  jbe     short loc_180018015
0x180018012  mov     rcx, [rcx]; S1
0x180018015  mov     r8, r15
0x180018018  cmp     r12, r15
0x18001801b  cmovb   r8, r12; N
0x18001801f  call    wmemcmp
0x180018024  test    eax, eax
0x180018026  jz      short loc_180018093
0x180018028  js      short loc_180018098
0x18001802a  mov     dword ptr [rbp+4Fh+var_C8+8], 1
0x180018031  mov     rsi, rdi
0x180018034  mov     rdi, [rdi]
0x180018037  cmp     [rdi+19h], r13b
0x18001803b  jz      short loc_180017FED
0x18001803d  mov     r13, qword ptr [rsp+120h+var_E0]
0x180018042  mov     r12, [rsp+120h+var_F8]
0x180018047  xor     r15d, r15d
0x18001804a  cmp     [rsi+19h], r15b
0x18001804e  jnz     short loc_1800180B2
0x180018050  lea     rdx, [rsi+20h]
0x180018054  mov     rdi, [rdx+10h]
0x180018058  cmp     qword ptr [rdx+18h], 7
0x18001805d  jbe     short loc_180018062
0x18001805f  mov     rdx, [rdx]; S2
0x180018062  mov     r15, [rbp+4Fh+N]
0x180018066  lea     rcx, [rbp+4Fh+S2]
0x18001806a  cmp     [rbp+4Fh+var_58], 7
0x18001806f  cmova   rcx, [rbp+4Fh+S2]; S1
0x180018074  mov     r8, r15
0x180018077  cmp     rdi, r15
0x18001807a  cmovb   r8, rdi; N
0x18001807e  call    wmemcmp
0x180018083  test    eax, eax
0x180018085  jz      short loc_1800180A2
0x180018087  xor     r15d, r15d
0x18001808a  test    eax, eax
0x18001808c  js      short loc_1800180B2
0x18001808e  jmp     loc_180018134
0x180018093  cmp     r15, r12
0x180018096  jnb     short loc_18001802A
0x180018098  mov     dword ptr [rbp+4Fh+var_C8+8], r13d
0x18001809c  add     rdi, 10h
0x1800180a0  jmp     short loc_180018034
0x1800180a2  cmp     r15, rdi
0x1800180a5  jb      short loc_1800180AF
0x1800180a7  xor     r15d, r15d
0x1800180aa  jmp     loc_180018134
0x1800180af  xor     r15d, r15d
0x1800180b2  mov     rax, 333333333333333h
0x1800180bc  cmp     [r14+8], rax
0x1800180c0  jnz     short loc_1800180D0
0x1800180c2  lea     rcx, aMapSetTooLong; "map/set too long"
0x1800180c9  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800180d0  mov     rsi, [r14]
0x1800180d3  mov     [rsp+120h+var_F8], r14
0x1800180d8  mov     [rsp+120h+var_F0], r15
0x1800180dd  mov     ecx, 50h ; 'P'; Size
0x1800180e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800180e7  mov     rdi, rax
0x1800180ea  mov     [rsp+120h+var_F0], rax
0x1800180ef  lea     rax, [rbp+4Fh+S2]
0x1800180f3  mov     qword ptr [rsp+120h+var_E0], rax
0x1800180f8  lea     rcx, [rdi+20h]
0x1800180fc  lea     r8, [rsp+120h+var_E0]
0x180018101  call    ??$?0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$Z$$V@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@ULeaseEntry@@@std@@QEAA@Upiecewise_construct_t@1@V?$tuple@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@V?$tuple@$$V@1@@Z
0x180018106  mov     [rdi], rsi
0x180018109  mov     [rdi+8], rsi
0x18001810d  mov     [rdi+10h], rsi
0x180018111  mov     word ptr [rdi+18h], 0
0x180018117  movups  xmm0, [rbp+4Fh+var_C8]
0x18001811b  movdqu  [rsp+120h+var_E0], xmm0
0x180018121  mov     r8, rdi
0x180018124  lea     rdx, [rsp+120h+var_E0]
0x180018129  mov     rcx, r14
0x18001812c  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@ULeaseEntry@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@ULeaseEntry@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@ULeaseEntry@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,LeaseEntry>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,LeaseEntry>,void *> *>,std::_Tree_node<std::pair<std::wstring const,LeaseEntry>,void *> * const)
0x180018131  mov     rsi, rax
0x180018134  cmp     [rsi+48h], r15
0x180018138  jnz     loc_1800181E3
0x18001813e  test    r12, r12
0x180018141  jz      short loc_18001814D
0x180018143  lea     rcx, [r12+8]
0x180018148  mov     rax, rcx
0x18001814b  jmp     short loc_180018153
0x18001814d  mov     rcx, r15
0x180018150  mov     rax, r15
0x180018153  mov     [rsp+120h+var_F8], rcx
0x180018158  test    rax, rax
0x18001815b  jz      short loc_18001816A
0x18001815d  mov     rax, [rcx]
0x180018160  mov     rax, [rax+8]
0x180018164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018169  nop
0x18001816a  lea     r9, [rsp+120h+var_F8]
0x18001816f  mov     r8, [rbp+4Fh+var_B0]
0x180018173  lea     rdx, [rbp+4Fh+S2]
0x180018177  lea     rcx, [rsp+120h+var_E0]
0x18001817c  call    ?CreateLease@@YA?AV?$ComPtr@UILeaseForCore@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UILicenseIdentityContext@@@23@AEBV?$ComPtr@UICoreForLease@@@23@@Z; CreateLease(std::wstring const &,Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &,Microsoft::WRL::ComPtr<ICoreForLease> const &)
0x180018181  mov     rcx, rax
0x180018184  mov     rax, r15
0x180018187  lea     rdx, [rbp+4Fh+var_78]
0x18001818b  cmp     rdx, rcx
0x18001818e  jz      short loc_180018196
0x180018190  mov     rax, [rcx]
0x180018193  mov     [rcx], r15
0x180018196  mov     rcx, [rsi+48h]
0x18001819a  mov     [rsi+48h], rax
0x18001819e  test    rcx, rcx
0x1800181a1  jz      short loc_1800181B0
0x1800181a3  mov     rax, [rcx]
0x1800181a6  mov     rax, [rax+10h]
0x1800181aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181af  nop
0x1800181b0  mov     rcx, qword ptr [rsp+120h+var_E0]
0x1800181b5  test    rcx, rcx
0x1800181b8  jz      short loc_1800181CC
0x1800181ba  mov     qword ptr [rsp+120h+var_E0], r15
0x1800181bf  mov     rax, [rcx]
0x1800181c2  mov     rax, [rax+10h]
0x1800181c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181cb  nop
0x1800181cc  mov     rcx, [rsp+120h+var_F8]
0x1800181d1  test    rcx, rcx
0x1800181d4  jz      short loc_1800181E3
0x1800181d6  mov     rax, [rcx]
0x1800181d9  mov     rax, [rax+10h]
0x1800181dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181e2  nop
0x1800181e3  inc     dword ptr [rsi+40h]
0x1800181e6  mov     rdi, [rsi+48h]
0x1800181ea  test    rdi, rdi
0x1800181ed  jz      short loc_180018206
0x1800181ef  mov     rax, [rdi]
0x1800181f2  mov     rcx, rdi
0x1800181f5  mov     rax, [rax+8]
0x1800181f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181fe  nop
0x1800181ff  mov     rbx, rdi
0x180018202  mov     [rbp+4Fh+var_A8], rbx
0x180018206  test    r13, r13
0x180018209  jz      short loc_180018214
0x18001820b  mov     rcx, r13; lpCriticalSection
0x18001820e  call    cs:__imp_LeaveCriticalSection
0x180018214  mov     rax, [rbx]
0x180018217  mov     rdx, [rbp+4Fh+var_A0]
0x18001821b  mov     rcx, rbx
0x18001821e  mov     rax, [rax+20h]
0x180018222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018227  mov     rax, [rbx]
0x18001822a  mov     rdx, [rbp+4Fh+var_98]
0x18001822e  mov     rcx, rbx
0x180018231  mov     rax, [rax+28h]
0x180018235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001823a  mov     rsi, [rbp+4Fh+var_90]
0x18001823e  mov     [rsi], r15
0x180018241  mov     [rsp+120h+var_D0], 1
0x180018249  mov     rax, [rbx]
0x18001824c  mov     rdi, [rax]
0x18001824f  mov     rcx, rsi
0x180018252  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180018257  mov     r8, rsi
0x18001825a  lea     rdx, _GUID_6f8d9846_4642_463f_ab03_4d6773d00157
0x180018261  mov     rcx, rbx
0x180018264  mov     rax, rdi
0x180018267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001826c  nop
0x18001826d  mov     rcx, [rbp+57h]; this
0x180018271  test    eax, eax
0x180018273  jns     short loc_18001828A
0x180018275  mov     r9d, eax; char *
0x180018278  lea     r8, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x18001827f  mov     edx, 153h; void *
0x180018284  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001828a  mov     rax, [rbx]
0x18001828d  mov     rcx, rbx
0x180018290  mov     rax, [rax+10h]
0x180018294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018299  nop
0x18001829a  mov     rdx, [rbp+4Fh+var_58]
0x18001829e  cmp     rdx, 7
0x1800182a2  jbe     short loc_1800182B5
0x1800182a4  lea     rdx, ds:2[rdx*2]
0x1800182ac  mov     rcx, [rbp+4Fh+S2]
0x1800182b0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800182b5  mov     [rbp+4Fh+N], r15
0x1800182b9  mov     [rbp+4Fh+var_58], 7
0x1800182c1  mov     word ptr [rbp+4Fh+S2], r15w
0x1800182c6  mov     rcx, [rsp+120h+Src]; pv
0x1800182cb  test    rcx, rcx
0x1800182ce  jz      short loc_1800182D6
0x1800182d0  call    cs:__imp_CoTaskMemFree
0x1800182d6  mov     rax, rsi
0x1800182d9  mov     rcx, [rbp+4Fh+var_50]
0x1800182dd  xor     rcx, rsp; StackCookie
0x1800182e0  call    __security_check_cookie
0x1800182e5  add     rsp, 0E8h
  ... truncated ...
```
