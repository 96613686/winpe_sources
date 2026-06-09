# LicenseManager::LicenseContentWithId(ushort const *,LicenseUsage,ILicenseInstance * *)

- ea: `0x18001ae10`
- end: `0x18001b19e`
- name: `?LicenseContentWithId@LicenseManager@@UEAAJPEBGW4LicenseUsage@@PEAPEAUILicenseInstance@@@Z`
- size: `910`
- prototype: `int __high(const unsigned __int16 *, enum LicenseUsage, struct ILicenseInstance **)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18008b400`
- `0x18008b410`

## callees

- `0x180013b50`
- `0x1800171b0`
- `0x1800193a4`
- `0x18001ae10`
- `0x18001b1a4`
- `0x180039dd0`
- `0x180054a54`
- `0x1800593bc`
- `0x180075e60`
- `0x18008251f`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001aea6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001aea6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001af47`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001af47`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall LicenseManager::LicenseContentWithId(__int64 a1, const WCHAR *a2, int a3, _QWORD *a4)
{
  __int64 result; // rax
  unsigned __int64 v7; // rbx
  __int64 *v8; // r12
  size_t v9; // rbx
  __int64 v10; // r15
  char *v11; // rsi
  size_t v12; // rbx
  _QWORD *v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  _QWORD *v20; // rcx
  wil *v21; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-B8h]
  int bIgnoreCasea; // [rsp+20h] [rbp-B8h]
  _QWORD *v24; // [rsp+40h] [rbp-98h] BYREF
  __int64 v25; // [rsp+48h] [rbp-90h] BYREF
  __int64 v26; // [rsp+50h] [rbp-88h] BYREF
  _QWORD *v27; // [rsp+58h] [rbp-80h] BYREF
  __int64 v28; // [rsp+60h] [rbp-78h] BYREF
  wil *v29; // [rsp+68h] [rbp-70h] BYREF
  __int128 v30; // [rsp+70h] [rbp-68h] BYREF
  __m128i si128; // [rsp+80h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  LODWORD(v25) = a3;
  if ( !a4 )
    return 2147500035LL;
  try
  {
    *a4 = 0;
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\manager.cpp",
      0x58u,
      "LicenseManager::LicenseContentWithId",
      (wchar_t *)L"Licensing %s (Active)",
      a2);
    v7 = -1;
    if ( CompareStringOrdinal(a2, -1, L"00000000-0000-0000-0000-000000000000", -1, 0) == 2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\manager.cpp",
        (const char *)0x87E10BC6LL,
        bIgnoreCase);
    (*(void (__fastcall **)(_QWORD, wil **))(**(_QWORD **)(a1 + 64) + 24LL))(*(_QWORD *)(a1 + 64), &v29);
    MakeCom<LicenseCallback,>(&v24);
    v8 = *(__int64 **)(a1 + 64);
    v26 = *v8;
    v27 = v24;
    if ( v24 )
      (*(void (__fastcall **)(_QWORD *))(*v24 + 8LL))(v24);
    v30 = 0;
    si128 = 0;
    do
      ++v7;
    while ( a2[v7] );
    if ( v7 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( v7 > 7 )
    {
      v10 = std::basic_string<unsigned short,content_id_char_traits,std::allocator<unsigned short>>::_Calculate_growth(
              v7,
              7,
              0x7FFFFFFFFFFFFFFELL);
      v11 = (char *)std::allocator<unsigned short>::allocate(&v30, v10 + 1);
      *(_QWORD *)&v30 = v11;
      si128.m128i_i64[0] = v7;
      si128.m128i_i64[1] = v10;
      v12 = 2 * v7;
      memcpy_0(v11, a2, v12);
      *(_WORD *)&v11[v12] = 0;
    }
    else
    {
      si128.m128i_i64[0] = v7;
      si128.m128i_i64[1] = 7;
      v9 = 2 * v7;
      memcpy_0(&v30, a2, v9);
      *(_WORD *)((char *)&v30 + v9) = 0;
    }
    (*(void (__fastcall **)(__int64 *, __int64 *, __int128 *, _QWORD, wil **, _QWORD **))(v26 + 64))(
      v8,
      &v28,
      &v30,
      (unsigned int)v25,
      &v29,
      &v27);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v30, 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v30) = 0;
    v13 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
    }
    (*(void (__fastcall **)(_QWORD *))(v24[1] + 24LL))(v24 + 1);
    v14 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(v24[1] + 40LL))(v24 + 1, &v26);
    v15 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(v24[1] + 32LL))(v24 + 1, &v25);
    LOBYTE(bIgnoreCasea) = 1;
    v16 = CreateLicenseInstance(*(_QWORD *)(a1 + 80), v15, v14, &v28);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\manager.cpp",
        (const char *)(unsigned int)v16,
        bIgnoreCasea);
    v17 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
    }
    v21 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(wil *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::ResultFromCaughtException(v21);
  }
  return result;
}

