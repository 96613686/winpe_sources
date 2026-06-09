# CControlPanelPage::LayoutInitialized(void)

- ea: `0x18002c718`
- end: `0x18002c8c6`
- name: `?LayoutInitialized@CControlPanelPage@@UEAAJXZ`
- size: `430`
- prototype: `__int64 __fastcall(CControlPanelPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x18001c5c0`

## callees

- `0x18002c718`
- `0x18002d220`
- `0x18002e010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002c80c`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002c80c`
- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x18002c795`
- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x18002c795`

## pseudocode

```c
__int64 __fastcall CControlPanelPage::LayoutInitialized(CControlPanelPage *this)
{
  char *v2; // rcx
  __int64 v3; // rax
  IUnknown *v4; // rcx
  __int64 v6; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v7; // [rsp+38h] [rbp-C8h] BYREF
  void *ppvOut; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v9; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v10[528]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = (char *)this - 224;
  if ( !*((_DWORD *)v2 + 58) )
  {
    v3 = *(_QWORD *)v2;
    v6 = 0;
    if ( (*(int (__fastcall **)(char *, GUID *, __int64 *))(v3 + 368))(
           v2,
           &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
           &v6) >= 0 )
    {
      IUnknown_ProfferService(*((_QWORD *)this - 1), &IID_IShellSearchTargetServices, v6, (char *)this + 8);
      v9 = 0;
      if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v6)(v6, &GUID_dda3a58a_43da_4a43_a5f2_f7abf6e3c026, &v9) >= 0 )
      {
        if ( (*(int (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v9 + 24LL))(v9, v10, 260) >= 0 )
        {
          v4 = (IUnknown *)*((_QWORD *)this - 1);
          ppvOut = 0;
          if ( IUnknown_QueryService(
                 v4,
                 (const GUID *const)&SID_SNavBar,
                 &GUID_a6087428_3be3_4d73_b308_7c04a540bf1a,
                 &ppvOut) >= 0 )
          {
            v7 = 0;
            if ( (*(int (__fastcall **)(void *, __int64 *, GUID *, __int64 *))(*(_QWORD *)ppvOut + 24LL))(
                   ppvOut,
                   OID_OSearchControl,
                   &GUID_111f7c32_0546_4227_8b7f_c53a0b114a0f,
                   &v7) >= 0 )
            {
              (*(void (__fastcall **)(__int64, _BYTE *, _QWORD))(*(_QWORD *)v7 + 64LL))(v7, v10, 0);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
          }
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002c718  mov     [rsp-8+arg_8], rbx
0x18002c71d  push    rbp
0x18002c71e  lea     rbp, [rsp-170h]
0x18002c726  sub     rsp, 270h
0x18002c72d  mov     rax, cs:__security_cookie
0x18002c734  xor     rax, rsp
0x18002c737  mov     [rbp+170h+var_10], rax
0x18002c73e  mov     rbx, rcx
0x18002c741  add     rcx, 0FFFFFFFFFFFFFF20h
0x18002c748  cmp     dword ptr [rcx+0E8h], 0
0x18002c74f  jnz     loc_18002C8A4
0x18002c755  mov     rax, [rcx]
0x18002c758  lea     r8, [rsp+270h+var_240]
0x18002c75d  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x18002c764  mov     [rsp+270h+var_240], 0
0x18002c76d  mov     rax, [rax+170h]
0x18002c774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c779  test    eax, eax
0x18002c77b  js      loc_18002C8A4
0x18002c781  mov     r8, [rsp+270h+var_240]
0x18002c786  lea     r9, [rbx+8]
0x18002c78a  mov     rcx, [rbx-8]
0x18002c78e  lea     rdx, IID_IShellSearchTargetServices
0x18002c795  call    cs:__imp_IUnknown_ProfferService
0x18002c79b  mov     rcx, [rsp+270h+var_240]
0x18002c7a0  lea     r8, [rsp+270h+var_228]
0x18002c7a5  mov     [rsp+270h+var_228], 0
0x18002c7ae  lea     rdx, _GUID_dda3a58a_43da_4a43_a5f2_f7abf6e3c026
0x18002c7b5  mov     rax, [rcx]
0x18002c7b8  mov     rax, [rax]
0x18002c7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7c0  test    eax, eax
0x18002c7c2  js      loc_18002C893
0x18002c7c8  mov     rcx, [rsp+270h+var_228]
0x18002c7cd  lea     rdx, [rsp+270h+var_220]
0x18002c7d2  mov     r8d, 104h
0x18002c7d8  mov     rax, [rcx]
0x18002c7db  mov     rax, [rax+18h]
0x18002c7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7e4  test    eax, eax
0x18002c7e6  js      loc_18002C882
0x18002c7ec  mov     rcx, [rbx-8]; punk
0x18002c7f0  lea     r9, [rsp+270h+ppvOut]; ppvOut
0x18002c7f5  lea     r8, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a; riid
0x18002c7fc  mov     [rsp+270h+ppvOut], 0
0x18002c805  lea     rdx, SID_SNavBar; guidService
0x18002c80c  call    cs:__imp_IUnknown_QueryService
0x18002c812  test    eax, eax
0x18002c814  js      short loc_18002C882
0x18002c816  mov     rcx, [rsp+270h+ppvOut]
0x18002c81b  lea     r9, [rsp+270h+var_238]
0x18002c820  mov     [rsp+270h+var_238], 0
0x18002c829  lea     r8, _GUID_111f7c32_0546_4227_8b7f_c53a0b114a0f
0x18002c830  lea     rdx, OID_OSearchControl
0x18002c837  mov     rax, [rcx]
0x18002c83a  mov     rax, [rax+18h]
0x18002c83e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c843  test    eax, eax
0x18002c845  js      short loc_18002C871
0x18002c847  mov     rcx, [rsp+270h+var_238]
0x18002c84c  lea     rdx, [rsp+270h+var_220]
0x18002c851  xor     r8d, r8d
0x18002c854  mov     rax, [rcx]
0x18002c857  mov     rax, [rax+40h]
0x18002c85b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c860  mov     rcx, [rsp+270h+var_238]
0x18002c865  mov     rax, [rcx]
0x18002c868  mov     rax, [rax+10h]
0x18002c86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c871  mov     rcx, [rsp+270h+ppvOut]
0x18002c876  mov     rax, [rcx]
0x18002c879  mov     rax, [rax+10h]
0x18002c87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c882  mov     rcx, [rsp+270h+var_228]
0x18002c887  mov     rax, [rcx]
0x18002c88a  mov     rax, [rax+10h]
0x18002c88e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c893  mov     rcx, [rsp+270h+var_240]
0x18002c898  mov     rax, [rcx]
0x18002c89b  mov     rax, [rax+10h]
0x18002c89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8a4  xor     eax, eax
0x18002c8a6  mov     rcx, [rbp+170h+var_10]
0x18002c8ad  xor     rcx, rsp; StackCookie
0x18002c8b0  call    __security_check_cookie
0x18002c8b5  mov     rbx, [rsp+270h+arg_8]
0x18002c8bd  add     rsp, 270h
0x18002c8c4  pop     rbp
0x18002c8c5  retn
```
