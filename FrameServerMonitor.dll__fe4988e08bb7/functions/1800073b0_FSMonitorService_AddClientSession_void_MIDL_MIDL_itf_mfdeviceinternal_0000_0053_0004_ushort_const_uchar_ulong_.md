# FSMonitorService::AddClientSession(void *,__MIDL___MIDL_itf_mfdeviceinternal_0000_0053_0004,ushort const *,uchar *,ulong,void * *)

- ea: `0x1800073b0`
- end: `0x18000775f`
- name: `?AddClientSession@FSMonitorService@@UEAAJPEAXW4__MIDL___MIDL_itf_mfdeviceinternal_0000_0053_0004@@PEBGPEAEKPEAPEAX@Z`
- size: `943`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const WCHAR *, __int64, int, _QWORD *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005f98`
- `0x180006a98`
- `0x180007348`
- `0x1800073b0`
- `0x1800099ac`
- `0x18000d538`
- `0x18000d890`
- `0x18001a448`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000773f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000773f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800074ce`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800074ce`

## pseudocode

```c
__int64 __fastcall FSMonitorService::AddClientSession(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const WCHAR *a4,
        __int64 a5,
        int a6,
        _QWORD *a7)
{
  char v10; // bp
  int v11; // eax
  const char *v12; // rax
  _QWORD *v13; // r14
  unsigned int v14; // edi
  __int64 v15; // rdx
  __int64 v16; // rbp
  _QWORD *v17; // r15
  const WCHAR *v18; // rax
  int v19; // eax
  int v20; // eax
  __int64 v22; // [rsp+80h] [rbp+8h] BYREF
  __int64 v23; // [rsp+88h] [rbp+10h]

  v23 = a2;
  v10 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v11 = *(_DWORD *)(a1 + 152);
  LODWORD(v22) = v11;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v12 = L"<nullptr>";
    if ( a4 )
      v12 = (const char *)a4;
    WPP_SF_qqdS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      38,
      (unsigned int)&WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
      a1,
      v10,
      a3,
      (__int64)v12);
    v11 = v22;
  }
  if ( *(_DWORD *)(a1 + 92) != 1 )
  {
    v14 = -1072873851;
    if ( !g_wppLevels )
      goto LABEL_38;
    v15 = 39;
LABEL_37:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, a1, v14);
LABEL_38:
    if ( byte_18005E5A5 )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 47, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, a1, v14);
    goto LABEL_40;
  }
  v13 = a7;
  if ( !a7 )
  {
    v14 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_38;
    v15 = (unsigned int)((_DWORD)a7 + 40);
    goto LABEL_37;
  }
  *a7 = 0;
  if ( !a4 )
  {
    v14 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_38;
    v15 = 41;
    goto LABEL_37;
  }
  v16 = 0;
  v17 = (_QWORD *)(a1 + 144);
  if ( !v11 )
  {
LABEL_15:
    v22 = 0;
    v19 = FSMSession::CreateFSMSession(v23, a3, a4, a5, a6, &v22);
    v14 = v19;
    if ( v19 >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 40LL))(v22);
      if ( (unsigned int)CTUnkArray<IFSCameraControlState>::Add((__int64 *)(a1 + 144), v22) )
      {
        *v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 56LL))(v22, a3);
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v22);
        goto LABEL_30;
      }
      v14 = -2147024882;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
          a1,
          -2147024882);
    }
    else if ( g_wppLevels )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, a1, v19);
    }
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v22);
    goto LABEL_38;
  }
  while ( 1 )
  {
    v18 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*v17 + 8 * v16) + 32LL))(*(_QWORD *)(*v17 + 8 * v16));
    if ( CompareStringOrdinal(a4, -1, v18, -1, 1) == 2 )
      break;
    v16 = (unsigned int)(v16 + 1);
    if ( (unsigned int)v16 >= (unsigned int)v22 )
      goto LABEL_15;
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(*v17 + 8 * v16) + 40LL))(*(_QWORD *)(*v17 + 8 * v16)) == 0x7FFFFFFF )
  {
    v14 = -2147023446;
    if ( !g_wppLevels )
      goto LABEL_38;
    v15 = 42;
    goto LABEL_37;
  }
  v20 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*v17 + 8 * v16) + 24LL))(
          *(_QWORD *)(*v17 + 8 * v16),
          v23,
          a3);
  v14 = v20;
  if ( v20 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, a1, v20);
    goto LABEL_38;
  }
  *v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*v17 + 8 * v16) + 56LL))(
           *(_QWORD *)(*v17 + 8 * v16),
           a3);
