# CSecurityData::InitLock(void)

- ea: `0x18005acd0`
- end: `0x18005ad17`
- name: `?InitLock@CSecurityData@@QEAAJXZ`
- size: `71`
- prototype: `__int64 __fastcall(CSecurityData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006bfc8`

## callees

- `0x18005acd0`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18005ace7`
- `ntdll!RtlDeleteResource` at `0x18005ace7`
- `ntdll!RtlInitializeResource` at `0x18005acfa`
- `ntdll!RtlInitializeResource` at `0x18005acfa`

## pseudocode

```c
__int64 __fastcall CSecurityData::InitLock(CSecurityData *this)
{
  if ( byte_1800B2F80 )
  {
    RtlDeleteResource(&Resource);
    byte_1800B2F80 = 0;
  }
  RtlInitializeResource(&Resource);
  byte_1800B2F80 = 1;
  return 0;
}

```

## disassembly

```asm
0x18005acd0  push    rbx
0x18005acd2  sub     rsp, 20h
0x18005acd6  xor     ebx, ebx
0x18005acd8  cmp     cs:byte_1800B2F80, bl
0x18005acde  jz      short loc_18005ACF3
0x18005ace0  lea     rcx, Resource; Resource
0x18005ace7  call    cs:__imp_RtlDeleteResource
0x18005aced  mov     cs:byte_1800B2F80, bl
0x18005acf3  lea     rcx, Resource; Resource
0x18005acfa  call    cs:__imp_RtlInitializeResource
0x18005ad00  jmp     short loc_18005AD04
0x18005ad02  mov     ebx, eax
0x18005ad04  test    ebx, ebx
0x18005ad06  js      short loc_18005AD0F
0x18005ad08  mov     cs:byte_1800B2F80, 1
0x18005ad0f  mov     eax, ebx
0x18005ad11  add     rsp, 20h
0x18005ad15  pop     rbx
0x18005ad16  retn
```
