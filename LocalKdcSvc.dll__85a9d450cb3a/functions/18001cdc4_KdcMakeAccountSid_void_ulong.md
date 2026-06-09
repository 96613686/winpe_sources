# KdcMakeAccountSid(void *,ulong)

- ea: `0x18001cdc4`
- end: `0x18001ce3e`
- name: `?KdcMakeAccountSid@@YAXPEAXK@Z`
- size: `122`
- prototype: `void __fastcall(PSID Sid, unsigned int)`
- caller_count: `13`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180016148`
- `0x180021eb4`
- `0x180027598`
- `0x1800280ac`
- `0x180028d24`
- `0x18002bdf4`
- `0x18002e6c4`
- `0x180040ebc`
- `0x18004dd60`
- `0x1800560a4`
- `0x18005d344`
- `0x18005e9ac`
- `0x18006afcc`

## callees

- `0x1800038f0`
- `0x180003908`
- `0x18001cdc4`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18001ce1b`
- `ntdll!RtlSubAuthoritySid` at `0x18001ce1b`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001ce0f`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001ce26`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001ce0f`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001ce26`
- `ntdll!RtlLengthSid` at `0x18001cddf`
- `ntdll!RtlLengthSid` at `0x18001cddf`

## pseudocode

```c
void __fastcall KdcMakeAccountSid(PSID Sid, ULONG a2)
{
  ULONG v4; // edi
  PUCHAR v5; // rax
  PUCHAR v6; // rax

  v4 = RtlLengthSid(GlobalDomainSid);
  memset_0(Sid, 0, 0x48u);
  if ( v4 < 0x44 )
  {
    memcpy_0(Sid, GlobalDomainSid, v4);
    v5 = RtlSubAuthorityCountSid(Sid);
    *RtlSubAuthoritySid(Sid, *v5) = a2;
    v6 = RtlSubAuthorityCountSid(Sid);
    ++*v6;
  }
}

```

## disassembly

```asm
0x18001cdc4  mov     [rsp+arg_0], rbx
0x18001cdc9  mov     [rsp+arg_8], rsi
0x18001cdce  push    rdi
0x18001cdcf  sub     rsp, 20h
0x18001cdd3  mov     rbx, rcx
0x18001cdd6  mov     esi, edx
0x18001cdd8  mov     rcx, cs:?GlobalDomainSid@@3PEAXEA; Sid
0x18001cddf  call    cs:__imp_RtlLengthSid
0x18001cde5  xor     edx, edx; Val
0x18001cde7  mov     rcx, rbx; void *
0x18001cdea  mov     edi, eax
0x18001cdec  lea     r8d, [rdx+48h]; Size
0x18001cdf0  call    memset_0
0x18001cdf5  cmp     edi, 44h ; 'D'
0x18001cdf8  jnb     short loc_18001CE2E
0x18001cdfa  mov     rdx, cs:?GlobalDomainSid@@3PEAXEA; Src
0x18001ce01  mov     r8d, edi; Size
0x18001ce04  mov     rcx, rbx; void *
0x18001ce07  call    memcpy_0
0x18001ce0c  mov     rcx, rbx; Sid
0x18001ce0f  call    cs:__imp_RtlSubAuthorityCountSid
0x18001ce15  mov     rcx, rbx; Sid
0x18001ce18  movzx   edx, byte ptr [rax]; SubAuthority
0x18001ce1b  call    cs:__imp_RtlSubAuthoritySid
0x18001ce21  mov     rcx, rbx; Sid
0x18001ce24  mov     [rax], esi
0x18001ce26  call    cs:__imp_RtlSubAuthorityCountSid
0x18001ce2c  inc     byte ptr [rax]
0x18001ce2e  mov     rbx, [rsp+28h+arg_0]
0x18001ce33  mov     rsi, [rsp+28h+arg_8]
0x18001ce38  add     rsp, 20h
0x18001ce3c  pop     rdi
0x18001ce3d  retn
```
