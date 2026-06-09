# RtlFindUnicodeSubstring

- ea: `0x14001ef20`
- end: `0x14001efc3`
- name: `RtlFindUnicodeSubstring`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001fd0`
- `0x14001ea74`

## callees

- `0x14001ef20`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeStrings` at `0x14001ef77`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x14001ef77`

## pseudocode

```c
const WCHAR *__fastcall RtlFindUnicodeSubstring(unsigned __int16 *a1, PCWCH *a2, BOOLEAN a3)
{
  const WCHAR *v6; // rsi
  __int64 i; // r14
  unsigned __int64 v8; // rdx

  if ( *a1 < *(_WORD *)a2 )
    return 0;
  v6 = (const WCHAR *)*((_QWORD *)a1 + 1);
  for ( i = 0; ; ++i )
  {
    v8 = *(unsigned __int16 *)a2;
    if ( (unsigned __int64)*a1 - 2 * i < v8 )
      break;
    if ( !RtlCompareUnicodeStrings(v6, v8 >> 1, a2[1], v8 >> 1, a3) )
      return v6;
    ++v6;
  }
  return 0;
}

```

## disassembly

```asm
0x14001ef20  mov     [rsp+arg_10], rbx
0x14001ef25  push    rbp
0x14001ef26  push    rdi
0x14001ef27  push    r15
0x14001ef29  sub     rsp, 30h
0x14001ef2d  movzx   eax, word ptr [rdx]
0x14001ef30  xor     r15d, r15d
0x14001ef33  movzx   ebp, r8b
0x14001ef37  mov     rdi, rdx
0x14001ef3a  mov     rbx, rcx
0x14001ef3d  cmp     [rcx], ax
0x14001ef40  jb      short loc_14001EFA3
0x14001ef42  mov     [rsp+48h+arg_0], rsi
0x14001ef47  mov     rsi, [rcx+8]
0x14001ef4b  mov     [rsp+48h+arg_8], r14
0x14001ef50  xor     r14d, r14d
0x14001ef53  movzx   ecx, word ptr [rbx]
0x14001ef56  lea     rax, [r14+r14]
0x14001ef5a  movzx   edx, word ptr [rdi]
0x14001ef5d  sub     rcx, rax
0x14001ef60  cmp     rcx, rdx
0x14001ef63  jb      short loc_14001EFBE
0x14001ef65  mov     r8, [rdi+8]; String2
0x14001ef69  mov     rcx, rsi; String1
0x14001ef6c  shr     rdx, 1; String1Length
0x14001ef6f  mov     r9, rdx; String2Length
0x14001ef72  mov     [rsp+48h+CaseInSensitive], bpl; CaseInSensitive
0x14001ef77  call    cs:__imp_RtlCompareUnicodeStrings
0x14001ef7e  nop     dword ptr [rax+rax+00h]
0x14001ef83  test    eax, eax
0x14001ef85  jnz     short loc_14001EFB5
0x14001ef87  mov     rax, rsi
0x14001ef8a  mov     rsi, [rsp+48h+arg_0]
0x14001ef8f  mov     r14, [rsp+48h+arg_8]
0x14001ef94  mov     rbx, [rsp+48h+arg_10]
0x14001ef99  add     rsp, 30h
0x14001ef9d  pop     r15
0x14001ef9f  pop     rdi
0x14001efa0  pop     rbp
0x14001efa1  retn
0x14001efa3  mov     rbx, [rsp+48h+arg_10]
0x14001efa8  mov     rax, r15
0x14001efab  add     rsp, 30h
0x14001efaf  pop     r15
0x14001efb1  pop     rdi
0x14001efb2  pop     rbp
0x14001efb3  retn
0x14001efb5  inc     r14
0x14001efb8  add     rsi, 2
0x14001efbc  jmp     short loc_14001EF53
0x14001efbe  mov     rax, r15
0x14001efc1  jmp     short loc_14001EF8A
```
