# _MdlHxmodReset(XMOD *)

- ea: `0x180020180`
- end: `0x180020576`
- name: `?_MdlHxmodReset@@YAXPEAUXMOD@@@Z`
- size: `1014`
- prototype: `void __fastcall(struct XMOD *)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18001fa78`
- `0x18002057c`

## callees

- `0x18001eae8`
- `0x18001eeb8`
- `0x18001eef0`
- `0x18001f6b8`
- `0x180020180`
- `0x180025548`
- `0x1800332fc`
- `0x1800334b4`
- `0x1800ce7ec`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!free` at `0x1800201f2`
- `MSVCR100!free` at `0x180020201`
- `MSVCR100!free` at `0x180020210`
- `MSVCR100!free` at `0x18002022a`
- `MSVCR100!free` at `0x18002023c`
- `MSVCR100!free` at `0x18002024b`
- `MSVCR100!free` at `0x18002027b`
- `MSVCR100!free` at `0x1800202a3`
- `MSVCR100!free` at `0x1800202bf`
- `MSVCR100!free` at `0x1800202dc`
- `MSVCR100!free` at `0x180020327`
- `MSVCR100!free` at `0x180020334`
- `MSVCR100!free` at `0x180020341`
- `MSVCR100!free` at `0x18002034e`
- `MSVCR100!free` at `0x180020396`
- `MSVCR100!free` at `0x1800203bd`
- `MSVCR100!free` at `0x1800203cc`
- `MSVCR100!free` at `0x180020412`
- `MSVCR100!free` at `0x180020421`
- `MSVCR100!free` at `0x180020430`
- `MSVCR100!free` at `0x180020442`
- `MSVCR100!free` at `0x180020454`
- `MSVCR100!free` at `0x180020466`
- `MSVCR100!free` at `0x180020478`
- `MSVCR100!free` at `0x1800201f2`
- `MSVCR100!free` at `0x180020201`
- `MSVCR100!free` at `0x180020210`
- `MSVCR100!free` at `0x18002022a`
- `MSVCR100!free` at `0x18002023c`
- `MSVCR100!free` at `0x18002024b`
- `MSVCR100!free` at `0x18002027b`
- `MSVCR100!free` at `0x1800202a3`
- `MSVCR100!free` at `0x1800202bf`
- `MSVCR100!free` at `0x1800202dc`
- `MSVCR100!free` at `0x180020327`
- `MSVCR100!free` at `0x180020334`
- `MSVCR100!free` at `0x180020341`
- `MSVCR100!free` at `0x18002034e`
- `MSVCR100!free` at `0x180020396`
- `MSVCR100!free` at `0x1800203bd`
- `MSVCR100!free` at `0x1800203cc`
- `MSVCR100!free` at `0x180020412`
- `MSVCR100!free` at `0x180020421`
- `MSVCR100!free` at `0x180020430`
- `MSVCR100!free` at `0x180020442`
- `MSVCR100!free` at `0x180020454`
- `MSVCR100!free` at `0x180020466`
- `MSVCR100!free` at `0x180020478`
- `USER32!DestroyIcon` at `0x1800203a3`
- `USER32!DestroyIcon` at `0x1800203a3`
- `GDI32!DeleteObject` at `0x1800202f4`
- `GDI32!DeleteObject` at `0x18002030c`
- `GDI32!DeleteObject` at `0x180020369`
- `GDI32!DeleteObject` at `0x18002037b`
- `GDI32!DeleteObject` at `0x1800202f4`
- `GDI32!DeleteObject` at `0x18002030c`
- `GDI32!DeleteObject` at `0x180020369`
- `GDI32!DeleteObject` at `0x18002037b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800204e4`
- `OLEAUT32!__imp_SysFreeString` at `0x180020500`
- `OLEAUT32!__imp_SysFreeString` at `0x1800204e4`
- `OLEAUT32!__imp_SysFreeString` at `0x180020500`

## pseudocode

```c
void __fastcall _MdlHxmodReset(struct XMOD *a1)
{
  __int64 v2; // rax
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // rsi
  void *v11; // rcx
  void *v12; // rcx
  int v13; // esi
  __int64 v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // rcx
  HICON v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  char v20; // cl
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  void *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  OLECHAR *v35; // rcx
  OLECHAR *v36; // rcx
  struct IClassFactory *v37; // rax
  struct IClassFactory *v38; // rdi
  char v39[48]; // [rsp+20h] [rbp-48h] BYREF

  if ( (*((_BYTE *)a1 + 116) & 1) != 0 )
  {
    v2 = *(_QWORD *)a1;
    if ( *(_BYTE *)(*(_QWORD *)a1 + 95LL) != 32 || (--dword_1803F7E74, !dword_1803F7E74) || *(_BYTE *)(v2 + 95) != 32 )
    {
      MdlCreateWndClassName(a1, v39, 42, 0);
      IsolationAwareUnregisterClassA(v39, Rby_hinstExe);
    }
  }
  v3 = (void *)*((_QWORD *)a1 + 8);
  if ( v3 )
    free(v3);
  v4 = (void *)*((_QWORD *)a1 + 4);
  if ( v4 )
    free(v4);
  v5 = (void *)*((_QWORD *)a1 + 5);
  if ( v5 )
    free(v5);
  if ( (*((_WORD *)a1 + 56) & 0x200) != 0 )
  {
    v6 = (void *)*((_QWORD *)a1 + 7);
    if ( v6 )
      free(v6);
  }
  v7 = (void *)*((_QWORD *)a1 + 64);
  if ( v7 )
    free(v7);
  v8 = (void *)*((_QWORD *)a1 + 13);
  if ( v8 )
    free(v8);
  if ( *((_QWORD *)a1 + 25) && *((_WORD *)a1 + 99) )
  {
    v9 = 0;
    v10 = *((unsigned __int16 *)a1 + 99);
    do
    {
      v11 = *(void **)(v9 + *((_QWORD *)a1 + 25) + 16);
      if ( v11 )
      {
        free(v11);
        *(_QWORD *)(v9 + *((_QWORD *)a1 + 25) + 16) = 0;
      }
      v9 += 32;
      --v10;
    }
    while ( v10 );
  }
  v12 = (void *)*((_QWORD *)a1 + 25);
  if ( v12 )
    free(v12);
  if ( (*((_WORD *)a1 + 58) & 0x4000) != 0 )
  {
    free(*((void **)a1 + 52));
    v13 = 0;
    if ( *((int *)a1 + 106) > 0 )
    {
      v14 = 0;
      do
      {
        free(*(void **)(v14 + *((_QWORD *)a1 + 54)));
        v15 = *((_QWORD *)a1 + 50);
        if ( *(_QWORD *)(v14 + v15) )
          DeleteObject(*(HGDIOBJ *)(v14 + v15));
        v16 = *((_QWORD *)a1 + 51);
        if ( *(_QWORD *)(v14 + v16) )
          DeleteObject(*(HGDIOBJ *)(v14 + v16));
        ++v13;
        v14 += 8;
      }
      while ( v13 < *((_DWORD *)a1 + 106) );
    }
    free(*((void **)a1 + 50));
    free(*((void **)a1 + 51));
    free(*((void **)a1 + 54));
    free(*((void **)a1 + 55));
    v17 = (HICON)*((_QWORD *)a1 + 56);
LABEL_41:
    if ( v17 )
      free(v17);
    goto LABEL_45;
  }
  v18 = (void *)*((_QWORD *)a1 + 50);
  if ( v18 )
    DeleteObject(v18);
  v19 = (void *)*((_QWORD *)a1 + 51);
  if ( v19 )
    DeleteObject(v19);
  v17 = (HICON)*((_QWORD *)a1 + 52);
  if ( *((_DWORD *)a1 + 98) )
    goto LABEL_41;
  if ( v17 )
    DestroyIcon(v17);
LABEL_45:
  v20 = *(_BYTE *)(*(_QWORD *)a1 + 95LL);
  if ( v20 == 19 )
  {
    v21 = (void *)*((_QWORD *)a1 + 9);
    if ( v21 )
      free(v21);
    v22 = (void *)*((_QWORD *)a1 + 12);
    if ( v22 )
      free(v22);
    RevokePrivateTInfo(*((struct ITypeInfo **)a1 + 18));
    RevokePrivateTInfo(*((struct ITypeInfo **)a1 + 19));
    RevokePrivateTInfo(*((struct ITypeInfo **)a1 + 22));
    RevokePrivateTInfo(*((struct ITypeInfo **)a1 + 20));
  }
  else if ( v20 == 32 )
  {
    v23 = (void *)*((_QWORD *)a1 + 9);
    if ( v23 )
      free(v23);
    v24 = (void *)*((_QWORD *)a1 + 12);
    if ( v24 )
      free(v24);
  }
  v25 = (void *)*((_QWORD *)a1 + 10);
  if ( v25 )
    free(v25);
  v26 = (void *)*((_QWORD *)a1 + 17);
  if ( v26 )
    free(v26);
  v27 = (void *)*((_QWORD *)a1 + 32);
  if ( v27 )
    free(v27);
  v28 = (void *)*((_QWORD *)a1 + 33);
  if ( v28 )
    free(v28);
  v29 = (void *)*((_QWORD *)a1 + 34);
  if ( v29 )
    free(v29);
  v30 = *((_QWORD *)a1 + 22);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  v31 = *((_QWORD *)a1 + 20);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  v32 = *((_QWORD *)a1 + 21);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  v33 = *((_QWORD *)a1 + 18);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  v34 = *((_QWORD *)a1 + 19);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  v35 = (OLECHAR *)*((_QWORD *)a1 + 23);
  if ( v35 )
    SysFreeString(v35);
  ReleaseTypeInfosThatUseXmod(a1);
  v36 = (OLECHAR *)*((_QWORD *)a1 + 37);
  *((_DWORD *)a1 + 130) = 0;
  SysFreeString(v36);
  *((_QWORD *)a1 + 37) = 0;
  v37 = LpcfOfHxmod(a1);
  v38 = v37;
  if ( v37 && (unsigned int)IsValidOleInterface(v37) )
  {
    ((void (__fastcall *)(struct IClassFactory *, _QWORD))v38->lpVtbl->LockServer)(v38, 0);
    ((void (__fastcall *)(struct IClassFactory *))v38->lpVtbl->Release)(v38);
    SetHxmodLpcf(a1, 0);
  }
  if ( *((char *)a1 + 114) >= 0 )
    ToolNeedsUpdate(0);
}

