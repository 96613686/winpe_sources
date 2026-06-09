# pUnloadMountedHives(ushort const *)

- ea: `0x140059484`
- end: `0x1400597b1`
- name: `?pUnloadMountedHives@@YAJPEBG@Z`
- size: `813`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400570e0`

## callees

- `0x1400275b4`
- `0x140055c70`
- `0x140055d10`
- `0x1400564fc`
- `0x140056998`
- `0x140059484`
- `0x140082010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400595c4`
- `KERNEL32!HeapFree` at `0x140059700`
- `KERNEL32!HeapFree` at `0x140059745`
- `KERNEL32!HeapFree` at `0x140059785`
- `KERNEL32!HeapFree` at `0x1400595c4`
- `KERNEL32!HeapFree` at `0x140059700`
- `KERNEL32!HeapFree` at `0x140059745`
- `KERNEL32!HeapFree` at `0x140059785`
- `KERNEL32!GetProcessHeap` at `0x1400595b0`
- `KERNEL32!GetProcessHeap` at `0x1400596ec`
- `KERNEL32!GetProcessHeap` at `0x140059731`
- `KERNEL32!GetProcessHeap` at `0x140059771`
- `KERNEL32!GetProcessHeap` at `0x1400595b0`
- `KERNEL32!GetProcessHeap` at `0x1400596ec`
- `KERNEL32!GetProcessHeap` at `0x140059731`
- `KERNEL32!GetProcessHeap` at `0x140059771`
- `KERNEL32!GetLastError` at `0x1400594dd`
- `KERNEL32!GetLastError` at `0x1400594fb`
- `KERNEL32!GetLastError` at `0x140059519`
- `KERNEL32!GetLastError` at `0x14005961c`
- `KERNEL32!GetLastError` at `0x14005963a`
- `KERNEL32!GetLastError` at `0x140059658`
- `KERNEL32!GetLastError` at `0x1400594dd`
- `KERNEL32!GetLastError` at `0x1400594fb`
- `KERNEL32!GetLastError` at `0x140059519`
- `KERNEL32!GetLastError` at `0x14005961c`
- `KERNEL32!GetLastError` at `0x14005963a`
- `KERNEL32!GetLastError` at `0x140059658`
- `WDSCORE!WdsSetupLogMessageW` at `0x140059596`
- `WDSCORE!WdsSetupLogMessageW` at `0x1400596d2`
- `WDSCORE!WdsSetupLogMessageW` at `0x140059596`
- `WDSCORE!WdsSetupLogMessageW` at `0x1400596d2`
- `WDSCORE!CurrentIP` at `0x140059527`
- `WDSCORE!CurrentIP` at `0x140059666`
- `WDSCORE!CurrentIP` at `0x140059527`
- `WDSCORE!CurrentIP` at `0x140059666`

## string_xrefs

- `0x140059567`: `pUnloadMountedHives`
- `0x1400596a3`: `pUnloadMountedHives`
- `0x14005953c`: `Conversion to NT path failed for %s. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall pUnloadMountedHives(char *a1)
{
  unsigned __int16 **Namespace; // rax
  signed int LastError; // eax
  bool v4; // sf
  signed int v5; // eax
  unsigned int v6; // esi
  DWORD v7; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  void *v10; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v13; // rax
  HKEY v14; // rdx
  const unsigned __int16 *v15; // r8
  signed int v16; // eax
  bool v17; // sf
  signed int v18; // eax
  DWORD v19; // edi
  __int64 v20; // rbx
  struct tagLOG_PARTIAL_MSG *v21; // rax
  void *v22; // rbx
  HANDLE v23; // rax
  void *v24; // rbx
  HANDLE v25; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  void **v28; // [rsp+70h] [rbp+1Fh] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp+27h]
  void **v30; // [rsp+80h] [rbp+2Fh] BYREF
  void **v31; // [rsp+88h] [rbp+37h]
  LPVOID v32; // [rsp+90h] [rbp+3Fh]

  lpMem = 0;
  v28 = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
  Namespace = (unsigned __int16 **)CBasicNodeType::GetNamespace((CBasicNodeType *)&v28);
  if ( !HiveListEnumerator::ConvertWin32PathToNt((WCHAR *)a1, Namespace) )
  {
    LastError = GetLastError();
    v4 = LastError < 0;
    if ( LastError > 0 )
      v4 = 1;
    if ( v4 )
    {
      v5 = GetLastError();
      v6 = v5;
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    v7 = GetLastError();
    v8 = CurrentIP();
    v9 = ConstructPartialMsgW(50331648, "Conversion to NT path failed for %s. Error: 0x%08X", a1, v6);
    WdsSetupLogMessageW(
      v9,
      0,
      L"D",
      0,
      544,
      L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
      L"pUnloadMountedHives",
      v8,
      v7,
      0,
      0);
LABEL_9:
    v28 = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
    v10 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v10);
    }
    return v6;
  }
  v13 = (unsigned __int16 *)((__int64 (__fastcall *)(void ***))v28[4])(&v28);
  v30 = &DirectoryHiveUnloader::`vftable';
  v32 = (LPVOID)StrDupe(v13);
  v31 = &RAII::CAutoWdsLibFree<unsigned short const *>::`vftable';
  if ( !RegValueEnumAction::Enumerate((struct RegValueEnumAction *)&v30, v14, v15) )
  {
    v16 = GetLastError();
    v17 = v16 < 0;
    if ( v16 > 0 )
      v17 = 1;
    if ( v17 )
    {
      v18 = GetLastError();
      v6 = v18;
      if ( v18 > 0 )
        v6 = (unsigned __int16)v18 | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    v19 = GetLastError();
    v20 = CurrentIP();
    v21 = ConstructPartialMsgW(50331648, "Enumeration of hive list failed. Error: 0x%08X", v6);
    WdsSetupLogMessageW(
      v21,
      0,
      L"D",
      0,
      554,
      L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
      L"pUnloadMountedHives",
      v20,
      v19,
      0,
      0);
    v31 = &RAII::CAutoWdsLibFree<unsigned short const *>::`vftable';
    v22 = v32;
    if ( v32 )
    {
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v22);
      v32 = 0;
    }
    v30 = &RegValueEnumAction::`vftable';
    goto LABEL_9;
  }
  v31 = &RAII::CAutoWdsLibFree<unsigned short const *>::`vftable';
  v24 = v32;
  if ( v32 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v24);
    v32 = 0;
  }
  v30 = &RegValueEnumAction::`vftable';
  v28 = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
  v26 = lpMem;
  if ( lpMem )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v26);
  }
  return 0;
}

