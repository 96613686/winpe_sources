# RetrieveServiceScoStatusRequestForIndication(_SCOCONTEXT *,_BTHHF_SCO_STATUS_INDICATION)

- ea: `0x14000ce50`
- end: `0x14000d086`
- name: `?RetrieveServiceScoStatusRequestForIndication@@YA?AU?$pair@JPEAUWDFREQUEST__@@@utl@@PEAU_SCOCONTEXT@@W4_BTHHF_SCO_STATUS_INDICATION@@@Z`
- size: `566`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1400112c4`
- `0x1400136b0`

## callees

- `0x1400041d0`
- `0x14000ce50`
- `0x140014388`
- `0x140014c60`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall RetrieveServiceScoStatusRequestForIndication(__int64 a1, __int64 a2, int a3)
{
  _QWORD *v3; // r14
  int v4; // ebp
  __int64 v5; // rdi
  char v7; // bl
  __int64 v8; // rdx
  int v9; // edx
  int v10; // r8d
  __int64 v11; // rdx
  int v12; // eax
  int v13; // r8d
  int v14; // edx
  _DWORD *v16; // [rsp+70h] [rbp+8h] BYREF

  v3 = (_QWORD *)(a1 + 8);
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  v4 = a3;
  v5 = a2;
  v7 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_BTHHF_SCO_STATUS_INDICATION(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      a3,
      WPP_GLOBAL_Control->DeviceExtension);
  }
  v8 = *(_QWORD *)(v5 + 384);
  *(_DWORD *)(v5 + 392) = v4;
  if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01015 + 1264))(
         WdfDriverGlobals,
         v8,
         v3) < 0 )
  {
    *(_DWORD *)(v5 + 396) = 1;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      v7 = 0;
    }
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = v7;
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v10,
        WPP_GLOBAL_Control->DeviceExtension,
        3,
        5,
        119,
        (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
    }
    *(_DWORD *)a1 = -1073741808;
  }
  else
  {
    *(_DWORD *)(v5 + 396) = 0;
    v11 = *v3;
    v16 = 0;
    v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _DWORD **))(WdfFunctions_01015 + 2160))(
            WdfDriverGlobals,
            v11,
            4,
            &v16);
    *(_DWORD *)a1 = v12;
    if ( v12 >= 0 )
    {
      *v16 = v4;
      v14 = *(_DWORD *)(v5 + 376);
      if ( (unsigned int)(v14 - 2) <= 1 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v7 = 0;
        }
        if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v14) = v7;
          LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_SCOSTATESCOSTATE(
            WPP_GLOBAL_Control->AttachedDevice,
            v14,
            v13,
            WPP_GLOBAL_Control->DeviceExtension,
            0);
        }
        *(_DWORD *)(v5 + 376) = 5;
      }
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2200))(
        WdfDriverGlobals,
        *v3,
        4);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x14000ce50  mov     [rsp+arg_8], rbx
0x14000ce55  mov     [rsp+arg_10], rbp
0x14000ce5a  push    rsi
0x14000ce5b  push    rdi
0x14000ce5c  push    r14
0x14000ce5e  sub     rsp, 50h
0x14000ce62  lea     r14, [rcx+8]
0x14000ce66  mov     dword ptr [rcx], 0
0x14000ce6c  mov     qword ptr [r14], 0
0x14000ce73  mov     ebp, r8d
0x14000ce76  mov     rdi, rdx
0x14000ce79  mov     rsi, rcx
0x14000ce7c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ce83  lea     rax, WPP_GLOBAL_Control
0x14000ce8a  mov     ebx, 1
0x14000ce8f  cmp     rcx, rax
0x14000ce92  jz      short loc_14000CEA5
0x14000ce94  mov     eax, [rcx+2Ch]
0x14000ce97  test    al, 10h
0x14000ce99  jz      short loc_14000CEA5
0x14000ce9b  cmp     byte ptr [rcx+29h], 4
0x14000ce9f  jb      short loc_14000CEA5
0x14000cea1  mov     dl, bl
0x14000cea3  jmp     short loc_14000CEA7
0x14000cea5  xor     dl, dl
0x14000cea7  lea     rax, WPP_RECORDER_INITIALIZED
0x14000ceae  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ceb5  setnz   r8b
0x14000ceb9  test    dl, dl
0x14000cebb  jnz     short loc_14000CEC2
0x14000cebd  test    r8b, r8b
0x14000cec0  jz      short loc_14000CED3
0x14000cec2  mov     r9, [rcx+40h]
0x14000cec6  mov     rcx, [rcx+18h]
0x14000ceca  mov     [rsp+68h+var_28], ebp
0x14000cece  call    WPP_RECORDER_AND_TRACE_SF_BTHHF_SCO_STATUS_INDICATION
0x14000ced3  mov     rdx, [rdi+180h]
0x14000ceda  mov     r8, r14
0x14000cedd  mov     [rdi+188h], ebp
0x14000cee3  mov     rax, cs:WdfFunctions_01015
0x14000ceea  mov     rcx, cs:WdfDriverGlobals
0x14000cef1  mov     rax, [rax+4F0h]
0x14000cef8  call    _guard_dispatch_icall
0x14000cefd  test    eax, eax
0x14000ceff  js      loc_14000CFF5
0x14000cf05  mov     dword ptr [rdi+18Ch], 0
0x14000cf0f  lea     r9, [rsp+68h+arg_0]
0x14000cf14  mov     rax, cs:WdfFunctions_01015
0x14000cf1b  mov     r8d, 4
0x14000cf21  mov     rdx, [r14]
0x14000cf24  mov     rcx, cs:WdfDriverGlobals
0x14000cf2b  mov     [rsp+68h+arg_0], 0
0x14000cf34  mov     rax, [rax+870h]
0x14000cf3b  mov     [rsp+68h+var_48], 0
0x14000cf44  call    _guard_dispatch_icall
0x14000cf49  mov     [rsi], eax
0x14000cf4b  test    eax, eax
0x14000cf4d  js      loc_14000D06D
0x14000cf53  mov     rax, [rsp+68h+arg_0]
0x14000cf58  mov     [rax], ebp
0x14000cf5a  mov     edx, [rdi+178h]
0x14000cf60  lea     eax, [rdx-2]
0x14000cf63  cmp     eax, ebx
0x14000cf65  ja      short loc_14000CFD0
0x14000cf67  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cf6e  lea     rax, WPP_GLOBAL_Control
0x14000cf75  cmp     rcx, rax
0x14000cf78  jz      short loc_14000CF87
0x14000cf7a  mov     eax, [rcx+2Ch]
0x14000cf7d  test    al, 10h
0x14000cf7f  jz      short loc_14000CF87
0x14000cf81  cmp     byte ptr [rcx+29h], 4
0x14000cf85  jnb     short loc_14000CF89
0x14000cf87  xor     bl, bl
0x14000cf89  lea     rax, WPP_RECORDER_INITIALIZED
0x14000cf90  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000cf97  setnz   r8b
0x14000cf9b  test    bl, bl
0x14000cf9d  jnz     short loc_14000CFA4
0x14000cf9f  test    r8b, r8b
0x14000cfa2  jz      short loc_14000CFC6
0x14000cfa4  mov     r9, [rcx+40h]
0x14000cfa8  mov     rcx, [rcx+18h]
0x14000cfac  mov     [rsp+68h+var_20], 5
0x14000cfb4  mov     [rsp+68h+var_28], edx
0x14000cfb8  mov     dl, bl
0x14000cfba  mov     [rsp+68h+var_38], 76h ; 'v'
0x14000cfc1  call    WPP_RECORDER_AND_TRACE_SF_SCOSTATESCOSTATE
0x14000cfc6  mov     dword ptr [rdi+178h], 5
0x14000cfd0  mov     rax, cs:WdfFunctions_01015
0x14000cfd7  mov     r8d, 4
0x14000cfdd  mov     rdx, [r14]
0x14000cfe0  mov     rcx, cs:WdfDriverGlobals
0x14000cfe7  mov     rax, [rax+898h]
0x14000cfee  call    _guard_dispatch_icall
0x14000cff3  jmp     short loc_14000D06D
0x14000cff5  mov     [rdi+18Ch], ebx
0x14000cffb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d002  lea     rax, WPP_GLOBAL_Control
0x14000d009  cmp     rcx, rax
0x14000d00c  jz      short loc_14000D01B
0x14000d00e  mov     eax, [rcx+2Ch]
0x14000d011  test    al, 10h
0x14000d013  jz      short loc_14000D01B
0x14000d015  cmp     byte ptr [rcx+29h], 3
0x14000d019  jnb     short loc_14000D01D
0x14000d01b  xor     bl, bl
0x14000d01d  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d024  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d02b  setnz   r8b
0x14000d02f  test    bl, bl
0x14000d031  jnz     short loc_14000D038
0x14000d033  test    r8b, r8b
0x14000d036  jz      short loc_14000D067
0x14000d038  mov     r9, [rcx+40h]
0x14000d03c  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000d043  mov     rcx, [rcx+18h]
0x14000d047  mov     dl, bl
0x14000d049  mov     [rsp+68h+var_30], rax
0x14000d04e  mov     [rsp+68h+var_38], 77h ; 'w'
0x14000d055  mov     [rsp+68h+var_40], 5
0x14000d05d  mov     byte ptr [rsp+68h+var_48], 3
0x14000d062  call    WPP_RECORDER_AND_TRACE_SF_
0x14000d067  mov     dword ptr [rsi], 0C0000010h
0x14000d06d  lea     r11, [rsp+68h+var_18]
0x14000d072  mov     rax, rsi
0x14000d075  mov     rbx, [r11+28h]
0x14000d079  mov     rbp, [r11+30h]
0x14000d07d  mov     rsp, r11
0x14000d080  pop     r14
0x14000d082  pop     rdi
0x14000d083  pop     rsi
0x14000d084  retn
```
