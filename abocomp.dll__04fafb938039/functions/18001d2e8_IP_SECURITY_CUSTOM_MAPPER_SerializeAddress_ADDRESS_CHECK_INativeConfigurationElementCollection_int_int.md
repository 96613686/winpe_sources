# IP_SECURITY_CUSTOM_MAPPER::SerializeAddress(ADDRESS_CHECK *,INativeConfigurationElementCollection *,int,int)

- ea: `0x18001d2e8`
- end: `0x18001d67f`
- name: `?SerializeAddress@IP_SECURITY_CUSTOM_MAPPER@@QEAAJPEAVADDRESS_CHECK@@PEAVINativeConfigurationElementCollection@@HH@Z`
- size: `919`
- prototype: `int(IP_SECURITY_CUSTOM_MAPPER *__hidden this, struct ADDRESS_CHECK *, struct INativeConfigurationElementCollection *, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800239e0`

## callees

- `0x18000341a`
- `0x180003460`
- `0x18001d2e8`
- `0x18002692c`
- `0x18002a938`
- `0x18002a9d4`
- `0x18002c010`

## import_xrefs

- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x18001d4da`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x18001d4da`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001d346`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001d371`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001d391`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001d346`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001d371`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001d391`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001d642`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001d64c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001d656`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001d642`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001d64c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001d656`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18001d41c`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18001d426`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18001d431`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18001d41c`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18001d426`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18001d431`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d556`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d594`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d5a7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d556`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d594`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d5a7`

## pseudocode

```c
__int64 __fastcall IP_SECURITY_CUSTOM_MAPPER::SerializeAddress(
        IP_SECURITY_CUSTOM_MAPPER *this,
        unsigned int **a2,
        struct INativeConfigurationElementCollection *a3,
        unsigned int a4,
        int a5)
{
  unsigned int *v8; // rdx
  int v9; // ebx
  unsigned int *v10; // rax
  __int64 v11; // rax
  unsigned int v12; // edi
  unsigned int v13; // esi
  int v14; // eax
  __int64 v15; // r8
  __int64 (__fastcall *v16)(__int64, const wchar_t *, unsigned __int16 *, _QWORD); // rbx
  unsigned __int16 *Str; // rax
  unsigned __int16 *v18; // rax
  const wchar_t *v19; // rdx
  __int64 v20; // rcx
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v23; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 *v24; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v25; // [rsp+48h] [rbp-B8h] BYREF
  char *v26; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v27; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v28[56]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v29[56]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v30[64]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v31[32]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v32[32]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v33[256]; // [rsp+190h] [rbp+90h] BYREF

  v22 = 0;
  memset_0(v31, 0, sizeof(v31));
  STRU::STRU((STRU *)v30, v31, 0x20u);
  memset_0(v33, 0, sizeof(v33));
  STRU::STRU((STRU *)v29, v33, 0x100u);
  memset_0(v32, 0, sizeof(v32));
  STRU::STRU((STRU *)v28, v32, 0x20u);
  v26 = 0;
  v25 = 0;
  v24 = 0;
  v23 = 2;
  if ( !a2 || !a3 )
  {
    v9 = -2147024809;
    goto LABEL_37;
  }
  v8 = *a2;
  v9 = 0;
  if ( a5 )
  {
    if ( v8 )
    {
      v10 = v8 + 1;
      if ( !a4 )
        v10 = *a2;
      v11 = *v10;
      goto LABEL_10;
    }
  }
  else if ( v8 )
  {
    v11 = *(unsigned int *)((char *)v8 + (a4 != 0 ? 4 : 0) + 8);
LABEL_10:
    LODWORD(v11) = v11 & 0x7FFFFFFF;
    v12 = *(unsigned int *)((char *)v8 + v11 + 4);
    goto LABEL_12;
  }
  v12 = 0;
LABEL_12:
  if ( v12 )
  {
    v13 = 0;
    while ( 1 )
    {
      STRU::Reset((STRU *)v29);
      STRU::Reset((STRU *)v30);
      STRU::Reset((STRU *)v28);
      if ( a5 )
      {
        if ( !(unsigned int)ADDRESS_CHECK::GetAddr((ADDRESS_CHECK *)a2, a4, v13, &v23, &v25, &v24) || v23 != 2 )
        {
LABEL_33:
          v20 = v22;
          goto LABEL_34;
        }
        v9 = DWordToIPStr(*(_DWORD *)v24, (struct STRU *)v30);
        if ( v9 < 0 )
          break;
        v14 = DWordToIPStr(*(_DWORD *)v25, (struct STRU *)v28);
      }
      else
      {
        if ( !(unsigned int)ADDRESS_CHECK::GetName((ADDRESS_CHECK *)a2, a4, v13, &v26, &v27) )
          goto LABEL_33;
        v15 = -1;
        do
          ++v15;
        while ( v26[v15] );
        v14 = STRU::CopyA((STRU *)v29, v26, v15);
      }
      v9 = v14;
      if ( v14 < 0 )
        break;
      v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, const wchar_t *, __int64 *))(*(_QWORD *)a3 + 48LL))(
             a3,
             L"add",
             &v22);
      if ( v9 < 0 )
        break;
      v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v22 + 136LL))(
             v22,
             L"allowed",
             a4,
             0);
      if ( v9 < 0 )
        break;
      v16 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, _QWORD))(*(_QWORD *)v22 + 128LL);
      if ( a5 )
      {
        Str = STRU::QueryStr((STRU *)v30);
        v9 = v16(v22, L"ipAddress", Str, 0);
        if ( v9 < 0 )
          break;
        v16 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, _QWORD))(*(_QWORD *)v22 + 128LL);
        v18 = STRU::QueryStr((STRU *)v28);
        v19 = L"subnetMask";
      }
      else
      {
        v18 = STRU::QueryStr((STRU *)v29);
        v19 = L"domainName";
      }
      v9 = v16(v22, v19, v18, 0);
      if ( v9 < 0 )
        break;
      v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, __int64, __int64, _QWORD))(*(_QWORD *)a3 + 56LL))(
             a3,
             v22,
             0xFFFFFFFFLL,
             0);
      if ( v9 < 0 )
        break;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      v20 = 0;
      v22 = 0;
