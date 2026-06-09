# CConnectedUser::DisconnectLocalUser(ushort const *,ushort const *,uchar *,ulong)

- ea: `0x180018040`
- end: `0x1800183d6`
- name: `?DisconnectLocalUser@CConnectedUser@@UEAAJPEBG0PEAEK@Z`
- size: `918`
- prototype: `__int64 __fastcall(CConnectedUser *this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003560`
- `0x18000acb0`
- `0x18000e39c`
- `0x180014430`
- `0x1800144b4`
- `0x1800144f4`
- `0x180018040`
- `0x180018dc8`
- `0x180019750`
- `0x18001b010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180018267`
- `ntdll!RtlInitUnicodeString` at `0x1800182d0`
- `ntdll!RtlInitUnicodeString` at `0x180018267`
- `ntdll!RtlInitUnicodeString` at `0x1800182d0`
- `SAMLIB!SamQueryInformationUser` at `0x1800181f0`
- `SAMLIB!SamQueryInformationUser` at `0x18001827c`
- `SAMLIB!SamQueryInformationUser` at `0x1800181f0`
- `SAMLIB!SamQueryInformationUser` at `0x18001827c`
- `SAMLIB!SamFreeMemory` at `0x180018370`
- `SAMLIB!SamFreeMemory` at `0x18001837f`
- `SAMLIB!SamFreeMemory` at `0x180018370`
- `SAMLIB!SamFreeMemory` at `0x18001837f`
- `SAMLIB!SamCloseHandle` at `0x180018361`
- `SAMLIB!SamCloseHandle` at `0x180018361`
- `SAMLIB!SamOpenUser` at `0x180018195`
- `SAMLIB!SamOpenUser` at `0x180018195`

## pseudocode

```c
__int64 __fastcall CConnectedUser::DisconnectLocalUser(
        CConnectedUser *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned int a5)
{
  int v8; // r12d
  int v9; // ecx
  int v10; // r8d
  __int64 v11; // r9
  CIdentityProfileHandler *v12; // rcx
  __int64 v13; // rdx
  _QWORD *v14; // rdi
  __int64 v15; // rax
  unsigned int v16; // ebx
  __int64 v17; // rax
  int v18; // ebx
  CIdentityProfileHandler *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rax
  int v22; // eax
  int v23; // ecx
  unsigned int v24; // ebx
  __int64 v25; // rdx
  __int64 v26; // r8
  int v28; // [rsp+30h] [rbp-51h] BYREF
  __int64 v29; // [rsp+38h] [rbp-49h] BYREF
  struct _UNICODE_STRING *v30; // [rsp+40h] [rbp-41h] BYREF
  unsigned int *v31; // [rsp+48h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-31h] BYREF
  struct _UNICODE_STRING v33; // [rsp+60h] [rbp-21h] BYREF
  _BYTE v34[16]; // [rsp+70h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v35; // [rsp+80h] [rbp-1h] BYREF

  v29 = 0;
  v28 = 0;
  v31 = 0;
  v30 = 0;
  v8 = (int)a4;
  DestinationString = 0;
  v33 = 0;
  CLogBlock::CLogBlock((CLogBlock *)v34, "CConnectedUser::DisconnectLocalUser", &v28);
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v9, (int)&DisconnectLocalUserStart, v10, v11, &v35);
  if ( !a3 )
  {
    v28 = -2147024809;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v13 = 68;
LABEL_7:
      v11 = 2147942487LL;
LABEL_8:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids, v11);
      goto LABEL_45;
    }
    goto LABEL_45;
  }
  v14 = (_QWORD *)((char *)this + 68);
  v15 = *(_QWORD *)((char *)this + 68) - 0x4967A148B16898C6LL;
  if ( *(_QWORD *)((char *)this + 68) == 0x4967A148B16898C6LL )
    v15 = *(_QWORD *)((char *)this + 76) - 0x2085DA55D7647191LL;
  if ( v15 )
  {
    v16 = *((_DWORD *)this + 16);
    v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 24LL))(*((_QWORD *)this + 11));
    v18 = SamOpenUser(v17, 0x2000000, v16, &v29);
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          70,
          WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids,
          *((unsigned int *)this + 16),
          v18);
      }
      goto LABEL_20;
    }
    v18 = SamQueryInformationUser(v29, 28, &v31);
    if ( v18 < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_20;
      }
      v20 = 71;
      goto LABEL_25;
    }
    v11 = *v31;
    if ( (v11 & 0x40000) == 0 )
      goto LABEL_42;
    v21 = *v14 - *((_QWORD *)v31 + 12);
    if ( *v14 == *((_QWORD *)v31 + 12) )
      v21 = *(_QWORD *)((char *)this + 76) - *((_QWORD *)v31 + 13);
    if ( v21 )
    {
LABEL_42:
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids, v11);
      }
      v28 = -2147019873;
      goto LABEL_45;
    }
    if ( !a2 )
    {
      v22 = SamQueryInformationUser(v29, 7, &v30);
      v11 = (unsigned int)v22;
      if ( v22 < 0 )
      {
        LODWORD(v11) = v22 | 0x10000000;
        v28 = v22 | 0x10000000;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v13 = 73;
          goto LABEL_8;
        }
        goto LABEL_45;
      }
      DestinationString = *v30;
      goto LABEL_37;
    }
LABEL_31:
    RtlInitUnicodeString(&DestinationString, a2);
LABEL_37:
    RtlInitUnicodeString(&v33, a3);
    v18 = LsaDisconnectLocalUser((int)this + 68, v8, a5, (unsigned int)&DestinationString, (__int64)&v33);
    if ( v18 >= 0 )
      goto LABEL_45;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
LABEL_20:
      v28 = v18 | 0x10000000;
      goto LABEL_45;
    }
    v20 = 74;
LABEL_25:
    WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids, (unsigned int)v18);
    goto LABEL_20;
  }
  if ( a2 )
    goto LABEL_31;
  v28 = -2147024809;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v13 = 69;
    goto LABEL_7;
  }
LABEL_45:
  if ( v29 )
    SamCloseHandle();
  if ( v30 )
    SamFreeMemory();
  v23 = (int)v31;
  if ( v31 )
    SamFreeMemory();
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v23, (int)&DisconnectLocalUserStop, v10, v11, &v35);
  v24 = MapErrorCodes(v28);
  CLogBlock::~CLogBlock((CLogBlock *)v34, v25, v26);
  return v24;
}

```

