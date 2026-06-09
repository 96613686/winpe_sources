# SystemSettings::DataModel::CSettingBase::get_Id(HSTRING__ * *)

- ea: `0x1800218b0`
- end: `0x1800218e4`
- name: `?get_Id@CSettingBase@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `52`
- prototype: `int(SystemSettings::DataModel::CSettingBase *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800218b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800218cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800218cc`

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
0x1800218b0  sub     rsp, 28h
0x1800218b4  mov     r8, rdx; string
0x1800218b7  mov     rax, [rcx+60h]
0x1800218bb  mov     rcx, [rax]; sourceString
0x1800218be  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800218c2  inc     rdx; length
0x1800218c5  cmp     word ptr [rcx+rdx*2], 0
0x1800218ca  jnz     short loc_1800218C2
0x1800218cc  call    cs:__imp_WindowsCreateString
0x1800218d3  nop     dword ptr [rax+rax+00h]
0x1800218d8  jmp     short loc_1800218DE
0x1800218da  mov     eax, [rsp+28h+arg_0]
0x1800218de  add     rsp, 28h
0x1800218e2  retn
```
