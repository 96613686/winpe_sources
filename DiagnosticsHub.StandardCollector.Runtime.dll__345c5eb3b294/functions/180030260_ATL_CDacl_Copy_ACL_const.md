# ATL::CDacl::Copy(_ACL const &)

- ea: `0x180030260`
- end: `0x18003064d`
- name: `?Copy@CDacl@ATL@@AEAAXAEBU_ACL@@@Z`
- size: `1005`
- prototype: `void(ATL::CDacl *__hidden this, const struct _ACL *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180030650`

## callees

- `0x180002604`
- `0x18002fe28`
- `0x180030260`
- `0x180030844`
- `0x180031094`
- `0x180031264`
- `0x1800315c8`
- `0x1800316c4`
- `0x180049b50`
- `0x18004a03c`
- `0x18004a078`
- `0x18004a1c0`
- `0x18004ad26`
- `0x18004b640`

## import_xrefs

- `ADVAPI32!GetAce` at `0x180030371`
- `ADVAPI32!GetAce` at `0x180030371`
- `ADVAPI32!GetAclInformation` at `0x18003031d`
- `ADVAPI32!GetAclInformation` at `0x18003033b`
- `ADVAPI32!GetAclInformation` at `0x18003031d`
- `ADVAPI32!GetAclInformation` at `0x18003033b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180030303`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180030303`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ATL::CDacl::Copy(ATL::CDacl *this, struct _ACL *a2)
{
  ATL::CDacl *v3; // r14
  DWORD i; // r12d
  int v5; // r13d
  _OWORD *v6; // r15
  _OWORD *v7; // rbx
  char *v8; // rcx
  _QWORD *v9; // rsi
  _OWORD *v10; // rax
  _OWORD *v11; // rax
  unsigned __int64 v12; // r13
  ATL::CDacl::CAccessAce *v13; // r15
  unsigned __int64 v14; // r13
  _QWORD *v15; // [rsp+38h] [rbp-100h]
  ATL::CDacl::CAccessAce *v16; // [rsp+38h] [rbp-100h]
  void *v19; // [rsp+50h] [rbp-E8h]
  LPVOID pAce; // [rsp+58h] [rbp-E0h] BYREF
  int v21; // [rsp+60h] [rbp-D8h] BYREF
  DWORD pAclInformation[6]; // [rsp+68h] [rbp-D0h] BYREF
  _BYTE v23[128]; // [rsp+80h] [rbp-B8h] BYREF

  v3 = this;
  if ( !a2 )
  {
    (*(void (__fastcall **)(ATL::CDacl *))(*(_QWORD *)this + 16LL))(this);
    *((_BYTE *)v3 + 16) = 1;
    return;
  }
  memset_0(v23, 0, 0x78u);
  ATL::CSid::CSid((ATL::CSid *)v23);
  free(*((void **)v3 + 1));
  *((_QWORD *)v3 + 1) = 0;
  if ( !GetAclInformation(a2, pAclInformation, 0xCu, AclSizeInformation)
    || !GetAclInformation(a2, &v21, 4u, AclRevisionInformation) )
  {
LABEL_37:
    ATL::AtlThrowLastWin32();
  }
  *((_DWORD *)v3 + 5) = v21;
  for ( i = 0; i < pAclInformation[0]; ++i )
  {
    if ( !GetAce(a2, i, &pAce) )
      goto LABEL_37;
    v5 = *((_DWORD *)pAce + 1);
    if ( !*(_BYTE *)pAce || *(_BYTE *)pAce == 1 )
    {
      ATL::CSid::operator=((__int64)v23, (char *)pAce + 8);
      try
      {
        v19 = operator new(0x98u);
        memset_0(v19, 0, 0x98u);
        v13 = ATL::CDacl::CAccessAce::CAccessAce(
                (ATL::CDacl::CAccessAce *)v19,
                (const struct ATL::CSid *)v23,
                v5,
                *((_BYTE *)pAce + 1),
                *(_BYTE *)pAce == 0);
        v16 = v13;
      }
      catch ( ... )
      {
        v13 = v16;
        v3 = this;
      }
      if ( !v13
        || (v14 = *((_QWORD *)v3 + 4), v14 >= *((_QWORD *)v3 + 5))
        && (_mm_lfence(),
            !(unsigned __int8)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
                                (char *)v3 + 24,
                                v14 + 1)) )
      {
LABEL_40:
        ATL::AtlThrowImpl(-2147024882);
      }
      *(_QWORD *)(*((_QWORD *)v3 + 3) + 8 * v14) = v13;
    }
    else
    {
      if ( (unsigned int)*(unsigned __int8 *)pAce - 5 > 1 )
        continue;
      v6 = 0;
      v7 = 0;
      v8 = (char *)pAce + 44;
      if ( (*((_DWORD *)pAce + 2) & 1) != 0 )
        v6 = (char *)pAce + 12;
      else
        v8 = (char *)pAce + 28;
      if ( (*((_BYTE *)pAce + 8) & 2) != 0 )
        v7 = (char *)pAce + (v6 != 0 ? 28LL : 12LL);
      else
        v8 -= 16;
      ATL::CSid::operator=((__int64)v23, v8);
      try
      {
        v9 = operator new(0xA8u);
        memset_0(v9, 0, 0xA8u);
        ATL::CDacl::CAccessAce::CAccessAce(
          (ATL::CDacl::CAccessAce *)v9,
          (const struct ATL::CSid *)v23,
          v5,
          *((_BYTE *)pAce + 1),
          *(_BYTE *)pAce == 5);
        *v9 = &ATL::CDacl::CAccessObjectAce::`vftable';
        v9[19] = 0;
        v9[20] = 0;
        if ( v6 )
        {
          v10 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
          if ( !v10 )
          {
            v9[19] = 0;
            ATL::AtlThrowImpl(-2147024882);
          }
          *v10 = *v6;
          v9[19] = v10;
        }
        if ( v7 )
        {
          v11 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
          if ( !v11 )
          {
            v9[20] = 0;
            operator delete((void *)v9[19]);
            v9[19] = 0;
            ATL::AtlThrowImpl(-2147024882);
          }
          *v11 = *v7;
          v9[20] = v11;
        }
        v15 = v9;
      }
      catch ( ... )
      {
        v9 = v15;
        v3 = this;
      }
      if ( !v9 )
        goto LABEL_40;
      v12 = *((_QWORD *)v3 + 4);
      if ( v12 >= *((_QWORD *)v3 + 5) )
      {
        _mm_lfence();
        if ( !(unsigned __int8)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
                                 (char *)v3 + 24,
                                 v12 + 1) )
          goto LABEL_40;
      }
      *(_QWORD *)(*((_QWORD *)v3 + 3) + 8 * v12) = v9;
    }
    ++*((_QWORD *)v3 + 4);
  }
  ATL::CSid::~CSid((ATL::CSid *)v23);
}

