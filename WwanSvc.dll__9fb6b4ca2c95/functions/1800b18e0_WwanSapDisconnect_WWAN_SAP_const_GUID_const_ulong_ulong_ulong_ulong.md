# WwanSapDisconnect(WWAN_SAP const *,_GUID const *,ulong,ulong,ulong *,ulong *)

- ea: `0x1800b18e0`
- end: `0x1800b1b54`
- name: `?WwanSapDisconnect@@YAKPEBUWWAN_SAP@@PEBU_GUID@@KKPEAK2@Z`
- size: `628`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, unsigned int, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800ac7f0`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x18008da2c`
- `0x1800b18e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b1ae7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b1ae7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b1916`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b1916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b192c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1af1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b192c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1af1`

## string_xrefs

- `0x1800b1941`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b1b06`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b1935`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapDisconnect(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int *a6)
{
  MessageParams *v6; // r12
  MessageParams *v7; // r15
  MessageParams *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v12; // rax
  MessageParams *v13; // rsi
  char *v14; // rdi
  MessageParams **v15; // rdx
  unsigned int **v16; // rdx
  _QWORD *v17; // rdx
  _QWORD *v18; // rdx
  _QWORD *v19; // rdx
  _QWORD *v20; // rdx
  _QWORD *v21; // rdx
  unsigned int *v22; // rax
  _QWORD *v23; // rdx
  unsigned int v24; // edx
  unsigned int v25; // ebx
  __int64 v26; // rcx
  DWORD v27; // eax
  MessageParams *v29; // [rsp+60h] [rbp+40h] BYREF
  MessageParams *v30; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v31; // [rsp+70h] [rbp+50h] BYREF

  v6 = (MessageParams *)a4;
  v7 = (MessageParams *)a3;
  v31 = 0;
  EventW = (MessageParams *)CreateEventW(0, 1, 0, 0);
  v30 = EventW;
  if ( EventW == (MessageParams *)-1LL || (MessageParams *)((char *)EventW + 1) == (MessageParams *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x330u, "CreateEvent", LastError);
  }
  v29 = (MessageParams *)operator new(0x48u);
  v12 = MessageParams::MessageParams(v29);
  v13 = v12;
  v14 = (char *)v12 + 48;
  v29 = EventW;
  v15 = (MessageParams **)*((_QWORD *)v12 + 7);
  if ( v15 == *((MessageParams ***)v12 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v12 + 48, v15, &v29);
  }
  else
  {
    *v15 = EventW;
    *((_QWORD *)v12 + 7) += 8LL;
  }
  v29 = (MessageParams *)&v31;
  v16 = (unsigned int **)*((_QWORD *)v14 + 1);
  if ( v16 == *((unsigned int ***)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v16, &v29);
  }
  else
  {
    *v16 = &v31;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v29 = (MessageParams *)a2;
  v17 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v17 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v17, &v29);
  }
  else
  {
    *v17 = a2;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v29 = v7;
  v18 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v18 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v18, &v29);
  }
  else
  {
    *v18 = v7;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v29 = v6;
  v19 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v19 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v19, &v29);
  }
  else
  {
    *v19 = v6;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v20 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v20 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v20, &a5);
  }
  else
  {
    *v20 = a5;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  a5 = a6;
  v21 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v21 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v21, &a5);
  }
  else
  {
    *v21 = a6;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v22 = (unsigned int *)*((unsigned int *)a1 + 40);
  a5 = v22;
  v23 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v23 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v23, &a5);
  }
  else
  {
    *v23 = v22;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(8, v13) )
  {
    if ( v13 )
      MessageParams::`scalar deleting destructor'(v13, v24);
    WwanLog::Error("WwanSapDisconnect", 0, L"Notification dispatcher: Failed to Queue Message");
    v25 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v27 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x347u, "WaitForSingleObject", v27);
    }
    v25 = v31;
    if ( !v31 && (byte_1801528C2 & 0x10) != 0 )
    {
      McTemplateU0j_EventWriteTransfer(v26, CancelWwanResumeReconnect, a2);
      v25 = v31;
    }
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v30);
  return v25;
}

