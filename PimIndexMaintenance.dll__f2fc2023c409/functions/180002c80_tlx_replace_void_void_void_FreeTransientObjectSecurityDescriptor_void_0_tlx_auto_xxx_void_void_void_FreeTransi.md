# tlx::replace<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0>(tlx::auto_xxx<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0> &)

- ea: `0x180002c80`
- end: `0x180002ca7`
- name: `??$replace@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@0@@Z`
- size: `39`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002df4`

## callees

- `0x180002c80`

## import_xrefs

- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180002c91`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180002c91`

## pseudocode

```c
_QWORD *__fastcall tlx::replace<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),0>(
        _QWORD *a1)
{
  if ( *a1 )
    FreeTransientObjectSecurityDescriptor();
  *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x180002c80  push    rbx
0x180002c82  sub     rsp, 20h
0x180002c86  mov     rbx, rcx
0x180002c89  mov     rcx, [rcx]
0x180002c8c  test    rcx, rcx
0x180002c8f  jz      short loc_180002C97
0x180002c91  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180002c97  mov     qword ptr [rbx], 0
0x180002c9e  mov     rax, rbx
0x180002ca1  add     rsp, 20h
0x180002ca5  pop     rbx
0x180002ca6  retn
```
