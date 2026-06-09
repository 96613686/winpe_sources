# Controller_TelemetryOkToGenerateReport

- ea: `0x140079a78`
- end: `0x140079d74`
- name: `Controller_TelemetryOkToGenerateReport`
- size: `764`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140042d88`

## callees

- `0x14001ad0c`
- `0x14001d02c`
- `0x1400599b0`
- `0x140079a78`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140079bb3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140079cc7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140079bb3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140079cc7`

## string_xrefs

- `0x140079ba8`: `OutOfOrderCommandCompletion`

## pseudocode

```c
char __fastcall Controller_TelemetryOkToGenerateReport(_QWORD *a1, __int64 a2, int a3)
{
  char v3; // di
  __int64 v4; // rax
  unsigned __int8 v5; // cf
  int v8; // r8d
  int v9; // r8d
  int v10; // eax
  unsigned int v11; // edx
  char v12; // cl
  int v13; // r9d
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  __int64 v19; // [rsp+70h] [rbp+20h] BYREF
  int v20; // [rsp+80h] [rbp+30h] BYREF
  __int64 v21; // [rsp+88h] [rbp+38h] BYREF

  v20 = 0;
  v21 = 0;
  v3 = 0;
  v4 = a1[97];
  v5 = _bittest64(&v4, a3 & 0x3F);
  v19 = 0;
  DestinationString = 0;
  if ( !v5 )
  {
    v8 = a3 - 4109;
    if ( !v8 )
    {
      v17 = *(_DWORD *)(a2 + 84);
      if ( (v17 & 1) == 0 )
      {
        v3 = 1;
        *(_DWORD *)(a2 + 84) = v17 | 1;
        return v3;
      }
      goto LABEL_4;
    }
    v9 = v8 - 2;
    if ( v9 )
    {
      if ( v9 != 3 )
        return 1;
      v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64, _QWORD, __int64 *))(WdfFunctions_01033 + 384))(
              WdfDriverGlobals,
              *a1,
              1,
              131078,
              0,
              &v19);
      v12 = v10;
      if ( v10 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_4;
        v13 = 245;
        goto LABEL_21;
      }
      RtlInitUnicodeString(&DestinationString, L"OutOfOrderCommandCompletion");
      v14 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, __int64, int *, _QWORD, _QWORD))(WdfFunctions_01033 + 1880))(
              WdfDriverGlobals,
              v19,
              &DestinationString,
              4,
              &v20,
              0,
              0);
      v11 = 0x80000000;
      v12 = v14;
      if ( (int)(v14 + 0x80000000) >= 0 && v14 != -1073741772 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_4;
        v13 = 246;
        goto LABEL_21;
      }
    }
    else
    {
      v15 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64, _QWORD, __int64 *))(WdfFunctions_01033 + 384))(
              WdfDriverGlobals,
              *a1,
              1,
              131078,
              0,
              &v19);
      v12 = v15;
      if ( v15 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_4;
        v13 = 243;
        goto LABEL_21;
      }
      RtlInitUnicodeString(&DestinationString, L"OutdatedFirmwareVersion");
      v16 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, __int64, __int64 *, _QWORD, _QWORD))(WdfFunctions_01033 + 1880))(
              WdfDriverGlobals,
              v19,
              &DestinationString,
              8,
              &v21,
              0,
              0);
      v12 = v16;
      if ( v16 >= 0 )
      {
        if ( a1[91] == v21 )
          goto LABEL_4;
      }
      else if ( v16 != -1073741772 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_4;
        v13 = 244;
LABEL_21:
        LOBYTE(v11) = 3;
        WPP_RECORDER_SF_d(a1[9], v11, 4, v13, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, v12);
        goto LABEL_4;
      }
    }
    v3 = 1;
    goto LABEL_4;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return v3;
  LOBYTE(a2) = 4;
  WPP_RECORDER_SF_D(a1[9], a2, 4, 242, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, a3);
LABEL_4:
  if ( v19 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01033 + 1848))(WdfDriverGlobals);
  return v3;
}

```

## disassembly

