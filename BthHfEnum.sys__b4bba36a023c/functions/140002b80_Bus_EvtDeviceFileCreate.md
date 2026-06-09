# Bus_EvtDeviceFileCreate

- ea: `0x140002b80`
- end: `0x140002eda`
- name: `Bus_EvtDeviceFileCreate`
- size: `858`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140002b80`
- `0x140004318`
- `0x140004810`
- `0x14000bd78`
- `0x140011c2c`
- `0x140011ea8`
- `0x14001ae00`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140002c14`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002c2b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002c14`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002c2b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140002c9e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140002e3b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140002c9e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140002e3b`

## string_xrefs

- `0x140002c06`: `\service`

## pseudocode

```c
__int64 __fastcall Bus_EvtDeviceFileCreate(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rsi
  const UNICODE_STRING *v7; // rbx
  int v8; // edx
  int v9; // r8d
  char v10; // di
  __int64 v11; // rdx
  int v12; // r8d
  int v13; // ebx
  __int64 v14; // rdx
  int Queue; // eax
  __int64 v16; // r13
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-49h] BYREF
  UNICODE_STRING String2; // [rsp+60h] [rbp-39h] BYREF
  __int128 v20; // [rsp+70h] [rbp-29h] BYREF
  __int128 v21; // [rsp+80h] [rbp-19h]
  __int128 v22; // [rsp+90h] [rbp-9h]
  __int64 *v23; // [rsp+A0h] [rbp+7h]
  __int64 v24; // [rsp+100h] [rbp+67h] BYREF

  v23 = 0;
  DestinationString = 0;
  String2 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400220B0);
  v7 = (const UNICODE_STRING *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1096))(
                                 WdfDriverGlobals,
                                 a3);
  RtlInitUnicodeString(&DestinationString, L"\\service");
  RtlInitUnicodeString(&String2, *(PCWSTR *)(v6 + 304));
  v10 = 1;
  LOBYTE(v8) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_S(WPP_GLOBAL_Control->AttachedDevice, v8, v9, WPP_GLOBAL_Control->DeviceExtension);
  }
  if ( !RtlCompareUnicodeString(v7, &DestinationString, 1u) )
  {
    if ( !*(_QWORD *)(v6 + 312) )
    {
      v23 = off_140022128;
      *(_QWORD *)&v21 = 0;
      v24 = 0;
      v20 = 0;
      LODWORD(v20) = 56;
      v22 = 0;
      *((_QWORD *)&v21 + 1) = 0x100000001LL;
      v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *, __int64 *))(WdfFunctions_01015 + 1624))(
              WdfDriverGlobals,
              a3,
              &v20,
              &v24);
      if ( v13 >= 0 )
      {
        v14 = v24 + 16;
        *(_DWORD *)(v6 + 344) = 1;
        Queue = BthRfcommCreateQueue(a1, v14);
        v16 = v24;
        v13 = Queue;
        if ( Queue >= 0 )
          v13 = BthScoRegisterServer(a1);
        if ( v13 < 0 )
        {
          BthScoUnRegisterServer(a1);
          v11 = *(_QWORD *)(v16 + 16);
          if ( v11 )
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
        }
        else
        {
          *(_QWORD *)(v6 + 312) = a3;
          v13 = 0;
        }
      }
      goto LABEL_16;
    }
LABEL_31:
    v13 = -1073741790;
    goto LABEL_16;
  }
  if ( RtlCompareUnicodeString(v7, &String2, 1u) )
  {
    v13 = -1073741809;
    goto LABEL_16;
  }
  if ( *(_QWORD *)(v6 + 320) )
    goto LABEL_31;
  v23 = off_140022100;
  *(_QWORD *)&v21 = 0;
  v24 = 0;
  v20 = 0;
  LODWORD(v20) = 56;
  v22 = 0;
  *((_QWORD *)&v21 + 1) = 0x100000001LL;
  v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *, __int64 *))(WdfFunctions_01015 + 1624))(
          WdfDriverGlobals,
          a3,
          &v20,
          &v24);
  if ( v13 >= 0 )
    *(_QWORD *)(v6 + 320) = a3;
  *(_DWORD *)(v24 + 20) = 1;
LABEL_16:
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v10 = 0;
  }
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = v10;
    LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
      WPP_GLOBAL_Control->AttachedDevice,
      v11,
      v12,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      21,
      (__int64)WPP_9739fd3d85a33a980818697074cd9c28_Traceguids,
      v13);
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
           WdfDriverGlobals,
           a2,
           (unsigned int)v13);
}

```

