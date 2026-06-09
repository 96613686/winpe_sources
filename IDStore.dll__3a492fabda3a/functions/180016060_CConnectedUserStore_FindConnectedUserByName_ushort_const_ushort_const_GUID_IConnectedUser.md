# CConnectedUserStore::FindConnectedUserByName(ushort const *,ushort const *,_GUID *,IConnectedUser * *)

- ea: `0x180016060`
- end: `0x1800163f9`
- name: `?FindConnectedUserByName@CConnectedUserStore@@UEAAJPEBG0PEAU_GUID@@PEAPEAUIConnectedUser@@@Z`
- size: `921`
- prototype: `__int64 __fastcall(CConnectedUserStore *__hidden this, wchar_t *, wchar_t *String1, struct _GUID *, struct IConnectedUser **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001064`
- `0x180003560`
- `0x1800035f0`
- `0x18000acb0`
- `0x18000e30c`
- `0x18000e39c`
- `0x1800144b4`
- `0x1800145a0`
- `0x180016060`
- `0x180016d1c`
- `0x18001719c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001639b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001639b`
- `SAMLIB!SamLookupNamesInDomain2` at `0x180016297`
- `SAMLIB!SamLookupNamesInDomain2` at `0x180016297`
- `SAMLIB!SamFreeMemory` at `0x1800163aa`
- `SAMLIB!SamFreeMemory` at `0x1800163b9`
- `SAMLIB!SamFreeMemory` at `0x1800163aa`
- `SAMLIB!SamFreeMemory` at `0x1800163b9`

## pseudocode

