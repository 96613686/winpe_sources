# CTooltip::ShowComCtlTip(ushort *,HWND__ *,tagMSG *,tagRECT *,unsigned __int64,int,int,tagPOINT *)

- ea: `0x180724884`
- end: `0x180724bf5`
- name: `?ShowComCtlTip@CTooltip@@AEAAJPEAGPEAUHWND__@@PEAUtagMSG@@PEAUtagRECT@@_KHHPEAUtagPOINT@@@Z`
- size: `881`
- prototype: `__int64 __usercall@<rax>(CTooltip *__hidden this@<rcx>, unsigned __int16 *@<rdx>, HWND@<r8>, struct tagMSG *@<r9>, RECT *lprc1, unsigned __int64, int, int, struct tagPOINT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18071bd4c`

## callees

- `0x1801bf178`
- `0x180724884`
- `0x180b48b20`
- `0x180b48d1c`
- `0x180b51354`
- `0x1810c2cb6`

## import_xrefs

- `USER32!IsWindow` at `0x1807248c6`
- `USER32!IsWindow` at `0x1807248c6`
- `USER32!DestroyWindow` at `0x1807248d3`
- `USER32!DestroyWindow` at `0x1807248d3`
- `USER32!SendMessageW` at `0x18072493f`
- `USER32!SendMessageW` at `0x1807249c9`
- `USER32!SendMessageW` at `0x180724a03`
- `USER32!SendMessageW` at `0x180724abc`
- `USER32!SendMessageW` at `0x180724ad1`
- `USER32!SendMessageW` at `0x180724ba3`
- `USER32!SendMessageW` at `0x180724bd8`
- `USER32!SendMessageW` at `0x18072493f`
- `USER32!SendMessageW` at `0x1807249c9`
- `USER32!SendMessageW` at `0x180724a03`
- `USER32!SendMessageW` at `0x180724abc`
- `USER32!SendMessageW` at `0x180724ad1`
- `USER32!SendMessageW` at `0x180724ba3`
- `USER32!SendMessageW` at `0x180724bd8`
- `USER32!MapWindowPoints` at `0x180724bb7`
- `USER32!MapWindowPoints` at `0x180724bb7`
- `USER32!EqualRect` at `0x1807249ac`
- `USER32!EqualRect` at `0x180724b5c`
- `USER32!EqualRect` at `0x1807249ac`
- `USER32!EqualRect` at `0x180724b5c`

## pseudocode

```c

```
