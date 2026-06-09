# System.Xml.Xsl.Qil.QilVisitor::Visit

- ea: `0x3a690`
- end: `0x3adbb`
- name: `System.Xml.Xsl.Qil.QilVisitor::Visit`
- size: `1835`
- prototype: ``
- caller_count: `41`
- callee_count: `110`
- tags: `registry_config`

## callers

- `0x35a40`
- `0x385a0`
- `0x38d30`
- `0x39020`
- `0x3a5e0`
- `0x3a600`
- `0x3c850`
- `0x42af0`
- `0x49750`
- `0x4a930`
- `0x4af60`
- `0x4aff0`
- `0x4b030`
- `0x4b190`
- `0x4b1a0`
- `0x4b4e0`
- `0x4bbe0`
- `0x4c350`
- `0x4c770`
- `0x4cb70`
- `0x4cbb0`
- `0x4cc30`
- `0x4d270`
- `0x4d740`
- `0x4d8a0`
- `0x4d910`
- `0x4e720`
- `0x4eb20`
- `0x4ece0`
- `0x4ee70`
- `0x505b0`
- `0x50670`
- `0x50740`
- `0x50780`
- `0x55f50`
- `0x55f70`
- `0x55fb0`
- `0x57690`
- `0x576a0`
- `0x578f0`
- `0x57a90`

## callees

- `0x376a0`
- `0x3a690`
- `0x3ae30`
- `0x3ae40`
- `0x3ae50`
- `0x3ae60`
- `0x3ae70`
- `0x3ae80`
- `0x3ae90`
- `0x3aea0`
- `0x3aeb0`
- `0x3aec0`
- `0x3aed0`
- `0x3aee0`
- `0x3aef0`
- `0x3af00`
- `0x3af10`
- `0x3af20`
- `0x3af40`
- `0x3af60`
- `0x3af80`
- `0x3af90`
- `0x3afa0`
- `0x3afb0`
- `0x3afc0`
- `0x3afd0`
- `0x3afe0`
- `0x3aff0`
- `0x3b000`
- `0x3b010`
- `0x3b020`
- `0x3b030`
- `0x3b040`
- `0x3b050`
- `0x3b060`
- `0x3b070`
- `0x3b080`
- `0x3b090`
- `0x3b0a0`
- `0x3b0b0`
- `0x3b0c0`
- `0x3b0d0`
- `0x3b0e0`
- `0x3b0f0`
- `0x3b100`
- `0x3b110`
- `0x3b120`
- `0x3b130`
- `0x3b140`
- `0x3b150`

## pseudocode

```c

```

## disassembly

