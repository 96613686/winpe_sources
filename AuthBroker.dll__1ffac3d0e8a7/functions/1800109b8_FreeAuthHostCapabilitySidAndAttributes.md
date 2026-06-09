# _FreeAuthHostCapabilitySidAndAttributes

- ea: `0x1800109b8`
- end: `0x1800109f8`
- name: `_FreeAuthHostCapabilitySidAndAttributes`
- size: `64`
- prototype: `void __fastcall(_SID_AND_ATTRIBUTES *capabilitySidAndAttributes, unsigned int capabilityCount)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ed84`
- `0x180010494`
- `0x180010e58`

## callees

- `0x1800109b8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800109da`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800109da`

## pseudocode

```c
void __fastcall FreeAuthHostCapabilitySidAndAttributes(
        _SID_AND_ATTRIBUTES *capabilitySidAndAttributes,
        unsigned int capabilityCount)
{
  unsigned int i; // ebx
  void *Sid; // rcx

  if ( capabilityCount )
  {
    for ( i = 0; i < capabilityCount; ++i )
    {
      Sid = capabilitySidAndAttributes[i].Sid;
      if ( Sid )
      {
        FreeSid(Sid);
        capabilitySidAndAttributes[i].Sid = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x1800109b8  test    capabilityCount, capabilityCount
0x1800109ba  jz      short locret_1800109F7
0x1800109bc  push    rbx
0x1800109bd  push    rbp
0x1800109be  push    rsi
0x1800109bf  push    rdi
0x1800109c0  sub     rsp, 28h
0x1800109c4  mov     esi, capabilityCount
0x1800109c6  mov     rbp, capabilitySidAndAttributes
0x1800109c9  xor     ebx, ebx
0x1800109cb  mov     edi, ebx
0x1800109cd  add     rdi, rdi
0x1800109d0  mov     capabilitySidAndAttributes, [rbp+rdi*8+0]; pSid
0x1800109d5  test    capabilitySidAndAttributes, capabilitySidAndAttributes
0x1800109d8  jz      short loc_1800109E9
0x1800109da  call    cs:__imp_FreeSid
0x1800109e0  mov     qword ptr [rbp+rdi*8+0], 0
0x1800109e9  inc     ebx
0x1800109eb  cmp     ebx, esi
0x1800109ed  jb      short loc_1800109CB
0x1800109ef  add     rsp, 28h
0x1800109f3  pop     rdi
0x1800109f4  pop     rsi
0x1800109f5  pop     rbp
0x1800109f6  pop     rbx
0x1800109f7  retn
```
