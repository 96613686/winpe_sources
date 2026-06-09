# CTemplate::AppendMapFile(ushort const *,CTemplate::CFileMap *,uchar,CHitObj *,uchar)

- ea: `0x180014970`
- end: `0x180014a9b`
- name: `?AppendMapFile@CTemplate@@AEAAXPEBGPEAVCFileMap@1@EPEAVCHitObj@@E@Z`
- size: `299`
- prototype: `void __fastcall(CTemplate *this, const unsigned __int16 *, wchar_t **, unsigned __int8, struct CHitObj *, unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800140a0`
- `0x18005e24c`

## callees

- `0x180014970`
- `0x18001650c`
- `0x180016918`
- `0x180017a8c`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800149b6`
- `KERNEL32!HeapAlloc` at `0x1800149b6`
- `KERNEL32!RaiseException` at `0x18002c3e3`
- `KERNEL32!RaiseException` at `0x18002c3fc`
- `KERNEL32!RaiseException` at `0x18002c3e3`
- `KERNEL32!RaiseException` at `0x18002c3fc`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800149d3`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800149d3`

## pseudocode

```c
void __fastcall CTemplate::AppendMapFile(
        CTemplate *this,
        const unsigned __int16 *a2,
        wchar_t **a3,
        unsigned __int8 a4,
        struct CHitObj *a5,
        unsigned __int8 a6)
{
  int v6; // eax
  int v8; // edi
  SIZE_T v11; // rax
  LPVOID v12; // rax
  char *v13; // rax
  const unsigned __int16 *v14; // r8
  char *v15; // rcx

  v6 = *((_DWORD *)this + 74);
  v8 = a4;
  *((_DWORD *)this + 74) = v6 + 1;
  if ( v6 )
  {
    v12 = CTemplate::SmallReAlloc(*((void **)this + 34), 8LL * (unsigned int)(v6 + 1));
  }
  else
  {
    v11 = _RoundUp(8u);
    v12 = HeapAlloc(CTemplate::sm_hSmallHeap, 0, v11);
  }
  *((_QWORD *)this + 34) = v12;
  if ( !v12 )
    RaiseException(0x8007000E, 0, 0, 0);
  v13 = (char *)ALLOC_CACHE_HANDLER::Alloc(CTemplate::CFileMap::sm_pach);
  v15 = v13;
  if ( v13 )
  {
    *((_DWORD *)v13 + 18) &= 0xC0000000;
    *((_DWORD *)v13 + 19) &= 0xFFFFFFFC;
    *(_QWORD *)v13 = 0;
    *((_QWORD *)v13 + 1) = 0;
    *((_QWORD *)v13 + 2) = 0;
    *((_QWORD *)v13 + 3) = 0;
    *((_QWORD *)v13 + 4) = 0;
    *((_QWORD *)v13 + 5) = 0;
    *((_QWORD *)v13 + 6) = 0;
    *((_QWORD *)v13 + 7) = 0;
    *((_QWORD *)v13 + 8) = 0;
    *(_QWORD *)(v13 + 84) = 0;
    *((_QWORD *)v13 + 12) = 0;
    *((_QWORD *)v13 + 13) = 0;
    *((_QWORD *)v13 + 14) = 0;
    *((_QWORD *)v13 + 15) = 0;
    *((_DWORD *)v13 + 32) = 0;
    *((_DWORD *)v13 + 20) = 0;
  }
  else
  {
    v15 = 0;
  }
  *(_QWORD *)(*((_QWORD *)this + 34) + 8LL * (unsigned int)(*((_DWORD *)this + 74) - 1)) = v15;
  if ( !v15 )
    RaiseException(0x8007000E, 0, 0, 0);
  CTemplate::CFileMap::MapFile(
    *(CTemplate::CFileMap **)(*((_QWORD *)this + 34) + 8LL * (unsigned int)(*((_DWORD *)this + 74) - 1)),
    a2,
    v14,
    a3,
    v8,
    a5,
    a6);
}

