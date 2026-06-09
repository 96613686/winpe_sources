# Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)

- ea: `0x18000ad58`
- end: `0x18000ae38`
- name: `?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z`
- size: `224`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a5e0`
- `0x18000a7e0`
- `0x18000ae40`

## callees

- `0x18000ad58`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18000ad9c`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18000adb9`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18000ad9c`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18000adb9`
- `api-ms-win-core-winrt-error-l1-1-1!RoGetMatchingRestrictedErrorInfo` at `0x18000addc`
- `api-ms-win-core-winrt-error-l1-1-1!RoGetMatchingRestrictedErrorInfo` at `0x18000addc`
- `api-ms-win-core-winrt-error-l1-1-1!IsErrorPropagationEnabled` at `0x18000ada4`
- `api-ms-win-core-winrt-error-l1-1-1!IsErrorPropagationEnabled` at `0x18000ada4`
- `api-ms-win-core-winrt-error-l1-1-1!RoReportFailedDelegate` at `0x18000adf0`
- `api-ms-win-core-winrt-error-l1-1-1!RoReportFailedDelegate` at `0x18000adf0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
        __int64 a1,
        __int64 a2)
{
  int v3; // ebx
  int MatchingRestrictedErrorInfo; // ecx
  int v5; // eax
  __int64 v6; // rcx
  __int64 v8; // [rsp+58h] [rbp+20h] BYREF

  v3 = a1;
  if ( (_DWORD)a1 == -2147417848
    || (_DWORD)a1 == -2147023174
    || (_DWORD)a1 == -1996357631
    || (_DWORD)a1 == -2147418105
    || (_DWORD)a1 == -2147418094 )
  {
    RoTransformError(a1, 0, 0);
    v3 = 0;
  }
  if ( (unsigned int)IsErrorPropagationEnabled() )
  {
    if ( v3 < 0 )
    {
      v8 = 0;
      MatchingRestrictedErrorInfo = RoGetMatchingRestrictedErrorInfo((unsigned int)v3, &v8);
      if ( MatchingRestrictedErrorInfo >= 0 )
        MatchingRestrictedErrorInfo = RoReportFailedDelegate(a2, v8);
      v5 = 0;
      if ( MatchingRestrictedErrorInfo < 0 )
        v5 = v3;
      v3 = v5;
      v6 = v8;
      if ( v8 )
      {
        v8 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
    }
  }
  else if ( v3 < 0 )
  {
    RoTransformError((unsigned int)v3, 0, 0);
    return 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ad58  mov     [rsp+arg_0], rbx
0x18000ad5d  mov     [rsp+arg_8], rsi
0x18000ad62  push    rdi
0x18000ad63  sub     rsp, 30h
0x18000ad67  mov     rdi, r8
0x18000ad6a  mov     rsi, rdx
0x18000ad6d  mov     ebx, ecx
0x18000ad6f  cmp     ecx, 80010108h
0x18000ad75  jz      short loc_18000AD97
0x18000ad77  cmp     ecx, 800706BAh
0x18000ad7d  jz      short loc_18000AD97
0x18000ad7f  cmp     ecx, 89020001h
0x18000ad85  jz      short loc_18000AD97
0x18000ad87  cmp     ecx, 80010007h
0x18000ad8d  jz      short loc_18000AD97
0x18000ad8f  cmp     ecx, 80010012h
0x18000ad95  jnz     short loc_18000ADA4
0x18000ad97  xor     r8d, r8d
0x18000ad9a  xor     edx, edx
0x18000ad9c  call    cs:__imp_RoTransformError
0x18000ada2  xor     ebx, ebx
0x18000ada4  call    cs:__imp_IsErrorPropagationEnabled
0x18000adaa  test    eax, eax
0x18000adac  jnz     short loc_18000ADC3
0x18000adae  test    ebx, ebx
0x18000adb0  jns     short loc_18000AE26
0x18000adb2  xor     r8d, r8d
0x18000adb5  xor     edx, edx
0x18000adb7  mov     ecx, ebx
0x18000adb9  call    cs:__imp_RoTransformError
0x18000adbf  xor     ebx, ebx
0x18000adc1  jmp     short loc_18000AE26
0x18000adc3  test    ebx, ebx
0x18000adc5  jns     short loc_18000AE26
0x18000adc7  mov     [rsp+38h+var_18], rdi
0x18000adcc  mov     [rsp+38h+arg_18], 0
0x18000add5  lea     rdx, [rsp+38h+arg_18]
0x18000adda  mov     ecx, ebx
0x18000addc  call    cs:__imp_RoGetMatchingRestrictedErrorInfo
0x18000ade2  mov     ecx, eax
0x18000ade4  test    eax, eax
0x18000ade6  js      short loc_18000ADF8
0x18000ade8  mov     rdx, [rsp+38h+arg_18]
0x18000aded  mov     rcx, rsi
0x18000adf0  call    cs:__imp_RoReportFailedDelegate
0x18000adf6  mov     ecx, eax
0x18000adf8  xor     eax, eax
0x18000adfa  test    ecx, ecx
0x18000adfc  cmovs   eax, ebx
0x18000adff  mov     ebx, eax
0x18000ae01  mov     rax, [rsp+38h+var_18]
0x18000ae06  mov     rcx, [rsp+38h+arg_18]
0x18000ae0b  test    rcx, rcx
0x18000ae0e  jz      short loc_18000AE26
0x18000ae10  mov     [rsp+38h+arg_18], 0
0x18000ae19  mov     rax, [rcx]
0x18000ae1c  mov     rax, [rax+10h]
0x18000ae20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae25  nop
0x18000ae26  mov     eax, ebx
0x18000ae28  mov     rbx, [rsp+38h+arg_0]
0x18000ae2d  mov     rsi, [rsp+38h+arg_8]
0x18000ae32  add     rsp, 30h
0x18000ae36  pop     rdi
0x18000ae37  retn
```
