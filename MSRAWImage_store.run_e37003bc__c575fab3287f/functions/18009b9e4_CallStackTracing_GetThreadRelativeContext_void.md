# CallStackTracing::GetThreadRelativeContext(void)

- ea: `0x18009b9e4`
- end: `0x18009ba88`
- name: `?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ`
- size: `164`
- prototype: `struct CallStackContext *__fastcall(CallStackTracing *__hidden this)`
- caller_count: `69`
- callee_count: `2`
- tags: ``

## callers

- `0x180001a40`
- `0x1800023a0`
- `0x180002590`
- `0x1800989fc`
- `0x180098c20`
- `0x1800990d4`
- `0x1800997d0`
- `0x180099b80`
- `0x180099d30`
- `0x180099e70`
- `0x18009a000`
- `0x18009a410`
- `0x18009a900`
- `0x18009ac30`
- `0x18009b030`
- `0x18009b1c0`
- `0x18009b4b0`
- `0x18009b6f0`
- `0x18009ba90`
- `0x18009c120`
- `0x18009c940`
- `0x18009cde0`
- `0x18009d37c`
- `0x18009d58c`
- `0x18009da50`
- `0x18009deb0`
- `0x18009e190`
- `0x1800a0f4c`
- `0x1800a13d0`
- `0x1800a17a0`
- `0x1800a1ab0`
- `0x1800a1c40`
- `0x1800a1e10`
- `0x1800a2030`
- `0x1800a25b8`
- `0x1800a27cc`
- `0x1800a58b4`
- `0x1800a5b90`
- `0x1800a6784`
- `0x1800a6a40`
- `0x1800a6d94`
- `0x1800a713c`
- `0x1800a7520`
- `0x1800a7b28`
- `0x1800a7f98`
- `0x1800a81cc`
- `0x1800a8588`
- `0x1800a8df0`
- `0x1800a98c0`
- `0x1800aa7f0`

## callees

- `0x18009b9e4`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009ba14`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009ba14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009ba68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009ba68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ba03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ba2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ba03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ba2a`

## pseudocode

```c
struct CallStackContext *__fastcall CallStackTracing::GetThreadRelativeContext(CallStackTracing *this)
{
  char *v1; // rbx
  DWORD LastError; // esi
  char *Value; // rax
  void ***v5; // rcx
  __int64 v6; // rax

  v1 = (char *)this + 208;
  if ( *((_BYTE *)this + 8) )
  {
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)this + 3));
    if ( Value )
    {
      v1 = Value;
    }
    else if ( !GetLastError() )
    {
      v5 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v5 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      v6 = ((__int64 (__fastcall *)(void ***))**v5)(v5);
      if ( v6 )
        v1 = (char *)v6;
    }
    SetLastError(LastError);
  }
  return (struct CallStackContext *)v1;
}

```

## disassembly

```asm
0x18009b9e4  mov     [rsp+arg_0], rbx
0x18009b9e9  mov     [rsp+arg_8], rsi
0x18009b9ee  push    rdi
0x18009b9ef  sub     rsp, 20h
0x18009b9f3  cmp     byte ptr [rcx+8], 0
0x18009b9f7  lea     rbx, [rcx+0D0h]
0x18009b9fe  mov     rdi, rcx
0x18009ba01  jz      short loc_18009BA74
0x18009ba03  call    cs:__imp_GetLastError
0x18009ba0a  nop     dword ptr [rax+rax+00h]
0x18009ba0f  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18009ba12  mov     esi, eax
0x18009ba14  call    cs:__imp_TlsGetValue
0x18009ba1b  nop     dword ptr [rax+rax+00h]
0x18009ba20  test    rax, rax
0x18009ba23  jz      short loc_18009BA2A
0x18009ba25  mov     rbx, rax
0x18009ba28  jmp     short loc_18009BA66
0x18009ba2a  call    cs:__imp_GetLastError
0x18009ba31  nop     dword ptr [rax+rax+00h]
0x18009ba36  test    eax, eax
0x18009ba38  jnz     short loc_18009BA66
0x18009ba3a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ba41  test    rcx, rcx
0x18009ba44  jnz     short loc_18009BA54
0x18009ba46  lea     rcx, off_1800E5190
0x18009ba4d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ba54  mov     rax, [rcx]
0x18009ba57  mov     rax, [rax]
0x18009ba5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ba5f  test    rax, rax
0x18009ba62  cmovnz  rbx, rax
0x18009ba66  mov     ecx, esi; dwErrCode
0x18009ba68  call    cs:__imp_SetLastError
0x18009ba6f  nop     dword ptr [rax+rax+00h]
0x18009ba74  mov     rsi, [rsp+28h+arg_8]
0x18009ba79  mov     rax, rbx
0x18009ba7c  mov     rbx, [rsp+28h+arg_0]
0x18009ba81  add     rsp, 20h
0x18009ba85  pop     rdi
0x18009ba86  retn
```
