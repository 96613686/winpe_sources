# KdcInsertRequestorGuidIntoMarshalledPac(PKERB_AUTHORIZATION_DATA_s *)

- ea: `0x18004941c`
- end: `0x18004980b`
- name: `?KdcInsertRequestorGuidIntoMarshalledPac@@YAJPEAUPKERB_AUTHORIZATION_DATA_s@@@Z`
- size: `1007`
- prototype: `__int64 __fastcall(struct PKERB_AUTHORIZATION_DATA_s *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004ab84`

## callees

- `0x1800038f0`
- `0x1800101c4`
- `0x1800101ec`
- `0x180049298`
- `0x18004941c`
- `0x18005a060`
- `0x18005a090`
- `0x18005d820`
- `0x18006fc78`
- `0x180070984`
- `0x180070f30`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180049567`
- `ntdll!RtlLengthSid` at `0x18004958b`
- `ntdll!RtlLengthSid` at `0x18004959f`
- `ntdll!RtlLengthSid` at `0x1800495c3`
- `ntdll!RtlLengthSid` at `0x180049567`
- `ntdll!RtlLengthSid` at `0x18004958b`
- `ntdll!RtlLengthSid` at `0x18004959f`
- `ntdll!RtlLengthSid` at `0x1800495c3`
- `ntdll!RtlValidSid` at `0x180049579`
- `ntdll!RtlValidSid` at `0x180049579`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x1800494d8`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18004975c`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x1800497e4`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x1800494d8`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18004975c`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x1800497e4`
- `SAMSRV!SamIGetUserLogonInformation3` at `0x18004967e`
- `SAMSRV!SamIGetUserLogonInformation3` at `0x18004967e`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1800494e2`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180049766`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1800497ee`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1800494e2`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180049766`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1800497ee`

## pseudocode

```c
__int64 __fastcall KdcInsertRequestorGuidIntoMarshalledPac(
        struct PKERB_AUTHORIZATION_DATA_s *a1,
        __int64 a2,
        struct _PAC_INFO_BUFFER *a3)
{
  unsigned int *v4; // r14
  struct _PAC_INFO_BUFFER *v5; // rsi
  struct _PACTYPE *v6; // rcx
  struct _PAC_INFO_BUFFER *v7; // r8
  struct _PAC_INFO_BUFFER *v8; // rax
  struct _PACTYPE *v9; // rcx
  __int64 v10; // r9
  void *v11; // rcx
  unsigned int inserted; // ebx
  void *v14; // rcx
  ULONG v15; // ebx
  ULONG v16; // eax
  void *v17; // rdi
  ULONG v18; // eax
  __int16 v19; // ax
  struct _PACTYPE *v20; // rcx
  unsigned int v21; // edx
  CSecurityData *v22; // rcx
  __int64 v23; // rdx
  __int128 v24; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v25[2]; // [rsp+70h] [rbp-10h] BYREF
  struct _PAC_INFO_BUFFER *v26; // [rsp+C0h] [rbp+40h] BYREF
  struct _GUID *v27; // [rsp+C8h] [rbp+48h] BYREF

