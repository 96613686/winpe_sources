# DELETE_SURFOBJ(_SURFOBJ * *,HBITMAP__ * *)

- ea: `0x180062e04`
- end: `0x180062e60`
- name: `?DELETE_SURFOBJ@@YAXPEAPEAU_SURFOBJ@@PEAPEAUHBITMAP__@@@Z`
- size: `92`
- prototype: `void __fastcall(struct _SURFOBJ **, HSURF *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180062e70`
- `0x180063700`
- `0x180063e10`
- `0x180065a34`
- `0x180069760`
- `0x180069874`

## callees

- `0x180062e04`

## import_xrefs

- `GDI32!EngUnlockSurface` at `0x180062e21`
- `GDI32!EngUnlockSurface` at `0x180062e21`
- `GDI32!EngDeleteSurface` at `0x180062e41`
- `GDI32!EngDeleteSurface` at `0x180062e41`

## pseudocode

```c
void __fastcall DELETE_SURFOBJ(struct _SURFOBJ **a1, HSURF *a2)
{
  SURFOBJ *v4; // rcx

  if ( a1 )
  {
    v4 = *a1;
    if ( v4 )
    {
      EngUnlockSurface(v4);
      *a1 = 0;
    }
  }
  if ( a2 )
  {
    if ( *a2 )
    {
      EngDeleteSurface(*a2);
      *a2 = 0;
    }
  }
}

```

## disassembly

```asm
0x180062e04  mov     [rsp+arg_0], rbx
0x180062e09  push    rdi
0x180062e0a  sub     rsp, 20h
0x180062e0e  mov     rbx, rdx
0x180062e11  mov     rdi, rcx
0x180062e14  test    rcx, rcx
0x180062e17  jz      short loc_180062E34
0x180062e19  mov     rcx, [rcx]; pso
0x180062e1c  test    rcx, rcx
0x180062e1f  jz      short loc_180062E34
0x180062e21  call    cs:__imp_EngUnlockSurface
0x180062e28  nop     dword ptr [rax+rax+00h]
0x180062e2d  mov     qword ptr [rdi], 0
0x180062e34  test    rbx, rbx
0x180062e37  jz      short loc_180062E54
0x180062e39  mov     rcx, [rbx]; hsurf
0x180062e3c  test    rcx, rcx
0x180062e3f  jz      short loc_180062E54
0x180062e41  call    cs:__imp_EngDeleteSurface
0x180062e48  nop     dword ptr [rax+rax+00h]
0x180062e4d  mov     qword ptr [rbx], 0
0x180062e54  mov     rbx, [rsp+28h+arg_0]
0x180062e59  add     rsp, 20h
0x180062e5d  pop     rdi
0x180062e5e  retn
```