```

## disassembly

```asm
0x1800b18e0  mov     [rsp-38h+arg_18], rbx
0x1800b18e5  push    rbp
0x1800b18e6  push    rsi
0x1800b18e7  push    rdi
0x1800b18e8  push    r12
0x1800b18ea  push    r13
0x1800b18ec  push    r14
0x1800b18ee  push    r15
0x1800b18f0  mov     rbp, rsp
0x1800b18f3  sub     rsp, 20h
0x1800b18f7  mov     r12d, r9d
0x1800b18fa  mov     r15d, r8d
0x1800b18fd  mov     r14, rdx
0x1800b1900  mov     r13, rcx
0x1800b1903  mov     [rbp+arg_10], 0
0x1800b190a  xor     r9d, r9d; lpName
0x1800b190d  xor     r8d, r8d; bInitialState
0x1800b1910  lea     edx, [r9+1]; bManualReset
0x1800b1914  xor     ecx, ecx; lpEventAttributes
0x1800b1916  call    cs:__imp_CreateEventW
0x1800b191c  mov     rbx, rax
0x1800b191f  mov     [rbp+arg_8], rax
0x1800b1923  inc     rax
0x1800b1926  cmp     rax, 1
0x1800b192a  ja      short loc_1800B194D
0x1800b192c  call    cs:__imp_GetLastError
0x1800b1932  mov     r9d, eax; unsigned int
0x1800b1935  lea     r8, aCreateevent; "CreateEvent"
0x1800b193c  mov     edx, 330h; unsigned int
0x1800b1941  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b1948  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b194d  mov     ecx, 48h ; 'H'; Size
0x1800b1952  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b1957  mov     [rbp+arg_0], rax
0x1800b195b  mov     rcx, rax; this
0x1800b195e  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b1963  mov     rsi, rax
0x1800b1966  lea     rdi, [rax+30h]
0x1800b196a  mov     [rbp+arg_0], rbx
0x1800b196e  mov     rdx, [rdi+8]
0x1800b1972  cmp     rdx, [rdi+10h]
0x1800b1976  jz      short loc_1800B1982
0x1800b1978  mov     [rdx], rbx
0x1800b197b  add     qword ptr [rdi+8], 8
0x1800b1980  jmp     short loc_1800B198E
0x1800b1982  lea     r8, [rbp+arg_0]
0x1800b1986  mov     rcx, rdi
0x1800b1989  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b198e  lea     rax, [rbp+arg_10]
0x1800b1992  mov     [rbp+arg_0], rax
0x1800b1996  mov     rdx, [rdi+8]
0x1800b199a  cmp     rdx, [rdi+10h]
0x1800b199e  jz      short loc_1800B19AE
0x1800b19a0  lea     rax, [rbp+arg_10]
0x1800b19a4  mov     [rdx], rax
0x1800b19a7  add     qword ptr [rdi+8], 8
0x1800b19ac  jmp     short loc_1800B19BA
0x1800b19ae  lea     r8, [rbp+arg_0]
0x1800b19b2  mov     rcx, rdi
0x1800b19b5  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b19ba  mov     [rbp+arg_0], r14
0x1800b19be  mov     rdx, [rdi+8]
0x1800b19c2  cmp     rdx, [rdi+10h]
0x1800b19c6  jz      short loc_1800B19D2
0x1800b19c8  mov     [rdx], r14
0x1800b19cb  add     qword ptr [rdi+8], 8
0x1800b19d0  jmp     short loc_1800B19DE
0x1800b19d2  lea     r8, [rbp+arg_0]
0x1800b19d6  mov     rcx, rdi
0x1800b19d9  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b19de  mov     rax, r15
0x1800b19e1  mov     [rbp+arg_0], rax
0x1800b19e5  mov     rdx, [rdi+8]
0x1800b19e9  cmp     rdx, [rdi+10h]
0x1800b19ed  jz      short loc_1800B19F9
0x1800b19ef  mov     [rdx], rax
0x1800b19f2  add     qword ptr [rdi+8], 8
0x1800b19f7  jmp     short loc_1800B1A05
0x1800b19f9  lea     r8, [rbp+arg_0]
0x1800b19fd  mov     rcx, rdi
0x1800b1a00  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1a05  mov     rax, r12
0x1800b1a08  mov     [rbp+arg_0], rax
0x1800b1a0c  mov     rdx, [rdi+8]
0x1800b1a10  cmp     rdx, [rdi+10h]
0x1800b1a14  jz      short loc_1800B1A20
0x1800b1a16  mov     [rdx], rax
0x1800b1a19  add     qword ptr [rdi+8], 8
0x1800b1a1e  jmp     short loc_1800B1A2C
0x1800b1a20  lea     r8, [rbp+arg_0]
0x1800b1a24  mov     rcx, rdi
0x1800b1a27  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1a2c  mov     rax, [rbp+arg_20]
0x1800b1a30  mov     [rbp+arg_20], rax
0x1800b1a34  mov     rdx, [rdi+8]
0x1800b1a38  cmp     rdx, [rdi+10h]
0x1800b1a3c  jz      short loc_1800B1A48
0x1800b1a3e  mov     [rdx], rax
0x1800b1a41  add     qword ptr [rdi+8], 8
0x1800b1a46  jmp     short loc_1800B1A54
0x1800b1a48  lea     r8, [rbp+arg_20]
0x1800b1a4c  mov     rcx, rdi
0x1800b1a4f  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1a54  mov     rax, [rbp+arg_28]
0x1800b1a58  mov     [rbp+arg_20], rax
0x1800b1a5c  mov     rdx, [rdi+8]
0x1800b1a60  cmp     rdx, [rdi+10h]
0x1800b1a64  jz      short loc_1800B1A70
0x1800b1a66  mov     [rdx], rax
0x1800b1a69  add     qword ptr [rdi+8], 8
0x1800b1a6e  jmp     short loc_1800B1A7C
0x1800b1a70  lea     r8, [rbp+arg_20]
0x1800b1a74  mov     rcx, rdi
0x1800b1a77  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1a7c  mov     eax, [r13+0A0h]
0x1800b1a83  mov     [rbp+arg_20], rax
0x1800b1a87  mov     rdx, [rdi+8]
0x1800b1a8b  cmp     rdx, [rdi+10h]
0x1800b1a8f  jz      short loc_1800B1A9B
0x1800b1a91  mov     [rdx], rax
0x1800b1a94  add     qword ptr [rdi+8], 8
0x1800b1a99  jmp     short loc_1800B1AA7
0x1800b1a9b  lea     r8, [rbp+arg_20]
0x1800b1a9f  mov     rcx, rdi
0x1800b1aa2  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1aa7  mov     rdx, rsi
0x1800b1aaa  mov     ecx, 8
0x1800b1aaf  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b1ab4  test    eax, eax
0x1800b1ab6  jz      short loc_1800B1AE1
0x1800b1ab8  test    rsi, rsi
0x1800b1abb  jz      short loc_1800B1AC5
0x1800b1abd  mov     rcx, rsi; this
0x1800b1ac0  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b1ac5  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b1acc  xor     edx, edx; struct _GUID *
0x1800b1ace  lea     rcx, aWwansapdisconn; "WwanSapDisconnect"
0x1800b1ad5  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b1ada  mov     ebx, 1Fh
0x1800b1adf  jmp     short loc_1800B1B34
0x1800b1ae1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b1ae4  mov     rcx, rbx; hHandle
0x1800b1ae7  call    cs:__imp_WaitForSingleObject
0x1800b1aed  test    eax, eax
0x1800b1aef  jz      short loc_1800B1B12
0x1800b1af1  call    cs:__imp_GetLastError
0x1800b1af7  mov     r9d, eax; unsigned int
0x1800b1afa  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b1b01  mov     edx, 347h; unsigned int
0x1800b1b06  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b1b0d  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b1b12  mov     ebx, [rbp+arg_10]
0x1800b1b15  test    ebx, ebx
0x1800b1b17  jnz     short loc_1800B1B34
0x1800b1b19  test    cs:byte_1801528C2, 10h
0x1800b1b20  jz      short loc_1800B1B34
0x1800b1b22  mov     r8, r14
0x1800b1b25  lea     rdx, CancelWwanResumeReconnect
0x1800b1b2c  call    McTemplateU0j_EventWriteTransfer
0x1800b1b31  mov     ebx, [rbp+arg_10]
0x1800b1b34  lea     rcx, [rbp+arg_8]
0x1800b1b38  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b1b3d  mov     eax, ebx
0x1800b1b3f  mov     rbx, [rsp+20h+arg_18]
0x1800b1b44  add     rsp, 20h
0x1800b1b48  pop     r15
0x1800b1b4a  pop     r14
0x1800b1b4c  pop     r13
0x1800b1b4e  pop     r12
0x1800b1b50  pop     rdi
0x1800b1b51  pop     rsi
0x1800b1b52  pop     rbp
0x1800b1b53  retn
```
