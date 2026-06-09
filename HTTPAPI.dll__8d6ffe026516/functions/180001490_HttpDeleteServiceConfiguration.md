# HttpDeleteServiceConfiguration

- ea: `0x180001490`
- end: `0x1800015c8`
- name: `HttpDeleteServiceConfiguration`
- size: `312`
- prototype: `ULONG __stdcall(HANDLE ServiceHandle, HTTP_SERVICE_CONFIG_ID ConfigId, PVOID pConfigInformation, ULONG ConfigInformationLength, LPOVERLAPPED pOverlapped)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001240`
- `0x180001490`
- `0x180001710`
- `0x180002b40`
- `0x18000a4c8`
- `0x18000a5f0`
- `0x18000b0b8`

## pseudocode

```c
ULONG __stdcall HttpDeleteServiceConfiguration(
        HANDLE ServiceHandle,
        HTTP_SERVICE_CONFIG_ID ConfigId,
        PVOID pConfigInformation,
        ULONG ConfigInformationLength,
        LPOVERLAPPED pOverlapped)
{
  __int64 v5; // rbx
  ULONG v8; // esi
  __int64 v10; // rcx
  ULONG result; // eax
  int v12; // eax
  HTTP_SERVICE_CONFIG_ID InputBuffer[4]; // [rsp+40h] [rbp-118h] BYREF
  _BYTE v14[224]; // [rsp+50h] [rbp-108h] BYREF

  v5 = ConfigId;
  InputBuffer[0] = ConfigId;
  v8 = 216;
  memset_0(v14, 0, 0xD8u);
  if ( (byte_1800126A3 & 4) != 0 )
  {
    WPP_SF_I(v10, 45, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids, v5);
    SLODWORD(v5) = InputBuffer[0];
  }
  if ( pOverlapped || ServiceHandle )
    return 87;
  if ( (_DWORD)v5 == 2 )
  {
    if ( pConfigInformation && ConfigInformationLength == 16 )
      return RemoveUrlFromUrlGroup(g_ServiceCommChannelHandle, 0);
    return 87;
  }
  if ( (unsigned int)v5 <= 0xB && (v12 = 2146, _bittest(&v12, v5)) )
  {
    result = ConvertToSniConfig((unsigned int)v5, pConfigInformation, ConfigInformationLength, v14);
    if ( result )
      return result;
    pConfigInformation = v14;
  }
  else
  {
    v8 = ConfigInformationLength;
  }
  return HttpApiSynchronousDeviceControl(
           g_ServiceCommChannelHandle,
           0x128091u,
           InputBuffer,
           4u,
           pConfigInformation,
           v8,
           0);
}

```

## disassembly

```asm
0x180001490  mov     [rsp+arg_0], rbx
0x180001495  mov     [rsp+arg_18], rbp
0x18000149a  push    rsi
0x18000149b  push    rdi
0x18000149c  push    r14
0x18000149e  sub     rsp, 140h
0x1800014a5  mov     rax, cs:__security_cookie
0x1800014ac  xor     rax, rsp
0x1800014af  mov     [rsp+158h+var_28], rax
0x1800014b7  movsxd  rbx, edx
0x1800014ba  mov     r14, r8
0x1800014bd  mov     rdi, rcx
0x1800014c0  mov     [rsp+158h+InputBuffer], ebx
0x1800014c4  mov     esi, 0D8h
0x1800014c9  lea     rcx, [rsp+158h+var_108]; void *
0x1800014ce  mov     r8d, esi; Size
0x1800014d1  xor     edx, edx; Val
0x1800014d3  mov     ebp, r9d
0x1800014d6  call    memset_0
0x1800014db  test    cs:byte_1800126A3, 4
0x1800014e2  jz      short loc_1800014FC
0x1800014e4  mov     r9, rbx
0x1800014e7  lea     r8, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids
0x1800014ee  mov     edx, 2Dh ; '-'
0x1800014f3  call    WPP_SF_I
0x1800014f8  mov     ebx, [rsp+158h+InputBuffer]
0x1800014fc  cmp     [rsp+158h+pOverlapped], 0
0x180001505  jnz     loc_18000159B
0x18000150b  test    rdi, rdi
0x18000150e  jnz     loc_18000159B
0x180001514  cmp     ebx, 2
0x180001517  jnz     short loc_18000153D
0x180001519  test    r14, r14
0x18000151c  jz      short loc_18000159B
0x18000151e  cmp     ebp, 10h
0x180001521  jnz     short loc_18000159B
0x180001523  mov     r9, [r14]
0x180001526  xor     r8d, r8d
0x180001529  mov     rcx, cs:g_ServiceCommChannelHandle; FileHandle
0x180001530  xor     edx, edx
0x180001532  mov     dword ptr [rsp+158h+var_138], edi; int
0x180001536  call    RemoveUrlFromUrlGroup
0x18000153b  jmp     short loc_1800015A0
0x18000153d  cmp     ebx, 0Bh
0x180001540  ja      short loc_180001569
0x180001542  mov     eax, 862h
0x180001547  bt      eax, ebx
0x18000154a  jnb     short loc_180001569
0x18000154c  lea     r9, [rsp+158h+var_108]
0x180001551  mov     r8d, ebp
0x180001554  mov     rdx, r14
0x180001557  mov     ecx, ebx
0x180001559  call    ConvertToSniConfig
0x18000155e  test    eax, eax
0x180001560  jnz     short loc_1800015A0
0x180001562  lea     r14, [rsp+158h+var_108]
0x180001567  jmp     short loc_18000156B
0x180001569  mov     esi, ebp
0x18000156b  mov     rcx, cs:g_ServiceCommChannelHandle; FileHandle
0x180001572  lea     r8, [rsp+158h+InputBuffer]; InputBuffer
0x180001577  mov     [rsp+158h+var_128], 0; __int64
0x180001580  mov     r9d, 4; InputBufferLength
0x180001586  mov     [rsp+158h+var_130], esi; ULONG
0x18000158a  mov     edx, 128091h; IoControlCode
0x18000158f  mov     [rsp+158h+var_138], r14; PVOID
0x180001594  call    HttpApiSynchronousDeviceControl
0x180001599  jmp     short loc_1800015A0
0x18000159b  mov     eax, 57h ; 'W'
0x1800015a0  mov     rcx, [rsp+158h+var_28]
0x1800015a8  xor     rcx, rsp; StackCookie
0x1800015ab  call    __security_check_cookie
0x1800015b0  lea     r11, [rsp+158h+var_18]
0x1800015b8  mov     rbx, [r11+20h]
0x1800015bc  mov     rbp, [r11+38h]
0x1800015c0  mov     rsp, r11
0x1800015c3  pop     r14
0x1800015c5  pop     rdi
0x1800015c6  pop     rsi
0x1800015c7  retn
```
