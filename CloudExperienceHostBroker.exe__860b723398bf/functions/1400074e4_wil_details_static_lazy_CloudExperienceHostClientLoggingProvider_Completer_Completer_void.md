# wil::details::static_lazy<CloudExperienceHostClientLoggingProvider>::Completer::~Completer(void)

- ea: `0x1400074e4`
- end: `0x14000753e`
- name: `??1Completer@?$static_lazy@VCloudExperienceHostClientLoggingProvider@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400092b4`

## callees

- `0x1400015d4`
- `0x1400074e4`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140007537`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<CloudExperienceHostClientLoggingProvider>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  void *v3; // rcx
  __int64 v4; // rax

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    v3 = *(void **)(*(_QWORD *)a1 + 32LL);
    *(_QWORD *)(v2 + 16) = v3;
    *(_BYTE *)(v2 + 24) = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(v3);
    v4 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v4 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x1400074e4  mov     [rsp+arg_0], rbx
0x1400074e9  push    rdi
0x1400074ea  sub     rsp, 20h
0x1400074ee  cmp     dword ptr [rcx+8], 0
0x1400074f2  mov     rdi, rcx
0x1400074f5  jnz     short loc_140007523
0x1400074f7  mov     rbx, [rcx]
0x1400074fa  mov     rcx, [rbx+20h]; CallbackContext
0x1400074fe  mov     [rbx+10h], rcx
0x140007502  mov     byte ptr [rbx+18h], 1
0x140007506  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000750b  mov     rax, [rbx+8]
0x14000750f  lea     rcx, [rbx+8]
0x140007513  mov     dword ptr [rbx+1Ch], 1
0x14000751a  mov     rax, [rax+8]
0x14000751e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007523  mov     rcx, [rdi]
0x140007526  mov     edx, [rdi+8]
0x140007529  lea     r8, [rcx+8]
0x14000752d  mov     rbx, [rsp+28h+arg_0]
0x140007532  add     rsp, 20h
0x140007536  pop     rdi
0x140007537  jmp     cs:__imp_InitOnceComplete
```
