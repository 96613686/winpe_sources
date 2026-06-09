# CProjSite::Create(int,wchar_t const *,VBEPROJTYPE,CVbeProject * *)

- ea: `0x18007631c`
- end: `0x1800768a5`
- name: `?Create@CProjSite@@SAJHPEB_WW4VBEPROJTYPE@@PEAPEAVCVbeProject@@@Z`
- size: `1417`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x18006b740`
- `0x18006c05c`

## callees

- `0x18001b8b0`
- `0x18001bf20`
- `0x18001bf84`
- `0x180026838`
- `0x18005ab18`
- `0x180069e64`
- `0x180075f88`
- `0x180075ffc`
- `0x18007631c`
- `0x1800cb6f0`
- `0x1800cb79c`
- `0x180379380`
- `0x180379520`
- `0x180379546`

## import_xrefs

- `MSVCR100!free` at `0x180076865`
- `MSVCR100!free` at `0x180076865`
- `MSVCR100!malloc` at `0x1800767ab`
- `MSVCR100!malloc` at `0x1800767ab`
- `ole32!StgOpenStorage` at `0x180076756`
- `ole32!StgOpenStorage` at `0x180076785`
- `ole32!StgOpenStorage` at `0x180076756`
- `ole32!StgOpenStorage` at `0x180076785`
- `ole32!StgCreateDocfile` at `0x180076615`
- `ole32!StgCreateDocfile` at `0x180076615`
- `OLEAUT32!__imp_SysAllocString` at `0x180076719`
- `OLEAUT32!__imp_SysAllocString` at `0x180076719`
- `OLEAUT32!__imp_SysFreeString` at `0x180076828`
- `OLEAUT32!__imp_SysFreeString` at `0x180076828`

## pseudocode

```c
__int64 __fastcall CProjSite::Create(int a1, const OLECHAR *a2, unsigned int a3, _QWORD *a4)
{
  _QWORD *v4; // r12
  unsigned int v5; // ebx
  WCHAR *v7; // r13
  CProjSite *v8; // rsi
  unsigned __int16 v9; // r14
  int v10; // edx
  unsigned int v11; // edi
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  unsigned int v17; // r12d
  IStorage *v18; // rax
  __int64 v19; // rbx
  char *v20; // rax
  __int64 result; // rax
  int v22; // eax
  bool v23; // zf
  HRESULT v24; // edi
  int v25; // edi
  char *v26; // rbx
  char *v27; // rax
  int v28; // eax
  const char *PrintFullPath; // rbx
  const char *v30; // r11
  __int64 v31; // rax
  unsigned __int64 v32; // rax
  __int64 v33; // rcx
  unsigned __int64 v34; // rcx
  void *v35; // rsp
  void *v36; // rsp
  wchar_t *v37; // rax
  HRESULT v38; // eax
  void *v39; // rdi
  _QWORD *v40; // rax
  _QWORD *v41; // rsi
  __int64 v42; // rbx
  IStorage *ppstgOpen; // [rsp+40h] [rbp+0h] BYREF
  __int64 v44; // [rsp+48h] [rbp+8h]
  int v45; // [rsp+50h] [rbp+10h] BYREF
  int v46; // [rsp+54h] [rbp+14h]
  _BYTE v47[24]; // [rsp+58h] [rbp+18h] BYREF

  v4 = a4;
  v44 = (__int64)a4;
  v5 = a3;
  v46 = a1;
  ppstgOpen = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0x8000;
  if ( !a1 )
  {
    CFileRep::CFileRep((CFileRep *)v47);
    if ( !a2 )
    {
      v25 = dword_1803F99EC;
      dword_1803F99EC = 181010;
      v26 = IntlLpstrStringOfID(498);
      v27 = IntlLpstrStringOfID(82);
      v28 = DlgIdFileOpen((struct CFileRep *)v47, v27, 0, v26, (struct CFileRep *)&g_Dlg_filerepLastPathFiles, 0, 0);
      dword_1803F99EC = v25;
      if ( !v28 )
      {
        CFileRep::~CFileRep((CFileRep *)v47);
        return 0;
      }
      if ( ((unsigned __int64)CFileRep::GetPrintFullPath((CFileRep *)v47) & 0xFFFFFFFFFFFF0000uLL) != 0 )
      {
        PrintFullPath = CFileRep::GetPrintFullPath((CFileRep *)v47);
        v30 = CFileRep::GetPrintFullPath((CFileRep *)v47);
        v31 = -1;
        do
          ++v31;
        while ( v30[v31] );
        v32 = 2 * v31 + 2;
        v33 = v32 + 15;
        if ( v32 + 15 < v32 )
          v33 = 0xFFFFFFFFFFFFFF0LL;
        v34 = v33 & 0xFFFFFFFFFFFFFFF0uLL;
        v35 = alloca(v34);
        v36 = alloca(v34);
        v37 = strcpyWfromA((wchar_t *)&ppstgOpen, PrintFullPath);
      }
      else
      {
        v37 = (wchar_t *)CFileRep::GetPrintFullPath((CFileRep *)v47);
      }
      a2 = v37;
    }
    v7 = SysAllocString(a2);
    if ( v7 )
    {
      v38 = StgOpenStorage(v7, 0, 0x10012u, 0, 0, &ppstgOpen);
      v24 = v38;
      if ( v38 >= 0 )
        goto LABEL_79;
      if ( v38 == -2147287035 )
        v24 = StgOpenStorage(v7, 0, 0x10010u, 0, 0, &ppstgOpen);
      if ( v24 >= 0 )
      {
LABEL_79:
        v5 = 4;
        CFileRep::~CFileRep((CFileRep *)v47);
LABEL_80:
        v39 = g_hHeapPrimary;
        v40 = malloc(0x40u);
        v41 = v40;
        if ( v40 )
          memset_0(v40, 0, 0x40u);
        if ( v41 && (*v41 = v39, (v8 = (CProjSite *)(v41 + 1)) != 0) )
          *(_QWORD *)v8 = &CProjSite::`vftable';
        else
          v8 = 0;
        if ( !v8 )
          return 2147942414LL;
        v24 = CProjSite::Init(v8, v9, v5, ppstgOpen, v7, v46);
        if ( v24 >= 0 && v4 )
          *v4 = *((_QWORD *)v8 + 5);
        goto LABEL_91;
      }
    }
    else
    {
      v24 = -2147024882;
    }
    CFileRep::~CFileRep((CFileRep *)v47);
LABEL_91:
    SysFreeString(v7);
    if ( v24 < 0 && v8 )
    {
      v42 = *((_QWORD *)v8 + 5);
      if ( v42 )
      {
        *((_QWORD *)v8 + 5) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      }
      else
      {
        CProjSite::~CProjSite(v8);
        free((char *)v8 - 8);
      }
    }
    if ( ppstgOpen )
      ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
    return (unsigned int)v24;
  }
  if ( a3 != 4 )
  {
LABEL_59:
    v24 = StgCreateDocfile(0, 0x4011012u, 0, &ppstgOpen);
    if ( v24 >= 0 )
      goto LABEL_80;
    goto LABEL_91;
  }
  v10 = g_fSupportDHTMLProjects;
  v5 = 0;
  v11 = g_fSupportDHTMLProjects != 0;
  if ( g_fSupportMTProjects )
    ++v11;
  if ( g_fSupportAddinProjects )
    ++v11;
  if ( g_fSupportGenericProjects )
    ++v11;
  v12 = 16LL * v11;
  v13 = v12 + 15;
  if ( v12 + 15 < v12 )
    v13 = 0xFFFFFFFFFFFFFF0LL;
  v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
  v15 = alloca(v14);
  v16 = alloca(v14);
  v17 = 0;
  if ( g_fSupportGenericProjects )
  {
    v44 = 3;
    v17 = 1;
    ppstgOpen = (IStorage *)IntlLpstrStringOfID(592);
    v10 = g_fSupportDHTMLProjects;
  }
  if ( v10 )
  {
    (&ppstgOpen)[2 * v17] = (IStorage *)IntlLpstrStringOfID(594);
    (&ppstgOpen)[2 * v17++ + 1] = 0;
    v5 = 0;
  }
  if ( g_fSupportAddinProjects )
  {
    v18 = (IStorage *)IntlLpstrStringOfID(591);
    (&ppstgOpen)[2 * v17 + 1] = (IStorage *)2;
    (&ppstgOpen)[2 * v17++] = v18;
    v5 = 0;
  }
  if ( g_fSupportMTProjects )
  {
    v19 = 2LL * v17;
    (&ppstgOpen)[v19] = (IStorage *)IntlLpstrStringOfID(593);
    (&ppstgOpen)[v19 + 1] = (IStorage *)1;
    v5 = 0;
  }
  v20 = IntlLpstrStringOfID(84);
  result = DlgFileNew(v20, (struct FILENEWITEM *)&ppstgOpen, v11, 0, &v45);
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)result == 1 )
      return 0;
    if ( v45 )
    {
      if ( v45 != 1 )
      {
        if ( v45 == 2 )
        {
          if ( g_fSupportGenericProjects && g_fSupportDHTMLProjects && g_fSupportAddinProjects )
            v5 = 2;
          else
            v5 = g_fSupportMTProjects != 0 ? 1 : 4;
        }
        else if ( !g_fSupportGenericProjects
               || !g_fSupportDHTMLProjects
               || !g_fSupportAddinProjects
               || (v5 = 1, !g_fSupportMTProjects) )
        {
          v5 = 4;
        }
        goto LABEL_46;
      }
      if ( g_fSupportGenericProjects && g_fSupportDHTMLProjects )
      {
LABEL_46:
        if ( v5 )
        {
          switch ( v5 )
          {
            case 1u:
              v9 = -24576;
              break;
            case 2u:
              v9 = -16384;
              break;
            case 3u:
              v9 = 0x8000;
              break;
            default:
              v24 = -2147467259;
              goto LABEL_91;
          }
        }
        else
        {
          if ( (int)CVbe::UseIEVersion(*((struct IVbeSite **)CVbe::m_pVbe + 9), 4, 1) < 0 )
          {
            v24 = 0;
            goto LABEL_91;
          }
          v9 = -28672;
        }
        v4 = (_QWORD *)v44;
        goto LABEL_59;
      }
      v22 = 2;
      v5 = g_fSupportMTProjects != 0 ? 1 : 4;
      v23 = g_fSupportAddinProjects == 0;
    }
    else
    {
      v5 = g_fSupportMTProjects != 0 ? 1 : 4;
      if ( g_fSupportAddinProjects )
        v5 = 2;
      v22 = 3;
      if ( g_fSupportDHTMLProjects )
        v5 = 0;
      v23 = g_fSupportGenericProjects == 0;
    }
    if ( !v23 )
      v5 = v22;
    goto LABEL_46;
  }
  return result;
}

```

## disassembly

```asm
0x18007631c  push    rbp
0x18007631e  push    r12
0x180076320  push    r13
0x180076322  push    r14
0x180076324  push    r15
0x180076326  mov     eax, 80h
0x18007632b  call    _alloca_probe
0x180076330  sub     rsp, rax
0x180076333  lea     rbp, [rsp+40h]
0x180076338  mov     [rbp+60h+arg_0], rbx
0x18007633c  mov     [rbp+60h+arg_8], rsi
0x180076340  mov     [rbp+60h+arg_10], rdi
0x180076347  mov     rax, cs:__security_cookie
0x18007634e  xor     rax, rbp
0x180076351  mov     [rbp+60h+var_30], rax
0x180076355  xor     r15d, r15d
0x180076358  mov     r12, r9
0x18007635b  mov     [rbp+60h+var_58], r9
0x18007635f  mov     ebx, r8d
0x180076362  mov     rdi, rdx
0x180076365  mov     [rbp+60h+var_4C], ecx
0x180076368  mov     [rbp+60h+ppstgOpen], r15
0x18007636c  mov     r13d, r15d
0x18007636f  mov     esi, r15d
0x180076372  mov     r14d, 8000h
0x180076378  test    ecx, ecx
0x18007637a  jz      loc_18007662A
0x180076380  lea     r15d, [rsi+4]
0x180076384  cmp     ebx, r15d
0x180076387  jnz     loc_1800765F8
0x18007638d  mov     edx, cs:?g_fSupportDHTMLProjects@@3HA; int g_fSupportDHTMLProjects
0x180076393  xor     ebx, ebx
0x180076395  lea     eax, [rsi+1]
0x180076398  test    edx, edx
0x18007639a  mov     edi, ebx
0x18007639c  cmovnz  edi, eax
0x18007639f  cmp     cs:?g_fSupportMTProjects@@3HA, ebx; int g_fSupportMTProjects
0x1800763a5  jz      short loc_1800763A9
0x1800763a7  add     edi, eax
0x1800763a9  cmp     cs:?g_fSupportAddinProjects@@3HA, ebx; int g_fSupportAddinProjects
0x1800763af  jz      short loc_1800763B3
0x1800763b1  add     edi, eax
0x1800763b3  mov     r8d, cs:?g_fSupportGenericProjects@@3HA; int g_fSupportGenericProjects
0x1800763ba  test    r8d, r8d
0x1800763bd  jz      short loc_1800763C1
0x1800763bf  add     edi, eax
0x1800763c1  mov     eax, edi
0x1800763c3  shl     rax, 4
0x1800763c7  lea     rcx, [rax+0Fh]
0x1800763cb  cmp     rcx, rax
0x1800763ce  ja      short loc_1800763DA
0x1800763d0  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800763da  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800763de  mov     rax, rcx
0x1800763e1  call    _alloca_probe
0x1800763e6  sub     rsp, rcx
0x1800763e9  mov     r12d, ebx
0x1800763ec  lea     r14, [rsp+0A0h+ppstgOpen]
0x1800763f1  test    r8d, r8d
0x1800763f4  jz      short loc_180076417
0x1800763f6  mov     ecx, 250h; int
0x1800763fb  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x180076400  mov     qword ptr [r14+8], 3
0x180076408  mov     r12d, 1
0x18007640e  mov     [r14], rax
0x180076411  mov     edx, cs:?g_fSupportDHTMLProjects@@3HA; int g_fSupportDHTMLProjects
0x180076417  test    edx, edx
0x180076419  jz      short loc_18007643B
0x18007641b  mov     ebx, r12d
0x18007641e  mov     ecx, 252h; int
0x180076423  add     rbx, rbx
0x180076426  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x18007642b  xor     edx, edx
0x18007642d  mov     [r14+rbx*8], rax
0x180076431  mov     [r14+rbx*8+8], rdx
0x180076436  inc     r12d
0x180076439  xor     ebx, ebx
0x18007643b  cmp     cs:?g_fSupportAddinProjects@@3HA, ebx; int g_fSupportAddinProjects
0x180076441  jz      short loc_180076465
0x180076443  mov     ebx, r12d
0x180076446  mov     ecx, 24Fh; int
0x18007644b  add     rbx, rbx
0x18007644e  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x180076453  mov     qword ptr [r14+rbx*8+8], 2
0x18007645c  mov     [r14+rbx*8], rax
0x180076460  inc     r12d
0x180076463  xor     ebx, ebx
0x180076465  cmp     cs:?g_fSupportMTProjects@@3HA, ebx; int g_fSupportMTProjects
0x18007646b  jz      short loc_180076490
0x18007646d  mov     ebx, r12d
0x180076470  mov     ecx, 251h; int
0x180076475  add     rbx, rbx
0x180076478  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x18007647d  mov     r12d, 1
0x180076483  mov     [r14+rbx*8], rax
0x180076487  mov     [r14+rbx*8+8], r12
0x18007648c  xor     ebx, ebx
0x18007648e  jmp     short loc_180076496
0x180076490  mov     r12d, 1
0x180076496  mov     ecx, 54h ; 'T'; int
0x18007649b  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x1800764a0  xor     r9d, r9d; int
0x1800764a3  mov     r8d, edi; int
0x1800764a6  mov     rcx, rax; char *
0x1800764a9  lea     rax, [rbp+60h+var_50]
0x1800764ad  mov     rdx, r14; struct FILENEWITEM *
0x1800764b0  mov     qword ptr [rsp+0A0h+reserved], rax; int *
0x1800764b5  call    ?DlgFileNew@@YAJPEADPEAUFILENEWITEM@@HHPEAH@Z; DlgFileNew(char *,FILENEWITEM *,int,int,int *)
0x1800764ba  test    eax, eax
0x1800764bc  js      loc_18007687C
0x1800764c2  cmp     eax, r12d
0x1800764c5  jnz     short loc_1800764CE
0x1800764c7  xor     eax, eax
0x1800764c9  jmp     loc_18007687C
0x1800764ce  mov     eax, [rbp+60h+var_50]
0x1800764d1  test    eax, eax
0x1800764d3  jnz     short loc_180076507
0x1800764d5  mov     eax, cs:?g_fSupportMTProjects@@3HA; int g_fSupportMTProjects
0x1800764db  neg     eax
0x1800764dd  sbb     ebx, ebx
0x1800764df  xor     edx, edx
0x1800764e1  and     ebx, 0FFFFFFFDh
0x1800764e4  lea     eax, [rdx+2]
0x1800764e7  add     ebx, r15d
0x1800764ea  cmp     cs:?g_fSupportAddinProjects@@3HA, edx; int g_fSupportAddinProjects
0x1800764f0  cmovnz  ebx, eax
0x1800764f3  cmp     cs:?g_fSupportDHTMLProjects@@3HA, edx; int g_fSupportDHTMLProjects
0x1800764f9  lea     eax, [rdx+3]
0x1800764fc  cmovnz  ebx, edx
0x1800764ff  cmp     cs:?g_fSupportGenericProjects@@3HA, edx; int g_fSupportGenericProjects
0x180076505  jmp     short loc_180076537
0x180076507  cmp     eax, r12d
0x18007650a  jnz     short loc_18007653C
0x18007650c  cmp     cs:?g_fSupportGenericProjects@@3HA, ebx; int g_fSupportGenericProjects
0x180076512  jz      short loc_18007651C
0x180076514  cmp     cs:?g_fSupportDHTMLProjects@@3HA, ebx; int g_fSupportDHTMLProjects
0x18007651a  jnz     short loc_180076599
0x18007651c  mov     eax, cs:?g_fSupportMTProjects@@3HA; int g_fSupportMTProjects
0x180076522  neg     eax
0x180076524  sbb     ebx, ebx
0x180076526  xor     edx, edx
0x180076528  and     ebx, 0FFFFFFFDh
0x18007652b  lea     eax, [rdx+2]
0x18007652e  add     ebx, r15d
0x180076531  cmp     cs:?g_fSupportAddinProjects@@3HA, edx; int g_fSupportAddinProjects
0x180076537  cmovnz  ebx, eax
0x18007653a  jmp     short loc_180076599
0x18007653c  mov     ecx, 2
0x180076541  cmp     eax, ecx
0x180076543  jnz     short loc_180076573
0x180076545  cmp     cs:?g_fSupportGenericProjects@@3HA, ebx; int g_fSupportGenericProjects
0x18007654b  jz      short loc_180076561
0x18007654d  cmp     cs:?g_fSupportDHTMLProjects@@3HA, ebx; int g_fSupportDHTMLProjects
0x180076553  jz      short loc_180076561
0x180076555  cmp     cs:?g_fSupportAddinProjects@@3HA, ebx; int g_fSupportAddinProjects
0x18007655b  jz      short loc_180076561
0x18007655d  mov     ebx, ecx
0x18007655f  jmp     short loc_180076599
0x180076561  mov     eax, cs:?g_fSupportMTProjects@@3HA; int g_fSupportMTProjects
0x180076567  neg     eax
0x180076569  sbb     ebx, ebx
0x18007656b  and     ebx, 0FFFFFFFDh
0x18007656e  add     ebx, r15d
0x180076571  jmp     short loc_180076599
0x180076573  cmp     cs:?g_fSupportGenericProjects@@3HA, ebx; int g_fSupportGenericProjects
0x180076579  jz      short loc_180076596
0x18007657b  cmp     cs:?g_fSupportDHTMLProjects@@3HA, ebx; int g_fSupportDHTMLProjects
0x180076581  jz      short loc_180076596
0x180076583  cmp     cs:?g_fSupportAddinProjects@@3HA, ebx; int g_fSupportAddinProjects
0x180076589  jz      short loc_180076596
0x18007658b  cmp     cs:?g_fSupportMTProjects@@3HA, ebx; int g_fSupportMTProjects
0x180076591  mov     ebx, r12d
0x180076594  jnz     short loc_180076599
0x180076596  mov     ebx, r15d
0x180076599  mov     ecx, ebx
0x18007659b  test    ebx, ebx
0x18007659d  jz      short loc_1800765CB
0x18007659f  dec     ecx
0x1800765a1  jz      short loc_1800765C3
0x1800765a3  dec     ecx
0x1800765a5  jz      short loc_1800765B8
0x1800765a7  xor     r15d, r15d
0x1800765aa  dec     ecx
0x1800765ac  jz      short loc_1800765FD
0x1800765ae  mov     edi, 80004005h
0x1800765b3  jmp     loc_180076825
0x1800765b8  mov     r14d, 0C000h
0x1800765be  xor     r15d, r15d
0x1800765c1  jmp     short loc_180076603
0x1800765c3  mov     r14d, 0A000h
0x1800765c9  jmp     short loc_1800765BE
0x1800765cb  mov     rax, cs:?m_pVbe@CVbe@@0PEAV1@EA; CVbe * CVbe::m_pVbe
0x1800765d2  mov     r8d, r12d; int
0x1800765d5  mov     edx, r15d; int
0x1800765d8  mov     rcx, [rax+48h]; struct IVbeSite *
0x1800765dc  call    ?UseIEVersion@CVbe@@SAJPEAUIVbeSite@@JJ@Z; CVbe::UseIEVersion(IVbeSite *,long,long)
0x1800765e1  xor     r15d, r15d
0x1800765e4  test    eax, eax
0x1800765e6  js      short loc_1800765F0
0x1800765e8  mov     r14d, 9000h
0x1800765ee  jmp     short loc_180076603
0x1800765f0  mov     edi, r15d
0x1800765f3  jmp     loc_180076825
0x1800765f8  xor     r15d, r15d
0x1800765fb  jmp     short loc_180076607
0x1800765fd  mov     r14d, 8000h
0x180076603  mov     r12, [rbp+60h+var_58]
0x180076607  lea     r9, [rbp+60h+ppstgOpen]; ppstgOpen
0x18007660b  xor     r8d, r8d; reserved
0x18007660e  mov     edx, 4011012h; grfMode
0x180076613  xor     ecx, ecx; pwcsName
0x180076615  call    cs:__imp_StgCreateDocfile
0x18007661b  mov     edi, eax
0x18007661d  test    eax, eax
0x18007661f  js      loc_180076825
0x180076625  jmp     loc_18007679F
0x18007662a  lea     rcx, [rbp+60h+var_48]; this
0x18007662e  call    ??0CFileRep@@QEAA@XZ; CFileRep::CFileRep(void)
0x180076633  test    rdi, rdi
0x180076636  jnz     loc_180076716
0x18007663c  mov     edi, cs:dword_1803F99EC
0x180076642  mov     ecx, 1F2h; int
0x180076647  mov     cs:dword_1803F99EC, 2C312h
0x180076651  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x180076656  mov     ecx, 52h ; 'R'; int
0x18007665b  mov     rbx, rax
0x18007665e  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x180076663  mov     [rsp+0A0h+var_70], r15d; unsigned int
0x180076668  mov     rdx, rax; char *
0x18007666b  lea     rax, ?g_Dlg_filerepLastPathFiles@@3VCFileRep@@A; CFileRep g_Dlg_filerepLastPathFiles
0x180076672  lea     rcx, [rbp+60h+var_48]; struct CFileRep *
0x180076676  mov     r9, rbx; char *
0x180076679  xor     r8d, r8d; char *
0x18007667c  mov     [rsp+0A0h+var_78], r15; int *
0x180076681  mov     qword ptr [rsp+0A0h+reserved], rax; struct CFileRep *
0x180076686  call    ?DlgIdFileOpen@@YAHPEAVCFileRep@@PEAD110PEAHK@Z; DlgIdFileOpen(CFileRep *,char *,char *,char *,CFileRep *,int *,ulong)
0x18007668b  mov     cs:dword_1803F99EC, edi
0x180076691  lea     rcx, [rbp+60h+var_48]; this
0x180076695  test    eax, eax
0x180076697  jnz     short loc_1800766A3
0x180076699  call    ??1CFileRep@@QEAA@XZ; CFileRep::~CFileRep(void)
0x18007669e  jmp     loc_1800764C7
0x1800766a3  call    ?GetPrintFullPath@CFileRep@@QEAAPEBDXZ; CFileRep::GetPrintFullPath(void)
0x1800766a8  lea     rcx, [rbp+60h+var_48]; this
0x1800766ac  test    rax, 0FFFFFFFFFFFF0000h
0x1800766b2  jz      short loc_18007670E
0x1800766b4  call    ?GetPrintFullPath@CFileRep@@QEAAPEBDXZ; CFileRep::GetPrintFullPath(void)
0x1800766b9  lea     rcx, [rbp+60h+var_48]; this
0x1800766bd  mov     rbx, rax
0x1800766c0  call    ?GetPrintFullPath@CFileRep@@QEAAPEBDXZ; CFileRep::GetPrintFullPath(void)
0x1800766c5  mov     r11, rax
0x1800766c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800766cc  inc     rax
0x1800766cf  cmp     [r11+rax], r15b
0x1800766d3  jnz     short loc_1800766CC
0x1800766d5  lea     rax, ds:2[rax*2]
0x1800766dd  lea     rcx, [rax+0Fh]
0x1800766e1  cmp     rcx, rax
0x1800766e4  ja      short loc_1800766F0
0x1800766e6  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800766f0  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800766f4  mov     rax, rcx
0x1800766f7  call    _alloca_probe
0x1800766fc  sub     rsp, rcx
0x1800766ff  mov     rdx, rbx; char *
0x180076702  lea     rcx, [rsp+0A0h+ppstgOpen]; wchar_t *
0x180076707  call    ?strcpyWfromA@@YAPEA_WPEA_WPEBD@Z; strcpyWfromA(wchar_t *,char const *)
0x18007670c  jmp     short loc_180076713
0x18007670e  call    ?GetPrintFullPath@CFileRep@@QEAAPEBDXZ; CFileRep::GetPrintFullPath(void)
0x180076713  mov     rdi, rax
0x180076716  mov     rcx, rdi; psz
0x180076719  call    cs:__imp_SysAllocString
0x18007671f  mov     r13, rax
0x180076722  test    rax, rax
0x180076725  jnz     short loc_18007673A
0x180076727  mov     edi, 8007000Eh
0x18007672c  lea     rcx, [rbp+60h+var_48]; this
0x180076730  call    ??1CFileRep@@QEAA@XZ; CFileRep::~CFileRep(void)
0x180076735  jmp     loc_180076825
0x18007673a  lea     rax, [rbp+60h+ppstgOpen]
0x18007673e  xor     r9d, r9d; snbExclude
0x180076741  xor     edx, edx; pstgPriority
0x180076743  mov     [rsp+0A0h+var_78], rax; ppstgOpen
0x180076748  mov     r8d, 10012h; grfMode
0x18007674e  mov     rcx, r13; pwcsName
0x180076751  mov     [rsp+0A0h+reserved], r15d; reserved
0x180076756  call    cs:__imp_StgOpenStorage
0x18007675c  mov     edi, eax
0x18007675e  test    eax, eax
0x180076760  jns     short loc_180076791
0x180076762  cmp     eax, 80030005h
0x180076767  jnz     short loc_18007678D
0x180076769  lea     rax, [rbp+60h+ppstgOpen]
0x18007676d  xor     r9d, r9d; snbExclude
0x180076770  xor     edx, edx; pstgPriority
0x180076772  mov     [rsp+0A0h+var_78], rax; ppstgOpen
0x180076777  mov     r8d, 10010h; grfMode
0x18007677d  mov     rcx, r13; pwcsName
0x180076780  mov     [rsp+0A0h+reserved], r15d; reserved
0x180076785  call    cs:__imp_StgOpenStorage
  ... truncated ...
```
