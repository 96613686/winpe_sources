# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::ResolveTypeCode

- ea: `0x3ac0`
- end: `0x3b18`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::ResolveTypeCode`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x39d0`

## callees

- `0x3ac0`
- `0x3b20`
- `0x3ba0`

## pseudocode

```c

```

## disassembly

```asm
0x3ac0  ldarg.0
0x3ac1  ldarg.1
0x3ac2  bne.un.s loc_3AC6
0x3ac4  ldarg.0
0x3ac5  ret
0x3ac6  ldarg.0
0x3ac7  ldc.i4.1
0x3ac8  beq.s    loc_3ACE
0x3aca  ldarg.1
0x3acb  ldc.i4.1
0x3acc  bne.un.s loc_3AD0
0x3ace  ldc.i4.1
0x3acf  ret
0x3ad0  ldarg.0
0x3ad1  ldc.i4.s 0x12
0x3ad3  beq.s    loc_3AF4
0x3ad5  ldarg.1
0x3ad6  ldc.i4.s 0x12
0x3ad8  beq.s    loc_3AF4
0x3ada  ldarg.0
0x3adb  ldc.i4.s 0x10
0x3add  beq.s    loc_3AF4
0x3adf  ldarg.1
0x3ae0  ldc.i4.s 0x10
0x3ae2  beq.s    loc_3AF4
0x3ae4  ldarg.0
0x3ae5  ldc.i4.3
0x3ae6  beq.s    loc_3AF4
0x3ae8  ldarg.1
0x3ae9  ldc.i4.3
0x3aea  beq.s    loc_3AF4
0x3aec  ldarg.0
0x3aed  ldc.i4.4
0x3aee  beq.s    loc_3AF4
0x3af0  ldarg.1
0x3af1  ldc.i4.4
0x3af2  bne.un.s loc_3AF7
0x3af4  ldc.i4.s 0x12
0x3af6  ret
0x3af7  ldarg.0
0x3af8  call     valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.DataAggregate/DataTypeCode Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::ConvertToDataTypeCode(valuetype [mscorlib]System.TypeCode typeCode)
0x3afd  ldarg.1
0x3afe  call     valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.DataAggregate/DataTypeCode Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::ConvertToDataTypeCode(valuetype [mscorlib]System.TypeCode typeCode)
0x3b03  stloc.0
0x3b04  ldloc.0
0x3b05  call     valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.DataAggregate/DataTypeCode [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.DataTypeUtility::CommonNumericDenominator(valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.DataAggregate/DataTypeCode, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.DataAggregate/DataTypeCode)
0x3b0a  stloc.1
0x3b0b  ldloc.1
0x3b0c  brtrue.s loc_3B11
0x3b0e  ldc.i4.s 0x12
0x3b10  ret
0x3b11  ldloc.1
0x3b12  call     valuetype [mscorlib]System.TypeCode Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::ConvertToTypeCode(valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.DataAggregate/DataTypeCode dataTypeCode)
0x3b17  ret
```
