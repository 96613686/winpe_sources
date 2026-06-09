# CXAMLHostWindow::_UpdateAccentPolicy(void)

- ea: `0x18002fb9c`
- end: `0x18002fc6f`
- name: `?_UpdateAccentPolicy@CXAMLHostWindow@@AEAAXXZ`
- size: `211`
- prototype: `void __fastcall(CXAMLHostWindow *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002e0d4`
- `0x1800300e0`

## callees

- `0x18002fb9c`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `USER32!SetWindowCompositionAttribute` at `0x18002fc4b`
- `USER32!SetWindowCompositionAttribute` at `0x18002fc4b`
- `UxTheme!__imp_GetUserColorPreference` at `0x18002fc0a`
- `UxTheme!__imp_GetUserColorPreference` at `0x18002fc0a`
- `UxTheme!__imp_GetColorFromPreference` at `0x18002fc1f`
- `UxTheme!__imp_GetColorFromPreference` at `0x18002fc1f`

## pseudocode

```c
void __fastcall CXAMLHostWindow::_UpdateAccentPolicy(CXAMLHostWindow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  unsigned int v4; // ebx
  int ColorFromPreference; // eax
  __int64 v6; // rcx
  __int64 v7; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v8[3]; // [rsp+28h] [rbp-38h] BYREF
  __int128 v9; // [rsp+40h] [rbp-20h] BYREF

  if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 24LL))(*((_QWORD *)this + 26)) + 40)
      & 0x10) == 0 )
  {
    v2 = *((_QWORD *)this + 26);
    v9 = 0;
    LODWORD(v9) = 1;
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
    v7 = 0;
    v4 = *(_DWORD *)(v3 + 56);
    GetUserColorPreference(&v7, 0);
    ColorFromPreference = GetColorFromPreference(&v7, v4, 0, 1);
    v6 = *((_QWORD *)this + 24);
    DWORD2(v9) = ColorFromPreference;
    v8[1] = &v9;
    v8[0] = 19;
    v8[2] = 16;
    SetWindowCompositionAttribute(v6, v8);
  }
}

```

## disassembly

```asm
0x18002fb9c  mov     [rsp-8+arg_8], rbx
0x18002fba1  mov     [rsp-8+arg_10], rdi
0x18002fba6  push    rbp
0x18002fba7  mov     rbp, rsp
0x18002fbaa  sub     rsp, 60h
0x18002fbae  mov     rax, cs:__security_cookie
0x18002fbb5  xor     rax, rsp
0x18002fbb8  mov     [rbp+var_10], rax
0x18002fbbc  mov     rdi, rcx
0x18002fbbf  mov     rcx, [rcx+0D0h]
0x18002fbc6  mov     rax, [rcx]
0x18002fbc9  mov     rax, [rax+18h]
0x18002fbcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbd2  test    byte ptr [rax+28h], 10h
0x18002fbd6  jnz     short loc_18002FC51
0x18002fbd8  mov     rcx, [rdi+0D0h]
0x18002fbdf  xorps   xmm0, xmm0
0x18002fbe2  movups  [rbp+var_20], xmm0
0x18002fbe6  mov     dword ptr [rbp+var_20], 1
0x18002fbed  mov     rax, [rcx]
0x18002fbf0  mov     rax, [rax+18h]
0x18002fbf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbf9  xor     edx, edx
0x18002fbfb  mov     [rbp+var_40], 0
0x18002fc03  lea     rcx, [rbp+var_40]
0x18002fc07  mov     ebx, [rax+38h]
0x18002fc0a  call    cs:__imp_GetUserColorPreference
0x18002fc10  mov     r9d, 1
0x18002fc16  lea     rcx, [rbp+var_40]
0x18002fc1a  xor     r8d, r8d
0x18002fc1d  mov     edx, ebx
0x18002fc1f  call    cs:__imp_GetColorFromPreference
0x18002fc25  mov     rcx, [rdi+0C0h]
0x18002fc2c  lea     rdx, [rbp+var_38]
0x18002fc30  mov     dword ptr [rbp+var_20+8], eax
0x18002fc33  lea     rax, [rbp+var_20]
0x18002fc37  mov     [rbp+var_30], rax
0x18002fc3b  mov     [rbp+var_38], 13h
0x18002fc43  mov     [rbp+var_28], 10h
0x18002fc4b  call    cs:__imp_SetWindowCompositionAttribute
0x18002fc51  mov     rcx, [rbp+var_10]
0x18002fc55  xor     rcx, rsp; StackCookie
0x18002fc58  call    __security_check_cookie
0x18002fc5d  lea     r11, [rsp+60h+var_s0]
0x18002fc62  mov     rbx, [r11+18h]
0x18002fc66  mov     rdi, [r11+20h]
0x18002fc6a  mov     rsp, r11
0x18002fc6d  pop     rbp
0x18002fc6e  retn
```
