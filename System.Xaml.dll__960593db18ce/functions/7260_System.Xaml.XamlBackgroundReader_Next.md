# System.Xaml.XamlBackgroundReader::Next

- ea: `0x7260`
- end: `0x730e`
- name: `System.Xaml.XamlBackgroundReader::Next`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x7310`

## callees

- `0x2310`
- `0x7140`
- `0x7160`
- `0x7260`
- `0xb3f0`

## string_xrefs

- `0x7268`: `XamlBackgroundReader`

## pseudocode

```c

```

## disassembly

```asm
0x7260  ldarg.0
0x7261  call     instance bool System.Xaml.XamlReader::get_IsDisposed()
0x7266  brfalse.s loc_7273
0x7268  ldstr    aXamlbackground// "XamlBackgroundReader"
0x726d  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x7272  throw
0x7273  ldarg.0
0x7274  call     instance bool System.Xaml.XamlBackgroundReader::get_OutgoingEmpty()
0x7279  brfalse.s loc_72AD
0x727b  ldarg.0
0x727c  ldflda   valuetype System.Xaml.XamlNode System.Xaml.XamlBackgroundReader::_currentNode
0x7281  call     instance bool System.Xaml.XamlNode::get_IsEof()
0x7286  brfalse.s loc_728F
0x7288  ldarg.0
0x7289  ldfld    valuetype System.Xaml.XamlNode System.Xaml.XamlBackgroundReader::_currentNode
0x728e  ret
0x728f  ldarg.0
0x7290  ldfld    class [mscorlib]System.Threading.EventWaitHandle System.Xaml.XamlBackgroundReader::_providerFullEvent
0x7295  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x729a  pop
0x729b  ldarg.0
0x729c  call     instance void System.Xaml.XamlBackgroundReader::SwapBuffers()
0x72a1  ldarg.0
0x72a2  ldfld    class [mscorlib]System.Threading.EventWaitHandle System.Xaml.XamlBackgroundReader::_dataReceivedEvent
0x72a7  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x72ac  pop
0x72ad  ldarg.0
0x72ae  ldarg.0
0x72af  ldfld    valuetype System.Xaml.XamlNode[] System.Xaml.XamlBackgroundReader::_outgoing
0x72b4  ldarg.0
0x72b5  ldarg.0
0x72b6  ldfld    int32 System.Xaml.XamlBackgroundReader::_outIdx
0x72bb  stloc.0
0x72bc  ldloc.0
0x72bd  ldc.i4.1
0x72be  add
0x72bf  stfld    int32 System.Xaml.XamlBackgroundReader::_outIdx
0x72c4  ldloc.0
0x72c5  ldelem   System.Xaml.XamlNode
0x72ca  stfld    valuetype System.Xaml.XamlNode System.Xaml.XamlBackgroundReader::_currentNode
0x72cf  ldarg.0
0x72d0  ldflda   valuetype System.Xaml.XamlNode System.Xaml.XamlBackgroundReader::_currentNode
0x72d5  call     instance bool System.Xaml.XamlNode::get_IsEof()
0x72da  brfalse.s loc_7307
0x72dc  ldarg.0
0x72dd  ldfld    class [mscorlib]System.Threading.Thread System.Xaml.XamlBackgroundReader::_thread
0x72e2  brfalse.s loc_7307
0x72e4  ldarg.0
0x72e5  ldfld    class [mscorlib]System.Threading.Thread System.Xaml.XamlBackgroundReader::_thread
0x72ea  callvirt instance void [mscorlib]System.Threading.Thread::Join()
0x72ef  ldarg.0
0x72f0  ldfld    class [mscorlib]System.Exception System.Xaml.XamlBackgroundReader::_caughtException
0x72f5  brfalse.s loc_7307
0x72f7  ldarg.0
0x72f8  ldfld    class [mscorlib]System.Exception System.Xaml.XamlBackgroundReader::_caughtException
0x72fd  stloc.1
0x72fe  ldarg.0
0x72ff  ldnull
0x7300  stfld    class [mscorlib]System.Exception System.Xaml.XamlBackgroundReader::_caughtException
0x7305  ldloc.1
0x7306  throw
0x7307  ldarg.0
0x7308  ldfld    valuetype System.Xaml.XamlNode System.Xaml.XamlBackgroundReader::_currentNode
0x730d  ret
```
