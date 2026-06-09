# CTpUtils::GetRandomNumber(unsigned __int64)

- ea: `0x1800a35b4`
- end: `0x1800a3727`
- name: `?GetRandomNumber@CTpUtils@@CA_K_K@Z`
- size: `371`
- prototype: `unsigned __int64 __fastcall(unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a3480`

## callees

- `0x18003bf14`
- `0x1800a35b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1800a36a7`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1800a36a7`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x1800a36a1`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x1800a36a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a3688`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a3688`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a367e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a367e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a3668`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a3668`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a3674`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a3674`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800a3697`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800a3697`
- `CRYPTSP!CryptReleaseContext` at `0x1800a3651`
- `CRYPTSP!CryptReleaseContext` at `0x1800a3651`
- `CRYPTSP!CryptGenRandom` at `0x1800a3610`
- `CRYPTSP!CryptGenRandom` at `0x1800a3610`
- `CRYPTSP!CryptAcquireContextW` at `0x1800a35f4`
- `CRYPTSP!CryptAcquireContextW` at `0x1800a35f4`

## pseudocode

```c
HCRYPTPROV __fastcall CTpUtils::GetRandomNumber()
{
  __int64 v0; // rdx
  HCRYPTPROV v1; // rcx
  __int64 v2; // r8
  HCRYPTPROV result; // rax
  DWORD v4; // ebx
  DWORD v5; // edi
  DWORD v6; // ebx
  DWORD v7; // edi
  unsigned int v8; // eax
  int v9; // eax
  double v10; // xmm0_8
  unsigned __int64 pbBuffer; // [rsp+50h] [rbp+20h] BYREF
  HCRYPTPROV phProv; // [rsp+58h] [rbp+28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+30h] BYREF

  phProv = 0;
  pbBuffer = 0;
  SystemTimeAsFileTime = 0;
  if ( CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000000) )
  {
    v1 = phProv;
    if ( phProv )
    {
      while ( 1 )
      {
        CryptGenRandom(v1, 8u, (BYTE *)&pbBuffer);
        if ( pbBuffer <= 0xFFFFFFFFFB69296BuLL )
          break;
        v1 = phProv;
      }
      pbBuffer += 1 - 100000000 * (pbBuffer / 0x5F5E100);
      CryptReleaseContext(phProv, 0);
    }
  }
  result = pbBuffer;
  if ( !pbBuffer )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v4 = SystemTimeAsFileTime.dwHighDateTime ^ SystemTimeAsFileTime.dwLowDateTime;
    v5 = v4 ^ GetTickCount();
    v6 = v5 ^ GetCurrentProcessId();
    v7 = v6 ^ GetCurrentThreadId();
    v8 = (unsigned int)EncodePointer((PVOID)0xDEADBEEFLL);
    _o_srand(v7 ^ v8);
    v9 = rand();
    v1 = 0;
    v10 = (double)v9 / 32767.0 * 99999999.0 + 1.0;
    if ( v10 >= 9.223372036854776e18 )
    {
      v10 = v10 - 9.223372036854776e18;
      if ( v10 < 9.223372036854776e18 )
        v1 = 0x8000000000000000uLL;
    }
    result = v1 + (unsigned int)(int)v10;
    pbBuffer = result;
    if ( !result )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v1, v0, v2);
      result = pbBuffer;
    }
  }
  if ( result > 0x5F5E100 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v1, v0, v2);
    return pbBuffer;
  }
  return result;
}

```

## disassembly

