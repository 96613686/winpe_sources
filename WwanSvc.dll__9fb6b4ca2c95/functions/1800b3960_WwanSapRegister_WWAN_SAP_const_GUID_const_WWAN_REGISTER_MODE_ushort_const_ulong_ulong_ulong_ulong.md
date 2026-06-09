# WwanSapRegister(WWAN_SAP const *,_GUID const *,_WWAN_REGISTER_MODE,ushort const *,ulong,ulong,ulong *,ulong *)

- ea: `0x1800b3960`
- end: `0x1800b3bcb`
- name: `?WwanSapRegister@@YAKPEBUWWAN_SAP@@PEBU_GUID@@W4_WWAN_REGISTER_MODE@@PEBGKKPEAK4@Z`
- size: `619`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800ad2a0`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b3960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b3b83`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b3b83`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b3992`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b3992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b39a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b39a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3b8d`

## string_xrefs

- `0x1800b39bd`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b3ba2`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b39b1`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapRegister(
        MessageParams *a1,
        MessageParams *a2,
        unsigned int a3,
        MessageParams *a4,
        unsigned int a5,
        unsigned int a6,
        MessageParams *a7,
        MessageParams *a8)
{
  unsigned __int64 v9; // r12
  MessageParams *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v13; // rax
  MessageParams *v14; // rsi
  char *v15; // rdi
  MessageParams **v16; // rdx
  unsigned int **v17; // rdx
  MessageParams **v18; // rdx
  unsigned __int64 *v19; // rdx
  MessageParams **v20; // rdx
  _QWORD *v21; // rdx
  _QWORD *v22; // rdx
  MessageParams **v23; // rdx
  MessageParams **v24; // rdx
  unsigned int v25; // edx
  unsigned int v26; // ebx
  DWORD v27; // eax
  unsigned __int64 v29; // [rsp+60h] [rbp+40h] BYREF
  MessageParams *v30; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v31; // [rsp+70h] [rbp+50h] BYREF

  v29 = (unsigned __int64)a1;
  v9 = a3;
  v31 = 0;
  EventW = (MessageParams *)CreateEventW(0, 1, 0, 0);
  v30 = EventW;
  if ( EventW == (MessageParams *)-1LL || (MessageParams *)((char *)EventW + 1) == (MessageParams *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x29Au, "CreateEvent", LastError);
  }
  v29 = (unsigned __int64)operator new(0x48u);
  v13 = MessageParams::MessageParams((MessageParams *)v29);
  v14 = v13;
  v15 = (char *)v13 + 48;
  v29 = (unsigned __int64)EventW;
  v16 = (MessageParams **)*((_QWORD *)v13 + 7);
  if ( v16 == *((MessageParams ***)v13 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v13 + 48, v16, &v29);
  }
  else
  {
    *v16 = EventW;
    *((_QWORD *)v13 + 7) += 8LL;
  }
  v29 = (unsigned __int64)&v31;
  v17 = (unsigned int **)*((_QWORD *)v15 + 1);
  if ( v17 == *((unsigned int ***)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v17, &v29);
  }
  else
  {
    *v17 = &v31;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v29 = (unsigned __int64)a2;
  v18 = (MessageParams **)*((_QWORD *)v15 + 1);
  if ( v18 == *((MessageParams ***)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v18, &v29);
  }
  else
  {
    *v18 = a2;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v29 = v9;
  v19 = (unsigned __int64 *)*((_QWORD *)v15 + 1);
  if ( v19 == *((unsigned __int64 **)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v19, &v29);
  }
  else
  {
    *v19 = v9;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v29 = (unsigned __int64)a4;
  v20 = (MessageParams **)*((_QWORD *)v15 + 1);
  if ( v20 == *((MessageParams ***)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v20, &v29);
  }
  else
  {
    *v20 = a4;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v29 = a5;
  v21 = (_QWORD *)*((_QWORD *)v15 + 1);
  if ( v21 == *((_QWORD **)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v21, &v29);
  }
  else
  {
    *v21 = a5;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v29 = a6;
  v22 = (_QWORD *)*((_QWORD *)v15 + 1);
  if ( v22 == *((_QWORD **)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v22, &v29);
  }
  else
  {
    *v22 = a6;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v29 = (unsigned __int64)a7;
  v23 = (MessageParams **)*((_QWORD *)v15 + 1);
  if ( v23 == *((MessageParams ***)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v23, &v29);
  }
  else
  {
    *v23 = a7;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v29 = (unsigned __int64)a8;
  v24 = (MessageParams **)*((_QWORD *)v15 + 1);
  if ( v24 == *((MessageParams ***)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v24, &v29);
  }
  else
  {
    *v24 = a8;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(5, v14) )
  {
    if ( v14 )
      MessageParams::`scalar deleting destructor'(v14, v25);
    WwanLog::Error("WwanSapRegister", 0, L"Notification dispatcher: Failed to Queue Message");
    v26 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v27 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x2B2u, "WaitForSingleObject", v27);
    }
    v26 = v31;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v30);
  return v26;
}

