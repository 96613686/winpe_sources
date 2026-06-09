# CNavigateButton::_Execute(void)

- ea: `0x18000a8e0`
- end: `0x18000aa31`
- name: `?_Execute@CNavigateButton@@AEAAXXZ`
- size: `337`
- prototype: `void __fastcall(IUnknown **this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x18000a4a0`

## callees

- `0x18000a218`
- `0x18000a8e0`
- `0x18000b6de`
- `0x18000c010`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x18000a9f8`
- `SHELL32!ShellExecuteExW` at `0x18000a9f8`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000a940`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000a940`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000a98e`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000a9b3`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000a98e`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000a9b3`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000a982`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000a9a7`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000a982`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000a9a7`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000aa01`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000aa0a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000aa01`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000aa0a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000aa2a`

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
              (const struct DirectUI::PropertyInfo *)&off_18000D930,
              2,
              0);
    String = DirectUI::Value::GetString(Value);
    v7 = DirectUI::Element::GetValue(
           (DirectUI::Element *)this,
           (const struct DirectUI::PropertyInfo *)&off_18000D900,
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
0x18000a8e0  mov     [rsp-8+arg_0], rbx
0x18000a8e5  push    rbp
0x18000a8e6  push    rsi
0x18000a8e7  push    rdi
0x18000a8e8  push    r14
0x18000a8ea  push    r15
0x18000a8ec  lea     rbp, [rsp-37h]
0x18000a8f1  sub     rsp, 90h
0x18000a8f8  xor     edi, edi
0x18000a8fa  lea     rdx, [rbp+57h+arg_18]; struct DirectUI::Value **
0x18000a8fe  mov     [rbp+57h+arg_18], rdi
0x18000a902  mov     rbx, rcx
0x18000a905  call    ?GetShellExecute@CNavigateButton@@QEAAPEBGPEAPEAVValue@DirectUI@@@Z; CNavigateButton::GetShellExecute(DirectUI::Value * *)
0x18000a90a  mov     r15, rax
0x18000a90d  test    rax, rax
0x18000a910  jz      loc_18000AA10
0x18000a916  cmp     [rax], di
0x18000a919  jz      loc_18000AA10
0x18000a91f  mov     rcx, [rbx+0D8h]; punk
0x18000a926  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x18000a92a  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18000a931  mov     [rbp+57h+arg_10], rdi
0x18000a935  lea     rdx, SID_STopLevelBrowser; guidService
0x18000a93c  mov     [rbp+57h+ppvOut], rdi
0x18000a940  call    cs:__imp_IUnknown_QueryService
0x18000a946  test    eax, eax
0x18000a948  js      short loc_18000A96E
0x18000a94a  mov     rcx, [rbp+57h+ppvOut]
0x18000a94e  lea     rdx, [rbp+57h+arg_10]
0x18000a952  mov     rax, [rcx]
0x18000a955  mov     rax, [rax+18h]
0x18000a959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a95e  mov     rcx, [rbp+57h+ppvOut]
0x18000a962  mov     rax, [rcx]
0x18000a965  mov     rax, [rax+10h]
0x18000a969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a96e  xor     r9d, r9d
0x18000a971  lea     rdx, off_18000D930; "ShellExecuteVerb"
0x18000a978  mov     rcx, rbx
0x18000a97b  lea     esi, [r9+2]
0x18000a97f  mov     r8d, esi
0x18000a982  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18000a988  mov     rcx, rax
0x18000a98b  mov     r14, rax
0x18000a98e  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18000a994  xor     r9d, r9d
0x18000a997  lea     rdx, off_18000D900; "ShellExecuteParams"
0x18000a99e  mov     r8d, esi
0x18000a9a1  mov     rcx, rbx
0x18000a9a4  mov     rdi, rax
0x18000a9a7  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18000a9ad  mov     rcx, rax
0x18000a9b0  mov     rsi, rax
0x18000a9b3  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18000a9b9  xor     edx, edx; Val
0x18000a9bb  lea     rcx, [rbp+57h+pExecInfo]; void *
0x18000a9bf  mov     rbx, rax
0x18000a9c2  lea     r8d, [rdx+70h]; Size
0x18000a9c6  call    memset_0
0x18000a9cb  mov     rcx, [rbp+57h+arg_10]
0x18000a9cf  mov     [rbp+57h+pExecInfo.hwnd], rcx
0x18000a9d3  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x18000a9d7  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x18000a9de  mov     [rbp+57h+pExecInfo.nShow], 5
0x18000a9e5  mov     [rbp+57h+pExecInfo.lpFile], r15
0x18000a9e9  mov     [rbp+57h+pExecInfo.lpVerb], rdi
0x18000a9ed  mov     [rbp+57h+pExecInfo.lpParameters], rbx
0x18000a9f1  mov     [rbp+57h+pExecInfo.fMask], 400020Ch
0x18000a9f8  call    cs:__imp_ShellExecuteExW
0x18000a9fe  mov     rcx, r14
0x18000aa01  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000aa07  mov     rcx, rsi
0x18000aa0a  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000aa10  mov     rcx, [rbp+57h+arg_18]
0x18000aa14  mov     rbx, [rsp+0B0h+arg_0]
0x18000aa1c  add     rsp, 90h
0x18000aa23  pop     r15
0x18000aa25  pop     r14
0x18000aa27  pop     rdi
0x18000aa28  pop     rsi
0x18000aa29  pop     rbp
0x18000aa2a  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
