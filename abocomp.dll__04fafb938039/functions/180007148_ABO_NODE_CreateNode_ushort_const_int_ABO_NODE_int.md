# ABO_NODE::CreateNode(ushort const *,int,ABO_NODE * *,int)

- ea: `0x180007148`
- end: `0x18000752a`
- name: `?CreateNode@ABO_NODE@@QEAAJPEBGHPEAPEAV1@H@Z`
- size: `994`
- prototype: `__int64 __usercall@<rax>(ABO_NODE *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, struct ABO_NODE **@<r9>, int)`
- caller_count: `11`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x1800044e0`
- `0x180004828`
- `0x180006f54`
- `0x18000b3c0`
- `0x18000bf00`
- `0x18000c560`
- `0x18000f110`
- `0x18000f390`
- `0x180014488`
- `0x18001a860`
- `0x180020890`

## callees

- `0x18000341a`
- `0x180003460`
- `0x18000473c`
- `0x180005e94`
- `0x180006484`
- `0x180006b78`
- `0x180007080`
- `0x180007148`
- `0x180007950`
- `0x180009ab0`
- `0x18000a8cc`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180007394`
- `msvcrt!_wcsicmp` at `0x180007418`
- `msvcrt!_wcsicmp` at `0x1800074d7`
- `msvcrt!_wcsicmp` at `0x180007394`
- `msvcrt!_wcsicmp` at `0x180007418`
- `msvcrt!_wcsicmp` at `0x1800074d7`
- `msvcrt!wcschr` at `0x180007261`
- `msvcrt!wcschr` at `0x180007261`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007221`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800072b1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800072cf`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000734e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007221`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800072b1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800072cf`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000734e`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180007388`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180007408`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800074c7`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180007388`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180007408`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800074c7`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800073b7`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800073b7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800071aa`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800071d0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800071f5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800071aa`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800071d0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800071f5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800072ff`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000730a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007315`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800072ff`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000730a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007315`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18000735f`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18000735f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007254`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007278`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000728c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800072c1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007340`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007373`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800073e9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007254`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007278`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000728c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800072c1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007340`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007373`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800073e9`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180007241`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800074b9`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800074f5`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180007241`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800074b9`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800074f5`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000729d`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000729d`

## pseudocode

