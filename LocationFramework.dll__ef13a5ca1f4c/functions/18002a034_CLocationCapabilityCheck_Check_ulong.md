# CLocationCapabilityCheck::Check(ulong)

- ea: `0x18002a034`
- end: `0x18002a1f0`
- name: `?Check@CLocationCapabilityCheck@@SAJK@Z`
- size: `444`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180029ff0`

## callees

- `0x18001ebb0`
- `0x18002a034`
- `0x18002a1f8`
- `0x18002a41c`
- `0x1800a98c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1ba`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002a0c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002a0c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a092`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a092`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002a0b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002a0b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a113`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a113`
- `ntdll!RtlCapabilityCheck` at `0x18002a18e`
- `ntdll!RtlCapabilityCheck` at `0x18002a18e`
- `ntdll!RtlInitUnicodeString` at `0x18002a17c`
- `ntdll!RtlInitUnicodeString` at `0x18002a17c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002a0a0`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002a0a0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002a0d4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002a0d4`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18002a0e9`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18002a0e9`

## pseudocode

```c
__int64 __fastcall CLocationCapabilityCheck::Check(int a1)
{
  const wchar_t *v2; // rdi
  signed int v3; // ebx
  unsigned int CallerProcessId; // esi
  HANDLE CurrentThread; // rax
  char HasLocationDeviceCapability; // al
  signed int v8; // ecx
  signed int LastError; // eax
  void *TokenHandle; // [rsp+20h] [rbp-30h] BYREF
  char v11; // [rsp+28h] [rbp-28h] BYREF
  _BYTE v12[7]; // [rsp+29h] [rbp-27h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-20h] BYREF

  TokenHandle = 0;
  v11 = 0;
  v12[0] = 0;
  DestinationString = 0;
  switch ( a1 )
  {
    case 1:
      v2 = L"ID_CAP_LOCATION";
      break;
    case 16:
      v2 = L"ID_CAP_LOCATION_ADMIN";
      break;
    case 256:
      v2 = L"locationHistory";
      break;
    case 512:
      v2 = L"locationSystem";
      break;
    default:
      return (unsigned int)-2147024809;
  }
  v3 = 0;
  CallerProcessId = CLocationPrivileges::GetCallerProcessId();
  if ( CallerProcessId && CallerProcessId != GetCurrentProcessId() )
  {
    TokenHandle = 0;
    v3 = CoImpersonateClient();
    if ( v3 >= 0 )
    {
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        v3 = 0;
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
      }
      CoRevertToSelf();
    }
    if ( v3 >= 0 )
    {
      v3 = CapabilityCheck(TokenHandle, v2, &v11);
      if ( v3 >= 0 )
      {
        v3 = v11 != 1 ? 0x80070005 : 0;
        if ( a1 == 1 && v11 != 1 )
        {
          HasLocationDeviceCapability = CLocationCapabilityCheck::HasLocationDeviceCapability(TokenHandle);
          v8 = 0;
          if ( !HasLocationDeviceCapability )
            v8 = v3;
          v3 = v8;
          RtlInitUnicodeString(&DestinationString, L"location");
          if ( (int)RtlCapabilityCheck(TokenHandle, &DestinationString, v12) >= 0 && v12[0] == 1 )
            v3 = 0;
          if ( !CLocationCapabilityCheck::IsAppContainer(TokenHandle) )
            v3 = 0;
        }
      }
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002a034  push    rbp
0x18002a036  push    rbx
0x18002a037  push    rsi
0x18002a038  push    rdi
0x18002a039  push    r14
0x18002a03b  mov     rbp, rsp
0x18002a03e  sub     rsp, 50h
0x18002a042  mov     rax, cs:__security_cookie
0x18002a049  xor     rax, rsp
0x18002a04c  mov     [rbp+var_10], rax
0x18002a050  mov     eax, ecx
0x18002a052  mov     [rbp+TokenHandle], 0
0x18002a05a  mov     [rbp+var_28], 0
0x18002a05e  xorps   xmm0, xmm0
0x18002a061  mov     [rbp+var_27], 0
0x18002a065  mov     r14d, ecx
0x18002a068  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002a06c  sub     eax, 1
0x18002a06f  jz      loc_18002A132
0x18002a075  sub     eax, 0Fh
0x18002a078  jnz     loc_18002A13E
0x18002a07e  lea     rdi, aIdCapLocationA; "ID_CAP_LOCATION_ADMIN"
0x18002a085  xor     ebx, ebx
0x18002a087  call    ?GetCallerProcessId@CLocationPrivileges@@SAKXZ; CLocationPrivileges::GetCallerProcessId(void)
0x18002a08c  mov     esi, eax
0x18002a08e  test    eax, eax
0x18002a090  jz      short loc_18002A10A
0x18002a092  call    cs:__imp_GetCurrentProcessId
0x18002a098  cmp     esi, eax
0x18002a09a  jz      short loc_18002A10A
0x18002a09c  mov     [rbp+TokenHandle], rbx
0x18002a0a0  call    cs:__imp_CoImpersonateClient
0x18002a0a6  mov     ebx, eax
0x18002a0a8  mov     esi, 1
0x18002a0ad  test    eax, eax
0x18002a0af  js      short loc_18002A0DA
0x18002a0b1  call    cs:__imp_GetCurrentThread
0x18002a0b7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002a0bb  mov     r8d, esi; OpenAsSelf
0x18002a0be  mov     rcx, rax; ThreadHandle
0x18002a0c1  lea     edx, [rsi+7]; DesiredAccess
0x18002a0c4  call    cs:__imp_OpenThreadToken
0x18002a0ca  test    eax, eax
0x18002a0cc  jz      loc_18002A1BA
0x18002a0d2  xor     ebx, ebx
0x18002a0d4  call    cs:__imp_CoRevertToSelf
0x18002a0da  test    ebx, ebx
0x18002a0dc  js      short loc_18002A10A
0x18002a0de  mov     rcx, [rbp+TokenHandle]
0x18002a0e2  lea     r8, [rbp+var_28]
0x18002a0e6  mov     rdx, rdi
0x18002a0e9  call    cs:__imp_CapabilityCheck
0x18002a0ef  mov     ebx, eax
0x18002a0f1  test    eax, eax
0x18002a0f3  js      short loc_18002A10A
0x18002a0f5  mov     al, [rbp+var_28]
0x18002a0f8  sub     al, sil
0x18002a0fb  neg     al
0x18002a0fd  sbb     ebx, ebx
0x18002a0ff  and     ebx, 80070005h
0x18002a105  cmp     r14d, esi
0x18002a108  jz      short loc_18002A15B
0x18002a10a  mov     rcx, [rbp+TokenHandle]; hObject
0x18002a10e  test    rcx, rcx
0x18002a111  jz      short loc_18002A119
0x18002a113  call    cs:__imp_CloseHandle
0x18002a119  mov     eax, ebx
0x18002a11b  mov     rcx, [rbp+var_10]
0x18002a11f  xor     rcx, rsp; StackCookie
0x18002a122  call    __security_check_cookie
0x18002a127  add     rsp, 50h
0x18002a12b  pop     r14
0x18002a12d  pop     rdi
0x18002a12e  pop     rsi
0x18002a12f  pop     rbx
0x18002a130  pop     rbp
0x18002a131  retn
0x18002a132  lea     rdi, aIdCapLocation; "ID_CAP_LOCATION"
0x18002a139  jmp     loc_18002A085
0x18002a13e  sub     eax, 0F0h
0x18002a143  jz      loc_18002A1E4
0x18002a149  cmp     eax, 100h
0x18002a14e  jz      loc_18002A1D8
0x18002a154  mov     ebx, 80070057h
0x18002a159  jmp     short loc_18002A119
0x18002a15b  test    ebx, ebx
0x18002a15d  jns     short loc_18002A10A
0x18002a15f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002a163  call    ?HasLocationDeviceCapability@CLocationCapabilityCheck@@SA_NPEAX@Z; CLocationCapabilityCheck::HasLocationDeviceCapability(void *)
0x18002a168  xor     ecx, ecx
0x18002a16a  lea     rdx, SourceString; "location"
0x18002a171  test    al, al
0x18002a173  cmovz   ecx, ebx
0x18002a176  mov     ebx, ecx
0x18002a178  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002a17c  call    cs:__imp_RtlInitUnicodeString
0x18002a182  mov     rcx, [rbp+TokenHandle]
0x18002a186  lea     r8, [rbp+var_27]
0x18002a18a  lea     rdx, [rbp+DestinationString]
0x18002a18e  call    cs:__imp_RtlCapabilityCheck
0x18002a194  test    eax, eax
0x18002a196  jns     short loc_18002A1B0
0x18002a198  mov     rcx, [rbp+TokenHandle]; void *
0x18002a19c  call    ?IsAppContainer@CLocationCapabilityCheck@@SA_NPEAX@Z; CLocationCapabilityCheck::IsAppContainer(void *)
0x18002a1a1  test    al, al
0x18002a1a3  jnz     loc_18002A10A
0x18002a1a9  xor     ebx, ebx
0x18002a1ab  jmp     loc_18002A10A
0x18002a1b0  cmp     [rbp+var_27], sil
0x18002a1b4  jnz     short loc_18002A198
0x18002a1b6  xor     ebx, ebx
0x18002a1b8  jmp     short loc_18002A198
0x18002a1ba  call    cs:__imp_GetLastError
0x18002a1c0  mov     ebx, eax
0x18002a1c2  test    eax, eax
0x18002a1c4  jle     loc_18002A0D4
0x18002a1ca  movzx   ebx, ax
0x18002a1cd  or      ebx, 80070000h
0x18002a1d3  jmp     loc_18002A0D4
0x18002a1d8  lea     rdi, aLocationsystem_0; "locationSystem"
0x18002a1df  jmp     loc_18002A085
0x18002a1e4  lea     rdi, aLocationhistor; "locationHistory"
0x18002a1eb  jmp     loc_18002A085
```
