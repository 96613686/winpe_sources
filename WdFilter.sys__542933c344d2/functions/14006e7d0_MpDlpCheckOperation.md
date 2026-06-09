# MpDlpCheckOperation

- ea: `0x14006e7d0`
- end: `0x14006eb7f`
- name: `MpDlpCheckOperation`
- size: `943`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, int, __int64, __int64)`
- caller_count: `3`
- callee_count: `17`
- tags: `authz_impersonation, service_task`

## callers

- `0x14003fe70`
- `0x14006e4f4`
- `0x14006f0d8`

## callees

- `0x140002450`
- `0x1400026c0`
- `0x140003950`
- `0x1400044d0`
- `0x140004530`
- `0x1400051bc`
- `0x140011890`
- `0x140011900`
- `0x14002f9f0`
- `0x1400425e0`
- `0x140047950`
- `0x140056b50`
- `0x140056c20`
- `0x14006e7d0`
- `0x14006eb80`
- `0x14007451c`
- `0x140085d24`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x14006e879`
- `ntoskrnl!IoGetCurrentProcess` at `0x14006e879`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006eaf3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006eaf3`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14006e868`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14006e868`
- `ntoskrnl!ExQueryDepthSList` at `0x14006eb24`
- `ntoskrnl!ExQueryDepthSList` at `0x14006eb24`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14006eb53`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14006eb53`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006eada`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006eada`

## pseudocode

```c
__int64 __fastcall MpDlpCheckOperation(
        __int64 CallbackData,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        UNICODE_STRING *a6,
        __int64 a7)
{
  unsigned int v7; // r14d
  UNICODE_STRING *p_Name; // r12
  unsigned __int16 *RequestorProcess; // rdi
  struct _FLT_CALLBACK_DATA *v11; // rbx
  HANDLE v12; // rbx
  __int64 v13; // r15
  unsigned int v14; // esi
  int Length; // eax
  int v16; // eax
  _DWORD *PoolWithTag; // rax
  _DWORD *v18; // rbx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // r8d
  char *v24; // rsi
  USHORT v25; // bx
  USHORT DepthSList; // ax
  unsigned int v28; // [rsp+34h] [rbp-1Ch] BYREF
  PSLIST_ENTRY ListEntry; // [rsp+38h] [rbp-18h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+40h] [rbp-10h]

  v7 = 0;
  v28 = 0;
  FileNameInformation = 0;
  p_Name = 0;
  RequestorProcess = 0;
  ListEntry = 0;
  v11 = (struct _FLT_CALLBACK_DATA *)CallbackData;
  if ( !MpDlpIsEnabled(CallbackData, (_QWORD *)a3) )
    return 0;
  if ( (unsigned __int8)MpDlpIsProtectedProcess(a3) )
  {
LABEL_15:
    if ( a6 && a6->Length )
    {
      v13 = 72;
      p_Name = a6;
      v14 = 72;
    }
    else
    {
      if ( v11 && (int)MpQueryFileName(v11) >= 0 )
        p_Name = &FileNameInformation->Name;
      v13 = 72;
      v14 = 72;
      if ( !p_Name )
        goto LABEL_24;
    }
    Length = p_Name->Length;
    if ( (_WORD)Length )
      v14 = Length + 74;
LABEL_24:
    if ( RequestorProcess )
    {
      v16 = *RequestorProcess;
      if ( (_WORD)v16 )
        v14 += v16;
    }
    PoolWithTag = (_DWORD *)MpAllocatePoolWithTag(1, v14, 1818513485);
    v18 = PoolWithTag;
    if ( PoolWithTag )
    {
      *PoolWithTag = 328101;
      PoolWithTag[1] = v14;
      if ( a2 )
        v19 = *(_QWORD *)(a2 + 32);
      else
        v19 = 0;
      MpGetPriorityInfo(CallbackData, v19, PoolWithTag + 2);
      v18[14] = *(_DWORD *)(a3 + 24);
      *((_QWORD *)v18 + 3) = MpFileTimeToUlong64(*(_QWORD *)(a3 + 32));
      MpQuerySessionId(v21, v20, v18 + 15);
      v18[16] = a5;
      v18[17] = a4;
      if ( p_Name && p_Name->Length )
      {
        *((_QWORD *)v18 + 4) = 72;
        memmove(v18 + 18, p_Name->Buffer, p_Name->Length);
        *(_WORD *)((char *)v18 + 2 * ((unsigned __int64)p_Name->Length >> 1) + *((_QWORD *)v18 + 4)) = 0;
        v22 = p_Name->Length;
        v18[12] = v22;
        v13 = v22 + 74;
      }
      if ( RequestorProcess && *RequestorProcess )
      {
        *((_QWORD *)v18 + 5) = v13;
        memmove((char *)v18 + v13, *((const void **)RequestorProcess + 1), *RequestorProcess);
        v18[13] = *RequestorProcess;
      }
      v23 = MpDlpQueryService(a4, v18, &v28, a7);
      if ( v23 >= 0 )
      {
        v7 = v28;
        if ( v28 == 3 )
          v7 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            51,
            WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
            KeGetCurrentThread(),
            v23);
        }
        v7 = v28;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        50,
        WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
        KeGetCurrentThread(),
        -1073741670);
    }
    if ( FileNameInformation )
      FltReleaseFileNameInformation(FileNameInformation);
    if ( v18 )
      ExFreePoolWithTag(v18, 0x6C64504Du);
    goto LABEL_51;
  }
  if ( a5 > 1 )
    return 0;
  if ( v11 && MpGetRequestorProcessIdEx(v11) == *(HANDLE *)(a3 + 24) )
  {
    RequestorProcess = (unsigned __int16 *)MpGetRequestorProcess(v11);
  }
  else
  {
    v12 = *(HANDLE *)(a3 + 24);
    if ( PsGetCurrentProcessId() == v12 )
      RequestorProcess = (unsigned __int16 *)IoGetCurrentProcess();
    v11 = (struct _FLT_CALLBACK_DATA *)CallbackData;
  }
  if ( MpDlpShouldCheckMappedFileOperation((struct _KPROCESS *)RequestorProcess, a3, &ListEntry)
    || *(_DWORD *)(a3 + 240) == 20 && (MpFcKernelGetValue(283) & 2) != 0 )
  {
    RequestorProcess = (unsigned __int16 *)ListEntry;
    goto LABEL_15;
  }
  RequestorProcess = (unsigned __int16 *)ListEntry;
