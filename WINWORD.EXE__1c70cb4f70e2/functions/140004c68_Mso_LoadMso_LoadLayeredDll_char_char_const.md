# Mso::LoadMso::LoadLayeredDll<char>(char const *)

- ea: `0x140004c68`
- end: `0x140004cd9`
- name: `??$LoadLayeredDll@D@LoadMso@Mso@@YAPEAUHINSTANCE__@@PEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(char *String2)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400014c0`

## callees

- `0x140004474`
- `0x140004c68`
- `0x1400055d4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_stricmp` at `0x140004c8f`
- `api-ms-win-crt-string-l1-1-0!_stricmp` at `0x140004c8f`

## pseudocode

```c
HINSTANCE __fastcall Mso::LoadMso::LoadLayeredDll<char>(char *String2)
{
  __int64 *v2; // rbx
  HINSTANCE result; // rax
  const wchar_t *v4; // rdx

  v2 = &qword_140009800;
  while ( _stricmp((const char *)v2[2], String2) )
  {
    v2 += 17;
    if ( v2 == (__int64 *)&dword_140009B30 )
      return 0;
  }
  sub_1400055D4(*(unsigned int *)v2);
  result = (HINSTANCE)v2[3];
  if ( !result )
  {
    result = Mso::SafeLoadLibrary((const WCHAR *)v2[1], v4, 0);
    v2[3] = (__int64)result;
  }
  return result;
}

```

## disassembly

```asm
0x140004c68  mov     [rsp+arg_0], rbx
0x140004c6d  mov     [rsp+arg_8], rsi
0x140004c72  push    rdi
0x140004c73  sub     rsp, 20h
0x140004c77  mov     rdi, rcx
0x140004c7a  lea     rbx, qword_140009800
0x140004c81  lea     rsi, dword_140009B30
0x140004c88  mov     rcx, [rbx+10h]; String1
0x140004c8c  mov     rdx, rdi; String2
0x140004c8f  call    cs:__imp__stricmp
0x140004c95  test    eax, eax
0x140004c97  jz      short loc_140004CA9
0x140004c99  add     rbx, 88h
0x140004ca0  cmp     rbx, rsi
0x140004ca3  jnz     short loc_140004C88
0x140004ca5  xor     eax, eax
0x140004ca7  jmp     short loc_140004CC9
0x140004ca9  mov     ecx, [rbx]
0x140004cab  call    sub_1400055D4
0x140004cb0  mov     rax, [rbx+18h]
0x140004cb4  test    rax, rax
0x140004cb7  jnz     short loc_140004CC9
0x140004cb9  mov     rcx, [rbx+8]; this
0x140004cbd  xor     r8d, r8d; void *
0x140004cc0  call    ?SafeLoadLibrary@Mso@@YAPEAUHINSTANCE__@@PEB_WPEAXK@Z; Mso::SafeLoadLibrary(wchar_t const *,void *,ulong)
0x140004cc5  mov     [rbx+18h], rax
0x140004cc9  mov     rbx, [rsp+28h+arg_0]
0x140004cce  mov     rsi, [rsp+28h+arg_8]
0x140004cd3  add     rsp, 20h
0x140004cd7  pop     rdi
0x140004cd8  retn
```
