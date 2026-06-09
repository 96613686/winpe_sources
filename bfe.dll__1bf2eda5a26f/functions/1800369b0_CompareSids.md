# CompareSids

- ea: `0x1800369b0`
- end: `0x180036a3b`
- name: `CompareSids`
- size: `139`
- prototype: `__int64 __fastcall(PSID Sid, PSID)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180018bf0`

## callees

- `0x1800369b0`
- `0x180087dc0`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x1800369d0`
- `ntdll!RtlEqualSid` at `0x1800369d0`
- `ntdll!RtlSubAuthorityCountSid` at `0x180089f80`
- `ntdll!RtlSubAuthorityCountSid` at `0x180089f8c`
- `ntdll!RtlSubAuthorityCountSid` at `0x180089f80`
- `ntdll!RtlSubAuthorityCountSid` at `0x180089f8c`

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
0x1800369b0  mov     [rsp+arg_8], rbx
0x1800369b5  push    rsi
0x1800369b6  sub     rsp, 20h
0x1800369ba  mov     rsi, rdx
0x1800369bd  mov     rbx, rcx
0x1800369c0  test    rcx, rcx
0x1800369c3  jz      short loc_1800369EF
0x1800369c5  test    rdx, rdx
0x1800369c8  jz      short loc_180036A08
0x1800369ca  cmp     byte ptr [rcx+1], 1
0x1800369ce  jnz     short loc_180036A0F
0x1800369d0  call    cs:__imp_RtlEqualSid
0x1800369d6  xor     edx, edx
0x1800369d8  mov     ecx, 2
0x1800369dd  test    al, al
0x1800369df  cmovnz  ecx, edx
0x1800369e2  mov     eax, ecx
0x1800369e4  mov     rbx, [rsp+28h+arg_8]
0x1800369e9  add     rsp, 20h
0x1800369ed  pop     rsi
0x1800369ee  retn
0x1800369ef  test    rsi, rsi
0x1800369f2  jz      short loc_180036A04
0x1800369f4  mov     rbx, [rsp+28h+arg_8]
0x1800369f9  mov     eax, 1
0x1800369fe  add     rsp, 20h
0x180036a02  pop     rsi
0x180036a03  retn
0x180036a04  xor     eax, eax
0x180036a06  jmp     short loc_1800369E4
0x180036a08  mov     eax, 0FFFFFFFFh
0x180036a0d  jmp     short loc_1800369E4
0x180036a0f  cmp     byte ptr [rdx+1], 1
0x180036a13  jz      short loc_1800369D0
0x180036a15  movzx   eax, byte ptr [rdx]
0x180036a18  cmp     [rcx], al
0x180036a1a  jnz     loc_180089FBB
0x180036a20  mov     ecx, [rcx+2]
0x180036a23  sub     ecx, [rdx+2]
0x180036a26  jnz     loc_180089F74
0x180036a2c  movzx   ecx, word ptr [rbx+6]
0x180036a30  movzx   eax, word ptr [rdx+6]
0x180036a34  sub     ecx, eax
0x180036a36  jmp     loc_180089F74
0x180089f74  test    ecx, ecx
0x180089f76  jnz     short loc_180089FBB
0x180089f78  mov     rcx, rbx; Sid
0x180089f7b  mov     [rsp+28h+arg_0], rdi
0x180089f80  call    cs:__imp_RtlSubAuthorityCountSid
0x180089f86  mov     rcx, rsi; Sid
0x180089f89  movzx   edi, byte ptr [rax]
0x180089f8c  call    cs:__imp_RtlSubAuthorityCountSid
0x180089f92  lea     rdx, [rsi+8]; Buf2
0x180089f96  lea     rcx, [rbx+8]; Buf1
0x180089f9a  movzx   r8d, byte ptr [rax]
0x180089f9e  cmp     dil, r8b
0x180089fa1  cmovbe  r8d, edi
0x180089fa5  shl     r8, 2; Size
0x180089fa9  call    memcmp_0
0x180089fae  mov     rdi, [rsp+28h+arg_0]
0x180089fb3  test    eax, eax
0x180089fb5  jz      loc_180036A04
0x180089fbb  mov     eax, 2
0x180089fc0  jmp     loc_1800369E4
```
