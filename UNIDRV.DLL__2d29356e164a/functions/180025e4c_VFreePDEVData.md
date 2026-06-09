# VFreePDEVData

- ea: `0x180025e4c`
- end: `0x18002614b`
- name: `VFreePDEVData`
- size: `767`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001d140`
- `0x180025780`

## callees

- `0x180025e4c`
- `0x180026154`
- `0x180026234`
- `0x18002639c`
- `0x180075010`

## import_xrefs

- `KERNEL32!HeapDestroy` at `0x180026023`
- `KERNEL32!HeapDestroy` at `0x180026023`
- `KERNEL32!LocalFree` at `0x180025e88`
- `KERNEL32!LocalFree` at `0x180026007`
- `KERNEL32!LocalFree` at `0x180026018`
- `KERNEL32!LocalFree` at `0x18002603f`
- `KERNEL32!LocalFree` at `0x180026055`
- `KERNEL32!LocalFree` at `0x18002606b`
- `KERNEL32!LocalFree` at `0x1800260e8`
- `KERNEL32!LocalFree` at `0x1800260f3`
- `KERNEL32!LocalFree` at `0x1800260fe`
- `KERNEL32!LocalFree` at `0x180026109`
- `KERNEL32!LocalFree` at `0x180026114`
- `KERNEL32!LocalFree` at `0x18002611f`
- `KERNEL32!LocalFree` at `0x18002612a`
- `KERNEL32!LocalFree` at `0x180026135`
- `KERNEL32!LocalFree` at `0x180026140`
- `KERNEL32!LocalFree` at `0x180025e88`
- `KERNEL32!LocalFree` at `0x180026007`
- `KERNEL32!LocalFree` at `0x180026018`
- `KERNEL32!LocalFree` at `0x18002603f`
- `KERNEL32!LocalFree` at `0x180026055`
- `KERNEL32!LocalFree` at `0x18002606b`
- `KERNEL32!LocalFree` at `0x1800260e8`
- `KERNEL32!LocalFree` at `0x1800260f3`
- `KERNEL32!LocalFree` at `0x1800260fe`
- `KERNEL32!LocalFree` at `0x180026109`
- `KERNEL32!LocalFree` at `0x180026114`
- `KERNEL32!LocalFree` at `0x18002611f`
- `KERNEL32!LocalFree` at `0x18002612a`
- `KERNEL32!LocalFree` at `0x180026135`
- `KERNEL32!LocalFree` at `0x180026140`
- `ole32!CoUninitialize` at `0x180026060`
- `ole32!CoUninitialize` at `0x180026060`
- `GDI32!EngDeletePalette` at `0x180025f33`
- `GDI32!EngDeletePalette` at `0x180025f33`
- `GDI32!EngFreeModule` at `0x180026076`
- `GDI32!EngFreeModule` at `0x180026076`

## pseudocode

```c
void __fastcall VFreePDEVData(_DWORD *hMem)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  HPALETTE v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  __int64 v24; // rbx
  __int64 v25; // rbx

  if ( hMem )
  {
    VUnloadOemPlugins();
    if ( (hMem[29] & 0x8000000) != 0 )
      CoUninitialize();
    VUnloadFreeBinaryData(hMem);
    v2 = (void *)*((_QWORD *)hMem + 222);
    if ( v2 )
    {
      LocalFree(v2);
      *((_QWORD *)hMem + 222) = 0;
    }
    v3 = (void *)*((_QWORD *)hMem + 514);
    if ( v3 )
    {
      LocalFree(v3);
      *((_QWORD *)hMem + 514) = 0;
    }
    v4 = (void *)*((_QWORD *)hMem + 233);
    if ( v4 )
      HeapDestroy(v4);
    v5 = (void *)*((_QWORD *)hMem + 324);
    if ( v5 )
      LocalFree(v5);
    v6 = (void *)*((_QWORD *)hMem + 10);
    if ( v6 )
      EngFreeModule(v6);
    v7 = *((_QWORD *)hMem + 521);
    if ( v7 )
      (*(void (__fastcall **)(_DWORD *))(v7 + 72))(hMem);
    v8 = *((_QWORD *)hMem + 518);
    if ( v8 )
      (*(void (__fastcall **)(_DWORD *))(v8 + 72))(hMem);
    v9 = *((_QWORD *)hMem + 523);
    if ( v9 && *(_QWORD *)(v9 + 136) )
    {
      v24 = *((_QWORD *)hMem + 1);
      *((_QWORD *)hMem + 1) = *((_QWORD *)hMem + 522);
      (*(void (__fastcall **)(_DWORD *))(v9 + 136))(hMem);
      *((_QWORD *)hMem + 1) = v24;
    }
    v10 = *((_QWORD *)hMem + 523);
    if ( v10 && *(_QWORD *)(v10 + 160) )
    {
      v25 = *((_QWORD *)hMem + 1);
      *((_QWORD *)hMem + 1) = *((_QWORD *)hMem + 522);
      (*(void (**)(void))(v10 + 160))();
      *((_QWORD *)hMem + 1) = v25;
    }
    v11 = *((_QWORD *)hMem + 512);
    if ( v11 )
    {
      v12 = *(HPALETTE *)(v11 + 24);
      if ( v12 )
        EngDeletePalette(v12);
      v13 = *(void **)(*((_QWORD *)hMem + 512) + 16LL);
      if ( v13 )
        LocalFree(v13);
      v14 = (void *)*((_QWORD *)hMem + 512);
      if ( v14 )
        LocalFree(v14);
      *((_QWORD *)hMem + 512) = 0;
    }
    VWinResClose(hMem + 32);
    v15 = (void *)*((_QWORD *)hMem + 497);
    if ( v15 )
      LocalFree(v15);
    v16 = (void *)*((_QWORD *)hMem + 215);
    if ( v16 )
      LocalFree(v16);
    v17 = (void *)*((_QWORD *)hMem + 216);
    if ( v17 )
      LocalFree(v17);
    v18 = (void *)*((_QWORD *)hMem + 218);
    if ( v18 )
      LocalFree(v18);
    v19 = (void *)*((_QWORD *)hMem + 219);
    if ( v19 )
      LocalFree(v19);
    v20 = (void *)*((_QWORD *)hMem + 534);
    if ( v20 )
      LocalFree(v20);
    v21 = (void *)*((_QWORD *)hMem + 220);
    if ( v21 )
      LocalFree(v21);
    v22 = (void *)*((_QWORD *)hMem + 243);
    if ( v22 )
      LocalFree(v22);
    v23 = (void *)*((_QWORD *)hMem + 542);
    if ( v23 )
      LocalFree(v23);
    LocalFree(hMem);
  }
}

