# Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::.cctor

- ea: `0x3ac30`
- end: `0x3adf3`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::.cctor`
- size: `451`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x12830`

## string_xrefs

- `0x3ac80`: `Event/System/TimeCreated/@SystemTime`
- `0x3ad57`: `Event/System/TimeCreated/@SystemTime`
- `0x3ac62`: `Event/System/Task`
- `0x3ad90`: `Event/System/Task`
- `0x3ac94`: `Event/System/Computer`
- `0x3ad67`: `Event/System/Computer`
- `0x3ac9e`: `Event/System/Security/@UserID`
- `0x3ad6f`: `Event/System/Security/@UserID`
- `0x3acbc`: `Event/System/Execution/@ProcessID`
- `0x3acc6`: `Event/System/Execution/@ThreadID`

## pseudocode

```c

```

## disassembly

```asm
0x3ac30  ldstr    aSystem// "System"
0x3ac35  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::SystemNodeName
0x3ac3a  ldstr    aEventDebugdata// "Event/DebugData/Message"
0x3ac3f  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::DebugMessagePath
0x3ac44  ldstr    aEventDebugdata_0// "Event/DebugData/LevelName"
0x3ac49  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::DebugLevelPath
0x3ac4e  ldstr    aEventSystemKey// "Event/System/Keywords"
0x3ac53  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::KeywordsPath
0x3ac58  ldstr    aEventSystemLev// "Event/System/Level"
0x3ac5d  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::LevelsPath
0x3ac62  ldstr    aEventSystemTas// "Event/System/Task"
0x3ac67  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::TasksPath
0x3ac6c  ldstr    aEventSystemPro// "Event/System/Provider/@Name"
0x3ac71  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::SourcePath
0x3ac76  ldstr    aEventSystemEve// "Event/System/EventID"
0x3ac7b  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::EventIdPath
0x3ac80  ldstr    aEventSystemTim// "Event/System/TimeCreated/@SystemTime"
0x3ac85  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::TimeCreatedPath
0x3ac8a  ldstr    aEventSystemCha// "Event/System/Channel"
0x3ac8f  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::ChannelPath
0x3ac94  ldstr    aEventSystemCom// "Event/System/Computer"
0x3ac99  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::ComputerPath
0x3ac9e  ldstr    aEventSystemSec// "Event/System/Security/@UserID"
0x3aca3  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::UserIdPath
0x3aca8  ldstr    aEventSystemOpc// "Event/System/Opcode"
0x3acad  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::OpcodePath
0x3acb2  ldstr    aEventSystemEve_0// "Event/System/EventRecordID"
0x3acb7  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::EventRecordIdPath
0x3acbc  ldstr    aEventSystemExe// "Event/System/Execution/@ProcessID"
0x3acc1  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::ProcessIdPath
0x3acc6  ldstr    aEventSystemExe_0// "Event/System/Execution/@ThreadID"
0x3accb  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::ThreadIdPath
0x3acd0  ldstr    aEventSystemCor// "Event/System/Correlation/@ActivityID"
0x3acd5  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::ActivityIdPath
0x3acda  ldstr    aEventSystemCor_0// "Event/System/Correlation/@RelatedActivi"...
0x3acdf  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::RelativeActivityIdPath
0x3ace4  ldstr    aEventSystemPro_0// "Event/System/Provider/@EventSourceName"
0x3ace9  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::EventSourceNamePath
0x3acee  ldstr    aEventSystemExe_1// "Event/System/Execution/@ProcessorID"
0x3acf3  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::ProcessorIdPath
0x3acf8  ldstr    aEventSystemExe_2// "Event/System/Execution/@SessionID"
0x3acfd  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::SessionIdPath
0x3ad02  ldstr    aEventSystemExe_3// "Event/System/Execution/@KernelTime"
0x3ad07  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::KernelTimePath
0x3ad0c  ldstr    aEventSystemExe_4// "Event/System/Execution/@UserTime"
0x3ad11  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::UserTimePath
0x3ad16  ldstr    aEventSystemExe_5// "Event/System/Execution/@ProcessorTime"
0x3ad1b  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::ProcessorTime
0x3ad20  ldstr    aSystemBinaryda// "System/BinaryData"
0x3ad25  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::BinaryDataPath
0x3ad2a  ldstr    aEventRendering// "Event/RenderingInfo/Level"
0x3ad2f  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::RenderedLevel
0x3ad34  ldstr    aEventSystemPro_1// "Event/System/Provider/@Guid"
0x3ad39  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::ProviderGuidPath
0x3ad3e  ldc.i4.s 0xD
0x3ad40  newarr   [mscorlib]System.String
0x3ad45  dup
0x3ad46  ldc.i4.0
0x3ad47  ldstr    aEventSystemPro// "Event/System/Provider/@Name"
0x3ad4c  stelem.ref
0x3ad4d  dup
0x3ad4e  ldc.i4.1
0x3ad4f  ldstr    aEventSystemEve// "Event/System/EventID"
0x3ad54  stelem.ref
0x3ad55  dup
0x3ad56  ldc.i4.2
0x3ad57  ldstr    aEventSystemTim// "Event/System/TimeCreated/@SystemTime"
0x3ad5c  stelem.ref
0x3ad5d  dup
0x3ad5e  ldc.i4.3
0x3ad5f  ldstr    aEventSystemCha// "Event/System/Channel"
0x3ad64  stelem.ref
0x3ad65  dup
0x3ad66  ldc.i4.4
0x3ad67  ldstr    aEventSystemCom// "Event/System/Computer"
0x3ad6c  stelem.ref
0x3ad6d  dup
0x3ad6e  ldc.i4.5
0x3ad6f  ldstr    aEventSystemSec// "Event/System/Security/@UserID"
0x3ad74  stelem.ref
0x3ad75  dup
0x3ad76  ldc.i4.6
0x3ad77  ldstr    aEventRendering// "Event/RenderingInfo/Level"
0x3ad7c  stelem.ref
0x3ad7d  dup
0x3ad7e  ldc.i4.7
0x3ad7f  ldstr    aEventDebugdata_0// "Event/DebugData/LevelName"
0x3ad84  stelem.ref
0x3ad85  dup
0x3ad86  ldc.i4.8
0x3ad87  ldstr    aEventSystemLev// "Event/System/Level"
0x3ad8c  stelem.ref
0x3ad8d  dup
0x3ad8e  ldc.i4.s 9
0x3ad90  ldstr    aEventSystemTas// "Event/System/Task"
0x3ad95  stelem.ref
0x3ad96  dup
0x3ad97  ldc.i4.s 0xA
0x3ad99  ldstr    aEventSystemKey// "Event/System/Keywords"
0x3ad9e  stelem.ref
0x3ad9f  dup
0x3ada0  ldc.i4.s 0xB
0x3ada2  ldstr    aEventSystemOpc// "Event/System/Opcode"
0x3ada7  stelem.ref
0x3ada8  dup
0x3ada9  ldc.i4.s 0xC
0x3adab  ldstr    aEventSystemEve_0// "Event/System/EventRecordID"
0x3adb0  stelem.ref
0x3adb1  stsfld   string[] Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::LiteRecProps
0x3adb6  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::.ctor()
0x3adbb  stsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeLiteRecordContext
0x3adc0  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::.ctor()
0x3adc5  stsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeTaskContext
0x3adca  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::.ctor()
0x3adcf  stsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeKeyWordContext
0x3add4  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::.ctor()
0x3add9  stsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeLevelContext
0x3adde  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::.ctor()
0x3ade3  stsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeOpcodeContext
0x3ade8  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::.ctor()
0x3aded  stsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeUserContext
0x3adf2  ret
```
