# CCbsIdentity::SaveAsStringId(wchar_t * *)

- ea: `0x1400259e0`
- end: `0x140025b97`
- name: `?SaveAsStringId@CCbsIdentity@@UEAAJPEAPEA_W@Z`
- size: `439`
- prototype: `__int64 __fastcall(CCbsIdentity *__hidden this, wchar_t **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x14000ee94`
- `0x140016a40`
- `0x140016fb4`
- `0x14001cfc4`
- `0x14001d404`
- `0x14001ddb8`
- `0x1400259e0`

## string_xrefs

- `0x140025aab`: `onecore\base\cbs\identityutil\cbsidentity.cpp`

## pseudocode

```c
__int64 __fastcall CCbsIdentity::SaveAsStringId(CCbsIdentity *this, wchar_t **a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rdx
  int v8; // eax
  int v10; // [rsp+20h] [rbp-68h]
  __int64 v11; // [rsp+60h] [rbp-28h] BYREF
  int *v12; // [rsp+68h] [rbp-20h] BYREF
  int v13; // [rsp+70h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v11 = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
    v13 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid argument: pszIdentity");
      v12 = &v13;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)&v12);
    }
    v6 = 2147500035LL;
    v7 = 286;
    goto LABEL_10;
  }
  if ( !*((_DWORD *)this + 6) )
  {
    v8 = SczAllocFromSz(&v11, &qword_1400353C0);
    v4 = v8;
    if ( v8 < 0 )
    {
      v7 = 313;
      goto LABEL_9;
    }
    goto LABEL_15;
  }
  if ( !*((_DWORD *)this + 194) )
  {
    v10 = (_DWORD)this + 550;
    v8 = SczAllocFormatted(&v11, L"%s%c%s%c%s%c%s%c%s", (char *)this + 30);
    v4 = v8;
    if ( v8 < 0 )
    {
      v7 = 308;
      goto LABEL_9;
    }
LABEL_15:
    v8 = SczPublicAllocFromSz(a2, *((_QWORD *)this + 2), v11);
    v4 = v8;
    if ( v8 >= 0 )
    {
      v4 = 0;
      goto LABEL_18;
    }
    v7 = 316;
    goto LABEL_9;
  }
  v8 = SczAllocFromSz(&v11, (char *)this + 30);
  v4 = v8;
  if ( v8 >= 0 )
    goto LABEL_15;
  v7 = 292;
LABEL_9:
  v6 = (unsigned int)v8;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentity.cpp",
    (const char *)v6,
    v10);
LABEL_18:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v11);
  return v4;
}

```

## disassembly

