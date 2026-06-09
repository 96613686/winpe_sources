# Windows::Internal::XamlPopupWindowImpl::SetTitle(ushort const *)

- ea: `0x1800a2db0`
- end: `0x1800a2ee3`
- name: `?SetTitle@XamlPopupWindowImpl@Internal@Windows@@UEAAJPEBG@Z`
- size: `307`
- prototype: `__int64 __fastcall(Windows::Internal::XamlPopupWindowImpl *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000af94`
- `0x180032b5c`
- `0x180034db4`
- `0x18009f238`
- `0x1800a2db0`
- `0x1800e5010`

## import_xrefs

- `USER32!SetWindowTextW` at `0x1800a2dc6`
- `USER32!SetWindowTextW` at `0x1800a2e15`
- `USER32!SetWindowTextW` at `0x1800a2dc6`
- `USER32!SetWindowTextW` at `0x1800a2e15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2e25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2e3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2e25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2e3c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::XamlPopupWindowImpl::SetTitle(
        Windows::Internal::XamlPopupWindowImpl *this,
        const unsigned __int16 *a2)
{
  HWND v3; // rax
  bool v4; // zf
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // edi
  __int64 v8; // rdx
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // ebx
  int v13[2]; // [rsp+20h] [rbp-18h] BYREF
  LPCWSTR *p_lpString; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPCWSTR lpString; // [rsp+48h] [rbp+10h] BYREF

  lpString = a2;
  SetWindowTextW(*((HWND *)this + 7), a2);
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 88LL))(*((_QWORD *)this + 4)) == 1 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 120LL))(*((_QWORD *)this + 4)) )
    {
      v3 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 128LL))(*((_QWORD *)this + 4));
      if ( v3 )
        SetWindowTextW(v3, lpString);
    }
  }
  CoTaskMemFree(*((LPVOID *)this + 24));
  v4 = lpString == 0;
  *((_QWORD *)this + 24) = 0;
  if ( !v4 )
  {
    CoTaskMemFree(0);
    v7 = _AllocString<CTCoAllocPolicy>(v6, v5, lpString, (_QWORD *)this + 24);
    if ( v7 < 0 )
    {
      v8 = 1176;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"shell\\windowsuiimmersive\\popup\\xamlpopupwindowimpl.cpp",
        (const char *)(unsigned int)v7,
        v13[0]);
      return (unsigned int)v7;
    }
  }
  v10 = *((_QWORD *)this + 36);
  p_lpString = &lpString;
  *(_QWORD *)v13 = this;
  v7 = CreationThreadDispatcher::RunSync__lambda_a70ba324e342efb7ddaf68098acf6d61___(v10, v13);
  if ( v7 < 0 )
  {
    v8 = 1185;
    goto LABEL_8;
  }
  if ( !*((_QWORD *)this + 48) )
    return 0;
  v11 = Windows::Internal::XamlPopupWindowImpl::_EnsureProxy(this, 1);
  v12 = v11;
  if ( v11 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4A6,
    (unsigned int)"shell\\windowsuiimmersive\\popup\\xamlpopupwindowimpl.cpp",
    (const char *)(unsigned int)v11,
    v13[0]);
  return v12;
}

```

## disassembly

