# HttpUpdateServiceConfiguration

- ea: `0x180009280`
- end: `0x180009414`
- name: `HttpUpdateServiceConfiguration`
- size: `404`
- prototype: `ULONG __stdcall(HANDLE Handle, HTTP_SERVICE_CONFIG_ID ConfigId, PVOID ConfigInfo, ULONG ConfigInfoLength, LPOVERLAPPED Overlapped)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001710`
- `0x180002b40`
- `0x180008840`
- `0x180009280`
- `0x180009e14`
- `0x18000a4c8`
- `0x18000a5f0`
- `0x18000b0b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800093e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800093e1`

## pseudocode

```c
ULONG __stdcall HttpUpdateServiceConfiguration(
        HANDLE Handle,
        HTTP_SERVICE_CONFIG_ID ConfigId,
        PVOID ConfigInfo,
        ULONG ConfigInfoLength,
        LPOVERLAPPED Overlapped)
{
  __int64 v5; // rbx
  ULONG v8; // esi
  __int64 v10; // rcx
  void *v11; // rdi
  int v12; // eax
  ULONG v13; // ebx
  _BYTE *v14; // rax
  ULONG v15; // eax
  ULONG v17; // [rsp+40h] [rbp-C0h] BYREF
  HTTP_SERVICE_CONFIG_ID InputBuffer; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[176]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[224]; // [rsp+110h] [rbp+10h] BYREF

  v5 = ConfigId;
  InputBuffer = ConfigId;
  v8 = 216;
  memset_0(v21, 0, 0xD8u);
  memset_0(v20, 0, 0xA8u);
  v11 = 0;
  lpMem[0] = 0;
  v17 = 0;
  if ( (byte_1800126A3 & 4) != 0 )
  {
    WPP_SF_I(v10, 44, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids, v5);
    LODWORD(v5) = InputBuffer;
  }
  if ( Overlapped || Handle )
  {
    v13 = 87;
  }
  else
  {
    if ( (unsigned int)v5 <= 0xB && (v12 = 2146, _bittest(&v12, v5)) )
    {
      v13 = ConvertToSniConfig((unsigned int)v5, ConfigInfo, ConfigInfoLength, v21);
      if ( v13 )
        return v13;
      v14 = v21;
    }
    else
    {
      v13 = ConvertToSniExConfig((unsigned int)v5, ConfigInfo, ConfigInfoLength, v20);
      if ( v13 )
        return v13;
      v15 = SerializeUpdateExParams(v20, lpMem, &v17);
      v11 = lpMem[0];
      v13 = v15;
      if ( v15 )
        goto LABEL_14;
      v8 = v17;
      v14 = lpMem[0];
    }
    v13 = HttpApiSynchronousDeviceControl(g_ServiceCommChannelHandle, 0x12808Du, &InputBuffer, 4u, v14, v8, 0);
  }
LABEL_14:
  if ( v11 )
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v11);
  return v13;
}

```

## disassembly

