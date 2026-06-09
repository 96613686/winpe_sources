# _lambda_86689344bc66a1e4ae0e21c1a30e3fbd_::operator()

- ea: `0x180033ec0`
- end: `0x180033f8e`
- name: `_lambda_86689344bc66a1e4ae0e21c1a30e3fbd_::operator()`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180034a10`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x180033ec0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033edc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033eeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033edc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033eeb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033f25`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033f25`

## string_xrefs

- `0x180033f5a`: `shell\cloudexperiencehost\broker\lib\retaildemo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_86689344bc66a1e4ae0e21c1a30e3fbd_::operator()(HSTRING *a1, void *a2)
{
  PCWSTR StringRawBuffer; // rdi
  PCWSTR v4; // rsi
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v11; // [rsp+48h] [rbp+10h] BYREF

  v11 = a2;
  StringRawBuffer = WindowsGetStringRawBuffer(*a1, 0);
  v4 = WindowsGetStringRawBuffer(a1[2], 0);
  v11 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  v5 = CoCreateInstance(
         &GUID_de8dea9c_cc35_4a6e_8a17_f0c611f249a4,
         0,
         4u,
         &GUID_3308d940_83d8_4b26_887f_d0c45ade2ffc,
         &v11);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, PCWSTR, PCWSTR))(*(_QWORD *)v11 + 24LL))(v11, StringRawBuffer, v4);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v6 = 0;
      goto LABEL_7;
    }
    v7 = 129;
  }
  else
  {
    v7 = 128;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\retaildemo.cpp",
    (const char *)(unsigned int)v5,
    ppv);
LABEL_7:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  return v6;
}

```

## disassembly

```asm
0x180033ec0  mov     [rsp+arg_0], rbx
0x180033ec5  mov     [rsp+arg_10], rsi
0x180033eca  mov     [rsp+arg_8], rdx
0x180033ecf  push    rdi
0x180033ed0  sub     rsp, 30h
0x180033ed4  mov     rbx, rcx
0x180033ed7  xor     edx, edx; length
0x180033ed9  mov     rcx, [rcx]; string
0x180033edc  call    cs:__imp_WindowsGetStringRawBuffer
0x180033ee2  mov     rdi, rax
0x180033ee5  xor     edx, edx; length
0x180033ee7  mov     rcx, [rbx+10h]; string
0x180033eeb  call    cs:__imp_WindowsGetStringRawBuffer
0x180033ef1  mov     rsi, rax
0x180033ef4  mov     [rsp+38h+arg_8], 0
0x180033efd  lea     rcx, [rsp+38h+arg_8]
0x180033f02  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180033f07  lea     rax, [rsp+38h+arg_8]
0x180033f0c  mov     qword ptr [rsp+38h+ppv], rax; int
0x180033f11  lea     r9, _GUID_3308d940_83d8_4b26_887f_d0c45ade2ffc; riid
0x180033f18  xor     edx, edx; pUnkOuter
0x180033f1a  lea     r8d, [rdx+4]; dwClsContext
0x180033f1e  lea     rcx, _GUID_de8dea9c_cc35_4a6e_8a17_f0c611f249a4; rclsid
0x180033f25  call    cs:__imp_CoCreateInstance
0x180033f2b  mov     ebx, eax
0x180033f2d  test    eax, eax
0x180033f2f  jns     short loc_180033F38
0x180033f31  mov     edx, 80h
0x180033f36  jmp     short loc_180033F5A
0x180033f38  mov     rcx, [rsp+38h+arg_8]
0x180033f3d  mov     rax, [rcx]
0x180033f40  mov     r8, rsi
0x180033f43  mov     rdx, rdi
0x180033f46  mov     rax, [rax+18h]
0x180033f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f4f  mov     ebx, eax
0x180033f51  test    eax, eax
0x180033f53  jns     short loc_180033F70
0x180033f55  mov     edx, 81h; void *
0x180033f5a  lea     r8, aShellCloudexpe_3; "shell\\cloudexperiencehost\\broker\\lib"...
0x180033f61  mov     r9d, eax; char *
0x180033f64  mov     rcx, [rsp+38h]; this
0x180033f69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033f6e  jmp     short loc_180033F72
0x180033f70  xor     ebx, ebx
0x180033f72  lea     rcx, [rsp+38h+arg_8]
0x180033f77  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180033f7c  mov     eax, ebx
0x180033f7e  mov     rbx, [rsp+38h+arg_0]
0x180033f83  mov     rsi, [rsp+38h+arg_10]
0x180033f88  add     rsp, 30h
0x180033f8c  pop     rdi
0x180033f8d  retn
```
