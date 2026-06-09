# KnownSid::Cleanup(void)

- ea: `0x180050bc8`
- end: `0x180050bfa`
- name: `?Cleanup@KnownSid@@QEAAXXZ`
- size: `50`
- prototype: `void __fastcall(KnownSid *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180050c00`
- `0x1800512a8`
- `0x180056220`

## callees

- `0x180050bc8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050bdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050bdf`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180050be7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180050be7`

## pseudocode

```c
void __fastcall KnownSid::Cleanup(KnownSid *this)
{
  void *v2; // rcx

  v2 = *(void **)this;
  if ( v2 )
  {
    if ( *((_BYTE *)this + 8) )
      FreeSid(v2);
    else
      LocalFree(v2);
  }
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x180050bc8  push    rbx
0x180050bca  sub     rsp, 20h
0x180050bce  mov     rbx, rcx
0x180050bd1  mov     rcx, [rcx]; pSid
0x180050bd4  test    rcx, rcx
0x180050bd7  jz      short loc_180050BED
0x180050bd9  cmp     byte ptr [rbx+8], 0
0x180050bdd  jnz     short loc_180050BE7
0x180050bdf  call    cs:__imp_LocalFree
0x180050be5  jmp     short loc_180050BED
0x180050be7  call    cs:__imp_FreeSid
0x180050bed  mov     qword ptr [rbx], 0
0x180050bf4  add     rsp, 20h
0x180050bf8  pop     rbx
0x180050bf9  retn
```
