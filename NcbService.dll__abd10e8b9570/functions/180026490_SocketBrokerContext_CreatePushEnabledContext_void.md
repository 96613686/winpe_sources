# SocketBrokerContext::CreatePushEnabledContext(void *)

- ea: `0x180026490`
- end: `0x180026665`
- name: `?CreatePushEnabledContext@SocketBrokerContext@@QEAAKPEAX@Z`
- size: `469`
- prototype: `__int64 __fastcall(SocketBrokerContext *this, HANDLE Process)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029d40`

## callees

- `0x18000a0a0`
- `0x18000ad30`
- `0x180012be0`
- `0x18001d8e0`
- `0x18001e368`
- `0x18002129c`
- `0x180026490`
- `0x18002666c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026514`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026514`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026546`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800264ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800264ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026636`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026636`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18002653c`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18002653c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180026508`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180026508`
- `NSI!NsiSetAllParameters` at `0x18002660e`
- `NSI!NsiSetAllParameters` at `0x18002660e`

## string_xrefs

- `0x180026529`: `CreatePushEnabledContext:Failed to get Process ID`
- `0x18002655b`: `CreatePushEnabledContext: Failed to get Process session ID %d`
- `0x180026623`: `CreatePushEnabledContext: NsiSetAllParameters failed with `

## pseudocode

```c
__int64 __fastcall SocketBrokerContext::CreatePushEnabledContext(SocketBrokerContext *this, HANDLE Process)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  DWORD ProcessId; // eax
  DWORD v7; // edi
  DWORD LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  const wchar_t *v11; // r8
  __int64 WpmEpoc; // rax
  const unsigned __int16 *v13; // r8
  DWORD pSessionId; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v16; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v17[128]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v18; // [rsp+E0h] [rbp-20h]
  unsigned __int16 v19[262]; // [rsp+E4h] [rbp-1Ch] BYREF
  __int64 v20; // [rsp+2F0h] [rbp+1F0h]
  __int64 v21; // [rsp+2F8h] [rbp+1F8h]
  char v22; // [rsp+320h] [rbp+220h]
  __int16 v23; // [rsp+322h] [rbp+222h]
  int v24; // [rsp+324h] [rbp+224h]

  memset_0(v17, 0, 0x2C8u);
  pSessionId = 0;
  v16 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  LOBYTE(v4) = 1;
  if ( !(unsigned __int8)NcbRegistrarEffectiveSlotTypeRequiresHardware(v4) )
  {
    v5 = 50;
    goto LABEL_14;
  }
  ProcessId = GetProcessId(Process);
  v7 = ProcessId;
  if ( !ProcessId )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_14;
    v11 = L"CreatePushEnabledContext:Failed to get Process ID";
LABEL_13:
    McTemplateU0zq_EventWriteTransfer(v10, v9, v11, LastError);
    goto LABEL_14;
  }
  if ( !ProcessIdToSessionId(ProcessId, &pSessionId) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_14;
    v11 = L"CreatePushEnabledContext: Failed to get Process session ID %d";
    goto LABEL_13;
  }
  v5 = 0;
  if ( v7 != *((_DWORD *)this + 32) )
  {
    SocketBrokerContext::DeletePushEnableContext(this);
    *((_QWORD *)&v16 + 1) = *((_QWORD *)this + 17);
    v21 = 2;
    v22 = 0;
    LODWORD(v16) = v7;
    v23 = 1;
    v24 = 5;
    WpmEpoc = NcbRegistrarGetWpmEpoc();
    v13 = (const unsigned __int16 *)*((_QWORD *)this + 6);
    v20 = WpmEpoc;
    StringCchCopyW(v19, 0x104u, v13);
    v18 = pSessionId;
    LastError = NsiSetAllParameters(1, 2, NPI_MS_TCP_MODULEID, 31, &v16, 16, v17, 712);
    v5 = LastError;
    if ( LastError )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        v11 = L"CreatePushEnabledContext: NsiSetAllParameters failed with ";
        goto LABEL_13;
      }
    }
  }
LABEL_14:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return v5;
}

