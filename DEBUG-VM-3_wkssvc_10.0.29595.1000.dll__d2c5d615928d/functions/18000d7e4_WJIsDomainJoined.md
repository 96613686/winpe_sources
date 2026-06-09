# WJIsDomainJoined

- ea: `0x18000d7e4`
- end: `0x18000d8a4`
- name: `WJIsDomainJoined`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011438`

## callees

- `0x18000d7e4`

## import_xrefs

- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18000d85a`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18000d85a`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18000d814`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18000d88c`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18000d814`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18000d88c`
- `netutils!NetApiBufferFree` at `0x18000d875`
- `netutils!NetApiBufferFree` at `0x18000d875`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpGetJoinInformation` at `0x18000d82c`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpGetJoinInformation` at `0x18000d82c`

## pseudocode

```c
__int64 __fastcall WJIsDomainJoined(_DWORD *a1)
{
  int JoinInformation; // eax
  unsigned int v3; // edi
  unsigned int v4; // ebx
  void *v5; // rcx
  int v7; // [rsp+30h] [rbp+8h] BYREF
  LPVOID Buffer; // [rsp+38h] [rbp+10h] BYREF

  Buffer = 0;
  v7 = 0;
  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: started", L"WJIsDomainJoined");
  *a1 = 0;
  JoinInformation = NetpGetJoinInformation(0, &Buffer, &v7);
  v3 = JoinInformation;
  if ( JoinInformation )
  {
    if ( JoinInformation > 0 )
      v4 = (unsigned __int16)JoinInformation | 0x80070000;
    else
      v4 = JoinInformation;
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: NetpGetJoinInformation failed with exit code 0x%08x",
      L"WJIsDomainJoined",
      v4);
  }
  else
  {
    v5 = Buffer;
    v4 = 0;
    *a1 = v7 == 3;
    NetApiBufferFree(v5);
  }
  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: finished - hr: 0x%08x", L"WJIsDomainJoined", v4);
  return v3;
}

```

## disassembly

```asm
0x18000d7e4  mov     rax, rsp
0x18000d7e7  mov     [rax+18h], rbx
0x18000d7eb  mov     [rax+20h], rsi
0x18000d7ef  push    rdi
0x18000d7f0  sub     rsp, 20h
0x18000d7f4  mov     rsi, rcx
0x18000d7f7  mov     qword ptr [rax+10h], 0
0x18000d7ff  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18000d806  mov     dword ptr [rax+8], 0
0x18000d80d  lea     rdx, aWjisdomainjoin; "WJIsDomainJoined"
0x18000d814  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18000d81a  lea     r8, [rsp+28h+arg_0]
0x18000d81f  mov     dword ptr [rsi], 0
0x18000d825  lea     rdx, [rsp+28h+Buffer]
0x18000d82a  xor     ecx, ecx
0x18000d82c  call    cs:__imp_NetpGetJoinInformation
0x18000d832  mov     edi, eax
0x18000d834  test    eax, eax
0x18000d836  jz      short loc_18000D862
0x18000d838  test    eax, eax
0x18000d83a  jg      short loc_18000D840
0x18000d83c  mov     ebx, eax
0x18000d83e  jmp     short loc_18000D849
0x18000d840  movzx   ebx, di
0x18000d843  or      ebx, 80070000h
0x18000d849  mov     r8d, ebx
0x18000d84c  lea     rdx, aWjisdomainjoin; "WJIsDomainJoined"
0x18000d853  lea     rcx, aAutojoinsvcSNe; "AutoJoinSvc/%s: NetpGetJoinInformation "...
0x18000d85a  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18000d860  jmp     short loc_18000D87B
0x18000d862  mov     rcx, [rsp+28h+Buffer]; Buffer
0x18000d867  xor     eax, eax
0x18000d869  xor     ebx, ebx
0x18000d86b  cmp     [rsp+28h+arg_0], 3
0x18000d870  setz    al
0x18000d873  mov     [rsi], eax
0x18000d875  call    cs:__imp_NetApiBufferFree
0x18000d87b  mov     r8d, ebx
0x18000d87e  lea     rdx, aWjisdomainjoin; "WJIsDomainJoined"
0x18000d885  lea     rcx, aAutojoinsvcSFi_2; "AutoJoinSvc/%s: finished - hr: 0x%08x"
0x18000d88c  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18000d892  mov     rbx, [rsp+28h+arg_10]
0x18000d897  mov     eax, edi
0x18000d899  mov     rsi, [rsp+28h+arg_18]
0x18000d89e  add     rsp, 20h
0x18000d8a2  pop     rdi
0x18000d8a3  retn
```
