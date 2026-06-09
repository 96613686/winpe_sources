# CallStackTracing::GetThreadRelativeContext(void)

- ea: `0x18002a9bc`
- end: `0x18002aa7e`
- name: `?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ`
- size: `194`
- prototype: `struct CallStackContext *__fastcall(CallStackTracing *__hidden this)`
- caller_count: `80`
- callee_count: `2`
- tags: ``

## callers

- `0x18002a750`
- `0x18002a880`
- `0x18002ae0c`
- `0x18002afd0`
- `0x18002b100`
- `0x18002b628`
- `0x18002b7b0`
- `0x18002bdc0`
- `0x18002c4e0`
- `0x18002ddf0`
- `0x18002e250`
- `0x18002f56c`
- `0x1800302e0`
- `0x180030400`
- `0x180030510`
- `0x1800a5770`
- `0x1800a5ac0`
- `0x1800a761c`
- `0x1800a7910`
- `0x1800a7a60`
- `0x1800a7c88`
- `0x1800a84d0`
- `0x1800a86e0`
- `0x1800a9930`
- `0x1800a9b90`
- `0x1800aaf5c`
- `0x1800ab500`
- `0x1800ac0b0`
- `0x1800ac2d0`
- `0x1800ac420`
- `0x1800ac880`
- `0x1800ac9a0`
- `0x1800acb40`
- `0x1800ada38`
- `0x1800ae224`
- `0x1800ae3c0`
- `0x1800ae510`
- `0x1800aede0`
- `0x1800afb38`
- `0x1800afe40`
- `0x1800b00f0`
- `0x1800b0550`
- `0x1800b07d0`
- `0x1800b0950`
- `0x1800b0ac0`
- `0x1800b0c40`
- `0x1800b0e60`
- `0x1800b1220`
- `0x1800b13a0`
- `0x1800b15d0`

## callees

- `0x18002a9bc`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aa65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aa65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9fa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a9ea`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a9ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002aa10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002aa10`

## pseudocode

```c
struct CallStackContext *__fastcall CallStackTracing::GetThreadRelativeContext(CallStackTracing *this)
{
  char *v1; // rbx
  DWORD LastError; // esi
  char *Value; // rax
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  __int64 v7; // rax

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
      v5 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v6;
        if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
        {
          v5 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v5 = &qword_18015FF10;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
        }
      }
      v7 = (*(__int64 (__fastcall **)(__int64 *))*v5)(v5);
      if ( v7 )
        v1 = (char *)v7;
    }
    SetLastError(LastError);
  }
  return (struct CallStackContext *)v1;
}

```

## disassembly

```asm
0x18002a9bc  mov     [rsp+arg_0], rbx
0x18002a9c1  mov     [rsp+arg_8], rsi
0x18002a9c6  push    rdi
0x18002a9c7  sub     rsp, 20h
0x18002a9cb  cmp     byte ptr [rcx+8], 0
0x18002a9cf  lea     rbx, [rcx+0D0h]
0x18002a9d6  mov     rdi, rcx
0x18002a9d9  jz      loc_18002AA6B
0x18002a9df  call    cs:__imp_GetLastError
0x18002a9e5  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18002a9e8  mov     esi, eax
0x18002a9ea  call    cs:__imp_TlsGetValue
0x18002a9f0  test    rax, rax
0x18002a9f3  jz      short loc_18002A9FA
0x18002a9f5  mov     rbx, rax
0x18002a9f8  jmp     short loc_18002AA63
0x18002a9fa  call    cs:__imp_GetLastError
0x18002aa00  test    eax, eax
0x18002aa02  jnz     short loc_18002AA63
0x18002aa04  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002aa0b  test    rcx, rcx
0x18002aa0e  jnz     short loc_18002AA51
0x18002aa10  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002aa16  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002aa1d  mov     rcx, rax
0x18002aa20  test    rax, rax
0x18002aa23  jz      short loc_18002AA43
0x18002aa25  mov     rax, [rax]
0x18002aa28  mov     edx, 7F0h
0x18002aa2d  mov     rax, [rax+8]
0x18002aa31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa36  test    eax, eax
0x18002aa38  jz      short loc_18002AA43
0x18002aa3a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002aa41  jmp     short loc_18002AA51
0x18002aa43  lea     rcx, qword_18015FF10
0x18002aa4a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002aa51  mov     rax, [rcx]
0x18002aa54  mov     rax, [rax]
0x18002aa57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa5c  test    rax, rax
0x18002aa5f  cmovnz  rbx, rax
0x18002aa63  mov     ecx, esi; dwErrCode
0x18002aa65  call    cs:__imp_SetLastError
0x18002aa6b  mov     rsi, [rsp+28h+arg_8]
0x18002aa70  mov     rax, rbx
0x18002aa73  mov     rbx, [rsp+28h+arg_0]
0x18002aa78  add     rsp, 20h
0x18002aa7c  pop     rdi
0x18002aa7d  retn
```
