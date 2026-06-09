# CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)

- ea: `0x18000b4f4`
- end: `0x18000b51b`
- name: `??1?$CVectorDeleteMe@G@@QEAA@XZ`
- size: `39`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012e9c`
- `0x180013ddc`
- `0x180013edc`
- `0x1800142c0`
- `0x1800148e4`
- `0x1800149e8`
- `0x18001d896`
- `0x18001e850`
- `0x18001e9c1`
- `0x18001e9d3`

## callees

- `0x18000b4f4`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000b50f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000b50f`

## pseudocode

```c
int __fastcall CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(void **a1)
{
  void **v1; // rax
  void *v2; // rcx
  void **v3; // rcx

  v1 = a1;
  v2 = *a1;
  if ( v2 )
    goto LABEL_4;
  v3 = (void **)v1[1];
  if ( v3 )
  {
    v2 = *v3;
LABEL_4:
    LODWORD(v1) = CWin32DefaultArena::WbemMemFree(v2);
  }
  return (int)v1;
}

```

## disassembly

```asm
0x18000b4f4  sub     rsp, 28h
0x18000b4f8  mov     rax, rcx
0x18000b4fb  mov     rcx, [rcx]
0x18000b4fe  test    rcx, rcx
0x18000b501  jnz     short loc_18000B50F
0x18000b503  mov     rcx, [rax+8]
0x18000b507  test    rcx, rcx
0x18000b50a  jz      short loc_18000B516
0x18000b50c  mov     rcx, [rcx]
0x18000b50f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000b515  nop
0x18000b516  add     rsp, 28h
0x18000b51a  retn
```