```asm
0x1800a35b4  mov     [rsp-18h+pbBuffer], rcx
0x1800a35b9  push    rbp
0x1800a35ba  push    rbx
0x1800a35bb  push    rdi
0x1800a35bc  mov     rbp, rsp
0x1800a35bf  sub     rsp, 30h
0x1800a35c3  mov     ebx, 1
0x1800a35c8  mov     [rbp+phProv], 0
0x1800a35d0  mov     r9d, ebx; dwProvType
0x1800a35d3  mov     [rbp+pbBuffer], 0
0x1800a35db  xor     r8d, r8d; szProvider
0x1800a35de  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800a35e6  xor     edx, edx; szContainer
0x1800a35e8  mov     [rsp+30h+dwFlags], 0F0000000h; dwFlags
0x1800a35f0  lea     rcx, [rbp+phProv]; phProv
0x1800a35f4  call    cs:__imp_CryptAcquireContextW
0x1800a35fa  test    eax, eax
0x1800a35fc  jz      short loc_1800A3657
0x1800a35fe  mov     rcx, [rbp+phProv]; hProv
0x1800a3602  test    rcx, rcx
0x1800a3605  jz      short loc_1800A3657
0x1800a3607  lea     r8, [rbp+pbBuffer]; pbBuffer
0x1800a360b  mov     edx, 8; dwLen
0x1800a3610  call    cs:__imp_CryptGenRandom
0x1800a3616  mov     rcx, [rbp+pbBuffer]
0x1800a361a  cmp     rcx, 0FFFFFFFFFB69296Bh
0x1800a3621  jbe     short loc_1800A3629
0x1800a3623  mov     rcx, [rbp+phProv]
0x1800a3627  jmp     short loc_1800A3607
0x1800a3629  mov     rax, 0ABCC77118461CEFDh
0x1800a3633  mul     rcx
0x1800a3636  shr     rdx, 1Ah
0x1800a363a  imul    rax, rdx, 5F5E100h
0x1800a3641  xor     edx, edx; dwFlags
0x1800a3643  sub     rbx, rax
0x1800a3646  add     rcx, rbx
0x1800a3649  mov     [rbp+pbBuffer], rcx
0x1800a364d  mov     rcx, [rbp+phProv]; hProv
0x1800a3651  call    cs:__imp_CryptReleaseContext
0x1800a3657  mov     rax, [rbp+pbBuffer]
0x1800a365b  test    rax, rax
0x1800a365e  jnz     loc_1800A370E
0x1800a3664  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a3668  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a366e  mov     ebx, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800a3671  xor     ebx, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x1800a3674  call    cs:__imp_GetTickCount
0x1800a367a  mov     edi, eax
0x1800a367c  xor     edi, ebx
0x1800a367e  call    cs:__imp_GetCurrentProcessId
0x1800a3684  mov     ebx, eax
0x1800a3686  xor     ebx, edi
0x1800a3688  call    cs:__imp_GetCurrentThreadId
0x1800a368e  mov     edi, eax
0x1800a3690  mov     ecx, 0DEADBEEFh; Ptr
0x1800a3695  xor     edi, ebx
0x1800a3697  call    cs:__imp_EncodePointer
0x1800a369d  xor     eax, edi
0x1800a369f  mov     ecx, eax
0x1800a36a1  call    cs:__imp__o_srand
0x1800a36a7  call    cs:__imp_rand
0x1800a36ad  movsd   xmm1, cs:__real@43e0000000000000
0x1800a36b5  xor     ecx, ecx
0x1800a36b7  movd    xmm0, eax
0x1800a36bb  cvtdq2pd xmm0, xmm0
0x1800a36bf  divsd   xmm0, cs:__real@40dfffc000000000
0x1800a36c7  mulsd   xmm0, cs:__real@4197d783fc000000
0x1800a36cf  addsd   xmm0, cs:__real@3ff0000000000000
0x1800a36d7  comisd  xmm0, xmm1
0x1800a36db  jb      short loc_1800A36F4
0x1800a36dd  subsd   xmm0, xmm1
0x1800a36e1  comisd  xmm0, xmm1
0x1800a36e5  jnb     short loc_1800A36F4
0x1800a36e7  mov     rax, 8000000000000000h
0x1800a36f1  mov     rcx, rax
0x1800a36f4  cvttsd2si rax, xmm0
0x1800a36f9  add     rax, rcx
0x1800a36fc  mov     [rbp+pbBuffer], rax
0x1800a3700  test    rax, rax
0x1800a3703  jnz     short loc_1800A370E
0x1800a3705  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a370a  mov     rax, [rbp+pbBuffer]
0x1800a370e  cmp     rax, 5F5E100h
0x1800a3714  jbe     short loc_1800A371F
0x1800a3716  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a371b  mov     rax, [rbp+pbBuffer]
0x1800a371f  add     rsp, 30h
0x1800a3723  pop     rdi
0x1800a3724  pop     rbx
0x1800a3725  pop     rbp
0x1800a3726  retn
```
