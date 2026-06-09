# CallStackTracing::GetThreadRelativeContext(void)

- ea: `0x1800035c0`
- end: `0x180003684`
- name: `?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ`
- size: `196`
- prototype: `struct CallStackContext *__fastcall(CallStackTracing *__hidden this)`
- caller_count: `241`
- callee_count: `2`
- tags: ``

## callers

- `0x180001780`
- `0x1800019a0`
- `0x180002260`
- `0x1800026f0`
- `0x180002a10`
- `0x180002f50`
- `0x180003690`
- `0x180003950`
- `0x180004b2c`
- `0x180005290`
- `0x180005a40`
- `0x180005ed0`
- `0x180007d00`
- `0x180008f00`
- `0x180009820`
- `0x180009c5c`
- `0x18000a0cc`
- `0x18000a420`
- `0x18000a940`
- `0x18000abc8`
- `0x18000b41c`
- `0x18000e288`
- `0x18000e680`
- `0x18000f2a0`
- `0x18000f4a0`
- `0x18000faf4`
- `0x180010110`
- `0x180010630`
- `0x180010bcc`
- `0x180010fcc`
- `0x1800115b0`
- `0x180011a70`
- `0x180011f08`
- `0x1800120e0`
- `0x180012230`
- `0x180012420`
- `0x180012900`
- `0x1800129ec`
- `0x180012ed0`
- `0x1800133b0`
- `0x180014a80`
- `0x180014e14`
- `0x1800153f0`
- `0x18001561c`
- `0x180015e7c`
- `0x180015fe8`
- `0x180016720`
- `0x1800169a0`
- `0x180016bf0`
- `0x1800189cc`

## callees

- `0x1800035c0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003635`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003608`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003608`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800035f8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800035f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180003641`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180003641`

## pseudocode

```c
struct CallStackContext *__fastcall CallStackTracing::GetThreadRelativeContext(CallStackTracing *this)
{
  char *v1; // rdi
  DWORD LastError; // esi
  char *Value; // rax
  __int64 *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdx
  CallStackTracing *v9; // rax

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
      v6 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        {
          v6 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v6 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      v7 = (*(__int64 (__fastcall **)(__int64 *))*v6)(v6);
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
0x1800035c0  mov     [rsp+arg_8], rbx
0x1800035c5  push    rdi
0x1800035c6  sub     rsp, 20h
0x1800035ca  cmp     byte ptr [rcx+8], 0
0x1800035ce  lea     rdi, [rcx+0D0h]
0x1800035d5  mov     rbx, rcx
0x1800035d8  jnz     short loc_1800035E8
0x1800035da  mov     rbx, [rsp+28h+arg_8]
0x1800035df  mov     rax, rdi
0x1800035e2  add     rsp, 20h
0x1800035e6  pop     rdi
0x1800035e7  retn
0x1800035e8  mov     [rsp+28h+arg_0], rsi
0x1800035ed  call    cs:__imp_GetLastError
0x1800035f3  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x1800035f6  mov     esi, eax
0x1800035f8  call    cs:__imp_TlsGetValue
0x1800035fe  test    rax, rax
0x180003601  jz      short loc_180003635
0x180003603  mov     rdi, rax
0x180003606  mov     ecx, esi; dwErrCode
0x180003608  call    cs:__imp_SetLastError
0x18000360e  mov     rsi, [rsp+28h+arg_0]
0x180003613  jmp     short loc_1800035DA
0x180003615  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000361c  test    rcx, rcx
0x18000361f  jz      short loc_180003641
0x180003621  mov     rax, [rcx]
0x180003624  mov     rax, [rax]
0x180003627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000362c  test    rax, rax
0x18000362f  cmovnz  rdi, rax
0x180003633  jmp     short loc_180003606
0x180003635  call    cs:__imp_GetLastError
0x18000363b  test    eax, eax
0x18000363d  jnz     short loc_180003606
0x18000363f  jmp     short loc_180003615
0x180003641  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180003647  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000364e  mov     rcx, rax
0x180003651  test    rax, rax
0x180003654  jz      short loc_180003674
0x180003656  mov     rax, [rax]
0x180003659  mov     edx, 7F0h
0x18000365e  mov     rax, [rax+8]
0x180003662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003667  test    eax, eax
0x180003669  jz      short loc_180003674
0x18000366b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180003672  jmp     short loc_180003621
0x180003674  lea     rcx, qword_180069A90
0x18000367b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180003682  jmp     short loc_180003621
```
