# WUComTimeout::ComTimeout::MakeComCall__lambda_910c479648d882804510b1671eed198a___

- ea: `0x14003eeec`
- end: `0x14003f0cf`
- name: `WUComTimeout::ComTimeout::MakeComCall__lambda_910c479648d882804510b1671eed198a___`
- size: `483`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x14003e814`

## callees

- `0x140008de4`
- `0x1400154b4`
- `0x14003eeec`
- `0x14004484c`
- `0x14004489c`
- `0x140044994`
- `0x140045dc0`
- `0x14004cd00`

## string_xrefs

- `0x14003ef11`: `xpWbemLocator->ConnectServer(xbstrNetworkResource, nullptr , nullptr , nullptr , 0L , nullptr , nullptr , xpWbemServices.ReleaseAndGetAddressOf())`
- `0x14003f06c`: `WBemUtil::GetComputerInfoFromWMI`
- `0x14003ef1c`: `ComTimeout::MakeComCall [%hs]`
- `0x14003f00c`: `COM call timed out`
- `0x14003ef75`: `C:\__w\1\s\src\Client\inc\ComTimeout.h`
- `0x14003f046`: `WUComTimeout::ComTimeout::MakeComCall`
- `0x14003f07d`: `COM call [%hs, from %hs:%u] timed out after %u seconds`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WUComTimeout::ComTimeout::MakeComCall__lambda_910c479648d882804510b1671eed198a___(__int64 **a1)
{
  int v2; // eax
  int v3; // ebx
  __int64 v4; // rsi
  __int64 (__fastcall *v5)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, __int64 *); // rbp
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
    v5 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v4 + 24LL);
    v6 = a1[2];
    if ( *v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*v6 + 16LL))(*v6);
      *v6 = 0;
    }
    v3 = v5(v4, *a1[1], 0, 0, 0, 0, 0, 0, v6);
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
0x14003eeec  mov     r11, rsp
0x14003eeef  mov     [r11+10h], rbx
0x14003eef3  mov     [r11+18h], rbp
0x14003eef7  push    rsi
0x14003eef8  push    rdi
0x14003eef9  push    r12
0x14003eefb  sub     rsp, 70h
0x14003eeff  mov     rax, cs:__security_cookie
0x14003ef06  xor     rax, rsp
0x14003ef09  mov     [rsp+88h+var_28], rax
0x14003ef0e  mov     rdi, rcx
0x14003ef11  lea     r12, aXpwbemlocatorC; "xpWbemLocator->ConnectServer(xbstrNetwo"...
0x14003ef18  mov     [r11-58h], r12
0x14003ef1c  lea     rax, aComtimeoutMake; "ComTimeout::MakeComCall [%hs]"
0x14003ef23  mov     [r11-60h], rax
0x14003ef27  mov     qword ptr [r11-68h], 0
0x14003ef2f  xor     edx, edx
0x14003ef31  xor     ecx, ecx
0x14003ef33  lea     r9d, [rdx+5]
0x14003ef37  mov     r8d, 10000h
0x14003ef3d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003ef42  xorps   xmm0, xmm0
0x14003ef45  movups  [rsp+88h+pv], xmm0
0x14003ef4a  mov     qword ptr [rsp+88h+pv], 0
0x14003ef53  mov     word ptr [rsp+88h+pv+0Ch], 0
0x14003ef5a  lea     rcx, [rsp+88h+pv]; pv
0x14003ef5f  call    ?SetTimer@ComTimeout@WUComTimeout@@QEAAJK@Z; WUComTimeout::ComTimeout::SetTimer(ulong)
0x14003ef64  mov     ebx, eax
0x14003ef66  test    eax, eax
0x14003ef68  jns     short loc_14003EF8B
0x14003ef6a  mov     rcx, [rsp+88h]; this
0x14003ef72  mov     r9d, eax; char *
0x14003ef75  lea     r8, aCW1SSrcClientI; "C:\\__w\\1\\s\\src\\Client\\inc\\ComTim"...
0x14003ef7c  mov     edx, 2Eh ; '.'; void *
0x14003ef81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003ef86  jmp     loc_14003F0A1
0x14003ef8b  mov     rax, [rdi]
0x14003ef8e  mov     rsi, [rax]
0x14003ef91  mov     rax, [rsi]
0x14003ef94  mov     rbp, [rax+18h]
0x14003ef98  mov     rbx, [rdi+10h]
0x14003ef9c  mov     rcx, [rbx]
0x14003ef9f  test    rcx, rcx
0x14003efa2  jz      short loc_14003EFB7
0x14003efa4  mov     rax, [rcx]
0x14003efa7  mov     rax, [rax+10h]
0x14003efab  call    _guard_dispatch_icall
0x14003efb0  mov     qword ptr [rbx], 0
0x14003efb7  mov     rdx, [rdi+8]
0x14003efbb  mov     [rsp+88h+var_48], rbx
0x14003efc0  mov     [rsp+88h+var_50], 0
0x14003efc9  mov     [rsp+88h+var_58], 0
0x14003efd2  mov     dword ptr [rsp+88h+var_60], 0
0x14003efda  mov     [rsp+88h+var_68], 0
0x14003efe3  xor     r9d, r9d
0x14003efe6  xor     r8d, r8d
0x14003efe9  mov     rdx, [rdx]
0x14003efec  mov     rcx, rsi
0x14003efef  mov     rax, rbp
0x14003eff2  call    _guard_dispatch_icall
0x14003eff7  mov     ebx, eax
0x14003eff9  test    eax, eax
0x14003effb  jns     loc_14003F0A1
0x14003f001  cmp     byte ptr [rsp+88h+pv+0Dh], 0
0x14003f006  jz      loc_14003F0A1
0x14003f00c  lea     rax, aComCallTimedOu; "COM call timed out"
0x14003f013  mov     [rsp+88h+var_50], rax
0x14003f018  lea     rax, aFalse; "false"
0x14003f01f  mov     [rsp+88h+var_58], rax
0x14003f024  lea     rax, aTelemetryasser; "TelemetryAssert (%ws): %ws"
0x14003f02b  mov     [rsp+88h+var_60], rax
0x14003f030  mov     [rsp+88h+var_68], 0
0x14003f039  mov     edx, 34h ; '4'
0x14003f03e  lea     r9d, [rdx-31h]
0x14003f042  lea     r8d, [rdx-14h]
0x14003f046  lea     rcx, aWucomtimeoutCo; "WUComTimeout::ComTimeout::MakeComCall"
0x14003f04d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003f052  or      ecx, 0FFFFFFFFh; unsigned int
0x14003f055  mov     edx, ecx; unsigned int
0x14003f057  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x14003f05c  mov     [rsp+88h+var_40], 0Fh
0x14003f064  mov     dword ptr [rsp+88h+var_48], 0F4h
0x14003f06c  lea     rax, aWbemutilGetcom; "WBemUtil::GetComputerInfoFromWMI"
0x14003f073  mov     [rsp+88h+var_50], rax
0x14003f078  mov     [rsp+88h+var_58], r12
0x14003f07d  lea     rax, aComCallHsFromH; "COM call [%hs, from %hs:%u] timed out a"...
0x14003f084  mov     [rsp+88h+var_60], rax
0x14003f089  mov     dword ptr [rsp+88h+var_68], ebx
0x14003f08d  xor     edx, edx
0x14003f08f  xor     ecx, ecx
0x14003f091  lea     r9d, [rdx+1]
0x14003f095  mov     r8d, 10000h
0x14003f09b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003f0a0  nop
0x14003f0a1  lea     rcx, [rsp+88h+pv]; this
0x14003f0a6  call    ??1ComTimeout@WUComTimeout@@QEAA@XZ; WUComTimeout::ComTimeout::~ComTimeout(void)
0x14003f0ab  mov     eax, ebx
0x14003f0ad  mov     rcx, [rsp+88h+var_28]
0x14003f0b2  xor     rcx, rsp; StackCookie
0x14003f0b5  call    __security_check_cookie
0x14003f0ba  lea     r11, [rsp+88h+var_18]
0x14003f0bf  mov     rbx, [r11+28h]
0x14003f0c3  mov     rbp, [r11+30h]
0x14003f0c7  mov     rsp, r11
0x14003f0ca  pop     r12
0x14003f0cc  pop     rdi
0x14003f0cd  pop     rsi
0x14003f0ce  retn
```
