# WwanSapScan(WWAN_SAP const *,_GUID const *,ulong *,ulong *,ulong)

- ea: `0x1800b3df4`
- end: `0x1800b3fe5`
- name: `?WwanSapScan@@YAKPEBUWWAN_SAP@@PEBU_GUID@@PEAK2K@Z`
- size: `497`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, unsigned int *, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800ad3e0`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b3df4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b3f9d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b3f9d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b3e26`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b3e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3e3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3fa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3e3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3fa7`

## string_xrefs

- `0x1800b3e51`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b3fbc`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b3e45`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapScan(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        MessageParams *a3,
        MessageParams *a4,
        unsigned int a5)
{
  MessageParams *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v10; // rax
  MessageParams *v11; // rsi
  char *v12; // rdi
  MessageParams **v13; // rdx
  unsigned int **v14; // rdx
  _QWORD *v15; // rdx
  MessageParams **v16; // rdx
  MessageParams **v17; // rdx
  _QWORD *v18; // rdx
  unsigned int v19; // edx
  unsigned int v20; // ebx
  DWORD v21; // eax
  unsigned int v23; // [rsp+60h] [rbp+40h] BYREF
  int v24; // [rsp+64h] [rbp+44h]
  MessageParams *v25; // [rsp+68h] [rbp+48h] BYREF
  MessageParams *v26; // [rsp+70h] [rbp+50h] BYREF

  v24 = HIDWORD(a1);
  v23 = 0;
  EventW = (MessageParams *)CreateEventW(0, 1, 0, 0);
  v26 = EventW;
  if ( EventW == (MessageParams *)-1LL || (MessageParams *)((char *)EventW + 1) == (MessageParams *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x270u, "CreateEvent", LastError);
  }
  v25 = (MessageParams *)operator new(0x48u);
  v10 = MessageParams::MessageParams(v25);
  v11 = v10;
  v12 = (char *)v10 + 48;
  v25 = EventW;
  v13 = (MessageParams **)*((_QWORD *)v10 + 7);
  if ( v13 == *((MessageParams ***)v10 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v10 + 48, v13, &v25);
  }
  else
  {
    *v13 = EventW;
    *((_QWORD *)v10 + 7) += 8LL;
  }
  v25 = (MessageParams *)&v23;
  v14 = (unsigned int **)*((_QWORD *)v12 + 1);
  if ( v14 == *((unsigned int ***)v12 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v12, v14, &v25);
  }
  else
  {
    *v14 = &v23;
    *((_QWORD *)v12 + 1) += 8LL;
  }
  v25 = (MessageParams *)a2;
  v15 = (_QWORD *)*((_QWORD *)v12 + 1);
  if ( v15 == *((_QWORD **)v12 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v12, v15, &v25);
  }
  else
  {
    *v15 = a2;
    *((_QWORD *)v12 + 1) += 8LL;
  }
  v25 = a3;
  v16 = (MessageParams **)*((_QWORD *)v12 + 1);
  if ( v16 == *((MessageParams ***)v12 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v12, v16, &v25);
  }
  else
  {
    *v16 = a3;
    *((_QWORD *)v12 + 1) += 8LL;
  }
  v25 = a4;
  v17 = (MessageParams **)*((_QWORD *)v12 + 1);
  if ( v17 == *((MessageParams ***)v12 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v12, v17, &v25);
  }
  else
  {
    *v17 = a4;
    *((_QWORD *)v12 + 1) += 8LL;
  }
  v25 = (MessageParams *)a5;
  v18 = (_QWORD *)*((_QWORD *)v12 + 1);
  if ( v18 == *((_QWORD **)v12 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v12, v18, &v25);
  }
  else
  {
    *v18 = a5;
    *((_QWORD *)v12 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(4, v11) )
  {
    if ( v11 )
      MessageParams::`scalar deleting destructor'(v11, v19);
    WwanLog::Error("WwanSapScan", 0, L"Notification dispatcher: Failed to Queue Message");
    v20 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v21 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x285u, "WaitForSingleObject", v21);
    }
    v20 = v23;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v26);
  return v20;
}

