# std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<long (*const)(HKEY__ *),0>,long,HKEY__ *>::_Delete_this(bool)

- ea: `0x18001f070`
- end: `0x18001f0a5`
- name: `?_Delete_this@?$_Impl_no_alloc1@U?$_Callable_fun@Q6AJPEAUHKEY__@@@Z$0A@@tr1@std@@JPEAUHKEY__@@@tr1@std@@EEAAX_N@Z`
- size: `53`
- prototype: `void __fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18001f070`
- `0x180025010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001f094`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f094`

## pseudocode

```c
void __fastcall std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<long (*const)(HKEY__ *),0>,long,HKEY__ *>::_Delete_this(
        void *a1,
        char a2)
{
  (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, 0);
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x18001f070  mov     [rsp+arg_0], rbx
0x18001f075  push    rdi
0x18001f076  sub     rsp, 20h
0x18001f07a  mov     rax, [rcx]
0x18001f07d  mov     bl, dl
0x18001f07f  xor     edx, edx
0x18001f081  mov     rdi, rcx
0x18001f084  mov     rax, [rax+20h]
0x18001f088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f08d  test    bl, bl
0x18001f08f  jz      short loc_18001F09A
0x18001f091  mov     rcx, rdi
0x18001f094  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f09a  mov     rbx, [rsp+28h+arg_0]
0x18001f09f  add     rsp, 20h
0x18001f0a3  pop     rdi
0x18001f0a4  retn
```
