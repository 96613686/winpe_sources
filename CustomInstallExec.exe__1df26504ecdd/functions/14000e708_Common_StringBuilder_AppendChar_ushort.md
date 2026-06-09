# Common::StringBuilder::AppendChar(ushort)

- ea: `0x14000e708`
- end: `0x14000e779`
- name: `?AppendChar@StringBuilder@Common@@QEAAJG@Z`
- size: `113`
- prototype: `__int64 __fastcall(Common::StringBuilder *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140008ec8`

## callees

- `0x14000b854`
- `0x14000e708`
- `0x14000f010`

## string_xrefs

- `0x14000e742`: `onecore\base\appmodel\common\stringbuilder.cpp`

## pseudocode

```c
__int64 __fastcall Common::StringBuilder::AppendChar(Common::StringBuilder *this)
{
  int v2; // edx
  int v4; // eax
  unsigned int v5; // edi
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = **((_DWORD **)this + 1);
  if ( v2 == 0x3FFFFFFF )
    return 2147943683LL;
  v4 = (**(__int64 (__fastcall ***)(Common::StringBuilder *, _QWORD))this)(this, (unsigned int)(v2 + 1));
  v5 = v4;
  if ( v4 >= 0 )
  {
    *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL) + 2LL * (unsigned int)(**((_DWORD **)this + 1) - 1)) = 34;
    return 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1B,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)v4);
    return v5;
  }
}

```

## disassembly

```asm
0x14000e708  mov     [rsp+arg_0], rbx
0x14000e70d  push    rdi; int
0x14000e70e  sub     rsp, 20h
0x14000e712  mov     rax, [rcx+8]
0x14000e716  mov     rbx, rcx
0x14000e719  mov     edx, [rax]
0x14000e71b  cmp     edx, 3FFFFFFFh
0x14000e721  jnz     short loc_14000E72A
0x14000e723  mov     eax, 80070503h
0x14000e728  jmp     short loc_14000E76E
0x14000e72a  mov     rax, [rcx]
0x14000e72d  inc     edx
0x14000e72f  mov     rax, [rax]
0x14000e732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e737  mov     edi, eax
0x14000e739  test    eax, eax
0x14000e73b  jns     short loc_14000E75A
0x14000e73d  mov     rcx, [rsp+28h]; this
0x14000e742  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\string"...
0x14000e749  mov     r9d, eax; char *
0x14000e74c  mov     edx, 1Bh; void *
0x14000e751  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e756  mov     eax, edi
0x14000e758  jmp     short loc_14000E76E
0x14000e75a  mov     rdx, [rbx+8]
0x14000e75e  mov     ecx, [rdx]
0x14000e760  mov     rax, [rdx+8]
0x14000e764  dec     ecx
0x14000e766  mov     word ptr [rax+rcx*2], 22h ; '"'
0x14000e76c  xor     eax, eax
0x14000e76e  mov     rbx, [rsp+28h+arg_0]
0x14000e773  add     rsp, 20h
0x14000e777  pop     rdi
0x14000e778  retn
```
