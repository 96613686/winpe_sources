# UserOperationsImpl::CanUserResetNgcPin(int *,ulong *,ushort * *,ushort * *,ushort * *)

- ea: `0x180012c50`
- end: `0x180012d7e`
- name: `?CanUserResetNgcPin@UserOperationsImpl@@UEAAJPEAHPEAKPEAPEAG22@Z`
- size: `302`
- prototype: `__int64 __fastcall(UserOperationsImpl *__hidden this, int *, unsigned int *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x180012c50`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012c97`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012c97`

## string_xrefs

- `0x180012caa`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`
- `0x180012d04`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UserOperationsImpl::CanUserResetNgcPin(
        UserOperationsImpl *this,
        int *a2,
        unsigned int *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5)
{
  HRESULT Instance; // eax
  unsigned int v9; // ebx
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdx
  int ppv; // [rsp+20h] [rbp-38h]
  __int64 v16; // [rsp+40h] [rbp-18h] BYREF
  LPVOID v17[2]; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]

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
    v12 = v11(v10, &GUID_e19af835_9413_48a3_bdcc_28ba0286e348, &GUID_dee152d9_40a4_4bf9_8ac3_62cf1bb2203b, &v16);
    v9 = v12;
    if ( v12 >= 0 )
    {
      ppv = (int)a5;
      v12 = (*(__int64 (__fastcall **)(__int64, int *, unsigned int *, unsigned __int16 **))(*(_QWORD *)v16 + 48LL))(
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
      v13 = 415;
    }
    else
    {
      v13 = 412;
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
      (void *)0x199,
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
0x180012c50  push    rbp
0x180012c52  push    rbx
0x180012c53  push    rsi
0x180012c54  push    rdi
0x180012c55  push    r14
0x180012c57  push    r15
0x180012c59  mov     rbp, rsp
0x180012c5c  sub     rsp, 58h
0x180012c60  mov     rsi, r9
0x180012c63  mov     r14, r8
0x180012c66  mov     r15, rdx
0x180012c69  mov     [rbp+var_10], 0
0x180012c71  lea     rcx, [rbp+var_10]
0x180012c75  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012c7a  lea     rax, [rbp+var_10]
0x180012c7e  mov     [rsp+58h+ppv], rax; int
0x180012c83  lea     r9, _GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99; riid
0x180012c8a  xor     edx, edx; pUnkOuter
0x180012c8c  lea     r8d, [rdx+1]; dwClsContext
0x180012c90  lea     rcx, _GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684; rclsid
0x180012c97  call    cs:__imp_CoCreateInstance
0x180012c9d  mov     ebx, eax
0x180012c9f  test    eax, eax
0x180012ca1  jns     short loc_180012CC0
0x180012ca3  mov     rcx, [rbp+30h]; this
0x180012ca7  mov     r9d, eax; char *
0x180012caa  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x180012cb1  mov     edx, 199h; void *
0x180012cb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012cbb  jmp     loc_180012D66
0x180012cc0  mov     [rbp+var_18], 0
0x180012cc8  mov     rdi, [rbp+var_10]
0x180012ccc  mov     rax, [rdi]
0x180012ccf  mov     rbx, [rax+20h]
0x180012cd3  lea     rcx, [rbp+var_18]
0x180012cd7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012cdc  lea     r9, [rbp+var_18]
0x180012ce0  lea     r8, _GUID_dee152d9_40a4_4bf9_8ac3_62cf1bb2203b
0x180012ce7  lea     rdx, _GUID_e19af835_9413_48a3_bdcc_28ba0286e348
0x180012cee  mov     rcx, rdi
0x180012cf1  mov     rax, rbx
0x180012cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cf9  mov     ebx, eax
0x180012cfb  test    eax, eax
0x180012cfd  jns     short loc_180012D23
0x180012cff  mov     edx, 19Ch; void *
0x180012d04  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x180012d0b  mov     r9d, eax; char *
0x180012d0e  mov     rcx, [rbp+30h]; this
0x180012d12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d17  nop
0x180012d18  lea     rcx, [rbp+var_18]
0x180012d1c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012d21  jmp     short loc_180012D66
0x180012d23  mov     rcx, [rbp+var_18]
0x180012d27  mov     rax, [rcx]
0x180012d2a  mov     rdx, [rbp+arg_28]
0x180012d2e  mov     [rsp+58h+var_30], rdx
0x180012d33  mov     rdx, [rbp+arg_20]
0x180012d37  mov     [rsp+58h+ppv], rdx
0x180012d3c  mov     r9, rsi
0x180012d3f  mov     r8, r14
0x180012d42  mov     rdx, r15
0x180012d45  mov     rax, [rax+30h]
0x180012d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d4e  mov     ebx, eax
0x180012d50  test    eax, eax
0x180012d52  jns     short loc_180012D5B
0x180012d54  mov     edx, 19Fh
0x180012d59  jmp     short loc_180012D04
0x180012d5b  lea     rcx, [rbp+var_18]
0x180012d5f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012d64  xor     ebx, ebx
0x180012d66  lea     rcx, [rbp+var_10]
0x180012d6a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012d6f  mov     eax, ebx
0x180012d71  add     rsp, 58h
0x180012d75  pop     r15
0x180012d77  pop     r14
0x180012d79  pop     rdi
0x180012d7a  pop     rsi
0x180012d7b  pop     rbx
0x180012d7c  pop     rbp
0x180012d7d  retn
```
