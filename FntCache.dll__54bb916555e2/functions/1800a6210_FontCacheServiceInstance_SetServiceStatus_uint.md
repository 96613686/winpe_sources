# FontCacheServiceInstance::SetServiceStatus(uint)

- ea: `0x1800a6210`
- end: `0x1800a6281`
- name: `?SetServiceStatus@FontCacheServiceInstance@@CAXI@Z`
- size: `113`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800a61b0`
- `0x1800b06e4`
- `0x1800e4901`

## callees

- `0x1800a1558`
- `0x1800a6210`
- `0x1800aa650`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800a625f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800a625f`

## pseudocode

```c
void __fastcall FontCacheServiceInstance::SetServiceStatus(DWORD a1)
{
  DWORD v1; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  ServiceStatus.dwCurrentState = a1;
  v1 = _mm_cvtsi128_si32((__m128i)0LL);
  *(_OWORD *)&ServiceStatus.dwControlsAccepted = 0;
  if ( a1 == 4 )
    v1 = 5;
  ServiceStatus.dwWaitHint = 0;
  ServiceStatus.dwControlsAccepted = v1;
  ServiceStatus.dwServiceType = 32;
  if ( !SetServiceStatus(FontCacheServiceInstance::statusHandle_, &ServiceStatus) )
    OSException::ThrowLastError();
}

```

## disassembly

```asm
0x1800a6210  sub     rsp, 58h
0x1800a6214  mov     rax, cs:__security_cookie
0x1800a621b  xor     rax, rsp
0x1800a621e  mov     [rsp+58h+var_18], rax
0x1800a6223  xorps   xmm0, xmm0
0x1800a6226  mov     [rsp+58h+ServiceStatus.dwCurrentState], ecx
0x1800a622a  cmp     ecx, 4
0x1800a622d  movd    eax, xmm0
0x1800a6231  mov     rcx, cs:?statusHandle_@FontCacheServiceInstance@@0PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1800a6238  mov     edx, 5
0x1800a623d  movdqu  xmmword ptr [rsp+58h+ServiceStatus.dwControlsAccepted], xmm0
0x1800a6243  cmovz   eax, edx
0x1800a6246  mov     [rsp+58h+ServiceStatus.dwWaitHint], 0
0x1800a624e  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800a6253  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], eax
0x1800a6257  mov     [rsp+58h+ServiceStatus.dwServiceType], 20h ; ' '
0x1800a625f  call    cs:__imp_SetServiceStatus
0x1800a6265  test    eax, eax
0x1800a6267  jnz     short loc_1800A626F
0x1800a6269  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x1800a626f  mov     rcx, [rsp+58h+var_18]
0x1800a6274  xor     rcx, rsp; StackCookie
0x1800a6277  call    __security_check_cookie
0x1800a627c  add     rsp, 58h
0x1800a6280  retn
```
