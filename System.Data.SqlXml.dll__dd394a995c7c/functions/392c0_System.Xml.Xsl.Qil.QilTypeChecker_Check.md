# System.Xml.Xsl.Qil.QilTypeChecker::Check

- ea: `0x392c0`
- end: `0x399e1`
- name: `System.Xml.Xsl.Qil.QilTypeChecker::Check`
- size: `1825`
- prototype: ``
- caller_count: `1`
- callee_count: `109`
- tags: `registry_config`

## callers

- `0x38db0`

## callees

- `0x376a0`
- `0x392c0`
- `0x399f0`
- `0x39a00`
- `0x39a30`
- `0x39a60`
- `0x39a90`
- `0x39aa0`
- `0x39ad0`
- `0x39b00`
- `0x39b10`
- `0x39b20`
- `0x39b30`
- `0x39b40`
- `0x39b50`
- `0x39b60`
- `0x39b70`
- `0x39b90`
- `0x39ba0`
- `0x39bb0`
- `0x39bc0`
- `0x39bd0`
- `0x39be0`
- `0x39bf0`
- `0x39c00`
- `0x39c10`
- `0x39c20`
- `0x39c30`
- `0x39c40`
- `0x39c50`
- `0x39c60`
- `0x39c70`
- `0x39c80`
- `0x39c90`
- `0x39cb0`
- `0x39cc0`
- `0x39cd0`
- `0x39ce0`
- `0x39d10`
- `0x39d20`
- `0x39d50`
- `0x39d80`
- `0x39d90`
- `0x39da0`
- `0x39db0`
- `0x39dc0`
- `0x39df0`
- `0x39e00`
- `0x39e10`
- `0x39e20`

## pseudocode

```c

```

## disassembly