  v26 = 0;
  v24 = 0;
  v27 = 0;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_3875113a630833a3e73becf979560e87_Traceguids);
  v4 = (unsigned int *)((char *)a1 + 16);
  v5 = PAC_Find(*((struct _PACTYPE **)a1 + 3), 0x12u, a3);
  v8 = PAC_Find(v6, 0x14u, v7);
  if ( !v5 )
  {
    if ( (CSecurityData **)v10 != &WPP_GLOBAL_Control && (*(_BYTE *)(v10 + 28) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(v10 + 16), 111, WPP_3875113a630833a3e73becf979560e87_Traceguids);
    v11 = 0;
LABEL_9:
    MIDL_user_free(v11);
    MIDL_user_free(v26);
    SamIFree_UserInternal6Information(v27);
    SamIFreeSidAndAttributesList(&v24);
    return 0;
  }
  if ( v8 )
  {
    if ( (CSecurityData **)v10 != &WPP_GLOBAL_Control && (*(_BYTE *)(v10 + 28) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(v10 + 16), 112, WPP_3875113a630833a3e73becf979560e87_Traceguids);
    inserted = 0;
LABEL_20:
    v14 = 0;
LABEL_43:
    MIDL_user_free(v14);
    goto LABEL_44;
  }
  if ( !PAC_UnMarshal(v9, *v4) )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, WPP_3875113a630833a3e73becf979560e87_Traceguids);
    inserted = 60;
    goto LABEL_20;
  }
  if ( *((_DWORD *)v5 + 1) >= 0xCu )
  {
    v15 = *((_DWORD *)v5 + 1);
    if ( v15 >= RtlLengthSid(*((PSID *)v5 + 1)) )
    {
      if ( RtlValidSid(*((PSID *)v5 + 1)) )
      {
        v16 = RtlLengthSid(*((PSID *)v5 + 1));
        v17 = MIDL_user_allocate(v16);
        v18 = RtlLengthSid(*((PSID *)v5 + 1));
        memcpy_0(v17, *((const void **)v5 + 1), v18);
        v25[0] = 0;
        v25[1] = v17;
        v19 = RtlLengthSid(v17);
        v20 = (struct _PACTYPE *)*((_QWORD *)a1 + 3);
        v21 = *v4;
        LOWORD(v25[0]) = v19;
        WORD1(v25[0]) = v19;
        if ( !PAC_ReMarshal(v20, v21) )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, WPP_3875113a630833a3e73becf979560e87_Traceguids);
          }
LABEL_28:
          MIDL_user_free(v17);
          inserted = 60;
LABEL_44:
          MIDL_user_free(v26);
          SamIFree_UserInternal6Information(v27);
          SamIFreeSidAndAttributesList(&v24);
          return inserted;
        }
        if ( (int)((__int64 (__fastcall *)(void *, __int64, _QWORD *, __int64, _DWORD, _QWORD, _QWORD, _QWORD, struct _GUID **, __int128 *, _QWORD, _QWORD))SamIGetUserLogonInformation3)(
                    GlobalAccountDomainHandle,
                    136,
                    v25,
                    1,
                    0,
                    0,
                    0,
                    0,
                    &v27,
                    &v24,
                    0,
                    0) < 0 )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, WPP_3875113a630833a3e73becf979560e87_Traceguids, 0);
          }
          goto LABEL_28;
        }
        inserted = KdcBuildPacGuidBuffer(v27 + 47, &v26);
        if ( inserted )
        {
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_42;
          }
          v23 = 117;
        }
        else
        {
          inserted = KdcInsertPacSectionIntoMarshalledPac((struct _PACTYPE **)a1 + 3, (unsigned int *)a1 + 4, v26);
          if ( !inserted )
          {
            if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, WPP_3875113a630833a3e73becf979560e87_Traceguids);
            }
            v11 = v17;
            goto LABEL_9;
          }
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_42;
          }
          v23 = 118;
        }
        WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_3875113a630833a3e73becf979560e87_Traceguids, inserted);
LABEL_42:
        v14 = v17;
        goto LABEL_43;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, WPP_3875113a630833a3e73becf979560e87_Traceguids);
  MIDL_user_free(0);
  MIDL_user_free(v26);
  SamIFree_UserInternal6Information(v27);
  SamIFreeSidAndAttributesList(&v24);
  return 60;
}

