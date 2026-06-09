# MpCreateFileAsyncMessage

- ea: `0x140055520`
- end: `0x140055d47`
- name: `MpCreateFileAsyncMessage`
- size: `2087`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140030380`
- `0x14003a660`
- `0x1400451c0`
- `0x1400544a0`

## callees

- `0x1400018a4`
- `0x140002450`
- `0x1400026c0`
- `0x140003950`
- `0x140003af0`
- `0x140003d20`
- `0x140004030`
- `0x1400051bc`
- `0x1400118d0`
- `0x140011900`
- `0x140050b88`
- `0x140055520`
- `0x140056c20`
- `0x140068d64`
- `0x14006c3b4`

## import_xrefs

- `ntoskrnl!KeQueryPriorityThread` at `0x140055782`
- `ntoskrnl!KeQueryPriorityThread` at `0x140055782`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140055859`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140055859`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140055877`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140055877`
- `ntoskrnl!IoGetCurrentProcess` at `0x140055ae3`
- `ntoskrnl!IoGetCurrentProcess` at `0x140055ae3`
- `FLTMGR!FltGetFileNameInformation` at `0x1400555e6`
- `FLTMGR!FltGetFileNameInformation` at `0x140055acc`
- `FLTMGR!FltGetFileNameInformation` at `0x1400555e6`
- `FLTMGR!FltGetFileNameInformation` at `0x140055acc`
- `FLTMGR!FltRetrieveIoPriorityInfo` at `0x140055765`
- `FLTMGR!FltRetrieveIoPriorityInfo` at `0x140055765`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140055672`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140055672`

## pseudocode

```c
__int64 __fastcall MpCreateFileAsyncMessage(
        __int64 *a1,
        unsigned int *a2,
        unsigned int a3,
        struct _FLT_CALLBACK_DATA *a4,
        __int64 a5,
        int a6,
        int a7,
        int a8,
        __int64 a9,
        const void **a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14)
{
  char v15; // r14
  int v17; // eax
  FLT_FILE_NAME_OPTIONS v18; // edx
  __int64 v19; // rdx
  NTSTATUS v20; // ebx
  UNICODE_STRING *p_Name; // rsi
  int Length; // eax
  ULONG Size; // ebx
  unsigned int v25; // ecx
  unsigned int v26; // edi
  __int64 v27; // rcx
  int v28; // eax
  unsigned int v29; // edi
  __int64 PoolWithTag; // rax
  __int64 v31; // r12
  NTSTATUS v32; // eax
  ULONG PriorityThread; // eax
  IO_PRIORITY_HINT IoPriority; // ecx
  __int64 v35; // rdi
  PWSTR Buffer; // rdx
  __int64 v37; // rsi
  __int64 v38; // rax
  struct _FLT_CALLBACK_DATA *v39; // rcx
  int RequestorProcessId; // eax
  struct _FLT_CALLBACK_DATA *v41; // rcx
  struct _KPROCESS *RequestorProcess; // rax
  LONGLONG TimeQuadPart; // rax
  int v44; // eax
  unsigned int v45; // ecx
  int v46; // eax
  int v47; // eax
  __int64 v48; // rdx
  PETHREAD Thread; // rbx
  PEPROCESS CurrentProcess; // rax
  int v51; // eax
  NTSTATUS v52; // eax
  NTSTATUS v53; // [rsp+28h] [rbp-C1h]
  char v54; // [rsp+48h] [rbp-A1h] BYREF
  unsigned int v55; // [rsp+4Ch] [rbp-9Dh]
  unsigned int v56; // [rsp+50h] [rbp-99h]
  unsigned int v57; // [rsp+54h] [rbp-95h]
  __int64 v58; // [rsp+58h] [rbp-91h]
  const void **v59; // [rsp+60h] [rbp-89h]
  struct _FLT_CALLBACK_DATA *v60; // [rsp+68h] [rbp-81h]
  __int64 v61; // [rsp+70h] [rbp-79h]
  __int64 v62; // [rsp+78h] [rbp-71h]
  __int64 *v63; // [rsp+80h] [rbp-69h]
  unsigned int *v64; // [rsp+88h] [rbp-61h]
  __int128 v65; // [rsp+90h] [rbp-59h] BYREF
  PFLT_FILE_NAME_INFORMATION v66; // [rsp+A0h] [rbp-49h] BYREF
  struct _IO_PRIORITY_INFO FileNameInformation; // [rsp+A8h] [rbp-41h] BYREF
  int v68; // [rsp+B8h] [rbp-31h] BYREF

  v63 = a1;
  v15 = 0;
  v58 = a9;
  *a1 = 0;
  v60 = a4;
  v64 = a2;
  v59 = a10;
  v62 = a5;
  v61 = a11;
  v56 = 0;
  v55 = 0;
  v68 = 0;
  v66 = 0;
  v54 = 0;
  *a2 = 0;
  v65 = 0;
  if ( a3 == 5 || a3 == 2 )
  {
    if ( (a6 & 0x11) != 0 )
    {
      v52 = MpQueryTargetFileName((int)a4, a5, a6, a3, 0, &v66, (__int64)&v54);
      v15 = v54;
      v20 = v52;
      goto LABEL_9;
    }
    v17 = 0;
  }
  else
  {
    v17 = a6 & 0x11;
  }
  v18 = 513;
  *(_QWORD *)&FileNameInformation.Size = 0;
  if ( !byte_1400269F8 && !v17 )
    v18 = 257;
  v20 = FltGetFileNameInformation(a4, v18, (PFLT_FILE_NAME_INFORMATION *)&FileNameInformation);
  if ( v20 < 0 )
  {
    _mm_lfence();
    v20 = FltGetFileNameInformation(a4, 0x102u, (PFLT_FILE_NAME_INFORMATION *)&FileNameInformation);
  }
  else
  {
    v15 = 1;
  }
  if ( *(_QWORD *)&FileNameInformation.Size )
    v66 = *(PFLT_FILE_NAME_INFORMATION *)&FileNameInformation.Size;
LABEL_9:
  if ( v20 < 0
    || (p_Name = &v66->Name, v66 == (PFLT_FILE_NAME_INFORMATION)-8LL)
    || (Length = p_Name->Length, !(_WORD)Length) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_12;
    v48 = 64;
    v53 = v20;
    goto LABEL_48;
  }
  Size = Length + 2;
  FileNameInformation.Size = Length + 2;
  v25 = Length + 458;
  v57 = Length + 458;
  v26 = Length + 458;
  if ( a10 )
  {
    v47 = *(unsigned __int16 *)a10;
    v19 = 0;
    if ( (_WORD)v47 )
    {
      v55 = v25;
      v56 = v47 + 2;
      v26 = v47 + 2 + v25;
      v57 = v26;
    }
  }
  v27 = *(unsigned int *)(MpData + 868);
  if ( (v27 & 0x10000) != 0 )
  {
    Thread = a4->Thread;
    CurrentProcess = IoGetCurrentProcess();
    v28 = MpQuerySessionIdFromObjects(Thread, CurrentProcess, a13, &v68);
    Size = FileNameInformation.Size;
  }
  else
  {
    v28 = MpQuerySessionId(v27, v19, &v68);
  }
  if ( v28 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      65,
      WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
      KeGetCurrentThread(),
      v28);
  }
  if ( v58 )
  {
    v51 = MpQueryTransactionId(v58, &v65);
    if ( v51 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        66,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        KeGetCurrentThread(),
        v51);
    }
  }
  if ( v26 < 0x18 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
        KeGetCurrentThread());
    v20 = -1073741811;
    goto LABEL_57;
  }
  _mm_lfence();
  v29 = v26 + 24;
  PoolWithTag = MpAllocatePoolWithTag(1, v29, 1835094093);
  v31 = PoolWithTag;
  if ( !PoolWithTag )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
        KeGetCurrentThread());
    v20 = -1073741670;
