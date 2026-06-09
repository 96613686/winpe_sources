# System.ComponentModel.Design.SelectionService::System.ComponentModel.Design.ISelectionService.SetSelectedComponents_0

- ea: `0x62290`
- end: `0x62539`
- name: `System.ComponentModel.Design.SelectionService::System.ComponentModel.Design.ISelectionService.SetSelectedComponents_0`
- size: `681`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x61c80`
- `0x61dc0`
- `0x61e80`
- `0x62290`
- `0xc97e0`
- `0xc9850`

## string_xrefs

- `0x62330`: `components`
- `0x62426`: `components`
- `0x62490`: `components`

## pseudocode

```c

```

## disassembly

```asm
0x62290  ldarg.2
0x62291  ldc.i4.s 0x20
0x62293  and
0x62294  ldc.i4.s 0x20
0x62296  ceq
0x62298  stloc.0
0x62299  ldarg.2
0x6229a  ldc.i4.s 0x10
0x6229c  and
0x6229d  ldc.i4.s 0x10
0x6229f  ceq
0x622a1  stloc.1
0x622a2  ldarg.2
0x622a3  ldc.i4.s 0x40
0x622a5  and
0x622a6  ldc.i4.s 0x40
0x622a8  ceq
0x622aa  stloc.2
0x622ab  ldarg.2
0x622ac  ldc.i4   0x80
0x622b1  and
0x622b2  ldc.i4   0x80
0x622b7  ceq
0x622b9  stloc.3
0x622ba  ldarg.2
0x622bb  ldc.i4.2
0x622bc  and
0x622bd  ldc.i4.2
0x622be  ceq
0x622c0  stloc.s  4
0x622c2  ldloc.0
0x622c3  ldloc.2
0x622c4  or
0x622c5  ldloc.3
0x622c6  or
0x622c7  ldloc.s  4
0x622c9  or
0x622ca  ldc.i4.0
0x622cb  ceq
0x622cd  stloc.s  5
0x622cf  ldarg.1
0x622d0  brtrue.s loc_622DA
0x622d2  ldc.i4.0
0x622d3  newarr   [mscorlib]System.Object
0x622d8  starg.s  1
0x622da  ldloc.s  5
0x622dc  brfalse.s loc_62303
0x622de  call     valuetype [System.Windows.Forms]System.Windows.Forms.Keys [System.Windows.Forms]System.Windows.Forms.Control::get_ModifierKeys()
0x622e3  ldc.i4   0x30000
0x622e8  and
0x622e9  ldc.i4.0
0x622ea  cgt
0x622ec  stloc.0
0x622ed  ldloc.2
0x622ee  call     valuetype [System.Windows.Forms]System.Windows.Forms.Keys [System.Windows.Forms]System.Windows.Forms.Control::get_ModifierKeys()
0x622f3  ldc.i4   0x10000
0x622f8  ceq
0x622fa  or
0x622fb  stloc.2
0x622fc  ldloc.0
0x622fd  ldloc.2
0x622fe  or
0x622ff  brfalse.s loc_62303
0x62301  ldc.i4.0
0x62302  stloc.1
0x62303  ldc.i4.0
0x62304  stloc.s  6
0x62306  ldnull
0x62307  stloc.s  7
0x62309  ldloc.1
0x6230a  brfalse.s loc_6235B
0x6230c  ldc.i4.1
0x6230d  ldarg.1
0x6230e  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x62313  bne.un.s loc_6235B
0x62315  ldarg.1
0x62316  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x6231b  stloc.s  9
0x6231d  br.s     loc_6233B
0x6231f  ldloc.s  9
0x62321  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x62326  stloc.s  0xA
0x62328  ldloc.s  0xA
0x6232a  stloc.s  7
0x6232c  ldloc.s  0xA
0x6232e  brtrue.s loc_62344
0x62330  ldstr    aComponents// "components"
0x62335  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6233a  throw
0x6233b  ldloc.s  9
0x6233d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x62342  brtrue.s loc_6231F
0x62344  leave.s  loc_6235B
0x62346  ldloc.s  9
0x62348  isinst   [mscorlib]System.IDisposable
0x6234d  stloc.s  0xB
0x6234f  ldloc.s  0xB
0x62351  brfalse.s loc_6235A
0x62353  ldloc.s  0xB
0x62355  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6235a  endfinally
0x6235b  ldloc.s  7
0x6235d  brfalse.s loc_623BF
0x6235f  ldarg.0
0x62360  ldfld    class [mscorlib]System.Collections.ArrayList System.ComponentModel.Design.SelectionService::_selection
0x62365  brfalse.s loc_623BF
0x62367  ldarg.0
0x62368  ldfld    class [mscorlib]System.Collections.ArrayList System.ComponentModel.Design.SelectionService::_selection
0x6236d  ldloc.s  7
0x6236f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::IndexOf(object)
0x62374  dup
0x62375  stloc.s  8
0x62377  ldc.i4.m1
0x62378  beq.s    loc_623BF
0x6237a  ldloc.s  8
0x6237c  brfalse  loc_624F2
0x62381  ldarg.0
0x62382  ldfld    class [mscorlib]System.Collections.ArrayList System.ComponentModel.Design.SelectionService::_selection
0x62387  ldc.i4.0
0x62388  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x6238d  stloc.s  0xC
0x6238f  ldarg.0
0x62390  ldfld    class [mscorlib]System.Collections.ArrayList System.ComponentModel.Design.SelectionService::_selection
0x62395  ldc.i4.0
0x62396  ldarg.0
0x62397  ldfld    class [mscorlib]System.Collections.ArrayList System.ComponentModel.Design.SelectionService::_selection
0x6239c  ldloc.s  8
0x6239e  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x623a3  callvirt instance void [mscorlib]System.Collections.ArrayList::set_Item(int32, object)
0x623a8  ldarg.0
0x623a9  ldfld    class [mscorlib]System.Collections.ArrayList System.ComponentModel.Design.SelectionService::_selection
0x623ae  ldloc.s  8
0x623b0  ldloc.s  0xC
0x623b2  callvirt instance void [mscorlib]System.Collections.ArrayList::set_Item(int32, object)
0x623b7  ldc.i4.1
0x623b8  stloc.s  6
0x623ba  br       loc_624F2
0x623bf  ldloc.0
0x623c0  brtrue   loc_62479
0x623c5  ldloc.2
0x623c6  brtrue   loc_62479
0x623cb  ldloc.3
0x623cc  brtrue   loc_62479
0x623d1  ldarg.0
0x623d2  ldfld    class [mscorlib]System.Collections.ArrayList System.ComponentModel.Design.SelectionService::_selection
0x623d7  brfalse  loc_62479
0x623dc  ldarg.0
0x623dd  ldfld    class [mscorlib]System.Collections.ArrayList System.ComponentModel.Design.SelectionService::_selection
0x623e2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x623e7  newarr   [mscorlib]System.Object
0x623ec  stloc.s  0xD
0x623ee  ldarg.0
0x623ef  ldfld    class [mscorlib]System.Collections.ArrayList System.ComponentModel.Design.SelectionService::_selection
0x623f4  ldloc.s  0xD
0x623f6  ldc.i4.0
0x623f7  callvirt instance void [mscorlib]System.Collections.ArrayList::CopyTo(class [mscorlib]System.Array, int32)
0x623fc  ldloc.s  0xD
0x623fe  stloc.s  0xE
0x62400  ldc.i4.0
0x62401  stloc.s  0xF
0x62403  br.s     loc_62471
0x62405  ldloc.s  0xE
0x62407  ldloc.s  0xF
0x62409  ldelem.ref
0x6240a  stloc.s  0x10
0x6240c  ldc.i4.1
0x6240d  stloc.s  0x11
0x6240f  ldarg.1
0x62410  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x62415  stloc.s  0x12
0x62417  br.s     loc_6243C
0x62419  ldloc.s  0x12
0x6241b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x62420  stloc.s  0x13
0x62422  ldloc.s  0x13
0x62424  brtrue.s loc_62431
0x62426  ldstr    aComponents// "components"
0x6242b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x62430  throw
0x62431  ldloc.s  0x13
0x62433  ldloc.s  0x10
0x62435  bne.un.s loc_6243C
0x62437  ldc.i4.0
0x62438  stloc.s  0x11
0x6243a  leave.s  loc_6245C
0x6243c  ldloc.s  0x12
0x6243e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x62443  brtrue.s loc_62419
0x62445  leave.s  loc_6245C
0x62447  ldloc.s  0x12
0x62449  isinst   [mscorlib]System.IDisposable
0x6244e  stloc.s  0xB
0x62450  ldloc.s  0xB
0x62452  brfalse.s loc_6245B
0x62454  ldloc.s  0xB
0x62456  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6245b  endfinally
0x6245c  ldloc.s  0x11
0x6245e  brfalse.s loc_6246B
0x62460  ldarg.0
0x62461  ldloc.s  0x10
0x62463  call     instance void System.ComponentModel.Design.SelectionService::RemoveSelection(object sel)
0x62468  ldc.i4.1
0x62469  stloc.s  6
0x6246b  ldloc.s  0xF
0x6246d  ldc.i4.1
0x6246e  add
0x6246f  stloc.s  0xF
0x62471  ldloc.s  0xF
0x62473  ldloc.s  0xE
0x62475  ldlen
0x62476  conv.i4
0x62477  blt.s    loc_62405
0x62479  ldarg.1
0x6247a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x6247f  stloc.s  0x14
0x62481  br.s     loc_624D2
0x62483  ldloc.s  0x14
0x62485  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6248a  stloc.s  0x15
0x6248c  ldloc.s  0x15
0x6248e  brtrue.s loc_6249B
0x62490  ldstr    aComponents// "components"
0x62495  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6249a  throw
0x6249b  ldarg.0
0x6249c  ldfld    class [mscorlib]System.Collections.ArrayList System.ComponentModel.Design.SelectionService::_selection
0x624a1  brfalse.s loc_624C4
0x624a3  ldarg.0
0x624a4  ldfld    class [mscorlib]System.Collections.ArrayList System.ComponentModel.Design.SelectionService::_selection
0x624a9  ldloc.s  0x15
0x624ab  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x624b0  brfalse.s loc_624C4
0x624b2  ldloc.0
0x624b3  ldloc.3
0x624b4  or
0x624b5  brfalse.s loc_624D2
0x624b7  ldarg.0
0x624b8  ldloc.s  0x15
0x624ba  call     instance void System.ComponentModel.Design.SelectionService::RemoveSelection(object sel)
0x624bf  ldc.i4.1
0x624c0  stloc.s  6
0x624c2  br.s     loc_624D2
0x624c4  ldloc.3
0x624c5  brtrue.s loc_624D2
0x624c7  ldarg.0
0x624c8  ldloc.s  0x15
0x624ca  call     instance void System.ComponentModel.Design.SelectionService::AddSelection(object sel)
0x624cf  ldc.i4.1
0x624d0  stloc.s  6
0x624d2  ldloc.s  0x14
0x624d4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x624d9  brtrue.s loc_62483
0x624db  leave.s  loc_624F2
0x624dd  ldloc.s  0x14
0x624df  isinst   [mscorlib]System.IDisposable
0x624e4  stloc.s  0xB
0x624e6  ldloc.s  0xB
0x624e8  brfalse.s loc_624F1
0x624ea  ldloc.s  0xB
0x624ec  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x624f1  endfinally
0x624f2  ldloc.s  6
0x624f4  brfalse.s loc_62538
0x624f6  ldarg.0
0x624f7  ldfld    class [mscorlib]System.Collections.ArrayList System.ComponentModel.Design.SelectionService::_selection
0x624fc  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x62501  ldc.i4.0
0x62502  ble.s    loc_62522
0x62504  ldarg.0
0x62505  ldfld    class System.Windows.Forms.Design.StatusCommandUI System.ComponentModel.Design.SelectionService::_statusCommandUI
0x6250a  ldarg.0
0x6250b  ldfld    class [mscorlib]System.Collections.ArrayList System.ComponentModel.Design.SelectionService::_selection
0x62510  ldc.i4.0
0x62511  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x62516  isinst   [System]System.ComponentModel.Component
0x6251b  callvirt instance void System.Windows.Forms.Design.StatusCommandUI::SetStatusInformation(class [System]System.ComponentModel.Component selectedComponent)
0x62520  br.s     loc_62532
0x62522  ldarg.0
0x62523  ldfld    class System.Windows.Forms.Design.StatusCommandUI System.ComponentModel.Design.SelectionService::_statusCommandUI
0x62528  ldsfld   valuetype [System.Drawing]System.Drawing.Rectangle [System.Drawing]System.Drawing.Rectangle::Empty
0x6252d  callvirt instance void System.Windows.Forms.Design.StatusCommandUI::SetStatusInformation(valuetype [System.Drawing]System.Drawing.Rectangle bounds)
0x62532  ldarg.0
0x62533  call     instance void System.ComponentModel.Design.SelectionService::OnSelectionChanged()
0x62538  ret
```