LABEL_51:
  if ( RequestorProcess )
  {
    MpDlpCleanupMappedFileNamesArray(RequestorProcess);
    v24 = (char *)MpDlpData + 144;
    ++*((_DWORD *)MpDlpData + 43);
    v25 = *((_WORD *)v24 + 8);
    DepthSList = ExQueryDepthSList((PSLIST_HEADER)v24);
    _mm_lfence();
    if ( DepthSList < v25 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)v24, (PSLIST_ENTRY)RequestorProcess);
    }
    else
    {
      ++*((_DWORD *)v24 + 8);
      (*((void (__fastcall **)(unsigned __int16 *, char *))v24 + 7))(RequestorProcess, v24);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14006e7d0  mov     rax, rsp
0x14006e7d3  mov     [rax+18h], rbx
0x14006e7d7  mov     [rax+20h], r9d
0x14006e7db  mov     [rax+10h], rdx
0x14006e7df  mov     [rax+8], rcx
0x14006e7e3  push    rbp
0x14006e7e4  push    rsi
0x14006e7e5  push    rdi
0x14006e7e6  push    r12
0x14006e7e8  push    r13
0x14006e7ea  push    r14
0x14006e7ec  push    r15
0x14006e7ee  mov     rbp, rsp
0x14006e7f1  sub     rsp, 50h
0x14006e7f5  xor     r15d, r15d
0x14006e7f8  mov     rdx, r8
0x14006e7fb  mov     r14d, r15d
0x14006e7fe  mov     [rbp+var_1C], r15d
0x14006e802  mov     [rbp+FileNameInformation], r15
0x14006e806  mov     r12d, r15d
0x14006e809  mov     [rbp+var_20], r15b
0x14006e80d  mov     edi, r15d
0x14006e810  mov     [rbp+ListEntry], r15
0x14006e814  mov     esi, r9d
0x14006e817  mov     r13, r8
0x14006e81a  mov     rbx, rcx
0x14006e81d  call    MpDlpIsEnabled
0x14006e822  test    al, al
0x14006e824  jz      loc_14006EB64
0x14006e82a  mov     rcx, r13
0x14006e82d  call    MpDlpIsProtectedProcess
0x14006e832  test    al, al
0x14006e834  jnz     loc_14006E8C4
0x14006e83a  cmp     [rbp+arg_20], 1
0x14006e83e  ja      loc_14006EB64
0x14006e844  test    rbx, rbx
0x14006e847  jz      short loc_14006E864
0x14006e849  mov     rcx, rbx
0x14006e84c  call    MpGetRequestorProcessIdEx
0x14006e851  cmp     rax, [r13+18h]
0x14006e855  jnz     short loc_14006E864
0x14006e857  mov     rcx, rbx
0x14006e85a  call    MpGetRequestorProcess
0x14006e85f  mov     rdi, rax
0x14006e862  jmp     short loc_14006E88C
0x14006e864  mov     rbx, [r13+18h]
0x14006e868  call    cs:__imp_PsGetCurrentProcessId
0x14006e86f  nop     dword ptr [rax+rax+00h]
0x14006e874  cmp     rax, rbx
0x14006e877  jnz     short loc_14006E888
0x14006e879  call    cs:__imp_IoGetCurrentProcess
0x14006e880  nop     dword ptr [rax+rax+00h]
0x14006e885  mov     rdi, rax
0x14006e888  mov     rbx, [rbp+arg_0]
0x14006e88c  lea     r8, [rbp+ListEntry]
0x14006e890  mov     rdx, r13
0x14006e893  mov     rcx, rdi
0x14006e896  call    MpDlpShouldCheckMappedFileOperation
0x14006e89b  test    al, al
0x14006e89d  jnz     short loc_14006E8C0
0x14006e89f  cmp     dword ptr [r13+0F0h], 14h
0x14006e8a7  jnz     short loc_14006E8B7
0x14006e8a9  mov     ecx, 11Bh
0x14006e8ae  call    MpFcKernelGetValue
0x14006e8b3  test    al, 2
0x14006e8b5  jnz     short loc_14006E8C0
0x14006e8b7  mov     rdi, [rbp+ListEntry]
0x14006e8bb  jmp     loc_14006EAFF
0x14006e8c0  mov     rdi, [rbp+ListEntry]
0x14006e8c4  mov     rax, [rbp+arg_28]
0x14006e8c8  test    rax, rax
0x14006e8cb  jz      short loc_14006E8E3
0x14006e8cd  cmp     r15w, [rax]
0x14006e8d1  jz      short loc_14006E8E3
0x14006e8d3  mov     r15d, 48h ; 'H'
0x14006e8d9  mov     r12, rax
0x14006e8dc  mov     esi, r15d
0x14006e8df  xor     ecx, ecx
0x14006e8e1  jmp     short loc_14006E916
0x14006e8e3  test    rbx, rbx
0x14006e8e6  jz      short loc_14006E906
0x14006e8e8  lea     r9, [rbp+var_20]
0x14006e8ec  mov     edx, esi
0x14006e8ee  lea     r8, [rbp+FileNameInformation]
0x14006e8f2  mov     rcx, rbx; CallbackData
0x14006e8f5  call    MpQueryFileName
0x14006e8fa  test    eax, eax
0x14006e8fc  js      short loc_14006E906
0x14006e8fe  mov     r12, [rbp+FileNameInformation]
0x14006e902  add     r12, 8
0x14006e906  xor     ecx, ecx
0x14006e908  mov     r15d, 48h ; 'H'
0x14006e90e  mov     esi, r15d
0x14006e911  test    r12, r12
0x14006e914  jz      short loc_14006E923
0x14006e916  movzx   eax, word ptr [r12]
0x14006e91b  cmp     cx, ax
0x14006e91e  jz      short loc_14006E923
0x14006e920  lea     esi, [rax+4Ah]
0x14006e923  test    rdi, rdi
0x14006e926  jz      short loc_14006E932
0x14006e928  movzx   eax, word ptr [rdi]
0x14006e92b  test    ax, ax
0x14006e92e  jz      short loc_14006E932
0x14006e930  add     esi, eax
0x14006e932  mov     edx, esi
0x14006e934  mov     ecx, 1
0x14006e939  mov     r8d, 6C64504Dh
0x14006e93f  call    MpAllocatePoolWithTag
0x14006e944  mov     rbx, rax
0x14006e947  test    rax, rax
0x14006e94a  jnz     short loc_14006E99E
0x14006e94c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e953  lea     rax, WPP_GLOBAL_Control
0x14006e95a  cmp     rcx, rax
0x14006e95d  jz      loc_14006EACE
0x14006e963  mov     eax, [rcx+2Ch]
0x14006e966  test    al, 1
0x14006e968  jz      loc_14006EACE
0x14006e96e  mov     r9, gs:188h
0x14006e977  lea     edx, [rbx+32h]
0x14006e97a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e981  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x14006e988  mov     [rsp+50h+var_30], 0C000009Ah
0x14006e990  mov     rcx, [rcx+18h]
0x14006e994  call    WPP_SF_qD
0x14006e999  jmp     loc_14006EACE
0x14006e99e  mov     dword ptr [rax], 501A5h
0x14006e9a4  mov     [rax+4], esi
0x14006e9a7  mov     rax, [rbp+arg_8]
0x14006e9ab  test    rax, rax
0x14006e9ae  jz      short loc_14006E9B6
0x14006e9b0  mov     rdx, [rax+20h]
0x14006e9b4  jmp     short loc_14006E9B9
0x14006e9b6  mov     rdx, r14
0x14006e9b9  mov     rcx, [rbp+arg_0]
0x14006e9bd  lea     r8, [rbx+8]
0x14006e9c1  call    MpGetPriorityInfo
0x14006e9c6  mov     eax, [r13+18h]
0x14006e9ca  mov     [rbx+38h], eax
0x14006e9cd  mov     rcx, [r13+20h]
0x14006e9d1  call    MpFileTimeToUlong64
0x14006e9d6  lea     r8, [rbx+3Ch]
0x14006e9da  mov     [rbx+18h], rax
0x14006e9de  call    MpQuerySessionId
0x14006e9e3  mov     eax, [rbp+arg_20]
0x14006e9e6  mov     esi, [rbp+arg_18]
0x14006e9e9  mov     [rbx+40h], eax
0x14006e9ec  mov     [rbx+44h], esi
0x14006e9ef  test    r12, r12
0x14006e9f2  jz      short loc_14006EA33
0x14006e9f4  cmp     r14w, [r12]
0x14006e9f9  jz      short loc_14006EA33
0x14006e9fb  mov     [rbx+20h], r15
0x14006e9ff  lea     rcx, [rbx+48h]; void *
0x14006ea03  movzx   r8d, word ptr [r12]; Size
0x14006ea08  mov     rdx, [r12+8]; Src
0x14006ea0d  call    memmove
0x14006ea12  movzx   eax, word ptr [r12]
0x14006ea17  shr     rax, 1
0x14006ea1a  lea     rcx, [rbx+rax*2]
0x14006ea1e  mov     rax, [rbx+20h]
0x14006ea22  mov     [rcx+rax], r14w
0x14006ea27  movzx   eax, word ptr [r12]
0x14006ea2c  mov     [rbx+30h], eax
0x14006ea2f  lea     r15, [rax+4Ah]
0x14006ea33  test    rdi, rdi
0x14006ea36  jz      short loc_14006EA59
0x14006ea38  cmp     [rdi], r14w
0x14006ea3c  jz      short loc_14006EA59
0x14006ea3e  mov     [rbx+28h], r15
0x14006ea42  lea     rcx, [rbx+r15]; void *
0x14006ea46  movzx   r8d, word ptr [rdi]; Size
0x14006ea4a  mov     rdx, [rdi+8]; Src
0x14006ea4e  call    memmove
0x14006ea53  movzx   eax, word ptr [rdi]
0x14006ea56  mov     [rbx+34h], eax
0x14006ea59  mov     r9, [rbp+arg_30]
0x14006ea5d  lea     r8, [rbp+var_1C]
0x14006ea61  mov     rdx, rbx
0x14006ea64  mov     ecx, esi
0x14006ea66  call    MpDlpQueryService
0x14006ea6b  xor     r15d, r15d
0x14006ea6e  mov     r8d, eax
0x14006ea71  test    eax, eax
0x14006ea73  jns     short loc_14006EAC2
0x14006ea75  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ea7c  lea     rax, WPP_GLOBAL_Control
0x14006ea83  cmp     rcx, rax
0x14006ea86  jz      short loc_14006EABC
0x14006ea88  mov     ecx, [rcx+2Ch]
0x14006ea8b  test    cl, 1
0x14006ea8e  jz      short loc_14006EABC
0x14006ea90  lfence
0x14006ea93  mov     r9, gs:188h
0x14006ea9c  lea     edx, [r15+33h]
0x14006eaa0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006eaa7  mov     [rsp+50h+var_30], r8d
0x14006eaac  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x14006eab3  mov     rcx, [rcx+18h]
0x14006eab7  call    WPP_SF_qD
0x14006eabc  mov     r14d, [rbp+var_1C]
0x14006eac0  jmp     short loc_14006EACE
0x14006eac2  mov     r14d, [rbp+var_1C]
0x14006eac6  cmp     r14d, 3
0x14006eaca  cmovz   r14d, r15d
0x14006eace  mov     rax, [rbp+FileNameInformation]
0x14006ead2  test    rax, rax
0x14006ead5  jz      short loc_14006EAE6
0x14006ead7  mov     rcx, rax; FileNameInformation
0x14006eada  call    cs:__imp_FltReleaseFileNameInformation
0x14006eae1  nop     dword ptr [rax+rax+00h]
0x14006eae6  test    rbx, rbx
0x14006eae9  jz      short loc_14006EAFF
0x14006eaeb  mov     edx, 6C64504Dh; Tag
0x14006eaf0  mov     rcx, rbx; P
0x14006eaf3  call    cs:__imp_ExFreePoolWithTag
0x14006eafa  nop     dword ptr [rax+rax+00h]
0x14006eaff  test    rdi, rdi
0x14006eb02  jz      short loc_14006EB5F
0x14006eb04  mov     rcx, rdi
0x14006eb07  call    MpDlpCleanupMappedFileNamesArray
0x14006eb0c  mov     rsi, cs:MpDlpData
0x14006eb13  add     rsi, 90h
0x14006eb1a  mov     rcx, rsi; SListHead
0x14006eb1d  inc     dword ptr [rsi+1Ch]
0x14006eb20  movzx   ebx, word ptr [rsi+10h]
0x14006eb24  call    cs:__imp_ExQueryDepthSList
0x14006eb2b  nop     dword ptr [rax+rax+00h]
0x14006eb30  lfence
0x14006eb33  cmp     ax, bx
0x14006eb36  jb      short loc_14006EB4D
0x14006eb38  inc     dword ptr [rsi+20h]
0x14006eb3b  mov     rdx, rsi
0x14006eb3e  mov     rax, [rsi+38h]
0x14006eb42  mov     rcx, rdi
0x14006eb45  call    cs:__guard_dispatch_icall_fptr
0x14006eb4b  jmp     short loc_14006EB5F
0x14006eb4d  mov     rdx, rdi; ListEntry
0x14006eb50  mov     rcx, rsi; ListHead
0x14006eb53  call    cs:__imp_ExpInterlockedPushEntrySList
0x14006eb5a  nop     dword ptr [rax+rax+00h]
0x14006eb5f  mov     eax, r14d
0x14006eb62  jmp     short loc_14006EB66
0x14006eb64  xor     eax, eax
0x14006eb66  mov     rbx, [rsp+50h+arg_10]
0x14006eb6e  add     rsp, 50h
0x14006eb72  pop     r15
0x14006eb74  pop     r14
0x14006eb76  pop     r13
0x14006eb78  pop     r12
0x14006eb7a  pop     rdi
0x14006eb7b  pop     rsi
0x14006eb7c  pop     rbp
0x14006eb7d  retn
```
