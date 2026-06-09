# CalculateNewDacl(_ACL *,_ACL * const,bool,bool,bool,bool *,_ACL * *)

- ea: `0x180018f3c`
- end: `0x180019206`
- name: `?CalculateNewDacl@@YAJPEAU_ACL@@QEAU1@_N22PEA_NPEAPEAU1@@Z`
- size: `714`
- prototype: `__int64 __fastcall(PACL pAcl, struct _ACL *const Source, char, char, bool, struct _ACL *Destination, struct _ACL **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019b04`

## callees

- `0x180007a10`
- `0x18000d710`
- `0x180018248`
- `0x180018f3c`
- `0x18001a0fc`
- `0x18001a324`
- `0x18001a56c`
- `0x18004a620`
- `0x18004c98a`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800190ef`
- `msvcrt!memcpy_s` at `0x1800190ef`
- `ntdll!RtlAddAce` at `0x180019113`
- `ntdll!RtlAddAce` at `0x180019113`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180018f9c`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18001902a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180018f9c`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18001902a`

## string_xrefs

- `0x180018fc7`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x180018fe6`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x180019157`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x18001916c`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x1800191b7`: `onecore\admin\appmodel\common\directoryacls.cpp`

## pseudocode

```c
__int64 __fastcall CalculateNewDacl(
        PACL pAcl,
        struct _ACL *const Source,
        char a3,
        char a4,
        bool a5,
        struct _ACL *Destination,
        struct _ACL **a7)
{
  bool *v7; // r14
  struct _ACL **v9; // rcx
  bool v10; // al
  char v11; // r15
  DWORD v13; // ebx
  const char *v14; // r9
  int v15; // eax
  unsigned int LastError; // edi
  struct _ACL *v18; // rbx
  DWORD i; // r14d
  bool v20; // di
  const char *v21; // r9
  struct _ACE_HEADER *v22; // rax
  char v23; // cl
  unsigned int AceSize; // ecx
  unsigned int v25; // r15d
  struct _ACL *v26; // rdi
  NTSTATUS v27; // eax
  __int64 v28; // rdx
  unsigned int v29; // esi
  ULONG AceListLength; // [rsp+20h] [rbp-20h]
  LPVOID pAce; // [rsp+30h] [rbp-10h] BYREF
  struct _ACL *v32; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  bool v35; // [rsp+98h] [rbp+58h] BYREF

  v7 = (bool *)Destination;
  pAce = 0;
  v9 = a7;
  v10 = 1;
  v35 = 1;
  v11 = a3;
  Destination->AclRevision = 0;
  *v9 = 0;
  if ( a4 )
  {
    v13 = 0;
    while ( v10 )
    {
      if ( v13 >= Source->AceCount )
        return 0;
      if ( !GetAce(Source, v13, &pAce) )
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x3CA,
                 (unsigned int)"onecore\\admin\\appmodel\\common\\directoryacls.cpp",
                 v14);
      v15 = DACLContainsAce(pAcl, (struct _ACE_HEADER *)pAce, &v35);
      LastError = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3CB,
          (unsigned int)"onecore\\admin\\appmodel\\common\\directoryacls.cpp",
          (const char *)(unsigned int)v15,
          AceListLength);
        return LastError;
      }
      v10 = v35;
      ++v13;
    }
  }
  v18 = 0;
  *v7 = 1;
  v32 = 0;
  for ( i = 0; i < pAcl->AceCount; ++i )
  {
    v35 = 0;
    v20 = 0;
    if ( !GetAce(pAcl, i, &pAce) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x3DA,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\directoryacls.cpp",
                    v21);
      goto LABEL_39;
    }
    v22 = (struct _ACE_HEADER *)pAce;
    v23 = 0;
    if ( v11 )
    {
      *((_BYTE *)pAce + 1) &= ~0x10u;
      v22 = (struct _ACE_HEADER *)pAce;
    }
    else if ( (*((_BYTE *)pAce + 1) & 0x10) != 0 )
    {
      v20 = 1;
      v35 = 1;
      v23 = 1;
    }
    if ( !a5 || v22->AceType != 9 )
    {
      if ( !v23 )
      {
        LastError = DACLContainsAce(Source, v22, &v35);
        if ( (LastError & 0x80000000) != 0 )
        {
          v28 = 1008;
          goto LABEL_32;
        }
        v22 = (struct _ACE_HEADER *)pAce;
        v20 = v35;
      }
      if ( !v20 )
      {
        AceSize = v22->AceSize;
        v25 = AceSize + Source->AclSize;
        if ( v25 < AceSize )
        {
          LastError = -2147024362;
          v28 = 1014;
LABEL_32:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v28,
            (unsigned int)"onecore\\admin\\appmodel\\common\\directoryacls.cpp",
            (const char *)LastError,
            AceListLength);
LABEL_39:
          if ( v18 )
            Common::GlobalHeap::Free(v18);
          return LastError;
        }
        Destination = 0;
        Common::GlobalHeap::Alloc(v25, (void **)&Destination);
        v26 = Destination;
        if ( !Destination )
        {
          LastError = -2147024882;
          v28 = 1017;
          goto LABEL_32;
        }
        memset_0(Destination, 0, v25);
        memcpy_s(v26, v25, Source, Source->AclSize);
        v26->AclSize = v25;
        v27 = RtlAddAce(v26, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1));
        if ( v27 < 0 )
        {
          v29 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x405,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\directoryacls.cpp",
                  (const char *)(unsigned int)v27,
                  AceListLength);
          Common::GlobalHeap::Free(v26);
          if ( v18 )
            Common::GlobalHeap::Free(v18);
          return v29;
        }
        wistd::unique_ptr<_ACL,wistd::default_delete<_ACL>>::swap(&v32, &Destination);
        v18 = v32;
        Source = v32;
        if ( Destination )
          Common::GlobalHeap::Free(Destination);
        v11 = a3;
      }
    }
  }
  if ( v18 )
    *a7 = v18;
  return 0;
}

```

