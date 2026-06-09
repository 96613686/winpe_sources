# WdfIoQueueFindAndCompleteStatusIoctlRequest

- ea: `0x14000aac0`
- end: `0x14000ae27`
- name: `WdfIoQueueFindAndCompleteStatusIoctlRequest`
- size: `871`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400069f8`
- `0x140007768`
- `0x14000f700`
- `0x14002b22c`

## callees

- `0x140004810`
- `0x14000498c`
- `0x14000aac0`
- `0x14000ae30`
- `0x14001ae00`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000ab72`
- `ntoskrnl!RtlCompareMemory` at `0x14000ab72`

## pseudocode

```c
__int64 __fastcall WdfIoQueueFindAndCompleteStatusIoctlRequest(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _DWORD *a4,
        _DWORD *Source2,
        __int64 a6)
{
  unsigned int v7; // ebx
  __int64 v8; // rdi
  int v10; // edx
  int v11; // r8d
  int IoctlRequest; // eax
  int v13; // edx
  int v14; // r8d
  unsigned int v15; // ebx
  int v17; // eax
  int v18; // edx
  int v19; // r8d
  _DWORD *v20; // [rsp+50h] [rbp-58h] BYREF

  a6 = 0;
  v7 = a3;
  v20 = 0;
  v8 = a2;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
    || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
  {
    LOBYTE(a2) = 0;
  }
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      1,
      10,
      (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids,
      v7);
  }
  if ( RtlCompareMemory(a4, Source2, 4u) == 4 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    {
      LOBYTE(v10) = 0;
    }
    if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
        WPP_GLOBAL_Control->AttachedDevice,
        v10,
        v11,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        1,
        11,
        (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids,
        v7);
    }
    return 0;
  }
  IoctlRequest = WdfIoQueueFindIoctlRequest(a1, v8, v7, &a6);
  v15 = IoctlRequest;
  if ( IoctlRequest < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || (LOBYTE(v13) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    {
      LOBYTE(v13) = 0;
    }
    if ( (_BYTE)v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
        WPP_GLOBAL_Control->AttachedDevice,
        v13,
        v14,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        1,
        12,
        (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids,
        IoctlRequest);
    }
    return v15;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
    || (LOBYTE(v13) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
  {
    LOBYTE(v13) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (LOBYTE(v14) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v14) = 0;
  }
  if ( (_BYTE)v13 || (_BYTE)v14 )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v13,
      v14,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      13,
      (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids,
      a6);
  v17 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _DWORD **, _QWORD))(WdfFunctions_01015 + 2160))(
          WdfDriverGlobals,
          a6,
          4,
          &v20,
          0);
  v15 = v17;
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || (LOBYTE(v18) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    {
      LOBYTE(v18) = 0;
    }
    if ( (_BYTE)v18 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
        WPP_GLOBAL_Control->AttachedDevice,
        v18,
        v19,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        1,
        14,
        (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids,
        v17);
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
      WdfDriverGlobals,
      a6,
      v15);
    return v15;
  }
  *Source2 = *a4;
  *v20 = *a4;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64))(WdfFunctions_01015 + 2120))(
    WdfDriverGlobals,
    a6,
    0,
    4);
  return 0;
}

```

## disassembly

