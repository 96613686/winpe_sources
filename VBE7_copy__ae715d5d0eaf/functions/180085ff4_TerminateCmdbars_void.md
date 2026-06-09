# TerminateCmdbars(void)

- ea: `0x180085ff4`
- end: `0x1800863a8`
- name: `?TerminateCmdbars@@YAXXZ`
- size: `948`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180024ce0`

## callees

- `0x1800610c0`
- `0x180085ff4`
- `0x1800872fc`
- `0x180379380`

## import_xrefs

- `MSVCR100!free` at `0x1800861c2`
- `MSVCR100!free` at `0x18008632e`
- `MSVCR100!free` at `0x180086347`
- `MSVCR100!free` at `0x180086359`
- `MSVCR100!free` at `0x18008636b`
- `MSVCR100!free` at `0x180086384`
- `MSVCR100!free` at `0x1800861c2`
- `MSVCR100!free` at `0x18008632e`
- `MSVCR100!free` at `0x180086347`
- `MSVCR100!free` at `0x180086359`
- `MSVCR100!free` at `0x18008636b`
- `MSVCR100!free` at `0x180086384`
- `KERNEL32!GlobalLock` at `0x18008626d`
- `KERNEL32!GlobalLock` at `0x18008626d`
- `KERNEL32!GlobalUnlock` at `0x1800862d7`
- `KERNEL32!GlobalUnlock` at `0x1800862d7`
- `ADVAPI32!RegSetValueExA` at `0x1800862c3`
- `ADVAPI32!RegSetValueExA` at `0x1800862c3`
- `ADVAPI32!RegCloseKey` at `0x1800862cd`
- `ADVAPI32!RegCloseKey` at `0x1800862cd`
- `ole32!GetHGlobalFromStream` at `0x180086263`
- `ole32!GetHGlobalFromStream` at `0x180086263`
- `ole32!CreateStreamOnHGlobal` at `0x180086207`
- `ole32!CreateStreamOnHGlobal` at `0x180086207`

## string_xrefs

- `0x180086295`: `UIAccess`

## pseudocode

```c
void __fastcall TerminateCmdbars()
{
  int v0; // eax
  __int64 v1; // rdi
  _DWORD *v2; // r10
  int v3; // ecx
  int v4; // eax
  _QWORD *j; // rax
  struct CmdBarExt *v6; // rdx
  int v7; // r8d
  __int64 v8; // rcx
  _QWORD *v9; // r10
  __int64 v10; // rcx
  _QWORD *v11; // rax
  struct IStreamVtbl *lpVtbl; // rax
  DWORD cbData; // ebx
  const BYTE *lpData; // rdi
  const CHAR *v15; // rdx
  _QWORD *v16; // rax
  _QWORD *v17; // rbx
  HKEY hKey; // [rsp+40h] [rbp-28h] BYREF
  HGLOBAL phglobal[2]; // [rsp+48h] [rbp-20h] BYREF
  DWORD v20[4]; // [rsp+58h] [rbp-10h] BYREF
  int i; // [rsp+90h] [rbp+28h] BYREF
  unsigned int v22; // [rsp+98h] [rbp+30h] BYREF
  __int64 v23; // [rsp+A0h] [rbp+38h] BYREF
  LPSTREAM ppstm; // [rsp+A8h] [rbp+40h] BYREF

  v1 = (unsigned int)(v0 - 103);
  g_fInTerminateCmdBars = v0 - 103;
  if ( ToolBarSet_ptbs )
  {
    while ( 1 )
    {
      v2 = (char *)IMsoPointers_rgpmso + 24 * g_itbAddIns;
      v3 = v2[2];
      if ( v3 <= g_iNumCmdsOnAddinMenu )
        break;
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)v2 + 72LL))(
        *(_QWORD *)v2,
        (unsigned int)(v3 - 1),
        0);
      --*((_DWORD *)IMsoPointers_rgpmso + 6 * g_itbAddIns + 2);
    }
    v4 = 72;
    for ( i = 72; i < iIMsoPointersSize; v4 = i )
    {
      CmdBarDestroyMenu(v4);
      i += v1;
    }
