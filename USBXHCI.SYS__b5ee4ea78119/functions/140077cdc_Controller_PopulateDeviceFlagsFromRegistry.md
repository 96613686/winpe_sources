# Controller_PopulateDeviceFlagsFromRegistry

- ea: `0x140077cdc`
- end: `0x140077f0a`
- name: `Controller_PopulateDeviceFlagsFromRegistry`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400777b8`

## callees

- `0x14001ad0c`
- `0x140045764`
- `0x1400599b0`
- `0x140077cdc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140077ddc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140077ddc`

## pseudocode

```c
__int64 __fastcall Controller_PopulateDeviceFlagsFromRegistry(__int64 *a1, int a2)
{
  __int64 v3; // rdx
  __int64 v5; // rax
  __int64 result; // rax
  int v7; // edx
  int v8; // edx
  unsigned int i; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v11; // [rsp+78h] [rbp+10h] BYREF
  __int64 v12; // [rsp+80h] [rbp+18h] BYREF

  v3 = *a1;
  v12 = 0;
  v11 = 0;
  DestinationString = 0;
  if ( a2 == 2 )
  {
    v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 312))(WdfDriverGlobals, v3);
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _QWORD, __int64 *))(WdfFunctions_01033
                                                                                                 + 952))(
               WdfDriverGlobals,
               v5,
               131097,
               0,
               &v12);
  }
  else
  {
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64, _QWORD, __int64 *))(WdfFunctions_01033 + 384))(
               WdfDriverGlobals,
               v3,
               1,
               131097,
               0,
               &v12);
  }
  if ( (int)result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"UseStrictBiosHandoff");
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, unsigned int *))(WdfFunctions_01033 + 1920))(
               WdfDriverGlobals,
               v12,
               &DestinationString,
               &v11);
    if ( (int)result >= 0 )
    {
      result = v11;
      if ( v11 )
      {
        if ( v11 == 1 )
        {
          result = 0x8000000000000000uLL;
          a1[92] |= 0x8000000000000000uLL;
        }
      }
      else
      {
        result = 0x7FFFFFFFFFFFFFFFLL;
        a1[92] &= ~0x8000000000000000uLL;
      }
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 3;
    result = WPP_RECORDER_SF_d(a1[9], v7, 4, 168, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, result);
  }
  v8 = v12;
  if ( v12 )
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01033 + 1848))(WdfDriverGlobals);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    result = (__int64)WPP_GLOBAL_Control;
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v8) = 5;
      result = WPP_RECORDER_SF_d(a1[9], v8, 4, 169, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, a2);
    }
  }
  for ( i = 0; i < 2; ++i )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      result = (__int64)WPP_GLOBAL_Control;
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v8) = 5;
        result = WPP_RECORDER_SF_di(
                   a1[9],
                   v8,
                   4,
                   170,
                   (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
                   i,
                   a1[i + 92]);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140077cdc  mov     rax, rsp
0x140077cdf  mov     [rax+8], rbx
0x140077ce3  mov     [rax+20h], rbp
0x140077ce7  push    rsi
0x140077ce8  push    rdi
0x140077ce9  push    r15
0x140077ceb  sub     rsp, 50h
0x140077cef  xor     esi, esi
0x140077cf1  mov     edi, edx
0x140077cf3  mov     rdx, [rcx]
0x140077cf6  xorps   xmm0, xmm0
0x140077cf9  mov     [rax+18h], rsi
0x140077cfd  mov     rbx, rcx
0x140077d00  mov     [rax+10h], esi
0x140077d03  movups  xmmword ptr [rax-28h], xmm0
0x140077d07  mov     rax, cs:WdfFunctions_01033
0x140077d0e  cmp     edi, 2
0x140077d11  jnz     short loc_140077D5E
0x140077d13  mov     rax, [rax+138h]
0x140077d1a  mov     rcx, cs:WdfDriverGlobals
0x140077d21  call    _guard_dispatch_icall
0x140077d26  mov     rcx, cs:WdfFunctions_01033
0x140077d2d  mov     rdx, rax
0x140077d30  xor     r9d, r9d
0x140077d33  mov     r8d, 20019h
0x140077d39  mov     r10, [rcx+3B8h]
0x140077d40  lea     rcx, [rsp+68h+arg_10]
0x140077d48  mov     [rsp+68h+var_48], rcx
0x140077d4d  mov     rax, r10
0x140077d50  mov     rcx, cs:WdfDriverGlobals
0x140077d57  call    _guard_dispatch_icall
0x140077d5c  jmp     short loc_140077D8F
0x140077d5e  mov     rax, [rax+180h]
0x140077d65  lea     rcx, [rsp+68h+arg_10]
0x140077d6d  mov     [rsp+68h+var_40], rcx
0x140077d72  mov     r9d, 20019h
0x140077d78  mov     rcx, cs:WdfDriverGlobals
0x140077d7f  mov     r8d, 1
0x140077d85  mov     [rsp+68h+var_48], rsi
0x140077d8a  call    _guard_dispatch_icall
0x140077d8f  lea     rbp, WPP_RECORDER_INITIALIZED
0x140077d96  lea     r15, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140077d9d  test    eax, eax
0x140077d9f  jns     short loc_140077DD0
0x140077da1  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140077da8  jz      loc_140077E49
0x140077dae  mov     rcx, [rbx+48h]
0x140077db2  mov     r9d, 0A8h
0x140077db8  mov     dword ptr [rsp+68h+var_40], eax
0x140077dbc  mov     r8d, 4
0x140077dc2  mov     dl, 3
0x140077dc4  mov     [rsp+68h+var_48], r15
0x140077dc9  call    WPP_RECORDER_SF_d
0x140077dce  jmp     short loc_140077E49
0x140077dd0  lea     rdx, aUsestrictbiosh; "UseStrictBiosHandoff"
0x140077dd7  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140077ddc  call    cs:__imp_RtlInitUnicodeString
0x140077de3  nop     dword ptr [rax+rax+00h]
0x140077de8  mov     rax, cs:WdfFunctions_01033
0x140077def  lea     r9, [rsp+68h+arg_8]
0x140077df4  mov     rdx, [rsp+68h+arg_10]
0x140077dfc  lea     r8, [rsp+68h+DestinationString]
0x140077e01  mov     rcx, cs:WdfDriverGlobals
0x140077e08  mov     rax, [rax+780h]
0x140077e0f  call    _guard_dispatch_icall
0x140077e14  test    eax, eax
0x140077e16  js      short loc_140077E49
0x140077e18  mov     eax, [rsp+68h+arg_8]
0x140077e1c  test    eax, eax
0x140077e1e  jnz     short loc_140077E33
0x140077e20  mov     rax, 7FFFFFFFFFFFFFFFh
0x140077e2a  and     [rbx+2E0h], rax
0x140077e31  jmp     short loc_140077E49
0x140077e33  cmp     eax, 1
0x140077e36  jnz     short loc_140077E49
0x140077e38  mov     rax, 8000000000000000h
0x140077e42  or      [rbx+2E0h], rax
0x140077e49  mov     rdx, [rsp+68h+arg_10]
0x140077e51  test    rdx, rdx
0x140077e54  jz      short loc_140077E70
0x140077e56  mov     rax, cs:WdfFunctions_01033
0x140077e5d  mov     rcx, cs:WdfDriverGlobals
0x140077e64  mov     rax, [rax+738h]
0x140077e6b  call    _guard_dispatch_icall
0x140077e70  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140077e77  jz      short loc_140077EA6
0x140077e79  mov     rax, cs:WPP_GLOBAL_Control
0x140077e80  cmp     [rax+48h], si
0x140077e84  jz      short loc_140077EA6
0x140077e86  mov     rcx, [rbx+48h]
0x140077e8a  mov     r9d, 0A9h
0x140077e90  mov     dword ptr [rsp+68h+var_40], edi
0x140077e94  mov     r8d, 4
0x140077e9a  mov     dl, 5
0x140077e9c  mov     [rsp+68h+var_48], r15
0x140077ea1  call    WPP_RECORDER_SF_d
0x140077ea6  mov     edi, esi
0x140077ea8  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140077eaf  jz      short loc_140077EED
0x140077eb1  mov     rax, cs:WPP_GLOBAL_Control
0x140077eb8  cmp     [rax+48h], si
0x140077ebc  jz      short loc_140077EED
0x140077ebe  mov     rcx, [rbx+48h]
0x140077ec2  mov     r9d, 0AAh
0x140077ec8  mov     eax, edi
0x140077eca  mov     r8d, 4
0x140077ed0  mov     dl, 5
0x140077ed2  mov     rax, [rbx+rax*8+2E0h]
0x140077eda  mov     [rsp+68h+var_38], rax
0x140077edf  mov     dword ptr [rsp+68h+var_40], edi
0x140077ee3  mov     [rsp+68h+var_48], r15
0x140077ee8  call    WPP_RECORDER_SF_di
0x140077eed  inc     edi
0x140077eef  cmp     edi, 2
0x140077ef2  jb      short loc_140077EA8
0x140077ef4  lea     r11, [rsp+68h+var_18]
0x140077ef9  mov     rbx, [r11+20h]
0x140077efd  mov     rbp, [r11+38h]
0x140077f01  mov     rsp, r11
0x140077f04  pop     r15
0x140077f06  pop     rdi
0x140077f07  pop     rsi
0x140077f08  retn
```
