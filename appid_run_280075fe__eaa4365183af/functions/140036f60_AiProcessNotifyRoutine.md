# AiProcessNotifyRoutine

- ea: `0x140036f60`
- end: `0x14003739c`
- name: `AiProcessNotifyRoutine`
- size: `1084`
- prototype: `void __stdcall(PEPROCESS Process, HANDLE ProcessId, PPS_CREATE_NOTIFY_INFO CreateInfo)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x140001550`
- `0x140001590`
- `0x1400016a8`
- `0x140001a00`
- `0x140002118`
- `0x140006a20`
- `0x14001f3c0`
- `0x140027d28`
- `0x140036f60`
- `0x1400373b0`

## import_xrefs

- `ntoskrnl!SeLocateProcessImageName` at `0x140037042`
- `ntoskrnl!SeLocateProcessImageName` at `0x140037042`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037376`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037376`
- `ntoskrnl!EtwWriteTransfer` at `0x1400371df`
- `ntoskrnl!EtwWriteTransfer` at `0x1400372ee`
- `ntoskrnl!EtwWriteTransfer` at `0x1400371df`
- `ntoskrnl!EtwWriteTransfer` at `0x1400372ee`

## pseudocode

```c
void __fastcall AiProcessNotifyRoutine(PEPROCESS Process, HANDLE ProcessId, __int64 CreateInfo)
{
  const UNICODE_STRING *v6; // r12
  PDEVICE_OBJECT v7; // rdx
  PCUNICODE_STRING v8; // rcx
  char v9; // al
  __int64 v10; // rsi
  __int64 PerformanceCounter; // rbx
  struct _UNICODE_STRING *v12; // rdx
  int v13; // eax
  NTSTATUS ProcessNotifyRoutine; // eax
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned __int64 updated; // r14
  const struct _TraceLoggingMetadata_t *v19; // r8
  __int64 FileNameFromPath; // r8
  PWSTR Buffer; // rax
  __int64 v22; // rdx
  PUNICODE_STRING v23; // rcx
  PUNICODE_STRING pImageFileName; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int64 v25; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v26; // [rsp+70h] [rbp-98h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+88h] [rbp-80h] BYREF
  __int16 *v29; // [rsp+98h] [rbp-70h]
  int v30; // [rsp+A0h] [rbp-68h]
  int v31; // [rsp+A4h] [rbp-64h]
  unsigned __int64 *v32; // [rsp+A8h] [rbp-60h]
  __int64 v33; // [rsp+B0h] [rbp-58h]
  WCHAR *v34; // [rsp+B8h] [rbp-50h]
  _QWORD v35[5]; // [rsp+C0h] [rbp-48h] BYREF

  pImageFileName = 0;
  v6 = 0;
  if ( CreateInfo )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      v8 = (PCUNICODE_STRING)&qword_140009298;
      if ( *(_QWORD *)(CreateInfo + 56) )
        v8 = *(PCUNICODE_STRING *)(CreateInfo + 56);
      v9 = 89;
      if ( (*(_DWORD *)(CreateInfo + 8) & 1) == 0 )
        v9 = 78;
      WPP_SF_qDDZcZ(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)WPP_GLOBAL_Control,
        78,
        (_DWORD)Process,
        (char)ProcessId,
        *(_DWORD *)(CreateInfo + 16),
        *(_QWORD *)(CreateInfo + 48),
        v9,
        (__int64)v8);
    }
    LOBYTE(v7) = 1;
    v10 = CreateInfo + 8;
    PerformanceCounter = AiQueryPerformanceCounter(0, v7);
    if ( (*(_DWORD *)(CreateInfo + 8) & 1) != 0 )
    {
      v12 = *(struct _UNICODE_STRING **)(CreateInfo + 48);
      pImageFileName = v12;
    }
    else
    {
      v13 = SeLocateProcessImageName(Process, &pImageFileName);
      *(_DWORD *)(CreateInfo + 64) = v13;
      if ( v13 < 0 )
        goto LABEL_29;
      v12 = pImageFileName;
      v6 = *(const UNICODE_STRING **)(CreateInfo + 48);
      *(_QWORD *)(CreateInfo + 48) = pImageFileName;
    }
    ProcessNotifyRoutine = AipCreateProcessNotifyRoutine(
                             (__int64)ProcessId,
                             (PVOID *)v12,
                             *(_QWORD *)(CreateInfo + 40),
                             (__int64)Process,
                             CreateInfo);
    LOBYTE(v15) = 1;
    *(_DWORD *)(CreateInfo + 64) = ProcessNotifyRoutine;
    updated = AiUpdatePerfTime(&AiPerfStats, PerformanceCounter, v15);
    v19 = &TraceLoggingMetadata;
    if ( updated > 0x7A120 )
    {
      FileNameFromPath = (unsigned __int16)AiGetFileNameFromPath(pImageFileName);
      if ( (unsigned int)dword_140019000 > 4 )
      {
        v16 = qword_140019018;
        if ( (qword_140019010 & 0x200000000000LL) != 0 && (qword_140019018 & 0x200000000000LL) == qword_140019018 )
        {
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0x200000000000LL;
          Buffer = pImageFileName->Buffer;
          v22 = ((unsigned __int64)pImageFileName->Length >> 1) - FileNameFromPath;
          v33 = 2;
          v25 = updated;
          v35[2] = 8;
          v35[4] = 8;
          v34 = &Buffer[v22];
          v32 = v35;
          v35[0] = (unsigned int)(2 * FileNameFromPath);
          v35[1] = &v25;
          v26 = *(int *)(CreateInfo + 64);
          v35[3] = &v26;
          *(_DWORD *)&EventDescriptor.Level = 4;
          UserData.Ptr = (ULONGLONG)EventInformation;
          UserData.Size = *(unsigned __int16 *)EventInformation;
          v29 = (__int16 *)&byte_140015ED7;
          UserData.Reserved = 2;
          v30 = 88;
          v31 = 1;
          EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
        }
      }
      v19 = &TraceLoggingMetadata;
    }
    if ( *(_QWORD *)&qword_140019628 >= 0xC350u )
    {
      if ( (unsigned int)dword_140019000 > 4
        && (qword_140019010 & 0x200000000000LL) != 0
        && (qword_140019018 & 0x200000000000LL) == qword_140019018 )
      {
        v25 = *(_QWORD *)&qword_140019628;
        v26 = (unsigned __int64)AiPerfStats / *(_QWORD *)&qword_140019628;
        v33 = 8;
        v32 = &v26;
        v35[0] = 8;
        v34 = (WCHAR *)&v25;
        *(_DWORD *)&EventDescriptor.Level = 4;
        UserData.Ptr = (ULONGLONG)EventInformation;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0x200000000000LL;
        UserData.Size = *(unsigned __int16 *)EventInformation;
        v29 = word_140015E82;
        UserData.Reserved = 2;
        v30 = 73;
        v31 = 1;
        EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
      }
      AiResetPerfTimeCounter(&AiPerfStats, v16, v19, v17);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_c7f28e522d5a3d44ab43fad3c67cb075_Traceguids);
  }
  else
  {
    AiRemoveProcFromTracking((struct _DEVICE_OBJECT *)Process, ProcessId);
    v10 = 8;
  }
LABEL_29:
  v23 = pImageFileName;
  if ( pImageFileName )
  {
    if ( (*(_DWORD *)v10 & 1) == 0 )
    {
      *(_QWORD *)(CreateInfo + 48) = v6;
      ExFreePoolWithTag(v23, 0);
    }
  }
}

```

