# CServerObject_RawFactory::CreateServerSide(CServerObject_ProviderRegistrationV1 &,_GUID *,ushort const *,ushort const *,ushort *,IUnknown * *)

- ea: `0x140007384`
- end: `0x140007691`
- name: `?CreateServerSide@CServerObject_RawFactory@@SAJAEAVCServerObject_ProviderRegistrationV1@@PEAU_GUID@@PEBG2PEAGPEAPEAUIUnknown@@@Z`
- size: `781`
- prototype: `__int64 __fastcall(struct CServerObject_ProviderRegistrationV1 *, struct _GUID *, struct IUnknown *, const unsigned __int16 *, unsigned __int16 *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001270`
- `0x140007698`

## callees

- `0x140007384`
- `0x1400138f0`
- `0x1400234b8`
- `0x140046430`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x14000755e`
- `NCObjAPI!WmiSetAndCommitObject` at `0x140007621`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14000755e`
- `NCObjAPI!WmiSetAndCommitObject` at `0x140007621`
- `wbemcomn!GetMemLogObject` at `0x140007627`
- `wbemcomn!GetMemLogObject` at `0x140007627`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140007632`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140007632`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400073de`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400073de`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CServerObject_RawFactory::CreateServerSide(
        struct CServerObject_ProviderRegistrationV1 *a1,
        struct _GUID *a2,
        struct IUnknown *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct IUnknown **a6)
{
  unsigned __int64 v9; // rcx
  int v10; // ebx
  __int64 v11; // r12
  __int64 v12; // r9
  GUID *v13; // rdx
  CMemoryLog *MemLogObject; // rax
  const struct _GUID *v16; // [rsp+20h] [rbp-E0h]
  unsigned int v17; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v18; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v19; // [rsp+80h] [rbp-80h]
  OLECHAR sz[80]; // [rsp+90h] [rbp-70h] BYREF

  v18 = a4;
  v19 = a5;
  if ( a2 )
    StringFromGUID2(a2, sz, 78);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
      *((unsigned int *)a1 + 420));
  }
  v9 = *((unsigned int *)a1 + 420);
  if ( (int)v9 <= 7 )
  {
    if ( (_DWORD)v9 != 7 )
    {
      v9 = (unsigned int)(v9 - 1);
      if ( (_DWORD)v9 )
      {
        v9 = (unsigned int)(v9 - 1);
        if ( !(_DWORD)v9 )
        {
          if ( *((_DWORD *)a1 + 11) == 1 )
          {
            v17 = 5;
            goto LABEL_30;
          }
          goto LABEL_24;
        }
        v9 = (unsigned int)(v9 - 1);
        if ( !(_DWORD)v9 )
        {
          if ( *((_DWORD *)a1 + 11) == 1 )
          {
            v17 = 65540;
            goto LABEL_30;
          }
LABEL_24:
          v10 = -2147217390;
          *a6 = 0;
          goto LABEL_25;
        }
        v9 = (unsigned int)(v9 - 2);
        if ( (_DWORD)v9 )
        {
          if ( (_DWORD)v9 == 1 && *((_DWORD *)a1 + 11) == 1 )
          {
            v17 = 65541;
LABEL_30:
            v13 = (GUID *)((char *)a1 + 1776);
            goto LABEL_31;
          }
          goto LABEL_24;
        }
      }
    }
LABEL_28:
    if ( *((_DWORD *)a1 + 11) == 1 )
    {
      v17 = 1;
      goto LABEL_30;
    }
    goto LABEL_24;
  }
  v9 = (unsigned int)(v9 - 8);
  if ( !(_DWORD)v9 )
    goto LABEL_28;
  v9 = (unsigned int)(v9 - 2);
  if ( (_DWORD)v9 )
  {
    v9 = (unsigned int)(v9 - 1);
    if ( (_DWORD)v9 )
    {
      v9 = (unsigned int)(v9 - 1);
      if ( (unsigned int)v9 >= 2 )
        goto LABEL_24;
    }
    goto LABEL_28;
  }
  v17 = 1;
  v13 = &CLSID_NCProvider;
LABEL_31:
  v10 = CServerObject_RawFactory::CreateInstance(
          (struct CServerObject_ProviderRegistrationV1 *)v9,
          v13,
          a3,
          &v17,
          v16,
          (void **)a6);
