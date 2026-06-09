# APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)

- ea: `0x18002b564`
- end: `0x18002b667`
- name: `?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z`
- size: `259`
- prototype: `__int64 __fastcall(APP_OBJECT_UTILS *__hidden this, struct IExtensionContext *, struct ICommandParameterList *, const unsigned __int16 *, struct STRU *, int, int)`
- caller_count: `28`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180010cc0`
- `0x180011690`
- `0x180014010`
- `0x180014690`
- `0x180015138`
- `0x180015ab0`
- `0x180016200`
- `0x180017560`
- `0x180017f90`
- `0x180019f48`
- `0x18001d714`
- `0x18001d8c0`
- `0x18001e590`
- `0x18001f120`
- `0x1800200b0`
- `0x180020674`
- `0x180021658`
- `0x180022a9c`
- `0x180023740`
- `0x180024090`
- `0x180025748`
- `0x180026aec`
- `0x180027190`
- `0x180027cc0`
- `0x180028f50`
- `0x18002b0cc`
- `0x18002b304`
- `0x18002b3f0`

## callees

- `0x180002e90`
- `0x18002b564`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall APP_OBJECT_UTILS::PopParameter(
        APP_OBJECT_UTILS *this,
        struct IExtensionContext *a2,
        struct ICommandParameterList *a3,
        const unsigned __int16 *a4,
        struct STRU *a5,
        int a6,
        int a7)
{
  int v10; // eax
  signed int v11; // ebx
  __int64 v12; // rax
  unsigned __int16 *v14; // [rsp+50h] [rbp+8h] BYREF
  const unsigned __int16 *v15; // [rsp+60h] [rbp+18h] BYREF

  v14 = 0;
  v15 = 0;
  if ( a3 && a4 && a5 && a2 )
  {
    v10 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)a3 + 40LL))(
            a3,
            a4,
            &v14);
    v11 = v10;
    if ( a6 && v10 == -2147023483 )
    {
      v12 = *(_QWORD *)a2;
      v11 = -2147024809;
      v15 = a4;
      (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, const unsigned __int16 **, _DWORD))(v12 + 144))(
        a2,
        2147942487LL,
        3221226486LL,
        &v15,
        0);
    }
    else if ( v10 >= 0 )
    {
      v11 = STRU::Copy(a5, (const unsigned __int8 *)v14);
      if ( v11 >= 0 )
      {
        v14 = 0;
        if ( a7 )
          return (unsigned int)(*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *))(*(_QWORD *)a3 + 48LL))(
                                 a3,
                                 a4);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002b564  mov     r11, rsp
0x18002b567  mov     [r11+10h], rbx
0x18002b56b  mov     [r11+8], rcx
0x18002b56f  push    rsi
0x18002b570  push    rdi
0x18002b571  push    r14
0x18002b573  sub     rsp, 30h
0x18002b577  mov     qword ptr [r11+8], 0
0x18002b57f  mov     rsi, r9
0x18002b582  mov     qword ptr [r11+18h], 0
0x18002b58a  mov     rdi, r8
0x18002b58d  mov     r14, rdx
0x18002b590  test    r8, r8
0x18002b593  jz      loc_18002B652
0x18002b599  test    r9, r9
0x18002b59c  jz      loc_18002B652
0x18002b5a2  cmp     [rsp+48h+arg_20], 0
0x18002b5a8  jz      loc_18002B652
0x18002b5ae  test    rdx, rdx
0x18002b5b1  jz      loc_18002B652
0x18002b5b7  mov     rax, [r8]
0x18002b5ba  mov     rdx, r9
0x18002b5bd  lea     r8, [r11+8]
0x18002b5c1  mov     rcx, rdi
0x18002b5c4  mov     rax, [rax+28h]
0x18002b5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5cd  cmp     [rsp+48h+arg_28], 0
0x18002b5d2  mov     ebx, eax
0x18002b5d4  jz      short loc_18002B610
0x18002b5d6  cmp     eax, 80070585h
0x18002b5db  jnz     short loc_18002B610
0x18002b5dd  mov     rax, [r14]
0x18002b5e0  lea     r9, [rsp+48h+arg_10]
0x18002b5e5  mov     ebx, 80070057h
0x18002b5ea  mov     [rsp+48h+arg_10], rsi
0x18002b5ef  mov     r8d, 0C00003F6h
0x18002b5f5  mov     [rsp+48h+var_28], 0
0x18002b5fd  mov     edx, ebx
0x18002b5ff  mov     rcx, r14
0x18002b602  mov     rax, [rax+90h]
0x18002b609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b60e  jmp     short loc_18002B657
0x18002b610  test    eax, eax
0x18002b612  js      short loc_18002B657
0x18002b614  mov     rdx, [rsp+48h+arg_0]; unsigned __int16 *
0x18002b619  mov     rcx, [rsp+48h+arg_20]; this
0x18002b61e  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002b623  mov     ebx, eax
0x18002b625  test    eax, eax
0x18002b627  js      short loc_18002B657
0x18002b629  cmp     [rsp+48h+arg_30], 0
0x18002b631  mov     [rsp+48h+arg_0], 0
0x18002b63a  jz      short loc_18002B657
0x18002b63c  mov     rax, [rdi]
0x18002b63f  mov     rdx, rsi
0x18002b642  mov     rcx, rdi
0x18002b645  mov     rax, [rax+30h]
0x18002b649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b64e  mov     ebx, eax
0x18002b650  jmp     short loc_18002B657
0x18002b652  mov     ebx, 80070057h
0x18002b657  mov     eax, ebx
0x18002b659  mov     rbx, [rsp+48h+arg_8]
0x18002b65e  add     rsp, 30h
0x18002b662  pop     r14
0x18002b664  pop     rdi
0x18002b665  pop     rsi
0x18002b666  retn
```
