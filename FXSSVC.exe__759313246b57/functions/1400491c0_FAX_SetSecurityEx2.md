# FAX_SetSecurityEx2

- ea: `0x1400491c0`
- end: `0x140049672`
- name: `FAX_SetSecurityEx2`
- size: `1202`
- prototype: `__int64 __fastcall(__int64, SECURITY_INFORMATION, void *, ULONG)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x14000cc48`
- `0x140047d20`
- `0x1400487d4`
- `0x1400491c0`
- `0x1400589ac`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x140049408`
- `ADVAPI32!OpenThreadToken` at `0x140049408`
- `ADVAPI32!SetPrivateObjectSecurity` at `0x1400494f1`
- `ADVAPI32!SetPrivateObjectSecurity` at `0x1400494f1`
- `KERNEL32!GetLastError` at `0x140049418`
- `KERNEL32!GetLastError` at `0x140049501`
- `KERNEL32!GetLastError` at `0x140049602`
- `KERNEL32!GetLastError` at `0x140049418`
- `KERNEL32!GetLastError` at `0x140049501`
- `KERNEL32!GetLastError` at `0x140049602`
- `KERNEL32!CloseHandle` at `0x1400495da`
- `KERNEL32!CloseHandle` at `0x1400495da`
- `KERNEL32!EnterCriticalSection` at `0x1400492fc`
- `KERNEL32!EnterCriticalSection` at `0x1400492fc`
- `KERNEL32!LeaveCriticalSection` at `0x1400495c4`
- `KERNEL32!LeaveCriticalSection` at `0x1400495c4`
- `KERNEL32!GetCurrentThread` at `0x1400493ed`
- `KERNEL32!GetCurrentThread` at `0x1400493ed`
- `RPCRT4!RpcRevertToSelf` at `0x140049452`
- `RPCRT4!RpcRevertToSelf` at `0x140049494`
- `RPCRT4!RpcRevertToSelf` at `0x140049452`
- `RPCRT4!RpcRevertToSelf` at `0x140049494`
- `RPCRT4!RpcImpersonateClient` at `0x1400493ad`
- `RPCRT4!RpcImpersonateClient` at `0x1400493ad`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x14004929d`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x14004929d`

## pseudocode

```c
// Hidden C++ exception states: #wind=72 #try_helpers=1
__int64 __fastcall FAX_SetSecurityEx2(__int64 a1, SECURITY_INFORMATION a2, void *a3, ULONG a4)
{
  CMapDeviceId *v7; // rcx
  __int64 v8; // rdx
  int v10; // ebx
  DWORD v11; // ecx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  CMapDeviceId *v14; // rcx
  __int64 v15; // rdx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v18; // eax
  int ConfigEvent; // eax
  DWORD v20; // eax
  void *TokenHandle; // [rsp+30h] [rbp-48h] BYREF
  int v22; // [rsp+90h] [rbp+18h] BYREF

  v22 = 0;
  TokenHandle = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a3 || !a4 )
  {
    if ( v7 == (CMapDeviceId *)&WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 4) == 0 || *((_BYTE *)v7 + 25) < 2u )
      return 87;
    v8 = 56;
    goto LABEL_89;
  }
  if ( (a2 & 0xF) == 0 )
  {
    if ( v7 == (CMapDeviceId *)&WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 4) == 0 || *((_BYTE *)v7 + 25) < 2u )
      return 87;
    v8 = 57;