```

## disassembly

```asm
0x140059484  mov     rax, rsp
0x140059487  push    rbp
0x140059488  push    r12
0x14005948a  push    r14
0x14005948c  lea     rbp, [rax-5Fh]
0x140059490  sub     rsp, 90h
0x140059497  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x14005949f  mov     [rax+8], rbx
0x1400594a3  mov     [rax+10h], rsi
0x1400594a7  mov     [rax+18h], rdi
0x1400594ab  mov     r14, rcx
0x1400594ae  mov     [rbp+57h+lpMem], 0
0x1400594b6  lea     r12, ??_7?$CAutoWdsLibFree@PEAG@RAII@@6B@; const RAII::CAutoWdsLibFree<ushort *>::`vftable'
0x1400594bd  mov     [rbp+57h+var_38], r12
0x1400594c1  lea     rcx, [rbp+57h+var_38]; this
0x1400594c5  call    ?GetNamespace@CBasicNodeType@@UEBAPEBU_LUTF8_STRING@@XZ; CBasicNodeType::GetNamespace(void)
0x1400594ca  mov     rdx, rax; unsigned __int16 **
0x1400594cd  mov     rcx, r14; unsigned __int16 *
0x1400594d0  call    ?ConvertWin32PathToNt@HiveListEnumerator@@SA_NPEBGPEAPEAG@Z; HiveListEnumerator::ConvertWin32PathToNt(ushort const *,ushort * *)
0x1400594d5  test    al, al
0x1400594d7  jnz     loc_1400595D7
0x1400594dd  call    cs:__imp_GetLastError
0x1400594e4  nop     dword ptr [rax+rax+00h]
0x1400594e9  mov     ebx, 80070000h
0x1400594ee  test    eax, eax
0x1400594f0  jle     short loc_1400594F9
0x1400594f2  movzx   eax, ax
0x1400594f5  or      eax, ebx
0x1400594f7  test    eax, eax
0x1400594f9  jns     short loc_140059514
0x1400594fb  call    cs:__imp_GetLastError
0x140059502  nop     dword ptr [rax+rax+00h]
0x140059507  mov     esi, eax
0x140059509  test    eax, eax
0x14005950b  jle     short loc_140059519
0x14005950d  movzx   esi, ax
0x140059510  or      esi, ebx
0x140059512  jmp     short loc_140059519
0x140059514  mov     esi, 80004005h
0x140059519  call    cs:__imp_GetLastError
0x140059520  nop     dword ptr [rax+rax+00h]
0x140059525  mov     edi, eax
0x140059527  call    cs:__imp_CurrentIP
0x14005952e  nop     dword ptr [rax+rax+00h]
0x140059533  mov     rbx, rax
0x140059536  mov     r9d, esi
0x140059539  mov     r8, r14
0x14005953c  lea     rdx, aConversionToNt; "Conversion to NT path failed for %s. Er"...
0x140059543  mov     ecx, 3000000h; unsigned int
0x140059548  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005954d  mov     [rsp+0A0h+var_50], 0
0x140059555  mov     qword ptr [rsp+0A0h+var_58], 0
0x14005955e  mov     dword ptr [rsp+0A0h+var_60], edi
0x140059562  mov     qword ptr [rsp+0A0h+var_68], rbx
0x140059567  lea     rcx, aPunloadmounted; "pUnloadMountedHives"
0x14005956e  mov     [rsp+0A0h+var_70], rcx
0x140059573  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x14005957a  mov     [rsp+0A0h+var_78], rcx
0x14005957f  mov     dword ptr [rsp+0A0h+var_80], 220h
0x140059587  xor     r9d, r9d
0x14005958a  lea     r8, aD; "D"
0x140059591  xor     edx, edx
0x140059593  mov     rcx, rax
0x140059596  call    cs:__imp_WdsSetupLogMessageW
0x14005959d  nop     dword ptr [rax+rax+00h]
0x1400595a2  nop
0x1400595a3  mov     [rbp+57h+var_38], r12
0x1400595a7  mov     rbx, [rbp+57h+lpMem]
0x1400595ab  test    rbx, rbx
0x1400595ae  jz      short loc_1400595D0
0x1400595b0  call    cs:__imp_GetProcessHeap
0x1400595b7  nop     dword ptr [rax+rax+00h]
0x1400595bc  mov     r8, rbx; lpMem
0x1400595bf  xor     edx, edx; dwFlags
0x1400595c1  mov     rcx, rax; hHeap
0x1400595c4  call    cs:__imp_HeapFree
0x1400595cb  nop     dword ptr [rax+rax+00h]
0x1400595d0  mov     eax, esi
0x1400595d2  jmp     loc_140059793
0x1400595d7  mov     rax, [rbp+57h+var_38]
0x1400595db  lea     rcx, [rbp+57h+var_38]
0x1400595df  mov     rax, [rax+20h]
0x1400595e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400595e8  nop
0x1400595e9  lea     rcx, ??_7DirectoryHiveUnloader@@6B@; const DirectoryHiveUnloader::`vftable'
0x1400595f0  mov     [rbp+57h+var_28], rcx
0x1400595f4  mov     rcx, rax; unsigned __int16 *
0x1400595f7  call    StrDupe
0x1400595fc  mov     [rbp+57h+var_18], rax
0x140059600  lea     r14, ??_7?$CAutoWdsLibFree@PEBG@RAII@@6B@; const RAII::CAutoWdsLibFree<ushort const *>::`vftable'
0x140059607  mov     [rbp+57h+var_20], r14
0x14005960b  lea     rcx, [rbp+57h+var_28]; struct RegValueEnumAction *
0x14005960f  call    ?Enumerate@RegValueEnumAction@@SA_NAEAV1@PEAUHKEY__@@PEBG@Z; RegValueEnumAction::Enumerate(RegValueEnumAction &,HKEY__ *,ushort const *)
0x140059614  test    al, al
0x140059616  jnz     loc_140059724
0x14005961c  call    cs:__imp_GetLastError
0x140059623  nop     dword ptr [rax+rax+00h]
0x140059628  mov     ebx, 80070000h
0x14005962d  test    eax, eax
0x14005962f  jle     short loc_140059638
0x140059631  movzx   eax, ax
0x140059634  or      eax, ebx
0x140059636  test    eax, eax
0x140059638  jns     short loc_140059653
0x14005963a  call    cs:__imp_GetLastError
0x140059641  nop     dword ptr [rax+rax+00h]
0x140059646  mov     esi, eax
0x140059648  test    eax, eax
0x14005964a  jle     short loc_140059658
0x14005964c  movzx   esi, ax
0x14005964f  or      esi, ebx
0x140059651  jmp     short loc_140059658
0x140059653  mov     esi, 80004005h
0x140059658  call    cs:__imp_GetLastError
0x14005965f  nop     dword ptr [rax+rax+00h]
0x140059664  mov     edi, eax
0x140059666  call    cs:__imp_CurrentIP
0x14005966d  nop     dword ptr [rax+rax+00h]
0x140059672  mov     rbx, rax
0x140059675  mov     r8d, esi
0x140059678  lea     rdx, aEnumerationOfH; "Enumeration of hive list failed. Error:"...
0x14005967f  mov     ecx, 3000000h; unsigned int
0x140059684  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140059689  mov     [rsp+0A0h+var_50], 0
0x140059691  mov     qword ptr [rsp+0A0h+var_58], 0
0x14005969a  mov     dword ptr [rsp+0A0h+var_60], edi
0x14005969e  mov     qword ptr [rsp+0A0h+var_68], rbx
0x1400596a3  lea     rcx, aPunloadmounted; "pUnloadMountedHives"
0x1400596aa  mov     [rsp+0A0h+var_70], rcx
0x1400596af  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x1400596b6  mov     [rsp+0A0h+var_78], rcx
0x1400596bb  mov     dword ptr [rsp+0A0h+var_80], 22Ah
0x1400596c3  xor     r9d, r9d
0x1400596c6  lea     r8, aD; "D"
0x1400596cd  xor     edx, edx
0x1400596cf  mov     rcx, rax
0x1400596d2  call    cs:__imp_WdsSetupLogMessageW
0x1400596d9  nop     dword ptr [rax+rax+00h]
0x1400596de  nop
0x1400596df  mov     [rbp+57h+var_20], r14
0x1400596e3  mov     rbx, [rbp+57h+var_18]
0x1400596e7  test    rbx, rbx
0x1400596ea  jz      short loc_140059714
0x1400596ec  call    cs:__imp_GetProcessHeap
0x1400596f3  nop     dword ptr [rax+rax+00h]
0x1400596f8  mov     r8, rbx; lpMem
0x1400596fb  xor     edx, edx; dwFlags
0x1400596fd  mov     rcx, rax; hHeap
0x140059700  call    cs:__imp_HeapFree
0x140059707  nop     dword ptr [rax+rax+00h]
0x14005970c  mov     [rbp+57h+var_18], 0
0x140059714  lea     rax, ??_7RegValueEnumAction@@6B@; const RegValueEnumAction::`vftable'
0x14005971b  mov     [rbp+57h+var_28], rax
0x14005971f  jmp     loc_1400595A3
0x140059724  mov     [rbp+57h+var_20], r14
0x140059728  mov     rbx, [rbp+57h+var_18]
0x14005972c  test    rbx, rbx
0x14005972f  jz      short loc_140059759
0x140059731  call    cs:__imp_GetProcessHeap
0x140059738  nop     dword ptr [rax+rax+00h]
0x14005973d  mov     r8, rbx; lpMem
0x140059740  xor     edx, edx; dwFlags
0x140059742  mov     rcx, rax; hHeap
0x140059745  call    cs:__imp_HeapFree
0x14005974c  nop     dword ptr [rax+rax+00h]
0x140059751  mov     [rbp+57h+var_18], 0
0x140059759  lea     rax, ??_7RegValueEnumAction@@6B@; const RegValueEnumAction::`vftable'
0x140059760  mov     [rbp+57h+var_28], rax
0x140059764  mov     [rbp+57h+var_38], r12
0x140059768  mov     rbx, [rbp+57h+lpMem]
0x14005976c  test    rbx, rbx
0x14005976f  jz      short loc_140059791
0x140059771  call    cs:__imp_GetProcessHeap
0x140059778  nop     dword ptr [rax+rax+00h]
0x14005977d  mov     r8, rbx; lpMem
0x140059780  xor     edx, edx; dwFlags
0x140059782  mov     rcx, rax; hHeap
0x140059785  call    cs:__imp_HeapFree
0x14005978c  nop     dword ptr [rax+rax+00h]
0x140059791  xor     eax, eax
0x140059793  lea     r11, [rsp+0A0h+var_10]
0x14005979b  mov     rbx, [r11+20h]
0x14005979f  mov     rsi, [r11+28h]
0x1400597a3  mov     rdi, [r11+30h]
0x1400597a7  mov     rsp, r11
0x1400597aa  pop     r14
0x1400597ac  pop     r12
0x1400597ae  pop     rbp
0x1400597af  retn
```
