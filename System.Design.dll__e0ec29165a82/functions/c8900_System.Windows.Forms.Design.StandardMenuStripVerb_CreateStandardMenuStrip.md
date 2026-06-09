# System.Windows.Forms.Design.StandardMenuStripVerb::CreateStandardMenuStrip

- ea: `0xc8900`
- end: `0xc8fa6`
- name: `System.Windows.Forms.Design.StandardMenuStripVerb::CreateStandardMenuStrip`
- size: `1702`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0xc8860`

## callees

- `0x584f0`
- `0x58af0`
- `0x5b990`
- `0x8ef40`
- `0xc8900`
- `0xc93c0`
- `0xc9520`
- `0xec590`

## string_xrefs

- `0xc89d9`: `StandardMenuCopy`
- `0xc892b`: `StandardMenuOpen`
- `0xc8bfa`: `StandardMenuCreateDesc`

## pseudocode

```c

```

## disassembly

```asm
0xc8900  ldc.i4.4
0xc8901  newarr   string[]
0xc8906  dup
0xc8907  ldc.i4.0
0xc8908  ldc.i4.s 0xB
0xc890a  newarr   [mscorlib]System.String
0xc890f  dup
0xc8910  ldc.i4.0
0xc8911  ldstr    aStandardmenufi// "StandardMenuFile"
0xc8916  call     string System.Design.SR::GetString(string name)
0xc891b  stelem.ref
0xc891c  dup
0xc891d  ldc.i4.1
0xc891e  ldstr    aStandardmenune// "StandardMenuNew"
0xc8923  call     string System.Design.SR::GetString(string name)
0xc8928  stelem.ref
0xc8929  dup
0xc892a  ldc.i4.2
0xc892b  ldstr    aStandardmenuop// "StandardMenuOpen"
0xc8930  call     string System.Design.SR::GetString(string name)
0xc8935  stelem.ref
0xc8936  dup
0xc8937  ldc.i4.3
0xc8938  ldstr    asc_12DF04// "-"
0xc893d  stelem.ref
0xc893e  dup
0xc893f  ldc.i4.4
0xc8940  ldstr    aStandardmenusa// "StandardMenuSave"
0xc8945  call     string System.Design.SR::GetString(string name)
0xc894a  stelem.ref
0xc894b  dup
0xc894c  ldc.i4.5
0xc894d  ldstr    aStandardmenusa_0// "StandardMenuSaveAs"
0xc8952  call     string System.Design.SR::GetString(string name)
0xc8957  stelem.ref
0xc8958  dup
0xc8959  ldc.i4.6
0xc895a  ldstr    asc_12DF04// "-"
0xc895f  stelem.ref
0xc8960  dup
0xc8961  ldc.i4.7
0xc8962  ldstr    aStandardmenupr// "StandardMenuPrint"
0xc8967  call     string System.Design.SR::GetString(string name)
0xc896c  stelem.ref
0xc896d  dup
0xc896e  ldc.i4.8
0xc896f  ldstr    aStandardmenupr_0// "StandardMenuPrintPreview"
0xc8974  call     string System.Design.SR::GetString(string name)
0xc8979  stelem.ref
0xc897a  dup
0xc897b  ldc.i4.s 9
0xc897d  ldstr    asc_12DF04// "-"
0xc8982  stelem.ref
0xc8983  dup
0xc8984  ldc.i4.s 0xA
0xc8986  ldstr    aStandardmenuex// "StandardMenuExit"
0xc898b  call     string System.Design.SR::GetString(string name)
0xc8990  stelem.ref
0xc8991  stelem.ref
0xc8992  dup
0xc8993  ldc.i4.1
0xc8994  ldc.i4.s 9
0xc8996  newarr   [mscorlib]System.String
0xc899b  dup
0xc899c  ldc.i4.0
0xc899d  ldstr    aStandardmenued// "StandardMenuEdit"
0xc89a2  call     string System.Design.SR::GetString(string name)
0xc89a7  stelem.ref
0xc89a8  dup
0xc89a9  ldc.i4.1
0xc89aa  ldstr    aStandardmenuun// "StandardMenuUndo"
0xc89af  call     string System.Design.SR::GetString(string name)
0xc89b4  stelem.ref
0xc89b5  dup
0xc89b6  ldc.i4.2
0xc89b7  ldstr    aStandardmenure// "StandardMenuRedo"
0xc89bc  call     string System.Design.SR::GetString(string name)
0xc89c1  stelem.ref
0xc89c2  dup
0xc89c3  ldc.i4.3
0xc89c4  ldstr    asc_12DF04// "-"
0xc89c9  stelem.ref
0xc89ca  dup
0xc89cb  ldc.i4.4
0xc89cc  ldstr    aStandardmenucu// "StandardMenuCut"
0xc89d1  call     string System.Design.SR::GetString(string name)
0xc89d6  stelem.ref
0xc89d7  dup
0xc89d8  ldc.i4.5
0xc89d9  ldstr    aStandardmenuco// "StandardMenuCopy"
0xc89de  call     string System.Design.SR::GetString(string name)
0xc89e3  stelem.ref
0xc89e4  dup
0xc89e5  ldc.i4.6
0xc89e6  ldstr    aStandardmenupa// "StandardMenuPaste"
0xc89eb  call     string System.Design.SR::GetString(string name)
0xc89f0  stelem.ref
0xc89f1  dup
0xc89f2  ldc.i4.7
0xc89f3  ldstr    asc_12DF04// "-"
0xc89f8  stelem.ref
0xc89f9  dup
0xc89fa  ldc.i4.8
0xc89fb  ldstr    aStandardmenuse// "StandardMenuSelectAll"
0xc8a00  call     string System.Design.SR::GetString(string name)
0xc8a05  stelem.ref
0xc8a06  stelem.ref
0xc8a07  dup
0xc8a08  ldc.i4.2
0xc8a09  ldc.i4.3
0xc8a0a  newarr   [mscorlib]System.String
0xc8a0f  dup
0xc8a10  ldc.i4.0
0xc8a11  ldstr    aStandardmenuto// "StandardMenuTools"
0xc8a16  call     string System.Design.SR::GetString(string name)
0xc8a1b  stelem.ref
0xc8a1c  dup
0xc8a1d  ldc.i4.1
0xc8a1e  ldstr    aStandardmenucu_0// "StandardMenuCustomize"
0xc8a23  call     string System.Design.SR::GetString(string name)
0xc8a28  stelem.ref
0xc8a29  dup
0xc8a2a  ldc.i4.2
0xc8a2b  ldstr    aStandardmenuop_0// "StandardMenuOptions"
0xc8a30  call     string System.Design.SR::GetString(string name)
0xc8a35  stelem.ref
0xc8a36  stelem.ref
0xc8a37  dup
0xc8a38  ldc.i4.3
0xc8a39  ldc.i4.6
0xc8a3a  newarr   [mscorlib]System.String
0xc8a3f  dup
0xc8a40  ldc.i4.0
0xc8a41  ldstr    aStandardmenuhe// "StandardMenuHelp"
0xc8a46  call     string System.Design.SR::GetString(string name)
0xc8a4b  stelem.ref
0xc8a4c  dup
0xc8a4d  ldc.i4.1
0xc8a4e  ldstr    aStandardmenuco_0// "StandardMenuContents"
0xc8a53  call     string System.Design.SR::GetString(string name)
0xc8a58  stelem.ref
0xc8a59  dup
0xc8a5a  ldc.i4.2
0xc8a5b  ldstr    aStandardmenuin// "StandardMenuIndex"
0xc8a60  call     string System.Design.SR::GetString(string name)
0xc8a65  stelem.ref
0xc8a66  dup
0xc8a67  ldc.i4.3
0xc8a68  ldstr    aStandardmenuse_0// "StandardMenuSearch"
0xc8a6d  call     string System.Design.SR::GetString(string name)
0xc8a72  stelem.ref
0xc8a73  dup
0xc8a74  ldc.i4.4
0xc8a75  ldstr    asc_12DF04// "-"
0xc8a7a  stelem.ref
0xc8a7b  dup
0xc8a7c  ldc.i4.5
0xc8a7d  ldstr    aStandardmenuab// "StandardMenuAbout"
0xc8a82  call     string System.Design.SR::GetString(string name)
0xc8a87  stelem.ref
0xc8a88  stelem.ref
0xc8a89  stloc.0
0xc8a8a  ldc.i4.4
0xc8a8b  newarr   string[]
0xc8a90  dup
0xc8a91  ldc.i4.0
0xc8a92  ldc.i4.s 0xB
0xc8a94  newarr   [mscorlib]System.String
0xc8a99  dup
0xc8a9a  ldc.i4.0
0xc8a9b  ldstr    asc_12DF92// ""
0xc8aa0  stelem.ref
0xc8aa1  dup
0xc8aa2  ldc.i4.1
0xc8aa3  ldstr    aNew_0// "new"
0xc8aa8  stelem.ref
0xc8aa9  dup
0xc8aaa  ldc.i4.2
0xc8aab  ldstr    aOpen_0// "open"
0xc8ab0  stelem.ref
0xc8ab1  dup
0xc8ab2  ldc.i4.3
0xc8ab3  ldstr    asc_12DF04// "-"
0xc8ab8  stelem.ref
0xc8ab9  dup
0xc8aba  ldc.i4.4
0xc8abb  ldstr    aSave// "save"
0xc8ac0  stelem.ref
0xc8ac1  dup
0xc8ac2  ldc.i4.5
0xc8ac3  ldstr    asc_12DF92// ""
0xc8ac8  stelem.ref
0xc8ac9  dup
0xc8aca  ldc.i4.6
0xc8acb  ldstr    asc_12DF04// "-"
0xc8ad0  stelem.ref
0xc8ad1  dup
0xc8ad2  ldc.i4.7
0xc8ad3  ldstr    aPrint// "print"
0xc8ad8  stelem.ref
0xc8ad9  dup
0xc8ada  ldc.i4.8
0xc8adb  ldstr    aPrintpreview// "printPreview"
0xc8ae0  stelem.ref
0xc8ae1  dup
0xc8ae2  ldc.i4.s 9
0xc8ae4  ldstr    asc_12DF04// "-"
0xc8ae9  stelem.ref
0xc8aea  dup
0xc8aeb  ldc.i4.s 0xA
0xc8aed  ldstr    asc_12DF92// ""
0xc8af2  stelem.ref
0xc8af3  stelem.ref
0xc8af4  dup
0xc8af5  ldc.i4.1
0xc8af6  ldc.i4.s 9
0xc8af8  newarr   [mscorlib]System.String
0xc8afd  dup
0xc8afe  ldc.i4.0
0xc8aff  ldstr    asc_12DF92// ""
0xc8b04  stelem.ref
0xc8b05  dup
0xc8b06  ldc.i4.1
0xc8b07  ldstr    asc_12DF92// ""
0xc8b0c  stelem.ref
0xc8b0d  dup
0xc8b0e  ldc.i4.2
0xc8b0f  ldstr    asc_12DF92// ""
0xc8b14  stelem.ref
0xc8b15  dup
0xc8b16  ldc.i4.3
0xc8b17  ldstr    asc_12DF04// "-"
0xc8b1c  stelem.ref
0xc8b1d  dup
0xc8b1e  ldc.i4.4
0xc8b1f  ldstr    aCut// "cut"
0xc8b24  stelem.ref
0xc8b25  dup
0xc8b26  ldc.i4.5
0xc8b27  ldstr    aCopy// "copy"
0xc8b2c  stelem.ref
0xc8b2d  dup
0xc8b2e  ldc.i4.6
0xc8b2f  ldstr    aPaste// "paste"
0xc8b34  stelem.ref
0xc8b35  dup
0xc8b36  ldc.i4.7
0xc8b37  ldstr    asc_12DF04// "-"
0xc8b3c  stelem.ref
0xc8b3d  dup
0xc8b3e  ldc.i4.8
0xc8b3f  ldstr    asc_12DF92// ""
0xc8b44  stelem.ref
0xc8b45  stelem.ref
0xc8b46  dup
0xc8b47  ldc.i4.2
0xc8b48  ldc.i4.3
0xc8b49  newarr   [mscorlib]System.String
0xc8b4e  dup
0xc8b4f  ldc.i4.0
0xc8b50  ldstr    asc_12DF92// ""
0xc8b55  stelem.ref
0xc8b56  dup
0xc8b57  ldc.i4.1
0xc8b58  ldstr    asc_12DF92// ""
0xc8b5d  stelem.ref
0xc8b5e  dup
0xc8b5f  ldc.i4.2
0xc8b60  ldstr    asc_12DF92// ""
0xc8b65  stelem.ref
0xc8b66  stelem.ref
0xc8b67  dup
0xc8b68  ldc.i4.3
0xc8b69  ldc.i4.6
0xc8b6a  newarr   [mscorlib]System.String
0xc8b6f  dup
0xc8b70  ldc.i4.0
0xc8b71  ldstr    asc_12DF92// ""
0xc8b76  stelem.ref
0xc8b77  dup
0xc8b78  ldc.i4.1
0xc8b79  ldstr    asc_12DF92// ""
0xc8b7e  stelem.ref
0xc8b7f  dup
0xc8b80  ldc.i4.2
0xc8b81  ldstr    asc_12DF92// ""
0xc8b86  stelem.ref
0xc8b87  dup
0xc8b88  ldc.i4.3
0xc8b89  ldstr    asc_12DF92// ""
0xc8b8e  stelem.ref
0xc8b8f  dup
0xc8b90  ldc.i4.4
0xc8b91  ldstr    asc_12DF04// "-"
0xc8b96  stelem.ref
0xc8b97  dup
0xc8b98  ldc.i4.5
0xc8b99  ldstr    asc_12DF92// ""
0xc8b9e  stelem.ref
0xc8b9f  stelem.ref
  ... truncated ...
```
