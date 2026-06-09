# CTemplate::Compile(CHitObj *)

- ea: `0x1800140a0`
- end: `0x18001459c`
- name: `?Compile@CTemplate@@QEAAJPEAVCHitObj@@@Z`
- size: `1276`
- prototype: `__int64 __fastcall(CTemplate *this, void **)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800140a0`
- `0x1800145a4`
- `0x1800145d4`
- `0x180014740`
- `0x180014898`
- `0x180014970`
- `0x180014f34`
- `0x1800157dc`
- `0x180016780`
- `0x180016c3c`
- `0x180017338`
- `0x180017484`
- `0x18001a3c0`
- `0x180023dd0`
- `0x18005ace8`
- `0x18005cb70`
- `0x18005d7e4`
- `0x18005d834`
- `0x18005f23c`
- `0x180064010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800140eb`
- `KERNEL32!HeapAlloc` at `0x1800140eb`
- `KERNEL32!GetCPInfo` at `0x180014327`
- `KERNEL32!GetCPInfo` at `0x180014327`
- `KERNEL32!RaiseException` at `0x18001442e`
- `KERNEL32!RaiseException` at `0x18001442e`
- `KERNEL32!SetEvent` at `0x18001454e`
- `KERNEL32!SetEvent` at `0x18002c276`
- `KERNEL32!SetEvent` at `0x18001454e`
- `KERNEL32!SetEvent` at `0x18002c276`
- `KERNEL32!GetTickCount` at `0x18001436a`
- `KERNEL32!GetTickCount` at `0x18001436a`
- `iisutil!PuDbgPrint` at `0x18002c12b`
- `iisutil!PuDbgPrint` at `0x18002c1b1`
- `iisutil!PuDbgPrint` at `0x18002c1e9`
- `iisutil!PuDbgPrint` at `0x18002c223`
- `iisutil!PuDbgPrint` at `0x18002c12b`
- `iisutil!PuDbgPrint` at `0x18002c1b1`
- `iisutil!PuDbgPrint` at `0x18002c1e9`
- `iisutil!PuDbgPrint` at `0x18002c223`

## string_xrefs

- `0x18002c11d`: `inetsrv\iis\svcs\cmp\asp\template.cpp`
- `0x18002c1a3`: `inetsrv\iis\svcs\cmp\asp\template.cpp`
- `0x18002c1db`: `inetsrv\iis\svcs\cmp\asp\template.cpp`
- `0x18002c215`: `inetsrv\iis\svcs\cmp\asp\template.cpp`
- `0x18002c104`: `Script Compiled\n`
- `0x18002c110`: `CTemplate::Compile`
- `0x18002c196`: `CTemplate::Compile`
- `0x18002c1ce`: `CTemplate::Compile`
- `0x18002c208`: `CTemplate::Compile`

## pseudocode

