# CMapi2Handler::ValidateMapiUrl(wchar_t const *)

- ea: `0x180012554`
- end: `0x180012693`
- name: `?ValidateMapiUrl@CMapi2Handler@@AEAAJPEB_W@Z`
- size: `319`
- prototype: `__int64 __fastcall(CMapi2Handler *this, const wchar_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000f370`
- `0x18000fbc0`

## callees

- `0x18000e684`
- `0x18000e8ac`
- `0x18000ebac`
- `0x1800114cc`
- `0x180011884`
- `0x180012554`
- `0x18002c070`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012599`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012599`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800125f6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012625`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800125f6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012625`

## pseudocode

```c
__int64 __fastcall CMapi2Handler::ValidateMapiUrl(CMapi2Handler *this, const wchar_t *a2)
{
  _QWORD *v3; // rax
  int v4; // ebx
  unsigned int v5; // ebx
  PCNZWCH lpString1; // [rsp+38h] [rbp-9h] BYREF
  PCNZWCH v8; // [rsp+40h] [rbp-1h]
  __int64 v9; // [rsp+50h] [rbp+Fh]
  __int64 v10; // [rsp+58h] [rbp+17h]
  CMapi2Handler *v11; // [rsp+A8h] [rbp+67h] BYREF
  __int64 v12; // [rsp+B8h] [rbp+77h] BYREF

  v11 = this;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v11);
  v3 = (_QWORD *)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Left(&v11, &v12, 5);
  v4 = _o__wcsicmp(*v3, L"mapi:");
  ATL::CStringData::Release((ATL::CStringData *)(v12 - 24));
  if ( v4 )
  {
    v5 = -2147024809;
  }
  else
  {
    CMapiUrl::CMapiUrl((CMapiUrl *)&lpString1, a2);
    CMapiUrl::InitFormattedUrlSid();
    if ( CompareStringW(0x7Fu, 1u, lpString1, *((_DWORD *)lpString1 - 4), L"mapi", -1) == 2
      && CompareStringW(0x7Fu, 1u, v8, *((_DWORD *)v8 - 4), CMapiUrl::s_userSid, *((_DWORD *)CMapiUrl::s_userSid - 4)) == 2 )
    {
      if ( !*(_DWORD *)(v9 - 16) || *(_DWORD *)(v10 - 16) )
      {
        CMapiUrl::~CMapiUrl((CMapiUrl *)&lpString1);
        v5 = 0;
      }
      else
      {
        CMapiUrl::~CMapiUrl((CMapiUrl *)&lpString1);
        v5 = -2147216895;
      }
    }
    else
    {
      CMapiUrl::~CMapiUrl((CMapiUrl *)&lpString1);
      v5 = -2147218169;
    }
  }
  ATL::CStringData::Release((CMapi2Handler *)((char *)v11 - 24));
  return v5;
}

```

## disassembly

```asm
0x180012554  mov     rax, rsp
0x180012557  mov     [rax+10h], rbx
0x18001255b  mov     [rax+20h], rdi
0x18001255f  mov     [rax+8], rcx
0x180012563  push    rbp
0x180012564  lea     rbp, [rax-5Fh]
0x180012568  sub     rsp, 90h
0x18001256f  mov     rdi, rdx
0x180012572  lea     rcx, [rbp+57h+arg_0]
0x180012576  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x18001257b  nop
0x18001257c  mov     r8d, 5
0x180012582  lea     rdx, [rbp+57h+arg_10]
0x180012586  lea     rcx, [rbp+57h+arg_0]
0x18001258a  call    ?Left@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Left(int)
0x18001258f  lea     rdx, aMapi_2; "mapi:"
0x180012596  mov     rcx, [rax]
0x180012599  call    cs:__imp__o__wcsicmp
0x18001259f  mov     ebx, eax
0x1800125a1  mov     rcx, [rbp+57h+arg_10]
0x1800125a5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800125a9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800125ae  test    ebx, ebx
0x1800125b0  jz      short loc_1800125BC
0x1800125b2  mov     ebx, 80070057h
0x1800125b7  jmp     loc_18001266F
0x1800125bc  mov     rdx, rdi; wchar_t *
0x1800125bf  lea     rcx, [rbp+57h+lpString1]; this
0x1800125c3  call    ??0CMapiUrl@@QEAA@PEB_W@Z; CMapiUrl::CMapiUrl(wchar_t const *)
0x1800125c8  nop
0x1800125c9  call    ?InitFormattedUrlSid@CMapiUrl@@CAJXZ; CMapiUrl::InitFormattedUrlSid(void)
0x1800125ce  mov     r8, [rbp+57h+lpString1]; lpString1
0x1800125d2  mov     [rsp+90h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800125da  lea     rax, aMapi_0; "mapi"
0x1800125e1  mov     [rsp+90h+lpString2], rax; lpString2
0x1800125e6  mov     r9d, [r8-10h]; cchCount1
0x1800125ea  mov     ebx, 1
0x1800125ef  mov     edx, ebx; dwCmpFlags
0x1800125f1  lea     edi, [rbx+7Eh]
0x1800125f4  mov     ecx, edi; Locale
0x1800125f6  call    cs:__imp_CompareStringW
0x1800125fc  cmp     eax, 2
0x1800125ff  jnz     short loc_180012661
0x180012601  mov     rax, cs:?s_userSid@CMapiUrl@@0V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@A; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> CMapiUrl::s_userSid
0x180012608  mov     r10, [rbp+57h+var_58]
0x18001260c  mov     r8d, [rax-10h]
0x180012610  mov     [rsp+90h+cchCount2], r8d; cchCount2
0x180012615  mov     [rsp+90h+lpString2], rax; lpString2
0x18001261a  mov     r9d, [r10-10h]; cchCount1
0x18001261e  mov     r8, r10; lpString1
0x180012621  mov     edx, ebx; dwCmpFlags
0x180012623  mov     ecx, edi; Locale
0x180012625  call    cs:__imp_CompareStringW
0x18001262b  cmp     eax, 2
0x18001262e  jnz     short loc_180012661
0x180012630  mov     rax, [rbp+57h+var_48]
0x180012634  cmp     dword ptr [rax-10h], 0
0x180012638  jz      short loc_180012654
0x18001263a  mov     rax, [rbp+57h+var_40]
0x18001263e  cmp     dword ptr [rax-10h], 0
0x180012642  jnz     short loc_180012654
0x180012644  lea     rcx, [rbp+57h+lpString1]; this
0x180012648  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x18001264d  mov     ebx, 80041201h
0x180012652  jmp     short loc_18001266F
0x180012654  lea     rcx, [rbp+57h+lpString1]; this
0x180012658  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x18001265d  xor     ebx, ebx
0x18001265f  jmp     short loc_18001266F
0x180012661  lea     rcx, [rbp+57h+lpString1]; this
0x180012665  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x18001266a  mov     ebx, 80040D07h
0x18001266f  mov     rcx, [rbp+57h+arg_0]
0x180012673  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180012677  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001267c  mov     eax, ebx
0x18001267e  lea     r11, [rsp+90h+var_s0]
0x180012686  mov     rbx, [r11+18h]
0x18001268a  mov     rdi, [r11+28h]
0x18001268e  mov     rsp, r11
0x180012691  pop     rbp
0x180012692  retn
```
