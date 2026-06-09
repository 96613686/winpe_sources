# CommandImpl::RunCommand(wchar_t const *)

- ea: `0x180048d58`
- end: `0x180048fde`
- name: `?RunCommand@CommandImpl@@AEAAJPEB_W@Z`
- size: `646`
- prototype: `__int64 __fastcall(CommandImpl *__hidden this, LPCWSTR lpCmdLine)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180048b08`

## callees

- `0x180009380`
- `0x18000a718`
- `0x180018920`
- `0x18002ebe8`
- `0x1800483bc`
- `0x180048d58`
- `0x180048fe4`
- `0x18004975c`
- `0x18004bc0c`
- `0x180056500`
- `0x18005c660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048dd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048dd2`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x180048db3`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x180048db3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048dc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048dc6`

## string_xrefs

- `0x180048e29`: `Error parsing command line argument %ws`
- `0x180048e38`: `C:\__w\1\s\src\orchestrator\clientImpl\lib\CommandImpl.cpp`
- `0x180048e92`: `C:\__w\1\s\src\orchestrator\clientImpl\lib\CommandImpl.cpp`
- `0x180048e80`: `Unknown command mode: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CommandImpl::RunCommand(CommandImpl *this, LPCWSTR lpCmdLine)
{
  wchar_t *v3; // rsi
  int v4; // eax
  LPWSTR *v5; // rax
  void *v6; // rcx
  signed int LastError; // eax
  __int64 v8; // rdx
  unsigned int v9; // ebx
  const char *v10; // rax
  const char **v12; // rsi
  int v13; // ebx
  const char *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  const struct std::filesystem::path *v17; // rcx
  int v18; // ebx
  unsigned __int64 v19; // [rsp+20h] [rbp-1F8h]
  wchar_t *v20[2]; // [rsp+30h] [rbp-1E8h] BYREF
  _OWORD v21[2]; // [rsp+40h] [rbp-1D8h] BYREF
  _BYTE v22[32]; // [rsp+60h] [rbp-1B8h] BYREF
  int pNumArgs[4]; // [rsp+80h] [rbp-198h] BYREF
  _BYTE v24[352]; // [rsp+90h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  v3 = 0;
  v20[0] = 0;
  v4 = 0;
  pNumArgs[0] = 0;
  if ( !lpCmdLine || !*lpCmdLine )
    goto LABEL_10;
  v5 = CommandLineToArgvW(lpCmdLine, pNumArgs);
  v6 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = v5;
  if ( v6 )
    LocalFree(v6);
  if ( *((_QWORD *)this + 1) )
  {
    v4 = pNumArgs[0];
LABEL_10:
    v9 = CommandLineBase::Parse(this, *((const wchar_t ***)this + 1), v4, (const wchar_t **)v20, v19);
    v3 = v20[0];
    goto LABEL_11;
  }
  LastError = GetLastError();
  v9 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v9 = LastError;
LABEL_11:
  if ( (v9 & 0x80000000) == 0 )
  {
    v12 = (const char **)((char *)this + 48);
    LOBYTE(v8) = *((_BYTE *)this + 40);
    v13 = CommandImpl::Str2Command(*((_QWORD *)this + 6), v8);
    if ( v13 )
    {
      if ( v13 == 1 )
      {
        return 0;
      }
      else
      {
        memset(v24, 0, 0x158u);
        ClientTelemetry::Run::Start<wchar_t const * &,uus::UusInfo const &>(v24, (char *)this + 48, (char *)this + 24);
        if ( v13 == 2 )
        {
          v15 = *((_QWORD *)this + 7);
          if ( v15 )
          {
            v16 = -1;
            do
              ++v16;
            while ( *(_WORD *)(v15 + 2 * v16) );
            v20[0] = *((wchar_t **)this + 7);
            v20[1] = (wchar_t *)v16;
            std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v22, v20);
            v17 = (const struct std::filesystem::path *)v22;
            v18 = 5;
          }
          else
          {
            v21[0] = 0;
            v21[1] = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(v21[0]) = 0;
            v17 = (const struct std::filesystem::path *)v21;
            v18 = 2;
          }
          pNumArgs[0] = v18;
          CommandImpl::Analyze(v17);
          if ( (v18 & 2) != 0 )
          {
            LOBYTE(v18) = v18 & 0xFD;
            std::wstring::~wstring(v21);
          }
          if ( (v18 & 1) != 0 )
            std::wstring::~wstring(v22);
          ClientTelemetry::Run::~Run((ClientTelemetry::Run *)v24);
          return 0;
        }
        else
        {
          ClientTelemetry::Run::~Run((ClientTelemetry::Run *)v24);
          return 2147942422LL;
        }
      }
    }
    else
    {
      v14 = (const char *)&S2;
      if ( *v12 )
        v14 = *v12;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)(unsigned int)(v13 + 63),
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\lib\\CommandImpl.cpp",
        (const char *)0x80070016LL,
        (int)"Unknown command mode: %ws",
        v14);
      return 2147942422LL;
    }
  }
  else
  {
    v10 = (const char *)&S2;
    if ( v3 )
      v10 = (const char *)v3;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x39,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\lib\\CommandImpl.cpp",
      (const char *)v9,
      (int)"Error parsing command line argument %ws",
      v10);
    return v9;
  }
}

```

