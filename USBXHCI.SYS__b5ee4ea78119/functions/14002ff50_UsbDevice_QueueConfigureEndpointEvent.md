# UsbDevice_QueueConfigureEndpointEvent

- ea: `0x14002ff50`
- end: `0x140030329`
- name: `UsbDevice_QueueConfigureEndpointEvent`
- size: `985`
- prototype: ``
- caller_count: `11`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400296ac`
- `0x14002ff50`
- `0x140035c70`
- `0x140037c20`
- `0x14003c038`
- `0x14004dd84`
- `0x14004de60`
- `0x14004df60`
- `0x14004e8e0`
- `0x14004ec28`
- `0x14004f030`

## callees

- `0x1400038c0`
- `0x14001bb78`
- `0x1400252d0`
- `0x14002b2c0`
- `0x14002f98c`
- `0x14002fa04`
- `0x14002ff50`
- `0x140030330`
- `0x140035d48`
- `0x1400384f4`
- `0x14003c038`
- `0x14004e8e0`
- `0x14004e9a0`
- `0x14004ec28`

## string_xrefs

- `0x1400302a3`: `Unexpected ConfigureEndpointState value`

## pseudocode

```c
__int64 __fastcall UsbDevice_QueueConfigureEndpointEvent(__int64 a1, int a2)
{
  int v2; // r8d
  int v3; // ebx
  __int64 v4; // rsi
  unsigned int v6; // ebp
  int v7; // ecx
  int v8; // eax
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  __int64 v14; // rcx
  int v16; // ebx
  int v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // ecx
  int v21; // eax
  bool v22; // cf
  int v23; // eax
  int v24; // ebx
  int v25; // ecx
  int v26; // ebx
  int v27; // ebx
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rdx
  int v31; // ebx
  __int64 v32; // r9
  const char *v33; // rcx
  char v34; // [rsp+30h] [rbp-48h]

  v2 = *(_DWORD *)(a1 + 608);
  v3 = 14;
  v4 = *(_QWORD *)(a1 + 600);
  v6 = 1;
  if ( v2 > 7 )
  {
    if ( v2 == 8 )
    {
      v20 = a2 - 1;
      if ( a2 != 1 )
      {
LABEL_43:
        if ( v20 != 1 )
          goto LABEL_12;
LABEL_44:
        v3 = 12;
        goto LABEL_12;
      }
    }
    else
    {
      if ( v2 != 9 )
      {
        if ( (unsigned int)(v2 - 10) >= 2 )
          goto LABEL_12;
        v20 = a2 - 1;
        if ( a2 == 1 )
          goto LABEL_44;
        goto LABEL_43;
      }
      v7 = a2 - 3;
      if ( a2 != 3 )
      {
LABEL_7:
        if ( v7 == 1 )
          v3 = 11;
        goto LABEL_12;
      }
    }
    v3 = 10;
    goto LABEL_12;
  }
  switch ( v2 )
  {
    case 7:
      if ( a2 == 3 )
      {
        v3 = 8;
      }
      else if ( a2 == 4 )
      {
        v3 = 9;
      }
      goto LABEL_12;
    case 0:
      v8 = 1;
      if ( a2 != 5 )
        v8 = 14;
      v3 = v8;
      goto LABEL_12;
    case 1:
      v20 = a2 - 1;
      if ( a2 == 1 )
      {
        v3 = 2;
        goto LABEL_12;
      }
      goto LABEL_43;
    case 2:
      v7 = a2 - 3;
      if ( a2 == 3 )
      {
        v3 = 3;
        goto LABEL_12;
      }
      goto LABEL_7;
  }
  if ( v2 != 3 )
  {
    switch ( v2 )
    {
      case 4:
        v25 = a2 - 1;
        if ( a2 == 1 )
        {
          v3 = v25 + 5;
          goto LABEL_12;
        }
        break;
      case 5:
        v25 = a2 - 1;
        if ( a2 == 1 )
        {
          v3 = v25 + 6;
          goto LABEL_12;
        }
        break;
      case 6:
        v25 = a2 - 1;
        if ( a2 != 1 )
          break;
LABEL_64:
        v3 = 7;
        goto LABEL_12;
      default:
        goto LABEL_12;
    }
    if ( v25 == 1 )
      v3 = 13;
    goto LABEL_12;
  }
  if ( a2 == 3 )
  {
    v3 = 4;
    goto LABEL_12;
  }
  if ( a2 == 4 )
    goto LABEL_64;
LABEL_12:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v34 = a2;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_ddd(
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
      a2,
      12,
      65,
      (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids,
      v2,
      v34,
      v3);
  }
  *(_DWORD *)(a1 + 608) = v3;
  if ( v3 <= 7 )
  {
    if ( v3 != 7 )
    {
      if ( v3 )
      {
        v16 = v3 - 1;
        if ( !v16 )
        {
          v21 = UsbDevice_ValidateEndpointConfigureRequest(a1, v4);
          if ( v21 < 0 )
          {
            UsbDevice_SetConfigureRequestStatus(a1, (unsigned int)v21);
            v6 = 2;
          }
          v18 = v6;
          goto LABEL_28;
        }
        v17 = v16 - 1;
        if ( !v17 )
        {
          v18 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 8) + 1084LL) != 2) + 3;
LABEL_28:
          v19 = a1;
          return UsbDevice_QueueConfigureEndpointEvent(v19, v18);
        }
        v24 = v17 - 1;
        if ( !v24 )
        {
          v23 = UsbDevice_NumberOfOffloadedEndpointsInDropEndpointsList(v4);
          goto LABEL_48;
        }
        v26 = v24 - 1;
        if ( !v26 )
          return UsbDevice_HandleSendStopEndpointToOffloadedEndpointsState(a1, v4);
        v27 = v26 - 1;
        if ( v27 )
        {
          if ( v27 != 1 )
            goto LABEL_87;
          return UsbDevice_HandleUnassignPinsForOffloadedEndpointsState(a1, v4);
        }
        v28 = UsbDevice_InitializeInputContextForAddDropEndpoints(a1, v4, 1);
        v29 = a1;
        if ( v28 < 0 )
        {
LABEL_80:
          UsbDevice_SetConfigureRequestStatus(v29, (unsigned int)v28);
          v18 = 2;
          return UsbDevice_QueueConfigureEndpointEvent(v19, v18);
        }
        *(_BYTE *)(a1 + 460) = 0;
        v30 = 1;
      }
      else
      {
        v30 = 5;
        v29 = a1;
      }
      return UsbDevice_SendConfigureEndpointCommand(v29, v30);
    }
    v23 = *(_DWORD *)(v4 + 84);
