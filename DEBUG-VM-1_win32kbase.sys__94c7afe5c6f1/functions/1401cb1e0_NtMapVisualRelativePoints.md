# NtMapVisualRelativePoints

- ea: `0x1401cb1e0`
- end: `0x1401cb4f7`
- name: `NtMapVisualRelativePoints`
- size: `791`
- prototype: `__int64 __fastcall(int, int, int, int, volatile void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x140012c80`
- `0x140029324`
- `0x140029fe8`
- `0x14002a0e4`
- `0x140073a50`
- `0x140076ef0`
- `0x1400cb450`
- `0x140189580`
- `0x1401aa4fc`
- `0x1401ca884`
- `0x1401cb1e0`
- `0x1401cb500`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401cb383`
- `ntoskrnl!ProbeForRead` at `0x1401cb383`
- `ntoskrnl!ProbeForWrite` at `0x1401cb3b5`
- `ntoskrnl!ProbeForWrite` at `0x1401cb3b5`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401cb35a`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401cb38f`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401cb35a`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401cb38f`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1401cb404`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1401cb404`
- `WIN32K!W32GetUserSessionState` at `0x1401cb202`
- `WIN32K!W32GetUserSessionState` at `0x1401cb2dc`
- `WIN32K!W32GetUserSessionState` at `0x1401cb494`
- `WIN32K!W32GetUserSessionState` at `0x1401cb202`
- `WIN32K!W32GetUserSessionState` at `0x1401cb2dc`
- `WIN32K!W32GetUserSessionState` at `0x1401cb494`

## pseudocode

```c
__int64 __fastcall NtMapVisualRelativePoints(void *a1, void *a2, unsigned int a3, char *a4, char *a5)
{
  __int64 UserSessionState; // r14
  __int64 v6; // rax
  char v7; // si
  _QWORD *v8; // rbx
  char v9; // bl
  bool v10; // r14
  __int64 v11; // rax
  int v12; // r8d
  int v13; // edx
  __int64 CurrentProcessWow64Process; // rax
  __int64 v15; // rax
  CTouchProcessor *v16; // rcx
  int i; // ebx
  NTSTATUS v18; // eax
  int v19; // r14d
  ULONG v20; // eax
  bool v21; // r12
  char LastError; // bl
  __int64 v23; // rcx
  __int64 v24; // rax
  int v25; // r8d
  int v26; // edx

  UserSessionState = W32GetUserSessionState(a1);
  v6 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
         UserSessionState,
         0,
         0,
         _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
  *(_QWORD *)(UserSessionState + 16) = v6;
  v7 = 1;
  if ( v6 )
  {
    while ( 1 )
    {
      v8 = *(_QWORD **)(UserSessionState + 19544);
      if ( !v8 )
        break;
      *(_QWORD *)(UserSessionState + 19544) = v8[2];
      v8[2] = 0;
      if ( !*(_DWORD *)(*v8 + 8LL) )
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
      HMUnlockObject(*v8);
    }
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
    || (v9 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v9 = 0;
  }
  v10 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v11 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v12) = v10;
    LOBYTE(v13) = v9;
    WPP_RECORDER_AND_TRACE_SF_ii(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v13,
      v12,
      *(_QWORD *)(v11 + 69136),
      4,
      2,
      10,
      (__int64)&WPP_f8d355b3ab2236f38d0e596538285f9e_Traceguids,
      (char)a1,
      (char)a2);
  }
  if ( 8 * (unsigned __int64)a3 > 0xFFFFFFFF )
  {
    v19 = 0;
    UserSetLastError(8);
  }
  else
  {
    CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
    ProbeForRead(a4, 8 * a3, CurrentProcessWow64Process != 0 ? 1 : 4);
    v15 = PsGetCurrentProcessWow64Process();
    ProbeForWrite(a5, 8 * a3, v15 != 0 ? 1 : 4);
    for ( i = 0; i != a3; ++i )
    {
      v18 = KernelMapVisualRelativePoint(
              a1,
              a2,
              (const struct VisualPoint *)&a4[8 * i],
              (struct VisualPoint *)&a5[8 * i]);
      if ( v18 < 0 )
      {
        v19 = 0;
        v20 = RtlNtStatusToDosError(v18);
        UserSetLastError(v20);
        goto LABEL_22;
      }
    }
    v19 = 1;
  }
