# CW32System::GetKeyStateFromCoreWindow(int)

- ea: `0x1800d9b40`
- end: `0x1800d9cf5`
- name: `?GetKeyStateFromCoreWindow@CW32System@@SAFH@Z`
- size: `437`
- prototype: `__int16 __fastcall(int nVirtKey)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180048d5c`
- `0x1800d9b40`
- `0x1800ed8a0`
- `0x18013ead4`
- `0x1801462c4`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d9b93`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d9b93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9b61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9bb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9c6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9cdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9b61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9bb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9c6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9cdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d9b7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d9b7a`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyState` at `0x1800d9bac`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyState` at `0x1800d9bac`

## pseudocode

```c
__int64 __fastcall CW32System::GetKeyStateFromCoreWindow(unsigned int nVirtKey)
{
  unsigned __int16 KeyState; // bx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v6; // rdi
  int (__fastcall *v7)(__int64, __int64 *); // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // [rsp+20h] [rbp-10h] BYREF
  int v11; // [rsp+68h] [rbp+38h] BYREF
  HSTRING string; // [rsp+70h] [rbp+40h] BYREF
  __int64 v13; // [rsp+78h] [rbp+48h] BYREF

  v10 = 0;
  v13 = 0;
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  if ( WindowsCreateString(L"Windows.UI.Core.CoreWindow", 0x1Au, &string) >= 0
    && (int)RoGetActivationFactory(string, &GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1, &v10) >= 0
    && (v6 = v10,
        v7 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 48LL),
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13),
        v7(v6, &v13) >= 0)
    && v13
    && (v11 = 0, (*(int (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v13 + 168LL))(v13, nVirtKey, &v11) >= 0)
    && (v11 & 1) != 0 )
  {
    WindowsDeleteString(string);
    v8 = v13;
    string = 0;
    if ( v13 )
    {
      v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v9 = v10;
    if ( v10 )
    {
      v10 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return 4294934528LL;
  }
  else
  {
    if ( (unsigned __int8)IsGetKeyStatePresent() )
    {
      KeyState = GetKeyState(nVirtKey);
      WindowsDeleteString(string);
      v3 = v13;
      string = 0;
      if ( v13 )
      {
        v13 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
      }
    }
    else
    {
      v11 = nVirtKey;
      if ( !IsTrackedKey(&v11)
        || (KeyState = 0x8000, (CW32System::GetKeyMask(nVirtKey) & CW32System::_wKeyboardFlags) == 0) )
      {
        KeyState = 0;
      }
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    }
    v4 = v10;
    if ( v10 )
    {
      v10 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return KeyState;
  }
}

```

## disassembly

