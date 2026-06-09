# WUComTimeout::ComTimeout::MakeComCall__lambda_5356d91da545972b1b115d33b2d2653d___

- ea: `0x14003eb78`
- end: `0x14003ed3b`
- name: `WUComTimeout::ComTimeout::MakeComCall__lambda_5356d91da545972b1b115d33b2d2653d___`
- size: `451`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x14003e428`

## callees

- `0x140008de4`
- `0x1400154b4`
- `0x14003eb78`
- `0x14004484c`
- `0x14004489c`
- `0x140044994`
- `0x140045dc0`
- `0x14004cd00`

## string_xrefs

- `0x14003eb9d`: `pWbemServices->CreateInstanceEnum(xbstrWin32Class.Get(), 0, 0, xpEnum.ReleaseAndGetAddressOf())`
- `0x14003eba8`: `ComTimeout::MakeComCall [%hs]`
- `0x14003ec78`: `COM call timed out`
- `0x14003ec01`: `C:\__w\1\s\src\Client\inc\ComTimeout.h`
- `0x14003ecb2`: `WUComTimeout::ComTimeout::MakeComCall`
- `0x14003ece9`: `COM call [%hs, from %hs:%u] timed out after %u seconds`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WUComTimeout::ComTimeout::MakeComCall__lambda_5356d91da545972b1b115d33b2d2653d___(__int64 **a1)
{
  int v2; // eax
  int v3; // ebx
  __int64 v4; // rsi
  __int64 (__fastcall *v5)(__int64, _QWORD, _QWORD, _QWORD, __int64 *); // rbp
  __int64 *v6; // rbx
  int v8; // [rsp+20h] [rbp-68h]
  __int64 v9; // [rsp+20h] [rbp-68h]
  __int128 pv; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  WUTrace(0, 0, 0x10000, 5, 0, L"ComTimeout::MakeComCall [%hs]");
  pv = 0;
  WORD6(pv) = 0;
  v2 = WUComTimeout::ComTimeout::SetTimer(&pv);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = **a1;
    v5 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v4 + 144LL);
    v6 = a1[2];
    if ( *v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*v6 + 16LL))(*v6);
      *v6 = 0;
    }
    v3 = v5(v4, *a1[1], 0, 0, v6);
    if ( v3 < 0 && BYTE13(pv) )
    {
      WUTrace("WUComTimeout::ComTimeout::MakeComCall", 52, 32, 3, 0, L"TelemetryAssert (%ws): %ws");
      WUTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
      LODWORD(v9) = v3;
      WUTrace(0, 0, 0x10000, 1, v9, L"COM call [%hs, from %hs:%u] timed out after %u seconds");
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\ComTimeout.h",
      (const char *)(unsigned int)v2,
      v8);
  }
  WUComTimeout::ComTimeout::~ComTimeout((PTP_TIMER *)&pv);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14003eb78  mov     r11, rsp
0x14003eb7b  mov     [r11+10h], rbx
0x14003eb7f  mov     [r11+18h], rbp
0x14003eb83  push    rsi
0x14003eb84  push    rdi
0x14003eb85  push    r12
0x14003eb87  sub     rsp, 70h
0x14003eb8b  mov     rax, cs:__security_cookie
0x14003eb92  xor     rax, rsp
0x14003eb95  mov     [rsp+88h+var_28], rax
0x14003eb9a  mov     rdi, rcx
0x14003eb9d  lea     r12, aPwbemservicesC; "pWbemServices->CreateInstanceEnum(xbstr"...
0x14003eba4  mov     [r11-58h], r12
0x14003eba8  lea     rax, aComtimeoutMake; "ComTimeout::MakeComCall [%hs]"
0x14003ebaf  mov     [r11-60h], rax
0x14003ebb3  mov     qword ptr [r11-68h], 0
0x14003ebbb  xor     edx, edx
0x14003ebbd  xor     ecx, ecx
0x14003ebbf  lea     r9d, [rdx+5]
0x14003ebc3  mov     r8d, 10000h
0x14003ebc9  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003ebce  xorps   xmm0, xmm0
0x14003ebd1  movups  [rsp+88h+pv], xmm0
0x14003ebd6  mov     qword ptr [rsp+88h+pv], 0
0x14003ebdf  mov     word ptr [rsp+88h+pv+0Ch], 0
0x14003ebe6  lea     rcx, [rsp+88h+pv]; pv
0x14003ebeb  call    ?SetTimer@ComTimeout@WUComTimeout@@QEAAJK@Z; WUComTimeout::ComTimeout::SetTimer(ulong)
0x14003ebf0  mov     ebx, eax
0x14003ebf2  test    eax, eax
0x14003ebf4  jns     short loc_14003EC17
0x14003ebf6  mov     rcx, [rsp+88h]; this
0x14003ebfe  mov     r9d, eax; char *
0x14003ec01  lea     r8, aCW1SSrcClientI; "C:\\__w\\1\\s\\src\\Client\\inc\\ComTim"...
0x14003ec08  mov     edx, 2Eh ; '.'; void *
0x14003ec0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003ec12  jmp     loc_14003ED0D
0x14003ec17  mov     rax, [rdi]
0x14003ec1a  mov     rsi, [rax]
0x14003ec1d  mov     rax, [rsi]
0x14003ec20  mov     rbp, [rax+90h]
0x14003ec27  mov     rbx, [rdi+10h]
0x14003ec2b  mov     rcx, [rbx]
0x14003ec2e  test    rcx, rcx
0x14003ec31  jz      short loc_14003EC46
0x14003ec33  mov     rax, [rcx]
0x14003ec36  mov     rax, [rax+10h]
0x14003ec3a  call    _guard_dispatch_icall
0x14003ec3f  mov     qword ptr [rbx], 0
0x14003ec46  mov     rdx, [rdi+8]
0x14003ec4a  mov     [rsp+88h+var_68], rbx
0x14003ec4f  xor     r9d, r9d
0x14003ec52  xor     r8d, r8d
0x14003ec55  mov     rdx, [rdx]
0x14003ec58  mov     rcx, rsi
0x14003ec5b  mov     rax, rbp
0x14003ec5e  call    _guard_dispatch_icall
0x14003ec63  mov     ebx, eax
0x14003ec65  test    eax, eax
0x14003ec67  jns     loc_14003ED0D
0x14003ec6d  cmp     byte ptr [rsp+88h+pv+0Dh], 0
0x14003ec72  jz      loc_14003ED0D
0x14003ec78  lea     rax, aComCallTimedOu; "COM call timed out"
0x14003ec7f  mov     [rsp+88h+var_50], rax
0x14003ec84  lea     rax, aFalse; "false"
0x14003ec8b  mov     [rsp+88h+var_58], rax
0x14003ec90  lea     rax, aTelemetryasser; "TelemetryAssert (%ws): %ws"
0x14003ec97  mov     [rsp+88h+var_60], rax
0x14003ec9c  mov     [rsp+88h+var_68], 0
0x14003eca5  mov     edx, 34h ; '4'
0x14003ecaa  lea     r9d, [rdx-31h]
0x14003ecae  lea     r8d, [rdx-14h]
0x14003ecb2  lea     rcx, aWucomtimeoutCo; "WUComTimeout::ComTimeout::MakeComCall"
0x14003ecb9  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003ecbe  or      ecx, 0FFFFFFFFh; unsigned int
0x14003ecc1  mov     edx, ecx; unsigned int
0x14003ecc3  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x14003ecc8  mov     [rsp+88h+var_40], 0Fh
0x14003ecd0  mov     [rsp+88h+var_48], 2Ch ; ','
0x14003ecd8  lea     rax, aWbemutilGetfir; "WBemUtil::GetFirstWbemObject"
0x14003ecdf  mov     [rsp+88h+var_50], rax
0x14003ece4  mov     [rsp+88h+var_58], r12
0x14003ece9  lea     rax, aComCallHsFromH; "COM call [%hs, from %hs:%u] timed out a"...
0x14003ecf0  mov     [rsp+88h+var_60], rax
0x14003ecf5  mov     dword ptr [rsp+88h+var_68], ebx
0x14003ecf9  xor     edx, edx
0x14003ecfb  xor     ecx, ecx
0x14003ecfd  lea     r9d, [rdx+1]
0x14003ed01  mov     r8d, 10000h
0x14003ed07  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003ed0c  nop
0x14003ed0d  lea     rcx, [rsp+88h+pv]; this
0x14003ed12  call    ??1ComTimeout@WUComTimeout@@QEAA@XZ; WUComTimeout::ComTimeout::~ComTimeout(void)
0x14003ed17  mov     eax, ebx
0x14003ed19  mov     rcx, [rsp+88h+var_28]
0x14003ed1e  xor     rcx, rsp; StackCookie
0x14003ed21  call    __security_check_cookie
0x14003ed26  lea     r11, [rsp+88h+var_18]
0x14003ed2b  mov     rbx, [r11+28h]
0x14003ed2f  mov     rbp, [r11+30h]
0x14003ed33  mov     rsp, r11
0x14003ed36  pop     r12
0x14003ed38  pop     rdi
0x14003ed39  pop     rsi
0x14003ed3a  retn
```
