# CTitleBar::SetAppId(ushort const *,int)

- ea: `0x180024ad0`
- end: `0x180024c3a`
- name: `?SetAppId@CTitleBar@@UEAAXPEBGH@Z`
- size: `362`
- prototype: `void(CTitleBar *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800116c0`
- `0x180024184`
- `0x180024ad0`
- `0x180024c40`
- `0x180024ef8`
- `0x180025000`
- `0x18002c7f0`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024c2a`
- `bcp47mrm!GetApplicationLayoutDirection` at `0x180024b53`
- `bcp47mrm!GetApplicationLayoutDirection` at `0x180024b53`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTitleBar::SetAppId(CTitleBar *this, wchar_t *a2, int a3)
{
  int v6; // eax
  unsigned __int16 **v7; // r8
  int ApplicationLayoutDirection; // eax
  int v9; // eax
  bool v10; // zf
  CTitleBar *v11; // rbx
  int v12; // eax
  int v13; // eax
  LPVOID pv[9]; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v16; // [rsp+80h] [rbp+18h] BYREF

  v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         (__int64)this + 424,
         a2,
         0xFFFFFFFFFFFFFFFFuLL);
  if ( v6 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xCF0,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)(unsigned int)v6,
      (int)pv[0]);
  pv[0] = 0;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  if ( (int)CallerIdentity::GetPackageFullNameFromAppId(a2, (unsigned __int16 *)pv, v7) >= 0 )
  {
    v16 = 0;
    ApplicationLayoutDirection = GetApplicationLayoutDirection(pv[0], &v16);
    if ( ApplicationLayoutDirection < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xCF7,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
        (const char *)(unsigned int)ApplicationLayoutDirection,
        (int)pv[0]);
    v9 = v16;
    if ( v16 == -1 )
      goto LABEL_11;
    if ( v16 )
    {
      v10 = v16 == 1;
      if ( v16 == 1 )
      {
LABEL_13:
        v11 = (CTitleBar *)((char *)this - 56);
        CTitleBar::_ReconcileFlowDirectionSettings((CTitleBar *)((char *)this - 56), v10, *((_BYTE *)this + 503));
        goto LABEL_15;
      }
      if ( v16 != 2 && v16 != 3 )
      {
LABEL_11:
        Mirror_IsThreadRTL();
        v9 = v16;
      }
    }
    v10 = v9 == 1;
    goto LABEL_13;
  }
  v11 = (CTitleBar *)((char *)this - 56);
LABEL_15:
  v12 = (*(__int64 (__fastcall **)(_QWORD *, wchar_t *))(**((_QWORD **)v11 + 51) + 48LL))(*((_QWORD **)v11 + 51), a2);
  if ( v12 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD0E,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)(unsigned int)v12,
      (int)pv[0]);
  if ( a3 )
  {
    v13 = CTitleBar::_InitializePersistence(v11);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD14,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
        (const char *)(unsigned int)v13,
        (int)pv[0]);
  }
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
}

```

## disassembly

