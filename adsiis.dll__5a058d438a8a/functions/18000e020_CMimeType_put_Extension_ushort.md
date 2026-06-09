# CMimeType::put_Extension(ushort *)

- ea: `0x18000e020`
- end: `0x18000e06f`
- name: `?put_Extension@CMimeType@@UEAAJPEAG@Z`
- size: `79`
- prototype: `int(CMimeType *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000e020`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsStr` at `0x18000e04e`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18000e04e`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000e045`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000e045`

## pseudocode

```c
__int64 __fastcall CMimeType::put_Extension(CMimeType *this, unsigned __int16 *a2)
{
  WCHAR *v5; // rcx
  LPWSTR v6; // rax

  if ( !a2 )
    return 2147500037LL;
  v5 = (WCHAR *)*((_QWORD *)this + 4);
  if ( v5 )
    FreeADsStr(v5);
  v6 = AllocADsStr(a2);
  *((_QWORD *)this + 4) = v6;
  return v6 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18000e020  mov     [rsp+arg_0], rbx
0x18000e025  push    rdi
0x18000e026  sub     rsp, 20h
0x18000e02a  mov     rdi, rdx
0x18000e02d  mov     rbx, rcx
0x18000e030  test    rdx, rdx
0x18000e033  jnz     short loc_18000E03C
0x18000e035  mov     eax, 80004005h
0x18000e03a  jmp     short loc_18000E064
0x18000e03c  mov     rcx, [rcx+20h]; pStr
0x18000e040  test    rcx, rcx
0x18000e043  jz      short loc_18000E04B
0x18000e045  call    cs:__imp_FreeADsStr
0x18000e04b  mov     rcx, rdi; pStr
0x18000e04e  call    cs:__imp_AllocADsStr
0x18000e054  mov     [rbx+20h], rax
0x18000e058  neg     rax
0x18000e05b  sbb     eax, eax
0x18000e05d  not     eax
0x18000e05f  and     eax, 8007000Eh
0x18000e064  mov     rbx, [rsp+28h+arg_0]
0x18000e069  add     rsp, 20h
0x18000e06d  pop     rdi
0x18000e06e  retn
```
