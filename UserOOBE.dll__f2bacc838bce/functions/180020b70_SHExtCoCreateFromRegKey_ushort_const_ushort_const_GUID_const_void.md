# SHExtCoCreateFromRegKey(ushort const *,ushort const *,_GUID const &,void * *)

- ea: `0x180020b70`
- end: `0x180020c50`
- name: `?SHExtCoCreateFromRegKey@@YAJPEBG0AEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001fcc0`
- `0x180020350`
- `0x180020760`
- `0x180029b68`

## callees

- `0x1800032b0`
- `0x180020b70`

## import_xrefs

- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegGetUSValueW` at `0x180020bdf`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegGetUSValueW` at `0x180020bdf`
- `SHCORE!__imp_GUIDFromStringW` at `0x180020bfb`
- `SHCORE!__imp_GUIDFromStringW` at `0x180020bfb`
- `ext-ms-win-shell-shell32-l1-2-2!__imp_SHExtCoCreateInstance` at `0x180020c25`
- `ext-ms-win-shell-shell32-l1-2-2!__imp_SHExtCoCreateInstance` at `0x180020c25`

## string_xrefs

- `0x180020ba5`: `TaskScheduler`

## pseudocode

```c
__int64 __fastcall SHExtCoCreateFromRegKey(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v5; // ebx
  DWORD pcbData; // [rsp+40h] [rbp-248h] BYREF
  __int128 v8; // [rsp+48h] [rbp-240h] BYREF
  _BYTE pvData[528]; // [rsp+60h] [rbp-228h] BYREF

  *a4 = 0;
  pcbData = 520;
  v5 = -2147467259;
  if ( !SHRegGetUSValueW(
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
          L"TaskScheduler",
          0,
          pvData,
          &pcbData,
          0,
          0,
          0) )
  {
    v8 = 0;
    if ( (unsigned int)GUIDFromStringW(pvData, &v8) )
      return (unsigned int)SHExtCoCreateInstance(&v8, 0, 1, 2, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, a4);
  }
  return v5;
}

```

## disassembly

```asm
0x180020b70  mov     [rsp+arg_0], rbx
0x180020b75  push    rdi
0x180020b76  sub     rsp, 280h
0x180020b7d  mov     rax, cs:__security_cookie
0x180020b84  xor     rax, rsp
0x180020b87  mov     [rsp+288h+var_18], rax
0x180020b8f  mov     [rsp+288h+dwDefaultDataSize], 0; dwDefaultDataSize
0x180020b97  lea     rax, [rsp+288h+var_248]
0x180020b9c  mov     [rsp+288h+pvDefaultData], 0; pvDefaultData
0x180020ba5  lea     rdx, pszValue; "TaskScheduler"
0x180020bac  mov     rdi, r9
0x180020baf  mov     qword ptr [r9], 0
0x180020bb6  mov     [rsp+288h+fIgnoreHKCU], 0; fIgnoreHKCU
0x180020bbe  lea     r9, [rsp+288h+pvData]; pvData
0x180020bc3  xor     r8d, r8d; pdwType
0x180020bc6  mov     [rsp+288h+pcbData], rax; pcbData
0x180020bcb  lea     rcx, pszSubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180020bd2  mov     [rsp+288h+var_248], 208h
0x180020bda  mov     ebx, 80004005h
0x180020bdf  call    cs:__imp_SHRegGetUSValueW
0x180020be5  test    eax, eax
0x180020be7  jnz     short loc_180020C2D
0x180020be9  xorps   xmm0, xmm0
0x180020bec  lea     rdx, [rsp+288h+var_240]
0x180020bf1  lea     rcx, [rsp+288h+pvData]
0x180020bf6  movups  [rsp+288h+var_240], xmm0
0x180020bfb  call    cs:__imp_GUIDFromStringW
0x180020c01  test    eax, eax
0x180020c03  jz      short loc_180020C2D
0x180020c05  xor     edx, edx
0x180020c07  mov     qword ptr [rsp+288h+fIgnoreHKCU], rdi
0x180020c0c  lea     rax, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85
0x180020c13  lea     rcx, [rsp+288h+var_240]
0x180020c18  mov     [rsp+288h+pcbData], rax
0x180020c1d  lea     r9d, [rdx+2]
0x180020c21  lea     r8d, [rdx+1]
0x180020c25  call    cs:__imp_SHExtCoCreateInstance
0x180020c2b  mov     ebx, eax
0x180020c2d  mov     eax, ebx
0x180020c2f  mov     rcx, [rsp+288h+var_18]
0x180020c37  xor     rcx, rsp; StackCookie
0x180020c3a  call    __security_check_cookie
0x180020c3f  mov     rbx, [rsp+288h+arg_0]
0x180020c47  add     rsp, 280h
0x180020c4e  pop     rdi
0x180020c4f  retn
```
