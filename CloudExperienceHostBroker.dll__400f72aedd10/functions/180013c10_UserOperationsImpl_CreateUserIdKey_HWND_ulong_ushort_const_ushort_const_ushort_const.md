# UserOperationsImpl::CreateUserIdKey(HWND__ *,ulong,ushort const *,ushort const *,ushort const *)

- ea: `0x180013c10`
- end: `0x180013d39`
- name: `?CreateUserIdKey@UserOperationsImpl@@UEAAJPEAUHWND__@@KPEBG11@Z`
- size: `297`
- prototype: `__int64 __fastcall(UserOperationsImpl *__hidden this, HWND, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x180013c10`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013c5e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013c5e`

## string_xrefs

- `0x180013d05`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UserOperationsImpl::CreateUserIdKey(
        UserOperationsImpl *this,
        HWND a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  HRESULT Instance; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  LPVOID v11; // rdi
  __int64 (__fastcall *v12)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  int ppv; // [rsp+20h] [rbp-58h]
  __int64 v15; // [rsp+40h] [rbp-38h] BYREF
  LPVOID v16[6]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v16[0] = 0;
  v15 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v16);
  Instance = CoCreateInstance(
               &GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684,
               0,
               1u,
               &GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99,
               v16);
  v9 = Instance;
  if ( Instance < 0 )
  {
    v10 = 294;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    goto LABEL_10;
  }
  v11 = v16[0];
  v12 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v16[0] + 32LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  Instance = v12(v11, &GUID_e19af835_9413_48a3_bdcc_28ba0286e348, &GUID_dee152d9_40a4_4bf9_8ac3_62cf1bb2203b, &v15);
  v9 = Instance;
  if ( Instance < 0 )
  {
    v10 = 295;
    goto LABEL_9;
  }
  ppv = (int)a5;
  Instance = (*(__int64 (__fastcall **)(__int64, HWND, _QWORD, const unsigned __int16 *))(*(_QWORD *)v15 + 24LL))(
               v15,
               a2,
               a3,
               a4);
  v9 = Instance;
  if ( Instance < 0 && Instance != -2147023673 && Instance != -2138701818 )
  {
    v10 = 302;
    goto LABEL_9;
  }
LABEL_10:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v16);
  return v9;
}

```

## disassembly

```asm
0x180013c10  push    rbx
0x180013c12  push    rbp
0x180013c13  push    rsi
0x180013c14  push    rdi
0x180013c15  push    r14
0x180013c17  sub     rsp, 50h
0x180013c1b  mov     rsi, r9
0x180013c1e  mov     ebp, r8d
0x180013c21  mov     r14, rdx
0x180013c24  mov     [rsp+78h+var_30], 0
0x180013c2d  mov     [rsp+78h+var_38], 0
0x180013c36  lea     rcx, [rsp+78h+var_30]
0x180013c3b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013c40  lea     rax, [rsp+78h+var_30]
0x180013c45  mov     [rsp+78h+ppv], rax; ppv
0x180013c4a  lea     r9, _GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99; riid
0x180013c51  xor     edx, edx; pUnkOuter
0x180013c53  lea     r8d, [rdx+1]; dwClsContext
0x180013c57  lea     rcx, _GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684; rclsid
0x180013c5e  call    cs:__imp_CoCreateInstance
0x180013c64  mov     ebx, eax
0x180013c66  test    eax, eax
0x180013c68  jns     short loc_180013C74
0x180013c6a  mov     edx, 126h
0x180013c6f  jmp     loc_180013D02
0x180013c74  mov     rdi, [rsp+78h+var_30]
0x180013c79  mov     rax, [rdi]
0x180013c7c  mov     rbx, [rax+20h]
0x180013c80  lea     rcx, [rsp+78h+var_38]
0x180013c85  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013c8a  lea     r9, [rsp+78h+var_38]
0x180013c8f  lea     r8, _GUID_dee152d9_40a4_4bf9_8ac3_62cf1bb2203b
0x180013c96  lea     rdx, _GUID_e19af835_9413_48a3_bdcc_28ba0286e348
0x180013c9d  mov     rcx, rdi
0x180013ca0  mov     rax, rbx
0x180013ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ca8  mov     ebx, eax
0x180013caa  test    eax, eax
0x180013cac  jns     short loc_180013CB5
0x180013cae  mov     edx, 127h
0x180013cb3  jmp     short loc_180013D02
0x180013cb5  mov     rcx, [rsp+78h+var_38]
0x180013cba  mov     rax, [rcx]
0x180013cbd  mov     rdx, [rsp+78h+arg_28]
0x180013cc5  mov     [rsp+78h+var_50], rdx
0x180013cca  mov     rdx, [rsp+78h+arg_20]
0x180013cd2  mov     [rsp+78h+ppv], rdx; int
0x180013cd7  mov     r9, rsi
0x180013cda  mov     r8d, ebp
0x180013cdd  mov     rdx, r14
0x180013ce0  mov     rax, [rax+18h]
0x180013ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ce9  mov     ebx, eax
0x180013ceb  test    eax, eax
0x180013ced  jns     short loc_180013D17
0x180013cef  cmp     eax, 800704C7h
0x180013cf4  jz      short loc_180013D17
0x180013cf6  cmp     eax, 80860006h
0x180013cfb  jz      short loc_180013D17
0x180013cfd  mov     edx, 12Eh; void *
0x180013d02  mov     r9d, eax; char *
0x180013d05  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x180013d0c  mov     rcx, [rsp+78h]; this
0x180013d11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013d16  nop
0x180013d17  lea     rcx, [rsp+78h+var_38]
0x180013d1c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013d21  nop
0x180013d22  lea     rcx, [rsp+78h+var_30]
0x180013d27  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013d2c  mov     eax, ebx
0x180013d2e  add     rsp, 50h
0x180013d32  pop     r14
0x180013d34  pop     rdi
0x180013d35  pop     rsi
0x180013d36  pop     rbp
0x180013d37  pop     rbx
0x180013d38  retn
```
