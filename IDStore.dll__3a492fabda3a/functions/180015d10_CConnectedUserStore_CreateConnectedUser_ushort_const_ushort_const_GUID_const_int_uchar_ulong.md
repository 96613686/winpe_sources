# CConnectedUserStore::CreateConnectedUser(ushort const *,ushort const *,_GUID const &,int,uchar *,ulong)

- ea: `0x180015d10`
- end: `0x180016058`
- name: `?CreateConnectedUser@CConnectedUserStore@@UEAAJPEBG0AEBU_GUID@@HPEAEK@Z`
- size: `840`
- prototype: `__int64 __fastcall(CConnectedUserStore *__hidden this, PCWSTR SourceString, wchar_t *String1, const struct _GUID *, int, char *AuthIdentityByteArray, unsigned int AuthIdentityLength)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003560`
- `0x18000acb0`
- `0x18000e39c`
- `0x180014430`
- `0x1800144b4`
- `0x180014540`
- `0x180015d10`
- `0x180016d1c`
- `0x180017328`
- `0x180018ca0`
- `0x180019750`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180015fed`
- `ntdll!RtlInitUnicodeString` at `0x180015ffa`
- `ntdll!RtlInitUnicodeString` at `0x180015fed`
- `ntdll!RtlInitUnicodeString` at `0x180015ffa`

## string_xrefs

- `0x180015d5b`: `CConnectedUserStore::CreateConnectedUser`

## pseudocode

```c
__int64 __fastcall CConnectedUserStore::CreateConnectedUser(
        CConnectedUserStore *this,
        PCWSTR SourceString,
        wchar_t *String1,
        const struct _GUID *a4,
        int a5,
        char *AuthIdentityByteArray,
        unsigned int AuthIdentityLength)
{
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  CIdentityProfileHandler *v14; // r10
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // ecx
  __int64 v19; // r8
  int v20; // r9d
  __int64 v21; // rax
  unsigned int v22; // eax
  __int64 v23; // r10
  unsigned int v24; // ebx
  int IdentityProviderName; // eax
  int ConnectedUser; // eax
  int v28; // [rsp+30h] [rbp-51h] BYREF
  wchar_t *v29; // [rsp+38h] [rbp-49h] BYREF
  struct _UNICODE_STRING v30; // [rsp+40h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-31h] BYREF
  _BYTE v32[16]; // [rsp+60h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+70h] [rbp-11h] BYREF

  v28 = 0;
  v29 = 0;
  DestinationString = 0;
  v30 = 0;
  CLogBlock::CLogBlock((CLogBlock *)v32, "CConnectedUserStore::CreateConnectedUser", &v28);
  if ( !AuthIdentityByteArray || !AuthIdentityLength )
  {
    if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v11, (int)&CreateUnverifiedUserStart, v12, v13, &v33);
    if ( AuthIdentityByteArray )
    {
      if ( AuthIdentityLength )
        goto LABEL_5;
    }
    else if ( !AuthIdentityLength )
    {
      goto LABEL_5;
    }
    v28 = -2147024809;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_28;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, 2147942487LL);
    goto LABEL_19;
  }
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v11, (int)&CreateVerifiedUserStart, v12, v13, &v33);
LABEL_5:
  if ( !String1 )
  {
    v28 = -2147467261;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_28;
    }
    v15 = 39;
    v16 = 2147500035LL;
    goto LABEL_9;
  }
  v21 = *(_QWORD *)&a4->Data1 - 0x4967A148B16898C6LL;
  if ( *(_QWORD *)&a4->Data1 == 0x4967A148B16898C6LL )
    v21 = *(_QWORD *)a4->Data4 - 0x2085DA55D7647191LL;
  if ( !v21 )
  {
    v28 = -2147024846;
    goto LABEL_28;
  }
  IdentityProviderName = CConnectedUserStore::GetIdentityProviderName(this, a4, (const unsigned __int16 **)&v29);
  v28 = IdentityProviderName;
  if ( IdentityProviderName >= 0 )
  {
    if ( AuthIdentityByteArray
      && (IdentityProviderName = CConnectedUserStore::ValidateAuthBuffer(
                                   AuthIdentityByteArray,
                                   AuthIdentityLength,
                                   String1,
                                   v29),
          v28 = IdentityProviderName,
          IdentityProviderName < 0) )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v15 = 41;
        goto LABEL_38;
      }
    }
    else
    {
      if ( SourceString )
        RtlInitUnicodeString(&DestinationString, SourceString);
      RtlInitUnicodeString(&v30, String1);
      ConnectedUser = LsaCreateConnectedUser(
                        (unsigned int)&DestinationString,
                        (unsigned int)&v30,
                        a5,
                        (_DWORD)a4,
                        (__int64)AuthIdentityByteArray,
                        AuthIdentityLength);
      if ( ConnectedUser >= 0 )
        goto LABEL_19;
      IdentityProviderName = ConnectedUser | 0x10000000;
      v28 = IdentityProviderName;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v15 = 42;
        goto LABEL_38;
      }
    }
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v15 = 40;
LABEL_38:
      v16 = (unsigned int)IdentityProviderName;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v16);
