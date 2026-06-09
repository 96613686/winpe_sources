# OpenTapiLine(_LINE_INFO *)

- ea: `0x14004ba44`
- end: `0x14004bc3a`
- name: `?OpenTapiLine@@YAHPEAU_LINE_INFO@@@Z`
- size: `502`
- prototype: `__int64 __fastcall(DWORD_PTR dwCallbackInstance)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x14001f9b0`
- `0x14001ffb0`
- `0x14002e51c`
- `0x14004a8e0`
- `0x14004caf0`

## callees

- `0x140004b30`
- `0x140004df0`
- `0x14004ba44`
- `0x14004e5c4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14004bc0f`
- `KERNEL32!SetLastError` at `0x14004bc0f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14004bc04`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14004bc04`
- `KERNEL32!EnterCriticalSection` at `0x14004ba9c`
- `KERNEL32!EnterCriticalSection` at `0x14004ba9c`
- `KERNEL32!LeaveCriticalSection` at `0x14004bbe3`
- `KERNEL32!LeaveCriticalSection` at `0x14004bbe3`
- `TAPI32!lineOpenW` at `0x14004bae2`
- `TAPI32!lineOpenW` at `0x14004bb34`
- `TAPI32!lineOpenW` at `0x14004bae2`
- `TAPI32!lineOpenW` at `0x14004bb34`
- `TAPI32!lineSetStatusMessages` at `0x14004bb99`
- `TAPI32!lineSetStatusMessages` at `0x14004bb99`

## pseudocode

```c
__int64 __fastcall OpenTapiLine(DWORD_PTR dwCallbackInstance)
{
  DWORD v2; // edx
  LONG v3; // eax
  LONG v4; // edi
  _DWORD *v5; // rsi
  HLINE v6; // ecx
  DWORD v7; // ebp
  LONG v8; // eax
  __int64 v9; // r8
  int v10; // eax
  HLINE hLine; // [rsp+70h] [rbp+8h] BYREF

  hLine = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
  }
  EnterCriticalSection(&g_CsLine);
  v2 = *(_DWORD *)(dwCallbackInstance + 20);
  if ( *(_DWORD *)(dwCallbackInstance + 104) )
  {
    if ( !lineOpenW(g_hLineApp, v2, &hLine, 0x20000u, 0, dwCallbackInstance, 6u, 0x12u, 0) )
      goto LABEL_15;
    v3 = lineOpenW(
           g_hLineApp,
           *(_DWORD *)(dwCallbackInstance + 20),
           &hLine,
           0x20000u,
           0,
           dwCallbackInstance,
           6u,
           0x10u,
           0);
  }
  else
  {
    v3 = lineOpenW(g_hLineApp, v2, &hLine, 0x20000u, 0, dwCallbackInstance, 6u, 0x20u, 0);
  }
  v4 = v3;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        77,
        (unsigned int)&WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
        *(_QWORD *)(dwCallbackInstance + 56),
        v3);
    }
    v5 = (_DWORD *)(dwCallbackInstance + 32);
    goto LABEL_21;
  }
LABEL_15:
  v5 = (_DWORD *)(dwCallbackInstance + 32);
  v6 = hLine;
  v7 = *(_DWORD *)(dwCallbackInstance + 164) & 0x1000E02;
  *(_DWORD *)(dwCallbackInstance + 32) = hLine;
  v8 = lineSetStatusMessages(v6, v7, 0x3Cu);
  v4 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, v9, v7, 60, v8);
    }
    v4 = 0;
  }
LABEL_21:
  LeaveCriticalSection(&g_CsLine);
  v10 = *(_DWORD *)(dwCallbackInstance + 76);
  if ( v4 )
  {
    *v5 = 0;
    *(_DWORD *)(dwCallbackInstance + 76) = v10 | 0x20000000;
    GetSystemTimeAsFileTime((LPFILETIME)(dwCallbackInstance + 176));
    SetLastError(0x1Fu);
    return 0;
  }
  else
  {
    *(_DWORD *)(dwCallbackInstance + 76) = v10 & 0xDFFFFFFF;
    return 1;
  }
}

