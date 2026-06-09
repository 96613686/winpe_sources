# F12::SiteCommandMessage(void)

- ea: `0x18002f710`
- end: `0x18002f736`
- name: `?SiteCommandMessage@F12@@YAIXZ`
- size: `38`
- prototype: `unsigned int __fastcall(F12 *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800234d8`
- `0x180023660`
- `0x180024d00`
- `0x180028228`
- `0x18002b910`

## callees

- `0x18002f710`

## import_xrefs

- `USER32!RegisterWindowMessageW` at `0x18002f725`
- `USER32!RegisterWindowMessageW` at `0x18002f725`

## string_xrefs

- `0x18002f71e`: `WM_F12_SITE_COMMAND`

## pseudocode

```c
UINT __fastcall F12::SiteCommandMessage(F12 *this)
{
  UINT result; // eax

  result = dword_180050890;
  if ( !dword_180050890 )
  {
    result = RegisterWindowMessageW(L"WM_F12_SITE_COMMAND");
    dword_180050890 = result;
  }
  return result;
}

```

## disassembly

```asm
0x18002f710  sub     rsp, 28h
0x18002f714  mov     eax, cs:dword_180050890
0x18002f71a  test    eax, eax
0x18002f71c  jnz     short loc_18002F731
0x18002f71e  lea     rcx, aWmF12SiteComma; "WM_F12_SITE_COMMAND"
0x18002f725  call    cs:__imp_RegisterWindowMessageW
0x18002f72b  mov     cs:dword_180050890, eax
0x18002f731  add     rsp, 28h
0x18002f735  retn
```