```asm
0x140079a78  push    rbp
0x140079a7a  push    rbx
0x140079a7b  push    rdi
0x140079a7c  mov     rbp, rsp
0x140079a7f  sub     rsp, 50h
0x140079a83  mov     eax, r8d
0x140079a86  mov     [rbp+arg_10], 0
0x140079a8d  and     eax, 3Fh
0x140079a90  mov     [rbp+arg_18], 0
0x140079a98  movzx   r9d, al
0x140079a9c  xor     dil, dil
0x140079a9f  mov     rax, [rcx+308h]
0x140079aa6  xorps   xmm0, xmm0
0x140079aa9  bt      rax, r9
0x140079aad  mov     [rbp+arg_0], 0
0x140079ab5  mov     rbx, rcx
0x140079ab8  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140079abc  jnb     short loc_140079B26
0x140079abe  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140079ac5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140079acc  jz      short loc_140079B1A
0x140079ace  mov     rcx, [rcx+48h]
0x140079ad2  lea     rax, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140079ad9  mov     dword ptr [rsp+50h+var_28], r8d
0x140079ade  mov     r9d, 0F2h
0x140079ae4  mov     r8d, 4
0x140079aea  mov     [rsp+50h+var_30], rax
0x140079aef  mov     dl, r8b
0x140079af2  call    WPP_RECORDER_SF_D
0x140079af7  mov     rdx, [rbp+arg_0]
0x140079afb  test    rdx, rdx
0x140079afe  jz      short loc_140079B1A
0x140079b00  mov     rcx, cs:WdfFunctions_01033
0x140079b07  mov     rax, [rcx+738h]
0x140079b0e  mov     rcx, cs:WdfDriverGlobals
0x140079b15  call    _guard_dispatch_icall
0x140079b1a  mov     al, dil
0x140079b1d  add     rsp, 50h
0x140079b21  pop     rdi
0x140079b22  pop     rbx
0x140079b23  pop     rbp
0x140079b24  retn
0x140079b26  sub     r8d, 100Dh
0x140079b2d  jz      loc_140079D5B
0x140079b33  sub     r8d, 2
0x140079b37  jz      loc_140079C3B
0x140079b3d  cmp     r8d, 3
0x140079b41  jz      short loc_140079B48
0x140079b43  mov     dil, 1
0x140079b46  jmp     short loc_140079B1A
0x140079b48  mov     rax, cs:WdfFunctions_01033
0x140079b4f  lea     rcx, [rbp+arg_0]
0x140079b53  mov     rdx, [rbx]
0x140079b56  mov     r9d, 20006h
0x140079b5c  mov     [rsp+50h+var_28], rcx
0x140079b61  mov     r8d, 1
0x140079b67  mov     rcx, cs:WdfDriverGlobals
0x140079b6e  mov     rax, [rax+180h]
0x140079b75  mov     [rsp+50h+var_30], 0
0x140079b7e  call    _guard_dispatch_icall
0x140079b83  mov     ecx, eax
0x140079b85  test    eax, eax
0x140079b87  jns     short loc_140079BA8
0x140079b89  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140079b90  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140079b97  jz      loc_140079AF7
0x140079b9d  mov     r9d, 0F5h
0x140079ba3  jmp     loc_140079C96
0x140079ba8  lea     rdx, aOutofordercomm; "OutOfOrderCommandCompletion"
0x140079baf  lea     rcx, [rbp+DestinationString]; DestinationString
0x140079bb3  call    cs:__imp_RtlInitUnicodeString
0x140079bba  nop     dword ptr [rax+rax+00h]
0x140079bbf  mov     rax, cs:WdfFunctions_01033
0x140079bc6  lea     rcx, [rbp+arg_10]
0x140079bca  mov     rdx, [rbp+arg_0]
0x140079bce  lea     r8, [rbp+DestinationString]
0x140079bd2  mov     [rsp+50h+var_20], 0
0x140079bdb  mov     r9d, 4
0x140079be1  mov     [rsp+50h+var_28], 0
0x140079bea  mov     rax, [rax+758h]
0x140079bf1  mov     [rsp+50h+var_30], rcx
0x140079bf6  mov     rcx, cs:WdfDriverGlobals
0x140079bfd  call    _guard_dispatch_icall
0x140079c02  mov     edx, 80000000h
0x140079c07  mov     ecx, eax
0x140079c09  add     eax, edx
0x140079c0b  test    edx, eax
0x140079c0d  jnz     loc_140079D53
0x140079c13  cmp     ecx, 0C0000034h
0x140079c19  jz      loc_140079D53
0x140079c1f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140079c26  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140079c2d  jz      loc_140079AF7
0x140079c33  mov     r9d, 0F6h
0x140079c39  jmp     short loc_140079C96
0x140079c3b  mov     rax, cs:WdfFunctions_01033
0x140079c42  lea     rcx, [rbp+arg_0]
0x140079c46  mov     rdx, [rbx]
0x140079c49  mov     r9d, 20006h
0x140079c4f  mov     [rsp+50h+var_28], rcx
0x140079c54  mov     r8d, 1
0x140079c5a  mov     rcx, cs:WdfDriverGlobals
0x140079c61  mov     rax, [rax+180h]
0x140079c68  mov     [rsp+50h+var_30], 0
0x140079c71  call    _guard_dispatch_icall
0x140079c76  mov     ecx, eax
0x140079c78  test    eax, eax
0x140079c7a  jns     short loc_140079CBC
0x140079c7c  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140079c83  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140079c8a  jz      loc_140079AF7
0x140079c90  mov     r9d, 0F3h
0x140079c96  mov     dword ptr [rsp+50h+var_28], ecx
0x140079c9a  lea     rax, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140079ca1  mov     rcx, [rbx+48h]
0x140079ca5  mov     r8d, 4
0x140079cab  mov     dl, 3
0x140079cad  mov     [rsp+50h+var_30], rax
0x140079cb2  call    WPP_RECORDER_SF_d
0x140079cb7  jmp     loc_140079AF7
0x140079cbc  lea     rdx, aOutdatedfirmwa; "OutdatedFirmwareVersion"
0x140079cc3  lea     rcx, [rbp+DestinationString]; DestinationString
0x140079cc7  call    cs:__imp_RtlInitUnicodeString
0x140079cce  nop     dword ptr [rax+rax+00h]
0x140079cd3  mov     rax, cs:WdfFunctions_01033
0x140079cda  lea     rcx, [rbp+arg_18]
0x140079cde  mov     rdx, [rbp+arg_0]
0x140079ce2  lea     r8, [rbp+DestinationString]
0x140079ce6  mov     [rsp+50h+var_20], 0
0x140079cef  mov     r9d, 8
0x140079cf5  mov     [rsp+50h+var_28], 0
0x140079cfe  mov     rax, [rax+758h]
0x140079d05  mov     [rsp+50h+var_30], rcx
0x140079d0a  mov     rcx, cs:WdfDriverGlobals
0x140079d11  call    _guard_dispatch_icall
0x140079d16  mov     ecx, eax
0x140079d18  test    eax, eax
0x140079d1a  jns     short loc_140079D42
0x140079d1c  cmp     eax, 0C0000034h
0x140079d21  jz      short loc_140079D53
0x140079d23  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140079d2a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140079d31  jz      loc_140079AF7
0x140079d37  mov     r9d, 0F4h
0x140079d3d  jmp     loc_140079C96
0x140079d42  mov     rax, [rbp+arg_18]
0x140079d46  cmp     [rbx+2D8h], rax
0x140079d4d  jz      loc_140079AF7
0x140079d53  mov     dil, 1
0x140079d56  jmp     loc_140079AF7
0x140079d5b  mov     eax, [rdx+54h]
0x140079d5e  test    al, 1
0x140079d60  jnz     loc_140079AF7
0x140079d66  or      eax, 1
0x140079d69  mov     dil, 1
0x140079d6c  mov     [rdx+54h], eax
0x140079d6f  jmp     loc_140079B1A
```
