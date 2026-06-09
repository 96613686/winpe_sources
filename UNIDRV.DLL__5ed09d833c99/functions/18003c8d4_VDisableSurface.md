# VDisableSurface

- ea: `0x18003c8d4`
- end: `0x18003c9b3`
- name: `VDisableSurface`
- size: `223`
- prototype: `int __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18004a890`
- `0x18004a8f0`

## callees

- `0x18003c8d4`
- `0x180077010`

## import_xrefs

- `GDI32!EngUnlockSurface` at `0x18003c917`
- `GDI32!EngUnlockSurface` at `0x18003c958`
- `GDI32!EngUnlockSurface` at `0x18003c917`
- `GDI32!EngUnlockSurface` at `0x18003c958`
- `GDI32!EngDeleteSurface` at `0x18003c935`
- `GDI32!EngDeleteSurface` at `0x18003c97b`
- `GDI32!EngDeleteSurface` at `0x18003c998`
- `GDI32!EngDeleteSurface` at `0x18003c935`
- `GDI32!EngDeleteSurface` at `0x18003c97b`
- `GDI32!EngDeleteSurface` at `0x18003c998`

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
0x18003c8d4  push    rbx
0x18003c8d6  sub     rsp, 20h
0x18003c8da  mov     rax, [rcx+1048h]
0x18003c8e1  mov     rbx, rcx
0x18003c8e4  mov     rax, [rax+40h]
0x18003c8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8ed  mov     rax, [rbx+1030h]
0x18003c8f4  mov     rcx, rbx
0x18003c8f7  mov     rax, [rax+40h]
0x18003c8fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c900  cmp     qword ptr [rbx+58h], 0
0x18003c905  jz      loc_18003C98F
0x18003c90b  mov     rcx, [rbx+10C0h]; pso
0x18003c912  test    rcx, rcx
0x18003c915  jz      short loc_18003C94C
0x18003c917  call    cs:__imp_EngUnlockSurface
0x18003c91e  nop     dword ptr [rax+rax+00h]
0x18003c923  mov     rcx, [rbx+10D8h]; hsurf
0x18003c92a  mov     qword ptr [rbx+10C0h], 0
0x18003c935  call    cs:__imp_EngDeleteSurface
0x18003c93c  nop     dword ptr [rax+rax+00h]
0x18003c941  mov     qword ptr [rbx+10D8h], 0
0x18003c94c  mov     rcx, [rbx+10B8h]; pso
0x18003c953  test    rcx, rcx
0x18003c956  jz      short loc_18003C977
0x18003c958  call    cs:__imp_EngUnlockSurface
0x18003c95f  nop     dword ptr [rax+rax+00h]
0x18003c964  mov     qword ptr [rbx+68h], 0
0x18003c96c  mov     qword ptr [rbx+10B8h], 0
0x18003c977  mov     rcx, [rbx+58h]; hsurf
0x18003c97b  call    cs:__imp_EngDeleteSurface
0x18003c982  nop     dword ptr [rax+rax+00h]
0x18003c987  mov     qword ptr [rbx+58h], 0
0x18003c98f  mov     rcx, [rbx+60h]; hsurf
0x18003c993  test    rcx, rcx
0x18003c996  jz      short loc_18003C9AC
0x18003c998  call    cs:__imp_EngDeleteSurface
0x18003c99f  nop     dword ptr [rax+rax+00h]
0x18003c9a4  mov     qword ptr [rbx+60h], 0
0x18003c9ac  add     rsp, 20h
0x18003c9b0  pop     rbx
0x18003c9b1  retn
```
