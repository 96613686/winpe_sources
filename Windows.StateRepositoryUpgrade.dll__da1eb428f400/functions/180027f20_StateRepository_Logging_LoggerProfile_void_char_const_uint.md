# StateRepository::Logging::LoggerProfile(void *,char const *,uint)

- ea: `0x180027f20`
- end: `0x180027f6f`
- name: `?LoggerProfile@Logging@StateRepository@@YAXPEAXPEBDI@Z`
- size: `79`
- prototype: `void __fastcall(StateRepository::Logging *__hidden this, void *, const char *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180027f20`
- `0x180029120`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027f3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027f3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027f46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027f46`

## pseudocode

```c
void __fastcall StateRepository::Logging::LoggerProfile(StateRepository::Logging *this, void *a2, const char *a3)
{
  int v3; // edi
  int v4; // esi
  char CurrentThreadId; // bl
  char CurrentProcessId; // al
  int v7; // edx
  int v8; // ecx

  v3 = (int)a3;
  v4 = (int)a2;
  if ( (byte_18004BB81 & 0x40) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessId = GetCurrentProcessId();
    McTemplateU0qsqq_EventWriteTransfer(v8, v7, v3, v4, CurrentProcessId, CurrentThreadId);
  }
}

```

## disassembly

```asm
0x180027f20  mov     [rsp+arg_0], rbx
0x180027f25  mov     [rsp+arg_8], rsi
0x180027f2a  push    rdi
0x180027f2b  sub     rsp, 30h
0x180027f2f  test    cs:byte_18004BB81, 40h
0x180027f36  mov     edi, r8d
0x180027f39  mov     rsi, rdx
0x180027f3c  jz      short loc_180027F5F
0x180027f3e  call    cs:__imp_GetCurrentThreadId
0x180027f44  mov     ebx, eax
0x180027f46  call    cs:__imp_GetCurrentProcessId
0x180027f4c  mov     r9, rsi
0x180027f4f  mov     [rsp+38h+var_10], ebx
0x180027f53  mov     r8d, edi
0x180027f56  mov     [rsp+38h+var_18], eax
0x180027f5a  call    McTemplateU0qsqq_EventWriteTransfer
0x180027f5f  mov     rbx, [rsp+38h+arg_0]
0x180027f64  mov     rsi, [rsp+38h+arg_8]
0x180027f69  add     rsp, 30h
0x180027f6d  pop     rdi
0x180027f6e  retn
```