```asm
0x1800a2db0  mov     [rsp+arg_0], rbx
0x1800a2db5  mov     [rsp+lpString], rdx
0x1800a2dba  push    rdi
0x1800a2dbb  sub     rsp, 30h
0x1800a2dbf  mov     rbx, rcx
0x1800a2dc2  mov     rcx, [rcx+38h]; hWnd
0x1800a2dc6  call    cs:__imp_SetWindowTextW
0x1800a2dcc  mov     rcx, [rbx+20h]
0x1800a2dd0  mov     rax, [rcx]
0x1800a2dd3  mov     rax, [rax+58h]
0x1800a2dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2ddc  cmp     eax, 1
0x1800a2ddf  jnz     short loc_1800A2E1B
0x1800a2de1  mov     rcx, [rbx+20h]
0x1800a2de5  mov     rax, [rcx]
0x1800a2de8  mov     rax, [rax+78h]
0x1800a2dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2df1  test    al, al
0x1800a2df3  jz      short loc_1800A2E1B
0x1800a2df5  mov     rcx, [rbx+20h]
0x1800a2df9  mov     rax, [rcx]
0x1800a2dfc  mov     rax, [rax+80h]
0x1800a2e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2e08  test    rax, rax
0x1800a2e0b  jz      short loc_1800A2E1B
0x1800a2e0d  mov     rdx, [rsp+38h+lpString]; lpString
0x1800a2e12  mov     rcx, rax; hWnd
0x1800a2e15  call    cs:__imp_SetWindowTextW
0x1800a2e1b  lea     rdi, [rbx+0C0h]
0x1800a2e22  mov     rcx, [rdi]; pv
0x1800a2e25  call    cs:__imp_CoTaskMemFree
0x1800a2e2b  cmp     [rsp+38h+lpString], 0
0x1800a2e31  mov     qword ptr [rdi], 0
0x1800a2e38  jz      short loc_1800A2E72
0x1800a2e3a  xor     ecx, ecx; pv
0x1800a2e3c  call    cs:__imp_CoTaskMemFree
0x1800a2e42  mov     r8, [rsp+38h+lpString]
0x1800a2e47  mov     r9, rdi
0x1800a2e4a  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800a2e4f  mov     edi, eax
0x1800a2e51  test    eax, eax
0x1800a2e53  jns     short loc_1800A2E72
0x1800a2e55  mov     edx, 498h; void *
0x1800a2e5a  mov     rcx, [rsp+38h]; this
0x1800a2e5f  lea     r8, aShellWindowsui_15; "shell\\windowsuiimmersive\\popup\\xamlp"...
0x1800a2e66  mov     r9d, edi; char *
0x1800a2e69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2e6e  mov     eax, edi
0x1800a2e70  jmp     short loc_1800A2ED8
0x1800a2e72  mov     rcx, [rbx+120h]
0x1800a2e79  lea     rax, [rsp+38h+lpString]
0x1800a2e7e  lea     rdx, [rsp+38h+var_18]
0x1800a2e83  mov     [rsp+38h+var_10], rax
0x1800a2e88  mov     qword ptr [rsp+38h+var_18], rbx; int
0x1800a2e8d  call    CreationThreadDispatcher__RunSync__lambda_a70ba324e342efb7ddaf68098acf6d61___
0x1800a2e92  mov     edi, eax
0x1800a2e94  test    eax, eax
0x1800a2e96  jns     short loc_1800A2E9F
0x1800a2e98  mov     edx, 4A1h
0x1800a2e9d  jmp     short loc_1800A2E5A
0x1800a2e9f  cmp     qword ptr [rbx+180h], 0
0x1800a2ea7  jz      short loc_1800A2ED6
0x1800a2ea9  mov     dl, 1; bool
0x1800a2eab  mov     rcx, rbx; this
0x1800a2eae  call    ?_EnsureProxy@XamlPopupWindowImpl@Internal@Windows@@AEAAJ_N@Z; Windows::Internal::XamlPopupWindowImpl::_EnsureProxy(bool)
0x1800a2eb3  mov     ebx, eax
0x1800a2eb5  test    eax, eax
0x1800a2eb7  jns     short loc_1800A2ED6
0x1800a2eb9  mov     rcx, [rsp+38h]; this
0x1800a2ebe  lea     r8, aShellWindowsui_15; "shell\\windowsuiimmersive\\popup\\xamlp"...
0x1800a2ec5  mov     r9d, eax; char *
0x1800a2ec8  mov     edx, 4A6h; void *
0x1800a2ecd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2ed2  mov     eax, ebx
0x1800a2ed4  jmp     short loc_1800A2ED8
0x1800a2ed6  xor     eax, eax
0x1800a2ed8  mov     rbx, [rsp+38h+arg_0]
0x1800a2edd  add     rsp, 30h
0x1800a2ee1  pop     rdi
0x1800a2ee2  retn
```
