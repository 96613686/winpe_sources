# RegisterWindowServiceForAccountsControl(HWND__ *,IUnknown *)

- ea: `0x18000eb40`
- end: `0x18000ec9d`
- name: `?RegisterWindowServiceForAccountsControl@@YAJPEAUHWND__@@PEAUIUnknown@@@Z`
- size: `349`
- prototype: `HRESULT __fastcall(HWND__ *hWnd, IUnknown *punk)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001449c`

## callees

- `0x18000737c`
- `0x18000eb40`
- `0x180021010`

## import_xrefs

- `twinapi.appcore!__imp_CoreRegisterWindowService` at `0x18000ebff`
- `twinapi.appcore!__imp_CoreRegisterWindowService` at `0x18000ebff`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x18000ebe8`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x18000ebe8`

## pseudocode

```c
__int64 __fastcall RegisterWindowServiceForAccountsControl(HWND__ *hWnd, IUnknown *punk)
{
  signed int v4; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v5; // rcx
  unsigned __int16 v6; // dx
  IWABAccountsSettings *ptr; // rcx
  Microsoft::WRL::ComPtr<IWABAccountsSettings> spWABAccountsSettings; // [rsp+30h] [rbp+8h] BYREF

  spWABAccountsSettings.ptr_ = 0;
  if ( hWnd )
  {
    if ( punk )
    {
      if ( (int)CoreQueryWindowService(
                  hWnd,
                  &IID_IWABAccountsSettings,
                  &GUID_d20b9b1a_d98a_4614_b864_569ab45cb262,
                  &spWABAccountsSettings) >= 0 )
      {
        v4 = -2147023654;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
          && WPP_GLOBAL_Control[1].Control.Level >= 2u )
        {
          v6 = 19;
          goto LABEL_22;
        }
      }
      else
      {
        v4 = CoreRegisterWindowService(hWnd, &IID_IWABAccountsSettings, punk);
        if ( v4 >= 0 )
        {
          v4 = 0;
          goto $exit_0;
        }
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
          && WPP_GLOBAL_Control[1].Control.Level >= 2u )
        {
          v6 = 18;
          goto LABEL_22;
        }
      }
    }
    else
    {
      v4 = -2147467261;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        v6 = 17;
        goto LABEL_22;
      }
    }
  }
  else
  {
    v4 = -2147418113;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      v6 = 16;
LABEL_22:
      WPP_SF_d(v5[1].Control.Logger, v6, WPP_45b5685ebfb435f6729103b2dc52367a_Traceguids, v4);
    }
  }
$exit_0:
  ptr = spWABAccountsSettings.ptr_;
  if ( spWABAccountsSettings.ptr_ )
  {
    spWABAccountsSettings.ptr_ = 0;
    ptr->Release(ptr);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000eb40  mov     [rsp+arg_8], rbx
0x18000eb45  push    rdi
0x18000eb46  sub     rsp, 20h
0x18000eb4a  mov     [rsp+28h+spWABAccountsSettings.ptr_], 0
0x18000eb53  mov     rdi, punk
0x18000eb56  mov     rbx, hWnd
0x18000eb59  test    hWnd, hWnd
0x18000eb5c  jnz     short loc_18000EB98
0x18000eb5e  mov     ebx, 8000FFFFh
0x18000eb63  mov     hWnd, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000eb6a  lea     rax, WPP_GLOBAL_Control
0x18000eb71  cmp     hWnd, rax
0x18000eb74  jz      $exit_0
0x18000eb7a  test    byte ptr [hWnd+44h], 8
0x18000eb7e  jz      $exit_0
0x18000eb84  cmp     byte ptr [hWnd+41h], 2
0x18000eb88  jb      $exit_0
0x18000eb8e  mov     edx, 10h
0x18000eb93  jmp     loc_18000EC5E
0x18000eb98  test    rdi, rdi
0x18000eb9b  jnz     short loc_18000EBD5
0x18000eb9d  mov     ebx, 80004003h
0x18000eba2  mov     hWnd, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000eba9  lea     rax, WPP_GLOBAL_Control
0x18000ebb0  cmp     hWnd, rax
0x18000ebb3  jz      $exit_0
0x18000ebb9  test    byte ptr [hWnd+44h], 8
0x18000ebbd  jz      $exit_0
0x18000ebc3  cmp     byte ptr [hWnd+41h], 2
0x18000ebc7  jb      $exit_0
0x18000ebcd  lea     edx, [rdi+11h]
0x18000ebd0  jmp     loc_18000EC5E
0x18000ebd5  lea     r9, [rsp+28h+spWABAccountsSettings]
0x18000ebda  lea     r8, _GUID_d20b9b1a_d98a_4614_b864_569ab45cb262
0x18000ebe1  lea     punk, IID_IWABAccountsSettings
0x18000ebe8  call    cs:__imp_CoreQueryWindowService
0x18000ebee  test    eax, eax
0x18000ebf0  jns     short loc_18000EC35
0x18000ebf2  mov     r8, rdi
0x18000ebf5  lea     punk, IID_IWABAccountsSettings
0x18000ebfc  mov     hWnd, rbx
0x18000ebff  call    cs:__imp_CoreRegisterWindowService
0x18000ec05  mov     ebx, eax
0x18000ec07  test    eax, eax
0x18000ec09  jns     short loc_18000EC31
0x18000ec0b  mov     hWnd, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000ec12  lea     rax, WPP_GLOBAL_Control
0x18000ec19  cmp     hWnd, rax
0x18000ec1c  jz      short $exit_0
0x18000ec1e  test    byte ptr [hWnd+44h], 8
0x18000ec22  jz      short $exit_0
0x18000ec24  cmp     byte ptr [hWnd+41h], 2
0x18000ec28  jb      short $exit_0
0x18000ec2a  mov     edx, 12h
0x18000ec2f  jmp     short loc_18000EC5E
0x18000ec31  xor     ebx, ebx
0x18000ec33  jmp     short $exit_0
0x18000ec35  mov     ebx, 800704DAh
0x18000ec3a  mov     hWnd, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000ec41  lea     rax, WPP_GLOBAL_Control
0x18000ec48  cmp     hWnd, rax
0x18000ec4b  jz      short $exit_0
0x18000ec4d  test    byte ptr [hWnd+44h], 8
0x18000ec51  jz      short $exit_0
0x18000ec53  cmp     byte ptr [hWnd+41h], 2
0x18000ec57  jb      short $exit_0
0x18000ec59  mov     edx, 13h; id
0x18000ec5e  mov     hWnd, [hWnd+38h]; Logger
0x18000ec62  lea     r8, WPP_45b5685ebfb435f6729103b2dc52367a_Traceguids; TraceGuid
0x18000ec69  mov     r9d, ebx; _a1
0x18000ec6c  call    WPP_SF_d
0x18000ec71  mov     hWnd, [rsp+28h+spWABAccountsSettings.ptr_]
0x18000ec76  test    hWnd, hWnd
0x18000ec79  jz      short loc_18000EC90
0x18000ec7b  mov     [rsp+28h+spWABAccountsSettings.ptr_], 0
0x18000ec84  mov     rax, [hWnd]
0x18000ec87  mov     rax, [rax+10h]
0x18000ec8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec90  mov     eax, ebx
0x18000ec92  mov     rbx, [rsp+28h+arg_8]
0x18000ec97  add     rsp, 20h
0x18000ec9b  pop     rdi
0x18000ec9c  retn
```
