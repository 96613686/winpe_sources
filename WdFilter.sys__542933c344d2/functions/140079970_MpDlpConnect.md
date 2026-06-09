# MpDlpConnect

- ea: `0x140079970`
- end: `0x140079e6d`
- name: `MpDlpConnect`
- size: `1277`
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
- `0x140075c60`
- `0x140079970`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079e1b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008d0dc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079e1b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008d0dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140079e0f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008d0d0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140079e0f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008d0d0`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140079af2`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140079af2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140079a06`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140079a06`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400799f1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400799f1`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400799c2`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400799c2`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400799d6`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400799d6`

## pseudocode

```c
__int64 __fastcall MpDlpConnect(__int64 a1, __int64 a2, __int64 a3, __int64 a4, PVOID *ConnectionPortCookie)
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
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        37,
        (unsigned int)WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids,
        (_DWORD)CurrentProcess,
        (__int64)CurrentProcessId);
    goto LABEL_13;
  }
  if ( !*(_QWORD *)(MpData + 256) || !*(_QWORD *)(MpData + 264) )
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
        v14 = 38;
LABEL_21:
        WPP_SF_qqqq(
          v13->AttachedDevice,
          v14,
          MpData,
          (_DWORD)CurrentProcess,
          (__int64)CurrentProcessId,
          *(_QWORD *)(MpData + 256),
          *(_QWORD *)(MpData + 264));
LABEL_13:
        v7 = -1073741790;
        goto LABEL_58;
      }
      if ( (ProcessInformation[0] & 7) == 0 || (unsigned __int8)((ProcessInformation[0] >> 4) - 3) > 4u )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_13;
        v14 = 39;
        goto LABEL_21;
      }
    }
    *(_QWORD *)(MpData + 256) = CurrentProcess;
    *(_QWORD *)(MpData + 264) = CurrentProcessId;
    LOBYTE(v12) = 1;
    MpSetProcessExempt(0, 0, v12, CurrentProcess);
  }
  v15 = *(_QWORD *)(MpData + 256);
  if ( CurrentProcess != (PEPROCESS)v15 )
  {
    v16 = *(_QWORD *)(MpData + 264);
    if ( CurrentProcessId != (HANDLE)v16 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_qqqq(
          WPP_GLOBAL_Control->AttachedDevice,
          40,
          v15,
          (_DWORD)CurrentProcess,
          (__int64)CurrentProcessId,
          v15,
          v16);
      goto LABEL_13;
    }
  }
  if ( a2 == MpData + 304 )
  {
    *(_QWORD *)(MpData + 304) = a1;
    *ConnectionPortCookie = (PVOID)(MpData + 304);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_54;
    v18 = 41;
LABEL_53:
    WPP_SF_(v17->AttachedDevice, v18, WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids);
LABEL_54:
    _InterlockedAdd((volatile signed __int32 *)(MpData + 272), 1u);
    v7 = 0;
    goto LABEL_58;
  }
  if ( a2 == MpData + 336 )
  {
    *(_QWORD *)(MpData + 336) = a1;
    *ConnectionPortCookie = (PVOID)(MpData + 336);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_54;
    v18 = 42;
    goto LABEL_53;
  }
  if ( a2 == MpData + 368 )
  {
    *(_QWORD *)(MpData + 368) = a1;
    *ConnectionPortCookie = (PVOID)(MpData + 368);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_54;
    v18 = 43;
    goto LABEL_53;
  }
  if ( a2 == MpData + 400 )
  {
    *(_QWORD *)(MpData + 400) = a1;
    *ConnectionPortCookie = (PVOID)(MpData + 400);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_54;
    v18 = 44;
    goto LABEL_53;
  }
  if ( a2 == MpData + 432 )
  {
    *(_QWORD *)(MpData + 432) = a1;
    *ConnectionPortCookie = (PVOID)(MpData + 432);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_54;
    v18 = 45;
    goto LABEL_53;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids, a2);
