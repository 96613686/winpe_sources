# ScheduledTask::ScheduledTask(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)

- ea: `0x18000cad0`
- end: `0x18000cd53`
- name: `??0ScheduledTask@@AEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@0@Z`
- size: `643`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c514`

## callees

- `0x180005894`
- `0x180005f24`
- `0x18000760c`
- `0x18000cad0`
- `0x180010150`
- `0x180046010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000cce3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cce3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cb53`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cb53`

## string_xrefs

- `0x18000cb64`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18000cbe8`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18000cc2d`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18000cc6f`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18000ccb0`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18000cd12`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`

## pseudocode

```c
__int64 __fastcall ScheduledTask::ScheduledTask(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  OLECHAR **v4; // r14
  __int64 *v5; // r13
  __int64 *v6; // r12
  __int64 *v7; // r15
  HRESULT v8; // eax
  int v9; // eax
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, _QWORD, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, OLECHAR **); // r15
  OLECHAR *v21; // rbx
  int v22; // eax
  int ppv; // [rsp+28h] [rbp-99h]
  _QWORD v25[5]; // [rsp+30h] [rbp-91h] BYREF
  __int128 v26; // [rsp+58h] [rbp-69h] BYREF
  __int64 v27; // [rsp+68h] [rbp-59h]
  __int128 v28; // [rsp+78h] [rbp-49h] BYREF
  __int64 v29; // [rsp+88h] [rbp-39h]
  __int128 v30; // [rsp+98h] [rbp-29h] BYREF
  __int64 v31; // [rsp+A8h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+5Fh]
  LPVOID v34; // [rsp+138h] [rbp+77h] BYREF
  char v35; // [rsp+140h] [rbp+7Fh] BYREF

  *(_BYTE *)a1 = 0;
  *(_QWORD *)(a1 + 8) = *a3;
  *a3 = 0;
  v4 = (OLECHAR **)(a1 + 16);
  *(_QWORD *)(a1 + 16) = 0;
  v5 = (__int64 *)(a1 + 24);
  *(_QWORD *)(a1 + 24) = 0;
  v6 = (__int64 *)(a1 + 32);
  *(_QWORD *)(a1 + 32) = 0;
  v7 = (__int64 *)(a1 + 40);
  *(_QWORD *)(a1 + 40) = 0;
  v34 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  v8 = CoCreateInstance(
         &GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd,
         0,
         1u,
         &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
         &v34);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      (const char *)(unsigned int)v8,
      ppv);
  memset(&v25[1], 0, 24);
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v34 + 80LL))(
         v34,
         &v30,
         &v28,
         &v26);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      (const char *)(unsigned int)v9,
      (int)&v25[1]);
  v10 = v34;
  v11 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v34 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v5);
  v12 = v11(v10, *a2, v5);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      (const char *)(unsigned int)v12,
      (int)&v25[1]);
  v13 = *v5;
  v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*v5 + 104LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v6);
  v15 = v14(v13, *(_QWORD *)(a1 + 8), v6);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      (const char *)(unsigned int)v15,
      (int)&v25[1]);
  v16 = *v6;
  v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v6 + 152LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v7);
  v18 = v17(v16, v7);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x133,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      (const char *)(unsigned int)v18,
      (int)&v25[1]);
  v19 = *v7;
  v20 = *(__int64 (__fastcall **)(__int64, OLECHAR **))(*(_QWORD *)*v7 + 152LL);
  v21 = *v4;
  if ( *v4 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v35);
    SysFreeString(v21);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v35);
  }
  *v4 = 0;
  v22 = v20(v19, v4);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x134,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      (const char *)(unsigned int)v22,
      (int)&v25[1]);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  return a1;
}

```

## disassembly

