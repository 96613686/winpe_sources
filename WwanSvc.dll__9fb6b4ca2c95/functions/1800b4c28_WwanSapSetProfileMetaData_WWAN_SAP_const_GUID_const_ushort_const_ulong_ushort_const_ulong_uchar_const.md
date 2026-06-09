# WwanSapSetProfileMetaData(WWAN_SAP const *,_GUID const *,ushort const *,ulong,ushort const *,ulong,uchar const *)

- ea: `0x1800b4c28`
- end: `0x1800b4e6c`
- name: `?WwanSapSetProfileMetaData@@YAKPEBUWWAN_SAP@@PEBU_GUID@@PEBGK2KPEBE@Z`
- size: `580`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800ad680`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b4c28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4e24`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4e24`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b4c5a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b4c5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4e2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4e2e`

## string_xrefs

- `0x1800b4c85`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b4e43`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`

## pseudocode

```c
__int64 __fastcall WwanSapSetProfileMetaData(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        MessageParams *a3,
        unsigned int a4,
        MessageParams *a5,
        unsigned int a6,
        MessageParams *a7)
{
  MessageParams *v7; // r12
  MessageParams *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v12; // rax
  MessageParams *v13; // rsi
  char *v14; // rdi
  MessageParams **v15; // rdx
  unsigned int **v16; // rdx
  _QWORD *v17; // rdx
  MessageParams **v18; // rdx
  _QWORD *v19; // rdx
  MessageParams **v20; // rdx
  _QWORD *v21; // rdx
  MessageParams **v22; // rdx
  unsigned int v23; // edx
  unsigned int v24; // ebx
  DWORD v25; // eax
  MessageParams *v27; // [rsp+60h] [rbp+40h] BYREF
  MessageParams *v28; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v29; // [rsp+78h] [rbp+58h] BYREF

  v27 = a1;
  v7 = (MessageParams *)a4;
  v29 = 0;
  EventW = (MessageParams *)CreateEventW(0, 1, 0, 0);
  v28 = EventW;
  if ( EventW == (MessageParams *)-1LL || (MessageParams *)((char *)EventW + 1) == (MessageParams *)1 )
  {
    LastError = GetLastError();
    __FatalError(
      "onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c",
      0x559u,
      "Failure while creating an Event",
      LastError);
  }
  v27 = (MessageParams *)operator new(0x48u);
  v12 = MessageParams::MessageParams(v27);
  v13 = v12;
  v14 = (char *)v12 + 48;
  v27 = EventW;
  v15 = (MessageParams **)*((_QWORD *)v12 + 7);
  if ( v15 == *((MessageParams ***)v12 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v12 + 48, v15, &v27);
  }
  else
  {
    *v15 = EventW;
    *((_QWORD *)v12 + 7) += 8LL;
  }
  v27 = (MessageParams *)&v29;
  v16 = (unsigned int **)*((_QWORD *)v14 + 1);
  if ( v16 == *((unsigned int ***)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v16, &v27);
  }
  else
  {
    *v16 = &v29;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = (MessageParams *)a2;
  v17 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v17 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v17, &v27);
  }
  else
  {
    *v17 = a2;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = a3;
  v18 = (MessageParams **)*((_QWORD *)v14 + 1);
  if ( v18 == *((MessageParams ***)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v18, &v27);
  }
  else
  {
    *v18 = a3;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = v7;
  v19 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v19 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v19, &v27);
  }
  else
  {
    *v19 = v7;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = a5;
  v20 = (MessageParams **)*((_QWORD *)v14 + 1);
  if ( v20 == *((MessageParams ***)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v20, &v27);
  }
  else
  {
    *v20 = a5;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = (MessageParams *)a6;
  v21 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v21 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v21, &v27);
  }
  else
  {
    *v21 = a6;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = a7;
  v22 = (MessageParams **)*((_QWORD *)v14 + 1);
  if ( v22 == *((MessageParams ***)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v22, &v27);
  }
  else
  {
    *v22 = a7;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(20, v13) )
  {
    if ( v13 )
      MessageParams::`scalar deleting destructor'(v13, v23);
    WwanLog::Error("WwanSapSetProfileMetaData", 0, L"Notification dispatcher: Failed to Queue Message");
    v24 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v25 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x570u, "WaitForSingleObject", v25);
    }
    v24 = v29;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v28);
  return v24;
}

