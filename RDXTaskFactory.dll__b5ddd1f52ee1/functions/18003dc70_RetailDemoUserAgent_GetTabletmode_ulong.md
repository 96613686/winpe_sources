# RetailDemoUserAgent::GetTabletmode(ulong *)

- ea: `0x18003dc70`
- end: `0x18003dd90`
- name: `?GetTabletmode@RetailDemoUserAgent@@UEAAJPEAK@Z`
- size: `288`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180008bbc`
- `0x18000aa7c`
- `0x18003dc70`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003dcb8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003dcb8`

## string_xrefs

- `0x18003dccb`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003dd21`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RetailDemoUserAgent::GetTabletmode(RetailDemoUserAgent *this, unsigned int *a2, __int64 a3)
{
  HRESULT v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  int ppv; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  unsigned int v21; // [rsp+58h] [rbp+28h] BYREF
  __int64 v22; // [rsp+60h] [rbp+30h] BYREF
  LPVOID v23; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  v23 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23, a2, a3);
  v4 = CoCreateInstance(&CLSID_ImmersiveShell, 0, 0x404u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v23);
  v7 = v4;
  if ( v4 >= 0 )
  {
    v22 = 0;
    v10 = v23;
    v11 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v23 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22, v5, v6);
    v12 = v11(v10, &GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a, &GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a, &v22);
    v7 = v12;
    if ( v12 >= 0 )
    {
      v21 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v22 + 24LL))(v22, &v21);
      v7 = v12;
      if ( v12 >= 0 )
      {
        *a2 = v21;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22, v16, v17);
        v7 = 0;
        goto LABEL_9;
      }
      v13 = 2119;
    }
    else
    {
      v13 = 2116;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v12,
      ppv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22, v14, v15);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x841,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  }
LABEL_9:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23, v8, v9);
  return v7;
}

```

## disassembly

```asm
0x18003dc70  mov     [rsp-18h+arg_0], rbx
0x18003dc75  push    rbp
0x18003dc76  push    rsi
0x18003dc77  push    rdi
0x18003dc78  mov     rbp, rsp
0x18003dc7b  sub     rsp, 30h
0x18003dc7f  mov     rsi, rdx
0x18003dc82  mov     dword ptr [rdx], 0
0x18003dc88  mov     [rbp+arg_18], 0
0x18003dc90  lea     rcx, [rbp+arg_18]
0x18003dc94  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003dc99  lea     rax, [rbp+arg_18]
0x18003dc9d  mov     qword ptr [rsp+30h+ppv], rax; int
0x18003dca2  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18003dca9  xor     edx, edx; pUnkOuter
0x18003dcab  mov     r8d, 404h; dwClsContext
0x18003dcb1  lea     rcx, CLSID_ImmersiveShell; rclsid
0x18003dcb8  call    cs:__imp_CoCreateInstance
0x18003dcbe  mov     ebx, eax
0x18003dcc0  test    eax, eax
0x18003dcc2  jns     short loc_18003DCE1
0x18003dcc4  mov     rcx, [rbp+18h]; this
0x18003dcc8  mov     r9d, eax; char *
0x18003dccb  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003dcd2  mov     edx, 841h; void *
0x18003dcd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dcdc  jmp     loc_18003DD78
0x18003dce1  mov     [rbp+arg_10], 0
0x18003dce9  mov     rdi, [rbp+arg_18]
0x18003dced  mov     rax, [rdi]
0x18003dcf0  mov     rbx, [rax+18h]
0x18003dcf4  lea     rcx, [rbp+arg_10]
0x18003dcf8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003dcfd  lea     r9, [rbp+arg_10]
0x18003dd01  lea     rdx, _GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a
0x18003dd08  mov     r8, rdx
0x18003dd0b  mov     rcx, rdi
0x18003dd0e  mov     rax, rbx
0x18003dd11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd16  mov     ebx, eax
0x18003dd18  test    eax, eax
0x18003dd1a  jns     short loc_18003DD40
0x18003dd1c  mov     edx, 844h; void *
0x18003dd21  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003dd28  mov     r9d, eax; char *
0x18003dd2b  mov     rcx, [rbp+18h]; this
0x18003dd2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dd34  nop
0x18003dd35  lea     rcx, [rbp+arg_10]
0x18003dd39  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003dd3e  jmp     short loc_18003DD78
0x18003dd40  mov     [rbp+arg_8], 0
0x18003dd47  mov     rcx, [rbp+arg_10]
0x18003dd4b  mov     rax, [rcx]
0x18003dd4e  lea     rdx, [rbp+arg_8]
0x18003dd52  mov     rax, [rax+18h]
0x18003dd56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd5b  mov     ebx, eax
0x18003dd5d  test    eax, eax
0x18003dd5f  jns     short loc_18003DD68
0x18003dd61  mov     edx, 847h
0x18003dd66  jmp     short loc_18003DD21
0x18003dd68  mov     eax, [rbp+arg_8]
0x18003dd6b  mov     [rsi], eax
0x18003dd6d  lea     rcx, [rbp+arg_10]
0x18003dd71  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003dd76  xor     ebx, ebx
0x18003dd78  lea     rcx, [rbp+arg_18]
0x18003dd7c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003dd81  mov     eax, ebx
0x18003dd83  mov     rbx, [rsp+30h+arg_0]
0x18003dd88  add     rsp, 30h
0x18003dd8c  pop     rdi
0x18003dd8d  pop     rsi
0x18003dd8e  pop     rbp
0x18003dd8f  retn
```
