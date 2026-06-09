# CConnectedUser::InitializeConnectedUser(ulong,_GUID,IConnectedUserSite *)

- ea: `0x1800037a0`
- end: `0x180003a60`
- name: `?InitializeConnectedUser@CConnectedUser@@QEAAJKU_GUID@@PEAVIConnectedUserSite@@@Z`
- size: `704`
- prototype: `__int64 __fastcall(CConnectedUser *this, unsigned int, struct _GUID *, struct IConnectedUserSite *)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002500`
- `0x1800035f0`
- `0x180004490`

## callees

- `0x180001d70`
- `0x180003560`
- `0x1800037a0`
- `0x1800144b4`
- `0x1800144f4`
- `0x1800191ac`
- `0x180019210`
- `0x180019716`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall CConnectedUser::InitializeConnectedUser(
        CConnectedUser *this,
        unsigned int a2,
        struct _GUID *a3,
        struct IConnectedUserSite *a4)
{
  CIdentityProfileHandler *v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // edx
  __int64 v12; // r8
  void *v13; // rax
  __int64 v14; // rax
  CIdentityProfileHandler *v15; // rcx
  unsigned int v16; // ebx
  unsigned int v18; // ebp
  int v19; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v20[10]; // [rsp+38h] [rbp-50h] BYREF

  v19 = 0;
  v20[1] = "CConnectedUser::InitializeConnectedUser";
  v20[0] = &v19;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CConnectedUser::InitializeConnectedUser");
    v8 = WPP_GLOBAL_Control;
  }
  if ( !memcmp_0(a3, &xmmword_18001E7E0, 0x10u) )
  {
    v19 = -2147024846;
    CLogBlock::~CLogBlock((CLogBlock *)v20, v9, v10);
    return 2147942450LL;
  }
  else
  {
    if ( a4 )
    {
      if ( *((_QWORD *)this + 11) )
      {
        v16 = -2147023649;
        v19 = -2147023649;
        if ( v8 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v8 + 2), 11, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids, 2147943647LL);
          v16 = v19;
        }
        CLogBlock::~CLogBlock((CLogBlock *)v20, v9, v10);
        return v16;
      }
      if ( !memcmp_0(a3, &GUID_NULL, 0x10u) )
      {
        v13 = (void *)(*(__int64 (__fastcall **)(struct IConnectedUserSite *))(*(_QWORD *)a4 + 24LL))(a4);
        v19 = LookupProviderGuidFromSam(v13, a2, (struct _GUID *)((char *)this + 68));
        if ( v19 < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
LABEL_17:
            if ( v19 >= 0 )
            {
              *((_DWORD *)this + 16) = a2;
              *((_QWORD *)this + 11) = a4;
              (*(void (__fastcall **)(struct IConnectedUserSite *))(*(_QWORD *)a4 + 8LL))(a4);
              v15 = WPP_GLOBAL_Control;
            }
LABEL_19:
            v16 = v19;
            if ( v19 < 0 )
            {
              if ( v15 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
                return v16;
              if ( (*((_BYTE *)v15 + 28) & 4) != 0 )
              {
                WPP_SF_sL(*((_QWORD *)v15 + 2), v11, v12, (unsigned int)"CConnectedUser::InitializeConnectedUser", v19);
                v15 = WPP_GLOBAL_Control;
              }
            }
            if ( v15 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x400) != 0 )
              WPP_SF_s(*((_QWORD *)v15 + 2), 12, v12, "CConnectedUser::InitializeConnectedUser");
            return v16;
          }
          WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids, a2, v19);
        }
        else
        {
          v14 = *(_QWORD *)((char *)this + 68) - *(_QWORD *)&GUID_NULL.Data1;
          if ( !v14 )
            v14 = *(_QWORD *)((char *)this + 76) - *(_QWORD *)GUID_NULL.Data4;
          if ( !v14 )
          {
            v19 = -2147024809;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            {
              goto LABEL_19;
            }
            WPP_SF_DD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              12,
              WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids,
              a2,
              -2147024809);
          }
        }
      }
      else
      {
        *(struct _GUID *)((char *)this + 68) = *a3;
      }
      v15 = WPP_GLOBAL_Control;
      goto LABEL_17;
    }
    v18 = -2147024809;
    v19 = -2147024809;
    if ( v8 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v8 + 2), 10, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids, 2147942487LL);
      v18 = v19;
    }
    CLogBlock::~CLogBlock((CLogBlock *)v20, v9, v10);
    return v18;
  }
}

