# WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb::GetVerbDisplayName(tagMENUITEMINFOW const &,HMENU__ *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1800dc4e0`
- end: `0x1800dc8a7`
- name: `?GetVerbDisplayName@TileShellItemVerb@Private@UnifiedTile@Shell@WindowsInternal@@CAJAEBUtagMENUITEMINFOW@@PEAUHMENU__@@PEAPEAUHSTRING__@@22@Z`
- size: `967`
- prototype: `static int(const struct tagMENUITEMINFOW *, HMENU, HSTRING *, HSTRING *, HSTRING *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800db974`
- `0x1801a4dc4`

## callees

- `0x18001dac0`
- `0x180030e44`
- `0x18003153c`
- `0x180073930`
- `0x1800dc4e0`
- `0x180147be8`
- `0x1801506f0`
- `0x180201e50`
- `0x18020295c`
- `0x18022cc70`
- `0x1802358d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc764`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc82d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc83d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc84d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc764`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc82d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc83d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc84d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800dc77d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800dc77d`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemInfoW` at `0x1800dc5bb`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemInfoW` at `0x1800dc5bb`

## string_xrefs

- `0x1800dc564`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1800dc5cd`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1800dc71f`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1800dc794`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1800dc7e4`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb::GetVerbDisplayName(
        const struct tagMENUITEMINFOW *a1,
        HMENU a2,
        HSTRING *a3,
        HSTRING *a4,
        HSTRING *a5)
{
  const char *v9; // r9
  __int64 v10; // rbx
  unsigned __int16 *v11; // r12
  unsigned __int16 *i; // rsi
  unsigned __int16 v13; // r9
  unsigned __int16 *v14; // rbx
  char v15; // di
  __int64 v16; // rdx
  PCNZWCH *v17; // rcx
  int v18; // eax
  UINT32 v19; // ebx
  const WCHAR *v20; // rdi
  HRESULT v21; // eax
  HSTRING v22; // rcx
  int v23; // eax
  HSTRING v24; // rax
  HSTRING v25; // rax
  HSTRING v26; // rax
  HSTRING string; // [rsp+20h] [rbp-2E8h] BYREF
  HSTRING v29; // [rsp+28h] [rbp-2E0h] BYREF
  unsigned __int16 v30[4]; // [rsp+30h] [rbp-2D8h] BYREF
  HSTRING v31; // [rsp+38h] [rbp-2D0h] BYREF
  struct tagMENUITEMINFOW mii; // [rsp+40h] [rbp-2C8h] BYREF
  PCNZWCH sourceString[2]; // [rsp+90h] [rbp-278h] BYREF
  UINT32 length[2]; // [rsp+A0h] [rbp-268h]
  unsigned __int64 v35; // [rsp+A8h] [rbp-260h]
  _WORD v36[264]; // [rsp+B0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+0h]

  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  memset_0(v36, 0, 0x208u);
  if ( (a1->fType & 0x40) != 0 && a1->cch + 1 >= 0x104 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
      (const char *)0x8007007ALL,
      (int)string);
  memset_0(&mii, 0, sizeof(mii));
  mii.cbSize = 80;
  mii.fMask = 64;
  mii.cch = 260;
  mii.dwTypeData = v36;
  if ( !GetMenuItemInfoW(a2, a1->wID, 0, &mii) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1F0,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
      v9);
  v10 = -1;
  do
    ++v10;
  while ( v36[v10] );
  *(_OWORD *)sourceString = 0;
  *(_QWORD *)length = 0;
  v35 = 0;
  std::wstring::_Construct_empty(sourceString);
  std::wstring::reserve(sourceString, v10);
  v29 = 0;
  v11 = &v36[v10];
  for ( i = v36; i < v11; i = v14 + 1 )
  {
    v13 = *i;
    if ( *i == 9 )
      break;
    v14 = i + 1;
    if ( v13 == 38 )
    {
      v15 = 1;
      v13 = *v14;
    }
    else
    {
      v15 = 0;
    }
    if ( !v15 )
      v14 = i;
    v30[0] = v13;
    i = v14;
    if ( v13 == 9 || !v13 )
      break;
    v16 = *(_QWORD *)length;
    v17 = sourceString;
    if ( *(_QWORD *)length >= v35 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(
        sourceString,
        *(_QWORD *)length,
        0);
    }
    else
    {
      ++*(_QWORD *)length;
      if ( v35 > 7 )
        v17 = (PCNZWCH *)sourceString[0];
      *((_WORD *)v17 + v16) = v13;
      *((_WORD *)v17 + v16 + 1) = 0;
    }
    if ( v15 && a4 && !v29 )
    {
      v18 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v29, v30, 1u);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x211,
          (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
          (const char *)(unsigned int)v18,
          (int)string);
    }
  }
  string = 0;
  v19 = length[0];
  v20 = (const WCHAR *)sourceString;
  if ( v35 > 7 )
    v20 = sourceString[0];
  WindowsDeleteString(0);
  string = 0;
  v21 = WindowsCreateString(v20, v19, &string);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x216,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
      (const char *)(unsigned int)v21,
      (int)string);
  v22 = 0;
  v31 = 0;
  if ( a5 && i < v11 && *i == 9 )
  {
    *(_QWORD *)v30 = i + 1;
    v23 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v31);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x21C,
        (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
        (const char *)(unsigned int)v23,
        (int)string);
    v22 = v31;
  }
  v24 = string;
  string = 0;
  *a3 = v24;
  if ( a4 )
  {
    v25 = v29;
    v29 = 0;
    *a4 = v25;
  }
  if ( a5 )
  {
    v26 = v22;
    v22 = 0;
    v31 = 0;
    *a5 = v26;
  }
  WindowsDeleteString(v22);
  v31 = 0;
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v29);
  v29 = 0;
  if ( v35 > 7 )
    std::_Deallocate<16>(sourceString[0], 2 * v35 + 2);
  return 0;
}

