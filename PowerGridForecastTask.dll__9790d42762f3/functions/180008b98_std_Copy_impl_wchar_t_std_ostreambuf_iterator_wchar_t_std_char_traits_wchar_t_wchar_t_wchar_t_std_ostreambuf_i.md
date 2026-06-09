# std::_Copy_impl<wchar_t *,std::ostreambuf_iterator<wchar_t,std::char_traits<wchar_t>>>(wchar_t *,wchar_t *,std::ostreambuf_iterator<wchar_t,std::char_traits<wchar_t>>,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x180008b98`
- end: `0x180008c2e`
- name: `??$_Copy_impl@PEA_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@YA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@0@PEA_W0V10@U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `150`
- prototype: `_OWORD *__fastcall(_OWORD *, unsigned __int16 *, unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c010`

## callees

- `0x180008b98`
- `0x180037010`

## pseudocode

```c
_OWORD *__fastcall std::_Copy_impl<wchar_t *,std::ostreambuf_iterator<wchar_t>>(
        _OWORD *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4)
{
  unsigned __int16 *v6; // rbx
  __int64 v8; // rdi
  unsigned __int16 v9; // r8
  int *v10; // rax
  unsigned __int16 **v11; // rcx
  unsigned __int16 *v12; // rdx
  _OWORD *result; // rax

  v6 = a2;
  if ( a2 != a3 )
  {
    v8 = *(_QWORD *)(a4 + 8);
    do
    {
      if ( !v8
        || ((v9 = *v6, !**(_QWORD **)(v8 + 64)) || (v10 = *(int **)(v8 + 88), *v10 <= 0)
          ? (v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 24LL))(v8, v9))
          : (--*v10, v11 = *(unsigned __int16 ***)(v8 + 64), v12 = *v11, ++*v11, *v12 = v9),
            v9 == 0xFFFF) )
      {
        *(_BYTE *)a4 = 1;
      }
      ++v6;
    }
    while ( v6 != a3 );
  }
  result = a1;
  *a1 = *(_OWORD *)a4;
  return result;
}

```

## disassembly

```asm
0x180008b98  push    rbx
0x180008b9a  push    rbp
0x180008b9b  push    rsi
0x180008b9c  push    rdi
0x180008b9d  push    r14
0x180008b9f  sub     rsp, 20h
0x180008ba3  mov     rsi, r9
0x180008ba6  mov     r14, r8
0x180008ba9  mov     rbx, rdx
0x180008bac  mov     rbp, rcx
0x180008baf  cmp     rdx, r8
0x180008bb2  jz      short loc_180008C18
0x180008bb4  mov     rdi, [r9+8]
0x180008bb8  test    rdi, rdi
0x180008bbb  jz      short loc_180008C0C
0x180008bbd  mov     rax, [rdi+40h]
0x180008bc1  movzx   r8d, word ptr [rbx]
0x180008bc5  cmp     qword ptr [rax], 0
0x180008bc9  jz      short loc_180008BEA
0x180008bcb  mov     rax, [rdi+58h]
0x180008bcf  cmp     dword ptr [rax], 0
0x180008bd2  jle     short loc_180008BEA
0x180008bd4  dec     dword ptr [rax]
0x180008bd6  mov     rcx, [rdi+40h]
0x180008bda  mov     rdx, [rcx]
0x180008bdd  lea     rax, [rdx+2]
0x180008be1  mov     [rcx], rax
0x180008be4  mov     [rdx], r8w
0x180008be8  jmp     short loc_180008C01
0x180008bea  mov     rax, [rdi]
0x180008bed  movzx   edx, r8w
0x180008bf1  mov     rcx, rdi
0x180008bf4  mov     rax, [rax+18h]
0x180008bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bfd  movzx   r8d, ax
0x180008c01  mov     eax, 0FFFFh
0x180008c06  cmp     r8w, ax
0x180008c0a  jnz     short loc_180008C0F
0x180008c0c  mov     byte ptr [rsi], 1
0x180008c0f  add     rbx, 2
0x180008c13  cmp     rbx, r14
0x180008c16  jnz     short loc_180008BB8
0x180008c18  movups  xmm0, xmmword ptr [rsi]
0x180008c1b  mov     rax, rbp
0x180008c1e  movdqu  xmmword ptr [rbp+0], xmm0
0x180008c23  add     rsp, 20h
0x180008c27  pop     r14
0x180008c29  pop     rdi
0x180008c2a  pop     rsi
0x180008c2b  pop     rbp
0x180008c2c  pop     rbx
0x180008c2d  retn
```
