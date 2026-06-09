# WinHttpProxyResolver::Initialize(WinHttpSession &)

- ea: `0x1800981c8`
- end: `0x18009825d`
- name: `?Initialize@WinHttpProxyResolver@@QEAAJAEAVWinHttpSession@@@Z`
- size: `149`
- prototype: `__int64 __fastcall(WinHttpProxyResolver *__hidden this, struct WinHttpSession *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180098264`

## callees

- `0x18008aa28`
- `0x1800981c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009821a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009821a`
- `WINHTTP!WinHttpCreateProxyResolver` at `0x1800981ea`
- `WINHTTP!WinHttpCreateProxyResolver` at `0x1800981ea`

## string_xrefs

- `0x180098203`: `WinHttpCreateProxyResolver`

## pseudocode

```c
__int64 __fastcall WinHttpProxyResolver::Initialize(WinHttpProxyResolver *this, HINTERNET *a2)
{
  signed int v3; // eax
  signed int v4; // ebx
  const wchar_t *v5; // r8
  HINTERNET v6; // rax
  signed int LastError; // eax
  HINTERNET phResolver; // [rsp+38h] [rbp+10h] BYREF

  phResolver = 0;
  v3 = WinHttpCreateProxyResolver(a2[1], &phResolver);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 < 0 )
  {
    v5 = L"WinHttpCreateProxyResolver";
LABEL_10:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"WinHttpProxyResolver::Initialize",
      v5,
      (unsigned int)v4);
    return (unsigned int)v4;
  }
  v6 = phResolver;
  *((_QWORD *)this + 1) = phResolver;
  if ( !v6 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = L"WinHttpProxyResolver::Attach";
      goto LABEL_10;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800981c8  mov     [rsp+arg_0], rbx
0x1800981cd  push    rdi
0x1800981ce  sub     rsp, 20h
0x1800981d2  mov     rax, rdx
0x1800981d5  mov     [rsp+28h+phResolver], 0
0x1800981de  mov     rdi, rcx
0x1800981e1  lea     rdx, [rsp+28h+phResolver]; phResolver
0x1800981e6  mov     rcx, [rax+8]; hSession
0x1800981ea  call    cs:__imp_WinHttpCreateProxyResolver
0x1800981f0  mov     ebx, eax
0x1800981f2  test    eax, eax
0x1800981f4  jle     short loc_1800981FF
0x1800981f6  movzx   ebx, ax
0x1800981f9  or      ebx, 80070000h
0x1800981ff  test    ebx, ebx
0x180098201  jns     short loc_18009820C
0x180098203  lea     r8, aWinhttpcreatep_0; "WinHttpCreateProxyResolver"
0x18009820a  jmp     short loc_18009823A
0x18009820c  mov     rax, [rsp+28h+phResolver]
0x180098211  mov     [rdi+8], rax
0x180098215  test    rax, rax
0x180098218  jnz     short loc_180098250
0x18009821a  call    cs:__imp_GetLastError
0x180098220  mov     ebx, eax
0x180098222  test    eax, eax
0x180098224  jle     short loc_18009822F
0x180098226  movzx   ebx, ax
0x180098229  or      ebx, 80070000h
0x18009822f  test    ebx, ebx
0x180098231  jns     short loc_180098250
0x180098233  lea     r8, aWinhttpproxyre_1; "WinHttpProxyResolver::Attach"
0x18009823a  mov     r9d, ebx
0x18009823d  lea     rdx, aWinhttpproxyre; "WinHttpProxyResolver::Initialize"
0x180098244  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009824b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098250  mov     eax, ebx
0x180098252  mov     rbx, [rsp+28h+arg_0]
0x180098257  add     rsp, 20h
0x18009825b  pop     rdi
0x18009825c  retn
```