LABEL_34:
      if ( ++v13 >= v12 )
        goto LABEL_38;
    }
  }
LABEL_37:
  v20 = v22;
LABEL_38:
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v22 = 0;
  }
  STRU::~STRU((STRU *)v28);
  STRU::~STRU((STRU *)v29);
  STRU::~STRU((STRU *)v30);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001d2e8  push    rbp
0x18001d2ea  push    rbx
0x18001d2eb  push    rsi
0x18001d2ec  push    rdi
0x18001d2ed  push    r13
0x18001d2ef  push    r14
0x18001d2f1  push    r15
0x18001d2f3  lea     rbp, [rsp-2A0h]
0x18001d2fb  sub     rsp, 3A0h
0x18001d302  mov     rax, cs:__security_cookie
0x18001d309  xor     rax, rsp
0x18001d30c  mov     [rbp+2D0h+var_40], rax
0x18001d313  mov     r15, r8
0x18001d316  mov     [rsp+3D0h+var_3A0], 0
0x18001d31f  mov     r13, rdx
0x18001d322  lea     rcx, [rbp+2D0h+var_2C0]; void *
0x18001d326  mov     edi, 40h ; '@'
0x18001d32b  xor     edx, edx; Val
0x18001d32d  mov     r8d, edi; Size
0x18001d330  mov     r14d, r9d
0x18001d333  call    memset_0
0x18001d338  lea     ebx, [rdi-20h]
0x18001d33b  mov     r8d, ebx
0x18001d33e  lea     rdx, [rbp+2D0h+var_2C0]
0x18001d342  lea     rcx, [rbp+2D0h+var_300]
0x18001d346  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001d34c  xor     edx, edx; Val
0x18001d34e  lea     rcx, [rbp+2D0h+var_240]; void *
0x18001d355  mov     r8d, 200h; Size
0x18001d35b  call    memset_0
0x18001d360  mov     r8d, 100h
0x18001d366  lea     rdx, [rbp+2D0h+var_240]
0x18001d36d  lea     rcx, [rbp+2D0h+var_338]
0x18001d371  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001d377  mov     r8d, edi; Size
0x18001d37a  lea     rcx, [rbp+2D0h+var_280]; void *
0x18001d37e  xor     edx, edx; Val
0x18001d380  call    memset_0
0x18001d385  mov     r8d, ebx
0x18001d388  lea     rdx, [rbp+2D0h+var_280]
0x18001d38c  lea     rcx, [rsp+3D0h+var_370]
0x18001d391  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001d397  mov     [rsp+3D0h+var_380], 0
0x18001d3a0  mov     [rsp+3D0h+var_388], 0
0x18001d3a9  mov     [rsp+3D0h+var_390], 0
0x18001d3b2  mov     [rsp+3D0h+var_398], 2
0x18001d3ba  test    r13, r13
0x18001d3bd  jz      loc_18001D619
0x18001d3c3  test    r15, r15
0x18001d3c6  jz      loc_18001D619
0x18001d3cc  mov     rdx, [r13+0]
0x18001d3d0  xor     ebx, ebx
0x18001d3d2  cmp     [rbp+2D0h+arg_20], ebx
0x18001d3d8  jz      short loc_18001D3EE
0x18001d3da  test    rdx, rdx
0x18001d3dd  jz      short loc_18001D40C
0x18001d3df  test    r14d, r14d
0x18001d3e2  lea     rax, [rdx+4]
0x18001d3e6  cmovz   rax, rdx
0x18001d3ea  mov     eax, [rax]
0x18001d3ec  jmp     short loc_18001D402
0x18001d3ee  test    rdx, rdx
0x18001d3f1  jz      short loc_18001D40C
0x18001d3f3  mov     eax, r14d
0x18001d3f6  neg     eax
0x18001d3f8  sbb     rcx, rcx
0x18001d3fb  and     ecx, 4
0x18001d3fe  mov     eax, [rcx+rdx+8]
0x18001d402  btr     eax, 1Fh
0x18001d406  mov     edi, [rax+rdx+4]
0x18001d40a  jmp     short loc_18001D40E
0x18001d40c  xor     edi, edi
0x18001d40e  test    edi, edi
0x18001d410  jz      loc_18001D61E
0x18001d416  xor     esi, esi
0x18001d418  lea     rcx, [rbp+2D0h+var_338]
0x18001d41c  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18001d422  lea     rcx, [rbp+2D0h+var_300]
0x18001d426  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18001d42c  lea     rcx, [rsp+3D0h+var_370]
0x18001d431  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18001d437  cmp     [rbp+2D0h+arg_20], 0
0x18001d43e  mov     r8d, esi; unsigned int
0x18001d441  mov     edx, r14d; int
0x18001d444  mov     rcx, r13; this
0x18001d447  jz      short loc_18001D4A7
0x18001d449  lea     rax, [rsp+3D0h+var_390]
0x18001d44e  mov     [rsp+3D0h+var_3A8], rax; unsigned __int8 **
0x18001d453  lea     r9, [rsp+3D0h+var_398]; unsigned int *
0x18001d458  lea     rax, [rsp+3D0h+var_388]
0x18001d45d  mov     [rsp+3D0h+var_3B0], rax; unsigned __int8 **
0x18001d462  call    ?GetAddr@ADDRESS_CHECK@@QEAAHHKPEAKPEAPEAE1@Z; ADDRESS_CHECK::GetAddr(int,ulong,ulong *,uchar * *,uchar * *)
0x18001d467  test    eax, eax
0x18001d469  jz      loc_18001D608
0x18001d46f  cmp     [rsp+3D0h+var_398], 2
0x18001d474  jnz     loc_18001D608
0x18001d47a  mov     rcx, [rsp+3D0h+var_390]
0x18001d47f  lea     rdx, [rbp+2D0h+var_300]; struct STRU *
0x18001d483  mov     ecx, [rcx]; unsigned int
0x18001d485  call    ?DWordToIPStr@@YAJKPEAVSTRU@@@Z; DWordToIPStr(ulong,STRU *)
0x18001d48a  mov     ebx, eax
0x18001d48c  test    eax, eax
0x18001d48e  js      loc_18001D61E
0x18001d494  mov     rcx, [rsp+3D0h+var_388]
0x18001d499  lea     rdx, [rsp+3D0h+var_370]; struct STRU *
0x18001d49e  mov     ecx, [rcx]; unsigned int
0x18001d4a0  call    ?DWordToIPStr@@YAJKPEAVSTRU@@@Z; DWordToIPStr(ulong,STRU *)
0x18001d4a5  jmp     short loc_18001D4E0
0x18001d4a7  lea     rax, [rsp+3D0h+var_378]
0x18001d4ac  lea     r9, [rsp+3D0h+var_380]; char **
0x18001d4b1  mov     [rsp+3D0h+var_3B0], rax; unsigned int *
0x18001d4b6  call    ?GetName@ADDRESS_CHECK@@QEAAHHKPEAPEADPEAK@Z; ADDRESS_CHECK::GetName(int,ulong,char * *,ulong *)
0x18001d4bb  test    eax, eax
0x18001d4bd  jz      loc_18001D608
0x18001d4c3  mov     rdx, [rsp+3D0h+var_380]
0x18001d4c8  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d4cc  inc     r8
0x18001d4cf  cmp     byte ptr [rdx+r8], 0
0x18001d4d4  jnz     short loc_18001D4CC
0x18001d4d6  lea     rcx, [rbp+2D0h+var_338]
0x18001d4da  call    cs:__imp_?CopyA@STRU@@QEAAJPEBDK@Z; STRU::CopyA(char const *,ulong)
0x18001d4e0  mov     ebx, eax
0x18001d4e2  test    eax, eax
0x18001d4e4  js      loc_18001D61E
0x18001d4ea  mov     rax, [r15]
0x18001d4ed  lea     r8, [rsp+3D0h+var_3A0]
0x18001d4f2  lea     rdx, aAdd; "add"
0x18001d4f9  mov     rcx, r15
0x18001d4fc  mov     rax, [rax+30h]
0x18001d500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d505  mov     ebx, eax
0x18001d507  test    eax, eax
0x18001d509  js      loc_18001D61E
0x18001d50f  mov     rcx, [rsp+3D0h+var_3A0]
0x18001d514  lea     rdx, aAllowed; "allowed"
0x18001d51b  xor     r9d, r9d
0x18001d51e  mov     r8d, r14d
0x18001d521  mov     rax, [rcx]
0x18001d524  mov     rax, [rax+88h]
0x18001d52b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d530  mov     ebx, eax
0x18001d532  test    eax, eax
0x18001d534  js      loc_18001D61E
0x18001d53a  cmp     [rbp+2D0h+arg_20], 0
0x18001d541  mov     rax, [rsp+3D0h+var_3A0]
0x18001d546  mov     rcx, [rax]
0x18001d549  mov     rbx, [rcx+80h]
0x18001d550  jz      short loc_18001D5A3
0x18001d552  lea     rcx, [rbp+2D0h+var_300]
0x18001d556  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d55c  mov     rcx, [rsp+3D0h+var_3A0]
0x18001d561  lea     rdx, aIpaddress; "ipAddress"
0x18001d568  mov     r8, rax
0x18001d56b  xor     r9d, r9d
0x18001d56e  mov     rax, rbx
0x18001d571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d576  mov     ebx, eax
0x18001d578  test    eax, eax
0x18001d57a  js      loc_18001D61E
0x18001d580  mov     rax, [rsp+3D0h+var_3A0]
0x18001d585  mov     rcx, [rax]
0x18001d588  mov     rbx, [rcx+80h]
0x18001d58f  lea     rcx, [rsp+3D0h+var_370]
0x18001d594  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d59a  lea     rdx, aSubnetmask; "subnetMask"
0x18001d5a1  jmp     short loc_18001D5B4
0x18001d5a3  lea     rcx, [rbp+2D0h+var_338]
0x18001d5a7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d5ad  lea     rdx, aDomainname; "domainName"
0x18001d5b4  mov     rcx, [rsp+3D0h+var_3A0]
0x18001d5b9  mov     r8, rax
0x18001d5bc  mov     rax, rbx
0x18001d5bf  xor     r9d, r9d
0x18001d5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5c7  mov     ebx, eax
0x18001d5c9  test    eax, eax
0x18001d5cb  js      short loc_18001D61E
0x18001d5cd  mov     rax, [r15]
0x18001d5d0  xor     r9d, r9d
0x18001d5d3  mov     rdx, [rsp+3D0h+var_3A0]
0x18001d5d8  or      r8d, 0FFFFFFFFh
0x18001d5dc  mov     rcx, r15
0x18001d5df  mov     rax, [rax+38h]
0x18001d5e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5e8  mov     ebx, eax
0x18001d5ea  test    eax, eax
0x18001d5ec  js      short loc_18001D61E
0x18001d5ee  mov     rcx, [rsp+3D0h+var_3A0]
0x18001d5f3  mov     rax, [rcx]
0x18001d5f6  mov     rax, [rax+10h]
0x18001d5fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5ff  xor     ecx, ecx
0x18001d601  mov     [rsp+3D0h+var_3A0], rcx
0x18001d606  jmp     short loc_18001D60D
0x18001d608  mov     rcx, [rsp+3D0h+var_3A0]
0x18001d60d  inc     esi
0x18001d60f  cmp     esi, edi
0x18001d611  jb      loc_18001D418
0x18001d617  jmp     short loc_18001D623
0x18001d619  mov     ebx, 80070057h
0x18001d61e  mov     rcx, [rsp+3D0h+var_3A0]
0x18001d623  test    rcx, rcx
0x18001d626  jz      short loc_18001D63D
0x18001d628  mov     rax, [rcx]
0x18001d62b  mov     rax, [rax+10h]
0x18001d62f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d634  mov     [rsp+3D0h+var_3A0], 0
0x18001d63d  lea     rcx, [rsp+3D0h+var_370]
0x18001d642  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001d648  lea     rcx, [rbp+2D0h+var_338]
0x18001d64c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001d652  lea     rcx, [rbp+2D0h+var_300]
0x18001d656  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001d65c  mov     eax, ebx
0x18001d65e  mov     rcx, [rbp+2D0h+var_40]
0x18001d665  xor     rcx, rsp; StackCookie
0x18001d668  call    __security_check_cookie
0x18001d66d  add     rsp, 3A0h
0x18001d674  pop     r15
0x18001d676  pop     r14
0x18001d678  pop     r13
0x18001d67a  pop     rdi
0x18001d67b  pop     rsi
0x18001d67c  pop     rbx
0x18001d67d  pop     rbp
0x18001d67e  retn
```
