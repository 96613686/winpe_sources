# CERT_MANYTO1_MAPPER::Match(_CERT_CONTEXT const *,int *,STRU *,STRU *,int *)

- ea: `0x180003824`
- end: `0x1800039de`
- name: `?Match@CERT_MANYTO1_MAPPER@@QEAAJPEBU_CERT_CONTEXT@@PEAHPEAVSTRU@@21@Z`
- size: `442`
- prototype: `__int64 __fastcall(CERT_MANYTO1_MAPPER *__hidden this, const struct _CERT_CONTEXT *, int *, struct STRU *, struct STRU *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001da0`

## callees

- `0x180003628`
- `0x180003824`
- `0x1800039e4`
- `0x180006d92`
- `0x180006dd0`

## import_xrefs

- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800038bd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800038bd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003909`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003935`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003909`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003935`
- `iisutil!DecryptMemoryPassword` at `0x180003920`
- `iisutil!DecryptMemoryPassword` at `0x180003920`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003971`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003971`

## pseudocode

```c
__int64 __fastcall CERT_MANYTO1_MAPPER::Match(
        CERT_MANYTO1_MAPPER *this,
        const struct _CERT_CONTEXT *a2,
        int *a3,
        struct STRU *a4,
        struct STRU *a5,
        int *a6)
{
  char *v6; // r13
  char *v7; // rdi
  int v9; // r15d
  CERT_MAP_RULE_ELEMENT *i; // rsi
  int v11; // ebx
  __int64 v12; // rcx
  const unsigned __int16 *v13; // rax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  STRU *v16; // [rsp+28h] [rbp-D8h]
  STRU *v17; // [rsp+30h] [rbp-D0h]
  int *v18; // [rsp+38h] [rbp-C8h]
  _QWORD v19[5]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v20; // [rsp+68h] [rbp-98h]
  __int128 v21; // [rsp+78h] [rbp-88h]
  _BYTE v22[32]; // [rsp+90h] [rbp-70h] BYREF
  const unsigned __int16 *v23; // [rsp+B0h] [rbp-50h]
  int v24; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v25[256]; // [rsp+D0h] [rbp-30h] BYREF

  v6 = (char *)this + 8;
  v7 = (char *)*((_QWORD *)this + 1);
  v17 = a5;
  v9 = 0;
  v18 = a6;
  v16 = a4;
  v20 = 0;
  v19[0] = a2;
  v21 = 0;
  while ( 1 )
  {
    if ( v7 == v6 )
    {
      *a3 = 0;
      goto LABEL_20;
    }
    v15 = 0;
    memset_0(v25, 0, sizeof(v25));
    STRU::STRU((STRU *)v22, v25, 0x100u);
    for ( i = (CERT_MAP_RULE_ELEMENT *)*((_QWORD *)v7 + 33);
          i != (CERT_MAP_RULE_ELEMENT *)(v7 + 264);
          i = *(CERT_MAP_RULE_ELEMENT **)i )
    {
      v11 = CERT_MAP_RULE_ELEMENT::Match(i, (struct DECODED_CERT *)v19, &v15);
      if ( v11 < 0 )
        goto LABEL_12;
      if ( !v15 )
      {
        v9 = 0;
        goto LABEL_11;
      }
    }
    v9 = 1;
    v11 = STRU::Copy(v16, *((const unsigned __int16 **)v7 + 6));
    if ( v11 >= 0 )
    {
      v11 = DecryptMemoryPassword((struct STRU *)(v7 + 136), (struct STRU *)v22);
      if ( v11 >= 0 )
      {
        v11 = STRU::Copy(v17, v23);
        if ( v11 >= 0 )
        {
          *v18 = *((_DWORD *)v7 + 64);
LABEL_11:
          v11 = 0;
        }
      }
    }
LABEL_12:
    if ( v24 )
    {
      v12 = (unsigned int)(2 * v24);
      v13 = v23;
      if ( 2 * v24 )
      {
        do
        {
          *(_BYTE *)v13 = 0;
          v13 = (const unsigned __int16 *)((char *)v13 + 1);
          --v12;
        }
        while ( v12 );
      }
    }
    STRU::~STRU((STRU *)v22);
    if ( v11 < 0 )
      goto LABEL_21;
    if ( v9 )
      break;
    v7 = *(char **)v7;
  }
  *a3 = 1;
LABEL_20:
  v11 = 0;
LABEL_21:
  DECODED_CERT::~DECODED_CERT((DECODED_CERT *)v19);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180003824  mov     [rsp-8+arg_8], rbx
0x180003829  push    rbp
0x18000382a  push    rsi
0x18000382b  push    rdi
0x18000382c  push    r12
0x18000382e  push    r13
0x180003830  push    r14
0x180003832  push    r15
0x180003834  lea     rbp, [rsp-1E0h]
0x18000383c  sub     rsp, 2E0h
0x180003843  mov     rax, cs:__security_cookie
0x18000384a  xor     rax, rsp
0x18000384d  mov     [rbp+210h+var_40], rax
0x180003854  mov     rax, [rbp+210h+arg_20]
0x18000385b  lea     r13, [rcx+8]
0x18000385f  mov     rdi, [r13+0]
0x180003863  xorps   xmm0, xmm0
0x180003866  mov     [rsp+310h+var_2E0], rax
0x18000386b  mov     r12, r8
0x18000386e  mov     rax, [rbp+210h+arg_28]
0x180003875  xor     r15d, r15d
0x180003878  mov     [rsp+310h+var_2D8], rax
0x18000387d  mov     [rsp+310h+var_2E8], r9
0x180003882  movups  [rsp+310h+var_2A8], xmm0
0x180003887  mov     [rsp+310h+var_2D0], rdx
0x18000388c  movups  [rsp+310h+var_298], xmm0
0x180003891  jmp     loc_180003983
0x180003896  xor     edx, edx; Val
0x180003898  mov     [rsp+310h+var_2F0], 0
0x1800038a0  mov     r8d, 200h; Size
0x1800038a6  lea     rcx, [rbp+210h+var_240]; void *
0x1800038aa  call    memset_0
0x1800038af  mov     r8d, 100h
0x1800038b5  lea     rdx, [rbp+210h+var_240]
0x1800038b9  lea     rcx, [rbp+210h+var_280]
0x1800038bd  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800038c3  lea     r14, [rdi+108h]
0x1800038ca  mov     rsi, [r14]
0x1800038cd  jmp     short loc_1800038F5
0x1800038cf  lea     r8, [rsp+310h+var_2F0]; int *
0x1800038d4  mov     rcx, rsi; this
0x1800038d7  lea     rdx, [rsp+310h+var_2D0]; struct DECODED_CERT *
0x1800038dc  call    ?Match@CERT_MAP_RULE_ELEMENT@@QEAAJPEAVDECODED_CERT@@PEAH@Z; CERT_MAP_RULE_ELEMENT::Match(DECODED_CERT *,int *)
0x1800038e1  mov     ebx, eax
0x1800038e3  test    eax, eax
0x1800038e5  js      short loc_180003950
0x1800038e7  cmp     [rsp+310h+var_2F0], 0
0x1800038ec  jz      loc_1800039CC
0x1800038f2  mov     rsi, [rsi]
0x1800038f5  cmp     rsi, r14
0x1800038f8  jnz     short loc_1800038CF
0x1800038fa  mov     rdx, [rdi+30h]
0x1800038fe  mov     r15d, 1
0x180003904  mov     rcx, [rsp+310h+var_2E8]
0x180003909  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000390f  mov     ebx, eax
0x180003911  test    eax, eax
0x180003913  js      short loc_180003950
0x180003915  lea     rcx, [rdi+88h]
0x18000391c  lea     rdx, [rbp+210h+var_280]
0x180003920  call    cs:__imp_?DecryptMemoryPassword@@YAJPEAVSTRU@@0@Z; DecryptMemoryPassword(STRU *,STRU *)
0x180003926  mov     ebx, eax
0x180003928  test    eax, eax
0x18000392a  js      short loc_180003950
0x18000392c  mov     rdx, [rbp+210h+var_260]
0x180003930  mov     rcx, [rsp+310h+var_2E0]
0x180003935  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000393b  mov     ebx, eax
0x18000393d  test    eax, eax
0x18000393f  js      short loc_180003950
0x180003941  mov     rcx, [rsp+310h+var_2D8]
0x180003946  mov     eax, [rdi+100h]
0x18000394c  mov     [rcx], eax
0x18000394e  xor     ebx, ebx
0x180003950  mov     eax, [rbp+210h+var_250]
0x180003953  test    eax, eax
0x180003955  jz      short loc_18000396D
0x180003957  add     eax, eax
0x180003959  mov     ecx, eax
0x18000395b  mov     rax, [rbp+210h+var_260]
0x18000395f  jz      short loc_18000396D
0x180003961  mov     byte ptr [rax], 0
0x180003964  inc     rax
0x180003967  sub     rcx, 1
0x18000396b  jnz     short loc_180003961
0x18000396d  lea     rcx, [rbp+210h+var_280]
0x180003971  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003977  test    ebx, ebx
0x180003979  js      short loc_180003996
0x18000397b  test    r15d, r15d
0x18000397e  jnz     short loc_1800039D4
0x180003980  mov     rdi, [rdi]
0x180003983  cmp     rdi, r13
0x180003986  jnz     loc_180003896
0x18000398c  mov     dword ptr [r12], 0
0x180003994  xor     ebx, ebx
0x180003996  lea     rcx, [rsp+310h+var_2D0]; this
0x18000399b  call    ??1DECODED_CERT@@QEAA@XZ; DECODED_CERT::~DECODED_CERT(void)
0x1800039a0  mov     eax, ebx
0x1800039a2  mov     rcx, [rbp+210h+var_40]
0x1800039a9  xor     rcx, rsp; StackCookie
0x1800039ac  call    __security_check_cookie
0x1800039b1  mov     rbx, [rsp+310h+arg_8]
0x1800039b9  add     rsp, 2E0h
0x1800039c0  pop     r15
0x1800039c2  pop     r14
0x1800039c4  pop     r13
0x1800039c6  pop     r12
0x1800039c8  pop     rdi
0x1800039c9  pop     rsi
0x1800039ca  pop     rbp
0x1800039cb  retn
0x1800039cc  xor     r15d, r15d
0x1800039cf  jmp     loc_18000394E
0x1800039d4  mov     dword ptr [r12], 1
0x1800039dc  jmp     short loc_180003994
```