LABEL_7:
    for ( j = g_pCustomBar; j; j = (_QWORD *)j[3] )
    {
      if ( !*((_DWORD *)j + 4) && j[1] )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)j[1] + 96LL))(j[1]);
        goto LABEL_7;
      }
    }
    v6 = (struct CmdBarExt *)g_pCmdBarExtHead;
    while ( v6 )
    {
      v22 = -1;
      v23 = 0;
      i = 0;
LABEL_15:
      while ( (*(unsigned int (__fastcall **)(struct IMsoToolbarSet *, _QWORD, _QWORD, _QWORD, _DWORD, int *, unsigned int *, __int64 *))(*(_QWORD *)ToolBarSet_ptbs + 120LL))(
                ToolBarSet_ptbs,
                *((unsigned int *)v6 + 4),
                *((unsigned int *)v6 + 5),
                0,
                v1,
                &i,
                &v22,
                &v23) )
      {
        v6 = (struct CmdBarExt *)g_pCmdBarExtHead;
        if ( *(_QWORD *)g_pCmdBarExtHead == v23 )
        {
          v7 = 0;
          v8 = 0;
          if ( iIMsoPointersSize > 0 )
          {
            v9 = (char *)IMsoPointers_rgpmso + 16;
            while ( v7 == iIMsoPointersSize - 1 || *v9 != *((_QWORD *)g_pCmdBarExtHead + 1) )
            {
              v7 += v1;
              v8 += v1;
              v9 += 3;
              if ( v7 >= iIMsoPointersSize )
                goto LABEL_24;
            }
            v10 = *((_QWORD *)IMsoPointers_rgpmso + 3 * v8);
            if ( v10 )
            {
LABEL_29:
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v10 + 72LL))(v10, v22, 0);
              break;
            }
          }
LABEL_24:
          v11 = g_pCustomBar;
          if ( g_pCustomBar )
          {
            while ( *v11 != *((_QWORD *)g_pCmdBarExtHead + 1) )
            {
              v11 = (_QWORD *)v11[3];
              if ( !v11 )
                goto LABEL_15;
            }
            v10 = v11[1];
            if ( v10 )
              goto LABEL_29;
          }
        }
      }
      g_pCmdBarExtEnd = (struct CmdBarExt *)*((_QWORD *)g_pCmdBarExtHead + 4);
      free(g_pCmdBarExtHead);
      v6 = g_pCmdBarExtEnd;
      g_pCmdBarExtHead = g_pCmdBarExtEnd;
    }
    if ( (*(unsigned int (__fastcall **)(struct IMsoToolbarSet *))(*(_QWORD *)ToolBarSet_ptbs + 304LL))(ToolBarSet_ptbs) )
    {
      ppstm = 0;
      phglobal[0] = 0;
      CreateStreamOnHGlobal(0, v1, &ppstm);
      LODWORD(v23) = 105;
      ((void (__fastcall *)(LPSTREAM, __int64 *, __int64))ppstm->lpVtbl->Write)(ppstm, &v23, 4);
      (*(void (__fastcall **)(struct IMsoToolbarSet *, LPSTREAM, _QWORD))(*(_QWORD *)ToolBarSet_ptbs + 80LL))(
        ToolBarSet_ptbs,
        ppstm,
        0);
      lpVtbl = ppstm->lpVtbl;
      phglobal[1] = 0;
      ((void (__fastcall *)(LPSTREAM, _QWORD, __int64, DWORD *))lpVtbl->Seek)(ppstm, 0, 2, v20);
      cbData = v20[0];
      GetHGlobalFromStream(ppstm, phglobal);
      lpData = (const BYTE *)GlobalLock(phglobal[0]);
      hKey = 0;
      if ( !(unsigned int)VBRegOpenOptionRoot(HKEY_CURRENT_USER, &hKey) )
      {
        v15 = "UI";
        if ( *((_DWORD *)CVbe::m_pVbe + 49) )
          v15 = "UIAccess";
        RegSetValueExA(hKey, v15, 0, 3u, lpData, cbData);
        RegCloseKey(hKey);
      }
      GlobalUnlock(phglobal[0]);
      ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
    }
    MsoDestroyIPrefAPI(g_msopref);
    (*(void (__fastcall **)(struct IMsoToolbarSet *))(*(_QWORD *)ToolBarSet_ptbsProjwin + 128LL))(ToolBarSet_ptbsProjwin);
    ToolBarSet_ptbsProjwin = 0;
    (*(void (__fastcall **)(struct IMsoToolbarSet *))(*(_QWORD *)ToolBarSet_ptbs + 128LL))(ToolBarSet_ptbs);
    ToolBarSet_ptbs = 0;
    if ( IMsoPointers_rgpmso )
    {
      free(IMsoPointers_rgpmso);
      IMsoPointers_rgpmso = 0;
    }
    if ( NewItems_rgtbitem )
      free(NewItems_rgtbitem);
    if ( NewTBInfo_rgtb )
      free(NewTBInfo_rgtb);
    if ( New_rgMenuInfo )
      free(New_rgMenuInfo);
    v16 = g_pCustomBar;
    if ( g_pCustomBar )
    {
      do
      {
        v17 = (_QWORD *)v16[3];
        free(v16);
        v16 = v17;
        g_pCustomBar = v17;
      }
      while ( v17 );
    }
    g_fInTerminateCmdBars = 0;
  }
}

