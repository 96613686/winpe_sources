# Windows::Networking::UX::CStaticIpConfig::Equals(Windows::Networking::UX::IStaticIpConfig *,uchar *)

- ea: `0x180013d70`
- end: `0x180013f26`
- name: `?Equals@CStaticIpConfig@UX@Networking@Windows@@UEAAJPEAUIStaticIpConfig@234@PEAE@Z`
- size: `438`
- prototype: `int(Windows::Networking::UX::CStaticIpConfig *__hidden this, struct Windows::Networking::UX::IStaticIpConfig *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a70c`
- `0x18000e768`
- `0x180013d70`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013d9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013dfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013e3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013f13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013d9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013dfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013e3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013f13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013e6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013eaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013e6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013eaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180013edb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180013edb`

## string_xrefs

- `0x180013dcb`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180013e24`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::CStaticIpConfig::Equals(
        Windows::Networking::UX::CStaticIpConfig *this,
        struct Windows::Networking::UX::IStaticIpConfig *a2,
        bool *a3)
{
  __int64 (__fastcall *v6)(Windows::Networking::UX::CStaticIpConfig *, _QWORD, HSTRING *); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  HSTRING v9; // rcx
  __int64 (__fastcall *v10)(struct Windows::Networking::UX::IStaticIpConfig *, _QWORD, HSTRING *); // rbx
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
  v6 = *(__int64 (__fastcall **)(Windows::Networking::UX::CStaticIpConfig *, _QWORD, HSTRING *))(*(_QWORD *)this + 152LL);
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
      v10 = *(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, _QWORD, HSTRING *))(*(_QWORD *)a2 + 152LL);
      WindowsDeleteString(0);
      string = 0;
      v11 = v10(a2, 0, &string);
      v8 = v11;
      if ( v11 < 0 )
      {
        v12 = 336;
LABEL_6:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
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
            WPP_a128af0fe115351291fe35deaa64950b_Traceguids,
            StringRawBuffer);
          v13 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
        {
          v15 = WindowsGetStringRawBuffer(string, 0);
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a128af0fe115351291fe35deaa64950b_Traceguids, v15);
        }
      }
      v11 = WindowsCompareStringOrdinal(string1, string, &result);
      v8 = v11;
      if ( v11 < 0 )
      {
        v12 = 341;
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
    (void *)0x14B,
    (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
    (const char *)(unsigned int)v7,
    savedregs);
LABEL_18:
  WindowsDeleteString(string1);
  return v8;
}

