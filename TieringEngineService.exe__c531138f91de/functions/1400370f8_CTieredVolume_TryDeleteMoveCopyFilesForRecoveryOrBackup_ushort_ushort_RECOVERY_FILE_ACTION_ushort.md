# CTieredVolume::TryDeleteMoveCopyFilesForRecoveryOrBackup(ushort *,ushort *,RECOVERY_FILE_ACTION,ushort *)

- ea: `0x1400370f8`
- end: `0x1400374df`
- name: `?TryDeleteMoveCopyFilesForRecoveryOrBackup@CTieredVolume@@QEAAXPEAG0W4RECOVERY_FILE_ACTION@@0@Z`
- size: `999`
- prototype: `int __fastcall(__int64, __int64, __int64, unsigned int, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x14001a270`
- `0x14001b328`
- `0x140036390`
- `0x14003695c`

## callees

- `0x140002323`
- `0x140002db0`
- `0x140009af0`
- `0x140009c08`
- `0x1400163c0`
- `0x140017cd4`
- `0x140017e78`
- `0x140036aa8`
- `0x1400370f8`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003732f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003732f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400373cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400373e2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400373cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400373e2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140037320`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140037320`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1400373aa`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1400373aa`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14003742a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14003742a`

## pseudocode

```c
int __fastcall CTieredVolume::TryDeleteMoveCopyFilesForRecoveryOrBackup(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  __int64 v9; // r9
  _WORD *v10; // rax
  __int64 v11; // rdx
  unsigned int v12; // r8d
  __int64 v13; // r10
  __int64 v14; // rdx
  unsigned __int16 *v15; // rax
  unsigned int v16; // r8d
  _UNKNOWN **v17; // rax
  __int64 v18; // rax
  WCHAR *v19; // rdx
  WCHAR *v20; // rcx
  WCHAR *v21; // rcx
  _QWORD *v22; // rcx
  int v23; // edx
  int v24; // eax
  HANDLE FirstFileW; // rsi
  DWORD LastError; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-4A8h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp-258h] BYREF

  if ( !a2 )
  {
    LOBYTE(v12) = 87;
    goto LABEL_58;
  }
  v9 = 260;
  v10 = (_WORD *)a2;
  v11 = 260;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v11;
  }
  while ( v11 );
  v12 = v11 == 0 ? 0x80070057 : 0;
  if ( !v11 )
  {
LABEL_58:
    v17 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LODWORD(v17) = WPP_SF_Sd(
                       *((_QWORD *)WPP_GLOBAL_Control + 2),
                       25,
                       (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids,
                       a2,
                       v12);
    }
    return (int)v17;
  }
  v13 = (2 * (260 - v11)) & -(__int64)(v11 != 0);
  if ( !a5 )
  {
    LOBYTE(v16) = 87;
LABEL_52:
    v22 = WPP_GLOBAL_Control;
    v17 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (int)v17;
    }
    v23 = 26;
LABEL_56:
    LODWORD(v17) = WPP_SF_SSd(
                     v22[2],
                     v23,
                     (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids,
                     (_DWORD)a5,
                     a2,
                     v16);
    return (int)v17;
  }
  v14 = 260;
  v15 = a5;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  v16 = v14 == 0 ? 0x80070057 : 0;
  if ( !v14 )
    goto LABEL_52;
  if ( v13 + ((2 * (260 - v14)) & (unsigned __int64)-(__int64)(v14 != 0)) >= 0x206 )
  {
    v17 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LODWORD(v17) = WPP_SF_SS(
                       *((_QWORD *)WPP_GLOBAL_Control + 2),
                       27,
                       (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids,
                       (_DWORD)a5,
                       a2);
    }
    return (int)v17;
  }
  v18 = 2147483646;
  v19 = FileName;
  v20 = (WCHAR *)a2;
  do
  {
    if ( !v18 )
      break;
    if ( !*v20 )
      break;
    *v19++ = *v20++;
    --v18;
    --v9;
  }
  while ( v9 );
  v21 = v19 - 1;
  v16 = v9 == 0 ? 0x8007007A : 0;
  if ( v9 )
    v21 = v19;
  *v21 = 0;
  if ( !v9 )
  {
    v22 = WPP_GLOBAL_Control;
    v17 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (int)v17;
    }
    v23 = 28;
    goto LABEL_56;
  }
  v24 = StringCbCatW(FileName, (unsigned __int64)v19, a5);
  LOBYTE(v16) = v24;
  if ( v24 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    v17 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (int)v17;
    }
    v23 = 29;
    goto LABEL_56;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    LOBYTE(v16) = ATL::AtlHresultFromWin32(LastError);
    v22 = WPP_GLOBAL_Control;
    v17 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (int)v17;
    }
    v23 = 30;
    goto LABEL_56;
  }
  while ( 1 )
  {
    if ( FindFileData.cFileName[0] != 46 || FindFileData.cFileName[1] != 46 && FindFileData.cFileName[1] )
      TryDeleteMoveCopyFileForRecoveryOrBackup(a2, a3, a4, FindFileData.cFileName);
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      break;
    if ( *(_BYTE *)(a1 + 165)
      || *(_BYTE *)(a1 + 166)
      || WaitForSingleObject(*(HANDLE *)(a1 + 768), 0) != 258
      || WaitForSingleObject(*(HANDLE *)(a1 + 760), 0) != 258 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, a1 + 672);
      }
      break;
    }
  }
  LODWORD(v17) = FindClose(FirstFileW);
  return (int)v17;
}

