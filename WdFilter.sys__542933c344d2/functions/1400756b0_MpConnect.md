# MpConnect

- ea: `0x1400756b0`
- end: `0x140075c5f`
- name: `MpConnect`
- size: `1455`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID *ConnectionPortCookie)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x140003d20`
- `0x1400049dc`
- `0x14000aa0c`
- `0x14000ab20`
- `0x1400118d0`
- `0x14002c980`
- `0x1400756b0`
- `0x140075c60`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140075b7b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008cf0d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140075b7b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008cf0d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140075b6f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008cf01`
- `ntoskrnl!ExReleaseResourceLite` at `0x140075b6f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008cf01`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14007583c`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14007583c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140075746`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140075746`
- `ntoskrnl!CmUnRegisterCallback` at `0x140075bd2`
- `ntoskrnl!CmUnRegisterCallback` at `0x14008cf68`
- `ntoskrnl!CmUnRegisterCallback` at `0x140075bd2`
- `ntoskrnl!CmUnRegisterCallback` at `0x14008cf68`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140075731`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140075731`
- `ntoskrnl!IoGetCurrentProcess` at `0x140075702`
- `ntoskrnl!IoGetCurrentProcess` at `0x140075702`
- `ntoskrnl!ExAcquireFastMutex` at `0x140075b9d`
- `ntoskrnl!ExAcquireFastMutex` at `0x14008cf32`
- `ntoskrnl!ExAcquireFastMutex` at `0x140075b9d`
- `ntoskrnl!ExAcquireFastMutex` at `0x14008cf32`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140075716`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140075716`
- `ntoskrnl!ExReleaseFastMutex` at `0x140075c0f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14008cfa9`
- `ntoskrnl!ExReleaseFastMutex` at `0x140075c0f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14008cfa9`

## pseudocode

```c
__int64 __fastcall MpConnect(__int64 a1, __int64 a2, __int64 a3, __int64 a4, PVOID *ConnectionPortCookie)
{
  int v7; // edi
  bool v8; // r14
  PEPROCESS CurrentProcess; // r12
  HANDLE CurrentProcessId; // r13
  ULONG_PTR v11; // rbx
  __int64 v12; // r8
  PDEVICE_OBJECT v13; // rcx
  int v14; // edx
  __int64 v15; // r8
  __int64 v16; // r9
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  char *v20; // rax
  _BYTE ProcessInformation[8]; // [rsp+68h] [rbp-40h] BYREF

  v7 = -1073741823;
  ProcessInformation[0] = 0;
  v8 = 0;
  CurrentProcess = IoGetCurrentProcess();
  CurrentProcessId = PsGetCurrentProcessId();
  v11 = MpData;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(v11 + 752), 1u);
  if ( a3 )
  {
    if ( *(_DWORD *)a3 && *(_BYTE *)(a3 + 6) && *(_DWORD *)(MpData + 3928) == 1 && !*(_BYTE *)(MpData + 3932) )
    {
      *(_DWORD *)(MpData + 3928) = 0;
      *(_QWORD *)(*(_QWORD *)(MpData + 8) + 104LL) = *(_QWORD *)(MpData + 3920);
    }
    if ( *(_DWORD *)a3 >= 2u )
      v8 = *(_DWORD *)(a3 + 8) == 2;
  }
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        (unsigned int)WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids,
        (_DWORD)CurrentProcess,
        (__int64)CurrentProcessId);
    goto LABEL_13;
  }
  if ( !*(_QWORD *)(MpData + 232) || !*(_QWORD *)(MpData + 240) )
  {
    if ( (*(_DWORD *)(MpData + 864) & 8) != 0 )
    {
      if ( ZwQueryInformationProcess(
             (HANDLE)0xFFFFFFFFFFFFFFFFLL,
             ProcessAffinityUpdateMode|ProcessUserModeIOPL,
             ProcessInformation,
             1u,
             0) < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_13;
        v14 = 22;
LABEL_21:
        WPP_SF_qqqq(
          v13->AttachedDevice,
          v14,
          MpData,
          (_DWORD)CurrentProcess,
          (__int64)CurrentProcessId,
          *(_QWORD *)(MpData + 232),
          *(_QWORD *)(MpData + 240));
LABEL_13:
        v7 = -1073741790;
        goto LABEL_58;
      }
      if ( (ProcessInformation[0] & 7) == 0 || (unsigned __int8)((ProcessInformation[0] >> 4) - 3) > 4u )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_13;
        v14 = 23;
        goto LABEL_21;
      }
    }
    *(_QWORD *)(MpData + 232) = CurrentProcess;
    *(_QWORD *)(MpData + 240) = CurrentProcessId;
    LOBYTE(v12) = 1;
    MpSetProcessExempt(0, 0, v12, CurrentProcess);
  }
  v15 = *(_QWORD *)(MpData + 232);
  if ( CurrentProcess != (PEPROCESS)v15 )
  {
    v16 = *(_QWORD *)(MpData + 240);
    if ( CurrentProcessId != (HANDLE)v16 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_qqqq(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          v15,
          (_DWORD)CurrentProcess,
          (__int64)CurrentProcessId,
          v15,
          v16);
      goto LABEL_13;
    }
  }
  if ( a2 == MpData + 288 )
  {
    *(_QWORD *)(MpData + 288) = a1;
    *ConnectionPortCookie = (PVOID)(MpData + 288);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_54;
    v18 = 25;
LABEL_53:
    WPP_SF_(v17->AttachedDevice, v18, WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids);
LABEL_54:
    _InterlockedAdd((volatile signed __int32 *)(MpData + 248), 1u);
    v7 = 0;
    goto LABEL_58;
  }
  if ( a2 == MpData + 320 )
  {
    *(_QWORD *)(MpData + 320) = a1;
    *ConnectionPortCookie = (PVOID)(MpData + 320);
    *(_DWORD *)(MpData + 440) = 0;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_54;
    v18 = 26;
    goto LABEL_53;
  }
  if ( a2 == MpData + 352 )
  {
    *(_QWORD *)(MpData + 352) = a1;
    *ConnectionPortCookie = (PVOID)(MpData + 352);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_54;
    v18 = 27;
    goto LABEL_53;
  }
  if ( a2 == MpData + 384 )
  {
    *(_QWORD *)(MpData + 384) = a1;
    *ConnectionPortCookie = (PVOID)(MpData + 384);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_54;
    v18 = 28;
    goto LABEL_53;
  }
  if ( a2 == MpData + 416 )
  {
    *(_QWORD *)(MpData + 416) = a1;
    *ConnectionPortCookie = (PVOID)(MpData + 416);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_54;
    v18 = 29;
    goto LABEL_53;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids, a2);
