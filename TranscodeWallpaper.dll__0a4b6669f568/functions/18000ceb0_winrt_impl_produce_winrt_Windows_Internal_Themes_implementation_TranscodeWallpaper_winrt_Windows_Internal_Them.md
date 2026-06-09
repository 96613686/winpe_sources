# winrt::impl::produce<winrt::Windows::Internal::Themes::implementation::TranscodeWallpaper,winrt::Windows::Internal::Themes::ITranscodeWallpaperStatics>::TranscodeImageFile(void *,void *,uint *,uint *)

- ea: `0x18000ceb0`
- end: `0x18000d046`
- name: `?TranscodeImageFile@?$produce@UTranscodeWallpaper@implementation@Themes@Internal@Windows@winrt@@UITranscodeWallpaperStatics@3456@@impl@winrt@@UEAAHPEAX0PEAI1@Z`
- size: `406`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int *, _DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a1a8`
- `0x18000aa3c`
- `0x18000ab5c`
- `0x18000ae9c`
- `0x18000ceb0`
- `0x18000f010`

## import_xrefs

- `SHCORE!SHCreateStreamOnFileEx` at `0x18000cf4f`
- `SHCORE!SHCreateStreamOnFileEx` at `0x18000cf4f`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18000cf05`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18000cf05`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Themes::implementation::TranscodeWallpaper,winrt::Windows::Internal::Themes::ITranscodeWallpaperStatics>::TranscodeImageFile(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        _DWORD *a5)
{
  const WCHAR *v8; // rcx
  const WCHAR *v9; // rbx
  HRESULT v10; // eax
  unsigned int v11; // r8d
  HRESULT v12; // eax
  unsigned int v13; // r8d
  int v14; // eax
  unsigned int v15; // r8d
  int v16; // eax
  unsigned int v17; // r8d
  __int64 result; // rax
  int pstmTemplate; // [rsp+20h] [rbp-38h]
  int pstmTemplatea; // [rsp+20h] [rbp-38h]
  int pstmTemplateb; // [rsp+20h] [rbp-38h]
  unsigned int v22; // [rsp+30h] [rbp-28h] BYREF
  IStream *ppstm; // [rsp+38h] [rbp-20h] BYREF
  void *ppv[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v26; // [rsp+60h] [rbp+8h] BYREF

  v26 = a1;
  StripProcessPrivileges();
  ppv[0] = 0;
  if ( a2 )
  {
    v8 = *(const WCHAR **)(a2 + 16);
    v9 = &pszFile;
  }
  else
  {
    v9 = &pszFile;
    v8 = &pszFile;
  }
  v10 = SHCreateItemFromParsingName(v8, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, ppv);
  try
  {
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x3B, v11, (const char *)(unsigned int)v10, pstmTemplate);
    ppstm = 0;
    if ( a3 )
      v9 = *(const WCHAR **)(a3 + 16);
    v12 = SHCreateStreamOnFileEx(v9, 0x1012u, 0x80u, 1, 0, &ppstm);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x3D, v13, (const char *)(unsigned int)v12, pstmTemplatea);
    v22 = 0;
    LODWORD(v26) = 0;
    v14 = TranscodeImage((struct IShellItem *)ppv[0], 1, ppstm, &v22, (unsigned int *)&v26);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x42, v15, (const char *)(unsigned int)v14, pstmTemplateb);
    v16 = ((__int64 (__fastcall *)(IStream *, __int64))ppstm->lpVtbl->Commit)(ppstm, 4);
    if ( v16 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x43, v17, (const char *)(unsigned int)v16, pstmTemplateb);
    *a5 = v26;
    *a4 = v22;
    if ( ppstm )
      winrt::com_ptr<IShellItem>::unconditional_release_ref(&ppstm);
    if ( ppv[0] )
      winrt::com_ptr<IShellItem>::unconditional_release_ref(ppv);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v26);
  }
  return result;
}

```

## disassembly

