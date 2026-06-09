# CConnectedUserStore::CoCreateConnectedUser(ulong,_GUID const &,CConnectedUser * *)

- ea: `0x1800035f0`
- end: `0x18000378e`
- name: `?CoCreateConnectedUser@CConnectedUserStore@@AEAAJKAEBU_GUID@@PEAPEAVCConnectedUser@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(CConnectedUserStore *this, unsigned int, const struct _GUID *, struct CConnectedUser **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016060`

## callees

- `0x1800035f0`
- `0x1800037a0`
- `0x180003a70`
- `0x1800144b4`
- `0x1800191ac`
- `0x180019210`
- `0x18001b010`

## string_xrefs

- `0x180003619`: `CConnectedUserStore::CoCreateConnectedUser`

## pseudocode

```c
__int64 __fastcall CConnectedUserStore::CoCreateConnectedUser(
        CConnectedUserStore *this,
        unsigned int a2,
        const struct _GUID *a3,
        struct CConnectedUser **a4)
{
  int v8; // eax
  int v9; // edx
  __int64 v10; // r8
  CConnectedUser *v11; // rbx
  struct IConnectedUserSite *v12; // r9
  CIdentityProfileHandler *v13; // rcx
  unsigned int v14; // ebx
  __int64 v16; // rdx
  __int64 v17; // r9
  int v18; // [rsp+30h] [rbp-78h] BYREF
  struct _GUID v19; // [rsp+40h] [rbp-68h] BYREF
  int *v20; // [rsp+50h] [rbp-58h]
  const char *v21; // [rsp+58h] [rbp-50h]

  v18 = 0;
  *(_QWORD *)&v19.Data1 = 0;
  v21 = "CConnectedUserStore::CoCreateConnectedUser";
  v20 = &v18;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CConnectedUserStore::CoCreateConnectedUser");
  }
  v8 = ATL::CComObject<CConnectedUser>::CreateInstance(&v19);
  v18 = v8;
  if ( v8 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v16 = 105;
      v17 = (unsigned int)v8;
      goto LABEL_18;
    }
  }
  else
  {
    v11 = *(CConnectedUser **)&v19.Data1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v19.Data1 + 8LL))(*(_QWORD *)&v19.Data1);
    v19 = *a3;
    v12 = (CConnectedUserStore *)((char *)this + 8);
    if ( !this )
      v12 = 0;
    v18 = CConnectedUser::InitializeConnectedUser(v11, a2, &v19, v12);
    if ( v18 >= 0 )
    {
      *a4 = v11;
LABEL_9:
      v13 = WPP_GLOBAL_Control;
      goto LABEL_10;
    }
    (*(void (__fastcall **)(CConnectedUser *))(*(_QWORD *)v11 + 16LL))(v11);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v16 = 106;
      v17 = (unsigned int)v18;
LABEL_18:
      WPP_SF_d(*((_QWORD *)v13 + 2), v16, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v17);
      goto LABEL_9;
    }
  }
LABEL_10:
  v14 = v18;
  if ( v18 < 0 )
  {
    if ( v13 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      return v14;
    if ( (*((_BYTE *)v13 + 28) & 4) != 0 )
    {
      WPP_SF_sL(*((_QWORD *)v13 + 2), v9, v10, (unsigned int)"CConnectedUserStore::CoCreateConnectedUser", v18);
      v13 = WPP_GLOBAL_Control;
    }
  }
  if ( v13 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v13 + 7) & 0x400) != 0 )
    WPP_SF_s(*((_QWORD *)v13 + 2), 12, v10, "CConnectedUserStore::CoCreateConnectedUser");
  return v14;
}

```

## disassembly

