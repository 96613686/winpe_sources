# _DestroySkinnyHxmod(XMOD *)

- ea: `0x180082514`
- end: `0x1800825c4`
- name: `?_DestroySkinnyHxmod@@YAXPEAUXMOD@@@Z`
- size: `176`
- prototype: `void __fastcall(struct XMOD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180081b04`
- `0x180081fe8`
- `0x180082214`
- `0x180082668`

## callees

- `0x180082514`
- `0x180379380`

## import_xrefs

- `MSVCR100!free` at `0x180082536`
- `MSVCR100!free` at `0x180082545`
- `MSVCR100!free` at `0x180082554`
- `MSVCR100!free` at `0x180082563`
- `MSVCR100!free` at `0x18008257e`
- `MSVCR100!free` at `0x1800825b8`
- `MSVCR100!free` at `0x180082536`
- `MSVCR100!free` at `0x180082545`
- `MSVCR100!free` at `0x180082554`
- `MSVCR100!free` at `0x180082563`
- `MSVCR100!free` at `0x18008257e`
- `MSVCR100!free` at `0x1800825b8`
- `USER32!DestroyIcon` at `0x18008258b`
- `USER32!DestroyIcon` at `0x18008258b`
- `GDI32!DeleteObject` at `0x18008259d`
- `GDI32!DeleteObject` at `0x1800825af`
- `GDI32!DeleteObject` at `0x18008259d`
- `GDI32!DeleteObject` at `0x1800825af`

## pseudocode

```c
void __fastcall _DestroySkinnyHxmod(struct XMOD *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  HICON v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  if ( a1 )
  {
    v2 = *(void **)a1;
    if ( v2 )
      free(v2);
    v3 = (void *)*((_QWORD *)a1 + 12);
    if ( v3 )
      free(v3);
    v4 = (void *)*((_QWORD *)a1 + 9);
    if ( v4 )
      free(v4);
    v5 = (void *)*((_QWORD *)a1 + 13);
    if ( v5 )
      free(v5);
    v6 = (HICON)*((_QWORD *)a1 + 52);
    if ( *((_DWORD *)a1 + 98) )
    {
      if ( v6 )
        free(v6);
    }
    else if ( v6 )
    {
      DestroyIcon(v6);
    }
    v7 = (void *)*((_QWORD *)a1 + 51);
    if ( v7 )
      DeleteObject(v7);
    v8 = (void *)*((_QWORD *)a1 + 50);
    if ( v8 )
      DeleteObject(v8);
    free(a1);
  }
}

```

## disassembly

```asm
0x180082514  test    rcx, rcx
0x180082517  jz      locret_1800825C3
0x18008251d  push    rbx
0x18008251e  mov     eax, 20h
0x180082523  call    _alloca_probe
0x180082528  sub     rsp, rax
0x18008252b  mov     rbx, rcx
0x18008252e  mov     rcx, [rcx]; Block
0x180082531  test    rcx, rcx
0x180082534  jz      short loc_18008253C
0x180082536  call    cs:__imp_free
0x18008253c  mov     rcx, [rbx+60h]; Block
0x180082540  test    rcx, rcx
0x180082543  jz      short loc_18008254B
0x180082545  call    cs:__imp_free
0x18008254b  mov     rcx, [rbx+48h]; Block
0x18008254f  test    rcx, rcx
0x180082552  jz      short loc_18008255A
0x180082554  call    cs:__imp_free
0x18008255a  mov     rcx, [rbx+68h]; Block
0x18008255e  test    rcx, rcx
0x180082561  jz      short loc_180082569
0x180082563  call    cs:__imp_free
0x180082569  cmp     dword ptr [rbx+188h], 0
0x180082570  mov     rcx, [rbx+1A0h]; hIcon
0x180082577  jz      short loc_180082586
0x180082579  test    rcx, rcx
0x18008257c  jz      short loc_180082591
0x18008257e  call    cs:__imp_free
0x180082584  jmp     short loc_180082591
0x180082586  test    rcx, rcx
0x180082589  jz      short loc_180082591
0x18008258b  call    cs:__imp_DestroyIcon
0x180082591  mov     rcx, [rbx+198h]; ho
0x180082598  test    rcx, rcx
0x18008259b  jz      short loc_1800825A3
0x18008259d  call    cs:__imp_DeleteObject
0x1800825a3  mov     rcx, [rbx+190h]; ho
0x1800825aa  test    rcx, rcx
0x1800825ad  jz      short loc_1800825B5
0x1800825af  call    cs:__imp_DeleteObject
0x1800825b5  mov     rcx, rbx; Block
0x1800825b8  call    cs:__imp_free
0x1800825be  add     rsp, 20h
0x1800825c2  pop     rbx
0x1800825c3  retn
```
