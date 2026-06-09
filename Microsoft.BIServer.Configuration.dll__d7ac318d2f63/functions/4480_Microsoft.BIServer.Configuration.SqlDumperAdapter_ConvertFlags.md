# Microsoft.BIServer.Configuration.SqlDumperAdapter::ConvertFlags

- ea: `0x4480`
- end: `0x4704`
- name: `Microsoft.BIServer.Configuration.SqlDumperAdapter::ConvertFlags`
- size: `644`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x43b0`

## callees

- `0x4480`

## pseudocode

```c

```

## disassembly

```asm
0x4480  ldc.i4.0
0x4481  stloc.0
0x4482  ldarg.0
0x4483  box      Microsoft.BIServer.Configuration.DumperFlags
0x4488  ldc.i4.s 0x10
0x448a  box      Microsoft.BIServer.Configuration.DumperFlags
0x448f  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x4494  brfalse.s loc_449B
0x4496  ldloc.0
0x4497  ldc.i4.s 0x10
0x4499  or
0x449a  stloc.0
0x449b  ldarg.0
0x449c  box      Microsoft.BIServer.Configuration.DumperFlags
0x44a1  ldc.i4.s 0x20
0x44a3  box      Microsoft.BIServer.Configuration.DumperFlags
0x44a8  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x44ad  brfalse.s loc_44B4
0x44af  ldloc.0
0x44b0  ldc.i4.s 0x20
0x44b2  or
0x44b3  stloc.0
0x44b4  ldarg.0
0x44b5  box      Microsoft.BIServer.Configuration.DumperFlags
0x44ba  ldc.i4   0x10000
0x44bf  box      Microsoft.BIServer.Configuration.DumperFlags
0x44c4  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x44c9  brfalse.s loc_44D3
0x44cb  ldloc.0
0x44cc  ldc.i4   0x10000
0x44d1  or
0x44d2  stloc.0
0x44d3  ldarg.0
0x44d4  box      Microsoft.BIServer.Configuration.DumperFlags
0x44d9  ldc.i4.0
0x44da  box      Microsoft.BIServer.Configuration.DumperFlags
0x44df  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x44e4  brfalse.s loc_44EA
0x44e6  ldloc.0
0x44e7  ldc.i4.0
0x44e8  or
0x44e9  stloc.0
0x44ea  ldarg.0
0x44eb  box      Microsoft.BIServer.Configuration.DumperFlags
0x44f0  ldc.i4   0x80000
0x44f5  box      Microsoft.BIServer.Configuration.DumperFlags
0x44fa  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x44ff  brfalse.s loc_4509
0x4501  ldloc.0
0x4502  ldc.i4   0x80000
0x4507  or
0x4508  stloc.0
0x4509  ldarg.0
0x450a  box      Microsoft.BIServer.Configuration.DumperFlags
0x450f  ldc.i4   0x2000
0x4514  box      Microsoft.BIServer.Configuration.DumperFlags
0x4519  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x451e  brfalse.s loc_4528
0x4520  ldloc.0
0x4521  ldc.i4   0x2000
0x4526  or
0x4527  stloc.0
0x4528  ldarg.0
0x4529  box      Microsoft.BIServer.Configuration.DumperFlags
0x452e  ldc.i4   0x8000
0x4533  box      Microsoft.BIServer.Configuration.DumperFlags
0x4538  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x453d  brfalse.s loc_4547
0x453f  ldloc.0
0x4540  ldc.i4   0x8000
0x4545  or
0x4546  stloc.0
0x4547  ldarg.0
0x4548  box      Microsoft.BIServer.Configuration.DumperFlags
0x454d  ldc.i4   0x200000
0x4552  box      Microsoft.BIServer.Configuration.DumperFlags
0x4557  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x455c  brfalse.s loc_4566
0x455e  ldloc.0
0x455f  ldc.i4   0x200000
0x4564  or
0x4565  stloc.0
0x4566  ldarg.0
0x4567  box      Microsoft.BIServer.Configuration.DumperFlags
0x456c  ldc.i4   0x4000
0x4571  box      Microsoft.BIServer.Configuration.DumperFlags
0x4576  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x457b  brfalse.s loc_4585
0x457d  ldloc.0
0x457e  ldc.i4   0x4000
0x4583  or
0x4584  stloc.0
0x4585  ldarg.0
0x4586  box      Microsoft.BIServer.Configuration.DumperFlags
0x458b  ldc.i4   0x40000
0x4590  box      Microsoft.BIServer.Configuration.DumperFlags
0x4595  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x459a  brfalse.s loc_45A4
0x459c  ldloc.0
0x459d  ldc.i4   0x40000
0x45a2  or
0x45a3  stloc.0
0x45a4  ldarg.0
0x45a5  box      Microsoft.BIServer.Configuration.DumperFlags
0x45aa  ldc.i4.s 0x40
0x45ac  box      Microsoft.BIServer.Configuration.DumperFlags
0x45b1  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x45b6  brfalse.s loc_45BD
0x45b8  ldloc.0
0x45b9  ldc.i4.s 0x40
0x45bb  or
0x45bc  stloc.0
0x45bd  ldarg.0
0x45be  box      Microsoft.BIServer.Configuration.DumperFlags
0x45c3  ldc.i4   0x400000
0x45c8  box      Microsoft.BIServer.Configuration.DumperFlags
0x45cd  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x45d2  brfalse.s loc_45DC
0x45d4  ldloc.0
0x45d5  ldc.i4   0x400000
0x45da  or
0x45db  stloc.0
0x45dc  ldarg.0
0x45dd  box      Microsoft.BIServer.Configuration.DumperFlags
0x45e2  ldc.i4   0x1000
0x45e7  box      Microsoft.BIServer.Configuration.DumperFlags
0x45ec  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x45f1  brfalse.s loc_45FB
0x45f3  ldloc.0
0x45f4  ldc.i4   0x1000
0x45f9  or
0x45fa  stloc.0
0x45fb  ldarg.0
0x45fc  box      Microsoft.BIServer.Configuration.DumperFlags
0x4601  ldc.i4.2
0x4602  box      Microsoft.BIServer.Configuration.DumperFlags
0x4607  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x460c  brfalse.s loc_4612
0x460e  ldloc.0
0x460f  ldc.i4.2
0x4610  or
0x4611  stloc.0
0x4612  ldarg.0
0x4613  box      Microsoft.BIServer.Configuration.DumperFlags
0x4618  ldc.i4   0x20000
0x461d  box      Microsoft.BIServer.Configuration.DumperFlags
0x4622  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x4627  brfalse.s loc_4631
0x4629  ldloc.0
0x462a  ldc.i4   0x20000
0x462f  or
0x4630  stloc.0
0x4631  ldarg.0
0x4632  box      Microsoft.BIServer.Configuration.DumperFlags
0x4637  ldc.i4.8
0x4638  box      Microsoft.BIServer.Configuration.DumperFlags
0x463d  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x4642  brfalse.s loc_4648
0x4644  ldloc.0
0x4645  ldc.i4.8
0x4646  or
0x4647  stloc.0
0x4648  ldarg.0
0x4649  box      Microsoft.BIServer.Configuration.DumperFlags
0x464e  ldc.i4   0x400
0x4653  box      Microsoft.BIServer.Configuration.DumperFlags
0x4658  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x465d  brfalse.s loc_4667
0x465f  ldloc.0
0x4660  ldc.i4   0x400
0x4665  or
0x4666  stloc.0
0x4667  ldarg.0
0x4668  box      Microsoft.BIServer.Configuration.DumperFlags
0x466d  ldc.i4   0x100000
0x4672  box      Microsoft.BIServer.Configuration.DumperFlags
0x4677  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x467c  brfalse.s loc_4686
0x467e  ldloc.0
0x467f  ldc.i4   0x100000
0x4684  or
0x4685  stloc.0
0x4686  ldarg.0
0x4687  box      Microsoft.BIServer.Configuration.DumperFlags
0x468c  ldc.i4   0x4000000
0x4691  box      Microsoft.BIServer.Configuration.DumperFlags
0x4696  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x469b  brfalse.s loc_46A5
0x469d  ldloc.0
0x469e  ldc.i4   0x4000000
0x46a3  or
0x46a4  stloc.0
0x46a5  ldarg.0
0x46a6  box      Microsoft.BIServer.Configuration.DumperFlags
0x46ab  ldc.i4   0x800
0x46b0  box      Microsoft.BIServer.Configuration.DumperFlags
0x46b5  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x46ba  brfalse.s loc_46C4
0x46bc  ldloc.0
0x46bd  ldc.i4   0x800
0x46c2  or
0x46c3  stloc.0
0x46c4  ldarg.0
0x46c5  box      Microsoft.BIServer.Configuration.DumperFlags
0x46ca  ldc.i4   0x100
0x46cf  box      Microsoft.BIServer.Configuration.DumperFlags
0x46d4  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x46d9  brfalse.s loc_46E3
0x46db  ldloc.0
0x46dc  ldc.i4   0x100
0x46e1  or
0x46e2  stloc.0
0x46e3  ldarg.0
0x46e4  box      Microsoft.BIServer.Configuration.DumperFlags
0x46e9  ldc.i4   0x200
0x46ee  box      Microsoft.BIServer.Configuration.DumperFlags
0x46f3  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x46f8  brfalse.s loc_4702
0x46fa  ldloc.0
0x46fb  ldc.i4   0x200
0x4700  or
0x4701  stloc.0
0x4702  ldloc.0
0x4703  ret
```