```asm
0x180009280  mov     [rsp-8+arg_0], rbx
0x180009285  mov     [rsp-8+arg_18], rsi
0x18000928a  push    rbp
0x18000928b  push    rdi
0x18000928c  push    r12
0x18000928e  push    r14
0x180009290  push    r15
0x180009292  lea     rbp, [rsp-100h]
0x18000929a  sub     rsp, 200h
0x1800092a1  mov     rax, cs:__security_cookie
0x1800092a8  xor     rax, rsp
0x1800092ab  mov     [rbp+120h+var_30], rax
0x1800092b2  movsxd  rbx, edx
0x1800092b5  mov     r15, r8
0x1800092b8  mov     r12, rcx
0x1800092bb  mov     [rsp+220h+InputBuffer], ebx
0x1800092bf  mov     esi, 0D8h
0x1800092c4  lea     rcx, [rbp+120h+var_110]; void *
0x1800092c8  mov     r8d, esi; Size
0x1800092cb  xor     edx, edx; Val
0x1800092cd  mov     r14d, r9d
0x1800092d0  call    memset_0
0x1800092d5  xor     edx, edx; Val
0x1800092d7  lea     r8d, [rsi-30h]; Size
0x1800092db  lea     rcx, [rsp+220h+var_1C0]; void *
0x1800092e0  call    memset_0
0x1800092e5  xor     edi, edi
0x1800092e7  mov     [rsp+220h+lpMem], rdi
0x1800092ec  mov     [rsp+220h+var_1E0], edi
0x1800092f0  test    cs:byte_1800126A3, 4
0x1800092f7  jz      short loc_18000930F
0x1800092f9  mov     r9, rbx
0x1800092fc  lea     edx, [rdi+2Ch]
0x1800092ff  lea     r8, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids
0x180009306  call    WPP_SF_I
0x18000930b  mov     ebx, [rsp+220h+InputBuffer]
0x18000930f  cmp     [rbp+120h+Overlapped], rdi
0x180009316  jnz     loc_1800093C5
0x18000931c  test    r12, r12
0x18000931f  jnz     loc_1800093C5
0x180009325  cmp     ebx, 0Bh
0x180009328  ja      short loc_180009355
0x18000932a  mov     eax, 862h
0x18000932f  bt      eax, ebx
0x180009332  jnb     short loc_180009355
0x180009334  lea     r9, [rbp+120h+var_110]
0x180009338  mov     r8d, r14d
0x18000933b  mov     rdx, r15
0x18000933e  mov     ecx, ebx
0x180009340  call    ConvertToSniConfig
0x180009345  mov     ebx, eax
0x180009347  test    eax, eax
0x180009349  jnz     loc_1800093E7
0x18000934f  lea     rax, [rbp+120h+var_110]
0x180009353  jmp     short loc_180009393
0x180009355  lea     r9, [rsp+220h+var_1C0]
0x18000935a  mov     r8d, r14d
0x18000935d  mov     rdx, r15
0x180009360  mov     ecx, ebx
0x180009362  call    ConvertToSniExConfig
0x180009367  mov     ebx, eax
0x180009369  test    eax, eax
0x18000936b  jnz     short loc_1800093E7
0x18000936d  lea     r8, [rsp+220h+var_1E0]
0x180009372  lea     rdx, [rsp+220h+lpMem]
0x180009377  lea     rcx, [rsp+220h+var_1C0]
0x18000937c  call    SerializeUpdateExParams
0x180009381  mov     rdi, [rsp+220h+lpMem]
0x180009386  mov     ebx, eax
0x180009388  test    eax, eax
0x18000938a  jnz     short loc_1800093CA
0x18000938c  mov     esi, [rsp+220h+var_1E0]
0x180009390  mov     rax, rdi
0x180009393  mov     rcx, cs:g_ServiceCommChannelHandle; FileHandle
0x18000939a  lea     r8, [rsp+220h+InputBuffer]; InputBuffer
0x18000939f  mov     [rsp+220h+var_1F0], 0; __int64
0x1800093a8  mov     r9d, 4; InputBufferLength
0x1800093ae  mov     [rsp+220h+var_1F8], esi; ULONG
0x1800093b2  mov     edx, 12808Dh; IoControlCode
0x1800093b7  mov     [rsp+220h+var_200], rax; PVOID
0x1800093bc  call    HttpApiSynchronousDeviceControl
0x1800093c1  mov     ebx, eax
0x1800093c3  jmp     short loc_1800093CA
0x1800093c5  mov     ebx, 57h ; 'W'
0x1800093ca  test    rdi, rdi
0x1800093cd  jz      short loc_1800093E7
0x1800093cf  mov     rcx, gs:60h
0x1800093d8  mov     r8, rdi; lpMem
0x1800093db  xor     edx, edx; dwFlags
0x1800093dd  mov     rcx, [rcx+30h]; hHeap
0x1800093e1  call    cs:__imp_HeapFree
0x1800093e7  mov     eax, ebx
0x1800093e9  mov     rcx, [rbp+120h+var_30]
0x1800093f0  xor     rcx, rsp; StackCookie
0x1800093f3  call    __security_check_cookie
0x1800093f8  lea     r11, [rsp+220h+var_20]
0x180009400  mov     rbx, [r11+30h]
0x180009404  mov     rsi, [r11+48h]
0x180009408  mov     rsp, r11
0x18000940b  pop     r15
0x18000940d  pop     r14
0x18000940f  pop     r12
0x180009411  pop     rdi
0x180009412  pop     rbp
0x180009413  retn
```
