# GameInputServerManager::~GameInputServerManager(void)

- ea: `0x140001718`
- end: `0x1400017c1`
- name: `??1GameInputServerManager@@QEAA@XZ`
- size: `169`
- prototype: `void __fastcall(GameInputServerManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140005a88`

## callees

- `0x140001718`
- `0x14000652c`
- `0x140008010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x14000176b`
- `ntdll!RtlFreeHeap` at `0x1400017b0`
- `ntdll!RtlFreeHeap` at `0x14000176b`
- `ntdll!RtlFreeHeap` at `0x1400017b0`

## pseudocode

```c
void __fastcall GameInputServerManager::~GameInputServerManager(GameInputServerManager *this)
{
  __int64 v2; // rcx
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  __int64 v4; // rcx
  struct _RTL_CRITICAL_SECTION *v5; // rbx

  v2 = *((_QWORD *)this + 1);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = *(struct _RTL_CRITICAL_SECTION **)this;
  *(_QWORD *)this = 0;
  if ( v3 )
  {
    GameInputModule::~GameInputModule(v3);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  }
  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 1) = 0;
  }
  v5 = *(struct _RTL_CRITICAL_SECTION **)this;
  if ( v5 )
  {
    GameInputModule::~GameInputModule(v5);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  }
}

```

## disassembly

```asm
0x140001718  mov     [rsp+arg_0], rbx
0x14000171d  push    rdi
0x14000171e  sub     rsp, 20h
0x140001722  mov     rbx, rcx
0x140001725  mov     rcx, [rcx+8]
0x140001729  test    rcx, rcx
0x14000172c  jz      short loc_140001742
0x14000172e  mov     rax, [rcx]
0x140001731  mov     rax, [rax+10h]
0x140001735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000173a  mov     qword ptr [rbx+8], 0
0x140001742  mov     rdi, [rbx]
0x140001745  mov     qword ptr [rbx], 0
0x14000174c  test    rdi, rdi
0x14000174f  jz      short loc_140001771
0x140001751  mov     rcx, rdi; this
0x140001754  call    ??1GameInputModule@@QEAA@XZ; GameInputModule::~GameInputModule(void)
0x140001759  mov     rcx, gs:60h
0x140001762  mov     r8, rdi; P
0x140001765  xor     edx, edx; Flags
0x140001767  mov     rcx, [rcx+30h]; HeapHandle
0x14000176b  call    cs:__imp_RtlFreeHeap
0x140001771  mov     rcx, [rbx+8]
0x140001775  test    rcx, rcx
0x140001778  jz      short loc_14000178E
0x14000177a  mov     rax, [rcx]
0x14000177d  mov     rax, [rax+10h]
0x140001781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001786  mov     qword ptr [rbx+8], 0
0x14000178e  mov     rbx, [rbx]
0x140001791  test    rbx, rbx
0x140001794  jz      short loc_1400017B6
0x140001796  mov     rcx, rbx; this
0x140001799  call    ??1GameInputModule@@QEAA@XZ; GameInputModule::~GameInputModule(void)
0x14000179e  mov     rcx, gs:60h
0x1400017a7  mov     r8, rbx; P
0x1400017aa  xor     edx, edx; Flags
0x1400017ac  mov     rcx, [rcx+30h]; HeapHandle
0x1400017b0  call    cs:__imp_RtlFreeHeap
0x1400017b6  mov     rbx, [rsp+28h+arg_0]
0x1400017bb  add     rsp, 20h
0x1400017bf  pop     rdi
0x1400017c0  retn
```
