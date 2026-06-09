# WwanSapConnect(WWAN_SAP const *,_GUID const *,WWAN_CONNECTION_MODE,ulong,ushort const *,_GUID const *,ulong,ulong *,ulong *)

- ea: `0x1800b0f20`
- end: `0x1800b1237`
- name: `?WwanSapConnect@@YAKPEBUWWAN_SAP@@PEBU_GUID@@W4WWAN_CONNECTION_MODE@@KPEBG1KPEAK4@Z`
- size: `791`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800ac5d0`

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
- `0x1800b0f20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b11ce`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b11ce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b0f80`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b0f80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0f96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b11d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0f96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b11d8`

## string_xrefs

- `0x1800b0fab`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b11ed`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b0f9f`: `CreateEvent`
- `0x1800b0f55`: `Cannot connect to non-temporary profile from MBAE app; returning ERROR_ACCESS_DENIED`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapConnect(
        __int64 a1,
        _DWORD *a2,
        int a3,
        unsigned int a4,
        _DWORD *a5,
        _DWORD *a6,
        unsigned int a7,
        _DWORD *a8,
        _DWORD *a9)
{
  unsigned __int64 v9; // r15
  unsigned __int64 v10; // rsi
  _DWORD *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v16; // rax
  MessageParams *v17; // rax
  MessageParams *v18; // r14
  char *v19; // rdi
  _QWORD *v20; // rdx
  unsigned int **v21; // rdx
  _QWORD *v22; // rdx
  unsigned __int64 *v23; // rdx
  unsigned __int64 *v24; // rdx
  _QWORD *v25; // rdx
  _QWORD *v26; // rdx
  _QWORD *v27; // rdx
  _QWORD *v28; // rdx
  _QWORD *v29; // rdx
  _DWORD *v30; // rax
  _QWORD *v31; // rdx
  unsigned int v32; // edx
  unsigned int v33; // ebx
  __int64 v34; // rcx
  DWORD v35; // eax
  unsigned __int64 v36; // [rsp+20h] [rbp-18h] BYREF
  _DWORD *v37; // [rsp+28h] [rbp-10h] BYREF
  unsigned int v38; // [rsp+80h] [rbp+48h] BYREF

  v9 = a4;
  v10 = a3;
  v38 = 0;
  if ( !*(_DWORD *)(a1 + 160) || a3 == 1 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    v37 = EventW;
    if ( EventW == (_DWORD *)-1LL || (_DWORD *)((char *)EventW + 1) == (_DWORD *)1 )
    {
      LastError = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x2D0u, "CreateEvent", LastError);
    }
    v16 = (MessageParams *)operator new(0x48u);
    v17 = MessageParams::MessageParams(v16);
    v18 = v17;
    v19 = (char *)v17 + 48;
    v36 = (unsigned __int64)EventW;
    v20 = (_QWORD *)*((_QWORD *)v17 + 7);
    if ( v20 == *((_QWORD **)v17 + 8) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v17 + 48, v20, &v36);
    }
    else
    {
      *v20 = EventW;
      *((_QWORD *)v17 + 7) += 8LL;
    }
    v36 = (unsigned __int64)&v38;
    v21 = (unsigned int **)*((_QWORD *)v19 + 1);
    if ( v21 == *((unsigned int ***)v19 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v19, v21, &v36);
    }
    else
    {
      *v21 = &v38;
      *((_QWORD *)v19 + 1) += 8LL;
    }
    v36 = (unsigned __int64)a2;
    v22 = (_QWORD *)*((_QWORD *)v19 + 1);
    if ( v22 == *((_QWORD **)v19 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v19, v22, &v36);
    }
    else
    {
      *v22 = a2;
      *((_QWORD *)v19 + 1) += 8LL;
    }
    v36 = v10;
    v23 = (unsigned __int64 *)*((_QWORD *)v19 + 1);
    if ( v23 == *((unsigned __int64 **)v19 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v19, v23, &v36);
    }
    else
    {
      *v23 = v10;
      *((_QWORD *)v19 + 1) += 8LL;
    }
    v36 = v9;
    v24 = (unsigned __int64 *)*((_QWORD *)v19 + 1);
    if ( v24 == *((unsigned __int64 **)v19 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v19, v24, &v36);
    }
    else
    {
      *v24 = v9;
      *((_QWORD *)v19 + 1) += 8LL;
    }
    v36 = (unsigned __int64)a5;
    v25 = (_QWORD *)*((_QWORD *)v19 + 1);
    if ( v25 == *((_QWORD **)v19 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v19, v25, &v36);
    }
    else
    {
      *v25 = a5;
      *((_QWORD *)v19 + 1) += 8LL;
    }
    v36 = (unsigned __int64)a6;
    v26 = (_QWORD *)*((_QWORD *)v19 + 1);
    if ( v26 == *((_QWORD **)v19 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v19, v26, &v36);
    }
    else
    {
      *v26 = a6;
      *((_QWORD *)v19 + 1) += 8LL;
    }
    v36 = a7;
    v27 = (_QWORD *)*((_QWORD *)v19 + 1);
    if ( v27 == *((_QWORD **)v19 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v19, v27, &v36);
    }
    else
    {
      *v27 = a7;
      *((_QWORD *)v19 + 1) += 8LL;
    }
    v36 = (unsigned __int64)a8;
    v28 = (_QWORD *)*((_QWORD *)v19 + 1);
    if ( v28 == *((_QWORD **)v19 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v19, v28, &v36);
    }
    else
    {
      *v28 = a8;
      *((_QWORD *)v19 + 1) += 8LL;
    }
    v36 = (unsigned __int64)a9;
    v29 = (_QWORD *)*((_QWORD *)v19 + 1);
    if ( v29 == *((_QWORD **)v19 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v19, v29, &v36);
    }
    else
    {
      *v29 = a9;
      *((_QWORD *)v19 + 1) += 8LL;
    }
    v30 = (_DWORD *)*(unsigned int *)(a1 + 160);
    v36 = (unsigned __int64)v30;
    v31 = (_QWORD *)*((_QWORD *)v19 + 1);
    if ( v31 == *((_QWORD **)v19 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v19, v31, &v36);
    }
    else
    {
      *v31 = v30;
      *((_QWORD *)v19 + 1) += 8LL;
    }
    if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(6, v18) )
    {
      if ( v18 )
        MessageParams::`scalar deleting destructor'(v18, v32);
      WwanLog::Error("WwanSapConnect", 0, L"Notification dispatcher: Failed to Queue Message");
      v33 = 31;
    }
    else
    {
      if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
      {
        v35 = GetLastError();
        __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x2EAu, "WaitForSingleObject", v35);
      }
      v33 = v38;
      if ( !v38 && (byte_1801528C2 & 0x10) != 0 )
      {
        McTemplateU0j_EventWriteTransfer(v34, CancelWwanResumeReconnect, a2);
        v33 = v38;
      }
    }
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v37);
    return v33;
  }
  else
  {
    WwanLog::Error(
      "WwanSapConnect",
      0,
      L"Cannot connect to non-temporary profile from MBAE app; returning ERROR_ACCESS_DENIED");
    return 5;
  }
}