```asm
0x1800d9b40  push    rbp
0x1800d9b42  push    rbx
0x1800d9b43  push    rsi
0x1800d9b44  push    rdi
0x1800d9b45  push    r14
0x1800d9b47  mov     rbp, rsp
0x1800d9b4a  sub     rsp, 30h
0x1800d9b4e  xor     r14d, r14d
0x1800d9b51  mov     esi, ecx
0x1800d9b53  xor     ecx, ecx; string
0x1800d9b55  mov     [rbp+var_10], r14
0x1800d9b59  mov     [rbp+arg_18], r14
0x1800d9b5d  mov     [rbp+string], r14
0x1800d9b61  call    cs:__imp_WindowsDeleteString
0x1800d9b67  lea     r8, [rbp+string]; string
0x1800d9b6b  mov     [rbp+string], r14
0x1800d9b6f  lea     edx, [r14+1Ah]; length
0x1800d9b73  lea     rcx, ?RuntimeClass_Windows_UI_Core_CoreWindow@@3QBGB; "Windows.UI.Core.CoreWindow"
0x1800d9b7a  call    cs:__imp_WindowsCreateString
0x1800d9b80  test    eax, eax
0x1800d9b82  js      short loc_1800D9B9D
0x1800d9b84  mov     rcx, [rbp+string]
0x1800d9b88  lea     r8, [rbp+var_10]
0x1800d9b8c  lea     rdx, _GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1
0x1800d9b93  call    cs:__imp_RoGetActivationFactory
0x1800d9b99  test    eax, eax
0x1800d9b9b  jns     short loc_1800D9C03
0x1800d9b9d  call    IsGetKeyStatePresent
0x1800d9ba2  test    al, al
0x1800d9ba4  jz      loc_1800D9CB0
0x1800d9baa  mov     ecx, esi; nVirtKey
0x1800d9bac  call    cs:__imp_GetKeyState
0x1800d9bb2  mov     rcx, [rbp+string]; string
0x1800d9bb6  movzx   ebx, ax
0x1800d9bb9  call    cs:__imp_WindowsDeleteString
0x1800d9bbf  mov     rcx, [rbp+arg_18]
0x1800d9bc3  mov     [rbp+string], r14
0x1800d9bc7  test    rcx, rcx
0x1800d9bca  jz      short loc_1800D9BDC
0x1800d9bcc  mov     [rbp+arg_18], r14
0x1800d9bd0  mov     rdx, [rcx]
0x1800d9bd3  mov     rax, [rdx+10h]
0x1800d9bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9bdc  mov     rcx, [rbp+var_10]
0x1800d9be0  test    rcx, rcx
0x1800d9be3  jz      short loc_1800D9BF5
0x1800d9be5  mov     [rbp+var_10], r14
0x1800d9be9  mov     rax, [rcx]
0x1800d9bec  mov     rax, [rax+10h]
0x1800d9bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9bf5  movzx   eax, bx
0x1800d9bf8  add     rsp, 30h
0x1800d9bfc  pop     r14
0x1800d9bfe  pop     rdi
0x1800d9bff  pop     rsi
0x1800d9c00  pop     rbx
0x1800d9c01  pop     rbp
0x1800d9c02  retn
0x1800d9c03  mov     rdi, [rbp+var_10]
0x1800d9c07  lea     rcx, [rbp+arg_18]
0x1800d9c0b  mov     rax, [rdi]
0x1800d9c0e  mov     rbx, [rax+30h]
0x1800d9c12  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d9c17  lea     rdx, [rbp+arg_18]
0x1800d9c1b  mov     rcx, rdi
0x1800d9c1e  mov     rax, rbx
0x1800d9c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9c26  test    eax, eax
0x1800d9c28  js      loc_1800D9B9D
0x1800d9c2e  mov     rcx, [rbp+arg_18]
0x1800d9c32  test    rcx, rcx
0x1800d9c35  jz      loc_1800D9B9D
0x1800d9c3b  mov     [rbp+arg_8], r14d
0x1800d9c3f  lea     r8, [rbp+arg_8]
0x1800d9c43  mov     rax, [rcx]
0x1800d9c46  mov     edx, esi
0x1800d9c48  mov     rax, [rax+0A8h]
0x1800d9c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9c54  test    eax, eax
0x1800d9c56  js      loc_1800D9B9D
0x1800d9c5c  test    byte ptr [rbp+arg_8], 1
0x1800d9c60  jz      loc_1800D9B9D
0x1800d9c66  mov     rcx, [rbp+string]; string
0x1800d9c6a  call    cs:__imp_WindowsDeleteString
0x1800d9c70  mov     rcx, [rbp+arg_18]
0x1800d9c74  mov     [rbp+string], r14
0x1800d9c78  test    rcx, rcx
0x1800d9c7b  jz      short loc_1800D9C8D
0x1800d9c7d  mov     [rbp+arg_18], r14
0x1800d9c81  mov     rax, [rcx]
0x1800d9c84  mov     rax, [rax+10h]
0x1800d9c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9c8d  mov     rcx, [rbp+var_10]
0x1800d9c91  test    rcx, rcx
0x1800d9c94  jz      short loc_1800D9CA6
0x1800d9c96  mov     [rbp+var_10], r14
0x1800d9c9a  mov     rax, [rcx]
0x1800d9c9d  mov     rax, [rax+10h]
0x1800d9ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9ca6  mov     eax, 0FFFF8000h
0x1800d9cab  jmp     loc_1800D9BF8
0x1800d9cb0  lea     rcx, [rbp+arg_8]; int *
0x1800d9cb4  mov     [rbp+arg_8], esi
0x1800d9cb7  call    ?IsTrackedKey@@YA_NAEBH@Z; IsTrackedKey(int const &)
0x1800d9cbc  test    al, al
0x1800d9cbe  jz      short loc_1800D9CD6
0x1800d9cc0  movzx   ecx, si; unsigned __int16
0x1800d9cc3  call    ?GetKeyMask@CW32System@@SAGG@Z; CW32System::GetKeyMask(ushort)
0x1800d9cc8  test    cs:?_wKeyboardFlags@CW32System@@0GA, ax; ushort CW32System::_wKeyboardFlags
0x1800d9ccf  mov     ebx, 0FFFF8000h
0x1800d9cd4  jnz     short loc_1800D9CD9
0x1800d9cd6  mov     ebx, r14d
0x1800d9cd9  mov     rcx, [rbp+string]; string
0x1800d9cdd  call    cs:__imp_WindowsDeleteString
0x1800d9ce3  lea     rcx, [rbp+arg_18]
0x1800d9ce7  mov     [rbp+string], r14
0x1800d9ceb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d9cf0  jmp     loc_1800D9BDC
```
