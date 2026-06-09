# CPropertyCache::findproperty(ushort *,ulong *)

- ea: `0x180010bf8`
- end: `0x180010c49`
- name: `?findproperty@CPropertyCache@@QEAAJPEAGPEAK@Z`
- size: `81`
- prototype: `int(CPropertyCache *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1800032a0`
- `0x1800035a0`
- `0x180006b00`
- `0x180006f60`
- `0x180007300`
- `0x180007940`
- `0x1800103bc`
- `0x180010cd8`
- `0x180010ecc`
- `0x1800110bc`
- `0x1800111b4`

## callees

- `0x180010bf8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180010c21`
- `msvcrt!_wcsicmp` at `0x180010c21`

## pseudocode

```c
__int64 __fastcall CPropertyCache::findproperty(CPropertyCache *this, unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int i; // ebx

  for ( i = 0; i < *((_DWORD *)this + 2); ++i )
  {
    if ( !_wcsicmp((const wchar_t *)(*((_QWORD *)this + 4) + 544LL * i), a2) )
    {
      *a3 = i;
      return 0;
    }
  }
  *a3 = 0;
  return 2147504141LL;
}

```

## disassembly

```asm
0x180010bf8  push    rbx
0x180010bfa  push    rbp
0x180010bfb  push    rsi
0x180010bfc  push    rdi
0x180010bfd  sub     rsp, 28h
0x180010c01  mov     rdi, r8
0x180010c04  mov     rbp, rdx
0x180010c07  mov     rsi, rcx
0x180010c0a  xor     ebx, ebx
0x180010c0c  cmp     ebx, [rsi+8]
0x180010c0f  jnb     short loc_180010C35
0x180010c11  mov     eax, ebx
0x180010c13  mov     rdx, rbp; String2
0x180010c16  imul    rcx, rax, 220h
0x180010c1d  add     rcx, [rsi+20h]; String1
0x180010c21  call    cs:__imp__wcsicmp
0x180010c27  test    eax, eax
0x180010c29  jz      short loc_180010C2F
0x180010c2b  inc     ebx
0x180010c2d  jmp     short loc_180010C0C
0x180010c2f  mov     [rdi], ebx
0x180010c31  xor     eax, eax
0x180010c33  jmp     short loc_180010C40
0x180010c35  mov     dword ptr [rdi], 0
0x180010c3b  mov     eax, 8000500Dh
0x180010c40  add     rsp, 28h
0x180010c44  pop     rdi
0x180010c45  pop     rsi
0x180010c46  pop     rbp
0x180010c47  pop     rbx
0x180010c48  retn
```