```

## disassembly

```asm
0x18004941c  push    rbp
0x18004941e  push    rbx
0x18004941f  push    rsi
0x180049420  push    rdi
0x180049421  push    r13
0x180049423  push    r14
0x180049425  push    r15
0x180049427  mov     rbp, rsp
0x18004942a  sub     rsp, 80h
0x180049431  xorps   xmm0, xmm0
0x180049434  mov     [rbp+arg_0], 0
0x18004943c  movups  [rbp+var_20], xmm0
0x180049440  mov     r13, rcx
0x180049443  mov     [rbp+arg_8], 0
0x18004944b  mov     r9, cs:WPP_GLOBAL_Control
0x180049452  lea     rdi, WPP_GLOBAL_Control
0x180049459  cmp     r9, rdi
0x18004945c  jz      short loc_180049481
0x18004945e  test    byte ptr [r9+1Ch], 4
0x180049463  jz      short loc_180049481
0x180049465  mov     rcx, [r9+10h]
0x180049469  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x180049470  mov     edx, 6Eh ; 'n'
0x180049475  call    WPP_SF_
0x18004947a  mov     r9, cs:WPP_GLOBAL_Control
0x180049481  lea     r14, [r13+10h]
0x180049485  mov     edx, 12h; unsigned int
0x18004948a  mov     rcx, [r14+8]; struct _PACTYPE *
0x18004948e  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x180049493  mov     edx, 14h; unsigned int
0x180049498  mov     rsi, rax
0x18004949b  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x1800494a0  test    rsi, rsi
0x1800494a3  jnz     short loc_1800494EF
0x1800494a5  cmp     r9, rdi
0x1800494a8  jz      short loc_1800494C4
0x1800494aa  test    byte ptr [r9+1Ch], 1
0x1800494af  jz      short loc_1800494C4
0x1800494b1  mov     rcx, [r9+10h]
0x1800494b5  lea     edx, [rsi+6Fh]
0x1800494b8  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x1800494bf  call    WPP_SF_
0x1800494c4  xor     ecx, ecx; void *
0x1800494c6  call    MIDL_user_free
0x1800494cb  mov     rcx, [rbp+arg_0]; void *
0x1800494cf  call    MIDL_user_free
0x1800494d4  mov     rcx, [rbp+arg_8]
0x1800494d8  call    cs:__imp_SamIFree_UserInternal6Information
0x1800494de  lea     rcx, [rbp+var_20]
0x1800494e2  call    cs:__imp_SamIFreeSidAndAttributesList
0x1800494e8  xor     eax, eax
0x1800494ea  jmp     loc_1800497F9
0x1800494ef  test    rax, rax
0x1800494f2  jz      short loc_180049519
0x1800494f4  cmp     r9, rdi
0x1800494f7  jz      short loc_180049515
0x1800494f9  test    byte ptr [r9+1Ch], 1
0x1800494fe  jz      short loc_180049515
0x180049500  mov     rcx, [r9+10h]
0x180049504  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x18004950b  mov     edx, 70h ; 'p'
0x180049510  call    WPP_SF_
0x180049515  xor     ebx, ebx
0x180049517  jmp     short loc_18004954F
0x180049519  mov     edx, [r14]; unsigned int
0x18004951c  call    ?PAC_UnMarshal@@YAKPEAU_PACTYPE@@K@Z; PAC_UnMarshal(_PACTYPE *,ulong)
0x180049521  test    eax, eax
0x180049523  jnz     short loc_180049556
0x180049525  mov     rcx, cs:WPP_GLOBAL_Control
0x18004952c  cmp     rcx, rdi
0x18004952f  jz      short loc_18004954A
0x180049531  test    byte ptr [rcx+1Ch], 1
0x180049535  jz      short loc_18004954A
0x180049537  mov     rcx, [rcx+10h]
0x18004953b  lea     edx, [rax+71h]
0x18004953e  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x180049545  call    WPP_SF_
0x18004954a  mov     ebx, 3Ch ; '<'
0x18004954f  xor     ecx, ecx
0x180049551  jmp     loc_18004974A
0x180049556  cmp     dword ptr [rsi+4], 0Ch
0x18004955a  jb      loc_1800497A9
0x180049560  mov     rcx, [rsi+8]; Sid
0x180049564  mov     ebx, [rsi+4]
0x180049567  call    cs:__imp_RtlLengthSid
0x18004956d  cmp     ebx, eax
0x18004956f  jb      loc_1800497A9
0x180049575  mov     rcx, [rsi+8]; Sid
0x180049579  call    cs:__imp_RtlValidSid
0x18004957f  test    al, al
0x180049581  jz      loc_1800497A9
0x180049587  mov     rcx, [rsi+8]; Sid
0x18004958b  call    cs:__imp_RtlLengthSid
0x180049591  mov     ecx, eax; size
0x180049593  call    MIDL_user_allocate
0x180049598  mov     rcx, [rsi+8]; Sid
0x18004959c  mov     rdi, rax
0x18004959f  call    cs:__imp_RtlLengthSid
0x1800495a5  mov     rdx, [rsi+8]; Src
0x1800495a9  mov     rcx, rdi; void *
0x1800495ac  mov     r8d, eax; Size
0x1800495af  call    memcpy_0
0x1800495b4  mov     rcx, rdi; Sid
0x1800495b7  mov     [rbp+var_10], 0
0x1800495bf  mov     [rbp+var_8], rdi
0x1800495c3  call    cs:__imp_RtlLengthSid
0x1800495c9  mov     rcx, [r13+18h]; struct _PACTYPE *
0x1800495cd  mov     edx, [r14]; unsigned int
0x1800495d0  mov     word ptr [rbp+var_10], ax
0x1800495d4  mov     word ptr [rbp+var_10+2], ax
0x1800495d8  call    ?PAC_ReMarshal@@YAEPEAU_PACTYPE@@K@Z; PAC_ReMarshal(_PACTYPE *,ulong)
0x1800495dd  test    al, al
0x1800495df  jnz     short loc_180049621
0x1800495e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800495e8  lea     rax, WPP_GLOBAL_Control
0x1800495ef  cmp     rcx, rax
0x1800495f2  jz      short loc_18004960F
0x1800495f4  test    byte ptr [rcx+1Ch], 1
0x1800495f8  jz      short loc_18004960F
0x1800495fa  mov     rcx, [rcx+10h]
0x1800495fe  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x180049605  mov     edx, 73h ; 's'
0x18004960a  call    WPP_SF_
0x18004960f  mov     rcx, rdi; void *
0x180049612  call    MIDL_user_free
0x180049617  mov     ebx, 3Ch ; '<'
0x18004961c  jmp     loc_18004974F
0x180049621  mov     rcx, cs:?GlobalAccountDomainHandle@@3PEAXEA; void * GlobalAccountDomainHandle
0x180049628  lea     rax, [rbp+var_20]
0x18004962c  mov     [rsp+80h+var_28], 0
0x180049635  lea     r8, [rbp+var_10]
0x180049639  mov     [rsp+80h+var_30], 0
0x180049642  mov     r9d, 1
0x180049648  mov     [rsp+80h+var_38], rax
0x18004964d  mov     edx, 88h
0x180049652  lea     rax, [rbp+arg_8]
0x180049656  mov     [rsp+80h+var_40], rax
0x18004965b  mov     [rsp+80h+var_48], 0
0x180049664  mov     [rsp+80h+var_50], 0
0x18004966d  mov     [rsp+80h+var_58], 0
0x180049676  mov     [rsp+80h+var_60], 0
0x18004967e  call    cs:__imp_SamIGetUserLogonInformation3
0x180049684  test    eax, eax
0x180049686  jns     short loc_1800496C6
0x180049688  mov     rcx, cs:WPP_GLOBAL_Control
0x18004968f  lea     rax, WPP_GLOBAL_Control
0x180049696  cmp     rcx, rax
0x180049699  jz      loc_18004960F
0x18004969f  test    byte ptr [rcx+1Ch], 1
0x1800496a3  jz      loc_18004960F
0x1800496a9  mov     rcx, [rcx+10h]
0x1800496ad  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x1800496b4  mov     edx, 74h ; 't'
0x1800496b9  xor     r9d, r9d
0x1800496bc  call    WPP_SF_d
0x1800496c1  jmp     loc_18004960F
0x1800496c6  mov     rcx, [rbp+arg_8]
0x1800496ca  lea     rdx, [rbp+arg_0]; struct _PAC_INFO_BUFFER **
0x1800496ce  add     rcx, 2F0h; struct _GUID *
0x1800496d5  call    ?KdcBuildPacGuidBuffer@@YAJPEAU_GUID@@PEAPEAU_PAC_INFO_BUFFER@@@Z; KdcBuildPacGuidBuffer(_GUID *,_PAC_INFO_BUFFER * *)
0x1800496da  mov     ebx, eax
0x1800496dc  test    eax, eax
0x1800496de  jz      short loc_180049700
0x1800496e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800496e7  lea     rax, WPP_GLOBAL_Control
0x1800496ee  cmp     rcx, rax
0x1800496f1  jz      short loc_180049747
0x1800496f3  test    byte ptr [rcx+1Ch], 1
0x1800496f7  jz      short loc_180049747
0x1800496f9  mov     edx, 75h ; 'u'
0x1800496fe  jmp     short loc_180049734
0x180049700  mov     r8, [rbp+arg_0]; struct _PAC_INFO_BUFFER *
0x180049704  lea     rcx, [r14+8]; struct _PACTYPE **
0x180049708  mov     rdx, r14; unsigned int *
0x18004970b  call    ?KdcInsertPacSectionIntoMarshalledPac@@YAJPEAPEAU_PACTYPE@@PEAKPEAU_PAC_INFO_BUFFER@@@Z; KdcInsertPacSectionIntoMarshalledPac(_PACTYPE * *,ulong *,_PAC_INFO_BUFFER *)
0x180049710  mov     ebx, eax
0x180049712  test    eax, eax
0x180049714  jz      short loc_180049773
0x180049716  mov     rcx, cs:WPP_GLOBAL_Control
0x18004971d  lea     rax, WPP_GLOBAL_Control
0x180049724  cmp     rcx, rax
0x180049727  jz      short loc_180049747
0x180049729  test    byte ptr [rcx+1Ch], 1
0x18004972d  jz      short loc_180049747
0x18004972f  mov     edx, 76h ; 'v'
0x180049734  mov     rcx, [rcx+10h]
0x180049738  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x18004973f  mov     r9d, ebx
0x180049742  call    WPP_SF_d
0x180049747  mov     rcx, rdi; void *
0x18004974a  call    MIDL_user_free
0x18004974f  mov     rcx, [rbp+arg_0]; void *
0x180049753  call    MIDL_user_free
0x180049758  mov     rcx, [rbp+arg_8]
0x18004975c  call    cs:__imp_SamIFree_UserInternal6Information
0x180049762  lea     rcx, [rbp+var_20]
0x180049766  call    cs:__imp_SamIFreeSidAndAttributesList
0x18004976c  mov     eax, ebx
0x18004976e  jmp     loc_1800497F9
0x180049773  mov     rcx, cs:WPP_GLOBAL_Control
0x18004977a  lea     rax, WPP_GLOBAL_Control
0x180049781  cmp     rcx, rax
0x180049784  jz      short loc_1800497A1
0x180049786  test    byte ptr [rcx+1Ch], 4
0x18004978a  jz      short loc_1800497A1
0x18004978c  mov     rcx, [rcx+10h]
0x180049790  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x180049797  mov     edx, 77h ; 'w'
0x18004979c  call    WPP_SF_
0x1800497a1  mov     rcx, rdi
0x1800497a4  jmp     loc_1800494C6
0x1800497a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800497b0  cmp     rcx, rdi
0x1800497b3  jz      short loc_1800497D0
0x1800497b5  test    byte ptr [rcx+1Ch], 1
0x1800497b9  jz      short loc_1800497D0
0x1800497bb  mov     rcx, [rcx+10h]
0x1800497bf  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x1800497c6  mov     edx, 72h ; 'r'
0x1800497cb  call    WPP_SF_
0x1800497d0  xor     ecx, ecx; void *
0x1800497d2  call    MIDL_user_free
0x1800497d7  mov     rcx, [rbp+arg_0]; void *
0x1800497db  call    MIDL_user_free
0x1800497e0  mov     rcx, [rbp+arg_8]
0x1800497e4  call    cs:__imp_SamIFree_UserInternal6Information
0x1800497ea  lea     rcx, [rbp+var_20]
0x1800497ee  call    cs:__imp_SamIFreeSidAndAttributesList
0x1800497f4  mov     eax, 3Ch ; '<'
0x1800497f9  add     rsp, 80h
0x180049800  pop     r15
0x180049802  pop     r14
0x180049804  pop     r13
0x180049806  pop     rdi
0x180049807  pop     rsi
0x180049808  pop     rbx
0x180049809  pop     rbp
0x18004980a  retn
```
