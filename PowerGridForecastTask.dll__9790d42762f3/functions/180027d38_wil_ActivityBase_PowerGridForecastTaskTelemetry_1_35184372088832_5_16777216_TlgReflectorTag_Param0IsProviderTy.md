# wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PowerGridForecastTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<PowerGridForecastTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x180027d38`
- end: `0x180027daf`
- name: `??1?$ActivityData@VPowerGridForecastTaskTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPowerGridForecastTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180027cc4`
- `0x180028468`

## callees

- `0x180027a1c`
- `0x180027d38`
- `0x18002866c`
- `0x18002befc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027d6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027d6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027d5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027d5d`

## pseudocode

```c
void __fastcall wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PowerGridForecastTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<PowerGridForecastTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>(
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
    v4 = (unsigned int *)PowerGridForecastTaskTelemetry::Provider();
    _tlgWriteActivityAutoStop<35184372088832,5>(v4, a1 + 8);
  }
  *(_DWORD *)a1 = 3;
}

```

## disassembly

```asm
0x180027d38  mov     [rsp+arg_0], rbx
0x180027d3d  mov     [rsp+arg_8], rsi
0x180027d42  push    rdi
0x180027d43  sub     rsp, 20h
0x180027d47  mov     rdi, rcx
0x180027d4a  add     rcx, 50h ; 'P'; this
0x180027d4e  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x180027d53  cmp     byte ptr [rdi+40h], 0
0x180027d57  jz      short loc_180027D75
0x180027d59  mov     rbx, [rdi+38h]
0x180027d5d  call    cs:__imp_GetProcessHeap
0x180027d63  mov     r8, rbx; lpMem
0x180027d66  xor     edx, edx; dwFlags
0x180027d68  mov     rcx, rax; hHeap
0x180027d6b  call    cs:__imp_HeapFree
0x180027d71  mov     byte ptr [rdi+40h], 0
0x180027d75  mov     qword ptr [rdi+38h], 0
0x180027d7d  cmp     dword ptr [rdi], 1
0x180027d80  jnz     short loc_180027D99
0x180027d82  mov     dword ptr [rdi], 2
0x180027d88  call    ?Provider@PowerGridForecastTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; PowerGridForecastTaskTelemetry::Provider(void)
0x180027d8d  lea     rdx, [rdi+8]
0x180027d91  mov     rcx, rax
0x180027d94  call    ??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)
0x180027d99  mov     rbx, [rsp+28h+arg_0]
0x180027d9e  mov     rsi, [rsp+28h+arg_8]
0x180027da3  mov     dword ptr [rdi], 3
0x180027da9  add     rsp, 20h
0x180027dad  pop     rdi
0x180027dae  retn
```
