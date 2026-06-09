# UserOperationsImpl::RecoverPin(HWND__ *,ushort const *)

- ea: `0x180016d30`
- end: `0x180016e51`
- name: `?RecoverPin@UserOperationsImpl@@UEAAJPEAUHWND__@@PEBG@Z`
- size: `289`
- prototype: `__int64 __fastcall(UserOperationsImpl *__hidden this, HWND, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x180016d30`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016d79`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016d79`

## string_xrefs

- `0x180016d8c`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`
- `0x180016de6`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UserOperationsImpl::RecoverPin(UserOperationsImpl *this, HWND a2, const unsigned __int16 *a3)
{
  HRESULT Instance; // eax
  unsigned int v6; // ebx
  LPVOID v7; // rdi
  __int64 (__fastcall *v8)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdx
  int ppv; // [rsp+20h] [rbp-20h]
  LPVOID v13[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  __int64 v15; // [rsp+78h] [rbp+38h] BYREF

  v13[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v13);
  Instance = CoCreateInstance(
               &GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684,
               0,
               1u,
               &GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99,
               v13);
  v6 = Instance;
  if ( Instance >= 0 )
  {
    v15 = 0;
    v7 = v13[0];
    v8 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v13[0] + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
    v9 = v8(v7, &GUID_e19af835_9413_48a3_bdcc_28ba0286e348, &GUID_dee152d9_40a4_4bf9_8ac3_62cf1bb2203b, &v15);
    v6 = v9;
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, HWND, const unsigned __int16 *))(*(_QWORD *)v15 + 32LL))(v15, a2, a3);
      v6 = v9;
      if ( v9 >= 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
        v6 = 0;
        goto LABEL_9;
      }
      v10 = 431;
    }
    else
    {
      v10 = 429;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  }
LABEL_9:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v13);
  return v6;
}

```

## disassembly

```asm
0x180016d30  mov     [rsp-18h+arg_0], rbx
0x180016d35  mov     [rsp-18h+arg_8], rsi
0x180016d3a  push    rbp
0x180016d3b  push    rdi
0x180016d3c  push    r14
0x180016d3e  mov     rbp, rsp
0x180016d41  sub     rsp, 40h
0x180016d45  mov     rsi, r8
0x180016d48  mov     r14, rdx
0x180016d4b  mov     [rbp+var_10], 0
0x180016d53  lea     rcx, [rbp+var_10]
0x180016d57  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016d5c  lea     rax, [rbp+var_10]
0x180016d60  mov     qword ptr [rsp+40h+ppv], rax; int
0x180016d65  lea     r9, _GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99; riid
0x180016d6c  xor     edx, edx; pUnkOuter
0x180016d6e  lea     r8d, [rdx+1]; dwClsContext
0x180016d72  lea     rcx, _GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684; rclsid
0x180016d79  call    cs:__imp_CoCreateInstance
0x180016d7f  mov     ebx, eax
0x180016d81  test    eax, eax
0x180016d83  jns     short loc_180016DA2
0x180016d85  mov     rcx, [rbp+18h]; this
0x180016d89  mov     r9d, eax; char *
0x180016d8c  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x180016d93  mov     edx, 1AAh; void *
0x180016d98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016d9d  jmp     loc_180016E33
0x180016da2  mov     [rbp+arg_18], 0
0x180016daa  mov     rdi, [rbp+var_10]
0x180016dae  mov     rax, [rdi]
0x180016db1  mov     rbx, [rax+20h]
0x180016db5  lea     rcx, [rbp+arg_18]
0x180016db9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016dbe  lea     r9, [rbp+arg_18]
0x180016dc2  lea     r8, _GUID_dee152d9_40a4_4bf9_8ac3_62cf1bb2203b
0x180016dc9  lea     rdx, _GUID_e19af835_9413_48a3_bdcc_28ba0286e348
0x180016dd0  mov     rcx, rdi
0x180016dd3  mov     rax, rbx
0x180016dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ddb  mov     ebx, eax
0x180016ddd  test    eax, eax
0x180016ddf  jns     short loc_180016E05
0x180016de1  mov     edx, 1ADh; void *
0x180016de6  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x180016ded  mov     r9d, eax; char *
0x180016df0  mov     rcx, [rbp+18h]; this
0x180016df4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016df9  nop
0x180016dfa  lea     rcx, [rbp+arg_18]
0x180016dfe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016e03  jmp     short loc_180016E33
0x180016e05  mov     rcx, [rbp+arg_18]
0x180016e09  mov     rax, [rcx]
0x180016e0c  mov     r8, rsi
0x180016e0f  mov     rdx, r14
0x180016e12  mov     rax, [rax+20h]
0x180016e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e1b  mov     ebx, eax
0x180016e1d  test    eax, eax
0x180016e1f  jns     short loc_180016E28
0x180016e21  mov     edx, 1AFh
0x180016e26  jmp     short loc_180016DE6
0x180016e28  lea     rcx, [rbp+arg_18]
0x180016e2c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016e31  xor     ebx, ebx
0x180016e33  lea     rcx, [rbp+var_10]
0x180016e37  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016e3c  mov     eax, ebx
0x180016e3e  mov     rbx, [rsp+40h+arg_0]
0x180016e43  mov     rsi, [rsp+40h+arg_8]
0x180016e48  add     rsp, 40h
0x180016e4c  pop     r14
0x180016e4e  pop     rdi
0x180016e4f  pop     rbp
0x180016e50  retn
```
