# MpDlpPostCreate

- ea: `0x14003fe70`
- end: `0x140040385`
- name: `MpDlpPostCreate`
- size: `1301`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14002e850`

## callees

- `0x140002450`
- `0x1400051bc`
- `0x140007098`
- `0x1400118d0`
- `0x14003fe70`
- `0x140040388`
- `0x140040680`
- `0x1400408b0`
- `0x140042be0`
- `0x14006e7d0`
- `0x1400762f4`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x1400400d1`
- `ntoskrnl!ExGetPreviousMode` at `0x1400400d1`
- `ntoskrnl!PsInitialSystemProcess` at `0x1400400e8`
- `FLTMGR!FltReleaseContext` at `0x14004020d`
- `FLTMGR!FltReleaseContext` at `0x14004020d`
- `FLTMGR!FltCancelFileOpen` at `0x140040069`
- `FLTMGR!FltCancelFileOpen` at `0x140040069`
- `FLTMGR!FltIsDirectory` at `0x14003ff11`
- `FLTMGR!FltIsDirectory` at `0x14003ff11`
- `FLTMGR!FltGetInstanceContext` at `0x1400401f2`
- `FLTMGR!FltGetInstanceContext` at `0x1400401f2`

## string_xrefs

- `0x140040040`: `[DLP-filter] Denied Process '%wZ' (pid = %#x) from opening file '%wZ' for write on %ws. reason: %d`
- `0x1400400a5`: `[DLP-filter] Denied access to sensitive file '%wZ' for Process '%wZ' (pid = %#x), reason: %d`

## pseudocode

