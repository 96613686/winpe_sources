# WinApiLite::CreateWellKnownSid(WELL_KNOWN_SID_TYPE,void *,void *,ulong *)

- ea: `0x1800169f0`
- end: `0x180016a0a`
- name: `?CreateWellKnownSid@WinApiLite@@UEAAHW4WELL_KNOWN_SID_TYPE@@PEAX1PEAK@Z`
- size: `26`
- prototype: `BOOL __fastcall(WinApiLite *this, enum WELL_KNOWN_SID_TYPE, void *, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180016a03`

## pseudocode

```c
BOOL __fastcall WinApiLite::CreateWellKnownSid(
        WinApiLite *this,
        enum WELL_KNOWN_SID_TYPE a2,
        void *a3,
        void *a4,
        unsigned int *a5)
{
  return CreateWellKnownSid(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x1800169f0  mov     rax, r9
0x1800169f3  mov     r10, r8
0x1800169f6  mov     r9, [rsp+arg_20]
0x1800169fb  mov     ecx, edx
0x1800169fd  mov     r8, rax
0x180016a00  mov     rdx, r10
0x180016a03  jmp     cs:__imp_CreateWellKnownSid
```
