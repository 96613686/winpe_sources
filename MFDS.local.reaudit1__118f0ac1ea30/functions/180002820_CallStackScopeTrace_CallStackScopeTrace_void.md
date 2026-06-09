# CallStackScopeTrace::~CallStackScopeTrace(void)

- ea: `0x180002820`
- end: `0x180002958`
- name: `??1CallStackScopeTrace@@QEAA@XZ`
- size: `312`
- prototype: `void __fastcall(CallStackScopeTrace *__hidden this)`
- caller_count: `775`
- callee_count: `2`
- tags: ``

## callers

- `0x180001530`
- `0x180002960`
- `0x1800036b0`
- `0x180004fd8`
- `0x180005050`
- `0x1800051e0`
- `0x18000524c`
- `0x180005380`
- `0x1800056a4`
- `0x180006800`
- `0x180007230`
- `0x1800098e0`
- `0x180009980`
- `0x180009d98`
- `0x18000a4e0`
- `0x18000aa74`
- `0x18000ab30`
- `0x18000abec`
- `0x18000acb0`
- `0x18000ae18`
- `0x18000aec8`
- `0x18000afc8`
- `0x18000b21c`
- `0x18000ba00`
- `0x18000bf80`
- `0x18000c664`
- `0x18000ca98`
- `0x18000cdd0`
- `0x18000cf70`
- `0x18000d010`
- `0x18000d1d0`
- `0x18000d2d4`
- `0x18000d41c`
- `0x18000d768`
- `0x18000dbd0`
- `0x18000deac`
- `0x18000e030`
- `0x18000e334`
- `0x18000e48c`
- `0x18000e784`
- `0x18000ea84`
- `0x18000eb90`
- `0x18000f718`
- `0x18000fa00`
- `0x18000fb3c`
- `0x18000fd30`
- `0x180010380`
- `0x180010400`
- `0x180011260`
- `0x180011950`

## callees

- `0x180002820`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000286f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000286f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028be`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002859`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002859`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000290f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000290f`

## pseudocode

```c
void __fastcall CallStackScopeTrace::~CallStackScopeTrace(CallStackScopeTrace *this)
{
  CallStackTracing *v1; // rbx
  GUID *v2; // rdi
  DWORD LastError; // esi
  GUID *Value; // rax
  int v5; // eax
  int v6; // eax
  CallStackTracing *v7; // rcx
  __int64 v8; // rax
  CallStackTracing *v9; // rax

  v1 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v2 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    LastError = GetLastError();
    Value = (GUID *)TlsGetValue(*((_DWORD *)v1 + 3));
    if ( Value )
    {
      v2 = Value;
    }
    else if ( !GetLastError() )
    {
      v7 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        {
          v7 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v7 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v8 = (**(__int64 (__fastcall ***)(CallStackTracing *))v7)(v7);
      if ( v8 )
        v2 = (GUID *)v8;
    }
    SetLastError(LastError);
    v5 = *(_DWORD *)&v2[124].Data2;
    if ( v5 )
    {
      v6 = v5 - 1;
      *(_DWORD *)&v2[124].Data2 = v6;
      if ( !v6 )
      {
        *(_DWORD *)&v2[124].Data2 = 0;
        *(_QWORD *)&v2[126].Data1 = 0;
        *(_DWORD *)&v2[124].Data4[4] = 0;
        v2[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v2[126].Data4 = 0;
        v2[124].Data1 = GetCurrentThreadId();
      }
    }
  }
}

```

## disassembly

```asm
0x180002820  push    rbx
0x180002822  sub     rsp, 20h
0x180002826  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000282d  cmp     byte ptr [rbx+8], 0
0x180002831  jz      loc_1800028D5
0x180002837  mov     [rsp+28h+arg_8], rdi
0x18000283c  lea     rdi, [rbx+0D0h]
0x180002843  mov     [rsp+28h+arg_0], rsi
0x180002848  call    cs:__imp_GetLastError
0x18000284f  nop     dword ptr [rax+rax+00h]
0x180002854  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180002857  mov     esi, eax
0x180002859  call    cs:__imp_TlsGetValue
0x180002860  nop     dword ptr [rax+rax+00h]
0x180002865  test    rax, rax
0x180002868  jz      short loc_1800028DC
0x18000286a  mov     rdi, rax
0x18000286d  mov     ecx, esi; dwErrCode
0x18000286f  call    cs:__imp_SetLastError
0x180002876  nop     dword ptr [rax+rax+00h]
0x18000287b  mov     eax, [rdi+7C4h]
0x180002881  mov     rsi, [rsp+28h+arg_0]
0x180002886  test    eax, eax
0x180002888  jz      short loc_1800028D0
0x18000288a  sub     eax, 1
0x18000288d  mov     [rdi+7C4h], eax
0x180002893  jnz     short loc_1800028D0
0x180002895  xor     eax, eax
0x180002897  mov     [rdi+7C4h], eax
0x18000289d  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800028a4  mov     [rdi+7E0h], rax
0x1800028ab  mov     [rdi+7CCh], eax
0x1800028b1  movups  xmmword ptr [rdi+7D0h], xmm0
0x1800028b8  mov     [rdi+7E8h], eax
0x1800028be  call    cs:__imp_GetCurrentThreadId
0x1800028c5  nop     dword ptr [rax+rax+00h]
0x1800028ca  mov     [rdi+7C0h], eax
0x1800028d0  mov     rdi, [rsp+28h+arg_8]
0x1800028d5  add     rsp, 20h
0x1800028d9  pop     rbx
0x1800028da  retn
0x1800028dc  call    cs:__imp_GetLastError
0x1800028e3  nop     dword ptr [rax+rax+00h]
0x1800028e8  test    eax, eax
0x1800028ea  jnz     short loc_18000286D
0x1800028ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800028f3  test    rcx, rcx
0x1800028f6  jz      short loc_18000290F
0x1800028f8  mov     rax, [rcx]
0x1800028fb  mov     rax, [rax]
0x1800028fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002903  test    rax, rax
0x180002906  cmovnz  rdi, rax
0x18000290a  jmp     loc_18000286D
0x18000290f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180002916  nop     dword ptr [rax+rax+00h]
0x18000291b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180002922  mov     rcx, rax
0x180002925  test    rax, rax
0x180002928  jz      short loc_180002948
0x18000292a  mov     rax, [rax]
0x18000292d  mov     edx, 7F0h
0x180002932  mov     rax, [rax+8]
0x180002936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000293b  test    eax, eax
0x18000293d  jz      short loc_180002948
0x18000293f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180002946  jmp     short loc_1800028F8
0x180002948  lea     rcx, qword_1800EB130
0x18000294f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180002956  jmp     short loc_1800028F8
```
