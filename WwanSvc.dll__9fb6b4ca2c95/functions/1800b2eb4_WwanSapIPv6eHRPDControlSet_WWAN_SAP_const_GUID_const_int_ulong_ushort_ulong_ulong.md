# WwanSapIPv6eHRPDControlSet(WWAN_SAP const *,_GUID const *,int,ulong,ushort *,ulong *,ulong *)

- ea: `0x1800b2eb4`
- end: `0x1800b30fc`
- name: `?WwanSapIPv6eHRPDControlSet@@YAKPEBUWWAN_SAP@@PEBU_GUID@@HKPEAGPEAK3@Z`
- size: `584`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, int, unsigned int, unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800acf40`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b2eb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b30b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b30b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b2ee6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b2ee6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2efc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b30be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2efc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b30be`

## string_xrefs

- `0x1800b2f11`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b30d3`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b2f05`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapIPv6eHRPDControlSet(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int *a6,
        unsigned int *a7)
{
  MessageParams *v7; // r12
  MessageParams *v8; // r15
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
  _QWORD *v22; // rdx
  unsigned int v23; // edx
  unsigned int v24; // ebx
  DWORD v25; // eax
  MessageParams *v27; // [rsp+60h] [rbp+40h] BYREF
  MessageParams *v28; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v29; // [rsp+70h] [rbp+50h] BYREF

  v27 = a1;
  v7 = (MessageParams *)a4;
  v8 = (MessageParams *)a3;
  v29 = 0;
  EventW = (MessageParams *)CreateEventW(0, 1, 0, 0);
  v28 = EventW;
  if ( EventW == (MessageParams *)-1LL || (MessageParams *)((char *)EventW + 1) == (MessageParams *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xB01u, "CreateEvent", LastError);
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
  v27 = v8;
  v18 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v18 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v18, &v27);
  }
  else
  {
    *v18 = v8;
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
  v27 = (MessageParams *)a5;
  v20 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v20 == *((_QWORD **)v14 + 2) )
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
  v27 = (MessageParams *)a7;
  v22 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v22 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v22, &v27);
  }
  else
  {
    *v22 = a7;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(43, v13) )
  {
    if ( v13 )
      MessageParams::`scalar deleting destructor'(v13, v23);
    WwanLog::Error("WwanSapIPv6eHRPDControlSet", 0, L"Notification dispatcher: Failed to Queue Message");
    v24 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v25 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xB18u, "WaitForSingleObject", v25);
    }
    v24 = v29;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v28);
  return v24;
}

```

## disassembly

```asm
0x1800b2eb4  mov     [rsp-38h+arg_0], rcx
0x1800b2eb9  push    rbp
0x1800b2eba  push    rbx
0x1800b2ebb  push    rsi
0x1800b2ebc  push    rdi
0x1800b2ebd  push    r12
0x1800b2ebf  push    r14
0x1800b2ec1  push    r15
0x1800b2ec3  mov     rbp, rsp
0x1800b2ec6  sub     rsp, 20h
0x1800b2eca  mov     r12d, r9d
0x1800b2ecd  mov     r15d, r8d
0x1800b2ed0  mov     r14, rdx
0x1800b2ed3  mov     [rbp+arg_10], 0
0x1800b2eda  xor     r9d, r9d; lpName
0x1800b2edd  xor     r8d, r8d; bInitialState
0x1800b2ee0  lea     edx, [r9+1]; bManualReset
0x1800b2ee4  xor     ecx, ecx; lpEventAttributes
0x1800b2ee6  call    cs:__imp_CreateEventW
0x1800b2eec  mov     rbx, rax
0x1800b2eef  mov     [rbp+arg_8], rax
0x1800b2ef3  inc     rax
0x1800b2ef6  cmp     rax, 1
0x1800b2efa  ja      short loc_1800B2F1D
0x1800b2efc  call    cs:__imp_GetLastError
0x1800b2f02  mov     r9d, eax; unsigned int
0x1800b2f05  lea     r8, aCreateevent; "CreateEvent"
0x1800b2f0c  mov     edx, 0B01h; unsigned int
0x1800b2f11  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b2f18  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b2f1d  mov     ecx, 48h ; 'H'; Size
0x1800b2f22  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b2f27  mov     [rbp+arg_0], rax
0x1800b2f2b  mov     rcx, rax; this
0x1800b2f2e  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b2f33  mov     rsi, rax
0x1800b2f36  lea     rdi, [rax+30h]
0x1800b2f3a  mov     [rbp+arg_0], rbx
0x1800b2f3e  mov     rdx, [rdi+8]
0x1800b2f42  cmp     rdx, [rdi+10h]
0x1800b2f46  jz      short loc_1800B2F52
0x1800b2f48  mov     [rdx], rbx
0x1800b2f4b  add     qword ptr [rdi+8], 8
0x1800b2f50  jmp     short loc_1800B2F5E
0x1800b2f52  lea     r8, [rbp+arg_0]
0x1800b2f56  mov     rcx, rdi
0x1800b2f59  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b2f5e  lea     rax, [rbp+arg_10]
0x1800b2f62  mov     [rbp+arg_0], rax
0x1800b2f66  mov     rdx, [rdi+8]
0x1800b2f6a  cmp     rdx, [rdi+10h]
0x1800b2f6e  jz      short loc_1800B2F7E
0x1800b2f70  lea     rax, [rbp+arg_10]
0x1800b2f74  mov     [rdx], rax
0x1800b2f77  add     qword ptr [rdi+8], 8
0x1800b2f7c  jmp     short loc_1800B2F8A
0x1800b2f7e  lea     r8, [rbp+arg_0]
0x1800b2f82  mov     rcx, rdi
0x1800b2f85  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b2f8a  mov     [rbp+arg_0], r14
0x1800b2f8e  mov     rdx, [rdi+8]
0x1800b2f92  cmp     rdx, [rdi+10h]
0x1800b2f96  jz      short loc_1800B2FA2
0x1800b2f98  mov     [rdx], r14
0x1800b2f9b  add     qword ptr [rdi+8], 8
0x1800b2fa0  jmp     short loc_1800B2FAE
0x1800b2fa2  lea     r8, [rbp+arg_0]
0x1800b2fa6  mov     rcx, rdi
0x1800b2fa9  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b2fae  mov     rax, r15
0x1800b2fb1  mov     [rbp+arg_0], rax
0x1800b2fb5  mov     rdx, [rdi+8]
0x1800b2fb9  cmp     rdx, [rdi+10h]
0x1800b2fbd  jz      short loc_1800B2FC9
0x1800b2fbf  mov     [rdx], rax
0x1800b2fc2  add     qword ptr [rdi+8], 8
0x1800b2fc7  jmp     short loc_1800B2FD5
0x1800b2fc9  lea     r8, [rbp+arg_0]
0x1800b2fcd  mov     rcx, rdi
0x1800b2fd0  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b2fd5  mov     rax, r12
0x1800b2fd8  mov     [rbp+arg_0], rax
0x1800b2fdc  mov     rdx, [rdi+8]
0x1800b2fe0  cmp     rdx, [rdi+10h]
0x1800b2fe4  jz      short loc_1800B2FF0
0x1800b2fe6  mov     [rdx], rax
0x1800b2fe9  add     qword ptr [rdi+8], 8
0x1800b2fee  jmp     short loc_1800B2FFC
0x1800b2ff0  lea     r8, [rbp+arg_0]
0x1800b2ff4  mov     rcx, rdi
0x1800b2ff7  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b2ffc  mov     rax, [rbp+arg_20]
0x1800b3000  mov     [rbp+arg_0], rax
0x1800b3004  mov     rdx, [rdi+8]
0x1800b3008  cmp     rdx, [rdi+10h]
0x1800b300c  jz      short loc_1800B3018
0x1800b300e  mov     [rdx], rax
0x1800b3011  add     qword ptr [rdi+8], 8
0x1800b3016  jmp     short loc_1800B3024
0x1800b3018  lea     r8, [rbp+arg_0]
0x1800b301c  mov     rcx, rdi
0x1800b301f  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3024  mov     rax, [rbp+arg_28]
0x1800b3028  mov     [rbp+arg_0], rax
0x1800b302c  mov     rdx, [rdi+8]
0x1800b3030  cmp     rdx, [rdi+10h]
0x1800b3034  jz      short loc_1800B3040
0x1800b3036  mov     [rdx], rax
0x1800b3039  add     qword ptr [rdi+8], 8
0x1800b303e  jmp     short loc_1800B304C
0x1800b3040  lea     r8, [rbp+arg_0]
0x1800b3044  mov     rcx, rdi
0x1800b3047  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b304c  mov     rax, [rbp+arg_30]
0x1800b3050  mov     [rbp+arg_0], rax
0x1800b3054  mov     rdx, [rdi+8]
0x1800b3058  cmp     rdx, [rdi+10h]
0x1800b305c  jz      short loc_1800B3068
0x1800b305e  mov     [rdx], rax
0x1800b3061  add     qword ptr [rdi+8], 8
0x1800b3066  jmp     short loc_1800B3074
0x1800b3068  lea     r8, [rbp+arg_0]
0x1800b306c  mov     rcx, rdi
0x1800b306f  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3074  mov     rdx, rsi
0x1800b3077  mov     ecx, 2Bh ; '+'
0x1800b307c  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b3081  test    eax, eax
0x1800b3083  jz      short loc_1800B30AE
0x1800b3085  test    rsi, rsi
0x1800b3088  jz      short loc_1800B3092
0x1800b308a  mov     rcx, rsi; this
0x1800b308d  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b3092  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b3099  xor     edx, edx; struct _GUID *
0x1800b309b  lea     rcx, aWwansapipv6ehr_0; "WwanSapIPv6eHRPDControlSet"
0x1800b30a2  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b30a7  mov     ebx, 1Fh
0x1800b30ac  jmp     short loc_1800B30E2
0x1800b30ae  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b30b1  mov     rcx, rbx; hHandle
0x1800b30b4  call    cs:__imp_WaitForSingleObject
0x1800b30ba  test    eax, eax
0x1800b30bc  jz      short loc_1800B30DF
0x1800b30be  call    cs:__imp_GetLastError
0x1800b30c4  mov     r9d, eax; unsigned int
0x1800b30c7  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b30ce  mov     edx, 0B18h; unsigned int
0x1800b30d3  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b30da  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b30df  mov     ebx, [rbp+arg_10]
0x1800b30e2  lea     rcx, [rbp+arg_8]
0x1800b30e6  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b30eb  mov     eax, ebx
0x1800b30ed  add     rsp, 20h
0x1800b30f1  pop     r15
0x1800b30f3  pop     r14
0x1800b30f5  pop     r12
0x1800b30f7  pop     rdi
0x1800b30f8  pop     rsi
0x1800b30f9  pop     rbx
0x1800b30fa  pop     rbp
0x1800b30fb  retn
```
