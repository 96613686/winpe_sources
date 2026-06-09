# ProjectionIterator<ConfigLocationToRawConfigSelector>::CreateInstance(IXPathNodeIterator *,IUnknown * *)

- ea: `0x180007c58`
- end: `0x180007ce9`
- name: `?CreateInstance@?$ProjectionIterator@VConfigLocationToRawConfigSelector@@@@SAJPEAUIXPathNodeIterator@@PEAPEAUIUnknown@@@Z`
- size: `145`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180007510`
- `0x180007b40`
- `0x180007e20`

## callees

- `0x180001194`
- `0x180002310`
- `0x1800075c4`
- `0x180007c58`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProjectionIterator<ConfigLocationToRawConfigSelector>::CreateInstance(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx

  v4 = operator new(0x28u);
  v5 = v4;
  if ( v4 )
  {
    SimpleIUnknownImpl<IXPathNodeIterator>::SimpleIUnknownImpl<IXPathNodeIterator>(v4);
    ModuleRefCounter::AddRef();
    *v5 = &ProjectionIterator<ConfigLocationToRawConfigSelector>::`vftable';
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
0x180007c58  mov     [rsp+arg_0], rbx
0x180007c5d  mov     [rsp+arg_10], rsi
0x180007c62  push    rdi
0x180007c63  sub     rsp, 20h
0x180007c67  mov     rsi, rdx
0x180007c6a  mov     rdi, rcx
0x180007c6d  mov     ecx, 28h ; '('; Size
0x180007c72  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007c77  mov     rbx, rax
0x180007c7a  mov     [rsp+28h+arg_8], rax
0x180007c7f  test    rax, rax
0x180007c82  jz      short loc_180007CCD
0x180007c84  mov     rcx, rax
0x180007c87  call    ??0?$SimpleIUnknownImpl@UIXPathNodeIterator@@@@QEAA@XZ; SimpleIUnknownImpl<IXPathNodeIterator>::SimpleIUnknownImpl<IXPathNodeIterator>(void)
0x180007c8c  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180007c91  lea     rax, ??_7?$ProjectionIterator@VConfigLocationToRawConfigSelector@@@@6B@; const ProjectionIterator<ConfigLocationToRawConfigSelector>::`vftable'
0x180007c98  mov     [rbx], rax
0x180007c9b  mov     [rbx+18h], rdi
0x180007c9f  test    rdi, rdi
0x180007ca2  jz      short loc_180007CB4
0x180007ca4  mov     rax, [rdi]
0x180007ca7  mov     rcx, rdi
0x180007caa  mov     rax, [rax+8]
0x180007cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cb3  nop
0x180007cb4  mov     qword ptr [rbx+20h], 0
0x180007cbc  mov     [rsi], rbx
0x180007cbf  neg     rbx
0x180007cc2  sbb     eax, eax
0x180007cc4  not     eax
0x180007cc6  and     eax, 8007000Eh
0x180007ccb  jmp     short loc_180007CD9
0x180007ccd  mov     qword ptr [rsi], 0
0x180007cd4  mov     eax, 8007000Eh
0x180007cd9  mov     rbx, [rsp+28h+arg_0]
0x180007cde  mov     rsi, [rsp+28h+arg_10]
0x180007ce3  add     rsp, 20h
0x180007ce7  pop     rdi
0x180007ce8  retn
```