```asm
0x3a690  ldarg.1
0x3a691  brtrue.s loc_3A69A
0x3a693  ldarg.0
0x3a694  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNull()
0x3a699  ret
0x3a69a  ldarg.1
0x3a69b  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x3a6a0  stloc.0
0x3a6a1  ldloc.0
0x3a6a2  switch   loc_3A858, loc_3A865, loc_3A872, loc_3A87F, loc_3A88C, loc_3A899, loc_3A8A6, loc_3A8B3, loc_3A8C0, loc_3A8CD, loc_3A8D5, loc_3A8E2, loc_3A8EF, loc_3A8FC, loc_3A909, loc_3A916, loc_3A923, loc_3A930, loc_3A93D, loc_3A945, loc_3A94D, loc_3A95A, loc_3A967, loc_3A974, loc_3A981, loc_3A98E, loc_3A99B, loc_3A9A8, loc_3A9B5, loc_3A9C2, loc_3A9CF, loc_3A9DC, loc_3A9E9, loc_3A9F6, loc_3AA03, loc_3AA10, loc_3AA1D, loc_3AA2A, loc_3AA37, loc_3AA44, loc_3AA51, loc_3AA5E, loc_3AA6B, loc_3AA78, loc_3AA85, loc_3AA92, loc_3AA9F, loc_3AAAC, loc_3AAB9, loc_3AAC6, loc_3AAD3, loc_3AAE0, loc_3AAED, loc_3AAFA, loc_3AB07 \
0x3a853  br       loc_3ADB3
0x3a858  ldarg.0
0x3a859  ldarg.1
0x3a85a  castclass System.Xml.Xsl.Qil.QilExpression
0x3a85f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitQilExpression(class System.Xml.Xsl.Qil.QilExpression n)
0x3a864  ret
0x3a865  ldarg.0
0x3a866  ldarg.1
0x3a867  castclass System.Xml.Xsl.Qil.QilList
0x3a86c  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitFunctionList(class System.Xml.Xsl.Qil.QilList n)
0x3a871  ret
0x3a872  ldarg.0
0x3a873  ldarg.1
0x3a874  castclass System.Xml.Xsl.Qil.QilList
0x3a879  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitGlobalVariableList(class System.Xml.Xsl.Qil.QilList n)
0x3a87e  ret
0x3a87f  ldarg.0
0x3a880  ldarg.1
0x3a881  castclass System.Xml.Xsl.Qil.QilList
0x3a886  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitGlobalParameterList(class System.Xml.Xsl.Qil.QilList n)
0x3a88b  ret
0x3a88c  ldarg.0
0x3a88d  ldarg.1
0x3a88e  castclass System.Xml.Xsl.Qil.QilList
0x3a893  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitActualParameterList(class System.Xml.Xsl.Qil.QilList n)
0x3a898  ret
0x3a899  ldarg.0
0x3a89a  ldarg.1
0x3a89b  castclass System.Xml.Xsl.Qil.QilList
0x3a8a0  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitFormalParameterList(class System.Xml.Xsl.Qil.QilList n)
0x3a8a5  ret
0x3a8a6  ldarg.0
0x3a8a7  ldarg.1
0x3a8a8  castclass System.Xml.Xsl.Qil.QilList
0x3a8ad  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitSortKeyList(class System.Xml.Xsl.Qil.QilList n)
0x3a8b2  ret
0x3a8b3  ldarg.0
0x3a8b4  ldarg.1
0x3a8b5  castclass System.Xml.Xsl.Qil.QilList
0x3a8ba  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitBranchList(class System.Xml.Xsl.Qil.QilList n)
0x3a8bf  ret
0x3a8c0  ldarg.0
0x3a8c1  ldarg.1
0x3a8c2  castclass System.Xml.Xsl.Qil.QilUnary
0x3a8c7  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitOptimizeBarrier(class System.Xml.Xsl.Qil.QilUnary n)
0x3a8cc  ret
0x3a8cd  ldarg.0
0x3a8ce  ldarg.1
0x3a8cf  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitUnknown(class System.Xml.Xsl.Qil.QilNode n)
0x3a8d4  ret
0x3a8d5  ldarg.0
0x3a8d6  ldarg.1
0x3a8d7  castclass System.Xml.Xsl.Qil.QilDataSource
0x3a8dc  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitDataSource(class System.Xml.Xsl.Qil.QilDataSource n)
0x3a8e1  ret
0x3a8e2  ldarg.0
0x3a8e3  ldarg.1
0x3a8e4  castclass System.Xml.Xsl.Qil.QilUnary
0x3a8e9  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x3a8ee  ret
0x3a8ef  ldarg.0
0x3a8f0  ldarg.1
0x3a8f1  castclass System.Xml.Xsl.Qil.QilUnary
0x3a8f6  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitError(class System.Xml.Xsl.Qil.QilUnary n)
0x3a8fb  ret
0x3a8fc  ldarg.0
0x3a8fd  ldarg.1
0x3a8fe  castclass System.Xml.Xsl.Qil.QilUnary
0x3a903  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitWarning(class System.Xml.Xsl.Qil.QilUnary n)
0x3a908  ret
0x3a909  ldarg.0
0x3a90a  ldarg.1
0x3a90b  castclass System.Xml.Xsl.Qil.QilIterator
0x3a910  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitFor(class System.Xml.Xsl.Qil.QilIterator n)
0x3a915  ret
0x3a916  ldarg.0
0x3a917  ldarg.1
0x3a918  castclass System.Xml.Xsl.Qil.QilIterator
0x3a91d  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLet(class System.Xml.Xsl.Qil.QilIterator n)
0x3a922  ret
0x3a923  ldarg.0
0x3a924  ldarg.1
0x3a925  castclass System.Xml.Xsl.Qil.QilParameter
0x3a92a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitParameter(class System.Xml.Xsl.Qil.QilParameter n)
0x3a92f  ret
0x3a930  ldarg.0
0x3a931  ldarg.1
0x3a932  castclass System.Xml.Xsl.Qil.QilUnary
0x3a937  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitPositionOf(class System.Xml.Xsl.Qil.QilUnary n)
0x3a93c  ret
0x3a93d  ldarg.0
0x3a93e  ldarg.1
0x3a93f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitTrue(class System.Xml.Xsl.Qil.QilNode n)
0x3a944  ret
0x3a945  ldarg.0
0x3a946  ldarg.1
0x3a947  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitFalse(class System.Xml.Xsl.Qil.QilNode n)
0x3a94c  ret
0x3a94d  ldarg.0
0x3a94e  ldarg.1
0x3a94f  castclass System.Xml.Xsl.Qil.QilLiteral
0x3a954  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLiteralString(class System.Xml.Xsl.Qil.QilLiteral n)
0x3a959  ret
0x3a95a  ldarg.0
0x3a95b  ldarg.1
0x3a95c  castclass System.Xml.Xsl.Qil.QilLiteral
0x3a961  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLiteralInt32(class System.Xml.Xsl.Qil.QilLiteral n)
0x3a966  ret
0x3a967  ldarg.0
0x3a968  ldarg.1
0x3a969  castclass System.Xml.Xsl.Qil.QilLiteral
0x3a96e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLiteralInt64(class System.Xml.Xsl.Qil.QilLiteral n)
0x3a973  ret
0x3a974  ldarg.0
0x3a975  ldarg.1
0x3a976  castclass System.Xml.Xsl.Qil.QilLiteral
0x3a97b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLiteralDouble(class System.Xml.Xsl.Qil.QilLiteral n)
0x3a980  ret
0x3a981  ldarg.0
0x3a982  ldarg.1
0x3a983  castclass System.Xml.Xsl.Qil.QilLiteral
0x3a988  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLiteralDecimal(class System.Xml.Xsl.Qil.QilLiteral n)
0x3a98d  ret
0x3a98e  ldarg.0
0x3a98f  ldarg.1
0x3a990  castclass System.Xml.Xsl.Qil.QilName
0x3a995  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLiteralQName(class System.Xml.Xsl.Qil.QilName n)
0x3a99a  ret
0x3a99b  ldarg.0
0x3a99c  ldarg.1
0x3a99d  castclass System.Xml.Xsl.Qil.QilLiteral
0x3a9a2  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLiteralType(class System.Xml.Xsl.Qil.QilLiteral n)
0x3a9a7  ret
0x3a9a8  ldarg.0
0x3a9a9  ldarg.1
0x3a9aa  castclass System.Xml.Xsl.Qil.QilLiteral
0x3a9af  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLiteralObject(class System.Xml.Xsl.Qil.QilLiteral n)
0x3a9b4  ret
0x3a9b5  ldarg.0
0x3a9b6  ldarg.1
0x3a9b7  castclass System.Xml.Xsl.Qil.QilBinary
0x3a9bc  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitAnd(class System.Xml.Xsl.Qil.QilBinary n)
0x3a9c1  ret
0x3a9c2  ldarg.0
0x3a9c3  ldarg.1
0x3a9c4  castclass System.Xml.Xsl.Qil.QilBinary
0x3a9c9  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitOr(class System.Xml.Xsl.Qil.QilBinary n)
0x3a9ce  ret
0x3a9cf  ldarg.0
0x3a9d0  ldarg.1
0x3a9d1  castclass System.Xml.Xsl.Qil.QilUnary
0x3a9d6  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNot(class System.Xml.Xsl.Qil.QilUnary n)
0x3a9db  ret
0x3a9dc  ldarg.0
0x3a9dd  ldarg.1
0x3a9de  castclass System.Xml.Xsl.Qil.QilTernary
0x3a9e3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitConditional(class System.Xml.Xsl.Qil.QilTernary n)
0x3a9e8  ret
0x3a9e9  ldarg.0
0x3a9ea  ldarg.1
0x3a9eb  castclass System.Xml.Xsl.Qil.QilChoice
0x3a9f0  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitChoice(class System.Xml.Xsl.Qil.QilChoice n)
0x3a9f5  ret
0x3a9f6  ldarg.0
0x3a9f7  ldarg.1
0x3a9f8  castclass System.Xml.Xsl.Qil.QilUnary
0x3a9fd  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLength(class System.Xml.Xsl.Qil.QilUnary n)
0x3aa02  ret
0x3aa03  ldarg.0
0x3aa04  ldarg.1
0x3aa05  castclass System.Xml.Xsl.Qil.QilList
0x3aa0a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitSequence(class System.Xml.Xsl.Qil.QilList n)
0x3aa0f  ret
0x3aa10  ldarg.0
0x3aa11  ldarg.1
0x3aa12  castclass System.Xml.Xsl.Qil.QilBinary
0x3aa17  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitUnion(class System.Xml.Xsl.Qil.QilBinary n)
0x3aa1c  ret
0x3aa1d  ldarg.0
0x3aa1e  ldarg.1
0x3aa1f  castclass System.Xml.Xsl.Qil.QilBinary
0x3aa24  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitIntersection(class System.Xml.Xsl.Qil.QilBinary n)
0x3aa29  ret
0x3aa2a  ldarg.0
0x3aa2b  ldarg.1
0x3aa2c  castclass System.Xml.Xsl.Qil.QilBinary
0x3aa31  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitDifference(class System.Xml.Xsl.Qil.QilBinary n)
0x3aa36  ret
0x3aa37  ldarg.0
0x3aa38  ldarg.1
0x3aa39  castclass System.Xml.Xsl.Qil.QilUnary
0x3aa3e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitAverage(class System.Xml.Xsl.Qil.QilUnary n)
0x3aa43  ret
0x3aa44  ldarg.0
0x3aa45  ldarg.1
0x3aa46  castclass System.Xml.Xsl.Qil.QilUnary
0x3aa4b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitSum(class System.Xml.Xsl.Qil.QilUnary n)
0x3aa50  ret
0x3aa51  ldarg.0
0x3aa52  ldarg.1
0x3aa53  castclass System.Xml.Xsl.Qil.QilUnary
0x3aa58  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitMinimum(class System.Xml.Xsl.Qil.QilUnary n)
0x3aa5d  ret
0x3aa5e  ldarg.0
0x3aa5f  ldarg.1
0x3aa60  castclass System.Xml.Xsl.Qil.QilUnary
0x3aa65  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitMaximum(class System.Xml.Xsl.Qil.QilUnary n)
0x3aa6a  ret
0x3aa6b  ldarg.0
0x3aa6c  ldarg.1
0x3aa6d  castclass System.Xml.Xsl.Qil.QilUnary
0x3aa72  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNegate(class System.Xml.Xsl.Qil.QilUnary n)
0x3aa77  ret
0x3aa78  ldarg.0
0x3aa79  ldarg.1
0x3aa7a  castclass System.Xml.Xsl.Qil.QilBinary
0x3aa7f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitAdd(class System.Xml.Xsl.Qil.QilBinary n)
0x3aa84  ret
0x3aa85  ldarg.0
0x3aa86  ldarg.1
0x3aa87  castclass System.Xml.Xsl.Qil.QilBinary
0x3aa8c  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitSubtract(class System.Xml.Xsl.Qil.QilBinary n)
0x3aa91  ret
0x3aa92  ldarg.0
0x3aa93  ldarg.1
0x3aa94  castclass System.Xml.Xsl.Qil.QilBinary
0x3aa99  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitMultiply(class System.Xml.Xsl.Qil.QilBinary n)
0x3aa9e  ret
0x3aa9f  ldarg.0
0x3aaa0  ldarg.1
0x3aaa1  castclass System.Xml.Xsl.Qil.QilBinary
0x3aaa6  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitDivide(class System.Xml.Xsl.Qil.QilBinary n)
0x3aaab  ret
0x3aaac  ldarg.0
0x3aaad  ldarg.1
0x3aaae  castclass System.Xml.Xsl.Qil.QilBinary
0x3aab3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitModulo(class System.Xml.Xsl.Qil.QilBinary n)
0x3aab8  ret
0x3aab9  ldarg.0
0x3aaba  ldarg.1
0x3aabb  castclass System.Xml.Xsl.Qil.QilUnary
0x3aac0  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitStrLength(class System.Xml.Xsl.Qil.QilUnary n)
0x3aac5  ret
0x3aac6  ldarg.0
0x3aac7  ldarg.1
0x3aac8  castclass System.Xml.Xsl.Qil.QilStrConcat
0x3aacd  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitStrConcat(class System.Xml.Xsl.Qil.QilStrConcat n)
0x3aad2  ret
0x3aad3  ldarg.0
0x3aad4  ldarg.1
0x3aad5  castclass System.Xml.Xsl.Qil.QilBinary
0x3aada  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitStrParseQName(class System.Xml.Xsl.Qil.QilBinary n)
0x3aadf  ret
0x3aae0  ldarg.0
0x3aae1  ldarg.1
0x3aae2  castclass System.Xml.Xsl.Qil.QilBinary
0x3aae7  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNe(class System.Xml.Xsl.Qil.QilBinary n)
0x3aaec  ret
0x3aaed  ldarg.0
0x3aaee  ldarg.1
0x3aaef  castclass System.Xml.Xsl.Qil.QilBinary
0x3aaf4  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitEq(class System.Xml.Xsl.Qil.QilBinary n)
0x3aaf9  ret
0x3aafa  ldarg.0
0x3aafb  ldarg.1
0x3aafc  castclass System.Xml.Xsl.Qil.QilBinary
0x3ab01  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitGt(class System.Xml.Xsl.Qil.QilBinary n)
0x3ab06  ret
0x3ab07  ldarg.0
0x3ab08  ldarg.1
0x3ab09  castclass System.Xml.Xsl.Qil.QilBinary
0x3ab0e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitGe(class System.Xml.Xsl.Qil.QilBinary n)
0x3ab13  ret
0x3ab14  ldarg.0
0x3ab15  ldarg.1
0x3ab16  castclass System.Xml.Xsl.Qil.QilBinary
0x3ab1b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLt(class System.Xml.Xsl.Qil.QilBinary n)
0x3ab20  ret
0x3ab21  ldarg.0
0x3ab22  ldarg.1
0x3ab23  castclass System.Xml.Xsl.Qil.QilBinary
0x3ab28  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLe(class System.Xml.Xsl.Qil.QilBinary n)
0x3ab2d  ret
0x3ab2e  ldarg.0
0x3ab2f  ldarg.1
0x3ab30  castclass System.Xml.Xsl.Qil.QilBinary
0x3ab35  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitIs(class System.Xml.Xsl.Qil.QilBinary n)
0x3ab3a  ret
0x3ab3b  ldarg.0
0x3ab3c  ldarg.1
  ... truncated ...
```
