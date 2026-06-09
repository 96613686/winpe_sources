# FCropGetPicSizes(WWD *,DOD *,long,CHP *,PICDIM *,ulong,long,long)

- ea: `0x1801f86e0`
- end: `0x1801f8fda`
- name: `?FCropGetPicSizes@@YA_NPEAVWWD@@PEAVDOD@@JPEAUCHP@@PEAUPICDIM@@KJJ@Z`
- size: `2298`
- prototype: `bool __usercall@<al>(struct WWD *@<rcx>, struct DOD *@<rdx>, int@<r8d>, struct CHP *@<r9>, struct PICDIM *, unsigned int, int, int)`
- caller_count: `3`
- callee_count: `21`
- tags: ``

## callers

- `0x1801f7ce4`
- `0x180201b94`
- `0x180a29884`

## callees

- `0x18004e290`
- `0x1800540e4`
- `0x18005414c`
- `0x18005ac40`
- `0x1801edaf8`
- `0x1801f6c30`
- `0x1801f7550`
- `0x1801f7854`
- `0x1801f86e0`
- `0x1801f8fdc`
- `0x1801f9fb8`
- `0x1802071b0`
- `0x180294a50`
- `0x1803e7b8c`
- `0x1804c9874`
- `0x18056fbbc`
- `0x180b8d174`
- `0x18100b138`
- `0x1811b8554`
- `0x1812103d0`
- `0x1812e383c`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1801f87a3`
- `KERNEL32!TlsGetValue` at `0x1801f87b5`
- `KERNEL32!TlsGetValue` at `0x1801f8812`
- `KERNEL32!TlsGetValue` at `0x1801f8825`
- `KERNEL32!TlsGetValue` at `0x1801f8857`
- `KERNEL32!TlsGetValue` at `0x1801f8875`
- `KERNEL32!TlsGetValue` at `0x1801f88a8`
- `KERNEL32!TlsGetValue` at `0x1801f88c2`
- `KERNEL32!TlsGetValue` at `0x1801f88dc`
- `KERNEL32!TlsGetValue` at `0x1801f88f6`
- `KERNEL32!TlsGetValue` at `0x1801f891f`
- `KERNEL32!TlsGetValue` at `0x1801f8938`
- `KERNEL32!TlsGetValue` at `0x1801f8964`
- `KERNEL32!TlsGetValue` at `0x1801f8a55`
- `KERNEL32!TlsGetValue` at `0x1801f8a85`
- `KERNEL32!TlsGetValue` at `0x1801f8ab5`
- `KERNEL32!TlsGetValue` at `0x1801f8ae5`
- `KERNEL32!TlsGetValue` at `0x1801f8b71`
- `KERNEL32!TlsGetValue` at `0x1801f8b84`
- `KERNEL32!TlsGetValue` at `0x1801f8bad`
- `KERNEL32!TlsGetValue` at `0x1801f8bc0`
- `KERNEL32!TlsGetValue` at `0x1801f8be3`
- `KERNEL32!TlsGetValue` at `0x1801f8bf6`
- `KERNEL32!TlsGetValue` at `0x1801f8c20`
- `KERNEL32!TlsGetValue` at `0x1801f8c42`
- `KERNEL32!TlsGetValue` at `0x1801f8c5a`
- `KERNEL32!TlsGetValue` at `0x1801f8c6d`
- `KERNEL32!TlsGetValue` at `0x1801f8c96`
- `KERNEL32!TlsGetValue` at `0x1801f8ca9`
- `KERNEL32!TlsGetValue` at `0x1801f8ccc`
- `KERNEL32!TlsGetValue` at `0x1801f8cdf`
- `KERNEL32!TlsGetValue` at `0x1801f8d0b`
- `KERNEL32!TlsGetValue` at `0x1801f8d2a`
- `KERNEL32!TlsGetValue` at `0x1801f8da3`
- `KERNEL32!TlsGetValue` at `0x1801f8db6`
- `KERNEL32!TlsGetValue` at `0x1801f8deb`
- `KERNEL32!TlsGetValue` at `0x1801f8e46`
- `KERNEL32!TlsGetValue` at `0x1801f8ed7`
- `KERNEL32!TlsGetValue` at `0x1801f8eec`
- `KERNEL32!TlsGetValue` at `0x1801f8efb`
- `KERNEL32!TlsGetValue` at `0x1801f8f57`
- `KERNEL32!TlsGetValue` at `0x1801f8f6e`
- `KERNEL32!TlsGetValue` at `0x1801f8f7d`
- `KERNEL32!TlsGetValue` at `0x1801f87a3`
- `KERNEL32!TlsGetValue` at `0x1801f87b5`
- `KERNEL32!TlsGetValue` at `0x1801f8812`
- `KERNEL32!TlsGetValue` at `0x1801f8825`
- `KERNEL32!TlsGetValue` at `0x1801f8857`
- `KERNEL32!TlsGetValue` at `0x1801f8875`
- `KERNEL32!TlsGetValue` at `0x1801f88a8`
- `KERNEL32!TlsGetValue` at `0x1801f88c2`
- `KERNEL32!TlsGetValue` at `0x1801f88dc`
- `KERNEL32!TlsGetValue` at `0x1801f88f6`
- `KERNEL32!TlsGetValue` at `0x1801f891f`
- `KERNEL32!TlsGetValue` at `0x1801f8938`
- `KERNEL32!TlsGetValue` at `0x1801f8964`
- `KERNEL32!TlsGetValue` at `0x1801f8a55`
- `KERNEL32!TlsGetValue` at `0x1801f8a85`
- `KERNEL32!TlsGetValue` at `0x1801f8ab5`
- `KERNEL32!TlsGetValue` at `0x1801f8ae5`
- `KERNEL32!TlsGetValue` at `0x1801f8b71`
- `KERNEL32!TlsGetValue` at `0x1801f8b84`
- `KERNEL32!TlsGetValue` at `0x1801f8bad`
- `KERNEL32!TlsGetValue` at `0x1801f8bc0`
- `KERNEL32!TlsGetValue` at `0x1801f8be3`
- `KERNEL32!TlsGetValue` at `0x1801f8bf6`
- `KERNEL32!TlsGetValue` at `0x1801f8c20`
- `KERNEL32!TlsGetValue` at `0x1801f8c42`
- `KERNEL32!TlsGetValue` at `0x1801f8c5a`
- `KERNEL32!TlsGetValue` at `0x1801f8c6d`
- `KERNEL32!TlsGetValue` at `0x1801f8c96`
- `KERNEL32!TlsGetValue` at `0x1801f8ca9`
- `KERNEL32!TlsGetValue` at `0x1801f8ccc`
- `KERNEL32!TlsGetValue` at `0x1801f8cdf`
- `KERNEL32!TlsGetValue` at `0x1801f8d0b`
- `KERNEL32!TlsGetValue` at `0x1801f8d2a`
- `KERNEL32!TlsGetValue` at `0x1801f8da3`
- `KERNEL32!TlsGetValue` at `0x1801f8db6`
- `KERNEL32!TlsGetValue` at `0x1801f8deb`
- `KERNEL32!TlsGetValue` at `0x1801f8e46`
- `KERNEL32!TlsGetValue` at `0x1801f8ed7`
- `KERNEL32!TlsGetValue` at `0x1801f8eec`
- `KERNEL32!TlsGetValue` at `0x1801f8efb`
- `KERNEL32!TlsGetValue` at `0x1801f8f57`
- `KERNEL32!TlsGetValue` at `0x1801f8f6e`
- `KERNEL32!TlsGetValue` at `0x1801f8f7d`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x1801f89dc`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x1801f89dc`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801f8986`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801f8b14`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801f8dda`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801f8986`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801f8b14`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801f8dda`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1801f89ae`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1801f89ae`

## pseudocode

```c

```