LABEL_89:
    WPP_SF_(*((_QWORD *)v7 + 2), v8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    return 87;
  }
  if ( (a2 & 0xFFFFFFF0) != 0 )
  {
    if ( v7 == (CMapDeviceId *)&WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 4) == 0 || *((_BYTE *)v7 + 25) < 2u )
      return 87;
    v8 = 58;
    goto LABEL_89;
  }
  if ( !RtlValidRelativeSecurityDescriptor(a3, a4, a2) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    }
    return 13;
  }
  v10 = ((a2 & 1) << 19) | 0x40000;
  if ( (a2 & 6) == 0 )
    v10 = (a2 & 1) << 19;
  EnterCriticalSection(&g_CsSecurity);
  v11 = v10 | 0x1000000;
  if ( (a2 & 8) == 0 )
    v11 = v10;
  v12 = FaxSvcAccessCheck(v11, &v22, 0, 1);
  v13 = v12;
  if ( v12 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_75;
    }
    v15 = 60;
    goto LABEL_32;
  }
  if ( !v22 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    }
    v13 = 5;
    goto LABEL_75;
  }
  v12 = RpcImpersonateClient(0);
  v13 = v12;
  if ( v12 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_75;
    }
    v15 = 62;
    goto LABEL_32;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, LastError);
    }
    v12 = RpcRevertToSelf();
    if ( !v12 )
      goto LABEL_75;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_75;
    }
    v15 = 64;
    goto LABEL_32;
  }
  v12 = RpcRevertToSelf();
  v13 = v12;
  if ( v12 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_75;
    }
    v15 = 65;
    goto LABEL_32;
  }
  if ( SetPrivateObjectSecurity(a2, a3, &g_pFaxSD, (PGENERIC_MAPPING)&GenericMapping, TokenHandle) )
  {
    v18 = SaveSecurityDescriptor(g_pFaxSD);
    v13 = v18;
    if ( v18 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v18);
      }
      v13 = 1015;
    }
    else
    {
      ConfigEvent = CreateConfigEvent(5);
      if ( ConfigEvent
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_h(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids,
          (unsigned __int16)ConfigEvent);
      }
    }
    goto LABEL_75;
  }
  v12 = GetLastError();
  v13 = v12;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = 66;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v12);
  }
LABEL_75:
  LeaveCriticalSection(&g_CsSecurity);
  if ( TokenHandle
    && !CloseHandle(TokenHandle)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v20 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v20);
  }
  if ( v13 == 8 || v13 == 14 )
    return 7001;
  return v13;
}

