# wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x18000dd54`
- end: `0x18000ddcb`
- name: `??1?$ActivityData@VServiceHostLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000dcdc`
- `0x18000df78`
- `0x18000e2ec`

## callees

- `0x180004438`
- `0x18000a648`
- `0x18000d928`
- `0x18000dd54`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd79`

## pseudocode

```c
void __fastcall wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>(
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
    v4 = (unsigned int *)ServiceHostLogging::Provider();
    _tlgWriteActivityAutoStop<70368744177664,5>(v4, a1 + 8);
  }
  *(_DWORD *)a1 = 3;
}

```

## disassembly

```asm
0x18000dd54  mov     [rsp+arg_0], rbx
0x18000dd59  mov     [rsp+arg_8], rsi
0x18000dd5e  push    rdi
0x18000dd5f  sub     rsp, 20h
0x18000dd63  mov     rdi, rcx
0x18000dd66  add     rcx, 50h ; 'P'; this
0x18000dd6a  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x18000dd6f  cmp     byte ptr [rdi+40h], 0
0x18000dd73  jz      short loc_18000DD91
0x18000dd75  mov     rbx, [rdi+38h]
0x18000dd79  call    cs:__imp_GetProcessHeap
0x18000dd7f  mov     r8, rbx; lpMem
0x18000dd82  xor     edx, edx; dwFlags
0x18000dd84  mov     rcx, rax; hHeap
0x18000dd87  call    cs:__imp_HeapFree
0x18000dd8d  mov     byte ptr [rdi+40h], 0
0x18000dd91  mov     qword ptr [rdi+38h], 0
0x18000dd99  cmp     dword ptr [rdi], 1
0x18000dd9c  jnz     short loc_18000DDB5
0x18000dd9e  mov     dword ptr [rdi], 2
0x18000dda4  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000dda9  lea     rdx, [rdi+8]
0x18000ddad  mov     rcx, rax
0x18000ddb0  call    ??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)
0x18000ddb5  mov     rbx, [rsp+28h+arg_0]
0x18000ddba  mov     rsi, [rsp+28h+arg_8]
0x18000ddbf  mov     dword ptr [rdi], 3
0x18000ddc5  add     rsp, 20h
0x18000ddc9  pop     rdi
0x18000ddca  retn
```
