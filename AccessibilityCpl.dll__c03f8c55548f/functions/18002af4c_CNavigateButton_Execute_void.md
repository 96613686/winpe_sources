# CNavigateButton::_Execute(void)

- ea: `0x18002af4c`
- end: `0x18002b09d`
- name: `?_Execute@CNavigateButton@@AEAAXXZ`
- size: `337`
- prototype: `void __fastcall(CNavigateButton *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x18002ab60`

## callees

- `0x18002a908`
- `0x18002af4c`
- `0x18002d1ee`
- `0x18002e010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002afac`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002afac`
- `SHELL32!ShellExecuteExW` at `0x18002b064`
- `SHELL32!ShellExecuteExW` at `0x18002b064`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002afee`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002b013`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002afee`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002b013`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18002affa`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18002b01f`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18002affa`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18002b01f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002b06d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002b076`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002b06d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002b076`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002b096`

## pseudocode

```c
void __fastcall CNavigateButton::_Execute(IUnknown **this)
{
  const unsigned __int16 *ShellExecute; // rax
  const WCHAR *v3; // r15
  IUnknown *v4; // rcx
  DirectUI::Value *Value; // r14
  const WCHAR *String; // rdi
  DirectUI::Value *v7; // rsi
  const WCHAR *v8; // rbx
  SHELLEXECUTEINFOW pExecInfo; // [rsp+20h] [rbp-39h] BYREF
  void *ppvOut; // [rsp+C8h] [rbp+6Fh] BYREF
  HWND v11; // [rsp+D0h] [rbp+77h] BYREF
  struct DirectUI::Value *v12; // [rsp+D8h] [rbp+7Fh] BYREF

  v12 = 0;
  ShellExecute = CNavigateButton::GetShellExecute((CNavigateButton *)this, &v12);
  v3 = ShellExecute;
  if ( ShellExecute && *ShellExecute )
  {
    v4 = this[27];
    v11 = 0;
    ppvOut = 0;
    if ( IUnknown_QueryService(
           v4,
           (const GUID *const)&SID_STopLevelBrowser,
           &GUID_000214e2_0000_0000_c000_000000000046,
           &ppvOut) >= 0 )
    {
      (*(void (__fastcall **)(void *, HWND *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, &v11);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
    Value = DirectUI::Element::GetValue(
              (DirectUI::Element *)this,
              (const struct DirectUI::PropertyInfo *)&off_18002FB90,
              2,
              0);
    String = DirectUI::Value::GetString(Value);
    v7 = DirectUI::Element::GetValue(
           (DirectUI::Element *)this,
           (const struct DirectUI::PropertyInfo *)&off_18002FB60,
           2,
           0);
    v8 = DirectUI::Value::GetString(v7);
    memset_0(&pExecInfo, 0, sizeof(pExecInfo));
    pExecInfo.hwnd = v11;
    pExecInfo.cbSize = 112;
    pExecInfo.nShow = 5;
    pExecInfo.lpFile = v3;
    pExecInfo.lpVerb = String;
    pExecInfo.lpParameters = v8;
    pExecInfo.fMask = 67109388;
    ShellExecuteExW(&pExecInfo);
    DirectUI::Value::Release(Value);
    DirectUI::Value::Release(v7);
  }
  DirectUI::Value::Release(v12);
}

```

## disassembly

```asm
0x18002af4c  mov     [rsp-8+arg_0], rbx
0x18002af51  push    rbp
0x18002af52  push    rsi
0x18002af53  push    rdi
0x18002af54  push    r14
0x18002af56  push    r15
0x18002af58  lea     rbp, [rsp-37h]
0x18002af5d  sub     rsp, 90h
0x18002af64  xor     edi, edi
0x18002af66  lea     rdx, [rbp+57h+arg_18]; struct DirectUI::Value **
0x18002af6a  mov     [rbp+57h+arg_18], rdi
0x18002af6e  mov     rbx, rcx
0x18002af71  call    ?GetShellExecute@CNavigateButton@@QEAAPEBGPEAPEAVValue@DirectUI@@@Z; CNavigateButton::GetShellExecute(DirectUI::Value * *)
0x18002af76  mov     r15, rax
0x18002af79  test    rax, rax
0x18002af7c  jz      loc_18002B07C
0x18002af82  cmp     [rax], di
0x18002af85  jz      loc_18002B07C
0x18002af8b  mov     rcx, [rbx+0D8h]; punk
0x18002af92  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x18002af96  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18002af9d  mov     [rbp+57h+arg_10], rdi
0x18002afa1  lea     rdx, SID_STopLevelBrowser; guidService
0x18002afa8  mov     [rbp+57h+ppvOut], rdi
0x18002afac  call    cs:__imp_IUnknown_QueryService
0x18002afb2  test    eax, eax
0x18002afb4  js      short loc_18002AFDA
0x18002afb6  mov     rcx, [rbp+57h+ppvOut]
0x18002afba  lea     rdx, [rbp+57h+arg_10]
0x18002afbe  mov     rax, [rcx]
0x18002afc1  mov     rax, [rax+18h]
0x18002afc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002afca  mov     rcx, [rbp+57h+ppvOut]
0x18002afce  mov     rax, [rcx]
0x18002afd1  mov     rax, [rax+10h]
0x18002afd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002afda  xor     r9d, r9d
0x18002afdd  lea     rdx, off_18002FB90; "ShellExecuteVerb"
0x18002afe4  mov     rcx, rbx
0x18002afe7  lea     esi, [r9+2]
0x18002afeb  mov     r8d, esi
0x18002afee  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18002aff4  mov     rcx, rax
0x18002aff7  mov     r14, rax
0x18002affa  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18002b000  xor     r9d, r9d
0x18002b003  lea     rdx, off_18002FB60; "ShellExecuteParams"
0x18002b00a  mov     r8d, esi
0x18002b00d  mov     rcx, rbx
0x18002b010  mov     rdi, rax
0x18002b013  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18002b019  mov     rcx, rax
0x18002b01c  mov     rsi, rax
0x18002b01f  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18002b025  xor     edx, edx; Val
0x18002b027  lea     rcx, [rbp+57h+pExecInfo]; void *
0x18002b02b  mov     rbx, rax
0x18002b02e  lea     r8d, [rdx+70h]; Size
0x18002b032  call    memset_0
0x18002b037  mov     rcx, [rbp+57h+arg_10]
0x18002b03b  mov     [rbp+57h+pExecInfo.hwnd], rcx
0x18002b03f  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x18002b043  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x18002b04a  mov     [rbp+57h+pExecInfo.nShow], 5
0x18002b051  mov     [rbp+57h+pExecInfo.lpFile], r15
0x18002b055  mov     [rbp+57h+pExecInfo.lpVerb], rdi
0x18002b059  mov     [rbp+57h+pExecInfo.lpParameters], rbx
0x18002b05d  mov     [rbp+57h+pExecInfo.fMask], 400020Ch
0x18002b064  call    cs:__imp_ShellExecuteExW
0x18002b06a  mov     rcx, r14
0x18002b06d  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18002b073  mov     rcx, rsi
0x18002b076  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18002b07c  mov     rcx, [rbp+57h+arg_18]
0x18002b080  mov     rbx, [rsp+0B0h+arg_0]
0x18002b088  add     rsp, 90h
0x18002b08f  pop     r15
0x18002b091  pop     r14
0x18002b093  pop     rdi
0x18002b094  pop     rsi
0x18002b095  pop     rbp
0x18002b096  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