```

## disassembly

```asm
0x180020180  mov     [rsp+arg_8], rbx
0x180020185  mov     [rsp+arg_10], rsi
0x18002018a  push    rdi
0x18002018b  mov     eax, 60h
0x180020190  call    _alloca_probe
0x180020195  sub     rsp, rax
0x180020198  mov     rax, cs:__security_cookie
0x18002019f  xor     rax, rsp
0x1800201a2  mov     [rsp+68h+var_18], rax
0x1800201a7  test    byte ptr [rcx+74h], 1
0x1800201ab  mov     rbx, rcx
0x1800201ae  jz      short loc_1800201E9
0x1800201b0  mov     rax, [rcx]
0x1800201b3  cmp     byte ptr [rax+5Fh], 20h ; ' '
0x1800201b7  jnz     short loc_1800201C7
0x1800201b9  dec     cs:dword_1803F7E74
0x1800201bf  jz      short loc_1800201C7
0x1800201c1  cmp     byte ptr [rax+5Fh], 20h ; ' '
0x1800201c5  jz      short loc_1800201E9
0x1800201c7  xor     r9d, r9d; int
0x1800201ca  lea     rdx, [rsp+68h+var_48]; char *
0x1800201cf  lea     r8d, [r9+2Ah]; int
0x1800201d3  call    ?MdlCreateWndClassName@@YAXPEAUXMOD@@PEADHH@Z; MdlCreateWndClassName(XMOD *,char *,int,int)
0x1800201d8  mov     rdx, cs:?Rby_hinstExe@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * Rby_hinstExe
0x1800201df  lea     rcx, [rsp+68h+var_48]
0x1800201e4  call    IsolationAwareUnregisterClassA
0x1800201e9  mov     rcx, [rbx+40h]; Block
0x1800201ed  test    rcx, rcx
0x1800201f0  jz      short loc_1800201F8
0x1800201f2  call    cs:__imp_free
0x1800201f8  mov     rcx, [rbx+20h]; Block
0x1800201fc  test    rcx, rcx
0x1800201ff  jz      short loc_180020207
0x180020201  call    cs:__imp_free
0x180020207  mov     rcx, [rbx+28h]; Block
0x18002020b  test    rcx, rcx
0x18002020e  jz      short loc_180020216
0x180020210  call    cs:__imp_free
0x180020216  mov     eax, 200h
0x18002021b  test    [rbx+70h], ax
0x18002021f  jz      short loc_180020230
0x180020221  mov     rcx, [rbx+38h]; Block
0x180020225  test    rcx, rcx
0x180020228  jz      short loc_180020230
0x18002022a  call    cs:__imp_free
0x180020230  mov     rcx, [rbx+200h]; Block
0x180020237  test    rcx, rcx
0x18002023a  jz      short loc_180020242
0x18002023c  call    cs:__imp_free
0x180020242  mov     rcx, [rbx+68h]; Block
0x180020246  test    rcx, rcx
0x180020249  jz      short loc_180020251
0x18002024b  call    cs:__imp_free
0x180020251  cmp     qword ptr [rbx+0C8h], 0
0x180020259  jz      short loc_180020297
0x18002025b  movzx   eax, word ptr [rbx+0C6h]
0x180020262  test    eax, eax
0x180020264  jz      short loc_180020297
0x180020266  xor     edi, edi
0x180020268  mov     esi, eax
0x18002026a  mov     rax, [rbx+0C8h]
0x180020271  mov     rcx, [rdi+rax+10h]; Block
0x180020276  test    rcx, rcx
0x180020279  jz      short loc_18002028E
0x18002027b  call    cs:__imp_free
0x180020281  mov     r11, [rbx+0C8h]
0x180020288  and     qword ptr [rdi+r11+10h], 0
0x18002028e  add     rdi, 20h ; ' '
0x180020292  dec     rsi
0x180020295  jnz     short loc_18002026A
0x180020297  mov     rcx, [rbx+0C8h]; Block
0x18002029e  test    rcx, rcx
0x1800202a1  jz      short loc_1800202A9
0x1800202a3  call    cs:__imp_free
0x1800202a9  mov     eax, 4000h
0x1800202ae  test    [rbx+74h], ax
0x1800202b2  jz      loc_18002035D
0x1800202b8  mov     rcx, [rbx+1A0h]; Block
0x1800202bf  call    cs:__imp_free
0x1800202c5  xor     esi, esi
0x1800202c7  cmp     [rbx+1A8h], esi
0x1800202cd  jle     short loc_180020320
0x1800202cf  xor     edi, edi
0x1800202d1  mov     rcx, [rbx+1B0h]
0x1800202d8  mov     rcx, [rdi+rcx]; Block
0x1800202dc  call    cs:__imp_free
0x1800202e2  mov     rcx, [rbx+190h]
0x1800202e9  cmp     qword ptr [rdi+rcx], 0
0x1800202ee  jz      short loc_1800202FA
0x1800202f0  mov     rcx, [rdi+rcx]; ho
0x1800202f4  call    cs:__imp_DeleteObject
0x1800202fa  mov     rcx, [rbx+198h]
0x180020301  cmp     qword ptr [rdi+rcx], 0
0x180020306  jz      short loc_180020312
0x180020308  mov     rcx, [rdi+rcx]; ho
0x18002030c  call    cs:__imp_DeleteObject
0x180020312  inc     esi
0x180020314  add     rdi, 8
0x180020318  cmp     esi, [rbx+1A8h]
0x18002031e  jl      short loc_1800202D1
0x180020320  mov     rcx, [rbx+190h]; Block
0x180020327  call    cs:__imp_free
0x18002032d  mov     rcx, [rbx+198h]; Block
0x180020334  call    cs:__imp_free
0x18002033a  mov     rcx, [rbx+1B0h]; Block
0x180020341  call    cs:__imp_free
0x180020347  mov     rcx, [rbx+1B8h]; Block
0x18002034e  call    cs:__imp_free
0x180020354  mov     rcx, [rbx+1C0h]
0x18002035b  jmp     short loc_180020391
0x18002035d  mov     rcx, [rbx+190h]; ho
0x180020364  test    rcx, rcx
0x180020367  jz      short loc_18002036F
0x180020369  call    cs:__imp_DeleteObject
0x18002036f  mov     rcx, [rbx+198h]; ho
0x180020376  test    rcx, rcx
0x180020379  jz      short loc_180020381
0x18002037b  call    cs:__imp_DeleteObject
0x180020381  cmp     dword ptr [rbx+188h], 0
0x180020388  mov     rcx, [rbx+1A0h]; hIcon
0x18002038f  jz      short loc_18002039E
0x180020391  test    rcx, rcx
0x180020394  jz      short loc_1800203A9
0x180020396  call    cs:__imp_free
0x18002039c  jmp     short loc_1800203A9
0x18002039e  test    rcx, rcx
0x1800203a1  jz      short loc_1800203A9
0x1800203a3  call    cs:__imp_DestroyIcon
0x1800203a9  mov     rax, [rbx]
0x1800203ac  mov     cl, [rax+5Fh]
0x1800203af  cmp     cl, 13h
0x1800203b2  jnz     short loc_180020404
0x1800203b4  mov     rcx, [rbx+48h]; Block
0x1800203b8  test    rcx, rcx
0x1800203bb  jz      short loc_1800203C3
0x1800203bd  call    cs:__imp_free
0x1800203c3  mov     rcx, [rbx+60h]; Block
0x1800203c7  test    rcx, rcx
0x1800203ca  jz      short loc_1800203D2
0x1800203cc  call    cs:__imp_free
0x1800203d2  mov     rcx, [rbx+90h]; struct ITypeInfo *
0x1800203d9  call    ?RevokePrivateTInfo@@YAXPEAUITypeInfo@@@Z; RevokePrivateTInfo(ITypeInfo *)
0x1800203de  mov     rcx, [rbx+98h]; struct ITypeInfo *
0x1800203e5  call    ?RevokePrivateTInfo@@YAXPEAUITypeInfo@@@Z; RevokePrivateTInfo(ITypeInfo *)
0x1800203ea  mov     rcx, [rbx+0B0h]; struct ITypeInfo *
0x1800203f1  call    ?RevokePrivateTInfo@@YAXPEAUITypeInfo@@@Z; RevokePrivateTInfo(ITypeInfo *)
0x1800203f6  mov     rcx, [rbx+0A0h]; struct ITypeInfo *
0x1800203fd  call    ?RevokePrivateTInfo@@YAXPEAUITypeInfo@@@Z; RevokePrivateTInfo(ITypeInfo *)
0x180020402  jmp     short loc_180020427
0x180020404  cmp     cl, 20h ; ' '
0x180020407  jnz     short loc_180020427
0x180020409  mov     rcx, [rbx+48h]; Block
0x18002040d  test    rcx, rcx
0x180020410  jz      short loc_180020418
0x180020412  call    cs:__imp_free
0x180020418  mov     rcx, [rbx+60h]; Block
0x18002041c  test    rcx, rcx
0x18002041f  jz      short loc_180020427
0x180020421  call    cs:__imp_free
0x180020427  mov     rcx, [rbx+50h]; Block
0x18002042b  test    rcx, rcx
0x18002042e  jz      short loc_180020436
0x180020430  call    cs:__imp_free
0x180020436  mov     rcx, [rbx+88h]; Block
0x18002043d  test    rcx, rcx
0x180020440  jz      short loc_180020448
0x180020442  call    cs:__imp_free
0x180020448  mov     rcx, [rbx+100h]; Block
0x18002044f  test    rcx, rcx
0x180020452  jz      short loc_18002045A
0x180020454  call    cs:__imp_free
0x18002045a  mov     rcx, [rbx+108h]; Block
0x180020461  test    rcx, rcx
0x180020464  jz      short loc_18002046C
0x180020466  call    cs:__imp_free
0x18002046c  mov     rcx, [rbx+110h]; Block
0x180020473  test    rcx, rcx
0x180020476  jz      short loc_18002047E
0x180020478  call    cs:__imp_free
0x18002047e  mov     rcx, [rbx+0B0h]
0x180020485  test    rcx, rcx
0x180020488  jz      short loc_180020490
0x18002048a  mov     rax, [rcx]
0x18002048d  call    qword ptr [rax+10h]
0x180020490  mov     rcx, [rbx+0A0h]
0x180020497  test    rcx, rcx
0x18002049a  jz      short loc_1800204A2
0x18002049c  mov     rax, [rcx]
0x18002049f  call    qword ptr [rax+10h]
0x1800204a2  mov     rcx, [rbx+0A8h]
0x1800204a9  test    rcx, rcx
0x1800204ac  jz      short loc_1800204B4
0x1800204ae  mov     rax, [rcx]
0x1800204b1  call    qword ptr [rax+10h]
0x1800204b4  mov     rcx, [rbx+90h]
0x1800204bb  test    rcx, rcx
0x1800204be  jz      short loc_1800204C6
0x1800204c0  mov     rax, [rcx]
0x1800204c3  call    qword ptr [rax+10h]
0x1800204c6  mov     rcx, [rbx+98h]
0x1800204cd  test    rcx, rcx
0x1800204d0  jz      short loc_1800204D8
0x1800204d2  mov     rax, [rcx]
0x1800204d5  call    qword ptr [rax+10h]
0x1800204d8  mov     rcx, [rbx+0B8h]; bstrString
0x1800204df  test    rcx, rcx
0x1800204e2  jz      short loc_1800204EA
0x1800204e4  call    cs:__imp_SysFreeString
0x1800204ea  mov     rcx, rbx; struct XMOD *
0x1800204ed  call    ?ReleaseTypeInfosThatUseXmod@@YAXPEAUXMOD@@@Z; ReleaseTypeInfosThatUseXmod(XMOD *)
0x1800204f2  mov     rcx, [rbx+128h]; bstrString
0x1800204f9  and     dword ptr [rbx+208h], 0
0x180020500  call    cs:__imp_SysFreeString
0x180020506  and     qword ptr [rbx+128h], 0
0x18002050e  mov     rcx, rbx; struct XMOD *
0x180020511  call    ?LpcfOfHxmod@@YAPEAUIClassFactory@@PEAUXMOD@@@Z; LpcfOfHxmod(XMOD *)
0x180020516  mov     rdi, rax
0x180020519  test    rax, rax
0x18002051c  jz      short loc_18002054A
0x18002051e  mov     rcx, rax; void *
0x180020521  call    ?IsValidOleInterface@@YAHPEAX@Z; IsValidOleInterface(void *)
0x180020526  test    eax, eax
0x180020528  jz      short loc_18002054A
0x18002052a  mov     r8, [rdi]
0x18002052d  xor     edx, edx
0x18002052f  mov     rcx, rdi
0x180020532  call    qword ptr [r8+20h]
0x180020536  mov     r11, [rdi]
0x180020539  mov     rcx, rdi
0x18002053c  call    qword ptr [r11+10h]
0x180020540  xor     edx, edx; struct IClassFactory *
0x180020542  mov     rcx, rbx; struct XMOD *
0x180020545  call    ?SetHxmodLpcf@@YAHPEAUXMOD@@PEAUIClassFactory@@@Z; SetHxmodLpcf(XMOD *,IClassFactory *)
0x18002054a  test    byte ptr [rbx+72h], 80h
0x18002054e  jnz     short loc_180020557
0x180020550  xor     ecx, ecx; int
0x180020552  call    ?ToolNeedsUpdate@@YAXH@Z; ToolNeedsUpdate(int)
0x180020557  mov     rcx, [rsp+68h+var_18]
0x18002055c  xor     rcx, rsp; StackCookie
0x18002055f  call    __security_check_cookie
0x180020564  lea     r11, [rsp+68h+var_8]
0x180020569  mov     rbx, [r11+18h]
0x18002056d  mov     rsi, [r11+20h]
0x180020571  mov     rsp, r11
0x180020574  pop     rdi
0x180020575  retn
```
