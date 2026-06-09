# wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x180024938`
- end: `0x1800249af`
- name: `??1?$ActivityData@VLanguageComponentsInstallerTelemetryProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800248c0`
- `0x180024a10`

## callees

- `0x1800066e8`
- `0x1800195c0`
- `0x180024764`
- `0x180024938`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002496b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002496b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002495d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002495d`

## pseudocode

```c
void __fastcall wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(
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
    v4 = (unsigned int *)LanguageComponentsInstallerTelemetryProvider::Provider();
    _tlgWriteActivityAutoStop<0,5>(v4, a1 + 8);
  }
  *(_DWORD *)a1 = 3;
}

```

## disassembly

```asm
0x180024938  mov     [rsp+arg_0], rbx
0x18002493d  mov     [rsp+arg_8], rsi
0x180024942  push    rdi
0x180024943  sub     rsp, 20h
0x180024947  mov     rdi, rcx
0x18002494a  add     rcx, 50h ; 'P'; this
0x18002494e  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x180024953  cmp     byte ptr [rdi+40h], 0
0x180024957  jz      short loc_180024975
0x180024959  mov     rbx, [rdi+38h]
0x18002495d  call    cs:__imp_GetProcessHeap
0x180024963  mov     r8, rbx; lpMem
0x180024966  xor     edx, edx; dwFlags
0x180024968  mov     rcx, rax; hHeap
0x18002496b  call    cs:__imp_HeapFree
0x180024971  mov     byte ptr [rdi+40h], 0
0x180024975  mov     qword ptr [rdi+38h], 0
0x18002497d  cmp     dword ptr [rdi], 1
0x180024980  jnz     short loc_180024999
0x180024982  mov     dword ptr [rdi], 2
0x180024988  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x18002498d  lea     rdx, [rdi+8]
0x180024991  mov     rcx, rax
0x180024994  call    ??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)
0x180024999  mov     rbx, [rsp+28h+arg_0]
0x18002499e  mov     rsi, [rsp+28h+arg_8]
0x1800249a3  mov     dword ptr [rdi], 3
0x1800249a9  add     rsp, 20h
0x1800249ad  pop     rdi
0x1800249ae  retn
```
