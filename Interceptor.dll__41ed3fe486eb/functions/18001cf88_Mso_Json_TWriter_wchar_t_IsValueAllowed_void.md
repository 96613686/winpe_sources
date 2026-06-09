# Mso::Json::TWriter<wchar_t>::IsValueAllowed(void)

- ea: `0x18001cf88`
- end: `0x18001d007`
- name: `?IsValueAllowed@?$TWriter@_W@Json@Mso@@QEBA_NXZ`
- size: `127`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001b880`
- `0x18001b900`
- `0x18001ba30`
- `0x18001bab0`
- `0x18001bb00`
- `0x18001bb50`
- `0x18001bba0`
- `0x18001bbf0`
- `0x18001bc40`
- `0x18001bc80`
- `0x18001c2b0`
- `0x18001c490`
- `0x18001c850`
- `0x18001c9d0`
- `0x18001ca40`
- `0x18001cab0`
- `0x18001cb20`
- `0x18001cb90`
- `0x18001ce10`
- `0x18001ce80`

## callees

- `0x18001cf88`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001cfca`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001cfca`

## pseudocode

```c
bool __fastcall Mso::Json::TWriter<wchar_t>::IsValueAllowed(__int64 a1)
{
  int v2; // edx
  int v3; // edx
  int v4; // edx
  __int64 v6; // rcx

  if ( !*(_BYTE *)(a1 + 92) )
    return 1;
  v2 = *(_DWORD *)(a1 + 88);
  if ( !v2 )
    return 1;
  v3 = v2 - 2;
  if ( !v3 )
    return 1;
  v4 = v3 - 1;
  if ( v4 && (unsigned int)(v4 - 1) >= 2 )
    return 0;
  v6 = *(_QWORD *)(a1 + 80);
  if ( !v6 )
    _invoke_watson(0, 0, 0, 0, 0);
  return *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 56)
                               + 8
                               * ((*(_QWORD *)(a1 + 64) - 1LL) & ((unsigned __int64)(v6 - 1 + *(_QWORD *)(a1 + 72)) >> 2)))
                   + 4LL * (((_DWORD)v6 - 1 + *(_DWORD *)(a1 + 72)) & 3)) == 0;
}

```

## disassembly

```asm
0x18001cf88  sub     rsp, 38h
0x18001cf8c  xor     r9d, r9d; LineNo
0x18001cf8f  mov     r8, rcx
0x18001cf92  cmp     [rcx+5Ch], r9b
0x18001cf96  jz      short loc_18001D000
0x18001cf98  mov     edx, [rcx+58h]
0x18001cf9b  test    edx, edx
0x18001cf9d  jz      short loc_18001D000
0x18001cf9f  sub     edx, 2
0x18001cfa2  jz      short loc_18001D000
0x18001cfa4  sub     edx, 1
0x18001cfa7  jz      short loc_18001CFB7
0x18001cfa9  sub     edx, 1
0x18001cfac  jz      short loc_18001CFB7
0x18001cfae  cmp     edx, 1
0x18001cfb1  jz      short loc_18001CFB7
0x18001cfb3  xor     al, al
0x18001cfb5  jmp     short loc_18001D002
0x18001cfb7  mov     rcx, [rcx+50h]; Expression
0x18001cfbb  test    rcx, rcx
0x18001cfbe  jnz     short loc_18001CFD1
0x18001cfc0  xor     r8d, r8d; FileName
0x18001cfc3  mov     [rsp+38h+Reserved], r9; Reserved
0x18001cfc8  xor     edx, edx; FunctionName
0x18001cfca  call    cs:__imp__invoke_watson
0x18001cfd1  mov     rdx, [r8+48h]
0x18001cfd5  dec     rcx
0x18001cfd8  mov     rax, [r8+40h]
0x18001cfdc  add     rdx, rcx
0x18001cfdf  dec     rax
0x18001cfe2  mov     rcx, rdx
0x18001cfe5  shr     rcx, 2
0x18001cfe9  and     edx, 3
0x18001cfec  and     rcx, rax
0x18001cfef  mov     rax, [r8+38h]
0x18001cff3  mov     rax, [rax+rcx*8]
0x18001cff7  cmp     [rax+rdx*4], r9d
0x18001cffb  setz    al
0x18001cffe  jmp     short loc_18001D002
0x18001d000  mov     al, 1
0x18001d002  add     rsp, 38h
0x18001d006  retn
```
