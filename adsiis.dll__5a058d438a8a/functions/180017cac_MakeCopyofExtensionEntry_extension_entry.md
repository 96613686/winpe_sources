# MakeCopyofExtensionEntry(_extension_entry *)

- ea: `0x180017cac`
- end: `0x180017d87`
- name: `?MakeCopyofExtensionEntry@@YAPEAU_extension_entry@@PEAU1@@Z`
- size: `219`
- prototype: `struct _extension_entry *__fastcall(wchar_t *Source)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180017c28`

## callees

- `0x180017cac`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180017ce1`
- `msvcrt!wcscpy_s` at `0x180017d2a`
- `msvcrt!wcscpy_s` at `0x180017ce1`
- `msvcrt!wcscpy_s` at `0x180017d2a`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180017cc8`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180017d11`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180017cc8`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180017d11`

## pseudocode

```c
wchar_t *__fastcall MakeCopyofExtensionEntry(wchar_t *Source)
{
  __int64 v1; // rbx
  wchar_t *v3; // rbp
  wchar_t *v4; // rax
  wchar_t *v5; // rdi
  wchar_t *v6; // rax
  wchar_t *v7; // rbx
  __int128 v8; // xmm0

  v1 = *((_QWORD *)Source + 71);
  v3 = 0;
  while ( v1 )
  {
    v4 = (wchar_t *)AllocADsMem(0x220u);
    v5 = v4;
    if ( v4 )
    {
      wcscpy_s(v4, 0x104u, (const wchar_t *)v1);
      *(_OWORD *)(v5 + 260) = *(_OWORD *)(v1 + 520);
      *((_QWORD *)v5 + 67) = v3;
      v3 = v5;
    }
    v1 = *(_QWORD *)(v1 + 536);
  }
  v6 = (wchar_t *)AllocADsMem(0x250u);
  v7 = v6;
  if ( v6 )
  {
    wcscpy_s(v6, 0x104u, Source);
    v8 = *(_OWORD *)(Source + 260);
    *((_QWORD *)v7 + 71) = v3;
    *((_QWORD *)v7 + 67) = 0;
    *(_OWORD *)(v7 + 260) = v8;
    *((_QWORD *)v7 + 68) = 0;
    *((_QWORD *)v7 + 69) = 0;
    *((_DWORD *)v7 + 140) = 0;
    *((_DWORD *)v7 + 144) = -1;
  }
  return v7;
}

```

## disassembly

```asm
0x180017cac  push    rbx
0x180017cae  push    rbp
0x180017caf  push    rsi
0x180017cb0  push    rdi
0x180017cb1  sub     rsp, 28h
0x180017cb5  mov     rbx, [rcx+238h]
0x180017cbc  mov     rsi, rcx
0x180017cbf  xor     ebp, ebp
0x180017cc1  jmp     short loc_180017D07
0x180017cc3  mov     ecx, 220h; cb
0x180017cc8  call    cs:__imp_AllocADsMem
0x180017cce  mov     rdi, rax
0x180017cd1  test    rax, rax
0x180017cd4  jz      short loc_180017D00
0x180017cd6  mov     r8, rbx; Source
0x180017cd9  mov     edx, 104h; SizeInWords
0x180017cde  mov     rcx, rax; Destination
0x180017ce1  call    cs:__imp_wcscpy_s
0x180017ce7  movups  xmm0, xmmword ptr [rbx+208h]
0x180017cee  movdqu  xmmword ptr [rdi+208h], xmm0
0x180017cf6  mov     [rdi+218h], rbp
0x180017cfd  mov     rbp, rdi
0x180017d00  mov     rbx, [rbx+218h]
0x180017d07  test    rbx, rbx
0x180017d0a  jnz     short loc_180017CC3
0x180017d0c  mov     ecx, 250h; cb
0x180017d11  call    cs:__imp_AllocADsMem
0x180017d17  mov     rbx, rax
0x180017d1a  test    rax, rax
0x180017d1d  jz      short loc_180017D7B
0x180017d1f  mov     r8, rsi; Source
0x180017d22  mov     edx, 104h; SizeInWords
0x180017d27  mov     rcx, rax; Destination
0x180017d2a  call    cs:__imp_wcscpy_s
0x180017d30  movups  xmm0, xmmword ptr [rsi+208h]
0x180017d37  mov     [rbx+238h], rbp
0x180017d3e  mov     qword ptr [rbx+218h], 0
0x180017d49  movdqu  xmmword ptr [rbx+208h], xmm0
0x180017d51  mov     qword ptr [rbx+220h], 0
0x180017d5c  mov     qword ptr [rbx+228h], 0
0x180017d67  mov     dword ptr [rbx+230h], 0
0x180017d71  mov     dword ptr [rbx+240h], 0FFFFFFFFh
0x180017d7b  mov     rax, rbx
0x180017d7e  add     rsp, 28h
0x180017d82  pop     rdi
0x180017d83  pop     rsi
0x180017d84  pop     rbp
0x180017d85  pop     rbx
0x180017d86  retn
```