LABEL_57:
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_12;
    _mm_lfence();
    v48 = 68;
    v53 = v20;
LABEL_48:
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v48,
      WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
      KeGetCurrentThread(),
      v53);
    goto LABEL_12;
  }
  *(_WORD *)PoolWithTag = 421;
  *(_DWORD *)(PoolWithTag + 4) = v29;
  FileNameInformation.Size = 16;
  *(_WORD *)(PoolWithTag + 2) = 2;
  *(_OWORD *)(PoolWithTag + 8) = 0;
  *(_QWORD *)&FileNameInformation.ThreadPriority = 0xFFFF;
  FileNameInformation.IoPriority = IoPriorityNormal;
  v32 = FltRetrieveIoPriorityInfo(0, 0, KeGetCurrentThread(), &FileNameInformation);
  if ( v32 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    _mm_lfence();
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids, (unsigned int)v32);
  }
  PriorityThread = KeQueryPriorityThread(KeGetCurrentThread());
  IoPriority = FileNameInformation.IoPriority;
  v35 = v31 + 24;
  *(_DWORD *)(v31 + 12) = PriorityThread;
  FileNameInformation.ThreadPriority = PriorityThread;
  *(_DWORD *)(v31 + 16) = FileNameInformation.PagePriority;
  *(_DWORD *)(v31 + 8) = IoPriority;
  *(_DWORD *)(v31 + 36) = 1;
  Buffer = p_Name->Buffer;
  *(_QWORD *)&FileNameInformation.Size = Size;
  memmove((void *)(v31 + 480), Buffer, Size - 2LL);
  v37 = v56;
  *(_WORD *)(v31 + 24 + 2 * (((unsigned __int64)Size + 454) >> 1)) = 0;
  *(_DWORD *)(v31 + 152) = Size;
  *(_QWORD *)(v31 + 144) = 456;
  if ( (_DWORD)v37 )
  {
    memmove((void *)(v35 + v55), v59[1], v37 - 2);
    *(_WORD *)(v35 + 2 * ((unsigned __int64)(v37 + *(_QWORD *)&FileNameInformation.Size + 454LL) >> 1)) = 0;
  }
  v38 = v55;
  v39 = v60;
  *(_DWORD *)(v31 + 136) = v37;
  *(_QWORD *)(v31 + 128) = v38;
  *(_BYTE *)(v31 + 160) = v15;
  *(_DWORD *)(v31 + 164) = a8;
  RequestorProcessId = MpGetRequestorProcessId(v39);
  v41 = v60;
  *(_DWORD *)(v31 + 52) = RequestorProcessId;
  RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(v41);
  TimeQuadPart = PsGetProcessCreateTimeQuadPart(RequestorProcess);
  *(_QWORD *)(v31 + 56) = MpFileTimeToUlong64(TimeQuadPart);
  *(_DWORD *)(v31 + 68) = v68;
  *(_DWORD *)(v31 + 64) = (unsigned int)PsGetCurrentThreadId();
  *(_OWORD *)(v31 + 72) = v65;
  if ( a3 == 3 )
  {
    v44 = MpGetFileWriteHistoryAndReset_0(v58, *(unsigned __int16 *)(v62 + 2), v61, v31 + 184);
    if ( v44 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        67,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        KeGetCurrentThread(),
        v44);
    }
  }
  else if ( a3 <= 1 )
  {
    if ( a12 )
    {
      *(_OWORD *)(v31 + 184) = *(_OWORD *)a12;
      *(_OWORD *)(v31 + 200) = *(_OWORD *)(a12 + 16);
      *(_OWORD *)(v31 + 216) = *(_OWORD *)(a12 + 32);
      *(_OWORD *)(v31 + 232) = *(_OWORD *)(a12 + 48);
      *(_OWORD *)(v31 + 248) = *(_OWORD *)(a12 + 64);
      *(_OWORD *)(v31 + 264) = *(_OWORD *)(a12 + 80);
      *(_OWORD *)(v31 + 280) = *(_OWORD *)(a12 + 96);
      *(_OWORD *)(v31 + 296) = *(_OWORD *)(a12 + 112);
      *(_OWORD *)(v31 + 312) = *(_OWORD *)(a12 + 128);
      *(_OWORD *)(v31 + 328) = *(_OWORD *)(a12 + 144);
      *(_OWORD *)(v31 + 344) = *(_OWORD *)(a12 + 160);
      *(_OWORD *)(v31 + 360) = *(_OWORD *)(a12 + 176);
      *(_OWORD *)(v31 + 376) = *(_OWORD *)(a12 + 192);
      *(_QWORD *)(v31 + 392) = *(_QWORD *)(a12 + 208);
      *(_DWORD *)(v31 + 400) = *(_DWORD *)(a12 + 216);
    }
    else
    {
      *(_BYTE *)(v31 + 184) = 0;
    }
    if ( a3 == 1 && a14 )
    {
      *(_QWORD *)(v31 + 416) = *(_QWORD *)a14;
      *(_QWORD *)(v31 + 424) = *(_QWORD *)(a14 + 8);
      *(_QWORD *)(v31 + 432) = *(_QWORD *)(a14 + 16);
      *(_QWORD *)(v31 + 440) = *(_QWORD *)(a14 + 24);
      *(_DWORD *)(v31 + 456) = *(_DWORD *)(a14 + 48);
      *(_QWORD *)(v31 + 448) = *(_QWORD *)(a14 + 40);
      *(_BYTE *)(v31 + 408) = 1;
    }
    else
    {
      *(_BYTE *)(v31 + 408) = 0;
    }
  }
  v45 = v57;
  *(_DWORD *)(v31 + 156) = a7;
  *(_DWORD *)(v31 + 176) = a6;
  *(_DWORD *)(v31 + 48) = a3;
  *(_DWORD *)(v31 + 32) = v45;
  *(_DWORD *)(v31 + 40) = 2;
  v46 = *(_DWORD *)(v31 + 472);
  if ( a13 )
  {
    *(_DWORD *)(v31 + 472) = v46 | 1;
    *(_DWORD *)(v31 + 168) = *(_DWORD *)(a13 + 56);
    *(_DWORD *)(v31 + 172) = *(_DWORD *)(a13 + 60);
  }
  else
  {
    *(_DWORD *)(v31 + 472) = v46 & 0xFFFFFFFE;
  }
  *v63 = v35;
  *v64 = v45;
  v20 = 0;
