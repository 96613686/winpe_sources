# Microsoft.SharePoint.Diagnostics.SqlTraceEvent::EventTypeFromName

- ea: `0x645390`
- end: `0x645b7f`
- name: `Microsoft.SharePoint.Diagnostics.SqlTraceEvent::EventTypeFromName`
- size: `2031`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x645390`

## string_xrefs

- `0x6453bd`: `rpccompleted`
- `0x6453d5`: `sqlbatchcompleted`
- `0x64541d`: `servicecontrol`
- `0x6454d3`: `spcachemiss`
- `0x6454e0`: `spcacheinsert`
- `0x6454ed`: `spcacheremove`
- `0x6454fa`: `sprecompile`
- `0x645507`: `spcachehit`
- `0x64552e`: `sqlstmtcompleted`
- `0x645548`: `spcompleted`
- `0x645562`: `spstmtcompleted`
- `0x64556f`: `objectcreated`
- `0x64557c`: `objectdeleted`
- `0x6455b0`: `cursoropen`
- `0x6455d7`: `autoupdatestats`
- `0x645673`: `cursorrecompile`
- `0x645791`: `showplanxml`

## pseudocode

```c

```

## disassembly

```asm
0x645390  ldarg.0
0x645391  callvirt instance string [mscorlib]System.String::ToLower()
0x645396  dup
0x645397  stloc.0
0x645398  brfalse  loc_645B6E
0x64539d  volatile.
0x64539f  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{7F5A19CB-910C-4E1B-81E8-035FE0963D88}::$$method0x6010713-1
0x6453a4  brtrue   loc_6458A8
0x6453a9  ldc.i4.s 0x62
0x6453ab  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x6453b0  dup
0x6453b1  ldstr    aNonevent// "nonevent"
0x6453b6  ldc.i4.0
0x6453b7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6453bc  dup
0x6453bd  ldstr    aRpccompleted// "rpccompleted"
0x6453c2  ldc.i4.1
0x6453c3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6453c8  dup
0x6453c9  ldstr    aRpcstarting// "rpcstarting"
0x6453ce  ldc.i4.2
0x6453cf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6453d4  dup
0x6453d5  ldstr    aSqlbatchcomple// "sqlbatchcompleted"
0x6453da  ldc.i4.3
0x6453db  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6453e0  dup
0x6453e1  ldstr    aSqlbatchstarti// "sqlbatchstarting"
0x6453e6  ldc.i4.4
0x6453e7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6453ec  dup
0x6453ed  ldstr    aLogin_0// "login"
0x6453f2  ldc.i4.5
0x6453f3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6453f8  dup
0x6453f9  ldstr    aLogout// "logout"
0x6453fe  ldc.i4.6
0x6453ff  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645404  dup
0x645405  ldstr    aAttention// "attention"
0x64540a  ldc.i4.7
0x64540b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645410  dup
0x645411  ldstr    aExistingconnec// "existingconnection"
0x645416  ldc.i4.8
0x645417  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64541c  dup
0x64541d  ldstr    aServicecontrol// "servicecontrol"
0x645422  ldc.i4.s 9
0x645424  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645429  dup
0x64542a  ldstr    aDtctransaction// "dtctransaction"
0x64542f  ldc.i4.s 0xA
0x645431  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645436  dup
0x645437  ldstr    aLoginfailed// "loginfailed"
0x64543c  ldc.i4.s 0xB
0x64543e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645443  dup
0x645444  ldstr    aEventlog_0// "eventlog"
0x645449  ldc.i4.s 0xC
0x64544b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645450  dup
0x645451  ldstr    aErrorlog// "errorlog"
0x645456  ldc.i4.s 0xD
0x645458  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64545d  dup
0x64545e  ldstr    aLockreleased// "lockreleased"
0x645463  ldc.i4.s 0xE
0x645465  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64546a  dup
0x64546b  ldstr    aLockacquired// "lockacquired"
0x645470  ldc.i4.s 0xF
0x645472  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645477  dup
0x645478  ldstr    aDeadlock// "deadlock"
0x64547d  ldc.i4.s 0x10
0x64547f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645484  dup
0x645485  ldstr    aDeadlocks// "deadlocks"
0x64548a  ldc.i4.s 0x11
0x64548c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645491  dup
0x645492  ldstr    aLockdeadlock// "lockdeadlock"
0x645497  ldc.i4.s 0x12
0x645499  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64549e  dup
0x64549f  ldstr    aLockcancel// "lockcancel"
0x6454a4  ldc.i4.s 0x13
0x6454a6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6454ab  dup
0x6454ac  ldstr    aLocktimeout_0// "locktimeout"
0x6454b1  ldc.i4.s 0x14
0x6454b3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6454b8  dup
0x6454b9  ldstr    aDopevent// "dopevent"
0x6454be  ldc.i4.s 0x15
0x6454c0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6454c5  dup
0x6454c6  ldstr    aException_0// "exception"
0x6454cb  ldc.i4.s 0x16
0x6454cd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6454d2  dup
0x6454d3  ldstr    aSpcachemiss// "spcachemiss"
0x6454d8  ldc.i4.s 0x17
0x6454da  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6454df  dup
0x6454e0  ldstr    aSpcacheinsert// "spcacheinsert"
0x6454e5  ldc.i4.s 0x18
0x6454e7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6454ec  dup
0x6454ed  ldstr    aSpcacheremove// "spcacheremove"
0x6454f2  ldc.i4.s 0x19
0x6454f4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6454f9  dup
0x6454fa  ldstr    aSprecompile// "sprecompile"
0x6454ff  ldc.i4.s 0x1A
0x645501  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645506  dup
0x645507  ldstr    aSpcachehit// "spcachehit"
0x64550c  ldc.i4.s 0x1B
0x64550e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645513  dup
0x645514  ldstr    aSpexeccontexth// "spexeccontexthit"
0x645519  ldc.i4.s 0x1C
0x64551b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645520  dup
0x645521  ldstr    aSqlstmtstartin// "sqlstmtstarting"
0x645526  ldc.i4.s 0x1D
0x645528  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64552d  dup
0x64552e  ldstr    aSqlstmtcomplet// "sqlstmtcompleted"
0x645533  ldc.i4.s 0x1E
0x645535  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64553a  dup
0x64553b  ldstr    aSpstarting// "spstarting"
0x645540  ldc.i4.s 0x1F
0x645542  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645547  dup
0x645548  ldstr    aSpcompleted// "spcompleted"
0x64554d  ldc.i4.s 0x20
0x64554f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645554  dup
0x645555  ldstr    aSpstmtstarting// "spstmtstarting"
0x64555a  ldc.i4.s 0x21
0x64555c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645561  dup
0x645562  ldstr    aSpstmtcomplete// "spstmtcompleted"
0x645567  ldc.i4.s 0x22
0x645569  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64556e  dup
0x64556f  ldstr    aObjectcreated// "objectcreated"
0x645574  ldc.i4.s 0x23
0x645576  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64557b  dup
0x64557c  ldstr    aObjectdeleted// "objectdeleted"
0x645581  ldc.i4.s 0x24
0x645583  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645588  dup
0x645589  ldstr    aSqltransaction// "sqltransaction"
0x64558e  ldc.i4.s 0x25
0x645590  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645595  dup
0x645596  ldstr    aScanstarted// "scanstarted"
0x64559b  ldc.i4.s 0x26
0x64559d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6455a2  dup
0x6455a3  ldstr    aScanstopped// "scanstopped"
0x6455a8  ldc.i4.s 0x27
0x6455aa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6455af  dup
0x6455b0  ldstr    aCursoropen// "cursoropen"
0x6455b5  ldc.i4.s 0x28
0x6455b7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6455bc  dup
0x6455bd  ldstr    aTransactionlog// "transactionlog"
0x6455c2  ldc.i4.s 0x29
0x6455c4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6455c9  dup
0x6455ca  ldstr    aHashwarning// "hashwarning"
0x6455cf  ldc.i4.s 0x2A
0x6455d1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6455d6  dup
0x6455d7  ldstr    aAutoupdatestat// "autoupdatestats"
0x6455dc  ldc.i4.s 0x2B
0x6455de  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6455e3  dup
0x6455e4  ldstr    aLockdeadlockch// "lockdeadlockchain"
0x6455e9  ldc.i4.s 0x2C
0x6455eb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6455f0  dup
0x6455f1  ldstr    aLockescalation// "lockescalation"
0x6455f6  ldc.i4.s 0x2D
0x6455f8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6455fd  dup
0x6455fe  ldstr    aOledberrors// "oledberrors"
0x645603  ldc.i4.s 0x2E
0x645605  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64560a  dup
0x64560b  ldstr    aExecutionwarni// "executionwarnings"
0x645610  ldc.i4.s 0x2F
0x645612  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645617  dup
0x645618  ldstr    aExecutionplan_0// "executionplan"
0x64561d  ldc.i4.s 0x30
0x64561f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645624  dup
0x645625  ldstr    aSortwarnings// "sortwarnings"
0x64562a  ldc.i4.s 0x31
0x64562c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645631  dup
0x645632  ldstr    aCursorprepare// "cursorprepare"
0x645637  ldc.i4.s 0x32
0x645639  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64563e  dup
0x64563f  ldstr    aPreparesql// "preparesql"
0x645644  ldc.i4.s 0x33
0x645646  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64564b  dup
0x64564c  ldstr    aExecpreparedsq// "execpreparedsql"
0x645651  ldc.i4.s 0x34
0x645653  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645658  dup
0x645659  ldstr    aUnpreparesql// "unpreparesql"
0x64565e  ldc.i4.s 0x35
0x645660  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645665  dup
0x645666  ldstr    aCursorexecute// "cursorexecute"
0x64566b  ldc.i4.s 0x36
0x64566d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645672  dup
0x645673  ldstr    aCursorrecompil// "cursorrecompile"
0x645678  ldc.i4.s 0x37
0x64567a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64567f  dup
0x645680  ldstr    aCursorimplicit// "cursorimplicitconversion"
0x645685  ldc.i4.s 0x38
0x645687  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64568c  dup
0x64568d  ldstr    aCursorunprepar// "cursorunprepare"
0x645692  ldc.i4.s 0x39
0x645694  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645699  dup
0x64569a  ldstr    aCursorclose// "cursorclose"
0x64569f  ldc.i4.s 0x3A
0x6456a1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6456a6  dup
0x6456a7  ldstr    aMissingcolumns// "missingcolumnstatistics"
0x6456ac  ldc.i4.s 0x3B
0x6456ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6456b3  dup
0x6456b4  ldstr    aMissingjoinpre// "missingjoinpredicate"
0x6456b9  ldc.i4.s 0x3C
0x6456bb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6456c0  dup
0x6456c1  ldstr    aServermemorych// "servermemorychange"
0x6456c6  ldc.i4.s 0x3D
0x6456c8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6456cd  dup
0x6456ce  ldstr    aUser82// "user82"
0x6456d3  ldc.i4.s 0x3E
0x6456d5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6456da  dup
0x6456db  ldstr    aUser83// "user83"
0x6456e0  ldc.i4.s 0x3F
0x6456e2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6456e7  dup
0x6456e8  ldstr    aUser84// "user84"
0x6456ed  ldc.i4.s 0x40
0x6456ef  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6456f4  dup
0x6456f5  ldstr    aUser85// "user85"
0x6456fa  ldc.i4.s 0x41
0x6456fc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645701  dup
0x645702  ldstr    aUser86// "user86"
0x645707  ldc.i4.s 0x42
0x645709  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64570e  dup
0x64570f  ldstr    aUser87// "user87"
0x645714  ldc.i4.s 0x43
0x645716  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64571b  dup
0x64571c  ldstr    aUser88// "user88"
0x645721  ldc.i4.s 0x44
0x645723  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645728  dup
0x645729  ldstr    aUser89// "user89"
0x64572e  ldc.i4.s 0x45
0x645730  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645735  dup
0x645736  ldstr    aUser90// "user90"
0x64573b  ldc.i4.s 0x46
0x64573d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x645742  dup
0x645743  ldstr    aUser91// "user91"
0x645748  ldc.i4.s 0x47
0x64574a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64574f  dup
0x645750  ldstr    aDatafileautogr// "datafileautogrow"
  ... truncated ...
```
