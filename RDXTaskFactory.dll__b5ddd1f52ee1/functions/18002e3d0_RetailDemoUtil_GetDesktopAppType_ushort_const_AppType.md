# RetailDemoUtil::GetDesktopAppType(ushort const *,AppType *)

- ea: `0x18002e3d0`
- end: `0x18002e5b2`
- name: `?GetDesktopAppType@RetailDemoUtil@@YAJPEBGPEAW4AppType@@@Z`
- size: `482`
- prototype: `__int64 __fastcall(RetailDemoUtil *__hidden this, const unsigned __int16 *, enum AppType *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800172c0`
- `0x180017d90`

## callees

- `0x180008bbc`
- `0x18000aa7c`
- `0x18002e3d0`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e418`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e418`

## string_xrefs

- `0x18002e42b`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002e483`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`
- `0x18002e4de`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoputil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RetailDemoUtil::GetDesktopAppType(RetailDemoUtil *this, unsigned __int16 *a2, enum AppType *a3)
{
  HRESULT v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  LPVOID v11; // rdi
  __int64 (__fastcall *v12)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, RetailDemoUtil *, _QWORD); // rbx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  int (__fastcall ***v25)(_QWORD, _QWORD, _QWORD); // rdi
  int (__fastcall *v26)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v27; // rdx
  __int64 v28; // r8
  int (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // rdi
  int (__fastcall *v30)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  int ppv; // [rsp+20h] [rbp-20h]
  __int64 v39; // [rsp+30h] [rbp-10h] BYREF
  __int64 v40; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  int (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp+38h] BYREF
  __int64 v43; // [rsp+80h] [rbp+40h] BYREF
  LPVOID v44; // [rsp+88h] [rbp+48h] BYREF

  *(_DWORD *)a2 = 0;
  v44 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44, a2, a3);
  v5 = CoCreateInstance(&CLSID_ImmersiveShell, 0, 4u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v44);
  v8 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
      (const char *)(unsigned int)v5,
      ppv);
    goto LABEL_13;
  }
  v43 = 0;
  v11 = v44;
  v12 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v44 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43, v6, v7);
  v13 = v12(v11, &GUID_1841c6d7_4f9d_42c0_af41_8747538f10e5, &GUID_1841c6d7_4f9d_42c0_af41_8747538f10e5, &v43);
  v8 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
      (const char *)(unsigned int)v13,
      ppv);
LABEL_5:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43, v16, v17);
    goto LABEL_13;
  }
  v42 = 0;
  v18 = v43;
  v19 = *(__int64 (__fastcall **)(__int64, RetailDemoUtil *, _QWORD))(*(_QWORD *)v43 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42, v14, v15);
  v20 = v19(v18, this, &v42);
  v8 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoputil.cpp",
      (const char *)(unsigned int)v20,
      ppv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42, v23, v24);
    goto LABEL_5;
  }
  v40 = 0;
  v39 = 0;
  v25 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v42;
  v26 = **v42;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40, v21, v22);
  if ( v26(v25, &GUID_f3527610_c76d_4316_ac8e_28651acf3df3, &v40) < 0 )
  {
    v29 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v42;
    v30 = **v42;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39, v27, v28);
    if ( v30(v29, &GUID_d8b456d0_bec6_4f57_bb1d_50559a14384b, &v39) >= 0 )
      *(_DWORD *)a2 = 1;
  }
  else
  {
    *(_DWORD *)a2 = 2;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39, v27, v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40, v31, v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42, v33, v34);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43, v35, v36);
  v8 = 0;
LABEL_13:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44, v9, v10);
  return v8;
}

