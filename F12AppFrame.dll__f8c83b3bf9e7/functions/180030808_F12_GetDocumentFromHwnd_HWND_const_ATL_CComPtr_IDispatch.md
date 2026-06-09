# F12::GetDocumentFromHwnd(HWND__ * const,ATL::CComPtr<IDispatch> &)

- ea: `0x180030808`
- end: `0x180030a70`
- name: `?GetDocumentFromHwnd@F12@@YAJQEAUHWND__@@AEAV?$CComPtr@UIDispatch@@@ATL@@@Z`
- size: `616`
- prototype: `__int64 __fastcall(HWND hWnd, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180013a90`

## callees

- `0x180030808`
- `0x180035010`

## import_xrefs

- `USER32!RegisterWindowMessageW` at `0x18003082e`
- `USER32!RegisterWindowMessageW` at `0x18003082e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageTimeoutW` at `0x180030866`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageTimeoutW` at `0x180030866`
- `OLEACC!ObjectFromLresult` at `0x180030898`
- `OLEACC!ObjectFromLresult` at `0x180030898`

## pseudocode

```c
__int64 __fastcall F12::GetDocumentFromHwnd(HWND hWnd, _QWORD *a2)
{
  UINT v4; // eax
  void *v5; // rbx
  __int64 v6; // rcx
  int v7; // eax
  void *v8; // rcx
  void *v9; // rdi
  __int64 v11; // [rsp+40h] [rbp-30h] BYREF
  __int64 v12; // [rsp+48h] [rbp-28h] BYREF
  ULONG_PTR dwResult; // [rsp+50h] [rbp-20h] BYREF
  void *ppvObject; // [rsp+58h] [rbp-18h] BYREF
  void *v15; // [rsp+60h] [rbp-10h]
  void *v16; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v17; // [rsp+A8h] [rbp+38h] BYREF

  v4 = Msg;
  if ( !Msg )
  {
    v4 = RegisterWindowMessageW(L"WM_HTML_GETOBJECT");
    Msg = v4;
  }
  dwResult = 0;
  if ( !SendMessageTimeoutW(hWnd, v4, 0, 0, 2u, 0x7D0u, &dwResult) )
    return 2147500037LL;
  if ( !dwResult )
    return 2147500037LL;
  ppvObject = 0;
  if ( ObjectFromLresult(dwResult, &IID_IDispatch, 0, &ppvObject) )
    return 2147500037LL;
  v5 = ppvObject;
  v15 = ppvObject;
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 8LL))(ppvObject);
  v6 = 0;
  v17 = 0;
  if ( v5 )
  {
    (**(void (__fastcall ***)(void *, GUID *, __int64 *))v5)(v5, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v17);
    v6 = v17;
  }
  if ( v6 )
  {
    v12 = 0;
    if ( !(*(unsigned int (__fastcall **)(__int64, SID *, GUID *, __int64 *))(*(_QWORD *)v6 + 24LL))(
            v6,
            &SID_STopLevelBrowser,
            &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
            &v12) )
    {
      v11 = 0;
      if ( !(*(unsigned int (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v12 + 24LL))(
              v12,
              &IID_IWebBrowserApp,
              &GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e,
              &v11) )
      {
        v16 = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v11 + 144LL))(v11, &v16);
        v8 = v16;
        if ( !v7 && v5 != v16 )
        {
          v9 = v16;
          if ( v16 )
          {
            (*(void (**)(void))(*(_QWORD *)v16 + 8LL))();
            v8 = v16;
          }
          if ( v5 )
          {
            (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
            v8 = v16;
          }
          v5 = v9;
          v15 = v9;
        }
        if ( v8 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
      }
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v6 = v17;
  }
  if ( (void *)*a2 != v5 )
  {
    if ( v5 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 8LL))(v5);
      v6 = v17;
    }
    if ( *a2 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
      v6 = v17;
    }
    *a2 = v5;
  }
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v5 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x180030808  mov     [rsp-18h+arg_0], rbx
0x18003080d  push    rbp
0x18003080e  push    rsi
0x18003080f  push    rdi
0x180030810  mov     rbp, rsp
0x180030813  sub     rsp, 70h
0x180030817  mov     rsi, rdx
0x18003081a  mov     rbx, rcx
0x18003081d  mov     eax, cs:Msg
0x180030823  test    eax, eax
0x180030825  jnz     short loc_18003083A
0x180030827  lea     rcx, aWmHtmlGetobjec; "WM_HTML_GETOBJECT"
0x18003082e  call    cs:__imp_RegisterWindowMessageW
0x180030834  mov     cs:Msg, eax
0x18003083a  mov     [rbp+dwResult], 0
0x180030842  lea     rcx, [rbp+dwResult]
0x180030846  mov     [rsp+70h+lpdwResult], rcx; lpdwResult
0x18003084b  mov     [rsp+70h+uTimeout], 7D0h; uTimeout
0x180030853  mov     [rsp+70h+fuFlags], 2; fuFlags
0x18003085b  xor     r9d, r9d; lParam
0x18003085e  xor     r8d, r8d; wParam
0x180030861  mov     edx, eax; Msg
0x180030863  mov     rcx, rbx; hWnd
0x180030866  call    cs:__imp_SendMessageTimeoutW
0x18003086c  test    rax, rax
0x18003086f  jz      loc_180030A5B
0x180030875  mov     rcx, [rbp+dwResult]; lResult
0x180030879  test    rcx, rcx
0x18003087c  jz      loc_180030A5B
0x180030882  mov     [rbp+ppvObject], 0
0x18003088a  lea     r9, [rbp+ppvObject]; ppvObject
0x18003088e  xor     r8d, r8d; wParam
0x180030891  lea     rdx, IID_IDispatch; riid
0x180030898  call    cs:__imp_ObjectFromLresult
0x18003089e  test    eax, eax
0x1800308a0  jnz     loc_180030A5B
0x1800308a6  mov     rbx, [rbp+ppvObject]
0x1800308aa  mov     [rbp+var_10], rbx
0x1800308ae  test    rbx, rbx
0x1800308b1  jz      short loc_1800308C3
0x1800308b3  mov     rax, [rbx]
0x1800308b6  mov     rcx, rbx
0x1800308b9  mov     rax, [rax+8]
0x1800308bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308c2  nop
0x1800308c3  xor     ecx, ecx
0x1800308c5  mov     [rbp+arg_18], rcx
0x1800308c9  test    rbx, rbx
0x1800308cc  jz      short loc_1800308EB
0x1800308ce  mov     rax, [rbx]
0x1800308d1  lea     r8, [rbp+arg_18]
0x1800308d5  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x1800308dc  mov     rcx, rbx
0x1800308df  mov     rax, [rax]
0x1800308e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308e7  mov     rcx, [rbp+arg_18]
0x1800308eb  test    rcx, rcx
0x1800308ee  jz      loc_1800309F5
0x1800308f4  mov     [rbp+var_28], 0
0x1800308fc  mov     rax, [rcx]
0x1800308ff  lea     r9, [rbp+var_28]
0x180030903  lea     r8, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x18003090a  lea     rdx, SID_STopLevelBrowser
0x180030911  mov     rax, [rax+18h]
0x180030915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003091a  test    eax, eax
0x18003091c  jnz     loc_1800309DB
0x180030922  mov     [rbp+var_30], 0
0x18003092a  mov     rcx, [rbp+var_28]
0x18003092e  mov     rax, [rcx]
0x180030931  lea     r9, [rbp+var_30]
0x180030935  lea     r8, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x18003093c  lea     rdx, IID_IWebBrowserApp
0x180030943  mov     rax, [rax+18h]
0x180030947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003094c  test    eax, eax
0x18003094e  jnz     short loc_1800309C5
0x180030950  mov     [rbp+arg_10], 0
0x180030958  mov     rcx, [rbp+var_30]
0x18003095c  mov     rax, [rcx]
0x18003095f  lea     rdx, [rbp+arg_10]
0x180030963  mov     rax, [rax+90h]
0x18003096a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003096f  mov     rcx, [rbp+arg_10]
0x180030973  test    eax, eax
0x180030975  jnz     short loc_1800309B3
0x180030977  cmp     rbx, rcx
0x18003097a  jz      short loc_1800309B3
0x18003097c  mov     rdi, rcx
0x18003097f  test    rcx, rcx
0x180030982  jz      short loc_180030994
0x180030984  mov     rax, [rcx]
0x180030987  mov     rax, [rax+8]
0x18003098b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030990  mov     rcx, [rbp+arg_10]
0x180030994  test    rbx, rbx
0x180030997  jz      short loc_1800309AC
0x180030999  mov     rax, [rbx]
0x18003099c  mov     rcx, rbx
0x18003099f  mov     rax, [rax+10h]
0x1800309a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309a8  mov     rcx, [rbp+arg_10]
0x1800309ac  mov     rbx, rdi
0x1800309af  mov     [rbp+var_10], rbx
0x1800309b3  test    rcx, rcx
0x1800309b6  jz      short loc_1800309C5
0x1800309b8  mov     rax, [rcx]
0x1800309bb  mov     rax, [rax+10h]
0x1800309bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309c4  nop
0x1800309c5  mov     rcx, [rbp+var_30]
0x1800309c9  test    rcx, rcx
0x1800309cc  jz      short loc_1800309DB
0x1800309ce  mov     rax, [rcx]
0x1800309d1  mov     rax, [rax+10h]
0x1800309d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309da  nop
0x1800309db  mov     rcx, [rbp+var_28]
0x1800309df  test    rcx, rcx
0x1800309e2  jz      short loc_1800309F1
0x1800309e4  mov     rax, [rcx]
0x1800309e7  mov     rax, [rax+10h]
0x1800309eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309f0  nop
0x1800309f1  mov     rcx, [rbp+arg_18]
0x1800309f5  cmp     [rsi], rbx
0x1800309f8  jz      short loc_180030A30
0x1800309fa  test    rbx, rbx
0x1800309fd  jz      short loc_180030A12
0x1800309ff  mov     rax, [rbx]
0x180030a02  mov     rcx, rbx
0x180030a05  mov     rax, [rax+8]
0x180030a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a0e  mov     rcx, [rbp+arg_18]
0x180030a12  mov     rdx, [rsi]
0x180030a15  test    rdx, rdx
0x180030a18  jz      short loc_180030A2D
0x180030a1a  mov     rax, [rdx]
0x180030a1d  mov     rcx, rdx
0x180030a20  mov     rax, [rax+10h]
0x180030a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a29  mov     rcx, [rbp+arg_18]
0x180030a2d  mov     [rsi], rbx
0x180030a30  test    rcx, rcx
0x180030a33  jz      short loc_180030A42
0x180030a35  mov     rax, [rcx]
0x180030a38  mov     rax, [rax+10h]
0x180030a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a41  nop
0x180030a42  test    rbx, rbx
0x180030a45  jz      short loc_180030A57
0x180030a47  mov     rax, [rbx]
0x180030a4a  mov     rcx, rbx
0x180030a4d  mov     rax, [rax+10h]
0x180030a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a56  nop
0x180030a57  xor     eax, eax
0x180030a59  jmp     short loc_180030A60
0x180030a5b  mov     eax, 80004005h
0x180030a60  mov     rbx, [rsp+70h+arg_0]
0x180030a68  add     rsp, 70h
0x180030a6c  pop     rdi
0x180030a6d  pop     rsi
0x180030a6e  pop     rbp
0x180030a6f  retn
```