```

## disassembly

```asm
0x1800b4c28  mov     [rsp-38h+arg_0], rcx
0x1800b4c2d  push    rbp
0x1800b4c2e  push    rbx
0x1800b4c2f  push    rsi
0x1800b4c30  push    rdi
0x1800b4c31  push    r12
0x1800b4c33  push    r14
0x1800b4c35  push    r15
0x1800b4c37  mov     rbp, rsp
0x1800b4c3a  sub     rsp, 20h
0x1800b4c3e  mov     r12d, r9d
0x1800b4c41  mov     r15, r8
0x1800b4c44  mov     r14, rdx
0x1800b4c47  mov     [rbp+arg_18], 0
0x1800b4c4e  xor     r9d, r9d; lpName
0x1800b4c51  xor     r8d, r8d; bInitialState
0x1800b4c54  lea     edx, [r9+1]; bManualReset
0x1800b4c58  xor     ecx, ecx; lpEventAttributes
0x1800b4c5a  call    cs:__imp_CreateEventW
0x1800b4c60  mov     rbx, rax
0x1800b4c63  mov     [rbp+arg_8], rax
0x1800b4c67  inc     rax
0x1800b4c6a  cmp     rax, 1
0x1800b4c6e  ja      short loc_1800B4C91
0x1800b4c70  call    cs:__imp_GetLastError
0x1800b4c76  mov     r9d, eax; unsigned int
0x1800b4c79  lea     r8, aFailureWhileCr; "Failure while creating an Event"
0x1800b4c80  mov     edx, 559h; unsigned int
0x1800b4c85  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b4c8c  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b4c91  mov     ecx, 48h ; 'H'; Size
0x1800b4c96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b4c9b  mov     [rbp+arg_0], rax
0x1800b4c9f  mov     rcx, rax; this
0x1800b4ca2  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b4ca7  mov     rsi, rax
0x1800b4caa  lea     rdi, [rax+30h]
0x1800b4cae  mov     [rbp+arg_0], rbx
0x1800b4cb2  mov     rdx, [rdi+8]
0x1800b4cb6  cmp     rdx, [rdi+10h]
0x1800b4cba  jz      short loc_1800B4CC6
0x1800b4cbc  mov     [rdx], rbx
0x1800b4cbf  add     qword ptr [rdi+8], 8
0x1800b4cc4  jmp     short loc_1800B4CD2
0x1800b4cc6  lea     r8, [rbp+arg_0]
0x1800b4cca  mov     rcx, rdi
0x1800b4ccd  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4cd2  lea     rax, [rbp+arg_18]
0x1800b4cd6  mov     [rbp+arg_0], rax
0x1800b4cda  mov     rdx, [rdi+8]
0x1800b4cde  cmp     rdx, [rdi+10h]
0x1800b4ce2  jz      short loc_1800B4CF2
0x1800b4ce4  lea     rax, [rbp+arg_18]
0x1800b4ce8  mov     [rdx], rax
0x1800b4ceb  add     qword ptr [rdi+8], 8
0x1800b4cf0  jmp     short loc_1800B4CFE
0x1800b4cf2  lea     r8, [rbp+arg_0]
0x1800b4cf6  mov     rcx, rdi
0x1800b4cf9  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4cfe  mov     [rbp+arg_0], r14
0x1800b4d02  mov     rdx, [rdi+8]
0x1800b4d06  cmp     rdx, [rdi+10h]
0x1800b4d0a  jz      short loc_1800B4D16
0x1800b4d0c  mov     [rdx], r14
0x1800b4d0f  add     qword ptr [rdi+8], 8
0x1800b4d14  jmp     short loc_1800B4D22
0x1800b4d16  lea     r8, [rbp+arg_0]
0x1800b4d1a  mov     rcx, rdi
0x1800b4d1d  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4d22  mov     [rbp+arg_0], r15
0x1800b4d26  mov     rdx, [rdi+8]
0x1800b4d2a  cmp     rdx, [rdi+10h]
0x1800b4d2e  jz      short loc_1800B4D3A
0x1800b4d30  mov     [rdx], r15
0x1800b4d33  add     qword ptr [rdi+8], 8
0x1800b4d38  jmp     short loc_1800B4D46
0x1800b4d3a  lea     r8, [rbp+arg_0]
0x1800b4d3e  mov     rcx, rdi
0x1800b4d41  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4d46  mov     rax, r12
0x1800b4d49  mov     [rbp+arg_0], rax
0x1800b4d4d  mov     rdx, [rdi+8]
0x1800b4d51  cmp     rdx, [rdi+10h]
0x1800b4d55  jz      short loc_1800B4D61
0x1800b4d57  mov     [rdx], rax
0x1800b4d5a  add     qword ptr [rdi+8], 8
0x1800b4d5f  jmp     short loc_1800B4D6D
0x1800b4d61  lea     r8, [rbp+arg_0]
0x1800b4d65  mov     rcx, rdi
0x1800b4d68  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4d6d  mov     rax, [rbp+arg_20]
0x1800b4d71  mov     [rbp+arg_0], rax
0x1800b4d75  mov     rdx, [rdi+8]
0x1800b4d79  cmp     rdx, [rdi+10h]
0x1800b4d7d  jz      short loc_1800B4D89
0x1800b4d7f  mov     [rdx], rax
0x1800b4d82  add     qword ptr [rdi+8], 8
0x1800b4d87  jmp     short loc_1800B4D95
0x1800b4d89  lea     r8, [rbp+arg_0]
0x1800b4d8d  mov     rcx, rdi
0x1800b4d90  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4d95  mov     eax, [rbp+arg_28]
0x1800b4d98  mov     [rbp+arg_0], rax
0x1800b4d9c  mov     rdx, [rdi+8]
0x1800b4da0  cmp     rdx, [rdi+10h]
0x1800b4da4  jz      short loc_1800B4DB0
0x1800b4da6  mov     [rdx], rax
0x1800b4da9  add     qword ptr [rdi+8], 8
0x1800b4dae  jmp     short loc_1800B4DBC
0x1800b4db0  lea     r8, [rbp+arg_0]
0x1800b4db4  mov     rcx, rdi
0x1800b4db7  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4dbc  mov     rax, [rbp+arg_30]
0x1800b4dc0  mov     [rbp+arg_0], rax
0x1800b4dc4  mov     rdx, [rdi+8]
0x1800b4dc8  cmp     rdx, [rdi+10h]
0x1800b4dcc  jz      short loc_1800B4DD8
0x1800b4dce  mov     [rdx], rax
0x1800b4dd1  add     qword ptr [rdi+8], 8
0x1800b4dd6  jmp     short loc_1800B4DE4
0x1800b4dd8  lea     r8, [rbp+arg_0]
0x1800b4ddc  mov     rcx, rdi
0x1800b4ddf  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4de4  mov     rdx, rsi
0x1800b4de7  mov     ecx, 14h
0x1800b4dec  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b4df1  test    eax, eax
0x1800b4df3  jz      short loc_1800B4E1E
0x1800b4df5  test    rsi, rsi
0x1800b4df8  jz      short loc_1800B4E02
0x1800b4dfa  mov     rcx, rsi; this
0x1800b4dfd  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b4e02  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b4e09  xor     edx, edx; struct _GUID *
0x1800b4e0b  lea     rcx, aWwansapsetprof; "WwanSapSetProfileMetaData"
0x1800b4e12  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b4e17  mov     ebx, 1Fh
0x1800b4e1c  jmp     short loc_1800B4E52
0x1800b4e1e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b4e21  mov     rcx, rbx; hHandle
0x1800b4e24  call    cs:__imp_WaitForSingleObject
0x1800b4e2a  test    eax, eax
0x1800b4e2c  jz      short loc_1800B4E4F
0x1800b4e2e  call    cs:__imp_GetLastError
0x1800b4e34  mov     r9d, eax; unsigned int
0x1800b4e37  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b4e3e  mov     edx, 570h; unsigned int
0x1800b4e43  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b4e4a  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b4e4f  mov     ebx, [rbp+arg_18]
0x1800b4e52  lea     rcx, [rbp+arg_8]
0x1800b4e56  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b4e5b  mov     eax, ebx
0x1800b4e5d  add     rsp, 20h
0x1800b4e61  pop     r15
0x1800b4e63  pop     r14
0x1800b4e65  pop     r12
0x1800b4e67  pop     rdi
0x1800b4e68  pop     rsi
0x1800b4e69  pop     rbx
0x1800b4e6a  pop     rbp
0x1800b4e6b  retn
```
