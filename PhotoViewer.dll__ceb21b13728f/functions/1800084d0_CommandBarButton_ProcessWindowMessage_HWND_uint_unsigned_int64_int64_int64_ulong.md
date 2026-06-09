# CommandBarButton::ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 &,ulong)

- ea: `0x1800084d0`
- end: `0x18000878c`
- name: `?ProcessWindowMessage@CommandBarButton@@UEAAHPEAUHWND__@@I_K_JAEA_JK@Z`
- size: `700`
- prototype: `__int64 __fastcall(CommandBarButton *__hidden this, HWND hWnd, unsigned int, unsigned __int64, LPARAM, __int64 *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006d0d0`
- `0x18006d0e0`

## callees

- `0x1800084d0`
- `0x180008ac0`
- `0x180025154`
- `0x180033e94`
- `0x180072c48`
- `0x180074bd8`
- `0x1800757c8`
- `0x18007583c`
- `0x1800758e8`

## import_xrefs

- `USER32!GetNextDlgGroupItem` at `0x1800086b3`
- `USER32!GetNextDlgGroupItem` at `0x1800086b3`
- `USER32!SetFocus` at `0x1800086c7`
- `USER32!SetFocus` at `0x1800086c7`
- `USER32!GetParent` at `0x180008699`
- `USER32!GetParent` at `0x180008699`
- `USER32!GetWindowLongW` at `0x18000866c`
- `USER32!GetWindowLongW` at `0x18000866c`

## pseudocode

```c

```
