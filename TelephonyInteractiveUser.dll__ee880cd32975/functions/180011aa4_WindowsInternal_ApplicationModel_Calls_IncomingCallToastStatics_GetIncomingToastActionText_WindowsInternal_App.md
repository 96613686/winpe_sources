# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::GetIncomingToastActionText(WindowsInternal::ApplicationModel::Calls::IncomingToastAction)

- ea: `0x180011aa4`
- end: `0x180011b99`
- name: `?GetIncomingToastActionText@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@SAPEBGW4IncomingToastAction@234@@Z`
- size: `245`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014510`
- `0x180015944`

## callees

- `0x1800011fc`
- `0x180001dc0`
- `0x180011aa4`
- `0x180011e5c`
- `0x1800165c4`

## pseudocode

```c
const wchar_t *__fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::GetIncomingToastActionText(
        __int64 a1)
{
  __int64 v1; // rdx
  int v3; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+38h] [rbp-40h] BYREF
  int *v5; // [rsp+58h] [rbp-20h]
  __int64 v6; // [rsp+60h] [rbp-18h]

  switch ( (_DWORD)a1 )
  {
    case 0:
      return L"TextReply";
    case 1:
      return L"AnswerWithAudio";
    case 2:
      return L"DropAccept";
    case 3:
      return L"Ignore";
    case 4:
      return L"Answer";
  }
  v1 = (unsigned int)(a1 - 5);
  if ( (_DWORD)a1 == 5 )
    return L"AnswerWithVideo";
  if ( (_DWORD)a1 == 6 )
    return L"SendPhone";
  if ( (unsigned int)dword_180025038 > 4 )
  {
    v3 = a1;
    v5 = &v3;
    v6 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180025038, (unsigned __int8 *)&byte_180020D0B, 0, 0, 3u, &v4);
  }
  Log_AssertionEvent_2(a1, v1, 173);
  MicrosoftTelemetryAssertTriggeredNoArgs();
  return 0;
}

```

## disassembly

```asm
0x180011aa4  mov     r11, rsp
0x180011aa7  sub     rsp, 78h
0x180011aab  mov     rax, cs:__security_cookie
0x180011ab2  xor     rax, rsp
0x180011ab5  mov     [rsp+78h+var_10], rax
0x180011aba  mov     edx, ecx
0x180011abc  test    ecx, ecx
0x180011abe  jz      loc_180011B80
0x180011ac4  sub     edx, 1
0x180011ac7  jz      loc_180011B77
0x180011acd  sub     edx, 1
0x180011ad0  jz      loc_180011B6E
0x180011ad6  sub     edx, 1
0x180011ad9  jz      loc_180011B65
0x180011adf  sub     edx, 1
0x180011ae2  jz      short loc_180011B5C
0x180011ae4  sub     edx, 1
0x180011ae7  jz      short loc_180011B53
0x180011ae9  cmp     edx, 1
0x180011aec  jz      short loc_180011B4A
0x180011aee  mov     eax, cs:dword_180025038
0x180011af4  cmp     eax, 4
0x180011af7  jbe     short loc_180011B36
0x180011af9  lea     rax, [r11-48h]
0x180011afd  mov     [rsp+78h+var_48], ecx
0x180011b01  mov     [r11-20h], rax
0x180011b05  lea     rdx, byte_180020D0B; int
0x180011b0c  lea     rax, [r11-40h]
0x180011b10  mov     qword ptr [r11-18h], 4
0x180011b18  mov     [r11-50h], rax
0x180011b1c  lea     rcx, dword_180025038; int
0x180011b23  xor     r9d, r9d; int
0x180011b26  mov     [rsp+78h+var_58], 3; ULONG
0x180011b2e  xor     r8d, r8d; int
0x180011b31  call    _tlgWriteTransfer_EventWriteTransfer
0x180011b36  mov     r8d, 0ADh
0x180011b3c  call    Log_AssertionEvent_2
0x180011b41  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180011b46  xor     eax, eax
0x180011b48  jmp     short loc_180011B87
0x180011b4a  lea     rax, aSendphone; "SendPhone"
0x180011b51  jmp     short loc_180011B87
0x180011b53  lea     rax, aAnswerwithvide; "AnswerWithVideo"
0x180011b5a  jmp     short loc_180011B87
0x180011b5c  lea     rax, aAnswer; "Answer"
0x180011b63  jmp     short loc_180011B87
0x180011b65  lea     rax, aIgnore; "Ignore"
0x180011b6c  jmp     short loc_180011B87
0x180011b6e  lea     rax, aDropaccept; "DropAccept"
0x180011b75  jmp     short loc_180011B87
0x180011b77  lea     rax, aAnswerwithaudi; "AnswerWithAudio"
0x180011b7e  jmp     short loc_180011B87
0x180011b80  lea     rax, aTextreply; "TextReply"
0x180011b87  mov     rcx, [rsp+78h+var_10]
0x180011b8c  xor     rcx, rsp; StackCookie
0x180011b8f  call    __security_check_cookie
0x180011b94  add     rsp, 78h
0x180011b98  retn
```
