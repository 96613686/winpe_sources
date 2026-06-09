# SITE_CUSTOM_PROVIDER::GenerateApplications(void)

- ea: `0x180014488`
- end: `0x180014777`
- name: `?GenerateApplications@SITE_CUSTOM_PROVIDER@@AEAAJXZ`
- size: `751`
- prototype: `__int64 __fastcall(SITE_CUSTOM_PROVIDER *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x180014b90`

## callees

- `0x180001f90`
- `0x180002990`
- `0x18000341a`
- `0x180003460`
- `0x18000473c`
- `0x1800047b0`
- `0x180006e28`
- `0x180007148`
- `0x180007ea8`
- `0x180013a08`
- `0x180013d64`
- `0x180014488`
- `0x180016040`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800145aa`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800145aa`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001468b`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001468b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800144f4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800144f4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180014744`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180014744`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800145dd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800145dd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800145c4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800145c4`

## pseudocode

```c
__int64 __fastcall SITE_CUSTOM_PROVIDER::GenerateApplications(SITE_CUSTOM_PROVIDER *this)
{
  __int64 v2; // rcx
  int NodesAndProperties; // ebx
  unsigned int v4; // r14d
  struct ABO_TREE **v5; // rbx
  const unsigned __int16 *Str; // rax
  int v7; // eax
  ABO_NODE *v8; // rdi
  APPLICATION_CUSTOM_PROVIDER *v9; // rax
  APPLICATION_CUSTOM_PROVIDER *v10; // rsi
  const unsigned __int16 *DefaultAppPoolName; // rax
  CUSTOM_PROPERTY_PROVIDER *v12; // rcx
  const unsigned __int16 *v13; // rax
  unsigned int v15; // [rsp+30h] [rbp-D0h] BYREF
  struct INativeConfigurationElement *v16; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  ABO_NODE *v18; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v19; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[56]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v21[256]; // [rsp+90h] [rbp-70h] BYREF

  v16 = 0;
  v17 = 0;
  v15 = 0;
  v18 = 0;
  memset_0(v21, 0, sizeof(v21));
  STRU::STRU((STRU *)v20, v21, 0x100u);
  v2 = *((_QWORD *)this + 3);
  v19 = 0;
  NodesAndProperties = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 40LL))(v2, &v17);
  if ( NodesAndProperties >= 0 )
  {
    NodesAndProperties = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 24LL))(v17, &v15);
    if ( NodesAndProperties >= 0 )
    {
      v4 = 0;
      if ( v15 )
      {
        while ( 1 )
        {
          NodesAndProperties = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v17 + 32LL))(
                                 v17,
                                 v4,
                                 &v16);
          if ( NodesAndProperties < 0 )
            goto LABEL_21;
          NodesAndProperties = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v16 + 64LL))(
                                 v16,
                                 L"path",
                                 &v19,
                                 0,
                                 0);
          if ( NodesAndProperties < 0 )
            goto LABEL_21;
          NodesAndProperties = STRU::Copy((STRU *)v20, L"ROOT");
          if ( NodesAndProperties < 0 )
            goto LABEL_21;
          NodesAndProperties = STRU::Append((STRU *)v20, v19);
          if ( NodesAndProperties < 0 )
            goto LABEL_21;
          v5 = (struct ABO_TREE **)*((_QWORD *)this + 2);
          Str = STRU::QueryStr((STRU *)v20);
          v7 = ABO_NODE::CreateNode(v5, Str, 1, &v18, 0);
          v8 = v18;
          NodesAndProperties = v7;
          if ( v7 < 0 )
            goto LABEL_19;
          v9 = (APPLICATION_CUSTOM_PROVIDER *)operator new(0x68u);
          if ( !v9 )
            break;
          v10 = APPLICATION_CUSTOM_PROVIDER::APPLICATION_CUSTOM_PROVIDER(
                  v9,
                  v8,
                  v16,
                  *((struct INativeConfigurationElement **)this + 3));
          if ( !v10 )
            break;
          DefaultAppPoolName = SITE_CUSTOM_PROVIDER::QueryDefaultAppPoolName(this);
          NodesAndProperties = APPLICATION_CUSTOM_PROVIDER::Create(v10, DefaultAppPoolName);
          v12 = v10;
          if ( NodesAndProperties < 0
            || (NodesAndProperties = ABO_NODE::AddProvider(v8, v10), v12 = v10, NodesAndProperties < 0) )
          {
            CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v12);
            goto LABEL_19;
          }
          CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v10);
          NodesAndProperties = ABO_NODE::GenerateNodesAndProperties(v8);
          if ( NodesAndProperties < 0 )
          {
            v13 = STRU::QueryStr((ABO_NODE *)((char *)v8 + 56));
            ABO_MAPPER_LOG::WriteLogEntry(
              (HANDLE *)g_pAboLog,
              L"Failed to generate Application Node and Properties for node (%s).  error = %08x\n",
              v13,
              (unsigned int)NodesAndProperties);
            *((_DWORD *)v8 + 61) = 3;
            *((_DWORD *)v8 + 62) = NodesAndProperties;
            NodesAndProperties = 0;
          }
          ABO_NODE::DereferenceAboNode(v8);
          v18 = 0;
          (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v16 + 16LL))(v16);
          ++v4;
          v16 = 0;
          if ( v4 >= v15 )
            goto LABEL_23;
        }
        NodesAndProperties = -2147024888;
LABEL_19:
        if ( v8 )
          ABO_NODE::DereferenceAboNode(v8);
      }
    }
  }
LABEL_21:
  if ( v16 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
LABEL_23:
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  STRU::~STRU((STRU *)v20);
  return (unsigned int)NodesAndProperties;
}

```