```

## disassembly

```asm
0x180085ff4  push    rbp
0x180085ff6  push    rbx
0x180085ff7  push    rsi
0x180085ff8  push    rdi
0x180085ff9  mov     rbp, rsp
0x180085ffc  mov     eax, 68h
0x180086001  call    _alloca_probe
0x180086006  sub     rsp, rax
0x180086009  lea     edi, [rax-67h]
0x18008600c  xor     esi, esi
0x18008600e  cmp     cs:?ToolBarSet_ptbs@@3PEAUIMsoToolbarSet@@EA, rsi; IMsoToolbarSet * ToolBarSet_ptbs
0x180086015  mov     cs:?g_fInTerminateCmdBars@@3HA, edi; int g_fInTerminateCmdBars
0x18008601b  jz      loc_18008639F
0x180086021  jmp     short loc_18008604C
0x180086023  mov     rax, [r10]
0x180086026  lea     edx, [rcx-1]
0x180086029  xor     r8d, r8d
0x18008602c  mov     r9, [rax]
0x18008602f  mov     rcx, rax
0x180086032  call    qword ptr [r9+48h]
0x180086036  movsxd  r11, cs:?g_itbAddIns@@3HA; int g_itbAddIns
0x18008603d  mov     rax, cs:?IMsoPointers_rgpmso@@3PEAUtagVBTB@@EA; tagVBTB * IMsoPointers_rgpmso
0x180086044  lea     rcx, [r11+r11*2]
0x180086048  dec     dword ptr [rax+rcx*8+8]
0x18008604c  movsxd  rax, cs:?g_itbAddIns@@3HA; int g_itbAddIns
0x180086053  lea     rcx, [rax+rax*2]
0x180086057  mov     rax, cs:?IMsoPointers_rgpmso@@3PEAUtagVBTB@@EA; tagVBTB * IMsoPointers_rgpmso
0x18008605e  lea     r10, [rax+rcx*8]
0x180086062  mov     ecx, [r10+8]
0x180086066  cmp     ecx, cs:?g_iNumCmdsOnAddinMenu@@3HA; int g_iNumCmdsOnAddinMenu
0x18008606c  jg      short loc_180086023
0x18008606e  mov     eax, 48h ; 'H'
0x180086073  cmp     cs:?iIMsoPointersSize@@3HA, eax; int iIMsoPointersSize
0x180086079  mov     [rbp+arg_0], eax
0x18008607c  jle     short loc_180086095
0x18008607e  mov     ecx, eax; int
0x180086080  call    ?CmdBarDestroyMenu@@YAHH@Z; CmdBarDestroyMenu(int)
0x180086085  mov     eax, [rbp+arg_0]
0x180086088  add     eax, edi
0x18008608a  cmp     eax, cs:?iIMsoPointersSize@@3HA; int iIMsoPointersSize
0x180086090  mov     [rbp+arg_0], eax
0x180086093  jl      short loc_18008607E
0x180086095  mov     rax, cs:?g_pCustomBar@@3PEAUCmdBarCustomBar@@EA; CmdBarCustomBar * g_pCustomBar
0x18008609c  jmp     short loc_1800860B9
0x18008609e  cmp     [rax+10h], esi
0x1800860a1  jnz     short loc_1800860B5
0x1800860a3  cmp     [rax+8], rsi
0x1800860a7  jz      short loc_1800860B5
0x1800860a9  mov     rcx, [rax+8]
0x1800860ad  mov     rax, [rcx]
0x1800860b0  call    qword ptr [rax+60h]
0x1800860b3  jmp     short loc_180086095
0x1800860b5  mov     rax, [rax+18h]
0x1800860b9  test    rax, rax
0x1800860bc  jnz     short loc_18008609E
0x1800860be  mov     rdx, cs:?g_pCmdBarExtHead@@3PEAUCmdBarExt@@EA; CmdBarExt * g_pCmdBarExtHead
0x1800860c5  jmp     loc_1800861D6
0x1800860ca  or      [rbp+arg_8], 0FFFFFFFFh
0x1800860ce  mov     [rbp+arg_10], rsi
0x1800860d2  mov     [rbp+arg_0], esi
0x1800860d5  mov     rcx, cs:?ToolBarSet_ptbs@@3PEAUIMsoToolbarSet@@EA; IMsoToolbarSet * ToolBarSet_ptbs
0x1800860dc  lea     r8, [rbp+arg_10]
0x1800860e0  xor     r9d, r9d
0x1800860e3  mov     rax, [rcx]
0x1800860e6  mov     [rsp+68h+var_30], r8
0x1800860eb  lea     r8, [rbp+arg_8]
0x1800860ef  mov     [rsp+68h+var_38], r8
0x1800860f4  lea     r8, [rbp+arg_0]
0x1800860f8  mov     qword ptr [rsp+68h+cbData], r8
0x1800860fd  mov     r8d, [rdx+14h]
0x180086101  mov     edx, [rdx+10h]
0x180086104  mov     dword ptr [rsp+68h+lpData], edi
0x180086108  call    qword ptr [rax+78h]
0x18008610b  test    eax, eax
0x18008610d  jz      loc_1800861B0
0x180086113  mov     rdx, cs:?g_pCmdBarExtHead@@3PEAUCmdBarExt@@EA; CmdBarExt * g_pCmdBarExtHead
0x18008611a  mov     rax, [rbp+arg_10]
0x18008611e  cmp     [rdx], rax
0x180086121  jnz     short loc_1800860D5
0x180086123  mov     r9d, cs:?iIMsoPointersSize@@3HA; int iIMsoPointersSize
0x18008612a  mov     r8d, esi
0x18008612d  mov     rcx, rsi
0x180086130  test    r9d, r9d
0x180086133  jle     short loc_180086170
0x180086135  mov     r11, cs:?IMsoPointers_rgpmso@@3PEAUtagVBTB@@EA; tagVBTB * IMsoPointers_rgpmso
0x18008613c  lea     ebx, [r9-1]
0x180086140  lea     r10, [r11+10h]
0x180086144  cmp     r8d, ebx
0x180086147  jz      short loc_180086152
0x180086149  mov     rax, [rdx+8]
0x18008614d  cmp     [r10], rax
0x180086150  jz      short loc_180086163
0x180086152  add     r8d, edi
0x180086155  add     rcx, rdi
0x180086158  add     r10, 18h
0x18008615c  cmp     r8d, r9d
0x18008615f  jge     short loc_180086170
0x180086161  jmp     short loc_180086144
0x180086163  lea     rax, [rcx+rcx*2]
0x180086167  mov     rcx, [r11+rax*8]
0x18008616b  test    rcx, rcx
0x18008616e  jnz     short loc_1800861A4
0x180086170  mov     rax, cs:?g_pCustomBar@@3PEAUCmdBarCustomBar@@EA; CmdBarCustomBar * g_pCustomBar
0x180086177  test    rax, rax
0x18008617a  jz      loc_1800860D5
0x180086180  mov     rcx, [rdx+8]
0x180086184  cmp     [rax], rcx
0x180086187  jz      short loc_180086197
0x180086189  mov     rax, [rax+18h]
0x18008618d  test    rax, rax
0x180086190  jnz     short loc_180086184
0x180086192  jmp     loc_1800860D5
0x180086197  mov     rcx, [rax+8]
0x18008619b  test    rcx, rcx
0x18008619e  jz      loc_1800860D5
0x1800861a4  mov     rax, [rcx]
0x1800861a7  mov     edx, [rbp+arg_8]
0x1800861aa  xor     r8d, r8d
0x1800861ad  call    qword ptr [rax+48h]
0x1800861b0  mov     rcx, cs:?g_pCmdBarExtHead@@3PEAUCmdBarExt@@EA; Block
0x1800861b7  mov     rax, [rcx+20h]
0x1800861bb  mov     cs:?g_pCmdBarExtEnd@@3PEAUCmdBarExt@@EA, rax; CmdBarExt * g_pCmdBarExtEnd
0x1800861c2  call    cs:__imp_free
0x1800861c8  mov     rdx, cs:?g_pCmdBarExtEnd@@3PEAUCmdBarExt@@EA; CmdBarExt * g_pCmdBarExtEnd
0x1800861cf  mov     cs:?g_pCmdBarExtHead@@3PEAUCmdBarExt@@EA, rdx; CmdBarExt * g_pCmdBarExtHead
0x1800861d6  test    rdx, rdx
0x1800861d9  jnz     loc_1800860CA
0x1800861df  mov     rcx, cs:?ToolBarSet_ptbs@@3PEAUIMsoToolbarSet@@EA; IMsoToolbarSet * ToolBarSet_ptbs
0x1800861e6  mov     rax, [rcx]
0x1800861e9  call    qword ptr [rax+130h]
0x1800861ef  test    eax, eax
0x1800861f1  jz      loc_1800862E7
0x1800861f7  lea     r8, [rbp+ppstm]; ppstm
0x1800861fb  mov     edx, edi; fDeleteOnRelease
0x1800861fd  xor     ecx, ecx; hGlobal
0x1800861ff  mov     [rbp+ppstm], rsi
0x180086203  mov     [rbp+phglobal], rsi
0x180086207  call    cs:__imp_CreateStreamOnHGlobal
0x18008620d  mov     rcx, [rbp+ppstm]
0x180086211  xor     r9d, r9d
0x180086214  mov     dword ptr [rbp+arg_10], 69h ; 'i'
0x18008621b  mov     rax, [rcx]
0x18008621e  lea     r8d, [r9+4]
0x180086222  lea     rdx, [rbp+arg_10]
0x180086226  call    qword ptr [rax+20h]
0x180086229  mov     rcx, cs:?ToolBarSet_ptbs@@3PEAUIMsoToolbarSet@@EA; IMsoToolbarSet * ToolBarSet_ptbs
0x180086230  mov     rdx, [rbp+ppstm]
0x180086234  mov     rax, [rcx]
0x180086237  xor     r8d, r8d
0x18008623a  call    qword ptr [rax+50h]
0x18008623d  mov     rcx, [rbp+ppstm]
0x180086241  lea     r9, [rbp+var_10]
0x180086245  mov     rax, [rcx]
0x180086248  mov     r8d, 2
0x18008624e  mov     rdx, rsi
0x180086251  mov     [rbp+var_18], rsi
0x180086255  call    qword ptr [rax+28h]
0x180086258  mov     rcx, [rbp+ppstm]; pstm
0x18008625c  mov     ebx, [rbp+var_10]
0x18008625f  lea     rdx, [rbp+phglobal]; phglobal
0x180086263  call    cs:__imp_GetHGlobalFromStream
0x180086269  mov     rcx, [rbp+phglobal]; hMem
0x18008626d  call    cs:__imp_GlobalLock
0x180086273  lea     rdx, [rbp+hKey]; HKEY *
0x180086277  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18008627e  mov     rdi, rax
0x180086281  mov     [rbp+hKey], rsi
0x180086285  call    ?VBRegOpenOptionRoot@@YAJPEAUHKEY__@@PEAPEAU1@@Z; VBRegOpenOptionRoot(HKEY__ *,HKEY__ * *)
0x18008628a  test    eax, eax
0x18008628c  jnz     short loc_1800862D3
0x18008628e  mov     rcx, cs:?m_pVbe@CVbe@@0PEAV1@EA; CVbe * CVbe::m_pVbe
0x180086295  lea     rax, ?szVBCmdBarValueNameAccess@@3QBDB; "UIAccess"
0x18008629c  lea     rdx, ?szVBCmdBarValueName@@3QBDB; "UI"
0x1800862a3  cmp     [rcx+0C4h], esi
0x1800862a9  mov     rcx, [rbp+hKey]; hKey
0x1800862ad  mov     r9d, 3; dwType
0x1800862b3  cmovnz  rdx, rax; lpValueName
0x1800862b7  xor     r8d, r8d; Reserved
0x1800862ba  mov     [rsp+68h+cbData], ebx; cbData
0x1800862be  mov     [rsp+68h+lpData], rdi; lpData
0x1800862c3  call    cs:__imp_RegSetValueExA
0x1800862c9  mov     rcx, [rbp+hKey]; hKey
0x1800862cd  call    cs:__imp_RegCloseKey
0x1800862d3  mov     rcx, [rbp+phglobal]; hMem
0x1800862d7  call    cs:__imp_GlobalUnlock
0x1800862dd  mov     rcx, [rbp+ppstm]
0x1800862e1  mov     rax, [rcx]
0x1800862e4  call    qword ptr [rax+10h]
0x1800862e7  mov     rcx, cs:?g_msopref@@3PEAUIMsoPref@@EA; IMsoPref * g_msopref
0x1800862ee  call    cs:?MsoDestroyIPrefAPI@@3P6AXPEAUIMsoPref@@@ZEA; void (*MsoDestroyIPrefAPI)(IMsoPref *)
0x1800862f4  mov     rcx, cs:?ToolBarSet_ptbsProjwin@@3PEAUIMsoToolbarSet@@EA; IMsoToolbarSet * ToolBarSet_ptbsProjwin
0x1800862fb  mov     rax, [rcx]
0x1800862fe  call    qword ptr [rax+80h]
0x180086304  mov     rcx, cs:?ToolBarSet_ptbs@@3PEAUIMsoToolbarSet@@EA; IMsoToolbarSet * ToolBarSet_ptbs
0x18008630b  mov     cs:?ToolBarSet_ptbsProjwin@@3PEAUIMsoToolbarSet@@EA, rsi; IMsoToolbarSet * ToolBarSet_ptbsProjwin
0x180086312  mov     rax, [rcx]
0x180086315  call    qword ptr [rax+80h]
0x18008631b  mov     rcx, cs:?IMsoPointers_rgpmso@@3PEAUtagVBTB@@EA; Block
0x180086322  mov     cs:?ToolBarSet_ptbs@@3PEAUIMsoToolbarSet@@EA, rsi; IMsoToolbarSet * ToolBarSet_ptbs
0x180086329  test    rcx, rcx
0x18008632c  jz      short loc_18008633B
0x18008632e  call    cs:__imp_free
0x180086334  mov     cs:?IMsoPointers_rgpmso@@3PEAUtagVBTB@@EA, rsi; tagVBTB * IMsoPointers_rgpmso
0x18008633b  mov     rcx, cs:?NewItems_rgtbitem@@3PEAUtagTBITEM_NEW@@EA; Block
0x180086342  test    rcx, rcx
0x180086345  jz      short loc_18008634D
0x180086347  call    cs:__imp_free
0x18008634d  mov     rcx, cs:?NewTBInfo_rgtb@@3PEAUtagTBINFO_NEW@@EA; Block
0x180086354  test    rcx, rcx
0x180086357  jz      short loc_18008635F
0x180086359  call    cs:__imp_free
0x18008635f  mov     rcx, cs:?New_rgMenuInfo@@3PEAUtagVbaMENUINFO@@EA; Block
0x180086366  test    rcx, rcx
0x180086369  jz      short loc_180086371
0x18008636b  call    cs:__imp_free
0x180086371  mov     rax, cs:?g_pCustomBar@@3PEAUCmdBarCustomBar@@EA; CmdBarCustomBar * g_pCustomBar
0x180086378  test    rax, rax
0x18008637b  jz      short loc_180086399
0x18008637d  mov     rbx, [rax+18h]
0x180086381  mov     rcx, rax; Block
0x180086384  call    cs:__imp_free
0x18008638a  mov     rax, rbx
0x18008638d  mov     cs:?g_pCustomBar@@3PEAUCmdBarCustomBar@@EA, rbx; CmdBarCustomBar * g_pCustomBar
0x180086394  test    rbx, rbx
0x180086397  jnz     short loc_18008637D
0x180086399  mov     cs:?g_fInTerminateCmdBars@@3HA, esi; int g_fInTerminateCmdBars
0x18008639f  add     rsp, 68h
0x1800863a3  pop     rdi
0x1800863a4  pop     rsi
0x1800863a5  pop     rbx
0x1800863a6  pop     rbp
0x1800863a7  retn
```
