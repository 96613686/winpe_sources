# wil::details::static_lazy<CloudPrintHelperTelemetry>::Completer::~Completer(void)

- ea: `0x180012848`
- end: `0x18001289e`
- name: `??1Completer@?$static_lazy@VCloudPrintHelperTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e07c`

## callees

- `0x180012848`
- `0x18001a63c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180012897`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<CloudPrintHelperTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = CloudPrintHelperLogging::Provider();
    v3.Ptr = v2[1].Ptr;
    LOBYTE(v2[3].Ptr) = 0;
    HIDWORD(v2[3].Ptr) = 1;
    (*((void (__fastcall **)(LPINIT_ONCE))v3.Ptr + 1))(v2 + 1);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, *(_DWORD *)(a1 + 8), (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x180012848  mov     [rsp+arg_0], rbx
0x18001284d  push    rdi
0x18001284e  sub     rsp, 20h
0x180012852  cmp     dword ptr [rcx+8], 0
0x180012856  mov     rdi, rcx
0x180012859  jnz     short loc_180012883
0x18001285b  mov     rbx, [rcx]
0x18001285e  call    ?Provider@CloudPrintHelperLogging@@SAPEBU_tlgProvider_t@@XZ; CloudPrintHelperLogging::Provider(void)
0x180012863  mov     [rbx+10h], rax
0x180012867  lea     rcx, [rbx+8]
0x18001286b  mov     rax, [rbx+8]
0x18001286f  mov     byte ptr [rbx+18h], 0
0x180012873  mov     dword ptr [rbx+1Ch], 1
0x18001287a  mov     rax, [rax+8]
0x18001287e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012883  mov     rcx, [rdi]
0x180012886  mov     edx, [rdi+8]
0x180012889  lea     r8, [rcx+8]
0x18001288d  mov     rbx, [rsp+28h+arg_0]
0x180012892  add     rsp, 20h
0x180012896  pop     rdi
0x180012897  jmp     cs:__imp_InitOnceComplete
```
