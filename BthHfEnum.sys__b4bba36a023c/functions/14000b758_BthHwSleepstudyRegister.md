# BthHwSleepstudyRegister

- ea: `0x14000b758`
- end: `0x14000b958`
- name: `BthHwSleepstudyRegister`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002b5a0`

## callees

- `0x140005af8`
- `0x14000b758`
- `0x14001adc0`
- `0x14001ae00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000b7c4`
- `ntoskrnl!ExAllocatePool2` at `0x14000b7dd`
- `ntoskrnl!ExAllocatePool2` at `0x14000b7c4`
- `ntoskrnl!ExAllocatePool2` at `0x14000b7dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b910`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b929`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b910`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b929`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_RegisterComponentEx` at `0x14000b8ee`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_RegisterComponentEx` at `0x14000b8ee`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x14000b8a8`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GenerateGuid` at `0x14000b8a8`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GetPdoFriendlyName` at `0x14000b84e`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_GetPdoFriendlyName` at `0x14000b84e`

## pseudocode

```c
__int64 __fastcall BthHwSleepstudyRegister(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // r15
  void *Pool2; // rsi
  WCHAR *v5; // rax
  WCHAR *v6; // rdi
  NTSTATUS PdoFriendlyName; // ebx
  __int64 v8; // rax
  __int64 v9; // rax
  _QWORD v11[2]; // [rsp+30h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-39h] BYREF
  __int128 v13; // [rsp+50h] [rbp-29h] BYREF
  GUID v14; // [rsp+60h] [rbp-19h] BYREF
  __int128 v15; // [rsp+70h] [rbp-9h] BYREF

  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400220B0);
  v15 = 0;
  v3 = v2;
  Pool2 = (void *)ExAllocatePool2(64, 256, 1179145282);
  v5 = (WCHAR *)ExAllocatePool2(64, 512, 1179145282);
  v11[0] = 0x1000000;
  v6 = v5;
  DestinationString.Buffer = v5;
  v11[1] = Pool2;
  *(_QWORD *)&DestinationString.Length = 0x2000000;
  if ( Pool2 && v5 )
  {
    if ( qword_140022628 )
    {
      v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 264))(WdfDriverGlobals, a1);
      PdoFriendlyName = SleepstudyHelper_GetPdoFriendlyName(v8, v11);
      if ( PdoFriendlyName >= 0 )
      {
        PdoFriendlyName = RtlUnicodeStringPrintf(&DestinationString, L"%wZ (HFP Hands Free)", v11);
        if ( PdoFriendlyName >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 264))(
                 WdfDriverGlobals,
                 a1);
          PdoFriendlyName = SleepstudyHelper_GenerateGuid(0, v9, &v15);
          if ( PdoFriendlyName >= 0 )
          {
            v13 = v15;
            v14 = GUID_SLEEPSTUDY_BLUETOOTH_CONTROLLER_FDO;
            PdoFriendlyName = SleepstudyHelper_RegisterComponentEx(
                                qword_140022628,
                                &v14,
                                &v13,
                                &DestinationString,
                                v3 + 408);
          }
        }
      }
    }
    else
    {
      PdoFriendlyName = -1073741811;
    }
  }
  else
  {
    PdoFriendlyName = -1073741670;
    if ( !Pool2 )
      goto LABEL_11;
  }
  ExFreePoolWithTag(Pool2, 0x46485442u);
LABEL_11:
  if ( v6 )
    ExFreePoolWithTag(v6, 0x46485442u);
  return (unsigned int)PdoFriendlyName;
}

```

## disassembly

