# InstallPublishedApp(void *)

- ea: `0x1800433f0`
- end: `0x1800436cf`
- name: `?InstallPublishedApp@@YAKPEAX@Z`
- size: `735`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000b2dc`
- `0x180013490`
- `0x18001732c`
- `0x18001b5b8`
- `0x18001dfd8`
- `0x180042140`
- `0x1800433f0`
- `0x180043ddc`
- `0x1800582a2`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x180043666`
- `SHELL32!SHChangeNotify` at `0x180043666`
- `SHELL32!__imp_ILFree` at `0x180043670`
- `SHELL32!__imp_ILFree` at `0x180043670`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004356b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004356b`
- `USER32!LoadCursorW` at `0x180043426`
- `USER32!LoadCursorW` at `0x180043426`
- `USER32!SetCursor` at `0x18004342f`
- `USER32!SetCursor` at `0x180043681`
- `USER32!SetCursor` at `0x18004342f`
- `USER32!SetCursor` at `0x180043681`

## pseudocode

```c
__int64 __fastcall InstallPublishedApp(unsigned int *Parameter)
{
  HCURSOR CursorW; // rax
  HCURSOR v3; // r15
  GUID v4; // xmm0
  __int64 v5; // rcx
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rdx
  CDarwinPublishedApp *v8; // rax
  CDarwinPublishedApp *v9; // rax
  CDarwinPublishedApp *v10; // rdi
  int (__fastcall **v11)(CDarwinPublishedApp *, GUID *, __int64 *); // rcx
  int v12; // ebx
  __int64 v13; // rax
  ULONGLONG Ptr; // rcx
  int v15; // eax
  unsigned int v16; // edi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rax
  const struct _ITEMIDLIST_RELATIVE *v18; // rdx
  const struct _ITEMIDLIST_ABSOLUTE *v19; // rcx
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  unsigned __int16 **ppv; // [rsp+20h] [rbp-99h]
  unsigned __int64 *v25; // [rsp+28h] [rbp-91h]
  unsigned int v26; // [rsp+30h] [rbp-89h]
  __int64 v27; // [rsp+40h] [rbp-79h] BYREF
  __int64 v28; // [rsp+48h] [rbp-71h] BYREF
  _MANAGEDAPPLICATION v29; // [rsp+50h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR dwItem1; // [rsp+D0h] [rbp+17h] BYREF

  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v3 = SetCursor(CursorW);
  if ( !*((_WORD *)Parameter + 16) )
  {
    dwItem1.Ptr = 0;
    if ( CoCreateInstance(
           &GUID_352ec2b7_8b9a_11d1_b8ae_006008059382,
           0,
           1u,
           &GUID_c257690d_85de_417c_b964_c22b1a6bb5f7,
           (LPVOID *)&dwItem1) < 0 )
      goto LABEL_29;
    v27 = 0;
    v15 = (*(__int64 (__fastcall **)(ULONGLONG, _QWORD, __int64 *))(*(_QWORD *)dwItem1.Ptr + 48LL))(
            dwItem1.Ptr,
            0,
            &v27);
    v12 = v15;
    if ( v15 >= 0 )
    {
      v28 = 0;
      v16 = 0;
      if ( !v15 )
      {
        while ( 1 )
        {
          v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 24LL);
          if ( v16 >= Parameter[139] )
            break;
          v12 = v17(v27, &v28);
          if ( v12 >= 0 && v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          ++v16;
          if ( v12 )
            goto LABEL_24;
        }
        v12 = v17(v27, &v28);
        if ( v12 >= 0 && v28 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 64LL))(v28, 0);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        }
      }
LABEL_24:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    Ptr = dwItem1.Ptr;
    v13 = *(_QWORD *)dwItem1.Ptr;
LABEL_26:
    (*(void (__fastcall **)(ULONGLONG))(v13 + 16))(Ptr);
    if ( v12 < 0 )
      goto LABEL_29;
    goto LABEL_27;
  }
  memset_0(&v29, 0, sizeof(v29));
  v4 = (GUID)*((_OWORD *)Parameter + 1);
  v5 = Parameter[138];
  v6 = -1;
  v29.dwPathType = Parameter[138];
  v29.GpoId = v4;
  do
    ++v6;
  while ( *((_WORD *)Parameter + v6 + 16) );
  v29.pszPackageName = 0;
  if ( v6 + 1 >= v6 && (int)_AllocArray<unsigned short,CTLocalAllocPolicy>(v5, 0, v6 + 1, &v29) >= 0 )
  {
    StringCchCopyNExW(v29.pszPackageName, v6 + 1, (const unsigned __int16 *)Parameter + 16, v6, ppv, v25, v26);
    v8 = (CDarwinPublishedApp *)DirectUI::HAllocAndZero((DirectUI *)0x90, v7);
    if ( v8 )
    {
      v9 = CDarwinPublishedApp::CDarwinPublishedApp(v8, &v29);
      v10 = v9;
      if ( v9 )
      {
        v11 = *(int (__fastcall ***)(CDarwinPublishedApp *, GUID *, __int64 *))v9;
        v27 = 0;
        if ( (*v11)(v9, &GUID_12b81347_1b3a_4a04_aa61_3f768b67fd7e, &v27) < 0 )
        {
          v12 = (*(__int64 (__fastcall **)(CDarwinPublishedApp *, _QWORD))(*(_QWORD *)v10 + 64LL))(v10, 0);
        }
        else
        {
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v27 + 88LL))(
                  v27,
                  0,
                  *((_QWORD *)Parameter + 70));
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        v13 = *(_QWORD *)v10;
        Ptr = (ULONGLONG)v10;
        goto LABEL_26;
      }
    }
  }
