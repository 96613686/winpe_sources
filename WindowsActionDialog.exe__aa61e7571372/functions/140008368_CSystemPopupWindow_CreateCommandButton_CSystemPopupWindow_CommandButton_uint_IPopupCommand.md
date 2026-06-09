# CSystemPopupWindow::_CreateCommandButton(CSystemPopupWindow::CommandButton,uint,IPopupCommand * *)

- ea: `0x140008368`
- end: `0x140008496`
- name: `?_CreateCommandButton@CSystemPopupWindow@@AEAAJW4CommandButton@1@IPEAPEAUIPopupCommand@@@Z`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008790`

## callees

- `0x140001460`
- `0x140007d6c`
- `0x1400080c8`
- `0x1400080f4`
- `0x140008368`
- `0x14000a010`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x1400083b2`
- `KERNEL32!GetModuleHandleExW` at `0x1400083b2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400083dc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008477`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400083dc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008477`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSystemPopupWindow::_CreateCommandButton(__int64 a1, int a2, int a3, _QWORD *a4)
{
  const char *v7; // r9
  unsigned int LastError; // ebx
  __int64 *v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rcx
  int v13; // [rsp+20h] [rbp-50h]
  int v14; // [rsp+30h] [rbp-40h] BYREF
  int v15; // [rsp+38h] [rbp-38h] BYREF
  __int64 v16; // [rsp+40h] [rbp-30h] BYREF
  __int64 v17; // [rsp+48h] [rbp-28h] BYREF
  int (*v18)(struct IPopupWindow *, struct IPopupCommand *, void *); // [rsp+50h] [rbp-20h] BYREF
  HMODULE phModule; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v14 = a3;
  *a4 = 0;
  phModule = 0;
  if ( !GetModuleHandleExW(4u, (LPCWSTR)CSystemPopupWindow::_OnCommand, &phModule) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x95,
                  (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
                  v7);
LABEL_3:
    if ( phModule )
      FreeLibrary(phModule);
    return LastError;
  }
  v15 = a2;
  v17 = a1;
  v18 = CSystemPopupWindow::_OnCommand;
  v10 = (__int64 *)Microsoft::WRL::Details::Make<CShutdownPopupCommand,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,long (*)(IPopupWindow *,IPopupCommand *,void *),CSystemPopupWindow *,unsigned int,unsigned int &>(
                     (unsigned int)&v16,
                     (unsigned int)&phModule,
                     (unsigned int)&v18,
                     (unsigned int)&v17,
                     (__int64)&v15,
                     (__int64)&v14);
  v11 = *v10;
  *v10 = 0;
  v12 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( !v11 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
      (const char *)0x8007000ELL,
      v13);
    goto LABEL_3;
  }
  *a4 = v11;
  if ( phModule )
    FreeLibrary(phModule);
  return 0;
}

```

## disassembly

```asm
0x140008368  push    rbp
0x14000836a  push    rbx
0x14000836b  push    rsi
0x14000836c  push    rdi
0x14000836d  push    r15
0x14000836f  mov     rbp, rsp
0x140008372  sub     rsp, 70h
0x140008376  mov     rax, cs:__security_cookie
0x14000837d  xor     rax, rsp
0x140008380  mov     [rbp+var_10], rax
0x140008384  mov     rdi, r9
0x140008387  mov     esi, edx
0x140008389  mov     rbx, rcx
0x14000838c  mov     [rbp+var_40], r8d
0x140008390  mov     qword ptr [r9], 0
0x140008397  mov     [rbp+phModule], 0
0x14000839f  lea     r8, [rbp+phModule]; phModule
0x1400083a3  lea     r15, ?_OnCommand@CSystemPopupWindow@@CAJPEAUIPopupWindow@@PEAUIPopupCommand@@PEAX@Z; CSystemPopupWindow::_OnCommand(IPopupWindow *,IPopupCommand *,void *)
0x1400083aa  mov     rdx, r15; lpModuleName
0x1400083ad  mov     ecx, 4; dwFlags
0x1400083b2  call    cs:__imp_GetModuleHandleExW
0x1400083b8  test    eax, eax
0x1400083ba  jnz     short loc_1400083E9
0x1400083bc  mov     rcx, [rbp+28h]; this
0x1400083c0  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x1400083c7  mov     edx, 95h; void *
0x1400083cc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400083d1  mov     ebx, eax
0x1400083d3  mov     rcx, [rbp+phModule]; hLibModule
0x1400083d7  test    rcx, rcx
0x1400083da  jz      short loc_1400083E2
0x1400083dc  call    cs:__imp_FreeLibrary
0x1400083e2  mov     eax, ebx
0x1400083e4  jmp     loc_14000847F
0x1400083e9  mov     [rbp+var_38], esi
0x1400083ec  mov     [rbp+var_28], rbx
0x1400083f0  mov     [rbp+var_20], r15
0x1400083f4  lea     rax, [rbp+var_40]
0x1400083f8  mov     [rsp+70h+var_48], rax
0x1400083fd  lea     rax, [rbp+var_38]
0x140008401  mov     qword ptr [rsp+70h+var_50], rax; int
0x140008406  lea     r9, [rbp+var_28]
0x14000840a  lea     r8, [rbp+var_20]
0x14000840e  lea     rdx, [rbp+phModule]
0x140008412  lea     rcx, [rbp+var_30]
0x140008416  call    ??$Make@VCShutdownPopupCommand@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@P6AJPEAUIPopupWindow@@PEAUIPopupCommand@@PEAX@ZPEAVCSystemPopupWindow@@IAEAI@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCShutdownPopupCommand@@@12@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAP6AJPEAUIPopupWindow@@PEAUIPopupCommand@@PEAX@Z$$QEAPEAVCSystemPopupWindow@@$$QEAIAEAI@Z; Microsoft::WRL::Details::Make<CShutdownPopupCommand,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,long (*)(IPopupWindow *,IPopupCommand *,void *),CSystemPopupWindow *,uint,uint &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&,long (*&&)(IPopupWindow *,IPopupCommand *,void *),CSystemPopupWindow * &&,uint &&,uint &)
0x14000841b  mov     rbx, [rax]
0x14000841e  mov     qword ptr [rax], 0
0x140008425  mov     rcx, [rbp+var_30]
0x140008429  test    rcx, rcx
0x14000842c  jz      short loc_140008443
0x14000842e  mov     [rbp+var_30], 0
0x140008436  mov     rax, [rcx]
0x140008439  mov     rax, [rax+10h]
0x14000843d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008442  nop
0x140008443  test    rbx, rbx
0x140008446  jnz     short loc_14000846B
0x140008448  mov     rcx, [rbp+28h]; this
0x14000844c  mov     ebx, 8007000Eh
0x140008451  mov     r9d, ebx; char *
0x140008454  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x14000845b  mov     edx, 98h; void *
0x140008460  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008465  nop
0x140008466  jmp     loc_1400083D3
0x14000846b  mov     [rdi], rbx
0x14000846e  mov     rcx, [rbp+phModule]; hLibModule
0x140008472  test    rcx, rcx
0x140008475  jz      short loc_14000847D
0x140008477  call    cs:__imp_FreeLibrary
0x14000847d  xor     eax, eax
0x14000847f  mov     rcx, [rbp+var_10]
0x140008483  xor     rcx, rsp; StackCookie
0x140008486  call    __security_check_cookie
0x14000848b  add     rsp, 70h
0x14000848f  pop     r15
0x140008491  pop     rdi
0x140008492  pop     rsi
0x140008493  pop     rbx
0x140008494  pop     rbp
0x140008495  retn
```
