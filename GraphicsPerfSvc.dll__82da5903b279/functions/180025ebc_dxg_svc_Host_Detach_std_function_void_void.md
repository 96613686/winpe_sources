# dxg::svc::Host::Detach(std::function<void (void)>)

- ea: `0x180025ebc`
- end: `0x180025f7d`
- name: `?Detach@Host@svc@dxg@@QEAAXV?$function@$$A6AXXZ@std@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(LPSERVICE_STATUS lpServiceStatus)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011630`

## callees

- `0x180003ab0`
- `0x180011180`
- `0x180025ebc`
- `0x180026154`
- `0x1800261f4`
- `0x180031010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180025f35`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180025f35`

## string_xrefs

- `0x180025f47`: `onecoreuap\windows\directx\dxg\common\servicehelpers\host.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall dxg::svc::Host::Detach(LPSERVICE_STATUS lpServiceStatus, __int64 a2)
{
  __int64 (__fastcall ***v4)(_QWORD, _BYTE *); // rcx
  const char *v5; // r9
  _BYTE v7[56]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v8; // [rsp+68h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v8 = 0;
  v4 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(a2 + 56);
  if ( v4 )
    v8 = (**v4)(v4, v7);
  std::_Func_class<void,>::_Swap(v7);
  std::_Func_class<void,>::_Tidy(v7);
  lpServiceStatus->dwCurrentState = 4;
  lpServiceStatus->dwControlsAccepted = 5;
  if ( !SetServiceStatus(g::StatusHandle, lpServiceStatus) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\servicehelpers\\host.cpp",
      v5);
  return std::_Func_class<void,>::_Tidy(a2);
}

```

## disassembly

```asm
0x180025ebc  mov     r11, rsp
0x180025ebf  mov     [r11+18h], rbx
0x180025ec3  push    rdi
0x180025ec4  sub     rsp, 80h
0x180025ecb  mov     rax, cs:__security_cookie
0x180025ed2  xor     rax, rsp
0x180025ed5  mov     [rsp+88h+var_18], rax
0x180025eda  mov     rbx, rdx
0x180025edd  mov     rdi, rcx
0x180025ee0  mov     [r11-68h], rdx
0x180025ee4  mov     qword ptr [r11-20h], 0
0x180025eec  mov     rcx, [rdx+38h]
0x180025ef0  test    rcx, rcx
0x180025ef3  jz      short loc_180025F09
0x180025ef5  mov     rax, [rcx]
0x180025ef8  lea     rdx, [r11-58h]
0x180025efc  mov     rax, [rax]
0x180025eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f04  mov     [rsp+88h+var_20], rax
0x180025f09  lea     rcx, [rsp+88h+var_58]
0x180025f0e  call    ?_Swap@?$_Func_class@X$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<void,>::_Swap(std::_Func_class<void,> &)
0x180025f13  lea     rcx, [rsp+88h+var_58]
0x180025f18  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180025f1d  mov     dword ptr [rdi+4], 4
0x180025f24  mov     dword ptr [rdi+8], 5
0x180025f2b  mov     rdx, rdi; lpServiceStatus
0x180025f2e  mov     rcx, cs:?StatusHandle@g@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180025f35  call    cs:__imp_SetServiceStatus
0x180025f3b  mov     rcx, [rsp+88h]; this
0x180025f43  test    eax, eax
0x180025f45  jnz     short loc_180025F57
0x180025f47  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x180025f4e  lea     edx, [rax+76h]; void *
0x180025f51  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180025f57  mov     rcx, rbx
0x180025f5a  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180025f5f  mov     rcx, [rsp+88h+var_18]
0x180025f64  xor     rcx, rsp; StackCookie
0x180025f67  call    __security_check_cookie
0x180025f6c  mov     rbx, [rsp+88h+arg_10]
0x180025f74  add     rsp, 80h
0x180025f7b  pop     rdi
0x180025f7c  retn
```
