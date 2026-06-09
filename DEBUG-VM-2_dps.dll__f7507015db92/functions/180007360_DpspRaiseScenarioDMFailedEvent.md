# DpspRaiseScenarioDMFailedEvent

- ea: `0x180007360`
- end: `0x1800074fa`
- name: `DpspRaiseScenarioDMFailedEvent`
- size: `410`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180002090`
- `0x180003830`
- `0x1800057b0`
- `0x180012670`

## callees

- `0x180007360`
- `0x180009090`
- `0x180009fb0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800073fb`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800073fb`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800074b2`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800074b2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000742a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800074c1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000742a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800074c1`

## pseudocode

```c
__int64 __fastcall DpspRaiseScenarioDMFailedEvent(__int64 a1, const EVENT_DESCRIPTOR *a2)
{
  __int64 v5; // r8
  __int64 v6; // rax
  GUID ActivityId; // [rsp+30h] [rbp-39h] BYREF
  _BYTE UserData[24]; // [rsp+40h] [rbp-29h] BYREF
  __int128 v9; // [rsp+58h] [rbp-11h]
  __int128 v10; // [rsp+68h] [rbp-1h]
  __int128 v11; // [rsp+78h] [rbp+Fh]
  __int128 v12; // [rsp+88h] [rbp+1Fh]
  __int64 v13; // [rsp+98h] [rbp+2Fh]

  memset(UserData, 0, sizeof(UserData));
  v13 = 0;
  ActivityId = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  if ( a1 )
  {
    if ( EventEnabled(g_hETW, a2) )
    {
      if ( a1 != -24 )
        ActivityId = *(GUID *)(a1 + 24);
      EventActivityIdControl(4u, &ActivityId);
      v5 = *(_QWORD *)(a1 + 808);
      *(_QWORD *)UserData = *(_QWORD *)(a1 + 1216);
      *((_QWORD *)&v9 + 1) = a1 + 56;
      *(_QWORD *)&UserData[8] = 16;
      *(_QWORD *)&UserData[16] = a1 + 24;
      *(_QWORD *)&v9 = 16;
      *(_QWORD *)&v10 = 16;
      v6 = *(_QWORD *)(v5 + 128);
      *(_QWORD *)&v11 = *(unsigned int *)(v5 + 148);
      *((_QWORD *)&v11 + 1) = a1 + 132;
      *((_QWORD *)&v12 + 1) = v5;
      *((_QWORD *)&v10 + 1) = v6;
      *(_QWORD *)&v12 = 4;
      v13 = 16;
      EventWrite(g_hETW, a2, 6u, (PEVENT_DATA_DESCRIPTOR)UserData);
      EventActivityIdControl(2u, &ActivityId);
    }
    return 0;
  }
  else
  {
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsevents.cpp",
      (__int64)L"DpspRaiseScenarioDMFailedEvent",
      476,
      (const wchar_t *)L"Error = %d",
      87);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180007360  mov     [rsp-8+arg_18], rbx
0x180007365  push    rbp
0x180007366  push    r14
0x180007368  push    r15
0x18000736a  lea     rbp, [rsp-47h]
0x18000736f  sub     rsp, 0B0h
0x180007376  mov     rax, cs:__security_cookie
0x18000737d  xor     rax, rsp
0x180007380  mov     [rbp+57h+var_20], rax
0x180007384  xorps   xmm0, xmm0
0x180007387  xor     r15d, r15d
0x18000738a  xor     eax, eax
0x18000738c  mov     qword ptr [rbp+57h+UserData], r15
0x180007390  mov     [rbp+57h+var_28], rax
0x180007394  mov     r14, rdx
0x180007397  mov     rbx, rcx
0x18000739a  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x18000739e  movups  xmmword ptr [rbp+57h+UserData+8], xmm0
0x1800073a2  movups  [rbp+57h+var_68], xmm0
0x1800073a6  movups  [rbp+57h+var_58], xmm0
0x1800073aa  movups  [rbp+57h+var_48], xmm0
0x1800073ae  movups  [rbp+57h+var_38], xmm0
0x1800073b2  test    rcx, rcx
0x1800073b5  jnz     short loc_1800073E9
0x1800073b7  lea     r9, aErrorD; "Error = %d"
0x1800073be  mov     dword ptr [rsp+0C0h+Args], 57h ; 'W'; Args
0x1800073c6  mov     r8d, 1DCh; int
0x1800073cc  lea     rdx, aDpspraisescena; "DpspRaiseScenarioDMFailedEvent"
0x1800073d3  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800073da  call    WdipTraceError
0x1800073df  mov     eax, 80070057h
0x1800073e4  jmp     loc_1800074D9
0x1800073e9  mov     rcx, cs:g_hETW; RegHandle
0x1800073f0  mov     [rsp+0C0h+arg_0], rsi
0x1800073f8  mov     esi, r15d
0x1800073fb  call    cs:__imp_EventEnabled
0x180007401  test    al, al
0x180007403  jz      loc_1800074CF
0x180007409  mov     [rsp+0C0h+arg_10], rdi
0x180007411  lea     rdi, [rbx+18h]
0x180007415  test    rdi, rdi
0x180007418  jz      short loc_180007421
0x18000741a  movups  xmm0, xmmword ptr [rdi]
0x18000741d  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x180007421  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180007425  mov     ecx, 4; ControlCode
0x18000742a  call    cs:__imp_EventActivityIdControl
0x180007430  mov     r8, [rbx+328h]
0x180007437  lea     r9, [rbp+57h+UserData]; UserData
0x18000743b  mov     rax, [rbx+4C0h]
0x180007442  mov     rdx, r14; EventDescriptor
0x180007445  mov     qword ptr [rbp+57h+UserData], rax
0x180007449  lea     rax, [rbx+38h]
0x18000744d  mov     qword ptr [rbp+57h+var_68+8], rax
0x180007451  mov     qword ptr [rbp+57h+UserData+8], 10h
0x180007459  mov     qword ptr [rbp+57h+UserData+10h], rdi
0x18000745d  mov     qword ptr [rbp+57h+var_68], 10h
0x180007465  mov     qword ptr [rbp+57h+var_58], 10h
0x18000746d  mov     ecx, [r8+94h]
0x180007474  mov     rax, [r8+80h]
0x18000747b  mov     dword ptr [rbp+57h+var_48], ecx
0x18000747e  lea     rcx, [rbx+84h]
0x180007485  mov     qword ptr [rbp+57h+var_48+8], rcx
0x180007489  mov     rcx, cs:g_hETW; RegHandle
0x180007490  mov     qword ptr [rbp+57h+var_38+8], r8
0x180007494  mov     r8d, 6; UserDataCount
0x18000749a  mov     qword ptr [rbp+57h+var_58+8], rax
0x18000749e  mov     dword ptr [rbp+57h+var_48+4], r15d
0x1800074a2  mov     qword ptr [rbp+57h+var_38], 4
0x1800074aa  mov     [rbp+57h+var_28], 10h
0x1800074b2  call    cs:__imp_EventWrite
0x1800074b8  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1800074bc  mov     ecx, 2; ControlCode
0x1800074c1  call    cs:__imp_EventActivityIdControl
0x1800074c7  mov     rdi, [rsp+0C0h+arg_10]
0x1800074cf  mov     eax, esi
0x1800074d1  mov     rsi, [rsp+0C0h+arg_0]
0x1800074d9  mov     rcx, [rbp+57h+var_20]
0x1800074dd  xor     rcx, rsp; StackCookie
0x1800074e0  call    __security_check_cookie
0x1800074e5  mov     rbx, [rsp+0C0h+arg_18]
0x1800074ed  add     rsp, 0B0h
0x1800074f4  pop     r15
0x1800074f6  pop     r14
0x1800074f8  pop     rbp
0x1800074f9  retn
```
