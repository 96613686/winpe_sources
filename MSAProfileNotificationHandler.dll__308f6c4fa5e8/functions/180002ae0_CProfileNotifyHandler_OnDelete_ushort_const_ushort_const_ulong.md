# CProfileNotifyHandler::OnDelete(ushort const *,ushort const *,ulong)

- ea: `0x180002ae0`
- end: `0x180002c38`
- name: `?OnDelete@CProfileNotifyHandler@@UEAAJPEBG0K@Z`
- size: `344`
- prototype: `__int64 __fastcall(CProfileNotifyHandler *this, const char *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001d04`
- `0x180002974`
- `0x180002ae0`
- `0x180007360`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180002b2f`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180002b2f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180002ba1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180002ba1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180002bd8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180002bd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002be8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002be8`

## string_xrefs

- `0x180002bb0`: `hr = HRESULT_FROM_WIN32(ERROR_CANNOT_COPY)`

## pseudocode

```c
__int64 __fastcall CProfileNotifyHandler::OnDelete(
        CProfileNotifyHandler *this,
        const char *a2,
        const unsigned __int16 *a3)
{
  signed int v4; // ebx
  const char *v5; // rax
  unsigned int v6; // r8d
  size_t v7; // rdi
  unsigned __int64 v8; // rax
  void *v9; // rax
  void *v10; // rsi
  signed int LastError; // eax
  _QWORD v13[5]; // [rsp+30h] [rbp-28h] BYREF

  memset(v13, 0, 24);
  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = "hr = E_INVALIDARG";
    v6 = 141;
LABEL_16:
    Telemetry::IfFailExit((const char *)this, a2, v6, v4, v5);
    goto LABEL_17;
  }
  v7 = wcsnlen((const wchar_t *)a2, 0x46u) + 2;
  if ( v7 >= 0x46 )
  {
    v4 = -2147024872;
    v5 = "hr = HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)";
    v6 = 149;
    goto LABEL_16;
  }
  v8 = 4 * v7;
  if ( !is_mul_ok(2 * v7, 2u) )
    v8 = -1;
  v9 = operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( !v9 )
  {
    v4 = -2147024882;
    v5 = "hr = E_OUTOFMEMORY";
    v6 = 156;
    goto LABEL_16;
  }
  if ( (unsigned int)_o_wcscpy_s(v9, v7, a2) )
  {
    v4 = -2147024630;
    v5 = "hr = HRESULT_FROM_WIN32(ERROR_CANNOT_COPY)";
    v6 = 161;
    goto LABEL_16;
  }
  v4 = 0;
  v13[0] = CreateThread(0, 0, CProfileNotifyHandler::CleanupMSAState, v10, 0, 0);
  if ( !v13[0] )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = "hr = HRESULT_FROM_WIN32(GetLastError())";
      v6 = 176;
      goto LABEL_16;
    }
  }
LABEL_17:
  Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002ae0  mov     rax, rsp
0x180002ae3  mov     [rax+8], rbx
0x180002ae7  mov     [rax+10h], rsi
0x180002aeb  push    rdi
0x180002aec  sub     rsp, 50h
0x180002af0  mov     rbx, rdx
0x180002af3  mov     qword ptr [rax-28h], 0
0x180002afb  mov     qword ptr [rax-18h], 0
0x180002b03  mov     qword ptr [rax-20h], 0
0x180002b0b  test    rdx, rdx
0x180002b0e  jnz     short loc_180002B27
0x180002b10  mov     ebx, 80070057h
0x180002b15  lea     rax, aHrEInvalidarg; "hr = E_INVALIDARG"
0x180002b1c  mov     r8d, 8Dh
0x180002b22  jmp     loc_180002C0E
0x180002b27  mov     edx, 46h ; 'F'; MaxCount
0x180002b2c  mov     rcx, rbx; Source
0x180002b2f  call    cs:__imp_wcsnlen
0x180002b35  lea     rdi, [rax+2]
0x180002b39  cmp     rdi, 46h ; 'F'
0x180002b3d  jb      short loc_180002B56
0x180002b3f  mov     ebx, 80070018h
0x180002b44  lea     rax, aHrHresultFromW_1; "hr = HRESULT_FROM_WIN32(ERROR_BAD_LENGT"...
0x180002b4b  mov     r8d, 95h
0x180002b51  jmp     loc_180002C0E
0x180002b56  lea     rcx, [rdi+rdi]
0x180002b5a  mov     eax, 2
0x180002b5f  mul     rcx
0x180002b62  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180002b69  cmovb   rax, rcx
0x180002b6d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002b74  mov     rcx, rax; unsigned __int64
0x180002b77  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180002b7c  mov     rsi, rax
0x180002b7f  test    rax, rax
0x180002b82  jnz     short loc_180002B98
0x180002b84  mov     ebx, 8007000Eh
0x180002b89  lea     rax, aHrEOutofmemory; "hr = E_OUTOFMEMORY"
0x180002b90  mov     r8d, 9Ch
0x180002b96  jmp     short loc_180002C0E
0x180002b98  mov     r8, rbx
0x180002b9b  mov     rdx, rdi
0x180002b9e  mov     rcx, rsi
0x180002ba1  call    cs:__imp__o_wcscpy_s
0x180002ba7  test    eax, eax
0x180002ba9  jz      short loc_180002BBF
0x180002bab  mov     ebx, 8007010Ah
0x180002bb0  lea     rax, aHrHresultFromW_0; "hr = HRESULT_FROM_WIN32(ERROR_CANNOT_CO"...
0x180002bb7  mov     r8d, 0A1h
0x180002bbd  jmp     short loc_180002C0E
0x180002bbf  xor     ebx, ebx
0x180002bc1  mov     [rsp+58h+lpThreadId], rbx; lpThreadId
0x180002bc6  mov     [rsp+58h+dwCreationFlags], ebx; dwCreationFlags
0x180002bca  mov     r9, rsi; lpParameter
0x180002bcd  lea     r8, ?CleanupMSAState@CProfileNotifyHandler@@CAKPEAX@Z; lpStartAddress
0x180002bd4  xor     edx, edx; dwStackSize
0x180002bd6  xor     ecx, ecx; lpThreadAttributes
0x180002bd8  call    cs:__imp_CreateThread
0x180002bde  mov     [rsp+58h+var_28], rax
0x180002be3  test    rax, rax
0x180002be6  jnz     short loc_180002C1C
0x180002be8  call    cs:__imp_GetLastError
0x180002bee  mov     ebx, eax
0x180002bf0  test    eax, eax
0x180002bf2  jle     short loc_180002BFD
0x180002bf4  movzx   ebx, ax
0x180002bf7  or      ebx, 80070000h
0x180002bfd  test    ebx, ebx
0x180002bff  jns     short loc_180002C1C
0x180002c01  lea     rax, aHrHresultFromW; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180002c08  mov     r8d, 0B0h; unsigned int
0x180002c0e  mov     qword ptr [rsp+58h+dwCreationFlags], rax; char *
0x180002c13  mov     r9d, ebx; int
0x180002c16  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180002c1b  nop
0x180002c1c  lea     rcx, [rsp+58h+var_28]
0x180002c21  call    ??1?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAA@XZ; Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(void)
0x180002c26  mov     eax, ebx
0x180002c28  mov     rbx, [rsp+58h+arg_0]
0x180002c2d  mov     rsi, [rsp+58h+arg_8]
0x180002c32  add     rsp, 50h
0x180002c36  pop     rdi
0x180002c37  retn
```