```

## disassembly

```asm
0x180014970  push    rbx
0x180014972  push    rbp
0x180014973  push    rsi
0x180014974  push    rdi
0x180014975  push    r14
0x180014977  sub     rsp, 40h
0x18001497b  mov     eax, [rcx+128h]
0x180014981  mov     rbx, rcx
0x180014984  xor     r14d, r14d
0x180014987  movzx   edi, r9b
0x18001498b  mov     rsi, r8
0x18001498e  mov     rbp, rdx
0x180014991  lea     ecx, [rax+1]
0x180014994  mov     [rbx+128h], ecx
0x18001499a  test    eax, eax
0x18001499c  jnz     loc_18002C3BE
0x1800149a2  lea     ecx, [rax+8]; unsigned __int64
0x1800149a5  call    ?_RoundUp@@YA_K_K@Z; _RoundUp(unsigned __int64)
0x1800149aa  mov     rcx, cs:?sm_hSmallHeap@CTemplate@@2PEAXEA; hHeap
0x1800149b1  mov     r8, rax; dwBytes
0x1800149b4  xor     edx, edx; dwFlags
0x1800149b6  call    cs:__imp_HeapAlloc
0x1800149bc  mov     [rbx+110h], rax
0x1800149c3  test    rax, rax
0x1800149c6  jz      loc_18002C3D6
0x1800149cc  mov     rcx, cs:?sm_pach@CFileMap@CTemplate@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CTemplate::CFileMap::sm_pach
0x1800149d3  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x1800149d9  mov     rcx, rax
0x1800149dc  test    rax, rax
0x1800149df  jz      loc_180014A96
0x1800149e5  and     dword ptr [rax+48h], 0C0000000h
0x1800149ec  and     dword ptr [rax+4Ch], 0FFFFFFFCh
0x1800149f0  mov     [rax], r14
0x1800149f3  mov     [rax+8], r14
0x1800149f7  mov     [rax+10h], r14
0x1800149fb  mov     [rax+18h], r14
0x1800149ff  mov     [rax+20h], r14
0x180014a03  mov     [rax+28h], r14
0x180014a07  mov     [rax+30h], r14
0x180014a0b  mov     [rax+38h], r14
0x180014a0f  mov     [rax+40h], r14
0x180014a13  mov     [rax+54h], r14
0x180014a17  mov     [rax+60h], r14
0x180014a1b  mov     [rax+68h], r14
0x180014a1f  mov     [rax+70h], r14
0x180014a23  mov     [rax+78h], r14
0x180014a27  mov     [rax+80h], r14d
0x180014a2e  mov     [rax+50h], r14d
0x180014a32  mov     edx, [rbx+128h]
0x180014a38  mov     rax, [rbx+110h]
0x180014a3f  dec     edx
0x180014a41  mov     [rax+rdx*8], rcx
0x180014a45  test    rcx, rcx
0x180014a48  jz      loc_18002C3EF
0x180014a4e  mov     r10d, [rbx+128h]
0x180014a55  mov     r9, rsi; struct CTemplate::CFileMap *
0x180014a58  mov     rcx, [rbx+110h]
0x180014a5f  dec     r10d
0x180014a62  movzx   edx, [rsp+68h+arg_28]
0x180014a6a  mov     rax, [rsp+68h+arg_20]
0x180014a72  mov     [rsp+68h+var_38], edx; int
0x180014a76  mov     rdx, rbp; unsigned __int16 *
0x180014a79  mov     rcx, [rcx+r10*8]; this
0x180014a7d  mov     [rsp+68h+var_40], rax; struct CHitObj *
0x180014a82  mov     [rsp+68h+var_48], edi; int
0x180014a86  call    ?MapFile@CFileMap@CTemplate@@QEAAXPEBG0PEAV12@HPEAVCHitObj@@H@Z; CTemplate::CFileMap::MapFile(ushort const *,ushort const *,CTemplate::CFileMap *,int,CHitObj *,int)
0x180014a8b  add     rsp, 40h
0x180014a8f  pop     r14
0x180014a91  pop     rdi
0x180014a92  pop     rsi
0x180014a93  pop     rbp
0x180014a94  pop     rbx
0x180014a95  retn
0x180014a96  mov     rcx, r14
0x180014a99  jmp     short loc_180014A32
0x18002c3be  mov     edx, ecx
0x18002c3c0  mov     rcx, [rbx+110h]; void *
0x18002c3c7  shl     rdx, 3; unsigned __int64
0x18002c3cb  call    ?SmallReAlloc@CTemplate@@SAPEAXPEAX_K@Z; CTemplate::SmallReAlloc(void *,unsigned __int64)
0x18002c3d0  nop
0x18002c3d1  jmp     loc_1800149BC
0x18002c3d6  xor     r9d, r9d; lpArguments
0x18002c3d9  xor     r8d, r8d; nNumberOfArguments
0x18002c3dc  xor     edx, edx; dwExceptionFlags
0x18002c3de  mov     ecx, 8007000Eh; dwExceptionCode
0x18002c3e3  call    cs:__imp_RaiseException
0x18002c3e9  nop
0x18002c3ea  jmp     loc_1800149CC
0x18002c3ef  xor     r9d, r9d; lpArguments
0x18002c3f2  xor     r8d, r8d; nNumberOfArguments
0x18002c3f5  xor     edx, edx; dwExceptionFlags
0x18002c3f7  mov     ecx, 8007000Eh; dwExceptionCode
0x18002c3fc  call    cs:__imp_RaiseException
0x18002c402  nop
0x18002c403  jmp     loc_180014A4E
```
