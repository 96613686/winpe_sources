# Windows::Networking::UX::CEthernetAuthConfig::Equals(Windows::Networking::UX::IEthernetAuthConfig *,uchar *)

- ea: `0x18000d6e0`
- end: `0x18000d896`
- name: `?Equals@CEthernetAuthConfig@UX@Networking@Windows@@UEAAJPEAUIEthernetAuthConfig@234@PEAE@Z`
- size: `438`
- prototype: `int(Windows::Networking::UX::CEthernetAuthConfig *__hidden this, struct Windows::Networking::UX::IEthernetAuthConfig *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a70c`
- `0x18000d6e0`
- `0x18000e768`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d70f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d76a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d7ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d86f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d883`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d70f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d76a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d7ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d86f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d883`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d7dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d81a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d7dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d81a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18000d84b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18000d84b`

## string_xrefs

- `0x18000d73b`: `onecoreuap\net\ux\uxmanager\lib\cethernetauthconfig.cpp`
- `0x18000d794`: `onecoreuap\net\ux\uxmanager\lib\cethernetauthconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Networking::UX::CEthernetAuthConfig::Equals(
        Windows::Networking::UX::CEthernetAuthConfig *this,
        struct Windows::Networking::UX::IEthernetAuthConfig *a2,
        bool *a3)
{
  __int64 (__fastcall *v6)(Windows::Networking::UX::CEthernetAuthConfig *, _QWORD, HSTRING *); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  HSTRING v9; // rcx
  __int64 (__fastcall *v10)(struct Windows::Networking::UX::IEthernetAuthConfig *, _QWORD, HSTRING *); // rbx
  HRESULT v11; // eax
  __int64 v12; // rdx
  PVOID *v13; // rax
  PCWSTR StringRawBuffer; // rax
  PCWSTR v15; // rax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  INT32 result; // [rsp+50h] [rbp+30h] BYREF
  HSTRING string; // [rsp+60h] [rbp+40h] BYREF
  HSTRING string1; // [rsp+68h] [rbp+48h] BYREF

  *a3 = 0;
  string1 = 0;
  v6 = *(__int64 (__fastcall **)(Windows::Networking::UX::CEthernetAuthConfig *, _QWORD, HSTRING *))(*(_QWORD *)this + 160LL);
  WindowsDeleteString(0);
  string1 = 0;
  v7 = v6(this, 0, &string1);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = 0;
    string = 0;
    if ( a2 )
    {
      v10 = *(__int64 (__fastcall **)(struct Windows::Networking::UX::IEthernetAuthConfig *, _QWORD, HSTRING *))(*(_QWORD *)a2 + 160LL);
      WindowsDeleteString(0);
      string = 0;
      v11 = v10(a2, 0, &string);
      v8 = v11;
      if ( v11 < 0 )
      {
        v12 = 215;
LABEL_6:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cethernetauthconfig.cpp",
          (const char *)(unsigned int)v11,
          savedregs);
        WindowsDeleteString(string);
LABEL_17:
        string = 0;
        goto LABEL_18;
      }
      result = 0;
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string1, 0);
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            WPP_aa47c98b7bdc3b6080119ff2f27e99a7_Traceguids,
            StringRawBuffer);
          v13 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
        {
          v15 = WindowsGetStringRawBuffer(string, 0);
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_aa47c98b7bdc3b6080119ff2f27e99a7_Traceguids, v15);
        }
      }
      v11 = WindowsCompareStringOrdinal(string1, string, &result);
      v8 = v11;
      if ( v11 < 0 )
      {
        v12 = 220;
        goto LABEL_6;
      }
      *a3 = result == 0;
      v9 = string;
    }
    WindowsDeleteString(v9);
    v8 = 0;
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD2,
    (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cethernetauthconfig.cpp",
    (const char *)(unsigned int)v7,
    savedregs);
LABEL_18:
  WindowsDeleteString(string1);
  return v8;
}

