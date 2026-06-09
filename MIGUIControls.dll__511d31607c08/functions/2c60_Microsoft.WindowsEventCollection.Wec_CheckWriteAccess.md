# Microsoft.WindowsEventCollection.Wec::CheckWriteAccess

- ea: `0x2c60`
- end: `0x2d49`
- name: `Microsoft.WindowsEventCollection.Wec::CheckWriteAccess`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x890`
- `0xa30`
- `0xad0`
- `0xde0`
- `0x29e0`
- `0x2b00`
- `0x2b60`
- `0x2c60`

## string_xrefs

- `0x2c6f`: `WecTestWriteAccess-{0}`
- `0x2cdc`: `<QueryList><Query Id ='0' Path='Application'> <Select Path='Application'>*[System[Provider[@Name='TempProvider'] and (Level=1)]]</Select> </Query></QueryList>`

## pseudocode

```c

```

## disassembly

```asm
0x2c60  ldarg.0
0x2c61  ldfld    bool Microsoft.WindowsEventCollection.Wec::_writeAccessCheckDone
0x2c66  brfalse.s loc_2C6F
0x2c68  ldarg.0
0x2c69  ldfld    bool Microsoft.WindowsEventCollection.Wec::_checkWriteAccess
0x2c6e  ret
0x2c6f  ldstr    aWectestwriteac// "WecTestWriteAccess-{0}"
0x2c74  stloc.1
0x2c75  ldarg.0
0x2c76  call     instance string[] Microsoft.WindowsEventCollection.Wec::GetSubscriptionNames()
0x2c7b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x2c80  stloc.2
0x2c81  ldc.i4.0
0x2c82  stloc.3
0x2c83  ldc.i4   0x3E8
0x2c88  stloc.s  4
0x2c8a  ldnull
0x2c8b  ldloc.1
0x2c8c  ldc.i4.1
0x2c8d  newarr   [mscorlib]System.Object
0x2c92  dup
0x2c93  ldc.i4.0
0x2c94  ldloc.3
0x2c95  dup
0x2c96  ldc.i4.1
0x2c97  add
0x2c98  stloc.3
0x2c99  box      [mscorlib]System.Int32
0x2c9e  stelem.ref
0x2c9f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2ca4  stloc.0
0x2ca5  ldloc.2
0x2ca6  ldloc.0
0x2ca7  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x2cac  brfalse.s loc_2CB3
0x2cae  ldloc.3
0x2caf  ldloc.s  4
0x2cb1  blt.s    loc_2C8A
0x2cb3  ldloc.3
0x2cb4  ldloc.s  4
0x2cb6  blt.s    loc_2CC1
0x2cb8  ldarg.0
0x2cb9  ldc.i4.1
0x2cba  stfld    bool Microsoft.WindowsEventCollection.Wec::_writeAccessCheckDone
0x2cbf  ldc.i4.0
0x2cc0  ret
0x2cc1  nop
0x2cc2  ldloc.0
0x2cc3  newobj   instance void Microsoft.WindowsEventCollection.Subscription::.ctor(string subscriptionName)
0x2cc8  stloc.s  5
0x2cca  ldloc.s  5
0x2ccc  ldc.i4.0
0x2ccd  callvirt instance void Microsoft.WindowsEventCollection.Subscription::set_SetCredentials(bool value)
0x2cd2  ldloc.s  5
0x2cd4  ldc.i4.0
0x2cd5  callvirt instance void Microsoft.WindowsEventCollection.Subscription::set_Enabled(bool value)
0x2cda  ldloc.s  5
0x2cdc  ldstr    aQuerylistQuery_0// "<QueryList><Query Id ='0' Path='Applica"...
0x2ce1  callvirt instance void Microsoft.WindowsEventCollection.Subscription::set_Query(string value)
0x2ce6  ldarg.0
0x2ce7  ldloc.s  5
0x2ce9  call     instance void Microsoft.WindowsEventCollection.Wec::CreateSubscription(class Microsoft.WindowsEventCollection.Subscription subscription)
0x2cee  leave.s  loc_2D1F
0x2cf0  stloc.s  6
0x2cf2  ldloc.s  6
0x2cf4  callvirt instance int32 [System]System.ComponentModel.Win32Exception::get_NativeErrorCode()
0x2cf9  ldc.i4.5
0x2cfa  bne.un.s loc_2D08
0x2cfc  ldarg.0
0x2cfd  ldc.i4.1
0x2cfe  stfld    bool Microsoft.WindowsEventCollection.Wec::_writeAccessCheckDone
0x2d03  ldc.i4.0
0x2d04  stloc.s  7
0x2d06  leave.s  loc_2D46
0x2d08  ldloc.s  6
0x2d0a  throw
0x2d0b  pop
0x2d0c  ldarg.0
0x2d0d  ldc.i4.1
0x2d0e  stfld    bool Microsoft.WindowsEventCollection.Wec::_writeAccessCheckDone
0x2d13  ldarg.0
0x2d14  ldc.i4.0
0x2d15  stfld    bool Microsoft.WindowsEventCollection.Wec::_checkWriteAccess
0x2d1a  ldc.i4.0
0x2d1b  stloc.s  7
0x2d1d  leave.s  loc_2D46
0x2d1f  nop
0x2d20  ldarg.0
0x2d21  ldloc.0
0x2d22  call     instance void Microsoft.WindowsEventCollection.Wec::DeleteSubscription(string subscriptionName)
0x2d27  leave.s  loc_2D36
0x2d29  pop
0x2d2a  ldarg.0
0x2d2b  ldc.i4.1
0x2d2c  stfld    bool Microsoft.WindowsEventCollection.Wec::_writeAccessCheckDone
0x2d31  ldc.i4.0
0x2d32  stloc.s  7
0x2d34  leave.s  loc_2D46
0x2d36  ldarg.0
0x2d37  ldc.i4.1
0x2d38  stfld    bool Microsoft.WindowsEventCollection.Wec::_checkWriteAccess
0x2d3d  ldarg.0
0x2d3e  ldc.i4.1
0x2d3f  stfld    bool Microsoft.WindowsEventCollection.Wec::_writeAccessCheckDone
0x2d44  ldc.i4.1
0x2d45  ret
0x2d46  ldloc.s  7
0x2d48  ret
```
