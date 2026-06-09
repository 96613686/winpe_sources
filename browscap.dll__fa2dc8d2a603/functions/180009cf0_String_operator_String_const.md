# String::operator==(String const &)

- ea: `0x180009cf0`
- end: `0x180009d34`
- name: `??8String@@QEBA_NAEBV0@@Z`
- size: `68`
- prototype: `bool __fastcall(_BYTE *, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007570`
- `0x18000888c`
- `0x180008fa8`
- `0x18000a920`
- `0x18000ae60`

## callees

- `0x180009cf0`

## import_xrefs

- `msvcrt!_stricmp` at `0x180009d24`
- `msvcrt!_stricmp` at `0x180009d24`

## pseudocode

```c
bool __fastcall String::operator==(_BYTE *a1, __int64 a2)
{
  const char *v2; // rdx
  const char *v3; // r8
  signed __int64 v4; // rdx
  int v5; // ecx
  int v6; // eax

  v2 = *(const char **)(*(_QWORD *)a2 + 32LL);
  v3 = *(const char **)(*(_QWORD *)a1 + 32LL);
  if ( a1[8] )
  {
    v4 = v2 - v3;
    do
    {
      v5 = (unsigned __int8)v3[v4];
      v6 = *(unsigned __int8 *)v3 - v5;
      if ( v6 )
        break;
      ++v3;
    }
    while ( v5 );
  }
  else
  {
    v6 = _stricmp(*(const char **)(*(_QWORD *)a1 + 32LL), v2);
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x180009cf0  sub     rsp, 28h
0x180009cf4  cmp     byte ptr [rcx+8], 0
0x180009cf8  mov     rax, [rdx]
0x180009cfb  mov     rdx, [rax+20h]; String2
0x180009cff  mov     rax, [rcx]
0x180009d02  mov     r8, [rax+20h]
0x180009d06  jz      short loc_180009D21
0x180009d08  sub     rdx, r8
0x180009d0b  movzx   eax, byte ptr [r8]
0x180009d0f  movzx   ecx, byte ptr [r8+rdx]
0x180009d14  sub     eax, ecx
0x180009d16  jnz     short loc_180009D2A
0x180009d18  inc     r8
0x180009d1b  test    ecx, ecx
0x180009d1d  jnz     short loc_180009D0B
0x180009d1f  jmp     short loc_180009D2A
0x180009d21  mov     rcx, r8; String1
0x180009d24  call    cs:__imp__stricmp
0x180009d2a  test    eax, eax
0x180009d2c  setz    al
0x180009d2f  add     rsp, 28h
0x180009d33  retn
```
