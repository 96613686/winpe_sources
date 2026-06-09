# wil::details::static_lazy<NaturalLanguageTelemetry>::Completer::~Completer(void)

- ea: `0x180031cd8`
- end: `0x180031d3b`
- name: `??1Completer@?$static_lazy@VNaturalLanguageTelemetry@@@details@wil@@QEAA@XZ`
- size: `99`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180031c0c`
- `0x1800a1b4b`

## callees

- `0x180031cd8`
- `0x1800361d4`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180031cff`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180031cff`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<NaturalLanguageTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v3; // rbx

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v3 = *(LPINIT_ONCE *)a1;
    v3[2].Ptr = NaturalLanguageTelemetryProvider::Provider();
    LOBYTE(v3[3].Ptr) = 0;
    HIDWORD(v3[3].Ptr) = 1;
    (*((void (__fastcall **)(LPINIT_ONCE))v3[1].Ptr + 1))(v3 + 1);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, *(_DWORD *)(a1 + 8), (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x180031cd8  push    rdi
0x180031cda  sub     rsp, 30h
0x180031cde  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180031ce7  mov     [rsp+38h+arg_0], rbx
0x180031cec  mov     rdi, rcx
0x180031cef  cmp     dword ptr [rcx+8], 0
0x180031cf3  jz      short loc_180031D11
0x180031cf5  mov     rcx, [rdi]; lpInitOnce
0x180031cf8  lea     r8, [rcx+8]; lpContext
0x180031cfc  mov     edx, [rdi+8]; dwFlags
0x180031cff  call    cs:__imp_InitOnceComplete
0x180031d05  nop
0x180031d06  mov     rbx, [rsp+38h+arg_0]
0x180031d0b  add     rsp, 30h
0x180031d0f  pop     rdi
0x180031d10  retn
0x180031d11  mov     rbx, [rcx]
0x180031d14  call    ?Provider@NaturalLanguageTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; NaturalLanguageTelemetryProvider::Provider(void)
0x180031d19  mov     [rbx+10h], rax
0x180031d1d  mov     byte ptr [rbx+18h], 0
0x180031d21  mov     dword ptr [rbx+1Ch], 1
0x180031d28  mov     rax, [rbx+8]
0x180031d2c  lea     rcx, [rbx+8]
0x180031d30  mov     rax, [rax+8]
0x180031d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d39  jmp     short loc_180031CF5
```
