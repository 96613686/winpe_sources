# wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<EcoScoreTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<EcoScoreTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x180003048`
- end: `0x1800030bf`
- name: `??1?$ActivityData@VEcoScoreTaskTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VEcoScoreTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180002fd4`
- `0x1800032d8`

## callees

- `0x180002f5c`
- `0x180003048`
- `0x1800033f8`
- `0x180005760`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000306d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000306d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000307b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000307b`

## pseudocode

```c
void __fastcall wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<EcoScoreTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<EcoScoreTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>(
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
    v4 = (unsigned int *)EcoScoreTaskTelemetry::Provider();
    _tlgWriteActivityAutoStop<35184372088832,5>(v4, a1 + 8);
  }
  *(_DWORD *)a1 = 3;
}

```

## disassembly

```asm
0x180003048  mov     [rsp+arg_0], rbx
0x18000304d  mov     [rsp+arg_8], rsi
0x180003052  push    rdi
0x180003053  sub     rsp, 20h
0x180003057  mov     rdi, rcx
0x18000305a  add     rcx, 50h ; 'P'; this
0x18000305e  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x180003063  cmp     byte ptr [rdi+40h], 0
0x180003067  jz      short loc_180003085
0x180003069  mov     rbx, [rdi+38h]
0x18000306d  call    cs:__imp_GetProcessHeap
0x180003073  mov     r8, rbx; lpMem
0x180003076  xor     edx, edx; dwFlags
0x180003078  mov     rcx, rax; hHeap
0x18000307b  call    cs:__imp_HeapFree
0x180003081  mov     byte ptr [rdi+40h], 0
0x180003085  mov     qword ptr [rdi+38h], 0
0x18000308d  cmp     dword ptr [rdi], 1
0x180003090  jnz     short loc_1800030A9
0x180003092  mov     dword ptr [rdi], 2
0x180003098  call    ?Provider@EcoScoreTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; EcoScoreTaskTelemetry::Provider(void)
0x18000309d  lea     rdx, [rdi+8]
0x1800030a1  mov     rcx, rax
0x1800030a4  call    ??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)
0x1800030a9  mov     rbx, [rsp+28h+arg_0]
0x1800030ae  mov     rsi, [rsp+28h+arg_8]
0x1800030b3  mov     dword ptr [rdi], 3
0x1800030b9  add     rsp, 20h
0x1800030bd  pop     rdi
0x1800030be  retn
```
