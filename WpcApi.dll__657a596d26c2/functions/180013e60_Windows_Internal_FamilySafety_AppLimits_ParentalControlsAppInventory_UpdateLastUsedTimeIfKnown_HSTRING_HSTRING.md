# Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInventory::UpdateLastUsedTimeIfKnown(HSTRING__ *,HSTRING__ *,uchar *)

- ea: `0x180013e60`
- end: `0x180013efa`
- name: `?UpdateLastUsedTimeIfKnown@ParentalControlsAppInventory@AppLimits@FamilySafety@Internal@Windows@@EEAAJPEAUHSTRING__@@0PEAE@Z`
- size: `154`
- prototype: `__int64 __fastcall(Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInventory *__hidden this, HSTRING, HSTRING, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800032a0`
- `0x18000e248`
- `0x180013e60`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInventory::UpdateLastUsedTimeIfKnown(
        Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInventory *this,
        HSTRING a2,
        HSTRING a3,
        unsigned __int8 *a4)
{
  unsigned int updated; // ebx
  _QWORD *v5; // rdx
  _QWORD v7[7]; // [rsp+20h] [rbp-50h] BYREF
  _QWORD *v8; // [rsp+58h] [rbp-18h]
  HSTRING v9; // [rsp+88h] [rbp+18h] BYREF
  HSTRING v10; // [rsp+90h] [rbp+20h] BYREF
  unsigned __int8 *v11; // [rsp+98h] [rbp+28h] BYREF

  v11 = a4;
  v10 = a3;
  v9 = a2;
  v7[0] = &std::_Func_impl_no_alloc<_lambda_239bd7fe1db49e9a255a8ce28fba4e12_,void,>::`vftable';
  v7[1] = &v11;
  v7[2] = &v9;
  v7[3] = &v10;
  v8 = v7;
  updated = ApiBoundary::CatchActivity<wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser,>((__int64)v7);
  if ( v8 )
  {
    v5 = v7;
    LOBYTE(v5) = v8 != v7;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v8 + 32LL))(v8, v5);
  }
  return updated;
}

```

## disassembly

```asm
0x180013e60  mov     rax, rsp
0x180013e63  mov     [rax+8], rbx
0x180013e67  mov     [rax+20h], r9
0x180013e6b  mov     [rax+18h], r8
0x180013e6f  mov     [rax+10h], rdx
0x180013e73  push    rbp
0x180013e74  mov     rbp, rsp
0x180013e77  sub     rsp, 70h
0x180013e7b  mov     rax, cs:__security_cookie
0x180013e82  xor     rax, rsp
0x180013e85  mov     [rbp+var_10], rax
0x180013e89  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_239bd7fe1db49e9a255a8ce28fba4e12_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_239bd7fe1db49e9a255a8ce28fba4e12_,void,>::`vftable'
0x180013e90  mov     [rbp+var_50], rax
0x180013e94  lea     rax, [rbp+arg_18]
0x180013e98  mov     [rbp+var_48], rax
0x180013e9c  lea     rax, [rbp+arg_8]
0x180013ea0  mov     [rbp+var_40], rax
0x180013ea4  lea     rax, [rbp+arg_10]
0x180013ea8  mov     [rbp+var_38], rax
0x180013eac  lea     rax, [rbp+var_50]
0x180013eb0  mov     [rbp+var_18], rax
0x180013eb4  lea     rcx, [rbp+var_50]
0x180013eb8  call    ??$CatchActivity@VWpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser@AppInventoryLogger@AppInventory@AppLimits@wpc@@$$V@ApiBoundary@@YAJAEBV?$function@$$A6AXXZ@std@@@Z; ApiBoundary::CatchActivity<wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser,>(std::function<void (void)> const &)
0x180013ebd  mov     ebx, eax
0x180013ebf  mov     rcx, [rbp+var_18]
0x180013ec3  test    rcx, rcx
0x180013ec6  jz      short loc_180013EDE
0x180013ec8  mov     rax, [rcx]
0x180013ecb  lea     rdx, [rbp+var_50]
0x180013ecf  cmp     rcx, rdx
0x180013ed2  setnz   dl
0x180013ed5  mov     rax, [rax+20h]
0x180013ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ede  mov     eax, ebx
0x180013ee0  mov     rcx, [rbp+var_10]
0x180013ee4  xor     rcx, rsp; StackCookie
0x180013ee7  call    __security_check_cookie
0x180013eec  mov     rbx, [rsp+70h+arg_0]
0x180013ef4  add     rsp, 70h
0x180013ef8  pop     rbp
0x180013ef9  retn
```
