# CBdeCfgConsole::ShowDriveInfo(void)

- ea: `0x140003884`
- end: `0x140003f7b`
- name: `?ShowDriveInfo@CBdeCfgConsole@@AEAAJXZ`
- size: `1783`
- prototype: `__int64 __fastcall(CBdeCfgConsole *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x140001fac`

## callees

- `0x140001008`
- `0x1400016f3`
- `0x140001aa4`
- `0x140002898`
- `0x1400031c4`
- `0x1400032b0`
- `0x140003884`
- `0x140003f84`
- `0x140004460`
- `0x140005010`

## import_xrefs

- `BDEHDCFGLIB!?Unload@CBdeCfgLibraryLoader@@QEAAXXZ` at `0x140003f46`
- `BDEHDCFGLIB!?Unload@CBdeCfgLibraryLoader@@QEAAXXZ` at `0x1400048bc`
- `BDEHDCFGLIB!?Unload@CBdeCfgLibraryLoader@@QEAAXXZ` at `0x140003f46`
- `BDEHDCFGLIB!?Unload@CBdeCfgLibraryLoader@@QEAAXXZ` at `0x1400048bc`
- `BDEHDCFGLIB!BdeCfgLogError` at `0x140003f32`
- `BDEHDCFGLIB!BdeCfgLogError` at `0x14000489c`
- `BDEHDCFGLIB!BdeCfgLogError` at `0x140003f32`
- `BDEHDCFGLIB!BdeCfgLogError` at `0x14000489c`
- `BDEHDCFGLIB!BdeCfgCheckAndGetBootVolume` at `0x140003aa8`
- `BDEHDCFGLIB!BdeCfgCheckAndGetBootVolume` at `0x140003aa8`
- `BDEHDCFGLIB!BdeCfgGetVolumeDisk` at `0x140003ad8`
- `BDEHDCFGLIB!BdeCfgGetVolumeDisk` at `0x140003ad8`
- `BDEHDCFGLIB!BdeCfgCanCreateActivePartOnDisk` at `0x140003af1`
- `BDEHDCFGLIB!BdeCfgCanCreateActivePartOnDisk` at `0x140003af1`
- `BDEHDCFGLIB!BdeCfgFindLargestUnallocatedExtent` at `0x140003b1b`
- `BDEHDCFGLIB!BdeCfgFindLargestUnallocatedExtent` at `0x140003b1b`
- `BDEHDCFGLIB!BdeCfgFindCandidateVolumes` at `0x140003b58`
- `BDEHDCFGLIB!BdeCfgFindCandidateVolumes` at `0x140003b58`
- `BDEHDCFGLIB!BdeCfgFindVolumeWithName` at `0x140003d57`
- `BDEHDCFGLIB!BdeCfgFindVolumeWithName` at `0x140003d57`
- `BDEHDCFGLIB!BdeCfgCheckVolumeAsCandidate` at `0x140003d8a`
- `BDEHDCFGLIB!BdeCfgCheckVolumeAsCandidate` at `0x140003d8a`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140003999`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x1400039b7`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x1400039d5`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x1400039f3`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140003a11`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140003a32`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140003a53`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140003a8f`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140003999`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x1400039b7`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x1400039d5`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x1400039f3`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140003a11`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140003a32`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140003a53`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140003a8f`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::ShowDriveInfo(CBdeCfgConsole *this)
{
  char v2; // r13
  char v3; // si
  signed int ResourceString; // ebx
  __int64 v5; // rdx
  CBdeCfgConsole *v6; // rcx
  int LargestUnallocatedExtent; // eax
  int CandidateVolumes; // eax
  unsigned int v9; // r12d
  int v10; // eax
  __int64 v11; // rdx
  unsigned __int16 *v12; // rcx
  bool v13; // sf
  __int64 v14; // r8
  const wchar_t *v15; // r9
  __int64 v16; // rax
  wchar_t v17; // r10
  void *v18; // r15
  __int64 *v19; // rax
  __int64 v21; // [rsp+20h] [rbp-E28h]
  struct IVdsDisk *v22; // [rsp+48h] [rbp-E00h] BYREF
  struct IVdsVolume *v23; // [rsp+50h] [rbp-DF8h] BYREF
  unsigned __int16 *v24; // [rsp+58h] [rbp-DF0h] BYREF
  void *Block; // [rsp+60h] [rbp-DE8h] BYREF
  void *v26; // [rsp+68h] [rbp-DE0h] BYREF
  void *v27; // [rsp+70h] [rbp-DD8h] BYREF
  void *v28; // [rsp+78h] [rbp-DD0h] BYREF
  void *v29; // [rsp+80h] [rbp-DC8h] BYREF
  void *v30; // [rsp+88h] [rbp-DC0h] BYREF
  unsigned __int16 *v31; // [rsp+90h] [rbp-DB8h] BYREF
  void *v32; // [rsp+98h] [rbp-DB0h] BYREF
  unsigned int v33; // [rsp+A0h] [rbp-DA8h]
  void *v34; // [rsp+A8h] [rbp-DA0h]
  unsigned __int16 *v35; // [rsp+B0h] [rbp-D98h]
  __int64 v36; // [rsp+B8h] [rbp-D90h]
  struct IVdsVolume *v37; // [rsp+C0h] [rbp-D88h] BYREF
  unsigned __int64 v38[2]; // [rsp+C8h] [rbp-D80h] BYREF
  unsigned __int64 v39; // [rsp+D8h] [rbp-D70h] BYREF
  const wchar_t *v40; // [rsp+E0h] [rbp-D68h]
  __int64 v41; // [rsp+E8h] [rbp-D60h]
  __int64 v42; // [rsp+F0h] [rbp-D58h]
  _DWORD v43[428]; // [rsp+100h] [rbp-D48h] BYREF
  _BYTE v44[576]; // [rsp+7B0h] [rbp-698h] BYREF
  unsigned __int16 v45[264]; // [rsp+9F0h] [rbp-458h] BYREF
  unsigned __int16 v46[264]; // [rsp+C00h] [rbp-248h] BYREF

  v38[1] = (unsigned __int64)this;
  memset_0(v43, 0, sizeof(v43));
  memset_0(v44, 0, 0x238u);
  v38[0] = 0;
  v39 = 0;
  Block = 0;
  v24 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v23 = 0;
  v22 = 0;
  v37 = 0;
  v2 = 0;
  v3 = 0;
  memset_0(v46, 0, 0x208u);
  memset_0(v45, 0, 0x208u);
  ResourceString = CBdeCfgConsole::Initialize(this);
  if ( ResourceString >= 0 )
  {
    ResourceString = BdeCfgLoadResourceString(0x190u, (unsigned __int16 **)&Block);
    if ( ResourceString >= 0 )
    {
      ResourceString = BdeCfgLoadResourceString(0x191u, &v24);
      if ( ResourceString >= 0 )
      {
        ResourceString = BdeCfgLoadResourceString(0x192u, (unsigned __int16 **)&v26);
        if ( ResourceString >= 0 )
        {
          ResourceString = BdeCfgLoadResourceString(0x193u, (unsigned __int16 **)&v27);
          if ( ResourceString >= 0 )
          {
            ResourceString = BdeCfgLoadResourceString(0x194u, (unsigned __int16 **)&v28);
            if ( ResourceString >= 0 )
            {
              ResourceString = BdeCfgLoadResourceString(0x195u, (unsigned __int16 **)&v29);
              if ( ResourceString >= 0 )
              {
                ResourceString = BdeCfgLoadResourceString(0x196u, (unsigned __int16 **)&v30);
                if ( ResourceString >= 0 )
                {
                  ResourceString = CBdeCfgConsole::BdeCfgpLoadBrandedResourceString(v6, v5, &v31);
                  if ( ResourceString >= 0 )
                  {
                    ResourceString = BdeCfgLoadResourceString(0x198u, (unsigned __int16 **)&v32);
                    if ( ResourceString >= 0 )
                    {
                      ResourceString = BdeCfgCheckAndGetBootVolume(&v23);
                      if ( ResourceString == -1063256060 )
                        ResourceString = -1063256062;
                      if ( ResourceString >= 0 )
                      {
                        ResourceString = BdeCfgGetVolumeDisk(v23, &v22);
                        if ( ResourceString >= 0 )
                        {
                          if ( !BdeCfgCanCreateActivePartOnDisk(v22) )
                          {
                            LargestUnallocatedExtent = BdeCfgFindLargestUnallocatedExtent(
                                                         v22,
                                                         *((_QWORD *)this + 174),
                                                         &v39,
                                                         v38);
                            ResourceString = LargestUnallocatedExtent;
                            if ( LargestUnallocatedExtent < 0 )
                              goto LABEL_56;
                            if ( !LargestUnallocatedExtent )
                              v2 = 1;
                          }
                          CandidateVolumes = BdeCfgFindCandidateVolumes(
                                               v22,
                                               *((_QWORD *)this + 174),
                                               (CBdeCfgConsole *)((char *)this + 1392),
                                               (struct _BDECFG_CANDIDATES *)v43);
                          ResourceString = CandidateVolumes;
                          if ( CandidateVolumes >= 0 )
                          {
                            if ( !CandidateVolumes )
                              v3 = 1;
                            if ( v3 || v2 )
                            {
                              CBdeCfgConsole::PrintConsoleMessage(this, (const unsigned __int16 *)Block);
                              if ( v3 )
                              {
                                v9 = 0;
                                v33 = 0;
                                while ( v9 < v43[0] )
                                {
                                  if ( LOWORD(v43[142 * v9 + 141]) )
                                  {
                                    v10 = StringCchPrintfW(v46, 0x104u, L"%3c:", LOWORD(v43[142 * v9 + 141]));
                                  }
                                  else
                                  {
                                    LODWORD(v21) = v43[142 * v9 + 143];
                                    v10 = StringCchPrintfW(v46, 0x104u, L"%s%u", L"partition", v21);
                                  }
                                  ResourceString = v10;
                                  if ( v10 < 0 )
                                    goto LABEL_56;
                                  v11 = 260;
                                  v12 = v45;
                                  if ( v43[142 * v9 + 2] )
                                  {
                                    ResourceString = StringCchPrintfW(
                                                       v45,
                                                       0x104u,
                                                       L"%u",
                                                       (unsigned __int64)(*(_QWORD *)&v43[142 * v9 + 138] + 0xFFFFFLL) >> 20);
                                    v13 = ResourceString < 0;
                                  }
                                  else
                                  {
                                    v14 = 2147483646;
                                    v42 = 2147483646;
                                    v15 = L"---";
                                    v40 = L"---";
                                    v41 = 260;
                                    v35 = v45;
                                    ResourceString = 0;
                                    v16 = 0;
                                    v36 = 0;
                                    while ( v11 )
                                    {
                                      if ( !v14 )
                                        goto LABEL_41;
                                      v17 = *v15;
                                      if ( !*v15 )
                                        goto LABEL_41;
                                      v40 = ++v15;
                                      *v12++ = v17;
                                      v35 = v12;
                                      v41 = --v11;
                                      v42 = --v14;
                                      v36 = ++v16;
                                    }
                                    v35 = --v12;
                                    v36 = v16 - 1;
                                    ResourceString = -2147024774;
LABEL_41:
                                    *v12 = 0;
                                    v13 = ResourceString < 0;
                                  }
                                  if ( v13 )
                                    goto LABEL_56;
                                  v34 = 0;
                                  if ( v43[142 * v9 + 2] )
                                  {
                                    v18 = v27;
                                    v34 = v27;
                                    ResourceString = BdeCfgFindVolumeWithName(
                                                       (const unsigned __int16 *)&v43[142 * v9 + 4],
                                                       &v37);
                                    if ( !ResourceString )
                                    {
                                      if ( (int)BdeCfgCheckVolumeAsCandidate(
                                                  v37,
                                                  0,
                                                  (CBdeCfgConsole *)((char *)this + 1392),
                                                  1u,
                                                  (struct _BDECFG_CANDIDATE *)v44) >= 0 )
                                        v18 = v29;
                                      v34 = v18;
                                      ResourceString = 0;
                                    }
                                  }
                                  else
                                  {
                                    v18 = v28;
                                    v34 = v28;
                                  }
                                  if ( (v43[142 * v9 + 140] & 2) != 0 )
                                  {
                                    v19 = (__int64 *)v31;
                                  }
                                  else
                                  {
                                    v19 = &qword_140006840;
                                    if ( v43[142 * v9 + 3] )
                                      v19 = (__int64 *)v30;
                                  }
                                  CBdeCfgConsole::PrintConsoleMessage(
                                    this,
                                    v24,
                                    v46,
                                    (unsigned __int64)(*(_QWORD *)&v43[142 * v9++ + 134] + 0xFFFFFLL) >> 20,
                                    v18,
                                    v45,
                                    v19);
                                  v33 = v9;
                                }
                              }
                              if ( v2 )
                                CBdeCfgConsole::PrintConsoleMessage(
                                  this,
                                  v24,
                                  v26,
                                  (v38[0] + 0xFFFFF) >> 20,
                                  L"---",
                                  L"---",
                                  v32);
                            }
                            else
                            {
                              ResourceString = -1063256057;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_56:
  operator delete(Block);
  operator delete(v24);
  operator delete(v26);
  operator delete(v27);
  operator delete(v28);
  operator delete(v29);
  operator delete(v30);
  operator delete(v31);
  operator delete(v32);
  if ( v23 )
  {
    ((void (__fastcall *)(struct IVdsVolume *))v23->lpVtbl->Release)(v23);
    v23 = 0;
  }
  if ( v22 )
  {
    ((void (__fastcall *)(struct IVdsDisk *))v22->lpVtbl->Release)(v22);
    v22 = 0;
  }
  if ( ResourceString < 0 )
  {
    BdeCfgLogError(1, (unsigned int)ResourceString);
    CBdeCfgConsole::PrintConsoleMessage(this, ResourceString);
  }
  CBdeCfgLibraryLoader::Unload((CBdeCfgConsole *)((char *)this + 8));
  return (unsigned int)ResourceString;
}

```

## disassembly

```asm
0x140003884  mov     [rsp+arg_8], rbx
0x140003889  mov     [rsp+arg_10], rsi
0x14000388e  push    rdi
0x14000388f  push    r12
0x140003891  push    r13
0x140003893  push    r14
0x140003895  push    r15
0x140003897  sub     rsp, 0E20h
0x14000389e  mov     rax, cs:__security_cookie
0x1400038a5  xor     rax, rsp
0x1400038a8  mov     [rsp+0E48h+var_38], rax
0x1400038b0  mov     r14, rcx
0x1400038b3  mov     [rsp+0E48h+var_D78], rcx
0x1400038bb  xor     r15d, r15d
0x1400038be  mov     [rsp+0E48h+var_E08], r15d
0x1400038c3  xor     edx, edx; Val
0x1400038c5  mov     r8d, 6B0h; Size
0x1400038cb  lea     rcx, [rsp+0E48h+var_D48]; void *
0x1400038d3  call    memset_0
0x1400038d8  xor     edx, edx; Val
0x1400038da  mov     r8d, 238h; Size
0x1400038e0  lea     rcx, [rsp+0E48h+var_698]; void *
0x1400038e8  call    memset_0
0x1400038ed  mov     [rsp+0E48h+var_D80], r15
0x1400038f5  mov     [rsp+0E48h+var_D70], r15
0x1400038fd  mov     [rsp+0E48h+Block], r15
0x140003902  mov     [rsp+0E48h+var_DF0], r15
0x140003907  mov     [rsp+0E48h+var_DE0], r15
0x14000390c  mov     [rsp+0E48h+var_DD8], r15
0x140003911  mov     [rsp+0E48h+var_DD0], r15
0x140003916  mov     [rsp+0E48h+var_DC8], r15
0x14000391e  mov     [rsp+0E48h+var_DC0], r15
0x140003926  mov     [rsp+0E48h+var_DB8], r15
0x14000392e  mov     [rsp+0E48h+var_DB0], r15
0x140003936  mov     [rsp+0E48h+var_DF8], r15
0x14000393b  mov     [rsp+0E48h+var_E00], r15
0x140003940  mov     [rsp+0E48h+var_D88], r15
0x140003948  movzx   r13d, r15b
0x14000394c  mov     sil, r15b
0x14000394f  mov     ebx, 208h
0x140003954  mov     r8d, ebx; Size
0x140003957  xor     edx, edx; Val
0x140003959  lea     rcx, [rsp+0E48h+var_248]; void *
0x140003961  call    memset_0
0x140003966  mov     r8d, ebx; Size
0x140003969  xor     edx, edx; Val
0x14000396b  lea     rcx, [rsp+0E48h+var_458]; void *
0x140003973  call    memset_0
0x140003978  nop
0x140003979  mov     rcx, r14; this
0x14000397c  call    ?Initialize@CBdeCfgConsole@@QEAAJXZ; CBdeCfgConsole::Initialize(void)
0x140003981  mov     ebx, eax
0x140003983  mov     [rsp+0E48h+var_E08], eax
0x140003987  test    eax, eax
0x140003989  js      loc_140003E84
0x14000398f  lea     rdx, [rsp+0E48h+Block]
0x140003994  mov     ecx, 190h
0x140003999  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x14000399f  mov     ebx, eax
0x1400039a1  mov     [rsp+0E48h+var_E08], eax
0x1400039a5  test    eax, eax
0x1400039a7  js      loc_140003E84
0x1400039ad  lea     rdx, [rsp+0E48h+var_DF0]
0x1400039b2  mov     ecx, 191h
0x1400039b7  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x1400039bd  mov     ebx, eax
0x1400039bf  mov     [rsp+0E48h+var_E08], eax
0x1400039c3  test    eax, eax
0x1400039c5  js      loc_140003E84
0x1400039cb  lea     rdx, [rsp+0E48h+var_DE0]
0x1400039d0  mov     ecx, 192h
0x1400039d5  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x1400039db  mov     ebx, eax
0x1400039dd  mov     [rsp+0E48h+var_E08], eax
0x1400039e1  test    eax, eax
0x1400039e3  js      loc_140003E84
0x1400039e9  lea     rdx, [rsp+0E48h+var_DD8]
0x1400039ee  mov     ecx, 193h
0x1400039f3  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x1400039f9  mov     ebx, eax
0x1400039fb  mov     [rsp+0E48h+var_E08], eax
0x1400039ff  test    eax, eax
0x140003a01  js      loc_140003E84
0x140003a07  lea     rdx, [rsp+0E48h+var_DD0]
0x140003a0c  mov     ecx, 194h
0x140003a11  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x140003a17  mov     ebx, eax
0x140003a19  mov     [rsp+0E48h+var_E08], eax
0x140003a1d  test    eax, eax
0x140003a1f  js      loc_140003E84
0x140003a25  lea     rdx, [rsp+0E48h+var_DC8]
0x140003a2d  mov     ecx, 195h
0x140003a32  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x140003a38  mov     ebx, eax
0x140003a3a  mov     [rsp+0E48h+var_E08], eax
0x140003a3e  test    eax, eax
0x140003a40  js      loc_140003E84
0x140003a46  lea     rdx, [rsp+0E48h+var_DC0]
0x140003a4e  mov     ecx, 196h
0x140003a53  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x140003a59  mov     ebx, eax
0x140003a5b  mov     [rsp+0E48h+var_E08], eax
0x140003a5f  test    eax, eax
0x140003a61  js      loc_140003E84
0x140003a67  lea     r8, [rsp+0E48h+var_DB8]; unsigned __int16 **
0x140003a6f  call    ?BdeCfgpLoadBrandedResourceString@CBdeCfgConsole@@AEAAJIPEAPEAG@Z; CBdeCfgConsole::BdeCfgpLoadBrandedResourceString(uint,ushort * *)
0x140003a74  mov     ebx, eax
0x140003a76  mov     [rsp+0E48h+var_E08], eax
0x140003a7a  test    eax, eax
0x140003a7c  js      loc_140003E84
0x140003a82  lea     rdx, [rsp+0E48h+var_DB0]
0x140003a8a  mov     ecx, 198h
0x140003a8f  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x140003a95  mov     ebx, eax
0x140003a97  mov     [rsp+0E48h+var_E08], eax
0x140003a9b  test    eax, eax
0x140003a9d  js      loc_140003E84
0x140003aa3  lea     rcx, [rsp+0E48h+var_DF8]
0x140003aa8  call    cs:__imp_?BdeCfgCheckAndGetBootVolume@@YAJPEAPEAUIVdsVolume@@@Z; BdeCfgCheckAndGetBootVolume(IVdsVolume * *)
0x140003aae  mov     ebx, eax
0x140003ab0  mov     [rsp+0E48h+var_E08], eax
0x140003ab4  mov     eax, 0C0A00002h
0x140003ab9  cmp     ebx, 0C0A00004h
0x140003abf  cmovz   ebx, eax
0x140003ac2  mov     [rsp+0E48h+var_E08], ebx
0x140003ac6  test    ebx, ebx
0x140003ac8  js      loc_140003E84
0x140003ace  lea     rdx, [rsp+0E48h+var_E00]
0x140003ad3  mov     rcx, [rsp+0E48h+var_DF8]
0x140003ad8  call    cs:__imp_?BdeCfgGetVolumeDisk@@YAJPEAUIVdsVolume@@PEAPEAUIVdsDisk@@@Z; BdeCfgGetVolumeDisk(IVdsVolume *,IVdsDisk * *)
0x140003ade  mov     ebx, eax
0x140003ae0  mov     [rsp+0E48h+var_E08], eax
0x140003ae4  test    eax, eax
0x140003ae6  js      loc_140003E84
0x140003aec  mov     rcx, [rsp+0E48h+var_E00]
0x140003af1  call    cs:__imp_?BdeCfgCanCreateActivePartOnDisk@@YAJPEAUIVdsDisk@@@Z; BdeCfgCanCreateActivePartOnDisk(IVdsDisk *)
0x140003af7  mov     [rsp+0E48h+var_E08], eax
0x140003afb  test    eax, eax
0x140003afd  jnz     short loc_140003B39
0x140003aff  lea     r9, [rsp+0E48h+var_D80]
0x140003b07  lea     r8, [rsp+0E48h+var_D70]
0x140003b0f  mov     rdx, [r14+570h]
0x140003b16  mov     rcx, [rsp+0E48h+var_E00]
0x140003b1b  call    cs:__imp_?BdeCfgFindLargestUnallocatedExtent@@YAJPEAUIVdsDisk@@_KPEA_K2@Z; BdeCfgFindLargestUnallocatedExtent(IVdsDisk *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x140003b21  mov     ebx, eax
0x140003b23  mov     [rsp+0E48h+var_E08], eax
0x140003b27  test    eax, eax
0x140003b29  js      loc_140003E84
0x140003b2f  lea     edi, [r15+1]
0x140003b33  cmovz   r13d, edi
0x140003b37  jmp     short loc_140003B3E
0x140003b39  mov     edi, 1
0x140003b3e  lea     rax, [r14+570h]
0x140003b45  lea     r9, [rsp+0E48h+var_D48]
0x140003b4d  mov     r8, rax
0x140003b50  mov     rdx, [rax]
0x140003b53  mov     rcx, [rsp+0E48h+var_E00]
0x140003b58  call    cs:__imp_?BdeCfgFindCandidateVolumes@@YAJPEAUIVdsDisk@@_KQEAU_BDECFG_SIZE_REQUIREMENTS@@PEAU_BDECFG_CANDIDATES@@@Z; BdeCfgFindCandidateVolumes(IVdsDisk *,unsigned __int64,_BDECFG_SIZE_REQUIREMENTS * const,_BDECFG_CANDIDATES *)
0x140003b5e  mov     ebx, eax
0x140003b60  mov     [rsp+0E48h+var_E08], eax
0x140003b64  test    eax, eax
0x140003b66  js      loc_140003E8E
0x140003b6c  cmovz   esi, edi
0x140003b6f  test    sil, sil
0x140003b72  jnz     short loc_140003B87
0x140003b74  test    r13b, r13b
0x140003b77  jnz     short loc_140003B87
0x140003b79  mov     ebx, 0C0A00007h
0x140003b7e  mov     [rsp+0E48h+var_E08], ebx
0x140003b82  jmp     loc_140003E8E
0x140003b87  mov     rdx, [rsp+0E48h+Block]; unsigned __int16 *
0x140003b8c  mov     rcx, r14; this
0x140003b8f  call    ?PrintConsoleMessage@CBdeCfgConsole@@AEAAJPEBGZZ; CBdeCfgConsole::PrintConsoleMessage(ushort const *,...)
0x140003b94  test    sil, sil
0x140003b97  jz      loc_140003E3A
0x140003b9d  mov     r12d, r15d
0x140003ba0  mov     [rsp+0E48h+var_DA8], r15d
0x140003ba8  lea     r15, asc_140006750; "---"
0x140003baf  cmp     r12d, [rsp+0E48h+var_D48]
0x140003bb7  jnb     loc_140003E41
0x140003bbd  mov     eax, r12d
0x140003bc0  imul    rsi, rax, 238h
0x140003bc7  movzx   eax, [rsp+rsi+0E48h+var_B14]
0x140003bcf  mov     edx, 104h; unsigned __int64
0x140003bd4  lea     rcx, [rsp+0E48h+var_248]; unsigned __int16 *
0x140003bdc  test    ax, ax
0x140003bdf  jz      short loc_140003BF2
0x140003be1  mov     r9d, eax
0x140003be4  lea     r8, a3c; "%3c:"
0x140003beb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003bf0  jmp     short loc_140003C10
0x140003bf2  mov     eax, [rsp+rsi+0E48h+var_B0C]
0x140003bf9  mov     dword ptr [rsp+0E48h+var_E28], eax
0x140003bfd  lea     r9, aPartition; "partition"
0x140003c04  lea     r8, aSU; "%s%u"
0x140003c0b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003c10  mov     ebx, eax
0x140003c12  xor     eax, eax
0x140003c14  test    ebx, ebx
0x140003c16  mov     [rsp+0E48h+var_E08], ebx
0x140003c1a  js      loc_140003E8B
0x140003c20  mov     edx, 104h; unsigned __int64
0x140003c25  lea     rcx, [rsp+0E48h+var_458]; unsigned __int16 *
0x140003c2d  cmp     [rsp+rsi+0E48h+var_D40], eax
0x140003c34  jz      short loc_140003C65
0x140003c36  mov     r9, [rsp+rsi+0E48h+var_B20]
0x140003c3e  add     r9, 0FFFFFh
0x140003c45  shr     r9, 14h
0x140003c49  lea     r8, aU; "%u"
0x140003c50  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003c55  mov     ebx, eax
0x140003c57  mov     [rsp+0E48h+var_E08], eax
0x140003c5b  xor     r15d, r15d
0x140003c5e  test    eax, eax
0x140003c60  jmp     loc_140003D1F
0x140003c65  mov     r8d, 7FFFFFFEh
0x140003c6b  mov     [rsp+0E48h+var_D58], r8
0x140003c73  mov     r9, r15
0x140003c76  mov     [rsp+0E48h+var_D68], r15
0x140003c7e  mov     [rsp+0E48h+var_D60], rdx
0x140003c86  mov     [rsp+0E48h+var_D98], rcx
0x140003c8e  xor     r15d, r15d
0x140003c91  mov     ebx, r15d
0x140003c94  mov     eax, r15d
0x140003c97  mov     [rsp+0E48h+var_D90], rax
0x140003c9f  test    rdx, rdx
0x140003ca2  jz      short loc_140003CF7
0x140003ca4  test    r8, r8
0x140003ca7  jz      short loc_140003CF2
0x140003ca9  movzx   r10d, word ptr [r9]
0x140003cad  test    r10w, r10w
0x140003cb1  jz      short loc_140003CF2
0x140003cb3  add     r9, 2
0x140003cb7  mov     [rsp+0E48h+var_D68], r9
0x140003cbf  mov     [rcx], r10w
0x140003cc3  add     rcx, 2
0x140003cc7  mov     [rsp+0E48h+var_D98], rcx
0x140003ccf  sub     rdx, rdi
0x140003cd2  mov     [rsp+0E48h+var_D60], rdx
0x140003cda  sub     r8, rdi
0x140003cdd  mov     [rsp+0E48h+var_D58], r8
0x140003ce5  add     rax, rdi
0x140003ce8  mov     [rsp+0E48h+var_D90], rax
0x140003cf0  jmp     short loc_140003C9F
0x140003cf2  test    rdx, rdx
0x140003cf5  jnz     short loc_140003D13
0x140003cf7  sub     rcx, 2
0x140003cfb  mov     [rsp+0E48h+var_D98], rcx
0x140003d03  sub     rax, rdi
0x140003d06  mov     [rsp+0E48h+var_D90], rax
0x140003d0e  mov     ebx, 8007007Ah
0x140003d13  mov     eax, r15d
0x140003d16  mov     [rcx], ax
0x140003d19  mov     [rsp+0E48h+var_E08], ebx
0x140003d1d  test    ebx, ebx
0x140003d1f  js      loc_140003E8E
0x140003d25  mov     [rsp+0E48h+var_DA0], r15
0x140003d2d  cmp     [rsp+rsi+0E48h+var_D40], r15d
0x140003d35  jz      short loc_140003DB1
0x140003d37  mov     r15, [rsp+0E48h+var_DD8]
0x140003d3c  mov     [rsp+0E48h+var_DA0], r15
0x140003d44  lea     rcx, [rsp+0E48h+var_D38]
0x140003d4c  add     rcx, rsi
0x140003d4f  lea     rdx, [rsp+0E48h+var_D88]
0x140003d57  call    cs:__imp_?BdeCfgFindVolumeWithName@@YAJPEBGPEAPEAUIVdsVolume@@@Z; BdeCfgFindVolumeWithName(ushort const *,IVdsVolume * *)
0x140003d5d  mov     ebx, eax
0x140003d5f  mov     [rsp+0E48h+var_E08], eax
0x140003d63  xor     ecx, ecx
0x140003d65  test    eax, eax
0x140003d67  jnz     short loc_140003DC0
0x140003d69  lea     rax, [rsp+0E48h+var_698]
0x140003d71  mov     [rsp+0E48h+var_E28], rax
0x140003d76  mov     r9d, edi
0x140003d79  lea     r8, [r14+570h]
0x140003d80  xor     edx, edx
0x140003d82  mov     rcx, [rsp+0E48h+var_D88]
0x140003d8a  call    cs:__imp_?BdeCfgCheckVolumeAsCandidate@@YAJPEAUIVdsVolume@@_KQEAU_BDECFG_SIZE_REQUIREMENTS@@KPEAU_BDECFG_CANDIDATE@@@Z; BdeCfgCheckVolumeAsCandidate(IVdsVolume *,unsigned __int64,_BDECFG_SIZE_REQUIREMENTS * const,ulong,_BDECFG_CANDIDATE *)
0x140003d90  mov     [rsp+0E48h+var_E08], eax
0x140003d94  xor     ecx, ecx
0x140003d96  test    eax, eax
0x140003d98  cmovns  r15, [rsp+0E48h+var_DC8]
0x140003da1  mov     [rsp+0E48h+var_DA0], r15
0x140003da9  mov     ebx, ecx
0x140003dab  mov     [rsp+0E48h+var_E08], ecx
0x140003daf  jmp     short loc_140003DC0
0x140003db1  mov     r15, [rsp+0E48h+var_DD0]
0x140003db6  mov     [rsp+0E48h+var_DA0], r15
0x140003dbe  xor     ecx, ecx
0x140003dc0  test    [rsp+rsi+0E48h+var_B18], 2
0x140003dc8  jz      short loc_140003DD4
0x140003dca  mov     rax, [rsp+0E48h+var_DB8]
0x140003dd2  jmp     short loc_140003DEB
0x140003dd4  lea     rax, qword_140006840
0x140003ddb  cmp     [rsp+rsi+0E48h+var_D3C], ecx
0x140003de2  cmovnz  rax, [rsp+0E48h+var_DC0]
0x140003deb  mov     r9, [rsp+rsi+0E48h+var_B30]
0x140003df3  add     r9, 0FFFFFh
0x140003dfa  shr     r9, 14h
0x140003dfe  mov     [rsp+0E48h+var_E18], rax
0x140003e03  lea     rax, [rsp+0E48h+var_458]
  ... truncated ...
```
