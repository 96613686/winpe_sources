# BlackScreenDiagnostics::CBlackScreenDiagnosticReport::GetVidPnOwner(void)

- ea: `0x14000e750`
- end: `0x14000e7dd`
- name: `?GetVidPnOwner@CBlackScreenDiagnosticReport@BlackScreenDiagnostics@@AEAAPEBGXZ`
- size: `141`
- prototype: `const unsigned __int16 *__fastcall(BlackScreenDiagnostics::CBlackScreenDiagnosticReport *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000e994`

## callees

- `0x14000e750`
- `0x14000e7e4`

## string_xrefs

- `0x14000e7ad`: `QueryDisplayConfigFailure`
- `0x14000e7a4`: `OpenAdaptorFailure`

## pseudocode

```c
const unsigned __int16 *__fastcall BlackScreenDiagnostics::CBlackScreenDiagnosticReport::GetVidPnOwner(
        BlackScreenDiagnostics::CBlackScreenDiagnosticReport *this)
{
  int v2; // [rsp+30h] [rbp+8h] BYREF
  int v3; // [rsp+34h] [rbp+Ch]

  v3 = HIDWORD(this);
  v2 = 0;
  BlackScreenDiagnostics::GetVidPnOwnership(&v2);
  switch ( v2 )
  {
    case 1:
      return L"DWM";
    case 2:
      return L"NotDWM";
    case 3:
      return L"None";
    case 4:
      return L"NoVidPnPresent";
    case 5:
      return L"QueryDisplayConfigFailure";
    case 6:
      return L"OpenAdaptorFailure";
    case 7:
      return L"CheckVidPnExclusiveOwnershipFailure";
  }
  return L"Unknown";
}

```

## disassembly

```asm
0x14000e750  mov     [rsp+arg_0], rcx
0x14000e755  sub     rsp, 28h
0x14000e759  lea     rcx, [rsp+28h+arg_0]
0x14000e75e  mov     dword ptr [rsp+28h+arg_0], 0
0x14000e766  call    BlackScreenDiagnostics__GetVidPnOwnership
0x14000e76b  mov     ecx, dword ptr [rsp+28h+arg_0]
0x14000e76f  sub     ecx, 1
0x14000e772  jz      short loc_14000E7D1
0x14000e774  sub     ecx, 1
0x14000e777  jz      short loc_14000E7C8
0x14000e779  sub     ecx, 1
0x14000e77c  jz      short loc_14000E7BF
0x14000e77e  sub     ecx, 1
0x14000e781  jz      short loc_14000E7B6
0x14000e783  sub     ecx, 1
0x14000e786  jz      short loc_14000E7AD
0x14000e788  sub     ecx, 1
0x14000e78b  jz      short loc_14000E7A4
0x14000e78d  cmp     ecx, 1
0x14000e790  jz      short loc_14000E79B
0x14000e792  lea     rax, aUnknown; "Unknown"
0x14000e799  jmp     short loc_14000E7D8
0x14000e79b  lea     rax, aCheckvidpnexcl; "CheckVidPnExclusiveOwnershipFailure"
0x14000e7a2  jmp     short loc_14000E7D8
0x14000e7a4  lea     rax, aOpenadaptorfai; "OpenAdaptorFailure"
0x14000e7ab  jmp     short loc_14000E7D8
0x14000e7ad  lea     rax, aQuerydisplayco_0; "QueryDisplayConfigFailure"
0x14000e7b4  jmp     short loc_14000E7D8
0x14000e7b6  lea     rax, aNovidpnpresent; "NoVidPnPresent"
0x14000e7bd  jmp     short loc_14000E7D8
0x14000e7bf  lea     rax, aNone; "None"
0x14000e7c6  jmp     short loc_14000E7D8
0x14000e7c8  lea     rax, aNotdwm; "NotDWM"
0x14000e7cf  jmp     short loc_14000E7D8
0x14000e7d1  lea     rax, aDwm_0; "DWM"
0x14000e7d8  add     rsp, 28h
0x14000e7dc  retn
```
