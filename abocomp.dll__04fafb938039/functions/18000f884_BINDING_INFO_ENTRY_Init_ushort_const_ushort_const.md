# BINDING_INFO_ENTRY::Init(ushort const *,ushort const *)

- ea: `0x18000f884`
- end: `0x18000f910`
- name: `?Init@BINDING_INFO_ENTRY@@QEAAJPEBG0@Z`
- size: `140`
- prototype: `__int64 __fastcall(BINDING_INFO_ENTRY *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000b178`

## callees

- `0x18000f884`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f8aa`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f8bb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f8cf`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f8aa`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f8bb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f8cf`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f8e3`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f8f3`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f8e3`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f8f3`

## pseudocode

```c
int __fastcall BINDING_INFO_ENTRY::Init(
        BINDING_INFO_ENTRY *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int result; // eax
  STRU *v7; // rdi

  if ( !a2 || !a3 )
    return -2147024809;
  result = STRU::Copy((BINDING_INFO_ENTRY *)((char *)this + 8), a2);
  if ( result >= 0 )
  {
    result = STRU::Copy((BINDING_INFO_ENTRY *)((char *)this + 64), a3);
    if ( result >= 0 )
    {
      v7 = (BINDING_INFO_ENTRY *)((char *)this + 120);
      result = STRU::Copy(v7, a2);
      if ( result >= 0 )
      {
        result = STRU::Append(v7, L":");
        if ( result >= 0 )
          return STRU::Append(v7, a3);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f884  mov     [rsp+arg_0], rbx
0x18000f889  mov     [rsp+arg_8], rsi
0x18000f88e  push    rdi
0x18000f88f  sub     rsp, 20h
0x18000f893  mov     rbx, r8
0x18000f896  mov     rsi, rdx
0x18000f899  mov     rdi, rcx
0x18000f89c  test    rdx, rdx
0x18000f89f  jz      short loc_18000F8FB
0x18000f8a1  test    rbx, rbx
0x18000f8a4  jz      short loc_18000F8FB
0x18000f8a6  add     rcx, 8
0x18000f8aa  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000f8b0  test    eax, eax
0x18000f8b2  js      short loc_18000F900
0x18000f8b4  lea     rcx, [rdi+40h]
0x18000f8b8  mov     rdx, rbx
0x18000f8bb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000f8c1  test    eax, eax
0x18000f8c3  js      short loc_18000F900
0x18000f8c5  add     rdi, 78h ; 'x'
0x18000f8c9  mov     rdx, rsi
0x18000f8cc  mov     rcx, rdi
0x18000f8cf  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000f8d5  test    eax, eax
0x18000f8d7  js      short loc_18000F900
0x18000f8d9  lea     rdx, asc_180032CE8; ":"
0x18000f8e0  mov     rcx, rdi
0x18000f8e3  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000f8e9  test    eax, eax
0x18000f8eb  js      short loc_18000F900
0x18000f8ed  mov     rdx, rbx
0x18000f8f0  mov     rcx, rdi
0x18000f8f3  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000f8f9  jmp     short loc_18000F900
0x18000f8fb  mov     eax, 80070057h
0x18000f900  mov     rbx, [rsp+28h+arg_0]
0x18000f905  mov     rsi, [rsp+28h+arg_8]
0x18000f90a  add     rsp, 20h
0x18000f90e  pop     rdi
0x18000f90f  retn
```
