# CQMDSSecureableObject::GetObjectSecurity(void)

- ea: `0x180047070`
- end: `0x1800475ab`
- name: `?GetObjectSecurity@CQMDSSecureableObject@@EEAAJXZ`
- size: `1339`
- prototype: `__int64 __fastcall(CQMDSSecureableObject *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800457e4`

## callees

- `0x18000d1f0`
- `0x18000f35c`
- `0x1800129cc`
- `0x1800138e4`
- `0x180017f88`
- `0x18002c61c`
- `0x180046d68`
- `0x180047070`
- `0x180048980`
- `0x180050dd8`
- `0x1800950b0`
- `0x180095138`
- `0x1800951bc`
- `0x18009bd1c`
- `0x1800d6e3e`
- `0x1800d6ea0`
- `0x1800e4010`

## import_xrefs

- `msvcrt!free` at `0x1800472a9`
- `msvcrt!free` at `0x18004748c`
- `msvcrt!free` at `0x180047562`
- `msvcrt!free` at `0x1800472a9`
- `msvcrt!free` at `0x18004748c`
- `msvcrt!free` at `0x180047562`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180047450`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180047450`
- `mqsec!MQSec_SetPrivilegeInThread` at `0x180047122`
- `mqsec!MQSec_SetPrivilegeInThread` at `0x1800472fe`
- `mqsec!MQSec_SetPrivilegeInThread` at `0x180047390`
- `mqsec!MQSec_SetPrivilegeInThread` at `0x180047122`
- `mqsec!MQSec_SetPrivilegeInThread` at `0x1800472fe`
- `mqsec!MQSec_SetPrivilegeInThread` at `0x180047390`

## string_xrefs

