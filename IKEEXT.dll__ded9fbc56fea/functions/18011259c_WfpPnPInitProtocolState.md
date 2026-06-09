# WfpPnPInitProtocolState

- ea: `0x18011259c`
- end: `0x180112703`
- name: `WfpPnPInitProtocolState`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18011270c`

## callees

- `0x180004570`
- `0x1800061ec`
- `0x180010db0`
- `0x180014410`
- `0x18011259c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801125e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801125e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112677`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180112602`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180112602`
- `WS2_32!WSASocketA` at `0x1801125d7`
- `WS2_32!WSASocketA` at `0x1801125d7`
- `WS2_32!WSAEventSelect` at `0x18011262f`
- `WS2_32!WSAEventSelect` at `0x18011262f`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180112668`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180112668`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x1801126c2`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x1801126c2`

## string_xrefs

- `0x180112617`: `CreateEventA`
- `0x1801126e6`: `WfpPnPInitProtocolState`

## pseudocode

```c
__int64 __fastcall WfpPnPInitProtocolState(int a1, SOCKET *a2)
{
  int v2; // ebp
  void *v3; // rbx
  SOCKET v5; // rax
  DWORD LastError; // eax
  __int64 v7; // rcx
  const char *v8; // rdx
  HANDLE EventA; // rax
  void *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rbx

  v2 = 23;
  v3 = (void *)a1;
  if ( a1 != 1 )
    v2 = 2;
  v5 = WSASocketA(v2, 2, 0, 0, 0, 0);
  *a2 = v5;
  if ( v5 == -1 )
  {
    LastError = GetLastError();
    v8 = "WSASocketA";
    goto LABEL_15;
  }
  EventA = CreateEventA(0, 0, 0, 0);
  a2[1] = (SOCKET)EventA;
  if ( !EventA )
  {
    LastError = GetLastError();
    v8 = "CreateEventA";
    goto LABEL_15;
  }
  if ( WSAEventSelect(*a2, EventA, 512) )
  {
    LastError = GetLastError();
    v8 = "WSAEventSelect";
    goto LABEL_15;
  }
  v10 = v3;
  v11 = RegisterWaitForSingleObjectEx(a2[1], WfpPnpThreadPoolCallback, v3, 0xFFFFFFFFLL, 0);
  a2[2] = v11;
  if ( !v11 )
  {
    LastError = GetLastError();
    v8 = "RegisterWaitForSingleObjectEx";
    goto LABEL_15;
  }
  v12 = WfpPnPQueryAddressList((unsigned int)v3, a2 + 4);
  if ( v12 )
    goto LABEL_16;
  v12 = WfpPnPRegisterForAddressListChange(*a2);
  if ( v12 )
    goto LABEL_16;
  LastError = NotifyIpInterfaceChange(v2, WfpPnPNLInterfaceCallback, v10, 1u, (HANDLE *)a2 + 3);
  if ( LastError )
  {
    v8 = "NotifyIpInterfaceChange";
LABEL_15:
    v12 = WfpReportSysErrorAsWinError(v7, v8, LastError, 1);
    if ( v12 )
LABEL_16:
      WfpReportError(v12, "WfpPnPInitProtocolState");
  }
  return v12;
}

