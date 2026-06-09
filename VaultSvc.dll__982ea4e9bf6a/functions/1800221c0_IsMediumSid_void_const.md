# IsMediumSid(void * const)

- ea: `0x1800221c0`
- end: `0x180022218`
- name: `?IsMediumSid@@YAHQEAX@Z`
- size: `88`
- prototype: `BOOL __fastcall(PSID pSid1)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180021650`
- `0x1800219a0`

## callees

- `0x1800221c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800221d5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800221e9`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800221fd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800221d5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800221e9`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800221fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __fastcall IsMediumSid(PSID pSid1)
{
  BOOL result; // eax

  if ( !pSid1 )
    return 1;
  if ( EqualSid(pSid1, pSid2) )
    return 1;
  if ( EqualSid(pSid1, qword_18005F730) )
    return 1;
  result = EqualSid(pSid1, qword_18005F728);
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x1800221c0  push    rbx
0x1800221c2  sub     rsp, 20h
0x1800221c6  mov     rbx, rcx
0x1800221c9  test    rcx, rcx
0x1800221cc  jz      short loc_18002220D
0x1800221ce  mov     rdx, cs:pSid2; pSid2
0x1800221d5  call    cs:__imp_EqualSid
0x1800221db  test    eax, eax
0x1800221dd  jnz     short loc_18002220D
0x1800221df  mov     rdx, cs:qword_18005F730; pSid2
0x1800221e6  mov     rcx, rbx; pSid1
0x1800221e9  call    cs:__imp_EqualSid
0x1800221ef  test    eax, eax
0x1800221f1  jnz     short loc_18002220D
0x1800221f3  mov     rdx, cs:qword_18005F728; pSid2
0x1800221fa  mov     rcx, rbx; pSid1
0x1800221fd  call    cs:__imp_EqualSid
0x180022203  test    eax, eax
0x180022205  jnz     short loc_18002220D
0x180022207  add     rsp, 20h
0x18002220b  pop     rbx
0x18002220c  retn
0x18002220d  mov     eax, 1
0x180022212  add     rsp, 20h
0x180022216  pop     rbx
0x180022217  retn
```
