# CApplicationFrame::_ReconcilePresentation(HWND__ *)

- ea: `0x18003ca40`
- end: `0x18003cbca`
- name: `?_ReconcilePresentation@CApplicationFrame@@AEAAJPEAUHWND__@@@Z`
- size: `394`
- prototype: `__int64 __fastcall(CApplicationFrame *__hidden this, HWND)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18004f03c`
- `0x180050e30`

## callees

- `0x180014808`
- `0x180014b40`
- `0x1800343ac`
- `0x1800376cc`
- `0x180039c50`
- `0x18003ada8`
- `0x18003ca40`
- `0x180040270`
- `0x180041ec0`
- `0x180043c30`
- `0x18004ec10`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003cb06`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003cb06`
- `ext-ms-win-ntuser-private-l1-2-0!__imp_GetModernAppWindow` at `0x18003cabe`
- `ext-ms-win-ntuser-private-l1-2-0!__imp_GetModernAppWindow` at `0x18003cabe`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18003ca83`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18003ca83`
- `ext-ms-win-ntuser-window-l1-1-4!IsWindowEnabled` at `0x18003cb68`
- `ext-ms-win-ntuser-window-l1-1-4!IsWindowEnabled` at `0x18003cb68`
- `USER32!__imp_SetModernAppWindow` at `0x18003caa5`
- `USER32!__imp_SetModernAppWindow` at `0x18003caa5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CApplicationFrame::_ReconcilePresentation(CApplicationFrame *this, HWND a2)
{
  int Error; // esi
  void (__fastcall *v5)(_QWORD, _QWORD, _QWORD); // rax
  __int64 v6; // rdi
  BOOL v7; // eax
  DWORD dwProcessId; // [rsp+20h] [rbp-E0h] BYREF
  HWND v10; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v11[336]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v10 = a2;
  dwProcessId = 0;
  GetWindowThreadProcessId(a2, &dwProcessId);
  CApplicationFrameTelemetry::ReconcilePresentation::ReconcilePresentation((CApplicationFrameTelemetry::ReconcilePresentation *)v11);
  if ( (unsigned int)SetModernAppWindow(*((_QWORD *)this + 3), a2)
    || (Error = ResultFromKnownLastError(), Error >= 0)
    || (HWND)GetModernAppWindow(*((_QWORD *)this + 3)) == a2 )
  {
    v5 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD))*((_QWORD *)this + 93);
    if ( v5 )
    {
      if ( a2 )
      {
        v10 = (HWND)OpenProcess(0x200u, 0, dwProcessId);
        if ( v10 )
          (*((void (__fastcall **)(_QWORD, __int64, HWND *))this + 93))(*((_QWORD *)this + 3), 1, &v10);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v10);
      }
      else
      {
        v5(*((_QWORD *)this + 3), 0, 0);
      }
    }
    CApplicationFrame::_OnAfterPresentationChange(this, a2);
    v6 = *((_QWORD *)this + 21);
    *(_QWORD *)(v6 + 48) = a2;
    if ( a2 )
    {
      v7 = IsWindowEnabled(*(HWND *)(v6 + 56));
      CWindowPresentationMessaging::_SendForwardedMessage((CWindowPresentationMessaging *)v6, 0xAu, v7, 0);
    }
    CWindowPresentationMessaging::OnWindowPositionChanged((CWindowPresentationMessaging *)v6);
    CApplicationFrameTelemetry::ReconcilePresentation::Stop(
      (CApplicationFrameTelemetry::ReconcilePresentation *)v11,
      a2,
      dwProcessId);
    Error = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60E,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
      (const char *)(unsigned int)Error,
      dwProcessId);
  }
  CApplicationFrameTelemetry::ReconcilePresentation::~ReconcilePresentation((CApplicationFrameTelemetry::ReconcilePresentation *)v11);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18003ca40  mov     [rsp-8+arg_10], rbx
0x18003ca45  push    rbp
0x18003ca46  push    rsi
0x18003ca47  push    rdi
0x18003ca48  lea     rbp, [rsp-90h]
0x18003ca50  sub     rsp, 190h
0x18003ca57  mov     rax, cs:__security_cookie
0x18003ca5e  xor     rax, rsp
0x18003ca61  mov     [rbp+0A0h+var_20], rax
0x18003ca68  mov     rbx, rdx
0x18003ca6b  mov     rdi, rcx
0x18003ca6e  mov     [rsp+1A0h+var_178], rdx
0x18003ca73  mov     [rsp+1A0h+dwProcessId], 0; int
0x18003ca7b  lea     rdx, [rsp+1A0h+dwProcessId]; lpdwProcessId
0x18003ca80  mov     rcx, rbx; hWnd
0x18003ca83  call    cs:__imp_GetWindowThreadProcessId
0x18003ca89  lea     r9, [rsp+1A0h+dwProcessId]
0x18003ca8e  lea     r8, [rsp+1A0h+var_178]
0x18003ca93  lea     rcx, [rsp+1A0h+var_170]; this
0x18003ca98  call    ??$?0AEAPEAUHWND__@@AEAK@ReconcilePresentation@CApplicationFrameTelemetry@@AEAA@U?$integral_constant@D$0A@@wistd@@AEAPEAUHWND__@@AEAK@Z; CApplicationFrameTelemetry::ReconcilePresentation::ReconcilePresentation(wistd::integral_constant<char,0>,HWND__ * &,ulong &)
0x18003ca9d  nop
0x18003ca9e  mov     rdx, rbx
0x18003caa1  mov     rcx, [rdi+18h]
0x18003caa5  call    cs:__imp_SetModernAppWindow
0x18003caab  test    eax, eax
0x18003caad  jnz     short loc_18003CAE9
0x18003caaf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003cab4  mov     esi, eax
0x18003cab6  test    eax, eax
0x18003cab8  jns     short loc_18003CAE9
0x18003caba  mov     rcx, [rdi+18h]
0x18003cabe  call    cs:__imp_GetModernAppWindow
0x18003cac4  cmp     rax, rbx
0x18003cac7  jz      short loc_18003CAE9
0x18003cac9  mov     rcx, [rbp+0A8h]; this
0x18003cad0  mov     r9d, esi; char *
0x18003cad3  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x18003cada  mov     edx, 60Eh; void *
0x18003cadf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cae4  jmp     loc_18003CB9C
0x18003cae9  mov     rax, [rdi+2E8h]
0x18003caf0  test    rax, rax
0x18003caf3  jz      short loc_18003CB49
0x18003caf5  xor     edx, edx; bInheritHandle
0x18003caf7  test    rbx, rbx
0x18003cafa  jz      short loc_18003CB3D
0x18003cafc  mov     r8d, [rsp+1A0h+dwProcessId]; dwProcessId
0x18003cb01  mov     ecx, 200h; dwDesiredAccess
0x18003cb06  call    cs:__imp_OpenProcess
0x18003cb0c  mov     [rsp+1A0h+var_178], rax
0x18003cb11  test    rax, rax
0x18003cb14  jz      short loc_18003CB31
0x18003cb16  lea     r8, [rsp+1A0h+var_178]
0x18003cb1b  mov     edx, 1
0x18003cb20  mov     rcx, [rdi+18h]
0x18003cb24  mov     rax, [rdi+2E8h]
0x18003cb2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb30  nop
0x18003cb31  lea     rcx, [rsp+1A0h+var_178]
0x18003cb36  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003cb3b  jmp     short loc_18003CB49
0x18003cb3d  xor     r8d, r8d
0x18003cb40  mov     rcx, [rdi+18h]
0x18003cb44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb49  mov     rdx, rbx; HWND
0x18003cb4c  mov     rcx, rdi; this
0x18003cb4f  call    ?_OnAfterPresentationChange@CApplicationFrame@@AEAAXPEAUHWND__@@@Z; CApplicationFrame::_OnAfterPresentationChange(HWND__ *)
0x18003cb54  mov     rdi, [rdi+0A8h]
0x18003cb5b  mov     [rdi+30h], rbx
0x18003cb5f  test    rbx, rbx
0x18003cb62  jz      short loc_18003CB80
0x18003cb64  mov     rcx, [rdi+38h]; hWnd
0x18003cb68  call    cs:__imp_IsWindowEnabled
0x18003cb6e  movsxd  r8, eax; unsigned __int64
0x18003cb71  xor     r9d, r9d; __int64
0x18003cb74  lea     edx, [r9+0Ah]; unsigned int
0x18003cb78  mov     rcx, rdi; this
0x18003cb7b  call    ?_SendForwardedMessage@CWindowPresentationMessaging@@AEAAXI_K_J@Z; CWindowPresentationMessaging::_SendForwardedMessage(uint,unsigned __int64,__int64)
0x18003cb80  mov     rcx, rdi; this
0x18003cb83  call    ?OnWindowPositionChanged@CWindowPresentationMessaging@@QEAAXXZ; CWindowPresentationMessaging::OnWindowPositionChanged(void)
0x18003cb88  mov     r8d, [rsp+1A0h+dwProcessId]; unsigned int
0x18003cb8d  mov     rdx, rbx; HWND
0x18003cb90  lea     rcx, [rsp+1A0h+var_170]; this
0x18003cb95  call    ?Stop@ReconcilePresentation@CApplicationFrameTelemetry@@QEAAXPEAUHWND__@@K@Z; CApplicationFrameTelemetry::ReconcilePresentation::Stop(HWND__ *,ulong)
0x18003cb9a  xor     esi, esi
0x18003cb9c  lea     rcx, [rsp+1A0h+var_170]; this
0x18003cba1  call    ??1ReconcilePresentation@CApplicationFrameTelemetry@@QEAA@XZ; CApplicationFrameTelemetry::ReconcilePresentation::~ReconcilePresentation(void)
0x18003cba6  mov     eax, esi
0x18003cba8  mov     rcx, [rbp+0A0h+var_20]
0x18003cbaf  xor     rcx, rsp; StackCookie
0x18003cbb2  call    __security_check_cookie
0x18003cbb7  mov     rbx, [rsp+1A0h+arg_10]
0x18003cbbf  add     rsp, 190h
0x18003cbc6  pop     rdi
0x18003cbc7  pop     rsi
0x18003cbc8  pop     rbp
0x18003cbc9  retn
```
