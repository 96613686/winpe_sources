# Controller_TelemetryUpdateSubmitReportSuccess

- ea: `0x140079d7c`
- end: `0x140079fe9`
- name: `Controller_TelemetryUpdateSubmitReportSuccess`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140042d88`

## callees

- `0x14001ad0c`
- `0x14001d02c`
- `0x1400599b0`
- `0x140079d7c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140079e79`
- `ntoskrnl!RtlInitUnicodeString` at `0x140079f3e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140079e79`
- `ntoskrnl!RtlInitUnicodeString` at `0x140079f3e`

## string_xrefs

- `0x140079e6e`: `OutOfOrderCommandCompletion`

## pseudocode

```c
__int64 __fastcall Controller_TelemetryUpdateSubmitReportSuccess(_QWORD *a1, int a2)
{
  int v2; // ebx
  __int64 result; // rax
  int v5; // ebx
  int v6; // edx
  int v7; // r9d
  char v8; // [rsp+28h] [rbp-28h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  __int64 v10; // [rsp+80h] [rbp+30h] BYREF
  int v11; // [rsp+88h] [rbp+38h] BYREF

  v11 = 0;
  v10 = 0;
  v2 = a2;
  DestinationString = 0;
  if ( (a2 & 0xFFFFEFC0) != 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v8 = a2;
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_D(a1[9], a2, 4, 261, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, v8);
  }
  result = a1[97] | (1LL << (v2 & 0x3F));
  a1[97] = result;
  v5 = v2 - 4111;
  if ( v5 )
  {
    if ( v5 != 3 )
      goto LABEL_19;
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64, _QWORD, __int64 *))(WdfFunctions_01033 + 384))(
               WdfDriverGlobals,
               *a1,
               1,
               131078,
               0,
               &v10);
    if ( (int)result >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"OutOfOrderCommandCompletion");
      v11 = 1;
      result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, __int64, int, int *))(WdfFunctions_01033 + 1928))(
                 WdfDriverGlobals,
                 v10,
                 &DestinationString,
                 4,
                 4,
                 &v11);
      if ( (int)result >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_19;
      v7 = 265;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_19;
      v7 = 264;
    }
  }
  else
  {
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64, _QWORD, __int64 *))(WdfFunctions_01033 + 384))(
               WdfDriverGlobals,
               *a1,
               1,
               131078,
               0,
               &v10);
    if ( (int)result >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"OutdatedFirmwareVersion");
      result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, __int64, int, _QWORD *))(WdfFunctions_01033 + 1928))(
                 WdfDriverGlobals,
                 v10,
                 &DestinationString,
                 3,
                 8,
                 a1 + 91);
      if ( (int)result >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_19;
      v7 = 263;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_19;
      v7 = 262;
    }
  }
  LOBYTE(v6) = 3;
  result = WPP_RECORDER_SF_d(a1[9], v6, 4, v7, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, result);
LABEL_19:
  if ( v10 )
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01033 + 1848))(WdfDriverGlobals);
  return result;
}

