# SystemSettings::DataModel::CSettingBase::get_Id(HSTRING__ * *)

- ea: `0x180022aa0`
- end: `0x180022ace`
- name: `?get_Id@CSettingBase@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `46`
- prototype: `int(SystemSettings::DataModel::CSettingBase *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180022aa0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180022abc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180022abc`

## pseudocode

```c
HRESULT __fastcall SystemSettings::DataModel::CSettingBase::get_Id(
        SystemSettings::DataModel::CSettingBase *this,
        HSTRING *a2)
{
  const WCHAR *v3; // rcx
  __int64 v4; // rdx

  v3 = (const WCHAR *)**((_QWORD **)this + 12);
  v4 = -1;
  do
    ++v4;
  while ( v3[v4] );
  return WindowsCreateString(v3, v4, a2);
}

```

## disassembly

```asm
0x180022aa0  sub     rsp, 28h
0x180022aa4  mov     r8, rdx; string
0x180022aa7  mov     rax, [rcx+60h]
0x180022aab  mov     rcx, [rax]; sourceString
0x180022aae  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180022ab2  inc     rdx; length
0x180022ab5  cmp     word ptr [rcx+rdx*2], 0
0x180022aba  jnz     short loc_180022AB2
0x180022abc  call    cs:__imp_WindowsCreateString
0x180022ac2  jmp     short loc_180022AC8
0x180022ac4  mov     eax, [rsp+28h+arg_0]
0x180022ac8  add     rsp, 28h
0x180022acc  retn
```