```asm
0x18000cad0  mov     rax, rsp
0x18000cad3  mov     [rax+10h], rdx
0x18000cad7  mov     [rax+8], rcx
0x18000cadb  push    rbp
0x18000cadc  push    rbx
0x18000cadd  push    rsi
0x18000cade  push    rdi
0x18000cadf  push    r12
0x18000cae1  push    r13
0x18000cae3  push    r14
0x18000cae5  push    r15
0x18000cae7  lea     rbp, [rax-5Fh]
0x18000caeb  sub     rsp, 0D8h
0x18000caf2  movaps  xmmword ptr [rax-58h], xmm6
0x18000caf6  movaps  xmmword ptr [rax-68h], xmm7
0x18000cafa  mov     rsi, rcx
0x18000cafd  xor     ebx, ebx
0x18000caff  mov     [rcx], bl
0x18000cb01  mov     rax, [r8]
0x18000cb04  mov     [rcx+8], rax
0x18000cb08  mov     [r8], rbx
0x18000cb0b  lea     r14, [rcx+10h]
0x18000cb0f  mov     [r14], rbx
0x18000cb12  lea     r13, [rcx+18h]
0x18000cb16  mov     [r13+0], rbx
0x18000cb1a  lea     r12, [rcx+20h]
0x18000cb1e  mov     [r12], rbx
0x18000cb22  lea     r15, [rcx+28h]
0x18000cb26  mov     [r15], rbx
0x18000cb29  mov     [rbp+57h+arg_10], rbx
0x18000cb2d  lea     rcx, [rbp+57h+arg_10]
0x18000cb31  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cb36  lea     rax, [rbp+57h+arg_10]
0x18000cb3a  mov     [rsp+110h+ppv], rax; int
0x18000cb3f  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18000cb46  xor     edx, edx; pUnkOuter
0x18000cb48  lea     r8d, [rbx+1]; dwClsContext
0x18000cb4c  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x18000cb53  call    cs:__imp_CoCreateInstance
0x18000cb59  mov     rcx, [rbp+5Fh]; this
0x18000cb5d  test    eax, eax
0x18000cb5f  jns     short loc_18000CB76
0x18000cb61  mov     r9d, eax; char *
0x18000cb64  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18000cb6b  mov     edx, 12Dh; void *
0x18000cb70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cb76  mov     rcx, [rbp+57h+arg_10]
0x18000cb7a  xorps   xmm7, xmm7
0x18000cb7d  xor     eax, eax
0x18000cb7f  movq    xmm6, rax
0x18000cb84  xorps   xmm5, xmm5
0x18000cb87  movq    xmm4, rax
0x18000cb8c  xorps   xmm3, xmm3
0x18000cb8f  movq    xmm2, rax
0x18000cb94  xorps   xmm1, xmm1
0x18000cb97  movaps  xmmword ptr [rsp+110h+var_E8+8], xmm7
0x18000cb9c  movsd   [rbp+57h+var_D0], xmm6
0x18000cba1  movaps  [rbp+57h+var_C0], xmm5
0x18000cba5  movsd   [rbp+57h+var_B0], xmm4
0x18000cbaa  movaps  [rbp+57h+var_A0], xmm3
0x18000cbae  movsd   [rbp+57h+var_90], xmm2
0x18000cbb3  movaps  [rbp+57h+var_80], xmm1
0x18000cbb7  mov     [rbp+57h+var_70], rax
0x18000cbbb  mov     rax, [rcx]
0x18000cbbe  lea     rdx, [rsp+110h+var_E8+8]
0x18000cbc3  mov     [rsp+110h+ppv], rdx; int
0x18000cbc8  lea     r9, [rbp+57h+var_C0]
0x18000cbcc  lea     r8, [rbp+57h+var_A0]
0x18000cbd0  lea     rdx, [rbp+57h+var_80]
0x18000cbd4  mov     rax, [rax+50h]
0x18000cbd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbdd  mov     rcx, [rbp+5Fh]; this
0x18000cbe1  test    eax, eax
0x18000cbe3  jns     short loc_18000CBFA
0x18000cbe5  mov     r9d, eax; char *
0x18000cbe8  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18000cbef  mov     edx, 12Eh; void *
0x18000cbf4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cbfa  mov     rdi, [rbp+57h+arg_10]
0x18000cbfe  mov     rax, [rdi]
0x18000cc01  mov     rbx, [rax+38h]
0x18000cc05  mov     rcx, r13
0x18000cc08  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cc0d  mov     r8, r13
0x18000cc10  mov     rdx, [rbp+57h+arg_8]
0x18000cc14  mov     rdx, [rdx]
0x18000cc17  mov     rcx, rdi
0x18000cc1a  mov     rax, rbx
0x18000cc1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc22  mov     rcx, [rbp+5Fh]; this
0x18000cc26  test    eax, eax
0x18000cc28  jns     short loc_18000CC3F
0x18000cc2a  mov     r9d, eax; char *
0x18000cc2d  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18000cc34  mov     edx, 130h; void *
0x18000cc39  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cc3f  mov     rdi, [r13+0]
0x18000cc43  mov     rax, [rdi]
0x18000cc46  mov     rbx, [rax+68h]
0x18000cc4a  mov     rcx, r12
0x18000cc4d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cc52  mov     r8, r12
0x18000cc55  mov     rdx, [rsi+8]
0x18000cc59  mov     rcx, rdi
0x18000cc5c  mov     rax, rbx
0x18000cc5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc64  mov     rcx, [rbp+5Fh]; this
0x18000cc68  test    eax, eax
0x18000cc6a  jns     short loc_18000CC81
0x18000cc6c  mov     r9d, eax; char *
0x18000cc6f  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18000cc76  mov     edx, 132h; void *
0x18000cc7b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cc81  mov     rdi, [r12]
0x18000cc85  mov     rax, [rdi]
0x18000cc88  mov     rbx, [rax+98h]
0x18000cc8f  mov     rcx, r15
0x18000cc92  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cc97  mov     rdx, r15
0x18000cc9a  mov     rcx, rdi
0x18000cc9d  mov     rax, rbx
0x18000cca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cca5  mov     rcx, [rbp+5Fh]; this
0x18000cca9  test    eax, eax
0x18000ccab  jns     short loc_18000CCC2
0x18000ccad  mov     r9d, eax; char *
0x18000ccb0  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18000ccb7  mov     edx, 133h; void *
0x18000ccbc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000ccc2  mov     rdi, [r15]
0x18000ccc5  mov     rax, [rdi]
0x18000ccc8  mov     r15, [rax+98h]
0x18000cccf  mov     rbx, [r14]
0x18000ccd2  test    rbx, rbx
0x18000ccd5  jz      short loc_18000CCF2
0x18000ccd7  lea     rcx, [rbp+57h+arg_18]; this
0x18000ccdb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000cce0  mov     rcx, rbx; bstrString
0x18000cce3  call    cs:__imp_SysFreeString
0x18000cce9  lea     rcx, [rbp+57h+arg_18]; this
0x18000cced  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000ccf2  mov     qword ptr [r14], 0
0x18000ccf9  mov     rdx, r14
0x18000ccfc  mov     rcx, rdi
0x18000ccff  mov     rax, r15
0x18000cd02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd07  mov     rcx, [rbp+5Fh]; this
0x18000cd0b  test    eax, eax
0x18000cd0d  jns     short loc_18000CD24
0x18000cd0f  mov     r9d, eax; char *
0x18000cd12  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18000cd19  mov     edx, 134h; void *
0x18000cd1e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cd24  lea     rcx, [rbp+57h+arg_10]
0x18000cd28  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cd2d  nop
0x18000cd2e  mov     rax, rsi
0x18000cd31  lea     r11, [rsp+110h+var_38]
0x18000cd39  movaps  xmm6, xmmword ptr [r11-18h]
0x18000cd3e  movaps  xmm7, xmmword ptr [r11-28h]
0x18000cd43  mov     rsp, r11
0x18000cd46  pop     r15
0x18000cd48  pop     r14
0x18000cd4a  pop     r13
0x18000cd4c  pop     r12
0x18000cd4e  pop     rdi
0x18000cd4f  pop     rsi
0x18000cd50  pop     rbx
0x18000cd51  pop     rbp
0x18000cd52  retn
```