```asm
0x1400259e0  mov     [rsp+arg_10], rbx
0x1400259e5  mov     [rsp+arg_18], rsi
0x1400259ea  push    rdi
0x1400259eb  sub     rsp, 80h
0x1400259f2  mov     rax, cs:__security_cookie
0x1400259f9  xor     rax, rsp
0x1400259fc  mov     [rsp+88h+var_10], rax
0x140025a01  mov     [rsp+88h+var_28], 0
0x140025a0a  mov     rsi, rdx
0x140025a0d  mov     rdi, rcx
0x140025a10  test    rdx, rdx
0x140025a13  jnz     short loc_140025A70
0x140025a15  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025a1c  mov     ebx, 80004003h
0x140025a21  mov     [rsp+88h+var_18], ebx
0x140025a25  test    rcx, rcx
0x140025a28  jz      short loc_140025A66
0x140025a2a  lea     edi, [rdx+3]
0x140025a2d  mov     r8d, edi
0x140025a30  lea     r9, aInvalidArgumen_15; "Invalid argument: pszIdentity"
0x140025a37  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140025a3c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025a43  lea     rax, [rsp+88h+var_18]
0x140025a48  mov     [rsp+88h+var_20], rax
0x140025a4d  lea     r9, asc_1400353E8; ": {}"
0x140025a54  lea     rax, [rsp+88h+var_20]
0x140025a59  mov     r8d, edi
0x140025a5c  mov     [rsp+88h+var_68], rax
0x140025a61  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140025a66  mov     r9d, ebx
0x140025a69  mov     edx, 11Eh
0x140025a6e  jmp     short loc_140025AA3
0x140025a70  cmp     dword ptr [rcx+18h], 0
0x140025a74  jz      loc_140025B25
0x140025a7a  cmp     dword ptr [rcx+308h], 0
0x140025a81  jz      short loc_140025ABC
0x140025a83  lea     rdx, [rcx+1Eh]
0x140025a87  lea     rcx, [rsp+88h+var_28]
0x140025a8c  call    SczAllocFromSz
0x140025a91  mov     ebx, eax
0x140025a93  test    eax, eax
0x140025a95  jns     loc_140025B46
0x140025a9b  mov     edx, 124h; void *
0x140025aa0  mov     r9d, eax; char *
0x140025aa3  mov     rcx, [rsp+88h]; this
0x140025aab  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x140025ab2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025ab7  jmp     loc_140025B69
0x140025abc  movzx   r9d, word ptr [rcx+1Ch]
0x140025ac1  lea     rax, [rcx+2C8h]
0x140025ac8  mov     [rsp+88h+var_38], rax
0x140025acd  lea     rdx, [rdi+288h]
0x140025ad4  mov     [rsp+88h+var_40], r9d
0x140025ad9  lea     r8, [rdi+226h]
0x140025ae0  add     rcx, 248h
0x140025ae7  mov     [rsp+88h+var_48], rcx
0x140025aec  lea     rcx, [rsp+88h+var_28]
0x140025af1  mov     [rsp+88h+var_50], r9d
0x140025af6  mov     [rsp+88h+var_58], rdx
0x140025afb  lea     rdx, aSCSCSCSCS; "%s%c%s%c%s%c%s%c%s"
0x140025b02  mov     [rsp+88h+var_60], r9d
0x140025b07  mov     [rsp+88h+var_68], r8
0x140025b0c  lea     r8, [rdi+1Eh]
0x140025b10  call    SczAllocFormatted
0x140025b15  mov     ebx, eax
0x140025b17  test    eax, eax
0x140025b19  jns     short loc_140025B46
0x140025b1b  mov     edx, 134h
0x140025b20  jmp     loc_140025AA0
0x140025b25  lea     rdx, qword_1400353C0
0x140025b2c  lea     rcx, [rsp+88h+var_28]
0x140025b31  call    SczAllocFromSz
0x140025b36  mov     ebx, eax
0x140025b38  test    eax, eax
0x140025b3a  jns     short loc_140025B46
0x140025b3c  mov     edx, 139h
0x140025b41  jmp     loc_140025AA0
0x140025b46  mov     r8, [rsp+88h+var_28]
0x140025b4b  mov     rcx, rsi
0x140025b4e  mov     rdx, [rdi+10h]
0x140025b52  call    SczPublicAllocFromSz
0x140025b57  mov     ebx, eax
0x140025b59  test    eax, eax
0x140025b5b  jns     short loc_140025B67
0x140025b5d  mov     edx, 13Ch
0x140025b62  jmp     loc_140025AA0
0x140025b67  xor     ebx, ebx
0x140025b69  lea     rcx, [rsp+88h+var_28]
0x140025b6e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140025b73  mov     eax, ebx
0x140025b75  mov     rcx, [rsp+88h+var_10]
0x140025b7a  xor     rcx, rsp; StackCookie
0x140025b7d  call    __security_check_cookie
0x140025b82  lea     r11, [rsp+88h+var_8]
0x140025b8a  mov     rbx, [r11+20h]
0x140025b8e  mov     rsi, [r11+28h]
0x140025b92  mov     rsp, r11
0x140025b95  pop     rdi
0x140025b96  retn
```
