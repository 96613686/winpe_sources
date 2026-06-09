# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::InstallProgress(void)

- ea: `0x180023134`
- end: `0x1800231ee`
- name: `?InstallProgress@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAANXZ`
- size: `186`
- prototype: `double __fastcall(winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026270`

## callees

- `0x180022a0c`
- `0x180023134`
- `0x1800257a8`
- `0x1800271ac`
- `0x18002b010`

## string_xrefs

- `0x180023183`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
double __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::InstallProgress(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *this)
{
  int v2; // eax
  double v3; // xmm6_8
  double result; // xmm0_8
  const wil::ResultException *v5; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF
  __int64 v9; // [rsp+60h] [rbp+18h] BYREF

  try
  {
    winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(this, &v8);
    *((_DWORD *)this + 14) = 0;
    v9 = 0;
    v2 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 48LL))(v8, &v9);
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
        (const char *)(unsigned int)v2,
        (int)v5);
    if ( (_DWORD)v9 == 10 )
    {
      v3 = (double)SHIDWORD(v9) / 100.0;
      if ( v8 )
        winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v8);
      result = v3;
    }
    else
    {
      if ( v8 )
        winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v8);
      result = 0.0;
    }
  }
  catch ( const wil::ResultException *v5 )
  {
    *((_DWORD *)this + 14) = *((_DWORD *)v5 + 8);
    return 0.0;
  }
  catch ( ... )
  {
    *((_DWORD *)this + 14) = -2147467259;
    return 0.0;
  }
  return result;
}

```

## disassembly

```asm
0x180023134  mov     [rsp+arg_0], rcx
0x180023139  push    rbx
0x18002313a  sub     rsp, 40h
0x18002313e  movaps  [rsp+48h+var_18], xmm6
0x180023143  mov     rbx, rcx
0x180023146  lea     rdx, [rsp+48h+arg_8]
0x18002314b  call    ?GetUsoSession@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA?AU?$com_ptr@UIUsoSessionCommon@@@6@XZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(void)
0x180023150  nop
0x180023151  mov     dword ptr [rbx+38h], 0
0x180023158  mov     [rsp+48h+arg_10], 0
0x180023161  mov     rcx, [rsp+48h+arg_8]
0x180023166  mov     rax, [rcx]
0x180023169  lea     rdx, [rsp+48h+arg_10]
0x18002316e  mov     rax, [rax+30h]
0x180023172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023177  mov     rcx, [rsp+48h]; this
0x18002317c  test    eax, eax
0x18002317e  jns     short loc_180023194
0x180023180  mov     r9d, eax; char *
0x180023183  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x18002318a  mov     edx, 0E9h; void *
0x18002318f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180023194  cmp     dword ptr [rsp+48h+arg_10], 0Ah
0x180023199  jnz     short loc_1800231C6
0x18002319b  mov     eax, dword ptr [rsp+48h+arg_10+4]
0x18002319f  xorps   xmm6, xmm6
0x1800231a2  cvtsi2sd xmm6, rax
0x1800231a7  divsd   xmm6, cs:__real@4059000000000000
0x1800231af  cmp     [rsp+48h+arg_8], 0
0x1800231b5  jz      short loc_1800231C1
0x1800231b7  lea     rcx, [rsp+48h+arg_8]
0x1800231bc  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x1800231c1  movaps  xmm0, xmm6
0x1800231c4  jmp     short loc_1800231E2
0x1800231c6  cmp     [rsp+48h+arg_8], 0
0x1800231cc  jz      short loc_1800231D8
0x1800231ce  lea     rcx, [rsp+48h+arg_8]
0x1800231d3  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x1800231d8  xorps   xmm0, xmm0
0x1800231db  jmp     short loc_1800231E2
0x1800231dd  jmp     short $+2
0x1800231df  xorps   xmm0, xmm0
0x1800231e2  movaps  xmm6, [rsp+48h+var_18]
0x1800231e7  add     rsp, 40h
0x1800231eb  pop     rbx
0x1800231ec  retn
```