```asm
0x14000aac0  mov     rax, rsp
0x14000aac3  push    rbx
0x14000aac4  push    rbp
0x14000aac5  push    rsi
0x14000aac6  push    rdi
0x14000aac7  push    r12
0x14000aac9  push    r13
0x14000aacb  push    r14
0x14000aacd  push    r15
0x14000aacf  sub     rsp, 68h
0x14000aad3  xor     ebp, ebp
0x14000aad5  mov     r14, r9
0x14000aad8  mov     [rax+30h], rbp
0x14000aadc  mov     ebx, r8d
0x14000aadf  mov     [rax-58h], rbp
0x14000aae3  mov     rdi, rdx
0x14000aae6  mov     rsi, rcx
0x14000aae9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aaf0  lea     rax, WPP_GLOBAL_Control
0x14000aaf7  lea     r13d, [rbp+4]
0x14000aafb  lea     r12d, [rbp+1]
0x14000aaff  cmp     rcx, rax
0x14000ab02  jz      short loc_14000AB15
0x14000ab04  mov     eax, [rcx+2Ch]
0x14000ab07  test    r12b, al
0x14000ab0a  jz      short loc_14000AB15
0x14000ab0c  mov     dl, r12b
0x14000ab0f  cmp     [rcx+29h], r13b
0x14000ab13  jnb     short loc_14000AB18
0x14000ab15  mov     dl, bpl
0x14000ab18  lea     rax, WPP_RECORDER_INITIALIZED
0x14000ab1f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ab26  lea     r9, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x14000ab2d  setnz   r8b
0x14000ab31  test    dl, dl
0x14000ab33  jnz     short loc_14000AB3A
0x14000ab35  test    r8b, r8b
0x14000ab38  jz      short loc_14000AB61
0x14000ab3a  mov     dword ptr [rsp+0A8h+var_68], ebx
0x14000ab3e  mov     [rsp+0A8h+var_70], r9
0x14000ab43  mov     r9, [rcx+40h]
0x14000ab47  mov     rcx, [rcx+18h]
0x14000ab4b  mov     [rsp+0A8h+var_78], 0Ah
0x14000ab52  mov     [rsp+0A8h+var_80], r12d
0x14000ab57  mov     byte ptr [rsp+0A8h+var_88], r13b
0x14000ab5c  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x14000ab61  mov     r15, [rsp+0A8h+Source2]
0x14000ab69  mov     r8, r13; Length
0x14000ab6c  mov     rdx, r15; Source2
0x14000ab6f  mov     rcx, r14; Source1
0x14000ab72  call    cs:__imp_RtlCompareMemory
0x14000ab79  nop     dword ptr [rax+rax+00h]
0x14000ab7e  cmp     rax, r13
0x14000ab81  jnz     short loc_14000ABFC
0x14000ab83  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ab8a  lea     rdi, WPP_GLOBAL_Control
0x14000ab91  cmp     rcx, rdi
0x14000ab94  jz      short loc_14000ABA7
0x14000ab96  mov     eax, [rcx+2Ch]
0x14000ab99  test    r12b, al
0x14000ab9c  jz      short loc_14000ABA7
0x14000ab9e  mov     dl, r12b
0x14000aba1  cmp     [rcx+29h], r13b
0x14000aba5  jnb     short loc_14000ABAA
0x14000aba7  mov     dl, bpl
0x14000abaa  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000abb1  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000abb8  setnz   r8b
0x14000abbc  test    dl, dl
0x14000abbe  jnz     short loc_14000ABC9
0x14000abc0  test    r8b, r8b
0x14000abc3  jz      loc_14000AE13
0x14000abc9  mov     dword ptr [rsp+0A8h+var_68], ebx
0x14000abcd  lea     r9, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x14000abd4  mov     [rsp+0A8h+var_70], r9
0x14000abd9  mov     r9, [rcx+40h]
0x14000abdd  mov     rcx, [rcx+18h]
0x14000abe1  mov     [rsp+0A8h+var_78], 0Bh
0x14000abe8  mov     [rsp+0A8h+var_80], r12d
0x14000abed  mov     byte ptr [rsp+0A8h+var_88], r13b
0x14000abf2  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x14000abf7  jmp     loc_14000AE13
0x14000abfc  lea     r9, [rsp+0A8h+arg_28]
0x14000ac04  mov     r8d, ebx
0x14000ac07  mov     rdx, rdi
0x14000ac0a  mov     rcx, rsi
0x14000ac0d  call    WdfIoQueueFindIoctlRequest
0x14000ac12  mov     ebx, eax
0x14000ac14  test    eax, eax
0x14000ac16  jns     short loc_14000AC91
0x14000ac18  mov     r10, cs:WPP_GLOBAL_Control
0x14000ac1f  lea     rdi, WPP_GLOBAL_Control
0x14000ac26  cmp     r10, rdi
0x14000ac29  jz      short loc_14000AC3E
0x14000ac2b  mov     ecx, [r10+2Ch]
0x14000ac2f  test    r12b, cl
0x14000ac32  jz      short loc_14000AC3E
0x14000ac34  cmp     byte ptr [r10+29h], 2
0x14000ac39  mov     dl, r12b
0x14000ac3c  jnb     short loc_14000AC41
0x14000ac3e  mov     dl, bpl
0x14000ac41  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000ac48  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000ac4f  setnz   r8b
0x14000ac53  test    dl, dl
0x14000ac55  jnz     short loc_14000AC5C
0x14000ac57  test    r8b, r8b
0x14000ac5a  jz      short loc_14000AC8A
0x14000ac5c  mov     rcx, [r10+18h]
0x14000ac60  lea     r9, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x14000ac67  mov     dword ptr [rsp+0A8h+var_68], ebx
0x14000ac6b  mov     [rsp+0A8h+var_70], r9
0x14000ac70  mov     r9, [r10+40h]
0x14000ac74  mov     [rsp+0A8h+var_78], 0Ch
0x14000ac7b  mov     [rsp+0A8h+var_80], r12d
0x14000ac80  mov     byte ptr [rsp+0A8h+var_88], 2
0x14000ac85  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x14000ac8a  mov     eax, ebx
0x14000ac8c  jmp     loc_14000AE15
0x14000ac91  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ac98  lea     rdi, WPP_GLOBAL_Control
0x14000ac9f  cmp     rcx, rdi
0x14000aca2  jz      short loc_14000ACB5
0x14000aca4  mov     eax, [rcx+2Ch]
0x14000aca7  test    r12b, al
0x14000acaa  jz      short loc_14000ACB5
0x14000acac  cmp     byte ptr [rcx+29h], 5
0x14000acb0  mov     dl, r12b
0x14000acb3  jnb     short loc_14000ACB8
0x14000acb5  mov     dl, bpl
0x14000acb8  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000acbf  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000acc6  jz      short loc_14000ACD1
0x14000acc8  mov     r8b, r12b
0x14000accb  cmp     [rcx+48h], bp
0x14000accf  jnz     short loc_14000ACD4
0x14000acd1  mov     r8b, bpl
0x14000acd4  test    dl, dl
0x14000acd6  jnz     short loc_14000ACDD
0x14000acd8  test    r8b, r8b
0x14000acdb  jz      short loc_14000AD14
0x14000acdd  mov     rax, [rsp+0A8h+arg_28]
0x14000ace5  mov     r9, [rcx+40h]
0x14000ace9  mov     rcx, [rcx+18h]
0x14000aced  mov     [rsp+0A8h+var_68], rax
0x14000acf2  lea     rax, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x14000acf9  mov     [rsp+0A8h+var_70], rax
0x14000acfe  mov     [rsp+0A8h+var_78], 0Dh
0x14000ad05  mov     [rsp+0A8h+var_80], r12d
0x14000ad0a  mov     byte ptr [rsp+0A8h+var_88], 5
0x14000ad0f  call    WPP_RECORDER_AND_TRACE_SF_q
0x14000ad14  mov     rax, cs:WdfFunctions_01015
0x14000ad1b  lea     r9, [rsp+0A8h+var_58]
0x14000ad20  mov     rdx, [rsp+0A8h+arg_28]
0x14000ad28  mov     r8, r13
0x14000ad2b  mov     rcx, cs:WdfDriverGlobals
0x14000ad32  mov     [rsp+0A8h+var_88], rbp
0x14000ad37  mov     rax, [rax+870h]
0x14000ad3e  call    _guard_dispatch_icall
0x14000ad43  mov     ebx, eax
0x14000ad45  test    eax, eax
0x14000ad47  jns     loc_14000ADDB
0x14000ad4d  mov     r10, cs:WPP_GLOBAL_Control
0x14000ad54  cmp     r10, rdi
0x14000ad57  jz      short loc_14000AD6C
0x14000ad59  mov     ecx, [r10+2Ch]
0x14000ad5d  test    r12b, cl
0x14000ad60  jz      short loc_14000AD6C
0x14000ad62  cmp     byte ptr [r10+29h], 2
0x14000ad67  mov     dl, r12b
0x14000ad6a  jnb     short loc_14000AD6F
0x14000ad6c  mov     dl, bpl
0x14000ad6f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000ad76  setnz   r8b
0x14000ad7a  test    dl, dl
0x14000ad7c  jnz     short loc_14000AD83
0x14000ad7e  test    r8b, r8b
0x14000ad81  jz      short loc_14000ADB1
0x14000ad83  mov     rcx, [r10+18h]
0x14000ad87  lea     r9, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x14000ad8e  mov     dword ptr [rsp+0A8h+var_68], ebx
0x14000ad92  mov     [rsp+0A8h+var_70], r9
0x14000ad97  mov     r9, [r10+40h]
0x14000ad9b  mov     [rsp+0A8h+var_78], 0Eh
0x14000ada2  mov     [rsp+0A8h+var_80], r12d
0x14000ada7  mov     byte ptr [rsp+0A8h+var_88], 2
0x14000adac  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x14000adb1  mov     rax, cs:WdfFunctions_01015
0x14000adb8  mov     r8d, ebx
0x14000adbb  mov     rdx, [rsp+0A8h+arg_28]
0x14000adc3  mov     rcx, cs:WdfDriverGlobals
0x14000adca  mov     rax, [rax+838h]
0x14000add1  call    _guard_dispatch_icall
0x14000add6  jmp     loc_14000AC8A
0x14000addb  mov     eax, [r14]
0x14000adde  mov     r9, r13
0x14000ade1  mov     [r15], eax
0x14000ade4  xor     r8d, r8d
0x14000ade7  mov     rax, [rsp+0A8h+var_58]
0x14000adec  mov     ecx, [r14]
0x14000adef  mov     [rax], ecx
0x14000adf1  mov     rax, cs:WdfFunctions_01015
0x14000adf8  mov     rdx, [rsp+0A8h+arg_28]
0x14000ae00  mov     rcx, cs:WdfDriverGlobals
0x14000ae07  mov     rax, [rax+848h]
0x14000ae0e  call    _guard_dispatch_icall
0x14000ae13  xor     eax, eax
0x14000ae15  add     rsp, 68h
0x14000ae19  pop     r15
0x14000ae1b  pop     r14
0x14000ae1d  pop     r13
0x14000ae1f  pop     r12
0x14000ae21  pop     rdi
0x14000ae22  pop     rsi
0x14000ae23  pop     rbp
0x14000ae24  pop     rbx
0x14000ae25  retn
```
