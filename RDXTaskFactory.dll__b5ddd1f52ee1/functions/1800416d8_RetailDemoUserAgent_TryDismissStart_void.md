# RetailDemoUserAgent::TryDismissStart(void)

- ea: `0x1800416d8`
- end: `0x180041815`
- name: `?TryDismissStart@RetailDemoUserAgent@@AEAAJXZ`
- size: `317`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003ad30`

## callees

- `0x180008bbc`
- `0x18000aa7c`
- `0x1800416d8`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041728`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041728`

## string_xrefs

- `0x180041779`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x1800417ca`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RetailDemoUserAgent::TryDismissStart(RetailDemoUserAgent *this, __int64 a2, __int64 a3)
{
  _QWORD *v3; // rsi
  HRESULT v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // ebx
  __int64 v8; // rdx
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, SID *, GUID *, _QWORD *); // rbx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v16; // rdx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v19; // [rsp+40h] [rbp+8h] BYREF
  LPVOID v20; // [rsp+48h] [rbp+10h] BYREF

  v3 = (_QWORD *)((char *)this + 144);
  if ( !*((_QWORD *)this + 18) )
  {
    v20 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20, a2, a3);
    v4 = CoCreateInstance(&CLSID_ImmersiveShell, 0, 4u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v20);
    v7 = v4;
    if ( v4 < 0 )
    {
      v8 = 2447;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v4,
        ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20, v13, v14);
      return (unsigned int)v7;
    }
    v9 = v20;
    v10 = *(__int64 (__fastcall **)(LPVOID, SID *, GUID *, _QWORD *))(*(_QWORD *)v20 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v3, v5, v6);
    v4 = v10(v9, &SID_ImmersiveLauncher, &GUID_d8d60399_a0f1_f987_5551_321fd1b49864, v3);
    v7 = v4;
    if ( v4 < 0 )
    {
      v8 = 2448;
      goto LABEL_6;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20, v11, v12);
  }
  v19 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 56LL))(*v3, &v19);
  if ( v7 < 0 )
  {
    v16 = 2452;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v7,
      ppv);
    return (unsigned int)v7;
  }
  if ( v19 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 48LL))(*v3);
    if ( v7 < 0 )
    {
      v16 = 2456;
      goto LABEL_11;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800416d8  mov     rax, rsp
0x1800416db  mov     [rax+18h], rbx
0x1800416df  mov     [rax+20h], rsi
0x1800416e3  push    rdi
0x1800416e4  sub     rsp, 30h
0x1800416e8  lea     rsi, [rcx+90h]
0x1800416ef  cmp     qword ptr [rsi], 0
0x1800416f3  jnz     loc_1800417A3
0x1800416f9  mov     qword ptr [rax+10h], 0
0x180041701  lea     rcx, [rax+10h]
0x180041705  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004170a  lea     rax, [rsp+38h+arg_8]
0x18004170f  mov     qword ptr [rsp+38h+ppv], rax; int
0x180041714  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18004171b  xor     edx, edx; pUnkOuter
0x18004171d  lea     r8d, [rdx+4]; dwClsContext
0x180041721  lea     rcx, CLSID_ImmersiveShell; rclsid
0x180041728  call    cs:__imp_CoCreateInstance
0x18004172e  mov     ebx, eax
0x180041730  test    eax, eax
0x180041732  jns     short loc_18004173B
0x180041734  mov     edx, 98Fh
0x180041739  jmp     short loc_180041776
0x18004173b  mov     rdi, [rsp+38h+arg_8]
0x180041740  mov     rax, [rdi]
0x180041743  mov     rbx, [rax+18h]
0x180041747  mov     rcx, rsi
0x18004174a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004174f  mov     r9, rsi
0x180041752  lea     r8, _GUID_d8d60399_a0f1_f987_5551_321fd1b49864
0x180041759  lea     rdx, SID_ImmersiveLauncher
0x180041760  mov     rcx, rdi
0x180041763  mov     rax, rbx
0x180041766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004176b  mov     ebx, eax
0x18004176d  test    eax, eax
0x18004176f  jns     short loc_180041799
0x180041771  mov     edx, 990h; void *
0x180041776  mov     r9d, eax; char *
0x180041779  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180041780  mov     rcx, [rsp+38h]; this
0x180041785  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004178a  nop
0x18004178b  lea     rcx, [rsp+38h+arg_8]
0x180041790  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180041795  mov     eax, ebx
0x180041797  jmp     short loc_180041805
0x180041799  lea     rcx, [rsp+38h+arg_8]
0x18004179e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800417a3  mov     [rsp+38h+arg_0], 0
0x1800417ab  mov     rcx, [rsi]
0x1800417ae  mov     rax, [rcx]
0x1800417b1  lea     rdx, [rsp+38h+arg_0]
0x1800417b6  mov     rax, [rax+38h]
0x1800417ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417bf  mov     ebx, eax
0x1800417c1  test    eax, eax
0x1800417c3  jns     short loc_1800417E0
0x1800417c5  mov     edx, 994h; void *
0x1800417ca  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800417d1  mov     r9d, ebx; char *
0x1800417d4  mov     rcx, [rsp+38h]; this
0x1800417d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800417de  jmp     short loc_180041795
0x1800417e0  cmp     [rsp+38h+arg_0], 0
0x1800417e5  jz      short loc_180041803
0x1800417e7  mov     rcx, [rsi]
0x1800417ea  mov     rax, [rcx]
0x1800417ed  mov     rax, [rax+30h]
0x1800417f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417f6  mov     ebx, eax
0x1800417f8  test    eax, eax
0x1800417fa  jns     short loc_180041803
0x1800417fc  mov     edx, 998h
0x180041801  jmp     short loc_1800417CA
0x180041803  xor     eax, eax
0x180041805  mov     rbx, [rsp+38h+arg_10]
0x18004180a  mov     rsi, [rsp+38h+arg_18]
0x18004180f  add     rsp, 30h
0x180041813  pop     rdi
0x180041814  retn
```
