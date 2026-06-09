# UbpmpGetConsumerFriendlyName(ushort const *)

- ea: `0x18000a880`
- end: `0x18000a8ee`
- name: `?UbpmpGetConsumerFriendlyName@@YAPEBGPEBG@Z`
- size: `110`
- prototype: `const unsigned __int16 *__fastcall(PCNZWCH lpString1)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800057e0`
- `0x180009a30`
- `0x18000a230`
- `0x18000b938`
- `0x180030914`
- `0x180030ea4`

## callees

- `0x18000a880`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000a8d5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000a8d5`

## string_xrefs

- `0x18000a8ae`: `NT TASK`

## pseudocode

```c
PCNZWCH __fastcall UbpmpGetConsumerFriendlyName(PCNZWCH lpString1)
{
  PCNZWCH v1; // rbx
  __int64 v2; // rax

  v1 = lpString1;
  if ( lpString1 )
  {
    v2 = -1;
    do
      ++v2;
    while ( lpString1[v2] );
    if ( (unsigned int)v2 > 8 && CompareStringW(0x7Fu, 1u, lpString1, 7, L"NT TASK", 7) == 2 )
      v1 += 7;
  }
  return v1;
}

```

## disassembly

```asm
0x18000a880  push    rbx
0x18000a882  sub     rsp, 30h
0x18000a886  mov     rbx, rcx
0x18000a889  test    rcx, rcx
0x18000a88c  jz      short loc_18000A8A4
0x18000a88e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a895  inc     rax
0x18000a898  cmp     word ptr [rcx+rax*2], 0
0x18000a89d  jnz     short loc_18000A895
0x18000a89f  cmp     eax, 8
0x18000a8a2  ja      short loc_18000A8AE
0x18000a8a4  mov     rax, rbx
0x18000a8a7  add     rsp, 30h
0x18000a8ab  pop     rbx
0x18000a8ac  retn
0x18000a8ae  lea     rax, String2; "NT TASK"
0x18000a8b5  mov     [rsp+38h+cchCount2], 7; cchCount2
0x18000a8bd  mov     r9d, 7; cchCount1
0x18000a8c3  mov     [rsp+38h+lpString2], rax; lpString2
0x18000a8c8  mov     r8, rbx; lpString1
0x18000a8cb  mov     edx, 1; dwCmpFlags
0x18000a8d0  mov     ecx, 7Fh; Locale
0x18000a8d5  call    cs:__imp_CompareStringW
0x18000a8dc  nop     dword ptr [rax+rax+00h]
0x18000a8e1  cmp     eax, 2
0x18000a8e4  lea     rcx, [rbx+0Eh]
0x18000a8e8  cmovz   rbx, rcx
0x18000a8ec  jmp     short loc_18000A8A4
```
