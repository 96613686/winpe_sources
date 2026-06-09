# CLogger::GetLogLevel(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,LogLevel *)

- ea: `0x180038164`
- end: `0x1800382b8`
- name: `?GetLogLevel@CLogger@@CAJV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAW4LogLevel@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038518`
- `0x18003886c`

## callees

- `0x180002300`
- `0x18000ee70`
- `0x180011884`
- `0x18002a18c`
- `0x18002a398`
- `0x18002aca4`
- `0x18002add0`
- `0x18002cdd4`
- `0x180038164`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800381e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003820f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003822f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800381e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003820f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003822f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038258`

## string_xrefs

- `0x180038194`: `Software\Microsoft\Windows Search\Gather\Windows\SystemIndex\Protocols\Mapi`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CLogger::GetLogLevel(wchar_t *a1, unsigned __int8 *a2)
{
  unsigned int v4; // r9d
  unsigned int v5; // r9d
  DWORD LastError; // ebx
  const wchar_t *v8; // [rsp+20h] [rbp-E0h]
  const wchar_t *v9; // [rsp+20h] [rbp-E0h]
  unsigned int v10; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v11; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *v12[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[192]; // [rsp+50h] [rbp-B0h] BYREF

  v12[1] = a1;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    v12,
    "Software\\Microsoft\\Windows Search\\Gather\\Windows\\SystemIndex\\Protocols\\Mapi");
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &v11,
    "LogLevel.");
  ATL::CSimpleStringT<wchar_t,0>::Append(&v11, *(_QWORD *)a1, *(unsigned int *)(*(_QWORD *)a1 - 16LL));
  *(_DWORD *)a2 = 3;
  CRegistry::CRegistry((CRegistry *)v13, HKEY_LOCAL_MACHINE, v12[0], v4, v8);
  if ( !GetLastError() )
  {
    v10 = 4;
    CRegistry::GetValue((CRegistry *)v13, v11, a2, &v10);
  }
  if ( GetLastError() )
  {
    CRegistry::Init((CRegistry *)v13, HKEY_CURRENT_USER, v12[0], v5, v9);
    if ( !GetLastError() )
    {
      v10 = 4;
      CRegistry::GetValue((CRegistry *)v13, v11, a2, &v10);
    }
  }
  LastError = GetLastError();
  CRegistry::~CRegistry((CRegistry *)v13);
  ATL::CStringData::Release((ATL::CStringData *)(v11 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v12[0] - 12));
  ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)a1 - 24LL));
  return LastError;
}

```

## disassembly

```asm
0x180038164  mov     [rsp-8+arg_10], rbx
0x180038169  mov     [rsp-8+arg_18], rdi
0x18003816e  push    rbp
0x18003816f  lea     rbp, [rsp-20h]
0x180038174  sub     rsp, 120h
0x18003817b  mov     rax, cs:__security_cookie
0x180038182  xor     rax, rsp
0x180038185  mov     [rbp+20h+var_10], rax
0x180038189  mov     rbx, rdx
0x18003818c  mov     rdi, rcx
0x18003818f  mov     [rsp+120h+var_D8], rcx
0x180038194  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows Search\\Ga"...
0x18003819b  lea     rcx, [rsp+120h+var_E0]
0x1800381a0  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(char const *)
0x1800381a5  nop
0x1800381a6  lea     rdx, aLoglevel; "LogLevel."
0x1800381ad  lea     rcx, [rsp+120h+var_E8]
0x1800381b2  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(char const *)
0x1800381b7  nop
0x1800381b8  mov     rdx, [rdi]
0x1800381bb  mov     r8d, [rdx-10h]
0x1800381bf  lea     rcx, [rsp+120h+var_E8]
0x1800381c4  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *,int)
0x1800381c9  mov     dword ptr [rbx], 3
0x1800381cf  mov     r8, [rsp+120h+var_E0]; wchar_t *
0x1800381d4  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800381db  lea     rcx, [rsp+120h+var_D0]; this
0x1800381e0  call    ??0CRegistry@@QEAA@PEAUHKEY__@@PEB_WK1@Z; CRegistry::CRegistry(HKEY__ *,wchar_t const *,ulong,wchar_t const *)
0x1800381e5  nop
0x1800381e6  call    cs:__imp_GetLastError
0x1800381ec  test    eax, eax
0x1800381ee  jnz     short loc_18003820F
0x1800381f0  mov     [rsp+120h+var_F0], 4
0x1800381f8  lea     r9, [rsp+120h+var_F0]; unsigned int *
0x1800381fd  mov     r8, rbx; unsigned __int8 *
0x180038200  mov     rdx, [rsp+120h+var_E8]; wchar_t *
0x180038205  lea     rcx, [rsp+120h+var_D0]; this
0x18003820a  call    ?GetValue@CRegistry@@QEAAHPEB_WPEAEPEAK@Z; CRegistry::GetValue(wchar_t const *,uchar *,ulong *)
0x18003820f  call    cs:__imp_GetLastError
0x180038215  test    eax, eax
0x180038217  jz      short loc_180038258
0x180038219  mov     r8, [rsp+120h+var_E0]; wchar_t *
0x18003821e  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x180038225  lea     rcx, [rsp+120h+var_D0]; this
0x18003822a  call    ?Init@CRegistry@@QEAAJPEAUHKEY__@@PEB_WK1@Z; CRegistry::Init(HKEY__ *,wchar_t const *,ulong,wchar_t const *)
0x18003822f  call    cs:__imp_GetLastError
0x180038235  test    eax, eax
0x180038237  jnz     short loc_180038258
0x180038239  mov     [rsp+120h+var_F0], 4
0x180038241  lea     r9, [rsp+120h+var_F0]; unsigned int *
0x180038246  mov     r8, rbx; unsigned __int8 *
0x180038249  mov     rdx, [rsp+120h+var_E8]; wchar_t *
0x18003824e  lea     rcx, [rsp+120h+var_D0]; this
0x180038253  call    ?GetValue@CRegistry@@QEAAHPEB_WPEAEPEAK@Z; CRegistry::GetValue(wchar_t const *,uchar *,ulong *)
0x180038258  call    cs:__imp_GetLastError
0x18003825e  mov     ebx, eax
0x180038260  lea     rcx, [rsp+120h+var_D0]; this
0x180038265  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18003826a  nop
0x18003826b  mov     rcx, [rsp+120h+var_E8]
0x180038270  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180038274  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180038279  nop
0x18003827a  mov     rcx, [rsp+120h+var_E0]
0x18003827f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180038283  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180038288  nop
0x180038289  mov     rcx, [rdi]
0x18003828c  sub     rcx, 18h; this
0x180038290  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180038295  mov     eax, ebx
0x180038297  mov     rcx, [rbp+20h+var_10]
0x18003829b  xor     rcx, rsp; StackCookie
0x18003829e  call    __security_check_cookie
0x1800382a3  lea     r11, [rsp+120h+var_s0]
0x1800382ab  mov     rbx, [r11+20h]
0x1800382af  mov     rdi, [r11+28h]
0x1800382b3  mov     rsp, r11
0x1800382b6  pop     rbp
0x1800382b7  retn
```