```

## disassembly

```asm
0x180030260  mov     [rsp+arg_10], rbx
0x180030265  push    rsi
0x180030266  push    r12
0x180030268  push    r13
0x18003026a  push    r14
0x18003026c  push    r15
0x18003026e  sub     rsp, 110h
0x180030275  mov     rax, cs:__security_cookie
0x18003027c  xor     rax, rsp
0x18003027f  mov     [rsp+138h+var_38], rax
0x180030287  mov     rsi, rdx
0x18003028a  mov     r14, rcx
0x18003028d  mov     [rsp+138h+var_F8], rcx
0x180030292  mov     [rsp+138h+pAcl], rdx
0x180030297  test    rdx, rdx
0x18003029a  jnz     short loc_1800302D7
0x18003029c  mov     rax, [rcx]
0x18003029f  mov     rax, [rax+10h]
0x1800302a3  call    cs:__guard_dispatch_icall_fptr
0x1800302a9  mov     byte ptr [r14+10h], 1
0x1800302ae  mov     rcx, [rsp+138h+var_38]
0x1800302b6  xor     rcx, rsp; StackCookie
0x1800302b9  call    __security_check_cookie
0x1800302be  mov     rbx, [rsp+138h+arg_10]
0x1800302c6  add     rsp, 110h
0x1800302cd  pop     r15
0x1800302cf  pop     r14
0x1800302d1  pop     r13
0x1800302d3  pop     r12
0x1800302d5  pop     rsi
0x1800302d6  retn
0x1800302d7  xor     edx, edx; Val
0x1800302d9  lea     r8d, [rdx+78h]; Size
0x1800302dd  lea     rcx, [rsp+138h+var_B8]; void *
0x1800302e5  call    memset_0
0x1800302ea  lea     rcx, [rsp+138h+var_B8]; this
0x1800302f2  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x1800302f7  nop
0x1800302f8  xor     ebx, ebx
0x1800302fa  mov     [rsp+138h+var_100], rbx
0x1800302ff  mov     rcx, [r14+8]; Block
0x180030303  call    cs:__imp_free
0x180030309  mov     [r14+8], rbx
0x18003030d  lea     r9d, [rbx+2]; dwAclInformationClass
0x180030311  lea     r8d, [rbx+0Ch]; nAclInformationLength
0x180030315  lea     rdx, [rsp+138h+pAclInformation]; pAclInformation
0x18003031a  mov     rcx, rsi; pAcl
0x18003031d  call    cs:__imp_GetAclInformation
0x180030323  test    eax, eax
0x180030325  jz      loc_1800305F5
0x18003032b  lea     r9d, [rbx+1]; dwAclInformationClass
0x18003032f  lea     r8d, [rbx+4]; nAclInformationLength
0x180030333  lea     rdx, [rsp+138h+var_D8]; pAclInformation
0x180030338  mov     rcx, rsi; pAcl
0x18003033b  call    cs:__imp_GetAclInformation
0x180030341  test    eax, eax
0x180030343  jz      loc_1800305F5
0x180030349  mov     eax, [rsp+138h+var_D8]
0x18003034d  mov     [r14+14h], eax
0x180030351  xor     r12d, r12d
0x180030354  mov     [rsp+138h+var_108], r12d
0x180030359  cmp     r12d, [rsp+138h+pAclInformation]
0x18003035e  jnb     loc_1800305C9
0x180030364  lea     r8, [rsp+138h+pAce]; pAce
0x180030369  mov     edx, r12d; dwAceIndex
0x18003036c  mov     rcx, [rsp+138h+pAcl]; pAcl
0x180030371  call    cs:__imp_GetAce
0x180030377  test    eax, eax
0x180030379  jz      loc_1800305F5
0x18003037f  mov     rdx, [rsp+138h+pAce]
0x180030384  mov     r13d, [rdx+4]
0x180030388  movzx   ecx, byte ptr [rdx]
0x18003038b  test    ecx, ecx
0x18003038d  jz      loc_18003050F
0x180030393  sub     ecx, 1
0x180030396  jz      loc_18003050F
0x18003039c  sub     ecx, 4
0x18003039f  jz      short loc_1800303AA
0x1800303a1  cmp     ecx, 1
0x1800303a4  jnz     loc_1800305C1
0x1800303aa  xor     r15d, r15d
0x1800303ad  xor     ebx, ebx
0x1800303af  lea     rcx, [rdx+2Ch]
0x1800303b3  mov     r8d, [rdx+8]
0x1800303b7  and     r8d, 1
0x1800303bb  jz      short loc_1800303C1
0x1800303bd  lea     r15, [rdx+0Ch]
0x1800303c1  lea     rax, [rcx-10h]
0x1800303c5  test    r8d, r8d
0x1800303c8  cmovz   rcx, rax
0x1800303cc  test    byte ptr [rdx+8], 2
0x1800303d0  jz      short loc_1800303E7
0x1800303d2  mov     rax, r15
0x1800303d5  neg     rax
0x1800303d8  sbb     rbx, rbx
0x1800303db  and     ebx, 10h
0x1800303de  add     rbx, 0Ch
0x1800303e2  add     rbx, rdx
0x1800303e5  jmp     short loc_1800303EB
0x1800303e7  add     rcx, 0FFFFFFFFFFFFFFF0h
0x1800303eb  mov     rdx, rcx
0x1800303ee  lea     rcx, [rsp+138h+var_B8]
0x1800303f6  call    ??4CSid@ATL@@QEAAAEAV01@AEBU_SID@@@Z; ATL::CSid::operator=(_SID const &)
0x1800303fb  nop
0x1800303fc  mov     ecx, 0A8h; Size
0x180030401  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030406  mov     rsi, rax
0x180030409  mov     [rsp+138h+var_E8], rax
0x18003040e  xor     edx, edx; Val
0x180030410  mov     r8d, 0A8h; Size
0x180030416  mov     rcx, rax; void *
0x180030419  call    memset_0
0x18003041e  mov     r9, [rsp+138h+pAce]
0x180030423  cmp     byte ptr [r9], 5
0x180030427  setz    cl
0x18003042a  mov     [rsp+138h+var_118], cl; bool
0x18003042e  mov     r9b, [r9+1]; unsigned __int8
0x180030432  mov     r8d, r13d; unsigned int
0x180030435  lea     rdx, [rsp+138h+var_B8]; struct ATL::CSid *
0x18003043d  mov     rcx, rsi; this
0x180030440  call    ??0CAccessAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_N@Z; ATL::CDacl::CAccessAce::CAccessAce(ATL::CSid const &,ulong,uchar,bool)
0x180030445  nop
0x180030446  lea     rax, ??_7CAccessObjectAce@CDacl@ATL@@6B@; const ATL::CDacl::CAccessObjectAce::`vftable'
0x18003044d  mov     [rsi], rax
0x180030450  mov     qword ptr [rsi+98h], 0
0x18003045b  mov     qword ptr [rsi+0A0h], 0
0x180030466  test    r15, r15
0x180030469  jz      short loc_180030494
0x18003046b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180030472  mov     ecx, 10h; unsigned __int64
0x180030477  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003047c  test    rax, rax
0x18003047f  jz      loc_1800305FB
0x180030485  movups  xmm0, xmmword ptr [r15]
0x180030489  movdqu  xmmword ptr [rax], xmm0
0x18003048d  mov     [rsi+98h], rax
0x180030494  test    rbx, rbx
0x180030497  jz      short loc_1800304C1
0x180030499  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800304a0  mov     ecx, 10h; unsigned __int64
0x1800304a5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800304aa  test    rax, rax
0x1800304ad  jz      loc_180030610
0x1800304b3  movups  xmm0, xmmword ptr [rbx]
0x1800304b6  movdqu  xmmword ptr [rax], xmm0
0x1800304ba  mov     [rsi+0A0h], rax
0x1800304c1  mov     [rsp+138h+var_100], rsi
0x1800304c6  jmp     short loc_1800304D7
0x1800304c8  mov     rsi, [rsp+138h+var_100]
0x1800304cd  mov     r12d, [rsp+138h+var_108]
0x1800304d2  mov     r14, [rsp+138h+var_F8]
0x1800304d7  test    rsi, rsi
0x1800304da  jz      loc_180030642
0x1800304e0  mov     r13, [r14+20h]
0x1800304e4  cmp     r13, [r14+28h]
0x1800304e8  jb      short loc_180030502
0x1800304ea  lfence
0x1800304ed  lea     rdx, [r13+1]
0x1800304f1  lea     rcx, [r14+18h]
0x1800304f5  call    ?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(unsigned __int64)
0x1800304fa  test    al, al
0x1800304fc  jz      loc_180030642
0x180030502  mov     rax, [r14+18h]
0x180030506  mov     [rax+r13*8], rsi
0x18003050a  jmp     loc_1800305B6
0x18003050f  add     rdx, 8
0x180030513  lea     rcx, [rsp+138h+var_B8]
0x18003051b  call    ??4CSid@ATL@@QEAAAEAV01@AEBU_SID@@@Z; ATL::CSid::operator=(_SID const &)
0x180030520  nop
0x180030521  mov     ecx, 98h; Size
0x180030526  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003052b  mov     rbx, rax
0x18003052e  mov     [rsp+138h+var_E8], rax
0x180030533  xor     edx, edx; Val
0x180030535  mov     r8d, 98h; Size
0x18003053b  mov     rcx, rax; void *
0x18003053e  call    memset_0
0x180030543  mov     r9, [rsp+138h+pAce]
0x180030548  cmp     byte ptr [r9], 0
0x18003054c  setz    cl
0x18003054f  mov     [rsp+138h+var_118], cl; bool
0x180030553  mov     r9b, [r9+1]; unsigned __int8
0x180030557  mov     r8d, r13d; unsigned int
0x18003055a  lea     rdx, [rsp+138h+var_B8]; struct ATL::CSid *
0x180030562  mov     rcx, rbx; this
0x180030565  call    ??0CAccessAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_N@Z; ATL::CDacl::CAccessAce::CAccessAce(ATL::CSid const &,ulong,uchar,bool)
0x18003056a  mov     r15, rax
0x18003056d  mov     [rsp+138h+var_100], rax
0x180030572  jmp     short loc_180030583
0x180030574  mov     r15, [rsp+138h+var_100]
0x180030579  mov     r12d, [rsp+138h+var_108]
0x18003057e  mov     r14, [rsp+138h+var_F8]
0x180030583  test    r15, r15
0x180030586  jz      loc_180030642
0x18003058c  mov     r13, [r14+20h]
0x180030590  cmp     r13, [r14+28h]
0x180030594  jb      short loc_1800305AE
0x180030596  lfence
0x180030599  lea     rdx, [r13+1]
0x18003059d  lea     rcx, [r14+18h]
0x1800305a1  call    ?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(unsigned __int64)
0x1800305a6  test    al, al
0x1800305a8  jz      loc_180030642
0x1800305ae  mov     rax, [r14+18h]
0x1800305b2  mov     [rax+r13*8], r15
0x1800305b6  xor     ebx, ebx
0x1800305b8  inc     qword ptr [r14+20h]
0x1800305bc  mov     [rsp+138h+var_100], rbx
0x1800305c1  inc     r12d
0x1800305c4  jmp     loc_180030354
0x1800305c9  test    rbx, rbx
0x1800305cc  jz      short loc_1800305E3
0x1800305ce  mov     rax, [rbx]
0x1800305d1  mov     edx, 1
0x1800305d6  mov     rcx, rbx
0x1800305d9  mov     rax, [rax]
0x1800305dc  call    cs:__guard_dispatch_icall_fptr
0x1800305e2  nop
0x1800305e3  lea     rcx, [rsp+138h+var_B8]; this
0x1800305eb  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1800305f0  jmp     loc_1800302AE
0x1800305f5  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1800305fb  mov     qword ptr [rsi+98h], 0
0x180030606  mov     ecx, 8007000Eh; int
0x18003060b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180030610  mov     qword ptr [rsi+0A0h], 0
0x18003061b  mov     edx, 10h
0x180030620  mov     rcx, [rsi+98h]; Block
0x180030627  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003062c  mov     qword ptr [rsi+98h], 0
0x180030637  mov     ecx, 8007000Eh; int
0x18003063c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180030642  mov     ecx, 8007000Eh; int
0x180030647  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
