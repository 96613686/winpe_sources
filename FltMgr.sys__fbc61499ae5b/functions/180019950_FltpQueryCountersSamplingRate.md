# FltpQueryCountersSamplingRate

- ea: `0x180019950`
- end: `0x180019bcc`
- name: `FltpQueryCountersSamplingRate`
- size: `636`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180069c90`

## callees

- `0x180009f20`
- `0x180019950`
- `0x180024800`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180019b49`
- `ntoskrnl!ExFreePoolWithTag` at `0x180026392`
- `ntoskrnl!ExFreePoolWithTag` at `0x180019b49`
- `ntoskrnl!ExFreePoolWithTag` at `0x180026392`
- `ntoskrnl!ExAllocatePool2` at `0x180019a24`
- `ntoskrnl!ExAllocatePool2` at `0x1800263b1`
- `ntoskrnl!ExAllocatePool2` at `0x180019a24`
- `ntoskrnl!ExAllocatePool2` at `0x1800263b1`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180019a68`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180019a68`
- `ntoskrnl!RtlInitUnicodeString` at `0x180019adf`
- `ntoskrnl!RtlInitUnicodeString` at `0x180019adf`
- `ntoskrnl!ZwClose` at `0x180019b77`
- `ntoskrnl!ZwClose` at `0x180019b77`
- `ntoskrnl!ZwOpenKey` at `0x180019aab`
- `ntoskrnl!ZwOpenKey` at `0x180019aab`
- `ntoskrnl!ZwQueryValueKey` at `0x180019b12`
- `ntoskrnl!ZwQueryValueKey` at `0x180019b12`

## string_xrefs

- `0x1800199b0`: `\Registry\Machine\System\CurrentControlSet\Services\FltMgr\OneSettings\`

## pseudocode

```c
__int64 FltpQueryCountersSamplingRate()
{
  ULONG Length; // r14d
  unsigned int v1; // esi
  _DWORD *Pool2; // rbx
  NTSTATUS v3; // edi
  __int64 result; // rax
  ULONG ResultLength[2]; // [rsp+38h] [rbp-D0h] BYREF
  void *Destination; // [rsp+40h] [rbp-C8h] BYREF
  UNICODE_STRING Destination_8; // [rsp+48h] [rbp-C0h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes_8; // [rsp+58h] [rbp-B0h] BYREF
  UNICODE_STRING DestinationString; // [rsp+88h] [rbp-80h] BYREF
  WCHAR Source[72]; // [rsp+98h] [rbp-70h] BYREF
  char v11; // [rsp+128h] [rbp+20h] BYREF

  Length = 80;
  DestinationString = 0;
  memset(&ObjectAttributes_8, 0, 44);
  v1 = 1;
  wcscpy(Source, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\FltMgr\\OneSettings\\");
  Destination_8 = 0;
  Destination = 0;
  ResultLength[0] = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(256, 80, 1920224582);
  if ( Pool2 )
  {
    *(_QWORD *)&Destination_8.Length = 20971520;
    Destination_8.Buffer = (wchar_t *)&v11;
    RtlAppendUnicodeToString(&Destination_8, Source);
    ObjectAttributes_8.Length = 48;
    ObjectAttributes_8.ObjectName = &Destination_8;
    ObjectAttributes_8.RootDirectory = 0;
    ObjectAttributes_8.Attributes = 576;
    *(_OWORD *)&ObjectAttributes_8.SecurityDescriptor = 0;
    v3 = ZwOpenKey(&Destination, 0x20019u, &ObjectAttributes_8);
    if ( (int)FltpDbgStatus((unsigned int)v3, "minkernel\\fs\\filtermgr\\filter\\fltioperf.c", 904, 0) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"CountersSampling");
      while ( 1 )
      {
        v3 = ZwQueryValueKey(Destination, &DestinationString, KeyValuePartialInformation, Pool2, Length, ResultLength);
        if ( (int)FltpDbgStatus((unsigned int)v3, "minkernel\\fs\\filtermgr\\filter\\fltioperf.c", 925, 0) >= 0 )
          break;
        if ( v3 != -1073741789 && v3 != -2147483643 )
          goto LABEL_7;
        ExFreePoolWithTag(Pool2, 0x72744D46u);
        Length = ResultLength[0];
        Pool2 = (_DWORD *)ExAllocatePool2(256, ResultLength[0], 1920224582);
        if ( !Pool2 )
        {
          v3 = -1073741670;
          goto LABEL_8;
        }
      }
      if ( Pool2[1] == 4 )
        v1 = Pool2[3];
    }
LABEL_7:
    ExFreePoolWithTag(Pool2, 0x72744D46u);
  }
  else
  {
    v3 = -1073741670;
  }
LABEL_8:
  if ( Destination )
    ZwClose(Destination);
  result = 1000;
  if ( v3 >= 0 )
    return v1;
  return result;
}

