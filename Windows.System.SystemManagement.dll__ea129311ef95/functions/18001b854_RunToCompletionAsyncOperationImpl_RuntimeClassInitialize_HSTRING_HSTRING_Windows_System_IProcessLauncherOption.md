# RunToCompletionAsyncOperationImpl::RuntimeClassInitialize(HSTRING__ *,HSTRING__ *,Windows::System::IProcessLauncherOptions *)

- ea: `0x18001b854`
- end: `0x18001b98c`
- name: `?RuntimeClassInitialize@RunToCompletionAsyncOperationImpl@@QEAAJPEAUHSTRING__@@0PEAUIProcessLauncherOptions@System@Windows@@@Z`
- size: `312`
- prototype: `__int64 __fastcall(HSTRING *this, HSTRING, HSTRING, struct Windows::System::IProcessLauncherOptions *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017e14`

## callees

- `0x18000f854`
- `0x180017bec`
- `0x18001b854`
- `0x18001bad0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b93f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b93f`

## pseudocode

```c
__int64 __fastcall RunToCompletionAsyncOperationImpl::RuntimeClassInitialize(
        HSTRING *this,
        HSTRING a2,
        HSTRING a3,
        struct Windows::System::IProcessLauncherOptions *a4)
{
  __int64 result; // rax
  _QWORD *v8; // rbx
  __int64 (__fastcall *v9)(struct Windows::System::IProcessLauncherOptions *, HSTRING *); // rdi
  HSTRING v10; // [rsp+58h] [rbp+10h] BYREF
  HSTRING v11; // [rsp+60h] [rbp+18h] BYREF

  v11 = a3;
  v10 = a2;
  if ( !a2 )
    return 2147942487LL;
  v8 = this + 22;
  result = Microsoft::WRL::Wrappers::HString::Set(this + 22, &v10);
  if ( (int)result >= 0 )
  {
    if ( !*v8 )
      return 2147942487LL;
    result = RunToCompletionAsyncOperationImpl::ValidateExeFileName((RunToCompletionAsyncOperationImpl *)this);
    if ( (int)result >= 0 )
    {
      if ( !a3 || (result = Microsoft::WRL::Wrappers::HString::Set(this + 23, &v11), (int)result >= 0) )
      {
        if ( !a4
          || (result = (*(__int64 (__fastcall **)(struct Windows::System::IProcessLauncherOptions *, char *))(*(_QWORD *)a4 + 48LL))(
                         a4,
                         (char *)this + 200),
              (int)result >= 0)
          && (result = (*(__int64 (__fastcall **)(struct Windows::System::IProcessLauncherOptions *, char *))(*(_QWORD *)a4 + 64LL))(
                         a4,
                         (char *)this + 208),
              (int)result >= 0)
          && (result = (*(__int64 (__fastcall **)(struct Windows::System::IProcessLauncherOptions *, char *))(*(_QWORD *)a4 + 80LL))(
                         a4,
                         (char *)this + 216),
              (int)result >= 0)
          && (v9 = *(__int64 (__fastcall **)(struct Windows::System::IProcessLauncherOptions *, HSTRING *))(*(_QWORD *)a4 + 96LL),
              WindowsDeleteString(this[24]),
              this[24] = 0,
              result = v9(a4, this + 24),
              (int)result >= 0) )
        {
          result = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this + 30);
          if ( (int)result >= 0 )
            return (*((__int64 (__fastcall **)(char *))this[2] + 13))((char *)this + 16);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b854  mov     [rsp+arg_0], rbx
0x18001b859  mov     [rsp+arg_10], r8
0x18001b85e  mov     [rsp+arg_8], rdx
0x18001b863  push    rsi
0x18001b864  push    rdi
0x18001b865  push    r14
0x18001b867  sub     rsp, 30h
0x18001b86b  mov     r14, r9
0x18001b86e  mov     rdi, r8
0x18001b871  mov     rsi, rcx
0x18001b874  test    rdx, rdx
0x18001b877  jnz     short loc_18001B883
0x18001b879  mov     eax, 80070057h
0x18001b87e  jmp     loc_18001B97E
0x18001b883  lea     rbx, [rcx+0B0h]
0x18001b88a  mov     rcx, rbx; newString
0x18001b88d  lea     rdx, [rsp+48h+arg_8]; HSTRING *
0x18001b892  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18001b897  test    eax, eax
0x18001b899  js      loc_18001B97E
0x18001b89f  cmp     qword ptr [rbx], 0
0x18001b8a3  jz      short loc_18001B879
0x18001b8a5  mov     rcx, rsi; this
0x18001b8a8  call    ?ValidateExeFileName@RunToCompletionAsyncOperationImpl@@AEAAJXZ; RunToCompletionAsyncOperationImpl::ValidateExeFileName(void)
0x18001b8ad  test    eax, eax
0x18001b8af  js      loc_18001B97E
0x18001b8b5  test    rdi, rdi
0x18001b8b8  jz      short loc_18001B8D3
0x18001b8ba  lea     rcx, [rsi+0B8h]; newString
0x18001b8c1  lea     rdx, [rsp+48h+arg_10]; HSTRING *
0x18001b8c6  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18001b8cb  test    eax, eax
0x18001b8cd  js      loc_18001B97E
0x18001b8d3  test    r14, r14
0x18001b8d6  jz      loc_18001B95E
0x18001b8dc  mov     rax, [r14]
0x18001b8df  lea     rdx, [rsi+0C8h]
0x18001b8e6  mov     rcx, r14
0x18001b8e9  mov     rax, [rax+30h]
0x18001b8ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8f2  test    eax, eax
0x18001b8f4  js      loc_18001B97E
0x18001b8fa  mov     rax, [r14]
0x18001b8fd  lea     rdx, [rsi+0D0h]
0x18001b904  mov     rcx, r14
0x18001b907  mov     rax, [rax+40h]
0x18001b90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b910  test    eax, eax
0x18001b912  js      short loc_18001B97E
0x18001b914  mov     rax, [r14]
0x18001b917  lea     rdx, [rsi+0D8h]
0x18001b91e  mov     rcx, r14
0x18001b921  mov     rax, [rax+50h]
0x18001b925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b92a  test    eax, eax
0x18001b92c  js      short loc_18001B97E
0x18001b92e  mov     rax, [r14]
0x18001b931  lea     rbx, [rsi+0C0h]
0x18001b938  mov     rcx, [rbx]; string
0x18001b93b  mov     rdi, [rax+60h]
0x18001b93f  call    cs:__imp_WindowsDeleteString
0x18001b945  mov     rdx, rbx
0x18001b948  mov     qword ptr [rbx], 0
0x18001b94f  mov     rcx, r14
0x18001b952  mov     rax, rdi
0x18001b955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b95a  test    eax, eax
0x18001b95c  js      short loc_18001B97E
0x18001b95e  lea     rcx, [rsi+0F0h]
0x18001b965  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001b96a  test    eax, eax
0x18001b96c  js      short loc_18001B97E
0x18001b96e  lea     rcx, [rsi+10h]
0x18001b972  mov     rax, [rcx]
0x18001b975  mov     rax, [rax+68h]
0x18001b979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b97e  mov     rbx, [rsp+48h+arg_0]
0x18001b983  add     rsp, 30h
0x18001b987  pop     r14
0x18001b989  pop     rdi
0x18001b98a  pop     rsi
0x18001b98b  retn
```