- `0x18004711b`: `SeSecurityPrivilege`
- `0x1800472f7`: `SeSecurityPrivilege`
- `0x180047389`: `SeSecurityPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CQMDSSecureableObject::GetObjectSecurity(CQMDSSecureableObject *this)
{
  _BYTE *v2; // rsi
  __int64 v3; // rcx
  __int64 v4; // r8
  unsigned int v5; // r13d
  int v6; // eax
  int v7; // r15d
  unsigned int v8; // r14d
  __int64 v9; // r12
  int CachedQueueProperties; // edi
  __int64 v11; // rcx
  int v12; // eax
  PVOID *v13; // rcx
  int v14; // eax
  int v15; // eax
  __int64 v16; // r8
  unsigned __int16 v17; // r8
  void *v18; // rax
  void *v19; // rcx
  int MachineSecurityCache; // eax
  void *v21; // rax
  unsigned int Size; // [rsp+40h] [rbp-C0h] BYREF
  int Size_4; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  struct tagPROPVARIANT v26; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v27; // [rsp+68h] [rbp-98h] BYREF
  _BYTE *v28; // [rsp+78h] [rbp-88h]
  _BYTE pSecurityDescriptor[512]; // [rsp+80h] [rbp-80h] BYREF

  *((_QWORD *)this + 1) = 0;
  v2 = pSecurityDescriptor;
  Size = 512;
  LODWORD(v25) = 0;
  if ( !*((_DWORD *)this + 11) || !CQueueMgr::CanAccessDS() )
    goto LABEL_64;
  v5 = 7;
  if ( *(_DWORD *)(v3 + 40) )
  {
    v5 = 15;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 12, WPP_c687450366573ca356992ecf9dac13b8_Traceguids);
    v6 = MQSec_SetPrivilegeInThread(L"SeSecurityPrivilege", 1, 0);
    if ( v6 < 0 )
      LogMsgHR(v6, (wchar_t *)L"qmsecutl", 0xC5u);
  }
  v7 = 0;
  Size_4 = 0;
  while ( *((_DWORD *)this + 10) )
  {
    v8 = *((_DWORD *)this + 4);
    if ( v8 > 1 )
      break;
    v9 = *((_QWORD *)this + 4);
    CachedQueueProperties = ADInit(0, 0, 0, 0);
    if ( CachedQueueProperties >= 0 )
      CachedQueueProperties = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _BYTE *, unsigned int, unsigned __int64 *))(*(_QWORD *)g_pAD + 64LL))(
                                g_pAD,
                                v8,
                                v9,
                                v5,
                                v2,
                                Size,
                                &v25);
    if ( CachedQueueProperties >= 0 )
      goto LABEL_44;
    v7 = Size_4;
LABEL_25:
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 2) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        13,
        WPP_c687450366573ca356992ecf9dac13b8_Traceguids,
        *((unsigned int *)this + 10),
        CachedQueueProperties);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( CachedQueueProperties == -1072824285 )
    {
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 268) & 4) != 0 )
        WPP_SF_d(v13[32], 14, WPP_c687450366573ca356992ecf9dac13b8_Traceguids, (unsigned int)v25);
      free(*((void **)this + 1));
      v2 = MmAllocate((unsigned int)v25);
      *((_QWORD *)this + 1) = v2;
      Size = v25;
      Size_4 = ++v7;
    }
    else
    {
      if ( CachedQueueProperties == -1072824301 || (v5 & 8) == 0 )
        goto LABEL_44;
      v5 &= ~8u;
      v14 = MQSec_SetPrivilegeInThread(L"SeSecurityPrivilege", 0, 0);
      if ( v14 < 0 )
        LogMsgHR(v14, (wchar_t *)L"qmsecutl", 0xBAu);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 15, WPP_c687450366573ca356992ecf9dac13b8_Traceguids);
      *((_DWORD *)this + 10) = 0;
    }
    if ( v7 > 2 )
      goto LABEL_44;
  }
  v27 = 0;
  v28 = 0;
  LOWORD(v27) = 1;
  v11 = *((unsigned int *)this + 4);
  if ( (_DWORD)v11 )
  {
    if ( (_DWORD)v11 == 1 )
    {
      v12 = 1201;
    }
    else if ( (((_DWORD)v11 - 2) & 0xFFFFFFF7) != 0 )
    {
      v12 = 1101;
      if ( (_DWORD)v11 == 3 )
        v12 = 1601;
    }
    else
    {
      v12 = 1301;
    }
  }
  else
  {
    v12 = 1101;
  }
  CachedQueueProperties = ADGetObjectSecurityGuid(v11, 0, v4, *((_QWORD *)this + 4), v5, v12, &v27);
  if ( CachedQueueProperties < 0 )
    goto LABEL_25;
  v2 = v28;
  *((_QWORD *)this + 1) = v28;
  Size = DWORD2(v27);
LABEL_44:
  if ( *((_DWORD *)this + 10) )
  {
    v15 = MQSec_SetPrivilegeInThread(L"SeSecurityPrivilege", 0, 0);
    if ( v15 < 0 )
      LogMsgHR(v15, (wchar_t *)L"qmsecutl", 0xBBu);
    if ( ((*((_DWORD *)this + 4) - 2) & 0xFFFFFFF7) == 0 )
    {
      Size_4 = 301;
      memset(&v26, 0, sizeof(v26));
      v26.vt = 1;
      CachedQueueProperties = ADGetObjectPropertiesGuid(2, 0, v16, *((_QWORD *)this + 4), 1, &Size_4, &v26);
      if ( CachedQueueProperties < 0 )
      {
        v17 = 30;
        goto LABEL_75;
      }
      *((_QWORD *)this + 3) = v26.hVal.QuadPart;
LABEL_52:
      if ( *((_DWORD *)this + 4) == 1 && (unsigned int)QmpIsLocalMachine(*((const struct _GUID **)this + 4)) )
        SetMachineSecurityCache(v2, Size);
LABEL_55:
      if ( !*((_QWORD *)this + 1) )
      {
        Size = GetSecurityDescriptorLength(pSecurityDescriptor);
        v18 = MmAllocate(Size);
        *((_QWORD *)this + 1) = v18;
        memcpy_0(v18, pSecurityDescriptor, Size);
      }
      if ( CachedQueueProperties < 0 )
        goto LABEL_74;
      return (unsigned int)CachedQueueProperties;
    }
  }
  if ( CachedQueueProperties >= 0 )
    goto LABEL_52;
  v19 = (void *)*((_QWORD *)this + 1);
  if ( v19 )
  {
    free(v19);
    if ( v2 == *((_BYTE **)this + 1) )
    {
      v2 = pSecurityDescriptor;
      Size = 512;
    }
    *((_QWORD *)this + 1) = 0;
  }
  if ( CachedQueueProperties != -1072824301 )
    goto LABEL_74;
LABEL_64:
  if ( *((_DWORD *)this + 4) )
  {
    if ( *((_DWORD *)this + 4) == 1 && (unsigned int)QmpIsLocalMachine(*((const struct _GUID **)this + 4)) )
    {
      MachineSecurityCache = GetMachineSecurityCache(v2, &Size);
      CachedQueueProperties = MachineSecurityCache;
      if ( MachineSecurityCache >= 0 )
        goto LABEL_55;
      if ( MachineSecurityCache == -1072824285 )
      {
        v21 = MmAllocate(Size);
        *((_QWORD *)this + 1) = v21;
        CachedQueueProperties = GetMachineSecurityCache(v21, &Size);
        if ( CachedQueueProperties >= 0 )
          goto LABEL_55;
      }
      free(*((void **)this + 1));
      *((_QWORD *)this + 1) = 0;
    }
    CachedQueueProperties = -1072824301;
  }
  else
  {
    memset(&v26, 0, sizeof(v26));
    Size_4 = 1101;
    v26.vt = 1;
    CachedQueueProperties = GetCachedQueueProperties(
                              1u,
                              (unsigned int *const)&Size_4,
                              &v26,
                              *((const struct _GUID **)this + 4),
                              0);
    if ( CachedQueueProperties >= 0 )
    {
      *((_QWORD *)this + 1) = v26.bstrblobVal.pData;
      goto LABEL_55;
    }
  }
LABEL_74:
  v17 = 40;
LABEL_75:
  LogMsgHR(CachedQueueProperties, (wchar_t *)L"qmsecutl", v17);
  return (unsigned int)CachedQueueProperties;
}

```

