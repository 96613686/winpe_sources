# System.Windows.TemplateContentLoader::Load

- ea: `0x2e360`
- end: `0x2e38c`
- name: `System.Windows.TemplateContentLoader::Load`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x2c7e0`
- `0x2e360`

## string_xrefs

- `0x2e363`: `serviceProvider`
- `0x2e371`: `xamlReader`

## pseudocode

```c

```

## disassembly

```asm
0x2e360  ldarg.2
0x2e361  brtrue.s loc_2E36E
0x2e363  ldstr    aServiceprovide// "serviceProvider"
0x2e368  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2e36d  throw
0x2e36e  ldarg.1
0x2e36f  brtrue.s loc_2E37C
0x2e371  ldstr    aXamlreader// "xamlReader"
0x2e376  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2e37b  throw
0x2e37c  ldarg.2
0x2e37d  call     T0x2B00001B
0x2e382  stloc.0
0x2e383  ldarg.1
0x2e384  ldloc.0
0x2e385  ldarg.2
0x2e386  newobj   instance void System.Windows.TemplateContent::.ctor(class [System.Xaml]System.Xaml.XamlReader xamlReader, class [System.Xaml]System.Xaml.IXamlObjectWriterFactory factory, class [mscorlib]System.IServiceProvider context)
0x2e38b  ret
```
