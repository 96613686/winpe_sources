# PropertySetHelper::GetString(HSTRING__ *)

- ea: `0x180027e64`
- end: `0x180027f01`
- name: `?GetString@PropertySetHelper@@QEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@@Z`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180040854`

## callees

- `0x180003678`
- `0x180027e64`
- `0x180027f08`
- `0x180041054`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027eaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027eaa`

## string_xrefs

- `0x180027ed1`: `onecoreuap\windows\cdp\service\cdpusersvc\PropertySetHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HSTRING *__fastcall PropertySetHelper::GetString(__int64 a1, HSTRING *a2)
{
  __int64 PropertyValue; // rax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, HSTRING *); // rbx
  int v6; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v9; // [rsp+58h] [rbp+20h] BYREF

  *a2 = 0;
  PropertyValue = PropertySetHelper::GetPropertyValue(a1, &v9);
  v4 = *(_QWORD *)PropertyValue;
  v5 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)PropertyValue + 152LL);
  WindowsDeleteString(*a2);
  *a2 = 0;
  v6 = v5(v4, a2);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecoreuap\\windows\\cdp\\service\\cdpusersvc\\PropertySetHelper.h",
      (const char *)(unsigned int)v6,
      1);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  return a2;
}

```

## disassembly

```asm
0x180027e64  mov     rax, rsp
0x180027e67  mov     [rax+8], rbx
0x180027e6b  mov     [rax+18h], rsi
0x180027e6f  mov     [rax+10h], rdx
0x180027e73  push    rdi
0x180027e74  sub     rsp, 30h
0x180027e78  mov     rsi, rdx
0x180027e7b  mov     dword ptr [rax-18h], 0
0x180027e82  mov     qword ptr [rdx], 0
0x180027e89  mov     dword ptr [rax-18h], 1
0x180027e90  lea     rdx, [rax+20h]
0x180027e94  call    ?GetPropertyValue@PropertySetHelper@@AEBA?AV?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@PEAUHSTRING__@@@Z; PropertySetHelper::GetPropertyValue(HSTRING__ *)
0x180027e99  nop
0x180027e9a  mov     rdi, [rax]
0x180027e9d  mov     rax, [rdi]
0x180027ea0  mov     rbx, [rax+98h]
0x180027ea7  mov     rcx, [rsi]; string
0x180027eaa  call    cs:__imp_WindowsDeleteString
0x180027eb0  mov     qword ptr [rsi], 0
0x180027eb7  mov     rdx, rsi
0x180027eba  mov     rcx, rdi
0x180027ebd  mov     rax, rbx
0x180027ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ec5  mov     rcx, [rsp+38h]; this
0x180027eca  test    eax, eax
0x180027ecc  jns     short loc_180027EE3
0x180027ece  mov     r9d, eax; char *
0x180027ed1  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\cdp\\service\\cdpu"...
0x180027ed8  mov     edx, 30h ; '0'; void *
0x180027edd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180027ee3  lea     rcx, [rsp+38h+arg_18]
0x180027ee8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027eed  mov     rax, rsi
0x180027ef0  mov     rbx, [rsp+38h+arg_0]
0x180027ef5  mov     rsi, [rsp+38h+arg_10]
0x180027efa  add     rsp, 30h
0x180027efe  pop     rdi
0x180027eff  retn
```
