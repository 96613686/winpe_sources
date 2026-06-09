# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x180011ef4`
- end: `0x180011f8a`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `75`
- callee_count: `5`
- tags: ``

## callers

- `0x1800049a4`
- `0x180004aa0`
- `0x180006564`
- `0x1800068f0`
- `0x180006b20`
- `0x180007570`
- `0x180008f2c`
- `0x180009c7c`
- `0x18000a26c`
- `0x18000b948`
- `0x18000dcc8`
- `0x18000ea90`
- `0x18000f254`
- `0x18000febc`
- `0x180011118`
- `0x180011e58`
- `0x180019724`
- `0x180019904`
- `0x18001e51c`
- `0x18001f750`
- `0x18001faf4`
- `0x1800201f8`
- `0x180020358`
- `0x180022020`
- `0x180023764`
- `0x180025180`
- `0x180028220`
- `0x1800293fc`
- `0x180029734`
- `0x18002a450`
- `0x18002ade8`
- `0x18002af70`
- `0x18002b050`
- `0x18002b460`
- `0x18002b5e0`
- `0x18002ba04`
- `0x18002c44c`
- `0x1800308cc`
- `0x180030d4c`
- `0x1800325f4`
- `0x1800346cc`
- `0x18003552c`
- `0x180035cd0`
- `0x180037e48`
- `0x1800380a0`
- `0x18003f4b8`
- `0x180041cb0`
- `0x180047a70`
- `0x180047d1c`
- `0x18004a898`

## callees

- `0x180006828`
- `0x180008104`
- `0x18000c604`
- `0x180011e20`
- `0x180011ef4`

## import_xrefs

- `msvcrt!memmove_s` at `0x180011f64`
- `msvcrt!memmove_s` at `0x180011f64`
- `msvcrt!memcpy_s` at `0x180011f6f`
- `msvcrt!memcpy_s` at `0x180011f6f`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(char **a1, _BYTE *a2, unsigned int a3)
{
  __int64 v3; // rdi
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // r14
  char *v9; // rcx
  rsize_t v10; // rdx
  rsize_t v11; // r9

  v3 = (int)a3;
  if ( !a3 )
    return ATL::CSimpleStringT<unsigned short,0>::Empty(a1);
  if ( !a2 )
    ATL::AtlThrowImpl(-2147024809);
  v7 = (a2 - *a1) >> 1;
  v8 = *((unsigned int *)*a1 - 4);
  if ( (((*((_DWORD *)*a1 - 3) - a3) | (1 - *((_DWORD *)*a1 - 2))) & 0x80000000) != 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
  v9 = *a1;
  v10 = 2 * v3;
  v11 = 2 * v3;
  if ( v7 > v8 )
    memcpy_s(v9, v10, a2, v11);
  else
    memmove_s(v9, v10, &v9[2 * v7], v11);
  return ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, (unsigned int)v3);
}

```

## disassembly

```asm
0x180011ef4  push    rbx
0x180011ef6  push    rbp
0x180011ef7  push    rsi
0x180011ef8  push    rdi
0x180011ef9  push    r14
0x180011efb  sub     rsp, 20h
0x180011eff  movsxd  rdi, r8d
0x180011f02  mov     rbp, rdx
0x180011f05  mov     rbx, rcx
0x180011f08  test    r8d, r8d
0x180011f0b  jnz     short loc_180011F14
0x180011f0d  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180011f12  jmp     short loc_180011F7F
0x180011f14  test    rbp, rbp
0x180011f17  jnz     short loc_180011F24
0x180011f19  mov     ecx, 80070057h; int
0x180011f1e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011f24  mov     rax, [rcx]
0x180011f27  mov     rsi, rbp
0x180011f2a  sub     rsi, rax
0x180011f2d  mov     ecx, 1
0x180011f32  sar     rsi, 1
0x180011f35  sub     ecx, [rax-8]
0x180011f38  mov     r14d, [rax-10h]
0x180011f3c  mov     eax, [rax-0Ch]
0x180011f3f  sub     eax, edi
0x180011f41  or      ecx, eax
0x180011f43  jge     short loc_180011F4F
0x180011f45  mov     edx, edi
0x180011f47  mov     rcx, rbx
0x180011f4a  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180011f4f  mov     rcx, [rbx]; Destination
0x180011f52  mov     rdx, rdi
0x180011f55  add     rdx, rdx; DestinationSize
0x180011f58  mov     r9, rdx; SourceSize
0x180011f5b  cmp     rsi, r14
0x180011f5e  ja      short loc_180011F6C
0x180011f60  lea     r8, [rcx+rsi*2]; Source
0x180011f64  call    cs:__imp_memmove_s
0x180011f6a  jmp     short loc_180011F75
0x180011f6c  mov     r8, rbp; Source
0x180011f6f  call    cs:__imp_memcpy_s
0x180011f75  mov     edx, edi
0x180011f77  mov     rcx, rbx
0x180011f7a  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180011f7f  add     rsp, 20h
0x180011f83  pop     r14
0x180011f85  pop     rdi
0x180011f86  pop     rsi
0x180011f87  pop     rbp
0x180011f88  pop     rbx
0x180011f89  retn
```