## disassembly

```asm
0x180048d58  mov     [rsp+arg_10], rbx
0x180048d5d  push    rsi
0x180048d5e  push    rdi
0x180048d5f  push    r14
0x180048d61  sub     rsp, 200h
0x180048d68  mov     rax, cs:__security_cookie
0x180048d6f  xor     rax, rsp
0x180048d72  mov     [rsp+218h+var_28], rax
0x180048d7a  mov     r8, rdx
0x180048d7d  mov     rdi, rcx
0x180048d80  xor     r14d, r14d
0x180048d83  mov     [rsp+218h+pNumArgs], r14d
0x180048d8b  mov     esi, r14d
0x180048d8e  mov     [rsp+218h+var_1E8], r14
0x180048d93  mov     eax, r14d
0x180048d96  mov     [rsp+218h+pNumArgs], eax
0x180048d9d  test    rdx, rdx
0x180048da0  jz      short loc_180048DEF
0x180048da2  cmp     [rdx], r14w
0x180048da6  jz      short loc_180048DEF
0x180048da8  lea     rdx, [rsp+218h+pNumArgs]; pNumArgs
0x180048db0  mov     rcx, r8; lpCmdLine
0x180048db3  call    cs:__imp_CommandLineToArgvW
0x180048db9  mov     rcx, [rdi+8]; hMem
0x180048dbd  mov     [rdi+8], rax
0x180048dc1  test    rcx, rcx
0x180048dc4  jz      short loc_180048DCC
0x180048dc6  call    cs:__imp_LocalFree
0x180048dcc  cmp     [rdi+8], r14
0x180048dd0  jnz     short loc_180048DE8
0x180048dd2  call    cs:__imp_GetLastError
0x180048dd8  movzx   ebx, ax
0x180048ddb  or      ebx, 80070000h
0x180048de1  test    eax, eax
0x180048de3  cmovle  ebx, eax
0x180048de6  jmp     short loc_180048E0A
0x180048de8  mov     eax, [rsp+218h+pNumArgs]
0x180048def  movsxd  r8, eax; unsigned __int64
0x180048df2  lea     r9, [rsp+218h+var_1E8]; wchar_t **
0x180048df7  mov     rdx, [rdi+8]; wchar_t **
0x180048dfb  mov     rcx, rdi; this
0x180048dfe  call    ?Parse@CommandLineBase@@QEAAJPEAPEB_W_K01@Z; CommandLineBase::Parse(wchar_t const * *,unsigned __int64,wchar_t const * *,unsigned __int64)
0x180048e03  mov     ebx, eax
0x180048e05  mov     rsi, [rsp+218h+var_1E8]
0x180048e0a  test    ebx, ebx
0x180048e0c  jns     short loc_180048E50
0x180048e0e  lea     rax, S2
0x180048e15  test    rsi, rsi
0x180048e18  cmovnz  rax, rsi
0x180048e1c  mov     rcx, [rsp+218h]; this
0x180048e24  mov     [rsp+218h+var_1F0], rax; char *
0x180048e29  lea     rax, aErrorParsingCo; "Error parsing command line argument %ws"
0x180048e30  mov     qword ptr [rsp+218h+var_1F8], rax; int
0x180048e35  mov     r9d, ebx; char *
0x180048e38  lea     r8, aCW1SSrcOrchest_0; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x180048e3f  mov     edx, 39h ; '9'; void *
0x180048e44  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048e49  mov     eax, ebx
0x180048e4b  jmp     loc_180048FB9
0x180048e50  lea     rsi, [rdi+30h]
0x180048e54  mov     dl, [rdi+28h]
0x180048e57  mov     rcx, [rsi]
0x180048e5a  call    ?Str2Command@CommandImpl@@CA?AW4CommandMode@1@PEB_W_N@Z; CommandImpl::Str2Command(wchar_t const *,bool)
0x180048e5f  mov     ebx, eax
0x180048e61  test    eax, eax
0x180048e63  jnz     short loc_180048EAB
0x180048e65  lea     rax, S2
0x180048e6c  cmp     [rsi], r14
0x180048e6f  cmovnz  rax, [rsi]
0x180048e73  mov     rcx, [rsp+218h]; this
0x180048e7b  mov     [rsp+218h+var_1F0], rax; char *
0x180048e80  lea     rax, aUnknownCommand; "Unknown command mode: %ws"
0x180048e87  mov     qword ptr [rsp+218h+var_1F8], rax; int
0x180048e8c  mov     r9d, 80070016h; char *
0x180048e92  lea     r8, aCW1SSrcOrchest_0; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x180048e99  lea     edx, [rbx+3Fh]; void *
0x180048e9c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048ea1  mov     eax, 80070016h
0x180048ea6  jmp     loc_180048FB9
0x180048eab  cmp     ebx, 1
0x180048eae  jnz     short loc_180048EB7
0x180048eb0  xor     eax, eax
0x180048eb2  jmp     loc_180048FB9
0x180048eb7  xor     edx, edx; Val
0x180048eb9  mov     r8d, 158h; Size
0x180048ebf  lea     rcx, [rsp+218h+var_188]; void *
0x180048ec7  call    memset
0x180048ecc  lea     r8, [rdi+18h]
0x180048ed0  mov     rdx, rsi
0x180048ed3  lea     rcx, [rsp+218h+var_188]
0x180048edb  call    ??$Start@AEAPEB_WAEBUUusInfo@uus@@@Run@ClientTelemetry@@SA?AV01@AEAPEB_WAEBUUusInfo@uus@@@Z; ClientTelemetry::Run::Start<wchar_t const * &,uus::UusInfo const &>(wchar_t const * &,uus::UusInfo const &)
0x180048ee0  nop
0x180048ee1  test    ebx, ebx
0x180048ee3  jz      loc_180048F9E
0x180048ee9  sub     ebx, 1
0x180048eec  jz      loc_180048F9E
0x180048ef2  cmp     ebx, 1
0x180048ef5  jnz     loc_180048F9E
0x180048efb  mov     rcx, [rdi+38h]
0x180048eff  test    rcx, rcx
0x180048f02  jz      short loc_180048F37
0x180048f04  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048f08  inc     rax
0x180048f0b  cmp     [rcx+rax*2], r14w
0x180048f10  jnz     short loc_180048F08
0x180048f12  mov     [rsp+218h+var_1E8], rcx
0x180048f17  mov     [rsp+218h+var_1E0], rax
0x180048f1c  lea     rdx, [rsp+218h+var_1E8]
0x180048f21  lea     rcx, [rsp+218h+var_1B8]
0x180048f26  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180048f2b  lea     rcx, [rsp+218h+var_1B8]
0x180048f30  mov     ebx, 5
0x180048f35  jmp     short loc_180048F5D
0x180048f37  xorps   xmm0, xmm0
0x180048f3a  movups  [rsp+218h+var_1D8], xmm0
0x180048f3f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180048f47  movdqu  [rsp+218h+var_1C8], xmm1
0x180048f4d  mov     word ptr [rsp+218h+var_1D8], r14w
0x180048f53  lea     rcx, [rsp+218h+var_1D8]; struct std::filesystem::path *
0x180048f58  mov     ebx, 2
0x180048f5d  mov     [rsp+218h+pNumArgs], ebx
0x180048f64  call    ?Analyze@CommandImpl@@CAXAEBVpath@filesystem@std@@@Z; CommandImpl::Analyze(std::filesystem::path const &)
0x180048f69  nop
0x180048f6a  test    bl, 2
0x180048f6d  jz      short loc_180048F7D
0x180048f6f  and     ebx, 0FFFFFFFDh
0x180048f72  lea     rcx, [rsp+218h+var_1D8]; void *
0x180048f77  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048f7c  nop
0x180048f7d  test    bl, 1
0x180048f80  jz      short loc_180048F8D
0x180048f82  lea     rcx, [rsp+218h+var_1B8]; void *
0x180048f87  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048f8c  nop
0x180048f8d  lea     rcx, [rsp+218h+var_188]; this
0x180048f95  call    ??1Run@ClientTelemetry@@QEAA@XZ; ClientTelemetry::Run::~Run(void)
0x180048f9a  xor     eax, eax
0x180048f9c  jmp     short loc_180048FB9
0x180048f9e  lea     rcx, [rsp+218h+var_188]; this
0x180048fa6  call    ??1Run@ClientTelemetry@@QEAA@XZ; ClientTelemetry::Run::~Run(void)
0x180048fab  mov     eax, 80070016h
0x180048fb0  jmp     short loc_180048FB9
0x180048fb2  mov     eax, [rsp+218h+pNumArgs]
0x180048fb9  mov     rcx, [rsp+218h+var_28]
0x180048fc1  xor     rcx, rsp; StackCookie
0x180048fc4  call    __security_check_cookie
0x180048fc9  mov     rbx, [rsp+218h+arg_10]
0x180048fd1  add     rsp, 200h
0x180048fd8  pop     r14
0x180048fda  pop     rdi
0x180048fdb  pop     rsi
0x180048fdc  retn
```
