# WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::PostLineErrorToastNotification(_GUID,long)

- ea: `0x180004ef0`
- end: `0x180005001`
- name: `?PostLineErrorToastNotification@ServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@UEAAJU_GUID@@J@Z`
- size: `273`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics *__hidden this, struct _GUID *__struct_ptr, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800021b4`
- `0x180004d8c`
- `0x180004ef0`
- `0x1800053f0`
- `0x180005810`

## string_xrefs

- `0x180004f84`: `IncomingCall`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::PostLineErrorToastNotification(
        WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics *this,
        struct _GUID *a2,
        int a3)
{
  WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics *v3; // rdi
  int ToastString; // ebx
  __int64 v5; // r8
  __int64 v6; // r9
  void *Block[2]; // [rsp+40h] [rbp-30h] BYREF
  __int16 v9; // [rsp+50h] [rbp-20h] BYREF
  __int64 v10; // [rsp+52h] [rbp-1Eh]
  int v11; // [rsp+5Ah] [rbp-16h]
  __int16 v12; // [rsp+5Eh] [rbp-12h]

  v10 = 0;
  v12 = 0;
  v3 = (WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics *)((char *)this - 8);
  v11 = 0;
  Block[0] = &v9;
  Block[1] = &v9;
  v9 = 0;
  ToastString = WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::_GenerateToastString(
                  (__int64)this - 8,
                  (__int64)Block,
                  a3);
  if ( ToastString < 0 )
  {
    v6 = 43;
LABEL_3:
    Log_HREvent((unsigned int)ToastString, 1, v5, v6);
    if ( Block[0] != &v9 )
      operator delete(Block[0]);
    return (unsigned int)ToastString;
  }
  ToastString = WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::_PostToastNotification(
                  v3,
                  L"NonImmersivePackage",
                  L"Windows.Systemtoast.Calling",
                  (const unsigned __int16 *)Block[0],
                  &dword_18001D6C4,
                  L"IncomingCall",
                  0);
  if ( ToastString < 0 )
  {
    v6 = 45;
    goto LABEL_3;
  }
  if ( Block[0] != &v9 )
    operator delete(Block[0]);
  return 0;
}

```

## disassembly

```asm
0x180004ef0  mov     [rsp-8+arg_8], rbx
0x180004ef5  mov     [rsp-8+arg_18], rdi
0x180004efa  push    rbp
0x180004efb  mov     rbp, rsp
0x180004efe  sub     rsp, 70h
0x180004f02  mov     rax, cs:__security_cookie
0x180004f09  xor     rax, rsp
0x180004f0c  mov     [rbp+var_10], rax
0x180004f10  xor     eax, eax
0x180004f12  mov     [rbp+var_1E], 0
0x180004f1a  mov     [rbp+var_12], ax
0x180004f1e  lea     rdi, [rcx-8]
0x180004f22  lea     rax, [rbp+var_20]
0x180004f26  mov     [rbp+var_16], 0
0x180004f2d  mov     [rbp+Block], rax
0x180004f31  lea     rdx, [rbp+Block]
0x180004f35  lea     rax, [rbp+var_20]
0x180004f39  mov     rcx, rdi
0x180004f3c  mov     [rbp+var_28], rax
0x180004f40  xor     eax, eax
0x180004f42  mov     [rbp+var_20], ax
0x180004f46  call    ?_GenerateToastString@ServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@J@Z; WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::_GenerateToastString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,long)
0x180004f4b  mov     ebx, eax
0x180004f4d  test    eax, eax
0x180004f4f  jns     short loc_180004F80
0x180004f51  mov     r9d, 2Bh ; '+'
0x180004f57  mov     edx, 1
0x180004f5c  mov     ecx, ebx
0x180004f5e  call    Log_HREvent
0x180004f63  mov     rcx, [rbp+Block]; Block
0x180004f67  lea     rax, [rbp+var_20]
0x180004f6b  cmp     rcx, rax
0x180004f6e  jz      short loc_180004F7C
0x180004f70  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180004f77  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004f7c  mov     eax, ebx
0x180004f7e  jmp     short loc_180004FE3
0x180004f80  mov     r9, [rbp+Block]; unsigned __int16 *
0x180004f84  lea     rax, aIncomingcall; "IncomingCall"
0x180004f8b  mov     [rsp+70h+var_40], 0; int
0x180004f93  lea     r8, aWindowsSystemt; "Windows.Systemtoast.Calling"
0x180004f9a  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x180004f9f  lea     rdx, aNonimmersivepa; "NonImmersivePackage"
0x180004fa6  lea     rax, dword_18001D6C4
0x180004fad  mov     rcx, rdi; this
0x180004fb0  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x180004fb5  call    ?_PostToastNotification@ServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJPEBG0000H@Z; WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::_PostToastNotification(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int)
0x180004fba  mov     ebx, eax
0x180004fbc  test    eax, eax
0x180004fbe  jns     short loc_180004FC8
0x180004fc0  mov     r9d, 2Dh ; '-'
0x180004fc6  jmp     short loc_180004F57
0x180004fc8  mov     rcx, [rbp+Block]; Block
0x180004fcc  lea     rax, [rbp+var_20]
0x180004fd0  cmp     rcx, rax
0x180004fd3  jz      short loc_180004FE1
0x180004fd5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180004fdc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004fe1  xor     eax, eax
0x180004fe3  mov     rcx, [rbp+var_10]
0x180004fe7  xor     rcx, rsp; StackCookie
0x180004fea  call    __security_check_cookie
0x180004fef  lea     r11, [rsp+70h+var_s0]
0x180004ff4  mov     rbx, [r11+18h]
0x180004ff8  mov     rdi, [r11+28h]
0x180004ffc  mov     rsp, r11
0x180004fff  pop     rbp
0x180005000  retn
```