```asm
0x392c0  ldarg.1
0x392c1  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x392c6  stloc.0
0x392c7  ldloc.0
0x392c8  switch   loc_3947E, loc_3948B, loc_39498, loc_394A5, loc_394B2, loc_394BF, loc_394CC, loc_394D9, loc_394E6, loc_394F3, loc_394FB, loc_39508, loc_39515, loc_39522, loc_3952F, loc_3953C, loc_39549, loc_39556, loc_39563, loc_3956B, loc_39573, loc_39580, loc_3958D, loc_3959A, loc_395A7, loc_395B4, loc_395C1, loc_395CE, loc_395DB, loc_395E8, loc_395F5, loc_39602, loc_3960F, loc_3961C, loc_39629, loc_39636, loc_39643, loc_39650, loc_3965D, loc_3966A, loc_39677, loc_39684, loc_39691, loc_3969E, loc_396AB, loc_396B8, loc_396C5, loc_396D2, loc_396DF, loc_396EC, loc_396F9, loc_39706, loc_39713, loc_39720, loc_3972D \
0x39479  br       loc_399D9
0x3947e  ldarg.0
0x3947f  ldarg.1
0x39480  castclass System.Xml.Xsl.Qil.QilExpression
0x39485  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckQilExpression(class System.Xml.Xsl.Qil.QilExpression node)
0x3948a  ret
0x3948b  ldarg.0
0x3948c  ldarg.1
0x3948d  castclass System.Xml.Xsl.Qil.QilList
0x39492  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckFunctionList(class System.Xml.Xsl.Qil.QilList node)
0x39497  ret
0x39498  ldarg.0
0x39499  ldarg.1
0x3949a  castclass System.Xml.Xsl.Qil.QilList
0x3949f  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckGlobalVariableList(class System.Xml.Xsl.Qil.QilList node)
0x394a4  ret
0x394a5  ldarg.0
0x394a6  ldarg.1
0x394a7  castclass System.Xml.Xsl.Qil.QilList
0x394ac  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckGlobalParameterList(class System.Xml.Xsl.Qil.QilList node)
0x394b1  ret
0x394b2  ldarg.0
0x394b3  ldarg.1
0x394b4  castclass System.Xml.Xsl.Qil.QilList
0x394b9  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckActualParameterList(class System.Xml.Xsl.Qil.QilList node)
0x394be  ret
0x394bf  ldarg.0
0x394c0  ldarg.1
0x394c1  castclass System.Xml.Xsl.Qil.QilList
0x394c6  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckFormalParameterList(class System.Xml.Xsl.Qil.QilList node)
0x394cb  ret
0x394cc  ldarg.0
0x394cd  ldarg.1
0x394ce  castclass System.Xml.Xsl.Qil.QilList
0x394d3  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckSortKeyList(class System.Xml.Xsl.Qil.QilList node)
0x394d8  ret
0x394d9  ldarg.0
0x394da  ldarg.1
0x394db  castclass System.Xml.Xsl.Qil.QilList
0x394e0  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckBranchList(class System.Xml.Xsl.Qil.QilList node)
0x394e5  ret
0x394e6  ldarg.0
0x394e7  ldarg.1
0x394e8  castclass System.Xml.Xsl.Qil.QilUnary
0x394ed  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckOptimizeBarrier(class System.Xml.Xsl.Qil.QilUnary node)
0x394f2  ret
0x394f3  ldarg.0
0x394f4  ldarg.1
0x394f5  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckUnknown(class System.Xml.Xsl.Qil.QilNode node)
0x394fa  ret
0x394fb  ldarg.0
0x394fc  ldarg.1
0x394fd  castclass System.Xml.Xsl.Qil.QilDataSource
0x39502  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckDataSource(class System.Xml.Xsl.Qil.QilDataSource node)
0x39507  ret
0x39508  ldarg.0
0x39509  ldarg.1
0x3950a  castclass System.Xml.Xsl.Qil.QilUnary
0x3950f  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckNop(class System.Xml.Xsl.Qil.QilUnary node)
0x39514  ret
0x39515  ldarg.0
0x39516  ldarg.1
0x39517  castclass System.Xml.Xsl.Qil.QilUnary
0x3951c  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckError(class System.Xml.Xsl.Qil.QilUnary node)
0x39521  ret
0x39522  ldarg.0
0x39523  ldarg.1
0x39524  castclass System.Xml.Xsl.Qil.QilUnary
0x39529  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckWarning(class System.Xml.Xsl.Qil.QilUnary node)
0x3952e  ret
0x3952f  ldarg.0
0x39530  ldarg.1
0x39531  castclass System.Xml.Xsl.Qil.QilIterator
0x39536  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckFor(class System.Xml.Xsl.Qil.QilIterator node)
0x3953b  ret
0x3953c  ldarg.0
0x3953d  ldarg.1
0x3953e  castclass System.Xml.Xsl.Qil.QilIterator
0x39543  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckLet(class System.Xml.Xsl.Qil.QilIterator node)
0x39548  ret
0x39549  ldarg.0
0x3954a  ldarg.1
0x3954b  castclass System.Xml.Xsl.Qil.QilParameter
0x39550  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckParameter(class System.Xml.Xsl.Qil.QilParameter node)
0x39555  ret
0x39556  ldarg.0
0x39557  ldarg.1
0x39558  castclass System.Xml.Xsl.Qil.QilUnary
0x3955d  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckPositionOf(class System.Xml.Xsl.Qil.QilUnary node)
0x39562  ret
0x39563  ldarg.0
0x39564  ldarg.1
0x39565  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckTrue(class System.Xml.Xsl.Qil.QilNode node)
0x3956a  ret
0x3956b  ldarg.0
0x3956c  ldarg.1
0x3956d  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckFalse(class System.Xml.Xsl.Qil.QilNode node)
0x39572  ret
0x39573  ldarg.0
0x39574  ldarg.1
0x39575  castclass System.Xml.Xsl.Qil.QilLiteral
0x3957a  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckLiteralString(class System.Xml.Xsl.Qil.QilLiteral node)
0x3957f  ret
0x39580  ldarg.0
0x39581  ldarg.1
0x39582  castclass System.Xml.Xsl.Qil.QilLiteral
0x39587  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckLiteralInt32(class System.Xml.Xsl.Qil.QilLiteral node)
0x3958c  ret
0x3958d  ldarg.0
0x3958e  ldarg.1
0x3958f  castclass System.Xml.Xsl.Qil.QilLiteral
0x39594  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckLiteralInt64(class System.Xml.Xsl.Qil.QilLiteral node)
0x39599  ret
0x3959a  ldarg.0
0x3959b  ldarg.1
0x3959c  castclass System.Xml.Xsl.Qil.QilLiteral
0x395a1  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckLiteralDouble(class System.Xml.Xsl.Qil.QilLiteral node)
0x395a6  ret
0x395a7  ldarg.0
0x395a8  ldarg.1
0x395a9  castclass System.Xml.Xsl.Qil.QilLiteral
0x395ae  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckLiteralDecimal(class System.Xml.Xsl.Qil.QilLiteral node)
0x395b3  ret
0x395b4  ldarg.0
0x395b5  ldarg.1
0x395b6  castclass System.Xml.Xsl.Qil.QilName
0x395bb  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckLiteralQName(class System.Xml.Xsl.Qil.QilName node)
0x395c0  ret
0x395c1  ldarg.0
0x395c2  ldarg.1
0x395c3  castclass System.Xml.Xsl.Qil.QilLiteral
0x395c8  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckLiteralType(class System.Xml.Xsl.Qil.QilLiteral node)
0x395cd  ret
0x395ce  ldarg.0
0x395cf  ldarg.1
0x395d0  castclass System.Xml.Xsl.Qil.QilLiteral
0x395d5  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckLiteralObject(class System.Xml.Xsl.Qil.QilLiteral node)
0x395da  ret
0x395db  ldarg.0
0x395dc  ldarg.1
0x395dd  castclass System.Xml.Xsl.Qil.QilBinary
0x395e2  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckAnd(class System.Xml.Xsl.Qil.QilBinary node)
0x395e7  ret
0x395e8  ldarg.0
0x395e9  ldarg.1
0x395ea  castclass System.Xml.Xsl.Qil.QilBinary
0x395ef  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckOr(class System.Xml.Xsl.Qil.QilBinary node)
0x395f4  ret
0x395f5  ldarg.0
0x395f6  ldarg.1
0x395f7  castclass System.Xml.Xsl.Qil.QilUnary
0x395fc  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckNot(class System.Xml.Xsl.Qil.QilUnary node)
0x39601  ret
0x39602  ldarg.0
0x39603  ldarg.1
0x39604  castclass System.Xml.Xsl.Qil.QilTernary
0x39609  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckConditional(class System.Xml.Xsl.Qil.QilTernary node)
0x3960e  ret
0x3960f  ldarg.0
0x39610  ldarg.1
0x39611  castclass System.Xml.Xsl.Qil.QilChoice
0x39616  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckChoice(class System.Xml.Xsl.Qil.QilChoice node)
0x3961b  ret
0x3961c  ldarg.0
0x3961d  ldarg.1
0x3961e  castclass System.Xml.Xsl.Qil.QilUnary
0x39623  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckLength(class System.Xml.Xsl.Qil.QilUnary node)
0x39628  ret
0x39629  ldarg.0
0x3962a  ldarg.1
0x3962b  castclass System.Xml.Xsl.Qil.QilList
0x39630  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckSequence(class System.Xml.Xsl.Qil.QilList node)
0x39635  ret
0x39636  ldarg.0
0x39637  ldarg.1
0x39638  castclass System.Xml.Xsl.Qil.QilBinary
0x3963d  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckUnion(class System.Xml.Xsl.Qil.QilBinary node)
0x39642  ret
0x39643  ldarg.0
0x39644  ldarg.1
0x39645  castclass System.Xml.Xsl.Qil.QilBinary
0x3964a  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckIntersection(class System.Xml.Xsl.Qil.QilBinary node)
0x3964f  ret
0x39650  ldarg.0
0x39651  ldarg.1
0x39652  castclass System.Xml.Xsl.Qil.QilBinary
0x39657  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckDifference(class System.Xml.Xsl.Qil.QilBinary node)
0x3965c  ret
0x3965d  ldarg.0
0x3965e  ldarg.1
0x3965f  castclass System.Xml.Xsl.Qil.QilUnary
0x39664  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckAverage(class System.Xml.Xsl.Qil.QilUnary node)
0x39669  ret
0x3966a  ldarg.0
0x3966b  ldarg.1
0x3966c  castclass System.Xml.Xsl.Qil.QilUnary
0x39671  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckSum(class System.Xml.Xsl.Qil.QilUnary node)
0x39676  ret
0x39677  ldarg.0
0x39678  ldarg.1
0x39679  castclass System.Xml.Xsl.Qil.QilUnary
0x3967e  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckMinimum(class System.Xml.Xsl.Qil.QilUnary node)
0x39683  ret
0x39684  ldarg.0
0x39685  ldarg.1
0x39686  castclass System.Xml.Xsl.Qil.QilUnary
0x3968b  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckMaximum(class System.Xml.Xsl.Qil.QilUnary node)
0x39690  ret
0x39691  ldarg.0
0x39692  ldarg.1
0x39693  castclass System.Xml.Xsl.Qil.QilUnary
0x39698  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckNegate(class System.Xml.Xsl.Qil.QilUnary node)
0x3969d  ret
0x3969e  ldarg.0
0x3969f  ldarg.1
0x396a0  castclass System.Xml.Xsl.Qil.QilBinary
0x396a5  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckAdd(class System.Xml.Xsl.Qil.QilBinary node)
0x396aa  ret
0x396ab  ldarg.0
0x396ac  ldarg.1
0x396ad  castclass System.Xml.Xsl.Qil.QilBinary
0x396b2  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckSubtract(class System.Xml.Xsl.Qil.QilBinary node)
0x396b7  ret
0x396b8  ldarg.0
0x396b9  ldarg.1
0x396ba  castclass System.Xml.Xsl.Qil.QilBinary
0x396bf  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckMultiply(class System.Xml.Xsl.Qil.QilBinary node)
0x396c4  ret
0x396c5  ldarg.0
0x396c6  ldarg.1
0x396c7  castclass System.Xml.Xsl.Qil.QilBinary
0x396cc  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckDivide(class System.Xml.Xsl.Qil.QilBinary node)
0x396d1  ret
0x396d2  ldarg.0
0x396d3  ldarg.1
0x396d4  castclass System.Xml.Xsl.Qil.QilBinary
0x396d9  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckModulo(class System.Xml.Xsl.Qil.QilBinary node)
0x396de  ret
0x396df  ldarg.0
0x396e0  ldarg.1
0x396e1  castclass System.Xml.Xsl.Qil.QilUnary
0x396e6  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckStrLength(class System.Xml.Xsl.Qil.QilUnary node)
0x396eb  ret
0x396ec  ldarg.0
0x396ed  ldarg.1
0x396ee  castclass System.Xml.Xsl.Qil.QilStrConcat
0x396f3  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckStrConcat(class System.Xml.Xsl.Qil.QilStrConcat node)
0x396f8  ret
0x396f9  ldarg.0
0x396fa  ldarg.1
0x396fb  castclass System.Xml.Xsl.Qil.QilBinary
0x39700  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckStrParseQName(class System.Xml.Xsl.Qil.QilBinary node)
0x39705  ret
0x39706  ldarg.0
0x39707  ldarg.1
0x39708  castclass System.Xml.Xsl.Qil.QilBinary
0x3970d  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckNe(class System.Xml.Xsl.Qil.QilBinary node)
0x39712  ret
0x39713  ldarg.0
0x39714  ldarg.1
0x39715  castclass System.Xml.Xsl.Qil.QilBinary
0x3971a  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckEq(class System.Xml.Xsl.Qil.QilBinary node)
0x3971f  ret
0x39720  ldarg.0
0x39721  ldarg.1
0x39722  castclass System.Xml.Xsl.Qil.QilBinary
0x39727  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckGt(class System.Xml.Xsl.Qil.QilBinary node)
0x3972c  ret
0x3972d  ldarg.0
0x3972e  ldarg.1
0x3972f  castclass System.Xml.Xsl.Qil.QilBinary
0x39734  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckGe(class System.Xml.Xsl.Qil.QilBinary node)
0x39739  ret
0x3973a  ldarg.0
0x3973b  ldarg.1
0x3973c  castclass System.Xml.Xsl.Qil.QilBinary
0x39741  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckLt(class System.Xml.Xsl.Qil.QilBinary node)
0x39746  ret
0x39747  ldarg.0
0x39748  ldarg.1
0x39749  castclass System.Xml.Xsl.Qil.QilBinary
0x3974e  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckLe(class System.Xml.Xsl.Qil.QilBinary node)
0x39753  ret
0x39754  ldarg.0
0x39755  ldarg.1
0x39756  castclass System.Xml.Xsl.Qil.QilBinary
0x3975b  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckIs(class System.Xml.Xsl.Qil.QilBinary node)
0x39760  ret
0x39761  ldarg.0
0x39762  ldarg.1
0x39763  castclass System.Xml.Xsl.Qil.QilBinary
0x39768  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckAfter(class System.Xml.Xsl.Qil.QilBinary node)
0x3976d  ret
0x3976e  ldarg.0
0x3976f  ldarg.1
  ... truncated ...
```
