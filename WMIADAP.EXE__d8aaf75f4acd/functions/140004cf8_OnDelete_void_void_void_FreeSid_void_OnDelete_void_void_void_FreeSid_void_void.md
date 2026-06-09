# OnDelete<void *,void * (*)(void *),&FreeSid(void *)>::~OnDelete<void *,void * (*)(void *),&FreeSid(void *)>(void)

- ea: `0x140004cf8`
- end: `0x140004d0b`
- name: `??1?$OnDelete@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z@@QEAA@XZ`
- size: `19`
- prototype: `PVOID __fastcall(PSID *)`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001517d`
- `0x14001518f`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140004cff`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140004cff`

## pseudocode

```c
PVOID __fastcall OnDelete<void *,void * (*)(void *),&void * FreeSid(void *)>::~OnDelete<void *,void * (*)(void *),&void * FreeSid(void *)>(
        PSID *a1)
{
  return FreeSid(*a1);
}

```

## disassembly

```asm
0x140004cf8  sub     rsp, 28h
0x140004cfc  mov     rcx, [rcx]; pSid
0x140004cff  call    cs:__imp_FreeSid
0x140004d05  nop
0x140004d06  add     rsp, 28h
0x140004d0a  retn
```
