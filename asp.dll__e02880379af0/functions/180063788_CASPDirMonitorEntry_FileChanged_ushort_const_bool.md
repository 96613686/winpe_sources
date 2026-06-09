# CASPDirMonitorEntry::FileChanged(ushort const *,bool)

- ea: `0x180063788`
- end: `0x1800639de`
- name: `?FileChanged@CASPDirMonitorEntry@@AEAAXPEBG_N@Z`
- size: `598`
- prototype: `void(CASPDirMonitorEntry *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path`

## callers

- `0x1800631b0`

## callees

- `0x180006a38`
- `0x180023d86`
- `0x180023dd0`
- `0x1800340a4`
- `0x180034160`
- `0x180034454`
- `0x18003456c`
- `0x1800455f8`
- `0x180048280`
- `0x180063544`
- `0x180063788`

## import_xrefs

- `msvcrt!wcschr` at `0x180063823`
- `msvcrt!wcschr` at `0x180063823`
- `msvcrt!wcsncpy_s` at `0x18006389e`
- `msvcrt!wcsncpy_s` at `0x18006389e`
- `KERNEL32!HeapFree` at `0x180063998`
- `KERNEL32!HeapFree` at `0x180063998`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800638b5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800638b5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800638cb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800638cb`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180063873`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180063873`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800639a3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800639a3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180063889`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180063889`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800638e1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800638e1`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800637e0`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800637e0`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800639ae`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800639ae`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18006380a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18006380a`
- `iisutil!PuDbgPrint` at `0x180063947`
- `iisutil!PuDbgPrint` at `0x180063947`

## string_xrefs

- `0x180063922`: `ChangeNotification: Flushing "%S*" from cache.\n`

## pseudocode

```c
void __fastcall CASPDirMonitorEntry::FileChanged(const unsigned __int16 **this, wchar_t *a2, char a3)
{
  void *v6; // r12
  char v7; // r13
  wchar_t *v8; // rdi
  char v9; // si
  const WCHAR *Str; // rbx
  unsigned int v11; // edi
  wchar_t *Ptr; // rbx
  CIncFileMap *v13; // rcx
  CTemplateCacheManager *v14; // rcx
  unsigned __int16 *v15; // rcx
  CTemplateCacheManager *v16; // rcx
  CFileApplicationMap *v17; // rcx
  LPVOID lpMem; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[56]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v20[48]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v21[272]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v22[264]; // [rsp+1B0h] [rbp+B0h] BYREF

  memset_0(v21, 0, 0x108u);
  BUFFER::BUFFER((BUFFER *)v20, v21, 0x108u);
  memset_0(v22, 0, 0x208u);
  STRU::STRU((STRU *)v19, v22, 0x104u);
  v6 = 0;
  lpMem = 0;
  v7 = 0;
  v8 = wcschr(a2, 0x7Eu);
  if ( !v8 )
  {
LABEL_7:
    if ( (int)STRU::Copy((STRU *)v19, this[2]) < 0 || (int)STRU::Append((STRU *)v19, a2) < 0 )
      goto LABEL_19;
    v9 = 0;
    Str = STRU::QueryStr((STRU *)v19);
    goto LABEL_10;
  }
  if ( !(unsigned int)ConvertToLongFileName(this[2], a2, (unsigned __int16 **)&lpMem) )
  {
    if ( !a3 )
      goto LABEL_19;
    v11 = (unsigned int)(v8 - a2) >> 1;
    if ( !BUFFER::Resize((BUFFER *)v20, 2 * v11 + 2) )
      goto LABEL_19;
    v7 = 1;
    Ptr = (wchar_t *)BUFFER::QueryPtr((BUFFER *)v20);
    wcsncpy_s(Ptr, v11 + 1, a2, v11);
    v6 = lpMem;
    a2 = Ptr;
    goto LABEL_7;
  }
  v6 = lpMem;
  v9 = 1;
  Str = (const WCHAR *)lpMem;
LABEL_10:
  Normalize(Str);
  if ( !g_fShutDownInProgress )
  {
    if ( v7 )
    {
      LOBYTE(v13) = (g_dwDebugFlags & 3) != 0;
      if ( ((unsigned __int8)v13 & ((g_dwDebugFlags & 0x800) != 0)) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\cmp\\asp\\aspdmon.cpp",
          470,
          "CASPDirMonitorEntry::FileChanged",
          "ChangeNotification: Flushing \"%S*\" from cache.\n",
          Str);
      CIncFileMap::FlushFiles(v13, Str);
      CTemplateCacheManager::FlushFiles(v14, Str);
      v15 = 0;
    }
    else
    {
      CIncFileMap::Flush(v13, Str);
      CTemplateCacheManager::Flush(v16, Str, 0xFFFBAD1D);
      v15 = (unsigned __int16 *)Str;
    }
    Do449ChangeNotification(v15);
    CFileApplicationMap::ShutdownApplications(v17, Str);
  }
  if ( v9 )
    HeapFree(g_hDenaliHeap, 0, v6);
LABEL_19:
  STRU::~STRU((STRU *)v19);
  BUFFER::~BUFFER((BUFFER *)v20);
}

