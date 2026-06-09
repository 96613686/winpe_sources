# wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x1800121d8`
- end: `0x18001224f`
- name: `??1?$ActivityData@VLanguageComponentsInstallerTelemetryProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012160`
- `0x180015bb8`

## callees

- `0x1800066e8`
- `0x18000fac8`
- `0x1800121d8`
- `0x1800195c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001220b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001220b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800121fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800121fd`

## pseudocode

```c
void __fastcall wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(
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
    _tlgWriteActivityAutoStop<70368744177664,5>(v4, a1 + 8);
  }
  *(_DWORD *)a1 = 3;
}

```

## disassembly

```asm
0x1800121d8  mov     [rsp+arg_0], rbx
0x1800121dd  mov     [rsp+arg_8], rsi
0x1800121e2  push    rdi
0x1800121e3  sub     rsp, 20h
0x1800121e7  mov     rdi, rcx
0x1800121ea  add     rcx, 50h ; 'P'; this
0x1800121ee  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x1800121f3  cmp     byte ptr [rdi+40h], 0
0x1800121f7  jz      short loc_180012215
0x1800121f9  mov     rbx, [rdi+38h]
0x1800121fd  call    cs:__imp_GetProcessHeap
0x180012203  mov     r8, rbx; lpMem
0x180012206  xor     edx, edx; dwFlags
0x180012208  mov     rcx, rax; hHeap
0x18001220b  call    cs:__imp_HeapFree
0x180012211  mov     byte ptr [rdi+40h], 0
0x180012215  mov     qword ptr [rdi+38h], 0
0x18001221d  cmp     dword ptr [rdi], 1
0x180012220  jnz     short loc_180012239
0x180012222  mov     dword ptr [rdi], 2
0x180012228  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x18001222d  lea     rdx, [rdi+8]
0x180012231  mov     rcx, rax
0x180012234  call    ??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)
0x180012239  mov     rbx, [rsp+28h+arg_0]
0x18001223e  mov     rsi, [rsp+28h+arg_8]
0x180012243  mov     dword ptr [rdi], 3
0x180012249  add     rsp, 20h
0x18001224d  pop     rdi
0x18001224e  retn
```
