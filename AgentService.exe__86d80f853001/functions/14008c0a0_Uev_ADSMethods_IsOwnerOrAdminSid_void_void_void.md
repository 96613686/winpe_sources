# Uev::ADSMethods::IsOwnerOrAdminSid(void *,void *,void *)

- ea: `0x14008c0a0`
- end: `0x14008c0dd`
- name: `?IsOwnerOrAdminSid@ADSMethods@Uev@@UEBA_NPEAX00@Z`
- size: `61`
- prototype: `bool(Uev::ADSMethods *__hidden this, void *, void *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x14008c0a0`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x14008c0b6`
- `ADVAPI32!EqualSid` at `0x14008c0c6`
- `ADVAPI32!EqualSid` at `0x14008c0b6`
- `ADVAPI32!EqualSid` at `0x14008c0c6`

## pseudocode

```c
bool __fastcall Uev::ADSMethods::IsOwnerOrAdminSid(Uev::ADSMethods *this, void *a2, void *a3, void *a4)
{
  BOOL v6; // eax

  if ( EqualSid(a2, a3) || (v6 = EqualSid(a2, a4)) )
    LOBYTE(v6) = 1;
  return v6;
}

```

## disassembly

```asm
0x14008c0a0  mov     [rsp+arg_0], rbx
0x14008c0a5  push    rdi
0x14008c0a6  sub     rsp, 20h
0x14008c0aa  mov     rbx, rdx
0x14008c0ad  mov     rdi, r9
0x14008c0b0  mov     rcx, rbx; pSid1
0x14008c0b3  mov     rdx, r8; pSid2
0x14008c0b6  call    cs:__imp_EqualSid
0x14008c0bc  test    eax, eax
0x14008c0be  jnz     short loc_14008C0D0
0x14008c0c0  mov     rdx, rdi; pSid2
0x14008c0c3  mov     rcx, rbx; pSid1
0x14008c0c6  call    cs:__imp_EqualSid
0x14008c0cc  test    eax, eax
0x14008c0ce  jz      short loc_14008C0D2
0x14008c0d0  mov     al, 1
0x14008c0d2  mov     rbx, [rsp+28h+arg_0]
0x14008c0d7  add     rsp, 20h
0x14008c0db  pop     rdi
0x14008c0dc  retn
```
