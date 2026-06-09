# SocketBrokerContext::RetrieveContext(ushort const *,_SOCKET_BROKER_APP_CONTEXT * *)

- ea: `0x180026940`
- end: `0x180026a00`
- name: `?RetrieveContext@SocketBrokerContext@@QEAAKPEBGPEAPEAU_SOCKET_BROKER_APP_CONTEXT@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(SocketBrokerContext *this, const unsigned __int16 *, struct _SOCKET_BROKER_APP_CONTEXT **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180029f20`

## callees

- `0x180002770`
- `0x18000a0a0`
- `0x1800232dc`
- `0x180026940`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002695b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002699e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002695b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002699e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800269d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800269ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800269d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800269ed`

## string_xrefs

- `0x1800269c5`: `SharedSocket: NcbUtilsCopySBUserContext failed with`

## pseudocode

```c
__int64 __fastcall SocketBrokerContext::RetrieveContext(
        SocketBrokerContext *this,
        const unsigned __int16 *a2,
        struct _SOCKET_BROKER_APP_CONTEXT **a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  void (__fastcall ***Socket)(__int64); // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  void (__fastcall ***v10)(__int64); // rdi
  unsigned int v11; // ebx
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  *a3 = 0;
  Socket = SocketBrokerContext::FindSocket(this, a2);
  v10 = Socket;
  if ( Socket )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)Socket + 1);
    v12 = NcbUtilsCopySBAppContext(v10[16], a3);
    v11 = v12;
    if ( v12 && (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v14, v13, L"SharedSocket: NcbUtilsCopySBUserContext failed with", v12);
    LeaveCriticalSection((LPCRITICAL_SECTION)v10 + 1);
    (*v10)[1]((__int64)v10);
  }
  else
  {
    v11 = 4312;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v9, v8, L"RetrieveContext: could not find the socket", 4312);
  }
  LeaveCriticalSection(v3);
  return v11;
}

```

## disassembly

```asm
0x180026940  push    rbx
0x180026942  push    rbp
0x180026943  push    rsi
0x180026944  push    rdi
0x180026945  push    r14
0x180026947  sub     rsp, 20h
0x18002694b  lea     rbp, [rcx+40h]
0x18002694f  mov     rdi, rcx
0x180026952  mov     rcx, rbp; lpCriticalSection
0x180026955  mov     r14, r8
0x180026958  mov     rbx, rdx
0x18002695b  call    cs:__imp_EnterCriticalSection
0x180026961  mov     rdx, rbx; unsigned __int16 *
0x180026964  mov     qword ptr [r14], 0
0x18002696b  mov     rcx, rdi; this
0x18002696e  call    ?FindSocket@SocketBrokerContext@@AEAAPEAVSharedSocket@@PEBG@Z; SocketBrokerContext::FindSocket(ushort const *)
0x180026973  mov     rdi, rax
0x180026976  test    rax, rax
0x180026979  jnz     short loc_18002699A
0x18002697b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180026982  mov     ebx, 10D8h
0x180026987  jz      short loc_1800269EA
0x180026989  mov     r9d, ebx
0x18002698c  lea     r8, aRetrievecontex; "RetrieveContext: could not find the soc"...
0x180026993  call    McTemplateU0zq_EventWriteTransfer
0x180026998  jmp     short loc_1800269EA
0x18002699a  lea     rcx, [rax+28h]; lpCriticalSection
0x18002699e  call    cs:__imp_EnterCriticalSection
0x1800269a4  mov     rcx, [rdi+80h]
0x1800269ab  mov     rdx, r14
0x1800269ae  call    NcbUtilsCopySBAppContext
0x1800269b3  mov     ebx, eax
0x1800269b5  test    eax, eax
0x1800269b7  jz      short loc_1800269D1
0x1800269b9  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800269c0  jz      short loc_1800269D1
0x1800269c2  mov     r9d, eax
0x1800269c5  lea     r8, aSharedsocketNc_0; "SharedSocket: NcbUtilsCopySBUserContext"...
0x1800269cc  call    McTemplateU0zq_EventWriteTransfer
0x1800269d1  lea     rcx, [rdi+28h]; lpCriticalSection
0x1800269d5  call    cs:__imp_LeaveCriticalSection
0x1800269db  mov     rdx, [rdi]
0x1800269de  mov     rcx, rdi
0x1800269e1  mov     rax, [rdx+8]
0x1800269e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269ea  mov     rcx, rbp; lpCriticalSection
0x1800269ed  call    cs:__imp_LeaveCriticalSection
0x1800269f3  mov     eax, ebx
0x1800269f5  add     rsp, 20h
0x1800269f9  pop     r14
0x1800269fb  pop     rdi
0x1800269fc  pop     rsi
0x1800269fd  pop     rbp
0x1800269fe  pop     rbx
0x1800269ff  retn
```
