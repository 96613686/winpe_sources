# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x180028610`
- end: `0x1800286a6`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `5`
- tags: ``

## callers

- `0x180023a78`
- `0x180024370`
- `0x18002522c`
- `0x180025614`
- `0x1800256fc`
- `0x180025a50`
- `0x180028160`
- `0x180028434`
- `0x180029208`
- `0x18002940c`
- `0x1800298e4`
- `0x18002fd88`

## callees

- `0x18001f6ec`
- `0x180024d1c`
- `0x1800270dc`
- `0x180028128`
- `0x180028610`

## import_xrefs

- `msvcrt!memmove_s` at `0x180028680`
- `msvcrt!memmove_s` at `0x180028680`
- `msvcrt!memcpy_s` at `0x18002868b`
- `msvcrt!memcpy_s` at `0x18002868b`

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
    return ATL::CSimpleStringT<unsigned short,0>::Empty();
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
0x180028610  push    rbx
0x180028612  push    rbp
0x180028613  push    rsi
0x180028614  push    rdi
0x180028615  push    r14
0x180028617  sub     rsp, 20h
0x18002861b  movsxd  rdi, r8d
0x18002861e  mov     rbp, rdx
0x180028621  mov     rbx, rcx
0x180028624  test    r8d, r8d
0x180028627  jnz     short loc_180028630
0x180028629  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18002862e  jmp     short loc_18002869B
0x180028630  test    rbp, rbp
0x180028633  jnz     short loc_180028640
0x180028635  mov     ecx, 80070057h; int
0x18002863a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180028640  mov     rax, [rcx]
0x180028643  mov     rsi, rbp
0x180028646  sub     rsi, rax
0x180028649  mov     ecx, 1
0x18002864e  sar     rsi, 1
0x180028651  sub     ecx, [rax-8]
0x180028654  mov     r14d, [rax-10h]
0x180028658  mov     eax, [rax-0Ch]
0x18002865b  sub     eax, edi
0x18002865d  or      ecx, eax
0x18002865f  jge     short loc_18002866B
0x180028661  mov     edx, edi
0x180028663  mov     rcx, rbx
0x180028666  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002866b  mov     rcx, [rbx]; Destination
0x18002866e  mov     rdx, rdi
0x180028671  add     rdx, rdx; DestinationSize
0x180028674  mov     r9, rdx; SourceSize
0x180028677  cmp     rsi, r14
0x18002867a  ja      short loc_180028688
0x18002867c  lea     r8, [rcx+rsi*2]; Source
0x180028680  call    cs:__imp_memmove_s
0x180028686  jmp     short loc_180028691
0x180028688  mov     r8, rbp; Source
0x18002868b  call    cs:__imp_memcpy_s
0x180028691  mov     edx, edi
0x180028693  mov     rcx, rbx
0x180028696  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18002869b  add     rsp, 20h
0x18002869f  pop     r14
0x1800286a1  pop     rdi
0x1800286a2  pop     rsi
0x1800286a3  pop     rbp
0x1800286a4  pop     rbx
0x1800286a5  retn
```
