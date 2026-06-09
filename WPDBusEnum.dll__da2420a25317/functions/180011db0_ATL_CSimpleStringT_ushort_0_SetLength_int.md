# ATL::CSimpleStringT<ushort,0>::SetLength(int)

- ea: `0x180011db0`
- end: `0x180011ddf`
- name: `?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `47`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007880`
- `0x180011948`
- `0x180011a5c`
- `0x180011de8`

## callees

- `0x180011780`
- `0x180011db0`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetLength(_QWORD *a1, int a2)
{
  __int64 result; // rax

  if ( a2 < 0 || a2 > *(_DWORD *)(*a1 - 12LL) )
    ATL::AtlThrowImpl(-2147024809);
  *(_DWORD *)(*a1 - 16LL) = a2;
  result = 0;
  *(_WORD *)(*a1 + 2LL * a2) = 0;
  return result;
}

```

## disassembly

```asm
0x180011db0  sub     rsp, 28h
0x180011db4  test    edx, edx
0x180011db6  js      short loc_180011DD4
0x180011db8  mov     rax, [rcx]
0x180011dbb  cmp     edx, [rax-0Ch]
0x180011dbe  jg      short loc_180011DD4
0x180011dc0  mov     [rax-10h], edx
0x180011dc3  xor     eax, eax
0x180011dc5  mov     rcx, [rcx]
0x180011dc8  movsxd  rdx, edx
0x180011dcb  mov     [rcx+rdx*2], ax
0x180011dcf  add     rsp, 28h
0x180011dd3  retn
0x180011dd4  mov     ecx, 80070057h; int
0x180011dd9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
