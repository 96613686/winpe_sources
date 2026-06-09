# System.Windows.Interop.OSVersionHelper::.cctor

- ea: `0x61140`
- end: `0x61213`
- name: `System.Windows.Interop.OSVersionHelper::.cctor`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `41`
- tags: `loader_planting`

## callees

- `0x60ed0`
- `0x60ef0`
- `0x60f10`
- `0x60f30`
- `0x60f50`
- `0x60f70`
- `0x60f90`
- `0x60fb0`
- `0x60fd0`
- `0x60ff0`
- `0x61010`
- `0x61030`
- `0x61050`
- `0x61070`
- `0x61090`
- `0x610b0`
- `0x610d0`
- `0x610f0`
- `0x61110`
- `0x61130`
- `0x61220`
- `0x61230`
- `0x61240`
- `0x61250`
- `0x61260`
- `0x61270`
- `0x61280`
- `0x61290`
- `0x612a0`
- `0x612b0`
- `0x612c0`
- `0x612d0`
- `0x612e0`
- `0x612f0`
- `0x61300`
- `0x61310`
- `0x61320`
- `0x61330`
- `0x61340`
- `0x61350`
- `0x145db0`

## string_xrefs

- `0x61140`: `PresentationNative_v0400.dll`

## pseudocode

```c

```

## disassembly

```asm
0x61140  ldstr    aPresentationna// "PresentationNative_v0400.dll"
0x61145  call     void MS.Internal.PresentationCore.WpfLibraryLoader::EnsureLoaded(string dllName)
0x6114a  call     bool System.Windows.Interop.OSVersionHelper::IsWindows10RS5OrGreater()
0x6114f  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindows10RS5OrGreater(bool value)
0x61154  call     bool System.Windows.Interop.OSVersionHelper::IsWindows10RS4OrGreater()
0x61159  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindows10RS4OrGreater(bool value)
0x6115e  call     bool System.Windows.Interop.OSVersionHelper::IsWindows10RS3OrGreater()
0x61163  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindows10RS3OrGreater(bool value)
0x61168  call     bool System.Windows.Interop.OSVersionHelper::IsWindows10RS2OrGreater()
0x6116d  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindows10RS2OrGreater(bool value)
0x61172  call     bool System.Windows.Interop.OSVersionHelper::IsWindows10RS1OrGreater()
0x61177  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindows10RS1OrGreater(bool value)
0x6117c  call     bool System.Windows.Interop.OSVersionHelper::IsWindows10TH2OrGreater()
0x61181  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindows10TH2OrGreater(bool value)
0x61186  call     bool System.Windows.Interop.OSVersionHelper::IsWindows10TH1OrGreater()
0x6118b  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindows10TH1OrGreater(bool value)
0x61190  call     bool System.Windows.Interop.OSVersionHelper::IsWindows10OrGreater()
0x61195  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindows10OrGreater(bool value)
0x6119a  call     bool System.Windows.Interop.OSVersionHelper::IsWindows8Point1OrGreater()
0x6119f  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindows8Point1OrGreater(bool value)
0x611a4  call     bool System.Windows.Interop.OSVersionHelper::IsWindows8OrGreater()
0x611a9  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindows8OrGreater(bool value)
0x611ae  call     bool System.Windows.Interop.OSVersionHelper::IsWindows7SP1OrGreater()
0x611b3  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindows7SP1OrGreater(bool value)
0x611b8  call     bool System.Windows.Interop.OSVersionHelper::IsWindows7OrGreater()
0x611bd  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindows7OrGreater(bool value)
0x611c2  call     bool System.Windows.Interop.OSVersionHelper::IsWindowsVistaSP2OrGreater()
0x611c7  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindowsVistaSP2OrGreater(bool value)
0x611cc  call     bool System.Windows.Interop.OSVersionHelper::IsWindowsVistaSP1OrGreater()
0x611d1  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindowsVistaSP1OrGreater(bool value)
0x611d6  call     bool System.Windows.Interop.OSVersionHelper::IsWindowsVistaOrGreater()
0x611db  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindowsVistaOrGreater(bool value)
0x611e0  call     bool System.Windows.Interop.OSVersionHelper::IsWindowsXPSP3OrGreater()
0x611e5  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindowsXPSP3OrGreater(bool value)
0x611ea  call     bool System.Windows.Interop.OSVersionHelper::IsWindowsXPSP2OrGreater()
0x611ef  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindowsXPSP2OrGreater(bool value)
0x611f4  call     bool System.Windows.Interop.OSVersionHelper::IsWindowsXPSP1OrGreater()
0x611f9  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindowsXPSP1OrGreater(bool value)
0x611fe  call     bool System.Windows.Interop.OSVersionHelper::IsWindowsXPOrGreater()
0x61203  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindowsXPOrGreater(bool value)
0x61208  call     bool System.Windows.Interop.OSVersionHelper::IsWindowsServer()
0x6120d  call     void System.Windows.Interop.OSVersionHelper::set_IsOsWindowsServer(bool value)
0x61212  ret
```