```c
__int64 __fastcall ABO_NODE::CreateNode(
        struct ABO_TREE **this,
        const unsigned __int16 *a2,
        int a3,
        struct ABO_NODE **a4,
        int a5)
{
  int v5; // r15d
  int v9; // edi
  const unsigned __int16 *v10; // rdx
  ABO_NODE *v11; // rsi
  const wchar_t *Str; // rax
  wchar_t *v13; // rax
  wchar_t *v14; // r14
  __int64 v15; // rbx
  const unsigned __int16 *v16; // rax
  const unsigned __int16 *v17; // rax
  ABO_NODE *v18; // rbx
  const unsigned __int16 *v20; // rax
  __int64 v21; // r14
  const wchar_t *v22; // rbx
  const wchar_t *v23; // rax
  ABO_NODE *v24; // rax
  const unsigned __int16 *v25; // rax
  const wchar_t *v26; // rax
  const wchar_t *v27; // rax
  _BYTE v29[56]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v30[56]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v31[56]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v32[256]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v33[256]; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int16 v34[256]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v5 = a3;
  memset_0(v32, 0, sizeof(v32));
  STRU::STRU((STRU *)v30, v32, 0x100u);
  memset_0(v33, 0, sizeof(v33));
  STRU::STRU((STRU *)v29, v33, 0x100u);
  memset_0(v34, 0, sizeof(v34));
  STRU::STRU((STRU *)v31, v34, 0x100u);
  if ( !a2 )
  {
    v9 = -2147024809;
    goto LABEL_16;
  }
  v10 = a2 + 1;
  if ( *a2 != 47 )
    v10 = a2;
  v9 = STRU::Copy((STRU *)v29, v10);
  if ( v9 >= 0 )
  {
    v11 = (ABO_NODE *)this;
    ABO_NODE::ReferenceAboNode((ABO_NODE *)this);
    while ( !STRU::IsEmpty((STRU *)v29) )
    {
      Str = STRU::QueryStr((STRU *)v29);
      v13 = wcschr(Str, 0x2Fu);
      v14 = v13;
      if ( v13 )
      {
        v15 = v13 - STRU::QueryStr((STRU *)v29);
        v16 = STRU::QueryStr((STRU *)v29);
        v9 = STRU::Copy((STRU *)v30, v16, v15);
        if ( v9 < 0 )
          goto LABEL_11;
        v9 = STRU::Copy((STRU *)v31, v14 + 1);
        if ( v9 < 0 )
          goto LABEL_11;
        v17 = STRU::QueryStr((STRU *)v31);
        v9 = STRU::Copy((STRU *)v29, v17);
        if ( v9 < 0 )
          goto LABEL_11;
      }
      else
      {
        v20 = STRU::QueryStr((STRU *)v29);
        v9 = STRU::Copy((STRU *)v30, v20);
        if ( v9 < 0 )
          goto LABEL_11;
        STRU::Reset((STRU *)v29);
      }
      v21 = 0;
      if ( *((_DWORD *)v11 + 10) )
      {
        while ( 1 )
        {
          v22 = STRU::QueryStr((STRU *)v30);
          v23 = STRU::QueryStr((STRU *)(*(_QWORD *)(*((_QWORD *)v11 + 4) + 8 * v21) + 56LL));
          if ( !_wcsicmp(v23, v22) )
            break;
          v21 = (unsigned int)(v21 + 1);
          if ( (unsigned int)v21 >= *((_DWORD *)v11 + 10) )
          {
            v5 = a3;
            goto LABEL_23;
          }
        }
        ABO_NODE::DereferenceAboNode(v11);
        v11 = *(ABO_NODE **)(*((_QWORD *)v11 + 4) + 8 * v21);
        ABO_NODE::ReferenceAboNode(v11);
        if ( a5 )
        {
          if ( STRU::IsEmpty((STRU *)v29) )
          {
            v27 = STRU::QueryStr((ABO_NODE *)((char *)v11 + 56));
            if ( _wcsicmp(v27, L"ROOT") )
            {
              v9 = -2147024713;
LABEL_11:
              v18 = 0;
              goto LABEL_12;
            }
          }
        }
        v5 = a3;
      }
      else
      {
LABEL_23:
        v24 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
        if ( !v24 )
        {
          v18 = 0;
LABEL_41:
          v9 = -2147024888;
LABEL_12:
          if ( v11 )
            ABO_NODE::DereferenceAboNode(v11);
          if ( v18 )
            ABO_NODE::DereferenceAboNode(v18);
          goto LABEL_16;
        }
        v18 = ABO_NODE::ABO_NODE(v24, this[22], v5);
        if ( !v18 )
          goto LABEL_41;
        v25 = STRU::QueryStr((STRU *)v30);
        v9 = ABO_NODE::Create(v18, v25);
        if ( v9 < 0 )
          goto LABEL_12;
        v26 = STRU::QueryStr((ABO_NODE *)((char *)v18 + 56));
        if ( !_wcsicmp(v26, L"ROOT") )
        {
          if ( (unsigned int)ABO_NODE::FSiteNode(v11) )
          {
            v9 = ABO_NODE::SetDefaultKeyType(v18, L"IIsWebVirtualDir");
            if ( v9 < 0 )
              goto LABEL_12;
          }
        }
        v9 = ABO_NODE::AddChildNode(v11, v18);
        if ( v9 < 0 )
          goto LABEL_12;
        if ( !v5 )
        {
          v9 = ABO_NODE::MapAddKey(v11, v18);
          if ( v9 < 0 )
            goto LABEL_12;
        }
        ABO_NODE::DereferenceAboNode(v11);
        v11 = v18;
        ABO_NODE::ReferenceAboNode(v18);
        ABO_NODE::DereferenceAboNode(v18);
      }
    }
    v18 = 0;
    if ( !a4 )
      goto LABEL_12;
    *a4 = v11;
  }
LABEL_16:
  STRU::~STRU((STRU *)v31);
  STRU::~STRU((STRU *)v29);
  STRU::~STRU((STRU *)v30);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180007148  push    rbp
0x18000714a  push    rbx
0x18000714b  push    rsi
0x18000714c  push    rdi
0x18000714d  push    r12
0x18000714f  push    r13
0x180007151  push    r14
0x180007153  push    r15
0x180007155  lea     rbp, [rsp-5E8h]
0x18000715d  sub     rsp, 6E8h
0x180007164  mov     rax, cs:__security_cookie
0x18000716b  xor     rax, rsp
0x18000716e  mov     [rbp+620h+var_50], rax
0x180007175  mov     r15d, r8d
0x180007178  mov     [rsp+720h+var_700], r8d
0x18000717d  mov     rbx, rdx
0x180007180  mov     r13, rcx
0x180007183  mov     esi, 200h
0x180007188  lea     rcx, [rbp+620h+var_650]; void *
0x18000718c  mov     r8d, esi; Size
0x18000718f  xor     edx, edx; Val
0x180007191  mov     r12, r9
0x180007194  call    memset_0
0x180007199  mov     edi, 100h
0x18000719e  lea     rdx, [rbp+620h+var_650]
0x1800071a2  mov     r8d, edi
0x1800071a5  lea     rcx, [rsp+720h+var_6C0]
0x1800071aa  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800071b0  mov     r8d, esi; Size
0x1800071b3  lea     rcx, [rbp+620h+var_450]; void *
0x1800071ba  xor     edx, edx; Val
0x1800071bc  call    memset_0
0x1800071c1  mov     r8d, edi
0x1800071c4  lea     rdx, [rbp+620h+var_450]
0x1800071cb  lea     rcx, [rsp+720h+var_6F8]
0x1800071d0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800071d6  mov     r8d, esi; Size
0x1800071d9  lea     rcx, [rbp+620h+var_250]; void *
0x1800071e0  xor     edx, edx; Val
0x1800071e2  call    memset_0
0x1800071e7  mov     r8d, edi
0x1800071ea  lea     rdx, [rbp+620h+var_250]
0x1800071f1  lea     rcx, [rbp+620h+var_688]
0x1800071f5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800071fb  test    rbx, rbx
0x1800071fe  jnz     short loc_18000720A
0x180007200  mov     edi, 80070057h
0x180007205  jmp     loc_1800072FB
0x18000720a  mov     r14d, 2Fh ; '/'
0x180007210  lea     rdx, [rbx+2]
0x180007214  cmp     [rbx], r14w
0x180007218  lea     rcx, [rsp+720h+var_6F8]
0x18000721d  cmovnz  rdx, rbx
0x180007221  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180007227  mov     edi, eax
0x180007229  test    eax, eax
0x18000722b  js      loc_1800072FB
0x180007231  mov     rcx, r13; this
0x180007234  mov     rsi, r13
0x180007237  call    ?ReferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::ReferenceAboNode(void)
0x18000723c  lea     rcx, [rsp+720h+var_6F8]
0x180007241  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180007247  test    al, al
0x180007249  jnz     loc_180007516
0x18000724f  lea     rcx, [rsp+720h+var_6F8]
0x180007254  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000725a  mov     rcx, rax; Str
0x18000725d  movzx   edx, r14w; Ch
0x180007261  call    cs:__imp_wcschr
0x180007267  lea     rcx, [rsp+720h+var_6F8]
0x18000726c  mov     r14, rax
0x18000726f  test    rax, rax
0x180007272  jz      loc_180007340
0x180007278  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000727e  mov     rbx, r14
0x180007281  lea     rcx, [rsp+720h+var_6F8]
0x180007286  sub     rbx, rax
0x180007289  sar     rbx, 1
0x18000728c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180007292  mov     r8d, ebx
0x180007295  lea     rcx, [rsp+720h+var_6C0]
0x18000729a  mov     rdx, rax
0x18000729d  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800072a3  mov     edi, eax
0x1800072a5  test    eax, eax
0x1800072a7  js      short loc_1800072DF
0x1800072a9  lea     rdx, [r14+2]
0x1800072ad  lea     rcx, [rbp+620h+var_688]
0x1800072b1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800072b7  mov     edi, eax
0x1800072b9  test    eax, eax
0x1800072bb  js      short loc_1800072DF
0x1800072bd  lea     rcx, [rbp+620h+var_688]
0x1800072c1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800072c7  mov     rdx, rax
0x1800072ca  lea     rcx, [rsp+720h+var_6F8]
0x1800072cf  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800072d5  mov     edi, eax
0x1800072d7  test    eax, eax
0x1800072d9  jns     loc_180007365
0x1800072df  xor     ebx, ebx
0x1800072e1  test    rsi, rsi
0x1800072e4  jz      short loc_1800072EE
0x1800072e6  mov     rcx, rsi; this
0x1800072e9  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x1800072ee  test    rbx, rbx
0x1800072f1  jz      short loc_1800072FB
0x1800072f3  mov     rcx, rbx; this
0x1800072f6  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x1800072fb  lea     rcx, [rbp+620h+var_688]
0x1800072ff  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007305  lea     rcx, [rsp+720h+var_6F8]
0x18000730a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007310  lea     rcx, [rsp+720h+var_6C0]
0x180007315  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000731b  mov     eax, edi
0x18000731d  mov     rcx, [rbp+620h+var_50]
0x180007324  xor     rcx, rsp; StackCookie
0x180007327  call    __security_check_cookie
0x18000732c  add     rsp, 6E8h
0x180007333  pop     r15
0x180007335  pop     r14
0x180007337  pop     r13
0x180007339  pop     r12
0x18000733b  pop     rdi
0x18000733c  pop     rsi
0x18000733d  pop     rbx
0x18000733e  pop     rbp
0x18000733f  retn
0x180007340  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180007346  mov     rdx, rax
0x180007349  lea     rcx, [rsp+720h+var_6C0]
0x18000734e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180007354  mov     edi, eax
0x180007356  test    eax, eax
0x180007358  js      short loc_1800072DF
0x18000735a  lea     rcx, [rsp+720h+var_6F8]
0x18000735f  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x180007365  xor     r14d, r14d
0x180007368  cmp     [rsi+28h], r14d
0x18000736c  jbe     short loc_1800073B0
0x18000736e  lea     rcx, [rsp+720h+var_6C0]
0x180007373  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180007379  mov     rcx, [rsi+20h]
0x18000737d  mov     rbx, rax
0x180007380  mov     rcx, [rcx+r14*8]
0x180007384  add     rcx, 38h ; '8'
0x180007388  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18000738e  mov     rcx, rax; String1
0x180007391  mov     rdx, rbx; String2
0x180007394  call    cs:__imp__wcsicmp
0x18000739a  test    eax, eax
0x18000739c  jz      loc_180007493
0x1800073a2  inc     r14d
0x1800073a5  cmp     r14d, [rsi+28h]
0x1800073a9  jb      short loc_18000736E
0x1800073ab  mov     r15d, [rsp+720h+var_700]
0x1800073b0  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x1800073b7  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x1800073bd  test    rax, rax
0x1800073c0  jz      loc_18000750A
0x1800073c6  mov     rdx, [r13+0B0h]; struct ABO_TREE *
0x1800073cd  mov     r8d, r15d; int
0x1800073d0  mov     rcx, rax; this
0x1800073d3  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z; ABO_NODE::ABO_NODE(ABO_TREE *,int)
0x1800073d8  mov     rbx, rax
0x1800073db  test    rax, rax
0x1800073de  jz      loc_18000750C
0x1800073e4  lea     rcx, [rsp+720h+var_6C0]
0x1800073e9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800073ef  mov     rdx, rax; unsigned __int16 *
0x1800073f2  mov     rcx, rbx; this
0x1800073f5  call    ?Create@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::Create(ushort const *)
0x1800073fa  mov     edi, eax
0x1800073fc  test    eax, eax
0x1800073fe  js      loc_1800072E1
0x180007404  lea     rcx, [rbx+38h]
0x180007408  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18000740e  mov     rcx, rax; String1
0x180007411  lea     rdx, aRoot_0; "ROOT"
0x180007418  call    cs:__imp__wcsicmp
0x18000741e  test    eax, eax
0x180007420  jnz     short loc_180007447
0x180007422  mov     rcx, rsi; this
0x180007425  call    ?FSiteNode@ABO_NODE@@QEAAHXZ; ABO_NODE::FSiteNode(void)
0x18000742a  test    eax, eax
0x18000742c  jz      short loc_180007447
0x18000742e  lea     rdx, aIiswebvirtuald; "IIsWebVirtualDir"
0x180007435  mov     rcx, rbx; this
0x180007438  call    ?SetDefaultKeyType@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::SetDefaultKeyType(ushort const *)
0x18000743d  mov     edi, eax
0x18000743f  test    eax, eax
0x180007441  js      loc_1800072E1
0x180007447  mov     rdx, rbx; struct ABO_NODE *
0x18000744a  mov     rcx, rsi; this
0x18000744d  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::AddChildNode(ABO_NODE *)
0x180007452  mov     edi, eax
0x180007454  test    eax, eax
0x180007456  js      loc_1800072E1
0x18000745c  test    r15d, r15d
0x18000745f  jnz     short loc_180007476
0x180007461  mov     rdx, rbx; struct ABO_NODE *
0x180007464  mov     rcx, rsi; this
0x180007467  call    ?MapAddKey@ABO_NODE@@AEAAJPEAV1@@Z; ABO_NODE::MapAddKey(ABO_NODE *)
0x18000746c  mov     edi, eax
0x18000746e  test    eax, eax
0x180007470  js      loc_1800072E1
0x180007476  mov     rcx, rsi; this
0x180007479  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000747e  mov     rcx, rbx; this
0x180007481  mov     rsi, rbx
0x180007484  call    ?ReferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::ReferenceAboNode(void)
0x180007489  mov     rcx, rbx; this
0x18000748c  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180007491  jmp     short loc_1800074F0
0x180007493  mov     rcx, rsi; this
0x180007496  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000749b  mov     rax, [rsi+20h]
0x18000749f  mov     rsi, [rax+r14*8]
0x1800074a3  mov     rcx, rsi; this
0x1800074a6  call    ?ReferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::ReferenceAboNode(void)
0x1800074ab  cmp     [rbp+620h+arg_20], 0
0x1800074b2  jz      short loc_1800074EB
0x1800074b4  lea     rcx, [rsp+720h+var_6F8]
0x1800074b9  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x1800074bf  test    al, al
0x1800074c1  jz      short loc_1800074EB
0x1800074c3  lea     rcx, [rsi+38h]
0x1800074c7  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800074cd  mov     rcx, rax; String1
0x1800074d0  lea     rdx, aRoot_0; "ROOT"
0x1800074d7  call    cs:__imp__wcsicmp
0x1800074dd  test    eax, eax
0x1800074df  jz      short loc_1800074EB
0x1800074e1  mov     edi, 800700B7h
0x1800074e6  jmp     loc_1800072DF
0x1800074eb  mov     r15d, [rsp+720h+var_700]
0x1800074f0  lea     rcx, [rsp+720h+var_6F8]
0x1800074f5  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x1800074fb  test    al, al
0x1800074fd  jnz     short loc_180007516
0x1800074ff  mov     r14d, 2Fh ; '/'
0x180007505  jmp     loc_18000724F
0x18000750a  xor     ebx, ebx
0x18000750c  mov     edi, 80070008h
0x180007511  jmp     loc_1800072E1
0x180007516  xor     ebx, ebx
0x180007518  test    r12, r12
0x18000751b  jz      loc_1800072E1
0x180007521  mov     [r12], rsi
0x180007525  jmp     loc_1800072FB
```
