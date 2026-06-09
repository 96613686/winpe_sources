# UserOperationsImpl::SaveAuthState(ushort const *,ushort const *,ushort const *,ulong,uchar *)

- ea: `0x180017a10`
- end: `0x180017b29`
- name: `?SaveAuthState@UserOperationsImpl@@UEAAJPEBG00KPEAE@Z`
- size: `281`
- prototype: `__int64 __fastcall(UserOperationsImpl *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x180017a10`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017a5e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017a5e`

## string_xrefs

- `0x180017ab8`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UserOperationsImpl::SaveAuthState(
        UserOperationsImpl *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5)
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
  if ( Instance >= 0 )
  {
    v11 = v16[0];
    v12 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v16[0] + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
    Instance = v12(v11, &GUID_e1f5aa5b_065c_4e29_b454_c1bbfe0819d2, &GUID_381d73bb_f00c_42e2_9d9c_5b5b3d88d71f, &v15);
    v9 = Instance;
    if ( Instance >= 0 )
    {
      ppv = a5;
      Instance = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v15 + 40LL))(
                   v15,
                   a2,
                   a3,
                   a4);
      v9 = Instance;
      if ( Instance >= 0 )
      {
        v9 = 0;
        goto LABEL_9;
      }
      v10 = 279;
    }
    else
    {
      v10 = 273;
    }
  }
  else
  {
    v10 = 272;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
    (const char *)(unsigned int)Instance,
    ppv);
LABEL_9:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v16);
  return v9;
}

```

## disassembly

```asm
0x180017a10  push    rbx
0x180017a12  push    rbp
0x180017a13  push    rsi
0x180017a14  push    rdi
0x180017a15  push    r14
0x180017a17  sub     rsp, 50h
0x180017a1b  mov     rsi, r9
0x180017a1e  mov     rbp, r8
0x180017a21  mov     r14, rdx
0x180017a24  mov     [rsp+78h+var_30], 0
0x180017a2d  mov     [rsp+78h+var_38], 0
0x180017a36  lea     rcx, [rsp+78h+var_30]
0x180017a3b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017a40  lea     rax, [rsp+78h+var_30]
0x180017a45  mov     [rsp+78h+ppv], rax; int
0x180017a4a  lea     r9, _GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99; riid
0x180017a51  xor     edx, edx; pUnkOuter
0x180017a53  lea     r8d, [rdx+1]; dwClsContext
0x180017a57  lea     rcx, _GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684; rclsid
0x180017a5e  call    cs:__imp_CoCreateInstance
0x180017a64  mov     ebx, eax
0x180017a66  test    eax, eax
0x180017a68  jns     short loc_180017A71
0x180017a6a  mov     edx, 110h
0x180017a6f  jmp     short loc_180017AB0
0x180017a71  mov     rdi, [rsp+78h+var_30]
0x180017a76  mov     rax, [rdi]
0x180017a79  mov     rbx, [rax+20h]
0x180017a7d  lea     rcx, [rsp+78h+var_38]
0x180017a82  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017a87  lea     r9, [rsp+78h+var_38]
0x180017a8c  lea     r8, _GUID_381d73bb_f00c_42e2_9d9c_5b5b3d88d71f
0x180017a93  lea     rdx, _GUID_e1f5aa5b_065c_4e29_b454_c1bbfe0819d2
0x180017a9a  mov     rcx, rdi
0x180017a9d  mov     rax, rbx
0x180017aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017aa5  mov     ebx, eax
0x180017aa7  test    eax, eax
0x180017aa9  jns     short loc_180017AC6
0x180017aab  mov     edx, 111h; void *
0x180017ab0  mov     rcx, [rsp+78h]; this
0x180017ab5  mov     r9d, eax; char *
0x180017ab8  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x180017abf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ac4  jmp     short loc_180017B07
0x180017ac6  mov     rcx, [rsp+78h+var_38]
0x180017acb  mov     rax, [rcx]
0x180017ace  mov     rdx, [rsp+78h+arg_28]
0x180017ad6  mov     [rsp+78h+var_50], rdx
0x180017adb  mov     edx, [rsp+78h+arg_20]
0x180017ae2  mov     dword ptr [rsp+78h+ppv], edx
0x180017ae6  mov     r9, rsi
0x180017ae9  mov     r8, rbp
0x180017aec  mov     rdx, r14
0x180017aef  mov     rax, [rax+28h]
0x180017af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017af8  mov     ebx, eax
0x180017afa  test    eax, eax
0x180017afc  jns     short loc_180017B05
0x180017afe  mov     edx, 117h
0x180017b03  jmp     short loc_180017AB0
0x180017b05  xor     ebx, ebx
0x180017b07  lea     rcx, [rsp+78h+var_38]
0x180017b0c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017b11  nop
0x180017b12  lea     rcx, [rsp+78h+var_30]
0x180017b17  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017b1c  mov     eax, ebx
0x180017b1e  add     rsp, 50h
0x180017b22  pop     r14
0x180017b24  pop     rdi
0x180017b25  pop     rsi
0x180017b26  pop     rbp
0x180017b27  pop     rbx
0x180017b28  retn
```