```c
void __fastcall MpDlpPostCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3, __int64 *a4, __int64 a5)
{
  int v5; // r12d
  int v6; // r13d
  bool v7; // r15
  __int64 v12; // rbx
  int v13; // ecx
  __int64 v14; // rax
  PFLT_CONTEXT v15; // rdx
  int v16; // eax
  const wchar_t *v17; // rcx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  __int64 v19; // rcx
  struct _FLT_INSTANCE *v20; // rcx
  NTSTATUS InstanceContext; // ecx
  int v22; // eax
  int FileNameInformation; // [rsp+20h] [rbp-A8h]
  PFLT_FILE_NAME_INFORMATION FileNameInformationa; // [rsp+20h] [rbp-A8h]
  int FileNameInformationb; // [rsp+20h] [rbp-A8h]
  __int64 v26; // [rsp+28h] [rbp-A0h]
  size_t Size; // [rsp+38h] [rbp-90h]
  __int64 v28; // [rsp+58h] [rbp-70h]
  PFLT_CONTEXT Context; // [rsp+60h] [rbp-68h] BYREF
  unsigned __int8 v30[4]; // [rsp+68h] [rbp-60h] BYREF
  _DWORD v31[7]; // [rsp+6Ch] [rbp-5Ch] BYREF

  v5 = 0;
  v6 = 0;
  v7 = 0;
  v31[0] = 0;
  v30[0] = 0;
  if ( !CallbackData || !a2 || !a3 || !a4 || CallbackData->IoStatus.Status < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        110,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        KeGetCurrentThread(),
        -1073741811);
    return;
  }
  v12 = *a4;
  v28 = *a4;
  if ( (*a4 & 0x101) != 0 )
    return;
  FltIsDirectory(*(PFILE_OBJECT *)(a2 + 32), *(PFLT_INSTANCE *)(a2 + 24), v30);
  if ( v30[0] )
    return;
  if ( a5 )
  {
    v5 = *(_DWORD *)(*(_QWORD *)(a5 + 8) + 84LL);
  }
  else
  {
    v20 = *(struct _FLT_INSTANCE **)(a2 + 24);
    Context = 0;
    InstanceContext = FltGetInstanceContext(v20, &Context);
    if ( InstanceContext < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          111,
          WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
          KeGetCurrentThread(),
          InstanceContext);
      }
    }
    else
    {
      v5 = *((_DWORD *)Context + 21);
      FltReleaseContext(Context);
    }
  }
  v13 = MpCheckLoopbackOnPostCreate(CallbackData);
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        112,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        KeGetCurrentThread(),
        v13);
    }
    return;
  }
  v14 = a4[1];
  v15 = (PFLT_CONTEXT)(v12 & 0x200);
  Context = v15;
  if ( (v12 & 0x200) != 0 || v14 )
  {
    if ( (v5 & 0x10) == 0
      && !ExGetPreviousMode()
      && (_mm_lfence(), (PEPROCESS)MpGetRequestorProcess(CallbackData) == PsInitialSystemProcess)
      && (_mm_lfence(), Iopb = CallbackData->Iopb, (Iopb->OperationFlags & 1) != 0)
      && (v19 = *(_QWORD *)(Iopb->Parameters.WMI.ProviderId + 8), *(_QWORD *)(v19 + 32))
      && *(int *)(v19 + 40) >= 2 )
    {
      if ( (v28 & 0x2000) != 0 || (*(_DWORD *)(MpData + 864) & 0x4000) != 0 )
      {
        v15 = Context;
        goto LABEL_16;
      }
      _mm_lfence();
      v16 = MpDlpAtomicCheckFileAndOperationAccess(CallbackData, FileNameInformation, (__int64)a4, (__int64)v31);
    }
    else
    {
      _mm_lfence();
      LODWORD(Size) = 0;
      v16 = MpDlpCheckFileAccess(CallbackData, a2, a3, v5, a5, 0, (__int64)a4, Size, 0, (__int64)v31);
    }
    v6 = v16;
    if ( v16 == 2 )
    {
      _mm_lfence();
      LODWORD(FileNameInformationa) = v31[0];
      MpLogPrintfW(
        L"[DLP-filter] Denied access to sensitive file '%wZ' for Process '%wZ' (pid = %#x), reason: %d",
        &CallbackData->Iopb->TargetFileObject->FileName,
        *(_QWORD *)(a3 + 128),
        *(unsigned int *)(a3 + 24),
        FileNameInformationa);
LABEL_21:
      MpDlpBlockActionToNtStatus(a3, v31, &CallbackData->IoStatus);
      CallbackData->IoStatus.Information = 0;
      FltCancelFileOpen(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
      return;
    }
    v15 = Context;
    v7 = v16 == 1;
  }
LABEL_16:
  _mm_lfence();
  if ( (*(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16) & 0x2000006) == 0 || v7 || v15 )
    goto LABEL_17;
  if ( (v5 & 0x10) != 0 )
  {
    FileNameInformationb = 1;
    goto LABEL_39;
  }
  if ( (v5 & 0x800) != 0 )
  {
    FileNameInformationb = 0;
LABEL_39:
    _mm_lfence();
    v6 = MpDlpCheckOperation(CallbackData, FileNameInformationb, 0, (__int64)v31);
  }
LABEL_17:
  if ( v6 == 2 )
  {
    _mm_lfence();
    v17 = L"remote/external device";
    if ( (v5 & 0x10) == 0 )
      v17 = L"spooler file";
    LODWORD(v26) = v31[0];
    MpLogPrintfW(
      L"[DLP-filter] Denied Process '%wZ' (pid = %#x) from opening file '%wZ' for write on %ws. reason: %d",
      *(_QWORD *)(a3 + 128),
      *(unsigned int *)(a3 + 24),
      &CallbackData->Iopb->TargetFileObject->FileName,
      v17,
      v26);
    goto LABEL_21;
  }
  if ( (v5 & 0x10) != 0 )
  {
    v22 = 4;
    goto LABEL_46;
  }
  if ( (v5 & 0x800) != 0 )
  {
    v22 = 2;
LABEL_46:
    _mm_lfence();
    MpDlpSetProcessEntryFlags(CallbackData, 0, v5, v22);
  }
}

```

## disassembly

