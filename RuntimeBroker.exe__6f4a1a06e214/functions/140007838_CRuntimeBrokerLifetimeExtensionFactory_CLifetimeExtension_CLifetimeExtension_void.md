# CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension::~CLifetimeExtension(void)

- ea: `0x140007838`
- end: `0x14000786d`
- name: `??1CLifetimeExtension@CRuntimeBrokerLifetimeExtensionFactory@@AEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006fb0`

## callees

- `0x1400068a0`
- `0x140007838`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x14000784b`
- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x14000784b`

## pseudocode

```c
void __fastcall CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension::~CLifetimeExtension(
        CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension *this)
{
  CRuntimeBrokerLifetimeExtensionFactory *v2; // rcx

  *(_QWORD *)this = &CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension::`vftable';
  CoReleaseServerProcess();
  v2 = (CRuntimeBrokerLifetimeExtensionFactory *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    *((_QWORD *)this + 2) = 0;
    CRuntimeBrokerLifetimeExtensionFactory::Release(v2);
  }
}

```

## disassembly

```asm
0x140007838  push    rbx
0x14000783a  sub     rsp, 20h
0x14000783e  lea     rax, ??_7CLifetimeExtension@CRuntimeBrokerLifetimeExtensionFactory@@6B@; const CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension::`vftable'
0x140007845  mov     rbx, rcx
0x140007848  mov     [rcx], rax
0x14000784b  call    cs:__imp_CoReleaseServerProcess
0x140007851  mov     rcx, [rbx+10h]; this
0x140007855  test    rcx, rcx
0x140007858  jz      short loc_140007867
0x14000785a  mov     qword ptr [rbx+10h], 0
0x140007862  call    ?Release@CRuntimeBrokerLifetimeExtensionFactory@@UEAAKXZ; CRuntimeBrokerLifetimeExtensionFactory::Release(void)
0x140007867  add     rsp, 20h
0x14000786b  pop     rbx
0x14000786c  retn
```
