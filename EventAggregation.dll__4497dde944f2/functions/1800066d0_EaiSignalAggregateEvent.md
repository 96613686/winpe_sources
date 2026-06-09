# EaiSignalAggregateEvent

- ea: `0x1800066d0`
- end: `0x1800069bb`
- name: `EaiSignalAggregateEvent`
- size: `747`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800069d0`

## callees

- `0x1800066d0`
- `0x1800072e0`
- `0x18000c010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800067e1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800067e1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180006899`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180006899`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800067b3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000698e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800067b3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000698e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800067ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000689f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800067ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000689f`

## pseudocode

```c
ULONG __fastcall EaiSignalAggregateEvent(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        __int64 a7)
{
  __int64 v11; // rbx
  void (__fastcall *v12)(__int64, __int64, _QWORD, _QWORD); // rax
  void (__fastcall *v13)(__int64, _QWORD, __int64, _QWORD, unsigned int); // rax
  void (__fastcall *v14)(__int64, __int64, _QWORD, __int64, unsigned int, unsigned int, __int64); // rax
  bool v15; // zf
  ULONG result; // eax
  unsigned int v17; // [rsp+40h] [rbp-91h] BYREF
  __int64 v18; // [rsp+48h] [rbp-89h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-81h] BYREF
  __int64 v20; // [rsp+60h] [rbp-71h] BYREF
  EVENT_DESCRIPTOR v21; // [rsp+68h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-51h] BYREF
  __int16 *v23; // [rsp+90h] [rbp-41h]
  int v24; // [rsp+98h] [rbp-39h]
  int v25; // [rsp+9Ch] [rbp-35h]
  __int64 *v26; // [rsp+A0h] [rbp-31h]
  __int64 v27; // [rsp+A8h] [rbp-29h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+B0h] [rbp-21h]
  __int64 v29; // [rsp+B8h] [rbp-19h]
  unsigned int *v30; // [rsp+C0h] [rbp-11h]
  __int64 v31; // [rsp+C8h] [rbp-9h]

  if ( (unsigned int)dword_180012000 > 4 )
  {
    EventDescriptor.Keyword = 0;
    v26 = &v18;
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_180012008;
    v18 = a1;
    v27 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v23 = &word_18000F036;
    UserData.Reserved = 2;
    v24 = 42;
    v25 = 1;
    v17 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  v11 = *a3;
  if ( *(_DWORD *)(a1 + 108) == 1 )
    *(_DWORD *)(a1 + 108) = 2;
  *(_QWORD *)(a1 + 112) = GetCurrentThreadId();
  *(_DWORD *)(a1 + 88) = 0;
  RtlReleaseSRWLockExclusive(a1 + 80);
  if ( a2 )
  {
    switch ( a2 )
    {
      case 1u:
        v12 = *(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(a1 + 32);
        if ( v12 )
LABEL_10:
          v12(a1, v11, *(_QWORD *)(a1 + 72), a6);
        break;
      case 2u:
        v13 = *(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD, unsigned int))(a1 + 40);
        if ( v13 )
          v13(a1, *(_QWORD *)(a1 + 72), a4, a5, a6);
        break;
      case 3u:
        v12 = *(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(a1 + 48);
        if ( v12 )
          goto LABEL_10;
        break;
    }
  }
  else
  {
    v14 = *(void (__fastcall **)(__int64, __int64, _QWORD, __int64, unsigned int, unsigned int, __int64))(a1 + 24);
    if ( v14 )
      v14(a1, v11, *(_QWORD *)(a1 + 72), a4, a5, a6, a7);
  }
  RtlAcquireSRWLockExclusive(a1 + 80);
  *(_DWORD *)(a1 + 88) = GetCurrentThreadId();
  v15 = *(_DWORD *)(a1 + 108) == 2;
  *(_QWORD *)(a1 + 112) = 0;
  if ( v15 )
    *(_DWORD *)(a1 + 108) = 1;
  result = dword_180012000;
  if ( (unsigned int)dword_180012000 > 4 )
  {
    v21.Keyword = 0;
    v26 = &v20;
    *(_QWORD *)&EventDescriptor.Id = *a3;
    v20 = a1;
    p_EventDescriptor = &EventDescriptor;
    v27 = 8;
    v30 = &v17;
    *(_DWORD *)&v21.Level = 516;
    UserData.Ptr = (ULONGLONG)off_180012008;
    v29 = 8;
    v17 = a2;
    v31 = 4;
    *(_DWORD *)&v21.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v23 = (__int16 *)byte_18000EFE9;
    UserData.Reserved = 2;
    v24 = 65;
    v25 = 1;
    LODWORD(v18) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    return EventWriteTransfer(RegHandle, &v21, 0, 0, 5u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x1800066d0  mov     [rsp-8+arg_8], rbx
0x1800066d5  push    rbp
0x1800066d6  push    rsi
0x1800066d7  push    rdi
0x1800066d8  push    r12
0x1800066da  push    r13
0x1800066dc  push    r14
0x1800066de  push    r15
0x1800066e0  lea     rbp, [rsp-0Fh]
0x1800066e5  sub     rsp, 0E0h
0x1800066ec  mov     rax, cs:__security_cookie
0x1800066f3  xor     rax, rsp
0x1800066f6  mov     [rbp+3Fh+var_40], rax
0x1800066fa  mov     eax, cs:dword_180012000
0x180006700  mov     rdi, rcx
0x180006703  mov     r15, [rbp+3Fh+arg_30]
0x180006707  xor     ecx, ecx
0x180006709  mov     r12d, edx
0x18000670c  mov     r14, r9
0x18000670f  lea     rdx, _TraceLoggingMetadata
0x180006716  mov     r13, r8
0x180006719  cmp     eax, 4
0x18000671c  jbe     loc_1800067B9
0x180006722  mov     [rbp+3Fh+EventDescriptor.Keyword], rcx
0x180006726  lea     rax, [rsp+110h+var_C8]
0x18000672b  mov     [rbp+3Fh+var_70], rax
0x18000672f  xor     r9d, r9d; RelatedActivityId
0x180006732  movzx   eax, cs:word_18000F02C
0x180006739  xor     r8d, r8d; ActivityId
0x18000673c  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x18000673f  mov     rax, cs:off_180012008
0x180006746  mov     [rbp+3Fh+var_90.Ptr], rax
0x18000674a  mov     [rsp+110h+var_C8], rdi
0x18000674f  mov     [rbp+3Fh+var_68], 8
0x180006757  mov     dword ptr [rsp+110h+EventDescriptor.Id], 0B000000h
0x18000675f  movzx   eax, word ptr [rax]
0x180006762  mov     [rbp+3Fh+var_90.Size], eax
0x180006765  lea     rax, word_18000F036
0x18000676c  mov     [rbp+3Fh+var_80], rax
0x180006770  lea     rax, _TraceLoggingMetadataEnd
0x180006777  sub     eax, edx
0x180006779  mov     dword ptr [rbp+3Fh+var_90.0Ch], 2
0x180006780  mov     [rbp+3Fh+var_78], 2Ah ; '*'
0x180006787  lea     rdx, [rsp+110h+EventDescriptor]; EventDescriptor
0x18000678c  mov     [rbp+3Fh+var_74], 1
0x180006793  mov     [rsp+110h+var_D0], eax
0x180006797  mov     eax, [rsp+110h+var_D0]
0x18000679b  mov     rcx, cs:RegHandle; RegHandle
0x1800067a2  lea     rax, [rbp+3Fh+var_90]
0x1800067a6  mov     [rsp+110h+UserData], rax; UserData
0x1800067ab  mov     [rsp+110h+UserDataCount], 3; UserDataCount
0x1800067b3  call    cs:__imp_EventWriteTransfer
0x1800067b9  cmp     dword ptr [rdi+6Ch], 1
0x1800067bd  mov     rbx, [r13+0]
0x1800067c1  jnz     short loc_1800067CA
0x1800067c3  mov     dword ptr [rdi+6Ch], 2
0x1800067ca  call    cs:__imp_GetCurrentThreadId
0x1800067d0  mov     eax, eax
0x1800067d2  lea     rcx, [rdi+50h]
0x1800067d6  mov     [rdi+70h], rax
0x1800067da  mov     dword ptr [rdi+58h], 0
0x1800067e1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800067e7  mov     ecx, r12d
0x1800067ea  test    r12d, r12d
0x1800067ed  jz      short loc_180006867
0x1800067ef  sub     ecx, 1
0x1800067f2  jz      short loc_180006849
0x1800067f4  sub     ecx, 1
0x1800067f7  jz      short loc_180006824
0x1800067f9  cmp     ecx, 1
0x1800067fc  jnz     loc_180006895
0x180006802  mov     rax, [rdi+30h]
0x180006806  test    rax, rax
0x180006809  jz      loc_180006895
0x18000680f  mov     r9d, [rbp+3Fh+arg_28]
0x180006813  mov     rdx, rbx
0x180006816  mov     r8, [rdi+48h]
0x18000681a  mov     rcx, rdi
0x18000681d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006822  jmp     short loc_180006895
0x180006824  mov     rax, [rdi+28h]
0x180006828  test    rax, rax
0x18000682b  jz      short loc_180006895
0x18000682d  mov     ecx, [rbp+3Fh+arg_28]
0x180006830  mov     r8, r14
0x180006833  mov     r9d, [rbp+3Fh+arg_20]
0x180006837  mov     rdx, [rdi+48h]
0x18000683b  mov     [rsp+110h+UserDataCount], ecx
0x18000683f  mov     rcx, rdi
0x180006842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006847  jmp     short loc_180006895
0x180006849  mov     rax, [rdi+20h]
0x18000684d  test    rax, rax
0x180006850  jz      short loc_180006895
0x180006852  mov     r9d, [rbp+3Fh+arg_28]
0x180006856  mov     rdx, rbx
0x180006859  mov     r8, [rdi+48h]
0x18000685d  mov     rcx, rdi
0x180006860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006865  jmp     short loc_180006895
0x180006867  mov     rax, [rdi+18h]
0x18000686b  test    rax, rax
0x18000686e  jz      short loc_180006895
0x180006870  mov     ecx, [rbp+3Fh+arg_28]
0x180006873  mov     r9, r14
0x180006876  mov     r8, [rdi+48h]
0x18000687a  mov     rdx, rbx
0x18000687d  mov     [rsp+110h+var_E0], r15
0x180006882  mov     dword ptr [rsp+110h+UserData], ecx
0x180006886  mov     ecx, [rbp+3Fh+arg_20]
0x180006889  mov     [rsp+110h+UserDataCount], ecx
0x18000688d  mov     rcx, rdi
0x180006890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006895  lea     rcx, [rdi+50h]
0x180006899  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000689f  call    cs:__imp_GetCurrentThreadId
0x1800068a5  xor     ecx, ecx
0x1800068a7  mov     [rdi+58h], eax
0x1800068aa  cmp     dword ptr [rdi+6Ch], 2
0x1800068ae  mov     [rdi+70h], rcx
0x1800068b2  jnz     short loc_1800068BB
0x1800068b4  mov     dword ptr [rdi+6Ch], 1
0x1800068bb  mov     eax, cs:dword_180012000
0x1800068c1  cmp     eax, 4
0x1800068c4  jbe     loc_180006994
0x1800068ca  mov     [rbp+3Fh+var_A8.Keyword], rcx
0x1800068ce  lea     rax, [rbp+3Fh+var_B0]
0x1800068d2  mov     [rbp+3Fh+var_70], rax
0x1800068d6  lea     rcx, _TraceLoggingMetadata
0x1800068dd  mov     rax, [r13+0]
0x1800068e1  lea     rdx, [rbp+3Fh+var_A8]; EventDescriptor
0x1800068e5  mov     qword ptr [rsp+110h+EventDescriptor.Id], rax
0x1800068ea  xor     r9d, r9d; RelatedActivityId
0x1800068ed  mov     [rbp+3Fh+var_B0], rdi
0x1800068f1  lea     rax, [rsp+110h+EventDescriptor]
0x1800068f6  mov     [rbp+3Fh+var_60], rax
0x1800068fa  xor     r8d, r8d; ActivityId
0x1800068fd  lea     rax, [rsp+110h+var_D0]
0x180006902  mov     [rbp+3Fh+var_68], 8
0x18000690a  mov     [rbp+3Fh+var_50], rax
0x18000690e  movzx   eax, cs:word_18000EFDF
0x180006915  mov     dword ptr [rbp+3Fh+var_A8.Level], eax
0x180006918  mov     rax, cs:off_180012008
0x18000691f  mov     [rbp+3Fh+var_90.Ptr], rax
0x180006923  mov     [rbp+3Fh+var_58], 8
0x18000692b  mov     [rsp+110h+var_D0], r12d
0x180006930  mov     [rbp+3Fh+var_48], 4
0x180006938  mov     dword ptr [rbp+3Fh+var_A8.Id], 0B000000h
0x18000693f  movzx   eax, word ptr [rax]
0x180006942  mov     [rbp+3Fh+var_90.Size], eax
0x180006945  lea     rax, byte_18000EFE9
0x18000694c  mov     [rbp+3Fh+var_80], rax
0x180006950  lea     rax, _TraceLoggingMetadataEnd
0x180006957  sub     eax, ecx
0x180006959  mov     dword ptr [rbp+3Fh+var_90.0Ch], 2
0x180006960  mov     [rbp+3Fh+var_78], 41h ; 'A'
0x180006967  mov     [rbp+3Fh+var_74], 1
0x18000696e  mov     dword ptr [rsp+110h+var_C8], eax
0x180006972  mov     eax, dword ptr [rsp+110h+var_C8]
0x180006976  mov     rcx, cs:RegHandle; RegHandle
0x18000697d  lea     rax, [rbp+3Fh+var_90]
0x180006981  mov     [rsp+110h+UserData], rax; UserData
0x180006986  mov     [rsp+110h+UserDataCount], 5; UserDataCount
0x18000698e  call    cs:__imp_EventWriteTransfer
0x180006994  mov     rcx, [rbp+3Fh+var_40]
0x180006998  xor     rcx, rsp; StackCookie
0x18000699b  call    __security_check_cookie
0x1800069a0  mov     rbx, [rsp+110h+arg_8]
0x1800069a8  add     rsp, 0E0h
0x1800069af  pop     r15
0x1800069b1  pop     r14
0x1800069b3  pop     r13
0x1800069b5  pop     r12
0x1800069b7  pop     rdi
0x1800069b8  pop     rsi
0x1800069b9  pop     rbp
0x1800069ba  retn
```