```c
__int64 __fastcall CTemplate::Compile(CTemplate *this, void **a2)
{
  CTemplate::CWorkStore *v4; // rax
  __int64 v5; // rax
  CTemplate::CWorkStore **v6; // r12
  int v7; // esi
  CTemplate::CScriptStore *v8; // r9
  _DWORD *v9; // rax
  const char **v10; // rdx
  unsigned int v11; // edx
  int SIDFromTokenHandle; // ecx
  unsigned int *v13; // r15
  _DWORD *v14; // rcx
  int v15; // ecx
  unsigned int i; // eax
  __int64 v17; // r8
  unsigned int v18; // edx
  int v19; // ecx
  __int64 v20; // r8
  CTemplate::CWorkStore *v21; // rdx
  int v22; // eax
  unsigned int j; // r12d
  char v24; // r12
  unsigned int k; // r15d
  int v27; // eax
  unsigned int v28; // [rsp+40h] [rbp-B8h]
  unsigned __int16 *v29; // [rsp+48h] [rbp-B0h] BYREF
  char *v30; // [rsp+50h] [rbp-A8h] BYREF
  int v31; // [rsp+58h] [rbp-A0h]
  struct CHitObj *v32; // [rsp+60h] [rbp-98h]
  struct _GUID *v33; // [rsp+68h] [rbp-90h] BYREF
  unsigned int *v34; // [rsp+70h] [rbp-88h]
  CTemplate::CWorkStore *v35; // [rsp+80h] [rbp-78h] BYREF
  int v36; // [rsp+88h] [rbp-70h]
  CTemplate *v37; // [rsp+90h] [rbp-68h]
  char v38; // [rsp+98h] [rbp-60h]
  struct _cpinfo CPInfo; // [rsp+9Ch] [rbp-5Ch] BYREF
  int v40; // [rsp+B0h] [rbp-48h]
  __int64 v41; // [rsp+B8h] [rbp-40h]

  v33 = (struct _GUID *)this;
  v32 = (struct CHitObj *)a2;
  v4 = (CTemplate::CWorkStore *)HeapAlloc(g_hDenaliHeap, 0, 0xF0u);
  if ( v4 )
    v5 = CTemplate::CWorkStore::CWorkStore(v4);
  else
    v5 = 0;
  v6 = (CTemplate::CWorkStore **)((char *)this + 48);
  v29 = (unsigned __int16 *)((char *)this + 48);
  *((_QWORD *)this + 6) = v5;
  v7 = -2147024882;
  if ( v5 )
  {
    v8 = (CTemplate::CScriptStore *)(v5 + 72);
    v9 = a2[29];
    if ( !v9 )
      v9 = (_DWORD *)*((_QWORD *)a2[3] + 19);
    v10 = (const char **)a2[29];
    if ( !v10 )
      v10 = (const char **)*((_QWORD *)a2[3] + 19);
    v7 = CTemplate::CScriptStore::Init(
           v8,
           v10[25],
           (struct _GUID *)((unsigned __int64)(v9 + 17) & -(__int64)((v9[3] & 4) != 0)));
    if ( v7 == -2147319765 )
      CTemplate::HandleCTemplateError(this, 0, 0, 0x7ECu, 0, 0, (struct CHitObj *)a2);
    if ( v7 < 0 )
    {
      if ( *v6 )
      {
        CTemplate::CWorkStore::`scalar deleting destructor'(*v6, v11);
        *v6 = 0;
      }
    }
    else
    {
      CTemplate::CWorkStore::Init(*v6);
      CTemplate::AppendMapFile(this, 0, 0, 0, (struct CHitObj *)a2, *((_BYTE *)this + 392) & 1);
    }
  }
  SIDFromTokenHandle = 0;
  if ( v7 < 0
    || (SIDFromTokenHandle = CTemplate::GetSIDFromTokenHandle(
                               0,
                               a2[12],
                               (void **)this + 65,
                               (void **)this + 64,
                               (unsigned int *)this + 132),
        SIDFromTokenHandle < 0) )
  {
    v27 = *((_DWORD *)this + 98) | 4;
    if ( v7 < 0 )
      SIDFromTokenHandle = v7;
    *((_DWORD *)this + 93) = SIDFromTokenHandle;
    *((_DWORD *)this + 98) = v27 | 8;
    SetEvent(*((HANDLE *)this + 7));
  }
  else
  {
    v30 = (char *)this;
    *((_DWORD *)this + 99) = 0;
    v13 = (unsigned int *)((char *)this + 392);
    v34 = (unsigned int *)((char *)this + 392);
    *((_DWORD *)this + 98) = *((_DWORD *)this + 98) & 0xFFFFFF3F | 0x40;
    CTemplate::GetSegmentsFromFile(this, **((struct CTemplate::CFileMap ***)this + 34), *v6, (struct CHitObj *)a2, 1);
    CTemplate::GetLanguageEquivalents(this);
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v40 = 1;
    v41 = 0;
    v14 = a2[29];
    if ( !v14 )
      v14 = (_DWORD *)*((_QWORD *)a2[3] + 19);
    v15 = v14[12];
    v35 = *v6;
    v37 = this;
    v40 = v15;
    if ( !GetCPInfo(*((_DWORD *)this + 100), &CPInfo) )
      CPInfo.MaxCharSize = 0;
    v38 = 0;
    CTemplate::CWriteTemplate::WriteTemplateComponents((CTemplate::CWriteTemplate *)&v35);
    v38 = 1;
    CTemplate::CWriteTemplate::WriteTemplateComponents((CTemplate::CWriteTemplate *)&v35);
    *((_DWORD *)this + 125) = dword_180079E20;
    *((_DWORD *)this + 126) = GetTickCount();
    for ( i = 0; ; i = v28 + 1 )
    {
      v28 = i;
      if ( i >= *((_DWORD *)this + 74) )
        break;
      v17 = *((_QWORD *)this + 34);
      v18 = *v13
          & 0xFFFFDFFF
          ^ ((unsigned __int16)*v13
           | (unsigned __int16)((unsigned __int16)*(_DWORD *)(*(_QWORD *)(v17 + 8LL * i) + 76LL) << 13))
          & 0x2000;
      *v13 = v18;
      *v13 = v18
           & 0xFFFFBFFF
           ^ ((unsigned __int16)v18
            | (unsigned __int16)((unsigned __int16)*(_DWORD *)(*(_QWORD *)(v17 + 8LL * i) + 76LL) << 13))
           & 0x4000;
      CTemplate::CFileMap::CountChars(*(CTemplate::CFileMap **)(v17 + 8LL * i), *((_WORD *)this + 200));
    }
    v19 = 0;
    v20 = *((_QWORD *)v30 + 52);
    if ( v20 )
    {
      v31 = (*(__int64 (__fastcall **)(struct IWrapTypeLibs *, _QWORD, __int64, char *))(*(_QWORD *)g_pWrapTypelibs
                                                                                       + 24LL))(
              g_pWrapTypelibs,
              *((_QWORD *)this + 51),
              v20,
              (char *)this + 432);
      CTemplate::ReleaseTypeLibs(this);
      v19 = v31;
    }
    if ( v19 < 0 )
    {
      *((_QWORD *)this + 19) = 0;
      *((_DWORD *)this + 40) = 2040;
      CTemplate::ProcessSpecificError(this, **((struct CTemplate::CFileMap ***)this + 34), (struct CHitObj *)a2);
      RaiseException(0x8000D005, 0, 0, 0);
    }
    *v13 |= 2u;
    CTemplate::CWriteTemplate::~CWriteTemplate((CTemplate::CWriteTemplate *)&v35);
    if ( (*v13 & 1) == 0 )
    {
      v21 = *v6;
      v22 = *((_WORD *)*v6 + 49) ? *(unsigned __int16 *)(**((_QWORD **)v21 + 9) + 10LL) : 0;
      if ( *((_WORD *)v21 + 49) <= 1u
        && !v22
        && !*((_WORD *)v21 + 25)
        && *((_WORD *)v21 + 5) == 1
        && !*((_DWORD *)v30 + 112)
        && !*((_BYTE *)v21 + 160) )
      {
        *v13 |= 0x80u;
      }
    }
    if ( *v6 )
    {
      CTemplate::CWorkStore::`scalar deleting destructor'(*v6, (unsigned int)v21);
      *v6 = 0;
    }
    for ( j = 0; j < *((_DWORD *)this + 74); ++j )
      CTemplate::CFileMap::UnmapFile(*(CTemplate::CFileMap **)(*((_QWORD *)this + 34) + 8LL * j));
    v24 = g_dwDebugFlags;
    if ( (g_dwDebugFlags & 0x2000) != 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp",
          1745,
          "CTemplate::Compile",
          "Script Compiled\n");
        v24 = g_dwDebugFlags;
      }
      for ( k = 0; k < *((_DWORD *)this + 44); ++k )
      {
        v30 = 0;
        v29 = 0;
        CTemplate::GetScriptBlock(this, k, &v30, &v33, (const unsigned __int16 **)&v29);
        if ( (v24 & 3) != 0 )
        {
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp",
            1754,
            "CTemplate::Compile",
            "Engine %d, Language=\"%s\":\n",
            k,
            v30);
          v24 = g_dwDebugFlags;
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp",
              1755,
              "CTemplate::Compile",
              (const char *)v29);
            v24 = g_dwDebugFlags;
            if ( (g_dwDebugFlags & 3) != 0 )
            {
              PuDbgPrint(g_pDebug, "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp", 1756, "CTemplate::Compile", "\n");
              v24 = g_dwDebugFlags;
            }
          }
        }
      }
      v13 = v34;
    }
    *v13 |= 8u;
    SetEvent(*((HANDLE *)this + 7));
    *v13 = *v13 & 0xFFFFFEFF | (8 * (*((_DWORD *)a2[3] + 18) & 0x20));
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800140a0  mov     [rsp+arg_10], rbx
0x1800140a5  mov     [rsp+arg_18], rsi
0x1800140aa  push    rdi
0x1800140ab  push    r12
0x1800140ad  push    r13
0x1800140af  push    r14
0x1800140b1  push    r15
0x1800140b3  sub     rsp, 0D0h
0x1800140ba  mov     rax, cs:__security_cookie
0x1800140c1  xor     rax, rsp
0x1800140c4  mov     [rsp+0F8h+var_38], rax
0x1800140cc  mov     r14, rdx
0x1800140cf  mov     rdi, rcx
0x1800140d2  mov     [rsp+0F8h+var_90], rcx
0x1800140d7  mov     [rsp+0F8h+var_98], rdx
0x1800140dc  xor     edx, edx; dwFlags
0x1800140de  mov     r8d, 0F0h; dwBytes
0x1800140e4  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x1800140eb  call    cs:__imp_HeapAlloc
0x1800140f1  xor     ebx, ebx
0x1800140f3  test    rax, rax
0x1800140f6  jz      loc_18002C034
0x1800140fc  mov     rcx, rax; this
0x1800140ff  call    ??0CWorkStore@CTemplate@@QEAA@XZ; CTemplate::CWorkStore::CWorkStore(void)
0x180014104  lea     r12, [rdi+30h]
0x180014108  mov     [rsp+0F8h+var_B0], r12
0x18001410d  mov     [r12], rax
0x180014111  mov     esi, 8007000Eh
0x180014116  test    rax, rax
0x180014119  cmovnz  esi, ebx
0x18001411c  jz      loc_18002C09D
0x180014122  lea     r9, [rax+48h]
0x180014126  mov     rax, [r14+0E8h]
0x18001412d  test    rax, rax
0x180014130  jz      loc_18002C03C
0x180014136  mov     rdx, rax
0x180014139  mov     ecx, [rax+0Ch]
0x18001413c  and     cl, 4
0x18001413f  add     rax, 44h ; 'D'
0x180014143  neg     cl
0x180014145  sbb     r8, r8
0x180014148  and     r8, rax; struct _GUID *
0x18001414b  test    rdx, rdx
0x18001414e  jz      loc_18002C053
0x180014154  mov     rdx, [rdx+0C8h]; char *
0x18001415b  mov     rcx, r9; this
0x18001415e  call    ?Init@CScriptStore@CTemplate@@QEAAJPEBDPEAU_GUID@@@Z; CTemplate::CScriptStore::Init(char const *,_GUID *)
0x180014163  mov     esi, eax
0x180014165  cmp     eax, 8002802Bh
0x18001416a  jz      loc_18002C063
0x180014170  test    esi, esi
0x180014172  js      loc_18002C08A
0x180014178  mov     rcx, [r12]; this
0x18001417c  call    ?Init@CWorkStore@CTemplate@@QEAAXXZ; CTemplate::CWorkStore::Init(void)
0x180014181  mov     al, [rdi+188h]
0x180014187  mov     r13d, 1
0x18001418d  and     al, r13b
0x180014190  mov     byte ptr [rsp+0F8h+var_D0], al; unsigned __int8
0x180014194  mov     [rsp+0F8h+var_D8], r14; struct CHitObj *
0x180014199  xor     r9d, r9d; unsigned __int8
0x18001419c  xor     r8d, r8d; struct CTemplate::CFileMap *
0x18001419f  xor     edx, edx; unsigned __int16 *
0x1800141a1  mov     rcx, rdi; this
0x1800141a4  call    ?AppendMapFile@CTemplate@@AEAAXPEBGPEAVCFileMap@1@EPEAVCHitObj@@E@Z; CTemplate::AppendMapFile(ushort const *,CTemplate::CFileMap *,uchar,CHitObj *,uchar)
0x1800141a9  jmp     loc_18001423C
0x1800141ae  mov     esi, eax
0x1800141b0  mov     rdi, [rsp+0F8h+var_90]
0x1800141b5  cmp     qword ptr [rdi+30h], 0
0x1800141ba  jz      short loc_1800141D2
0x1800141bc  mov     rcx, [rdi+30h]; this
0x1800141c0  test    rcx, rcx
0x1800141c3  jz      short loc_1800141CA
0x1800141c5  call    ??_GCWorkStore@CTemplate@@QEAAPEAXI@Z; CTemplate::CWorkStore::`scalar deleting destructor'(uint)
0x1800141ca  mov     qword ptr [rdi+30h], 0
0x1800141d2  mov     r14, [rsp+0F8h+var_98]
0x1800141d7  cmp     esi, 8000D004h
0x1800141dd  jnz     short loc_1800141E7
0x1800141df  mov     rcx, r14; struct CHitObj *
0x1800141e2  call    HandleAccessFailure
0x1800141e7  cmp     esi, 8000D001h
0x1800141ed  jz      short loc_180014227
0x1800141ef  cmp     qword ptr [rdi+110h], 0
0x1800141f7  jz      short loc_180014227
0x1800141f9  mov     rax, [rdi+110h]
0x180014200  cmp     qword ptr [rax], 0
0x180014204  jz      short loc_180014227
0x180014206  mov     rcx, [rax]
0x180014209  mov     eax, 8000D002h
0x18001420e  cmp     dword ptr [rcx+80h], 0
0x180014215  cmovz   esi, eax
0x180014218  mov     rcx, [rdi+110h]
0x18001421f  mov     rcx, [rcx]; this
0x180014222  call    ?UnmapFile@CFileMap@CTemplate@@QEAAXXZ; CTemplate::CFileMap::UnmapFile(void)
0x180014227  mov     eax, 80004005h
0x18001422c  test    esi, esi
0x18001422e  cmovns  esi, eax
0x180014231  xor     ebx, ebx
0x180014233  lea     r13d, [rbx+1]
0x180014237  mov     r12, [rsp+0F8h+var_B0]
0x18001423c  mov     ecx, ebx; this
0x18001423e  test    esi, esi
0x180014240  js      loc_18002C255
0x180014246  lea     rax, [rdi+210h]
0x18001424d  lea     r9, [rdi+200h]; void **
0x180014254  lea     r8, [rdi+208h]; void **
0x18001425b  mov     [rsp+0F8h+var_D8], rax; unsigned int *
0x180014260  mov     rdx, [r14+60h]; void *
0x180014264  call    ?GetSIDFromTokenHandle@CTemplate@@QEAAJPEAXPEAPEAX1PEAK@Z; CTemplate::GetSIDFromTokenHandle(void *,void * *,void * *,ulong *)
0x180014269  mov     ecx, eax
0x18001426b  test    eax, eax
0x18001426d  js      loc_18002C255
0x180014273  mov     [rsp+0F8h+var_A8], rdi
0x180014278  mov     [rdi+18Ch], ebx
0x18001427e  lea     r15, [rdi+188h]
0x180014285  mov     [rsp+0F8h+var_88], r15
0x18001428a  mov     eax, [r15]
0x18001428d  btr     eax, 7
0x180014291  or      eax, 40h
0x180014294  mov     [r15], eax
0x180014297  mov     rdx, [rdi+110h]
0x18001429e  mov     dword ptr [rsp+0F8h+var_D8], r13d; int
0x1800142a3  mov     r9, r14; struct CHitObj *
0x1800142a6  mov     r8, [r12]; struct CTemplate::CWorkStore *
0x1800142aa  mov     rdx, [rdx]; struct CTemplate::CFileMap *
0x1800142ad  mov     rcx, rdi; this
0x1800142b0  call    ?GetSegmentsFromFile@CTemplate@@AEAAXAEAVCFileMap@1@AEAVCWorkStore@1@PEAVCHitObj@@H@Z; CTemplate::GetSegmentsFromFile(CTemplate::CFileMap &,CTemplate::CWorkStore &,CHitObj *,int)
0x1800142b5  mov     rcx, rdi; this
0x1800142b8  call    ?GetLanguageEquivalents@CTemplate@@AEAAXXZ; CTemplate::GetLanguageEquivalents(void)
0x1800142bd  mov     [rsp+0F8h+var_78], rbx
0x1800142c5  mov     [rsp+0F8h+var_70], ebx
0x1800142cc  mov     [rsp+0F8h+var_68], rbx
0x1800142d4  mov     [rsp+0F8h+var_60], bl
0x1800142db  mov     [rsp+0F8h+var_48], r13d
0x1800142e3  mov     [rsp+0F8h+var_40], rbx
0x1800142eb  mov     rcx, [r14+0E8h]
0x1800142f2  test    rcx, rcx
0x1800142f5  jz      loc_180014436
0x1800142fb  mov     ecx, [rcx+30h]
0x1800142fe  mov     rax, [r12]
0x180014302  mov     [rsp+0F8h+var_78], rax
0x18001430a  mov     [rsp+0F8h+var_68], rdi
0x180014312  mov     [rsp+0F8h+var_48], ecx
0x180014319  lea     rdx, [rsp+0F8h+CPInfo]; lpCPInfo
0x180014321  mov     ecx, [rdi+190h]; CodePage
0x180014327  call    cs:__imp_GetCPInfo
0x18001432d  test    eax, eax
0x18001432f  jz      loc_180014446
0x180014335  mov     [rsp+0F8h+var_60], bl
0x18001433c  lea     rcx, [rsp+0F8h+var_78]; this
0x180014344  call    ?WriteTemplateComponents@CWriteTemplate@CTemplate@@QEAAXXZ; CTemplate::CWriteTemplate::WriteTemplateComponents(void)
0x180014349  mov     [rsp+0F8h+var_60], r13b
0x180014351  lea     rcx, [rsp+0F8h+var_78]; this
0x180014359  call    ?WriteTemplateComponents@CWriteTemplate@CTemplate@@QEAAXXZ; CTemplate::CWriteTemplate::WriteTemplateComponents(void)
0x18001435e  mov     eax, cs:dword_180079E20
0x180014364  mov     [rdi+1F4h], eax
0x18001436a  call    cs:__imp_GetTickCount
0x180014370  mov     [rdi+1F8h], eax
0x180014376  mov     eax, ebx
0x180014378  mov     [rsp+0F8h+var_B8], eax
0x18001437c  cmp     eax, [rdi+128h]
0x180014382  jnb     short loc_1800143E0
0x180014384  mov     ecx, [r15]
0x180014387  mov     r9d, eax
0x18001438a  mov     r8, [rdi+110h]
0x180014391  mov     rax, [r8+r9*8]
0x180014395  mov     edx, [rax+4Ch]
0x180014398  shl     edx, 0Dh
0x18001439b  or      edx, ecx
0x18001439d  and     edx, 2000h
0x1800143a3  btr     ecx, 0Dh
0x1800143a7  xor     edx, ecx
0x1800143a9  mov     [r15], edx
0x1800143ac  mov     rax, [r8+r9*8]
0x1800143b0  mov     ecx, [rax+4Ch]
0x1800143b3  shl     ecx, 0Dh
0x1800143b6  or      ecx, edx
0x1800143b8  and     ecx, 4000h
0x1800143be  btr     edx, 0Eh
0x1800143c2  xor     ecx, edx
0x1800143c4  mov     [r15], ecx
0x1800143c7  movzx   edx, word ptr [rdi+190h]; unsigned __int16
0x1800143ce  mov     rcx, [r8+r9*8]; this
0x1800143d2  call    ?CountChars@CFileMap@CTemplate@@QEAAKG@Z; CTemplate::CFileMap::CountChars(ushort)
0x1800143d7  mov     eax, [rsp+0F8h+var_B8]
0x1800143db  add     eax, r13d
0x1800143de  jmp     short loc_180014378
0x1800143e0  mov     ecx, ebx
0x1800143e2  mov     rax, [rsp+0F8h+var_A8]
0x1800143e7  mov     r8, [rax+1A0h]
0x1800143ee  test    r8, r8
0x1800143f1  jnz     short loc_180014452
0x1800143f3  test    ecx, ecx
0x1800143f5  jns     loc_180014488
0x1800143fb  mov     [rdi+98h], rbx
0x180014402  mov     dword ptr [rdi+0A0h], 7F8h
0x18001440c  mov     rdx, [rdi+110h]
0x180014413  mov     r8, r14; struct CHitObj *
0x180014416  mov     rdx, [rdx]; struct CTemplate::CFileMap *
0x180014419  mov     rcx, rdi; this
0x18001441c  call    ?ProcessSpecificError@CTemplate@@AEAAXAEAVCFileMap@1@PEAVCHitObj@@@Z; CTemplate::ProcessSpecificError(CTemplate::CFileMap &,CHitObj *)
0x180014421  xor     r9d, r9d; lpArguments
0x180014424  xor     r8d, r8d; nNumberOfArguments
0x180014427  xor     edx, edx; dwExceptionFlags
0x180014429  mov     ecx, 8000D005h; dwExceptionCode
0x18001442e  call    cs:__imp_RaiseException
0x180014434  jmp     short loc_180014488
0x180014436  mov     rax, [r14+18h]
0x18001443a  mov     rcx, [rax+98h]
0x180014441  jmp     loc_1800142FB
0x180014446  mov     [rsp+0F8h+CPInfo.MaxCharSize], ebx
0x18001444d  jmp     loc_180014335
0x180014452  mov     rcx, cs:?g_pWrapTypelibs@@3PEAUIWrapTypeLibs@@EA; IWrapTypeLibs * g_pWrapTypelibs
0x180014459  mov     rax, [rcx]
0x18001445c  lea     r9, [rdi+1B0h]
0x180014463  mov     rdx, [rdi+198h]
0x18001446a  mov     rax, [rax+18h]
0x18001446e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014473  mov     [rsp+0F8h+var_A0], eax
0x180014477  mov     rcx, rdi; this
0x18001447a  call    ?ReleaseTypeLibs@CTemplate@@AEAAXXZ; CTemplate::ReleaseTypeLibs(void)
0x18001447f  mov     ecx, [rsp+0F8h+var_A0]
0x180014483  jmp     loc_1800143F3
0x180014488  or      dword ptr [r15], 2
0x18001448c  lea     rcx, [rsp+0F8h+var_78]; this
0x180014494  call    ??1CWriteTemplate@CTemplate@@QEAA@XZ; CTemplate::CWriteTemplate::~CWriteTemplate(void)
0x180014499  jmp     short loc_1800144B7
0x18001449b  mov     esi, eax
0x18001449d  xor     ebx, ebx
0x18001449f  lea     r13d, [rbx+1]
0x1800144a3  mov     r15, [rsp+0F8h+var_88]
0x1800144a8  mov     rdi, [rsp+0F8h+var_90]
0x1800144ad  mov     r14, [rsp+0F8h+var_98]
0x1800144b2  mov     r12, [rsp+0F8h+var_B0]
0x1800144b7  mov     r8d, [r15]
0x1800144ba  test    r13b, r8b
0x1800144bd  jnz     short loc_1800144EB
0x1800144bf  test    esi, esi
0x1800144c1  js      short loc_1800144EB
0x1800144c3  mov     rdx, [r12]; unsigned int
0x1800144c7  cmp     [rdx+62h], bx
0x1800144cb  jbe     loc_18002C0B0
0x1800144d1  mov     rax, [rdx+48h]
0x1800144d5  mov     rcx, [rax]
0x1800144d8  movzx   eax, word ptr [rcx+0Ah]
0x1800144dc  cmp     [rdx+62h], r13w
0x1800144e1  ja      short loc_1800144EB
0x1800144e3  test    eax, eax
0x1800144e5  jz      loc_18002C0B7
0x1800144eb  cmp     [r12], rbx
0x1800144ef  jz      short loc_1800144FE
0x1800144f1  mov     rcx, [r12]; this
0x1800144f5  call    ??_GCWorkStore@CTemplate@@QEAAPEAXI@Z; CTemplate::CWorkStore::`scalar deleting destructor'(uint)
0x1800144fa  mov     [r12], rbx
0x1800144fe  mov     r12d, ebx
0x180014501  cmp     [rdi+128h], ebx
0x180014507  jbe     short loc_180014528
0x180014509  mov     eax, r12d
0x18001450c  mov     rcx, [rdi+110h]
0x180014513  mov     rcx, [rcx+rax*8]; this
0x180014517  call    ?UnmapFile@CFileMap@CTemplate@@QEAAXXZ; CTemplate::CFileMap::UnmapFile(void)
0x18001451c  add     r12d, r13d
0x18001451f  cmp     r12d, [rdi+128h]
0x180014526  jb      short loc_180014509
0x180014528  mov     r12d, cs:g_dwDebugFlags
0x18001452f  bt      r12d, 0Dh
0x180014534  jb      loc_18002C0F6
0x18001453a  cmp     esi, 8000D005h
0x180014540  jz      loc_18002C242
0x180014546  or      dword ptr [r15], 8
0x18001454a  mov     rcx, [rdi+38h]; hEvent
0x18001454e  call    cs:__imp_SetEvent
0x180014554  mov     rax, [r14+18h]
0x180014558  mov     ecx, [rax+48h]
0x18001455b  and     ecx, 20h
0x18001455e  shl     ecx, 3
0x180014561  mov     eax, [r15]
0x180014564  btr     eax, 8
0x180014568  or      ecx, eax
0x18001456a  mov     [r15], ecx
0x18001456d  mov     eax, esi
0x18001456f  mov     rcx, [rsp+0F8h+var_38]
0x180014577  xor     rcx, rsp; StackCookie
0x18001457a  call    __security_check_cookie
0x18001457f  lea     r11, [rsp+0F8h+var_28]
0x180014587  mov     rbx, [r11+40h]
0x18001458b  mov     rsi, [r11+48h]
0x18001458f  mov     rsp, r11
0x180014592  pop     r15
0x180014594  pop     r14
0x180014596  pop     r13
0x180014598  pop     r12
0x18001459a  pop     rdi
0x18001459b  retn
0x18002c034  mov     rax, rbx
0x18002c037  jmp     loc_180014104
0x18002c03c  mov     rax, [r14+18h]
0x18002c040  mov     rax, [rax+98h]
0x18002c047  mov     rdx, [r14+0E8h]
0x18002c04e  jmp     loc_180014139
0x18002c053  mov     rax, [r14+18h]
  ... truncated ...
```
