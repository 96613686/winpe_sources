# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Delete(int,int)

- ea: `0x1800059b0`
- end: `0x180005a42`
- name: `?Delete@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHHH@Z`
- size: `146`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180005a48`
- `0x180029e88`

## callees

- `0x180005420`
- `0x18000546c`
- `0x1800059b0`
- `0x1800069a0`
- `0x180018524`

## import_xrefs

- `msvcrt!memmove_s` at `0x180005a0d`
- `msvcrt!memmove_s` at `0x180005a0d`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Delete(
        _QWORD *a1,
        int a2)
{
  int v2; // edi
  int v4; // esi
  int v5; // ebx
  unsigned int v6; // ebp
  __int64 Buffer; // rax
  errno_t v8; // eax

  v2 = 0;
  if ( a2 >= 0 )
    v2 = a2;
  if ( v2 == 0x7FFFFFFF )
    ATL::AtlThrowImpl(-2147024809);
  v4 = *(_DWORD *)(*a1 - 16LL);
  v5 = v4 - v2;
  if ( v2 + 1 <= v4 )
  {
    v6 = 1;
    goto LABEL_8;
  }
  if ( v5 > 0 )
  {
    v6 = *(_DWORD *)(*a1 - 16LL) - v2;
LABEL_8:
    Buffer = ATL::CSimpleStringT<unsigned short,0>::GetBuffer();
    v8 = memmove_s(
           (void *const)(Buffer + 2LL * v2),
           2LL * (int)(v5 - v6 + 1),
           (const void *const)(Buffer + 2 * (v2 + (unsigned __int64)v6)),
           2LL * (int)(v5 - v6 + 1));
    ATL::AtlCrtErrorCheck(v8);
    ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, v4 - v6);
  }
  return *(unsigned int *)(*a1 - 16LL);
}

```

## disassembly

```asm
0x1800059b0  push    rbx
0x1800059b2  push    rbp
0x1800059b3  push    rsi
0x1800059b4  push    rdi
0x1800059b5  push    r14
0x1800059b7  sub     rsp, 20h
0x1800059bb  xor     edi, edi
0x1800059bd  mov     r14, rcx
0x1800059c0  test    edx, edx
0x1800059c2  cmovns  edi, edx
0x1800059c5  cmp     edi, 7FFFFFFEh
0x1800059cb  jg      short loc_180005A37
0x1800059cd  mov     rax, [rcx]
0x1800059d0  lea     edx, [rdi+1]
0x1800059d3  mov     esi, [rax-10h]
0x1800059d6  mov     ebx, esi
0x1800059d8  sub     ebx, edi
0x1800059da  cmp     edx, esi
0x1800059dc  jle     short loc_1800059E6
0x1800059de  test    ebx, ebx
0x1800059e0  jle     short loc_180005A26
0x1800059e2  mov     ebp, ebx
0x1800059e4  jmp     short loc_1800059EB
0x1800059e6  mov     ebp, 1
0x1800059eb  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800059f0  movsxd  r9, edi
0x1800059f3  sub     ebx, ebp
0x1800059f5  mov     ecx, ebp
0x1800059f7  inc     ebx
0x1800059f9  add     rcx, r9
0x1800059fc  movsxd  rdx, ebx
0x1800059ff  add     rdx, rdx; DestinationSize
0x180005a02  lea     r8, [rax+rcx*2]; Source
0x180005a06  lea     rcx, [rax+r9*2]; Destination
0x180005a0a  mov     r9, rdx; SourceSize
0x180005a0d  call    cs:__imp_memmove_s
0x180005a13  mov     ecx, eax; int
0x180005a15  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180005a1a  sub     esi, ebp
0x180005a1c  mov     rcx, r14
0x180005a1f  mov     edx, esi
0x180005a21  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180005a26  mov     rax, [r14]
0x180005a29  mov     eax, [rax-10h]
0x180005a2c  add     rsp, 20h
0x180005a30  pop     r14
0x180005a32  pop     rdi
0x180005a33  pop     rsi
0x180005a34  pop     rbp
0x180005a35  pop     rbx
0x180005a36  retn
0x180005a37  mov     ecx, 80070057h; int
0x180005a3c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
