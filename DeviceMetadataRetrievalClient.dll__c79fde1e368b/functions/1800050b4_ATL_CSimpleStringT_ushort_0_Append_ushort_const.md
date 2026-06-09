# ATL::CSimpleStringT<ushort,0>::Append(ushort const *)

- ea: `0x1800050b4`
- end: `0x180005169`
- name: `?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(__int64 *, const void *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800061c8`
- `0x180008544`
- `0x18000913c`
- `0x18000a4c4`

## callees

- `0x1800050b4`
- `0x180005170`
- `0x18000823c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000512f`
- `msvcrt!memcpy_s` at `0x18000512f`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::Append(__int64 *a1, const void *a2)
{
  const void *v2; // rbp
  __int64 v4; // rbx
  unsigned __int64 v5; // r14
  unsigned __int64 v6; // r15
  int v7; // edi
  __int64 v8; // rax
  __int64 result; // rax

  v2 = a2;
  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *((_WORD *)a2 + v4) );
  }
  else
  {
    LODWORD(v4) = 0;
  }
  v5 = ((__int64)a2 - *a1) >> 1;
  v6 = *(unsigned int *)(*a1 - 16);
  v7 = v6 + v4;
  if ( (((*(_DWORD *)(*a1 - 12) - (v6 + v4)) | (1 - *(_DWORD *)(*a1 - 8))) & 0x80000000) != 0LL )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)v7);
  v8 = *a1;
  if ( v5 <= v6 )
    v2 = (const void *)(v8 + 2 * v5);
  memcpy_s((void *const)(v8 + 2 * v6), 2LL * (int)v4, v2, 2LL * (int)v4);
  if ( v7 < 0 || (result = *a1, v7 > *(_DWORD *)(*a1 - 12)) )
    ATL::AtlThrowImpl(-2147024809);
  *(_DWORD *)(result - 16) = v7;
  *(_WORD *)(*a1 + 2LL * v7) = 0;
  return result;
}

```

## disassembly

```asm
0x1800050b4  push    rbx
0x1800050b6  push    rbp
0x1800050b7  push    rsi
0x1800050b8  push    rdi
0x1800050b9  push    r12
0x1800050bb  push    r14
0x1800050bd  push    r15
0x1800050bf  sub     rsp, 20h
0x1800050c3  xor     r12d, r12d
0x1800050c6  mov     rbp, rdx
0x1800050c9  mov     rsi, rcx
0x1800050cc  test    rdx, rdx
0x1800050cf  jnz     short loc_1800050D6
0x1800050d1  mov     ebx, r12d
0x1800050d4  jmp     short loc_1800050E4
0x1800050d6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800050da  inc     rbx
0x1800050dd  cmp     [rdx+rbx*2], r12w
0x1800050e2  jnz     short loc_1800050DA
0x1800050e4  mov     rax, [rcx]
0x1800050e7  mov     r14, rdx
0x1800050ea  sub     r14, rax
0x1800050ed  mov     ecx, 1
0x1800050f2  sar     r14, 1
0x1800050f5  mov     r15d, [rax-10h]
0x1800050f9  sub     ecx, [rax-8]
0x1800050fc  mov     eax, [rax-0Ch]
0x1800050ff  lea     edi, [r15+rbx]
0x180005103  sub     eax, edi
0x180005105  or      ecx, eax
0x180005107  jge     short loc_180005113
0x180005109  mov     edx, edi
0x18000510b  mov     rcx, rsi
0x18000510e  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180005113  mov     rax, [rsi]
0x180005116  cmp     r14, r15
0x180005119  ja      short loc_18000511F
0x18000511b  lea     rbp, [rax+r14*2]
0x18000511f  movsxd  rdx, ebx
0x180005122  lea     rcx, [rax+r15*2]; Destination
0x180005126  add     rdx, rdx; DestinationSize
0x180005129  mov     r8, rbp; Source
0x18000512c  mov     r9, rdx; SourceSize
0x18000512f  call    cs:__imp_memcpy_s
0x180005135  test    edi, edi
0x180005137  js      short loc_18000515E
0x180005139  mov     rax, [rsi]
0x18000513c  cmp     edi, [rax-0Ch]
0x18000513f  jg      short loc_18000515E
0x180005141  mov     [rax-10h], edi
0x180005144  mov     rcx, [rsi]
0x180005147  movsxd  rdx, edi
0x18000514a  mov     [rcx+rdx*2], r12w
0x18000514f  add     rsp, 20h
0x180005153  pop     r15
0x180005155  pop     r14
0x180005157  pop     r12
0x180005159  pop     rdi
0x18000515a  pop     rsi
0x18000515b  pop     rbp
0x18000515c  pop     rbx
0x18000515d  retn
0x18000515e  mov     ecx, 80070057h; int
0x180005163  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
