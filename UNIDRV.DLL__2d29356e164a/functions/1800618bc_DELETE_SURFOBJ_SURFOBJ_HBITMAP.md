# DELETE_SURFOBJ(_SURFOBJ * *,HBITMAP__ * *)

- ea: `0x1800618bc`
- end: `0x18006190b`
- name: `?DELETE_SURFOBJ@@YAXPEAPEAU_SURFOBJ@@PEAPEAUHBITMAP__@@@Z`
- size: `79`
- prototype: `void __fastcall(struct _SURFOBJ **, HBITMAP *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180061920`
- `0x180062160`
- `0x180062830`
- `0x180064378`
- `0x180067f0c`
- `0x180068020`

## callees

- `0x1800618bc`

## import_xrefs

- `GDI32!EngUnlockSurface` at `0x1800618d9`
- `GDI32!EngUnlockSurface` at `0x1800618d9`
- `GDI32!EngDeleteSurface` at `0x1800618f3`
- `GDI32!EngDeleteSurface` at `0x1800618f3`

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
0x1800618bc  mov     [rsp+arg_0], rbx
0x1800618c1  push    rdi
0x1800618c2  sub     rsp, 20h
0x1800618c6  mov     rbx, rdx
0x1800618c9  mov     rdi, rcx
0x1800618cc  test    rcx, rcx
0x1800618cf  jz      short loc_1800618E6
0x1800618d1  mov     rcx, [rcx]; pso
0x1800618d4  test    rcx, rcx
0x1800618d7  jz      short loc_1800618E6
0x1800618d9  call    cs:__imp_EngUnlockSurface
0x1800618df  mov     qword ptr [rdi], 0
0x1800618e6  test    rbx, rbx
0x1800618e9  jz      short loc_180061900
0x1800618eb  mov     rcx, [rbx]; hsurf
0x1800618ee  test    rcx, rcx
0x1800618f1  jz      short loc_180061900
0x1800618f3  call    cs:__imp_EngDeleteSurface
0x1800618f9  mov     qword ptr [rbx], 0
0x180061900  mov     rbx, [rsp+28h+arg_0]
0x180061905  add     rsp, 20h
0x180061909  pop     rdi
0x18006190a  retn
```
