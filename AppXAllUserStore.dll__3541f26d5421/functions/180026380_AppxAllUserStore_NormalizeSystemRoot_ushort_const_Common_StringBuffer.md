# AppxAllUserStore::NormalizeSystemRoot(ushort const *,Common::StringBuffer &)

- ea: `0x180026380`
- end: `0x1800264d1`
- name: `?NormalizeSystemRoot@AppxAllUserStore@@YAJPEBGAEAVStringBuffer@Common@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(AppxAllUserStore *__hidden this, Common::StringBuffer *, struct Common::StringBuffer *)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180034de8`
- `0x18004252c`

## callees

- `0x180007a10`
- `0x180018248`
- `0x18001a464`
- `0x18001a6a0`
- `0x180026214`
- `0x1800262c8`
- `0x180026380`
- `0x18004c9d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800263e8`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800263e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026431`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026431`

## string_xrefs

- `0x180026405`: `onecore\admin\appmodel\appxalluserstore\src\commonutilities.cpp`
- `0x180026453`: `onecore\admin\appmodel\appxalluserstore\src\commonutilities.cpp`
- `0x1800264b4`: `onecore\admin\appmodel\appxalluserstore\src\commonutilities.cpp`
- `0x1800264a8`: `Path %ws.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::NormalizeSystemRoot(
        AppxAllUserStore *this,
        void **a2,
        struct Common::StringBuffer *a3)
{
  struct Common::StringBuffer *v5; // r8
  unsigned __int64 v6; // rax
  Common *v7; // rcx
  int HResultFromLastError; // eax
  unsigned int v9; // ebx
  int v11; // edi
  int bIgnoreCase; // [rsp+20h] [rbp-238h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  Common::GlobalHeap::Free(a2[1]);
  a2[1] = 0;
  *(_DWORD *)a2 = 0;
  *((_DWORD *)a2 + 4) = 0;
  if ( !this )
    return 0;
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)this + v6) );
  if ( v6 <= 3 )
  {
    if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    {
      HResultFromLastError = Common::GetHResultFromLastError(v7);
      v9 = HResultFromLastError;
      if ( HResultFromLastError < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\commonutilities.cpp",
          (const char *)(unsigned int)HResultFromLastError,
          bIgnoreCase);
      return v9;
    }
    if ( CompareStringOrdinal(Buffer, 1, (LPCWCH)this, 1, 1) == 2 )
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\commonutilities.cpp",
        0,
        (int)"Input %ws is the current OS.",
        (const char *)this);
      return 0;
    }
  }
  v11 = AppxAllUserStore::CopyWithNoTrailingBackslash(this, (Common::StringBuffer *)a2, v5);
  if ( v11 < 0 )
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\commonutilities.cpp",
      (const char *)(unsigned int)v11,
      (int)"Path %ws.",
      (const char *)this);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180026380  mov     [rsp+arg_10], rbx
0x180026385  mov     [rsp+arg_18], rsi
0x18002638a  push    rdi
0x18002638b  sub     rsp, 250h
0x180026392  mov     rax, cs:__security_cookie
0x180026399  xor     rax, rsp
0x18002639c  mov     [rsp+258h+var_18], rax
0x1800263a4  mov     rbx, rcx
0x1800263a7  mov     rdi, rdx
0x1800263aa  mov     rcx, [rdx+8]; void *
0x1800263ae  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800263b3  xor     esi, esi
0x1800263b5  mov     [rdi+8], rsi
0x1800263b9  mov     [rdi], esi
0x1800263bb  mov     [rdi+10h], esi
0x1800263be  test    rbx, rbx
0x1800263c1  jz      loc_180026468
0x1800263c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800263cb  inc     rax
0x1800263ce  cmp     [rbx+rax*2], si
0x1800263d2  jnz     short loc_1800263CB
0x1800263d4  cmp     rax, 3
0x1800263d8  ja      loc_18002648F
0x1800263de  mov     edx, 104h; uSize
0x1800263e3  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x1800263e8  call    cs:__imp_GetWindowsDirectoryW
0x1800263ee  test    eax, eax
0x1800263f0  jnz     short loc_18002641D
0x1800263f2  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x1800263f7  mov     ebx, eax
0x1800263f9  test    eax, eax
0x1800263fb  jns     short loc_180026419
0x1800263fd  mov     rcx, [rsp+258h]; this
0x180026405  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\appxalluserst"...
0x18002640c  mov     r9d, eax; char *
0x18002640f  mov     edx, 4Bh ; 'K'; void *
0x180026414  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026419  mov     eax, ebx
0x18002641b  jmp     short loc_18002646A
0x18002641d  mov     edx, 1; cchCount1
0x180026422  lea     rcx, [rsp+258h+Buffer]; lpString1
0x180026427  mov     r9d, edx; cchCount2
0x18002642a  mov     [rsp+258h+bIgnoreCase], edx; bIgnoreCase
0x18002642e  mov     r8, rbx; lpString2
0x180026431  call    cs:__imp_CompareStringOrdinal
0x180026437  cmp     eax, 2
0x18002643a  jnz     short loc_18002648F
0x18002643c  mov     rcx, [rsp+258h]; this
0x180026444  lea     rax, aInputWsIsTheCu; "Input %ws is the current OS."
0x18002644b  xor     r9d, r9d; char *
0x18002644e  mov     [rsp+258h+var_230], rbx; char *
0x180026453  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\appxalluserst"...
0x18002645a  mov     qword ptr [rsp+258h+bIgnoreCase], rax; int
0x18002645f  lea     edx, [r9+50h]; void *
0x180026463  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180026468  xor     eax, eax
0x18002646a  mov     rcx, [rsp+258h+var_18]
0x180026472  xor     rcx, rsp; StackCookie
0x180026475  call    __security_check_cookie
0x18002647a  lea     r11, [rsp+258h+var_8]
0x180026482  mov     rbx, [r11+20h]
0x180026486  mov     rsi, [r11+28h]
0x18002648a  mov     rsp, r11
0x18002648d  pop     rdi
0x18002648e  retn
0x18002648f  mov     rdx, rdi; Common::StringBuffer *
0x180026492  mov     rcx, rbx; this
0x180026495  call    ?CopyWithNoTrailingBackslash@AppxAllUserStore@@YAJPEBGAEAVStringBuffer@Common@@@Z; AppxAllUserStore::CopyWithNoTrailingBackslash(ushort const *,Common::StringBuffer &)
0x18002649a  mov     edi, eax
0x18002649c  test    eax, eax
0x18002649e  jns     short loc_1800264CD
0x1800264a0  mov     rcx, [rsp+258h]; this
0x1800264a8  lea     rax, aPathWs; "Path %ws."
0x1800264af  mov     [rsp+258h+var_230], rbx; char *
0x1800264b4  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800264bb  mov     r9d, edi; char *
0x1800264be  mov     qword ptr [rsp+258h+bIgnoreCase], rax; int
0x1800264c3  mov     edx, 56h ; 'V'; void *
0x1800264c8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800264cd  mov     eax, edi
0x1800264cf  jmp     short loc_18002646A
```