LABEL_25:
  v11 = *((_QWORD *)a1 + 6);
  v12 = *((_QWORD *)a1 + 8);
  if ( v10 < 0 )
  {
    WmiSetAndCommitObject(
      qword_140061368,
      1,
      v19,
      v12,
      a3,
      v18,
      (unsigned __int64)sz & -(__int64)(a2 != 0),
      v11,
      (char *)a1 + 1112);
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v10);
  }
  else
  {
    WmiSetAndCommitObject(
      ProviderSubSystem_Globals::s_EventClassHandles,
      1,
      v19,
      v12,
      a3,
      v18,
      (unsigned __int64)sz & -(__int64)(a2 != 0),
      v11,
      (char *)a1 + 1112);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140007384  push    rbp
0x140007386  push    rbx
0x140007387  push    rsi
0x140007388  push    rdi
0x140007389  push    r12
0x14000738b  push    r13
0x14000738d  push    r14
0x14000738f  push    r15
0x140007391  lea     rbp, [rsp-48h]
0x140007396  sub     rsp, 148h
0x14000739d  mov     rax, cs:__security_cookie
0x1400073a4  xor     rax, rsp
0x1400073a7  mov     [rbp+80h+var_50], rax
0x1400073ab  mov     rax, [rbp+80h+arg_20]
0x1400073b2  xor     r15d, r15d
0x1400073b5  mov     rsi, [rbp+80h+arg_28]
0x1400073bc  mov     r13, r8
0x1400073bf  mov     [rsp+180h+var_108], r9
0x1400073c4  mov     r14, rdx
0x1400073c7  mov     [rbp+80h+var_100], rax
0x1400073cb  mov     rdi, rcx
0x1400073ce  test    rdx, rdx
0x1400073d1  jz      short loc_1400073E4
0x1400073d3  lea     r8d, [r15+4Eh]; cchMax
0x1400073d7  mov     rcx, r14; rguid
0x1400073da  lea     rdx, [rbp+80h+sz]; lpsz
0x1400073de  call    cs:__imp_StringFromGUID2
0x1400073e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400073eb  lea     rax, WPP_GLOBAL_Control
0x1400073f2  cmp     rcx, rax
0x1400073f5  jz      short loc_14000741F
0x1400073f7  test    byte ptr [rcx+1Ch], 4
0x1400073fb  jz      short loc_14000741F
0x1400073fd  cmp     byte ptr [rcx+19h], 5
0x140007401  jb      short loc_14000741F
0x140007403  mov     r9d, [rdi+690h]
0x14000740a  lea     r8, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids
0x140007411  mov     rcx, [rcx+10h]
0x140007415  mov     edx, 0Eh
0x14000741a  call    WPP_SF_d
0x14000741f  mov     ecx, [rdi+690h]; struct CServerObject_ProviderRegistrationV1 *
0x140007425  cmp     ecx, 7
0x140007428  jg      short loc_140007489
0x14000742a  jz      loc_14000757A
0x140007430  sub     ecx, 1
0x140007433  jz      loc_14000757A
0x140007439  sub     ecx, 1
0x14000743c  jz      short loc_140007476
0x14000743e  sub     ecx, 1
0x140007441  jz      short loc_140007463
0x140007443  sub     ecx, 2
0x140007446  jz      loc_14000757A
0x14000744c  cmp     ecx, 1
0x14000744f  jnz     short loc_1400074B6
0x140007451  cmp     [rdi+2Ch], ecx
0x140007454  jnz     short loc_1400074B6
0x140007456  mov     [rsp+180h+var_110], 10005h
0x14000745e  jmp     loc_14000758C
0x140007463  cmp     dword ptr [rdi+2Ch], 1
0x140007467  jnz     short loc_1400074B6
0x140007469  mov     [rsp+180h+var_110], 10004h
0x140007471  jmp     loc_14000758C
0x140007476  cmp     dword ptr [rdi+2Ch], 1
0x14000747a  jnz     short loc_1400074B6
0x14000747c  mov     [rsp+180h+var_110], 5
0x140007484  jmp     loc_14000758C
0x140007489  sub     ecx, 8
0x14000748c  jz      loc_14000757A
0x140007492  sub     ecx, 2
0x140007495  jz      loc_140007569
0x14000749b  sub     ecx, 1
0x14000749e  jz      loc_14000757A
0x1400074a4  sub     ecx, 1
0x1400074a7  jz      loc_14000757A
0x1400074ad  cmp     ecx, 1
0x1400074b0  jz      loc_14000757A
0x1400074b6  mov     ebx, 80041012h
0x1400074bb  mov     [rsi], r15
0x1400074be  mov     ecx, [rdi+24h]
0x1400074c1  lea     r11, [rdi+250h]
0x1400074c8  mov     r8d, [rdi+20h]
0x1400074cc  lea     rsi, [rdi+48h]
0x1400074d0  mov     r12, [rdi+30h]
0x1400074d4  lea     r15, [rdi+458h]
0x1400074db  mov     r9, [rdi+40h]
0x1400074df  xor     eax, eax
0x1400074e1  test    ebx, ebx
0x1400074e3  js      loc_1400075A9
0x1400074e9  cmp     ecx, 1
0x1400074ec  mov     edx, 1
0x1400074f1  cmovnz  r11, rax
0x1400074f5  cmp     r8d, 1
0x1400074f9  mov     [rsp+180h+var_120], r11
0x1400074fe  cmovnz  rsi, rax
0x140007502  xor     r10d, r10d
0x140007505  cmp     ecx, 1
0x140007508  mov     [rsp+180h+var_128], rsi
0x14000750d  setnz   r10b
0x140007511  xor     ecx, ecx
0x140007513  dec     r10d
0x140007516  mov     [rsp+180h+var_130], r10d
0x14000751b  cmp     r8d, 1
0x14000751f  lea     r8, [rbp+80h+sz]
0x140007523  setnz   cl
0x140007526  dec     ecx
0x140007528  mov     [rsp+180h+var_138], ecx
0x14000752c  neg     r14
0x14000752f  mov     rcx, cs:?s_EventClassHandles@ProviderSubSystem_Globals@@2PAPEAXA; void * near * ProviderSubSystem_Globals::s_EventClassHandles
0x140007536  mov     [rsp+180h+var_140], r15
0x14000753b  sbb     rax, rax
0x14000753e  and     rax, r8
0x140007541  mov     [rsp+180h+var_148], r12
0x140007546  mov     r8, [rbp+80h+var_100]
0x14000754a  mov     [rsp+180h+var_150], rax
0x14000754f  mov     rax, [rsp+180h+var_108]
0x140007554  mov     [rsp+180h+var_158], rax
0x140007559  mov     [rsp+180h+var_160], r13
0x14000755e  call    cs:__imp_WmiSetAndCommitObject
0x140007564  jmp     loc_140007638
0x140007569  mov     [rsp+180h+var_110], 1
0x140007571  lea     rdx, CLSID_NCProvider
0x140007578  jmp     short loc_140007593
0x14000757a  cmp     dword ptr [rdi+2Ch], 1
0x14000757e  jnz     loc_1400074B6
0x140007584  mov     [rsp+180h+var_110], 1
0x14000758c  lea     rdx, [rdi+6F0h]; struct _GUID *
0x140007593  lea     r9, [rsp+180h+var_110]; unsigned int *
0x140007598  mov     [rsp+180h+var_158], rsi; void **
0x14000759d  call    ?CreateInstance@CServerObject_RawFactory@@SAJAEAVCServerObject_ProviderRegistrationV1@@AEBU_GUID@@PEAUIUnknown@@AEBK1PEAPEAX@Z; CServerObject_RawFactory::CreateInstance(CServerObject_ProviderRegistrationV1 &,_GUID const &,IUnknown *,ulong const &,_GUID const &,void * *)
0x1400075a2  mov     ebx, eax
0x1400075a4  jmp     loc_1400074BE
0x1400075a9  cmp     ecx, 1
0x1400075ac  mov     [rsp+180h+var_118], ebx
0x1400075b0  cmovnz  r11, rax
0x1400075b4  cmp     r8d, 1
0x1400075b8  mov     [rsp+180h+var_120], r11
0x1400075bd  cmovnz  rsi, rax
0x1400075c1  xor     edx, edx
0x1400075c3  mov     [rsp+180h+var_128], rsi
0x1400075c8  lea     r10d, [rdx+1]
0x1400075cc  cmp     ecx, r10d
0x1400075cf  setnz   dl
0x1400075d2  xor     ecx, ecx
0x1400075d4  sub     edx, r10d
0x1400075d7  mov     [rsp+180h+var_130], edx
0x1400075db  cmp     r8d, r10d
0x1400075de  lea     r8, [rbp+80h+sz]
0x1400075e2  mov     edx, r10d
0x1400075e5  setnz   cl
0x1400075e8  sub     ecx, r10d
0x1400075eb  mov     [rsp+180h+var_138], ecx
0x1400075ef  neg     r14
0x1400075f2  mov     rcx, cs:qword_140061368
0x1400075f9  mov     [rsp+180h+var_140], r15
0x1400075fe  sbb     rax, rax
0x140007601  and     rax, r8
0x140007604  mov     [rsp+180h+var_148], r12
0x140007609  mov     r8, [rbp+80h+var_100]
0x14000760d  mov     [rsp+180h+var_150], rax
0x140007612  mov     rax, [rsp+180h+var_108]
0x140007617  mov     [rsp+180h+var_158], rax
0x14000761c  mov     [rsp+180h+var_160], r13
0x140007621  call    cs:__imp_WmiSetAndCommitObject
0x140007627  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000762d  mov     rcx, rax
0x140007630  mov     edx, ebx
0x140007632  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140007638  mov     rcx, cs:WPP_GLOBAL_Control
0x14000763f  lea     rax, WPP_GLOBAL_Control
0x140007646  cmp     rcx, rax
0x140007649  jz      short loc_14000766F
0x14000764b  test    byte ptr [rcx+1Ch], 4
0x14000764f  jz      short loc_14000766F
0x140007651  cmp     byte ptr [rcx+19h], 2
0x140007655  jb      short loc_14000766F
0x140007657  mov     rcx, [rcx+10h]
0x14000765b  lea     r8, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids
0x140007662  mov     edx, 0Fh
0x140007667  mov     r9d, ebx
0x14000766a  call    WPP_SF_d
0x14000766f  mov     eax, ebx
0x140007671  mov     rcx, [rbp+80h+var_50]
0x140007675  xor     rcx, rsp; StackCookie
0x140007678  call    __security_check_cookie
0x14000767d  add     rsp, 148h
0x140007684  pop     r15
0x140007686  pop     r14
0x140007688  pop     r13
0x14000768a  pop     r12
0x14000768c  pop     rdi
0x14000768d  pop     rsi
0x14000768e  pop     rbx
0x14000768f  pop     rbp
0x140007690  retn
```
