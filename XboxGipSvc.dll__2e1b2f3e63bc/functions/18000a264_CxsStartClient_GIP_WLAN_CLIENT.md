# CxsStartClient(_GIP_WLAN_CLIENT *)

- ea: `0x18000a264`
- end: `0x18000a363`
- name: `?CxsStartClient@@YAKPEAU_GIP_WLAN_CLIENT@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(struct _GIP_WLAN_CLIENT *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800069a4`

## callees

- `0x180002158`
- `0x180002b70`
- `0x18000a264`
- `0x18000a450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a307`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a28a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a28a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a2d3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a2d3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000a2f8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000a2f8`

## pseudocode

```c
__int64 __fastcall CxsStartClient(struct _GIP_WLAN_CLIENT *a1)
{
  HANDLE EventW; // rax
  DWORD LastError; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  HANDLE Thread; // rax

  memset_0(a1, 0, 0xA8u);
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)a1 + 6) = EventW;
  if ( EventW )
  {
    InitializeCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 8));
    Thread = CreateThread(0, 0, CxsWorkerThread, a1, 0, 0);
    *((_QWORD *)a1 + 7) = Thread;
    if ( Thread )
      return 0;
    LastError = GetLastError();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 41;
      goto LABEL_11;
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 40;
LABEL_11:
      WPP_SF_D(v4[2], v5, &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids, LastError);
    }
  }
  if ( LastError )
    CxsStopClient(a1);
  return LastError;
}

```

## disassembly

```asm
0x18000a264  mov     [rsp+arg_0], rbx
0x18000a269  push    rdi
0x18000a26a  sub     rsp, 30h
0x18000a26e  xor     edx, edx; Val
0x18000a270  mov     r8d, 0A8h; Size
0x18000a276  mov     rdi, rcx
0x18000a279  call    memset_0
0x18000a27e  xor     r9d, r9d; lpName
0x18000a281  xor     r8d, r8d; bInitialState
0x18000a284  xor     ecx, ecx; lpEventAttributes
0x18000a286  lea     edx, [r9+1]; bManualReset
0x18000a28a  call    cs:__imp_CreateEventW
0x18000a290  mov     [rdi+30h], rax
0x18000a294  test    rax, rax
0x18000a297  jnz     short loc_18000A2CF
0x18000a299  call    cs:__imp_GetLastError
0x18000a29f  mov     ebx, eax
0x18000a2a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2a8  lea     rax, WPP_GLOBAL_Control
0x18000a2af  cmp     rcx, rax
0x18000a2b2  jz      loc_18000A346
0x18000a2b8  test    byte ptr [rcx+1Ch], 1
0x18000a2bc  jz      loc_18000A346
0x18000a2c2  cmp     byte ptr [rcx+19h], 2
0x18000a2c6  jb      short loc_18000A346
0x18000a2c8  mov     edx, 28h ; '('
0x18000a2cd  jmp     short loc_18000A333
0x18000a2cf  lea     rcx, [rdi+8]; lpCriticalSection
0x18000a2d3  call    cs:__imp_InitializeCriticalSection
0x18000a2d9  mov     r9, rdi; lpParameter
0x18000a2dc  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18000a2e5  lea     r8, ?CxsWorkerThread@@YAKPEAX@Z; lpStartAddress
0x18000a2ec  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18000a2f4  xor     edx, edx; dwStackSize
0x18000a2f6  xor     ecx, ecx; lpThreadAttributes
0x18000a2f8  call    cs:__imp_CreateThread
0x18000a2fe  mov     [rdi+38h], rax
0x18000a302  test    rax, rax
0x18000a305  jnz     short loc_18000A354
0x18000a307  call    cs:__imp_GetLastError
0x18000a30d  mov     ebx, eax
0x18000a30f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a316  lea     rax, WPP_GLOBAL_Control
0x18000a31d  cmp     rcx, rax
0x18000a320  jz      short loc_18000A346
0x18000a322  test    byte ptr [rcx+1Ch], 1
0x18000a326  jz      short loc_18000A346
0x18000a328  cmp     byte ptr [rcx+19h], 2
0x18000a32c  jb      short loc_18000A346
0x18000a32e  mov     edx, 29h ; ')'
0x18000a333  mov     rcx, [rcx+10h]
0x18000a337  lea     r8, WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids
0x18000a33e  mov     r9d, ebx
0x18000a341  call    WPP_SF_D
0x18000a346  test    ebx, ebx
0x18000a348  jz      short loc_18000A356
0x18000a34a  mov     rcx, rdi; struct _GIP_WLAN_CLIENT *
0x18000a34d  call    ?CxsStopClient@@YAXPEAU_GIP_WLAN_CLIENT@@@Z; CxsStopClient(_GIP_WLAN_CLIENT *)
0x18000a352  jmp     short loc_18000A356
0x18000a354  xor     ebx, ebx
0x18000a356  mov     eax, ebx
0x18000a358  mov     rbx, [rsp+38h+arg_0]
0x18000a35d  add     rsp, 30h
0x18000a361  pop     rdi
0x18000a362  retn
```
