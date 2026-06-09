# HttpSetServiceConfiguration

- ea: `0x1800015d0`
- end: `0x180001706`
- name: `HttpSetServiceConfiguration`
- size: `310`
- prototype: `ULONG __stdcall(HANDLE ServiceHandle, HTTP_SERVICE_CONFIG_ID ConfigId, PVOID pConfigInformation, ULONG ConfigInformationLength, LPOVERLAPPED pOverlapped)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800015d0`
- `0x180001710`
- `0x180002b40`
- `0x180009f28`
- `0x18000a4c8`
- `0x18000a5f0`
- `0x18000b0b8`

## pseudocode

```c
ULONG __stdcall HttpSetServiceConfiguration(
        HANDLE ServiceHandle,
        HTTP_SERVICE_CONFIG_ID ConfigId,
        PVOID pConfigInformation,
        ULONG ConfigInformationLength,
        LPOVERLAPPED pOverlapped)
{
  __int64 v5; // rdi
  ULONG v8; // esi
  __int64 v10; // rcx
  int v11; // eax
  ULONG result; // eax
  HTTP_SERVICE_CONFIG_ID InputBuffer[4]; // [rsp+40h] [rbp-118h] BYREF
  _BYTE v14[224]; // [rsp+50h] [rbp-108h] BYREF

  v5 = ConfigId;
  InputBuffer[0] = ConfigId;
  v8 = 216;
  memset_0(v14, 0, 0xD8u);
  if ( (byte_1800126A3 & 4) != 0 )
  {
    WPP_SF_I(v10, 43, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids, v5);
    SLODWORD(v5) = InputBuffer[0];
  }
  if ( pOverlapped || ServiceHandle )
    return 87;
  if ( (_DWORD)v5 == 2 )
    return SetUrlAclInfo(pConfigInformation, ConfigInformationLength);
  if ( (unsigned int)v5 > 0xB || (v11 = 2146, !_bittest(&v11, v5)) )
  {
    v8 = ConfigInformationLength;
    return HttpApiSynchronousDeviceControl(
             g_ServiceCommChannelHandle,
             0x128089u,
             InputBuffer,
             4u,
             pConfigInformation,
             v8,
             0);
  }
  result = ConvertToSniConfig((unsigned int)v5, pConfigInformation, ConfigInformationLength, v14);
  if ( !result )
  {
    pConfigInformation = v14;
    return HttpApiSynchronousDeviceControl(
             g_ServiceCommChannelHandle,
             0x128089u,
             InputBuffer,
             4u,
             pConfigInformation,
             v8,
             0);
  }
  return result;
}

```

## disassembly

```asm
0x1800015d0  mov     [rsp+arg_0], rbx
0x1800015d5  mov     [rsp+arg_18], rbp
0x1800015da  push    rsi
0x1800015db  push    rdi
0x1800015dc  push    r14
0x1800015de  sub     rsp, 140h
0x1800015e5  mov     rax, cs:__security_cookie
0x1800015ec  xor     rax, rsp
0x1800015ef  mov     [rsp+158h+var_28], rax
0x1800015f7  movsxd  rdi, edx
0x1800015fa  mov     r14, r8
0x1800015fd  mov     rbx, rcx
0x180001600  mov     [rsp+158h+InputBuffer], edi
0x180001604  mov     esi, 0D8h
0x180001609  lea     rcx, [rsp+158h+var_108]; void *
0x18000160e  mov     r8d, esi; Size
0x180001611  xor     edx, edx; Val
0x180001613  mov     ebp, r9d
0x180001616  call    memset_0
0x18000161b  test    cs:byte_1800126A3, 4
0x180001622  jnz     loc_1800016D3
0x180001628  cmp     [rsp+158h+pOverlapped], 0
0x180001631  jnz     loc_1800016CC
0x180001637  test    rbx, rbx
0x18000163a  jnz     loc_1800016CC
0x180001640  cmp     edi, 2
0x180001643  jz      loc_1800016F0
0x180001649  cmp     edi, 0Bh
0x18000164c  ja      short loc_18000169A
0x18000164e  mov     eax, 862h
0x180001653  bt      eax, edi
0x180001656  jnb     short loc_18000169A
0x180001658  lea     r9, [rsp+158h+var_108]
0x18000165d  mov     r8d, ebp
0x180001660  mov     rdx, r14
0x180001663  mov     ecx, edi
0x180001665  call    ConvertToSniConfig
0x18000166a  test    eax, eax
0x18000166c  jz      loc_1800016FF
0x180001672  mov     rcx, [rsp+158h+var_28]
0x18000167a  xor     rcx, rsp; StackCookie
0x18000167d  call    __security_check_cookie
0x180001682  lea     r11, [rsp+158h+var_18]
0x18000168a  mov     rbx, [r11+20h]
0x18000168e  mov     rbp, [r11+38h]
0x180001692  mov     rsp, r11
0x180001695  pop     r14
0x180001697  pop     rdi
0x180001698  pop     rsi
0x180001699  retn
0x18000169a  mov     esi, ebp
0x18000169c  mov     rcx, cs:g_ServiceCommChannelHandle; FileHandle
0x1800016a3  lea     r8, [rsp+158h+InputBuffer]; InputBuffer
0x1800016a8  mov     [rsp+158h+var_128], 0; __int64
0x1800016b1  mov     r9d, 4; InputBufferLength
0x1800016b7  mov     [rsp+158h+var_130], esi; ULONG
0x1800016bb  mov     edx, 128089h; IoControlCode
0x1800016c0  mov     [rsp+158h+var_138], r14; PVOID
0x1800016c5  call    HttpApiSynchronousDeviceControl
0x1800016ca  jmp     short loc_180001672
0x1800016cc  mov     eax, 57h ; 'W'
0x1800016d1  jmp     short loc_180001672
0x1800016d3  mov     r9, rdi
0x1800016d6  lea     r8, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids
0x1800016dd  mov     edx, 2Bh ; '+'
0x1800016e2  call    WPP_SF_I
0x1800016e7  mov     edi, [rsp+158h+InputBuffer]
0x1800016eb  jmp     loc_180001628
0x1800016f0  mov     edx, ebp
0x1800016f2  mov     rcx, r14
0x1800016f5  call    SetUrlAclInfo
0x1800016fa  jmp     loc_180001672
0x1800016ff  lea     r14, [rsp+158h+var_108]
0x180001704  jmp     short loc_18000169C
```
