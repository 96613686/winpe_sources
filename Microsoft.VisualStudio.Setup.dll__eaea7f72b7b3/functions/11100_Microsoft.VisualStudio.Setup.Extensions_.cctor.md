# Microsoft.VisualStudio.Setup.Extensions::.cctor

- ea: `0x11100`
- end: `0x11234`
- name: `Microsoft.VisualStudio.Setup.Extensions::.cctor`
- size: `308`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x11132`: `%CommonProgramW6432%`
- `0x1113c`: `CommonProgramFiles`
- `0x11146`: `CommonProgramFilesX86`
- `0x11150`: `CommonProgramFiles64`
- `0x1115a`: `CommonProgramFilesX64`
- `0x11164`: `ProgramData`
- `0x111b4`: `VSIXInstaller.exe`

## pseudocode

```c

```

## disassembly

```asm
0x11100  ldstr    aProgramw6432// "%ProgramW6432%"
0x11105  stsfld   string Microsoft.VisualStudio.Setup.Extensions::ProgramFiles64Env
0x1110a  ldstr    aProgramfiles// "ProgramFiles"
0x1110f  stsfld   string Microsoft.VisualStudio.Setup.Extensions::ProgramFiles
0x11114  ldstr    aProgramfilesx8// "ProgramFilesX86"
0x11119  stsfld   string Microsoft.VisualStudio.Setup.Extensions::ProgramFilesX86
0x1111e  ldstr    aProgramfiles64_1// "ProgramFiles64"
0x11123  stsfld   string Microsoft.VisualStudio.Setup.Extensions::ProgramFiles64
0x11128  ldstr    aProgramfilesx6// "ProgramFilesX64"
0x1112d  stsfld   string Microsoft.VisualStudio.Setup.Extensions::ProgramFilesX64
0x11132  ldstr    aCommonprogramw// "%CommonProgramW6432%"
0x11137  stsfld   string Microsoft.VisualStudio.Setup.Extensions::CommonProgramFiles64Env
0x1113c  ldstr    aCommonprogramf_0// "CommonProgramFiles"
0x11141  stsfld   string Microsoft.VisualStudio.Setup.Extensions::CommonProgramFiles
0x11146  ldstr    aCommonprogramf_1// "CommonProgramFilesX86"
0x1114b  stsfld   string Microsoft.VisualStudio.Setup.Extensions::CommonProgramFilesX86
0x11150  ldstr    aCommonprogramf_2// "CommonProgramFiles64"
0x11155  stsfld   string Microsoft.VisualStudio.Setup.Extensions::CommonProgramFiles64
0x1115a  ldstr    aCommonprogramf_3// "CommonProgramFilesX64"
0x1115f  stsfld   string Microsoft.VisualStudio.Setup.Extensions::CommonProgramFilesX64
0x11164  ldstr    aProgramdata// "ProgramData"
0x11169  stsfld   string Microsoft.VisualStudio.Setup.Extensions::ProgramData
0x1116e  ldstr    aSystem// "System"
0x11173  stsfld   string Microsoft.VisualStudio.Setup.Extensions::SystemToken
0x11178  ldstr    aSystemfolder_0// "SystemFolder"
0x1117d  stsfld   string Microsoft.VisualStudio.Setup.Extensions::SystemFolder
0x11182  ldstr    aSystemx86// "SystemX86"
0x11187  stsfld   string Microsoft.VisualStudio.Setup.Extensions::SystemX86
0x1118c  ldstr    aSystem64// "System64"
0x11191  stsfld   string Microsoft.VisualStudio.Setup.Extensions::System64
0x11196  ldstr    aSystemx64// "SystemX64"
0x1119b  stsfld   string Microsoft.VisualStudio.Setup.Extensions::SystemX64
0x111a0  ldstr    aWindows// "Windows"
0x111a5  stsfld   string Microsoft.VisualStudio.Setup.Extensions::Windows
0x111aa  ldstr    aFolder// "folder"
0x111af  stsfld   string Microsoft.VisualStudio.Setup.Extensions::FolderSuffix
0x111b4  ldstr    aVsixinstallerE// "VSIXInstaller.exe"
0x111b9  stsfld   string Microsoft.VisualStudio.Setup.Extensions::VSIXInstallerExeName
0x111be  ldstr    aEnUs_0// "en-US"
0x111c3  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(string)
0x111c8  stsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.Extensions::DefaultLocale
0x111cd  ldc.i4.2
0x111ce  newarr   [mscorlib]System.String
0x111d3  dup
0x111d4  ldc.i4.0
0x111d5  ldstr    aTrCy// "tr-CY"
0x111da  stelem.ref
0x111db  dup
0x111dc  ldc.i4.1
0x111dd  ldstr    aPtMo// "pt-MO"
0x111e2  stelem.ref
0x111e3  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Extensions::EnglishFallbackLocales
0x111e8  ldc.i4.s 0xE
0x111ea  newarr   [mscorlib]System.Int32
0x111ef  dup
0x111f0  ldtoken  valuetype __StaticArrayInitTypeSize=56 <PrivateImplementationDetails>::'9EF729961F1E098FF25FDF45E14B78587B6D77AAA6A17AEC9128ADFC48A4C8F3'
0x111f5  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x111fa  stsfld   int32[] Microsoft.VisualStudio.Setup.Extensions::SupportedLCIDs
0x111ff  ldc.i4   0x804
0x11204  stsfld   int32 Microsoft.VisualStudio.Setup.Extensions::SimplifiedChineseLCID
0x11209  ldc.i4   0x404
0x1120e  stsfld   int32 Microsoft.VisualStudio.Setup.Extensions::TraditionalChineseLCID
0x11213  ldc.i4   0x7C04
0x11218  stsfld   int32 Microsoft.VisualStudio.Setup.Extensions::MandarinTraditionalChineseLCID
0x1121d  ldc.i4.4
0x1121e  stsfld   int32 Microsoft.VisualStudio.Setup.Extensions::MandarinSimplifiedChineseLCID
0x11223  ldc.i4   0x7804
0x11228  stsfld   int32 Microsoft.VisualStudio.Setup.Extensions::ChineseLCID
0x1122d  ldnull
0x1122e  stsfld   class Microsoft.VisualStudio.Setup.ConditionEvaluatorFactory Microsoft.VisualStudio.Setup.Extensions::conditionEvaluatorFactory
0x11233  ret
```
