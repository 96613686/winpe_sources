# WinHttpRequest::ReadDataTrigger(ulong)

- ea: `0x18009bfec`
- end: `0x18009c0e6`
- name: `?ReadDataTrigger@WinHttpRequest@@AEAAJK@Z`
- size: `250`
- prototype: `int(WinHttpRequest *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180098b14`

## callees

- `0x180004a24`
- `0x180005f24`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008b2cc`
- `0x18009bfec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009c0bd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009c0bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c075`
- `WINHTTP!WinHttpReadData` at `0x18009c06b`
- `WINHTTP!WinHttpReadData` at `0x18009c06b`

## string_xrefs

- `0x18009c010`: `WinHttpRequest::ReadDataTrigger`
- `0x18009c037`: `WinHttpRequest::ReadDataTrigger`
- `0x18009c092`: `WinHttpRequest::ReadDataTrigger`
- `0x18009c0c6`: `WinHttpRequest::ReadDataTrigger`
- `0x18009c009`: `%s: Trying to read %lu bytes of data.`
- `0x18009c08b`: `WinHttpReadData`

## pseudocode

```c
__int64 __fastcall WinHttpRequest::ReadDataTrigger(HINTERNET *this, DWORD a2)
{
  unsigned int v2; // ebx
  void *v5; // rax
  void *v6; // rsi
  signed int LastError; // edi

  v2 = 0;
  if ( a2 )
  {
    Logger::TraceVerbose(L"%s: Trying to read %lu bytes of data.", L"WinHttpRequest::ReadDataTrigger", a2);
    v5 = operator new[](a2 + 1, (const struct std::nothrow_t *)std::nothrow);
    v6 = v5;
    if ( !v5 )
    {
      v2 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"WinHttpRequest::ReadDataTrigger");
LABEL_9:
      free(v6);
      goto LABEL_10;
    }
    memset_0(v5, 0, a2 + 1);
    if ( !WinHttpReadData(this[1], v6, a2, 0) )
    {
      LastError = GetLastError();
      Logger::WriteWinhttpReadFailureEvent(LastError);
      if ( LastError )
      {
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"WinHttpRequest::ReadDataTrigger",
          L"WinHttpReadData",
          (unsigned int)LastError);
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        else
          v2 = LastError;
        goto LABEL_9;
      }
    }
  }
LABEL_10:
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"WinHttpRequest::ReadDataTrigger", v2);
  return v2;
}

```

## disassembly

```asm
0x18009bfec  push    rbx
0x18009bfee  push    rbp
0x18009bfef  push    rsi
0x18009bff0  push    rdi
0x18009bff1  push    r14
0x18009bff3  sub     rsp, 20h
0x18009bff7  xor     ebx, ebx
0x18009bff9  mov     edi, edx
0x18009bffb  mov     r14, rcx
0x18009bffe  test    edx, edx
0x18009c000  jz      loc_18009C0C3
0x18009c006  mov     r8d, edx
0x18009c009  lea     rcx, aSTryingToReadL; "%s: Trying to read %lu bytes of data."
0x18009c010  lea     rdx, aWinhttprequest_13; "WinHttpRequest::ReadDataTrigger"
0x18009c017  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009c01c  lea     eax, [rdi+1]
0x18009c01f  mov     ecx, eax; unsigned __int64
0x18009c021  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009c028  mov     ebp, eax
0x18009c02a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18009c02f  mov     rsi, rax
0x18009c032  test    rax, rax
0x18009c035  jnz     short loc_18009C051
0x18009c037  lea     rdx, aWinhttprequest_13; "WinHttpRequest::ReadDataTrigger"
0x18009c03e  mov     ebx, 8007000Eh
0x18009c043  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18009c04a  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18009c04f  jmp     short loc_18009C0BA
0x18009c051  mov     r8, rbp; Size
0x18009c054  xor     edx, edx; Val
0x18009c056  mov     rcx, rsi; void *
0x18009c059  call    memset_0
0x18009c05e  mov     rcx, [r14+8]; hRequest
0x18009c062  xor     r9d, r9d; lpdwNumberOfBytesRead
0x18009c065  mov     r8d, edi; dwNumberOfBytesToRead
0x18009c068  mov     rdx, rsi; lpBuffer
0x18009c06b  call    cs:__imp_WinHttpReadData
0x18009c071  test    eax, eax
0x18009c073  jnz     short loc_18009C0C3
0x18009c075  call    cs:__imp_GetLastError
0x18009c07b  mov     ecx, eax; unsigned int
0x18009c07d  mov     edi, eax
0x18009c07f  call    ?WriteWinhttpReadFailureEvent@Logger@@SAJK@Z; Logger::WriteWinhttpReadFailureEvent(ulong)
0x18009c084  test    edi, edi
0x18009c086  jz      short loc_18009C0C3
0x18009c088  mov     r9d, edi
0x18009c08b  lea     r8, aWinhttpreaddat_0; "WinHttpReadData"
0x18009c092  lea     rdx, aWinhttprequest_13; "WinHttpRequest::ReadDataTrigger"
0x18009c099  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18009c0a0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009c0a5  test    edi, edi
0x18009c0a7  jg      short loc_18009C0AD
0x18009c0a9  mov     ebx, edi
0x18009c0ab  jmp     short loc_18009C0B6
0x18009c0ad  movzx   ebx, di
0x18009c0b0  or      ebx, 80070000h
0x18009c0b6  test    ebx, ebx
0x18009c0b8  jns     short loc_18009C0C3
0x18009c0ba  mov     rcx, rsi; Block
0x18009c0bd  call    cs:__imp_free
0x18009c0c3  mov     r8d, ebx
0x18009c0c6  lea     rdx, aWinhttprequest_13; "WinHttpRequest::ReadDataTrigger"
0x18009c0cd  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18009c0d4  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009c0d9  mov     eax, ebx
0x18009c0db  add     rsp, 20h
0x18009c0df  pop     r14
0x18009c0e1  pop     rdi
0x18009c0e2  pop     rsi
0x18009c0e3  pop     rbp
0x18009c0e4  pop     rbx
0x18009c0e5  retn
```
