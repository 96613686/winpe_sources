# ATL::CComContainedObject<CPimcManager>::~CComContainedObject<CPimcManager>(void)

- ea: `0x1800021e4`
- end: `0x18000221e`
- name: `??1?$CComContainedObject@VCPimcManager@@@ATL@@QEAA@XZ`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e563`
- `0x18000e626`

## callees

- `0x1800021e4`
- `0x180002264`
- `0x18000e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ATL::CComContainedObject<CPimcManager>::~CComContainedObject<CPimcManager>(__int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 32);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  return CPbList<CPimcManager::CHookWindowItem>::~CPbList<CPimcManager::CHookWindowItem>(a1 + 16);
}

```

## disassembly

```asm
0x1800021e4  mov     [rsp+arg_0], rcx
0x1800021e9  push    rbx
0x1800021ea  sub     rsp, 20h
0x1800021ee  mov     rbx, rcx
0x1800021f1  lea     rax, [rcx+20h]
0x1800021f5  mov     [rsp+28h+arg_8], rax
0x1800021fa  mov     rcx, [rax]
0x1800021fd  test    rcx, rcx
0x180002200  jz      short loc_180002210
0x180002202  mov     rax, [rcx]
0x180002205  mov     rax, [rax+10h]
0x180002209  call    cs:__guard_dispatch_icall_fptr
0x18000220f  nop
0x180002210  lea     rcx, [rbx+10h]
0x180002214  add     rsp, 20h
0x180002218  pop     rbx
0x180002219  jmp     ??1?$CPbList@UCHookWindowItem@CPimcManager@@@@QEAA@XZ; CPbList<CPimcManager::CHookWindowItem>::~CPbList<CPimcManager::CHookWindowItem>(void)
```
