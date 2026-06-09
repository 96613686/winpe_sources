# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::DownloadProgress(void)

- ea: `0x180020a74`
- end: `0x180020b51`
- name: `?DownloadProgress@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAANXZ`
- size: `221`
- prototype: `double __fastcall(winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026000`

## callees

- `0x180020a74`
- `0x180022a0c`
- `0x1800257a8`
- `0x1800271ac`
- `0x18002b010`

## string_xrefs

- `0x180020ac3`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
double __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::DownloadProgress(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *this)
{
  int v2; // eax
  double result; // xmm0_8
  double v4; // xmm6_8
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
        (void *)0xCA,
        (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
        (const char *)(unsigned int)v2,
        (int)v5);
    if ( (_DWORD)v9 == 10 )
    {
      if ( v8 )
        winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v8);
      result = DOUBLE_1_0;
    }
    else if ( (_DWORD)v9 == 4 )
    {
      v4 = (double)SHIDWORD(v9) / 100.0;
      if ( v8 )
        winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v8);
      result = v4;
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
0x180020a74  mov     [rsp+arg_0], rcx
0x180020a79  push    rbx
0x180020a7a  sub     rsp, 40h
0x180020a7e  movaps  [rsp+48h+var_18], xmm6
0x180020a83  mov     rbx, rcx
0x180020a86  lea     rdx, [rsp+48h+arg_8]
0x180020a8b  call    ?GetUsoSession@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA?AU?$com_ptr@UIUsoSessionCommon@@@6@XZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(void)
0x180020a90  nop
0x180020a91  mov     dword ptr [rbx+38h], 0
0x180020a98  mov     [rsp+48h+arg_10], 0
0x180020aa1  mov     rcx, [rsp+48h+arg_8]
0x180020aa6  mov     rax, [rcx]
0x180020aa9  lea     rdx, [rsp+48h+arg_10]
0x180020aae  mov     rax, [rax+30h]
0x180020ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ab7  mov     rcx, [rsp+48h]; this
0x180020abc  test    eax, eax
0x180020abe  jns     short loc_180020AD4
0x180020ac0  mov     r9d, eax; char *
0x180020ac3  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180020aca  mov     edx, 0CAh; void *
0x180020acf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020ad4  cmp     dword ptr [rsp+48h+arg_10], 0Ah
0x180020ad9  jnz     short loc_180020AF7
0x180020adb  cmp     [rsp+48h+arg_8], 0
0x180020ae1  jz      short loc_180020AED
0x180020ae3  lea     rcx, [rsp+48h+arg_8]
0x180020ae8  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x180020aed  movsd   xmm0, cs:__real@3ff0000000000000
0x180020af5  jmp     short loc_180020B45
0x180020af7  cmp     dword ptr [rsp+48h+arg_10], 4
0x180020afc  jnz     short loc_180020B29
0x180020afe  mov     eax, dword ptr [rsp+48h+arg_10+4]
0x180020b02  xorps   xmm6, xmm6
0x180020b05  cvtsi2sd xmm6, rax
0x180020b0a  divsd   xmm6, cs:__real@4059000000000000
0x180020b12  cmp     [rsp+48h+arg_8], 0
0x180020b18  jz      short loc_180020B24
0x180020b1a  lea     rcx, [rsp+48h+arg_8]
0x180020b1f  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x180020b24  movaps  xmm0, xmm6
0x180020b27  jmp     short loc_180020B45
0x180020b29  cmp     [rsp+48h+arg_8], 0
0x180020b2f  jz      short loc_180020B3B
0x180020b31  lea     rcx, [rsp+48h+arg_8]
0x180020b36  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x180020b3b  xorps   xmm0, xmm0
0x180020b3e  jmp     short loc_180020B45
0x180020b40  jmp     short $+2
0x180020b42  xorps   xmm0, xmm0
0x180020b45  movaps  xmm6, [rsp+48h+var_18]
0x180020b4a  add     rsp, 40h
0x180020b4e  pop     rbx
0x180020b4f  retn
```
