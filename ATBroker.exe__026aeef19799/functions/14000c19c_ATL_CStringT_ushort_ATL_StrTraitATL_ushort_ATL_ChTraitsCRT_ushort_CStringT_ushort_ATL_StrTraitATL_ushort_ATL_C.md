# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)

- ea: `0x14000c19c`
- end: `0x14000c219`
- name: `??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z`
- size: `125`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x14000c340`
- `0x14000d1b8`
- `0x14000e538`
- `0x14000ee8c`
- `0x140010960`
- `0x140015830`

## callees

- `0x140006c00`
- `0x14000c19c`
- `0x14000cb50`
- `0x140017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        __int64 *a1,
        const void *a2)
{
  __int64 v4; // r8

  *a1 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !a2 )
  {
    LODWORD(v4) = 0;
LABEL_8:
    ATL::CSimpleStringT<unsigned short,0>::SetString(a1, a2, v4);
    return a1;
  }
  if ( (unsigned __int64)a2 >= 0x10000 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *((_WORD *)a2 + v4) );
    goto LABEL_8;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
    a1,
    (unsigned __int16)a2);
  return a1;
}

```

## disassembly

```asm
0x14000c19c  mov     [rsp+arg_8], rbx
0x14000c1a1  mov     [rsp+arg_0], rcx
0x14000c1a6  push    rdi
0x14000c1a7  sub     rsp, 20h
0x14000c1ab  mov     rbx, rdx
0x14000c1ae  mov     rdi, rcx
0x14000c1b1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000c1b8  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000c1bf  mov     rax, [rax+18h]
0x14000c1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c1c8  add     rax, 18h
0x14000c1cc  mov     [rdi], rax
0x14000c1cf  xor     eax, eax
0x14000c1d1  test    rbx, rbx
0x14000c1d4  jz      short loc_14000C1FC
0x14000c1d6  cmp     rbx, 10000h
0x14000c1dd  jnb     short loc_14000C1EC
0x14000c1df  movzx   edx, bx
0x14000c1e2  mov     rcx, rdi
0x14000c1e5  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x14000c1ea  jmp     short loc_14000C20B
0x14000c1ec  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000c1f0  inc     r8
0x14000c1f3  cmp     [rbx+r8*2], ax
0x14000c1f8  jnz     short loc_14000C1F0
0x14000c1fa  jmp     short loc_14000C1FF
0x14000c1fc  mov     r8d, eax
0x14000c1ff  mov     rdx, rbx
0x14000c202  mov     rcx, rdi
0x14000c205  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000c20a  nop
0x14000c20b  mov     rax, rdi
0x14000c20e  mov     rbx, [rsp+28h+arg_8]
0x14000c213  add     rsp, 20h
0x14000c217  pop     rdi
0x14000c218  retn
```
