# CCbsIdentity::GetStringId(wchar_t * *)

- ea: `0x140024980`
- end: `0x140024b08`
- name: `?GetStringId@CCbsIdentity@@UEBAJPEAPEA_W@Z`
- size: `392`
- prototype: `__int64 __fastcall(CCbsIdentity *__hidden this, wchar_t **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x14001cfc4`
- `0x14001d404`
- `0x140024980`

## string_xrefs

- `0x1400249fb`: `onecore\base\cbs\identityutil\cbsidentity.cpp`
- `0x140024a55`: `onecore\base\cbs\identityutil\cbsidentity.cpp`

## pseudocode

```c
__int64 __fastcall CCbsIdentity::GetStringId(CCbsIdentity *this, wchar_t **a2)
{
  __int64 v2; // rdx
  int v4; // ebx
  __int64 v5; // rdx
  int v6; // [rsp+20h] [rbp-68h]
  int v7[2]; // [rsp+60h] [rbp-28h] BYREF
  int v8; // [rsp+68h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( a2 )
  {
    if ( *((_DWORD *)this + 6) )
    {
      if ( *((_DWORD *)this + 194) )
      {
        v4 = SczAllocFromSz(a2, (char *)this + 30);
        if ( v4 < 0 )
        {
          v5 = 329;
LABEL_9:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v5,
            (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentity.cpp",
            (const char *)(unsigned int)v4,
            v6);
          return (unsigned int)v4;
        }
      }
      else
      {
        v6 = (_DWORD)this + 550;
        v4 = SczAllocFormatted(a2, L"%s%c%s%c%s%c%s%c%s", (char *)this + 30);
        if ( v4 < 0 )
        {
          v5 = 345;
          goto LABEL_9;
        }
      }
    }
    else
    {
      v4 = SczAllocFromSz(a2, &qword_1400353C0);
      if ( v4 < 0 )
      {
        v5 = 350;
        goto LABEL_9;
      }
    }
    return 0;
  }
  v8 = -2147467261;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string id result specified");
    *(_QWORD *)v7 = &v8;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v2,
      3,
      (__int64)": {}",
      (__int64)v7);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x143,
    (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentity.cpp",
    (const char *)0x80004003LL,
    v6);
  return 2147500035LL;
}

```

## disassembly

```asm
0x140024980  push    rbx
0x140024982  sub     rsp, 80h
0x140024989  mov     rax, cs:__security_cookie
0x140024990  xor     rax, rsp
0x140024993  mov     [rsp+88h+var_18], rax
0x140024998  mov     r10, rdx
0x14002499b  mov     r8, rcx
0x14002499e  test    rdx, rdx
0x1400249a1  jnz     short loc_140024A1C
0x1400249a3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400249aa  mov     [rsp+88h+var_20], 80004003h
0x1400249b2  test    rcx, rcx
0x1400249b5  jz      short loc_1400249F3
0x1400249b7  lea     ebx, [rdx+3]
0x1400249ba  mov     r8d, ebx
0x1400249bd  lea     r9, aNoStringIdResu; "No string id result specified"
0x1400249c4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400249c9  lea     rcx, [rsp+88h+var_28]
0x1400249ce  mov     r8d, ebx
0x1400249d1  mov     qword ptr [rsp+88h+var_68], rcx; int
0x1400249d6  lea     rax, [rsp+88h+var_20]
0x1400249db  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400249e2  lea     r9, asc_1400353E8; ": {}"
0x1400249e9  mov     qword ptr [rsp+88h+var_28], rax
0x1400249ee  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400249f3  mov     rcx, [rsp+88h]; this
0x1400249fb  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x140024a02  mov     r9d, 80004003h; char *
0x140024a08  mov     edx, 143h; void *
0x140024a0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024a12  mov     eax, 80004003h
0x140024a17  jmp     loc_140024AF2
0x140024a1c  cmp     dword ptr [rcx+18h], 0
0x140024a20  jz      loc_140024AD1
0x140024a26  cmp     dword ptr [rcx+308h], 0
0x140024a2d  lea     r11, [rcx+1Eh]
0x140024a31  jz      short loc_140024A6B
0x140024a33  mov     rdx, r11
0x140024a36  mov     rcx, r10
0x140024a39  call    SczAllocFromSz
0x140024a3e  mov     ebx, eax
0x140024a40  test    eax, eax
0x140024a42  jns     loc_140024AF0
0x140024a48  mov     edx, 149h; void *
0x140024a4d  mov     rcx, [rsp+88h]; this
0x140024a55  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x140024a5c  mov     r9d, ebx; char *
0x140024a5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024a64  mov     eax, ebx
0x140024a66  jmp     loc_140024AF2
0x140024a6b  movzx   r9d, word ptr [rcx+1Ch]
0x140024a70  lea     rdx, [r8+288h]
0x140024a77  lea     rax, [rcx+2C8h]
0x140024a7e  add     r8, 226h
0x140024a85  mov     [rsp+88h+var_38], rax
0x140024a8a  add     rcx, 248h
0x140024a91  mov     [rsp+88h+var_40], r9d
0x140024a96  mov     [rsp+88h+var_48], rcx
0x140024a9b  mov     rcx, r10
0x140024a9e  mov     [rsp+88h+var_50], r9d
0x140024aa3  mov     [rsp+88h+var_58], rdx
0x140024aa8  lea     rdx, aSCSCSCSCS; "%s%c%s%c%s%c%s%c%s"
0x140024aaf  mov     [rsp+88h+var_60], r9d
0x140024ab4  mov     qword ptr [rsp+88h+var_68], r8
0x140024ab9  mov     r8, r11
0x140024abc  call    SczAllocFormatted
0x140024ac1  mov     ebx, eax
0x140024ac3  test    eax, eax
0x140024ac5  jns     short loc_140024AF0
0x140024ac7  mov     edx, 159h
0x140024acc  jmp     loc_140024A4D
0x140024ad1  lea     rdx, qword_1400353C0
0x140024ad8  mov     rcx, r10
0x140024adb  call    SczAllocFromSz
0x140024ae0  mov     ebx, eax
0x140024ae2  test    eax, eax
0x140024ae4  jns     short loc_140024AF0
0x140024ae6  mov     edx, 15Eh
0x140024aeb  jmp     loc_140024A4D
0x140024af0  xor     eax, eax
0x140024af2  mov     rcx, [rsp+88h+var_18]
0x140024af7  xor     rcx, rsp; StackCookie
0x140024afa  call    __security_check_cookie
0x140024aff  add     rsp, 80h
0x140024b06  pop     rbx
0x140024b07  retn
```
