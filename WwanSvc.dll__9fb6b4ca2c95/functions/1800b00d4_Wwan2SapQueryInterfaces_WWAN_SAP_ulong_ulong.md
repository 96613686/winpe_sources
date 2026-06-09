# Wwan2SapQueryInterfaces(WWAN_SAP *,ulong,ulong)

- ea: `0x1800b00d4`
- end: `0x1800b02a0`
- name: `?Wwan2SapQueryInterfaces@@YAKPEAUWWAN_SAP@@KK@Z`
- size: `460`
- prototype: `unsigned int __fastcall(struct WWAN_SAP *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800ac1d0`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b00d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0258`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0258`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b0102`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b0102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0262`

## string_xrefs

- `0x1800b012d`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b0277`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b0121`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Wwan2SapQueryInterfaces(struct WWAN_SAP *a1, unsigned int a2, unsigned int a3)
{
  MessageParams *v3; // r12
  MessageParams *v4; // r15
  MessageParams *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v8; // rax
  MessageParams *v9; // rsi
  char *v10; // rdi
  MessageParams **v11; // rdx
  unsigned int **v12; // rdx
  _QWORD *v13; // rdx
  _QWORD *v14; // rdx
  _QWORD *v15; // rdx
  unsigned int v16; // edx
  unsigned int v17; // ebx
  DWORD v18; // eax
  MessageParams *v20; // [rsp+60h] [rbp+40h] BYREF
  unsigned int v21; // [rsp+68h] [rbp+48h] BYREF
  MessageParams *v22; // [rsp+78h] [rbp+58h] BYREF

  v3 = (MessageParams *)a3;
  v4 = (MessageParams *)a2;
  v21 = 0;
  EventW = (MessageParams *)CreateEventW(0, 1, 0, 0);
  v22 = EventW;
  if ( EventW == (MessageParams *)-1LL || (MessageParams *)((char *)EventW + 1) == (MessageParams *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x5F3u, "CreateEvent", LastError);
  }
  v20 = (MessageParams *)operator new(0x48u);
  v8 = MessageParams::MessageParams(v20);
  v9 = v8;
  v10 = (char *)v8 + 48;
  v20 = EventW;
  v11 = (MessageParams **)*((_QWORD *)v8 + 7);
  if ( v11 == *((MessageParams ***)v8 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v8 + 48, v11, &v20);
  }
  else
  {
    *v11 = EventW;
    *((_QWORD *)v8 + 7) += 8LL;
  }
  v20 = (MessageParams *)&v21;
  v12 = (unsigned int **)*((_QWORD *)v10 + 1);
  if ( v12 == *((unsigned int ***)v10 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v10, v12, &v20);
  }
  else
  {
    *v12 = &v21;
    *((_QWORD *)v10 + 1) += 8LL;
  }
  v20 = a1;
  v13 = (_QWORD *)*((_QWORD *)v10 + 1);
  if ( v13 == *((_QWORD **)v10 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v10, v13, &v20);
  }
  else
  {
    *v13 = a1;
    *((_QWORD *)v10 + 1) += 8LL;
  }
  v20 = v4;
  v14 = (_QWORD *)*((_QWORD *)v10 + 1);
  if ( v14 == *((_QWORD **)v10 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v10, v14, &v20);
  }
  else
  {
    *v14 = v4;
    *((_QWORD *)v10 + 1) += 8LL;
  }
  v20 = v3;
  v15 = (_QWORD *)*((_QWORD *)v10 + 1);
  if ( v15 == *((_QWORD **)v10 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v10, v15, &v20);
  }
  else
  {
    *v15 = v3;
    *((_QWORD *)v10 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(35, v9) )
  {
    if ( v9 )
      MessageParams::`scalar deleting destructor'(v9, v16);
    WwanLog::Error("Wwan2SapQueryInterfaces", 0, L"Notification dispatcher: Failed to Queue Message");
    v17 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v18 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x607u, "WaitForSingleObject", v18);
    }
    v17 = v21;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v22);
  return v17;
}

```

## disassembly

```asm
0x1800b00d4  push    rbp
0x1800b00d6  push    rbx
0x1800b00d7  push    rsi
0x1800b00d8  push    rdi
0x1800b00d9  push    r12
0x1800b00db  push    r14
0x1800b00dd  push    r15
0x1800b00df  mov     rbp, rsp
0x1800b00e2  sub     rsp, 20h
0x1800b00e6  mov     r12d, r8d
0x1800b00e9  mov     r15d, edx
0x1800b00ec  mov     r14, rcx
0x1800b00ef  mov     [rbp+arg_8], 0
0x1800b00f6  xor     r9d, r9d; lpName
0x1800b00f9  xor     r8d, r8d; bInitialState
0x1800b00fc  lea     edx, [r9+1]; bManualReset
0x1800b0100  xor     ecx, ecx; lpEventAttributes
0x1800b0102  call    cs:__imp_CreateEventW
0x1800b0108  mov     rbx, rax
0x1800b010b  mov     [rbp+arg_18], rax
0x1800b010f  inc     rax
0x1800b0112  cmp     rax, 1
0x1800b0116  ja      short loc_1800B0139
0x1800b0118  call    cs:__imp_GetLastError
0x1800b011e  mov     r9d, eax; unsigned int
0x1800b0121  lea     r8, aCreateevent; "CreateEvent"
0x1800b0128  mov     edx, 5F3h; unsigned int
0x1800b012d  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b0134  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b0139  mov     ecx, 48h ; 'H'; Size
0x1800b013e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b0143  mov     [rbp+arg_0], rax
0x1800b0147  mov     rcx, rax; this
0x1800b014a  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b014f  mov     rsi, rax
0x1800b0152  lea     rdi, [rax+30h]
0x1800b0156  mov     [rbp+arg_0], rbx
0x1800b015a  mov     rdx, [rdi+8]
0x1800b015e  cmp     rdx, [rdi+10h]
0x1800b0162  jz      short loc_1800B016E
0x1800b0164  mov     [rdx], rbx
0x1800b0167  add     qword ptr [rdi+8], 8
0x1800b016c  jmp     short loc_1800B017A
0x1800b016e  lea     r8, [rbp+arg_0]
0x1800b0172  mov     rcx, rdi
0x1800b0175  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b017a  lea     rax, [rbp+arg_8]
0x1800b017e  mov     [rbp+arg_0], rax
0x1800b0182  mov     rdx, [rdi+8]
0x1800b0186  cmp     rdx, [rdi+10h]
0x1800b018a  jz      short loc_1800B019A
0x1800b018c  lea     rax, [rbp+arg_8]
0x1800b0190  mov     [rdx], rax
0x1800b0193  add     qword ptr [rdi+8], 8
0x1800b0198  jmp     short loc_1800B01A6
0x1800b019a  lea     r8, [rbp+arg_0]
0x1800b019e  mov     rcx, rdi
0x1800b01a1  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b01a6  mov     [rbp+arg_0], r14
0x1800b01aa  mov     rdx, [rdi+8]
0x1800b01ae  cmp     rdx, [rdi+10h]
0x1800b01b2  jz      short loc_1800B01BE
0x1800b01b4  mov     [rdx], r14
0x1800b01b7  add     qword ptr [rdi+8], 8
0x1800b01bc  jmp     short loc_1800B01CA
0x1800b01be  lea     r8, [rbp+arg_0]
0x1800b01c2  mov     rcx, rdi
0x1800b01c5  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b01ca  mov     rax, r15
0x1800b01cd  mov     [rbp+arg_0], rax
0x1800b01d1  mov     rdx, [rdi+8]
0x1800b01d5  cmp     rdx, [rdi+10h]
0x1800b01d9  jz      short loc_1800B01E5
0x1800b01db  mov     [rdx], rax
0x1800b01de  add     qword ptr [rdi+8], 8
0x1800b01e3  jmp     short loc_1800B01F1
0x1800b01e5  lea     r8, [rbp+arg_0]
0x1800b01e9  mov     rcx, rdi
0x1800b01ec  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b01f1  mov     rax, r12
0x1800b01f4  mov     [rbp+arg_0], rax
0x1800b01f8  mov     rdx, [rdi+8]
0x1800b01fc  cmp     rdx, [rdi+10h]
0x1800b0200  jz      short loc_1800B020C
0x1800b0202  mov     [rdx], rax
0x1800b0205  add     qword ptr [rdi+8], 8
0x1800b020a  jmp     short loc_1800B0218
0x1800b020c  lea     r8, [rbp+arg_0]
0x1800b0210  mov     rcx, rdi
0x1800b0213  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0218  mov     rdx, rsi
0x1800b021b  mov     ecx, 23h ; '#'
0x1800b0220  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b0225  test    eax, eax
0x1800b0227  jz      short loc_1800B0252
0x1800b0229  test    rsi, rsi
0x1800b022c  jz      short loc_1800B0236
0x1800b022e  mov     rcx, rsi; this
0x1800b0231  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b0236  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b023d  xor     edx, edx; struct _GUID *
0x1800b023f  lea     rcx, aWwan2sapqueryi; "Wwan2SapQueryInterfaces"
0x1800b0246  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b024b  mov     ebx, 1Fh
0x1800b0250  jmp     short loc_1800B0286
0x1800b0252  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b0255  mov     rcx, rbx; hHandle
0x1800b0258  call    cs:__imp_WaitForSingleObject
0x1800b025e  test    eax, eax
0x1800b0260  jz      short loc_1800B0283
0x1800b0262  call    cs:__imp_GetLastError
0x1800b0268  mov     r9d, eax; unsigned int
0x1800b026b  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b0272  mov     edx, 607h; unsigned int
0x1800b0277  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b027e  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b0283  mov     ebx, [rbp+arg_8]
0x1800b0286  lea     rcx, [rbp+arg_18]
0x1800b028a  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b028f  mov     eax, ebx
0x1800b0291  add     rsp, 20h
0x1800b0295  pop     r15
0x1800b0297  pop     r14
0x1800b0299  pop     r12
0x1800b029b  pop     rdi
0x1800b029c  pop     rsi
0x1800b029d  pop     rbx
0x1800b029e  pop     rbp
0x1800b029f  retn
```
