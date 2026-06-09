# FileFolder::GetExtractIconUIObjectOf(_ITEMIDLIST const *,_GUID const &,void * *)

- ea: `0x180008800`
- end: `0x1800088dd`
- name: `?GetExtractIconUIObjectOf@FileFolder@@MEAAXPEFBU_ITEMIDLIST@@AEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `void __fastcall(FileFolder *this, const struct _ITEMIDLIST *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180002030`
- `0x1800056e0`
- `0x18000591c`
- `0x180007150`
- `0x180008800`
- `0x1800088e4`

## import_xrefs

- `SHELL32!__imp_SHCreateFileExtractIconW` at `0x180008874`
- `SHELL32!__imp_SHCreateFileExtractIconW` at `0x180008874`

## pseudocode

```c
void __fastcall FileFolder::GetExtractIconUIObjectOf(
        FileFolder *this,
        const struct _ITEMIDLIST *a2,
        const struct _GUID *a3,
        void **a4)
{
  const WCHAR *v7; // rcx
  HRESULT IconW; // ebx
  unsigned int v9; // eax
  LPCWSTR pszFile[2]; // [rsp+20h] [rbp-48h] BYREF
  __m128i si128; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( a4 && a2 )
  {
    *(_OWORD *)pszFile = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(pszFile[0]) = 0;
    FileFolder::GetFileFolderName(this, a2, pszFile);
    if ( a2->mkid.cb < 0x32u )
    {
      v9 = wil::verify_hresult<long>(0x80070057);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\Utility.h",
        (const char *)v9,
        (int)pszFile[0]);
    }
    v7 = (const WCHAR *)pszFile;
    if ( si128.m128i_i64[1] > 7uLL )
      v7 = pszFile[0];
    IconW = SHCreateFileExtractIconW(v7, *(_DWORD *)&a2[6].mkid.cb, a3, a4);
    std::wstring::~wstring((char **)pszFile);
    if ( IconW < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x198,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
        (const char *)(unsigned int)IconW,
        (int)pszFile[0]);
  }
}

```

## disassembly

```asm
0x180008800  test    r9, r9
0x180008803  jz      locret_18000889E
0x180008809  push    rbx
0x18000880a  push    rsi
0x18000880b  push    rdi
0x18000880c  sub     rsp, 50h
0x180008810  mov     rax, cs:__security_cookie
0x180008817  xor     rax, rsp
0x18000881a  mov     [rsp+68h+var_28], rax
0x18000881f  mov     rdi, r9
0x180008822  mov     rsi, r8
0x180008825  mov     rbx, rdx
0x180008828  test    rdx, rdx
0x18000882b  jz      short loc_18000888A
0x18000882d  xorps   xmm0, xmm0
0x180008830  movups  xmmword ptr [rsp+68h+pszFile], xmm0
0x180008835  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000883d  movdqu  [rsp+68h+var_38], xmm1
0x180008843  xor     eax, eax
0x180008845  mov     word ptr [rsp+68h+pszFile], ax; int
0x18000884a  lea     r8, [rsp+68h+pszFile]
0x18000884f  call    ?GetFileFolderName@FileFolder@@IEAAXPEFBU_ITEMIDLIST@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FileFolder::GetFileFolderName(_ITEMIDLIST const *,std::wstring &)
0x180008854  cmp     word ptr [rbx], 32h ; '2'
0x180008858  jb      short loc_18000889F
0x18000885a  lea     rcx, [rsp+68h+pszFile]
0x18000885f  cmp     qword ptr [rsp+68h+var_38+8], 7
0x180008865  cmova   rcx, [rsp+68h+pszFile]; pszFile
0x18000886b  mov     r9, rdi; ppv
0x18000886e  mov     r8, rsi; riid
0x180008871  mov     edx, [rbx+12h]; dwFileAttributes
0x180008874  call    cs:__imp_SHCreateFileExtractIconW
0x18000887a  mov     ebx, eax
0x18000887c  lea     rcx, [rsp+68h+pszFile]
0x180008881  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008886  test    ebx, ebx
0x180008888  js      short loc_1800088C3
0x18000888a  mov     rcx, [rsp+68h+var_28]
0x18000888f  xor     rcx, rsp; StackCookie
0x180008892  call    __security_check_cookie
0x180008897  add     rsp, 50h
0x18000889b  pop     rdi
0x18000889c  pop     rsi
0x18000889d  pop     rbx
0x18000889e  retn
0x18000889f  mov     ecx, 80070057h
0x1800088a4  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800088a9  mov     r9d, eax; char *
0x1800088ac  mov     rcx, [rsp+68h]; this
0x1800088b1  lea     r8, aVmUxUiRemotefi_11; "vm\\ux\\ui\\remotefilebrowse\\Utility.h"
0x1800088b8  mov     edx, 118h; void *
0x1800088bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800088c3  mov     rcx, [rsp+68h]; this
0x1800088c8  mov     r9d, ebx; char *
0x1800088cb  lea     r8, aVmUxUiRemotefi_8; "vm\\ux\\ui\\remotefilebrowse\\filefolde"...
0x1800088d2  mov     edx, 198h; void *
0x1800088d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
