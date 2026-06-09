# AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)

- ea: `0x180017cd0`
- end: `0x180017f0f`
- name: `?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ`
- size: `575`
- prototype: `__int64(AppxAllUserStore::BasicLogFile *__hidden this, const unsigned __int16 *, ...)`
- caller_count: `46`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180016138`
- `0x180016878`
- `0x180016ba8`
- `0x180016d5c`
- `0x180016e70`
- `0x180016f78`
- `0x180017198`
- `0x180017330`
- `0x1800175c4`
- `0x1800178e8`
- `0x180019880`
- `0x180030964`
- `0x180030d98`
- `0x180030e4c`
- `0x180031c80`
- `0x180032248`
- `0x1800334f4`
- `0x180033908`
- `0x180033bb4`
- `0x180033dcc`
- `0x180034214`
- `0x180034de8`
- `0x180035140`
- `0x1800357a0`
- `0x180035bc8`
- `0x1800408f4`
- `0x1800409a0`
- `0x180040af4`
- `0x180040ba8`
- `0x180041198`
- `0x1800414c8`
- `0x1800417fc`
- `0x180041a94`
- `0x1800421f4`
- `0x18004252c`
- `0x180043130`
- `0x1800432ac`
- `0x1800434c8`
- `0x180043740`
- `0x180043b10`
- `0x18004445c`
- `0x180044624`
- `0x1800447c8`
- `0x180044ca0`
- `0x180044e34`
- `0x180045120`

## callees

- `0x180004920`
- `0x18000ae80`
- `0x18000ecdc`
- `0x18000ed34`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x18001a6a0`
- `0x180032eb4`
- `0x180036740`
- `0x18004c98a`
- `0x18004c9d0`

## string_xrefs

- `0x180017d19`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x180017d73`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x180017dde`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x180017e46`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x180017e83`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x180017ec1`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`

## pseudocode

```c
__int64 AppxAllUserStore::BasicLogFile::WriteMsg(AppxAllUserStore::BasicLogFile *this, const unsigned __int16 *a2, ...)
{
  __int64 v3; // rdx
  unsigned int v4; // edi
  int DateTimeString; // eax
  const char *v6; // r14
  size_t *v7; // r8
  unsigned int v8; // eax
  int argList; // [rsp+28h] [rbp-E0h]
  int argLista; // [rsp+28h] [rbp-E0h]
  __int128 v12; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+58h] [rbp-B0h]
  __int64 v14; // [rsp+60h] [rbp-A8h]
  wchar_t pszFormat[264]; // [rsp+68h] [rbp-A0h] BYREF
  wchar_t pszDest[520]; // [rsp+278h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6C0h] [rbp+5B8h]
  va_list va; // [rsp+6D8h] [rbp+5D0h] BYREF

  va_start(va, a2);
  if ( !a2 )
  {
    v3 = 170;
LABEL_3:
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
      (const char *)0x80070057LL,
      argList);
    return v4;
  }
  if ( *((_QWORD *)this + 3) == -1 )
  {
    v3 = 171;
    goto LABEL_3;
  }
  v14 = 0;
  LODWORD(v13) = 0;
  v12 = 0;
  DateTimeString = AppxAllUserStore::BasicLogFile::GetDateTimeString(this, (struct Common::StringBuffer *)&v12);
  if ( DateTimeString < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB1,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
      (const char *)(unsigned int)DateTimeString);
  memset_0(pszFormat, 0, 0x208u);
  v6 = (const char *)*((_QWORD *)&v12 + 1);
  v4 = StringCchPrintfW(pszFormat, 0x104u, L"%ls %ls\r\n", *((_QWORD *)&v12 + 1), a2);
  if ( (v4 & 0x80000000) == 0 )
  {
    memset_0(pszDest, 0, sizeof(pszDest));
    v8 = StringVPrintfWorkerW(pszDest, 0x208u, v7, pszFormat, va);
    v4 = wil::details::in1diag3::Log_IfFailedMsg(
           retaddr,
           (void *)0xB9,
           (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
           (const char *)v8,
           (__int64)"Format string %ls.",
           (const char *)pszFormat);
    if ( (int)(v4 + 0x80000000) < 0 || v4 == -2147024774 )
    {
      v4 = AppxAllUserStore::BasicLogFile::WriteLine(this, pszDest);
      if ( (v4 & 0x80000000) == 0 )
        v4 = 0;
      else
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xBD,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
          (const char *)v4,
          (int)"Msg %ls",
          (const char *)pszDest);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBC,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
        (const char *)v4,
        argLista);
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
      (const char *)v4,
      (int)"Date %ls formatString %ls.",
      v6,
      a2);
  }
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v12);
  return v4;
}

```