LABEL_30:
  if ( !*v13 )
  {
    v14 = -1072875845;
    if ( !g_wppLevels )
      goto LABEL_38;
    v15 = 46;
    goto LABEL_37;
  }
  FSMonitorService::InternalStopIdleTimer((FSMonitorService *)a1);
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qDq(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      48,
      &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
      a1,
      v14,
      *v13);
LABEL_40:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  return v14;
}

```

## disassembly

```asm
0x1800073b0  mov     [rsp+arg_10], rbx
0x1800073b5  mov     [rsp+arg_8], rdx
0x1800073ba  push    rbp
0x1800073bb  push    rsi
0x1800073bc  push    rdi
0x1800073bd  push    r12
0x1800073bf  push    r13
0x1800073c1  push    r14
0x1800073c3  push    r15
0x1800073c5  sub     rsp, 40h
0x1800073c9  mov     rsi, rcx
0x1800073cc  mov     rdi, r9
0x1800073cf  add     rcx, 30h ; '0'; lpCriticalSection
0x1800073d3  mov     r12d, r8d
0x1800073d6  mov     rbp, rdx
0x1800073d9  call    cs:__imp_EnterCriticalSection
0x1800073df  mov     eax, [rsi+98h]
0x1800073e5  mov     dword ptr [rsp+78h+arg_0], eax
0x1800073ec  cmp     cs:byte_18005E5A5, 8
0x1800073f3  lea     r13, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x1800073fa  jb      short loc_18000743E
0x1800073fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180007403  lea     rax, aNullptr; "<nullptr>"
0x18000740a  test    rdi, rdi
0x18000740d  mov     edx, 26h ; '&'
0x180007412  mov     r9, rsi
0x180007415  mov     r8, r13
0x180007418  cmovnz  rax, rdi
0x18000741c  mov     rcx, [rcx+0D8h]
0x180007423  mov     [rsp+78h+var_48], rax
0x180007428  mov     dword ptr [rsp+78h+var_50], r12d
0x18000742d  mov     qword ptr [rsp+78h+bIgnoreCase], rbp
0x180007432  call    WPP_SF_qqdS
0x180007437  mov     eax, dword ptr [rsp+78h+arg_0]
0x18000743e  cmp     dword ptr [rsi+5Ch], 1
0x180007442  jnz     loc_1800076DF
0x180007448  mov     r14, [rsp+78h+arg_30]
0x180007450  test    r14, r14
0x180007453  jnz     short loc_180007470
0x180007455  mov     edi, 80004003h
0x18000745a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007461  jb      loc_18000770C
0x180007467  lea     edx, [r14+28h]
0x18000746b  jmp     loc_1800076F2
0x180007470  mov     qword ptr [r14], 0
0x180007477  test    rdi, rdi
0x18000747a  jnz     short loc_180007498
0x18000747c  mov     edi, 80070057h
0x180007481  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007488  jb      loc_18000770C
0x18000748e  mov     edx, 29h ; ')'
0x180007493  jmp     loc_1800076F2
0x180007498  xor     ebp, ebp
0x18000749a  lea     r15, [rsi+90h]
0x1800074a1  test    eax, eax
0x1800074a3  jz      short loc_1800074EB
0x1800074a5  mov     rax, [r15]
0x1800074a8  mov     rcx, [rax+rbp*8]
0x1800074ac  mov     rax, [rcx]
0x1800074af  mov     rax, [rax+20h]
0x1800074b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074b8  mov     r8, rax; lpString2
0x1800074bb  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x1800074c3  or      eax, 0FFFFFFFFh
0x1800074c6  mov     rcx, rdi; lpString1
0x1800074c9  mov     r9d, eax; cchCount2
0x1800074cc  mov     edx, eax; cchCount1
0x1800074ce  call    cs:__imp_CompareStringOrdinal
0x1800074d4  cmp     eax, 2
0x1800074d7  jz      short loc_18000754F
0x1800074d9  inc     ebp
0x1800074db  cmp     ebp, dword ptr [rsp+78h+arg_0]
0x1800074e2  jb      short loc_1800074A5
0x1800074e4  lea     r13, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x1800074eb  mov     r9, [rsp+78h+arg_20]
0x1800074f3  lea     rax, [rsp+78h+arg_0]
0x1800074fb  mov     rcx, [rsp+78h+arg_8]
0x180007503  mov     r8, rdi
0x180007506  mov     [rsp+78h+var_50], rax
0x18000750b  mov     edx, r12d
0x18000750e  mov     eax, [rsp+78h+arg_28]
0x180007515  mov     [rsp+78h+bIgnoreCase], eax
0x180007519  mov     [rsp+78h+arg_0], 0
0x180007525  call    ?CreateFSMSession@FSMSession@@SAJPEAXW4__MIDL___MIDL_itf_mfdeviceinternal_0000_0053_0004@@PEBGPEAEKPEAPEAUIFSMSession@@@Z; FSMSession::CreateFSMSession(void *,__MIDL___MIDL_itf_mfdeviceinternal_0000_0053_0004,ushort const *,uchar *,ulong,IFSMSession * *)
0x18000752a  mov     edi, eax
0x18000752c  test    eax, eax
0x18000752e  jns     loc_1800075F0
0x180007534  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000753b  jb      loc_180007643
0x180007541  mov     edx, 2Ch ; ','
0x180007546  mov     [rsp+78h+bIgnoreCase], eax
0x18000754a  jmp     loc_18000762D
0x18000754f  mov     rax, [r15]
0x180007552  mov     rcx, [rax+rbp*8]
0x180007556  mov     rax, [rcx]
0x180007559  mov     rax, [rax+28h]
0x18000755d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007562  cmp     eax, 7FFFFFFFh
0x180007567  jnz     short loc_18000758C
0x180007569  mov     edi, 800705AAh
0x18000756e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007575  jb      loc_18000770C
0x18000757b  mov     edx, 2Ah ; '*'
0x180007580  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180007587  jmp     loc_1800076F5
0x18000758c  mov     rax, [r15]
0x18000758f  mov     r8d, r12d
0x180007592  mov     rdx, [rsp+78h+arg_8]
0x18000759a  mov     rcx, [rax+rbp*8]
0x18000759e  mov     rax, [rcx]
0x1800075a1  mov     rax, [rax+18h]
0x1800075a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075aa  mov     edi, eax
0x1800075ac  test    eax, eax
0x1800075ae  jns     short loc_1800075D2
0x1800075b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800075b7  jb      loc_18000770C
0x1800075bd  mov     edx, 2Bh ; '+'
0x1800075c2  mov     [rsp+78h+bIgnoreCase], eax
0x1800075c6  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x1800075cd  jmp     loc_1800076F9
0x1800075d2  mov     rax, [r15]
0x1800075d5  mov     edx, r12d
0x1800075d8  mov     rcx, [rax+rbp*8]
0x1800075dc  mov     rax, [rcx]
0x1800075df  mov     rax, [rax+38h]
0x1800075e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075e8  mov     [r14], rax
0x1800075eb  jmp     loc_18000767C
0x1800075f0  mov     rcx, [rsp+78h+arg_0]
0x1800075f8  mov     rax, [rcx]
0x1800075fb  mov     rax, [rax+28h]
0x1800075ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007604  mov     rdx, [rsp+78h+arg_0]
0x18000760c  mov     rcx, r15
0x18000760f  call    ?Add@?$CTUnkArray@UIFSCameraControlState@@@@QEAAHPEAUIFSCameraControlState@@@Z; CTUnkArray<IFSCameraControlState>::Add(IFSCameraControlState *)
0x180007614  test    eax, eax
0x180007616  jnz     short loc_180007655
0x180007618  mov     edi, 8007000Eh
0x18000761d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007624  jb      short loc_180007643
0x180007626  lea     edx, [rax+2Dh]
0x180007629  mov     [rsp+78h+bIgnoreCase], edi
0x18000762d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007634  mov     r9, rsi
0x180007637  mov     r8, r13
0x18000763a  mov     rcx, [rcx+10h]
0x18000763e  call    WPP_SF_qD
0x180007643  lea     rcx, [rsp+78h+arg_0]
0x18000764b  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180007650  jmp     loc_18000770C
0x180007655  mov     rcx, [rsp+78h+arg_0]
0x18000765d  mov     edx, r12d
0x180007660  mov     rax, [rcx]
0x180007663  mov     rax, [rax+38h]
0x180007667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000766c  lea     rcx, [rsp+78h+arg_0]
0x180007674  mov     [r14], rax
0x180007677  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18000767c  cmp     qword ptr [r14], 0
0x180007680  jnz     short loc_18000769A
0x180007682  mov     edi, 0C00D36BBh
0x180007687  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000768e  jb      short loc_18000770C
0x180007690  mov     edx, 2Eh ; '.'
0x180007695  jmp     loc_180007580
0x18000769a  mov     rcx, rsi; this
0x18000769d  call    ?InternalStopIdleTimer@FSMonitorService@@IEAAJXZ; FSMonitorService::InternalStopIdleTimer(void)
0x1800076a2  cmp     cs:byte_18005E5A5, 8
0x1800076a9  jb      loc_18000773B
0x1800076af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076b6  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x1800076bd  mov     rax, [r14]
0x1800076c0  mov     edx, 30h ; '0'
0x1800076c5  mov     [rsp+78h+var_50], rax
0x1800076ca  mov     r9, rsi
0x1800076cd  mov     [rsp+78h+bIgnoreCase], edi
0x1800076d1  mov     rcx, [rcx+0D8h]
0x1800076d8  call    WPP_SF_qDq
0x1800076dd  jmp     short loc_18000773B
0x1800076df  mov     edi, 0C00D3E85h
0x1800076e4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800076eb  jb      short loc_18000770C
0x1800076ed  mov     edx, 27h ; '''
0x1800076f2  mov     r8, r13
0x1800076f5  mov     [rsp+78h+bIgnoreCase], edi
0x1800076f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180007700  mov     r9, rsi
0x180007703  mov     rcx, [rcx+10h]
0x180007707  call    WPP_SF_qD
0x18000770c  cmp     cs:byte_18005E5A5, 1
0x180007713  jb      short loc_18000773B
0x180007715  mov     rcx, cs:WPP_GLOBAL_Control
0x18000771c  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180007723  mov     edx, 2Fh ; '/'
0x180007728  mov     [rsp+78h+bIgnoreCase], edi
0x18000772c  mov     r9, rsi
0x18000772f  mov     rcx, [rcx+0D8h]
0x180007736  call    WPP_SF_qD
0x18000773b  lea     rcx, [rsi+30h]; lpCriticalSection
0x18000773f  call    cs:__imp_LeaveCriticalSection
0x180007745  mov     rbx, [rsp+78h+arg_10]
0x18000774d  mov     eax, edi
0x18000774f  add     rsp, 40h
0x180007753  pop     r15
0x180007755  pop     r14
0x180007757  pop     r13
0x180007759  pop     r12
0x18000775b  pop     rdi
0x18000775c  pop     rsi
0x18000775d  pop     rbp
0x18000775e  retn
```
