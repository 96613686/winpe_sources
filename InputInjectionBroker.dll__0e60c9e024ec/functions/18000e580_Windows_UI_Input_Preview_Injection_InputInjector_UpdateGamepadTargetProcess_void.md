# Windows::UI::Input::Preview::Injection::InputInjector::UpdateGamepadTargetProcess(void)

- ea: `0x18000e580`
- end: `0x18000e602`
- name: `?UpdateGamepadTargetProcess@InputInjector@Injection@Preview@Input@UI@Windows@@AEAAJXZ`
- size: `130`
- prototype: `__int64 __fastcall(Windows::UI::Input::Preview::Injection::InputInjector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000ace0`
- `0x18000c9e0`

## callees

- `0x18000e580`
- `0x180011460`

## import_xrefs

- `XboxgipSynthetic!SyntheticController_SetTargetProcess` at `0x18000e5ea`
- `XboxgipSynthetic!SyntheticController_SetTargetProcess` at `0x18000e5ea`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Preview::Injection::InputInjector::UpdateGamepadTargetProcess(
        Windows::UI::Input::Preview::Injection::InputInjector *this)
{
  __int64 v1; // r10
  __int64 v2; // rdx
  __int64 result; // rax
  int v4; // eax
  __int64 v5; // [rsp+30h] [rbp-28h] BYREF
  int v6; // [rsp+38h] [rbp-20h]
  __int16 v7; // [rsp+3Ch] [rbp-1Ch]

  v1 = *((_QWORD *)this + 13);
  v2 = 0;
  result = 0;
  if ( v1 && *((_QWORD *)this + 21) )
  {
    v5 = 0;
    v7 = 0;
    v4 = *((_DWORD *)this + 45);
    v6 = 0;
    if ( (v4 & 2) != 0 )
    {
      v2 = 0x100000000000000LL;
    }
    else if ( (v4 & 4) != 0 )
    {
      v2 = *((unsigned int *)this + 46);
    }
    return SyntheticController_SetTargetProcess(v1, v2, 0, &v5, 14);
  }
  return result;
}

```

## disassembly

```asm
0x18000e580  sub     rsp, 58h
0x18000e584  mov     rax, cs:__security_cookie
0x18000e58b  xor     rax, rsp
0x18000e58e  mov     [rsp+58h+var_18], rax
0x18000e593  mov     r10, [rcx+68h]
0x18000e597  xor     edx, edx
0x18000e599  mov     eax, edx
0x18000e59b  test    r10, r10
0x18000e59e  jz      short loc_18000E5F0
0x18000e5a0  cmp     [rcx+0A8h], rdx
0x18000e5a7  jz      short loc_18000E5F0
0x18000e5a9  mov     [rsp+58h+var_28], rax
0x18000e5ae  mov     [rsp+58h+var_1C], ax
0x18000e5b3  mov     eax, [rcx+0B4h]
0x18000e5b9  mov     [rsp+58h+var_20], edx
0x18000e5bd  test    al, 2
0x18000e5bf  jz      short loc_18000E5CD
0x18000e5c1  mov     rdx, 100000000000000h
0x18000e5cb  jmp     short loc_18000E5D7
0x18000e5cd  test    al, 4
0x18000e5cf  jz      short loc_18000E5D7
0x18000e5d1  mov     edx, [rcx+0B8h]
0x18000e5d7  lea     r9, [rsp+58h+var_28]
0x18000e5dc  mov     [rsp+58h+var_38], 0Eh
0x18000e5e4  xor     r8d, r8d
0x18000e5e7  mov     rcx, r10
0x18000e5ea  call    cs:__imp_SyntheticController_SetTargetProcess
0x18000e5f0  mov     rcx, [rsp+58h+var_18]
0x18000e5f5  xor     rcx, rsp; StackCookie
0x18000e5f8  call    __security_check_cookie
0x18000e5fd  add     rsp, 58h
0x18000e601  retn
```