## disassembly

```asm
0x180017cd0  mov     rax, rsp
0x180017cd3  mov     [rax+10h], rdx
0x180017cd7  mov     [rax+18h], r8
0x180017cdb  mov     [rax+20h], r9
0x180017cdf  push    rbp
0x180017ce0  push    rsi
0x180017ce1  push    rdi
0x180017ce2  push    r12
0x180017ce4  push    r14
0x180017ce6  lea     rbp, [rax-5B8h]
0x180017ced  sub     rsp, 690h
0x180017cf4  mov     rax, cs:__security_cookie
0x180017cfb  xor     rax, rsp
0x180017cfe  mov     [rbp+5B0h+var_30], rax
0x180017d05  mov     rsi, rcx
0x180017d08  test    rdx, rdx
0x180017d0b  jnz     short loc_180017D32
0x180017d0d  mov     edx, 0AAh; void *
0x180017d12  mov     rcx, [rbp+5B8h]; this
0x180017d19  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180017d20  mov     edi, 80070057h
0x180017d25  mov     r9d, edi; char *
0x180017d28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d2d  jmp     loc_180017EEF
0x180017d32  cmp     qword ptr [rcx+18h], 0FFFFFFFFFFFFFFFFh
0x180017d37  jnz     short loc_180017D40
0x180017d39  mov     edx, 0ABh
0x180017d3e  jmp     short loc_180017D12
0x180017d40  xor     eax, eax
0x180017d42  mov     [rsp+6B0h+var_658], 0
0x180017d4b  xorps   xmm0, xmm0
0x180017d4e  mov     dword ptr [rsp+6B0h+var_660], eax
0x180017d52  lea     rdx, [rsp+6B0h+var_678+8]; struct Common::StringBuffer *
0x180017d57  movups  [rsp+6B0h+var_678+8], xmm0
0x180017d5c  lea     r12, [rbp+5B0h+arg_10]
0x180017d63  call    ?GetDateTimeString@BasicLogFile@AppxAllUserStore@@AEAAJAEAVStringBuffer@Common@@@Z; AppxAllUserStore::BasicLogFile::GetDateTimeString(Common::StringBuffer &)
0x180017d68  test    eax, eax
0x180017d6a  jns     short loc_180017D87
0x180017d6c  mov     rcx, [rbp+5B8h]; this
0x180017d73  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180017d7a  mov     r9d, eax; char *
0x180017d7d  mov     edx, 0B1h; void *
0x180017d82  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017d87  xor     edx, edx; Val
0x180017d89  lea     rcx, [rsp+6B0h+pszFormat]; void *
0x180017d8e  mov     r8d, 208h; Size
0x180017d94  call    memset_0
0x180017d99  mov     rax, [rbp+5B0h+arg_8]
0x180017da0  lea     r8, aLsLs; "%ls %ls\r\n"
0x180017da7  mov     r14, [rsp+6B0h+var_668]
0x180017dac  lea     rcx, [rsp+6B0h+pszFormat]; unsigned __int16 *
0x180017db1  mov     r9, r14
0x180017db4  mov     [rsp+6B0h+argList], rax
0x180017db9  mov     edx, 104h; unsigned __int64
0x180017dbe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017dc3  mov     edi, eax
0x180017dc5  test    eax, eax
0x180017dc7  jns     short loc_180017E06
0x180017dc9  mov     rdx, [rbp+5B0h+arg_8]
0x180017dd0  lea     rax, aDateLsFormatst; "Date %ls formatString %ls."
0x180017dd7  mov     rcx, [rbp+5B8h]; this
0x180017dde  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180017de5  mov     [rsp+30h], rdx
0x180017dea  mov     r9d, edi; char *
0x180017ded  mov     [rsp+6B0h+var_688], r14; char *
0x180017df2  mov     edx, 0B5h; void *
0x180017df7  mov     [rsp+6B0h+argList], rax; int
0x180017dfc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017e01  jmp     loc_180017EE5
0x180017e06  xor     edx, edx; Val
0x180017e08  lea     rcx, [rbp+5B0h+pszDest]; void *
0x180017e0f  mov     r8d, 410h; Size
0x180017e15  call    memset_0
0x180017e1a  lea     r9, [rsp+6B0h+pszFormat]; pszFormat
0x180017e1f  mov     [rsp+6B0h+argList], r12; argList
0x180017e24  mov     edx, 208h; cchDest
0x180017e29  lea     rcx, [rbp+5B0h+pszDest]; pszDest
0x180017e30  call    StringVPrintfWorkerW
0x180017e35  mov     rcx, [rbp+5B8h]; this
0x180017e3c  lea     rdx, [rsp+6B0h+pszFormat]
0x180017e41  mov     [rsp+6B0h+var_688], rdx; char *
0x180017e46  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180017e4d  lea     rdx, aFormatStringLs; "Format string %ls."
0x180017e54  mov     r9d, eax; char *
0x180017e57  mov     [rsp+6B0h+argList], rdx; int
0x180017e5c  mov     edx, 0B9h; void *
0x180017e61  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180017e66  mov     edi, eax
0x180017e68  mov     eax, 80000000h
0x180017e6d  lea     ecx, [rdi+rax]
0x180017e70  test    eax, ecx
0x180017e72  jnz     short loc_180017E99
0x180017e74  cmp     edi, 8007007Ah
0x180017e7a  jz      short loc_180017E99
0x180017e7c  mov     rcx, [rbp+5B8h]; this
0x180017e83  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180017e8a  mov     r9d, edi; char *
0x180017e8d  mov     edx, 0BCh; void *
0x180017e92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017e97  jmp     short loc_180017EE5
0x180017e99  lea     rdx, [rbp+5B0h+pszDest]; unsigned __int16 *
0x180017ea0  mov     rcx, rsi; this
0x180017ea3  call    ?WriteLine@BasicLogFile@AppxAllUserStore@@AEAAJPEBG@Z; AppxAllUserStore::BasicLogFile::WriteLine(ushort const *)
0x180017ea8  mov     edi, eax
0x180017eaa  test    eax, eax
0x180017eac  jns     short loc_180017EE3
0x180017eae  mov     rcx, [rbp+5B8h]; this
0x180017eb5  lea     rax, [rbp+5B0h+pszDest]
0x180017ebc  mov     [rsp+6B0h+var_688], rax; char *
0x180017ec1  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180017ec8  lea     rax, aMsgLs; "Msg %ls"
0x180017ecf  mov     r9d, edi; char *
0x180017ed2  mov     edx, 0BDh; void *
0x180017ed7  mov     [rsp+6B0h+argList], rax; int
0x180017edc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017ee1  jmp     short loc_180017EE5
0x180017ee3  xor     edi, edi
0x180017ee5  lea     rcx, [rsp+6B0h+var_678+8]; this
0x180017eea  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180017eef  mov     eax, edi
0x180017ef1  mov     rcx, [rbp+5B0h+var_30]
0x180017ef8  xor     rcx, rsp; StackCookie
0x180017efb  call    __security_check_cookie
0x180017f00  add     rsp, 690h
0x180017f07  pop     r14
0x180017f09  pop     r12
0x180017f0b  pop     rdi
0x180017f0c  pop     rsi
0x180017f0d  pop     rbp
0x180017f0e  retn
```
