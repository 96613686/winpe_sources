# UserOperationsImpl::GetAccountInformation(ushort const *,ushort const *,ushort * *,ushort * *)

- ea: `0x180014c50`
- end: `0x180014d75`
- name: `?GetAccountInformation@UserOperationsImpl@@UEAAJPEBG0PEAPEAG1@Z`
- size: `293`
- prototype: `__int64 __fastcall(UserOperationsImpl *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x180014c50`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014c97`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014c97`

## string_xrefs

- `0x180014caa`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`
- `0x180014d04`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UserOperationsImpl::GetAccountInformation(
        UserOperationsImpl *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5)
{
  HRESULT Instance; // eax
  unsigned int v9; // ebx
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdx
  int ppv; // [rsp+20h] [rbp-28h]
  __int64 v16; // [rsp+30h] [rbp-18h] BYREF
  LPVOID v17[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  v17[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
  Instance = CoCreateInstance(
               &GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684,
               0,
               1u,
               &GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99,
               v17);
  v9 = Instance;
  if ( Instance >= 0 )
  {
    v16 = 0;
    v10 = v17[0];
    v11 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v17[0] + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    v12 = v11(v10, &GUID_e1f5aa5b_065c_4e29_b454_c1bbfe0819d2, &GUID_381d73bb_f00c_42e2_9d9c_5b5b3d88d71f, &v16);
    v9 = v12;
    if ( v12 >= 0 )
    {
      ppv = (int)a5;
      v12 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v16 + 88LL))(
              v16,
              a2,
              a3,
              a4);
      v9 = v12;
      if ( v12 >= 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
        v9 = 0;
        goto LABEL_9;
      }
      v13 = 395;
    }
    else
    {
      v13 = 389;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v12,
      ppv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x182,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  }
LABEL_9:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
  return v9;
}

```

## disassembly

```asm
0x180014c50  push    rbp
0x180014c52  push    rbx
0x180014c53  push    rsi
0x180014c54  push    rdi
0x180014c55  push    r14
0x180014c57  push    r15
0x180014c59  mov     rbp, rsp
0x180014c5c  sub     rsp, 48h
0x180014c60  mov     rsi, r9
0x180014c63  mov     r14, r8
0x180014c66  mov     r15, rdx
0x180014c69  mov     [rbp+var_10], 0
0x180014c71  lea     rcx, [rbp+var_10]
0x180014c75  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014c7a  lea     rax, [rbp+var_10]
0x180014c7e  mov     qword ptr [rsp+48h+ppv], rax; int
0x180014c83  lea     r9, _GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99; riid
0x180014c8a  xor     edx, edx; pUnkOuter
0x180014c8c  lea     r8d, [rdx+1]; dwClsContext
0x180014c90  lea     rcx, _GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684; rclsid
0x180014c97  call    cs:__imp_CoCreateInstance
0x180014c9d  mov     ebx, eax
0x180014c9f  test    eax, eax
0x180014ca1  jns     short loc_180014CC0
0x180014ca3  mov     rcx, [rbp+30h]; this
0x180014ca7  mov     r9d, eax; char *
0x180014caa  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x180014cb1  mov     edx, 182h; void *
0x180014cb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014cbb  jmp     loc_180014D5D
0x180014cc0  mov     [rbp+var_18], 0
0x180014cc8  mov     rdi, [rbp+var_10]
0x180014ccc  mov     rax, [rdi]
0x180014ccf  mov     rbx, [rax+20h]
0x180014cd3  lea     rcx, [rbp+var_18]
0x180014cd7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014cdc  lea     r9, [rbp+var_18]
0x180014ce0  lea     r8, _GUID_381d73bb_f00c_42e2_9d9c_5b5b3d88d71f
0x180014ce7  lea     rdx, _GUID_e1f5aa5b_065c_4e29_b454_c1bbfe0819d2
0x180014cee  mov     rcx, rdi
0x180014cf1  mov     rax, rbx
0x180014cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cf9  mov     ebx, eax
0x180014cfb  test    eax, eax
0x180014cfd  jns     short loc_180014D23
0x180014cff  mov     edx, 185h; void *
0x180014d04  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x180014d0b  mov     r9d, eax; char *
0x180014d0e  mov     rcx, [rbp+30h]; this
0x180014d12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014d17  nop
0x180014d18  lea     rcx, [rbp+var_18]
0x180014d1c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014d21  jmp     short loc_180014D5D
0x180014d23  mov     rcx, [rbp+var_18]
0x180014d27  mov     rax, [rcx]
0x180014d2a  mov     rdx, [rbp+arg_20]
0x180014d2e  mov     qword ptr [rsp+48h+ppv], rdx
0x180014d33  mov     r9, rsi
0x180014d36  mov     r8, r14
0x180014d39  mov     rdx, r15
0x180014d3c  mov     rax, [rax+58h]
0x180014d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d45  mov     ebx, eax
0x180014d47  test    eax, eax
0x180014d49  jns     short loc_180014D52
0x180014d4b  mov     edx, 18Bh
0x180014d50  jmp     short loc_180014D04
0x180014d52  lea     rcx, [rbp+var_18]
0x180014d56  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014d5b  xor     ebx, ebx
0x180014d5d  lea     rcx, [rbp+var_10]
0x180014d61  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014d66  mov     eax, ebx
0x180014d68  add     rsp, 48h
0x180014d6c  pop     r15
0x180014d6e  pop     r14
0x180014d70  pop     rdi
0x180014d71  pop     rsi
0x180014d72  pop     rbx
0x180014d73  pop     rbp
0x180014d74  retn
```
