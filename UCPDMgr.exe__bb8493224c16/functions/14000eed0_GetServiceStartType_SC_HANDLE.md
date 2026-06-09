# GetServiceStartType(SC_HANDLE__ *)

- ea: `0x14000eed0`
- end: `0x14000ef84`
- name: `?GetServiceStartType@@YAKPEAUSC_HANDLE__@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(SC_HANDLE hService)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x14000ede0`

## callees

- `0x14000a390`
- `0x14000eed0`

## import_xrefs

- `ADVAPI32!QueryServiceConfigA` at `0x14000ef0a`
- `ADVAPI32!QueryServiceConfigA` at `0x14000ef43`
- `ADVAPI32!QueryServiceConfigA` at `0x14000ef0a`
- `ADVAPI32!QueryServiceConfigA` at `0x14000ef43`
- `KERNEL32!LocalAlloc` at `0x14000ef27`
- `KERNEL32!LocalAlloc` at `0x14000ef27`
- `KERNEL32!GetLastError` at `0x14000ef14`
- `KERNEL32!GetLastError` at `0x14000ef14`
- `KERNEL32!LocalFree` at `0x14000ef53`
- `KERNEL32!LocalFree` at `0x14000ef53`

## pseudocode

```c
__int64 __fastcall GetServiceStartType(SC_HANDLE hService)
{
  unsigned int dwStartType; // edi
  DWORD v3; // esi
  struct _QUERY_SERVICE_CONFIGA *v4; // rax
  struct _QUERY_SERVICE_CONFIGA *v5; // rbx
  SIZE_T uBytes; // [rsp+20h] [rbp-18h] BYREF

  LODWORD(uBytes) = 0;
  dwStartType = -1;
  if ( !QueryServiceConfigA(hService, 0, 0, (LPDWORD)&uBytes) )
  {
    if ( GetLastError() != 122 )
      return dwStartType;
    v3 = uBytes;
    v4 = (struct _QUERY_SERVICE_CONFIGA *)LocalAlloc(0, (unsigned int)uBytes);
    v5 = v4;
    if ( v4 )
    {
      if ( QueryServiceConfigA(hService, v4, v3, (LPDWORD)&uBytes) )
        dwStartType = v5->dwStartType;
      LocalFree(v5);
      return dwStartType;
    }
  }
  return 122;
}

```

## disassembly

```asm
0x14000eed0  mov     r11, rsp
0x14000eed3  mov     [r11+10h], rbx
0x14000eed7  mov     [r11+18h], rbp
0x14000eedb  mov     [r11+20h], rsi
0x14000eedf  push    rdi
0x14000eee0  sub     rsp, 30h
0x14000eee4  mov     rax, cs:__security_cookie
0x14000eeeb  xor     rax, rsp
0x14000eeee  mov     [rsp+38h+var_10], rax
0x14000eef3  lea     r9, [r11-18h]; pcbBytesNeeded
0x14000eef7  mov     dword ptr [rsp+38h+uBytes], 0
0x14000eeff  xor     r8d, r8d; cbBufSize
0x14000ef02  xor     edx, edx; lpServiceConfig
0x14000ef04  mov     rbp, rcx
0x14000ef07  or      edi, 0FFFFFFFFh
0x14000ef0a  call    cs:__imp_QueryServiceConfigA
0x14000ef10  test    eax, eax
0x14000ef12  jnz     short loc_14000EF5D
0x14000ef14  call    cs:__imp_GetLastError
0x14000ef1a  cmp     eax, 7Ah ; 'z'
0x14000ef1d  jnz     short loc_14000EF59
0x14000ef1f  mov     esi, dword ptr [rsp+38h+uBytes]
0x14000ef23  xor     ecx, ecx; uFlags
0x14000ef25  mov     edx, esi; uBytes
0x14000ef27  call    cs:__imp_LocalAlloc
0x14000ef2d  mov     rbx, rax
0x14000ef30  test    rax, rax
0x14000ef33  jz      short loc_14000EF5D
0x14000ef35  lea     r9, [rsp+38h+uBytes]; pcbBytesNeeded
0x14000ef3a  mov     r8d, esi; cbBufSize
0x14000ef3d  mov     rdx, rax; lpServiceConfig
0x14000ef40  mov     rcx, rbp; hService
0x14000ef43  call    cs:__imp_QueryServiceConfigA
0x14000ef49  test    eax, eax
0x14000ef4b  jz      short loc_14000EF50
0x14000ef4d  mov     edi, [rbx+4]
0x14000ef50  mov     rcx, rbx; hMem
0x14000ef53  call    cs:__imp_LocalFree
0x14000ef59  mov     eax, edi
0x14000ef5b  jmp     short loc_14000EF62
0x14000ef5d  mov     eax, 7Ah ; 'z'
0x14000ef62  mov     rcx, [rsp+38h+var_10]
0x14000ef67  xor     rcx, rsp; StackCookie
0x14000ef6a  call    __security_check_cookie
0x14000ef6f  mov     rbx, [rsp+38h+arg_8]
0x14000ef74  mov     rbp, [rsp+38h+arg_10]
0x14000ef79  mov     rsi, [rsp+38h+arg_18]
0x14000ef7e  add     rsp, 30h
0x14000ef82  pop     rdi
0x14000ef83  retn
```
