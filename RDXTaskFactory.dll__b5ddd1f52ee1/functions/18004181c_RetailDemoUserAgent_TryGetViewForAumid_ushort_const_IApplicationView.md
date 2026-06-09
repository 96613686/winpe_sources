# RetailDemoUserAgent::TryGetViewForAumid(ushort const *,IApplicationView * *)

- ea: `0x18004181c`
- end: `0x18004193e`
- name: `?TryGetViewForAumid@RetailDemoUserAgent@@AEAAJPEBGPEAPEAUIApplicationView@@@Z`
- size: `290`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this, const unsigned __int16 *, struct IApplicationView **)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180039a40`
- `0x18003dda0`
- `0x180041ad4`

## callees

- `0x180008bbc`
- `0x18000aa7c`
- `0x18004181c`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041895`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041895`

## string_xrefs

- `0x180041845`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x1800418e3`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RetailDemoUserAgent::TryGetViewForAumid(
        RetailDemoUserAgent *this,
        const unsigned __int16 *a2,
        struct IApplicationView **a3)
{
  unsigned int v5; // ebx
  HRESULT v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, GUID *, GUID *, RetailDemoUserAgent **); // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  int ppv; // [rsp+20h] [rbp-28h]
  int ppva; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  RetailDemoUserAgent *v21; // [rsp+50h] [rbp+8h] BYREF
  LPVOID v22; // [rsp+60h] [rbp+18h] BYREF

  v21 = this;
  if ( a3 )
  {
    v22 = 0;
    v21 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22, a2, a3);
    v6 = CoCreateInstance(&CLSID_ImmersiveShell, 0, 4u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v22);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v10 = v22;
      v11 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, RetailDemoUserAgent **))(*(_QWORD *)v22 + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21, v7, v8);
      v6 = v11(v10, &GUID_1841c6d7_4f9d_42c0_af41_8747538f10e5, &GUID_1841c6d7_4f9d_42c0_af41_8747538f10e5, &v21);
      v5 = v6;
      if ( v6 >= 0 )
      {
        v14 = (*(__int64 (__fastcall **)(RetailDemoUserAgent *, const unsigned __int16 *, struct IApplicationView **))(*(_QWORD *)v21 + 64LL))(
                v21,
                a2,
                a3);
        if ( v14 >= 0 )
          v5 = 0;
        else
          v5 = v14;
        goto LABEL_11;
      }
      v9 = 401;
    }
    else
    {
      v9 = 400;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v6,
      ppva);
LABEL_11:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21, v12, v13);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22, v15, v16);
    return v5;
  }
  v5 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x18B,
    (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
    (const char *)0x80070057LL,
    ppv);
  return v5;
}

```

## disassembly

```asm
0x18004181c  mov     [rsp+arg_8], rbx
0x180041821  mov     [rsp+arg_0], rcx
0x180041826  push    rbp
0x180041827  push    rsi
0x180041828  push    rdi
0x180041829  sub     rsp, 30h
0x18004182d  mov     rsi, r8
0x180041830  mov     rbp, rdx
0x180041833  test    r8, r8
0x180041836  jnz     short loc_18004185B
0x180041838  mov     rcx, [rsp+48h]; this
0x18004183d  mov     ebx, 80070057h
0x180041842  mov     r9d, ebx; char *
0x180041845  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18004184c  mov     edx, 18Bh; void *
0x180041851  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041856  jmp     loc_18004192F
0x18004185b  mov     [rsp+48h+arg_10], 0
0x180041864  mov     [rsp+48h+arg_0], 0
0x18004186d  lea     rcx, [rsp+48h+arg_10]
0x180041872  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180041877  lea     rax, [rsp+48h+arg_10]
0x18004187c  mov     qword ptr [rsp+48h+ppv], rax; int
0x180041881  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x180041888  xor     edx, edx; pUnkOuter
0x18004188a  lea     r8d, [rdx+4]; dwClsContext
0x18004188e  lea     rcx, CLSID_ImmersiveShell; rclsid
0x180041895  call    cs:__imp_CoCreateInstance
0x18004189b  mov     ebx, eax
0x18004189d  test    eax, eax
0x18004189f  jns     short loc_1800418A8
0x1800418a1  mov     edx, 190h
0x1800418a6  jmp     short loc_1800418E3
0x1800418a8  mov     rdi, [rsp+48h+arg_10]
0x1800418ad  mov     rax, [rdi]
0x1800418b0  mov     rbx, [rax+18h]
0x1800418b4  lea     rcx, [rsp+48h+arg_0]
0x1800418b9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800418be  lea     r9, [rsp+48h+arg_0]
0x1800418c3  lea     rdx, _GUID_1841c6d7_4f9d_42c0_af41_8747538f10e5
0x1800418ca  mov     r8, rdx
0x1800418cd  mov     rcx, rdi
0x1800418d0  mov     rax, rbx
0x1800418d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800418d8  mov     ebx, eax
0x1800418da  test    eax, eax
0x1800418dc  jns     short loc_1800418F9
0x1800418de  mov     edx, 191h; void *
0x1800418e3  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800418ea  mov     r9d, eax; char *
0x1800418ed  mov     rcx, [rsp+48h]; this
0x1800418f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800418f7  jmp     short loc_18004191A
0x1800418f9  mov     rcx, [rsp+48h+arg_0]
0x1800418fe  mov     rax, [rcx]
0x180041901  mov     r8, rsi
0x180041904  mov     rdx, rbp
0x180041907  mov     rax, [rax+40h]
0x18004190b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041910  test    eax, eax
0x180041912  jns     short loc_180041918
0x180041914  mov     ebx, eax
0x180041916  jmp     short loc_18004191A
0x180041918  xor     ebx, ebx
0x18004191a  lea     rcx, [rsp+48h+arg_0]
0x18004191f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180041924  nop
0x180041925  lea     rcx, [rsp+48h+arg_10]
0x18004192a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004192f  mov     eax, ebx
0x180041931  mov     rbx, [rsp+48h+arg_8]
0x180041936  add     rsp, 30h
0x18004193a  pop     rdi
0x18004193b  pop     rsi
0x18004193c  pop     rbp
0x18004193d  retn
```
