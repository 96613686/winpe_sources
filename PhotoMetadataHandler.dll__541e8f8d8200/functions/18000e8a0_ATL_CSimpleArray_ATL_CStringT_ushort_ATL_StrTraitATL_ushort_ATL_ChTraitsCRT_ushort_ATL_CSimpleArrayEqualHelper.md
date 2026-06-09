# ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)

- ea: `0x18000e8a0`
- end: `0x18000e906`
- name: `?RemoveAll@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ`
- size: `102`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e84c`
- `0x180011838`
- `0x180013c28`
- `0x18001cbc4`

## callees

- `0x18000b010`
- `0x18000e8a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e8f7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e8f7`

## pseudocode

```c
void __fastcall ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(
        __int64 a1)
{
  _DWORD *v1; // rdi
  int i; // esi

  v1 = (_DWORD *)(a1 + 8);
  if ( *(_QWORD *)a1 )
  {
    for ( i = 0; i < *v1; ++i )
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::`scalar deleting destructor'(*(_QWORD *)a1 + 8LL * i);
    free(*(void **)a1);
    *(_QWORD *)a1 = 0;
  }
  *(_DWORD *)(a1 + 12) = 0;
  *v1 = 0;
}

```

## disassembly

```asm
0x18000e8a0  mov     [rsp+arg_0], rbx
0x18000e8a5  mov     [rsp+arg_8], rsi
0x18000e8aa  push    rdi
0x18000e8ab  sub     rsp, 20h
0x18000e8af  cmp     qword ptr [rcx], 0
0x18000e8b3  lea     rdi, [rcx+8]
0x18000e8b7  mov     rbx, rcx
0x18000e8ba  jnz     short loc_18000E8D9
0x18000e8bc  mov     rsi, [rsp+28h+arg_8]
0x18000e8c1  mov     dword ptr [rbx+0Ch], 0
0x18000e8c8  mov     rbx, [rsp+28h+arg_0]
0x18000e8cd  mov     dword ptr [rdi], 0
0x18000e8d3  add     rsp, 20h
0x18000e8d7  pop     rdi
0x18000e8d8  retn
0x18000e8d9  xor     esi, esi
0x18000e8db  cmp     [rdi], esi
0x18000e8dd  jle     short loc_18000E8F4
0x18000e8df  mov     rax, [rbx]
0x18000e8e2  movsxd  rcx, esi
0x18000e8e5  lea     rcx, [rax+rcx*8]
0x18000e8e9  call    ??_G?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::`scalar deleting destructor'(uint)
0x18000e8ee  inc     esi
0x18000e8f0  cmp     esi, [rdi]
0x18000e8f2  jl      short loc_18000E8DF
0x18000e8f4  mov     rcx, [rbx]; Block
0x18000e8f7  call    cs:__imp_free
0x18000e8fd  mov     qword ptr [rbx], 0
0x18000e904  jmp     short loc_18000E8BC
```
