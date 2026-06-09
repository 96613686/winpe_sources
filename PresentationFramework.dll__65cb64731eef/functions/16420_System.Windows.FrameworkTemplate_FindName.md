# System.Windows.FrameworkTemplate::FindName

- ea: `0x16420`
- end: `0x16456`
- name: `System.Windows.FrameworkTemplate::FindName`
- size: `54`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x71970`
- `0x160890`
- `0x160920`
- `0x19d950`
- `0x1d9ec0`
- `0x229370`
- `0x241e10`

## callees

- `0xe6f0`
- `0x16420`
- `0x21af0`
- `0x38c40`

## string_xrefs

- `0x16429`: `templatedParent`
- `0x1643d`: `TemplateFindNameInInvalidElement`

## pseudocode

```c

```

## disassembly

```asm
0x16420  ldarg.0
0x16421  call     instance void [WindowsBase]System.Windows.Threading.DispatcherObject::VerifyAccess()
0x16426  ldarg.2
0x16427  brtrue.s loc_16434
0x16429  ldstr    aTemplatedparen// "templatedParent"
0x1642e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x16433  throw
0x16434  ldarg.0
0x16435  ldarg.2
0x16436  callvirt instance class System.Windows.FrameworkTemplate System.Windows.FrameworkElement::get_TemplateInternal()
0x1643b  beq.s    loc_1644D
0x1643d  ldstr    aTemplatefindna// "TemplateFindNameInInvalidElement"
0x16442  call     string System.Windows.SR::Get(string id)
0x16447  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1644c  throw
0x1644d  ldarg.2
0x1644e  ldarg.1
0x1644f  ldarg.0
0x16450  call     object System.Windows.StyleHelper::FindNameInTemplateContent(class [WindowsBase]System.Windows.DependencyObject container, string childName, class System.Windows.FrameworkTemplate frameworkTemplate)
0x16455  ret
```
