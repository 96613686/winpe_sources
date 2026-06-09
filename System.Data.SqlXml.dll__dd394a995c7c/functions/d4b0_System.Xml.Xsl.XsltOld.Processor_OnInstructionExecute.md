# System.Xml.Xsl.XsltOld.Processor::OnInstructionExecute

- ea: `0xd4b0`
- end: `0xd4e4`
- name: `System.Xml.Xsl.XsltOld.Processor::OnInstructionExecute`
- size: `52`
- prototype: ``
- caller_count: `24`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x9440`
- `0x54410`
- `0x54480`
- `0x544f0`
- `0x54560`
- `0x545d0`
- `0x54640`
- `0x546b0`
- `0x54720`
- `0x54790`
- `0x54800`
- `0x54890`
- `0x548f0`
- `0x54960`
- `0x549d0`
- `0x54a40`
- `0x54b00`
- `0x54b90`
- `0x54c00`
- `0x54c80`
- `0x54cf0`
- `0x54d60`
- `0x54de0`
- `0x54e40`

## callees

- `0xc700`
- `0x135f0`

## pseudocode

```c

```

## disassembly

```asm
0xd4b0  ldarg.0
0xd4b1  ldfld    class [System.Xml]System.Xml.HWStack System.Xml.Xsl.XsltOld.Processor::debuggerStack
0xd4b6  callvirt instance object [System.Xml]System.Xml.HWStack::Peek()
0xd4bb  castclass DebuggerFrame
0xd4c0  stloc.0
0xd4c1  ldloc.0
0xd4c2  ldarg.0
0xd4c3  ldfld    class [System.Xml]System.Xml.HWStack System.Xml.Xsl.XsltOld.Processor::actionStack
0xd4c8  callvirt instance object [System.Xml]System.Xml.HWStack::Peek()
0xd4cd  castclass System.Xml.Xsl.XsltOld.ActionFrame
0xd4d2  stfld    class System.Xml.Xsl.XsltOld.ActionFrame DebuggerFrame::actionFrame
0xd4d7  ldarg.0
0xd4d8  call     instance class System.Xml.Xsl.XsltOld.Debugger.IXsltDebugger System.Xml.Xsl.XsltOld.Processor::get_Debugger()
0xd4dd  ldarg.0
0xd4de  callvirt instance void System.Xml.Xsl.XsltOld.Debugger.IXsltDebugger::OnInstructionExecute(class System.Xml.Xsl.XsltOld.Debugger.IXsltProcessor xsltProcessor)
0xd4e3  ret
```
