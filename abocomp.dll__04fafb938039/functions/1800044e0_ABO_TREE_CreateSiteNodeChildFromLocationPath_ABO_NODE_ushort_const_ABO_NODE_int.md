# ABO_TREE::CreateSiteNodeChildFromLocationPath(ABO_NODE *,ushort const *,ABO_NODE * *,int *)

- ea: `0x1800044e0`
- end: `0x180004736`
- name: `?CreateSiteNodeChildFromLocationPath@ABO_TREE@@AEAAJPEAVABO_NODE@@PEBGPEAPEAV2@PEAH@Z`
- size: `598`
- prototype: `int(ABO_TREE *__hidden this, struct ABO_NODE *, const unsigned __int16 *, struct ABO_NODE **, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180004b80`

## callees

- `0x180001f90`
- `0x18000341a`
- `0x180003460`
- `0x1800044e0`
- `0x18000473c`
- `0x1800047b0`
- `0x180007148`
- `0x1800141f8`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800045f0`
- `msvcrt!_wcsnicmp` at `0x1800045f0`
- `msvcrt!wcschr` at `0x180004649`
- `msvcrt!wcschr` at `0x180004649`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000465e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000465e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004548`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000456d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004593`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004548`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000456d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004593`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800046f0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800046fa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004704`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800046f0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800046fa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004704`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004683`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004683`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004672`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004672`

## pseudocode

```c
__int64 __fastcall ABO_TREE::CreateSiteNodeChildFromLocationPath(
        ABO_TREE *this,
        struct ABO_NODE *a2,
        const unsigned __int16 *a3,
        struct ABO_NODE **a4,
        int *a5)
{
  ABO_NODE *v8; // rsi
  __int64 v9; // rbx
  int v10; // edi
  __int64 v11; // rcx
  const wchar_t *v12; // rax
  int v13; // ebx
  volatile signed __int32 *v14; // r14
  wchar_t *v15; // r12
  const unsigned __int16 *Str; // rax
  int v18; // [rsp+30h] [rbp-D0h]
  struct ABO_NODE *v19; // [rsp+38h] [rbp-C8h] BYREF
  int *v20; // [rsp+40h] [rbp-C0h]
  _BYTE v21[56]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v22[56]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v23[56]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v24[256]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v25[256]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v26[256]; // [rsp+4F0h] [rbp+3F0h] BYREF

  v20 = a5;
  memset_0(v24, 0, sizeof(v24));
  STRU::STRU((STRU *)v23, v24, 0x100u);
  memset_0(v25, 0, sizeof(v25));
  STRU::STRU((STRU *)v22, v25, 0x100u);
  memset_0(v26, 0, sizeof(v26));
  STRU::STRU((STRU *)v21, v26, 0x100u);
  v8 = 0;
  v19 = 0;
  if ( a2 && a3 && a4 )
  {
    v9 = 0;
    if ( !*((_DWORD *)a2 + 54) )
    {
LABEL_8:
      v13 = -2147024894;
      ABO_MAPPER_LOG::WriteLogEntry((HANDLE *)g_pAboLog, L" GetProvider on potential site failed %X", 2147942402LL);
      goto LABEL_22;
    }
    v10 = 1;
    while ( 1 )
    {
      v11 = *(_QWORD *)(*((_QWORD *)a2 + 26) + 8 * v9);
      v12 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      if ( !_wcsnicmp(L"IIsWebServer", v12, 0xCu) )
        break;
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= *((_DWORD *)a2 + 54) )
        goto LABEL_8;
    }
    v14 = *(volatile signed __int32 **)(*((_QWORD *)a2 + 26) + 8 * v9);
    _InterlockedAdd(v14 + 2, 1u);
    v18 = SITE_CUSTOM_PROVIDER::FHasApplication((SITE_CUSTOM_PROVIDER *)v14);
    v15 = wcschr(a3, 0x2Fu);
    v13 = STRU::Copy((STRU *)v21, L"ROOT");
    if ( v13 >= 0 )
    {
      v13 = STRU::Append((STRU *)v21, v15);
      if ( v13 >= 0 )
      {
        Str = STRU::QueryStr((STRU *)v21);
        v13 = ABO_NODE::CreateNode((struct ABO_TREE **)a2, Str, 1, &v19, 0);
        if ( v13 < 0 )
        {
          v8 = v19;
        }
        else
        {
          *a4 = v19;
          if ( v18 && v15 )
            v10 = 0;
          *v20 = v10;
        }
      }
    }
    if ( v14 )
      CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider((CUSTOM_PROPERTY_PROVIDER *)v14);
  }
  else
  {
    v13 = -2147024809;
  }
  if ( v8 )
    ABO_NODE::DereferenceAboNode(v8);
