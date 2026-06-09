# wil::details::static_lazy<DataSharingServiceProvider>::Completer::~Completer(void)

- ea: `0x18000441c`
- end: `0x180004476`
- name: `??1Completer@?$static_lazy@VDataSharingServiceProvider@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007008`

## callees

- `0x180001688`
- `0x18000441c`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000446f`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<DataSharingServiceProvider>::Completer::~Completer(_DWORD *a1)
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
0x18000441c  mov     [rsp+arg_0], rbx
0x180004421  push    rdi
0x180004422  sub     rsp, 20h
0x180004426  cmp     dword ptr [rcx+8], 0
0x18000442a  mov     rdi, rcx
0x18000442d  jnz     short loc_18000445B
0x18000442f  mov     rbx, [rcx]
0x180004432  mov     rcx, [rbx+20h]; CallbackContext
0x180004436  mov     [rbx+10h], rcx
0x18000443a  mov     byte ptr [rbx+18h], 1
0x18000443e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180004443  mov     rax, [rbx+8]
0x180004447  lea     rcx, [rbx+8]
0x18000444b  mov     dword ptr [rbx+1Ch], 1
0x180004452  mov     rax, [rax+8]
0x180004456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000445b  mov     rcx, [rdi]
0x18000445e  mov     edx, [rdi+8]
0x180004461  lea     r8, [rcx+8]
0x180004465  mov     rbx, [rsp+28h+arg_0]
0x18000446a  add     rsp, 20h
0x18000446e  pop     rdi
0x18000446f  jmp     cs:__imp_InitOnceComplete
```
