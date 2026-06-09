# Mso::LoadMso::DllData::DllData(Mso::LoadMso::LayerId,wchar_t const * const,char const * const)

- ea: `0x140001140`
- end: `0x140001194`
- name: `??0DllData@LoadMso@Mso@@QEAA@W4LayerId@12@QEB_WQEBD@Z`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001070`

## pseudocode

```c
__int64 __fastcall Mso::LoadMso::DllData::DllData(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  *(_DWORD *)a1 = a2;
  *(_QWORD *)(a1 + 8) = a3;
  *(_QWORD *)(a1 + 16) = a4;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_OWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 7;
  *(_WORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_DWORD *)(a1 + 80) = 0;
  *(_OWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 7;
  *(_WORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_DWORD *)(a1 + 128) = 0;
  return a1;
}

```

## disassembly

```asm
0x140001140  mov     [rcx], edx
0x140001142  xor     eax, eax
0x140001144  mov     [rcx+8], r8
0x140001148  xorps   xmm0, xmm0
0x14000114b  mov     [rcx+10h], r9
0x14000114f  mov     [rcx+18h], rax
0x140001153  mov     [rcx+20h], rax
0x140001157  movups  xmmword ptr [rcx+28h], xmm0
0x14000115b  mov     [rcx+38h], rax
0x14000115f  mov     qword ptr [rcx+40h], 7
0x140001167  mov     [rcx+28h], ax
0x14000116b  mov     [rcx+48h], rax
0x14000116f  mov     [rcx+50h], eax
0x140001172  movups  xmmword ptr [rcx+58h], xmm0
0x140001176  mov     [rcx+68h], rax
0x14000117a  mov     qword ptr [rcx+70h], 7
0x140001182  mov     [rcx+58h], ax
0x140001186  mov     [rcx+78h], rax
0x14000118a  mov     [rcx+80h], eax
0x140001190  mov     rax, rcx
0x140001193  retn
```
