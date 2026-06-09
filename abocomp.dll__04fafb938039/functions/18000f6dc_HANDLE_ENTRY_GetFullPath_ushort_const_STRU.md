# HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)

- ea: `0x18000f6dc`
- end: `0x18000f74e`
- name: `?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z`
- size: `114`
- prototype: `int(HANDLE_ENTRY *__hidden this, const unsigned __int16 *, struct STRU *)`
- caller_count: `17`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000b3c0`
- `0x18000bf00`
- `0x18000c560`
- `0x18000c990`
- `0x18000cbb0`
- `0x18000ce90`
- `0x18000d040`
- `0x18000d360`
- `0x18000d8f0`
- `0x18000db80`
- `0x18000dea0`
- `0x18000e170`
- `0x18000e3e0`
- `0x18000e6e0`
- `0x18000ed00`
- `0x18000f110`
- `0x18000f390`

## callees

- `0x18000f6dc`
- `0x18000f754`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f708`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f708`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f6fc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f6fc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f721`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f731`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f721`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f731`

## pseudocode

```c
int __fastcall HANDLE_ENTRY::GetFullPath(HANDLE_ENTRY *this, const unsigned __int16 *a2, struct STRU *a3)
{
  int result; // eax
  const unsigned __int16 *Str; // rax

  if ( !a3 )
    return -2147024809;
  Str = STRU::QueryStr((HANDLE_ENTRY *)((char *)this + 16));
  result = STRU::Copy(a3, Str);
  if ( result >= 0 )
  {
    if ( !a2 )
      return HANDLE_ENTRY::SanitizePath(a3);
    result = STRU::Append(a3, L"/");
    if ( result >= 0 )
    {
      result = STRU::Append(a3, a2);
      if ( result >= 0 )
        return HANDLE_ENTRY::SanitizePath(a3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f6dc  mov     [rsp+arg_0], rbx
0x18000f6e1  push    rdi
0x18000f6e2  sub     rsp, 20h
0x18000f6e6  mov     rbx, r8
0x18000f6e9  mov     rdi, rdx
0x18000f6ec  test    r8, r8
0x18000f6ef  jnz     short loc_18000F6F8
0x18000f6f1  mov     eax, 80070057h
0x18000f6f6  jmp     short loc_18000F743
0x18000f6f8  add     rcx, 10h
0x18000f6fc  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000f702  mov     rdx, rax
0x18000f705  mov     rcx, rbx
0x18000f708  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000f70e  test    eax, eax
0x18000f710  js      short loc_18000F743
0x18000f712  test    rdi, rdi
0x18000f715  jz      short loc_18000F73B
0x18000f717  lea     rdx, asc_18002E8E8; "/"
0x18000f71e  mov     rcx, rbx
0x18000f721  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000f727  test    eax, eax
0x18000f729  js      short loc_18000F743
0x18000f72b  mov     rdx, rdi
0x18000f72e  mov     rcx, rbx
0x18000f731  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000f737  test    eax, eax
0x18000f739  js      short loc_18000F743
0x18000f73b  mov     rcx, rbx; struct STRU *
0x18000f73e  call    ?SanitizePath@HANDLE_ENTRY@@CAJPEAVSTRU@@@Z; HANDLE_ENTRY::SanitizePath(STRU *)
0x18000f743  mov     rbx, [rsp+28h+arg_0]
0x18000f748  add     rsp, 20h
0x18000f74c  pop     rdi
0x18000f74d  retn
```