```asm
0x1800035f0  push    rbx
0x1800035f2  push    rbp
0x1800035f3  push    rsi
0x1800035f4  push    rdi
0x1800035f5  push    r12
0x1800035f7  push    r13
0x1800035f9  push    r14
0x1800035fb  push    r15
0x1800035fd  sub     rsp, 68h
0x180003601  mov     r14, r9
0x180003604  mov     rsi, r8
0x180003607  mov     ebp, edx
0x180003609  mov     rdi, rcx
0x18000360c  xor     r12d, r12d
0x18000360f  mov     [rsp+0A8h+var_78], r12d
0x180003614  mov     qword ptr [rsp+0A8h+var_68.Data1], r12
0x180003619  lea     r13, aCconnecteduser_6; "CConnectedUserStore::CoCreateConnectedU"...
0x180003620  mov     [rsp+0A8h+var_50], r13
0x180003625  lea     rax, [rsp+0A8h+var_78]
0x18000362a  mov     [rsp+0A8h+var_58], rax
0x18000362f  lea     r15, WPP_GLOBAL_Control
0x180003636  mov     rcx, cs:WPP_GLOBAL_Control
0x18000363d  cmp     rcx, r15
0x180003640  jz      short loc_18000364F
0x180003642  test    dword ptr [rcx+1Ch], 400h
0x180003649  jnz     loc_18000373E
0x18000364f  lea     rcx, [rsp+0A8h+var_68]
0x180003654  call    ?CreateInstance@?$CComObject@VCConnectedUser@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CConnectedUser>::CreateInstance(ATL::CComObject<CConnectedUser> * *)
0x180003659  mov     [rsp+0A8h+var_78], eax
0x18000365d  test    eax, eax
0x18000365f  js      loc_180003754
0x180003665  mov     rbx, qword ptr [rsp+0A8h+var_68.Data1]
0x18000366a  mov     rax, [rbx]
0x18000366d  mov     rcx, rbx
0x180003670  mov     rax, [rax+8]
0x180003674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003679  movups  xmm0, xmmword ptr [rsi]
0x18000367c  movaps  xmmword ptr [rsp+0A8h+var_68.Data1], xmm0
0x180003681  lea     r9, [rdi+8]
0x180003685  test    rdi, rdi
0x180003688  cmovz   r9, r12; struct IConnectedUserSite *
0x18000368c  lea     r8, [rsp+0A8h+var_68]; struct _GUID
0x180003691  mov     edx, ebp; unsigned int
0x180003693  mov     rcx, rbx; this
0x180003696  call    ?InitializeConnectedUser@CConnectedUser@@QEAAJKU_GUID@@PEAVIConnectedUserSite@@@Z; CConnectedUser::InitializeConnectedUser(ulong,_GUID,IConnectedUserSite *)
0x18000369b  mov     [rsp+0A8h+var_78], eax
0x18000369f  test    eax, eax
0x1800036a1  js      short loc_1800036DA
0x1800036a3  mov     [r14], rbx
0x1800036a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036ad  mov     ebx, [rsp+0A8h+var_78]
0x1800036b1  test    ebx, ebx
0x1800036b3  js      short loc_180003717
0x1800036b5  cmp     rcx, r15
0x1800036b8  jz      short loc_1800036C7
0x1800036ba  test    dword ptr [rcx+1Ch], 400h
0x1800036c1  jnz     loc_180003778
0x1800036c7  mov     eax, ebx
0x1800036c9  add     rsp, 68h
0x1800036cd  pop     r15
0x1800036cf  pop     r14
0x1800036d1  pop     r13
0x1800036d3  pop     r12
0x1800036d5  pop     rdi
0x1800036d6  pop     rsi
0x1800036d7  pop     rbp
0x1800036d8  pop     rbx
0x1800036d9  retn
0x1800036da  mov     rax, [rbx]
0x1800036dd  mov     rcx, rbx
0x1800036e0  mov     rax, [rax+10h]
0x1800036e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036f0  cmp     rcx, r15
0x1800036f3  jz      short loc_1800036AD
0x1800036f5  test    byte ptr [rcx+1Ch], 4
0x1800036f9  jz      short loc_1800036AD
0x1800036fb  mov     edx, 6Ah ; 'j'
0x180003700  mov     r9d, [rsp+0A8h+var_78]
0x180003705  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x18000370c  mov     rcx, [rcx+10h]
0x180003710  call    WPP_SF_d
0x180003715  jmp     short loc_1800036A6
0x180003717  cmp     rcx, r15
0x18000371a  jz      short loc_1800036C7
0x18000371c  test    byte ptr [rcx+1Ch], 4
0x180003720  jz      short loc_1800036B5
0x180003722  mov     [rsp+0A8h+var_88], ebx
0x180003726  mov     r9, r13
0x180003729  mov     rcx, [rcx+10h]
0x18000372d  call    WPP_SF_sL
0x180003732  mov     rcx, cs:WPP_GLOBAL_Control
0x180003739  jmp     loc_1800036B5
0x18000373e  mov     edx, 0Ah
0x180003743  mov     r9, r13
0x180003746  mov     rcx, [rcx+10h]
0x18000374a  call    WPP_SF_s
0x18000374f  jmp     loc_18000364F
0x180003754  mov     rcx, cs:WPP_GLOBAL_Control
0x18000375b  cmp     rcx, r15
0x18000375e  jz      loc_1800036AD
0x180003764  test    byte ptr [rcx+1Ch], 4
0x180003768  jz      loc_1800036AD
0x18000376e  mov     edx, 69h ; 'i'
0x180003773  mov     r9d, eax
0x180003776  jmp     short loc_180003705
0x180003778  mov     edx, 0Ch
0x18000377d  mov     r9, r13
0x180003780  mov     rcx, [rcx+10h]
0x180003784  call    WPP_SF_s
0x180003789  jmp     loc_1800036C7
```