```

## disassembly

```asm
0x1800dc4e0  push    rbx
0x1800dc4e2  push    rsi
0x1800dc4e3  push    rdi
0x1800dc4e4  push    r12
0x1800dc4e6  push    r13
0x1800dc4e8  push    r14
0x1800dc4ea  push    r15
0x1800dc4ec  sub     rsp, 2D0h
0x1800dc4f3  mov     rax, cs:__security_cookie
0x1800dc4fa  xor     rax, rsp
0x1800dc4fd  mov     [rsp+308h+var_48], rax
0x1800dc505  mov     r15, r9
0x1800dc508  mov     r13, r8
0x1800dc50b  mov     rdi, rdx
0x1800dc50e  mov     rbx, rcx
0x1800dc511  mov     r14, [rsp+308h+arg_20]
0x1800dc519  xor     r12d, r12d
0x1800dc51c  mov     [r8], r12
0x1800dc51f  test    r9, r9
0x1800dc522  jz      short loc_1800DC527
0x1800dc524  mov     [r9], r12
0x1800dc527  test    r14, r14
0x1800dc52a  jz      short loc_1800DC52F
0x1800dc52c  mov     [r14], r12
0x1800dc52f  xor     edx, edx; Val
0x1800dc531  mov     r8d, 208h; Size
0x1800dc537  lea     rcx, [rsp+308h+var_258]; void *
0x1800dc53f  call    memset_0
0x1800dc544  test    byte ptr [rbx+8], 40h
0x1800dc548  jz      short loc_1800DC575
0x1800dc54a  mov     rcx, [rsp+308h]; this
0x1800dc552  mov     eax, [rbx+40h]
0x1800dc555  inc     eax
0x1800dc557  cmp     eax, 104h
0x1800dc55c  jb      short loc_1800DC575
0x1800dc55e  mov     r9d, 8007007Ah; char *
0x1800dc564  lea     r8, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1800dc56b  mov     edx, 1E7h; void *
0x1800dc570  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800dc575  mov     esi, 50h ; 'P'
0x1800dc57a  mov     r8d, esi; Size
0x1800dc57d  xor     edx, edx; Val
0x1800dc57f  lea     rcx, [rsp+308h+mii]; void *
0x1800dc584  call    memset_0
0x1800dc589  mov     [rsp+308h+mii.cbSize], esi
0x1800dc58d  mov     [rsp+308h+mii.fMask], 40h ; '@'
0x1800dc595  mov     [rsp+308h+mii.cch], 104h
0x1800dc5a0  lea     rax, [rsp+308h+var_258]
0x1800dc5a8  mov     [rsp+308h+mii.dwTypeData], rax
0x1800dc5ad  lea     r9, [rsp+308h+mii]; lpmii
0x1800dc5b2  xor     r8d, r8d; fByPosition
0x1800dc5b5  mov     edx, [rbx+10h]; item
0x1800dc5b8  mov     rcx, rdi; hmenu
0x1800dc5bb  call    cs:__imp_GetMenuItemInfoW
0x1800dc5c1  mov     rcx, [rsp+308h]; this
0x1800dc5c9  test    eax, eax
0x1800dc5cb  jnz     short loc_1800DC5DE
0x1800dc5cd  lea     r8, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1800dc5d4  mov     edx, 1F0h; void *
0x1800dc5d9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800dc5de  lea     rax, [rsp+308h+var_258]
0x1800dc5e6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800dc5ea  inc     rbx
0x1800dc5ed  cmp     [rax+rbx*2], r12w
0x1800dc5f2  jnz     short loc_1800DC5EA
0x1800dc5f4  xorps   xmm0, xmm0
0x1800dc5f7  movups  xmmword ptr [rsp+308h+sourceString], xmm0
0x1800dc5ff  mov     qword ptr [rsp+308h+length], r12
0x1800dc607  mov     [rsp+308h+var_260], r12
0x1800dc60f  lea     rcx, [rsp+308h+sourceString]
0x1800dc617  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800dc61c  nop
0x1800dc61d  mov     rdx, rbx
0x1800dc620  lea     rcx, [rsp+308h+sourceString]
0x1800dc628  call    ?reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x1800dc62d  mov     [rsp+308h+var_2E0], r12
0x1800dc632  lea     r12, [rsp+308h+var_258]
0x1800dc63a  lea     r12, [r12+rbx*2]
0x1800dc63e  lea     rsi, [rsp+308h+var_258]
0x1800dc646  cmp     rsi, r12
0x1800dc649  jnb     loc_1800DC739
0x1800dc64f  movzx   r9d, word ptr [rsi]
0x1800dc653  cmp     r9w, 9
0x1800dc658  jz      loc_1800DC739
0x1800dc65e  lea     rbx, [rsi+2]
0x1800dc662  xor     r8d, r8d
0x1800dc665  cmp     r9w, 26h ; '&'
0x1800dc66a  jnz     short loc_1800DC675
0x1800dc66c  mov     dil, 1
0x1800dc66f  movzx   r9d, word ptr [rbx]
0x1800dc673  jmp     short loc_1800DC678
0x1800dc675  mov     dil, r8b
0x1800dc678  test    dil, dil
0x1800dc67b  cmovz   rbx, rsi
0x1800dc67f  mov     [rsp+308h+var_2D8], r9w
0x1800dc685  mov     rsi, rbx
0x1800dc688  cmp     r9w, 9
0x1800dc68d  jz      loc_1800DC73C
0x1800dc693  test    r9w, r9w
0x1800dc697  jz      loc_1800DC73C
0x1800dc69d  mov     rdx, qword ptr [rsp+308h+length]
0x1800dc6a5  lea     rcx, [rsp+308h+sourceString]
0x1800dc6ad  cmp     rdx, [rsp+308h+var_260]
0x1800dc6b5  jnb     short loc_1800DC6E2
0x1800dc6b7  lea     rax, [rdx+1]
0x1800dc6bb  mov     qword ptr [rsp+308h+length], rax
0x1800dc6c3  cmp     [rsp+308h+var_260], 7
0x1800dc6cc  cmova   rcx, [rsp+308h+sourceString]
0x1800dc6d5  mov     [rcx+rdx*2], r9w
0x1800dc6da  mov     [rcx+rdx*2+2], r8w
0x1800dc6e0  jmp     short loc_1800DC6EA
0x1800dc6e2  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1800dc6e7  xor     r8d, r8d
0x1800dc6ea  test    dil, dil
0x1800dc6ed  jz      short loc_1800DC730
0x1800dc6ef  test    r15, r15
0x1800dc6f2  jz      short loc_1800DC730
0x1800dc6f4  cmp     [rsp+308h+var_2E0], r8
0x1800dc6f9  jnz     short loc_1800DC730
0x1800dc6fb  mov     r8d, 1; unsigned int
0x1800dc701  lea     rdx, [rsp+308h+var_2D8]; unsigned __int16 *
0x1800dc706  lea     rcx, [rsp+308h+var_2E0]; this
0x1800dc70b  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800dc710  mov     rcx, [rsp+308h]; this
0x1800dc718  test    eax, eax
0x1800dc71a  jns     short loc_1800DC730
0x1800dc71c  mov     r9d, eax; char *
0x1800dc71f  lea     r8, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1800dc726  mov     edx, 211h; void *
0x1800dc72b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800dc730  lea     rsi, [rbx+2]
0x1800dc734  jmp     loc_1800DC646
0x1800dc739  xor     r8d, r8d
0x1800dc73c  mov     [rsp+308h+string], r8
0x1800dc741  mov     ebx, [rsp+308h+length]
0x1800dc748  lea     rdi, [rsp+308h+sourceString]
0x1800dc750  cmp     [rsp+308h+var_260], 7
0x1800dc759  cmova   rdi, [rsp+308h+sourceString]
0x1800dc762  xor     ecx, ecx; string
0x1800dc764  call    cs:__imp_WindowsDeleteString
0x1800dc76a  mov     [rsp+308h+string], 0; int
0x1800dc773  lea     r8, [rsp+308h+string]; string
0x1800dc778  mov     edx, ebx; length
0x1800dc77a  mov     rcx, rdi; sourceString
0x1800dc77d  call    cs:__imp_WindowsCreateString
0x1800dc783  mov     rcx, [rsp+308h]; this
0x1800dc78b  xor     ebx, ebx
0x1800dc78d  test    eax, eax
0x1800dc78f  jns     short loc_1800DC7A5
0x1800dc791  mov     r9d, eax; char *
0x1800dc794  lea     r8, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1800dc79b  mov     edx, 216h; void *
0x1800dc7a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800dc7a5  mov     rcx, rbx
0x1800dc7a8  mov     [rsp+308h+var_2D0], rbx
0x1800dc7ad  test    r14, r14
0x1800dc7b0  jz      short loc_1800DC7FA
0x1800dc7b2  cmp     rsi, r12
0x1800dc7b5  jnb     short loc_1800DC7FA
0x1800dc7b7  cmp     word ptr [rsi], 9
0x1800dc7bb  jnz     short loc_1800DC7FA
0x1800dc7bd  lea     rax, [rsi+2]
0x1800dc7c1  mov     qword ptr [rsp+308h+var_2D8], rax
0x1800dc7c6  lea     rdx, [rsp+308h+var_2D8]
0x1800dc7cb  lea     rcx, [rsp+308h+var_2D0]; string
0x1800dc7d0  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800dc7d5  mov     rcx, [rsp+308h]; this
0x1800dc7dd  test    eax, eax
0x1800dc7df  jns     short loc_1800DC7F5
0x1800dc7e1  mov     r9d, eax; char *
0x1800dc7e4  lea     r8, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1800dc7eb  mov     edx, 21Ch; void *
0x1800dc7f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800dc7f5  mov     rcx, [rsp+308h+var_2D0]
0x1800dc7fa  mov     rax, [rsp+308h+string]
0x1800dc7ff  mov     [rsp+308h+string], rbx
0x1800dc804  mov     [r13+0], rax
0x1800dc808  test    r15, r15
0x1800dc80b  jz      short loc_1800DC81A
0x1800dc80d  mov     rax, [rsp+308h+var_2E0]
0x1800dc812  mov     [rsp+308h+var_2E0], rbx
0x1800dc817  mov     [r15], rax
0x1800dc81a  test    r14, r14
0x1800dc81d  jz      short loc_1800DC82D
0x1800dc81f  mov     rax, rcx
0x1800dc822  mov     rcx, rbx; string
0x1800dc825  mov     [rsp+308h+var_2D0], rbx
0x1800dc82a  mov     [r14], rax
0x1800dc82d  call    cs:__imp_WindowsDeleteString
0x1800dc833  mov     [rsp+308h+var_2D0], rbx
0x1800dc838  mov     rcx, [rsp+308h+string]; string
0x1800dc83d  call    cs:__imp_WindowsDeleteString
0x1800dc843  mov     [rsp+308h+string], rbx
0x1800dc848  mov     rcx, [rsp+308h+var_2E0]; string
0x1800dc84d  call    cs:__imp_WindowsDeleteString
0x1800dc853  mov     [rsp+308h+var_2E0], rbx
0x1800dc858  mov     rdx, [rsp+308h+var_260]
0x1800dc860  cmp     rdx, 7
0x1800dc864  jbe     short loc_1800DC87B
0x1800dc866  lea     rdx, ds:2[rdx*2]
0x1800dc86e  mov     rcx, [rsp+308h+sourceString]
0x1800dc876  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800dc87b  xor     eax, eax
0x1800dc87d  jmp     short loc_1800DC883
0x1800dc87f  mov     eax, dword ptr [rsp+308h+var_2D8]
0x1800dc883  mov     rcx, [rsp+308h+var_48]
0x1800dc88b  xor     rcx, rsp; StackCookie
0x1800dc88e  call    __security_check_cookie
0x1800dc893  add     rsp, 2D0h
0x1800dc89a  pop     r15
0x1800dc89c  pop     r14
0x1800dc89e  pop     r13
0x1800dc8a0  pop     r12
0x1800dc8a2  pop     rdi
0x1800dc8a3  pop     rsi
0x1800dc8a4  pop     rbx
0x1800dc8a5  retn
```
