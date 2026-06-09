# VFreePDEVData

- ea: `0x1800264a4`
- end: `0x180026816`
- name: `VFreePDEVData`
- size: `882`
- prototype: `void __fastcall(_DWORD *hMem)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001d4e0`
- `0x180025dc0`

## callees

- `0x1800264a4`
- `0x18002681c`
- `0x180026904`
- `0x180026a74`
- `0x180077010`

## import_xrefs

- `KERNEL32!HeapDestroy` at `0x180026694`
- `KERNEL32!HeapDestroy` at `0x180026694`
- `KERNEL32!LocalFree` at `0x1800264e0`
- `KERNEL32!LocalFree` at `0x18002666b`
- `KERNEL32!LocalFree` at `0x180026683`
- `KERNEL32!LocalFree` at `0x1800266b6`
- `KERNEL32!LocalFree` at `0x1800266d2`
- `KERNEL32!LocalFree` at `0x1800266f4`
- `KERNEL32!LocalFree` at `0x18002677d`
- `KERNEL32!LocalFree` at `0x18002678e`
- `KERNEL32!LocalFree` at `0x18002679f`
- `KERNEL32!LocalFree` at `0x1800267b0`
- `KERNEL32!LocalFree` at `0x1800267c1`
- `KERNEL32!LocalFree` at `0x1800267d2`
- `KERNEL32!LocalFree` at `0x1800267e3`
- `KERNEL32!LocalFree` at `0x1800267f4`
- `KERNEL32!LocalFree` at `0x180026805`
- `KERNEL32!LocalFree` at `0x1800264e0`
- `KERNEL32!LocalFree` at `0x18002666b`
- `KERNEL32!LocalFree` at `0x180026683`
- `KERNEL32!LocalFree` at `0x1800266b6`
- `KERNEL32!LocalFree` at `0x1800266d2`
- `KERNEL32!LocalFree` at `0x1800266f4`
- `KERNEL32!LocalFree` at `0x18002677d`
- `KERNEL32!LocalFree` at `0x18002678e`
- `KERNEL32!LocalFree` at `0x18002679f`
- `KERNEL32!LocalFree` at `0x1800267b0`
- `KERNEL32!LocalFree` at `0x1800267c1`
- `KERNEL32!LocalFree` at `0x1800267d2`
- `KERNEL32!LocalFree` at `0x1800267e3`
- `KERNEL32!LocalFree` at `0x1800267f4`
- `KERNEL32!LocalFree` at `0x180026805`
- `ole32!CoUninitialize` at `0x1800266e3`
- `ole32!CoUninitialize` at `0x1800266e3`
- `GDI32!EngDeletePalette` at `0x180026591`
- `GDI32!EngDeletePalette` at `0x180026591`
- `GDI32!EngFreeModule` at `0x180026705`
- `GDI32!EngFreeModule` at `0x180026705`

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
    VUnloadOemPlugins(hMem);
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
    VWinResClose((HMODULE *)hMem + 16);
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
0x1800264a4  test    rcx, rcx
0x1800264a7  jz      locret_180026681
0x1800264ad  mov     [rsp+arg_0], rbx
0x1800264b2  push    rdi
0x1800264b3  sub     rsp, 20h
0x1800264b7  mov     rdi, rcx
0x1800264ba  call    VUnloadOemPlugins
0x1800264bf  test    dword ptr [rdi+74h], 8000000h
0x1800264c6  jnz     loc_1800266E3
0x1800264cc  mov     rcx, rdi
0x1800264cf  call    VUnloadFreeBinaryData
0x1800264d4  mov     rcx, [rdi+6F0h]; hMem
0x1800264db  test    rcx, rcx
0x1800264de  jz      short loc_1800264F7
0x1800264e0  call    cs:__imp_LocalFree
0x1800264e7  nop     dword ptr [rax+rax+00h]
0x1800264ec  mov     qword ptr [rdi+6F0h], 0
0x1800264f7  mov     rcx, [rdi+1010h]; hMem
0x1800264fe  test    rcx, rcx
0x180026501  jnz     loc_1800266B6
0x180026507  mov     rcx, [rdi+748h]; hHeap
0x18002650e  test    rcx, rcx
0x180026511  jnz     loc_180026694
0x180026517  mov     rcx, [rdi+0A20h]; hMem
0x18002651e  test    rcx, rcx
0x180026521  jnz     loc_1800266F4
0x180026527  mov     rcx, [rdi+50h]; h
0x18002652b  test    rcx, rcx
0x18002652e  jnz     loc_180026705
0x180026534  mov     rax, [rdi+1048h]
0x18002653b  test    rax, rax
0x18002653e  jz      short loc_18002654C
0x180026540  mov     rax, [rax+48h]
0x180026544  mov     rcx, rdi
0x180026547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002654c  mov     rax, [rdi+1030h]
0x180026553  test    rax, rax
0x180026556  jnz     loc_1800266A5
0x18002655c  mov     rdx, [rdi+1058h]
0x180026563  test    rdx, rdx
0x180026566  jnz     loc_180026716
0x18002656c  mov     rcx, [rdi+1058h]
0x180026573  test    rcx, rcx
0x180026576  jnz     loc_18002674B
0x18002657c  mov     rax, [rdi+1000h]
0x180026583  test    rax, rax
0x180026586  jz      short loc_1800265CC
0x180026588  mov     rcx, [rax+18h]; hpal
0x18002658c  test    rcx, rcx
0x18002658f  jz      short loc_18002659D
0x180026591  call    cs:__imp_EngDeletePalette
0x180026598  nop     dword ptr [rax+rax+00h]
0x18002659d  mov     rax, [rdi+1000h]
0x1800265a4  mov     rcx, [rax+10h]; hMem
0x1800265a8  test    rcx, rcx
0x1800265ab  jnz     loc_18002677D
0x1800265b1  mov     rcx, [rdi+1000h]; hMem
0x1800265b8  test    rcx, rcx
0x1800265bb  jnz     loc_18002678E
0x1800265c1  mov     qword ptr [rdi+1000h], 0
0x1800265cc  lea     rcx, [rdi+80h]; void *
0x1800265d3  call    VWinResClose
0x1800265d8  mov     rcx, [rdi+0F88h]; hMem
0x1800265df  test    rcx, rcx
0x1800265e2  jnz     loc_18002679F
0x1800265e8  mov     rcx, [rdi+6B8h]; hMem
0x1800265ef  test    rcx, rcx
0x1800265f2  jnz     loc_180026683
0x1800265f8  mov     rcx, [rdi+6C0h]; hMem
0x1800265ff  test    rcx, rcx
0x180026602  jnz     loc_1800266D2
0x180026608  mov     rcx, [rdi+6D0h]; hMem
0x18002660f  test    rcx, rcx
0x180026612  jnz     loc_1800267B0
0x180026618  mov     rcx, [rdi+6D8h]; hMem
0x18002661f  test    rcx, rcx
0x180026622  jnz     loc_1800267C1
0x180026628  mov     rcx, [rdi+10B0h]; hMem
0x18002662f  test    rcx, rcx
0x180026632  jnz     loc_1800267D2
0x180026638  mov     rcx, [rdi+6E0h]; hMem
0x18002663f  test    rcx, rcx
0x180026642  jnz     loc_1800267E3
0x180026648  mov     rcx, [rdi+798h]; hMem
0x18002664f  test    rcx, rcx
0x180026652  jnz     loc_1800267F4
0x180026658  mov     rcx, [rdi+10F0h]; hMem
0x18002665f  test    rcx, rcx
0x180026662  jnz     loc_180026805
0x180026668  mov     rcx, rdi; hMem
0x18002666b  call    cs:__imp_LocalFree
0x180026672  nop     dword ptr [rax+rax+00h]
0x180026677  mov     rbx, [rsp+28h+arg_0]
0x18002667c  add     rsp, 20h
0x180026680  pop     rdi
0x180026681  retn
0x180026683  call    cs:__imp_LocalFree
0x18002668a  nop     dword ptr [rax+rax+00h]
0x18002668f  jmp     loc_1800265F8
0x180026694  call    cs:__imp_HeapDestroy
0x18002669b  nop     dword ptr [rax+rax+00h]
0x1800266a0  jmp     loc_180026517
0x1800266a5  mov     rax, [rax+48h]
0x1800266a9  mov     rcx, rdi
0x1800266ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266b1  jmp     loc_18002655C
0x1800266b6  call    cs:__imp_LocalFree
0x1800266bd  nop     dword ptr [rax+rax+00h]
0x1800266c2  mov     qword ptr [rdi+1010h], 0
0x1800266cd  jmp     loc_180026507
0x1800266d2  call    cs:__imp_LocalFree
0x1800266d9  nop     dword ptr [rax+rax+00h]
0x1800266de  jmp     loc_180026608
0x1800266e3  call    cs:__imp_CoUninitialize
0x1800266ea  nop     dword ptr [rax+rax+00h]
0x1800266ef  jmp     loc_1800264CC
0x1800266f4  call    cs:__imp_LocalFree
0x1800266fb  nop     dword ptr [rax+rax+00h]
0x180026700  jmp     loc_180026527
0x180026705  call    cs:__imp_EngFreeModule
0x18002670c  nop     dword ptr [rax+rax+00h]
0x180026711  jmp     loc_180026534
0x180026716  cmp     qword ptr [rdx+88h], 0
0x18002671e  jz      loc_18002656C
0x180026724  mov     rax, [rdi+1050h]
0x18002672b  mov     rcx, rdi
0x18002672e  mov     rbx, [rdi+8]
0x180026732  mov     [rdi+8], rax
0x180026736  mov     rax, [rdx+88h]
0x18002673d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026742  mov     [rdi+8], rbx
0x180026746  jmp     loc_18002656C
0x18002674b  cmp     qword ptr [rcx+0A0h], 0
0x180026753  jz      loc_18002657C
0x180026759  mov     rax, [rdi+1050h]
0x180026760  mov     rbx, [rdi+8]
0x180026764  mov     [rdi+8], rax
0x180026768  mov     rax, [rcx+0A0h]
0x18002676f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026774  mov     [rdi+8], rbx
0x180026778  jmp     loc_18002657C
0x18002677d  call    cs:__imp_LocalFree
0x180026784  nop     dword ptr [rax+rax+00h]
0x180026789  jmp     loc_1800265B1
0x18002678e  call    cs:__imp_LocalFree
0x180026795  nop     dword ptr [rax+rax+00h]
0x18002679a  jmp     loc_1800265C1
0x18002679f  call    cs:__imp_LocalFree
0x1800267a6  nop     dword ptr [rax+rax+00h]
0x1800267ab  jmp     loc_1800265E8
0x1800267b0  call    cs:__imp_LocalFree
0x1800267b7  nop     dword ptr [rax+rax+00h]
0x1800267bc  jmp     loc_180026618
0x1800267c1  call    cs:__imp_LocalFree
0x1800267c8  nop     dword ptr [rax+rax+00h]
0x1800267cd  jmp     loc_180026628
0x1800267d2  call    cs:__imp_LocalFree
0x1800267d9  nop     dword ptr [rax+rax+00h]
0x1800267de  jmp     loc_180026638
0x1800267e3  call    cs:__imp_LocalFree
0x1800267ea  nop     dword ptr [rax+rax+00h]
0x1800267ef  jmp     loc_180026648
0x1800267f4  call    cs:__imp_LocalFree
0x1800267fb  nop     dword ptr [rax+rax+00h]
0x180026800  jmp     loc_180026658
0x180026805  call    cs:__imp_LocalFree
0x18002680c  nop     dword ptr [rax+rax+00h]
0x180026811  jmp     loc_180026668
```