LABEL_19:
      v14 = WPP_GLOBAL_Control;
    }
  }
  if ( v28 >= 0 )
  {
    if ( v14 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 0x10) != 0 )
      WPP_SF_S(*((_QWORD *)v14 + 2), 43, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, String1);
    goto LABEL_31;
  }
LABEL_28:
  v22 = MapErrorCodes(v28);
  v28 = v22;
  if ( (CIdentityProfileHandler **)v23 != &WPP_GLOBAL_Control && (*(_BYTE *)(v23 + 28) & 4) != 0 )
    WPP_SF_d(*(_QWORD *)(v23 + 16), 44, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v22);
LABEL_31:
  if ( (Microsoft_Windows_Security_IdentityStoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v18, (int)&CreateUserStop, v19, v20, &v33);
  v24 = v28;
  CLogBlock::~CLogBlock((CLogBlock *)v32, v17, v19);
  return v24;
}

```

## disassembly

```asm
0x180015d10  push    rbp
0x180015d12  push    rbx
0x180015d13  push    rsi
0x180015d14  push    rdi
0x180015d15  push    r12
0x180015d17  push    r14
0x180015d19  push    r15
0x180015d1b  lea     rbp, [rsp-0Fh]
0x180015d20  sub     rsp, 90h
0x180015d27  mov     rax, cs:__security_cookie
0x180015d2e  xor     rax, rsp
0x180015d31  mov     [rbp+3Fh+var_40], rax
0x180015d35  mov     rdi, [rbp+3Fh+AuthIdentityByteArray]
0x180015d39  mov     r14, r8
0x180015d3c  mov     r15, rdx
0x180015d3f  mov     [rbp+3Fh+var_90], 0
0x180015d46  mov     r12, rcx
0x180015d49  mov     [rbp+3Fh+var_88], 0
0x180015d51  xorps   xmm0, xmm0
0x180015d54  lea     r8, [rbp+3Fh+var_90]; int *
0x180015d58  xorps   xmm1, xmm1
0x180015d5b  lea     rdx, aCconnecteduser_3; "CConnectedUserStore::CreateConnectedUse"...
0x180015d62  lea     rcx, [rbp+3Fh+var_60]; this
0x180015d66  mov     rsi, r9
0x180015d69  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x180015d6d  movups  xmmword ptr [rbp+3Fh+var_80.Length], xmm1
0x180015d71  call    ??0CLogBlock@@QEAA@PEBDPEAJ@Z; CLogBlock::CLogBlock(char const *,long *)
0x180015d76  mov     ebx, [rbp+3Fh+AuthIdentityLength]
0x180015d79  lea     rax, WPP_GLOBAL_Control
0x180015d80  test    rdi, rdi
0x180015d83  jz      short loc_180015DF5
0x180015d85  test    ebx, ebx
0x180015d87  jz      short loc_180015DF5
0x180015d89  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x180015d90  jz      short loc_180015DA7
0x180015d92  lea     rax, [rbp+3Fh+var_50]
0x180015d96  lea     rdx, CreateVerifiedUserStart; int
0x180015d9d  mov     [rsp+0C0h+var_A0], rax; PEVENT_DATA_DESCRIPTOR
0x180015da2  call    McGenEventWrite_EventWriteTransfer
0x180015da7  test    r14, r14
0x180015daa  jnz     loc_180015EA8
0x180015db0  mov     [rbp+3Fh+var_90], 80004003h
0x180015db7  mov     r10, cs:WPP_GLOBAL_Control
0x180015dbe  lea     rbx, WPP_GLOBAL_Control
0x180015dc5  cmp     r10, rbx
0x180015dc8  jz      loc_180015EDD
0x180015dce  test    byte ptr [r10+1Ch], 4
0x180015dd3  jz      loc_180015EDD
0x180015dd9  lea     edx, [r14+27h]
0x180015ddd  mov     r9d, 80004003h
0x180015de3  mov     rcx, [r10+10h]
0x180015de7  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x180015dee  call    WPP_SF_d
0x180015df3  jmp     short loc_180015E71
0x180015df5  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x180015dfc  jz      short loc_180015E1A
0x180015dfe  lea     rax, [rbp+3Fh+var_50]
0x180015e02  lea     rdx, CreateUnverifiedUserStart; int
0x180015e09  mov     [rsp+0C0h+var_A0], rax; PEVENT_DATA_DESCRIPTOR
0x180015e0e  call    McGenEventWrite_EventWriteTransfer
0x180015e13  lea     rax, WPP_GLOBAL_Control
0x180015e1a  test    rdi, rdi
0x180015e1d  jz      short loc_180015E25
0x180015e1f  test    ebx, ebx
0x180015e21  jz      short loc_180015E2D
0x180015e23  jmp     short loc_180015DA7
0x180015e25  test    ebx, ebx
0x180015e27  jz      loc_180015DA7
0x180015e2d  mov     [rbp+3Fh+var_90], 80070057h
0x180015e34  mov     r10, cs:WPP_GLOBAL_Control
0x180015e3b  cmp     r10, rax
0x180015e3e  jz      loc_180015ED6
0x180015e44  test    byte ptr [r10+1Ch], 4
0x180015e49  jz      loc_180015ED6
0x180015e4f  mov     rcx, [r10+10h]
0x180015e53  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x180015e5a  mov     edx, 26h ; '&'
0x180015e5f  mov     r9d, 80070057h
0x180015e65  call    WPP_SF_d
0x180015e6a  lea     rbx, WPP_GLOBAL_Control
0x180015e71  mov     r10, cs:WPP_GLOBAL_Control
0x180015e78  cmp     [rbp+3Fh+var_90], 0
0x180015e7c  jl      short loc_180015EDD
0x180015e7e  cmp     r10, rbx
0x180015e81  jz      loc_180015F0C
0x180015e87  test    byte ptr [r10+1Ch], 10h
0x180015e8c  jz      short loc_180015F0C
0x180015e8e  mov     rcx, [r10+10h]
0x180015e92  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x180015e99  mov     edx, 2Bh ; '+'
0x180015e9e  mov     r9, r14
0x180015ea1  call    WPP_SF_S
0x180015ea6  jmp     short loc_180015F0C
0x180015ea8  mov     rax, [rsi]
0x180015eab  sub     rax, cs:qword_18001E550
0x180015eb2  jnz     short loc_180015EBF
0x180015eb4  mov     rax, [rsi+8]
0x180015eb8  sub     rax, cs:qword_18001E558
0x180015ebf  test    rax, rax
0x180015ec2  jnz     loc_180015F56
0x180015ec8  mov     r10, cs:WPP_GLOBAL_Control
0x180015ecf  mov     [rbp+3Fh+var_90], 80070032h
0x180015ed6  lea     rbx, WPP_GLOBAL_Control
0x180015edd  mov     ecx, [rbp+3Fh+var_90]; int
0x180015ee0  call    ?MapErrorCodes@@YAJJ@Z; MapErrorCodes(long)
0x180015ee5  mov     [rbp+3Fh+var_90], eax
0x180015ee8  cmp     r10, rbx
0x180015eeb  jz      short loc_180015F0C
0x180015eed  test    byte ptr [r10+1Ch], 4
0x180015ef2  jz      short loc_180015F0C
0x180015ef4  mov     rcx, [r10+10h]
0x180015ef8  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x180015eff  mov     edx, 2Ch ; ','
0x180015f04  mov     r9d, eax
0x180015f07  call    WPP_SF_d
0x180015f0c  test    cs:Microsoft_Windows_Security_IdentityStoreEnableBits, 1
0x180015f13  jz      short loc_180015F2A
0x180015f15  lea     rax, [rbp+3Fh+var_50]
0x180015f19  lea     rdx, CreateUserStop; int
0x180015f20  mov     [rsp+0C0h+var_A0], rax; PEVENT_DATA_DESCRIPTOR
0x180015f25  call    McGenEventWrite_EventWriteTransfer
0x180015f2a  mov     ebx, [rbp+3Fh+var_90]
0x180015f2d  lea     rcx, [rbp+3Fh+var_60]; this
0x180015f31  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x180015f36  mov     eax, ebx
0x180015f38  mov     rcx, [rbp+3Fh+var_40]
0x180015f3c  xor     rcx, rsp; StackCookie
0x180015f3f  call    __security_check_cookie
0x180015f44  add     rsp, 90h
0x180015f4b  pop     r15
0x180015f4d  pop     r14
0x180015f4f  pop     r12
0x180015f51  pop     rdi
0x180015f52  pop     rsi
0x180015f53  pop     rbx
0x180015f54  pop     rbp
0x180015f55  retn
0x180015f56  lea     r8, [rbp+3Fh+var_88]; unsigned __int16 **
0x180015f5a  mov     rdx, rsi; struct _GUID *
0x180015f5d  mov     rcx, r12; this
0x180015f60  call    ?GetIdentityProviderName@CConnectedUserStore@@AEAAJAEBU_GUID@@PEAPEBG@Z; CConnectedUserStore::GetIdentityProviderName(_GUID const &,ushort const * *)
0x180015f65  mov     [rbp+3Fh+var_90], eax
0x180015f68  test    eax, eax
0x180015f6a  jns     short loc_180015F9B
0x180015f6c  mov     r10, cs:WPP_GLOBAL_Control
0x180015f73  lea     rbx, WPP_GLOBAL_Control
0x180015f7a  cmp     r10, rbx
0x180015f7d  jz      loc_180015E78
0x180015f83  test    byte ptr [r10+1Ch], 4
0x180015f88  jz      loc_180015E78
0x180015f8e  mov     edx, 28h ; '('
0x180015f93  mov     r9d, eax
0x180015f96  jmp     loc_180015DE3
0x180015f9b  test    rdi, rdi
0x180015f9e  jz      short loc_180015FE1
0x180015fa0  mov     r9, [rbp+3Fh+var_88]; wchar_t *
0x180015fa4  mov     r8, r14; String1
0x180015fa7  mov     edx, ebx; AuthIdentityLength
0x180015fa9  mov     rcx, rdi; AuthIdentityByteArray
0x180015fac  call    ?ValidateAuthBuffer@CConnectedUserStore@@CAJPEAEKPEBG1@Z; CConnectedUserStore::ValidateAuthBuffer(uchar *,ulong,ushort const *,ushort const *)
0x180015fb1  mov     [rbp+3Fh+var_90], eax
0x180015fb4  test    eax, eax
0x180015fb6  jns     short loc_180015FE1
0x180015fb8  mov     r10, cs:WPP_GLOBAL_Control
0x180015fbf  lea     rbx, WPP_GLOBAL_Control
0x180015fc6  cmp     r10, rbx
0x180015fc9  jz      loc_180015E78
0x180015fcf  test    byte ptr [r10+1Ch], 4
0x180015fd4  jz      loc_180015E78
0x180015fda  mov     edx, 29h ; ')'
0x180015fdf  jmp     short loc_180015F93
0x180015fe1  test    r15, r15
0x180015fe4  jz      short loc_180015FF3
0x180015fe6  mov     rdx, r15; SourceString
0x180015fe9  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x180015fed  call    cs:__imp_RtlInitUnicodeString
0x180015ff3  mov     rdx, r14; SourceString
0x180015ff6  lea     rcx, [rbp+3Fh+var_80]; DestinationString
0x180015ffa  call    cs:__imp_RtlInitUnicodeString
0x180016000  mov     r8d, [rbp+3Fh+arg_20]
0x180016004  lea     rdx, [rbp+3Fh+var_80]
0x180016008  mov     r9, rsi
0x18001600b  mov     [rsp+0C0h+var_98], ebx
0x18001600f  lea     rcx, [rbp+3Fh+DestinationString]
0x180016013  mov     [rsp+0C0h+var_A0], rdi
0x180016018  call    LsaCreateConnectedUser
0x18001601d  test    eax, eax
0x18001601f  jns     loc_180015E6A
0x180016025  bts     eax, 1Ch
0x180016029  mov     [rbp+3Fh+var_90], eax
0x18001602c  mov     r10, cs:WPP_GLOBAL_Control
0x180016033  lea     rbx, WPP_GLOBAL_Control
0x18001603a  cmp     r10, rbx
0x18001603d  jz      loc_180015E78
0x180016043  test    byte ptr [r10+1Ch], 4
0x180016048  jz      loc_180015E78
0x18001604e  mov     edx, 2Ah ; '*'
0x180016053  jmp     loc_180015F93
```
