# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x140007708`
- end: `0x140007762`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000b9d0`

## callees

- `0x140001a24`
- `0x140007708`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000775b`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    *(_QWORD *)(v2 + 16) = *(_QWORD *)(*(_QWORD *)a1 + 32LL);
    *(_BYTE *)(v2 + 24) = 1;
    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation();
    v3 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v3 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x140007708  mov     [rsp+arg_0], rbx
0x14000770d  push    rdi
0x14000770e  sub     rsp, 20h
0x140007712  cmp     dword ptr [rcx+8], 0
0x140007716  mov     rdi, rcx
0x140007719  jnz     short loc_140007747
0x14000771b  mov     rbx, [rcx]
0x14000771e  mov     rcx, [rbx+20h]
0x140007722  mov     [rbx+10h], rcx
0x140007726  mov     byte ptr [rbx+18h], 1
0x14000772a  call    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation
0x14000772f  mov     rax, [rbx+8]
0x140007733  lea     rcx, [rbx+8]
0x140007737  mov     dword ptr [rbx+1Ch], 1
0x14000773e  mov     rax, [rax+8]
0x140007742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007747  mov     rcx, [rdi]
0x14000774a  mov     edx, [rdi+8]
0x14000774d  lea     r8, [rcx+8]
0x140007751  mov     rbx, [rsp+28h+arg_0]
0x140007756  add     rsp, 20h
0x14000775a  pop     rdi
0x14000775b  jmp     cs:__imp_InitOnceComplete
```
