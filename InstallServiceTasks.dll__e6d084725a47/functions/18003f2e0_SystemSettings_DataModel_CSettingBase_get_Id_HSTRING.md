# SystemSettings::DataModel::CSettingBase::get_Id(HSTRING__ * *)

- ea: `0x18003f2e0`
- end: `0x18003f30e`
- name: `?get_Id@CSettingBase@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `46`
- prototype: `int(SystemSettings::DataModel::CSettingBase *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18003f2e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003f2fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003f2fc`

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
0x18003f2e0  sub     rsp, 28h
0x18003f2e4  mov     r8, rdx; string
0x18003f2e7  mov     rax, [rcx+60h]
0x18003f2eb  mov     rcx, [rax]; sourceString
0x18003f2ee  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003f2f2  inc     rdx; length
0x18003f2f5  cmp     word ptr [rcx+rdx*2], 0
0x18003f2fa  jnz     short loc_18003F2F2
0x18003f2fc  call    cs:__imp_WindowsCreateString
0x18003f302  jmp     short loc_18003F308
0x18003f304  mov     eax, [rsp+28h+arg_0]
0x18003f308  add     rsp, 28h
0x18003f30c  retn
```
