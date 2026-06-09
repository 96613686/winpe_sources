# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::ISecondaryTileUserNotifierStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x180019b20`
- end: `0x180019b7f`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UISecondaryTileUserNotifierStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019b90`

## callees

- `0x180019afc`
- `0x180019b20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019b42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019b42`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::ISecondaryTileUserNotifierStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::ISecondaryTileUserNotifierStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180019b20  mov     [rsp+arg_0], rbx
0x180019b25  push    rdi
0x180019b26  sub     rsp, 20h
0x180019b2a  mov     qword ptr [r8], 0
0x180019b31  mov     ecx, 20h ; ' '; cb
0x180019b36  mov     dword ptr [rdx], 0
0x180019b3c  mov     rbx, r8
0x180019b3f  mov     rdi, rdx
0x180019b42  call    cs:__imp_CoTaskMemAlloc
0x180019b48  mov     r8, rax
0x180019b4b  test    rax, rax
0x180019b4e  jnz     short loc_180019B57
0x180019b50  mov     eax, 8007000Eh
0x180019b55  jmp     short loc_180019B74
0x180019b57  lea     rdx, [rsp+28h+arg_8]
0x180019b5c  mov     [rsp+28h+arg_8], 0
0x180019b64  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UISecondaryTileUserNotifierStatics@StateRepository@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::ISecondaryTileUserNotifierStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x180019b69  mov     dword ptr [rdi], 2
0x180019b6f  xor     eax, eax
0x180019b71  mov     [rbx], r8
0x180019b74  mov     rbx, [rsp+28h+arg_0]
0x180019b79  add     rsp, 20h
0x180019b7d  pop     rdi
0x180019b7e  retn
```