## disassembly

```asm
0x140036f60  mov     r11, rsp
0x140036f63  push    rbp
0x140036f64  push    rsi
0x140036f65  push    rdi
0x140036f66  push    r12
0x140036f68  lea     rbp, [r11-28h]
0x140036f6c  sub     rsp, 108h
0x140036f73  mov     rax, cs:__security_cookie
0x140036f7a  xor     rax, rsp
0x140036f7d  mov     [rbp+20h+var_40], rax
0x140036f81  mov     [r11+20h], rbx
0x140036f85  mov     rdi, r8
0x140036f88  mov     [r11-28h], r13
0x140036f8c  xor     r13d, r13d
0x140036f8f  mov     [r11-30h], r14
0x140036f93  mov     r14, rcx
0x140036f96  mov     [r11-38h], r15
0x140036f9a  mov     r15, rdx
0x140036f9d  mov     [rsp+120h+pImageFileName], r13
0x140036fa2  mov     r12d, r13d
0x140036fa5  test    r8, r8
0x140036fa8  jz      loc_140037337
0x140036fae  mov     rdx, cs:WPP_GLOBAL_Control
0x140036fb5  lea     rax, WPP_GLOBAL_Control
0x140036fbc  cmp     rdx, rax
0x140036fbf  jz      short loc_140037019
0x140036fc1  mov     eax, [rdx+2Ch]
0x140036fc4  test    al, 4
0x140036fc6  jz      short loc_140037019
0x140036fc8  mov     rax, [r8+38h]
0x140036fcc  lea     rcx, qword_140009298
0x140036fd3  test    rax, rax
0x140036fd6  mov     r9, r14
0x140036fd9  cmovnz  rcx, rax
0x140036fdd  mov     eax, [r8+8]
0x140036fe1  mov     [rsp+40h], rcx
0x140036fe6  test    al, 1
0x140036fe8  mov     rcx, [rdx+18h]
0x140036fec  mov     eax, 59h ; 'Y'
0x140036ff1  mov     r8d, 4Eh ; 'N'
0x140036ff7  cmovz   eax, r8d
0x140036ffb  mov     byte ptr [rsp+120h+var_E8], al
0x140036fff  mov     rax, [rdi+30h]
0x140037003  mov     qword ptr [rsp+120h+var_F0], rax
0x140037008  mov     eax, [rdi+10h]
0x14003700b  mov     dword ptr [rsp+120h+UserData], eax
0x14003700f  mov     [rsp+120h+UserDataCount], r15d
0x140037014  call    WPP_SF_qDDZcZ
0x140037019  mov     dl, 1
0x14003701b  xor     ecx, ecx
0x14003701d  call    AiQueryPerformanceCounter
0x140037022  lea     rsi, [rdi+8]
0x140037026  mov     rbx, rax
0x140037029  mov     eax, [rsi]
0x14003702b  test    al, 1
0x14003702d  jz      short loc_14003703A
0x14003702f  mov     rdx, [rdi+30h]
0x140037033  mov     [rsp+120h+pImageFileName], rdx
0x140037038  jmp     short loc_140037066
0x14003703a  lea     rdx, [rsp+120h+pImageFileName]; pImageFileName
0x14003703f  mov     rcx, r14; Process
0x140037042  call    cs:__imp_SeLocateProcessImageName
0x140037049  nop     dword ptr [rax+rax+00h]
0x14003704e  mov     [rdi+40h], eax
0x140037051  test    eax, eax
0x140037053  js      loc_140037340
0x140037059  mov     rdx, [rsp+120h+pImageFileName]
0x14003705e  mov     r12, [rdi+30h]
0x140037062  mov     [rdi+30h], rdx
0x140037066  mov     r8, [rdi+28h]
0x14003706a  mov     r9, r14
0x14003706d  mov     rcx, r15
0x140037070  mov     qword ptr [rsp+120h+UserDataCount], rdi
0x140037075  call    AipCreateProcessNotifyRoutine
0x14003707a  mov     r8b, 1
0x14003707d  mov     [rdi+40h], eax
0x140037080  mov     rdx, rbx
0x140037083  lea     rcx, AiPerfStats
0x14003708a  call    AiUpdatePerfTime
0x14003708f  lea     rbx, _TraceLoggingMetadataEnd
0x140037096  mov     r14, rax
0x140037099  lea     r8, _TraceLoggingMetadata
0x1400370a0  mov     r15, 200000000000h
0x1400370aa  cmp     rax, 7A120h
0x1400370b0  jbe     loc_1400371F2
0x1400370b6  mov     rcx, [rsp+120h+pImageFileName]; SourceString
0x1400370bb  call    AiGetFileNameFromPath
0x1400370c0  mov     ecx, cs:dword_140019000
0x1400370c6  movzx   r8d, ax
0x1400370ca  cmp     ecx, 4
0x1400370cd  jbe     loc_1400371EB
0x1400370d3  mov     rdx, cs:qword_140019018
0x1400370da  mov     rcx, cs:qword_140019010
0x1400370e1  test    r15, rcx
0x1400370e4  jz      loc_1400371EB
0x1400370ea  mov     rcx, rdx
0x1400370ed  and     rcx, r15
0x1400370f0  cmp     rcx, rdx
0x1400370f3  jnz     loc_1400371EB
0x1400370f9  mov     rcx, [rsp+120h+pImageFileName]
0x1400370fe  xor     r9d, r9d; RelatedActivityId
0x140037101  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x140037109  mov     [rsp+120h+EventDescriptor.Keyword], r15
0x14003710e  movzx   edx, word ptr [rcx]
0x140037111  mov     rax, [rcx+8]
0x140037115  shr     rdx, 1
0x140037118  sub     rdx, r8
0x14003711b  mov     [rbp+20h+var_78], 2
0x140037123  mov     dword ptr [rbp+20h+var_68+4], r13d
0x140037127  mov     [rsp+120h+var_C0], r14
0x14003712c  mov     [rbp+20h+var_58], 8
0x140037134  lea     rcx, [rax+rdx*2]
0x140037138  mov     [rbp+20h+var_48], 8
0x140037140  mov     [rbp+20h+var_70], rcx
0x140037144  lea     rax, [rbp+20h+var_68]
0x140037148  mov     [rbp+20h+var_80], rax
0x14003714c  lea     rcx, _TraceLoggingMetadata
0x140037153  mov     eax, r8d
0x140037156  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x14003715b  add     eax, eax
0x14003715d  xor     r8d, r8d; ActivityId
0x140037160  mov     dword ptr [rbp+20h+var_68], eax
0x140037163  lea     rax, [rsp+120h+var_C0]
0x140037168  mov     [rbp+20h+var_60], rax
0x14003716c  movsxd  rax, dword ptr [rdi+40h]
0x140037170  mov     qword ptr [rsp+120h+var_B8], rax
0x140037175  lea     rax, [rsp+120h+var_B8]
0x14003717a  mov     [rbp+20h+var_50], rax
0x14003717e  movzx   eax, cs:word_140015ECD
0x140037185  mov     dword ptr [rsp+120h+EventDescriptor.Level], eax
0x140037189  mov     rax, cs:EventInformation
0x140037190  mov     [rbp+20h+var_A0.Ptr], rax
0x140037194  movzx   eax, word ptr [rax]
0x140037197  mov     [rbp+20h+var_A0.Size], eax
0x14003719a  lea     rax, byte_140015ED7
0x1400371a1  mov     [rbp+20h+var_90], rax
0x1400371a5  mov     rax, rbx
0x1400371a8  sub     eax, ecx
0x1400371aa  mov     dword ptr [rbp+20h+var_A0.0Ch], 2
0x1400371b1  mov     [rbp+20h+var_88], 58h ; 'X'
0x1400371b8  mov     [rbp+20h+var_84], 1
0x1400371bf  mov     dword ptr [rsp+120h+var_D0], eax
0x1400371c3  mov     eax, dword ptr [rsp+120h+var_D0]
0x1400371c7  mov     rcx, cs:RegHandle; RegHandle
0x1400371ce  lea     rax, [rbp+20h+var_A0]
0x1400371d2  mov     [rsp+120h+UserData], rax; UserData
0x1400371d7  mov     [rsp+120h+UserDataCount], 6; UserDataCount
0x1400371df  call    cs:__imp_EtwWriteTransfer
0x1400371e6  nop     dword ptr [rax+rax+00h]
0x1400371eb  lea     r8, _TraceLoggingMetadata
0x1400371f2  cmp     cs:qword_140019628, 0C350h
0x1400371fd  jb      loc_140037306
0x140037203  mov     eax, cs:dword_140019000
0x140037209  cmp     eax, 4
0x14003720c  jbe     loc_1400372FA
0x140037212  mov     rcx, cs:qword_140019018
0x140037219  mov     rax, cs:qword_140019010
0x140037220  test    r15, rax
0x140037223  jz      loc_1400372FA
0x140037229  mov     rax, rcx
0x14003722c  and     rax, r15
0x14003722f  cmp     rax, rcx
0x140037232  jnz     loc_1400372FA
0x140037238  mov     rcx, cs:qword_140019628
0x14003723f  xor     edx, edx
0x140037241  mov     rax, cs:AiPerfStats
0x140037248  sub     ebx, r8d
0x14003724b  div     rcx
0x14003724e  mov     [rsp+120h+var_C0], rcx
0x140037253  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x140037258  mov     qword ptr [rsp+120h+var_B8], rax
0x14003725d  xor     r9d, r9d; RelatedActivityId
0x140037260  mov     [rbp+20h+var_78], 8
0x140037268  lea     rax, [rsp+120h+var_B8]
0x14003726d  mov     [rbp+20h+var_80], rax
0x140037271  xor     r8d, r8d; ActivityId
0x140037274  lea     rax, [rsp+120h+var_C0]
0x140037279  mov     [rbp+20h+var_68], 8
0x140037281  mov     [rbp+20h+var_70], rax
0x140037285  movzx   eax, cs:word_140015E78
0x14003728c  mov     dword ptr [rsp+120h+EventDescriptor.Level], eax
0x140037290  mov     rax, cs:EventInformation
0x140037297  mov     [rbp+20h+var_A0.Ptr], rax
0x14003729b  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x1400372a3  mov     [rsp+120h+EventDescriptor.Keyword], r15
0x1400372a8  movzx   eax, word ptr [rax]
0x1400372ab  mov     [rbp+20h+var_A0.Size], eax
0x1400372ae  lea     rax, word_140015E82
0x1400372b5  mov     [rbp+20h+var_90], rax
0x1400372b9  mov     dword ptr [rbp+20h+var_A0.0Ch], 2
0x1400372c0  mov     [rbp+20h+var_88], 49h ; 'I'
0x1400372c7  mov     [rbp+20h+var_84], 1
0x1400372ce  mov     dword ptr [rsp+120h+var_D0], ebx
0x1400372d2  mov     eax, dword ptr [rsp+120h+var_D0]
0x1400372d6  mov     rcx, cs:RegHandle; RegHandle
0x1400372dd  lea     rax, [rbp+20h+var_A0]
0x1400372e1  mov     [rsp+120h+UserData], rax; UserData
0x1400372e6  mov     [rsp+120h+UserDataCount], 4; UserDataCount
0x1400372ee  call    cs:__imp_EtwWriteTransfer
0x1400372f5  nop     dword ptr [rax+rax+00h]
0x1400372fa  lea     rcx, AiPerfStats
0x140037301  call    AiResetPerfTimeCounter
0x140037306  mov     rcx, cs:WPP_GLOBAL_Control
0x14003730d  lea     rax, WPP_GLOBAL_Control
0x140037314  cmp     rcx, rax
0x140037317  jz      short loc_140037340
0x140037319  mov     eax, [rcx+2Ch]
0x14003731c  test    al, 4
0x14003731e  jz      short loc_140037340
0x140037320  mov     rcx, [rcx+18h]
0x140037324  lea     r8, WPP_c7f28e522d5a3d44ab43fad3c67cb075_Traceguids
0x14003732b  mov     edx, 0Bh
0x140037330  call    WPP_SF_
0x140037335  jmp     short loc_140037340
0x140037337  call    AiRemoveProcFromTracking
0x14003733c  lea     rsi, [rdi+8]
0x140037340  mov     rcx, [rsp+120h+pImageFileName]; P
0x140037345  mov     r15, [rsp+120h+var_30]
0x14003734d  mov     r14, [rsp+120h+var_28]
0x140037355  mov     r13, [rsp+100h]
0x14003735d  mov     rbx, [rsp+120h+arg_18]
0x140037365  test    rcx, rcx
0x140037368  jz      short loc_140037382
0x14003736a  mov     eax, [rsi]
0x14003736c  test    al, 1
0x14003736e  jnz     short loc_140037382
0x140037370  xor     edx, edx; Tag
0x140037372  mov     [rdi+30h], r12
0x140037376  call    cs:__imp_ExFreePoolWithTag
0x14003737d  nop     dword ptr [rax+rax+00h]
0x140037382  mov     rcx, [rbp+20h+var_40]
0x140037386  xor     rcx, rsp; StackCookie
0x140037389  call    __security_check_cookie
0x14003738e  add     rsp, 108h
0x140037395  pop     r12
0x140037397  pop     rdi
0x140037398  pop     rsi
0x140037399  pop     rbp
0x14003739a  retn
```