```

## disassembly

```asm
0x14004ba44  mov     [rsp+arg_8], rbx
0x14004ba49  mov     [rsp+arg_10], rbp
0x14004ba4e  push    rsi
0x14004ba4f  push    rdi
0x14004ba50  push    r12
0x14004ba52  sub     rsp, 50h
0x14004ba56  mov     rbx, rcx
0x14004ba59  mov     [rsp+68h+hLine], 0
0x14004ba61  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ba68  lea     r12, WPP_GLOBAL_Control
0x14004ba6f  cmp     rcx, r12
0x14004ba72  jz      short loc_14004BA95
0x14004ba74  test    byte ptr [rcx+1Ch], 4
0x14004ba78  jz      short loc_14004BA95
0x14004ba7a  cmp     byte ptr [rcx+19h], 5
0x14004ba7e  jb      short loc_14004BA95
0x14004ba80  mov     rcx, [rcx+10h]
0x14004ba84  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004ba8b  mov     edx, 4Ch ; 'L'
0x14004ba90  call    WPP_SF_
0x14004ba95  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004ba9c  call    cs:__imp_EnterCriticalSection
0x14004baa2  cmp     dword ptr [rbx+68h], 0
0x14004baa6  lea     r8, [rsp+68h+hLine]; lphLine
0x14004baab  mov     edx, [rbx+14h]; dwDeviceID
0x14004baae  mov     r9d, 20000h; dwAPIVersion
0x14004bab4  mov     ecx, cs:?g_hLineApp@@3KA; hLineApp
0x14004baba  mov     [rsp+68h+lpCallParams], 0; lpCallParams
0x14004bac3  jz      short loc_14004BB17
0x14004bac5  mov     [rsp+68h+dwMediaModes], 12h; dwMediaModes
0x14004bacd  mov     [rsp+68h+dwPrivileges], 6; dwPrivileges
0x14004bad5  mov     [rsp+68h+dwCallbackInstance], rbx; dwCallbackInstance
0x14004bada  mov     [rsp+68h+dwExtVersion], 0; dwExtVersion
0x14004bae2  call    cs:__imp_lineOpenW
0x14004bae8  test    eax, eax
0x14004baea  jz      loc_14004BB7B
0x14004baf0  mov     edx, [rbx+14h]
0x14004baf3  lea     r8, [rsp+68h+hLine]
0x14004baf8  mov     ecx, cs:?g_hLineApp@@3KA; ulong g_hLineApp
0x14004bafe  mov     r9d, 20000h
0x14004bb04  mov     [rsp+68h+lpCallParams], 0
0x14004bb0d  mov     [rsp+68h+dwMediaModes], 10h
0x14004bb15  jmp     short loc_14004BB1F
0x14004bb17  mov     [rsp+68h+dwMediaModes], 20h ; ' '; dwMediaModes
0x14004bb1f  mov     [rsp+68h+dwPrivileges], 6; dwPrivileges
0x14004bb27  mov     [rsp+68h+dwCallbackInstance], rbx; dwCallbackInstance
0x14004bb2c  mov     [rsp+68h+dwExtVersion], 0; dwExtVersion
0x14004bb34  call    cs:__imp_lineOpenW
0x14004bb3a  mov     edi, eax
0x14004bb3c  test    eax, eax
0x14004bb3e  jz      short loc_14004BB7B
0x14004bb40  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bb47  cmp     rcx, r12
0x14004bb4a  jz      short loc_14004BB75
0x14004bb4c  test    byte ptr [rcx+1Ch], 4
0x14004bb50  jz      short loc_14004BB75
0x14004bb52  cmp     byte ptr [rcx+19h], 2
0x14004bb56  jb      short loc_14004BB75
0x14004bb58  mov     r9, [rbx+38h]
0x14004bb5c  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004bb63  mov     rcx, [rcx+10h]
0x14004bb67  mov     edx, 4Dh ; 'M'
0x14004bb6c  mov     [rsp+68h+dwExtVersion], eax
0x14004bb70  call    WPP_SF_Sd
0x14004bb75  lea     rsi, [rbx+20h]
0x14004bb79  jmp     short loc_14004BBDC
0x14004bb7b  mov     ebp, [rbx+0A4h]
0x14004bb81  lea     rsi, [rbx+20h]
0x14004bb85  mov     ecx, [rsp+68h+hLine]; hLine
0x14004bb89  and     ebp, 1000E02h
0x14004bb8f  mov     edx, ebp; dwLineStates
0x14004bb91  mov     [rsi], ecx
0x14004bb93  mov     r8d, 3Ch ; '<'; dwAddressStates
0x14004bb99  call    cs:__imp_lineSetStatusMessages
0x14004bb9f  mov     edi, eax
0x14004bba1  test    eax, eax
0x14004bba3  jz      short loc_14004BBDC
0x14004bba5  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bbac  cmp     rcx, r12
0x14004bbaf  jz      short loc_14004BBDA
0x14004bbb1  test    byte ptr [rcx+1Ch], 4
0x14004bbb5  jz      short loc_14004BBDA
0x14004bbb7  cmp     byte ptr [rcx+19h], 2
0x14004bbbb  jb      short loc_14004BBDA
0x14004bbbd  mov     rcx, [rcx+10h]
0x14004bbc1  mov     edx, 4Eh ; 'N'
0x14004bbc6  mov     dword ptr [rsp+68h+dwCallbackInstance], eax
0x14004bbca  mov     r9d, ebp
0x14004bbcd  mov     [rsp+68h+dwExtVersion], 3Ch ; '<'
0x14004bbd5  call    WPP_SF_DDD
0x14004bbda  xor     edi, edi
0x14004bbdc  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004bbe3  call    cs:__imp_LeaveCriticalSection
0x14004bbe9  mov     eax, [rbx+4Ch]
0x14004bbec  test    edi, edi
0x14004bbee  jz      short loc_14004BC19
0x14004bbf0  bts     eax, 1Dh
0x14004bbf4  mov     dword ptr [rsi], 0
0x14004bbfa  lea     rcx, [rbx+0B0h]; lpSystemTimeAsFileTime
0x14004bc01  mov     [rbx+4Ch], eax
0x14004bc04  call    cs:__imp_GetSystemTimeAsFileTime
0x14004bc0a  mov     ecx, 1Fh; dwErrCode
0x14004bc0f  call    cs:__imp_SetLastError
0x14004bc15  xor     eax, eax
0x14004bc17  jmp     short loc_14004BC25
0x14004bc19  btr     eax, 1Dh
0x14004bc1d  mov     [rbx+4Ch], eax
0x14004bc20  mov     eax, 1
0x14004bc25  lea     r11, [rsp+68h+var_18]
0x14004bc2a  mov     rbx, [r11+28h]
0x14004bc2e  mov     rbp, [r11+30h]
0x14004bc32  mov     rsp, r11
0x14004bc35  pop     r12
0x14004bc37  pop     rdi
0x14004bc38  pop     rsi
0x14004bc39  retn
```
