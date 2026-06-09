# Cn::Com::DeferredRelease::CreateNotificationCallback(void (*)(void *),void *)

- ea: `0x1800303b4`
- end: `0x18003043b`
- name: `?CreateNotificationCallback@DeferredRelease@Com@Cn@@QEAAXP6AXPEAX@Z0@Z`
- size: `135`
- prototype: `void __fastcall(Cn::Com::DeferredRelease *__hidden this, void (*)(void *), void *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18005bc90`
- `0x180084cb0`
- `0x1800b0d58`

## callees

- `0x18000b0bc`
- `0x1800303b4`
- `0x1800a2108`
- `0x1800c7d64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800303f1`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800303f1`

## string_xrefs

- `0x180030420`: `onecore\internal\sdk\inc\wil\opensource/wil/safecast.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Cn::Com::DeferredRelease::CreateNotificationCallback(
        Cn::Com::DeferredRelease *this,
        void (*a2)(void *),
        void *a3)
{
  int v6; // eax
  unsigned __int64 v7; // rbx
  _QWORD *v8; // rax
  int v9; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  size_t Count; // [rsp+68h] [rbp+20h] BYREF

  LODWORD(Count) = 0;
  v6 = ULongLongToUInt(0x20u, (unsigned int *)&Count);
  if ( v6 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/safecast.h",
      (const char *)(unsigned int)v6,
      v9);
  v7 = (unsigned int)Count;
  v8 = calloc((unsigned int)Count, 1u);
  if ( !v8 )
    CFlat::Abandonment::OutOfMemory(v7);
  v8[3] = a2;
  v8[2] = a3;
  *v8 = *(_QWORD *)this;
  *((_BYTE *)v8 + 8) = 2;
  *(_QWORD *)this = v8;
}

```

## disassembly

```asm
0x1800303b4  push    rbx
0x1800303b6  push    rbp
0x1800303b7  push    rsi
0x1800303b8  push    rdi
0x1800303b9  sub     rsp, 28h
0x1800303bd  mov     rsi, r8
0x1800303c0  mov     rbp, rdx
0x1800303c3  mov     rdi, rcx
0x1800303c6  mov     dword ptr [rsp+48h+Count], 0
0x1800303ce  lea     rdx, [rsp+48h+Count]; unsigned int *
0x1800303d3  mov     ecx, 20h ; ' '; unsigned __int64
0x1800303d8  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800303dd  mov     rcx, [rsp+48h]; this
0x1800303e2  test    eax, eax
0x1800303e4  js      short loc_18003041D
0x1800303e6  mov     ebx, dword ptr [rsp+48h+Count]
0x1800303ea  mov     edx, 1; Size
0x1800303ef  mov     ecx, ebx; Count
0x1800303f1  call    cs:__imp_calloc
0x1800303f7  mov     rdx, rax
0x1800303fa  test    rax, rax
0x1800303fd  jz      short loc_180030432
0x1800303ff  mov     [rax+18h], rbp
0x180030403  mov     [rax+10h], rsi
0x180030407  mov     rax, [rdi]
0x18003040a  mov     [rdx], rax
0x18003040d  mov     byte ptr [rdx+8], 2
0x180030411  mov     [rdi], rdx
0x180030414  add     rsp, 28h
0x180030418  pop     rdi
0x180030419  pop     rsi
0x18003041a  pop     rbp
0x18003041b  pop     rbx
0x18003041c  retn
0x18003041d  mov     r9d, eax; char *
0x180030420  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180030427  mov     edx, 10Fh; void *
0x18003042c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180030432  mov     rcx, rbx; unsigned __int64
0x180030435  call    ?OutOfMemory@Abandonment@CFlat@@SAX_K@Z; CFlat::Abandonment::OutOfMemory(unsigned __int64)
```
