# TokenUtility::_CreateAllAccessDaclForUserAndWorker(void *)

- ea: `0x180031f84`
- end: `0x18003209e`
- name: `?_CreateAllAccessDaclForUserAndWorker@TokenUtility@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `282`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180030a60`
- `0x180031a9c`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x18000e5f4`
- `0x18000f8a8`
- `0x180012498`
- `0x18001d058`
- `0x180028758`

## string_xrefs

- `0x180031fe3`: `Failed to get the SID attached to the token!`
- `0x180031ff2`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x180032052`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TokenUtility::_CreateAllAccessDaclForUserAndWorker(__int64 a1, __int64 a2, void *a3)
{
  unsigned int UserSidFromToken; // eax
  __int128 *v5; // r9
  unsigned int v6; // eax
  const char *v8; // [rsp+28h] [rbp-D8h]
  const char *v9; // [rsp+28h] [rbp-D8h]
  __int128 v10; // [rsp+40h] [rbp-C0h] BYREF
  __m128i si128; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v12[200]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v10 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v10) = 0;
  UserSidFromToken = PrintCore::TokenHelpers::GetUserSidFromToken(a3, &v10);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1B6,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)UserSidFromToken,
    (int)"Failed to get the SID attached to the token!",
    v8);
  memset_0(v12, 0, sizeof(v12));
  v5 = &v10;
  if ( si128.m128i_i64[1] > 7uLL )
    v5 = (__int128 *)v10;
  v6 = StringCchPrintfW(
         v12,
         0xC8u,
         L"D:(A;OICI;KA;;;S-1-5-99-216390572-1995538116-3857911515-2404958512-2623887229)(A;OICI;KA;;;%ws)(A;OICI;KA;;;SY)",
         v5);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1BA,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v6,
    (int)"StringCchPrintf failed!",
    v9);
  std::wstring::wstring(a2, (__int64)v12);
  std::wstring::_Tidy_deallocate(&v10);
  return a2;
}

```

## disassembly

```asm
0x180031f84  mov     [rsp-8+arg_0], rbx
0x180031f89  push    rbp
0x180031f8a  lea     rbp, [rsp-100h]
0x180031f92  sub     rsp, 200h
0x180031f99  mov     rax, cs:__security_cookie
0x180031fa0  xor     rax, rsp
0x180031fa3  mov     [rbp+100h+var_10], rax
0x180031faa  mov     rbx, rdx
0x180031fad  mov     [rsp+200h+var_1C8], rdx
0x180031fb2  xor     eax, eax
0x180031fb4  xorps   xmm0, xmm0
0x180031fb7  movups  [rsp+200h+var_1C0], xmm0
0x180031fbc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180031fc4  movdqu  [rsp+200h+var_1B0], xmm1
0x180031fca  mov     word ptr [rsp+200h+var_1C0], ax
0x180031fcf  lea     rdx, [rsp+200h+var_1C0]
0x180031fd4  mov     rcx, r8; TokenHandle
0x180031fd7  call    ?GetUserSidFromToken@TokenHelpers@PrintCore@@SAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintCore::TokenHelpers::GetUserSidFromToken(void *,std::wstring &)
0x180031fdc  mov     rcx, [rbp+108h]; this
0x180031fe3  lea     rdx, aFailedToGetThe_3; "Failed to get the SID attached to the t"...
0x180031fea  mov     qword ptr [rsp+200h+var_1E0], rdx; int
0x180031fef  mov     r9d, eax; char *
0x180031ff2  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180031ff9  mov     edx, 1B6h; void *
0x180031ffe  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180032003  xor     edx, edx; Val
0x180032005  mov     r8d, 190h; Size
0x18003200b  lea     rcx, [rsp+200h+var_1A0]; void *
0x180032010  call    memset_0
0x180032015  lea     r9, [rsp+200h+var_1C0]
0x18003201a  cmp     qword ptr [rsp+200h+var_1B0+8], 7
0x180032020  cmova   r9, qword ptr [rsp+200h+var_1C0]
0x180032026  lea     r8, aDAOiciKaS15992; "D:(A;OICI;KA;;;S-1-5-99-216390572-19955"...
0x18003202d  mov     edx, 0C8h; unsigned __int64
0x180032032  lea     rcx, [rsp+200h+var_1A0]; unsigned __int16 *
0x180032037  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003203c  mov     rcx, [rbp+108h]; this
0x180032043  lea     rdx, aStringcchprint_1; "StringCchPrintf failed!"
0x18003204a  mov     qword ptr [rsp+200h+var_1E0], rdx; int
0x18003204f  mov     r9d, eax; char *
0x180032052  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180032059  mov     edx, 1BAh; void *
0x18003205e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180032063  lea     rdx, [rsp+200h+var_1A0]
0x180032068  mov     rcx, rbx
0x18003206b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180032070  nop
0x180032071  lea     rcx, [rsp+200h+var_1C0]
0x180032076  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003207b  mov     rax, rbx
0x18003207e  mov     rcx, [rbp+100h+var_10]
0x180032085  xor     rcx, rsp; StackCookie
0x180032088  call    __security_check_cookie
0x18003208d  mov     rbx, [rsp+200h+arg_0]
0x180032095  add     rsp, 200h
0x18003209c  pop     rbp
0x18003209d  retn
```