## disassembly

```asm
0x140002b80  push    rbp
0x140002b82  push    rbx
0x140002b83  push    rsi
0x140002b84  push    rdi
0x140002b85  push    r12
0x140002b87  push    r13
0x140002b89  push    r14
0x140002b8b  push    r15
0x140002b8d  lea     rbp, [rsp-1Fh]
0x140002b92  sub     rsp, 0B8h
0x140002b99  xorps   xmm0, xmm0
0x140002b9c  xor     eax, eax
0x140002b9e  mov     [rbp+57h+var_50], rax
0x140002ba2  xorps   xmm1, xmm1
0x140002ba5  mov     rax, cs:WdfFunctions_01015
0x140002bac  mov     r12, rdx
0x140002baf  mov     r14, r8
0x140002bb2  mov     r15, rcx
0x140002bb5  mov     r8, cs:off_1400220B0
0x140002bbc  mov     rdx, rcx
0x140002bbf  mov     rcx, cs:WdfDriverGlobals
0x140002bc6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140002bca  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x140002bce  movups  [rbp+57h+var_80], xmm0
0x140002bd2  movups  [rbp+57h+var_70], xmm0
0x140002bd6  movups  [rbp+57h+var_60], xmm0
0x140002bda  mov     rax, [rax+650h]
0x140002be1  call    _guard_dispatch_icall
0x140002be6  mov     rcx, cs:WdfFunctions_01015
0x140002bed  mov     rsi, rax
0x140002bf0  mov     rdx, r14
0x140002bf3  mov     rax, [rcx+448h]
0x140002bfa  mov     rcx, cs:WdfDriverGlobals
0x140002c01  call    _guard_dispatch_icall
0x140002c06  lea     rdx, SourceString; "\\service"
0x140002c0d  mov     rbx, rax
0x140002c10  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140002c14  call    cs:__imp_RtlInitUnicodeString
0x140002c1b  nop     dword ptr [rax+rax+00h]
0x140002c20  mov     rdx, [rsi+130h]; SourceString
0x140002c27  lea     rcx, [rbp+57h+String2]; DestinationString
0x140002c2b  call    cs:__imp_RtlInitUnicodeString
0x140002c32  nop     dword ptr [rax+rax+00h]
0x140002c37  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c3e  lea     rax, WPP_GLOBAL_Control
0x140002c45  mov     edi, 1
0x140002c4a  cmp     rcx, rax
0x140002c4d  jz      short loc_140002C61
0x140002c4f  mov     eax, [rcx+2Ch]
0x140002c52  test    al, 8
0x140002c54  jz      short loc_140002C61
0x140002c56  cmp     byte ptr [rcx+29h], 4
0x140002c5a  jb      short loc_140002C61
0x140002c5c  mov     dl, dil
0x140002c5f  jmp     short loc_140002C63
0x140002c61  xor     dl, dl
0x140002c63  lea     r13, WPP_RECORDER_INITIALIZED
0x140002c6a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140002c71  setnz   r8b
0x140002c75  test    dl, dl
0x140002c77  jnz     short loc_140002C7E
0x140002c79  test    r8b, r8b
0x140002c7c  jz      short loc_140002C94
0x140002c7e  mov     rax, [rbx+8]
0x140002c82  mov     r9, [rcx+40h]
0x140002c86  mov     rcx, [rcx+18h]
0x140002c8a  mov     [rsp+0F0h+var_B0], rax
0x140002c8f  call    WPP_RECORDER_AND_TRACE_SF_S
0x140002c94  mov     r8b, dil; CaseInSensitive
0x140002c97  lea     rdx, [rbp+57h+DestinationString]; String2
0x140002c9b  mov     rcx, rbx; String1
0x140002c9e  call    cs:__imp_RtlCompareUnicodeString
0x140002ca5  nop     dword ptr [rax+rax+00h]
0x140002caa  test    eax, eax
0x140002cac  jnz     loc_140002E31
0x140002cb2  cmp     qword ptr [rsi+138h], 0
0x140002cba  jnz     loc_140002EC6
0x140002cc0  mov     rax, cs:off_140022128
0x140002cc7  lea     r9, [rbp+57h+arg_0]
0x140002ccb  mov     rcx, cs:WdfDriverGlobals
0x140002cd2  lea     r8, [rbp+57h+var_80]
0x140002cd6  xorps   xmm0, xmm0
0x140002cd9  mov     [rbp+57h+var_50], rax
0x140002cdd  mov     rax, cs:WdfFunctions_01015
0x140002ce4  mov     rdx, r14
0x140002ce7  movups  [rbp+57h+var_70], xmm0
0x140002ceb  mov     [rbp+57h+arg_0], 0
0x140002cf3  movups  [rbp+57h+var_80], xmm0
0x140002cf7  mov     dword ptr [rbp+57h+var_80], 38h ; '8'
0x140002cfe  movups  [rbp+57h+var_60], xmm0
0x140002d02  mov     dword ptr [rbp+57h+var_70+8], edi
0x140002d05  mov     dword ptr [rbp+57h+var_70+0Ch], edi
0x140002d08  mov     rax, [rax+658h]
0x140002d0f  call    _guard_dispatch_icall
0x140002d14  mov     ebx, eax
0x140002d16  test    eax, eax
0x140002d18  js      short loc_140002D5C
0x140002d1a  mov     rdx, [rbp+57h+arg_0]
0x140002d1e  mov     rcx, r15
0x140002d21  add     rdx, 10h
0x140002d25  mov     [rsi+158h], edi
0x140002d2b  call    BthRfcommCreateQueue
0x140002d30  mov     r13, [rbp+57h+arg_0]
0x140002d34  mov     ebx, eax
0x140002d36  test    eax, eax
0x140002d38  js      short loc_140002D44
0x140002d3a  mov     rcx, r15
0x140002d3d  call    BthScoRegisterServer
0x140002d42  mov     ebx, eax
0x140002d44  test    ebx, ebx
0x140002d46  js      loc_140002DFD
0x140002d4c  mov     [rsi+138h], r14
0x140002d53  xor     ebx, ebx
0x140002d55  lea     r13, WPP_RECORDER_INITIALIZED
0x140002d5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d63  lea     rax, WPP_GLOBAL_Control
0x140002d6a  cmp     rcx, rax
0x140002d6d  jz      short loc_140002D7C
0x140002d6f  mov     eax, [rcx+2Ch]
0x140002d72  test    al, 8
0x140002d74  jz      short loc_140002D7C
0x140002d76  cmp     byte ptr [rcx+29h], 4
0x140002d7a  jnb     short loc_140002D7F
0x140002d7c  xor     dil, dil
0x140002d7f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140002d86  setnz   r8b
0x140002d8a  test    dil, dil
0x140002d8d  jnz     short loc_140002D94
0x140002d8f  test    r8b, r8b
0x140002d92  jz      short loc_140002DC8
0x140002d94  mov     r9, [rcx+40h]
0x140002d98  lea     rax, WPP_9739fd3d85a33a980818697074cd9c28_Traceguids
0x140002d9f  mov     rcx, [rcx+18h]
0x140002da3  mov     dl, dil
0x140002da6  mov     dword ptr [rsp+0F0h+var_B0], ebx
0x140002daa  mov     [rsp+0F0h+var_B8], rax
0x140002daf  mov     [rsp+0F0h+var_C0], 15h
0x140002db6  mov     [rsp+0F0h+var_C8], 4
0x140002dbe  mov     [rsp+0F0h+var_D0], 4
0x140002dc3  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x140002dc8  mov     rax, cs:WdfFunctions_01015
0x140002dcf  mov     r8d, ebx
0x140002dd2  mov     rcx, cs:WdfDriverGlobals
0x140002dd9  mov     rdx, r12
0x140002ddc  mov     rax, [rax+838h]
0x140002de3  call    _guard_dispatch_icall
0x140002de8  add     rsp, 0B8h
0x140002def  pop     r15
0x140002df1  pop     r14
0x140002df3  pop     r13
0x140002df5  pop     r12
0x140002df7  pop     rdi
0x140002df8  pop     rsi
0x140002df9  pop     rbx
0x140002dfa  pop     rbp
0x140002dfb  retn
0x140002dfd  mov     rcx, r15
0x140002e00  call    BthScoUnRegisterServer
0x140002e05  mov     rdx, [r13+10h]
0x140002e09  test    rdx, rdx
0x140002e0c  jz      loc_140002D55
0x140002e12  mov     rax, cs:WdfFunctions_01015
0x140002e19  mov     rcx, cs:WdfDriverGlobals
0x140002e20  mov     rax, [rax+680h]
0x140002e27  call    _guard_dispatch_icall
0x140002e2c  jmp     loc_140002D55
0x140002e31  mov     r8b, dil; CaseInSensitive
0x140002e34  lea     rdx, [rbp+57h+String2]; String2
0x140002e38  mov     rcx, rbx; String1
0x140002e3b  call    cs:__imp_RtlCompareUnicodeString
0x140002e42  nop     dword ptr [rax+rax+00h]
0x140002e47  test    eax, eax
0x140002e49  jnz     loc_140002ED0
0x140002e4f  cmp     qword ptr [rsi+140h], 0
0x140002e57  jnz     short loc_140002EC6
0x140002e59  mov     rax, cs:off_140022100
0x140002e60  lea     r9, [rbp+57h+arg_0]
0x140002e64  mov     rcx, cs:WdfDriverGlobals
0x140002e6b  lea     r8, [rbp+57h+var_80]
0x140002e6f  xorps   xmm0, xmm0
0x140002e72  mov     [rbp+57h+var_50], rax
0x140002e76  mov     rax, cs:WdfFunctions_01015
0x140002e7d  mov     rdx, r14
0x140002e80  movups  [rbp+57h+var_70], xmm0
0x140002e84  mov     [rbp+57h+arg_0], 0
0x140002e8c  movups  [rbp+57h+var_80], xmm0
0x140002e90  mov     dword ptr [rbp+57h+var_80], 38h ; '8'
0x140002e97  movups  [rbp+57h+var_60], xmm0
0x140002e9b  mov     dword ptr [rbp+57h+var_70+8], edi
0x140002e9e  mov     dword ptr [rbp+57h+var_70+0Ch], edi
0x140002ea1  mov     rax, [rax+658h]
0x140002ea8  call    _guard_dispatch_icall
0x140002ead  mov     ebx, eax
0x140002eaf  test    eax, eax
0x140002eb1  js      short loc_140002EBA
0x140002eb3  mov     [rsi+140h], r14
0x140002eba  mov     rax, [rbp+57h+arg_0]
0x140002ebe  mov     [rax+14h], edi
0x140002ec1  jmp     loc_140002D5C
0x140002ec6  mov     ebx, 0C0000022h
0x140002ecb  jmp     loc_140002D5C
0x140002ed0  mov     ebx, 0C000000Fh
0x140002ed5  jmp     loc_140002D5C
```