LABEL_48:
    v22 = v23 != 0;
    goto LABEL_46;
  }
  v9 = v3 - 8;
  if ( !v9 )
    return UsbDevice_HandleAssignPinsForEndpointsToOffloadState(a1, v4);
  v10 = v9 - 1;
  if ( !v10 )
  {
    v22 = *(_BYTE *)(a1 + 460) != 0;
LABEL_46:
    v18 = 4 - (unsigned int)v22;
    goto LABEL_28;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v28 = UsbDevice_InitializeInputContextForAddDropEndpoints(a1, v4, 2);
    v29 = a1;
    if ( v28 >= 0 )
    {
      v30 = 2;
      return UsbDevice_SendConfigureEndpointCommand(v29, v30);
    }
    goto LABEL_80;
  }
  v12 = v11 - 1;
  if ( !v12 )
    return UsbDevice_HandleAddAndDropEndpointsState(a1, v4);
  v13 = v12 - 1;
  if ( !v13 )
  {
    v14 = a1;
    return UsbDevice_CompleteConfigureEndpointRequest(v14);
  }
  v31 = v13 - 1;
  if ( v31 )
  {
    if ( v31 == 1 )
    {
      v32 = 4839;
      v33 = "Unhandled event/transition encountered";
LABEL_88:
      Debug_FreAssertMsg(v33, 0, "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\usbdevice.c", v32);
      UsbDevice_SetConfigureRequestStatus(a1, 3221225701LL);
      return UsbDevice_CompleteConfigureEndpointRequest(v14);
    }
LABEL_87:
    v32 = 5223;
    v33 = "Unexpected ConfigureEndpointState value";
    goto LABEL_88;
  }
  UsbDevice_CompleteConfigureEndpointRequest(a1);
  return Controller_ReportFatalError(*(_QWORD *)(a1 + 8), 2, 4119, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x14002ff50  push    rbx
0x14002ff52  push    rbp
0x14002ff53  push    rsi
0x14002ff54  push    rdi
0x14002ff55  push    r14
0x14002ff57  push    r15
0x14002ff59  sub     rsp, 48h
0x14002ff5d  mov     r8d, [rcx+260h]
0x14002ff64  mov     ebx, 0Eh
0x14002ff69  mov     rsi, [rcx+258h]
0x14002ff70  xor     r14d, r14d
0x14002ff73  mov     rdi, rcx
0x14002ff76  lea     ebp, [rbx-0Dh]
0x14002ff79  lea     r10d, [rbx-2]
0x14002ff7d  lea     r15d, [rbx-0Ch]
0x14002ff81  cmp     r8d, 7
0x14002ff85  jg      loc_14003009B
0x14002ff8b  jz      loc_140030187
0x14002ff91  mov     ecx, r8d
0x14002ff94  test    r8d, r8d
0x14002ff97  jz      short loc_14002FFBF
0x14002ff99  sub     ecx, ebp
0x14002ff9b  jz      loc_140030069
0x14002ffa1  sub     ecx, ebp
0x14002ffa3  jnz     loc_14003011C
0x14002ffa9  mov     ecx, edx
0x14002ffab  sub     ecx, 3
0x14002ffae  jz      loc_1400300C2
0x14002ffb4  cmp     ecx, ebp
0x14002ffb6  jnz     short loc_14002FFC9
0x14002ffb8  mov     ebx, 0Bh
0x14002ffbd  jmp     short loc_14002FFC9
0x14002ffbf  cmp     edx, 5
0x14002ffc2  mov     eax, ebp
0x14002ffc4  cmovnz  eax, ebx
0x14002ffc7  mov     ebx, eax
0x14002ffc9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002ffd0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002ffd7  jz      short loc_14002FFEB
0x14002ffd9  mov     rax, cs:WPP_GLOBAL_Control
0x14002ffe0  cmp     [rax+48h], r14w
0x14002ffe5  jnz     loc_1400301C8
0x14002ffeb  mov     [rdi+260h], ebx
0x14002fff1  cmp     ebx, 7
0x14002fff4  jle     short loc_140030025
0x14002fff6  sub     ebx, 8
0x14002fff9  jz      loc_140030319
0x14002ffff  sub     ebx, ebp
0x140030001  jz      loc_1400300F1
0x140030007  sub     ebx, ebp
0x140030009  jz      loc_1400302FB
0x14003000f  sub     ebx, ebp
0x140030011  jz      short loc_140030077
0x140030013  sub     ebx, ebp
0x140030015  jnz     loc_140030286
0x14003001b  mov     rcx, rdi
0x14003001e  call    UsbDevice_CompleteConfigureEndpointRequest
0x140030023  jmp     short loc_14003005B
0x140030025  jz      loc_140030103
0x14003002b  test    ebx, ebx
0x14003002d  jz      loc_14003026F
0x140030033  sub     ebx, ebp
0x140030035  jz      short loc_140030084
0x140030037  sub     ebx, ebp
0x140030039  jnz     loc_14003010A
0x14003003f  mov     rax, [rdi+8]
0x140030043  mov     edx, r14d
0x140030046  cmp     [rax+43Ch], r15d
0x14003004d  setnz   dl
0x140030050  add     edx, 3
0x140030053  mov     rcx, rdi
0x140030056  call    UsbDevice_QueueConfigureEndpointEvent
0x14003005b  add     rsp, 48h
0x14003005f  pop     r15
0x140030061  pop     r14
0x140030063  pop     rdi
0x140030064  pop     rsi
0x140030065  pop     rbp
0x140030066  pop     rbx
0x140030067  retn
0x140030069  mov     ecx, edx
0x14003006b  sub     ecx, ebp
0x14003006d  jnz     short loc_1400300E1
0x14003006f  mov     ebx, r15d
0x140030072  jmp     loc_14002FFC9
0x140030077  mov     rdx, rsi
0x14003007a  mov     rcx, rdi
0x14003007d  call    UsbDevice_HandleAddAndDropEndpointsState
0x140030082  jmp     short loc_14003005B
0x140030084  mov     rdx, rsi
0x140030087  mov     rcx, rdi
0x14003008a  call    UsbDevice_ValidateEndpointConfigureRequest
0x14003008f  test    eax, eax
0x140030091  js      loc_14003025D
0x140030097  mov     edx, ebp
0x140030099  jmp     short loc_140030053
0x14003009b  mov     ecx, r8d
0x14003009e  sub     ecx, 8
0x1400300a1  jz      loc_1400301B9
0x1400300a7  sub     ecx, ebp
0x1400300a9  jz      short loc_1400300CC
0x1400300ab  sub     ecx, ebp
0x1400300ad  jz      loc_1400301AA
0x1400300b3  sub     ecx, ebp
0x1400300b5  jz      loc_1400301AA
0x1400300bb  sub     ecx, ebp
0x1400300bd  jmp     loc_14002FFC9
0x1400300c2  mov     ebx, 3
0x1400300c7  jmp     loc_14002FFC9
0x1400300cc  mov     ecx, edx
0x1400300ce  sub     ecx, 3
0x1400300d1  jnz     loc_14002FFB4
0x1400300d7  mov     ebx, 0Ah
0x1400300dc  jmp     loc_14002FFC9
0x1400300e1  cmp     ecx, ebp
0x1400300e3  jnz     loc_14002FFC9
0x1400300e9  mov     ebx, r10d
0x1400300ec  jmp     loc_14002FFC9
0x1400300f1  mov     al, [rdi+1CCh]
0x1400300f7  neg     al
0x1400300f9  sbb     edx, edx
0x1400300fb  add     edx, 4
0x1400300fe  jmp     loc_140030053
0x140030103  mov     eax, [rsi+54h]
0x140030106  neg     eax
0x140030108  jmp     short loc_1400300F9
0x14003010a  sub     ebx, ebp
0x14003010c  jnz     loc_1400301FE
0x140030112  mov     rcx, rsi
0x140030115  call    UsbDevice_NumberOfOffloadedEndpointsInDropEndpointsList
0x14003011a  jmp     short loc_140030106
0x14003011c  sub     ecx, ebp
0x14003011e  jz      short loc_140030164
0x140030120  sub     ecx, ebp
0x140030122  jz      short loc_140030156
0x140030124  sub     ecx, ebp
0x140030126  jz      short loc_140030148
0x140030128  cmp     ecx, ebp
0x14003012a  jnz     loc_14002FFC9
0x140030130  mov     ecx, edx
0x140030132  sub     ecx, ebp
0x140030134  jz      short loc_140030173
0x140030136  cmp     ecx, ebp
0x140030138  jnz     loc_14002FFC9
0x14003013e  mov     ebx, 0Dh
0x140030143  jmp     loc_14002FFC9
0x140030148  mov     ecx, edx
0x14003014a  sub     ecx, ebp
0x14003014c  jnz     short loc_140030136
0x14003014e  lea     ebx, [rcx+6]
0x140030151  jmp     loc_14002FFC9
0x140030156  mov     ecx, edx
0x140030158  sub     ecx, ebp
0x14003015a  jnz     short loc_140030136
0x14003015c  lea     ebx, [rcx+5]
0x14003015f  jmp     loc_14002FFC9
0x140030164  mov     ecx, edx
0x140030166  sub     ecx, 3
0x140030169  jz      short loc_14003017D
0x14003016b  cmp     ecx, ebp
0x14003016d  jnz     loc_14002FFC9
0x140030173  mov     ebx, 7
0x140030178  jmp     loc_14002FFC9
0x14003017d  mov     ebx, 4
0x140030182  jmp     loc_14002FFC9
0x140030187  mov     ecx, edx
0x140030189  sub     ecx, 3
0x14003018c  jz      short loc_1400301A0
0x14003018e  cmp     ecx, ebp
0x140030190  jnz     loc_14002FFC9
0x140030196  mov     ebx, 9
0x14003019b  jmp     loc_14002FFC9
0x1400301a0  mov     ebx, 8
0x1400301a5  jmp     loc_14002FFC9
0x1400301aa  mov     ecx, edx
0x1400301ac  sub     ecx, ebp
0x1400301ae  jz      loc_1400300E9
0x1400301b4  jmp     loc_1400300E1
0x1400301b9  mov     ecx, edx
0x1400301bb  sub     ecx, ebp
0x1400301bd  jnz     loc_1400300E1
0x1400301c3  jmp     loc_1400300D7
0x1400301c8  mov     rcx, [rdi+8]
0x1400301cc  lea     rax, WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids
0x1400301d3  mov     [rsp+78h+var_40], ebx
0x1400301d7  mov     r9d, 41h ; 'A'
0x1400301dd  mov     dword ptr [rsp+78h+var_48], edx
0x1400301e1  mov     dl, 5
0x1400301e3  mov     dword ptr [rsp+78h+var_50], r8d
0x1400301e8  mov     r8d, r10d
0x1400301eb  mov     rcx, [rcx+48h]
0x1400301ef  mov     [rsp+78h+var_58], rax
0x1400301f4  call    WPP_RECORDER_SF_ddd
0x1400301f9  jmp     loc_14002FFEB
0x1400301fe  sub     ebx, ebp
0x140030200  jz      short loc_14003024D
0x140030202  sub     ebx, ebp
0x140030204  jz      short loc_14003021E
0x140030206  cmp     ebx, ebp
0x140030208  jnz     loc_14003029D
0x14003020e  mov     rdx, rsi
0x140030211  mov     rcx, rdi
0x140030214  call    UsbDevice_HandleUnassignPinsForOffloadedEndpointsState
0x140030219  jmp     loc_14003005B
0x14003021e  mov     r8d, ebp
0x140030221  mov     rdx, rsi
0x140030224  mov     rcx, rdi
0x140030227  call    UsbDevice_InitializeInputContextForAddDropEndpoints
0x14003022c  mov     rcx, rdi
0x14003022f  test    eax, eax
0x140030231  js      short loc_14003023E
0x140030233  mov     [rdi+1CCh], r14b
0x14003023a  mov     edx, ebp
0x14003023c  jmp     short loc_14003027C
0x14003023e  mov     edx, eax
0x140030240  call    UsbDevice_SetConfigureRequestStatus
0x140030245  mov     edx, r15d
0x140030248  jmp     loc_140030056
0x14003024d  mov     rdx, rsi
0x140030250  mov     rcx, rdi
0x140030253  call    UsbDevice_HandleSendStopEndpointToOffloadedEndpointsState
0x140030258  jmp     loc_14003005B
0x14003025d  mov     edx, eax
0x14003025f  mov     rcx, rdi
0x140030262  call    UsbDevice_SetConfigureRequestStatus
0x140030267  mov     ebp, r15d
0x14003026a  jmp     loc_140030097
0x14003026f  mov     edx, 5
0x140030274  mov     rcx, rdi
0x140030277  jmp     short loc_14003027C
0x140030279  mov     edx, r15d
0x14003027c  call    UsbDevice_SendConfigureEndpointCommand
0x140030281  jmp     loc_14003005B
0x140030286  sub     ebx, ebp
0x140030288  jz      short loc_1400302CA
0x14003028a  cmp     ebx, ebp
0x14003028c  jnz     short loc_14003029D
0x14003028e  mov     r9d, 12E7h
0x140030294  lea     rcx, aUnhandledEvent; "Unhandled event/transition encountered"
0x14003029b  jmp     short loc_1400302AA
0x14003029d  mov     r9d, 1467h
0x1400302a3  lea     rcx, aUnexpectedConf; "Unexpected ConfigureEndpointState value"
0x1400302aa  xor     edx, edx
0x1400302ac  lea     r8, aOnecoreDrivers_17; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x1400302b3  call    Debug_FreAssertMsg
0x1400302b8  mov     edx, 0C00000E5h
0x1400302bd  mov     rcx, rdi
0x1400302c0  call    UsbDevice_SetConfigureRequestStatus
0x1400302c5  jmp     loc_14003001E
0x1400302ca  mov     rcx, rdi
0x1400302cd  call    UsbDevice_CompleteConfigureEndpointRequest
0x1400302d2  mov     rcx, [rdi+8]
0x1400302d6  xor     r9d, r9d
0x1400302d9  mov     [rsp+78h+var_48], r14
0x1400302de  mov     r8d, 1017h
0x1400302e4  mov     [rsp+78h+var_50], r14
0x1400302e9  mov     edx, r15d
0x1400302ec  mov     [rsp+78h+var_58], r14
0x1400302f1  call    Controller_ReportFatalError
0x1400302f6  jmp     loc_14003005B
0x1400302fb  mov     r8d, r15d
0x1400302fe  mov     rdx, rsi
0x140030301  mov     rcx, rdi
0x140030304  call    UsbDevice_InitializeInputContextForAddDropEndpoints
0x140030309  mov     rcx, rdi
0x14003030c  test    eax, eax
0x14003030e  js      loc_14003023E
0x140030314  jmp     loc_140030279
0x140030319  mov     rdx, rsi
0x14003031c  mov     rcx, rdi
0x14003031f  call    UsbDevice_HandleAssignPinsForEndpointsToOffloadState
0x140030324  jmp     loc_14003005B
```