```

## disassembly

```asm
0x18000d6e0  push    rbp
0x18000d6e2  push    rbx
0x18000d6e3  push    rsi
0x18000d6e4  push    rdi
0x18000d6e5  push    r14; int
0x18000d6e7  mov     rbp, rsp
0x18000d6ea  sub     rsp, 20h
0x18000d6ee  mov     r14, r8
0x18000d6f1  mov     rsi, rdx
0x18000d6f4  mov     rdi, rcx
0x18000d6f7  mov     byte ptr [r8], 0
0x18000d6fb  mov     [rbp+string1], 0
0x18000d703  mov     rax, [rcx]
0x18000d706  mov     rbx, [rax+0A0h]
0x18000d70d  xor     ecx, ecx; string
0x18000d70f  call    cs:__imp_WindowsDeleteString
0x18000d715  mov     [rbp+string1], 0
0x18000d71d  lea     r8, [rbp+string1]
0x18000d721  xor     edx, edx
0x18000d723  mov     rcx, rdi
0x18000d726  mov     rax, rbx
0x18000d729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d72e  mov     ebx, eax
0x18000d730  test    eax, eax
0x18000d732  jns     short loc_18000D751
0x18000d734  mov     rcx, [rbp+28h]; this
0x18000d738  mov     r9d, eax; char *
0x18000d73b  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\uxmanager\\lib\\ce"...
0x18000d742  mov     edx, 0D2h; void *
0x18000d747  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d74c  jmp     loc_18000D87F
0x18000d751  xor     ecx, ecx; string
0x18000d753  mov     [rbp+string], rcx
0x18000d757  test    rsi, rsi
0x18000d75a  jz      loc_18000D86F
0x18000d760  mov     rax, [rsi]
0x18000d763  mov     rbx, [rax+0A0h]
0x18000d76a  call    cs:__imp_WindowsDeleteString
0x18000d770  mov     [rbp+string], 0
0x18000d778  lea     r8, [rbp+string]
0x18000d77c  xor     edx, edx
0x18000d77e  mov     rcx, rsi
0x18000d781  mov     rax, rbx
0x18000d784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d789  mov     ebx, eax
0x18000d78b  test    eax, eax
0x18000d78d  jns     short loc_18000D7B7
0x18000d78f  mov     edx, 0D7h; void *
0x18000d794  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\uxmanager\\lib\\ce"...
0x18000d79b  mov     r9d, eax; char *
0x18000d79e  mov     rcx, [rbp+28h]; this
0x18000d7a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d7a7  nop
0x18000d7a8  mov     rcx, [rbp+string]; string
0x18000d7ac  call    cs:__imp_WindowsDeleteString
0x18000d7b2  jmp     loc_18000D877
0x18000d7b7  mov     [rbp+result], 0
0x18000d7be  lea     rbx, WPP_GLOBAL_Control
0x18000d7c5  mov     rax, cs:WPP_GLOBAL_Control
0x18000d7cc  cmp     rax, rbx
0x18000d7cf  jz      short loc_18000D83F
0x18000d7d1  test    byte ptr [rax+1Ch], 8
0x18000d7d5  jz      short loc_18000D809
0x18000d7d7  xor     edx, edx; length
0x18000d7d9  mov     rcx, [rbp+string1]; string
0x18000d7dd  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d7e3  mov     edx, 0Ah
0x18000d7e8  mov     r9, rax
0x18000d7eb  lea     r8, WPP_aa47c98b7bdc3b6080119ff2f27e99a7_Traceguids
0x18000d7f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7f9  mov     rcx, [rcx+10h]
0x18000d7fd  call    WPP_SF_S
0x18000d802  mov     rax, cs:WPP_GLOBAL_Control
0x18000d809  cmp     rax, rbx
0x18000d80c  jz      short loc_18000D83F
0x18000d80e  test    byte ptr [rax+1Ch], 8
0x18000d812  jz      short loc_18000D83F
0x18000d814  xor     edx, edx; length
0x18000d816  mov     rcx, [rbp+string]; string
0x18000d81a  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d820  mov     edx, 0Bh
0x18000d825  mov     r9, rax
0x18000d828  lea     r8, WPP_aa47c98b7bdc3b6080119ff2f27e99a7_Traceguids
0x18000d82f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d836  mov     rcx, [rcx+10h]
0x18000d83a  call    WPP_SF_S
0x18000d83f  lea     r8, [rbp+result]; result
0x18000d843  mov     rdx, [rbp+string]; string2
0x18000d847  mov     rcx, [rbp+string1]; string1
0x18000d84b  call    cs:__imp_WindowsCompareStringOrdinal
0x18000d851  mov     ebx, eax
0x18000d853  test    eax, eax
0x18000d855  jns     short loc_18000D861
0x18000d857  mov     edx, 0DCh
0x18000d85c  jmp     loc_18000D794
0x18000d861  cmp     [rbp+result], 0
0x18000d865  setz    al
0x18000d868  mov     [r14], al
0x18000d86b  mov     rcx, [rbp+string]; string
0x18000d86f  call    cs:__imp_WindowsDeleteString
0x18000d875  xor     ebx, ebx
0x18000d877  mov     [rbp+string], 0
0x18000d87f  mov     rcx, [rbp+string1]; string
0x18000d883  call    cs:__imp_WindowsDeleteString
0x18000d889  mov     eax, ebx
0x18000d88b  add     rsp, 20h
0x18000d88f  pop     r14
0x18000d891  pop     rdi
0x18000d892  pop     rsi
0x18000d893  pop     rbx
0x18000d894  pop     rbp
0x18000d895  retn
```
