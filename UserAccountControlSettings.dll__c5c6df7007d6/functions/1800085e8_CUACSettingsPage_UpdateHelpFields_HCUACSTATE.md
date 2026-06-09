# CUACSettingsPage::_UpdateHelpFields(HCUACSTATE)

- ea: `0x1800085e8`
- end: `0x180008815`
- name: `?_UpdateHelpFields@CUACSettingsPage@@AEAAXW4HCUACSTATE@@@Z`
- size: `557`
- prototype: `int __fastcall(__int64, int, __int64, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000751c`
- `0x180007be0`

## callees

- `0x18000855c`
- `0x1800085e8`
- `0x180009800`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000864b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008697`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800086fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000876b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000864b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008697`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800086fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000876b`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800086f2`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800087eb`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800086f2`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800087eb`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800087bc`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800087bc`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800087b3`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800087b3`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180008641`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000868d`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800086dc`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180008761`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180008641`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000868d`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800086dc`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180008761`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000879f`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x180008791`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x180008791`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x1800087fc`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x1800087fc`

## pseudocode

```c
int __fastcall CUACSettingsPage::_UpdateHelpFields(__int64 a1, int a2, __int64 a3, void *a4)
{
  __int64 v4; // rsi
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  _WORD *v9; // rdi
  DirectUI::Element *v10; // rcx
  char v11; // al
  __int64 v12; // r8
  void *v13; // r9
  char v14; // di
  __int64 v15; // rdx
  const unsigned __int16 *v16; // rcx
  HICON SharedIconFromDll; // rax
  struct DirectUI::Value *Graphic; // rax
  DirectUI::Value *v19; // rdi
  __int64 v20; // rcx
  int result; // eax
  int v22; // [rsp+20h] [rbp-10h]
  int v23; // [rsp+50h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp+30h] BYREF

  v4 = a2;
  if ( *(_QWORD *)(a1 + 64) )
  {
    v6 = *(_QWORD *)(a1 + 136);
    hMem = 0;
    if ( (int)TResourceStringAllocCopyEx<unsigned short *>(g_hinst, *(unsigned int *)(v6 + 16 * v4), a3, a4, v22, &hMem) >= 0 )
    {
      DirectUI::Element::SetContentString(*(DirectUI::Element **)(a1 + 64), (const unsigned __int16 *)hMem);
      LocalFree(hMem);
    }
  }
  if ( *(_QWORD *)(a1 + 72) )
  {
    v7 = *(_QWORD *)(a1 + 136);
    hMem = 0;
    if ( (int)TResourceStringAllocCopyEx<unsigned short *>(
                g_hinst,
                *(unsigned int *)(v7 + 16 * v4 + 4),
                a3,
                a4,
                v22,
                &hMem) >= 0 )
    {
      DirectUI::Element::SetContentString(*(DirectUI::Element **)(a1 + 72), (const unsigned __int16 *)hMem);
      LocalFree(hMem);
    }
  }
  if ( *(_QWORD *)(a1 + 80) )
  {
    v8 = *(_QWORD *)(a1 + 136);
    hMem = 0;
    if ( (int)TResourceStringAllocCopyEx<unsigned short *>(
                g_hinst,
                *(unsigned int *)(v8 + 16 * v4 + 8),
                a3,
                a4,
                v22,
                &hMem) >= 0 )
    {
      v9 = hMem;
      DirectUI::Element::SetContentString(*(DirectUI::Element **)(a1 + 80), (const unsigned __int16 *)hMem);
      v10 = *(DirectUI::Element **)(a1 + 88);
      if ( v10 )
        DirectUI::Element::SetVisible(v10, *v9 != 0);
      LocalFree(v9);
    }
  }
  if ( *(_QWORD *)(a1 + 96) )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 32) + 40LL))(
            *(_QWORD *)(a1 + 32),
            (unsigned int)v4);
    hMem = 0;
    v14 = v11;
    if ( v11 )
      v15 = 93;
    else
      v15 = *(unsigned int *)(*(_QWORD *)(a1 + 136) + 16 * v4 + 12);
    if ( (int)TResourceStringAllocCopyEx<unsigned short *>(g_hinst, v15, v12, v13, v22, &hMem) >= 0 )
    {
      DirectUI::Element::SetContentString(*(DirectUI::Element **)(a1 + 96), (const unsigned __int16 *)hMem);
      LocalFree(hMem);
    }
    SharedIconFromDll = (HICON)_LoadSharedIconFromDll(v16, v14 != 0 ? 84 : 81);
    if ( SharedIconFromDll )
    {
      Graphic = DirectUI::Value::CreateGraphic(SharedIconFromDll, 0, 0, 0);
      v19 = Graphic;
      if ( Graphic )
      {
        DirectUI::Element::SetValue(
          *(DirectUI::Element **)(a1 + 104),
          (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
          1,
          Graphic);
        DirectUI::Value::Release(v19);
      }
    }
  }
  v20 = *(_QWORD *)(a1 + 32);
  v23 = 0;
  result = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v20 + 32LL))(v20, (unsigned int)v4, &v23);
  if ( result >= 0 )
  {
    DirectUI::Element::SetVisible(*(DirectUI::Element **)(a1 + 112), v23 == 0);
    return DirectUI::Element::SetEnabled(*(DirectUI::Element **)(a1 + 120), v23 != 0);
  }
  return result;
}

```