LABEL_58:
  ExReleaseResourceLite((PERESOURCE)(MpData + 752));
  KeLeaveCriticalRegion();
  if ( v7 < 0 )
  {
    _mm_lfence();
    LOBYTE(v19) = ProcessInformation[0];
    MpTraceLogServiceConnectFailure((unsigned int)v7, CurrentProcess, CurrentProcessId, v19);
  }
  else
  {
    ExAcquireFastMutex((PFAST_MUTEX)((char *)MpRegData + 192));
    if ( (*(_DWORD *)(MpData + 864) & 8) == 0 && *((_QWORD *)MpRegData + 31) )
    {
      CmUnRegisterCallback(*(LARGE_INTEGER *)((char *)MpRegData + 248));
      *((_QWORD *)MpRegData + 31) = 0;
    }
    v20 = (char *)MpRegData;
    ++*((_DWORD *)MpRegData + 64);
    ExReleaseFastMutex((PFAST_MUTEX)(v20 + 192));
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400756b0  mov     [rsp+arg_0], rbx
0x1400756b5  mov     [rsp+arg_10], rsi
0x1400756ba  push    rdi
0x1400756bb  push    r12
0x1400756bd  push    r13
0x1400756bf  push    r14
0x1400756c1  push    r15
0x1400756c3  sub     rsp, 80h
0x1400756ca  mov     rax, cs:__security_cookie
0x1400756d1  xor     rax, rsp
0x1400756d4  mov     [rsp+0A8h+var_38], rax
0x1400756d9  mov     rsi, r8
0x1400756dc  mov     r15, rdx
0x1400756df  mov     [rsp+0A8h+var_60], rcx
0x1400756e4  mov     rax, [rsp+0A8h+ConnectionPortCookie]
0x1400756ec  mov     [rsp+0A8h+var_58], rax
0x1400756f1  mov     edi, 0C0000001h
0x1400756f6  mov     [rsp+0A8h+var_68], edi
0x1400756fa  mov     [rsp+0A8h+ProcessInformation], 0
0x1400756ff  xor     r14b, r14b
0x140075702  call    cs:__imp_IoGetCurrentProcess
0x140075709  nop     dword ptr [rax+rax+00h]
0x14007570e  mov     r12, rax
0x140075711  mov     [rsp+0A8h+var_48], rax
0x140075716  call    cs:__imp_PsGetCurrentProcessId
0x14007571d  nop     dword ptr [rax+rax+00h]
0x140075722  mov     r13, rax
0x140075725  mov     [rsp+0A8h+var_50], rax
0x14007572a  mov     rbx, cs:MpData
0x140075731  call    cs:__imp_KeEnterCriticalRegion
0x140075738  nop     dword ptr [rax+rax+00h]
0x14007573d  mov     dl, 1; Wait
0x14007573f  lea     rcx, [rbx+2F0h]; Resource
0x140075746  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14007574d  nop     dword ptr [rax+rax+00h]
0x140075752  xor     ebx, ebx
0x140075754  test    rsi, rsi
0x140075757  jz      short loc_1400757AF
0x140075759  cmp     dword ptr [rsi], 1
0x14007575c  jb      short loc_140075797
0x14007575e  cmp     [rsi+6], bl
0x140075761  jz      short loc_140075797
0x140075763  mov     rax, cs:MpData
0x14007576a  cmp     dword ptr [rax+0F58h], 1
0x140075771  jnz     short loc_140075797
0x140075773  cmp     [rax+0F5Ch], bl
0x140075779  jnz     short loc_140075797
0x14007577b  mov     [rax+0F58h], ebx
0x140075781  mov     rax, cs:MpData
0x140075788  mov     rcx, [rax+0F50h]
0x14007578f  mov     rax, [rax+8]
0x140075793  mov     [rax+68h], rcx
0x140075797  cmp     dword ptr [rsi], 2
0x14007579a  jb      short loc_1400757AF
0x14007579c  movzx   r14d, r14b
0x1400757a0  cmp     dword ptr [rsi+8], 2
0x1400757a4  mov     esi, 1
0x1400757a9  cmovz   r14d, esi
0x1400757ad  jmp     short loc_1400757B4
0x1400757af  mov     esi, 1
0x1400757b4  test    r14b, r14b
0x1400757b7  jz      short loc_1400757FB
0x1400757b9  lea     rax, WPP_GLOBAL_Control
0x1400757c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400757c7  cmp     rcx, rax
0x1400757ca  jz      short loc_1400757F1
0x1400757cc  mov     eax, [rcx+2Ch]
0x1400757cf  test    sil, al
0x1400757d2  jz      short loc_1400757F1
0x1400757d4  mov     edx, 15h
0x1400757d9  mov     [rsp+0A8h+ReturnLength], r13
0x1400757de  mov     r9, r12
0x1400757e1  lea     r8, WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids
0x1400757e8  mov     rcx, [rcx+18h]
0x1400757ec  call    WPP_SF_qq
0x1400757f1  mov     edi, 0C0000022h
0x1400757f6  jmp     loc_140075B5D
0x1400757fb  mov     rax, cs:MpData
0x140075802  cmp     [rax+0E8h], rbx
0x140075809  jz      short loc_140075818
0x14007580b  cmp     [rax+0F0h], rbx
0x140075812  jnz     loc_140075911
0x140075818  mov     eax, [rax+360h]
0x14007581e  test    al, 8
0x140075820  jz      loc_1400758E6
0x140075826  mov     [rsp+0A8h+ReturnLength], rbx; ReturnLength
0x14007582b  mov     r9d, esi; ProcessInformationLength
0x14007582e  lea     r8, [rsp+0A8h+ProcessInformation]; ProcessInformation
0x140075833  mov     edx, 3Dh ; '='; ProcessInformationClass
0x140075838  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14007583c  call    cs:__imp_ZwQueryInformationProcess
0x140075843  nop     dword ptr [rax+rax+00h]
0x140075848  mov     [rsp+0A8h+var_68], eax
0x14007584c  test    eax, eax
0x14007584e  jns     short loc_1400758A5
0x140075850  lea     rax, WPP_GLOBAL_Control
0x140075857  mov     rcx, cs:WPP_GLOBAL_Control
0x14007585e  cmp     rcx, rax
0x140075861  jz      short loc_1400757F1
0x140075863  mov     eax, [rcx+2Ch]
0x140075866  test    sil, al
0x140075869  jz      short loc_1400757F1
0x14007586b  mov     edx, 16h
0x140075870  mov     r8, cs:MpData
0x140075877  mov     rax, [r8+0F0h]
0x14007587e  mov     [rsp+0A8h+var_78], rax
0x140075883  mov     rax, [r8+0E8h]
0x14007588a  mov     [rsp+0A8h+var_80], rax
0x14007588f  mov     [rsp+0A8h+ReturnLength], r13
0x140075894  mov     r9, r12
0x140075897  mov     rcx, [rcx+18h]
0x14007589b  call    WPP_SF_qqqq
0x1400758a0  jmp     loc_1400757F1
0x1400758a5  mov     al, [rsp+0A8h+ProcessInformation]
0x1400758a9  mov     cl, al
0x1400758ab  and     cl, 7
0x1400758ae  cmp     cl, sil
0x1400758b1  jb      short loc_1400758BC
0x1400758b3  shr     al, 4
0x1400758b6  sub     al, 3
0x1400758b8  cmp     al, 4
0x1400758ba  jbe     short loc_1400758E6
0x1400758bc  lea     rax, WPP_GLOBAL_Control
0x1400758c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400758ca  cmp     rcx, rax
0x1400758cd  jz      loc_1400757F1
0x1400758d3  mov     eax, [rcx+2Ch]
0x1400758d6  test    sil, al
0x1400758d9  jz      loc_1400757F1
0x1400758df  mov     edx, 17h
0x1400758e4  jmp     short loc_140075870
0x1400758e6  mov     rax, cs:MpData
0x1400758ed  mov     [rax+0E8h], r12
0x1400758f4  mov     rax, cs:MpData
0x1400758fb  mov     [rax+0F0h], r13
0x140075902  mov     r9, r12
0x140075905  mov     r8b, sil
0x140075908  xor     edx, edx
0x14007590a  xor     ecx, ecx
0x14007590c  call    MpSetProcessExempt
0x140075911  mov     rax, cs:MpData
0x140075918  mov     r8, [rax+0E8h]
0x14007591f  cmp     r12, r8
0x140075922  jz      short loc_140075967
0x140075924  mov     r9, [rax+0F0h]
0x14007592b  cmp     r13, r9
0x14007592e  jz      short loc_140075967
0x140075930  lea     rax, WPP_GLOBAL_Control
0x140075937  mov     rcx, cs:WPP_GLOBAL_Control
0x14007593e  cmp     rcx, rax
0x140075941  jz      loc_1400757F1
0x140075947  mov     eax, [rcx+2Ch]
0x14007594a  test    sil, al
0x14007594d  jz      loc_1400757F1
0x140075953  mov     edx, 18h
0x140075958  mov     [rsp+0A8h+var_78], r9
0x14007595d  mov     [rsp+0A8h+var_80], r8
0x140075962  jmp     loc_14007588F
0x140075967  lea     rcx, [rax+120h]
0x14007596e  cmp     r15, rcx
0x140075971  jnz     short loc_1400759BC
0x140075973  mov     rdx, [rsp+0A8h+var_60]
0x140075978  mov     [rcx], rdx
0x14007597b  mov     rax, cs:MpData
0x140075982  add     rax, 120h
0x140075988  mov     rcx, [rsp+0A8h+var_58]
0x14007598d  mov     [rcx], rax
0x140075990  lea     rax, WPP_GLOBAL_Control
0x140075997  mov     rcx, cs:WPP_GLOBAL_Control
0x14007599e  cmp     rcx, rax
0x1400759a1  jz      loc_140075B14
0x1400759a7  mov     eax, [rcx+2Ch]
0x1400759aa  test    al, 4
0x1400759ac  jz      loc_140075B14
0x1400759b2  mov     edx, 19h
0x1400759b7  jmp     loc_140075B04
0x1400759bc  lea     rcx, [rax+140h]
0x1400759c3  cmp     r15, rcx
0x1400759c6  jnz     short loc_140075A1E
0x1400759c8  mov     rdx, [rsp+0A8h+var_60]
0x1400759cd  mov     [rcx], rdx
0x1400759d0  mov     rax, cs:MpData
0x1400759d7  add     rax, 140h
0x1400759dd  mov     rcx, [rsp+0A8h+var_58]
0x1400759e2  mov     [rcx], rax
0x1400759e5  mov     rax, cs:MpData
0x1400759ec  mov     [rax+1B8h], ebx
0x1400759f2  lea     rax, WPP_GLOBAL_Control
0x1400759f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140075a00  cmp     rcx, rax
0x140075a03  jz      loc_140075B14
0x140075a09  mov     eax, [rcx+2Ch]
0x140075a0c  test    al, 4
0x140075a0e  jz      loc_140075B14
0x140075a14  mov     edx, 1Ah
0x140075a19  jmp     loc_140075B04
0x140075a1e  lea     rcx, [rax+160h]
0x140075a25  cmp     r15, rcx
0x140075a28  jnz     short loc_140075A73
0x140075a2a  mov     rdx, [rsp+0A8h+var_60]
0x140075a2f  mov     [rcx], rdx
0x140075a32  mov     rax, cs:MpData
0x140075a39  add     rax, 160h
0x140075a3f  mov     rcx, [rsp+0A8h+var_58]
0x140075a44  mov     [rcx], rax
0x140075a47  lea     rax, WPP_GLOBAL_Control
0x140075a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140075a55  cmp     rcx, rax
0x140075a58  jz      loc_140075B14
0x140075a5e  mov     eax, [rcx+2Ch]
0x140075a61  test    al, 4
0x140075a63  jz      loc_140075B14
0x140075a69  mov     edx, 1Bh
0x140075a6e  jmp     loc_140075B04
0x140075a73  lea     rcx, [rax+180h]
0x140075a7a  cmp     r15, rcx
0x140075a7d  jnz     short loc_140075ABD
0x140075a7f  mov     rdx, [rsp+0A8h+var_60]
0x140075a84  mov     [rcx], rdx
0x140075a87  mov     rax, cs:MpData
0x140075a8e  add     rax, 180h
0x140075a94  mov     rcx, [rsp+0A8h+var_58]
0x140075a99  mov     [rcx], rax
0x140075a9c  lea     rax, WPP_GLOBAL_Control
0x140075aa3  mov     rcx, cs:WPP_GLOBAL_Control
0x140075aaa  cmp     rcx, rax
0x140075aad  jz      short loc_140075B14
0x140075aaf  mov     eax, [rcx+2Ch]
0x140075ab2  test    al, 4
0x140075ab4  jz      short loc_140075B14
0x140075ab6  mov     edx, 1Ch
0x140075abb  jmp     short loc_140075B04
0x140075abd  add     rax, 1A0h
0x140075ac3  cmp     r15, rax
0x140075ac6  jnz     short loc_140075B2A
0x140075ac8  mov     rdx, [rsp+0A8h+var_60]
0x140075acd  mov     [rax], rdx
0x140075ad0  mov     rax, cs:MpData
0x140075ad7  add     rax, 1A0h
0x140075add  mov     rcx, [rsp+0A8h+var_58]
0x140075ae2  mov     [rcx], rax
0x140075ae5  lea     rax, WPP_GLOBAL_Control
0x140075aec  mov     rcx, cs:WPP_GLOBAL_Control
0x140075af3  cmp     rcx, rax
0x140075af6  jz      short loc_140075B14
0x140075af8  mov     eax, [rcx+2Ch]
0x140075afb  test    al, 4
0x140075afd  jz      short loc_140075B14
0x140075aff  mov     edx, 1Dh
0x140075b04  lea     r8, WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids
0x140075b0b  mov     rcx, [rcx+18h]
0x140075b0f  call    WPP_SF_
0x140075b14  mov     rax, cs:MpData
0x140075b1b  lock add [rax+0F8h], esi
0x140075b22  mov     edi, ebx
0x140075b24  mov     [rsp+0A8h+var_68], ebx
0x140075b28  jmp     short loc_140075B61
0x140075b2a  lea     rax, WPP_GLOBAL_Control
0x140075b31  mov     rcx, cs:WPP_GLOBAL_Control
0x140075b38  cmp     rcx, rax
0x140075b3b  jz      short loc_140075B5D
0x140075b3d  mov     eax, [rcx+2Ch]
0x140075b40  test    sil, al
0x140075b43  jz      short loc_140075B5D
0x140075b45  mov     edx, 1Eh
0x140075b4a  mov     r9, r15
0x140075b4d  lea     r8, WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids
0x140075b54  mov     rcx, [rcx+18h]
0x140075b58  call    WPP_SF_q
0x140075b5d  mov     [rsp+0A8h+var_68], edi
0x140075b61  mov     rcx, cs:MpData
0x140075b68  add     rcx, 2F0h; Resource
0x140075b6f  call    cs:__imp_ExReleaseResourceLite
0x140075b76  nop     dword ptr [rax+rax+00h]
0x140075b7b  call    cs:__imp_KeLeaveCriticalRegion
0x140075b82  nop     dword ptr [rax+rax+00h]
0x140075b87  test    edi, edi
0x140075b89  js      loc_140075C1D
0x140075b8f  mov     rcx, cs:MpRegData
0x140075b96  add     rcx, 0C0h; FastMutex
0x140075b9d  call    cs:__imp_ExAcquireFastMutex
0x140075ba4  nop     dword ptr [rax+rax+00h]
0x140075ba9  mov     rax, cs:MpData
0x140075bb0  mov     ecx, [rax+360h]
0x140075bb6  test    cl, 8
0x140075bb9  jnz     short loc_140075BEC
0x140075bbb  mov     rcx, cs:MpRegData
0x140075bc2  cmp     [rcx+0F8h], rbx
0x140075bc9  jz      short loc_140075BEC
0x140075bcb  mov     rcx, [rcx+0F8h]; Cookie
0x140075bd2  call    cs:__imp_CmUnRegisterCallback
0x140075bd9  nop     dword ptr [rax+rax+00h]
0x140075bde  mov     rax, cs:MpRegData
0x140075be5  mov     [rax+0F8h], rbx
0x140075bec  mov     rax, cs:MpRegData
0x140075bf3  mov     ecx, [rax+100h]
0x140075bf9  inc     ecx
0x140075bfb  mov     rax, cs:MpRegData
0x140075c02  mov     [rax+100h], ecx
0x140075c08  lea     rcx, [rax+0C0h]; FastMutex
  ... truncated ...
```
