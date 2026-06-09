# System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::CollapseGlyph

- ea: `0xeea30`
- end: `0xeebb5`
- name: `System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::CollapseGlyph`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0xee8e0`

## callees

- `0x8ef40`
- `0xee960`
- `0xeea30`

## string_xrefs

- `0xeea5e`: `topopen.bmp`
- `0xeeab1`: `bottomopen.bmp`
- `0xeeb03`: `leftopen.bmp`
- `0xeeb56`: `rightopen.bmp`

## pseudocode

```c

```

## disassembly

```asm
0xeea30  ldarg.0
0xeea31  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripPanel System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::relatedPanel
0xeea36  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle [System.Windows.Forms]System.Windows.Forms.Control::get_Dock()
0xeea3b  stloc.0
0xeea3c  ldc.i4.0
0xeea3d  stloc.1
0xeea3e  ldc.i4.0
0xeea3f  stloc.2
0xeea40  ldloc.0
0xeea41  ldc.i4.1
0xeea42  sub
0xeea43  switch   loc_EEA5D, loc_EEAB0, loc_EEB02, loc_EEB55
0xeea58  br       loc_EEBA4
0xeea5d  ldarg.0
0xeea5e  ldstr    aTopopenBmp// "topopen.bmp"
0xeea63  call     instance void System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::SetBitmap(string fileName)
0xeea68  ldarga.s 1
0xeea6a  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_Width()
0xeea6f  ldarg.0
0xeea70  ldfld    int32 System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::imageWidth
0xeea75  sub
0xeea76  ldc.i4.2
0xeea77  div
0xeea78  stloc.1
0xeea79  ldloc.1
0xeea7a  ldc.i4.0
0xeea7b  ble      loc_EEBB4
0xeea80  ldarg.0
0xeea81  ldarga.s 1
0xeea83  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_X()
0xeea88  ldloc.1
0xeea89  add
0xeea8a  ldarga.s 1
0xeea8c  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_Y()
0xeea91  ldarga.s 1
0xeea93  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_Height()
0xeea98  add
0xeea99  ldarg.0
0xeea9a  ldfld    int32 System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::imageWidth
0xeea9f  ldarg.0
0xeeaa0  ldfld    int32 System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::imageHeight
0xeeaa5  newobj   instance void [System.Drawing]System.Drawing.Rectangle::.ctor(int32, int32, int32, int32)
0xeeaaa  stfld    valuetype [System.Drawing]System.Drawing.Rectangle System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::glyphBounds
0xeeaaf  ret
0xeeab0  ldarg.0
0xeeab1  ldstr    aBottomopenBmp// "bottomopen.bmp"
0xeeab6  call     instance void System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::SetBitmap(string fileName)
0xeeabb  ldarga.s 1
0xeeabd  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_Width()
0xeeac2  ldarg.0
0xeeac3  ldfld    int32 System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::imageWidth
0xeeac8  sub
0xeeac9  ldc.i4.2
0xeeaca  div
0xeeacb  stloc.1
0xeeacc  ldloc.1
0xeeacd  ldc.i4.0
0xeeace  ble      loc_EEBB4
0xeead3  ldarg.0
0xeead4  ldarga.s 1
0xeead6  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_X()
0xeeadb  ldloc.1
0xeeadc  add
0xeeadd  ldarga.s 1
0xeeadf  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_Y()
0xeeae4  ldarg.0
0xeeae5  ldfld    int32 System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::imageHeight
0xeeaea  sub
0xeeaeb  ldarg.0
0xeeaec  ldfld    int32 System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::imageWidth
0xeeaf1  ldarg.0
0xeeaf2  ldfld    int32 System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::imageHeight
0xeeaf7  newobj   instance void [System.Drawing]System.Drawing.Rectangle::.ctor(int32, int32, int32, int32)
0xeeafc  stfld    valuetype [System.Drawing]System.Drawing.Rectangle System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::glyphBounds
0xeeb01  ret
0xeeb02  ldarg.0
0xeeb03  ldstr    aLeftopenBmp// "leftopen.bmp"
0xeeb08  call     instance void System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::SetBitmap(string fileName)
0xeeb0d  ldarga.s 1
0xeeb0f  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_Height()
0xeeb14  ldarg.0
0xeeb15  ldfld    int32 System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::imageWidth
0xeeb1a  sub
0xeeb1b  ldc.i4.2
0xeeb1c  div
0xeeb1d  stloc.2
0xeeb1e  ldloc.2
0xeeb1f  ldc.i4.0
0xeeb20  ble      loc_EEBB4
0xeeb25  ldarg.0
0xeeb26  ldarga.s 1
0xeeb28  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_X()
0xeeb2d  ldarga.s 1
0xeeb2f  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_Width()
0xeeb34  add
0xeeb35  ldarga.s 1
0xeeb37  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_Y()
0xeeb3c  ldloc.2
0xeeb3d  add
0xeeb3e  ldarg.0
0xeeb3f  ldfld    int32 System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::imageHeight
0xeeb44  ldarg.0
0xeeb45  ldfld    int32 System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::imageWidth
0xeeb4a  newobj   instance void [System.Drawing]System.Drawing.Rectangle::.ctor(int32, int32, int32, int32)
0xeeb4f  stfld    valuetype [System.Drawing]System.Drawing.Rectangle System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::glyphBounds
0xeeb54  ret
0xeeb55  ldarg.0
0xeeb56  ldstr    aRightopenBmp// "rightopen.bmp"
0xeeb5b  call     instance void System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::SetBitmap(string fileName)
0xeeb60  ldarga.s 1
0xeeb62  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_Height()
0xeeb67  ldarg.0
0xeeb68  ldfld    int32 System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::imageWidth
0xeeb6d  sub
0xeeb6e  ldc.i4.2
0xeeb6f  div
0xeeb70  stloc.2
0xeeb71  ldloc.2
0xeeb72  ldc.i4.0
0xeeb73  ble.s    loc_EEBB4
0xeeb75  ldarg.0
0xeeb76  ldarga.s 1
0xeeb78  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_X()
0xeeb7d  ldarg.0
0xeeb7e  ldfld    int32 System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::imageHeight
0xeeb83  sub
0xeeb84  ldarga.s 1
0xeeb86  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_Y()
0xeeb8b  ldloc.2
0xeeb8c  add
0xeeb8d  ldarg.0
0xeeb8e  ldfld    int32 System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::imageHeight
0xeeb93  ldarg.0
0xeeb94  ldfld    int32 System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::imageWidth
0xeeb99  newobj   instance void [System.Drawing]System.Drawing.Rectangle::.ctor(int32, int32, int32, int32)
0xeeb9e  stfld    valuetype [System.Drawing]System.Drawing.Rectangle System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionGlyph::glyphBounds
0xeeba3  ret
0xeeba4  ldstr    aToolstrippanel// "ToolStripPanelGlyphUnsupportedDock"
0xeeba9  call     string System.Design.SR::GetString(string name)
0xeebae  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0xeebb3  throw
0xeebb4  ret
```
