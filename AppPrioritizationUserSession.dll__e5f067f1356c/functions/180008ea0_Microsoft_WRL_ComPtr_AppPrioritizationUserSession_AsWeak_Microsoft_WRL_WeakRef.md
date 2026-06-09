# Microsoft::WRL::ComPtr<AppPrioritizationUserSession>::AsWeak(Microsoft::WRL::WeakRef *)

- ea: `0x180008ea0`
- end: `0x180008fea`
- name: `?AsWeak@?$ComPtr@VAppPrioritizationUserSession@@@WRL@Microsoft@@QEBAJPEAVWeakRef@23@@Z`
- size: `330`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009110`

## callees

- `0x180002650`
- `0x180008ea0`
- `0x18000a1f0`
- `0x18000d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::ComPtr<AppPrioritizationUserSession>::AsWeak(__int64 a1, __int64 *a2)
{
  int v3; // ebx
  __int64 v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v10; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+28h] [rbp-20h] BYREF

  v10 = 0;
  v3 = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::QueryInterface(
         AppPrioritizationUserSessionStatics::s_instance,
         &GUID_00000038_0000_0000_c000_000000000046,
         &v10);
  if ( v3 >= 0 )
  {
    v11 = 0;
    v4 = v10;
    v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 24LL))(v10, &v11);
    if ( v3 >= 0 )
    {
      v6 = v11;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      v7 = *a2;
      *a2 = v6;
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      v8 = v11;
      if ( v11 )
      {
        v11 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      return 0;
    }
    else
    {
      v5 = v11;
      if ( v11 )
      {
        v11 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      }
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
  else if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008ea0  mov     r11, rsp
0x180008ea3  mov     [r11+8], rbx
0x180008ea7  mov     [r11+18h], rsi
0x180008eab  push    rdi
0x180008eac  sub     rsp, 40h
0x180008eb0  mov     rax, cs:__security_cookie
0x180008eb7  xor     rax, rsp
0x180008eba  mov     [rsp+48h+var_18], rax
0x180008ebf  mov     rsi, rdx
0x180008ec2  mov     qword ptr [r11-28h], 0
0x180008eca  lea     r8, [r11-28h]
0x180008ece  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x180008ed5  mov     rcx, cs:?s_instance@AppPrioritizationUserSessionStatics@@0V?$ComPtr@VAppPrioritizationUserSession@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<AppPrioritizationUserSession> AppPrioritizationUserSessionStatics::s_instance
0x180008edc  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIAppPrioritizationUserSessionInternal@@UIAppPrioritizationUserSession@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::QueryInterface(_GUID const &,void * *)
0x180008ee1  mov     ebx, eax
0x180008ee3  test    eax, eax
0x180008ee5  jns     short loc_180008F03
0x180008ee7  mov     rcx, [rsp+48h+var_28]
0x180008eec  test    rcx, rcx
0x180008eef  jz      short loc_180008EFE
0x180008ef1  mov     rax, [rcx]
0x180008ef4  mov     rax, [rax+10h]
0x180008ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008efd  nop
0x180008efe  jmp     loc_180008FCB
0x180008f03  mov     [rsp+48h+var_20], 0
0x180008f0c  mov     rdi, [rsp+48h+var_28]
0x180008f11  mov     rax, [rdi]
0x180008f14  lea     rdx, [rsp+48h+var_20]
0x180008f19  mov     rcx, rdi
0x180008f1c  mov     rax, [rax+18h]
0x180008f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f25  mov     ebx, eax
0x180008f27  test    eax, eax
0x180008f29  jns     short loc_180008F62
0x180008f2b  mov     rcx, [rsp+48h+var_20]
0x180008f30  test    rcx, rcx
0x180008f33  jz      short loc_180008F4B
0x180008f35  mov     [rsp+48h+var_20], 0
0x180008f3e  mov     rax, [rcx]
0x180008f41  mov     rax, [rax+10h]
0x180008f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f4a  nop
0x180008f4b  test    rdi, rdi
0x180008f4e  jz      short loc_180008F60
0x180008f50  mov     rax, [rdi]
0x180008f53  mov     rcx, rdi
0x180008f56  mov     rax, [rax+10h]
0x180008f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f5f  nop
0x180008f60  jmp     short loc_180008FCB
0x180008f62  mov     rbx, [rsp+48h+var_20]
0x180008f67  test    rbx, rbx
0x180008f6a  jz      short loc_180008F7C
0x180008f6c  mov     rax, [rbx]
0x180008f6f  mov     rcx, rbx
0x180008f72  mov     rax, [rax+8]
0x180008f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f7b  nop
0x180008f7c  mov     rcx, [rsi]
0x180008f7f  mov     [rsi], rbx
0x180008f82  test    rcx, rcx
0x180008f85  jz      short loc_180008F94
0x180008f87  mov     rax, [rcx]
0x180008f8a  mov     rax, [rax+10h]
0x180008f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f93  nop
0x180008f94  mov     rcx, [rsp+48h+var_20]
0x180008f99  test    rcx, rcx
0x180008f9c  jz      short loc_180008FB4
0x180008f9e  mov     [rsp+48h+var_20], 0
0x180008fa7  mov     rax, [rcx]
0x180008faa  mov     rax, [rax+10h]
0x180008fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fb3  nop
0x180008fb4  test    rdi, rdi
0x180008fb7  jz      short loc_180008FC9
0x180008fb9  mov     rax, [rdi]
0x180008fbc  mov     rcx, rdi
0x180008fbf  mov     rax, [rax+10h]
0x180008fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fc8  nop
0x180008fc9  xor     ebx, ebx
0x180008fcb  mov     eax, ebx
0x180008fcd  mov     rcx, [rsp+48h+var_18]
0x180008fd2  xor     rcx, rsp; StackCookie
0x180008fd5  call    __security_check_cookie
0x180008fda  mov     rbx, [rsp+48h+arg_0]
0x180008fdf  mov     rsi, [rsp+48h+arg_10]
0x180008fe4  add     rsp, 40h
0x180008fe8  pop     rdi
0x180008fe9  retn
```