```

## disassembly

```asm
0x180026490  mov     [rsp-8+arg_10], rbx
0x180026495  mov     [rsp-8+arg_18], rsi
0x18002649a  push    rbp
0x18002649b  push    rdi
0x18002649c  push    r14
0x18002649e  lea     rbp, [rsp-240h]
0x1800264a6  sub     rsp, 340h
0x1800264ad  mov     rax, cs:__security_cookie
0x1800264b4  xor     rax, rsp
0x1800264b7  mov     [rbp+250h+var_20], rax
0x1800264be  mov     rbx, rdx
0x1800264c1  mov     rsi, rcx
0x1800264c4  xor     edx, edx; Val
0x1800264c6  lea     rcx, [rsp+350h+var_2F0]; void *
0x1800264cb  mov     r8d, 2C8h; Size
0x1800264d1  call    memset_0
0x1800264d6  xorps   xmm0, xmm0
0x1800264d9  mov     [rsp+350h+pSessionId], 0
0x1800264e1  lea     rcx, [rsi+40h]; lpCriticalSection
0x1800264e5  movups  [rsp+350h+var_308], xmm0
0x1800264ea  call    cs:__imp_EnterCriticalSection
0x1800264f0  mov     cl, 1
0x1800264f2  call    NcbRegistrarEffectiveSlotTypeRequiresHardware
0x1800264f7  test    al, al
0x1800264f9  jnz     short loc_180026505
0x1800264fb  mov     ebx, 32h ; '2'
0x180026500  jmp     loc_180026632
0x180026505  mov     rcx, rbx; Process
0x180026508  call    cs:__imp_GetProcessId
0x18002650e  mov     edi, eax
0x180026510  test    eax, eax
0x180026512  jnz     short loc_180026535
0x180026514  call    cs:__imp_GetLastError
0x18002651a  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180026521  mov     ebx, eax
0x180026523  jz      loc_180026632
0x180026529  lea     r8, aCreatepushenab; "CreatePushEnabledContext:Failed to get "...
0x180026530  jmp     loc_18002662A
0x180026535  lea     rdx, [rsp+350h+pSessionId]; pSessionId
0x18002653a  mov     ecx, edi; dwProcessId
0x18002653c  call    cs:__imp_ProcessIdToSessionId
0x180026542  test    eax, eax
0x180026544  jnz     short loc_180026567
0x180026546  call    cs:__imp_GetLastError
0x18002654c  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180026553  mov     ebx, eax
0x180026555  jz      loc_180026632
0x18002655b  lea     r8, aCreatepushenab_1; "CreatePushEnabledContext: Failed to get"...
0x180026562  jmp     loc_18002662A
0x180026567  xor     ebx, ebx
0x180026569  cmp     edi, [rsi+80h]
0x18002656f  jz      loc_180026632
0x180026575  mov     rcx, rsi; this
0x180026578  call    ?DeletePushEnableContext@SocketBrokerContext@@AEAAKXZ; SocketBrokerContext::DeletePushEnableContext(void)
0x18002657d  mov     rax, [rsi+88h]
0x180026584  mov     ebx, 2
0x180026589  mov     qword ptr [rsp+350h+var_308+8], rax
0x18002658e  mov     [rbp+250h+var_58], rbx
0x180026595  mov     [rbp+250h+var_30], 0
0x18002659c  mov     dword ptr [rsp+350h+var_308], edi
0x1800265a0  mov     [rbp+250h+var_2E], 1
0x1800265a9  mov     [rbp+250h+var_2C], 5
0x1800265b3  call    NcbRegistrarGetWpmEpoc
0x1800265b8  mov     r8, [rsi+30h]; unsigned __int16 *
0x1800265bc  lea     rcx, [rbp+250h+var_26C]; unsigned __int16 *
0x1800265c0  mov     edx, 104h; unsigned __int64
0x1800265c5  mov     [rbp+250h+var_60], rax
0x1800265cc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800265d1  mov     r10d, [rsp+350h+pSessionId]
0x1800265d6  lea     rax, [rsp+350h+var_2F0]
0x1800265db  mov     [rsp+350h+var_318], 2C8h
0x1800265e3  lea     r9d, [rbx+1Dh]
0x1800265e7  mov     [rsp+350h+var_320], rax
0x1800265ec  lea     r8, NPI_MS_TCP_MODULEID
0x1800265f3  lea     rax, [rsp+350h+var_308]
0x1800265f8  mov     [rsp+350h+var_328], 10h
0x180026600  mov     edx, ebx
0x180026602  mov     [rsp+350h+var_330], rax
0x180026607  lea     ecx, [rbx-1]
0x18002660a  mov     [rbp+250h+var_270], r10d
0x18002660e  call    cs:__imp_NsiSetAllParameters
0x180026614  mov     ebx, eax
0x180026616  test    eax, eax
0x180026618  jz      short loc_180026632
0x18002661a  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180026621  jz      short loc_180026632
0x180026623  lea     r8, aCreatepushenab_0; "CreatePushEnabledContext: NsiSetAllPara"...
0x18002662a  mov     r9d, eax
0x18002662d  call    McTemplateU0zq_EventWriteTransfer
0x180026632  lea     rcx, [rsi+40h]; lpCriticalSection
0x180026636  call    cs:__imp_LeaveCriticalSection
0x18002663c  mov     eax, ebx
0x18002663e  mov     rcx, [rbp+250h+var_20]
0x180026645  xor     rcx, rsp; StackCookie
0x180026648  call    __security_check_cookie
0x18002664d  lea     r11, [rsp+350h+var_10]
0x180026655  mov     rbx, [r11+30h]
0x180026659  mov     rsi, [r11+38h]
0x18002665d  mov     rsp, r11
0x180026660  pop     r14
0x180026662  pop     rdi
0x180026663  pop     rbp
0x180026664  retn
```
