# WUComTimeout::ComTimeout::MakeComCall__lambda_33d158915d3784c0a0fbf60277e09e41___

- ea: `0x14003ed44`
- end: `0x14003eee3`
- name: `WUComTimeout::ComTimeout::MakeComCall__lambda_33d158915d3784c0a0fbf60277e09e41___`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14003e428`

## callees

- `0x140008de4`
- `0x1400154b4`
- `0x14003ed44`
- `0x14004484c`
- `0x14004489c`
- `0x140044994`
- `0x140045dc0`
- `0x14004cd00`

## string_xrefs

- `0x14003ed72`: `ComTimeout::MakeComCall [%hs]`
- `0x14003ee25`: `COM call timed out`
- `0x14003edc8`: `C:\__w\1\s\src\Client\inc\ComTimeout.h`
- `0x14003ee5d`: `WUComTimeout::ComTimeout::MakeComCall`
- `0x14003ee94`: `COM call [%hs, from %hs:%u] timed out after %u seconds`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WUComTimeout::ComTimeout::MakeComCall__lambda_33d158915d3784c0a0fbf60277e09e41___(_QWORD **a1)
{
  int v2; // eax
  int v3; // ebx
  int v5; // [rsp+20h] [rbp-58h]
  __int64 v6; // [rsp+20h] [rbp-58h]
  __int128 pv; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  WUTrace(0, 0, 0x10000, 5, 0, L"ComTimeout::MakeComCall [%hs]");
  pv = 0;
  WORD6(pv) = 0;
  v2 = WUComTimeout::ComTimeout::SetTimer(&pv);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD *))(*(_QWORD *)**a1 + 32LL))(
           **a1,
           6000,
           1,
           *a1[1],
           a1[2]);
    if ( v3 < 0 && BYTE13(pv) )
    {
      WUTrace("WUComTimeout::ComTimeout::MakeComCall", 52, 32, 3, 0, L"TelemetryAssert (%ws): %ws");
      WUTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
      LODWORD(v6) = v3;
      WUTrace(0, 0, 0x10000, 1, v6, L"COM call [%hs, from %hs:%u] timed out after %u seconds");
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\ComTimeout.h",
      (const char *)(unsigned int)v2,
      v5);
  }
  WUComTimeout::ComTimeout::~ComTimeout((PTP_TIMER *)&pv);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14003ed44  mov     r11, rsp
0x14003ed47  mov     [r11+10h], rbx
0x14003ed4b  mov     [r11+18h], rdi
0x14003ed4f  push    r14
0x14003ed51  sub     rsp, 70h
0x14003ed55  mov     rax, cs:__security_cookie
0x14003ed5c  xor     rax, rsp
0x14003ed5f  mov     [rsp+78h+var_18], rax
0x14003ed64  mov     rdi, rcx
0x14003ed67  lea     r14, aXpenumNext6000; "xpEnum->Next(6000, 1, ppObject, &uRetur"...
0x14003ed6e  mov     [r11-48h], r14
0x14003ed72  lea     rax, aComtimeoutMake; "ComTimeout::MakeComCall [%hs]"
0x14003ed79  mov     [r11-50h], rax
0x14003ed7d  mov     qword ptr [r11-58h], 0
0x14003ed85  xor     edx, edx
0x14003ed87  xor     ecx, ecx
0x14003ed89  lea     r9d, [rdx+5]
0x14003ed8d  mov     r8d, 10000h
0x14003ed93  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003ed98  xorps   xmm0, xmm0
0x14003ed9b  movups  [rsp+78h+pv], xmm0
0x14003eda0  mov     qword ptr [rsp+78h+pv], 0
0x14003eda9  mov     word ptr [rsp+78h+pv+0Ch], 0
0x14003edb0  lea     rcx, [rsp+78h+pv]; pv
0x14003edb5  call    ?SetTimer@ComTimeout@WUComTimeout@@QEAAJK@Z; WUComTimeout::ComTimeout::SetTimer(ulong)
0x14003edba  mov     ebx, eax
0x14003edbc  test    eax, eax
0x14003edbe  jns     short loc_14003EDDE
0x14003edc0  mov     rcx, [rsp+78h]; this
0x14003edc5  mov     r9d, eax; char *
0x14003edc8  lea     r8, aCW1SSrcClientI; "C:\\__w\\1\\s\\src\\Client\\inc\\ComTim"...
0x14003edcf  mov     edx, 2Eh ; '.'; void *
0x14003edd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003edd9  jmp     loc_14003EEB7
0x14003edde  mov     rax, [rdi]
0x14003ede1  mov     rcx, [rax]
0x14003ede4  mov     r9, [rdi+8]
0x14003ede8  mov     rax, [rcx]
0x14003edeb  mov     r10, [rax+20h]
0x14003edef  mov     rax, [rdi+10h]
0x14003edf3  mov     [rsp+78h+var_58], rax
0x14003edf8  mov     r9, [r9]
0x14003edfb  mov     edi, 1
0x14003ee00  mov     r8d, edi
0x14003ee03  mov     edx, 1770h
0x14003ee08  mov     rax, r10
0x14003ee0b  call    _guard_dispatch_icall
0x14003ee10  mov     ebx, eax
0x14003ee12  test    eax, eax
0x14003ee14  jns     loc_14003EEB7
0x14003ee1a  cmp     byte ptr [rsp+78h+pv+0Dh], 0
0x14003ee1f  jz      loc_14003EEB7
0x14003ee25  lea     rax, aComCallTimedOu; "COM call timed out"
0x14003ee2c  mov     [rsp+78h+var_40], rax
0x14003ee31  lea     rax, aFalse; "false"
0x14003ee38  mov     [rsp+78h+var_48], rax
0x14003ee3d  lea     rax, aTelemetryasser; "TelemetryAssert (%ws): %ws"
0x14003ee44  mov     [rsp+78h+var_50], rax
0x14003ee49  mov     [rsp+78h+var_58], 0
0x14003ee52  lea     edx, [rdi+33h]
0x14003ee55  lea     r9d, [rdi+2]
0x14003ee59  lea     r8d, [rdi+1Fh]
0x14003ee5d  lea     rcx, aWucomtimeoutCo; "WUComTimeout::ComTimeout::MakeComCall"
0x14003ee64  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003ee69  or      ecx, 0FFFFFFFFh; unsigned int
0x14003ee6c  mov     edx, ecx; unsigned int
0x14003ee6e  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x14003ee73  mov     [rsp+78h+var_30], 0Fh
0x14003ee7b  mov     [rsp+78h+var_38], 35h ; '5'
0x14003ee83  lea     rax, aWbemutilGetfir; "WBemUtil::GetFirstWbemObject"
0x14003ee8a  mov     [rsp+78h+var_40], rax
0x14003ee8f  mov     [rsp+78h+var_48], r14
0x14003ee94  lea     rax, aComCallHsFromH; "COM call [%hs, from %hs:%u] timed out a"...
0x14003ee9b  mov     [rsp+78h+var_50], rax
0x14003eea0  mov     dword ptr [rsp+78h+var_58], ebx
0x14003eea4  mov     r9d, edi
0x14003eea7  xor     edx, edx
0x14003eea9  xor     ecx, ecx
0x14003eeab  mov     r8d, 10000h
0x14003eeb1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003eeb6  nop
0x14003eeb7  lea     rcx, [rsp+78h+pv]; this
0x14003eebc  call    ??1ComTimeout@WUComTimeout@@QEAA@XZ; WUComTimeout::ComTimeout::~ComTimeout(void)
0x14003eec1  mov     eax, ebx
0x14003eec3  mov     rcx, [rsp+78h+var_18]
0x14003eec8  xor     rcx, rsp; StackCookie
0x14003eecb  call    __security_check_cookie
0x14003eed0  lea     r11, [rsp+78h+var_8]
0x14003eed5  mov     rbx, [r11+18h]
0x14003eed9  mov     rdi, [r11+20h]
0x14003eedd  mov     rsp, r11
0x14003eee0  pop     r14
0x14003eee2  retn
```
