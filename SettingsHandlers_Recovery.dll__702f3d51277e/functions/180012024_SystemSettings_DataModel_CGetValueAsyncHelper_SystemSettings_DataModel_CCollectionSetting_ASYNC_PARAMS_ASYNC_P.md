# SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::ASYNC_PARAMS::~ASYNC_PARAMS(void)

- ea: `0x180012024`
- end: `0x1800120a3`
- name: `??1ASYNC_PARAMS@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAA@XZ`
- size: `127`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180021150`
- `0x180021370`
- `0x1800235b0`

## callees

- `0x180012024`
- `0x18002b010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001205c`
- `ole32!CoTaskMemFree` at `0x18001205c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012036`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012036`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001204a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001204a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::ASYNC_PARAMS::~ASYNC_PARAMS(
        __int64 *a1)
{
  HMODULE v2; // rcx
  char *v3; // rcx
  void *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = (HMODULE)a1[5];
  if ( v2 )
    FreeLibrary(v2);
  v3 = (char *)a1[3];
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v3);
  v4 = (void *)a1[2];
  a1[2] = 0;
  CoTaskMemFree(v4);
  v5 = a1[1];
  if ( v5 )
  {
    a1[1] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
}

```

## disassembly

```asm
0x180012024  push    rbx
0x180012026  sub     rsp, 20h
0x18001202a  mov     rbx, rcx
0x18001202d  mov     rcx, [rcx+28h]; hLibModule
0x180012031  test    rcx, rcx
0x180012034  jz      short loc_18001203C
0x180012036  call    cs:__imp_FreeLibrary
0x18001203c  mov     rcx, [rbx+18h]; hObject
0x180012040  lea     rax, [rcx-1]
0x180012044  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012048  ja      short loc_180012050
0x18001204a  call    cs:__imp_CloseHandle
0x180012050  mov     rcx, [rbx+10h]; pv
0x180012054  mov     qword ptr [rbx+10h], 0
0x18001205c  call    cs:__imp_CoTaskMemFree
0x180012062  nop
0x180012063  mov     rcx, [rbx+8]
0x180012067  test    rcx, rcx
0x18001206a  jz      short loc_180012081
0x18001206c  mov     qword ptr [rbx+8], 0
0x180012074  mov     rax, [rcx]
0x180012077  mov     rax, [rax+10h]
0x18001207b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012080  nop
0x180012081  mov     rcx, [rbx]
0x180012084  test    rcx, rcx
0x180012087  jz      short loc_18001209D
0x180012089  mov     qword ptr [rbx], 0
0x180012090  mov     rax, [rcx]
0x180012093  mov     rax, [rax+10h]
0x180012097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001209c  nop
0x18001209d  add     rsp, 20h
0x1800120a1  pop     rbx
0x1800120a2  retn
```