```

## disassembly

```asm
0x18011259c  push    rbx
0x18011259e  push    rbp
0x18011259f  push    rsi
0x1801125a0  push    rdi
0x1801125a1  push    r15
0x1801125a3  sub     rsp, 30h
0x1801125a7  mov     ebp, 17h
0x1801125ac  movsxd  rbx, ecx
0x1801125af  mov     rdi, rdx
0x1801125b2  mov     [rsp+58h+dwFlags], 0; dwFlags
0x1801125ba  mov     [rsp+58h+g], 0; g
0x1801125c2  lea     r15d, [rbp-16h]
0x1801125c6  lea     edx, [rbp-15h]; type
0x1801125c9  cmp     ebx, r15d
0x1801125cc  cmovnz  ebp, edx
0x1801125cf  xor     r9d, r9d; lpProtocolInfo
0x1801125d2  mov     ecx, ebp; af
0x1801125d4  xor     r8d, r8d; protocol
0x1801125d7  call    cs:__imp_WSASocketA
0x1801125dd  mov     [rdi], rax
0x1801125e0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801125e4  jnz     short loc_1801125F8
0x1801125e6  call    cs:__imp_GetLastError
0x1801125ec  lea     rdx, aWsasocketa; "WSASocketA"
0x1801125f3  jmp     loc_1801126D3
0x1801125f8  xor     r9d, r9d; lpName
0x1801125fb  xor     r8d, r8d; bInitialState
0x1801125fe  xor     edx, edx; bManualReset
0x180112600  xor     ecx, ecx; lpEventAttributes
0x180112602  call    cs:__imp_CreateEventA
0x180112608  mov     [rdi+8], rax
0x18011260c  test    rax, rax
0x18011260f  jnz     short loc_180112623
0x180112611  call    cs:__imp_GetLastError
0x180112617  lea     rdx, aCreateeventa; "CreateEventA"
0x18011261e  jmp     loc_1801126D3
0x180112623  mov     rcx, [rdi]; s
0x180112626  mov     r8d, 200h; lNetworkEvents
0x18011262c  mov     rdx, rax; hEventObject
0x18011262f  call    cs:__imp_WSAEventSelect
0x180112635  test    eax, eax
0x180112637  jz      short loc_18011264B
0x180112639  call    cs:__imp_GetLastError
0x18011263f  lea     rdx, aWsaeventselect; "WSAEventSelect"
0x180112646  jmp     loc_1801126D3
0x18011264b  mov     rcx, [rdi+8]
0x18011264f  lea     rdx, WfpPnpThreadPoolCallback
0x180112656  or      r9d, 0FFFFFFFFh
0x18011265a  mov     [rsp+58h+g], 0
0x180112662  mov     r8, rbx
0x180112665  mov     rsi, rbx
0x180112668  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18011266e  mov     [rdi+10h], rax
0x180112672  test    rax, rax
0x180112675  jnz     short loc_180112686
0x180112677  call    cs:__imp_GetLastError
0x18011267d  lea     rdx, aRegisterwaitfo; "RegisterWaitForSingleObjectEx"
0x180112684  jmp     short loc_1801126D3
0x180112686  lea     rdx, [rdi+20h]
0x18011268a  mov     ecx, ebx
0x18011268c  call    WfpPnPQueryAddressList
0x180112691  mov     rbx, rax
0x180112694  test    rax, rax
0x180112697  jnz     short loc_1801126E6
0x180112699  mov     rcx, [rdi]
0x18011269c  call    WfpPnPRegisterForAddressListChange
0x1801126a1  mov     rbx, rax
0x1801126a4  test    rax, rax
0x1801126a7  jnz     short loc_1801126E6
0x1801126a9  lea     rax, [rdi+18h]
0x1801126ad  movzx   ecx, bp; Family
0x1801126b0  mov     r9b, r15b; InitialNotification
0x1801126b3  mov     qword ptr [rsp+58h+g], rax; NotificationHandle
0x1801126b8  mov     r8, rsi; CallerContext
0x1801126bb  lea     rdx, WfpPnPNLInterfaceCallback; Callback
0x1801126c2  call    cs:__imp_NotifyIpInterfaceChange
0x1801126c8  test    eax, eax
0x1801126ca  jz      short loc_1801126F5
0x1801126cc  lea     rdx, aNotifyipinterf_0; "NotifyIpInterfaceChange"
0x1801126d3  mov     r9d, r15d
0x1801126d6  mov     r8d, eax
0x1801126d9  call    WfpReportSysErrorAsWinError
0x1801126de  mov     rbx, rax
0x1801126e1  test    rax, rax
0x1801126e4  jz      short loc_1801126F5
0x1801126e6  lea     rdx, aWfppnpinitprot; "WfpPnPInitProtocolState"
0x1801126ed  mov     rcx, rbx
0x1801126f0  call    WfpReportError
0x1801126f5  mov     rax, rbx
0x1801126f8  add     rsp, 30h
0x1801126fc  pop     r15
0x1801126fe  pop     rdi
0x1801126ff  pop     rsi
0x180112700  pop     rbp
0x180112701  pop     rbx
0x180112702  retn
```
