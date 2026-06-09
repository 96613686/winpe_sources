# EnumProductsEx(ushort const *,ushort const *,ulong,ulong,bool,ushort * const,tagMSIINSTALLCONTEXT *,ushort *,ulong *,tagINSTALLSTATE *)

- ea: `0x1801093b0`
- end: `0x180109c90`
- name: `?EnumProductsEx@@YAIPEBG0KK_NQEAGPEAW4tagMSIINSTALLCONTEXT@@PEAGPEAKPEAW4tagINSTALLSTATE@@@Z`
- size: `2272`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, wchar_t *String1@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, bool, unsigned __int16 *const, enum tagMSIINSTALLCONTEXT *, unsigned __int16 *, unsigned int *, enum tagINSTALLSTATE *)`
- caller_count: `3`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180108854`
- `0x180109260`
- `0x18019d660`

## callees

- `0x180015690`
- `0x180017a84`
- `0x1800250d4`
- `0x180025560`
- `0x180025a18`
- `0x18004b560`
- `0x18004d38c`
- `0x18004ec1c`
- `0x18004ec7c`
- `0x18004f7a4`
- `0x18004fc48`
- `0x180050ec4`
- `0x180064a78`
- `0x180074bd0`
- `0x18008eac8`
- `0x1800b7874`
- `0x1801093b0`
- `0x180131bec`
- `0x18019b2e8`
- `0x180212ca4`
- `0x180212ddc`
- `0x180212f98`
- `0x18025ab80`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180109596`
- `msvcrt!_wcsicmp` at `0x180109596`
- `KERNEL32!GlobalFree` at `0x18010955b`
- `KERNEL32!GlobalFree` at `0x18010957a`
- `KERNEL32!GlobalFree` at `0x180109631`
- `KERNEL32!GlobalFree` at `0x18010967a`
- `KERNEL32!GlobalFree` at `0x180109699`
- `KERNEL32!GlobalFree` at `0x180109712`
- `KERNEL32!GlobalFree` at `0x180109731`
- `KERNEL32!GlobalFree` at `0x180109c06`
- `KERNEL32!GlobalFree` at `0x180109c25`
- `KERNEL32!GlobalFree` at `0x180109c3c`
- `KERNEL32!GlobalFree` at `0x180109c5b`
- `KERNEL32!GlobalFree` at `0x18010955b`
- `KERNEL32!GlobalFree` at `0x18010957a`
- `KERNEL32!GlobalFree` at `0x180109631`
- `KERNEL32!GlobalFree` at `0x18010967a`
- `KERNEL32!GlobalFree` at `0x180109699`
- `KERNEL32!GlobalFree` at `0x180109712`
- `KERNEL32!GlobalFree` at `0x180109731`
- `KERNEL32!GlobalFree` at `0x180109c06`
- `KERNEL32!GlobalFree` at `0x180109c25`
- `KERNEL32!GlobalFree` at `0x180109c3c`
- `KERNEL32!GlobalFree` at `0x180109c5b`
- `USER32!CharUpperW` at `0x1801094b3`
- `USER32!CharUpperW` at `0x1801094b3`

## string_xrefs

- `0x180109a14`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18010987c`: `Software\Microsoft\Windows\CurrentVersion\Installer\Managed`
- `0x1801095f3`: `Failed to get the current user SID with error code=%d`
- `0x18010993c`: `Local System sid is getting ignored. Specify machine context through dwContext parameter`

## pseudocode

```c

```
