# CLegacyHandlerShim::Init(_GUID const &,ISyncMgrEvent *)

- ea: `0x18001d900`
- end: `0x18001d9da`
- name: `?Init@CLegacyHandlerShim@@UEAAJAEBU_GUID@@PEAUISyncMgrEvent@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(CLegacyHandlerShim *__hidden this, const struct _GUID *, struct ISyncMgrEvent *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001d900`
- `0x18005292a`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHELL32!__imp_GUIDFromStringW` at `0x18001d9a6`
- `SHELL32!__imp_GUIDFromStringW` at `0x18001d9a6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d951`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d951`

## pseudocode

```c
__int64 __fastcall CLegacyHandlerShim::Init(CLegacyHandlerShim *this, const struct _GUID *a2, struct ISyncMgrEvent *a3)
{
  HRESULT v5; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-B68h] BYREF
  _BYTE v8[1836]; // [rsp+40h] [rbp-B58h] BYREF
  _BYTE v9[1044]; // [rsp+76Ch] [rbp-42Ch] BYREF

  ppv = 0;
  v5 = CoCreateInstance(&CLSID_SyncMgrp, 0, 0x15u, &GUID_1df997e7_21c2_4258_a795_49c5d8869bd2, &ppv);
  if ( v5 >= 0 )
  {
    memset_0(v8, 0, 0xB3Cu);
    v5 = (*(__int64 (__fastcall **)(LPVOID, char *, const struct _GUID *, _BYTE *))(*(_QWORD *)ppv + 56LL))(
           ppv,
           (char *)this + 12,
           a2,
           v8);
    if ( v5 >= 0 )
    {
      v5 = -2147024894;
      if ( (unsigned int)GUIDFromStringW(v9, (char *)this + 288) )
        return 0;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001d900  mov     [rsp+arg_10], rbx
0x18001d905  mov     [rsp+arg_18], rsi
0x18001d90a  push    rdi
0x18001d90b  sub     rsp, 0B90h
0x18001d912  mov     rax, cs:__security_cookie
0x18001d919  xor     rax, rsp
0x18001d91c  mov     [rsp+0B98h+var_18], rax
0x18001d924  mov     rsi, rdx
0x18001d927  mov     [rsp+0B98h+var_B68], 0
0x18001d930  xor     edx, edx; pUnkOuter
0x18001d932  lea     rax, [rsp+0B98h+var_B68]
0x18001d937  mov     rdi, rcx
0x18001d93a  mov     [rsp+0B98h+ppv], rax; ppv
0x18001d93f  lea     r9, _GUID_1df997e7_21c2_4258_a795_49c5d8869bd2; riid
0x18001d946  lea     rcx, CLSID_SyncMgrp; rclsid
0x18001d94d  lea     r8d, [rdx+15h]; dwClsContext
0x18001d951  call    cs:__imp_CoCreateInstance
0x18001d957  mov     ebx, eax
0x18001d959  test    eax, eax
0x18001d95b  js      short loc_18001D9B3
0x18001d95d  xor     edx, edx; Val
0x18001d95f  lea     rcx, [rsp+0B98h+var_B58]; void *
0x18001d964  mov     r8d, 0B3Ch; Size
0x18001d96a  call    memset_0
0x18001d96f  mov     rcx, [rsp+0B98h+var_B68]
0x18001d974  lea     rdx, [rdi+0Ch]
0x18001d978  lea     r9, [rsp+0B98h+var_B58]
0x18001d97d  mov     r8, rsi
0x18001d980  mov     rax, [rcx]
0x18001d983  mov     rax, [rax+38h]
0x18001d987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d98c  mov     ebx, eax
0x18001d98e  test    eax, eax
0x18001d990  js      short loc_18001D9B3
0x18001d992  lea     rdx, [rdi+120h]
0x18001d999  mov     ebx, 80070002h
0x18001d99e  lea     rcx, [rsp+0B98h+var_42C]
0x18001d9a6  call    cs:__imp_GUIDFromStringW
0x18001d9ac  xor     ecx, ecx
0x18001d9ae  test    eax, eax
0x18001d9b0  cmovnz  ebx, ecx
0x18001d9b3  mov     eax, ebx
0x18001d9b5  mov     rcx, [rsp+0B98h+var_18]
0x18001d9bd  xor     rcx, rsp; StackCookie
0x18001d9c0  call    __security_check_cookie
0x18001d9c5  lea     r11, [rsp+0B98h+var_8]
0x18001d9cd  mov     rbx, [r11+20h]
0x18001d9d1  mov     rsi, [r11+28h]
0x18001d9d5  mov     rsp, r11
0x18001d9d8  pop     rdi
0x18001d9d9  retn
```
