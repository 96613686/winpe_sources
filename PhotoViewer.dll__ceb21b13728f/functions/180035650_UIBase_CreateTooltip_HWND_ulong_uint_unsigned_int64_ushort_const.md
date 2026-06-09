# UIBase::CreateTooltip(HWND__ *,ulong,uint,unsigned __int64,ushort const *)

- ea: `0x180035650`
- end: `0x1800357a6`
- name: `?CreateTooltip@UIBase@@YAPEAUHWND__@@PEAU2@KI_KPEBG@Z`
- size: `342`
- prototype: `HWND __usercall@<rax>(HWND this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800286c8`
- `0x180064a90`
- `0x180076ddc`

## callees

- `0x180021ae0`
- `0x180035650`
- `0x18003f800`
- `0x180040264`
- `0x180073bcc`

## import_xrefs

- `USER32!SetWindowPos` at `0x180035708`
- `USER32!SetWindowPos` at `0x180035708`
- `USER32!SendMessageW` at `0x18003577a`
- `USER32!SendMessageW` at `0x18003577a`
- `USER32!IsWindow` at `0x1800356cf`
- `USER32!IsWindow` at `0x1800356cf`
- `USER32!GetClientRect` at `0x18003572b`
- `USER32!GetClientRect` at `0x18003572b`
- `USER32!GetWindowLongPtrW` at `0x18003567e`
- `USER32!GetWindowLongPtrW` at `0x18003567e`

## pseudocode

```c

```