LABEL_12:
  if ( v66 )
    FltReleaseFileNameInformation(v66);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x140055520  mov     r11, rsp
0x140055523  push    rbp
0x140055524  push    rbx
0x140055525  lea     rbp, [r11-17h]
0x140055529  sub     rsp, 0E8h
0x140055530  mov     rax, cs:__security_cookie
0x140055537  xor     rax, rsp
0x14005553a  mov     [rbp+0Fh+var_38], rax
0x14005553e  mov     r10, [rbp+0Fh+arg_20]
0x140055542  mov     rax, rcx
0x140055545  mov     [r11-18h], rdi
0x140055549  xorps   xmm0, xmm0
0x14005554c  xor     edi, edi
0x14005554e  mov     [r11-20h], r12
0x140055552  mov     r12, [rbp+0Fh+arg_48]
0x140055556  mov     [r11-28h], r13
0x14005555a  mov     r13, r9
0x14005555d  mov     [rbp+0Fh+var_78], rcx
0x140055561  mov     rcx, [rbp+0Fh+arg_40]
0x140055565  mov     [r11-30h], r14
0x140055569  xor     r14b, r14b
0x14005556c  mov     [rsp+0F0h+var_A0], rcx
0x140055571  mov     rcx, [rbp+0Fh+arg_50]
0x140055575  mov     [r11-38h], r15
0x140055579  mov     r15d, r8d
0x14005557c  mov     [rax], rdi
0x14005557f  mov     [rsp+0F0h+var_90], r9
0x140055584  mov     [rbp+0Fh+var_70], rdx
0x140055588  mov     [rsp+0F0h+var_98], r12
0x14005558d  mov     [rbp+0Fh+var_80], r10
0x140055591  mov     [rbp+0Fh+var_88], rcx
0x140055595  mov     dword ptr [rsp+0F0h+var_A8], edi
0x140055599  mov     dword ptr [rsp+0F0h+var_B0+4], edi
0x14005559d  mov     [rbp+0Fh+var_40], edi
0x1400555a0  mov     [rbp+0Fh+var_58], rdi
0x1400555a4  mov     byte ptr [rsp+0F0h+var_B0], r14b
0x1400555a9  mov     [rdx], edi
0x1400555ab  movups  [rbp+0Fh+var_68], xmm0
0x1400555af  cmp     r8d, 5
0x1400555b3  jz      loc_140055938
0x1400555b9  cmp     r8d, 2
0x1400555bd  jz      loc_140055938
0x1400555c3  mov     eax, [rbp+0Fh+arg_28]
0x1400555c6  and     eax, 11h
0x1400555c9  cmp     cs:byte_1400269F8, dil
0x1400555d0  mov     edx, 201h; NameOptions
0x1400555d5  mov     [rbp+0Fh+FileNameInformation], rdi
0x1400555d9  jz      loc_140055929
0x1400555df  lea     r8, [rbp+0Fh+FileNameInformation]; FileNameInformation
0x1400555e3  mov     rcx, r13; CallbackData
0x1400555e6  call    cs:__imp_FltGetFileNameInformation
0x1400555ed  nop     dword ptr [rax+rax+00h]
0x1400555f2  mov     ebx, eax
0x1400555f4  test    eax, eax
0x1400555f6  js      loc_140055ABD
0x1400555fc  mov     r14b, 1
0x1400555ff  mov     rax, [rbp+0Fh+FileNameInformation]
0x140055603  test    rax, rax
0x140055606  jz      short loc_14005560C
0x140055608  mov     [rbp+0Fh+var_58], rax
0x14005560c  mov     [rsp+0F0h+arg_10], rsi
0x140055614  test    ebx, ebx
0x140055616  js      short loc_140055622
0x140055618  mov     rsi, [rbp+0Fh+var_58]
0x14005561c  add     rsi, 8
0x140055620  jnz     short loc_140055697
0x140055622  mov     rax, cs:WPP_GLOBAL_Control
0x140055629  lea     r13, WPP_GLOBAL_Control
0x140055630  cmp     rax, r13
0x140055633  jnz     loc_140055A84
0x140055639  mov     rcx, [rbp+0Fh+var_58]; FileNameInformation
0x14005563d  mov     r15, [rsp+0F0h+var_30]
0x140055645  mov     r14, [rsp+0F0h+var_28]
0x14005564d  mov     r13, [rsp+0F0h+var_20]
0x140055655  mov     r12, [rsp+0F0h+var_18]
0x14005565d  mov     rdi, [rsp+0E0h]
0x140055665  mov     rsi, [rsp+0F0h+arg_10]
0x14005566d  test    rcx, rcx
0x140055670  jz      short loc_14005567E
0x140055672  call    cs:__imp_FltReleaseFileNameInformation
0x140055679  nop     dword ptr [rax+rax+00h]
0x14005567e  mov     eax, ebx
0x140055680  mov     rcx, [rbp+0Fh+var_38]
0x140055684  xor     rcx, rsp; StackCookie
0x140055687  call    __security_check_cookie
0x14005568c  add     rsp, 0E8h
0x140055693  pop     rbx
0x140055694  pop     rbp
0x140055695  retn
0x140055697  movzx   eax, word ptr [rsi]
0x14005569a  cmp     di, ax
0x14005569d  jz      short loc_140055622
0x14005569f  lea     ebx, [rax+2]
0x1400556a2  mov     dword ptr [rbp+0Fh+FileNameInformation], ebx
0x1400556a5  lea     ecx, [rbx+1C8h]
0x1400556ab  mov     dword ptr [rsp+0F0h+var_A8+4], ecx
0x1400556af  mov     edi, ecx
0x1400556b1  test    r12, r12
0x1400556b4  jnz     loc_140055A45
0x1400556ba  mov     rax, cs:MpData
0x1400556c1  mov     ecx, [rax+364h]
0x1400556c7  bt      ecx, 10h
0x1400556cb  jb      loc_140055ADF
0x1400556d1  lea     r8, [rbp+0Fh+var_40]
0x1400556d5  call    MpQuerySessionId
0x1400556da  lea     r13, WPP_GLOBAL_Control
0x1400556e1  mov     ecx, eax
0x1400556e3  test    eax, eax
0x1400556e5  js      loc_140055BE4
0x1400556eb  mov     rax, [rsp+0F0h+var_A0]
0x1400556f0  test    rax, rax
0x1400556f3  jnz     loc_140055B0A
0x1400556f9  cmp     edi, 18h
0x1400556fc  jb      loc_140055B6B
0x140055702  lfence
0x140055705  add     edi, 18h
0x140055708  mov     ecx, 1
0x14005570d  mov     edx, edi
0x14005570f  mov     r8d, 6D61504Dh
0x140055715  call    MpAllocatePoolWithTag
0x14005571a  mov     r12, rax
0x14005571d  test    rax, rax
0x140055720  jz      loc_140055C30
0x140055726  mov     word ptr [rax], 1A5h
0x14005572b  lea     r9, [rbp+0Fh+FileNameInformation]; PriorityInfo
0x14005572f  mov     [rax+4], edi
0x140055732  xorps   xmm0, xmm0
0x140055735  mov     eax, 2
0x14005573a  mov     dword ptr [rbp+0Fh+FileNameInformation], 10h
0x140055741  mov     [r12+2], ax
0x140055747  xor     edx, edx; FileObject
0x140055749  movups  xmmword ptr [r12+8], xmm0
0x14005574f  mov     [rbp+0Fh+FileNameInformation+4], 0FFFFh
0x140055757  xor     ecx, ecx; Data
0x140055759  mov     [rbp+0Fh+var_44], eax
0x14005575c  mov     r8, gs:188h; Thread
0x140055765  call    cs:__imp_FltRetrieveIoPriorityInfo
0x14005576c  nop     dword ptr [rax+rax+00h]
0x140055771  test    eax, eax
0x140055773  js      loc_140055C72
0x140055779  mov     rcx, gs:188h; Thread
0x140055782  call    cs:__imp_KeQueryPriorityThread
0x140055789  nop     dword ptr [rax+rax+00h]
0x14005578e  mov     ecx, [rbp+0Fh+var_44]
0x140055791  lea     rdi, [r12+18h]
0x140055796  mov     [r12+0Ch], eax
0x14005579b  mov     dword ptr [rbp+0Fh+FileNameInformation+4], eax
0x14005579e  mov     eax, [rbp+0Fh+var_48]
0x1400557a1  mov     [r12+10h], eax
0x1400557a6  mov     [r12+8], ecx
0x1400557ab  lea     rcx, [rdi+1C8h]; void *
0x1400557b2  mov     eax, ebx
0x1400557b4  mov     dword ptr [r12+24h], 1
0x1400557bd  mov     rdx, [rsi+8]; Src
0x1400557c1  mov     [rbp+0Fh+FileNameInformation], rax
0x1400557c5  lea     r8, [rax-2]; Size
0x1400557c9  call    memmove
0x1400557ce  mov     esi, dword ptr [rsp+0F0h+var_A8]
0x1400557d2  xor     edx, edx
0x1400557d4  mov     eax, ebx
0x1400557d6  add     rax, 1C6h
0x1400557dc  shr     rax, 1
0x1400557df  mov     [rdi+rax*2], dx
0x1400557e3  mov     [rdi+80h], ebx
0x1400557e9  mov     qword ptr [rdi+78h], 1C8h
0x1400557f1  test    esi, esi
0x1400557f3  jz      short loc_140055824
0x1400557f5  mov     rdx, [rsp+0F0h+var_98]
0x1400557fa  lea     r8, [rsi-2]; Size
0x1400557fe  mov     ecx, dword ptr [rsp+0F0h+var_B0+4]
0x140055802  add     rcx, rdi; void *
0x140055805  mov     rdx, [rdx+8]; Src
0x140055809  call    memmove
0x14005580e  mov     rax, [rbp+0Fh+FileNameInformation]
0x140055812  add     rax, 1C6h
0x140055818  add     rax, rsi
0x14005581b  shr     rax, 1
0x14005581e  xor     ecx, ecx
0x140055820  mov     [rdi+rax*2], cx
0x140055824  mov     eax, dword ptr [rsp+0F0h+var_B0+4]
0x140055828  mov     rcx, [rsp+0F0h+var_90]
0x14005582d  mov     [rdi+70h], esi
0x140055830  mov     [rdi+68h], rax
0x140055834  mov     eax, [rbp+0Fh+arg_38]
0x140055837  mov     [rdi+88h], r14b
0x14005583e  mov     [rdi+8Ch], eax
0x140055844  call    MpGetRequestorProcessId
0x140055849  mov     rcx, [rsp+0F0h+var_90]
0x14005584e  mov     [rdi+1Ch], eax
0x140055851  call    MpGetRequestorProcess
0x140055856  mov     rcx, rax; Process
0x140055859  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x140055860  nop     dword ptr [rax+rax+00h]
0x140055865  mov     rcx, rax
0x140055868  call    MpFileTimeToUlong64
0x14005586d  mov     [rdi+20h], rax
0x140055871  mov     eax, [rbp+0Fh+var_40]
0x140055874  mov     [rdi+2Ch], eax
0x140055877  call    cs:__imp_PsGetCurrentThreadId
0x14005587e  nop     dword ptr [rax+rax+00h]
0x140055883  mov     [rdi+28h], eax
0x140055886  movups  xmm0, [rbp+0Fh+var_68]
0x14005588a  movups  xmmword ptr [rdi+30h], xmm0
0x14005588e  cmp     r15d, 3
0x140055892  jnz     loc_14005594D
0x140055898  mov     rdx, [rbp+0Fh+var_80]
0x14005589c  lea     r9, [rdi+0A0h]
0x1400558a3  mov     r8, [rbp+0Fh+var_88]
0x1400558a7  mov     rcx, [rsp+0F0h+var_A0]
0x1400558ac  movzx   edx, word ptr [rdx+2]
0x1400558b0  call    MpGetFileWriteHistoryAndReset_0
0x1400558b5  test    eax, eax
0x1400558b7  js      loc_140055CB5
0x1400558bd  mov     eax, [rbp+0Fh+arg_30]
0x1400558c0  mov     ecx, dword ptr [rsp+0F0h+var_A8+4]
0x1400558c4  mov     rdx, [rbp+0Fh+arg_60]
0x1400558c8  mov     [rdi+84h], eax
0x1400558ce  mov     eax, [rbp+0Fh+arg_28]
0x1400558d1  mov     [rdi+98h], eax
0x1400558d7  mov     [rdi+18h], r15d
0x1400558db  mov     [rdi+8], ecx
0x1400558de  mov     dword ptr [rdi+10h], 2
0x1400558e5  mov     eax, [r12+1D8h]
0x1400558ed  test    rdx, rdx
0x1400558f0  jz      loc_140055D02
0x1400558f6  or      eax, 1
0x1400558f9  mov     [r12+1D8h], eax
0x140055901  mov     eax, [rdx+38h]
0x140055904  mov     [rdi+90h], eax
0x14005590a  mov     eax, [rdx+3Ch]
0x14005590d  mov     [rdi+94h], eax
0x140055913  mov     rax, [rbp+0Fh+var_78]
0x140055917  mov     [rax], rdi
0x14005591a  mov     rax, [rbp+0Fh+var_70]
0x14005591e  mov     [rax], ecx
0x140055920  xor     eax, eax
0x140055922  mov     ebx, eax
0x140055924  jmp     loc_140055639
0x140055929  test    eax, eax
0x14005592b  mov     ecx, 101h
0x140055930  cmovz   edx, ecx
0x140055933  jmp     loc_1400555DF
0x140055938  mov     ecx, [rbp+0Fh+arg_28]
0x14005593b  mov     eax, ecx
0x14005593d  and     eax, 11h
0x140055940  jnz     loc_140055BAE
0x140055946  mov     eax, edi
0x140055948  jmp     loc_1400555C9
0x14005594d  cmp     r15d, 1
0x140055951  ja      loc_1400558BD
0x140055957  mov     rdx, [rbp+0Fh+arg_58]
0x14005595b  test    rdx, rdx
0x14005595e  jz      loc_140055A78
0x140055964  movups  xmm0, xmmword ptr [rdx]
0x140055967  lea     rcx, [rdi+0A0h]
0x14005596e  movups  xmmword ptr [rcx], xmm0
0x140055971  lea     rcx, [rcx+80h]
0x140055978  movups  xmm1, xmmword ptr [rdx+10h]
0x14005597c  movups  xmmword ptr [rcx-70h], xmm1
0x140055980  movups  xmm0, xmmword ptr [rdx+20h]
0x140055984  movups  xmmword ptr [rcx-60h], xmm0
0x140055988  movups  xmm1, xmmword ptr [rdx+30h]
0x14005598c  movups  xmmword ptr [rcx-50h], xmm1
0x140055990  movups  xmm0, xmmword ptr [rdx+40h]
0x140055994  movups  xmmword ptr [rcx-40h], xmm0
0x140055998  movups  xmm1, xmmword ptr [rdx+50h]
0x14005599c  movups  xmmword ptr [rcx-30h], xmm1
0x1400559a0  movups  xmm0, xmmword ptr [rdx+60h]
0x1400559a4  movups  xmmword ptr [rcx-20h], xmm0
0x1400559a8  movups  xmm0, xmmword ptr [rdx+70h]
0x1400559ac  sub     rdx, 0FFFFFFFFFFFFFF80h
0x1400559b0  movups  xmmword ptr [rcx-10h], xmm0
0x1400559b4  movups  xmm1, xmmword ptr [rdx]
0x1400559b7  movups  xmmword ptr [rcx], xmm1
0x1400559ba  movups  xmm0, xmmword ptr [rdx+10h]
0x1400559be  movups  xmmword ptr [rcx+10h], xmm0
0x1400559c2  movups  xmm1, xmmword ptr [rdx+20h]
0x1400559c6  movups  xmmword ptr [rcx+20h], xmm1
0x1400559ca  movups  xmm0, xmmword ptr [rdx+30h]
0x1400559ce  movups  xmmword ptr [rcx+30h], xmm0
0x1400559d2  movups  xmm1, xmmword ptr [rdx+40h]
0x1400559d6  movups  xmmword ptr [rcx+40h], xmm1
0x1400559da  mov     rax, [rdx+50h]
0x1400559de  mov     [rcx+50h], rax
0x1400559e2  mov     eax, [rdx+58h]
0x1400559e5  mov     [rcx+58h], eax
0x1400559e8  cmp     r15d, 1
0x1400559ec  jnz     short loc_140055A6C
0x1400559ee  mov     rcx, [rbp+0Fh+arg_68]
0x1400559f5  test    rcx, rcx
0x1400559f8  jz      short loc_140055A6C
0x1400559fa  mov     rax, [rcx]
0x1400559fd  mov     [rdi+188h], rax
0x140055a04  mov     rax, [rcx+8]
0x140055a08  mov     [rdi+190h], rax
0x140055a0f  mov     rax, [rcx+10h]
0x140055a13  mov     [rdi+198h], rax
0x140055a1a  mov     rax, [rcx+18h]
0x140055a1e  mov     [rdi+1A0h], rax
0x140055a25  mov     eax, [rcx+30h]
  ... truncated ...
```
