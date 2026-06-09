# _lambda_8ecd11ac5a12bfd53b88480beac20eaf_::operator()

- ea: `0x180033f94`
- end: `0x180034054`
- name: `_lambda_8ecd11ac5a12bfd53b88480beac20eaf_::operator()`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180034af0`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x180033f94`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033fb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033fb0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033fea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033fea`

## string_xrefs

- `0x180034020`: `shell\cloudexperiencehost\broker\lib\retaildemo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_8ecd11ac5a12bfd53b88480beac20eaf_::operator()(__int64 a1, void *a2)
{
  PCWSTR StringRawBuffer; // rsi
  HRESULT v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v10; // [rsp+48h] [rbp+10h] BYREF

  v10 = a2;
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)a1, 0);
  v10 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  v4 = CoCreateInstance(
         &GUID_de8dea9c_cc35_4a6e_8a17_f0c611f249a4,
         0,
         4u,
         &GUID_3308d940_83d8_4b26_887f_d0c45ade2ffc,
         &v10);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, PCWSTR, _QWORD))(*(_QWORD *)v10 + 32LL))(
           v10,
           StringRawBuffer,
           *(unsigned int *)(a1 + 16));
    v5 = v4;
    if ( v4 >= 0 )
    {
      v5 = 0;
      goto LABEL_7;
    }
    v6 = 151;
  }
  else
  {
    v6 = 150;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\retaildemo.cpp",
    (const char *)(unsigned int)v4,
    ppv);
LABEL_7:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  return v5;
}

```

## disassembly

```asm
0x180033f94  mov     [rsp+arg_0], rbx
0x180033f99  mov     [rsp+arg_10], rsi
0x180033f9e  mov     [rsp+arg_8], rdx
0x180033fa3  push    rdi
0x180033fa4  sub     rsp, 30h
0x180033fa8  mov     rdi, rcx
0x180033fab  xor     edx, edx; length
0x180033fad  mov     rcx, [rcx]; string
0x180033fb0  call    cs:__imp_WindowsGetStringRawBuffer
0x180033fb6  mov     rsi, rax
0x180033fb9  mov     [rsp+38h+arg_8], 0
0x180033fc2  lea     rcx, [rsp+38h+arg_8]
0x180033fc7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180033fcc  lea     rax, [rsp+38h+arg_8]
0x180033fd1  mov     qword ptr [rsp+38h+ppv], rax; int
0x180033fd6  lea     r9, _GUID_3308d940_83d8_4b26_887f_d0c45ade2ffc; riid
0x180033fdd  xor     edx, edx; pUnkOuter
0x180033fdf  lea     r8d, [rdx+4]; dwClsContext
0x180033fe3  lea     rcx, _GUID_de8dea9c_cc35_4a6e_8a17_f0c611f249a4; rclsid
0x180033fea  call    cs:__imp_CoCreateInstance
0x180033ff0  mov     ebx, eax
0x180033ff2  test    eax, eax
0x180033ff4  jns     short loc_180033FFD
0x180033ff6  mov     edx, 96h
0x180033ffb  jmp     short loc_180034020
0x180033ffd  mov     rcx, [rsp+38h+arg_8]
0x180034002  mov     rax, [rcx]
0x180034005  mov     r8d, [rdi+10h]
0x180034009  mov     rdx, rsi
0x18003400c  mov     rax, [rax+20h]
0x180034010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034015  mov     ebx, eax
0x180034017  test    eax, eax
0x180034019  jns     short loc_180034036
0x18003401b  mov     edx, 97h; void *
0x180034020  lea     r8, aShellCloudexpe_3; "shell\\cloudexperiencehost\\broker\\lib"...
0x180034027  mov     r9d, eax; char *
0x18003402a  mov     rcx, [rsp+38h]; this
0x18003402f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034034  jmp     short loc_180034038
0x180034036  xor     ebx, ebx
0x180034038  lea     rcx, [rsp+38h+arg_8]
0x18003403d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034042  mov     eax, ebx
0x180034044  mov     rbx, [rsp+38h+arg_0]
0x180034049  mov     rsi, [rsp+38h+arg_10]
0x18003404e  add     rsp, 30h
0x180034052  pop     rdi
0x180034053  retn
```