```

## disassembly

```asm
0x180063788  mov     [rsp-8+arg_10], rbx
0x18006378d  push    rbp
0x18006378e  push    rsi
0x18006378f  push    rdi
0x180063790  push    r12
0x180063792  push    r13
0x180063794  push    r14
0x180063796  push    r15
0x180063798  lea     rbp, [rsp-2D0h]
0x1800637a0  sub     rsp, 3D0h
0x1800637a7  mov     rax, cs:__security_cookie
0x1800637ae  xor     rax, rsp
0x1800637b1  mov     [rbp+300h+var_40], rax
0x1800637b8  mov     sil, r8b
0x1800637bb  mov     r14, rdx
0x1800637be  mov     r15, rcx
0x1800637c1  mov     edi, 108h
0x1800637c6  mov     r8d, edi; Size
0x1800637c9  lea     rcx, [rbp+300h+var_360]; void *
0x1800637cd  xor     edx, edx; Val
0x1800637cf  call    memset_0
0x1800637d4  mov     r8d, edi
0x1800637d7  lea     rdx, [rbp+300h+var_360]
0x1800637db  lea     rcx, [rsp+400h+var_390]
0x1800637e0  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x1800637e6  xor     edx, edx; Val
0x1800637e8  lea     rcx, [rbp+300h+var_250]; void *
0x1800637ef  mov     r8d, 208h; Size
0x1800637f5  call    memset_0
0x1800637fa  lea     r8d, [rdi-4]
0x1800637fe  lea     rdx, [rbp+300h+var_250]
0x180063805  lea     rcx, [rsp+400h+var_3C8]
0x18006380a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180063810  xor     r12d, r12d
0x180063813  mov     rcx, r14; Str
0x180063816  mov     [rsp+400h+lpMem], r12
0x18006381b  xor     r13b, r13b
0x18006381e  lea     edx, [r12+7Eh]; Ch
0x180063823  call    cs:__imp_wcschr
0x180063829  mov     rdi, rax
0x18006382c  test    rax, rax
0x18006382f  jz      short loc_1800638AC
0x180063831  mov     rcx, [r15+10h]; unsigned __int16 *
0x180063835  lea     r8, [rsp+400h+lpMem]; unsigned __int16 **
0x18006383a  mov     rdx, r14; unsigned __int16 *
0x18006383d  call    ?ConvertToLongFileName@@YAHPEBG0PEAPEAG@Z; ConvertToLongFileName(ushort const *,ushort const *,ushort * *)
0x180063842  test    eax, eax
0x180063844  jz      short loc_180063856
0x180063846  mov     r12, [rsp+400h+lpMem]
0x18006384b  mov     sil, 1
0x18006384e  mov     rbx, r12
0x180063851  jmp     loc_1800638EA
0x180063856  test    sil, sil
0x180063859  jz      loc_18006399E
0x18006385f  sub     rdi, r14
0x180063862  lea     rcx, [rsp+400h+var_390]
0x180063867  sar     rdi, 1
0x18006386a  shr     edi, 1
0x18006386c  lea     edx, ds:2[rdi*2]
0x180063873  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180063879  test    al, al
0x18006387b  jz      loc_18006399E
0x180063881  lea     rcx, [rsp+400h+var_390]
0x180063886  mov     r13b, 1
0x180063889  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18006388f  mov     r9d, edi; MaxCount
0x180063892  lea     edx, [rdi+1]; SizeInWords
0x180063895  mov     rcx, rax; Destination
0x180063898  mov     r8, r14; Source
0x18006389b  mov     rbx, rax
0x18006389e  call    cs:__imp_wcsncpy_s
0x1800638a4  mov     r12, [rsp+400h+lpMem]
0x1800638a9  mov     r14, rbx
0x1800638ac  mov     rdx, [r15+10h]
0x1800638b0  lea     rcx, [rsp+400h+var_3C8]
0x1800638b5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800638bb  test    eax, eax
0x1800638bd  js      loc_18006399E
0x1800638c3  mov     rdx, r14
0x1800638c6  lea     rcx, [rsp+400h+var_3C8]
0x1800638cb  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800638d1  test    eax, eax
0x1800638d3  js      loc_18006399E
0x1800638d9  xor     sil, sil
0x1800638dc  lea     rcx, [rsp+400h+var_3C8]
0x1800638e1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800638e7  mov     rbx, rax
0x1800638ea  mov     rcx, rbx; lpsz
0x1800638ed  call    ?Normalize@@YAHPEAG@Z; Normalize(ushort *)
0x1800638f2  cmp     cs:?g_fShutDownInProgress@@3HA, 0; int g_fShutDownInProgress
0x1800638f9  jnz     loc_180063987
0x1800638ff  test    r13b, r13b
0x180063902  jz      short loc_180063961
0x180063904  mov     edx, cs:g_dwDebugFlags
0x18006390a  test    dl, 3
0x18006390d  setnz   cl
0x180063910  bt      edx, 0Bh
0x180063914  setb    al
0x180063917  test    al, cl
0x180063919  jz      short loc_18006394D
0x18006391b  mov     rcx, cs:g_pDebug
0x180063922  lea     rax, aChangenotifica; "ChangeNotification: Flushing \"%S*\" fr"...
0x180063929  mov     [rsp+400h+var_3D8], rbx
0x18006392e  lea     r9, aCaspdirmonitor; "CASPDirMonitorEntry::FileChanged"
0x180063935  mov     r8d, 1D6h
0x18006393b  mov     [rsp+400h+var_3E0], rax
0x180063940  lea     rdx, aInetsrvIisSvcs_1; "inetsrv\\iis\\svcs\\cmp\\asp\\aspdmon.c"...
0x180063947  call    cs:__imp_PuDbgPrint
0x18006394d  mov     rdx, rbx; unsigned __int16 *
0x180063950  call    ?FlushFiles@CIncFileMap@@QEAAXPEBG@Z; CIncFileMap::FlushFiles(ushort const *)
0x180063955  mov     rdx, rbx; unsigned __int16 *
0x180063958  call    ?FlushFiles@CTemplateCacheManager@@QEAAXPEBG@Z; CTemplateCacheManager::FlushFiles(ushort const *)
0x18006395d  xor     ecx, ecx
0x18006395f  jmp     short loc_18006397A
0x180063961  mov     rdx, rbx; unsigned __int16 *
0x180063964  call    ?Flush@CIncFileMap@@QEAAXPEBG@Z; CIncFileMap::Flush(ushort const *)
0x180063969  mov     r8d, 0FFFBAD1Dh; unsigned int
0x18006396f  mov     rdx, rbx; unsigned __int16 *
0x180063972  call    ?Flush@CTemplateCacheManager@@QEAAXPEBGK@Z; CTemplateCacheManager::Flush(ushort const *,ulong)
0x180063977  mov     rcx, rbx; unsigned __int16 *
0x18006397a  call    ?Do449ChangeNotification@@YAJPEAG@Z; Do449ChangeNotification(ushort *)
0x18006397f  mov     rdx, rbx; unsigned __int16 *
0x180063982  call    ?ShutdownApplications@CFileApplicationMap@@QEAAHPEBG@Z; CFileApplicationMap::ShutdownApplications(ushort const *)
0x180063987  test    sil, sil
0x18006398a  jz      short loc_18006399E
0x18006398c  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180063993  mov     r8, r12; lpMem
0x180063996  xor     edx, edx; dwFlags
0x180063998  call    cs:__imp_HeapFree
0x18006399e  lea     rcx, [rsp+400h+var_3C8]
0x1800639a3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800639a9  lea     rcx, [rsp+400h+var_390]
0x1800639ae  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800639b4  mov     rcx, [rbp+300h+var_40]
0x1800639bb  xor     rcx, rsp; StackCookie
0x1800639be  call    __security_check_cookie
0x1800639c3  mov     rbx, [rsp+400h+arg_10]
0x1800639cb  add     rsp, 3D0h
0x1800639d2  pop     r15
0x1800639d4  pop     r14
0x1800639d6  pop     r13
0x1800639d8  pop     r12
0x1800639da  pop     rdi
0x1800639db  pop     rsi
0x1800639dc  pop     rbp
0x1800639dd  retn
```