LABEL_22:
  STRU::~STRU((STRU *)v21);
  STRU::~STRU((STRU *)v22);
  STRU::~STRU((STRU *)v23);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800044e0  mov     [rsp-8+arg_0], rbx
0x1800044e5  push    rbp
0x1800044e6  push    rsi
0x1800044e7  push    rdi
0x1800044e8  push    r12
0x1800044ea  push    r13
0x1800044ec  push    r14
0x1800044ee  push    r15
0x1800044f0  lea     rbp, [rsp-600h]
0x1800044f8  sub     rsp, 700h
0x1800044ff  mov     rax, cs:__security_cookie
0x180004506  xor     rax, rsp
0x180004509  mov     [rbp+630h+var_40], rax
0x180004510  mov     rax, [rbp+630h+arg_20]
0x180004517  lea     rcx, [rbp+630h+var_640]; void *
0x18000451b  mov     r12, r8
0x18000451e  mov     [rsp+730h+var_6F0], rax
0x180004523  mov     r15, rdx
0x180004526  mov     edi, 200h
0x18000452b  mov     r8d, edi; Size
0x18000452e  xor     edx, edx; Val
0x180004530  mov     r13, r9
0x180004533  call    memset_0
0x180004538  mov     ebx, 100h
0x18000453d  lea     rdx, [rbp+630h+var_640]
0x180004541  mov     r8d, ebx
0x180004544  lea     rcx, [rbp+630h+var_678]
0x180004548  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000454e  mov     r8d, edi; Size
0x180004551  lea     rcx, [rbp+630h+var_440]; void *
0x180004558  xor     edx, edx; Val
0x18000455a  call    memset_0
0x18000455f  mov     r8d, ebx
0x180004562  lea     rdx, [rbp+630h+var_440]
0x180004569  lea     rcx, [rbp+630h+var_6B0]
0x18000456d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180004573  mov     r8d, edi; Size
0x180004576  lea     rcx, [rbp+630h+var_240]; void *
0x18000457d  xor     edx, edx; Val
0x18000457f  call    memset_0
0x180004584  mov     r8d, ebx
0x180004587  lea     rdx, [rbp+630h+var_240]
0x18000458e  lea     rcx, [rsp+730h+var_6E8]
0x180004593  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180004599  xor     esi, esi
0x18000459b  mov     [rsp+730h+var_6F8], rsi
0x1800045a0  test    r15, r15
0x1800045a3  jz      loc_1800046D9
0x1800045a9  test    r12, r12
0x1800045ac  jz      loc_1800046D9
0x1800045b2  test    r13, r13
0x1800045b5  jz      loc_1800046D9
0x1800045bb  xor     ebx, ebx
0x1800045bd  cmp     [r15+0D8h], ebx
0x1800045c4  jbe     short loc_180004605
0x1800045c6  lea     edi, [rsi+1]
0x1800045c9  mov     rax, [r15+0D0h]
0x1800045d0  mov     rcx, [rax+rbx*8]
0x1800045d4  mov     rax, [rcx]
0x1800045d7  mov     rax, [rax+10h]
0x1800045db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045e0  mov     rdx, rax; String2
0x1800045e3  lea     rcx, aIiswebserver; "IIsWebServer"
0x1800045ea  mov     r8d, 0Ch; MaxCount
0x1800045f0  call    cs:__imp__wcsnicmp
0x1800045f6  test    eax, eax
0x1800045f8  jz      short loc_180004625
0x1800045fa  add     ebx, edi
0x1800045fc  cmp     ebx, [r15+0D8h]
0x180004603  jb      short loc_1800045C9
0x180004605  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18000460c  lea     rdx, aGetproviderOnP; " GetProvider on potential site failed %"...
0x180004613  mov     ebx, 80070002h
0x180004618  mov     r8d, ebx
0x18000461b  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180004620  jmp     loc_1800046EB
0x180004625  mov     rax, [r15+0D0h]
0x18000462c  mov     r14, [rax+rbx*8]
0x180004630  lock add [r14+8], edi
0x180004635  mov     rcx, r14; this
0x180004638  call    ?FHasApplication@SITE_CUSTOM_PROVIDER@@QEAAHXZ; SITE_CUSTOM_PROVIDER::FHasApplication(void)
0x18000463d  mov     edx, 2Fh ; '/'; Ch
0x180004642  mov     [rsp+730h+var_700], eax
0x180004646  mov     rcx, r12; Str
0x180004649  call    cs:__imp_wcschr
0x18000464f  lea     rdx, aRoot_0; "ROOT"
0x180004656  mov     r12, rax
0x180004659  lea     rcx, [rsp+730h+var_6E8]
0x18000465e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004664  mov     ebx, eax
0x180004666  test    eax, eax
0x180004668  js      short loc_1800046CA
0x18000466a  mov     rdx, r12
0x18000466d  lea     rcx, [rsp+730h+var_6E8]
0x180004672  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004678  mov     ebx, eax
0x18000467a  test    eax, eax
0x18000467c  js      short loc_1800046CA
0x18000467e  lea     rcx, [rsp+730h+var_6E8]
0x180004683  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004689  lea     r9, [rsp+730h+var_6F8]; struct ABO_NODE **
0x18000468e  mov     [rsp+730h+var_710], esi; int
0x180004692  mov     rdx, rax; unsigned __int16 *
0x180004695  mov     r8d, edi; int
0x180004698  mov     rcx, r15; this
0x18000469b  call    ?CreateNode@ABO_NODE@@QEAAJPEBGHPEAPEAV1@H@Z; ABO_NODE::CreateNode(ushort const *,int,ABO_NODE * *,int)
0x1800046a0  mov     ebx, eax
0x1800046a2  test    eax, eax
0x1800046a4  js      short loc_1800046C5
0x1800046a6  mov     rax, [rsp+730h+var_6F8]
0x1800046ab  mov     [r13+0], rax
0x1800046af  cmp     [rsp+730h+var_700], esi
0x1800046b3  jz      short loc_1800046BC
0x1800046b5  test    r12, r12
0x1800046b8  jz      short loc_1800046BC
0x1800046ba  xor     edi, edi
0x1800046bc  mov     rax, [rsp+730h+var_6F0]
0x1800046c1  mov     [rax], edi
0x1800046c3  jmp     short loc_1800046CA
0x1800046c5  mov     rsi, [rsp+730h+var_6F8]
0x1800046ca  test    r14, r14
0x1800046cd  jz      short loc_1800046DE
0x1800046cf  mov     rcx, r14; this
0x1800046d2  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x1800046d7  jmp     short loc_1800046DE
0x1800046d9  mov     ebx, 80070057h
0x1800046de  test    rsi, rsi
0x1800046e1  jz      short loc_1800046EB
0x1800046e3  mov     rcx, rsi; this
0x1800046e6  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x1800046eb  lea     rcx, [rsp+730h+var_6E8]
0x1800046f0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800046f6  lea     rcx, [rbp+630h+var_6B0]
0x1800046fa  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004700  lea     rcx, [rbp+630h+var_678]
0x180004704  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000470a  mov     eax, ebx
0x18000470c  mov     rcx, [rbp+630h+var_40]
0x180004713  xor     rcx, rsp; StackCookie
0x180004716  call    __security_check_cookie
0x18000471b  mov     rbx, [rsp+730h+arg_0]
0x180004723  add     rsp, 700h
0x18000472a  pop     r15
0x18000472c  pop     r14
0x18000472e  pop     r13
0x180004730  pop     r12
0x180004732  pop     rdi
0x180004733  pop     rsi
0x180004734  pop     rbp
0x180004735  retn
```