LABEL_58:
  ExReleaseResourceLite((PERESOURCE)(MpData + 752));
  KeLeaveCriticalRegion();
  if ( v7 < 0 )
  {
    _mm_lfence();
    LOBYTE(v19) = ProcessInformation[0];
    MpTraceLogServiceConnectFailure((unsigned int)v7, CurrentProcess, CurrentProcessId, v19);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140079970  mov     [rsp+arg_0], rbx
0x140079975  mov     [rsp+arg_10], rsi
0x14007997a  push    rdi
0x14007997b  push    r12
0x14007997d  push    r13
0x14007997f  push    r14
0x140079981  push    r15
0x140079983  sub     rsp, 80h
0x14007998a  mov     rax, cs:__security_cookie
0x140079991  xor     rax, rsp
0x140079994  mov     [rsp+0A8h+var_38], rax
0x140079999  mov     rsi, r8
0x14007999c  mov     r15, rdx
0x14007999f  mov     [rsp+0A8h+var_60], rcx
0x1400799a4  mov     rax, [rsp+0A8h+ConnectionPortCookie]
0x1400799ac  mov     [rsp+0A8h+var_58], rax
0x1400799b1  mov     edi, 0C0000001h
0x1400799b6  mov     [rsp+0A8h+var_68], edi
0x1400799ba  mov     [rsp+0A8h+ProcessInformation], 0
0x1400799bf  xor     r14b, r14b
0x1400799c2  call    cs:__imp_IoGetCurrentProcess
0x1400799c9  nop     dword ptr [rax+rax+00h]
0x1400799ce  mov     r12, rax
0x1400799d1  mov     [rsp+0A8h+var_48], rax
0x1400799d6  call    cs:__imp_PsGetCurrentProcessId
0x1400799dd  nop     dword ptr [rax+rax+00h]
0x1400799e2  mov     r13, rax
0x1400799e5  mov     [rsp+0A8h+var_50], rax
0x1400799ea  mov     rbx, cs:MpData
0x1400799f1  call    cs:__imp_KeEnterCriticalRegion
0x1400799f8  nop     dword ptr [rax+rax+00h]
0x1400799fd  mov     dl, 1; Wait
0x1400799ff  lea     rcx, [rbx+2F0h]; Resource
0x140079a06  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140079a0d  nop     dword ptr [rax+rax+00h]
0x140079a12  xor     ecx, ecx
0x140079a14  lea     ebx, [rcx+1]
0x140079a17  test    rsi, rsi
0x140079a1a  jz      short loc_140079A6B
0x140079a1c  cmp     [rsi], ebx
0x140079a1e  jb      short loc_140079A5A
0x140079a20  cmp     [rsi+6], cl
0x140079a23  jz      short loc_140079A5A
0x140079a25  mov     rax, cs:MpData
0x140079a2c  cmp     [rax+0F58h], ebx
0x140079a32  jnz     short loc_140079A5A
0x140079a34  cmp     [rax+0F5Ch], cl
0x140079a3a  jnz     short loc_140079A5A
0x140079a3c  mov     [rax+0F58h], ecx
0x140079a42  mov     rax, cs:MpData
0x140079a49  mov     rcx, [rax+0F50h]
0x140079a50  mov     rax, [rax+8]
0x140079a54  mov     [rax+68h], rcx
0x140079a58  xor     ecx, ecx
0x140079a5a  cmp     dword ptr [rsi], 2
0x140079a5d  jb      short loc_140079A6B
0x140079a5f  movzx   r14d, r14b
0x140079a63  cmp     dword ptr [rsi+8], 2
0x140079a67  cmovz   r14d, ebx
0x140079a6b  test    r14b, r14b
0x140079a6e  jnz     short loc_140079AB1
0x140079a70  lea     rax, WPP_GLOBAL_Control
0x140079a77  mov     rcx, cs:WPP_GLOBAL_Control
0x140079a7e  cmp     rcx, rax
0x140079a81  jz      short loc_140079AA7
0x140079a83  mov     eax, [rcx+2Ch]
0x140079a86  test    bl, al
0x140079a88  jz      short loc_140079AA7
0x140079a8a  mov     edx, 25h ; '%'
0x140079a8f  mov     [rsp+0A8h+ReturnLength], r13
0x140079a94  mov     r9, r12
0x140079a97  lea     r8, WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids
0x140079a9e  mov     rcx, [rcx+18h]
0x140079aa2  call    WPP_SF_qq
0x140079aa7  mov     edi, 0C0000022h
0x140079aac  jmp     loc_140079DFD
0x140079ab1  mov     rax, cs:MpData
0x140079ab8  cmp     [rax+100h], rcx
0x140079abf  jz      short loc_140079ACE
0x140079ac1  cmp     [rax+108h], rcx
0x140079ac8  jnz     loc_140079BC4
0x140079ace  mov     eax, [rax+360h]
0x140079ad4  test    al, 8
0x140079ad6  jz      loc_140079B99
0x140079adc  mov     [rsp+0A8h+ReturnLength], rcx; ReturnLength
0x140079ae1  mov     r9d, ebx; ProcessInformationLength
0x140079ae4  lea     r8, [rsp+0A8h+ProcessInformation]; ProcessInformation
0x140079ae9  mov     edx, 3Dh ; '='; ProcessInformationClass
0x140079aee  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140079af2  call    cs:__imp_ZwQueryInformationProcess
0x140079af9  nop     dword ptr [rax+rax+00h]
0x140079afe  mov     [rsp+0A8h+var_68], eax
0x140079b02  test    eax, eax
0x140079b04  jns     short loc_140079B5A
0x140079b06  lea     rax, WPP_GLOBAL_Control
0x140079b0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140079b14  cmp     rcx, rax
0x140079b17  jz      short loc_140079AA7
0x140079b19  mov     eax, [rcx+2Ch]
0x140079b1c  test    bl, al
0x140079b1e  jz      short loc_140079AA7
0x140079b20  mov     edx, 26h ; '&'
0x140079b25  mov     r8, cs:MpData
0x140079b2c  mov     rax, [r8+108h]
0x140079b33  mov     [rsp+0A8h+var_78], rax
0x140079b38  mov     rax, [r8+100h]
0x140079b3f  mov     [rsp+0A8h+var_80], rax
0x140079b44  mov     [rsp+0A8h+ReturnLength], r13
0x140079b49  mov     r9, r12
0x140079b4c  mov     rcx, [rcx+18h]
0x140079b50  call    WPP_SF_qqqq
0x140079b55  jmp     loc_140079AA7
0x140079b5a  mov     al, [rsp+0A8h+ProcessInformation]
0x140079b5e  mov     cl, al
0x140079b60  and     cl, 7
0x140079b63  cmp     cl, bl
0x140079b65  jb      short loc_140079B70
0x140079b67  shr     al, 4
0x140079b6a  sub     al, 3
0x140079b6c  cmp     al, 4
0x140079b6e  jbe     short loc_140079B99
0x140079b70  lea     rax, WPP_GLOBAL_Control
0x140079b77  mov     rcx, cs:WPP_GLOBAL_Control
0x140079b7e  cmp     rcx, rax
0x140079b81  jz      loc_140079AA7
0x140079b87  mov     eax, [rcx+2Ch]
0x140079b8a  test    bl, al
0x140079b8c  jz      loc_140079AA7
0x140079b92  mov     edx, 27h ; '''
0x140079b97  jmp     short loc_140079B25
0x140079b99  mov     rax, cs:MpData
0x140079ba0  mov     [rax+100h], r12
0x140079ba7  mov     rax, cs:MpData
0x140079bae  mov     [rax+108h], r13
0x140079bb5  mov     r9, r12
0x140079bb8  mov     r8b, bl
0x140079bbb  xor     edx, edx
0x140079bbd  xor     ecx, ecx
0x140079bbf  call    MpSetProcessExempt
0x140079bc4  mov     rax, cs:MpData
0x140079bcb  mov     r8, [rax+100h]
0x140079bd2  cmp     r12, r8
0x140079bd5  jz      short loc_140079C19
0x140079bd7  mov     r9, [rax+108h]
0x140079bde  cmp     r13, r9
0x140079be1  jz      short loc_140079C19
0x140079be3  lea     rax, WPP_GLOBAL_Control
0x140079bea  mov     rcx, cs:WPP_GLOBAL_Control
0x140079bf1  cmp     rcx, rax
0x140079bf4  jz      loc_140079AA7
0x140079bfa  mov     eax, [rcx+2Ch]
0x140079bfd  test    bl, al
0x140079bff  jz      loc_140079AA7
0x140079c05  mov     edx, 28h ; '('
0x140079c0a  mov     [rsp+0A8h+var_78], r9
0x140079c0f  mov     [rsp+0A8h+var_80], r8
0x140079c14  jmp     loc_140079B44
0x140079c19  lea     rcx, [rax+130h]
0x140079c20  cmp     r15, rcx
0x140079c23  jnz     short loc_140079C6E
0x140079c25  mov     rdx, [rsp+0A8h+var_60]
0x140079c2a  mov     [rcx], rdx
0x140079c2d  mov     rax, cs:MpData
0x140079c34  add     rax, 130h
0x140079c3a  mov     rcx, [rsp+0A8h+var_58]
0x140079c3f  mov     [rcx], rax
0x140079c42  lea     rax, WPP_GLOBAL_Control
0x140079c49  mov     rcx, cs:WPP_GLOBAL_Control
0x140079c50  cmp     rcx, rax
0x140079c53  jz      loc_140079DB9
0x140079c59  mov     eax, [rcx+2Ch]
0x140079c5c  test    al, 4
0x140079c5e  jz      loc_140079DB9
0x140079c64  mov     edx, 29h ; ')'
0x140079c69  jmp     loc_140079DA9
0x140079c6e  lea     rcx, [rax+150h]
0x140079c75  cmp     r15, rcx
0x140079c78  jnz     short loc_140079CC3
0x140079c7a  mov     rdx, [rsp+0A8h+var_60]
0x140079c7f  mov     [rcx], rdx
0x140079c82  mov     rax, cs:MpData
0x140079c89  add     rax, 150h
0x140079c8f  mov     rcx, [rsp+0A8h+var_58]
0x140079c94  mov     [rcx], rax
0x140079c97  lea     rax, WPP_GLOBAL_Control
0x140079c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140079ca5  cmp     rcx, rax
0x140079ca8  jz      loc_140079DB9
0x140079cae  mov     eax, [rcx+2Ch]
0x140079cb1  test    al, 4
0x140079cb3  jz      loc_140079DB9
0x140079cb9  mov     edx, 2Ah ; '*'
0x140079cbe  jmp     loc_140079DA9
0x140079cc3  lea     rcx, [rax+170h]
0x140079cca  cmp     r15, rcx
0x140079ccd  jnz     short loc_140079D18
0x140079ccf  mov     rdx, [rsp+0A8h+var_60]
0x140079cd4  mov     [rcx], rdx
0x140079cd7  mov     rax, cs:MpData
0x140079cde  add     rax, 170h
0x140079ce4  mov     rcx, [rsp+0A8h+var_58]
0x140079ce9  mov     [rcx], rax
0x140079cec  lea     rax, WPP_GLOBAL_Control
0x140079cf3  mov     rcx, cs:WPP_GLOBAL_Control
0x140079cfa  cmp     rcx, rax
0x140079cfd  jz      loc_140079DB9
0x140079d03  mov     eax, [rcx+2Ch]
0x140079d06  test    al, 4
0x140079d08  jz      loc_140079DB9
0x140079d0e  mov     edx, 2Bh ; '+'
0x140079d13  jmp     loc_140079DA9
0x140079d18  lea     rcx, [rax+190h]
0x140079d1f  cmp     r15, rcx
0x140079d22  jnz     short loc_140079D62
0x140079d24  mov     rdx, [rsp+0A8h+var_60]
0x140079d29  mov     [rcx], rdx
0x140079d2c  mov     rax, cs:MpData
0x140079d33  add     rax, 190h
0x140079d39  mov     rcx, [rsp+0A8h+var_58]
0x140079d3e  mov     [rcx], rax
0x140079d41  lea     rax, WPP_GLOBAL_Control
0x140079d48  mov     rcx, cs:WPP_GLOBAL_Control
0x140079d4f  cmp     rcx, rax
0x140079d52  jz      short loc_140079DB9
0x140079d54  mov     eax, [rcx+2Ch]
0x140079d57  test    al, 4
0x140079d59  jz      short loc_140079DB9
0x140079d5b  mov     edx, 2Ch ; ','
0x140079d60  jmp     short loc_140079DA9
0x140079d62  add     rax, 1B0h
0x140079d68  cmp     r15, rax
0x140079d6b  jnz     short loc_140079DCB
0x140079d6d  mov     rdx, [rsp+0A8h+var_60]
0x140079d72  mov     [rax], rdx
0x140079d75  mov     rax, cs:MpData
0x140079d7c  add     rax, 1B0h
0x140079d82  mov     rcx, [rsp+0A8h+var_58]
0x140079d87  mov     [rcx], rax
0x140079d8a  lea     rax, WPP_GLOBAL_Control
0x140079d91  mov     rcx, cs:WPP_GLOBAL_Control
0x140079d98  cmp     rcx, rax
0x140079d9b  jz      short loc_140079DB9
0x140079d9d  mov     eax, [rcx+2Ch]
0x140079da0  test    al, 4
0x140079da2  jz      short loc_140079DB9
0x140079da4  mov     edx, 2Dh ; '-'
0x140079da9  lea     r8, WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids
0x140079db0  mov     rcx, [rcx+18h]
0x140079db4  call    WPP_SF_
0x140079db9  mov     rax, cs:MpData
0x140079dc0  lock add [rax+110h], ebx
0x140079dc7  xor     edi, edi
0x140079dc9  jmp     short loc_140079DFD
0x140079dcb  lea     rax, WPP_GLOBAL_Control
0x140079dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x140079dd9  cmp     rcx, rax
0x140079ddc  jz      short loc_140079DFD
0x140079dde  mov     eax, [rcx+2Ch]
0x140079de1  test    bl, al
0x140079de3  jz      short loc_140079DFD
0x140079de5  mov     edx, 2Eh ; '.'
0x140079dea  mov     r9, r15
0x140079ded  lea     r8, WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids
0x140079df4  mov     rcx, [rcx+18h]
0x140079df8  call    WPP_SF_q
0x140079dfd  mov     [rsp+0A8h+var_68], edi
0x140079e01  mov     rcx, cs:MpData
0x140079e08  add     rcx, 2F0h; Resource
0x140079e0f  call    cs:__imp_ExReleaseResourceLite
0x140079e16  nop     dword ptr [rax+rax+00h]
0x140079e1b  call    cs:__imp_KeLeaveCriticalRegion
0x140079e22  nop     dword ptr [rax+rax+00h]
0x140079e27  test    edi, edi
0x140079e29  jns     short loc_140079E40
0x140079e2b  lfence
0x140079e2e  mov     r9b, [rsp+0A8h+ProcessInformation]
0x140079e33  mov     r8, r13
0x140079e36  mov     rdx, r12
0x140079e39  mov     ecx, edi
0x140079e3b  call    MpTraceLogServiceConnectFailure
0x140079e40  mov     eax, edi
0x140079e42  mov     rcx, [rsp+0A8h+var_38]
0x140079e47  xor     rcx, rsp; StackCookie
0x140079e4a  call    __security_check_cookie
0x140079e4f  lea     r11, [rsp+0A8h+var_28]
0x140079e57  mov     rbx, [r11+30h]
0x140079e5b  mov     rsi, [r11+40h]
0x140079e5f  mov     rsp, r11
0x140079e62  pop     r15
0x140079e64  pop     r14
0x140079e66  pop     r13
0x140079e68  pop     r12
0x140079e6a  pop     rdi
0x140079e6b  retn
0x14008d0b9  push    rbp
0x14008d0bb  sub     rsp, 40h
0x14008d0bf  mov     rbp, rdx
0x14008d0c2  mov     rcx, cs:MpData
0x14008d0c9  add     rcx, 2F0h; Resource
0x14008d0d0  call    cs:__imp_ExReleaseResourceLite
  ... truncated ...
```