```

## disassembly

```asm
0x1800b3960  mov     [rsp-38h+arg_0], rcx
0x1800b3965  push    rbp
0x1800b3966  push    rbx
0x1800b3967  push    rsi
0x1800b3968  push    rdi
0x1800b3969  push    r12
0x1800b396b  push    r14
0x1800b396d  push    r15
0x1800b396f  mov     rbp, rsp
0x1800b3972  sub     rsp, 20h
0x1800b3976  mov     r15, r9
0x1800b3979  mov     r12d, r8d
0x1800b397c  mov     r14, rdx
0x1800b397f  mov     [rbp+arg_10], 0
0x1800b3986  xor     r9d, r9d; lpName
0x1800b3989  xor     r8d, r8d; bInitialState
0x1800b398c  lea     edx, [r9+1]; bManualReset
0x1800b3990  xor     ecx, ecx; lpEventAttributes
0x1800b3992  call    cs:__imp_CreateEventW
0x1800b3998  mov     rbx, rax
0x1800b399b  mov     [rbp+arg_8], rax
0x1800b399f  inc     rax
0x1800b39a2  cmp     rax, 1
0x1800b39a6  ja      short loc_1800B39C9
0x1800b39a8  call    cs:__imp_GetLastError
0x1800b39ae  mov     r9d, eax; unsigned int
0x1800b39b1  lea     r8, aCreateevent; "CreateEvent"
0x1800b39b8  mov     edx, 29Ah; unsigned int
0x1800b39bd  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b39c4  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b39c9  mov     ecx, 48h ; 'H'; Size
0x1800b39ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b39d3  mov     [rbp+arg_0], rax
0x1800b39d7  mov     rcx, rax; this
0x1800b39da  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b39df  mov     rsi, rax
0x1800b39e2  lea     rdi, [rax+30h]
0x1800b39e6  mov     [rbp+arg_0], rbx
0x1800b39ea  mov     rdx, [rdi+8]
0x1800b39ee  cmp     rdx, [rdi+10h]
0x1800b39f2  jz      short loc_1800B39FE
0x1800b39f4  mov     [rdx], rbx
0x1800b39f7  add     qword ptr [rdi+8], 8
0x1800b39fc  jmp     short loc_1800B3A0A
0x1800b39fe  lea     r8, [rbp+arg_0]
0x1800b3a02  mov     rcx, rdi
0x1800b3a05  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3a0a  lea     rax, [rbp+arg_10]
0x1800b3a0e  mov     [rbp+arg_0], rax
0x1800b3a12  mov     rdx, [rdi+8]
0x1800b3a16  cmp     rdx, [rdi+10h]
0x1800b3a1a  jz      short loc_1800B3A2A
0x1800b3a1c  lea     rax, [rbp+arg_10]
0x1800b3a20  mov     [rdx], rax
0x1800b3a23  add     qword ptr [rdi+8], 8
0x1800b3a28  jmp     short loc_1800B3A36
0x1800b3a2a  lea     r8, [rbp+arg_0]
0x1800b3a2e  mov     rcx, rdi
0x1800b3a31  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3a36  mov     [rbp+arg_0], r14
0x1800b3a3a  mov     rdx, [rdi+8]
0x1800b3a3e  cmp     rdx, [rdi+10h]
0x1800b3a42  jz      short loc_1800B3A4E
0x1800b3a44  mov     [rdx], r14
0x1800b3a47  add     qword ptr [rdi+8], 8
0x1800b3a4c  jmp     short loc_1800B3A5A
0x1800b3a4e  lea     r8, [rbp+arg_0]
0x1800b3a52  mov     rcx, rdi
0x1800b3a55  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3a5a  mov     rax, r12
0x1800b3a5d  mov     [rbp+arg_0], rax
0x1800b3a61  mov     rdx, [rdi+8]
0x1800b3a65  cmp     rdx, [rdi+10h]
0x1800b3a69  jz      short loc_1800B3A75
0x1800b3a6b  mov     [rdx], rax
0x1800b3a6e  add     qword ptr [rdi+8], 8
0x1800b3a73  jmp     short loc_1800B3A81
0x1800b3a75  lea     r8, [rbp+arg_0]
0x1800b3a79  mov     rcx, rdi
0x1800b3a7c  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3a81  mov     [rbp+arg_0], r15
0x1800b3a85  mov     rdx, [rdi+8]
0x1800b3a89  cmp     rdx, [rdi+10h]
0x1800b3a8d  jz      short loc_1800B3A99
0x1800b3a8f  mov     [rdx], r15
0x1800b3a92  add     qword ptr [rdi+8], 8
0x1800b3a97  jmp     short loc_1800B3AA5
0x1800b3a99  lea     r8, [rbp+arg_0]
0x1800b3a9d  mov     rcx, rdi
0x1800b3aa0  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3aa5  mov     eax, [rbp+arg_20]
0x1800b3aa8  mov     [rbp+arg_0], rax
0x1800b3aac  mov     rdx, [rdi+8]
0x1800b3ab0  cmp     rdx, [rdi+10h]
0x1800b3ab4  jz      short loc_1800B3AC0
0x1800b3ab6  mov     [rdx], rax
0x1800b3ab9  add     qword ptr [rdi+8], 8
0x1800b3abe  jmp     short loc_1800B3ACC
0x1800b3ac0  lea     r8, [rbp+arg_0]
0x1800b3ac4  mov     rcx, rdi
0x1800b3ac7  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3acc  mov     eax, [rbp+arg_28]
0x1800b3acf  mov     [rbp+arg_0], rax
0x1800b3ad3  mov     rdx, [rdi+8]
0x1800b3ad7  cmp     rdx, [rdi+10h]
0x1800b3adb  jz      short loc_1800B3AE7
0x1800b3add  mov     [rdx], rax
0x1800b3ae0  add     qword ptr [rdi+8], 8
0x1800b3ae5  jmp     short loc_1800B3AF3
0x1800b3ae7  lea     r8, [rbp+arg_0]
0x1800b3aeb  mov     rcx, rdi
0x1800b3aee  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3af3  mov     rax, [rbp+arg_30]
0x1800b3af7  mov     [rbp+arg_0], rax
0x1800b3afb  mov     rdx, [rdi+8]
0x1800b3aff  cmp     rdx, [rdi+10h]
0x1800b3b03  jz      short loc_1800B3B0F
0x1800b3b05  mov     [rdx], rax
0x1800b3b08  add     qword ptr [rdi+8], 8
0x1800b3b0d  jmp     short loc_1800B3B1B
0x1800b3b0f  lea     r8, [rbp+arg_0]
0x1800b3b13  mov     rcx, rdi
0x1800b3b16  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3b1b  mov     rax, [rbp+arg_38]
0x1800b3b1f  mov     [rbp+arg_0], rax
0x1800b3b23  mov     rdx, [rdi+8]
0x1800b3b27  cmp     rdx, [rdi+10h]
0x1800b3b2b  jz      short loc_1800B3B37
0x1800b3b2d  mov     [rdx], rax
0x1800b3b30  add     qword ptr [rdi+8], 8
0x1800b3b35  jmp     short loc_1800B3B43
0x1800b3b37  lea     r8, [rbp+arg_0]
0x1800b3b3b  mov     rcx, rdi
0x1800b3b3e  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3b43  mov     rdx, rsi
0x1800b3b46  mov     ecx, 5
0x1800b3b4b  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b3b50  test    eax, eax
0x1800b3b52  jz      short loc_1800B3B7D
0x1800b3b54  test    rsi, rsi
0x1800b3b57  jz      short loc_1800B3B61
0x1800b3b59  mov     rcx, rsi; this
0x1800b3b5c  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b3b61  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b3b68  xor     edx, edx; struct _GUID *
0x1800b3b6a  lea     rcx, aWwansapregiste; "WwanSapRegister"
0x1800b3b71  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b3b76  mov     ebx, 1Fh
0x1800b3b7b  jmp     short loc_1800B3BB1
0x1800b3b7d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b3b80  mov     rcx, rbx; hHandle
0x1800b3b83  call    cs:__imp_WaitForSingleObject
0x1800b3b89  test    eax, eax
0x1800b3b8b  jz      short loc_1800B3BAE
0x1800b3b8d  call    cs:__imp_GetLastError
0x1800b3b93  mov     r9d, eax; unsigned int
0x1800b3b96  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b3b9d  mov     edx, 2B2h; unsigned int
0x1800b3ba2  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b3ba9  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b3bae  mov     ebx, [rbp+arg_10]
0x1800b3bb1  lea     rcx, [rbp+arg_8]
0x1800b3bb5  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b3bba  mov     eax, ebx
0x1800b3bbc  add     rsp, 20h
0x1800b3bc0  pop     r15
0x1800b3bc2  pop     r14
0x1800b3bc4  pop     r12
0x1800b3bc6  pop     rdi
0x1800b3bc7  pop     rsi
0x1800b3bc8  pop     rbx
0x1800b3bc9  pop     rbp
0x1800b3bca  retn
```