## disassembly

```asm
0x180047070  push    rbp
0x180047072  push    rbx
0x180047073  push    rsi
0x180047074  push    rdi
0x180047075  push    r12
0x180047077  push    r13
0x180047079  push    r14
0x18004707b  push    r15
0x18004707d  lea     rbp, [rsp-198h]
0x180047085  sub     rsp, 298h
0x18004708c  mov     rax, cs:__security_cookie
0x180047093  xor     rax, rsp
0x180047096  mov     [rbp+1D0h+var_50], rax
0x18004709d  mov     rbx, rcx
0x1800470a0  xor     r12d, r12d
0x1800470a3  mov     [rcx+8], r12
0x1800470a7  lea     rsi, [rbp+1D0h+pSecurityDescriptor]
0x1800470ab  mov     dword ptr [rsp+2D0h+Size], 200h
0x1800470b3  mov     dword ptr [rsp+2D0h+var_288], r12d
0x1800470b8  lea     edi, [r12+1]
0x1800470bd  cmp     [rcx+2Ch], r12d
0x1800470c1  jz      loc_1800474BA
0x1800470c7  call    ?CanAccessDS@CQueueMgr@@SA_NXZ; CQueueMgr::CanAccessDS(void)
0x1800470cc  test    al, al
0x1800470ce  jz      loc_1800474BA
0x1800470d4  lea     r13d, [r12+7]
0x1800470d9  lea     rax, WPP_GLOBAL_Control
0x1800470e0  cmp     [rcx+28h], r12d
0x1800470e4  jz      short loc_180047140
0x1800470e6  lea     r13d, [r12+0Fh]
0x1800470eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800470f2  cmp     rcx, rax
0x1800470f5  jz      short loc_180047116
0x1800470f7  test    byte ptr [rcx+10Ch], 4
0x1800470fe  jz      short loc_180047116
0x180047100  lea     edx, [rdi+0Bh]
0x180047103  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x18004710a  mov     rcx, [rcx+100h]
0x180047111  call    WPP_SF_
0x180047116  xor     r8d, r8d
0x180047119  mov     edx, edi
0x18004711b  lea     rcx, aSesecuritypriv; "SeSecurityPrivilege"
0x180047122  call    cs:__imp_?MQSec_SetPrivilegeInThread@@YAJPEB_WHPEAH@Z; MQSec_SetPrivilegeInThread(wchar_t const *,int,int *)
0x180047128  test    eax, eax
0x18004712a  jns     short loc_180047140
0x18004712c  mov     r8d, 0C5h; unsigned __int16
0x180047132  lea     rdx, aQmsecutl; "qmsecutl"
0x180047139  mov     ecx, eax; int
0x18004713b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180047140  mov     r15d, r12d
0x180047143  mov     dword ptr [rsp+2D0h+Size+4], r12d
0x180047148  cmp     [rbx+28h], r12d
0x18004714c  jz      short loc_1800471B9
0x18004714e  mov     r14d, [rbx+10h]
0x180047152  cmp     r14d, edi
0x180047155  ja      short loc_1800471B9
0x180047157  mov     r15d, dword ptr [rsp+2D0h+Size]
0x18004715c  mov     r12, [rbx+20h]
0x180047160  xor     r9d, r9d; bool
0x180047163  xor     r8d, r8d; bool
0x180047166  xor     edx, edx; bool
0x180047168  xor     ecx, ecx; void (*)(void)
0x18004716a  call    ?ADInit@@YAJP6AXXZ_N11@Z; ADInit(void (*)(void),bool,bool,bool)
0x18004716f  mov     edi, eax
0x180047171  test    eax, eax
0x180047173  js      short loc_1800471A7
0x180047175  mov     rcx, cs:?g_pAD@@3V?$P@VCBaseADProvider@@@@A; P<CBaseADProvider> g_pAD
0x18004717c  mov     rax, [rcx]
0x18004717f  lea     rdx, [rsp+2D0h+var_288]
0x180047184  mov     [rsp+2D0h+var_2A0], rdx
0x180047189  mov     dword ptr [rsp+2D0h+var_2A8], r15d
0x18004718e  mov     [rsp+2D0h+var_2B0], rsi
0x180047193  mov     r9d, r13d
0x180047196  mov     r8, r12
0x180047199  mov     edx, r14d
0x18004719c  mov     rax, [rax+40h]
0x1800471a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471a5  mov     edi, eax
0x1800471a7  xor     r12d, r12d
0x1800471aa  test    edi, edi
0x1800471ac  jns     loc_180047374
0x1800471b2  mov     r15d, dword ptr [rsp+2D0h+Size+4]
0x1800471b7  jmp     short loc_18004722E
0x1800471b9  xorps   xmm0, xmm0
0x1800471bc  xor     eax, eax
0x1800471be  movups  [rsp+2D0h+var_268], xmm0
0x1800471c3  mov     [rsp+2D0h+var_258], rax
0x1800471c8  mov     word ptr [rsp+2D0h+var_268], di
0x1800471cd  mov     ecx, [rbx+10h]
0x1800471d0  test    ecx, ecx
0x1800471d2  jnz     short loc_1800471DB
0x1800471d4  mov     eax, 44Dh
0x1800471d9  jmp     short loc_180047206
0x1800471db  cmp     ecx, edi
0x1800471dd  jnz     short loc_1800471E6
0x1800471df  mov     eax, 4B1h
0x1800471e4  jmp     short loc_180047206
0x1800471e6  lea     eax, [rcx-2]
0x1800471e9  test    eax, 0FFFFFFF7h
0x1800471ee  jz      short loc_180047201
0x1800471f0  mov     eax, 44Dh
0x1800471f5  cmp     ecx, 3
0x1800471f8  jnz     short loc_180047206
0x1800471fa  mov     eax, 641h
0x1800471ff  jmp     short loc_180047206
0x180047201  mov     eax, 515h
0x180047206  lea     rdx, [rsp+2D0h+var_268]
0x18004720b  mov     [rsp+2D0h+var_2A0], rdx
0x180047210  mov     dword ptr [rsp+2D0h+var_2A8], eax
0x180047214  mov     dword ptr [rsp+2D0h+var_2B0], r13d
0x180047219  mov     r9, [rbx+20h]
0x18004721d  xor     edx, edx
0x18004721f  call    ?ADGetObjectSecurityGuid@@YAJW4AD_OBJECT@@PEB_W_NPEBU_GUID@@KKPEAUtagPROPVARIANT@@@Z; ADGetObjectSecurityGuid(AD_OBJECT,wchar_t const *,bool,_GUID const *,ulong,ulong,tagPROPVARIANT *)
0x180047224  mov     edi, eax
0x180047226  test    eax, eax
0x180047228  jns     loc_180047363
0x18004722e  mov     rcx, cs:WPP_GLOBAL_Control
0x180047235  lea     r14, WPP_GLOBAL_Control
0x18004723c  cmp     rcx, r14
0x18004723f  jz      short loc_180047271
0x180047241  test    byte ptr [rcx+10Ch], 2
0x180047248  jz      short loc_180047271
0x18004724a  mov     edx, 0Dh
0x18004724f  mov     dword ptr [rsp+2D0h+var_2B0], edi
0x180047253  mov     r9d, [rbx+28h]
0x180047257  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x18004725e  mov     rcx, [rcx+100h]
0x180047265  call    WPP_SF_Dd
0x18004726a  mov     rcx, cs:WPP_GLOBAL_Control
0x180047271  cmp     edi, 0C00E0023h
0x180047277  jnz     short loc_1800472D8
0x180047279  cmp     rcx, r14
0x18004727c  jz      short loc_1800472A5
0x18004727e  test    byte ptr [rcx+10Ch], 4
0x180047285  jz      short loc_1800472A5
0x180047287  mov     edx, 0Eh
0x18004728c  mov     r9d, dword ptr [rsp+2D0h+var_288]
0x180047291  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x180047298  mov     rcx, [rcx+100h]
0x18004729f  call    WPP_SF_d
0x1800472a4  nop
0x1800472a5  mov     rcx, [rbx+8]; Block
0x1800472a9  call    cs:__imp_free
0x1800472af  nop
0x1800472b0  mov     ecx, dword ptr [rsp+2D0h+var_288]; unsigned __int64
0x1800472b4  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800472b9  mov     rsi, rax
0x1800472bc  mov     [rbx+8], rax
0x1800472c0  mov     eax, dword ptr [rsp+2D0h+var_288]
0x1800472c4  mov     dword ptr [rsp+2D0h+Size], eax
0x1800472c8  mov     r14d, 1
0x1800472ce  add     r15d, r14d
0x1800472d1  mov     dword ptr [rsp+2D0h+Size+4], r15d
0x1800472d6  jmp     short loc_180047353
0x1800472d8  cmp     edi, 0C00E0013h
0x1800472de  jz      loc_180047374
0x1800472e4  test    r13b, 8
0x1800472e8  jz      loc_180047374
0x1800472ee  and     r13d, 0FFFFFFF7h
0x1800472f2  xor     r8d, r8d
0x1800472f5  xor     edx, edx
0x1800472f7  lea     rcx, aSesecuritypriv; "SeSecurityPrivilege"
0x1800472fe  call    cs:__imp_?MQSec_SetPrivilegeInThread@@YAJPEB_WHPEAH@Z; MQSec_SetPrivilegeInThread(wchar_t const *,int,int *)
0x180047304  test    eax, eax
0x180047306  jns     short loc_18004731C
0x180047308  mov     r8d, 0BAh; unsigned __int16
0x18004730e  lea     rdx, aQmsecutl; "qmsecutl"
0x180047315  mov     ecx, eax; int
0x180047317  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18004731c  mov     rcx, cs:WPP_GLOBAL_Control
0x180047323  cmp     rcx, r14
0x180047326  jz      short loc_180047349
0x180047328  test    byte ptr [rcx+10Ch], 4
0x18004732f  jz      short loc_180047349
0x180047331  mov     edx, 0Fh
0x180047336  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x18004733d  mov     rcx, [rcx+100h]
0x180047344  call    WPP_SF_
0x180047349  mov     [rbx+28h], r12d
0x18004734d  mov     r14d, 1
0x180047353  cmp     r15d, 2
0x180047357  jg      short loc_18004737A
0x180047359  mov     edi, 1
0x18004735e  jmp     loc_180047148
0x180047363  mov     rsi, [rsp+2D0h+var_258]
0x180047368  mov     [rbx+8], rsi
0x18004736c  mov     eax, dword ptr [rsp+2D0h+var_268+8]
0x180047370  mov     dword ptr [rsp+2D0h+Size], eax
0x180047374  mov     r14d, 1
0x18004737a  cmp     [rbx+28h], r12d
0x18004737e  jz      loc_18004741B
0x180047384  xor     r8d, r8d
0x180047387  xor     edx, edx
0x180047389  lea     rcx, aSesecuritypriv; "SeSecurityPrivilege"
0x180047390  call    cs:__imp_?MQSec_SetPrivilegeInThread@@YAJPEB_WHPEAH@Z; MQSec_SetPrivilegeInThread(wchar_t const *,int,int *)
0x180047396  test    eax, eax
0x180047398  jns     short loc_1800473AE
0x18004739a  mov     r8d, 0BBh; unsigned __int16
0x1800473a0  lea     rdx, aQmsecutl; "qmsecutl"
0x1800473a7  mov     ecx, eax; int
0x1800473a9  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800473ae  mov     eax, [rbx+10h]
0x1800473b1  sub     eax, 2
0x1800473b4  test    eax, 0FFFFFFF7h
0x1800473b9  jnz     short loc_18004741B
0x1800473bb  mov     dword ptr [rsp+2D0h+Size+4], 12Dh
0x1800473c3  xorps   xmm0, xmm0
0x1800473c6  xor     eax, eax
0x1800473c8  movups  xmmword ptr [rsp+2D0h+var_280], xmm0
0x1800473cd  mov     qword ptr [rsp+2D0h+var_280+10h], rax
0x1800473d2  mov     word ptr [rsp+2D0h+var_280], r14w
0x1800473d8  lea     rax, [rsp+2D0h+var_280]
0x1800473dd  mov     [rsp+2D0h+var_2A0], rax
0x1800473e2  lea     rax, [rsp+2D0h+Size+4]
0x1800473e7  mov     [rsp+2D0h+var_2A8], rax
0x1800473ec  mov     dword ptr [rsp+2D0h+var_2B0], r14d
0x1800473f1  mov     r9, [rbx+20h]
0x1800473f5  xor     edx, edx
0x1800473f7  lea     ecx, [rdx+2]
0x1800473fa  call    ?ADGetObjectPropertiesGuid@@YAJW4AD_OBJECT@@PEB_W_NPEBU_GUID@@KQEBKQEAUtagPROPVARIANT@@@Z; ADGetObjectPropertiesGuid(AD_OBJECT,wchar_t const *,bool,_GUID const *,ulong,ulong const * const,tagPROPVARIANT * const)
0x1800473ff  mov     edi, eax
0x180047401  test    eax, eax
0x180047403  jns     short loc_180047410
0x180047405  mov     r8d, 1Eh
0x18004740b  jmp     loc_180047578
0x180047410  mov     rax, qword ptr [rsp+2D0h+var_280+8]
0x180047415  mov     [rbx+18h], rax
0x180047419  jmp     short loc_18004741F
0x18004741b  test    edi, edi
0x18004741d  js      short loc_180047483
0x18004741f  cmp     [rbx+10h], r14d
0x180047423  jnz     short loc_180047446
0x180047425  mov     rcx, [rbx+20h]; struct _GUID *
0x180047429  call    ?QmpIsLocalMachine@@YAHPEBU_GUID@@@Z; QmpIsLocalMachine(_GUID const *)
0x18004742e  test    eax, eax
0x180047430  jz      short loc_18004743E
0x180047432  mov     edx, dword ptr [rsp+2D0h+Size]; unsigned int
0x180047436  mov     rcx, rsi; void *
0x180047439  call    ?SetMachineSecurityCache@@YAJPEBXK@Z; SetMachineSecurityCache(void const *,ulong)
0x18004743e  test    edi, edi
0x180047440  js      loc_180047572
0x180047446  cmp     [rbx+8], r12
0x18004744a  jnz     short loc_180047476
0x18004744c  lea     rcx, [rbp+1D0h+pSecurityDescriptor]; pSecurityDescriptor
0x180047450  call    cs:__imp_GetSecurityDescriptorLength
0x180047456  mov     ecx, eax; unsigned __int64
0x180047458  mov     dword ptr [rsp+2D0h+Size], ecx
0x18004745c  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180047461  mov     [rbx+8], rax
0x180047465  mov     r8d, dword ptr [rsp+2D0h+Size]; Size
0x18004746a  lea     rdx, [rbp+1D0h+pSecurityDescriptor]; Src
0x18004746e  mov     rcx, rax; void *
0x180047471  call    memcpy_0
0x180047476  test    edi, edi
0x180047478  jns     loc_180047586
0x18004747e  jmp     loc_180047572
0x180047483  mov     rcx, [rbx+8]; Block
0x180047487  test    rcx, rcx
0x18004748a  jz      short loc_1800474A9
0x18004748c  call    cs:__imp_free
0x180047492  nop
0x180047493  cmp     rsi, [rbx+8]
0x180047497  jnz     short loc_1800474A5
0x180047499  lea     rsi, [rbp+1D0h+pSecurityDescriptor]
0x18004749d  mov     dword ptr [rsp+2D0h+Size], 200h
0x1800474a5  mov     [rbx+8], r12
0x1800474a9  cmp     edi, 0C00E0013h
0x1800474af  jnz     loc_180047572
0x1800474b5  mov     edi, 1
0x1800474ba  cmp     [rbx+10h], r12d
0x1800474be  jnz     short loc_18004750A
0x1800474c0  xorps   xmm0, xmm0
0x1800474c3  xor     eax, eax
0x1800474c5  movups  xmmword ptr [rsp+2D0h+var_280], xmm0
0x1800474ca  mov     qword ptr [rsp+2D0h+var_280+10h], rax
0x1800474cf  mov     dword ptr [rsp+2D0h+Size+4], 44Dh
0x1800474d7  mov     word ptr [rsp+2D0h+var_280], di
0x1800474dc  mov     [rsp+2D0h+var_2B0], r12; wchar_t *
0x1800474e1  mov     r9, [rbx+20h]; struct _GUID *
0x1800474e5  lea     r8, [rsp+2D0h+var_280]; struct tagPROPVARIANT *
0x1800474ea  lea     rdx, [rsp+2D0h+Size+4]; unsigned int *
0x1800474ef  mov     ecx, edi; unsigned int
0x1800474f1  call    ?GetCachedQueueProperties@@YAJKQEAKQEAUtagPROPVARIANT@@PEBU_GUID@@PEB_W@Z; GetCachedQueueProperties(ulong,ulong * const,tagPROPVARIANT * const,_GUID const *,wchar_t const *)
0x1800474f6  mov     edi, eax
0x1800474f8  test    eax, eax
0x1800474fa  js      short loc_180047572
0x1800474fc  mov     rax, qword ptr [rsp+2D0h+var_280+10h]
0x180047501  mov     [rbx+8], rax
0x180047505  jmp     loc_180047446
0x18004750a  cmp     [rbx+10h], edi
0x18004750d  jnz     short loc_18004756D
0x18004750f  mov     rcx, [rbx+20h]; struct _GUID *
0x180047513  call    ?QmpIsLocalMachine@@YAHPEBU_GUID@@@Z; QmpIsLocalMachine(_GUID const *)
0x180047518  test    eax, eax
0x18004751a  jz      short loc_18004756D
0x18004751c  lea     rdx, [rsp+2D0h+Size]; unsigned int *
0x180047521  mov     rcx, rsi; Src
0x180047524  call    ?GetMachineSecurityCache@@YAJPEAXPEAK@Z; GetMachineSecurityCache(void *,ulong *)
0x180047529  mov     edi, eax
0x18004752b  test    eax, eax
  ... truncated ...
```
