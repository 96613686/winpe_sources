# CopySID

- ea: `0x1800020dc`
- end: `0x180002133`
- name: `CopySID`
- size: `87`
- prototype: `__int64 __fastcall(PSID SourceSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003840`

## callees

- `0x1800020dc`
- `0x180010208`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800020f0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800020f0`
- `ntdll!RtlCopySid` at `0x18000211a`
- `ntdll!RtlCopySid` at `0x18000211a`

## pseudocode

```c
void *__fastcall CopySID(PSID SourceSid)
{
  void *v2; // rbx
  DWORD LengthSid; // eax
  ULONG v4; // edi
  void *v5; // rax

  v2 = 0;
  LengthSid = GetLengthSid(SourceSid);
  v4 = LengthSid;
  if ( LengthSid )
  {
    v5 = operator new[](LengthSid, (const struct std::nothrow_t *)&std::nothrow);
    v2 = v5;
    if ( v5 )
      RtlCopySid(v4, v5, SourceSid);
  }
  return v2;
}

```

## disassembly

```asm
0x1800020dc  mov     [rsp+arg_0], rbx
0x1800020e1  mov     [rsp+arg_8], rsi
0x1800020e6  push    rdi
0x1800020e7  sub     rsp, 20h
0x1800020eb  mov     rsi, rcx
0x1800020ee  xor     ebx, ebx
0x1800020f0  call    cs:__imp_GetLengthSid
0x1800020f6  mov     edi, eax
0x1800020f8  test    eax, eax
0x1800020fa  jz      short loc_180002120
0x1800020fc  mov     ecx, edi; unsigned __int64
0x1800020fe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002105  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000210a  mov     rbx, rax
0x18000210d  test    rax, rax
0x180002110  jz      short loc_180002120
0x180002112  mov     r8, rsi; SourceSid
0x180002115  mov     rdx, rax; DestinationSid
0x180002118  mov     ecx, edi; DestinationSidLength
0x18000211a  call    cs:__imp_RtlCopySid
0x180002120  mov     rsi, [rsp+28h+arg_8]
0x180002125  mov     rax, rbx
0x180002128  mov     rbx, [rsp+28h+arg_0]
0x18000212d  add     rsp, 20h
0x180002131  pop     rdi
0x180002132  retn
```
