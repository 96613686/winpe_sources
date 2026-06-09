# wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DeviceCenterContextHandlersLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DeviceCenterContextHandlersLogging,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x180005b50`
- end: `0x180005bc7`
- name: `??1?$ActivityData@VDeviceCenterContextHandlersLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180005adc`
- `0x180005d1c`
- `0x180005f24`

## callees

- `0x1800057e8`
- `0x180005b50`
- `0x180005e3c`
- `0x180009170`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b83`

## pseudocode

```c
void __fastcall wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DeviceCenterContextHandlersLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DeviceCenterContextHandlersLogging,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int *v4; // rax

  wil::StoredFailureInfo::~StoredFailureInfo((wil::StoredFailureInfo *)(a1 + 80));
  if ( *(_BYTE *)(a1 + 64) )
  {
    v2 = *(void **)(a1 + 56);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    *(_BYTE *)(a1 + 64) = 0;
  }
  *(_QWORD *)(a1 + 56) = 0;
  if ( *(_DWORD *)a1 == 1 )
  {
    *(_DWORD *)a1 = 2;
    v4 = (unsigned int *)DeviceCenterContextHandlersLogging::Provider();
    _tlgWriteActivityAutoStop<35184372088832,5>(v4, a1 + 8);
  }
  *(_DWORD *)a1 = 3;
}

```

## disassembly

```asm
0x180005b50  mov     [rsp+arg_0], rbx
0x180005b55  mov     [rsp+arg_8], rsi
0x180005b5a  push    rdi
0x180005b5b  sub     rsp, 20h
0x180005b5f  mov     rdi, rcx
0x180005b62  add     rcx, 50h ; 'P'; this
0x180005b66  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x180005b6b  cmp     byte ptr [rdi+40h], 0
0x180005b6f  jz      short loc_180005B8D
0x180005b71  mov     rbx, [rdi+38h]
0x180005b75  call    cs:__imp_GetProcessHeap
0x180005b7b  mov     r8, rbx; lpMem
0x180005b7e  xor     edx, edx; dwFlags
0x180005b80  mov     rcx, rax; hHeap
0x180005b83  call    cs:__imp_HeapFree
0x180005b89  mov     byte ptr [rdi+40h], 0
0x180005b8d  mov     qword ptr [rdi+38h], 0
0x180005b95  cmp     dword ptr [rdi], 1
0x180005b98  jnz     short loc_180005BB1
0x180005b9a  mov     dword ptr [rdi], 2
0x180005ba0  call    ?Provider@DeviceCenterContextHandlersLogging@@SAPEBU_tlgProvider_t@@XZ; DeviceCenterContextHandlersLogging::Provider(void)
0x180005ba5  lea     rdx, [rdi+8]
0x180005ba9  mov     rcx, rax
0x180005bac  call    ??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)
0x180005bb1  mov     rbx, [rsp+28h+arg_0]
0x180005bb6  mov     rsi, [rsp+28h+arg_8]
0x180005bbb  mov     dword ptr [rdi], 3
0x180005bc1  add     rsp, 20h
0x180005bc5  pop     rdi
0x180005bc6  retn
```
