# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SetAutomaticReboot(bool)

- ea: `0x18002486c`
- end: `0x1800248d3`
- name: `?SetAutomaticReboot@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAAX_N@Z`
- size: `103`
- prototype: `void __fastcall(winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *__hidden this, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180023b1c`
- `0x180024c54`

## callees

- `0x180008a80`
- `0x18002486c`
- `0x1800257c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800248b1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800248b1`

## pseudocode

```c
void __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SetAutomaticReboot(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *this,
        unsigned __int8 a2)
{
  const WCHAR *v2; // rax
  LPCWSTR v3; // r8
  unsigned int v4; // eax
  unsigned int v5; // r8d
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int Data; // [rsp+48h] [rbp+10h] BYREF

  Data = a2;
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180042AB0);
  v2 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180042AD0);
  v4 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v2, v3, 4u, &Data, 4u);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x376, v5, (const char *)v4, lpData);
}

```

## disassembly

```asm
0x18002486c  sub     rsp, 38h
0x180024870  movzx   eax, dl
0x180024873  lea     rcx, qword_180042AB0
0x18002487a  mov     [rsp+38h+Data], eax
0x18002487e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180024883  lea     rcx, qword_180042AD0
0x18002488a  mov     r8, rax
0x18002488d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180024892  mov     rdx, rax; lpSubKey
0x180024895  mov     r9d, 4; dwType
0x18002489b  lea     rax, [rsp+38h+Data]
0x1800248a0  mov     [rsp+38h+cbData], r9d; cbData
0x1800248a5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800248ac  mov     [rsp+38h+lpData], rax; unsigned int
0x1800248b1  call    cs:__imp_RegSetKeyValueW
0x1800248b7  test    eax, eax
0x1800248b9  jz      short loc_1800248CE
0x1800248bb  mov     rcx, [rsp+38h]; this
0x1800248c0  mov     r9d, eax; char *
0x1800248c3  mov     edx, 376h; void *
0x1800248c8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800248ce  add     rsp, 38h
0x1800248d2  retn
```