```

## disassembly

```asm
0x1800b0f20  push    rbp
0x1800b0f22  push    rbx
0x1800b0f23  push    rsi
0x1800b0f24  push    rdi
0x1800b0f25  push    r12
0x1800b0f27  push    r13
0x1800b0f29  push    r14
0x1800b0f2b  push    r15
0x1800b0f2d  mov     rbp, rsp
0x1800b0f30  sub     rsp, 38h
0x1800b0f34  mov     r15d, r9d
0x1800b0f37  movsxd  rsi, r8d
0x1800b0f3a  mov     r12, rdx
0x1800b0f3d  mov     r13, rcx
0x1800b0f40  mov     [rbp+arg_0], 0
0x1800b0f47  cmp     dword ptr [rcx+0A0h], 0
0x1800b0f4e  jz      short loc_1800B0F74
0x1800b0f50  cmp     esi, 1
0x1800b0f53  jz      short loc_1800B0F74
0x1800b0f55  lea     r8, aCannotConnectT; "Cannot connect to non-temporary profile"...
0x1800b0f5c  xor     edx, edx; struct _GUID *
0x1800b0f5e  lea     rcx, aWwansapconnect_0; "WwanSapConnect"
0x1800b0f65  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b0f6a  mov     eax, 5
0x1800b0f6f  jmp     loc_1800B1226
0x1800b0f74  xor     r9d, r9d; lpName
0x1800b0f77  xor     r8d, r8d; bInitialState
0x1800b0f7a  lea     edx, [r9+1]; bManualReset
0x1800b0f7e  xor     ecx, ecx; lpEventAttributes
0x1800b0f80  call    cs:__imp_CreateEventW
0x1800b0f86  mov     rbx, rax
0x1800b0f89  mov     [rbp+var_10], rax
0x1800b0f8d  inc     rax
0x1800b0f90  cmp     rax, 1
0x1800b0f94  ja      short loc_1800B0FB7
0x1800b0f96  call    cs:__imp_GetLastError
0x1800b0f9c  mov     r9d, eax; unsigned int
0x1800b0f9f  lea     r8, aCreateevent; "CreateEvent"
0x1800b0fa6  mov     edx, 2D0h; unsigned int
0x1800b0fab  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b0fb2  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b0fb7  mov     ecx, 48h ; 'H'; Size
0x1800b0fbc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b0fc1  mov     [rbp+var_18], rax
0x1800b0fc5  mov     rcx, rax; this
0x1800b0fc8  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b0fcd  mov     r14, rax
0x1800b0fd0  lea     rdi, [rax+30h]
0x1800b0fd4  mov     [rbp+var_18], rbx
0x1800b0fd8  mov     rdx, [rdi+8]
0x1800b0fdc  cmp     rdx, [rdi+10h]
0x1800b0fe0  jz      short loc_1800B0FEC
0x1800b0fe2  mov     [rdx], rbx
0x1800b0fe5  add     qword ptr [rdi+8], 8
0x1800b0fea  jmp     short loc_1800B0FF8
0x1800b0fec  lea     r8, [rbp+var_18]
0x1800b0ff0  mov     rcx, rdi
0x1800b0ff3  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0ff8  lea     rax, [rbp+arg_0]
0x1800b0ffc  mov     [rbp+var_18], rax
0x1800b1000  mov     rdx, [rdi+8]
0x1800b1004  cmp     rdx, [rdi+10h]
0x1800b1008  jz      short loc_1800B1018
0x1800b100a  lea     rax, [rbp+arg_0]
0x1800b100e  mov     [rdx], rax
0x1800b1011  add     qword ptr [rdi+8], 8
0x1800b1016  jmp     short loc_1800B1024
0x1800b1018  lea     r8, [rbp+var_18]
0x1800b101c  mov     rcx, rdi
0x1800b101f  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1024  mov     [rbp+var_18], r12
0x1800b1028  mov     rdx, [rdi+8]
0x1800b102c  cmp     rdx, [rdi+10h]
0x1800b1030  jz      short loc_1800B103C
0x1800b1032  mov     [rdx], r12
0x1800b1035  add     qword ptr [rdi+8], 8
0x1800b103a  jmp     short loc_1800B1048
0x1800b103c  lea     r8, [rbp+var_18]
0x1800b1040  mov     rcx, rdi
0x1800b1043  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1048  mov     rax, rsi
0x1800b104b  mov     [rbp+var_18], rax
0x1800b104f  mov     rdx, [rdi+8]
0x1800b1053  cmp     rdx, [rdi+10h]
0x1800b1057  jz      short loc_1800B1063
0x1800b1059  mov     [rdx], rax
0x1800b105c  add     qword ptr [rdi+8], 8
0x1800b1061  jmp     short loc_1800B106F
0x1800b1063  lea     r8, [rbp+var_18]
0x1800b1067  mov     rcx, rdi
0x1800b106a  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b106f  mov     rax, r15
0x1800b1072  mov     [rbp+var_18], rax
0x1800b1076  mov     rdx, [rdi+8]
0x1800b107a  cmp     rdx, [rdi+10h]
0x1800b107e  jz      short loc_1800B108A
0x1800b1080  mov     [rdx], rax
0x1800b1083  add     qword ptr [rdi+8], 8
0x1800b1088  jmp     short loc_1800B1096
0x1800b108a  lea     r8, [rbp+var_18]
0x1800b108e  mov     rcx, rdi
0x1800b1091  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1096  mov     rax, [rbp+arg_20]
0x1800b109a  mov     [rbp+var_18], rax
0x1800b109e  mov     rdx, [rdi+8]
0x1800b10a2  cmp     rdx, [rdi+10h]
0x1800b10a6  jz      short loc_1800B10B2
0x1800b10a8  mov     [rdx], rax
0x1800b10ab  add     qword ptr [rdi+8], 8
0x1800b10b0  jmp     short loc_1800B10BE
0x1800b10b2  lea     r8, [rbp+var_18]
0x1800b10b6  mov     rcx, rdi
0x1800b10b9  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b10be  mov     rax, [rbp+arg_28]
0x1800b10c2  mov     [rbp+var_18], rax
0x1800b10c6  mov     rdx, [rdi+8]
0x1800b10ca  cmp     rdx, [rdi+10h]
0x1800b10ce  jz      short loc_1800B10DA
0x1800b10d0  mov     [rdx], rax
0x1800b10d3  add     qword ptr [rdi+8], 8
0x1800b10d8  jmp     short loc_1800B10E6
0x1800b10da  lea     r8, [rbp+var_18]
0x1800b10de  mov     rcx, rdi
0x1800b10e1  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b10e6  mov     eax, [rbp+arg_30]
0x1800b10e9  mov     [rbp+var_18], rax
0x1800b10ed  mov     rdx, [rdi+8]
0x1800b10f1  cmp     rdx, [rdi+10h]
0x1800b10f5  jz      short loc_1800B1101
0x1800b10f7  mov     [rdx], rax
0x1800b10fa  add     qword ptr [rdi+8], 8
0x1800b10ff  jmp     short loc_1800B110D
0x1800b1101  lea     r8, [rbp+var_18]
0x1800b1105  mov     rcx, rdi
0x1800b1108  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b110d  mov     rax, [rbp+arg_38]
0x1800b1114  mov     [rbp+var_18], rax
0x1800b1118  mov     rdx, [rdi+8]
0x1800b111c  cmp     rdx, [rdi+10h]
0x1800b1120  jz      short loc_1800B112C
0x1800b1122  mov     [rdx], rax
0x1800b1125  add     qword ptr [rdi+8], 8
0x1800b112a  jmp     short loc_1800B1138
0x1800b112c  lea     r8, [rbp+var_18]
0x1800b1130  mov     rcx, rdi
0x1800b1133  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1138  mov     rax, [rbp+arg_40]
0x1800b113f  mov     [rbp+var_18], rax
0x1800b1143  mov     rdx, [rdi+8]
0x1800b1147  cmp     rdx, [rdi+10h]
0x1800b114b  jz      short loc_1800B1157
0x1800b114d  mov     [rdx], rax
0x1800b1150  add     qword ptr [rdi+8], 8
0x1800b1155  jmp     short loc_1800B1163
0x1800b1157  lea     r8, [rbp+var_18]
0x1800b115b  mov     rcx, rdi
0x1800b115e  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1163  mov     eax, [r13+0A0h]
0x1800b116a  mov     [rbp+var_18], rax
0x1800b116e  mov     rdx, [rdi+8]
0x1800b1172  cmp     rdx, [rdi+10h]
0x1800b1176  jz      short loc_1800B1182
0x1800b1178  mov     [rdx], rax
0x1800b117b  add     qword ptr [rdi+8], 8
0x1800b1180  jmp     short loc_1800B118E
0x1800b1182  lea     r8, [rbp+var_18]
0x1800b1186  mov     rcx, rdi
0x1800b1189  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b118e  mov     rdx, r14
0x1800b1191  mov     ecx, 6
0x1800b1196  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b119b  test    eax, eax
0x1800b119d  jz      short loc_1800B11C8
0x1800b119f  test    r14, r14
0x1800b11a2  jz      short loc_1800B11AC
0x1800b11a4  mov     rcx, r14; this
0x1800b11a7  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b11ac  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b11b3  xor     edx, edx; struct _GUID *
0x1800b11b5  lea     rcx, aWwansapconnect_0; "WwanSapConnect"
0x1800b11bc  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b11c1  mov     ebx, 1Fh
0x1800b11c6  jmp     short loc_1800B121B
0x1800b11c8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b11cb  mov     rcx, rbx; hHandle
0x1800b11ce  call    cs:__imp_WaitForSingleObject
0x1800b11d4  test    eax, eax
0x1800b11d6  jz      short loc_1800B11F9
0x1800b11d8  call    cs:__imp_GetLastError
0x1800b11de  mov     r9d, eax; unsigned int
0x1800b11e1  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b11e8  mov     edx, 2EAh; unsigned int
0x1800b11ed  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b11f4  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b11f9  mov     ebx, [rbp+arg_0]
0x1800b11fc  test    ebx, ebx
0x1800b11fe  jnz     short loc_1800B121B
0x1800b1200  test    cs:byte_1801528C2, 10h
0x1800b1207  jz      short loc_1800B121B
0x1800b1209  mov     r8, r12
0x1800b120c  lea     rdx, CancelWwanResumeReconnect
0x1800b1213  call    McTemplateU0j_EventWriteTransfer
0x1800b1218  mov     ebx, [rbp+arg_0]
0x1800b121b  lea     rcx, [rbp+var_10]
0x1800b121f  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b1224  mov     eax, ebx
0x1800b1226  add     rsp, 38h
0x1800b122a  pop     r15
0x1800b122c  pop     r14
0x1800b122e  pop     r13
0x1800b1230  pop     r12
0x1800b1232  pop     rdi
0x1800b1233  pop     rsi
0x1800b1234  pop     rbx
0x1800b1235  pop     rbp
0x1800b1236  retn
```