```

## disassembly

```asm
0x18002e3d0  push    rbp
0x18002e3d2  push    rbx
0x18002e3d3  push    rsi
0x18002e3d4  push    rdi
0x18002e3d5  push    r14
0x18002e3d7  mov     rbp, rsp
0x18002e3da  sub     rsp, 40h
0x18002e3de  mov     rsi, rdx
0x18002e3e1  mov     r14, rcx
0x18002e3e4  mov     dword ptr [rdx], 0
0x18002e3ea  mov     [rbp+arg_18], 0
0x18002e3f2  lea     rcx, [rbp+arg_18]
0x18002e3f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e3fb  lea     rax, [rbp+arg_18]
0x18002e3ff  mov     qword ptr [rsp+40h+ppv], rax; int
0x18002e404  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18002e40b  xor     edx, edx; pUnkOuter
0x18002e40d  lea     r8d, [rdx+4]; dwClsContext
0x18002e411  lea     rcx, CLSID_ImmersiveShell; rclsid
0x18002e418  call    cs:__imp_CoCreateInstance
0x18002e41e  mov     ebx, eax
0x18002e420  test    eax, eax
0x18002e422  jns     short loc_18002E441
0x18002e424  mov     rcx, [rbp+28h]; this
0x18002e428  mov     r9d, eax; char *
0x18002e42b  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002e432  mov     edx, 46h ; 'F'; void *
0x18002e437  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e43c  jmp     loc_18002E59C
0x18002e441  mov     [rbp+arg_10], 0
0x18002e449  mov     rdi, [rbp+arg_18]
0x18002e44d  mov     rax, [rdi]
0x18002e450  mov     rbx, [rax+18h]
0x18002e454  lea     rcx, [rbp+arg_10]
0x18002e458  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e45d  lea     r9, [rbp+arg_10]
0x18002e461  lea     rdx, _GUID_1841c6d7_4f9d_42c0_af41_8747538f10e5
0x18002e468  mov     r8, rdx
0x18002e46b  mov     rcx, rdi
0x18002e46e  mov     rax, rbx
0x18002e471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e476  mov     ebx, eax
0x18002e478  test    eax, eax
0x18002e47a  jns     short loc_18002E4A3
0x18002e47c  mov     rcx, [rbp+28h]; this
0x18002e480  mov     r9d, eax; char *
0x18002e483  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002e48a  mov     edx, 48h ; 'H'; void *
0x18002e48f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e494  nop
0x18002e495  lea     rcx, [rbp+arg_10]
0x18002e499  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e49e  jmp     loc_18002E59C
0x18002e4a3  mov     [rbp+arg_8], 0
0x18002e4ab  mov     rdi, [rbp+arg_10]
0x18002e4af  mov     rax, [rdi]
0x18002e4b2  mov     rbx, [rax+40h]
0x18002e4b6  lea     rcx, [rbp+arg_8]
0x18002e4ba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e4bf  lea     r8, [rbp+arg_8]
0x18002e4c3  mov     rdx, r14
0x18002e4c6  mov     rcx, rdi
0x18002e4c9  mov     rax, rbx
0x18002e4cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4d1  mov     ebx, eax
0x18002e4d3  test    eax, eax
0x18002e4d5  jns     short loc_18002E4FB
0x18002e4d7  mov     rcx, [rbp+28h]; this
0x18002e4db  mov     r9d, eax; char *
0x18002e4de  lea     r8, aPcshellShellRe_26; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002e4e5  mov     edx, 4Ah ; 'J'; void *
0x18002e4ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e4ef  nop
0x18002e4f0  lea     rcx, [rbp+arg_8]
0x18002e4f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e4f9  jmp     short loc_18002E495
0x18002e4fb  mov     [rbp+var_8], 0
0x18002e503  mov     [rbp+var_10], 0
0x18002e50b  mov     rdi, [rbp+arg_8]
0x18002e50f  mov     rax, [rdi]
0x18002e512  mov     rbx, [rax]
0x18002e515  lea     rcx, [rbp+var_8]
0x18002e519  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e51e  lea     r8, [rbp+var_8]
0x18002e522  lea     rdx, _GUID_f3527610_c76d_4316_ac8e_28651acf3df3
0x18002e529  mov     rcx, rdi
0x18002e52c  mov     rax, rbx
0x18002e52f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e534  test    eax, eax
0x18002e536  js      short loc_18002E540
0x18002e538  mov     dword ptr [rsi], 2
0x18002e53e  jmp     short loc_18002E573
0x18002e540  mov     rdi, [rbp+arg_8]
0x18002e544  mov     rax, [rdi]
0x18002e547  mov     rbx, [rax]
0x18002e54a  lea     rcx, [rbp+var_10]
0x18002e54e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e553  lea     r8, [rbp+var_10]
0x18002e557  lea     rdx, _GUID_d8b456d0_bec6_4f57_bb1d_50559a14384b
0x18002e55e  mov     rcx, rdi
0x18002e561  mov     rax, rbx
0x18002e564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e569  test    eax, eax
0x18002e56b  js      short loc_18002E573
0x18002e56d  mov     dword ptr [rsi], 1
0x18002e573  lea     rcx, [rbp+var_10]
0x18002e577  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e57c  nop
0x18002e57d  lea     rcx, [rbp+var_8]
0x18002e581  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e586  nop
0x18002e587  lea     rcx, [rbp+arg_8]
0x18002e58b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e590  nop
0x18002e591  lea     rcx, [rbp+arg_10]
0x18002e595  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e59a  xor     ebx, ebx
0x18002e59c  lea     rcx, [rbp+arg_18]
0x18002e5a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e5a5  mov     eax, ebx
0x18002e5a7  add     rsp, 40h
0x18002e5ab  pop     r14
0x18002e5ad  pop     rdi
0x18002e5ae  pop     rsi
0x18002e5af  pop     rbx
0x18002e5b0  pop     rbp
0x18002e5b1  retn
```