```c
__int64 __fastcall CConnectedUserStore::FindConnectedUserByName(
        CConnectedUserStore *this,
        wchar_t *a2,
        wchar_t *String1,
        struct _GUID *a4,
        struct IConnectedUser **a5)
{
  struct IConnectedUser **v9; // rsi
  CIdentityProfileHandler *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  __int64 v15; // rax
  int v16; // ebx
  unsigned int v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // r8
  struct CConnectedUser *v21; // [rsp+30h] [rbp-50h] BYREF
  unsigned int *v22; // [rsp+38h] [rbp-48h] BYREF
  wchar_t *Source; // [rsp+40h] [rbp-40h] BYREF
  __int64 v24; // [rsp+48h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-30h] BYREF
  struct _GUID v26; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v27[16]; // [rsp+70h] [rbp-10h] BYREF
  int IdentityProviderName; // [rsp+B8h] [rbp+38h] BYREF

  IdentityProviderName = 0;
  Source = 0;
  v22 = 0;
  v24 = 0;
  v21 = 0;
  v26 = 0;
  *(_OWORD *)pv = 0;
  CLogBlock::CLogBlock((CLogBlock *)v27, "CConnectedUserStore::FindConnectedUserByName", &IdentityProviderName);
  v9 = a5;
  if ( a2 )
  {
    v13 = -1;
    if ( String1 )
    {
      if ( !a4 )
      {
        v14 = -1;
        do
          ++v14;
        while ( String1[v14] );
        if ( v14 > 0x7FFF )
        {
LABEL_49:
          IdentityProviderName = -2147024809;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
            goto LABEL_55;
          }
          v11 = 58;
          goto LABEL_52;
        }
        do
LABEL_15:
          ++v13;
        while ( a2[v13] );
        if ( v13 <= 0x7FFF )
        {
          if ( a4 )
          {
            v15 = *(_QWORD *)&a4->Data1 - 0x4967A148B16898C6LL;
            if ( *(_QWORD *)&a4->Data1 == 0x4967A148B16898C6LL )
              v15 = *(_QWORD *)a4->Data4 - 0x2085DA55D7647191LL;
            if ( !v15 )
            {
              IdentityProviderName = -2147024846;
              goto LABEL_55;
            }
            IdentityProviderName = CConnectedUserStore::GetIdentityProviderName(
                                     this,
                                     a4,
                                     (const unsigned __int16 **)&Source);
            v12 = (unsigned int)IdentityProviderName;
            if ( IdentityProviderName < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                v11 = 59;
                goto LABEL_53;
              }
              goto LABEL_54;
            }
            String1 = Source;
            v26 = *a4;
          }
          else
          {
            IdentityProviderName = CConnectedUserStore::GetIdentityProviderGuid(this, String1, &v26);
            v12 = (unsigned int)IdentityProviderName;
            if ( IdentityProviderName < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                v11 = 60;
                goto LABEL_53;
              }
              goto LABEL_54;
            }
          }
          IdentityProviderName = MakeQualifiedIdentityName(String1, a2, (struct _UNICODE_STRING *)pv);
          v12 = (unsigned int)IdentityProviderName;
          if ( IdentityProviderName >= 0 )
          {
            v16 = SamLookupNamesInDomain2(*((_QWORD *)this + 12), 1, pv, &v22, &v24);
            if ( v16 < 0 )
            {
              if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  62,
                  (unsigned int)WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids,
                  pv[1],
                  v16);
              }
              if ( v16 == -1073741709 )
                v16 = -1073741275;
              IdentityProviderName = v16 | 0x10000000;
              goto LABEL_54;
            }
            if ( v9 )
            {
              IdentityProviderName = CConnectedUserStore::CoCreateConnectedUser(this, *v22, &v26, &v21);
              v12 = (unsigned int)IdentityProviderName;
              if ( IdentityProviderName < 0 )
              {
                v10 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                {
                  v11 = 63;
                  goto LABEL_53;
                }
                goto LABEL_54;
              }
              *v9 = v21;
              v21 = 0;
            }
            IdentityProviderName = 0;
            goto LABEL_54;
          }
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v11 = 61;
            goto LABEL_53;
          }
LABEL_54:
          if ( IdentityProviderName >= 0 )
            goto LABEL_57;
          goto LABEL_55;
        }
        goto LABEL_49;
      }
    }
    else if ( a4 )
    {
      goto LABEL_15;
    }
    IdentityProviderName = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_55;
    }
    v11 = 57;
LABEL_52:
    v12 = 2147942487LL;
    goto LABEL_53;
  }
  IdentityProviderName = -2147467261;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v11 = 56;
    v12 = 2147500035LL;
LABEL_53:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v12);
    goto LABEL_54;
  }
LABEL_55:
  if ( v9 )
    *v9 = 0;
LABEL_57:
  if ( pv[1] )
    CoTaskMemFree(pv[1]);
  if ( v22 )
    SamFreeMemory(v22);
  if ( v24 )
    SamFreeMemory(v24);
  v17 = MapErrorCodes(IdentityProviderName);
  CLogBlock::~CLogBlock((CLogBlock *)v27, v18, v19);
  ATL::CComPtrBase<CConnectedUser>::~CComPtrBase<CConnectedUser>((__int64 *)&v21);
  return v17;
}

```

## disassembly

