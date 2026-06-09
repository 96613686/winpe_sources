# Microsoft.VisualStudio.Setup.UserActivityMonitor::remove_UserIdleStateChanged

- ea: `0x2b20`
- end: `0x2b49`
- name: `Microsoft.VisualStudio.Setup.UserActivityMonitor::remove_UserIdleStateChanged`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2b20`

## pseudocode

```c

```

## disassembly

```asm
0x2b20  ldarg.0
0x2b21  ldfld    class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs> Microsoft.VisualStudio.Setup.UserActivityMonitor::UserIdleStateChanged
0x2b26  stloc.0
0x2b27  ldloc.0
0x2b28  stloc.1
0x2b29  ldloc.1
0x2b2a  ldarg.1
0x2b2b  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x2b30  castclass class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs>
0x2b35  stloc.2
0x2b36  ldarg.0
0x2b37  ldflda   class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs> Microsoft.VisualStudio.Setup.UserActivityMonitor::UserIdleStateChanged
0x2b3c  ldloc.2
0x2b3d  ldloc.1
0x2b3e  call     T0x2B00003A
0x2b43  stloc.0
0x2b44  ldloc.0
0x2b45  ldloc.1
0x2b46  bne.un.s loc_2B27
0x2b48  ret
```
