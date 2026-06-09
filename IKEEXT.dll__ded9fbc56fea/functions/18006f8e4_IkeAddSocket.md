# IkeAddSocket

- ea: `0x18006f8e4`
- end: `0x18006f9f2`
- name: `IkeAddSocket`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18007111c`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x18004aa3c`
- `0x18006f8e4`
- `0x18006fc4c`
- `0x180070044`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f95d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f95d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f984`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f94a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f94a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f9ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f9ba`
- `WS2_32!WSAEventSelect` at `0x18006f97a`
- `WS2_32!WSAEventSelect` at `0x18006f97a`
- `WS2_32!__imp_closesocket` at `0x18006f9ac`
- `WS2_32!__imp_closesocket` at `0x18006f9ac`

## string_xrefs

- `0x18006f963`: `CreateEventW`

## pseudocode

```c
__int64 __fastcall IkeAddSocket(unsigned __int16 a1, int a2, SOCKET *a3, _QWORD *a4)
{
  HANDLE EventW; // rax
  SOCKET v9; // rbx
  void *v10; // rdi
  DWORD LastError; // eax
  __int64 v12; // rcx
  const char *v13; // rdx
  __int64 v14; // rsi
  SOCKET s[7]; // [rsp+20h] [rbp-38h] BYREF

  s[0] = 0;
  TraceLogHelper("IkeAddSocket", 1);
  if ( a2 )
  {
    if ( a2 != 1 )
      __fastfail(5u);
    IkeCreateV6Socket(a1, s);
  }
  else
  {
    IkeCreateV4Socket(a1, s);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v9 = s[0];
  v10 = EventW;
  if ( EventW )
  {
    if ( !s[0] || !WSAEventSelect(s[0], EventW, 1) )
    {
      *a3 = v9;
      v14 = 0;
      *a4 = v10;
      goto LABEL_17;
    }
    LastError = GetLastError();
    v13 = "WSAEventSelect";
  }
  else
  {
    LastError = GetLastError();
    v13 = "CreateEventW";
  }
  v14 = WfpReportSysErrorAsWinError(v12, v13, LastError, 1);
  if ( v14 )
  {
    if ( v9 )
      closesocket(v9);
    if ( v10 )
      CloseHandle(v10);
  }
LABEL_17:
  TraceLogHelper("IkeAddSocket", 0);
  return IkeReturnError(v14, "IkeAddSocket");
}

```

## disassembly

```asm
0x18006f8e4  push    rbx
0x18006f8e6  push    rsi
0x18006f8e7  push    rdi
0x18006f8e8  push    r14
0x18006f8ea  push    r15
0x18006f8ec  sub     rsp, 30h
0x18006f8f0  mov     ebx, edx
0x18006f8f2  mov     [rsp+58h+s], 0
0x18006f8fb  movzx   edi, cx
0x18006f8fe  mov     esi, 1
0x18006f903  mov     edx, esi
0x18006f905  lea     rcx, aIkeaddsocket; "IkeAddSocket"
0x18006f90c  mov     r14, r9
0x18006f90f  mov     r15, r8
0x18006f912  call    TraceLogHelper
0x18006f917  test    ebx, ebx
0x18006f919  jz      short loc_18006F933
0x18006f91b  cmp     ebx, esi
0x18006f91d  jz      short loc_18006F924
0x18006f91f  lea     ecx, [rsi+4]
0x18006f922  int     29h; Win8: RtlFailFast(ecx)
0x18006f924  lea     rdx, [rsp+58h+s]
0x18006f929  movzx   ecx, di
0x18006f92c  call    IkeCreateV6Socket
0x18006f931  jmp     short loc_18006F940
0x18006f933  lea     rdx, [rsp+58h+s]
0x18006f938  movzx   ecx, di
0x18006f93b  call    IkeCreateV4Socket
0x18006f940  xor     r9d, r9d; lpName
0x18006f943  xor     r8d, r8d; bInitialState
0x18006f946  xor     edx, edx; bManualReset
0x18006f948  xor     ecx, ecx; lpEventAttributes
0x18006f94a  call    cs:__imp_CreateEventW
0x18006f950  mov     rbx, [rsp+58h+s]
0x18006f955  mov     rdi, rax
0x18006f958  test    rax, rax
0x18006f95b  jnz     short loc_18006F96C
0x18006f95d  call    cs:__imp_GetLastError
0x18006f963  lea     rdx, aCreateeventw; "CreateEventW"
0x18006f96a  jmp     short loc_18006F991
0x18006f96c  test    rbx, rbx
0x18006f96f  jz      short loc_18006F9C2
0x18006f971  mov     r8d, esi; lNetworkEvents
0x18006f974  mov     rdx, rdi; hEventObject
0x18006f977  mov     rcx, rbx; s
0x18006f97a  call    cs:__imp_WSAEventSelect
0x18006f980  test    eax, eax
0x18006f982  jz      short loc_18006F9C2
0x18006f984  call    cs:__imp_GetLastError
0x18006f98a  lea     rdx, aWsaeventselect; "WSAEventSelect"
0x18006f991  mov     r9d, esi
0x18006f994  mov     r8d, eax
0x18006f997  call    WfpReportSysErrorAsWinError
0x18006f99c  mov     rsi, rax
0x18006f99f  test    rax, rax
0x18006f9a2  jz      short loc_18006F9CA
0x18006f9a4  test    rbx, rbx
0x18006f9a7  jz      short loc_18006F9B2
0x18006f9a9  mov     rcx, rbx; s
0x18006f9ac  call    cs:__imp_closesocket
0x18006f9b2  test    rdi, rdi
0x18006f9b5  jz      short loc_18006F9CA
0x18006f9b7  mov     rcx, rdi; hObject
0x18006f9ba  call    cs:__imp_CloseHandle
0x18006f9c0  jmp     short loc_18006F9CA
0x18006f9c2  mov     [r15], rbx
0x18006f9c5  xor     esi, esi
0x18006f9c7  mov     [r14], rdi
0x18006f9ca  xor     edx, edx
0x18006f9cc  lea     rcx, aIkeaddsocket; "IkeAddSocket"
0x18006f9d3  call    TraceLogHelper
0x18006f9d8  lea     rdx, aIkeaddsocket; "IkeAddSocket"
0x18006f9df  mov     rcx, rsi
0x18006f9e2  add     rsp, 30h
0x18006f9e6  pop     r15
0x18006f9e8  pop     r14
0x18006f9ea  pop     rdi
0x18006f9eb  pop     rsi
0x18006f9ec  pop     rbx
0x18006f9ed  jmp     IkeReturnError
```
