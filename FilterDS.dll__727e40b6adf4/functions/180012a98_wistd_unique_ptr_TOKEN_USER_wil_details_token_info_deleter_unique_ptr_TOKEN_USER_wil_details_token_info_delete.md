# wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(void)

- ea: `0x180012a98`
- end: `0x180012ab9`
- name: `??1?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180022ee0`
- `0x180022f04`

## callees

- `0x180012a98`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180012aae`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012aae`

## pseudocode

```c
void __fastcall wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x180012a98  sub     rsp, 28h
0x180012a9c  mov     rax, [rcx]
0x180012a9f  mov     qword ptr [rcx], 0
0x180012aa6  test    rax, rax
0x180012aa9  jz      short loc_180012AB4
0x180012aab  mov     rcx, rax
0x180012aae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012ab4  add     rsp, 28h
0x180012ab8  retn
```
