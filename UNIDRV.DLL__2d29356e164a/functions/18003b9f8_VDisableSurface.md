# VDisableSurface

- ea: `0x18003b9f8`
- end: `0x18003bab4`
- name: `VDisableSurface`
- size: `188`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180049340`
- `0x1800493a0`

## callees

- `0x18003b9f8`
- `0x180075010`

## import_xrefs

- `GDI32!EngUnlockSurface` at `0x18003ba37`
- `GDI32!EngUnlockSurface` at `0x18003ba6c`
- `GDI32!EngUnlockSurface` at `0x18003ba37`
- `GDI32!EngUnlockSurface` at `0x18003ba6c`
- `GDI32!EngDeleteSurface` at `0x18003ba4f`
- `GDI32!EngDeleteSurface` at `0x18003ba89`
- `GDI32!EngDeleteSurface` at `0x18003baa0`
- `GDI32!EngDeleteSurface` at `0x18003ba4f`
- `GDI32!EngDeleteSurface` at `0x18003ba89`
- `GDI32!EngDeleteSurface` at `0x18003baa0`

## pseudocode

```c
int __fastcall VDisableSurface(__int64 a1)
{
  int result; // eax
  SURFOBJ *v3; // rcx
  HSURF v4; // rcx
  SURFOBJ *v5; // rcx
  HSURF v6; // rcx

  (*(void (**)(void))(*(_QWORD *)(a1 + 4168) + 64LL))();
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 4144) + 64LL))(a1);
  if ( *(_QWORD *)(a1 + 88) )
  {
    v3 = *(SURFOBJ **)(a1 + 4288);
    if ( v3 )
    {
      EngUnlockSurface(v3);
      v4 = *(HSURF *)(a1 + 4312);
      *(_QWORD *)(a1 + 4288) = 0;
      EngDeleteSurface(v4);
      *(_QWORD *)(a1 + 4312) = 0;
    }
    v5 = *(SURFOBJ **)(a1 + 4280);
    if ( v5 )
    {
      EngUnlockSurface(v5);
      *(_QWORD *)(a1 + 104) = 0;
      *(_QWORD *)(a1 + 4280) = 0;
    }
    result = EngDeleteSurface(*(HSURF *)(a1 + 88));
    *(_QWORD *)(a1 + 88) = 0;
  }
  v6 = *(HSURF *)(a1 + 96);
  if ( v6 )
  {
    result = EngDeleteSurface(v6);
    *(_QWORD *)(a1 + 96) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003b9f8  push    rbx
0x18003b9fa  sub     rsp, 20h
0x18003b9fe  mov     rax, [rcx+1048h]
0x18003ba05  mov     rbx, rcx
0x18003ba08  mov     rax, [rax+40h]
0x18003ba0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba11  mov     rax, [rbx+1030h]
0x18003ba18  mov     rcx, rbx
0x18003ba1b  mov     rax, [rax+40h]
0x18003ba1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba24  cmp     qword ptr [rbx+58h], 0
0x18003ba29  jz      short loc_18003BA97
0x18003ba2b  mov     rcx, [rbx+10C0h]; pso
0x18003ba32  test    rcx, rcx
0x18003ba35  jz      short loc_18003BA60
0x18003ba37  call    cs:__imp_EngUnlockSurface
0x18003ba3d  mov     rcx, [rbx+10D8h]; hsurf
0x18003ba44  mov     qword ptr [rbx+10C0h], 0
0x18003ba4f  call    cs:__imp_EngDeleteSurface
0x18003ba55  mov     qword ptr [rbx+10D8h], 0
0x18003ba60  mov     rcx, [rbx+10B8h]; pso
0x18003ba67  test    rcx, rcx
0x18003ba6a  jz      short loc_18003BA85
0x18003ba6c  call    cs:__imp_EngUnlockSurface
0x18003ba72  mov     qword ptr [rbx+68h], 0
0x18003ba7a  mov     qword ptr [rbx+10B8h], 0
0x18003ba85  mov     rcx, [rbx+58h]; hsurf
0x18003ba89  call    cs:__imp_EngDeleteSurface
0x18003ba8f  mov     qword ptr [rbx+58h], 0
0x18003ba97  mov     rcx, [rbx+60h]; hsurf
0x18003ba9b  test    rcx, rcx
0x18003ba9e  jz      short loc_18003BAAE
0x18003baa0  call    cs:__imp_EngDeleteSurface
0x18003baa6  mov     qword ptr [rbx+60h], 0
0x18003baae  add     rsp, 20h
0x18003bab2  pop     rbx
0x18003bab3  retn
```
