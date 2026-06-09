# ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)

- ea: `0x18000ef18`
- end: `0x18000ef85`
- name: `?RemoveAll@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ`
- size: `109`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000eebc`
- `0x180012050`
- `0x1800145d4`
- `0x18001d958`

## callees

- `0x18000b554`
- `0x18000ef18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ef70`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ef70`

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
0x18000ef18  mov     [rsp+arg_0], rbx
0x18000ef1d  mov     [rsp+arg_8], rsi
0x18000ef22  push    rdi
0x18000ef23  sub     rsp, 20h
0x18000ef27  cmp     qword ptr [rcx], 0
0x18000ef2b  lea     rdi, [rcx+8]
0x18000ef2f  mov     rbx, rcx
0x18000ef32  jnz     short loc_18000EF52
0x18000ef34  mov     rsi, [rsp+28h+arg_8]
0x18000ef39  mov     dword ptr [rbx+0Ch], 0
0x18000ef40  mov     rbx, [rsp+28h+arg_0]
0x18000ef45  mov     dword ptr [rdi], 0
0x18000ef4b  add     rsp, 20h
0x18000ef4f  pop     rdi
0x18000ef50  retn
0x18000ef52  xor     esi, esi
0x18000ef54  cmp     [rdi], esi
0x18000ef56  jle     short loc_18000EF6D
0x18000ef58  mov     rax, [rbx]
0x18000ef5b  movsxd  rcx, esi
0x18000ef5e  lea     rcx, [rax+rcx*8]
0x18000ef62  call    ??_G?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::`scalar deleting destructor'(uint)
0x18000ef67  inc     esi
0x18000ef69  cmp     esi, [rdi]
0x18000ef6b  jl      short loc_18000EF58
0x18000ef6d  mov     rcx, [rbx]; Block
0x18000ef70  call    cs:__imp_free
0x18000ef77  nop     dword ptr [rax+rax+00h]
0x18000ef7c  mov     qword ptr [rbx], 0
0x18000ef83  jmp     short loc_18000EF34
```
