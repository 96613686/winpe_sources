# wil::details::out_param_t<std::unique_ptr<CKeyboardHandler,std::default_delete<CKeyboardHandler>>>::~out_param_t<std::unique_ptr<CKeyboardHandler,std::default_delete<CKeyboardHandler>>>(void)

- ea: `0x180012a0c`
- end: `0x180012a40`
- name: `??1?$out_param_t@V?$unique_ptr@VCKeyboardHandler@@U?$default_delete@VCKeyboardHandler@@@std@@@std@@@details@wil@@QEAA@XZ`
- size: `52`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800290ff`

## callees

- `0x180012a0c`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall wil::details::out_param_t<std::unique_ptr<CKeyboardHandler>>::~out_param_t<std::unique_ptr<CKeyboardHandler>>(
        __int64 a1)
{
  __int64 result; // rax
  __int64 (__fastcall ***v2)(_QWORD, __int64); // r8

  if ( *(_BYTE *)(a1 + 16) )
  {
    result = *(_QWORD *)(a1 + 8);
    v2 = **(__int64 (__fastcall *****)(_QWORD, __int64))a1;
    **(_QWORD **)a1 = result;
    if ( v2 )
      return (**v2)(v2, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180012a0c  sub     rsp, 28h
0x180012a10  cmp     byte ptr [rcx+10h], 0
0x180012a14  jz      short loc_180012A3B
0x180012a16  mov     rdx, [rcx]
0x180012a19  mov     rax, [rcx+8]
0x180012a1d  mov     r8, [rdx]
0x180012a20  mov     [rdx], rax
0x180012a23  test    r8, r8
0x180012a26  jz      short loc_180012A3B
0x180012a28  mov     rax, [r8]
0x180012a2b  mov     edx, 1
0x180012a30  mov     rcx, r8
0x180012a33  mov     rax, [rax]
0x180012a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a3b  add     rsp, 28h
0x180012a3f  retn
```
