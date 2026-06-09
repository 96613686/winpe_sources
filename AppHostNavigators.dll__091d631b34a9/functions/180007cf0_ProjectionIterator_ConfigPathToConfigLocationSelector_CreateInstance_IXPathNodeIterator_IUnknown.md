# ProjectionIterator<ConfigPathToConfigLocationSelector>::CreateInstance(IXPathNodeIterator *,IUnknown * *)

- ea: `0x180007cf0`
- end: `0x180007d81`
- name: `?CreateInstance@?$ProjectionIterator@VConfigPathToConfigLocationSelector@@@@SAJPEAUIXPathNodeIterator@@PEAPEAUIUnknown@@@Z`
- size: `145`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180007ba0`
- `0x180007ea0`

## callees

- `0x180001194`
- `0x180002310`
- `0x1800075c4`
- `0x180007cf0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ProjectionIterator<ConfigPathToConfigLocationSelector>::CreateInstance(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx

  v4 = operator new(0x28u);
  v5 = v4;
  if ( v4 )
  {
    SimpleIUnknownImpl<IXPathNodeIterator>::SimpleIUnknownImpl<IXPathNodeIterator>(v4);
    ModuleRefCounter::AddRef();
    *v5 = &ProjectionIterator<ConfigPathToConfigLocationSelector>::`vftable';
    v5[3] = a1;
    if ( a1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    v5[4] = 0;
    *a2 = v5;
    return v5 == 0 ? 0x8007000E : 0;
  }
  else
  {
    *a2 = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180007cf0  mov     [rsp+arg_0], rbx
0x180007cf5  mov     [rsp+arg_10], rsi
0x180007cfa  push    rdi
0x180007cfb  sub     rsp, 20h
0x180007cff  mov     rsi, rdx
0x180007d02  mov     rdi, rcx
0x180007d05  mov     ecx, 28h ; '('; Size
0x180007d0a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007d0f  mov     rbx, rax
0x180007d12  mov     [rsp+28h+arg_8], rax
0x180007d17  test    rax, rax
0x180007d1a  jz      short loc_180007D65
0x180007d1c  mov     rcx, rax
0x180007d1f  call    ??0?$SimpleIUnknownImpl@UIXPathNodeIterator@@@@QEAA@XZ; SimpleIUnknownImpl<IXPathNodeIterator>::SimpleIUnknownImpl<IXPathNodeIterator>(void)
0x180007d24  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180007d29  lea     rax, ??_7?$ProjectionIterator@VConfigPathToConfigLocationSelector@@@@6B@; const ProjectionIterator<ConfigPathToConfigLocationSelector>::`vftable'
0x180007d30  mov     [rbx], rax
0x180007d33  mov     [rbx+18h], rdi
0x180007d37  test    rdi, rdi
0x180007d3a  jz      short loc_180007D4C
0x180007d3c  mov     rax, [rdi]
0x180007d3f  mov     rcx, rdi
0x180007d42  mov     rax, [rax+8]
0x180007d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d4b  nop
0x180007d4c  mov     qword ptr [rbx+20h], 0
0x180007d54  mov     [rsi], rbx
0x180007d57  neg     rbx
0x180007d5a  sbb     eax, eax
0x180007d5c  not     eax
0x180007d5e  and     eax, 8007000Eh
0x180007d63  jmp     short loc_180007D71
0x180007d65  mov     qword ptr [rsi], 0
0x180007d6c  mov     eax, 8007000Eh
0x180007d71  mov     rbx, [rsp+28h+arg_0]
0x180007d76  mov     rsi, [rsp+28h+arg_10]
0x180007d7b  add     rsp, 20h
0x180007d7f  pop     rdi
0x180007d80  retn
```