```asm
0x14000b758  push    rbp
0x14000b75a  push    rbx
0x14000b75b  push    rsi
0x14000b75c  push    rdi
0x14000b75d  push    r12
0x14000b75f  push    r13
0x14000b761  push    r14
0x14000b763  push    r15
0x14000b765  lea     rbp, [rsp-1Fh]
0x14000b76a  sub     rsp, 98h
0x14000b771  mov     rax, cs:__security_cookie
0x14000b778  xor     rax, rsp
0x14000b77b  mov     [rbp+57h+var_50], rax
0x14000b77f  mov     rax, cs:WdfFunctions_01015
0x14000b786  mov     r14, rcx
0x14000b789  mov     r8, cs:off_1400220B0
0x14000b790  mov     rdx, rcx
0x14000b793  mov     rcx, cs:WdfDriverGlobals
0x14000b79a  mov     rax, [rax+650h]
0x14000b7a1  call    _guard_dispatch_icall
0x14000b7a6  xorps   xmm0, xmm0
0x14000b7a9  mov     edi, 46485442h
0x14000b7ae  mov     ebx, 40h ; '@'
0x14000b7b3  mov     r8d, edi
0x14000b7b6  mov     ecx, ebx
0x14000b7b8  mov     edx, 100h
0x14000b7bd  movups  [rbp+57h+var_60], xmm0
0x14000b7c1  mov     r15, rax
0x14000b7c4  call    cs:__imp_ExAllocatePool2
0x14000b7cb  nop     dword ptr [rax+rax+00h]
0x14000b7d0  mov     r8d, edi
0x14000b7d3  mov     edx, 200h
0x14000b7d8  mov     ecx, ebx
0x14000b7da  mov     rsi, rax
0x14000b7dd  call    cs:__imp_ExAllocatePool2
0x14000b7e4  nop     dword ptr [rax+rax+00h]
0x14000b7e9  mov     [rbp+57h+var_A0], 1000000h
0x14000b7f1  mov     rdi, rax
0x14000b7f4  mov     [rbp+57h+DestinationString.Buffer], rax
0x14000b7f8  mov     [rbp+57h+var_98], rsi
0x14000b7fc  mov     qword ptr [rbp+57h+DestinationString.Length], 2000000h
0x14000b804  test    rsi, rsi
0x14000b807  jz      loc_14000B8FE
0x14000b80d  test    rax, rax
0x14000b810  jz      loc_14000B8FE
0x14000b816  cmp     cs:qword_140022628, 0
0x14000b81e  jnz     short loc_14000B82A
0x14000b820  mov     ebx, 0C000000Dh
0x14000b825  jmp     loc_14000B908
0x14000b82a  mov     rax, cs:WdfFunctions_01015
0x14000b831  mov     rdx, r14
0x14000b834  mov     rcx, cs:WdfDriverGlobals
0x14000b83b  mov     rax, [rax+108h]
0x14000b842  call    _guard_dispatch_icall
0x14000b847  lea     rdx, [rbp+57h+var_A0]
0x14000b84b  mov     rcx, rax
0x14000b84e  call    cs:__imp_SleepstudyHelper_GetPdoFriendlyName
0x14000b855  nop     dword ptr [rax+rax+00h]
0x14000b85a  mov     ebx, eax
0x14000b85c  test    eax, eax
0x14000b85e  js      loc_14000B908
0x14000b864  lea     r8, [rbp+57h+var_A0]
0x14000b868  lea     rdx, aWzHfpHandsFree; "%wZ (HFP Hands Free)"
0x14000b86f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000b873  call    RtlUnicodeStringPrintf
0x14000b878  mov     ebx, eax
0x14000b87a  test    eax, eax
0x14000b87c  js      loc_14000B908
0x14000b882  mov     rax, cs:WdfFunctions_01015
0x14000b889  mov     rdx, r14
0x14000b88c  mov     rcx, cs:WdfDriverGlobals
0x14000b893  mov     rax, [rax+108h]
0x14000b89a  call    _guard_dispatch_icall
0x14000b89f  lea     r8, [rbp+57h+var_60]
0x14000b8a3  mov     rdx, rax
0x14000b8a6  xor     ecx, ecx
0x14000b8a8  call    cs:__imp_SleepstudyHelper_GenerateGuid
0x14000b8af  nop     dword ptr [rax+rax+00h]
0x14000b8b4  mov     ebx, eax
0x14000b8b6  test    eax, eax
0x14000b8b8  js      short loc_14000B908
0x14000b8ba  movups  xmm1, xmmword ptr cs:GUID_SLEEPSTUDY_BLUETOOTH_CONTROLLER_FDO.Data1
0x14000b8c1  lea     rax, [r15+198h]
0x14000b8c8  mov     rcx, cs:qword_140022628
0x14000b8cf  movaps  xmm0, [rbp+57h+var_60]
0x14000b8d3  lea     r9, [rbp+57h+DestinationString]
0x14000b8d7  lea     r8, [rbp+57h+var_80]
0x14000b8db  movdqa  [rbp+57h+var_80], xmm0
0x14000b8e0  lea     rdx, [rbp+57h+var_70]
0x14000b8e4  mov     [rsp+0D0h+var_B0], rax
0x14000b8e9  movdqu  [rbp+57h+var_70], xmm1
0x14000b8ee  call    cs:__imp_SleepstudyHelper_RegisterComponentEx
0x14000b8f5  nop     dword ptr [rax+rax+00h]
0x14000b8fa  mov     ebx, eax
0x14000b8fc  jmp     short loc_14000B908
0x14000b8fe  mov     ebx, 0C000009Ah
0x14000b903  test    rsi, rsi
0x14000b906  jz      short loc_14000B91C
0x14000b908  mov     edx, 46485442h; Tag
0x14000b90d  mov     rcx, rsi; P
0x14000b910  call    cs:__imp_ExFreePoolWithTag
0x14000b917  nop     dword ptr [rax+rax+00h]
0x14000b91c  test    rdi, rdi
0x14000b91f  jz      short loc_14000B935
0x14000b921  mov     edx, 46485442h; Tag
0x14000b926  mov     rcx, rdi; P
0x14000b929  call    cs:__imp_ExFreePoolWithTag
0x14000b930  nop     dword ptr [rax+rax+00h]
0x14000b935  mov     eax, ebx
0x14000b937  mov     rcx, [rbp+57h+var_50]
0x14000b93b  xor     rcx, rsp; StackCookie
0x14000b93e  call    __security_check_cookie
0x14000b943  add     rsp, 98h
0x14000b94a  pop     r15
0x14000b94c  pop     r14
0x14000b94e  pop     r13
0x14000b950  pop     r12
0x14000b952  pop     rdi
0x14000b953  pop     rsi
0x14000b954  pop     rbx
0x14000b955  pop     rbp
0x14000b956  retn
```
