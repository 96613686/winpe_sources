# CodecUtilPrivate::SetImageAsDesktopWallpaperDirect(Base::Path const &)

- ea: `0x18007a44c`
- end: `0x18007a515`
- name: `?SetImageAsDesktopWallpaperDirect@CodecUtilPrivate@@YAXAEBVPath@Base@@@Z`
- size: `201`
- prototype: `void __fastcall(CodecUtilPrivate *__hidden this, const struct Path *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007a024`

## callees

- `0x18000cb74`
- `0x18007a44c`
- `0x180080010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18007a47c`
- `ole32!CoCreateInstance` at `0x18007a47c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18007a488`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18007a4ac`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18007a4db`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18007a4fe`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18007a488`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18007a4ac`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18007a4db`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18007a4fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CodecUtilPrivate::SetImageAsDesktopWallpaperDirect(CodecUtilPrivate *this, const struct Path *a2)
{
  HRESULT v3; // eax
  int v4; // edx
  int v5; // eax
  int v6; // edx
  int v7; // eax
  int v8; // edx
  int v9; // eax
  int v10; // edx
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF
  __int64 v12; // [rsp+50h] [rbp+18h] BYREF

  ppv = 0;
  v3 = CoCreateInstance(&CLSID_ActiveDesktop, 0, 1u, &GUID_f490eb00_1240_11d1_9888_006097deacf9, &ppv);
  if ( v3 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v3, v4);
    __debugbreak();
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)ppv + 40LL))(ppv, *(_QWORD *)this, 0);
  if ( v5 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v5, v6);
    __debugbreak();
  }
  v12 = 8;
  v7 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, _QWORD))(*(_QWORD *)ppv + 56LL))(ppv, &v12, 0);
  if ( v7 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v7, v8);
    __debugbreak();
  }
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 39);
  if ( v9 < 0 )
    Base::Throw((Base *)(unsigned int)v9, v10);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppv);
}

```

## disassembly

```asm
0x18007a44c  push    rbx
0x18007a44e  sub     rsp, 30h
0x18007a452  mov     rbx, rcx
0x18007a455  mov     [rsp+38h+arg_8], 0
0x18007a45e  lea     rax, [rsp+38h+arg_8]
0x18007a463  mov     [rsp+38h+ppv], rax; ppv
0x18007a468  lea     r9, _GUID_f490eb00_1240_11d1_9888_006097deacf9; riid
0x18007a46f  xor     edx, edx; pUnkOuter
0x18007a471  lea     r8d, [rdx+1]; dwClsContext
0x18007a475  lea     rcx, CLSID_ActiveDesktop; rclsid
0x18007a47c  call    cs:__imp_CoCreateInstance
0x18007a482  test    eax, eax
0x18007a484  jns     short loc_18007A48F
0x18007a486  mov     ecx, eax
0x18007a488  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18007a48e  int     3; Trap to Debugger
0x18007a48f  mov     rcx, [rsp+38h+arg_8]
0x18007a494  mov     rax, [rcx]
0x18007a497  xor     r8d, r8d
0x18007a49a  mov     rdx, [rbx]
0x18007a49d  mov     rax, [rax+28h]
0x18007a4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a4a6  test    eax, eax
0x18007a4a8  jns     short loc_18007A4B3
0x18007a4aa  mov     ecx, eax
0x18007a4ac  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18007a4b2  int     3; Trap to Debugger
0x18007a4b3  mov     [rsp+38h+arg_10], 8
0x18007a4bc  mov     rcx, [rsp+38h+arg_8]
0x18007a4c1  mov     rax, [rcx]
0x18007a4c4  xor     r8d, r8d
0x18007a4c7  lea     rdx, [rsp+38h+arg_10]
0x18007a4cc  mov     rax, [rax+38h]
0x18007a4d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a4d5  test    eax, eax
0x18007a4d7  jns     short loc_18007A4E2
0x18007a4d9  mov     ecx, eax
0x18007a4db  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18007a4e1  int     3; Trap to Debugger
0x18007a4e2  mov     rcx, [rsp+38h+arg_8]
0x18007a4e7  mov     rax, [rcx]
0x18007a4ea  mov     edx, 27h ; '''
0x18007a4ef  mov     rax, [rax+18h]
0x18007a4f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a4f8  test    eax, eax
0x18007a4fa  jns     short loc_18007A505
0x18007a4fc  mov     ecx, eax
0x18007a4fe  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18007a504  nop
0x18007a505  lea     rcx, [rsp+38h+arg_8]
0x18007a50a  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18007a50f  add     rsp, 30h
0x18007a513  pop     rbx
0x18007a514  retn
```
