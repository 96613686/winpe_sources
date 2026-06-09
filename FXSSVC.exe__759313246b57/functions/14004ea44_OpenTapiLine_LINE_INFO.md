# OpenTapiLine(_LINE_INFO *)

- ea: `0x14004ea44`
- end: `0x14004ec65`
- name: `?OpenTapiLine@@YAHPEAU_LINE_INFO@@@Z`
- size: `545`
- prototype: `__int64 __fastcall(DWORD_PTR dwCallbackInstance)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1400207a0`
- `0x140020e00`
- `0x14002fbb0`
- `0x14004d830`
- `0x14004fbd0`

## callees

- `0x140004c78`
- `0x140004f64`
- `0x14004ea44`
- `0x140051804`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14004ec33`
- `KERNEL32!SetLastError` at `0x14004ec33`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14004ec22`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14004ec22`
- `KERNEL32!EnterCriticalSection` at `0x14004ea9c`
- `KERNEL32!EnterCriticalSection` at `0x14004ea9c`
- `KERNEL32!LeaveCriticalSection` at `0x14004ebfb`
- `KERNEL32!LeaveCriticalSection` at `0x14004ebfb`
- `TAPI32!lineOpenW` at `0x14004eae8`
- `TAPI32!lineOpenW` at `0x14004eb40`
- `TAPI32!lineOpenW` at `0x14004eae8`
- `TAPI32!lineOpenW` at `0x14004eb40`
- `TAPI32!lineSetStatusMessages` at `0x14004ebab`
- `TAPI32!lineSetStatusMessages` at `0x14004ebab`

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
0x14004ea44  mov     [rsp+arg_8], rbx
0x14004ea49  mov     [rsp+arg_10], rbp
0x14004ea4e  push    rsi
0x14004ea4f  push    rdi
0x14004ea50  push    r12
0x14004ea52  sub     rsp, 50h
0x14004ea56  mov     rbx, rcx
0x14004ea59  mov     [rsp+68h+hLine], 0
0x14004ea61  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ea68  lea     r12, WPP_GLOBAL_Control
0x14004ea6f  cmp     rcx, r12
0x14004ea72  jz      short loc_14004EA95
0x14004ea74  test    byte ptr [rcx+1Ch], 4
0x14004ea78  jz      short loc_14004EA95
0x14004ea7a  cmp     byte ptr [rcx+19h], 5
0x14004ea7e  jb      short loc_14004EA95
0x14004ea80  mov     rcx, [rcx+10h]
0x14004ea84  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004ea8b  mov     edx, 4Ch ; 'L'
0x14004ea90  call    WPP_SF_
0x14004ea95  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004ea9c  call    cs:__imp_EnterCriticalSection
0x14004eaa3  nop     dword ptr [rax+rax+00h]
0x14004eaa8  cmp     dword ptr [rbx+68h], 0
0x14004eaac  lea     r8, [rsp+68h+hLine]; lphLine
0x14004eab1  mov     edx, [rbx+14h]; dwDeviceID
0x14004eab4  mov     r9d, 20000h; dwAPIVersion
0x14004eaba  mov     ecx, cs:?g_hLineApp@@3KA; hLineApp
0x14004eac0  mov     [rsp+68h+lpCallParams], 0; lpCallParams
0x14004eac9  jz      short loc_14004EB23
0x14004eacb  mov     [rsp+68h+dwMediaModes], 12h; dwMediaModes
0x14004ead3  mov     [rsp+68h+dwPrivileges], 6; dwPrivileges
0x14004eadb  mov     [rsp+68h+dwCallbackInstance], rbx; dwCallbackInstance
0x14004eae0  mov     [rsp+68h+dwExtVersion], 0; dwExtVersion
0x14004eae8  call    cs:__imp_lineOpenW
0x14004eaef  nop     dword ptr [rax+rax+00h]
0x14004eaf4  test    eax, eax
0x14004eaf6  jz      loc_14004EB8D
0x14004eafc  mov     edx, [rbx+14h]
0x14004eaff  lea     r8, [rsp+68h+hLine]
0x14004eb04  mov     ecx, cs:?g_hLineApp@@3KA; ulong g_hLineApp
0x14004eb0a  mov     r9d, 20000h
0x14004eb10  mov     [rsp+68h+lpCallParams], 0
0x14004eb19  mov     [rsp+68h+dwMediaModes], 10h
0x14004eb21  jmp     short loc_14004EB2B
0x14004eb23  mov     [rsp+68h+dwMediaModes], 20h ; ' '; dwMediaModes
0x14004eb2b  mov     [rsp+68h+dwPrivileges], 6; dwPrivileges
0x14004eb33  mov     [rsp+68h+dwCallbackInstance], rbx; dwCallbackInstance
0x14004eb38  mov     [rsp+68h+dwExtVersion], 0; dwExtVersion
0x14004eb40  call    cs:__imp_lineOpenW
0x14004eb47  nop     dword ptr [rax+rax+00h]
0x14004eb4c  mov     edi, eax
0x14004eb4e  test    eax, eax
0x14004eb50  jz      short loc_14004EB8D
0x14004eb52  mov     rcx, cs:WPP_GLOBAL_Control
0x14004eb59  cmp     rcx, r12
0x14004eb5c  jz      short loc_14004EB87
0x14004eb5e  test    byte ptr [rcx+1Ch], 4
0x14004eb62  jz      short loc_14004EB87
0x14004eb64  cmp     byte ptr [rcx+19h], 2
0x14004eb68  jb      short loc_14004EB87
0x14004eb6a  mov     r9, [rbx+38h]
0x14004eb6e  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004eb75  mov     rcx, [rcx+10h]
0x14004eb79  mov     edx, 4Dh ; 'M'
0x14004eb7e  mov     [rsp+68h+dwExtVersion], eax
0x14004eb82  call    WPP_SF_Sd
0x14004eb87  lea     rsi, [rbx+20h]
0x14004eb8b  jmp     short loc_14004EBF4
0x14004eb8d  mov     ebp, [rbx+0A4h]
0x14004eb93  lea     rsi, [rbx+20h]
0x14004eb97  mov     ecx, [rsp+68h+hLine]; hLine
0x14004eb9b  and     ebp, 1000E02h
0x14004eba1  mov     edx, ebp; dwLineStates
0x14004eba3  mov     [rsi], ecx
0x14004eba5  mov     r8d, 3Ch ; '<'; dwAddressStates
0x14004ebab  call    cs:__imp_lineSetStatusMessages
0x14004ebb2  nop     dword ptr [rax+rax+00h]
0x14004ebb7  mov     edi, eax
0x14004ebb9  test    eax, eax
0x14004ebbb  jz      short loc_14004EBF4
0x14004ebbd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ebc4  cmp     rcx, r12
0x14004ebc7  jz      short loc_14004EBF2
0x14004ebc9  test    byte ptr [rcx+1Ch], 4
0x14004ebcd  jz      short loc_14004EBF2
0x14004ebcf  cmp     byte ptr [rcx+19h], 2
0x14004ebd3  jb      short loc_14004EBF2
0x14004ebd5  mov     rcx, [rcx+10h]
0x14004ebd9  mov     edx, 4Eh ; 'N'
0x14004ebde  mov     dword ptr [rsp+68h+dwCallbackInstance], eax
0x14004ebe2  mov     r9d, ebp
0x14004ebe5  mov     [rsp+68h+dwExtVersion], 3Ch ; '<'
0x14004ebed  call    WPP_SF_DDD
0x14004ebf2  xor     edi, edi
0x14004ebf4  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004ebfb  call    cs:__imp_LeaveCriticalSection
0x14004ec02  nop     dword ptr [rax+rax+00h]
0x14004ec07  mov     eax, [rbx+4Ch]
0x14004ec0a  test    edi, edi
0x14004ec0c  jz      short loc_14004EC43
0x14004ec0e  bts     eax, 1Dh
0x14004ec12  mov     dword ptr [rsi], 0
0x14004ec18  lea     rcx, [rbx+0B0h]; lpSystemTimeAsFileTime
0x14004ec1f  mov     [rbx+4Ch], eax
0x14004ec22  call    cs:__imp_GetSystemTimeAsFileTime
0x14004ec29  nop     dword ptr [rax+rax+00h]
0x14004ec2e  mov     ecx, 1Fh; dwErrCode
0x14004ec33  call    cs:__imp_SetLastError
0x14004ec3a  nop     dword ptr [rax+rax+00h]
0x14004ec3f  xor     eax, eax
0x14004ec41  jmp     short loc_14004EC4F
0x14004ec43  btr     eax, 1Dh
0x14004ec47  mov     [rbx+4Ch], eax
0x14004ec4a  mov     eax, 1
0x14004ec4f  lea     r11, [rsp+68h+var_18]
0x14004ec54  mov     rbx, [r11+28h]
0x14004ec58  mov     rbp, [r11+30h]
0x14004ec5c  mov     rsp, r11
0x14004ec5f  pop     r12
0x14004ec61  pop     rdi
0x14004ec62  pop     rsi
0x14004ec63  retn
```