## disassembly

```asm
0x180014488  mov     [rsp-8+arg_8], rbx
0x18001448d  mov     [rsp-8+arg_10], rsi
0x180014492  push    rbp
0x180014493  push    rdi
0x180014494  push    r12
0x180014496  push    r14
0x180014498  push    r15
0x18001449a  lea     rbp, [rsp-1A0h]
0x1800144a2  sub     rsp, 2A0h
0x1800144a9  mov     rax, cs:__security_cookie
0x1800144b0  xor     rax, rsp
0x1800144b3  mov     [rbp+1C0h+var_30], rax
0x1800144ba  xor     r12d, r12d
0x1800144bd  mov     r15, rcx
0x1800144c0  lea     rcx, [rbp+1C0h+var_230]; void *
0x1800144c4  mov     [rsp+2C0h+var_288], r12
0x1800144c9  xor     edx, edx; Val
0x1800144cb  mov     [rsp+2C0h+var_280], r12
0x1800144d0  mov     r8d, 200h; Size
0x1800144d6  mov     [rsp+2C0h+var_290], r12d
0x1800144db  mov     [rsp+2C0h+var_278], r12
0x1800144e0  call    memset_0
0x1800144e5  mov     r8d, 100h
0x1800144eb  lea     rdx, [rbp+1C0h+var_230]
0x1800144ef  lea     rcx, [rsp+2C0h+var_268]
0x1800144f4  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800144fa  mov     rcx, [r15+18h]
0x1800144fe  lea     rdx, [rsp+2C0h+var_280]
0x180014503  mov     [rsp+2C0h+var_270], r12
0x180014508  mov     rax, [rcx]
0x18001450b  mov     rax, [rax+28h]
0x18001450f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014514  mov     ebx, eax
0x180014516  test    eax, eax
0x180014518  js      loc_180014709
0x18001451e  mov     rcx, [rsp+2C0h+var_280]
0x180014523  lea     rdx, [rsp+2C0h+var_290]
0x180014528  mov     rax, [rcx]
0x18001452b  mov     rax, [rax+18h]
0x18001452f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014534  mov     ebx, eax
0x180014536  test    eax, eax
0x180014538  js      loc_180014709
0x18001453e  mov     r14d, r12d
0x180014541  cmp     [rsp+2C0h+var_290], r12d
0x180014546  jbe     loc_180014709
0x18001454c  mov     rcx, [rsp+2C0h+var_280]
0x180014551  lea     r8, [rsp+2C0h+var_288]
0x180014556  mov     edx, r14d
0x180014559  mov     rax, [rcx]
0x18001455c  mov     rax, [rax+20h]
0x180014560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014565  mov     ebx, eax
0x180014567  test    eax, eax
0x180014569  js      loc_180014709
0x18001456f  mov     rcx, [rsp+2C0h+var_288]
0x180014574  lea     r8, [rsp+2C0h+var_270]
0x180014579  xor     r9d, r9d
0x18001457c  mov     qword ptr [rsp+2C0h+var_2A0], r12
0x180014581  lea     rdx, aPath; "path"
0x180014588  mov     rax, [rcx]
0x18001458b  mov     rax, [rax+40h]
0x18001458f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014594  mov     ebx, eax
0x180014596  test    eax, eax
0x180014598  js      loc_180014709
0x18001459e  lea     rdx, aRoot_0; "ROOT"
0x1800145a5  lea     rcx, [rsp+2C0h+var_268]
0x1800145aa  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800145b0  mov     ebx, eax
0x1800145b2  test    eax, eax
0x1800145b4  js      loc_180014709
0x1800145ba  mov     rdx, [rsp+2C0h+var_270]
0x1800145bf  lea     rcx, [rsp+2C0h+var_268]
0x1800145c4  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800145ca  mov     ebx, eax
0x1800145cc  test    eax, eax
0x1800145ce  js      loc_180014709
0x1800145d4  mov     rbx, [r15+10h]
0x1800145d8  lea     rcx, [rsp+2C0h+var_268]
0x1800145dd  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800145e3  lea     r9, [rsp+2C0h+var_278]; struct ABO_NODE **
0x1800145e8  mov     [rsp+2C0h+var_2A0], r12d; int
0x1800145ed  mov     rdx, rax; unsigned __int16 *
0x1800145f0  mov     r8d, 1; int
0x1800145f6  mov     rcx, rbx; this
0x1800145f9  call    ?CreateNode@ABO_NODE@@QEAAJPEBGHPEAPEAV1@H@Z; ABO_NODE::CreateNode(ushort const *,int,ABO_NODE * *,int)
0x1800145fe  mov     rdi, [rsp+2C0h+var_278]
0x180014603  mov     ebx, eax
0x180014605  test    eax, eax
0x180014607  js      loc_1800146FC
0x18001460d  mov     ecx, 68h ; 'h'; Size
0x180014612  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014617  test    rax, rax
0x18001461a  jz      loc_1800146F7
0x180014620  mov     r9, [r15+18h]; struct INativeConfigurationElement *
0x180014624  mov     rdx, rdi; struct ABO_NODE *
0x180014627  mov     r8, [rsp+2C0h+var_288]; struct INativeConfigurationElement *
0x18001462c  mov     rcx, rax; this
0x18001462f  call    ??0APPLICATION_CUSTOM_PROVIDER@@QEAA@PEAVABO_NODE@@PEAVINativeConfigurationElement@@1@Z; APPLICATION_CUSTOM_PROVIDER::APPLICATION_CUSTOM_PROVIDER(ABO_NODE *,INativeConfigurationElement *,INativeConfigurationElement *)
0x180014634  mov     rsi, rax
0x180014637  test    rax, rax
0x18001463a  jz      loc_1800146F7
0x180014640  mov     rcx, r15; this
0x180014643  call    ?QueryDefaultAppPoolName@SITE_CUSTOM_PROVIDER@@QEBAPEBGXZ; SITE_CUSTOM_PROVIDER::QueryDefaultAppPoolName(void)
0x180014648  mov     rdx, rax; unsigned __int16 *
0x18001464b  mov     rcx, rsi; this
0x18001464e  call    ?Create@APPLICATION_CUSTOM_PROVIDER@@QEAAJPEBG@Z; APPLICATION_CUSTOM_PROVIDER::Create(ushort const *)
0x180014653  mov     ebx, eax
0x180014655  mov     rcx, rsi; this
0x180014658  test    eax, eax
0x18001465a  js      loc_1800146F0
0x180014660  mov     rdx, rsi; struct CUSTOM_PROPERTY_PROVIDER *
0x180014663  mov     rcx, rdi; this
0x180014666  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x18001466b  mov     ebx, eax
0x18001466d  mov     rcx, rsi; this
0x180014670  test    eax, eax
0x180014672  js      short loc_1800146F0
0x180014674  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x180014679  mov     rcx, rdi; this
0x18001467c  call    ?GenerateNodesAndProperties@ABO_NODE@@QEAAJXZ; ABO_NODE::GenerateNodesAndProperties(void)
0x180014681  mov     ebx, eax
0x180014683  test    eax, eax
0x180014685  jns     short loc_1800146BD
0x180014687  lea     rcx, [rdi+38h]
0x18001468b  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180014691  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180014698  lea     rdx, aFailedToGenera_0; "Failed to generate Application Node and"...
0x18001469f  mov     r8, rax
0x1800146a2  mov     r9d, ebx
0x1800146a5  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x1800146aa  mov     dword ptr [rdi+0F4h], 3
0x1800146b4  mov     [rdi+0F8h], ebx
0x1800146ba  mov     ebx, r12d
0x1800146bd  mov     rcx, rdi; this
0x1800146c0  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x1800146c5  mov     rcx, [rsp+2C0h+var_288]
0x1800146ca  mov     [rsp+2C0h+var_278], r12
0x1800146cf  mov     rax, [rcx]
0x1800146d2  mov     rax, [rax+10h]
0x1800146d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146db  inc     r14d
0x1800146de  mov     [rsp+2C0h+var_288], r12
0x1800146e3  cmp     r14d, [rsp+2C0h+var_290]
0x1800146e8  jb      loc_18001454C
0x1800146ee  jmp     short loc_180014724
0x1800146f0  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x1800146f5  jmp     short loc_1800146FC
0x1800146f7  mov     ebx, 80070008h
0x1800146fc  test    rdi, rdi
0x1800146ff  jz      short loc_180014709
0x180014701  mov     rcx, rdi; this
0x180014704  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180014709  mov     rcx, [rsp+2C0h+var_288]
0x18001470e  test    rcx, rcx
0x180014711  jz      short loc_180014724
0x180014713  mov     rax, [rcx]
0x180014716  mov     rax, [rax+10h]
0x18001471a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001471f  mov     [rsp+2C0h+var_288], r12
0x180014724  mov     rcx, [rsp+2C0h+var_280]
0x180014729  test    rcx, rcx
0x18001472c  jz      short loc_18001473F
0x18001472e  mov     rax, [rcx]
0x180014731  mov     rax, [rax+10h]
0x180014735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001473a  mov     [rsp+2C0h+var_280], r12
0x18001473f  lea     rcx, [rsp+2C0h+var_268]
0x180014744  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001474a  mov     eax, ebx
0x18001474c  mov     rcx, [rbp+1C0h+var_30]
0x180014753  xor     rcx, rsp; StackCookie
0x180014756  call    __security_check_cookie
0x18001475b  lea     r11, [rsp+2C0h+var_20]
0x180014763  mov     rbx, [r11+38h]
0x180014767  mov     rsi, [r11+40h]
0x18001476b  mov     rsp, r11
0x18001476e  pop     r15
0x180014770  pop     r14
0x180014772  pop     r12
0x180014774  pop     rdi
0x180014775  pop     rbp
0x180014776  retn
```
