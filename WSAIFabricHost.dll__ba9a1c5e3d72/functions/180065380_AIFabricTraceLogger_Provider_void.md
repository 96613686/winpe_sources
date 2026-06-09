# AIFabricTraceLogger::Provider(void)

- ea: `0x180065380`
- end: `0x18006546e`
- name: `?Provider@AIFabricTraceLogger@@SAPEBU_tlgProvider_t@@XZ`
- size: `238`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `52`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800560dc`
- `0x180056188`
- `0x18005648c`
- `0x1800566dc`
- `0x180056788`
- `0x180056834`
- `0x1800568e0`
- `0x180056cac`
- `0x180056d58`
- `0x180056fdc`
- `0x180057510`
- `0x180057574`
- `0x18005762c`
- `0x180057798`
- `0x180057850`
- `0x1800579bc`
- `0x180057a20`
- `0x180057b28`
- `0x180057d20`
- `0x180057da4`
- `0x180057e28`
- `0x180057eac`
- `0x18005a200`
- `0x18005cf54`
- `0x18005d8dc`
- `0x18005fff0`
- `0x1800601e0`
- `0x180061350`
- `0x180062158`
- `0x180062660`
- `0x18006caf8`
- `0x18006cb80`
- `0x18006cdf0`
- `0x18006ce70`
- `0x18006cf1c`
- `0x18006cf9c`
- `0x18006d01c`
- `0x18006d1a4`
- `0x18006d22c`
- `0x18006d2e8`
- `0x18006d368`
- `0x18006e878`
- `0x18006fe10`
- `0x1800706fc`
- `0x18007496c`
- `0x180078760`
- `0x180078a0c`
- `0x18007a260`
- `0x18007ad68`
- `0x18007ae6c`

## callees

- `0x1800016ac`
- `0x180005120`
- `0x180065380`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800653a8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800653a8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180065459`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180065459`

## pseudocode

```c
const struct _tlgProvider_t *AIFabricTraceLogger::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( __std_init_once_begin_initialize(&`AIFabricTraceLogger::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_1800AFC08 = 0;
    v2 = &qword_1800AFC00;
    qword_1800AFC00 = (__int64)&SearchIndexerTraceProvider::`vftable';
    byte_1800AFC10 = 0;
    dword_1800AFC14 = 0;
    qword_1800AFC18 = &`AIFabricTraceLogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_146d6cabc909b0255d1759d068a80e2e_::_lambda_invoker_cdecl_);
    qword_1800AFC08 = (__int64)qword_1800AFC18;
    byte_1800AFC10 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_1800AFC18);
    dword_1800AFC14 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800AFC00 + 8))(&qword_1800AFC00);
    InitOnceComplete(&`AIFabricTraceLogger::Instance'::`2'::wrapper, 0, &qword_1800AFC00);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x180065380  mov     rax, rsp
0x180065383  push    rbx
0x180065384  sub     rsp, 20h
0x180065388  lea     r9, [rax+10h]; lpContext
0x18006538c  mov     qword ptr [rax+10h], 0
0x180065394  lea     r8, [rax+8]; fPending
0x180065398  mov     dword ptr [rax+8], 0
0x18006539f  xor     edx, edx; dwFlags
0x1800653a1  lea     rcx, ?wrapper@?1??Instance@AIFabricTraceLogger@@KAPEAV2@XZ@4V?$static_lazy@VAIFabricTraceLogger@@@details@wil@@A; lpInitOnce
0x1800653a8  call    cs:__imp___std_init_once_begin_initialize
0x1800653ae  test    eax, eax
0x1800653b0  jz      loc_18006545F
0x1800653b6  cmp     [rsp+28h+arg_0], 0
0x1800653bb  jz      loc_18006545F
0x1800653c1  lea     rbx, qword_1800AFC00
0x1800653c8  mov     cs:qword_1800AFC08, 0
0x1800653d3  lea     rax, ??_7SearchIndexerTraceProvider@@6B@; const SearchIndexerTraceProvider::`vftable'
0x1800653da  mov     [rsp+28h+arg_8], rbx
0x1800653df  mov     cs:qword_1800AFC00, rax
0x1800653e6  mov     cs:byte_1800AFC10, 0
0x1800653ed  mov     cs:dword_1800AFC14, 0
0x1800653f7  lea     rax, ?__hInner@?1???0StaticHandle@AIFabricTraceLogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `AIFabricTraceLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800653fe  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_146d6cabc909b0255d1759d068a80e2e_@@CA@XZ; void (__cdecl *)()
0x180065405  mov     cs:qword_1800AFC18, rax
0x18006540c  call    atexit
0x180065411  mov     rcx, cs:qword_1800AFC18; CallbackContext
0x180065418  xor     r8d, r8d
0x18006541b  xor     edx, edx
0x18006541d  mov     cs:qword_1800AFC08, rcx
0x180065424  mov     cs:byte_1800AFC10, 1
0x18006542b  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180065430  mov     rax, cs:qword_1800AFC00
0x180065437  mov     rcx, rbx
0x18006543a  mov     cs:dword_1800AFC14, 1
0x180065444  mov     rax, [rax+8]
0x180065448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006544d  mov     r8, rbx; lpContext
0x180065450  lea     rcx, ?wrapper@?1??Instance@AIFabricTraceLogger@@KAPEAV2@XZ@4V?$static_lazy@VAIFabricTraceLogger@@@details@wil@@A; lpInitOnce
0x180065457  xor     edx, edx; dwFlags
0x180065459  call    cs:__imp_InitOnceComplete
0x18006545f  mov     rax, [rsp+28h+arg_8]
0x180065464  mov     rax, [rax+8]
0x180065468  add     rsp, 20h
0x18006546c  pop     rbx
0x18006546d  retn
```