```asm
0x18000ceb0  mov     [rsp+arg_8], rbx
0x18000ceb5  mov     [rsp+arg_10], rsi
0x18000ceba  mov     [rsp+arg_0], rcx
0x18000cebf  push    rdi
0x18000cec0  sub     rsp, 50h
0x18000cec4  mov     rsi, r9
0x18000cec7  mov     rdi, r8
0x18000ceca  mov     rbx, rdx
0x18000cecd  call    ?StripProcessPrivileges@@YAJXZ; StripProcessPrivileges(void)
0x18000ced2  mov     [rsp+58h+ppv], 0
0x18000cedb  test    rbx, rbx
0x18000cede  jz      short loc_18000CEED
0x18000cee0  mov     rcx, [rbx+10h]
0x18000cee4  lea     rbx, pszFile
0x18000ceeb  jmp     short loc_18000CEF7
0x18000ceed  lea     rbx, pszFile
0x18000cef4  mov     rcx, rbx; pszPath
0x18000cef7  lea     r9, [rsp+58h+ppv]; ppv
0x18000cefc  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18000cf03  xor     edx, edx; pbc
0x18000cf05  call    cs:__imp_SHCreateItemFromParsingName
0x18000cf0b  mov     rcx, [rsp+58h]; this
0x18000cf10  test    eax, eax
0x18000cf12  js      loc_18000D00F
0x18000cf18  mov     [rsp+58h+var_20], 0
0x18000cf21  test    rdi, rdi
0x18000cf24  jz      short loc_18000CF2A
0x18000cf26  mov     rbx, [rdi+10h]
0x18000cf2a  lea     rax, [rsp+58h+var_20]
0x18000cf2f  mov     [rsp+58h+ppstm], rax; ppstm
0x18000cf34  mov     [rsp+58h+pstmTemplate], 0; int
0x18000cf3d  mov     edx, 1012h; grfMode
0x18000cf42  mov     r9d, 1; fCreate
0x18000cf48  lea     r8d, [r9+7Fh]; dwAttributes
0x18000cf4c  mov     rcx, rbx; pszFile
0x18000cf4f  call    cs:__imp_SHCreateStreamOnFileEx
0x18000cf55  mov     rcx, [rsp+58h]; this
0x18000cf5a  test    eax, eax
0x18000cf5c  js      loc_18000D01D
0x18000cf62  mov     [rsp+58h+var_28], 0
0x18000cf6a  mov     dword ptr [rsp+58h+arg_0], 0
0x18000cf72  lea     rax, [rsp+58h+arg_0]
0x18000cf77  mov     [rsp+58h+pstmTemplate], rax; int
0x18000cf7c  lea     r9, [rsp+58h+var_28]; unsigned int *
0x18000cf81  mov     r8, [rsp+58h+var_20]; struct IStream *
0x18000cf86  mov     dl, 1; bool
0x18000cf88  mov     rcx, [rsp+58h+ppv]; struct IShellItem *
0x18000cf8d  call    ?TranscodeImage@@YAJPEAUIShellItem@@_NPEAUIStream@@PEAI3@Z; TranscodeImage(IShellItem *,bool,IStream *,uint *,uint *)
0x18000cf92  mov     rcx, [rsp+58h]; this
0x18000cf97  test    eax, eax
0x18000cf99  js      loc_18000D02A
0x18000cf9f  mov     rcx, [rsp+58h+var_20]
0x18000cfa4  mov     rax, [rcx]
0x18000cfa7  mov     edx, 4
0x18000cfac  mov     rax, [rax+40h]
0x18000cfb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfb5  mov     rcx, [rsp+58h]; this
0x18000cfba  test    eax, eax
0x18000cfbc  js      short loc_18000D037
0x18000cfbe  mov     rcx, [rsp+58h+arg_20]
0x18000cfc6  mov     eax, dword ptr [rsp+58h+arg_0]
0x18000cfca  mov     [rcx], eax
0x18000cfcc  mov     eax, [rsp+58h+var_28]
0x18000cfd0  mov     [rsi], eax
0x18000cfd2  cmp     [rsp+58h+var_20], 0
0x18000cfd8  jz      short loc_18000CFE5
0x18000cfda  lea     rcx, [rsp+58h+var_20]
0x18000cfdf  call    ?unconditional_release_ref@?$com_ptr@UIShellItem@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellItem>::unconditional_release_ref(void)
0x18000cfe4  nop
0x18000cfe5  cmp     [rsp+58h+ppv], 0
0x18000cfeb  jz      short loc_18000CFF7
0x18000cfed  lea     rcx, [rsp+58h+ppv]
0x18000cff2  call    ?unconditional_release_ref@?$com_ptr@UIShellItem@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellItem>::unconditional_release_ref(void)
0x18000cff7  xor     eax, eax
0x18000cff9  jmp     short loc_18000CFFF
0x18000cffb  mov     eax, dword ptr [rsp+58h+arg_0]
0x18000cfff  mov     rbx, [rsp+58h+arg_8]
0x18000d004  mov     rsi, [rsp+58h+arg_10]
0x18000d009  add     rsp, 50h
0x18000d00d  pop     rdi
0x18000d00e  retn
0x18000d00f  mov     r9d, eax; char *
0x18000d012  mov     edx, 3Bh ; ';'; void *
0x18000d017  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d01d  mov     r9d, eax; char *
0x18000d020  mov     edx, 3Dh ; '='; void *
0x18000d025  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d02a  mov     r9d, eax; char *
0x18000d02d  mov     edx, 42h ; 'B'; void *
0x18000d032  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d037  mov     r9d, eax; char *
0x18000d03a  mov     edx, 43h ; 'C'; void *
0x18000d03f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
