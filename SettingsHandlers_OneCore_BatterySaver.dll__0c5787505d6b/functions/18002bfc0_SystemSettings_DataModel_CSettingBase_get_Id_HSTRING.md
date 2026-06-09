# SystemSettings::DataModel::CSettingBase::get_Id(HSTRING__ * *)

- ea: `0x18002bfc0`
- end: `0x18002bfee`
- name: `?get_Id@CSettingBase@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `46`
- prototype: `int(SystemSettings::DataModel::CSettingBase *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18002bfc0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002bfdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002bfdc`

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
0x18002bfc0  sub     rsp, 28h
0x18002bfc4  mov     r8, rdx; string
0x18002bfc7  mov     rax, [rcx+60h]
0x18002bfcb  mov     rcx, [rax]; sourceString
0x18002bfce  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002bfd2  inc     rdx; length
0x18002bfd5  cmp     word ptr [rcx+rdx*2], 0
0x18002bfda  jnz     short loc_18002BFD2
0x18002bfdc  call    cs:__imp_WindowsCreateString
0x18002bfe2  jmp     short loc_18002BFE8
0x18002bfe4  mov     eax, [rsp+28h+arg_0]
0x18002bfe8  add     rsp, 28h
0x18002bfec  retn
```