```

## disassembly

```asm
0x180019950  mov     r11, rsp
0x180019953  push    rbp
0x180019954  push    rsi
0x180019955  push    rdi
0x180019956  lea     rbp, [r11-188h]
0x18001995d  sub     rsp, 270h
0x180019964  mov     rax, cs:__security_cookie
0x18001996b  xor     rax, rsp
0x18001996e  mov     [rbp+180h+var_20], rax
0x180019975  xorps   xmm0, xmm0
0x180019978  mov     [r11+8], rbx
0x18001997c  movups  xmmword ptr [rsp+280h+ObjectAttributes+18h], xmm0
0x180019981  mov     [r11+10h], r14
0x180019985  xor     edi, edi
0x180019987  movups  xmmword ptr [rsp+280h+ObjectAttributes+24h], xmm0
0x18001998c  mov     r14d, 50h ; 'P'
0x180019992  xor     eax, eax
0x180019994  movups  xmmword ptr [rbp+180h+DestinationString.Length], xmm0
0x180019998  mov     r8d, 72744D46h
0x18001999e  mov     edx, r14d
0x1800199a1  movups  xmmword ptr [rsp+280h+ObjectAttributes+8], xmm0
0x1800199a6  mov     ecx, 100h
0x1800199ab  mov     esi, 1
0x1800199b0  movaps  xmm0, xmmword ptr cs:aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800199b7  xorps   xmm1, xmm1
0x1800199ba  movaps  xmmword ptr [rbp+180h+Source], xmm0
0x1800199be  movaps  xmm0, xmmword ptr cs:aRegistryMachin_0+20h; "e\\System\\CurrentControlSet\\Services"...
0x1800199c5  movups  xmmword ptr [rsp+280h+Destination.Buffer], xmm1
0x1800199ca  mov     qword ptr [rsp+280h+Destination.Length], rdi
0x1800199cf  movaps  xmm1, xmmword ptr cs:aRegistryMachin_0+10h; "y\\Machine\\System\\CurrentControlSet\\"...
0x1800199d6  movaps  [rbp+180h+var_1D0], xmm0
0x1800199da  movaps  xmm0, xmmword ptr cs:aRegistryMachin_0+40h; "ControlSet\\Services\\FltMgr\\OneSettin"...
0x1800199e1  movaps  [rbp+180h+var_1E0], xmm1
0x1800199e5  movaps  xmm1, xmmword ptr cs:aRegistryMachin_0+30h; "\\CurrentControlSet\\Services\\FltMgr\\"...
0x1800199ec  movaps  [rbp+180h+var_1B0], xmm0
0x1800199f0  movaps  xmm0, xmmword ptr cs:aRegistryMachin_0+60h; "ces\\FltMgr\\OneSettings\\"
0x1800199f7  movaps  [rbp+180h+var_1C0], xmm1
0x1800199fb  movaps  xmm1, xmmword ptr cs:aRegistryMachin_0+50h; "et\\Services\\FltMgr\\OneSettings\\"
0x180019a02  movaps  [rbp+180h+var_190], xmm0
0x180019a06  movaps  xmm0, xmmword ptr cs:aRegistryMachin_0+80h; "ttings\\"
0x180019a0d  movaps  [rbp+180h+var_1A0], xmm1
0x180019a11  movaps  xmm1, xmmword ptr cs:aRegistryMachin_0+70h; "gr\\OneSettings\\"
0x180019a18  movaps  [rbp+180h+var_170], xmm0
0x180019a1c  mov     [rsp+280h+var_250], edi
0x180019a20  movaps  [rbp+180h+var_180], xmm1
0x180019a24  call    cs:__imp_ExAllocatePool2
0x180019a2b  nop     dword ptr [rax+rax+00h]
0x180019a30  mov     rbx, rax
0x180019a33  test    rax, rax
0x180019a36  jz      loc_180019BA8
0x180019a3c  xorps   xmm0, xmm0
0x180019a3f  mov     [rsp+280h+arg_10], r15
0x180019a47  movups  xmmword ptr [rsp+280h+Destination.Buffer], xmm0
0x180019a4c  mov     eax, 140h
0x180019a51  lea     rdx, [rbp+180h+Source]; Source
0x180019a55  mov     word ptr [rsp+280h+Destination.Buffer+2], ax
0x180019a5a  lea     rcx, [rsp+280h+Destination.Buffer]; Destination
0x180019a5f  lea     rax, [rbp+180h+var_160]
0x180019a63  mov     qword ptr [rsp+280h+ObjectAttributes], rax
0x180019a68  call    cs:__imp_RtlAppendUnicodeToString
0x180019a6f  nop     dword ptr [rax+rax+00h]
0x180019a74  lea     rax, [rsp+280h+Destination.Buffer]
0x180019a79  mov     dword ptr [rsp+280h+ObjectAttributes+8], 30h ; '0'
0x180019a81  xorps   xmm0, xmm0
0x180019a84  mov     qword ptr [rsp+280h+ObjectAttributes+18h], rax
0x180019a89  lea     r8, [rsp+280h+ObjectAttributes+8]; ObjectAttributes
0x180019a8e  mov     qword ptr [rsp+280h+ObjectAttributes+10h], rdi
0x180019a93  mov     edx, 20019h; DesiredAccess
0x180019a98  mov     dword ptr [rsp+280h+ObjectAttributes+20h], 240h
0x180019aa0  lea     rcx, [rsp+280h+Destination]; KeyHandle
0x180019aa5  movdqu  xmmword ptr [rsp+280h+ObjectAttributes+28h], xmm0
0x180019aab  call    cs:__imp_ZwOpenKey
0x180019ab2  nop     dword ptr [rax+rax+00h]
0x180019ab7  mov     r8d, 388h
0x180019abd  lea     rdx, aMinkernelFsFil_8; "minkernel\\fs\\filtermgr\\filter\\fltio"...
0x180019ac4  mov     ecx, eax
0x180019ac6  xor     r9d, r9d
0x180019ac9  mov     edi, eax
0x180019acb  call    FltpDbgStatus
0x180019ad0  test    eax, eax
0x180019ad2  js      short loc_180019B41
0x180019ad4  lea     rdx, SourceString; "CountersSampling"
0x180019adb  lea     rcx, [rbp+180h+DestinationString]; DestinationString
0x180019adf  call    cs:__imp_RtlInitUnicodeString
0x180019ae6  nop     dword ptr [rax+rax+00h]
0x180019aeb  mov     r15d, 39Dh
0x180019af1  mov     rcx, qword ptr [rsp+280h+Destination.Length]; KeyHandle
0x180019af6  lea     rax, [rsp+280h+var_250]
0x180019afb  mov     [rsp+280h+ResultLength], rax; ResultLength
0x180019b00  lea     rdx, [rbp+180h+DestinationString]; ValueName
0x180019b04  mov     r9, rbx; KeyValueInformation
0x180019b07  mov     [rsp+280h+Length], r14d; Length
0x180019b0c  mov     r8d, 2; KeyValueInformationClass
0x180019b12  call    cs:__imp_ZwQueryValueKey
0x180019b19  nop     dword ptr [rax+rax+00h]
0x180019b1e  xor     r9d, r9d
0x180019b21  lea     rdx, aMinkernelFsFil_8; "minkernel\\fs\\filtermgr\\filter\\fltio"...
0x180019b28  mov     ecx, eax
0x180019b2a  mov     r8d, r15d
0x180019b2d  mov     edi, eax
0x180019b2f  call    FltpDbgStatus
0x180019b34  test    eax, eax
0x180019b36  js      short loc_180019BAF
0x180019b38  cmp     dword ptr [rbx+4], 4
0x180019b3c  jnz     short loc_180019B41
0x180019b3e  mov     esi, [rbx+0Ch]
0x180019b41  mov     edx, 72744D46h; Tag
0x180019b46  mov     rcx, rbx; P
0x180019b49  call    cs:__imp_ExFreePoolWithTag
0x180019b50  nop     dword ptr [rax+rax+00h]
0x180019b55  mov     r15, [rsp+280h+arg_10]
0x180019b5d  mov     rcx, qword ptr [rsp+280h+Destination.Length]; Handle
0x180019b62  mov     r14, [rsp+280h+arg_8]
0x180019b6a  mov     rbx, [rsp+280h+arg_0]
0x180019b72  test    rcx, rcx
0x180019b75  jz      short loc_180019B83
0x180019b77  call    cs:__imp_ZwClose
0x180019b7e  nop     dword ptr [rax+rax+00h]
0x180019b83  test    edi, edi
0x180019b85  mov     eax, 3E8h
0x180019b8a  cmovns  eax, esi
0x180019b8d  mov     rcx, [rbp+180h+var_20]
0x180019b94  xor     rcx, rsp; StackCookie
0x180019b97  call    __security_check_cookie
0x180019b9c  add     rsp, 270h
0x180019ba3  pop     rdi
0x180019ba4  pop     rsi
0x180019ba5  pop     rbp
0x180019ba6  retn
0x180019ba8  mov     edi, 0C000009Ah
0x180019bad  jmp     short loc_180019B5D
0x180019baf  cmp     edi, 0C0000023h
0x180019bb5  jz      loc_18002638A
0x180019bbb  cmp     edi, 80000005h
0x180019bc1  jnz     loc_180019B41
0x180019bc7  jmp     loc_18002638A
0x18002638a  mov     edx, 72744D46h; Tag
0x18002638f  mov     rcx, rbx; P
0x180026392  call    cs:__imp_ExFreePoolWithTag
0x180026399  nop     dword ptr [rax+rax+00h]
0x18002639e  mov     r14d, [rsp+280h+var_250]
0x1800263a3  mov     ecx, 100h
0x1800263a8  mov     edx, r14d
0x1800263ab  mov     r8d, 72744D46h
0x1800263b1  call    cs:__imp_ExAllocatePool2
0x1800263b8  nop     dword ptr [rax+rax+00h]
0x1800263bd  mov     rbx, rax
0x1800263c0  test    rax, rax
0x1800263c3  jnz     loc_180019AF1
0x1800263c9  mov     edi, 0C000009Ah
0x1800263ce  jmp     loc_180019B55
```