```

## disassembly

```asm
0x18001ae10  push    rbx
0x18001ae12  push    rsi
0x18001ae13  push    rdi
0x18001ae14  push    r12
0x18001ae16  push    r13
0x18001ae18  push    r14
0x18001ae1a  push    r15
0x18001ae1c  sub     rsp, 0A0h
0x18001ae23  mov     rax, cs:__security_cookie
0x18001ae2a  xor     rax, rsp
0x18001ae2d  mov     [rsp+0D8h+var_48], rax
0x18001ae35  mov     r14, r9
0x18001ae38  mov     dword ptr [rsp+0D8h+var_90], r8d
0x18001ae3d  mov     rdi, rdx
0x18001ae40  mov     r13, rcx
0x18001ae43  xor     r15d, r15d
0x18001ae46  test    r9, r9
0x18001ae49  jnz     short loc_18001AE55
0x18001ae4b  mov     eax, 80004003h
0x18001ae50  jmp     loc_18001B17A
0x18001ae55  mov     [r9], r15
0x18001ae58  mov     [rsp+0D8h+var_B0], rdi
0x18001ae5d  lea     rax, aLicensingSActi; "Licensing %s (Active)"
0x18001ae64  mov     qword ptr [rsp+0D8h+bIgnoreCase], rax; Format
0x18001ae69  lea     r9, aLicensemanager_0; "LicenseManager::LicenseContentWithId"
0x18001ae70  mov     r8d, 58h ; 'X'; unsigned int
0x18001ae76  lea     rdx, aOnecoreuapEndu_15; "onecoreuap\\enduser\\winstore\\licensem"...
0x18001ae7d  lea     ecx, [r8-55h]; unsigned int
0x18001ae81  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18001ae86  mov     rsi, [rsp+0D8h]
0x18001ae8e  mov     [rsp+0D8h+bIgnoreCase], r15d; int
0x18001ae93  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001ae97  mov     r9d, ebx; cchCount2
0x18001ae9a  lea     r8, a00000000000000; "00000000-0000-0000-0000-000000000000"
0x18001aea1  mov     edx, ebx; cchCount1
0x18001aea3  mov     rcx, rdi; lpString1
0x18001aea6  call    cs:__imp_CompareStringOrdinal
0x18001aeac  cmp     eax, 2
0x18001aeaf  jnz     short loc_18001AEC9
0x18001aeb1  mov     r9d, 87E10BC6h; char *
0x18001aeb7  lea     r8, aOnecoreuapEndu_15; "onecoreuap\\enduser\\winstore\\licensem"...
0x18001aebe  lea     edx, [rbx+5Dh]; void *
0x18001aec1  mov     rcx, rsi; this
0x18001aec4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001aec9  mov     rcx, [r13+40h]
0x18001aecd  mov     rax, [rcx]
0x18001aed0  lea     rdx, [rsp+0D8h+var_70]
0x18001aed5  mov     rax, [rax+18h]
0x18001aed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aede  nop
0x18001aedf  lea     rcx, [rsp+0D8h+var_98]
0x18001aee4  call    ??$MakeCom@VLicenseCallback@@$$V@@YA?AV?$ComPtr@VLicenseCallback@@@WRL@Microsoft@@XZ; MakeCom<LicenseCallback,>(void)
0x18001aee9  nop
0x18001aeea  mov     r12, [r13+40h]
0x18001aeee  mov     rax, [r12]
0x18001aef2  mov     [rsp+0D8h+var_88], rax
0x18001aef7  mov     rcx, [rsp+0D8h+var_98]
0x18001aefc  mov     [rsp+0D8h+var_80], rcx
0x18001af01  test    rcx, rcx
0x18001af04  jz      short loc_18001AF13
0x18001af06  mov     rax, [rcx]
0x18001af09  mov     rax, [rax+8]
0x18001af0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af12  nop
0x18001af13  xorps   xmm0, xmm0
0x18001af16  movups  [rsp+0D8h+var_68], xmm0
0x18001af1b  xorps   xmm1, xmm1
0x18001af1e  movdqu  [rsp+0D8h+var_58], xmm1
0x18001af27  inc     rbx
0x18001af2a  cmp     [rdi+rbx*2], r15w
0x18001af2f  jnz     short loc_18001AF27
0x18001af31  mov     r8, 7FFFFFFFFFFFFFFEh
0x18001af3b  cmp     rbx, r8
0x18001af3e  jbe     short loc_18001AF4D
0x18001af40  lea     rcx, aStringTooLong; "string too long"
0x18001af47  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001af4d  cmp     rbx, 7
0x18001af51  ja      short loc_18001AF82
0x18001af53  mov     qword ptr [rsp+0D8h+var_58], rbx
0x18001af5b  mov     qword ptr [rsp+0D8h+var_58+8], 7
0x18001af67  add     rbx, rbx
0x18001af6a  mov     r8, rbx; Size
0x18001af6d  mov     rdx, rdi; Src
0x18001af70  lea     rcx, [rsp+0D8h+var_68]; void *
0x18001af75  call    memcpy_0
0x18001af7a  mov     word ptr [rsp+rbx+0D8h+var_68], r15w
0x18001af80  jmp     short loc_18001AFD1
0x18001af82  mov     edx, 7
0x18001af87  mov     rcx, rbx
0x18001af8a  call    ?_Calculate_growth@?$basic_string@GUcontent_id_char_traits@@V?$allocator@G@std@@@std@@CA_K_K00@Z; std::basic_string<ushort,content_id_char_traits,std::allocator<ushort>>::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18001af8f  mov     r15, rax
0x18001af92  lea     rdx, [rax+1]
0x18001af96  lea     rcx, [rsp+0D8h+var_68]
0x18001af9b  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x18001afa0  mov     rsi, rax
0x18001afa3  mov     qword ptr [rsp+0D8h+var_68], rax
0x18001afa8  mov     qword ptr [rsp+0D8h+var_58], rbx
0x18001afb0  mov     qword ptr [rsp+0D8h+var_58+8], r15
0x18001afb8  add     rbx, rbx
0x18001afbb  mov     r8, rbx; Size
0x18001afbe  mov     rdx, rdi; Src
0x18001afc1  mov     rcx, rax; void *
0x18001afc4  call    memcpy_0
0x18001afc9  xor     r15d, r15d
0x18001afcc  mov     [rbx+rsi], r15w
0x18001afd1  lea     rax, [rsp+0D8h+var_80]
0x18001afd6  mov     [rsp+0D8h+var_B0], rax
0x18001afdb  lea     rax, [rsp+0D8h+var_70]
0x18001afe0  mov     qword ptr [rsp+0D8h+bIgnoreCase], rax
0x18001afe5  mov     r9d, dword ptr [rsp+0D8h+var_90]
0x18001afea  lea     r8, [rsp+0D8h+var_68]
0x18001afef  lea     rdx, [rsp+0D8h+var_78]
0x18001aff4  mov     rcx, r12
0x18001aff7  mov     rax, [rsp+0D8h+var_88]
0x18001affc  mov     rax, [rax+40h]
0x18001b000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b005  nop
0x18001b006  mov     rdx, qword ptr [rsp+0D8h+var_58+8]
0x18001b00e  cmp     rdx, 7
0x18001b012  jbe     short loc_18001B026
0x18001b014  lea     rdx, ds:2[rdx*2]
0x18001b01c  mov     rcx, qword ptr [rsp+0D8h+var_68]
0x18001b021  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001b026  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001b02e  movdqu  [rsp+0D8h+var_58], xmm0
0x18001b037  mov     word ptr [rsp+0D8h+var_68], r15w
0x18001b03d  mov     rcx, [rsp+0D8h+var_80]
0x18001b042  test    rcx, rcx
0x18001b045  jz      short loc_18001B059
0x18001b047  mov     [rsp+0D8h+var_80], r15
0x18001b04c  mov     rax, [rcx]
0x18001b04f  mov     rax, [rax+10h]
0x18001b053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b058  nop
0x18001b059  mov     rcx, [rsp+0D8h+var_98]
0x18001b05e  add     rcx, 8
0x18001b062  mov     rax, [rcx]
0x18001b065  mov     rax, [rax+18h]
0x18001b069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b06e  mov     rcx, [rsp+0D8h+var_98]
0x18001b073  add     rcx, 8
0x18001b077  mov     rax, [rcx]
0x18001b07a  lea     rdx, [rsp+0D8h+var_88]
0x18001b07f  mov     rax, [rax+28h]
0x18001b083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b088  mov     rbx, rax
0x18001b08b  mov     r8, [rsp+0D8h+var_98]
0x18001b090  mov     rcx, [r8+8]
0x18001b094  mov     rax, [rcx+20h]
0x18001b098  lea     rdx, [rsp+0D8h+var_90]
0x18001b09d  lea     rcx, [r8+8]
0x18001b0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0a6  nop
0x18001b0a7  mov     [rsp+0D8h+var_B0], r14
0x18001b0ac  mov     byte ptr [rsp+0D8h+bIgnoreCase], 1; int
0x18001b0b1  lea     r9, [rsp+0D8h+var_78]
0x18001b0b6  mov     r8, rbx
0x18001b0b9  mov     rdx, rax
0x18001b0bc  mov     rcx, [r13+50h]
0x18001b0c0  call    ?CreateLicenseInstance@@YAJPEAUIServiceProvider@@AEBV?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@AEBV?$ComPtr@UIStoredLeaseDocument@@@34@AEBV?$ComPtr@UIKeyStateMachine@@@34@_NPEAPEAUILicenseInstance@@@Z; CreateLicenseInstance(IServiceProvider *,Microsoft::WRL::ComPtr<IStoredKeyDocument> const &,Microsoft::WRL::ComPtr<IStoredLeaseDocument> const &,Microsoft::WRL::ComPtr<IKeyStateMachine> const &,bool,ILicenseInstance * *)
0x18001b0c5  mov     rcx, [rsp+0D8h]; this
0x18001b0cd  test    eax, eax
0x18001b0cf  jns     short loc_18001B0E6
0x18001b0d1  mov     r9d, eax; char *
0x18001b0d4  lea     r8, aOnecoreuapEndu_15; "onecoreuap\\enduser\\winstore\\licensem"...
0x18001b0db  mov     edx, 66h ; 'f'; void *
0x18001b0e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001b0e6  mov     rcx, [rsp+0D8h+var_90]
0x18001b0eb  test    rcx, rcx
0x18001b0ee  jz      short loc_18001B102
0x18001b0f0  mov     [rsp+0D8h+var_90], r15
0x18001b0f5  mov     rax, [rcx]
0x18001b0f8  mov     rax, [rax+10h]
0x18001b0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b101  nop
0x18001b102  mov     rcx, [rsp+0D8h+var_88]
0x18001b107  test    rcx, rcx
0x18001b10a  jz      short loc_18001B11E
0x18001b10c  mov     [rsp+0D8h+var_88], r15
0x18001b111  mov     rax, [rcx]
0x18001b114  mov     rax, [rax+10h]
0x18001b118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b11d  nop
0x18001b11e  mov     rcx, [rsp+0D8h+var_78]
0x18001b123  test    rcx, rcx
0x18001b126  jz      short loc_18001B13A
0x18001b128  mov     [rsp+0D8h+var_78], r15
0x18001b12d  mov     rax, [rcx]
0x18001b130  mov     rax, [rax+10h]
0x18001b134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b139  nop
0x18001b13a  mov     rcx, [rsp+0D8h+var_98]
0x18001b13f  test    rcx, rcx
0x18001b142  jz      short loc_18001B156
0x18001b144  mov     [rsp+0D8h+var_98], r15
0x18001b149  mov     rax, [rcx]
0x18001b14c  mov     rax, [rax+10h]
0x18001b150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b155  nop
0x18001b156  mov     rcx, [rsp+0D8h+var_70]
0x18001b15b  test    rcx, rcx
0x18001b15e  jz      short loc_18001B172
0x18001b160  mov     [rsp+0D8h+var_70], r15
0x18001b165  mov     rax, [rcx]
0x18001b168  mov     rax, [rax+10h]
0x18001b16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b171  nop
0x18001b172  xor     eax, eax
0x18001b174  jmp     short loc_18001B17A
0x18001b176  mov     eax, dword ptr [rsp+0D8h+var_90]
0x18001b17a  mov     rcx, [rsp+0D8h+var_48]
0x18001b182  xor     rcx, rsp; StackCookie
0x18001b185  call    __security_check_cookie
0x18001b18a  add     rsp, 0A0h
0x18001b191  pop     r15
0x18001b193  pop     r14
0x18001b195  pop     r13
0x18001b197  pop     r12
0x18001b199  pop     rdi
0x18001b19a  pop     rsi
0x18001b19b  pop     rbx
0x18001b19c  retn
```
