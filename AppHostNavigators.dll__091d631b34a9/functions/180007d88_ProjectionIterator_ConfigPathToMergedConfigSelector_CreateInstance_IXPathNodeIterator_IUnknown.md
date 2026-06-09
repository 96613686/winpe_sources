# ProjectionIterator<ConfigPathToMergedConfigSelector>::CreateInstance(IXPathNodeIterator *,IUnknown * *)

- ea: `0x180007d88`
- end: `0x180007e19`
- name: `?CreateInstance@?$ProjectionIterator@VConfigPathToMergedConfigSelector@@@@SAJPEAUIXPathNodeIterator@@PEAPEAUIUnknown@@@Z`
- size: `145`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180007450`
- `0x180007c00`
- `0x180007f20`

## callees

- `0x180001194`
- `0x180002310`
- `0x1800075c4`
- `0x180007d88`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ProjectionIterator<ConfigPathToMergedConfigSelector>::CreateInstance(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx

  v4 = operator new(0x28u);
  v5 = v4;
  if ( v4 )
  {
    SimpleIUnknownImpl<IXPathNodeIterator>::SimpleIUnknownImpl<IXPathNodeIterator>(v4);
    ModuleRefCounter::AddRef();
    *v5 = &ProjectionIterator<ConfigPathToMergedConfigSelector>::`vftable';
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
0x180007d88  mov     [rsp+arg_0], rbx
0x180007d8d  mov     [rsp+arg_10], rsi
0x180007d92  push    rdi
0x180007d93  sub     rsp, 20h
0x180007d97  mov     rsi, rdx
0x180007d9a  mov     rdi, rcx
0x180007d9d  mov     ecx, 28h ; '('; Size
0x180007da2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007da7  mov     rbx, rax
0x180007daa  mov     [rsp+28h+arg_8], rax
0x180007daf  test    rax, rax
0x180007db2  jz      short loc_180007DFD
0x180007db4  mov     rcx, rax
0x180007db7  call    ??0?$SimpleIUnknownImpl@UIXPathNodeIterator@@@@QEAA@XZ; SimpleIUnknownImpl<IXPathNodeIterator>::SimpleIUnknownImpl<IXPathNodeIterator>(void)
0x180007dbc  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180007dc1  lea     rax, ??_7?$ProjectionIterator@VConfigPathToMergedConfigSelector@@@@6B@; const ProjectionIterator<ConfigPathToMergedConfigSelector>::`vftable'
0x180007dc8  mov     [rbx], rax
0x180007dcb  mov     [rbx+18h], rdi
0x180007dcf  test    rdi, rdi
0x180007dd2  jz      short loc_180007DE4
0x180007dd4  mov     rax, [rdi]
0x180007dd7  mov     rcx, rdi
0x180007dda  mov     rax, [rax+8]
0x180007dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007de3  nop
0x180007de4  mov     qword ptr [rbx+20h], 0
0x180007dec  mov     [rsi], rbx
0x180007def  neg     rbx
0x180007df2  sbb     eax, eax
0x180007df4  not     eax
0x180007df6  and     eax, 8007000Eh
0x180007dfb  jmp     short loc_180007E09
0x180007dfd  mov     qword ptr [rsi], 0
0x180007e04  mov     eax, 8007000Eh
0x180007e09  mov     rbx, [rsp+28h+arg_0]
0x180007e0e  mov     rsi, [rsp+28h+arg_10]
0x180007e13  add     rsp, 20h
0x180007e17  pop     rdi
0x180007e18  retn
```
