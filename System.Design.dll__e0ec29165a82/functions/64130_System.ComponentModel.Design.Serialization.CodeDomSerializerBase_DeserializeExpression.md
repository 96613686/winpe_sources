# System.ComponentModel.Design.Serialization.CodeDomSerializerBase::DeserializeExpression

- ea: `0x64130`
- end: `0x64d98`
- name: `System.ComponentModel.Design.Serialization.CodeDomSerializerBase::DeserializeExpression`
- size: `3176`
- prototype: ``
- caller_count: `13`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x63480`
- `0x63660`
- `0x64020`
- `0x64130`
- `0x64ef0`
- `0x65020`
- `0x65210`
- `0x65510`
- `0x656a0`
- `0x657d0`
- `0x6a4b0`
- `0x71690`
- `0x129870`

## callees

- `0x63b80`
- `0x63bb0`
- `0x63c40`
- `0x63ca0`
- `0x64020`
- `0x64130`
- `0x65510`
- `0x65810`
- `0x65870`
- `0x66f00`
- `0x6beb0`
- `0x8eec0`
- `0x8ef40`

## string_xrefs

- `0x64132`: `CodeDomSerializerBase::DeserializeExpression`

## pseudocode

```c

```

## disassembly

```asm
0x64130  ldarg.3
0x64131  stloc.0
0x64132  ldstr    aCodedomseriali_2// "CodeDomSerializerBase::DeserializeExpre"...
0x64137  call     class [mscorlib]System.IDisposable System.ComponentModel.Design.Serialization.CodeDomSerializerBase::TraceScope(string name)
0x6413c  stloc.1
0x6413d  br       loc_64D84
0x64142  ldloc.0
0x64143  isinst   [System]System.CodeDom.CodePrimitiveExpression
0x64148  dup
0x64149  stloc.2
0x6414a  brfalse.s loc_64158
0x6414c  ldloc.2
0x6414d  callvirt instance object [System]System.CodeDom.CodePrimitiveExpression::get_Value()
0x64152  stloc.0
0x64153  leave    loc_64D96
0x64158  ldloc.0
0x64159  isinst   [System]System.CodeDom.CodePropertyReferenceExpression
0x6415e  dup
0x6415f  stloc.3
0x64160  brfalse.s loc_64171
0x64162  ldarg.0
0x64163  ldarg.1
0x64164  ldloc.3
0x64165  ldc.i4.1
0x64166  call     instance object System.ComponentModel.Design.Serialization.CodeDomSerializerBase::DeserializePropertyReferenceExpression(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, class [System]System.CodeDom.CodePropertyReferenceExpression propertyReferenceEx, bool reportError)
0x6416b  stloc.0
0x6416c  leave    loc_64D96
0x64171  ldloc.0
0x64172  isinst   [System]System.CodeDom.CodeThisReferenceExpression
0x64177  brfalse.s loc_641E6
0x64179  ldarg.1
0x6417a  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::get_Context()
0x6417f  ldtoken  System.ComponentModel.Design.Serialization.RootContext
0x64184  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x64189  callvirt instance object [System]System.ComponentModel.Design.Serialization.ContextStack::get_Item(class [mscorlib]System.Type)
0x6418e  castclass System.ComponentModel.Design.Serialization.RootContext
0x64193  stloc.s  0x13
0x64195  ldloc.s  0x13
0x64197  brfalse.s loc_641A3
0x64199  ldloc.s  0x13
0x6419b  callvirt instance object System.ComponentModel.Design.Serialization.RootContext::get_Value()
0x641a0  stloc.0
0x641a1  br.s     loc_641C6
0x641a3  ldarg.1
0x641a4  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0x641a9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x641ae  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x641b3  isinst   [System]System.ComponentModel.Design.IDesignerHost
0x641b8  stloc.s  0x14
0x641ba  ldloc.s  0x14
0x641bc  brfalse.s loc_641C6
0x641be  ldloc.s  0x14
0x641c0  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.IDesignerHost::get_RootComponent()
0x641c5  stloc.0
0x641c6  ldloc.0
0x641c7  brtrue   loc_64D8A
0x641cc  ldarg.1
0x641cd  ldstr    aSerializernoro// "SerializerNoRootExpression"
0x641d2  call     string System.Design.SR::GetString(string name)
0x641d7  ldstr    aSerializernoro// "SerializerNoRootExpression"
0x641dc  call     void System.ComponentModel.Design.Serialization.CodeDomSerializerBase::Error(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, string exceptionText, string helpLink)
0x641e1  leave    loc_64D96
0x641e6  ldloc.0
0x641e7  isinst   [System]System.CodeDom.CodeTypeReferenceExpression
0x641ec  dup
0x641ed  stloc.s  4
0x641ef  brfalse.s loc_6420A
0x641f1  ldarg.1
0x641f2  ldarg.1
0x641f3  ldloc.s  4
0x641f5  callvirt instance class [System]System.CodeDom.CodeTypeReference [System]System.CodeDom.CodeTypeReferenceExpression::get_Type()
0x641fa  call     string System.ComponentModel.Design.Serialization.CodeDomSerializerBase::GetTypeNameFromCodeTypeReference(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, class [System]System.CodeDom.CodeTypeReference typeref)
0x641ff  callvirt instance class [mscorlib]System.Type [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::GetType(string)
0x64204  stloc.0
0x64205  leave    loc_64D96
0x6420a  ldloc.0
0x6420b  isinst   [System]System.CodeDom.CodeObjectCreateExpression
0x64210  dup
0x64211  stloc.s  5
0x64213  brfalse  loc_64404
0x64218  ldnull
0x64219  stloc.0
0x6421a  ldarg.1
0x6421b  ldarg.1
0x6421c  ldloc.s  5
0x6421e  callvirt instance class [System]System.CodeDom.CodeTypeReference [System]System.CodeDom.CodeObjectCreateExpression::get_CreateType()
0x64223  call     string System.ComponentModel.Design.Serialization.CodeDomSerializerBase::GetTypeNameFromCodeTypeReference(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, class [System]System.CodeDom.CodeTypeReference typeref)
0x64228  callvirt instance class [mscorlib]System.Type [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::GetType(string)
0x6422d  stloc.s  0x15
0x6422f  ldloc.s  0x15
0x64231  ldnull
0x64232  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x64237  brfalse  loc_643D5
0x6423c  ldloc.s  5
0x6423e  callvirt instance class [System]System.CodeDom.CodeExpressionCollection [System]System.CodeDom.CodeObjectCreateExpression::get_Parameters()
0x64243  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x64248  newarr   [mscorlib]System.Object
0x6424d  stloc.s  0x16
0x6424f  ldc.i4.1
0x64250  stloc.s  0x17
0x64252  ldc.i4.0
0x64253  stloc.s  0x18
0x64255  br       loc_643AD
0x6425a  ldloc.s  0x16
0x6425c  ldloc.s  0x18
0x6425e  ldarg.0
0x6425f  ldarg.1
0x64260  ldnull
0x64261  ldloc.s  5
0x64263  callvirt instance class [System]System.CodeDom.CodeExpressionCollection [System]System.CodeDom.CodeObjectCreateExpression::get_Parameters()
0x64268  ldloc.s  0x18
0x6426a  callvirt instance class [System]System.CodeDom.CodeExpression [System]System.CodeDom.CodeExpressionCollection::get_Item(int32)
0x6426f  call     instance object System.ComponentModel.Design.Serialization.CodeDomSerializerBase::DeserializeExpression(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, string name, class [System]System.CodeDom.CodeExpression expression)
0x64274  stelem.ref
0x64275  ldloc.s  0x16
0x64277  ldloc.s  0x18
0x64279  ldelem.ref
0x6427a  isinst   [System]System.CodeDom.CodeExpression
0x6427f  brfalse  loc_643A7
0x64284  ldtoken  [mscorlib]System.Delegate
0x64289  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6428e  ldloc.s  0x15
0x64290  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x64295  brfalse  loc_643A2
0x6429a  ldloc.s  0x16
0x6429c  ldlen
0x6429d  conv.i4
0x6429e  ldc.i4.1
0x6429f  bne.un   loc_643A2
0x642a4  ldloc.s  0x16
0x642a6  ldloc.s  0x18
0x642a8  ldelem.ref
0x642a9  isinst   [System]System.CodeDom.CodeMethodReferenceExpression
0x642ae  brfalse  loc_643A2
0x642b3  ldloc.s  0x16
0x642b5  ldloc.s  0x18
0x642b7  ldelem.ref
0x642b8  castclass [System]System.CodeDom.CodeMethodReferenceExpression
0x642bd  stloc.s  0x19
0x642bf  ldloc.s  0x19
0x642c1  callvirt instance class [System]System.CodeDom.CodeExpression [System]System.CodeDom.CodeMethodReferenceExpression::get_TargetObject()
0x642c6  isinst   [System]System.CodeDom.CodeThisReferenceExpression
0x642cb  brtrue   loc_643A2
0x642d0  ldarg.0
0x642d1  ldarg.1
0x642d2  ldnull
0x642d3  ldloc.s  0x19
0x642d5  callvirt instance class [System]System.CodeDom.CodeExpression [System]System.CodeDom.CodeMethodReferenceExpression::get_TargetObject()
0x642da  call     instance object System.ComponentModel.Design.Serialization.CodeDomSerializerBase::DeserializeExpression(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, string name, class [System]System.CodeDom.CodeExpression expression)
0x642df  stloc.s  0x1A
0x642e1  ldloc.s  0x1A
0x642e3  isinst   [System]System.CodeDom.CodeExpression
0x642e8  brtrue   loc_643A2
0x642ed  ldloc.s  0x15
0x642ef  ldstr    aInvoke// "Invoke"
0x642f4  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string)
0x642f9  stloc.s  0x1B
0x642fb  ldloc.s  0x1B
0x642fd  ldnull
0x642fe  call     bool [mscorlib]System.Reflection.MethodInfo::op_Inequality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x64303  brfalse  loc_643A2
0x64308  ldloc.s  0x1B
0x6430a  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0x6430f  stloc.s  0x1C
0x64311  ldloc.s  0x1C
0x64313  ldlen
0x64314  conv.i4
0x64315  newarr   [mscorlib]System.Type
0x6431a  stloc.s  0x1D
0x6431c  ldc.i4.0
0x6431d  stloc.s  0x1F
0x6431f  br.s     loc_64336
0x64321  ldloc.s  0x1D
0x64323  ldloc.s  0x1F
0x64325  ldloc.s  0x1C
0x64327  ldloc.s  0x18
0x64329  ldelem.ref
0x6432a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.ParameterInfo::get_ParameterType()
0x6432f  stelem.ref
0x64330  ldloc.s  0x1F
0x64332  ldc.i4.1
0x64333  add
0x64334  stloc.s  0x1F
0x64336  ldloc.s  0x1F
0x64338  ldloc.s  0x1D
0x6433a  ldlen
0x6433b  conv.i4
0x6433c  blt.s    loc_64321
0x6433e  ldarg.1
0x6433f  ldloc.s  0x1A
0x64341  call     class [mscorlib]System.Type System.ComponentModel.Design.Serialization.CodeDomSerializerBase::GetReflectionTypeHelper(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object instance)
0x64346  ldloc.s  0x19
0x64348  callvirt instance string [System]System.CodeDom.CodeMethodReferenceExpression::get_MethodName()
0x6434d  ldloc.s  0x1D
0x6434f  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, class [mscorlib]System.Type[])
0x64354  stloc.s  0x1E
0x64356  ldloc.s  0x1E
0x64358  ldnull
0x64359  call     bool [mscorlib]System.Reflection.MethodInfo::op_Inequality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x6435e  brfalse.s loc_643A2
0x64360  ldloc.s  0x1A
0x64362  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x64367  ldloc.s  0x19
0x64369  callvirt instance string [System]System.CodeDom.CodeMethodReferenceExpression::get_MethodName()
0x6436e  ldloc.s  0x1D
0x64370  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, class [mscorlib]System.Type[])
0x64375  stloc.s  0x1E
0x64377  ldloc.s  0x15
0x64379  ldc.i4.2
0x6437a  newarr   [mscorlib]System.Object
0x6437f  dup
0x64380  ldc.i4.0
0x64381  ldloc.s  0x1A
0x64383  stelem.ref
0x64384  dup
0x64385  ldc.i4.1
0x64386  ldloc.s  0x1E
0x64388  callvirt instance valuetype [mscorlib]System.RuntimeMethodHandle [mscorlib]System.Reflection.MethodBase::get_MethodHandle()
0x6438d  stloc.s  0x20
0x6438f  ldloca.s 0x20
0x64391  call     instance native int [mscorlib]System.RuntimeMethodHandle::GetFunctionPointer()
0x64396  box      [mscorlib]System.IntPtr
0x6439b  stelem.ref
0x6439c  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type, object[])
0x643a1  stloc.0
0x643a2  ldc.i4.0
0x643a3  stloc.s  0x17
0x643a5  br.s     loc_643B8
0x643a7  ldloc.s  0x18
0x643a9  ldc.i4.1
0x643aa  add
0x643ab  stloc.s  0x18
0x643ad  ldloc.s  0x18
0x643af  ldloc.s  0x16
0x643b1  ldlen
0x643b2  conv.i4
0x643b3  blt      loc_6425A
0x643b8  ldloc.s  0x17
0x643ba  brfalse  loc_64D8A
0x643bf  ldarg.0
0x643c0  ldarg.1
0x643c1  ldloc.s  0x15
0x643c3  ldloc.s  0x16
0x643c5  ldarg.2
0x643c6  ldarg.2
0x643c7  ldnull
0x643c8  cgt.un
0x643ca  callvirt instance object System.ComponentModel.Design.Serialization.CodeDomSerializerBase::DeserializeInstance(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, class [mscorlib]System.Type type, object[] parameters, string name, bool addToContainer)
0x643cf  stloc.0
0x643d0  leave    loc_64D96
0x643d5  ldarg.1
0x643d6  ldstr    aSerializertype// "SerializerTypeNotFound"
0x643db  ldc.i4.1
0x643dc  newarr   [mscorlib]System.Object
0x643e1  dup
0x643e2  ldc.i4.0
0x643e3  ldloc.s  5
0x643e5  callvirt instance class [System]System.CodeDom.CodeTypeReference [System]System.CodeDom.CodeObjectCreateExpression::get_CreateType()
0x643ea  callvirt instance string [System]System.CodeDom.CodeTypeReference::get_BaseType()
0x643ef  stelem.ref
0x643f0  call     string System.Design.SR::GetString(string name, object[] args)
0x643f5  ldstr    aSerializertype// "SerializerTypeNotFound"
0x643fa  call     void System.ComponentModel.Design.Serialization.CodeDomSerializerBase::Error(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, string exceptionText, string helpLink)
0x643ff  leave    loc_64D96
0x64404  ldloc.0
0x64405  isinst   [System]System.CodeDom.CodeArgumentReferenceExpression
0x6440a  dup
0x6440b  stloc.s  6
0x6440d  brfalse.s loc_6444D
0x6440f  ldarg.1
0x64410  ldloc.s  6
0x64412  callvirt instance string [System]System.CodeDom.CodeArgumentReferenceExpression::get_ParameterName()
0x64417  callvirt instance object [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::GetInstance(string)
0x6441c  stloc.0
0x6441d  ldloc.0
0x6441e  brtrue   loc_64D8A
0x64423  ldarg.1
0x64424  ldstr    aSerializerunde// "SerializerUndeclaredName"
0x64429  ldc.i4.1
0x6442a  newarr   [mscorlib]System.Object
0x6442f  dup
0x64430  ldc.i4.0
0x64431  ldloc.s  6
0x64433  callvirt instance string [System]System.CodeDom.CodeArgumentReferenceExpression::get_ParameterName()
0x64438  stelem.ref
0x64439  call     string System.Design.SR::GetString(string name, object[] args)
0x6443e  ldstr    aSerializerunde// "SerializerUndeclaredName"
0x64443  call     void System.ComponentModel.Design.Serialization.CodeDomSerializerBase::Error(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, string exceptionText, string helpLink)
0x64448  leave    loc_64D96
0x6444d  ldloc.0
0x6444e  isinst   [System]System.CodeDom.CodeFieldReferenceExpression
0x64453  dup
0x64454  stloc.s  7
0x64456  brfalse  loc_645E4
0x6445b  ldarg.0
0x6445c  ldarg.1
0x6445d  ldnull
0x6445e  ldloc.s  7
0x64460  callvirt instance class [System]System.CodeDom.CodeExpression [System]System.CodeDom.CodeFieldReferenceExpression::get_TargetObject()
0x64465  call     instance object System.ComponentModel.Design.Serialization.CodeDomSerializerBase::DeserializeExpression(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, string name, class [System]System.CodeDom.CodeExpression expression)
  ... truncated ...
```