```

## disassembly

```asm
0x1400370f8  push    rbx
0x1400370fa  push    rbp
0x1400370fb  push    rsi
0x1400370fc  push    rdi
0x1400370fd  push    r12
0x1400370ff  push    r14
0x140037101  push    r15
0x140037103  sub     rsp, 4A0h
0x14003710a  mov     rax, cs:__security_cookie
0x140037111  xor     rax, rsp
0x140037114  mov     [rsp+4D8h+var_48], rax
0x14003711c  mov     rdi, [rsp+4D8h+arg_20]
0x140037124  xor     r12d, r12d
0x140037127  mov     r15d, r9d
0x14003712a  mov     r14, r8
0x14003712d  mov     rbx, rdx
0x140037130  mov     rbp, rcx
0x140037133  test    rdx, rdx
0x140037136  jz      loc_14003747B
0x14003713c  mov     r9d, 104h
0x140037142  mov     rax, rbx
0x140037145  mov     edx, r9d
0x140037148  cmp     [rax], r12w
0x14003714c  jz      short loc_140037158
0x14003714e  add     rax, 2
0x140037152  sub     rdx, 1
0x140037156  jnz     short loc_140037148
0x140037158  mov     rax, rdx
0x14003715b  mov     ecx, 80070057h
0x140037160  neg     rax
0x140037163  sbb     r8d, r8d
0x140037166  not     r8d
0x140037169  and     r8d, ecx
0x14003716c  test    rdx, rdx
0x14003716f  jz      loc_140037481
0x140037175  mov     rax, r9
0x140037178  sub     rax, rdx
0x14003717b  add     rax, rax
0x14003717e  neg     rdx
0x140037181  sbb     r10, r10
0x140037184  and     r10, rax
0x140037187  test    rdi, rdi
0x14003718a  jz      loc_140037435
0x140037190  mov     rdx, r9
0x140037193  mov     rax, rdi
0x140037196  cmp     [rax], r12w
0x14003719a  jz      short loc_1400371A6
0x14003719c  add     rax, 2
0x1400371a0  sub     rdx, 1
0x1400371a4  jnz     short loc_140037196
0x1400371a6  mov     rax, rdx
0x1400371a9  neg     rax
0x1400371ac  sbb     r8d, r8d
0x1400371af  not     r8d
0x1400371b2  and     r8d, ecx
0x1400371b5  test    rdx, rdx
0x1400371b8  jz      loc_140037438
0x1400371be  mov     rcx, r9
0x1400371c1  sub     rcx, rdx
0x1400371c4  add     rcx, rcx
0x1400371c7  neg     rdx
0x1400371ca  sbb     rax, rax
0x1400371cd  and     rax, rcx
0x1400371d0  add     rax, r10
0x1400371d3  cmp     rax, 206h
0x1400371d9  jb      short loc_140037228
0x1400371db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400371e2  lea     rax, WPP_GLOBAL_Control
0x1400371e9  cmp     rcx, rax
0x1400371ec  jz      loc_1400374BD
0x1400371f2  test    byte ptr [rcx+1Ch], 1
0x1400371f6  jz      loc_1400374BD
0x1400371fc  cmp     byte ptr [rcx+19h], 2
0x140037200  jb      loc_1400374BD
0x140037206  mov     rcx, [rcx+10h]
0x14003720a  lea     r8, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids
0x140037211  mov     edx, 1Bh
0x140037216  mov     [rsp+4D8h+var_4B8], rbx
0x14003721b  mov     r9, rdi
0x14003721e  call    WPP_SF_SS
0x140037223  jmp     loc_1400374BD
0x140037228  mov     eax, 7FFFFFFEh
0x14003722d  lea     rdx, [rsp+4D8h+FileName]
0x140037235  mov     rcx, rbx
0x140037238  test    rax, rax
0x14003723b  jz      short loc_14003725C
0x14003723d  movzx   r8d, word ptr [rcx]
0x140037241  test    r8w, r8w
0x140037245  jz      short loc_14003725C
0x140037247  mov     [rdx], r8w
0x14003724b  add     rcx, 2
0x14003724f  add     rdx, 2; unsigned __int64
0x140037253  dec     rax
0x140037256  sub     r9, 1
0x14003725a  jnz     short loc_140037238
0x14003725c  mov     rax, r9
0x14003725f  lea     rcx, [rdx-2]
0x140037263  neg     rax
0x140037266  sbb     r8d, r8d
0x140037269  not     r8d
0x14003726c  and     r8d, 8007007Ah
0x140037273  test    r9, r9
0x140037276  cmovnz  rcx, rdx
0x14003727a  mov     [rcx], r12w
0x14003727e  jnz     short loc_1400372B5
0x140037280  mov     rcx, cs:WPP_GLOBAL_Control
0x140037287  lea     rax, WPP_GLOBAL_Control
0x14003728e  cmp     rcx, rax
0x140037291  jz      loc_1400374BD
0x140037297  test    byte ptr [rcx+1Ch], 1
0x14003729b  jz      loc_1400374BD
0x1400372a1  cmp     byte ptr [rcx+19h], 2
0x1400372a5  jb      loc_1400374BD
0x1400372ab  mov     edx, 1Ch
0x1400372b0  jmp     loc_14003745C
0x1400372b5  mov     r8, rdi; unsigned __int16 *
0x1400372b8  lea     rcx, [rsp+4D8h+FileName]; unsigned __int16 *
0x1400372c0  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1400372c5  mov     r8d, eax
0x1400372c8  test    eax, eax
0x1400372ca  jns     short loc_140037301
0x1400372cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400372d3  lea     rax, WPP_GLOBAL_Control
0x1400372da  cmp     rcx, rax
0x1400372dd  jz      loc_1400374BD
0x1400372e3  test    byte ptr [rcx+1Ch], 1
0x1400372e7  jz      loc_1400374BD
0x1400372ed  cmp     byte ptr [rcx+19h], 2
0x1400372f1  jb      loc_1400374BD
0x1400372f7  mov     edx, 1Dh
0x1400372fc  jmp     loc_14003745C
0x140037301  xor     edx, edx; Val
0x140037303  lea     rcx, [rsp+4D8h+FindFileData]; void *
0x140037308  mov     r8d, 250h; Size
0x14003730e  call    memset_0
0x140037313  lea     rdx, [rsp+4D8h+FindFileData]; lpFindFileData
0x140037318  lea     rcx, [rsp+4D8h+FileName]; lpFileName
0x140037320  call    cs:__imp_FindFirstFileW
0x140037326  mov     rsi, rax
0x140037329  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14003732d  jnz     short loc_140037372
0x14003732f  call    cs:__imp_GetLastError
0x140037335  mov     ecx, eax; unsigned int
0x140037337  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14003733c  mov     r8d, eax
0x14003733f  mov     rcx, cs:WPP_GLOBAL_Control
0x140037346  lea     rax, WPP_GLOBAL_Control
0x14003734d  cmp     rcx, rax
0x140037350  jz      loc_1400374BD
0x140037356  test    byte ptr [rcx+1Ch], 1
0x14003735a  jz      loc_1400374BD
0x140037360  cmp     byte ptr [rcx+19h], 2
0x140037364  jb      loc_1400374BD
0x14003736a  lea     edx, [rsi+1Fh]
0x14003736d  jmp     loc_14003745C
0x140037372  mov     edi, 102h
0x140037377  cmp     [rsp+4D8h+FindFileData.cFileName], 2Eh ; '.'
0x14003737d  jnz     short loc_14003738F
0x14003737f  movzx   eax, [rsp+4D8h+FindFileData.cFileName+2]
0x140037384  cmp     ax, 2Eh ; '.'
0x140037388  jz      short loc_1400373A2
0x14003738a  test    ax, ax
0x14003738d  jz      short loc_1400373A2
0x14003738f  lea     r9, [rsp+4D8h+FindFileData.cFileName]
0x140037394  mov     r8d, r15d
0x140037397  mov     rdx, r14
0x14003739a  mov     rcx, rbx
0x14003739d  call    ?TryDeleteMoveCopyFileForRecoveryOrBackup@@YAXPEAG0W4RECOVERY_FILE_ACTION@@0@Z; TryDeleteMoveCopyFileForRecoveryOrBackup(ushort *,ushort *,RECOVERY_FILE_ACTION,ushort *)
0x1400373a2  lea     rdx, [rsp+4D8h+FindFileData]; lpFindFileData
0x1400373a7  mov     rcx, rsi; hFindFile
0x1400373aa  call    cs:__imp_FindNextFileW
0x1400373b0  test    eax, eax
0x1400373b2  jz      short loc_140037427
0x1400373b4  cmp     [rbp+0A5h], r12b
0x1400373bb  jnz     short loc_1400373EC
0x1400373bd  cmp     [rbp+0A6h], r12b
0x1400373c4  jnz     short loc_1400373EC
0x1400373c6  mov     rcx, [rbp+300h]; hHandle
0x1400373cd  xor     edx, edx; dwMilliseconds
0x1400373cf  call    cs:__imp_WaitForSingleObject
0x1400373d5  cmp     eax, edi
0x1400373d7  jnz     short loc_1400373EC
0x1400373d9  mov     rcx, [rbp+2F8h]; hHandle
0x1400373e0  xor     edx, edx; dwMilliseconds
0x1400373e2  call    cs:__imp_WaitForSingleObject
0x1400373e8  cmp     eax, edi
0x1400373ea  jz      short loc_140037377
0x1400373ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400373f3  lea     rax, WPP_GLOBAL_Control
0x1400373fa  cmp     rcx, rax
0x1400373fd  jz      short loc_140037427
0x1400373ff  test    byte ptr [rcx+1Ch], 1
0x140037403  jz      short loc_140037427
0x140037405  cmp     byte ptr [rcx+19h], 5
0x140037409  jb      short loc_140037427
0x14003740b  mov     rcx, [rcx+10h]
0x14003740f  lea     r9, [rbp+2A0h]
0x140037416  mov     edx, 0FCh
0x14003741b  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140037422  call    WPP_SF_Z
0x140037427  mov     rcx, rsi; hFindFile
0x14003742a  call    cs:__imp_FindClose
0x140037430  jmp     loc_1400374BD
0x140037435  mov     r8d, ecx
0x140037438  mov     rcx, cs:WPP_GLOBAL_Control
0x14003743f  lea     rax, WPP_GLOBAL_Control
0x140037446  cmp     rcx, rax
0x140037449  jz      short loc_1400374BD
0x14003744b  test    byte ptr [rcx+1Ch], 1
0x14003744f  jz      short loc_1400374BD
0x140037451  cmp     byte ptr [rcx+19h], 2
0x140037455  jb      short loc_1400374BD
0x140037457  mov     edx, 1Ah
0x14003745c  mov     rcx, [rcx+10h]
0x140037460  mov     r9, rdi
0x140037463  mov     [rsp+4D8h+var_4B0], r8d
0x140037468  lea     r8, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids
0x14003746f  mov     [rsp+4D8h+var_4B8], rbx
0x140037474  call    WPP_SF_SSd
0x140037479  jmp     short loc_1400374BD
0x14003747b  mov     r8d, 80070057h
0x140037481  mov     rcx, cs:WPP_GLOBAL_Control
0x140037488  lea     rax, WPP_GLOBAL_Control
0x14003748f  cmp     rcx, rax
0x140037492  jz      short loc_1400374BD
0x140037494  test    byte ptr [rcx+1Ch], 1
0x140037498  jz      short loc_1400374BD
0x14003749a  cmp     byte ptr [rcx+19h], 2
0x14003749e  jb      short loc_1400374BD
0x1400374a0  mov     rcx, [rcx+10h]
0x1400374a4  mov     edx, 19h
0x1400374a9  mov     dword ptr [rsp+4D8h+var_4B8], r8d
0x1400374ae  mov     r9, rbx
0x1400374b1  lea     r8, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids
0x1400374b8  call    WPP_SF_Sd
0x1400374bd  mov     rcx, [rsp+4D8h+var_48]
0x1400374c5  xor     rcx, rsp; StackCookie
0x1400374c8  call    __security_check_cookie
0x1400374cd  add     rsp, 4A0h
0x1400374d4  pop     r15
0x1400374d6  pop     r14
0x1400374d8  pop     r12
0x1400374da  pop     rdi
0x1400374db  pop     rsi
0x1400374dc  pop     rbp
0x1400374dd  pop     rbx
0x1400374de  retn
```