```asm
0x14003fe70  mov     r11, rsp
0x14003fe73  push    rbp
0x14003fe74  push    rsi
0x14003fe75  push    rdi
0x14003fe76  push    r12
0x14003fe78  push    r13
0x14003fe7a  push    r14
0x14003fe7c  push    r15
0x14003fe7e  sub     rsp, 90h
0x14003fe85  mov     rax, cs:__security_cookie
0x14003fe8c  xor     rax, rsp
0x14003fe8f  mov     qword ptr [rsp+0C8h+var_5C+4], rax
0x14003fe94  mov     rax, [rsp+0C8h+arg_20]
0x14003fe9c  xor     r12d, r12d
0x14003fe9f  xor     r13d, r13d
0x14003fea2  mov     [rsp+0C8h+var_78], rax
0x14003fea7  xor     r15b, r15b
0x14003feaa  mov     [r11-5Ch], r12d
0x14003feae  mov     [r11-60h], r12b
0x14003feb2  mov     r14, r9
0x14003feb5  mov     rbp, r8
0x14003feb8  mov     rdi, rdx
0x14003febb  mov     rsi, rcx
0x14003febe  test    rcx, rcx
0x14003fec1  jz      loc_140040331
0x14003fec7  test    rdx, rdx
0x14003feca  jz      loc_140040331
0x14003fed0  test    r8, r8
0x14003fed3  jz      loc_140040331
0x14003fed9  test    r9, r9
0x14003fedc  jz      loc_140040331
0x14003fee2  cmp     [rcx+18h], r12d
0x14003fee6  jl      loc_140040331
0x14003feec  mov     [r11-40h], rbx
0x14003fef0  mov     rbx, [r9]
0x14003fef3  mov     [rsp+0C8h+var_70], rbx
0x14003fef8  test    rbx, 101h
0x14003feff  jnz     loc_140040075
0x14003ff05  mov     rdx, [rdx+18h]; Instance
0x14003ff09  lea     r8, [r11-60h]; IsDirectory
0x14003ff0d  mov     rcx, [rdi+20h]; FileObject
0x14003ff11  call    cs:__imp_FltIsDirectory
0x14003ff18  nop     dword ptr [rax+rax+00h]
0x14003ff1d  cmp     [rsp+0C8h+var_60], r12b
0x14003ff22  jnz     loc_140040075
0x14003ff28  mov     rax, [rsp+0C8h+var_78]
0x14003ff2d  test    rax, rax
0x14003ff30  jz      loc_1400401E4
0x14003ff36  mov     rax, [rax+8]
0x14003ff3a  mov     r12d, [rax+54h]
0x14003ff3e  mov     r8, r14
0x14003ff41  mov     rdx, rdi
0x14003ff44  mov     rcx, rsi; CallbackData
0x14003ff47  call    MpCheckLoopbackOnPostCreate
0x14003ff4c  mov     ecx, eax
0x14003ff4e  test    eax, eax
0x14003ff50  js      loc_1400402B3
0x14003ff56  mov     rax, [r14+8]
0x14003ff5a  mov     rdx, rbx
0x14003ff5d  and     edx, 200h
0x14003ff63  mov     r8d, 1
0x14003ff69  mov     [rsp+0C8h+Context], rdx
0x14003ff6e  jz      loc_140040180
0x14003ff74  test    r12b, 10h
0x14003ff78  jz      loc_1400400D1
0x14003ff7e  lfence
0x14003ff81  xor     ebx, ebx
0x14003ff83  lea     rax, [rsp+0C8h+var_5C]
0x14003ff88  mov     [rsp+0C8h+var_80], rax; __int64
0x14003ff8d  mov     r9d, r12d
0x14003ff90  mov     rax, [rsp+0C8h+var_78]
0x14003ff95  mov     r8, rbp
0x14003ff98  mov     [rsp+0C8h+var_88], rbx; __int64
0x14003ff9d  mov     rdx, rdi
0x14003ffa0  mov     dword ptr [rsp+0C8h+Size], ebx; Size
0x14003ffa4  mov     rcx, rsi; CallbackData
0x14003ffa7  mov     [rsp+0C8h+var_98], r14; __int64
0x14003ffac  mov     [rsp+0C8h+var_A0], rbx; __int64
0x14003ffb1  mov     [rsp+0C8h+FileNameInformation], rax; __int64
0x14003ffb6  call    MpDlpCheckFileAccess
0x14003ffbb  mov     r13d, eax
0x14003ffbe  cmp     eax, 2
0x14003ffc1  jz      loc_14004009E
0x14003ffc7  mov     rdx, [rsp+0C8h+Context]
0x14003ffcc  cmp     eax, 1
0x14003ffcf  movzx   r15d, r15b
0x14003ffd3  mov     r8d, 1
0x14003ffd9  cmovz   r15d, r8d
0x14003ffdd  lfence
0x14003ffe0  mov     rax, [rsi+10h]
0x14003ffe4  mov     rcx, [rax+18h]
0x14003ffe8  test    dword ptr [rcx+10h], 2000006h
0x14003ffef  jnz     loc_14004018E
0x14003fff5  mov     eax, r12d
0x14003fff8  and     eax, 10h
0x14003fffb  cmp     r13d, 2
0x14003ffff  jnz     loc_14004021E
0x140040005  lfence
0x140040008  mov     r8d, [rbp+18h]
0x14004000c  lea     rdx, aSpoolerFile; "spooler file"
0x140040013  test    eax, eax
0x140040015  lea     rcx, aRemoteExternal; "remote/external device"
0x14004001c  mov     rax, [rsi+10h]
0x140040020  cmovz   rcx, rdx
0x140040024  mov     rdx, [rbp+80h]
0x14004002b  mov     r9, [rax+8]
0x14004002f  mov     eax, [rsp+0C8h+var_5C]
0x140040033  add     r9, 58h ; 'X'
0x140040037  mov     dword ptr [rsp+0C8h+var_A0], eax
0x14004003b  mov     [rsp+0C8h+FileNameInformation], rcx
0x140040040  lea     rcx, aDlpFilterDenie_0; "[DLP-filter] Denied Process '%wZ' (pid "...
0x140040047  call    MpLogPrintfW
0x14004004c  lea     r8, [rsi+18h]
0x140040050  mov     rcx, rbp
0x140040053  lea     rdx, [rsp+0C8h+var_5C]
0x140040058  call    MpDlpBlockActionToNtStatus
0x14004005d  mov     [rsi+20h], rbx
0x140040061  mov     rdx, [rdi+20h]; FileObject
0x140040065  mov     rcx, [rdi+18h]; Instance
0x140040069  call    cs:__imp_FltCancelFileOpen
0x140040070  nop     dword ptr [rax+rax+00h]
0x140040075  mov     rbx, [rsp+0C8h+var_40]
0x14004007d  mov     rcx, qword ptr [rsp+0C8h+var_5C+4]
0x140040082  xor     rcx, rsp; StackCookie
0x140040085  call    __security_check_cookie
0x14004008a  add     rsp, 90h
0x140040091  pop     r15
0x140040093  pop     r14
0x140040095  pop     r13
0x140040097  pop     r12
0x140040099  pop     rdi
0x14004009a  pop     rsi
0x14004009b  pop     rbp
0x14004009c  retn
0x14004009e  lfence
0x1400400a1  mov     rax, [rsi+10h]
0x1400400a5  lea     rcx, aDlpFilterDenie; "[DLP-filter] Denied access to sensitive"...
0x1400400ac  mov     r9d, [rbp+18h]
0x1400400b0  mov     r8, [rbp+80h]
0x1400400b7  mov     rdx, [rax+8]
0x1400400bb  mov     eax, [rsp+0C8h+var_5C]
0x1400400bf  add     rdx, 58h ; 'X'
0x1400400c3  mov     dword ptr [rsp+0C8h+FileNameInformation], eax
0x1400400c7  call    MpLogPrintfW
0x1400400cc  jmp     loc_14004004C
0x1400400d1  call    cs:__imp_ExGetPreviousMode
0x1400400d8  nop     dword ptr [rax+rax+00h]
0x1400400dd  test    al, al
0x1400400df  jnz     loc_14003FF7E
0x1400400e5  lfence
0x1400400e8  mov     rax, cs:__imp_PsInitialSystemProcess
0x1400400ef  mov     rcx, rsi
0x1400400f2  mov     rbx, [rax]
0x1400400f5  call    MpGetRequestorProcess
0x1400400fa  cmp     rax, rbx
0x1400400fd  jnz     loc_14003FF7E
0x140040103  lfence
0x140040106  mov     rcx, [rsi+10h]
0x14004010a  test    byte ptr [rcx+6], 1
0x14004010e  jz      loc_14003FF7E
0x140040114  mov     rax, [rcx+18h]
0x140040118  mov     rcx, [rax+8]
0x14004011c  cmp     [rcx+20h], r13
0x140040120  jz      loc_14003FF7E
0x140040126  cmp     dword ptr [rcx+28h], 2
0x14004012a  jl      loc_14003FF7E
0x140040130  test    [rsp+0C8h+var_70], 2000h
0x140040139  jnz     loc_140040306
0x14004013f  mov     rax, cs:MpData
0x140040146  test    dword ptr [rax+360h], 4000h
0x140040150  jnz     loc_140040306
0x140040156  lfence
0x140040159  lea     rax, [rsp+0C8h+var_5C]
0x14004015e  mov     r9d, r12d
0x140040161  mov     [rsp+0C8h+var_98], rax; __int64
0x140040166  mov     r8, rbp
0x140040169  mov     rdx, rdi
0x14004016c  mov     [rsp+0C8h+var_A0], r14; __int64
0x140040171  mov     rcx, rsi; CallbackData
0x140040174  call    MpDlpAtomicCheckFileAndOperationAccess
0x140040179  xor     ebx, ebx
0x14004017b  jmp     loc_14003FFBB
0x140040180  test    rax, rax
0x140040183  jnz     loc_14003FF74
0x140040189  jmp     loc_140040311
0x14004018e  test    r15b, r15b
0x140040191  jnz     loc_14003FFF5
0x140040197  test    rdx, rdx
0x14004019a  jnz     loc_14003FFF5
0x1400401a0  test    r12b, 10h
0x1400401a4  jnz     loc_140040318
0x1400401aa  bt      r12d, 0Bh
0x1400401af  jnb     loc_14003FFF5
0x1400401b5  lea     rax, [rsp+0C8h+var_5C]
0x1400401ba  mov     [rsp+0C8h+var_98], rax; __int64
0x1400401bf  mov     [rsp+0C8h+var_A0], rbx; __int64
0x1400401c4  mov     dword ptr [rsp+0C8h+FileNameInformation], ebx; int
0x1400401c8  lfence
0x1400401cb  mov     r9d, r12d
0x1400401ce  mov     r8, rbp
0x1400401d1  mov     rdx, rdi
0x1400401d4  mov     rcx, rsi; CallbackData
0x1400401d7  call    MpDlpCheckOperation
0x1400401dc  mov     r13d, eax
0x1400401df  jmp     loc_14003FFF5
0x1400401e4  mov     rcx, [rdi+18h]; Instance
0x1400401e8  lea     rdx, [rsp+0C8h+Context]; Context
0x1400401ed  mov     [rsp+0C8h+Context], r12
0x1400401f2  call    cs:__imp_FltGetInstanceContext
0x1400401f9  nop     dword ptr [rax+rax+00h]
0x1400401fe  mov     ecx, eax
0x140040200  test    eax, eax
0x140040202  js      short loc_140040260
0x140040204  mov     rcx, [rsp+0C8h+Context]; Context
0x140040209  mov     r12d, [rcx+54h]
0x14004020d  call    cs:__imp_FltReleaseContext
0x140040214  nop     dword ptr [rax+rax+00h]
0x140040219  jmp     loc_14003FF3E
0x14004021e  test    eax, eax
0x140040220  jnz     short loc_140040234
0x140040222  bt      r12d, 0Bh
0x140040227  jnb     loc_140040075
0x14004022d  mov     eax, 2
0x140040232  jmp     short loc_140040239
0x140040234  mov     eax, 4
0x140040239  lfence
0x14004023c  mov     dword ptr [rsp+0C8h+var_98], eax; int
0x140040240  xor     r9d, r9d
0x140040243  mov     dword ptr [rsp+0C8h+var_A0], r12d; int
0x140040248  mov     r8, rbp
0x14004024b  mov     rdx, rdi
0x14004024e  mov     [rsp+0C8h+FileNameInformation], rbx; FileNameInformation
0x140040253  mov     rcx, rsi; CallbackData
0x140040256  call    MpDlpSetProcessEntryFlags
0x14004025b  jmp     loc_140040075
0x140040260  mov     rdx, cs:WPP_GLOBAL_Control
0x140040267  lea     rax, WPP_GLOBAL_Control
0x14004026e  cmp     rdx, rax
0x140040271  jz      loc_14003FF3E
0x140040277  mov     eax, [rdx+2Ch]
0x14004027a  test    al, 1
0x14004027c  jz      loc_14003FF3E
0x140040282  lfence
0x140040285  mov     r9, gs:188h
0x14004028e  lea     r8, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids
0x140040295  mov     dword ptr [rsp+0C8h+FileNameInformation], ecx
0x140040299  mov     edx, 6Fh ; 'o'
0x14004029e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400402a5  mov     rcx, [rcx+18h]
0x1400402a9  call    WPP_SF_qD
0x1400402ae  jmp     loc_14003FF3E
0x1400402b3  mov     rdx, cs:WPP_GLOBAL_Control
0x1400402ba  lea     rax, WPP_GLOBAL_Control
0x1400402c1  cmp     rdx, rax
0x1400402c4  jz      loc_140040075
0x1400402ca  mov     eax, [rdx+2Ch]
0x1400402cd  test    al, 1
0x1400402cf  jz      loc_140040075
0x1400402d5  lfence
0x1400402d8  mov     r9, gs:188h
0x1400402e1  lea     r8, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids
0x1400402e8  mov     dword ptr [rsp+0C8h+FileNameInformation], ecx
0x1400402ec  mov     edx, 70h ; 'p'
0x1400402f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400402f8  mov     rcx, [rcx+18h]
0x1400402fc  call    WPP_SF_qD
0x140040301  jmp     loc_140040075
0x140040306  mov     rdx, [rsp+0C8h+Context]
0x14004030b  mov     r8d, 1
0x140040311  xor     ebx, ebx
0x140040313  jmp     loc_14003FFDD
0x140040318  lea     rax, [rsp+0C8h+var_5C]
0x14004031d  mov     [rsp+0C8h+var_98], rax
0x140040322  mov     [rsp+0C8h+var_A0], rbx
0x140040327  mov     dword ptr [rsp+0C8h+FileNameInformation], r8d
0x14004032c  jmp     loc_1400401C8
0x140040331  mov     rcx, cs:WPP_GLOBAL_Control
0x140040338  lea     rax, WPP_GLOBAL_Control
0x14004033f  cmp     rcx, rax
0x140040342  jz      loc_14004007D
0x140040348  mov     eax, [rcx+2Ch]
0x14004034b  test    al, 1
0x14004034d  jz      loc_14004007D
0x140040353  mov     r9, gs:188h
0x14004035c  lea     r8, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids
0x140040363  mov     rcx, cs:WPP_GLOBAL_Control
0x14004036a  mov     edx, 6Eh ; 'n'
0x14004036f  mov     dword ptr [rsp+0C8h+FileNameInformation], 0C000000Dh
0x140040377  mov     rcx, [rcx+18h]
0x14004037b  call    WPP_SF_qD
0x140040380  jmp     loc_14004007D
```