LABEL_22:
  if ( !v19 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      v7 = 0;
    }
    v21 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LastError = UserGetLastError();
      v24 = W32GetUserSessionState(v23);
      LOBYTE(v25) = v21;
      LOBYTE(v26) = v7;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v26,
        v25,
        *(_QWORD *)(v24 + 69136),
        2,
        2,
        11,
        (__int64)&WPP_f8d355b3ab2236f38d0e596538285f9e_Traceguids,
        LastError);
    }
  }
  UserSessionSwitchLeaveCritWithNonPaged((__int64)v16);
  return v19;
}

```

## disassembly

```asm
0x1401cb1e0  mov     rax, rsp
0x1401cb1e3  mov     [rax+20h], r9
0x1401cb1e7  mov     [rax+18h], r8d
0x1401cb1eb  mov     [rax+10h], rdx
0x1401cb1ef  mov     [rax+8], rcx
0x1401cb1f3  push    rbx
0x1401cb1f4  push    rsi
0x1401cb1f5  push    rdi
0x1401cb1f6  push    r12
0x1401cb1f8  push    r13
0x1401cb1fa  push    r14
0x1401cb1fc  push    r15
0x1401cb1fe  sub     rsp, 70h
0x1401cb202  call    cs:__imp_W32GetUserSessionState
0x1401cb209  nop     dword ptr [rax+rax+00h]
0x1401cb20e  mov     r14, rax
0x1401cb211  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401cb218  xor     r8d, r8d
0x1401cb21b  xor     edx, edx
0x1401cb21d  mov     rcx, rax
0x1401cb220  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401cb225  mov     [r14+10h], rax
0x1401cb229  xor     edi, edi
0x1401cb22b  lea     esi, [rdi+1]
0x1401cb22e  lea     r15d, [rdi+2]
0x1401cb232  test    rax, rax
0x1401cb235  jz      short loc_1401CB29A
0x1401cb237  mov     rbx, [r14+4C58h]
0x1401cb23e  test    rbx, rbx
0x1401cb241  jz      short loc_1401CB282
0x1401cb243  mov     rax, [rbx+10h]
0x1401cb247  mov     [r14+4C58h], rax
0x1401cb24e  mov     [rbx+10h], rdi
0x1401cb252  mov     rax, [rbx]
0x1401cb255  cmp     [rax+8], esi
0x1401cb258  jnb     short loc_1401CB278
0x1401cb25a  mov     [rsp+0A8h+var_58], 20000h
0x1401cb262  mov     r8d, 1236h
0x1401cb268  mov     edx, [rsp+0A8h+var_58]
0x1401cb26c  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401cb273  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401cb278  mov     rcx, [rbx]
0x1401cb27b  call    HMUnlockObject
0x1401cb280  jmp     short loc_1401CB237
0x1401cb282  lea     rcx, [r14+4C78h]
0x1401cb289  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cb28e  lea     rcx, [r14+4C68h]
0x1401cb295  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cb29a  lea     r12, WPP_GLOBAL_Control
0x1401cb2a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cb2a8  cmp     rcx, r12
0x1401cb2ab  jz      short loc_1401CB2BE
0x1401cb2ad  mov     eax, [rcx+2Ch]
0x1401cb2b0  test    r15b, al
0x1401cb2b3  jz      short loc_1401CB2BE
0x1401cb2b5  cmp     byte ptr [rcx+29h], 4
0x1401cb2b9  mov     bl, sil
0x1401cb2bc  jnb     short loc_1401CB2C1
0x1401cb2be  mov     bl, dil
0x1401cb2c1  lea     r13, WPP_RECORDER_INITIALIZED
0x1401cb2c8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1401cb2cf  setnz   r14b
0x1401cb2d3  test    bl, bl
0x1401cb2d5  jnz     short loc_1401CB2DC
0x1401cb2d7  test    r14b, r14b
0x1401cb2da  jz      short loc_1401CB33B
0x1401cb2dc  call    cs:__imp_W32GetUserSessionState
0x1401cb2e3  nop     dword ptr [rax+rax+00h]
0x1401cb2e8  mov     r9, [rax+10E10h]
0x1401cb2ef  mov     rax, [rsp+0A8h+arg_8]
0x1401cb2f7  mov     [rsp+0A8h+var_60], rax
0x1401cb2fc  mov     rax, [rsp+0A8h+arg_0]
0x1401cb304  mov     [rsp+0A8h+var_68], rax
0x1401cb309  lea     rax, WPP_f8d355b3ab2236f38d0e596538285f9e_Traceguids
0x1401cb310  mov     [rsp+0A8h+var_70], rax
0x1401cb315  mov     [rsp+0A8h+var_78], 0Ah
0x1401cb31c  mov     [rsp+0A8h+var_80], r15d
0x1401cb321  mov     [rsp+0A8h+var_88], 4
0x1401cb326  mov     r8b, r14b
0x1401cb329  mov     dl, bl
0x1401cb32b  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cb332  mov     rcx, [rcx+18h]
0x1401cb336  call    WPP_RECORDER_AND_TRACE_SF_ii
0x1401cb33b  mov     eax, [rsp+0A8h+arg_10]
0x1401cb342  shl     rax, 3
0x1401cb346  mov     ecx, 0FFFFFFFFh
0x1401cb34b  cmp     rax, rcx
0x1401cb34e  ja      loc_1401CB445
0x1401cb354  mov     [rsp+0A8h+var_58], edi
0x1401cb358  mov     ebx, eax
0x1401cb35a  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401cb361  nop     dword ptr [rax+rax+00h]
0x1401cb366  neg     rax
0x1401cb369  sbb     r8d, r8d
0x1401cb36c  mov     r14d, 0FFFFFFFDh
0x1401cb372  and     r8d, r14d
0x1401cb375  add     r8d, 4; Alignment
0x1401cb379  mov     edx, ebx; Length
0x1401cb37b  mov     rcx, [rsp+0A8h+Address]; Address
0x1401cb383  call    cs:__imp_ProbeForRead
0x1401cb38a  nop     dword ptr [rax+rax+00h]
0x1401cb38f  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401cb396  nop     dword ptr [rax+rax+00h]
0x1401cb39b  neg     rax
0x1401cb39e  sbb     r8d, r8d
0x1401cb3a1  and     r8d, r14d
0x1401cb3a4  add     r8d, 4; Alignment
0x1401cb3a8  mov     edx, ebx; Length
0x1401cb3aa  mov     r14, [rsp+0A8h+arg_20]
0x1401cb3b2  mov     rcx, r14; Address
0x1401cb3b5  call    cs:__imp_ProbeForWrite
0x1401cb3bc  nop     dword ptr [rax+rax+00h]
0x1401cb3c1  mov     ebx, edi
0x1401cb3c3  mov     [rsp+0A8h+var_54], ebx
0x1401cb3c7  cmp     ebx, [rsp+0A8h+arg_10]
0x1401cb3ce  jz      short loc_1401CB41D
0x1401cb3d0  mov     eax, ebx
0x1401cb3d2  lea     r9, [r14+rax*8]; struct VisualPoint *
0x1401cb3d6  mov     rcx, [rsp+0A8h+Address]
0x1401cb3de  lea     r8, [rcx+rax*8]; struct VisualPoint *
0x1401cb3e2  mov     rdx, [rsp+0A8h+arg_8]; void *
0x1401cb3ea  mov     rcx, [rsp+0A8h+arg_0]; void *
0x1401cb3f2  call    ?KernelMapVisualRelativePoint@@YAJ_J0PEBUVisualPoint@@PEAU1@@Z; KernelMapVisualRelativePoint(__int64,__int64,VisualPoint const *,VisualPoint *)
0x1401cb3f7  test    eax, eax
0x1401cb3f9  jns     short loc_1401CB419
0x1401cb3fb  mov     r14d, edi
0x1401cb3fe  mov     [rsp+0A8h+var_44], edi
0x1401cb402  mov     ecx, eax; Status
0x1401cb404  call    cs:__imp_RtlNtStatusToDosError
0x1401cb40b  nop     dword ptr [rax+rax+00h]
0x1401cb410  mov     ecx, eax
0x1401cb412  call    UserSetLastError
0x1401cb417  jmp     short loc_1401CB452
0x1401cb419  add     ebx, esi
0x1401cb41b  jmp     short loc_1401CB3C3
0x1401cb41d  mov     r14d, esi
0x1401cb420  jmp     short loc_1401CB452
0x1401cb422  mov     r14d, [rsp+0A8h+var_58]
0x1401cb427  mov     [rsp+0A8h+var_44], r14d
0x1401cb42c  xor     edi, edi
0x1401cb42e  lea     esi, [rdi+1]
0x1401cb431  lea     r15d, [rdi+2]
0x1401cb435  lea     r12, WPP_GLOBAL_Control
0x1401cb43c  lea     r13, WPP_RECORDER_INITIALIZED
0x1401cb443  jmp     short loc_1401CB452
0x1401cb445  mov     r14d, edi
0x1401cb448  mov     ecx, 8
0x1401cb44d  call    UserSetLastError
0x1401cb452  test    r14d, r14d
0x1401cb455  jnz     loc_1401CB4DE
0x1401cb45b  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cb462  cmp     rcx, r12
0x1401cb465  jz      short loc_1401CB475
0x1401cb467  mov     eax, [rcx+2Ch]
0x1401cb46a  test    r15b, al
0x1401cb46d  jz      short loc_1401CB475
0x1401cb46f  cmp     [rcx+29h], r15b
0x1401cb473  jnb     short loc_1401CB478
0x1401cb475  mov     sil, dil
0x1401cb478  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1401cb47f  setnz   r12b
0x1401cb483  test    sil, sil
0x1401cb486  jnz     short loc_1401CB48D
0x1401cb488  test    r12b, r12b
0x1401cb48b  jz      short loc_1401CB4DE
0x1401cb48d  call    UserGetLastError
0x1401cb492  mov     ebx, eax
0x1401cb494  call    cs:__imp_W32GetUserSessionState
0x1401cb49b  nop     dword ptr [rax+rax+00h]
0x1401cb4a0  mov     r9, [rax+10E10h]
0x1401cb4a7  mov     dword ptr [rsp+0A8h+var_68], ebx
0x1401cb4ab  lea     rax, WPP_f8d355b3ab2236f38d0e596538285f9e_Traceguids
0x1401cb4b2  mov     [rsp+0A8h+var_70], rax
0x1401cb4b7  mov     [rsp+0A8h+var_78], 0Bh
0x1401cb4be  mov     [rsp+0A8h+var_80], r15d
0x1401cb4c3  mov     [rsp+0A8h+var_88], r15b
0x1401cb4c8  mov     r8b, r12b
0x1401cb4cb  mov     dl, sil
0x1401cb4ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1401cb4d5  mov     rcx, [rcx+18h]
0x1401cb4d9  call    WPP_RECORDER_AND_TRACE_SF_D
0x1401cb4de  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401cb4e3  movsxd  rax, r14d
0x1401cb4e6  add     rsp, 70h
0x1401cb4ea  pop     r15
0x1401cb4ec  pop     r14
0x1401cb4ee  pop     r13
0x1401cb4f0  pop     r12
0x1401cb4f2  pop     rdi
0x1401cb4f3  pop     rsi
0x1401cb4f4  pop     rbx
0x1401cb4f5  retn
0x14023a2b1  push    rbp
0x14023a2b3  sub     rsp, 50h
0x14023a2b7  mov     rbp, rdx
0x14023a2ba  mov     rax, [rcx]
0x14023a2bd  mov     ecx, [rax]
0x14023a2bf  mov     [rbp+58h], ecx
0x14023a2c2  mov     ecx, [rbp+58h]
0x14023a2c5  call    SetLastNtError
0x14023a2ca  mov     dword ptr [rbp+60h], 1
0x14023a2d1  mov     eax, [rbp+60h]
0x14023a2d4  add     rsp, 50h
0x14023a2d8  pop     rbp
0x14023a2d9  retn
```