```

## disassembly

```asm
0x140079d7c  mov     [rsp-28h+arg_10], rbx
0x140079d81  push    rbp
0x140079d82  push    rdi
0x140079d83  push    r12
0x140079d85  push    r14
0x140079d87  push    r15
0x140079d89  mov     rbp, rsp
0x140079d8c  sub     rsp, 50h
0x140079d90  mov     [rbp+arg_8], 0
0x140079d97  xorps   xmm0, xmm0
0x140079d9a  mov     [rbp+arg_0], 0
0x140079da2  mov     ebx, edx
0x140079da4  lea     r12, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140079dab  mov     rdi, rcx
0x140079dae  lea     r14, WPP_RECORDER_INITIALIZED
0x140079db5  mov     r15d, 4
0x140079dbb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140079dbf  test    edx, 0FFFFEFC0h
0x140079dc5  jz      short loc_140079DED
0x140079dc7  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140079dce  jz      short loc_140079DED
0x140079dd0  mov     rcx, [rcx+48h]
0x140079dd4  mov     r9d, 105h
0x140079dda  mov     dword ptr [rsp+50h+var_28], edx
0x140079dde  mov     r8d, r15d
0x140079de1  mov     dl, 2
0x140079de3  mov     [rsp+50h+var_30], r12
0x140079de8  call    WPP_RECORDER_SF_D
0x140079ded  mov     rax, [rdi+308h]
0x140079df4  mov     ecx, ebx
0x140079df6  and     ecx, 3Fh
0x140079df9  bts     rax, rcx
0x140079dfd  mov     [rdi+308h], rax
0x140079e04  sub     ebx, 100Fh
0x140079e0a  jz      loc_140079EDF
0x140079e10  cmp     ebx, 3
0x140079e13  jnz     loc_140079FB0
0x140079e19  mov     rax, cs:WdfFunctions_01033
0x140079e20  lea     rcx, [rbp+arg_0]
0x140079e24  mov     rdx, [rdi]
0x140079e27  lea     r8d, [rbx-2]
0x140079e2b  mov     qword ptr [rsp+50h+var_28], rcx
0x140079e30  mov     r9d, 20006h
0x140079e36  mov     rcx, cs:WdfDriverGlobals
0x140079e3d  mov     rax, [rax+180h]
0x140079e44  mov     [rsp+50h+var_30], 0
0x140079e4d  call    _guard_dispatch_icall
0x140079e52  test    eax, eax
0x140079e54  jns     short loc_140079E6E
0x140079e56  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140079e5d  jz      loc_140079FB0
0x140079e63  mov     r9d, 108h
0x140079e69  jmp     loc_140079F99
0x140079e6e  lea     rdx, aOutofordercomm; "OutOfOrderCommandCompletion"
0x140079e75  lea     rcx, [rbp+DestinationString]; DestinationString
0x140079e79  call    cs:__imp_RtlInitUnicodeString
0x140079e80  nop     dword ptr [rax+rax+00h]
0x140079e85  mov     rax, cs:WdfFunctions_01033
0x140079e8c  lea     rcx, [rbp+arg_8]
0x140079e90  mov     rdx, [rbp+arg_0]
0x140079e94  lea     r8, [rbp+DestinationString]
0x140079e98  mov     qword ptr [rsp+50h+var_28], rcx
0x140079e9d  mov     r9d, r15d
0x140079ea0  mov     rcx, cs:WdfDriverGlobals
0x140079ea7  mov     [rbp+arg_8], 1
0x140079eae  mov     rax, [rax+788h]
0x140079eb5  mov     dword ptr [rsp+50h+var_30], r15d
0x140079eba  call    _guard_dispatch_icall
0x140079ebf  test    eax, eax
0x140079ec1  jns     loc_140079FB0
0x140079ec7  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140079ece  jz      loc_140079FB0
0x140079ed4  mov     r9d, 109h
0x140079eda  jmp     loc_140079F99
0x140079edf  mov     rax, cs:WdfFunctions_01033
0x140079ee6  lea     rcx, [rbp+arg_0]
0x140079eea  mov     rdx, [rdi]
0x140079eed  mov     r9d, 20006h
0x140079ef3  mov     qword ptr [rsp+50h+var_28], rcx
0x140079ef8  mov     r8d, 1
0x140079efe  mov     rcx, cs:WdfDriverGlobals
0x140079f05  mov     rax, [rax+180h]
0x140079f0c  mov     [rsp+50h+var_30], 0
0x140079f15  call    _guard_dispatch_icall
0x140079f1a  test    eax, eax
0x140079f1c  jns     short loc_140079F33
0x140079f1e  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140079f25  jz      loc_140079FB0
0x140079f2b  mov     r9d, 106h
0x140079f31  jmp     short loc_140079F99
0x140079f33  lea     rdx, aOutdatedfirmwa; "OutdatedFirmwareVersion"
0x140079f3a  lea     rcx, [rbp+DestinationString]; DestinationString
0x140079f3e  call    cs:__imp_RtlInitUnicodeString
0x140079f45  nop     dword ptr [rax+rax+00h]
0x140079f4a  mov     rax, cs:WdfFunctions_01033
0x140079f51  lea     rcx, [rdi+2D8h]
0x140079f58  mov     rdx, [rbp+arg_0]
0x140079f5c  lea     r8, [rbp+DestinationString]
0x140079f60  mov     qword ptr [rsp+50h+var_28], rcx
0x140079f65  mov     r9d, 3
0x140079f6b  mov     rcx, cs:WdfDriverGlobals
0x140079f72  mov     rax, [rax+788h]
0x140079f79  mov     dword ptr [rsp+50h+var_30], 8
0x140079f81  call    _guard_dispatch_icall
0x140079f86  test    eax, eax
0x140079f88  jns     short loc_140079FB0
0x140079f8a  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140079f91  jz      short loc_140079FB0
0x140079f93  mov     r9d, 107h
0x140079f99  mov     rcx, [rdi+48h]
0x140079f9d  mov     r8d, r15d
0x140079fa0  mov     dword ptr [rsp+50h+var_28], eax
0x140079fa4  mov     dl, 3
0x140079fa6  mov     [rsp+50h+var_30], r12
0x140079fab  call    WPP_RECORDER_SF_d
0x140079fb0  mov     rdx, [rbp+arg_0]
0x140079fb4  test    rdx, rdx
0x140079fb7  jz      short loc_140079FD3
0x140079fb9  mov     rax, cs:WdfFunctions_01033
0x140079fc0  mov     rcx, cs:WdfDriverGlobals
0x140079fc7  mov     rax, [rax+738h]
0x140079fce  call    _guard_dispatch_icall
0x140079fd3  mov     rbx, [rsp+50h+arg_10]
0x140079fdb  add     rsp, 50h
0x140079fdf  pop     r15
0x140079fe1  pop     r14
0x140079fe3  pop     r12
0x140079fe5  pop     rdi
0x140079fe6  pop     rbp
0x140079fe7  retn
```