```

## disassembly

```asm
0x1400491c0  mov     rax, rsp
0x1400491c3  push    rbx
0x1400491c4  push    rbp
0x1400491c5  push    rsi
0x1400491c6  push    r12
0x1400491c8  push    r13
0x1400491ca  push    r14
0x1400491cc  sub     rsp, 48h
0x1400491d0  mov     ebx, r9d
0x1400491d3  mov     dword ptr [rax+18h], 0
0x1400491da  mov     rbp, r8
0x1400491dd  mov     qword ptr [rax-48h], 0
0x1400491e5  mov     esi, edx
0x1400491e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400491ee  lea     r12, WPP_GLOBAL_Control
0x1400491f5  lea     r13, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x1400491fc  mov     r14b, 4
0x1400491ff  cmp     rcx, r12
0x140049202  jz      short loc_140049228
0x140049204  test    [rcx+1Ch], r14b
0x140049208  jz      short loc_140049228
0x14004920a  cmp     byte ptr [rcx+19h], 5
0x14004920e  jb      short loc_140049228
0x140049210  mov     rcx, [rcx+10h]
0x140049214  mov     edx, 37h ; '7'
0x140049219  mov     r8, r13
0x14004921c  call    WPP_SF_
0x140049221  mov     rcx, cs:WPP_GLOBAL_Control
0x140049228  test    rbp, rbp
0x14004922b  jz      loc_14004963C
0x140049231  test    ebx, ebx
0x140049233  jz      loc_14004963C
0x140049239  test    sil, 0Fh
0x14004923d  jnz     short loc_140049266
0x14004923f  cmp     rcx, r12
0x140049242  jz      loc_14004965E
0x140049248  test    [rcx+1Ch], r14b
0x14004924c  jz      loc_14004965E
0x140049252  cmp     byte ptr [rcx+19h], 2
0x140049256  jb      loc_14004965E
0x14004925c  mov     edx, 39h ; '9'
0x140049261  jmp     loc_140049652
0x140049266  test    esi, 0FFFFFFF0h
0x14004926c  jz      short loc_140049295
0x14004926e  cmp     rcx, r12
0x140049271  jz      loc_14004965E
0x140049277  test    [rcx+1Ch], r14b
0x14004927b  jz      loc_14004965E
0x140049281  cmp     byte ptr [rcx+19h], 2
0x140049285  jb      loc_14004965E
0x14004928b  mov     edx, 3Ah ; ':'
0x140049290  jmp     loc_140049652
0x140049295  mov     r8d, esi; RequiredInformation
0x140049298  mov     edx, ebx; SecurityDescriptorLength
0x14004929a  mov     rcx, rbp; SecurityDescriptorInput
0x14004929d  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1400492a4  nop     dword ptr [rax+rax+00h]
0x1400492a9  test    al, al
0x1400492ab  jnz     short loc_1400492E0
0x1400492ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400492b4  cmp     rcx, r12
0x1400492b7  jz      short loc_1400492D6
0x1400492b9  test    [rcx+1Ch], r14b
0x1400492bd  jz      short loc_1400492D6
0x1400492bf  cmp     byte ptr [rcx+19h], 2
0x1400492c3  jb      short loc_1400492D6
0x1400492c5  mov     rcx, [rcx+10h]
0x1400492c9  mov     edx, 3Bh ; ';'
0x1400492ce  mov     r8, r13
0x1400492d1  call    WPP_SF_
0x1400492d6  mov     eax, 0Dh
0x1400492db  jmp     loc_140049663
0x1400492e0  mov     ecx, esi
0x1400492e2  and     ecx, 1
0x1400492e5  shl     ecx, 13h
0x1400492e8  mov     ebx, ecx
0x1400492ea  bts     ebx, 12h
0x1400492ee  test    sil, 6
0x1400492f2  cmovz   ebx, ecx
0x1400492f5  lea     rcx, ?g_CsSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400492fc  call    cs:__imp_EnterCriticalSection
0x140049303  nop     dword ptr [rax+rax+00h]
0x140049308  mov     ecx, ebx
0x14004930a  lea     rdx, [rsp+78h+arg_10]; int *
0x140049312  bts     ecx, 18h
0x140049316  mov     r9d, 1; int
0x14004931c  test    sil, 8
0x140049320  cmovz   ecx, ebx; unsigned int
0x140049323  xor     r8d, r8d; unsigned int *
0x140049326  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14004932b  mov     ebx, eax
0x14004932d  test    eax, eax
0x14004932f  jz      short loc_14004936E
0x140049331  mov     rcx, cs:WPP_GLOBAL_Control
0x140049338  cmp     rcx, r12
0x14004933b  jz      loc_1400495BD
0x140049341  test    [rcx+1Ch], r14b
0x140049345  jz      loc_1400495BD
0x14004934b  cmp     byte ptr [rcx+19h], 2
0x14004934f  jb      loc_1400495BD
0x140049355  mov     edx, 3Ch ; '<'
0x14004935a  mov     rcx, [rcx+10h]
0x14004935e  mov     r9d, eax
0x140049361  mov     r8, r13
0x140049364  call    WPP_SF_d
0x140049369  jmp     loc_1400495BD
0x14004936e  cmp     [rsp+78h+arg_10], 0
0x140049376  jnz     short loc_1400493AB
0x140049378  mov     rcx, cs:WPP_GLOBAL_Control
0x14004937f  cmp     rcx, r12
0x140049382  jz      short loc_1400493A1
0x140049384  test    [rcx+1Ch], r14b
0x140049388  jz      short loc_1400493A1
0x14004938a  cmp     byte ptr [rcx+19h], 2
0x14004938e  jb      short loc_1400493A1
0x140049390  mov     rcx, [rcx+10h]
0x140049394  mov     edx, 3Dh ; '='
0x140049399  mov     r8, r13
0x14004939c  call    WPP_SF_
0x1400493a1  mov     ebx, 5
0x1400493a6  jmp     loc_1400495BD
0x1400493ab  xor     ecx, ecx; BindingHandle
0x1400493ad  call    cs:__imp_RpcImpersonateClient
0x1400493b4  nop     dword ptr [rax+rax+00h]
0x1400493b9  mov     ebx, eax
0x1400493bb  test    eax, eax
0x1400493bd  jz      short loc_1400493ED
0x1400493bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400493c6  cmp     rcx, r12
0x1400493c9  jz      loc_1400495BD
0x1400493cf  test    [rcx+1Ch], r14b
0x1400493d3  jz      loc_1400495BD
0x1400493d9  cmp     byte ptr [rcx+19h], 2
0x1400493dd  jb      loc_1400495BD
0x1400493e3  mov     edx, 3Eh ; '>'
0x1400493e8  jmp     loc_14004935A
0x1400493ed  call    cs:__imp_GetCurrentThread
0x1400493f4  nop     dword ptr [rax+rax+00h]
0x1400493f9  xor     r8d, r8d; OpenAsSelf
0x1400493fc  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x140049401  mov     rcx, rax; ThreadHandle
0x140049404  lea     edx, [r8+8]; DesiredAccess
0x140049408  call    cs:__imp_OpenThreadToken
0x14004940f  nop     dword ptr [rax+rax+00h]
0x140049414  test    eax, eax
0x140049416  jnz     short loc_140049494
0x140049418  call    cs:__imp_GetLastError
0x14004941f  nop     dword ptr [rax+rax+00h]
0x140049424  mov     ebx, eax
0x140049426  mov     rcx, cs:WPP_GLOBAL_Control
0x14004942d  cmp     rcx, r12
0x140049430  jz      short loc_140049452
0x140049432  test    [rcx+1Ch], r14b
0x140049436  jz      short loc_140049452
0x140049438  cmp     byte ptr [rcx+19h], 2
0x14004943c  jb      short loc_140049452
0x14004943e  mov     rcx, [rcx+10h]
0x140049442  mov     edx, 3Fh ; '?'
0x140049447  mov     r9d, eax
0x14004944a  mov     r8, r13
0x14004944d  call    WPP_SF_d
0x140049452  call    cs:__imp_RpcRevertToSelf
0x140049459  nop     dword ptr [rax+rax+00h]
0x14004945e  test    eax, eax
0x140049460  jz      loc_1400495BD
0x140049466  mov     rcx, cs:WPP_GLOBAL_Control
0x14004946d  cmp     rcx, r12
0x140049470  jz      loc_1400495BD
0x140049476  test    [rcx+1Ch], r14b
0x14004947a  jz      loc_1400495BD
0x140049480  cmp     byte ptr [rcx+19h], 2
0x140049484  jb      loc_1400495BD
0x14004948a  mov     edx, 40h ; '@'
0x14004948f  jmp     loc_14004935A
0x140049494  call    cs:__imp_RpcRevertToSelf
0x14004949b  nop     dword ptr [rax+rax+00h]
0x1400494a0  mov     ebx, eax
0x1400494a2  test    eax, eax
0x1400494a4  jz      short loc_1400494D4
0x1400494a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400494ad  cmp     rcx, r12
0x1400494b0  jz      loc_1400495BD
0x1400494b6  test    [rcx+1Ch], r14b
0x1400494ba  jz      loc_1400495BD
0x1400494c0  cmp     byte ptr [rcx+19h], 2
0x1400494c4  jb      loc_1400495BD
0x1400494ca  mov     edx, 41h ; 'A'
0x1400494cf  jmp     loc_14004935A
0x1400494d4  mov     rax, [rsp+78h+TokenHandle]
0x1400494d9  lea     r9, GenericMapping; GenericMapping
0x1400494e0  lea     r8, ?g_pFaxSD@@3PEAXEA; ObjectsSecurityDescriptor
0x1400494e7  mov     [rsp+78h+Token], rax; Token
0x1400494ec  mov     rdx, rbp; ModificationDescriptor
0x1400494ef  mov     ecx, esi; SecurityInformation
0x1400494f1  call    cs:__imp_SetPrivateObjectSecurity
0x1400494f8  nop     dword ptr [rax+rax+00h]
0x1400494fd  test    eax, eax
0x1400494ff  jnz     short loc_14004953D
0x140049501  call    cs:__imp_GetLastError
0x140049508  nop     dword ptr [rax+rax+00h]
0x14004950d  mov     ebx, eax
0x14004950f  mov     rcx, cs:WPP_GLOBAL_Control
0x140049516  cmp     rcx, r12
0x140049519  jz      loc_1400495BD
0x14004951f  test    [rcx+1Ch], r14b
0x140049523  jz      loc_1400495BD
0x140049529  cmp     byte ptr [rcx+19h], 2
0x14004952d  jb      loc_1400495BD
0x140049533  mov     edx, 42h ; 'B'
0x140049538  jmp     loc_14004935A
0x14004953d  mov     rcx, cs:?g_pFaxSD@@3PEAXEA; pAbsoluteSecurityDescriptor
0x140049544  call    ?SaveSecurityDescriptor@@YAKPEAX@Z; SaveSecurityDescriptor(void *)
0x140049549  mov     ebx, eax
0x14004954b  test    eax, eax
0x14004954d  jz      short loc_140049582
0x14004954f  mov     rcx, cs:WPP_GLOBAL_Control
0x140049556  cmp     rcx, r12
0x140049559  jz      short loc_14004957B
0x14004955b  test    [rcx+1Ch], r14b
0x14004955f  jz      short loc_14004957B
0x140049561  cmp     byte ptr [rcx+19h], 2
0x140049565  jb      short loc_14004957B
0x140049567  mov     rcx, [rcx+10h]
0x14004956b  mov     edx, 43h ; 'C'
0x140049570  mov     r9d, eax
0x140049573  mov     r8, r13
0x140049576  call    WPP_SF_d
0x14004957b  mov     ebx, 3F7h
0x140049580  jmp     short loc_1400495BD
0x140049582  mov     ecx, 5
0x140049587  call    ?CreateConfigEvent@@YAKW4FAX_ENUM_CONFIG_TYPE@@@Z; CreateConfigEvent(FAX_ENUM_CONFIG_TYPE)
0x14004958c  test    eax, eax
0x14004958e  jz      short loc_1400495BD
0x140049590  mov     rcx, cs:WPP_GLOBAL_Control
0x140049597  cmp     rcx, r12
0x14004959a  jz      short loc_1400495BD
0x14004959c  test    [rcx+1Ch], r14b
0x1400495a0  jz      short loc_1400495BD
0x1400495a2  cmp     byte ptr [rcx+19h], 2
0x1400495a6  jb      short loc_1400495BD
0x1400495a8  mov     rcx, [rcx+10h]
0x1400495ac  movzx   r9d, ax
0x1400495b0  mov     edx, 44h ; 'D'
0x1400495b5  mov     r8, r13
0x1400495b8  call    WPP_SF_h
0x1400495bd  lea     rcx, ?g_CsSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400495c4  call    cs:__imp_LeaveCriticalSection
0x1400495cb  nop     dword ptr [rax+rax+00h]
0x1400495d0  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x1400495d5  test    rcx, rcx
0x1400495d8  jz      short loc_140049629
0x1400495da  call    cs:__imp_CloseHandle
0x1400495e1  nop     dword ptr [rax+rax+00h]
0x1400495e6  test    eax, eax
0x1400495e8  jnz     short loc_140049629
0x1400495ea  mov     rax, cs:WPP_GLOBAL_Control
0x1400495f1  cmp     rax, r12
0x1400495f4  jz      short loc_140049629
0x1400495f6  test    [rax+1Ch], r14b
0x1400495fa  jz      short loc_140049629
0x1400495fc  cmp     byte ptr [rax+19h], 2
0x140049600  jb      short loc_140049629
0x140049602  call    cs:__imp_GetLastError
0x140049609  nop     dword ptr [rax+rax+00h]
0x14004960e  mov     rcx, cs:WPP_GLOBAL_Control
0x140049615  mov     edx, 45h ; 'E'
0x14004961a  mov     r9d, eax
0x14004961d  mov     r8, r13
0x140049620  mov     rcx, [rcx+10h]
0x140049624  call    WPP_SF_d
0x140049629  cmp     ebx, 8
0x14004962c  jz      short loc_140049633
0x14004962e  cmp     ebx, 0Eh
0x140049631  jnz     short loc_140049638
0x140049633  mov     ebx, 1B59h
0x140049638  mov     eax, ebx
0x14004963a  jmp     short loc_140049663
0x14004963c  cmp     rcx, r12
0x14004963f  jz      short loc_14004965E
0x140049641  test    [rcx+1Ch], r14b
0x140049645  jz      short loc_14004965E
0x140049647  cmp     byte ptr [rcx+19h], 2
0x14004964b  jb      short loc_14004965E
0x14004964d  mov     edx, 38h ; '8'
0x140049652  mov     rcx, [rcx+10h]
0x140049656  mov     r8, r13
0x140049659  call    WPP_SF_
0x14004965e  mov     eax, 57h ; 'W'
0x140049663  add     rsp, 48h
0x140049667  pop     r14
0x140049669  pop     r13
0x14004966b  pop     r12
0x14004966d  pop     rsi
0x14004966e  pop     rbp
0x14004966f  pop     rbx
0x140049670  retn
```