## disassembly

```asm
0x180018f3c  mov     [rsp-38h+arg_0], rbx
0x180018f41  mov     [rsp-38h+arg_10], r8b
0x180018f46  push    rbp
0x180018f47  push    rsi
0x180018f48  push    rdi
0x180018f49  push    r12
0x180018f4b  push    r13
0x180018f4d  push    r14
0x180018f4f  push    r15
0x180018f51  mov     rbp, rsp
0x180018f54  sub     rsp, 40h
0x180018f58  mov     r14, [rbp+Destination]
0x180018f5c  xor     r13d, r13d
0x180018f5f  mov     [rbp+pAce], r13
0x180018f63  mov     r12, rcx
0x180018f66  mov     rcx, [rbp+arg_30]
0x180018f6a  mov     al, 1
0x180018f6c  mov     [rbp+arg_18], al
0x180018f6f  mov     r15b, r8b
0x180018f72  mov     [r14], r13b
0x180018f75  mov     rsi, rdx
0x180018f78  mov     [rcx], r13
0x180018f7b  test    r9b, r9b
0x180018f7e  jz      short loc_180018FFC
0x180018f80  mov     ebx, r13d
0x180018f83  test    al, al
0x180018f85  jz      short loc_180018FFC
0x180018f87  movzx   eax, word ptr [rsi+4]
0x180018f8b  cmp     ebx, eax
0x180018f8d  jnb     loc_1800191EC
0x180018f93  lea     r8, [rbp+pAce]; pAce
0x180018f97  mov     edx, ebx; dwAceIndex
0x180018f99  mov     rcx, rsi; pAcl
0x180018f9c  call    cs:__imp_GetAce
0x180018fa2  test    eax, eax
0x180018fa4  jz      short loc_180018FE2
0x180018fa6  mov     rdx, [rbp+pAce]; struct _ACE_HEADER *
0x180018faa  lea     r8, [rbp+arg_18]; bool *
0x180018fae  mov     rcx, r12; pAcl
0x180018fb1  call    ?DACLContainsAce@@YAJQEAU_ACL@@PEAU_ACE_HEADER@@PEA_N@Z; DACLContainsAce(_ACL * const,_ACE_HEADER *,bool *)
0x180018fb6  mov     edi, eax
0x180018fb8  test    eax, eax
0x180018fba  js      short loc_180018FC3
0x180018fbc  mov     al, [rbp+arg_18]
0x180018fbf  inc     ebx
0x180018fc1  jmp     short loc_180018F83
0x180018fc3  mov     rcx, [rbp+38h]; this
0x180018fc7  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\common\\direc"...
0x180018fce  mov     r9d, edi; char *
0x180018fd1  mov     edx, 3CBh; void *
0x180018fd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018fdb  mov     eax, edi
0x180018fdd  jmp     loc_1800191EE
0x180018fe2  mov     rcx, [rbp+38h]; this
0x180018fe6  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\common\\direc"...
0x180018fed  mov     edx, 3CAh; void *
0x180018ff2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018ff7  jmp     loc_1800191EE
0x180018ffc  mov     rbx, r13
0x180018fff  mov     byte ptr [r14], 1
0x180019003  mov     [rbp+var_8], rbx
0x180019007  mov     r14d, r13d
0x18001900a  movzx   eax, word ptr [r12+4]
0x180019010  cmp     r14d, eax
0x180019013  jnb     loc_1800191E0
0x180019019  lea     r8, [rbp+pAce]; pAce
0x18001901d  mov     [rbp+arg_18], r13b
0x180019021  mov     edx, r14d; dwAceIndex
0x180019024  mov     rcx, r12; pAcl
0x180019027  mov     dil, r13b
0x18001902a  call    cs:__imp_GetAce
0x180019030  test    eax, eax
0x180019032  jz      loc_1800191B3
0x180019038  mov     rax, [rbp+pAce]
0x18001903c  mov     cl, r13b
0x18001903f  test    r15b, r15b
0x180019042  jz      short loc_18001904E
0x180019044  and     byte ptr [rax+1], 0EFh
0x180019048  mov     rax, [rbp+pAce]
0x18001904c  jmp     short loc_18001905E
0x18001904e  test    byte ptr [rax+1], 10h
0x180019052  jz      short loc_18001905E
0x180019054  mov     dil, 1
0x180019057  mov     [rbp+arg_18], dil
0x18001905b  mov     cl, dil
0x18001905e  cmp     [rbp+arg_20], r13b
0x180019062  jz      short loc_18001906D
0x180019064  cmp     byte ptr [rax], 9
0x180019067  jz      loc_180019146
0x18001906d  test    cl, cl
0x18001906f  jnz     short loc_180019092
0x180019071  lea     r8, [rbp+arg_18]; bool *
0x180019075  mov     rdx, rax; struct _ACE_HEADER *
0x180019078  mov     rcx, rsi; pAcl
0x18001907b  call    ?DACLContainsAce@@YAJQEAU_ACL@@PEAU_ACE_HEADER@@PEA_N@Z; DACLContainsAce(_ACL * const,_ACE_HEADER *,bool *)
0x180019080  mov     edi, eax
0x180019082  test    eax, eax
0x180019084  js      loc_18001914E
0x18001908a  mov     rax, [rbp+pAce]
0x18001908e  mov     dil, [rbp+arg_18]
0x180019092  test    dil, dil
0x180019095  jnz     loc_180019146
0x18001909b  movzx   ecx, word ptr [rax+2]
0x18001909f  movzx   r15d, word ptr [rsi+2]
0x1800190a4  add     r15d, ecx
0x1800190a7  cmp     r15d, ecx
0x1800190aa  jb      loc_1800191A7
0x1800190b0  mov     [rbp+Destination], r13
0x1800190b4  lea     rdx, [rbp+Destination]; void **
0x1800190b8  mov     ecx, r15d; Size
0x1800190bb  mov     r13d, r15d
0x1800190be  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x1800190c3  mov     rdi, [rbp+Destination]
0x1800190c7  mov     [rbp+Destination], rdi
0x1800190cb  test    rdi, rdi
0x1800190ce  jz      loc_18001919B
0x1800190d4  mov     r8d, r13d; Size
0x1800190d7  xor     edx, edx; Val
0x1800190d9  mov     rcx, rdi; void *
0x1800190dc  call    memset_0
0x1800190e1  movzx   r9d, word ptr [rsi+2]; SourceSize
0x1800190e6  mov     r8, rsi; Source
0x1800190e9  mov     edx, r13d; DestinationSize
0x1800190ec  mov     rcx, rdi; Destination
0x1800190ef  call    cs:__imp_memcpy_s
0x1800190f5  mov     [rdi+2], r15w
0x1800190fa  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x1800190fe  mov     r9, [rbp+pAce]; AceList
0x180019102  mov     edx, 2; AceRevision
0x180019107  mov     rcx, rdi; Acl
0x18001910a  movzx   eax, word ptr [r9+2]
0x18001910f  mov     [rsp+40h+AceListLength], eax; int
0x180019113  call    cs:__imp_RtlAddAce
0x180019119  xor     r13d, r13d
0x18001911c  test    eax, eax
0x18001911e  js      short loc_180019168
0x180019120  lea     rdx, [rbp+Destination]
0x180019124  lea     rcx, [rbp+var_8]
0x180019128  call    ?swap@?$unique_ptr@U_ACL@@U?$default_delete@U_ACL@@@wistd@@@wistd@@QEAAXAEAV12@@Z; wistd::unique_ptr<_ACL,wistd::default_delete<_ACL>>::swap(wistd::unique_ptr<_ACL,wistd::default_delete<_ACL>> &)
0x18001912d  mov     rcx, [rbp+Destination]; void *
0x180019131  mov     rbx, [rbp+var_8]
0x180019135  mov     rsi, rbx
0x180019138  test    rcx, rcx
0x18001913b  jz      short loc_180019142
0x18001913d  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180019142  mov     r15b, [rbp+arg_10]
0x180019146  inc     r14d
0x180019149  jmp     loc_18001900A
0x18001914e  mov     edx, 3F0h; void *
0x180019153  mov     rcx, [rbp+38h]; this
0x180019157  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\common\\direc"...
0x18001915e  mov     r9d, edi; char *
0x180019161  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019166  jmp     short loc_1800191CA
0x180019168  mov     rcx, [rbp+38h]; this
0x18001916c  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\common\\direc"...
0x180019173  mov     r9d, eax; char *
0x180019176  mov     edx, 405h; void *
0x18001917b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180019180  mov     rcx, rdi; void *
0x180019183  mov     esi, eax
0x180019185  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18001918a  test    rbx, rbx
0x18001918d  jz      short loc_180019197
0x18001918f  mov     rcx, rbx; void *
0x180019192  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180019197  mov     eax, esi
0x180019199  jmp     short loc_1800191EE
0x18001919b  mov     edi, 8007000Eh
0x1800191a0  mov     edx, 3F9h
0x1800191a5  jmp     short loc_180019153
0x1800191a7  mov     edi, 80070216h
0x1800191ac  mov     edx, 3F6h
0x1800191b1  jmp     short loc_180019153
0x1800191b3  mov     rcx, [rbp+38h]; this
0x1800191b7  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\common\\direc"...
0x1800191be  mov     edx, 3DAh; void *
0x1800191c3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800191c8  mov     edi, eax
0x1800191ca  test    rbx, rbx
0x1800191cd  jz      loc_180018FDB
0x1800191d3  mov     rcx, rbx; void *
0x1800191d6  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800191db  jmp     loc_180018FDB
0x1800191e0  test    rbx, rbx
0x1800191e3  jz      short loc_1800191EC
0x1800191e5  mov     rax, [rbp+arg_30]
0x1800191e9  mov     [rax], rbx
0x1800191ec  xor     eax, eax
0x1800191ee  mov     rbx, [rsp+40h+arg_0]
0x1800191f6  add     rsp, 40h
0x1800191fa  pop     r15
0x1800191fc  pop     r14
0x1800191fe  pop     r13
0x180019200  pop     r12
0x180019202  pop     rdi
0x180019203  pop     rsi
0x180019204  pop     rbp
0x180019205  retn
```
