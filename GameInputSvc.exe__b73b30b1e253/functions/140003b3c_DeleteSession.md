# DeleteSession

- ea: `0x140003b3c`
- end: `0x140003c55`
- name: `DeleteSession`
- size: `281`
- prototype: `BOOLEAN __fastcall(HANDLE *)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400038b0`
- `0x1400039a8`
- `0x1400046a0`
- `0x140004950`

## callees

- `0x14000116c`
- `0x140003b3c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140003c4e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003b6a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003c1a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003b6a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003c1a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140003b52`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140003b52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c31`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140003b81`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140003b81`

## string_xrefs

- `0x140003bb5`: `GameInput Instance timeout during Session deletion`

## pseudocode

```c
BOOLEAN __fastcall DeleteSession(HANDLE *a1)
{
  HANDLE v2; // rcx
  HANDLE v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  HANDLE v6; // rcx
  int v8; // [rsp+50h] [rbp+8h] BYREF
  const char *v9; // [rsp+58h] [rbp+10h] BYREF
  const char *v10; // [rsp+60h] [rbp+18h] BYREF

  v2 = a1[13];
  if ( v2 )
  {
    SetEvent(v2);
    v3 = a1[15];
    if ( v3 )
    {
      if ( WaitForSingleObject(v3, 0x1388u) )
      {
        TerminateProcess(a1[15], 0x5B4u);
        if ( (unsigned int)dword_14000E000 > 2
          && (qword_14000E010 & 0x800) != 0
          && (qword_14000E018 & 0x800) == qword_14000E018 )
        {
          v8 = 69;
          v9 = "GameInput Instance timeout during Session deletion";
          v10 = "onecore\\xbox\\gameinput\\published\\svc\\session.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            qword_14000E018,
            (int)word_14000B1FA,
            v4,
            v5,
            (__int64 **)&v10,
            (__int64)&v8,
            (__int64 **)&v9);
        }
      }
      CloseHandle(a1[15]);
    }
    v6 = a1[16];
    if ( v6 )
    {
      WaitForSingleObject(v6, 0x1388u);
      CloseHandle(a1[16]);
    }
    CloseHandle(a1[13]);
  }
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x140003b3c  push    rbx
0x140003b3e  sub     rsp, 40h
0x140003b42  mov     rbx, rcx
0x140003b45  mov     rcx, [rcx+68h]; hEvent
0x140003b49  test    rcx, rcx
0x140003b4c  jz      loc_140003C37
0x140003b52  call    cs:__imp_SetEvent
0x140003b58  mov     rcx, [rbx+78h]; hHandle
0x140003b5c  test    rcx, rcx
0x140003b5f  jz      loc_140003C09
0x140003b65  mov     edx, 1388h; dwMilliseconds
0x140003b6a  call    cs:__imp_WaitForSingleObject
0x140003b70  test    eax, eax
0x140003b72  jz      loc_140003BFF
0x140003b78  mov     rcx, [rbx+78h]; hProcess
0x140003b7c  mov     edx, 5B4h; uExitCode
0x140003b81  call    cs:__imp_TerminateProcess
0x140003b87  mov     eax, cs:dword_14000E000
0x140003b8d  cmp     eax, 2
0x140003b90  jbe     short loc_140003BFF
0x140003b92  mov     rcx, cs:qword_14000E018
0x140003b99  mov     edx, 800h
0x140003b9e  mov     rax, cs:qword_14000E010
0x140003ba5  test    rdx, rax
0x140003ba8  jz      short loc_140003BFF
0x140003baa  mov     rax, rcx
0x140003bad  and     rax, rdx
0x140003bb0  cmp     rax, rcx
0x140003bb3  jnz     short loc_140003BFF
0x140003bb5  lea     rax, aGameinputInsta; "GameInput Instance timeout during Sessi"...
0x140003bbc  mov     [rsp+48h+arg_0], 45h ; 'E'
0x140003bc4  mov     [rsp+48h+arg_8], rax
0x140003bc9  lea     rdx, word_14000B1FA
0x140003bd0  lea     rax, aOnecoreXboxGam_3; "onecore\\xbox\\gameinput\\published\\sv"...
0x140003bd7  mov     [rsp+48h+arg_10], rax
0x140003bdc  lea     rax, [rsp+48h+arg_8]
0x140003be1  mov     [rsp+48h+var_18], rax
0x140003be6  lea     rax, [rsp+48h+arg_0]
0x140003beb  mov     [rsp+48h+var_20], rax
0x140003bf0  lea     rax, [rsp+48h+arg_10]
0x140003bf5  mov     [rsp+48h+var_28], rax
0x140003bfa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140003bff  mov     rcx, [rbx+78h]; hObject
0x140003c03  call    cs:__imp_CloseHandle
0x140003c09  mov     rcx, [rbx+80h]; hHandle
0x140003c10  test    rcx, rcx
0x140003c13  jz      short loc_140003C2D
0x140003c15  mov     edx, 1388h; dwMilliseconds
0x140003c1a  call    cs:__imp_WaitForSingleObject
0x140003c20  mov     rcx, [rbx+80h]; hObject
0x140003c27  call    cs:__imp_CloseHandle
0x140003c2d  mov     rcx, [rbx+68h]; hObject
0x140003c31  call    cs:__imp_CloseHandle
0x140003c37  mov     rcx, gs:60h
0x140003c40  mov     r8, rbx
0x140003c43  xor     edx, edx
0x140003c45  mov     rcx, [rcx+30h]
0x140003c49  add     rsp, 40h
0x140003c4d  pop     rbx
0x140003c4e  jmp     cs:__imp_RtlFreeHeap
```