## disassembly

```asm
0x1800085e8  mov     [rsp-18h+arg_8], rbx
0x1800085ed  mov     [rsp-18h+arg_18], rsi
0x1800085f2  push    rbp
0x1800085f3  push    rdi
0x1800085f4  push    r14
0x1800085f6  mov     rbp, rsp
0x1800085f9  sub     rsp, 30h
0x1800085fd  xor     r14d, r14d
0x180008600  movsxd  rsi, edx
0x180008603  mov     rbx, rcx
0x180008606  cmp     [rcx+40h], r14
0x18000860a  jz      short loc_180008651
0x18000860c  mov     rdx, [rcx+88h]
0x180008613  mov     rax, rsi
0x180008616  add     rax, rax
0x180008619  mov     [rbp+hMem], r14
0x18000861d  lea     rcx, [rbp+hMem]
0x180008621  mov     [rsp+30h+Src], rcx; Src
0x180008626  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; int
0x18000862d  mov     edx, [rdx+rax*8]; int
0x180008630  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180008635  test    eax, eax
0x180008637  js      short loc_180008651
0x180008639  mov     rdx, [rbp+hMem]
0x18000863d  mov     rcx, [rbx+40h]
0x180008641  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180008647  mov     rcx, [rbp+hMem]; hMem
0x18000864b  call    cs:__imp_LocalFree
0x180008651  cmp     [rbx+48h], r14
0x180008655  jz      short loc_18000869D
0x180008657  mov     rdx, [rbx+88h]
0x18000865e  lea     rcx, [rbp+hMem]
0x180008662  mov     [rsp+30h+Src], rcx; Src
0x180008667  mov     rax, rsi
0x18000866a  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; int
0x180008671  add     rax, rax
0x180008674  mov     [rbp+hMem], r14
0x180008678  mov     edx, [rdx+rax*8+4]; int
0x18000867c  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180008681  test    eax, eax
0x180008683  js      short loc_18000869D
0x180008685  mov     rdx, [rbp+hMem]
0x180008689  mov     rcx, [rbx+48h]
0x18000868d  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180008693  mov     rcx, [rbp+hMem]; hMem
0x180008697  call    cs:__imp_LocalFree
0x18000869d  cmp     [rbx+50h], r14
0x1800086a1  jz      short loc_180008701
0x1800086a3  mov     rdx, [rbx+88h]
0x1800086aa  lea     rcx, [rbp+hMem]
0x1800086ae  mov     [rsp+30h+Src], rcx; Src
0x1800086b3  mov     rax, rsi
0x1800086b6  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; int
0x1800086bd  add     rax, rax
0x1800086c0  mov     [rbp+hMem], r14
0x1800086c4  mov     edx, [rdx+rax*8+8]; int
0x1800086c8  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1800086cd  test    eax, eax
0x1800086cf  js      short loc_180008701
0x1800086d1  mov     rdi, [rbp+hMem]
0x1800086d5  mov     rcx, [rbx+50h]
0x1800086d9  mov     rdx, rdi
0x1800086dc  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1800086e2  mov     rcx, [rbx+58h]
0x1800086e6  test    rcx, rcx
0x1800086e9  jz      short loc_1800086F8
0x1800086eb  cmp     [rdi], r14w
0x1800086ef  setnz   dl
0x1800086f2  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1800086f8  mov     rcx, rdi; hMem
0x1800086fb  call    cs:__imp_LocalFree
0x180008701  cmp     [rbx+60h], r14
0x180008705  jz      loc_1800087C2
0x18000870b  mov     rcx, [rbx+20h]
0x18000870f  mov     edx, esi
0x180008711  mov     rax, [rcx]
0x180008714  mov     rax, [rax+28h]
0x180008718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000871d  mov     [rbp+hMem], r14
0x180008721  mov     dil, al
0x180008724  test    al, al
0x180008726  jz      short loc_18000872F
0x180008728  mov     edx, 5Dh ; ']'
0x18000872d  jmp     short loc_180008740
0x18000872f  mov     rax, [rbx+88h]
0x180008736  mov     rcx, rsi
0x180008739  add     rcx, rcx
0x18000873c  mov     edx, [rax+rcx*8+0Ch]; int
0x180008740  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; int
0x180008747  lea     rax, [rbp+hMem]
0x18000874b  mov     [rsp+30h+Src], rax; Src
0x180008750  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180008755  test    eax, eax
0x180008757  js      short loc_180008771
0x180008759  mov     rdx, [rbp+hMem]
0x18000875d  mov     rcx, [rbx+60h]
0x180008761  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180008767  mov     rcx, [rbp+hMem]; hMem
0x18000876b  call    cs:__imp_LocalFree
0x180008771  neg     dil
0x180008774  sbb     edx, edx
0x180008776  and     edx, 3
0x180008779  add     edx, 51h ; 'Q'; int
0x18000877c  call    ?_LoadSharedIconFromDll@@YAPEAUHICON__@@PEBGH@Z; _LoadSharedIconFromDll(ushort const *,int)
0x180008781  test    rax, rax
0x180008784  jz      short loc_1800087C2
0x180008786  xor     r9d, r9d
0x180008789  xor     r8d, r8d
0x18000878c  xor     edx, edx
0x18000878e  mov     rcx, rax
0x180008791  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z; DirectUI::Value::CreateGraphic(HICON__ *,bool,bool,bool)
0x180008797  mov     rdi, rax
0x18000879a  test    rax, rax
0x18000879d  jz      short loc_1800087C2
0x18000879f  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800087a6  mov     r9, rax
0x1800087a9  mov     rcx, [rbx+68h]
0x1800087ad  mov     r8d, 1
0x1800087b3  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1800087b9  mov     rcx, rdi
0x1800087bc  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800087c2  mov     rcx, [rbx+20h]
0x1800087c6  lea     r8, [rbp+arg_0]
0x1800087ca  mov     [rbp+arg_0], r14d
0x1800087ce  mov     edx, esi
0x1800087d0  mov     rax, [rcx]
0x1800087d3  mov     rax, [rax+20h]
0x1800087d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087dc  test    eax, eax
0x1800087de  js      short loc_180008802
0x1800087e0  cmp     [rbp+arg_0], r14d
0x1800087e4  mov     rcx, [rbx+70h]
0x1800087e8  setz    dl
0x1800087eb  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1800087f1  cmp     [rbp+arg_0], r14d
0x1800087f5  mov     rcx, [rbx+78h]
0x1800087f9  setnz   dl
0x1800087fc  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180008802  mov     rbx, [rsp+30h+arg_8]
0x180008807  mov     rsi, [rsp+30h+arg_18]
0x18000880c  add     rsp, 30h
0x180008810  pop     r14
0x180008812  pop     rdi
0x180008813  pop     rbp
0x180008814  retn
```