```

## disassembly

```asm
0x1800b3df4  mov     [rsp-38h+arg_0], rcx
0x1800b3df9  push    rbp
0x1800b3dfa  push    rbx
0x1800b3dfb  push    rsi
0x1800b3dfc  push    rdi
0x1800b3dfd  push    r12
0x1800b3dff  push    r14
0x1800b3e01  push    r15
0x1800b3e03  mov     rbp, rsp
0x1800b3e06  sub     rsp, 20h
0x1800b3e0a  mov     r12, r9
0x1800b3e0d  mov     r15, r8
0x1800b3e10  mov     r14, rdx
0x1800b3e13  mov     dword ptr [rbp+arg_0], 0
0x1800b3e1a  xor     r9d, r9d; lpName
0x1800b3e1d  xor     r8d, r8d; bInitialState
0x1800b3e20  lea     edx, [r9+1]; bManualReset
0x1800b3e24  xor     ecx, ecx; lpEventAttributes
0x1800b3e26  call    cs:__imp_CreateEventW
0x1800b3e2c  mov     rbx, rax
0x1800b3e2f  mov     [rbp+arg_10], rax
0x1800b3e33  inc     rax
0x1800b3e36  cmp     rax, 1
0x1800b3e3a  ja      short loc_1800B3E5D
0x1800b3e3c  call    cs:__imp_GetLastError
0x1800b3e42  mov     r9d, eax; unsigned int
0x1800b3e45  lea     r8, aCreateevent; "CreateEvent"
0x1800b3e4c  mov     edx, 270h; unsigned int
0x1800b3e51  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b3e58  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b3e5d  mov     ecx, 48h ; 'H'; Size
0x1800b3e62  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b3e67  mov     [rbp+arg_8], rax
0x1800b3e6b  mov     rcx, rax; this
0x1800b3e6e  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b3e73  mov     rsi, rax
0x1800b3e76  lea     rdi, [rax+30h]
0x1800b3e7a  mov     [rbp+arg_8], rbx
0x1800b3e7e  mov     rdx, [rdi+8]
0x1800b3e82  cmp     rdx, [rdi+10h]
0x1800b3e86  jz      short loc_1800B3E92
0x1800b3e88  mov     [rdx], rbx
0x1800b3e8b  add     qword ptr [rdi+8], 8
0x1800b3e90  jmp     short loc_1800B3E9E
0x1800b3e92  lea     r8, [rbp+arg_8]
0x1800b3e96  mov     rcx, rdi
0x1800b3e99  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3e9e  lea     rax, [rbp+arg_0]
0x1800b3ea2  mov     [rbp+arg_8], rax
0x1800b3ea6  mov     rdx, [rdi+8]
0x1800b3eaa  cmp     rdx, [rdi+10h]
0x1800b3eae  jz      short loc_1800B3EBE
0x1800b3eb0  lea     rax, [rbp+arg_0]
0x1800b3eb4  mov     [rdx], rax
0x1800b3eb7  add     qword ptr [rdi+8], 8
0x1800b3ebc  jmp     short loc_1800B3ECA
0x1800b3ebe  lea     r8, [rbp+arg_8]
0x1800b3ec2  mov     rcx, rdi
0x1800b3ec5  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3eca  mov     [rbp+arg_8], r14
0x1800b3ece  mov     rdx, [rdi+8]
0x1800b3ed2  cmp     rdx, [rdi+10h]
0x1800b3ed6  jz      short loc_1800B3EE2
0x1800b3ed8  mov     [rdx], r14
0x1800b3edb  add     qword ptr [rdi+8], 8
0x1800b3ee0  jmp     short loc_1800B3EEE
0x1800b3ee2  lea     r8, [rbp+arg_8]
0x1800b3ee6  mov     rcx, rdi
0x1800b3ee9  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3eee  mov     [rbp+arg_8], r15
0x1800b3ef2  mov     rdx, [rdi+8]
0x1800b3ef6  cmp     rdx, [rdi+10h]
0x1800b3efa  jz      short loc_1800B3F06
0x1800b3efc  mov     [rdx], r15
0x1800b3eff  add     qword ptr [rdi+8], 8
0x1800b3f04  jmp     short loc_1800B3F12
0x1800b3f06  lea     r8, [rbp+arg_8]
0x1800b3f0a  mov     rcx, rdi
0x1800b3f0d  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3f12  mov     [rbp+arg_8], r12
0x1800b3f16  mov     rdx, [rdi+8]
0x1800b3f1a  cmp     rdx, [rdi+10h]
0x1800b3f1e  jz      short loc_1800B3F2A
0x1800b3f20  mov     [rdx], r12
0x1800b3f23  add     qword ptr [rdi+8], 8
0x1800b3f28  jmp     short loc_1800B3F36
0x1800b3f2a  lea     r8, [rbp+arg_8]
0x1800b3f2e  mov     rcx, rdi
0x1800b3f31  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3f36  mov     eax, [rbp+arg_20]
0x1800b3f39  mov     [rbp+arg_8], rax
0x1800b3f3d  mov     rdx, [rdi+8]
0x1800b3f41  cmp     rdx, [rdi+10h]
0x1800b3f45  jz      short loc_1800B3F51
0x1800b3f47  mov     [rdx], rax
0x1800b3f4a  add     qword ptr [rdi+8], 8
0x1800b3f4f  jmp     short loc_1800B3F5D
0x1800b3f51  lea     r8, [rbp+arg_8]
0x1800b3f55  mov     rcx, rdi
0x1800b3f58  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3f5d  mov     rdx, rsi
0x1800b3f60  mov     ecx, 4
0x1800b3f65  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b3f6a  test    eax, eax
0x1800b3f6c  jz      short loc_1800B3F97
0x1800b3f6e  test    rsi, rsi
0x1800b3f71  jz      short loc_1800B3F7B
0x1800b3f73  mov     rcx, rsi; this
0x1800b3f76  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b3f7b  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b3f82  xor     edx, edx; struct _GUID *
0x1800b3f84  lea     rcx, aWwansapscan; "WwanSapScan"
0x1800b3f8b  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b3f90  mov     ebx, 1Fh
0x1800b3f95  jmp     short loc_1800B3FCB
0x1800b3f97  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b3f9a  mov     rcx, rbx; hHandle
0x1800b3f9d  call    cs:__imp_WaitForSingleObject
0x1800b3fa3  test    eax, eax
0x1800b3fa5  jz      short loc_1800B3FC8
0x1800b3fa7  call    cs:__imp_GetLastError
0x1800b3fad  mov     r9d, eax; unsigned int
0x1800b3fb0  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b3fb7  mov     edx, 285h; unsigned int
0x1800b3fbc  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b3fc3  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b3fc8  mov     ebx, dword ptr [rbp+arg_0]
0x1800b3fcb  lea     rcx, [rbp+arg_10]
0x1800b3fcf  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b3fd4  mov     eax, ebx
0x1800b3fd6  add     rsp, 20h
0x1800b3fda  pop     r15
0x1800b3fdc  pop     r14
0x1800b3fde  pop     r12
0x1800b3fe0  pop     rdi
0x1800b3fe1  pop     rsi
0x1800b3fe2  pop     rbx
0x1800b3fe3  pop     rbp
0x1800b3fe4  retn
```