```

## disassembly

```asm
0x180013d70  push    rbp
0x180013d72  push    rbx
0x180013d73  push    rsi
0x180013d74  push    rdi
0x180013d75  push    r14; int
0x180013d77  mov     rbp, rsp
0x180013d7a  sub     rsp, 20h
0x180013d7e  mov     r14, r8
0x180013d81  mov     rsi, rdx
0x180013d84  mov     rdi, rcx
0x180013d87  mov     byte ptr [r8], 0
0x180013d8b  mov     [rbp+string1], 0
0x180013d93  mov     rax, [rcx]
0x180013d96  mov     rbx, [rax+98h]
0x180013d9d  xor     ecx, ecx; string
0x180013d9f  call    cs:__imp_WindowsDeleteString
0x180013da5  mov     [rbp+string1], 0
0x180013dad  lea     r8, [rbp+string1]
0x180013db1  xor     edx, edx
0x180013db3  mov     rcx, rdi
0x180013db6  mov     rax, rbx
0x180013db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dbe  mov     ebx, eax
0x180013dc0  test    eax, eax
0x180013dc2  jns     short loc_180013DE1
0x180013dc4  mov     rcx, [rbp+28h]; this
0x180013dc8  mov     r9d, eax; char *
0x180013dcb  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180013dd2  mov     edx, 14Bh; void *
0x180013dd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ddc  jmp     loc_180013F0F
0x180013de1  xor     ecx, ecx; string
0x180013de3  mov     [rbp+string], rcx
0x180013de7  test    rsi, rsi
0x180013dea  jz      loc_180013EFF
0x180013df0  mov     rax, [rsi]
0x180013df3  mov     rbx, [rax+98h]
0x180013dfa  call    cs:__imp_WindowsDeleteString
0x180013e00  mov     [rbp+string], 0
0x180013e08  lea     r8, [rbp+string]
0x180013e0c  xor     edx, edx
0x180013e0e  mov     rcx, rsi
0x180013e11  mov     rax, rbx
0x180013e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e19  mov     ebx, eax
0x180013e1b  test    eax, eax
0x180013e1d  jns     short loc_180013E47
0x180013e1f  mov     edx, 150h; void *
0x180013e24  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180013e2b  mov     r9d, eax; char *
0x180013e2e  mov     rcx, [rbp+28h]; this
0x180013e32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013e37  nop
0x180013e38  mov     rcx, [rbp+string]; string
0x180013e3c  call    cs:__imp_WindowsDeleteString
0x180013e42  jmp     loc_180013F07
0x180013e47  mov     [rbp+result], 0
0x180013e4e  lea     rbx, WPP_GLOBAL_Control
0x180013e55  mov     rax, cs:WPP_GLOBAL_Control
0x180013e5c  cmp     rax, rbx
0x180013e5f  jz      short loc_180013ECF
0x180013e61  test    byte ptr [rax+1Ch], 8
0x180013e65  jz      short loc_180013E99
0x180013e67  xor     edx, edx; length
0x180013e69  mov     rcx, [rbp+string1]; string
0x180013e6d  call    cs:__imp_WindowsGetStringRawBuffer
0x180013e73  mov     edx, 0Ah
0x180013e78  mov     r9, rax
0x180013e7b  lea     r8, WPP_a128af0fe115351291fe35deaa64950b_Traceguids
0x180013e82  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e89  mov     rcx, [rcx+10h]
0x180013e8d  call    WPP_SF_S
0x180013e92  mov     rax, cs:WPP_GLOBAL_Control
0x180013e99  cmp     rax, rbx
0x180013e9c  jz      short loc_180013ECF
0x180013e9e  test    byte ptr [rax+1Ch], 8
0x180013ea2  jz      short loc_180013ECF
0x180013ea4  xor     edx, edx; length
0x180013ea6  mov     rcx, [rbp+string]; string
0x180013eaa  call    cs:__imp_WindowsGetStringRawBuffer
0x180013eb0  mov     edx, 0Bh
0x180013eb5  mov     r9, rax
0x180013eb8  lea     r8, WPP_a128af0fe115351291fe35deaa64950b_Traceguids
0x180013ebf  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ec6  mov     rcx, [rcx+10h]
0x180013eca  call    WPP_SF_S
0x180013ecf  lea     r8, [rbp+result]; result
0x180013ed3  mov     rdx, [rbp+string]; string2
0x180013ed7  mov     rcx, [rbp+string1]; string1
0x180013edb  call    cs:__imp_WindowsCompareStringOrdinal
0x180013ee1  mov     ebx, eax
0x180013ee3  test    eax, eax
0x180013ee5  jns     short loc_180013EF1
0x180013ee7  mov     edx, 155h
0x180013eec  jmp     loc_180013E24
0x180013ef1  cmp     [rbp+result], 0
0x180013ef5  setz    al
0x180013ef8  mov     [r14], al
0x180013efb  mov     rcx, [rbp+string]; string
0x180013eff  call    cs:__imp_WindowsDeleteString
0x180013f05  xor     ebx, ebx
0x180013f07  mov     [rbp+string], 0
0x180013f0f  mov     rcx, [rbp+string1]; string
0x180013f13  call    cs:__imp_WindowsDeleteString
0x180013f19  mov     eax, ebx
0x180013f1b  add     rsp, 20h
0x180013f1f  pop     r14
0x180013f21  pop     rdi
0x180013f22  pop     rsi
0x180013f23  pop     rbx
0x180013f24  pop     rbp
0x180013f25  retn
```
