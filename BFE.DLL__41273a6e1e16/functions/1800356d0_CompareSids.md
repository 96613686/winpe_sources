# CompareSids

- ea: `0x1800356d0`
- end: `0x180035763`
- name: `CompareSids`
- size: `147`
- prototype: `__int64 __fastcall(PSID Sid, PSID)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019850`

## callees

- `0x1800356d0`
- `0x18008ad60`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x1800356f0`
- `ntdll!RtlEqualSid` at `0x1800356f0`
- `ntdll!RtlSubAuthorityCountSid` at `0x18008cae4`
- `ntdll!RtlSubAuthorityCountSid` at `0x18008caf6`
- `ntdll!RtlSubAuthorityCountSid` at `0x18008cae4`
- `ntdll!RtlSubAuthorityCountSid` at `0x18008caf6`

## pseudocode

```c
__int64 __fastcall CompareSids(char *Sid, char *a2)
{
  BOOLEAN v4; // al
  unsigned int v5; // ecx
  int v7; // ecx
  unsigned int v8; // edi
  __int64 v9; // r8

  if ( !Sid )
    return a2 != 0;
  if ( !a2 )
    return 0xFFFFFFFFLL;
  if ( Sid[1] != 1 && a2[1] != 1 )
  {
    if ( *Sid != *a2 )
      return 2;
    v7 = *(_DWORD *)(Sid + 2) - *(_DWORD *)(a2 + 2);
    if ( !v7 )
      v7 = *((unsigned __int16 *)Sid + 3) - *((unsigned __int16 *)a2 + 3);
    if ( v7 )
      return 2;
    v8 = *RtlSubAuthorityCountSid(Sid);
    v9 = *RtlSubAuthorityCountSid(a2);
    if ( (unsigned __int8)v8 <= (unsigned __int8)v9 )
      v9 = v8;
    if ( memcmp_0(Sid + 8, a2 + 8, 4 * v9) )
      return 2;
    return 0;
  }
  v4 = RtlEqualSid(Sid, a2);
  v5 = 2;
  if ( v4 )
    return 0;
  return v5;
}

```

## disassembly

```asm
0x1800356d0  mov     [rsp+arg_8], rbx
0x1800356d5  push    rsi
0x1800356d6  sub     rsp, 20h
0x1800356da  mov     rsi, rdx
0x1800356dd  mov     rbx, rcx
0x1800356e0  test    rcx, rcx
0x1800356e3  jz      short loc_180035716
0x1800356e5  test    rdx, rdx
0x1800356e8  jz      short loc_180035730
0x1800356ea  cmp     byte ptr [rcx+1], 1
0x1800356ee  jnz     short loc_180035737
0x1800356f0  call    cs:__imp_RtlEqualSid
0x1800356f7  nop     dword ptr [rax+rax+00h]
0x1800356fc  xor     edx, edx
0x1800356fe  mov     ecx, 2
0x180035703  test    al, al
0x180035705  cmovnz  ecx, edx
0x180035708  mov     eax, ecx
0x18003570a  mov     rbx, [rsp+28h+arg_8]
0x18003570f  add     rsp, 20h
0x180035713  pop     rsi
0x180035714  retn
0x180035716  test    rsi, rsi
0x180035719  jz      short loc_18003572C
0x18003571b  mov     rbx, [rsp+28h+arg_8]
0x180035720  mov     eax, 1
0x180035725  add     rsp, 20h
0x180035729  pop     rsi
0x18003572a  retn
0x18003572c  xor     eax, eax
0x18003572e  jmp     short loc_18003570A
0x180035730  mov     eax, 0FFFFFFFFh
0x180035735  jmp     short loc_18003570A
0x180035737  cmp     byte ptr [rdx+1], 1
0x18003573b  jz      short loc_1800356F0
0x18003573d  movzx   eax, byte ptr [rdx]
0x180035740  cmp     [rcx], al
0x180035742  jnz     loc_18008CB2B
0x180035748  mov     ecx, [rcx+2]
0x18003574b  sub     ecx, [rdx+2]
0x18003574e  jnz     loc_18008CAD8
0x180035754  movzx   ecx, word ptr [rbx+6]
0x180035758  movzx   eax, word ptr [rdx+6]
0x18003575c  sub     ecx, eax
0x18003575e  jmp     loc_18008CAD8
0x18008cad8  test    ecx, ecx
0x18008cada  jnz     short loc_18008CB2B
0x18008cadc  mov     rcx, rbx; Sid
0x18008cadf  mov     [rsp+28h+arg_0], rdi
0x18008cae4  call    cs:__imp_RtlSubAuthorityCountSid
0x18008caeb  nop     dword ptr [rax+rax+00h]
0x18008caf0  mov     rcx, rsi; Sid
0x18008caf3  movzx   edi, byte ptr [rax]
0x18008caf6  call    cs:__imp_RtlSubAuthorityCountSid
0x18008cafd  nop     dword ptr [rax+rax+00h]
0x18008cb02  lea     rdx, [rsi+8]; Buf2
0x18008cb06  lea     rcx, [rbx+8]; Buf1
0x18008cb0a  movzx   r8d, byte ptr [rax]
0x18008cb0e  cmp     dil, r8b
0x18008cb11  cmovbe  r8d, edi
0x18008cb15  shl     r8, 2; Size
0x18008cb19  call    memcmp_0
0x18008cb1e  mov     rdi, [rsp+28h+arg_0]
0x18008cb23  test    eax, eax
0x18008cb25  jz      loc_18003572C
0x18008cb2b  mov     eax, 2
0x18008cb30  jmp     loc_18003570A
```