```

## disassembly

```asm
0x180025e4c  test    rcx, rcx
0x180025e4f  jz      locret_180026017
0x180025e55  mov     [rsp+arg_0], rbx
0x180025e5a  push    rdi
0x180025e5b  sub     rsp, 20h
0x180025e5f  mov     rdi, rcx
0x180025e62  call    VUnloadOemPlugins
0x180025e67  test    dword ptr [rdi+74h], 8000000h
0x180025e6e  jnz     loc_180026060
0x180025e74  mov     rcx, rdi
0x180025e77  call    VUnloadFreeBinaryData
0x180025e7c  mov     rcx, [rdi+6F0h]; hMem
0x180025e83  test    rcx, rcx
0x180025e86  jz      short loc_180025E99
0x180025e88  call    cs:__imp_LocalFree
0x180025e8e  mov     qword ptr [rdi+6F0h], 0
0x180025e99  mov     rcx, [rdi+1010h]; hMem
0x180025ea0  test    rcx, rcx
0x180025ea3  jnz     loc_18002603F
0x180025ea9  mov     rcx, [rdi+748h]; hHeap
0x180025eb0  test    rcx, rcx
0x180025eb3  jnz     loc_180026023
0x180025eb9  mov     rcx, [rdi+0A20h]; hMem
0x180025ec0  test    rcx, rcx
0x180025ec3  jnz     loc_18002606B
0x180025ec9  mov     rcx, [rdi+50h]; h
0x180025ecd  test    rcx, rcx
0x180025ed0  jnz     loc_180026076
0x180025ed6  mov     rax, [rdi+1048h]
0x180025edd  test    rax, rax
0x180025ee0  jz      short loc_180025EEE
0x180025ee2  mov     rax, [rax+48h]
0x180025ee6  mov     rcx, rdi
0x180025ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025eee  mov     rax, [rdi+1030h]
0x180025ef5  test    rax, rax
0x180025ef8  jnz     loc_18002602E
0x180025efe  mov     rdx, [rdi+1058h]
0x180025f05  test    rdx, rdx
0x180025f08  jnz     loc_180026081
0x180025f0e  mov     rcx, [rdi+1058h]
0x180025f15  test    rcx, rcx
0x180025f18  jnz     loc_1800260B6
0x180025f1e  mov     rax, [rdi+1000h]
0x180025f25  test    rax, rax
0x180025f28  jz      short loc_180025F68
0x180025f2a  mov     rcx, [rax+18h]; hpal
0x180025f2e  test    rcx, rcx
0x180025f31  jz      short loc_180025F39
0x180025f33  call    cs:__imp_EngDeletePalette
0x180025f39  mov     rax, [rdi+1000h]
0x180025f40  mov     rcx, [rax+10h]; hMem
0x180025f44  test    rcx, rcx
0x180025f47  jnz     loc_1800260E8
0x180025f4d  mov     rcx, [rdi+1000h]; hMem
0x180025f54  test    rcx, rcx
0x180025f57  jnz     loc_1800260F3
0x180025f5d  mov     qword ptr [rdi+1000h], 0
0x180025f68  lea     rcx, [rdi+80h]; void *
0x180025f6f  call    VWinResClose
0x180025f74  mov     rcx, [rdi+0F88h]; hMem
0x180025f7b  test    rcx, rcx
0x180025f7e  jnz     loc_1800260FE
0x180025f84  mov     rcx, [rdi+6B8h]; hMem
0x180025f8b  test    rcx, rcx
0x180025f8e  jnz     loc_180026018
0x180025f94  mov     rcx, [rdi+6C0h]; hMem
0x180025f9b  test    rcx, rcx
0x180025f9e  jnz     loc_180026055
0x180025fa4  mov     rcx, [rdi+6D0h]; hMem
0x180025fab  test    rcx, rcx
0x180025fae  jnz     loc_180026109
0x180025fb4  mov     rcx, [rdi+6D8h]; hMem
0x180025fbb  test    rcx, rcx
0x180025fbe  jnz     loc_180026114
0x180025fc4  mov     rcx, [rdi+10B0h]; hMem
0x180025fcb  test    rcx, rcx
0x180025fce  jnz     loc_18002611F
0x180025fd4  mov     rcx, [rdi+6E0h]; hMem
0x180025fdb  test    rcx, rcx
0x180025fde  jnz     loc_18002612A
0x180025fe4  mov     rcx, [rdi+798h]; hMem
0x180025feb  test    rcx, rcx
0x180025fee  jnz     loc_180026135
0x180025ff4  mov     rcx, [rdi+10F0h]; hMem
0x180025ffb  test    rcx, rcx
0x180025ffe  jnz     loc_180026140
0x180026004  mov     rcx, rdi; hMem
0x180026007  call    cs:__imp_LocalFree
0x18002600d  mov     rbx, [rsp+28h+arg_0]
0x180026012  add     rsp, 20h
0x180026016  pop     rdi
0x180026017  retn
0x180026018  call    cs:__imp_LocalFree
0x18002601e  jmp     loc_180025F94
0x180026023  call    cs:__imp_HeapDestroy
0x180026029  jmp     loc_180025EB9
0x18002602e  mov     rax, [rax+48h]
0x180026032  mov     rcx, rdi
0x180026035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002603a  jmp     loc_180025EFE
0x18002603f  call    cs:__imp_LocalFree
0x180026045  mov     qword ptr [rdi+1010h], 0
0x180026050  jmp     loc_180025EA9
0x180026055  call    cs:__imp_LocalFree
0x18002605b  jmp     loc_180025FA4
0x180026060  call    cs:__imp_CoUninitialize
0x180026066  jmp     loc_180025E74
0x18002606b  call    cs:__imp_LocalFree
0x180026071  jmp     loc_180025EC9
0x180026076  call    cs:__imp_EngFreeModule
0x18002607c  jmp     loc_180025ED6
0x180026081  cmp     qword ptr [rdx+88h], 0
0x180026089  jz      loc_180025F0E
0x18002608f  mov     rax, [rdi+1050h]
0x180026096  mov     rcx, rdi
0x180026099  mov     rbx, [rdi+8]
0x18002609d  mov     [rdi+8], rax
0x1800260a1  mov     rax, [rdx+88h]
0x1800260a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260ad  mov     [rdi+8], rbx
0x1800260b1  jmp     loc_180025F0E
0x1800260b6  cmp     qword ptr [rcx+0A0h], 0
0x1800260be  jz      loc_180025F1E
0x1800260c4  mov     rax, [rdi+1050h]
0x1800260cb  mov     rbx, [rdi+8]
0x1800260cf  mov     [rdi+8], rax
0x1800260d3  mov     rax, [rcx+0A0h]
0x1800260da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260df  mov     [rdi+8], rbx
0x1800260e3  jmp     loc_180025F1E
0x1800260e8  call    cs:__imp_LocalFree
0x1800260ee  jmp     loc_180025F4D
0x1800260f3  call    cs:__imp_LocalFree
0x1800260f9  jmp     loc_180025F5D
0x1800260fe  call    cs:__imp_LocalFree
0x180026104  jmp     loc_180025F84
0x180026109  call    cs:__imp_LocalFree
0x18002610f  jmp     loc_180025FB4
0x180026114  call    cs:__imp_LocalFree
0x18002611a  jmp     loc_180025FC4
0x18002611f  call    cs:__imp_LocalFree
0x180026125  jmp     loc_180025FD4
0x18002612a  call    cs:__imp_LocalFree
0x180026130  jmp     loc_180025FE4
0x180026135  call    cs:__imp_LocalFree
0x18002613b  jmp     loc_180025FF4
0x180026140  call    cs:__imp_LocalFree
0x180026146  jmp     loc_180026004
```
