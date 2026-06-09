# CSecurityData::~CSecurityData(void)

- ea: `0x18005a21c`
- end: `0x18005a251`
- name: `??1CSecurityData@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CSecurityData *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009bf40`

## callees

- `0x18000e9a4`
- `0x18005a21c`
- `0x18005a284`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18005a23a`
- `ntdll!RtlDeleteResource` at `0x18005a23a`

## pseudocode

```c
void __fastcall CSecurityData::~CSecurityData(CSecurityData *this)
{
  CSecurityData::Cleanup(this);
  if ( *((_BYTE *)this + 560) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 464));
  std::vector<unsigned int>::_Tidy((char *)this + 416);
}

```

## disassembly

```asm
0x18005a21c  push    rbx
0x18005a21e  sub     rsp, 20h
0x18005a222  mov     rbx, rcx
0x18005a225  call    ?Cleanup@CSecurityData@@QEAAXXZ; CSecurityData::Cleanup(void)
0x18005a22a  cmp     byte ptr [rbx+230h], 0
0x18005a231  jz      short loc_18005A240
0x18005a233  lea     rcx, [rbx+1D0h]; Resource
0x18005a23a  call    cs:__imp_RtlDeleteResource
0x18005a240  lea     rcx, [rbx+1A0h]
0x18005a247  add     rsp, 20h
0x18005a24b  pop     rbx
0x18005a24c  jmp     ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
```
