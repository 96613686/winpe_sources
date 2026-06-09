# AccessibilityCplCore::GetParentWindow(void)

- ea: `0x1800071f0`
- end: `0x1800072b7`
- name: `?GetParentWindow@AccessibilityCplCore@@IEAAPEAUHWND__@@XZ`
- size: `199`
- prototype: `HWND __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800134a0`
- `0x18001cc70`

## callees

- `0x18000466c`
- `0x1800071f0`
- `0x18002e010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000727f`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000727f`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000724f`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000724f`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x180007226`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x180007226`

## pseudocode

```c
HWND __fastcall AccessibilityCplCore::GetParentWindow(AccessibilityCplCore *this)
{
  void **v2; // rbx
  IUnknown *v3; // rcx
  IUnknown *v4; // rbx
  HWND phwnd; // [rsp+30h] [rbp+8h] BYREF
  void *ppvOut; // [rsp+38h] [rbp+10h] BYREF
  void *v8; // [rsp+40h] [rbp+18h] BYREF

  phwnd = (HWND)*((_QWORD *)this + 1);
  if ( !phwnd )
  {
    v2 = (void **)((char *)this + 16);
    if ( *((_QWORD *)this + 2)
      || IUnknown_GetSite(*((IUnknown **)this + 12), &GUID_00000000_0000_0000_c000_000000000046, v2) >= 0 )
    {
      v3 = (IUnknown *)*v2;
      ppvOut = 0;
      if ( IUnknown_QueryService(
             v3,
             (const GUID *const)&SID_STopLevelBrowser,
             &GUID_00000000_0000_0000_c000_000000000046,
             &ppvOut) >= 0 )
      {
        v4 = (IUnknown *)ppvOut;
        v8 = ppvOut;
        if ( ppvOut )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 8LL))(ppvOut);
        if ( IUnknown_GetWindow(v4, &phwnd) >= 0 )
          *((_QWORD *)this + 1) = phwnd;
        else
          phwnd = 0;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
      }
    }
  }
  return phwnd;
}

```

## disassembly

```asm
0x1800071f0  mov     [rsp+arg_18], rbx
0x1800071f5  push    rdi
0x1800071f6  sub     rsp, 20h
0x1800071fa  mov     rax, [rcx+8]
0x1800071fe  mov     rdi, rcx
0x180007201  mov     [rsp+28h+phwnd], rax
0x180007206  test    rax, rax
0x180007209  jnz     loc_1800072A7
0x18000720f  lea     rbx, [rcx+10h]
0x180007213  cmp     [rbx], rax
0x180007216  jnz     short loc_180007230
0x180007218  mov     rcx, [rcx+60h]; punk
0x18000721c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180007223  mov     r8, rbx; ppv
0x180007226  call    cs:__imp_IUnknown_GetSite
0x18000722c  test    eax, eax
0x18000722e  js      short loc_1800072A7
0x180007230  mov     rcx, [rbx]; punk
0x180007233  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x180007238  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000723f  mov     [rsp+28h+ppvOut], 0
0x180007248  lea     rdx, SID_STopLevelBrowser; guidService
0x18000724f  call    cs:__imp_IUnknown_QueryService
0x180007255  test    eax, eax
0x180007257  js      short loc_1800072A7
0x180007259  mov     rbx, [rsp+28h+ppvOut]
0x18000725e  mov     [rsp+28h+arg_10], rbx
0x180007263  test    rbx, rbx
0x180007266  jz      short loc_180007277
0x180007268  mov     rax, [rbx]
0x18000726b  mov     rcx, rbx
0x18000726e  mov     rax, [rax+8]
0x180007272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007277  lea     rdx, [rsp+28h+phwnd]; phwnd
0x18000727c  mov     rcx, rbx; punk
0x18000727f  call    cs:__imp_IUnknown_GetWindow
0x180007285  test    eax, eax
0x180007287  jns     short loc_180007294
0x180007289  mov     [rsp+28h+phwnd], 0
0x180007292  jmp     short loc_18000729D
0x180007294  mov     rax, [rsp+28h+phwnd]
0x180007299  mov     [rdi+8], rax
0x18000729d  lea     rcx, [rsp+28h+arg_10]
0x1800072a2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800072a7  mov     rax, [rsp+28h+phwnd]
0x1800072ac  mov     rbx, [rsp+28h+arg_18]
0x1800072b1  add     rsp, 20h
0x1800072b5  pop     rdi
0x1800072b6  retn
```