```asm
0x180016060  mov     [rsp-28h+arg_0], rbx
0x180016065  mov     [rsp-28h+arg_10], rsi
0x18001606a  push    rbp
0x18001606b  push    rdi
0x18001606c  push    r12
0x18001606e  push    r14
0x180016070  push    r15
0x180016072  mov     rbp, rsp
0x180016075  sub     rsp, 80h
0x18001607c  xor     r12d, r12d
0x18001607f  xorps   xmm0, xmm0
0x180016082  mov     rdi, r8
0x180016085  mov     [rbp+arg_8], r12d
0x180016089  mov     r15, rdx
0x18001608c  mov     [rbp+Source], r12
0x180016090  mov     r14, rcx
0x180016093  mov     [rbp+var_48], r12
0x180016097  lea     r8, [rbp+arg_8]; int *
0x18001609b  mov     [rbp+var_38], r12
0x18001609f  lea     rdx, aCconnecteduser_8; "CConnectedUserStore::FindConnectedUserB"...
0x1800160a6  mov     [rbp+var_50], r12
0x1800160aa  lea     rcx, [rbp+var_10]; this
0x1800160ae  mov     rbx, r9
0x1800160b1  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x1800160b5  movups  xmmword ptr [rbp+pv], xmm0
0x1800160b9  call    ??0CLogBlock@@QEAA@PEBDPEAJ@Z; CLogBlock::CLogBlock(char const *,long *)
0x1800160be  mov     rsi, [rbp+arg_20]
0x1800160c2  test    r15, r15
0x1800160c5  jnz     short loc_1800160FF
0x1800160c7  mov     [rbp+arg_8], 80004003h
0x1800160ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800160d5  lea     rax, WPP_GLOBAL_Control
0x1800160dc  cmp     rcx, rax
0x1800160df  jz      loc_18001638A
0x1800160e5  test    byte ptr [rcx+1Ch], 4
0x1800160e9  jz      loc_18001638A
0x1800160ef  lea     edx, [r12+38h]
0x1800160f4  mov     r9d, 80004003h
0x1800160fa  jmp     loc_180016374
0x1800160ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016103  mov     edx, 7FFFh
0x180016108  test    rdi, rdi
0x18001610b  jnz     short loc_180016114
0x18001610d  test    rbx, rbx
0x180016110  jz      short loc_180016119
0x180016112  jmp     short loc_180016161
0x180016114  test    rbx, rbx
0x180016117  jz      short loc_18001614B
0x180016119  mov     [rbp+arg_8], 80070057h
0x180016120  mov     rcx, cs:WPP_GLOBAL_Control
0x180016127  lea     rax, WPP_GLOBAL_Control
0x18001612e  cmp     rcx, rax
0x180016131  jz      loc_18001638A
0x180016137  test    byte ptr [rcx+1Ch], 4
0x18001613b  jz      loc_18001638A
0x180016141  mov     edx, 39h ; '9'
0x180016146  jmp     loc_18001636E
0x18001614b  mov     rcx, rax
0x18001614e  inc     rcx
0x180016151  cmp     [rdi+rcx*2], r12w
0x180016156  jnz     short loc_18001614E
0x180016158  cmp     rcx, rdx
0x18001615b  ja      loc_180016349
0x180016161  inc     rax
0x180016164  cmp     [r15+rax*2], r12w
0x180016169  jnz     short loc_180016161
0x18001616b  cmp     rax, rdx
0x18001616e  ja      loc_180016349
0x180016174  test    rbx, rbx
0x180016177  jz      loc_180016239
0x18001617d  mov     rax, [rbx]
0x180016180  sub     rax, cs:qword_18001E550
0x180016187  jnz     short loc_180016194
0x180016189  mov     rax, [rbx+8]
0x18001618d  sub     rax, cs:qword_18001E558
0x180016194  test    rax, rax
0x180016197  jnz     short loc_1800161A5
0x180016199  mov     [rbp+arg_8], 80070032h
0x1800161a0  jmp     loc_18001638A
0x1800161a5  lea     r8, [rbp+Source]; unsigned __int16 **
0x1800161a9  mov     rdx, rbx; struct _GUID *
0x1800161ac  mov     rcx, r14; this
0x1800161af  call    ?GetIdentityProviderName@CConnectedUserStore@@AEAAJAEBU_GUID@@PEAPEBG@Z; CConnectedUserStore::GetIdentityProviderName(_GUID const &,ushort const * *)
0x1800161b4  mov     [rbp+arg_8], eax
0x1800161b7  mov     r9d, eax
0x1800161ba  test    eax, eax
0x1800161bc  jns     short loc_1800161E9
0x1800161be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800161c5  lea     rax, WPP_GLOBAL_Control
0x1800161cc  cmp     rcx, rax
0x1800161cf  jz      loc_180016384
0x1800161d5  test    byte ptr [rcx+1Ch], 4
0x1800161d9  jz      loc_180016384
0x1800161df  mov     edx, 3Bh ; ';'
0x1800161e4  jmp     loc_180016374
0x1800161e9  movups  xmm0, xmmword ptr [rbx]
0x1800161ec  mov     rdi, [rbp+Source]
0x1800161f0  movdqu  xmmword ptr [rbp+var_20.Data1], xmm0
0x1800161f5  lea     r8, [rbp+pv]; struct _UNICODE_STRING *
0x1800161f9  mov     rdx, r15; wchar_t *
0x1800161fc  mov     rcx, rdi; Source
0x1800161ff  call    ?MakeQualifiedIdentityName@@YAJPEBG0PEAU_UNICODE_STRING@@@Z; MakeQualifiedIdentityName(ushort const *,ushort const *,_UNICODE_STRING *)
0x180016204  mov     [rbp+arg_8], eax
0x180016207  mov     r9d, eax
0x18001620a  test    eax, eax
0x18001620c  jns     short loc_18001627D
0x18001620e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016215  lea     rax, WPP_GLOBAL_Control
0x18001621c  cmp     rcx, rax
0x18001621f  jz      loc_180016384
0x180016225  test    byte ptr [rcx+1Ch], 4
0x180016229  jz      loc_180016384
0x18001622f  mov     edx, 3Dh ; '='
0x180016234  jmp     loc_180016374
0x180016239  lea     r8, [rbp+var_20]; struct _GUID *
0x18001623d  mov     rdx, rdi; String1
0x180016240  mov     rcx, r14; this
0x180016243  call    ?GetIdentityProviderGuid@CConnectedUserStore@@AEAAJPEBGPEAU_GUID@@@Z; CConnectedUserStore::GetIdentityProviderGuid(ushort const *,_GUID *)
0x180016248  mov     [rbp+arg_8], eax
0x18001624b  mov     r9d, eax
0x18001624e  test    eax, eax
0x180016250  jns     short loc_1800161F5
0x180016252  mov     rcx, cs:WPP_GLOBAL_Control
0x180016259  lea     rax, WPP_GLOBAL_Control
0x180016260  cmp     rcx, rax
0x180016263  jz      loc_180016384
0x180016269  test    byte ptr [rcx+1Ch], 4
0x18001626d  jz      loc_180016384
0x180016273  mov     edx, 3Ch ; '<'
0x180016278  jmp     loc_180016374
0x18001627d  mov     rcx, [r14+60h]
0x180016281  lea     rax, [rbp+var_38]
0x180016285  lea     r9, [rbp+var_48]
0x180016289  mov     [rsp+80h+var_60], rax
0x18001628e  lea     r8, [rbp+pv]
0x180016292  mov     edx, 1
0x180016297  call    cs:__imp_SamLookupNamesInDomain2
0x18001629d  mov     ebx, eax
0x18001629f  test    eax, eax
0x1800162a1  jns     short loc_1800162F3
0x1800162a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162aa  lea     rax, WPP_GLOBAL_Control
0x1800162b1  cmp     rcx, rax
0x1800162b4  jz      short loc_1800162D9
0x1800162b6  test    byte ptr [rcx+1Ch], 4
0x1800162ba  jz      short loc_1800162D9
0x1800162bc  mov     r9, [rbp+pv+8]
0x1800162c0  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x1800162c7  mov     rcx, [rcx+10h]
0x1800162cb  mov     edx, 3Eh ; '>'
0x1800162d0  mov     dword ptr [rsp+80h+var_60], ebx
0x1800162d4  call    WPP_SF_Sd
0x1800162d9  cmp     ebx, 0C0000073h
0x1800162df  mov     eax, 0C0000225h
0x1800162e4  cmovz   ebx, eax
0x1800162e7  bts     ebx, 1Ch
0x1800162eb  mov     [rbp+arg_8], ebx
0x1800162ee  jmp     loc_180016384
0x1800162f3  test    rsi, rsi
0x1800162f6  jz      short loc_180016343
0x1800162f8  mov     rdx, [rbp+var_48]
0x1800162fc  lea     r9, [rbp+var_50]; struct CConnectedUser **
0x180016300  lea     r8, [rbp+var_20]; struct _GUID *
0x180016304  mov     rcx, r14; this
0x180016307  mov     edx, [rdx]; unsigned int
0x180016309  call    ?CoCreateConnectedUser@CConnectedUserStore@@AEAAJKAEBU_GUID@@PEAPEAVCConnectedUser@@@Z; CConnectedUserStore::CoCreateConnectedUser(ulong,_GUID const &,CConnectedUser * *)
0x18001630e  mov     [rbp+arg_8], eax
0x180016311  mov     r9d, eax
0x180016314  test    eax, eax
0x180016316  jns     short loc_180016338
0x180016318  mov     rcx, cs:WPP_GLOBAL_Control
0x18001631f  lea     rax, WPP_GLOBAL_Control
0x180016326  cmp     rcx, rax
0x180016329  jz      short loc_180016384
0x18001632b  test    byte ptr [rcx+1Ch], 4
0x18001632f  jz      short loc_180016384
0x180016331  mov     edx, 3Fh ; '?'
0x180016336  jmp     short loc_180016374
0x180016338  mov     rax, [rbp+var_50]
0x18001633c  mov     [rsi], rax
0x18001633f  mov     [rbp+var_50], r12
0x180016343  mov     [rbp+arg_8], r12d
0x180016347  jmp     short loc_180016384
0x180016349  mov     [rbp+arg_8], 80070057h
0x180016350  mov     rcx, cs:WPP_GLOBAL_Control
0x180016357  lea     rax, WPP_GLOBAL_Control
0x18001635e  cmp     rcx, rax
0x180016361  jz      short loc_18001638A
0x180016363  test    byte ptr [rcx+1Ch], 4
0x180016367  jz      short loc_18001638A
0x180016369  mov     edx, 3Ah ; ':'
0x18001636e  mov     r9d, 80070057h
0x180016374  mov     rcx, [rcx+10h]
0x180016378  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x18001637f  call    WPP_SF_d
0x180016384  cmp     [rbp+arg_8], r12d
0x180016388  jge     short loc_180016392
0x18001638a  test    rsi, rsi
0x18001638d  jz      short loc_180016392
0x18001638f  mov     [rsi], r12
0x180016392  mov     rcx, [rbp+pv+8]; pv
0x180016396  test    rcx, rcx
0x180016399  jz      short loc_1800163A1
0x18001639b  call    cs:__imp_CoTaskMemFree
0x1800163a1  mov     rcx, [rbp+var_48]
0x1800163a5  test    rcx, rcx
0x1800163a8  jz      short loc_1800163B0
0x1800163aa  call    cs:__imp_SamFreeMemory
0x1800163b0  mov     rcx, [rbp+var_38]
0x1800163b4  test    rcx, rcx
0x1800163b7  jz      short loc_1800163BF
0x1800163b9  call    cs:__imp_SamFreeMemory
0x1800163bf  mov     ecx, [rbp+arg_8]; int
0x1800163c2  call    ?MapErrorCodes@@YAJJ@Z; MapErrorCodes(long)
0x1800163c7  lea     rcx, [rbp+var_10]; this
0x1800163cb  mov     ebx, eax
0x1800163cd  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x1800163d2  lea     rcx, [rbp+var_50]
0x1800163d6  call    ??1?$CComPtrBase@VCConnectedUser@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CConnectedUser>::~CComPtrBase<CConnectedUser>(void)
0x1800163db  lea     r11, [rsp+80h+var_s0]
0x1800163e3  mov     eax, ebx
0x1800163e5  mov     rbx, [r11+30h]
0x1800163e9  mov     rsi, [r11+40h]
0x1800163ed  mov     rsp, r11
0x1800163f0  pop     r15
0x1800163f2  pop     r14
0x1800163f4  pop     r12
0x1800163f6  pop     rdi
0x1800163f7  pop     rbp
0x1800163f8  retn
```