LABEL_27:
  v18 = (const struct _ITEMIDLIST_RELATIVE *)*((_QWORD *)Parameter + 1);
  v19 = *(const struct _ITEMIDLIST_ABSOLUTE **)Parameter;
  dwItem1.Ptr = 0;
  if ( (int)SHILCombine(v19, v18, (struct _ITEMIDLIST_ABSOLUTE **)&dwItem1) >= 0 )
  {
    SHChangeNotify(0x2000, 0x3000u, (LPCVOID)dwItem1.Ptr, 0);
    ILFree((LPITEMIDLIST)dwItem1.Ptr);
  }
LABEL_29:
  FreePublishedAppDataParam(Parameter);
  SetCursor(v3);
  if ( (Microsoft_Windows_Shell_AppWizCplEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      v20,
      (int)&AppWizCpl_SoftwareExplorer_InstallApplicationLaunch_Stop,
      v21,
      v22,
      &dwItem1);
  return 0;
}

```

## disassembly

```asm
0x1800433f0  mov     [rsp-8+arg_8], rbx
0x1800433f5  mov     [rsp-8+arg_10], rsi
0x1800433fa  push    rbp
0x1800433fb  push    rdi
0x1800433fc  push    r12
0x1800433fe  push    r14
0x180043400  push    r15
0x180043402  lea     rbp, [rsp-37h]
0x180043407  sub     rsp, 0F0h
0x18004340e  mov     rax, cs:__security_cookie
0x180043415  xor     rax, rsp
0x180043418  mov     [rbp+57h+var_30], rax
0x18004341c  mov     rsi, rcx
0x18004341f  mov     edx, 7F02h; lpCursorName
0x180043424  xor     ecx, ecx; hInstance
0x180043426  call    cs:__imp_LoadCursorW
0x18004342c  mov     rcx, rax; hCursor
0x18004342f  call    cs:__imp_SetCursor
0x180043435  xor     r12d, r12d
0x180043438  mov     r15, rax
0x18004343b  cmp     [rsi+20h], r12w
0x180043440  jz      loc_18004354A
0x180043446  xor     edx, edx; Val
0x180043448  lea     rcx, [rbp+57h+var_C0]; void *
0x18004344c  mov     r8d, 80h; Size
0x180043452  call    memset_0
0x180043457  movups  xmm0, xmmword ptr [rsi+10h]
0x18004345b  mov     ecx, [rsi+228h]
0x180043461  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180043465  mov     [rbp+57h+var_C0.dwPathType], ecx
0x180043468  movdqu  xmmword ptr [rbp+57h+var_C0.GpoId.Data1], xmm0
0x18004346d  inc     rbx
0x180043470  cmp     [rsi+rbx*2+20h], r12w
0x180043476  jnz     short loc_18004346D
0x180043478  lea     rdi, [rbx+1]
0x18004347c  mov     [rbp+57h+var_C0.pszPackageName], r12
0x180043480  cmp     rdi, rbx
0x180043483  jb      loc_18004363D
0x180043489  lea     r9, [rbp+57h+var_C0]
0x18004348d  mov     r8, rdi
0x180043490  xor     edx, edx
0x180043492  call    ??$_AllocArray@GVCTLocalAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTLocalAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x180043497  test    eax, eax
0x180043499  js      loc_18004363D
0x18004349f  mov     rcx, [rbp+57h+var_C0.pszPackageName]; unsigned __int16 *
0x1800434a3  lea     r8, [rsi+20h]; unsigned __int16 *
0x1800434a7  mov     r9, rbx; unsigned __int64
0x1800434aa  mov     rdx, rdi; unsigned __int64
0x1800434ad  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800434b2  mov     ecx, 90h; this
0x1800434b7  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x1800434bc  test    rax, rax
0x1800434bf  jz      loc_18004363D
0x1800434c5  lea     rdx, [rbp+57h+var_C0]; struct _MANAGEDAPPLICATION *
0x1800434c9  mov     rcx, rax; this
0x1800434cc  call    ??0CDarwinPublishedApp@@QEAA@PEBU_MANAGEDAPPLICATION@@@Z; CDarwinPublishedApp::CDarwinPublishedApp(_MANAGEDAPPLICATION const *)
0x1800434d1  mov     rdi, rax
0x1800434d4  test    rax, rax
0x1800434d7  jz      loc_18004363D
0x1800434dd  mov     rcx, [rax]
0x1800434e0  lea     r8, [rbp+57h+var_D0]
0x1800434e4  lea     rdx, _GUID_12b81347_1b3a_4a04_aa61_3f768b67fd7e
0x1800434eb  mov     [rbp+57h+var_D0], r12
0x1800434ef  mov     rax, [rcx]
0x1800434f2  mov     rcx, rdi
0x1800434f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434fa  xor     edx, edx
0x1800434fc  test    eax, eax
0x1800434fe  js      short loc_18004352E
0x180043500  mov     rcx, [rbp+57h+var_D0]
0x180043504  mov     r8, [rsi+230h]
0x18004350b  mov     rax, [rcx]
0x18004350e  mov     rax, [rax+58h]
0x180043512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043517  mov     rdx, [rbp+57h+var_D0]
0x18004351b  mov     ebx, eax
0x18004351d  mov     rcx, [rdx]
0x180043520  mov     rax, [rcx+10h]
0x180043524  mov     rcx, rdx
0x180043527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004352c  jmp     short loc_18004353F
0x18004352e  mov     rax, [rdi]
0x180043531  mov     rcx, rdi
0x180043534  mov     rax, [rax+40h]
0x180043538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004353d  mov     ebx, eax
0x18004353f  mov     rax, [rdi]
0x180043542  mov     rcx, rdi
0x180043545  jmp     loc_180043630
0x18004354a  xor     edx, edx; pUnkOuter
0x18004354c  mov     qword ptr [rbp+57h+dwItem1], r12
0x180043550  lea     rax, [rbp+57h+dwItem1]
0x180043554  lea     r9, _GUID_c257690d_85de_417c_b964_c22b1a6bb5f7; riid
0x18004355b  mov     [rsp+110h+ppv], rax; ppv
0x180043560  lea     rcx, _GUID_352ec2b7_8b9a_11d1_b8ae_006008059382; rclsid
0x180043567  lea     r8d, [rdx+1]; dwClsContext
0x18004356b  call    cs:__imp_CoCreateInstance
0x180043571  test    eax, eax
0x180043573  js      loc_180043676
0x180043579  mov     rcx, qword ptr [rbp+57h+dwItem1]
0x18004357d  lea     r8, [rbp+57h+var_D0]
0x180043581  mov     [rbp+57h+var_D0], r12
0x180043585  xor     edx, edx
0x180043587  mov     rax, [rcx]
0x18004358a  mov     rax, [rax+30h]
0x18004358e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043593  mov     ebx, eax
0x180043595  test    eax, eax
0x180043597  js      loc_180043629
0x18004359d  mov     [rbp+57h+var_C8], r12
0x1800435a1  mov     edi, r12d
0x1800435a4  jnz     short loc_180043619
0x1800435a6  lea     rdx, [rbp+57h+var_C8]
0x1800435aa  mov     rcx, [rbp+57h+var_D0]
0x1800435ae  mov     rax, [rcx]
0x1800435b1  mov     rax, [rax+18h]
0x1800435b5  cmp     edi, [rsi+22Ch]
0x1800435bb  jnb     short loc_1800435E5
0x1800435bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435c2  mov     ebx, eax
0x1800435c4  test    eax, eax
0x1800435c6  js      short loc_1800435DD
0x1800435c8  mov     rcx, [rbp+57h+var_C8]
0x1800435cc  test    rcx, rcx
0x1800435cf  jz      short loc_1800435DD
0x1800435d1  mov     rax, [rcx]
0x1800435d4  mov     rax, [rax+10h]
0x1800435d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435dd  inc     edi
0x1800435df  test    ebx, ebx
0x1800435e1  jz      short loc_1800435A6
0x1800435e3  jmp     short loc_180043619
0x1800435e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435ea  mov     ebx, eax
0x1800435ec  test    eax, eax
0x1800435ee  js      short loc_180043619
0x1800435f0  mov     rcx, [rbp+57h+var_C8]
0x1800435f4  test    rcx, rcx
0x1800435f7  jz      short loc_180043619
0x1800435f9  mov     rax, [rcx]
0x1800435fc  xor     edx, edx
0x1800435fe  mov     rax, [rax+40h]
0x180043602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043607  mov     rcx, [rbp+57h+var_C8]
0x18004360b  mov     ebx, eax
0x18004360d  mov     rax, [rcx]
0x180043610  mov     rax, [rax+10h]
0x180043614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043619  mov     rcx, [rbp+57h+var_D0]
0x18004361d  mov     rax, [rcx]
0x180043620  mov     rax, [rax+10h]
0x180043624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043629  mov     rcx, qword ptr [rbp+57h+dwItem1]
0x18004362d  mov     rax, [rcx]
0x180043630  mov     rax, [rax+10h]
0x180043634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043639  test    ebx, ebx
0x18004363b  js      short loc_180043676
0x18004363d  mov     rdx, [rsi+8]; struct _ITEMIDLIST_RELATIVE *
0x180043641  lea     r8, [rbp+57h+dwItem1]; struct _ITEMIDLIST_ABSOLUTE **
0x180043645  mov     rcx, [rsi]; struct _ITEMIDLIST_ABSOLUTE *
0x180043648  mov     qword ptr [rbp+57h+dwItem1], r12
0x18004364c  call    ?SHILCombine@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILCombine(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_ABSOLUTE * *)
0x180043651  test    eax, eax
0x180043653  js      short loc_180043676
0x180043655  mov     r8, qword ptr [rbp+57h+dwItem1]; dwItem1
0x180043659  xor     r9d, r9d; dwItem2
0x18004365c  mov     edx, 3000h; uFlags
0x180043661  mov     ecx, 2000h; wEventId
0x180043666  call    cs:__imp_SHChangeNotify
0x18004366c  mov     rcx, qword ptr [rbp+57h+dwItem1]; pidl
0x180043670  call    cs:__imp_ILFree
0x180043676  mov     rcx, rsi; hMem
0x180043679  call    ?FreePublishedAppDataParam@@YAXPEAUtagPublishedAppData@@@Z; FreePublishedAppDataParam(tagPublishedAppData *)
0x18004367e  mov     rcx, r15; hCursor
0x180043681  call    cs:__imp_SetCursor
0x180043687  test    cs:Microsoft_Windows_Shell_AppWizCplEnableBits, 1
0x18004368e  jz      short loc_1800436A5
0x180043690  lea     rax, [rbp+57h+dwItem1]
0x180043694  lea     rdx, AppWizCpl_SoftwareExplorer_InstallApplicationLaunch_Stop; int
0x18004369b  mov     [rsp+110h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x1800436a0  call    McGenEventWrite_EventWriteTransfer
0x1800436a5  xor     eax, eax
0x1800436a7  mov     rcx, [rbp+57h+var_30]
0x1800436ab  xor     rcx, rsp; StackCookie
0x1800436ae  call    __security_check_cookie
0x1800436b3  lea     r11, [rsp+110h+var_20]
0x1800436bb  mov     rbx, [r11+38h]
0x1800436bf  mov     rsi, [r11+40h]
0x1800436c3  mov     rsp, r11
0x1800436c6  pop     r15
0x1800436c8  pop     r14
0x1800436ca  pop     r12
0x1800436cc  pop     rdi
0x1800436cd  pop     rbp
0x1800436ce  retn
```