```asm
0x180024ad0  push    rbx
0x180024ad2  push    rbp
0x180024ad3  push    rsi
0x180024ad4  push    r14
0x180024ad6  sub     rsp, 48h
0x180024ada  mov     r14d, r8d
0x180024add  mov     rbp, rdx
0x180024ae0  mov     rsi, rcx
0x180024ae3  add     rcx, 1A8h
0x180024aea  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180024aee  mov     r8, rbx
0x180024af1  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180024af6  mov     rcx, [rsp+68h]; this
0x180024afb  test    eax, eax
0x180024afd  jns     short loc_180024B13
0x180024aff  mov     r9d, eax; char *
0x180024b02  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180024b09  mov     edx, 0CF0h; void *
0x180024b0e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024b13  mov     [rsp+68h+pv], 0; int
0x180024b1c  mov     [rsp+68h+var_40], rbx
0x180024b21  mov     [rsp+68h+var_38], rbx
0x180024b26  lea     rdx, [rsp+68h+pv]; unsigned __int16 *
0x180024b2b  mov     rcx, rbp; this
0x180024b2e  call    ?GetPackageFullNameFromAppId@CallerIdentity@@YAJPEBGPEAPEAG@Z; CallerIdentity::GetPackageFullNameFromAppId(ushort const *,ushort * *)
0x180024b33  test    eax, eax
0x180024b35  js      loc_180024BBB
0x180024b3b  mov     [rsp+68h+arg_10], 0
0x180024b46  lea     rdx, [rsp+68h+arg_10]
0x180024b4e  mov     rcx, [rsp+68h+pv]
0x180024b53  call    cs:__imp_GetApplicationLayoutDirection
0x180024b59  mov     rcx, [rsp+68h]; this
0x180024b5e  test    eax, eax
0x180024b60  jns     short loc_180024B76
0x180024b62  mov     r9d, eax; char *
0x180024b65  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180024b6c  mov     edx, 0CF7h; void *
0x180024b71  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024b76  mov     eax, [rsp+68h+arg_10]
0x180024b7d  cmp     eax, ebx
0x180024b7f  jz      short loc_180024B94
0x180024b81  test    eax, eax
0x180024b83  jz      short loc_180024BA0
0x180024b85  cmp     eax, 1
0x180024b88  jz      short loc_180024BA3
0x180024b8a  cmp     eax, 2
0x180024b8d  jz      short loc_180024BA0
0x180024b8f  cmp     eax, 3
0x180024b92  jz      short loc_180024BA0
0x180024b94  call    ?Mirror_IsThreadRTL@@YAHXZ; Mirror_IsThreadRTL(void)
0x180024b99  mov     eax, [rsp+68h+arg_10]
0x180024ba0  cmp     eax, 1
0x180024ba3  setz    dl; bool
0x180024ba6  lea     rbx, [rsi-38h]
0x180024baa  mov     r8b, [rsi+1F7h]; bool
0x180024bb1  mov     rcx, rbx; this
0x180024bb4  call    ?_ReconcileFlowDirectionSettings@CTitleBar@@AEAAX_N0@Z; CTitleBar::_ReconcileFlowDirectionSettings(bool,bool)
0x180024bb9  jmp     short loc_180024BBF
0x180024bbb  lea     rbx, [rsi-38h]
0x180024bbf  mov     rcx, [rbx+198h]
0x180024bc6  mov     rax, [rcx]
0x180024bc9  mov     rdx, rbp
0x180024bcc  mov     rax, [rax+30h]
0x180024bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bd5  mov     rcx, [rsp+68h]; this
0x180024bda  test    eax, eax
0x180024bdc  jns     short loc_180024BF2
0x180024bde  mov     r9d, eax; char *
0x180024be1  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180024be8  mov     edx, 0D0Eh; void *
0x180024bed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024bf2  test    r14d, r14d
0x180024bf5  jz      short loc_180024C1D
0x180024bf7  mov     rcx, rbx; this
0x180024bfa  call    ?_InitializePersistence@CTitleBar@@AEAAJXZ; CTitleBar::_InitializePersistence(void)
0x180024bff  mov     rcx, [rsp+68h]; this
0x180024c04  test    eax, eax
0x180024c06  jns     short loc_180024C1D
0x180024c08  mov     r9d, eax; char *
0x180024c0b  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180024c12  mov     edx, 0D14h; void *
0x180024c17  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024c1c  nop
0x180024c1d  cmp     [rsp+68h+pv], 0
0x180024c23  jz      short loc_180024C30
0x180024c25  mov     rcx, [rsp+68h+pv]; pv
0x180024c2a  call    cs:__imp_CoTaskMemFree
0x180024c30  add     rsp, 48h
0x180024c34  pop     r14
0x180024c36  pop     rsi
0x180024c37  pop     rbp
0x180024c38  pop     rbx
0x180024c39  retn
```
