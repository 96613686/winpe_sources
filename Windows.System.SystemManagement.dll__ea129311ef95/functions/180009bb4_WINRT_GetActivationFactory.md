# WINRT_GetActivationFactory

- ea: `0x180009bb4`
- end: `0x180009c7e`
- name: `WINRT_GetActivationFactory`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cf40`

## callees

- `0x180003eb0`
- `0x1800050bc`
- `0x180005a1c`
- `0x180005ebc`
- `0x180006214`
- `0x180009034`
- `0x180009bb4`

## string_xrefs

- `0x180009bdb`: `Windows.System.Update.SystemUpdateManager`

## pseudocode

```c
__int64 __fastcall WINRT_GetActivationFactory(HSTRING a1, _QWORD *a2)
{
  __int64 v4; // rax
  __int64 v5; // r9
  __int64 v6; // rcx
  _WORD *v7; // rax
  _WORD *v8; // rcx
  __int64 v9; // rbx
  __int64 result; // rax
  Microsoft::WRL::Details *v11; // rax
  __int64 v12; // rdx
  _WORD *v13; // [rsp+20h] [rbp-18h] BYREF
  __int64 v14; // [rsp+28h] [rbp-10h]
  HSTRING v15; // [rsp+40h] [rbp+8h] BYREF
  __int64 v16; // [rsp+50h] [rbp+18h] BYREF

  v15 = a1;
  winrt::hstring::operator std::basic_string_view<unsigned short>(&v15, &v13);
  v4 = std::_WChar_traits<unsigned short>::length(L"Windows.System.Update.SystemUpdateManager");
  try
  {
    v6 = 2 * v4;
    if ( 2 * v14 == 2 * v4 )
    {
      v7 = &v13[v14];
      v8 = (_WORD *)(v5 + v6);
      while ( v7 != v13 )
      {
        if ( *--v7 != *--v8 )
          goto LABEL_9;
      }
      winrt::impl::make_factory<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager>(&v16);
      v9 = v16;
      v16 = 0;
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v16);
      *a2 = v9;
      if ( v9 )
        return 0;
    }
    else
    {
LABEL_9:
      *a2 = 0;
    }
    v11 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
    result = Microsoft::WRL::Details::GetActivationFactory<1>(v11, v12, a1, a2);
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v16);
  }
  return result;
}

```

## disassembly

```asm
0x180009bb4  mov     rax, rsp
0x180009bb7  mov     [rax+10h], rbx
0x180009bbb  mov     [rax+20h], rsi
0x180009bbf  mov     [rax+8], rcx
0x180009bc3  push    rdi
0x180009bc4  sub     rsp, 30h
0x180009bc8  mov     rdi, rdx
0x180009bcb  mov     rsi, rcx
0x180009bce  lea     rdx, [rax-18h]
0x180009bd2  lea     rcx, [rax+8]
0x180009bd6  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x180009bdb  lea     r9, aWindowsSystemU_3; "Windows.System.Update.SystemUpdateManag"...
0x180009be2  mov     rcx, r9
0x180009be5  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180009bea  lea     rcx, [rax+rax]
0x180009bee  mov     rax, [rsp+38h+var_10]
0x180009bf3  add     rax, rax
0x180009bf6  cmp     rax, rcx
0x180009bf9  jnz     short loc_180009C4D
0x180009bfb  mov     rdx, [rsp+38h+var_18]
0x180009c00  add     rax, rdx
0x180009c03  add     rcx, r9
0x180009c06  cmp     rax, rdx
0x180009c09  jz      short loc_180009C1F
0x180009c0b  add     rcx, 0FFFFFFFFFFFFFFFEh
0x180009c0f  add     rax, 0FFFFFFFFFFFFFFFEh
0x180009c13  movzx   r8d, word ptr [rcx]
0x180009c17  cmp     [rax], r8w
0x180009c1b  jz      short loc_180009C06
0x180009c1d  jmp     short loc_180009C4D
0x180009c1f  lea     rcx, [rsp+38h+arg_10]
0x180009c24  call    ??$make_factory@USystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@@impl@winrt@@YA?AUIActivationFactory@Foundation@Windows@1@XZ; winrt::impl::make_factory<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager>(void)
0x180009c29  mov     rbx, [rsp+38h+arg_10]
0x180009c2e  mov     [rsp+38h+arg_10], 0
0x180009c37  lea     rcx, [rsp+38h+arg_10]; this
0x180009c3c  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x180009c41  mov     [rdi], rbx
0x180009c44  test    rbx, rbx
0x180009c47  jz      short loc_180009C54
0x180009c49  xor     eax, eax
0x180009c4b  jmp     short loc_180009C6D
0x180009c4d  mov     qword ptr [rdi], 0
0x180009c54  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180009c59  mov     r9, rdi
0x180009c5c  mov     r8, rsi
0x180009c5f  mov     rcx, rax; this
0x180009c62  call    ??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)
0x180009c67  jmp     short loc_180009C6D
0x180009c69  mov     eax, dword ptr [rsp+38h+arg_10]
0x180009c6d  mov     rbx, [rsp+38h+arg_8]
0x180009c72  mov     rsi, [rsp+38h+arg_18]
0x180009c77  add     rsp, 30h
0x180009c7b  pop     rdi
0x180009c7c  retn
```
