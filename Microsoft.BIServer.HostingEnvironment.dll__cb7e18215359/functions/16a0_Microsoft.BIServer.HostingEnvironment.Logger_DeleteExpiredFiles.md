# Microsoft.BIServer.HostingEnvironment.Logger::DeleteExpiredFiles

- ea: `0x16a0`
- end: `0x16cd`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::DeleteExpiredFiles`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x16d0`

## pseudocode

```c

```

## disassembly

```asm
0x16a0  ldarg.1
0x16a1  ldarg.0
0x16a2  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x16a7  ldstr    aLog_1// "*.log"
0x16ac  call     instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles(string)
0x16b1  call     void Microsoft.BIServer.HostingEnvironment.Logger::DeleteExpiredFilesInternal(int32 keepUntilDays, class [mscorlib]System.IO.FileInfo[] logFiles)
0x16b6  ldarg.1
0x16b7  ldarg.0
0x16b8  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x16bd  ldstr    aMtrx_0// "*.mtrx"
0x16c2  call     instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles(string)
0x16c7  call     void Microsoft.BIServer.HostingEnvironment.Logger::DeleteExpiredFilesInternal(int32 keepUntilDays, class [mscorlib]System.IO.FileInfo[] logFiles)
0x16cc  ret
```