## disassembly

```asm
0x180018040  push    rbp
0x180018042  push    rbx
0x180018043  push    rsi
0x180018044  push    rdi
0x180018045  push    r12
0x180018047  push    r14
0x180018049  push    r15
0x18001804b  lea     rbp, [rsp-1Fh]
0x180018050  sub     rsp, 0A0h
0x180018057  mov     rax, cs:__security_cookie
0x18001805e  xor     rax, rsp
0x180018061  mov     [rbp+4Fh+var_40], rax
0x180018065  mov     r15, r8
0x180018068  mov     [rbp+4Fh+var_98], 0
0x180018070  mov     rsi, rdx
0x180018073  mov     [rbp+4Fh+var_A0], 0
0x18001807a  mov     r14, rcx
0x18001807d  mov     [rbp+4Fh+var_88], 0
0x180018085  xorps   xmm0, xmm0
0x180018088  mov     [rbp+4Fh+var_90], 0
0x180018090  xorps   xmm1, xmm1
0x180018093  lea     r8, [rbp+4Fh+var_A0]; int *
0x180018097  lea     rdx, aCconnecteduser_17; "CConnectedUser::DisconnectLocalUser"
0x18001809e  mov     r12, r9
0x1800180a1  lea     rcx, [rbp+4Fh+var_60]; this
0x1800180a5  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1800180a9  movups  xmmword ptr [rbp+4Fh+var_70.Length], xmm1
0x1800180ad  call    ??0CLogBlock@@QEAA@PEBDPEAJ@Z; CLogBlock::CLogBlock(char const *,long *)
0x1800180b2  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x1800180b9  jz      short loc_1800180D0
0x1800180bb  lea     rax, [rbp+4Fh+var_50]
0x1800180bf  lea     rdx, DisconnectLocalUserStart; int
0x1800180c6  mov     [rsp+0D0h+var_B0], rax; PEVENT_DATA_DESCRIPTOR
0x1800180cb  call    McGenEventWrite_EventWriteTransfer
0x1800180d0  test    r15, r15
0x1800180d3  jnz     short loc_18001811C
0x1800180d5  mov     [rbp+4Fh+var_A0], 80070057h
0x1800180dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800180e3  lea     rax, WPP_GLOBAL_Control
0x1800180ea  cmp     rcx, rax
0x1800180ed  jz      loc_180018358
0x1800180f3  test    byte ptr [rcx+1Ch], 4
0x1800180f7  jz      loc_180018358
0x1800180fd  lea     edx, [r15+44h]
0x180018101  mov     r9d, 80070057h
0x180018107  mov     rcx, [rcx+10h]
0x18001810b  lea     r8, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids
0x180018112  call    WPP_SF_d
0x180018117  jmp     loc_180018358
0x18001811c  lea     rdi, [r14+44h]
0x180018120  mov     rax, [rdi]
0x180018123  sub     rax, qword ptr cs:xmmword_18001E7E0
0x18001812a  jnz     short loc_180018137
0x18001812c  mov     rax, [rdi+8]
0x180018130  sub     rax, qword ptr cs:xmmword_18001E7E0+8
0x180018137  test    rax, rax
0x18001813a  jnz     short loc_180018172
0x18001813c  test    rsi, rsi
0x18001813f  jnz     loc_180018260
0x180018145  mov     [rbp+4Fh+var_A0], 80070057h
0x18001814c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018153  lea     rax, WPP_GLOBAL_Control
0x18001815a  cmp     rcx, rax
0x18001815d  jz      loc_180018358
0x180018163  test    byte ptr [rcx+1Ch], 4
0x180018167  jz      loc_180018358
0x18001816d  lea     edx, [rsi+45h]
0x180018170  jmp     short loc_180018101
0x180018172  mov     rcx, [r14+58h]
0x180018176  mov     ebx, [r14+40h]
0x18001817a  mov     rax, [rcx]
0x18001817d  mov     rax, [rax+18h]
0x180018181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018186  lea     r9, [rbp+4Fh+var_98]
0x18001818a  mov     r8d, ebx
0x18001818d  mov     edx, 2000000h
0x180018192  mov     rcx, rax
0x180018195  call    cs:__imp_SamOpenUser
0x18001819b  mov     ebx, eax
0x18001819d  test    eax, eax
0x18001819f  jns     short loc_1800181E3
0x1800181a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181a8  lea     rax, WPP_GLOBAL_Control
0x1800181af  cmp     rcx, rax
0x1800181b2  jz      short loc_1800181D7
0x1800181b4  test    byte ptr [rcx+1Ch], 4
0x1800181b8  jz      short loc_1800181D7
0x1800181ba  mov     r9d, [r14+40h]
0x1800181be  lea     r8, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids
0x1800181c5  mov     rcx, [rcx+10h]
0x1800181c9  mov     edx, 46h ; 'F'
0x1800181ce  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x1800181d2  call    WPP_SF_DD
0x1800181d7  bts     ebx, 1Ch
0x1800181db  mov     [rbp+4Fh+var_A0], ebx
0x1800181de  jmp     loc_180018358
0x1800181e3  mov     rcx, [rbp+4Fh+var_98]
0x1800181e7  lea     r8, [rbp+4Fh+var_88]
0x1800181eb  mov     edx, 1Ch
0x1800181f0  call    cs:__imp_SamQueryInformationUser
0x1800181f6  mov     ebx, eax
0x1800181f8  test    eax, eax
0x1800181fa  jns     short loc_18001822F
0x1800181fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180018203  lea     rax, WPP_GLOBAL_Control
0x18001820a  cmp     rcx, rax
0x18001820d  jz      short loc_1800181D7
0x18001820f  test    byte ptr [rcx+1Ch], 4
0x180018213  jz      short loc_1800181D7
0x180018215  mov     edx, 47h ; 'G'
0x18001821a  mov     rcx, [rcx+10h]
0x18001821e  lea     r8, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids
0x180018225  mov     r9d, ebx
0x180018228  call    WPP_SF_d
0x18001822d  jmp     short loc_1800181D7
0x18001822f  mov     rcx, [rbp+4Fh+var_88]
0x180018233  mov     r9d, [rcx]
0x180018236  bt      r9d, 12h
0x18001823b  jnb     loc_180018323
0x180018241  mov     rax, [rdi]
0x180018244  sub     rax, [rcx+60h]
0x180018248  jnz     short loc_180018252
0x18001824a  mov     rax, [rdi+8]
0x18001824e  sub     rax, [rcx+68h]
0x180018252  test    rax, rax
0x180018255  jnz     loc_180018323
0x18001825b  test    rsi, rsi
0x18001825e  jz      short loc_18001826F
0x180018260  mov     rdx, rsi; SourceString
0x180018263  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x180018267  call    cs:__imp_RtlInitUnicodeString
0x18001826d  jmp     short loc_1800182C9
0x18001826f  mov     rcx, [rbp+4Fh+var_98]
0x180018273  lea     r8, [rbp+4Fh+var_90]
0x180018277  mov     edx, 7
0x18001827c  call    cs:__imp_SamQueryInformationUser
0x180018282  mov     r9d, eax
0x180018285  test    eax, eax
0x180018287  jns     short loc_1800182BD
0x180018289  bts     r9d, 1Ch
0x18001828e  mov     [rbp+4Fh+var_A0], r9d
0x180018292  mov     rcx, cs:WPP_GLOBAL_Control
0x180018299  lea     rax, WPP_GLOBAL_Control
0x1800182a0  cmp     rcx, rax
0x1800182a3  jz      loc_180018358
0x1800182a9  test    byte ptr [rcx+1Ch], 4
0x1800182ad  jz      loc_180018358
0x1800182b3  mov     edx, 49h ; 'I'
0x1800182b8  jmp     loc_180018107
0x1800182bd  mov     rax, [rbp+4Fh+var_90]
0x1800182c1  movups  xmm0, xmmword ptr [rax]
0x1800182c4  movdqu  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1800182c9  mov     rdx, r15; SourceString
0x1800182cc  lea     rcx, [rbp+4Fh+var_70]; DestinationString
0x1800182d0  call    cs:__imp_RtlInitUnicodeString
0x1800182d6  mov     r8d, [rbp+4Fh+arg_20]
0x1800182da  lea     rax, [rbp+4Fh+var_70]
0x1800182de  lea     r9, [rbp+4Fh+DestinationString]
0x1800182e2  mov     [rsp+0D0h+var_B0], rax
0x1800182e7  mov     rdx, r12
0x1800182ea  mov     rcx, rdi
0x1800182ed  call    LsaDisconnectLocalUser
0x1800182f2  mov     ebx, eax
0x1800182f4  test    eax, eax
0x1800182f6  jns     short loc_180018358
0x1800182f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182ff  lea     rax, WPP_GLOBAL_Control
0x180018306  cmp     rcx, rax
0x180018309  jz      loc_1800181D7
0x18001830f  test    byte ptr [rcx+1Ch], 4
0x180018313  jz      loc_1800181D7
0x180018319  mov     edx, 4Ah ; 'J'
0x18001831e  jmp     loc_18001821A
0x180018323  mov     rcx, cs:WPP_GLOBAL_Control
0x18001832a  lea     rax, WPP_GLOBAL_Control
0x180018331  cmp     rcx, rax
0x180018334  jz      short loc_180018351
0x180018336  test    byte ptr [rcx+1Ch], 4
0x18001833a  jz      short loc_180018351
0x18001833c  mov     rcx, [rcx+10h]
0x180018340  lea     r8, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids
0x180018347  mov     edx, 48h ; 'H'
0x18001834c  call    WPP_SF_d
0x180018351  mov     [rbp+4Fh+var_A0], 8007139Fh
0x180018358  mov     rcx, [rbp+4Fh+var_98]
0x18001835c  test    rcx, rcx
0x18001835f  jz      short loc_180018367
0x180018361  call    cs:__imp_SamCloseHandle
0x180018367  mov     rcx, [rbp+4Fh+var_90]
0x18001836b  test    rcx, rcx
0x18001836e  jz      short loc_180018376
0x180018370  call    cs:__imp_SamFreeMemory
0x180018376  mov     rcx, [rbp+4Fh+var_88]
0x18001837a  test    rcx, rcx
0x18001837d  jz      short loc_180018385
0x18001837f  call    cs:__imp_SamFreeMemory
0x180018385  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x18001838c  jz      short loc_1800183A3
0x18001838e  lea     rax, [rbp+4Fh+var_50]
0x180018392  lea     rdx, DisconnectLocalUserStop; int
0x180018399  mov     [rsp+0D0h+var_B0], rax; PEVENT_DATA_DESCRIPTOR
0x18001839e  call    McGenEventWrite_EventWriteTransfer
0x1800183a3  mov     ecx, [rbp+4Fh+var_A0]; int
0x1800183a6  call    ?MapErrorCodes@@YAJJ@Z; MapErrorCodes(long)
0x1800183ab  lea     rcx, [rbp+4Fh+var_60]; this
0x1800183af  mov     ebx, eax
0x1800183b1  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x1800183b6  mov     eax, ebx
0x1800183b8  mov     rcx, [rbp+4Fh+var_40]
0x1800183bc  xor     rcx, rsp; StackCookie
0x1800183bf  call    __security_check_cookie
0x1800183c4  add     rsp, 0A0h
0x1800183cb  pop     r15
0x1800183cd  pop     r14
0x1800183cf  pop     r12
0x1800183d1  pop     rdi
0x1800183d2  pop     rsi
0x1800183d3  pop     rbx
0x1800183d4  pop     rbp
0x1800183d5  retn
```