```

## disassembly

```asm
0x1800037a0  push    rbx
0x1800037a2  push    rbp
0x1800037a3  push    rsi
0x1800037a4  push    rdi
0x1800037a5  push    r12
0x1800037a7  push    r14
0x1800037a9  push    r15
0x1800037ab  sub     rsp, 50h
0x1800037af  mov     rbx, r9
0x1800037b2  mov     rbp, r8
0x1800037b5  mov     r14d, edx
0x1800037b8  mov     rdi, rcx
0x1800037bb  mov     [rsp+88h+var_58], 0
0x1800037c3  lea     r12, aCconnecteduser_18; "CConnectedUser::InitializeConnectedUser"
0x1800037ca  mov     [rsp+88h+var_48], r12
0x1800037cf  lea     rax, [rsp+88h+var_58]
0x1800037d4  mov     [rsp+88h+var_50], rax
0x1800037d9  lea     r15, WPP_GLOBAL_Control
0x1800037e0  mov     rsi, cs:WPP_GLOBAL_Control
0x1800037e7  cmp     rsi, r15
0x1800037ea  jz      short loc_1800037F9
0x1800037ec  test    dword ptr [rsi+1Ch], 400h
0x1800037f3  jnz     loc_1800039BF
0x1800037f9  mov     r8d, 10h; Size
0x1800037ff  lea     rdx, xmmword_18001E7E0; Buf2
0x180003806  mov     rcx, rbp; Buf1
0x180003809  call    memcmp_0
0x18000380e  test    eax, eax
0x180003810  jz      loc_180003951
0x180003816  test    rbx, rbx
0x180003819  jz      loc_1800039DC
0x18000381f  cmp     qword ptr [rdi+58h], 0
0x180003824  jnz     loc_1800039A2
0x18000382a  mov     r8d, 10h; Size
0x180003830  lea     rdx, GUID_NULL; Buf2
0x180003837  mov     rcx, rbp; Buf1
0x18000383a  call    memcmp_0
0x18000383f  test    eax, eax
0x180003841  jnz     short loc_1800038B7
0x180003843  mov     rax, [rbx]
0x180003846  mov     rcx, rbx
0x180003849  mov     rax, [rax+18h]
0x18000384d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003852  mov     rcx, rax; void *
0x180003855  lea     r8, [rdi+44h]; struct _GUID *
0x180003859  mov     edx, r14d; unsigned int
0x18000385c  call    ?LookupProviderGuidFromSam@@YAJPEAXKPEAU_GUID@@@Z; LookupProviderGuidFromSam(void *,ulong,_GUID *)
0x180003861  mov     [rsp+88h+var_58], eax
0x180003865  test    eax, eax
0x180003867  js      loc_18000391A
0x18000386d  mov     rax, [rdi+44h]
0x180003871  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180003878  jnz     short loc_180003885
0x18000387a  mov     rax, [rdi+4Ch]
0x18000387e  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180003885  test    rax, rax
0x180003888  jnz     short loc_1800038BF
0x18000388a  mov     ebp, 80070057h
0x18000388f  mov     [rsp+88h+var_58], ebp
0x180003893  mov     rcx, cs:WPP_GLOBAL_Control
0x18000389a  cmp     rcx, r15
0x18000389d  jz      short loc_1800038EB
0x18000389f  test    byte ptr [rcx+1Ch], 4
0x1800038a3  jz      short loc_1800038EB
0x1800038a5  mov     edx, 0Ch
0x1800038aa  mov     [rsp+88h+var_68], 80070057h
0x1800038b2  jmp     loc_180003939
0x1800038b7  movaps  xmm0, xmmword ptr [rbp+0]
0x1800038bb  movups  xmmword ptr [rdi+44h], xmm0
0x1800038bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038c6  cmp     [rsp+88h+var_58], 0
0x1800038cb  jl      short loc_1800038EB
0x1800038cd  mov     [rdi+40h], r14d
0x1800038d1  mov     [rdi+58h], rbx
0x1800038d5  mov     rax, [rbx]
0x1800038d8  mov     rcx, rbx
0x1800038db  mov     rax, [rax+8]
0x1800038df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038eb  mov     ebx, [rsp+88h+var_58]
0x1800038ef  test    ebx, ebx
0x1800038f1  js      loc_180003977
0x1800038f7  cmp     rcx, r15
0x1800038fa  jz      short loc_180003909
0x1800038fc  test    dword ptr [rcx+1Ch], 400h
0x180003903  jnz     loc_180003A4A
0x180003909  mov     eax, ebx
0x18000390b  add     rsp, 50h
0x18000390f  pop     r15
0x180003911  pop     r14
0x180003913  pop     r12
0x180003915  pop     rdi
0x180003916  pop     rsi
0x180003917  pop     rbp
0x180003918  pop     rbx
0x180003919  retn
0x18000391a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003921  cmp     rcx, r15
0x180003924  jz      short loc_1800038C6
0x180003926  test    byte ptr [rcx+1Ch], 4
0x18000392a  jz      short loc_1800038C6
0x18000392c  mov     edx, 0Dh
0x180003931  mov     eax, [rsp+88h+var_58]
0x180003935  mov     [rsp+88h+var_68], eax
0x180003939  mov     r9d, r14d
0x18000393c  lea     r8, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids
0x180003943  mov     rcx, [rcx+10h]
0x180003947  call    WPP_SF_DD
0x18000394c  jmp     loc_1800038BF
0x180003951  mov     [rsp+88h+var_58], 80070032h
0x180003959  lea     rcx, [rsp+88h+var_50]; this
0x18000395e  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x180003963  mov     eax, 80070032h
0x180003968  add     rsp, 50h
0x18000396c  pop     r15
0x18000396e  pop     r14
0x180003970  pop     r12
0x180003972  pop     rdi
0x180003973  pop     rsi
0x180003974  pop     rbp
0x180003975  pop     rbx
0x180003976  retn
0x180003977  cmp     rcx, r15
0x18000397a  jz      short loc_180003909
0x18000397c  test    byte ptr [rcx+1Ch], 4
0x180003980  jz      loc_1800038F7
0x180003986  mov     [rsp+88h+var_68], ebx
0x18000398a  mov     r9, r12
0x18000398d  mov     rcx, [rcx+10h]
0x180003991  call    WPP_SF_sL
0x180003996  mov     rcx, cs:WPP_GLOBAL_Control
0x18000399d  jmp     loc_1800038F7
0x1800039a2  mov     ebx, 800704DFh
0x1800039a7  mov     [rsp+88h+var_58], ebx
0x1800039ab  cmp     rsi, r15
0x1800039ae  jnz     short loc_180003A20
0x1800039b0  lea     rcx, [rsp+88h+var_50]; this
0x1800039b5  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x1800039ba  jmp     loc_180003909
0x1800039bf  mov     edx, 0Ah
0x1800039c4  mov     r9, r12
0x1800039c7  mov     rcx, [rsi+10h]
0x1800039cb  call    WPP_SF_s
0x1800039d0  mov     rsi, cs:WPP_GLOBAL_Control
0x1800039d7  jmp     loc_1800037F9
0x1800039dc  mov     ebp, 80070057h
0x1800039e1  mov     [rsp+88h+var_58], ebp
0x1800039e5  cmp     rsi, r15
0x1800039e8  jz      short loc_180003A0F
0x1800039ea  test    byte ptr [rsi+1Ch], 4
0x1800039ee  jz      short loc_180003A0F
0x1800039f0  mov     edx, 0Ah
0x1800039f5  mov     r9d, 80070057h
0x1800039fb  lea     r8, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids
0x180003a02  mov     rcx, [rsi+10h]
0x180003a06  call    WPP_SF_d
0x180003a0b  mov     ebp, [rsp+88h+var_58]
0x180003a0f  lea     rcx, [rsp+88h+var_50]; this
0x180003a14  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x180003a19  mov     eax, ebp
0x180003a1b  jmp     loc_18000390B
0x180003a20  test    byte ptr [rsi+1Ch], 4
0x180003a24  jz      short loc_1800039B0
0x180003a26  mov     edx, 0Bh
0x180003a2b  mov     r9d, 800704DFh
0x180003a31  lea     r8, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids
0x180003a38  mov     rcx, [rsi+10h]
0x180003a3c  call    WPP_SF_d
0x180003a41  mov     ebx, [rsp+88h+var_58]
0x180003a45  jmp     loc_1800039B0
0x180003a4a  mov     edx, 0Ch
0x180003a4f  mov     r9, r12
0x180003a52  mov     rcx, [rcx+10h]
0x180003a56  call    WPP_SF_s
0x180003a5b  jmp     loc_180003909
```
