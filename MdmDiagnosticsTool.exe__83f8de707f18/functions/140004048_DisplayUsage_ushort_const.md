# DisplayUsage(ushort const *)

- ea: `0x140004048`
- end: `0x140004251`
- name: `?DisplayUsage@@YAXPEBG@Z`
- size: `521`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008694`

## import_xrefs

- `msvcrt!wprintf` at `0x14000405f`
- `msvcrt!wprintf` at `0x140004075`
- `msvcrt!wprintf` at `0x140004088`
- `msvcrt!wprintf` at `0x14000409e`
- `msvcrt!wprintf` at `0x1400040ad`
- `msvcrt!wprintf` at `0x1400040c3`
- `msvcrt!wprintf` at `0x1400040d6`
- `msvcrt!wprintf` at `0x1400040e9`
- `msvcrt!wprintf` at `0x1400040fc`
- `msvcrt!wprintf` at `0x14000410f`
- `msvcrt!wprintf` at `0x140004122`
- `msvcrt!wprintf` at `0x140004135`
- `msvcrt!wprintf` at `0x140004148`
- `msvcrt!wprintf` at `0x14000415b`
- `msvcrt!wprintf` at `0x14000416e`
- `msvcrt!wprintf` at `0x140004184`
- `msvcrt!wprintf` at `0x140004193`
- `msvcrt!wprintf` at `0x1400041a9`
- `msvcrt!wprintf` at `0x1400041bc`
- `msvcrt!wprintf` at `0x1400041cb`
- `msvcrt!wprintf` at `0x1400041e1`
- `msvcrt!wprintf` at `0x1400041f4`
- `msvcrt!wprintf` at `0x140004203`
- `msvcrt!wprintf` at `0x140004219`
- `msvcrt!wprintf` at `0x14000422c`
- `msvcrt!wprintf` at `0x14000405f`
- `msvcrt!wprintf` at `0x140004075`
- `msvcrt!wprintf` at `0x140004088`
- `msvcrt!wprintf` at `0x14000409e`
- `msvcrt!wprintf` at `0x1400040ad`
- `msvcrt!wprintf` at `0x1400040c3`
- `msvcrt!wprintf` at `0x1400040d6`
- `msvcrt!wprintf` at `0x1400040e9`
- `msvcrt!wprintf` at `0x1400040fc`
- `msvcrt!wprintf` at `0x14000410f`
- `msvcrt!wprintf` at `0x140004122`
- `msvcrt!wprintf` at `0x140004135`
- `msvcrt!wprintf` at `0x140004148`
- `msvcrt!wprintf` at `0x14000415b`
- `msvcrt!wprintf` at `0x14000416e`
- `msvcrt!wprintf` at `0x140004184`
- `msvcrt!wprintf` at `0x140004193`
- `msvcrt!wprintf` at `0x1400041a9`
- `msvcrt!wprintf` at `0x1400041bc`
- `msvcrt!wprintf` at `0x1400041cb`
- `msvcrt!wprintf` at `0x1400041e1`
- `msvcrt!wprintf` at `0x1400041f4`
- `msvcrt!wprintf` at `0x140004203`
- `msvcrt!wprintf` at `0x140004219`
- `msvcrt!wprintf` at `0x14000422c`
- `msvcrt!wprintf` at `0x140004245`

## string_xrefs

- `0x14000406e`: `  Usage1: %ws -out <output folder path>\n`
- `0x140004081`: `      * Output MDM diagnostics info only to given folder path specified in -out parameter.\n`
- `0x140004097`: `      eg: %ws -out c:\temp\outputfolder\n`
- `0x1400040bc`: `  Usage2: %ws -area <area name(s)> -cab <output cab file path>\n`
- `0x1400040cf`: `      * Collect predefined area logs and create a log cab to given cab file.\n`
- `0x140004154`: `      * Please find all possible areas in registry under:\n`
- `0x14000417d`: `      eg: %ws -area Autopilot;Tpm -cab c:\temp\AutopilotDiag.cab\n`
- `0x1400041a2`: `  Usage3: %ws -area <area name(s)> -zip <output zip file path>\n`
- `0x1400041b5`: `      * Collect predefined area logs and create a log zip to given zip file. Areas supported are the same as Usage2 for creating cab\n`
- `0x1400041da`: `  Usage4: %ws -xml <xml file of information to gather> -zip <output zip file path> -server <MDM Server to alert>\n`
- `0x1400041ed`: `      * Collect information specified in the xml and create a log zip to given zip file. \n`

## pseudocode

```c
void __fastcall DisplayUsage(const unsigned __int16 *a1)
{
  wprintf(L"\n");
  wprintf(L"  Usage1: %ws -out <output folder path>\n", a1);
  wprintf(L"      * Output MDM diagnostics info only to given folder path specified in -out parameter.\n");
  wprintf(L"      eg: %ws -out c:\\temp\\outputfolder\n", a1);
  wprintf(L"\n");
  wprintf(L"  Usage2: %ws -area <area name(s)> -cab <output cab file path>\n", a1);
  wprintf(L"      * Collect predefined area logs and create a log cab to given cab file.\n");
  wprintf(L"      * Supported area name example:\n");
  wprintf(L"          Autopilot\n");
  wprintf(L"          DeviceProvisioning\n");
  wprintf(L"          Tpm\n");
  wprintf(L"      * It also supports multiple areas, separated by ';', example:\n");
  wprintf(L"          Autopilot;DeviceEnrollment;Tpm\n");
  wprintf(L"      * Please find all possible areas in registry under:\n");
  wprintf(L"          HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MdmDiagnostics\\Area\n");
  wprintf(L"      eg: %ws -area Autopilot;Tpm -cab c:\\temp\\AutopilotDiag.cab\n", a1);
  wprintf(L"\n");
  wprintf(L"  Usage3: %ws -area <area name(s)> -zip <output zip file path>\n", a1);
  wprintf(
    L"      * Collect predefined area logs and create a log zip to given zip file. Areas supported are the same as Usage2 "
     "for creating cab\n");
  wprintf(L"\n");
  wprintf(
    L"  Usage4: %ws -xml <xml file of information to gather> -zip <output zip file path> -server <MDM Server to alert>\n",
    a1);
  wprintf(L"      * Collect information specified in the xml and create a log zip to given zip file. \n");
  wprintf(L"\n");
  wprintf(L"  Usage5: %ws -clean\n", a1);
  wprintf(L"      * Cleans up all the diagnostic log files collected. \n");
  wprintf(L"\n");
}

```

## disassembly

```asm
0x140004048  mov     [rsp+arg_0], rbx
0x14000404d  push    rdi
0x14000404e  sub     rsp, 20h
0x140004052  mov     rbx, rcx
0x140004055  lea     rdi, Format; "\n"
0x14000405c  mov     rcx, rdi; Format
0x14000405f  call    cs:__imp_wprintf
0x140004066  nop     dword ptr [rax+rax+00h]
0x14000406b  mov     rdx, rbx
0x14000406e  lea     rcx, aUsage1WsOutOut; "  Usage1: %ws -out <output folder path>"...
0x140004075  call    cs:__imp_wprintf
0x14000407c  nop     dword ptr [rax+rax+00h]
0x140004081  lea     rcx, aOutputMdmDiagn; "      * Output MDM diagnostics info onl"...
0x140004088  call    cs:__imp_wprintf
0x14000408f  nop     dword ptr [rax+rax+00h]
0x140004094  mov     rdx, rbx
0x140004097  lea     rcx, aEgWsOutCTempOu; "      eg: %ws -out c:\\temp\\outputfold"...
0x14000409e  call    cs:__imp_wprintf
0x1400040a5  nop     dword ptr [rax+rax+00h]
0x1400040aa  mov     rcx, rdi; Format
0x1400040ad  call    cs:__imp_wprintf
0x1400040b4  nop     dword ptr [rax+rax+00h]
0x1400040b9  mov     rdx, rbx
0x1400040bc  lea     rcx, aUsage2WsAreaAr; "  Usage2: %ws -area <area name(s)> -cab"...
0x1400040c3  call    cs:__imp_wprintf
0x1400040ca  nop     dword ptr [rax+rax+00h]
0x1400040cf  lea     rcx, aCollectPredefi; "      * Collect predefined area logs an"...
0x1400040d6  call    cs:__imp_wprintf
0x1400040dd  nop     dword ptr [rax+rax+00h]
0x1400040e2  lea     rcx, aSupportedAreaN; "      * Supported area name example:\n"
0x1400040e9  call    cs:__imp_wprintf
0x1400040f0  nop     dword ptr [rax+rax+00h]
0x1400040f5  lea     rcx, aAutopilot; "          Autopilot\n"
0x1400040fc  call    cs:__imp_wprintf
0x140004103  nop     dword ptr [rax+rax+00h]
0x140004108  lea     rcx, aDeviceprovisio; "          DeviceProvisioning\n"
0x14000410f  call    cs:__imp_wprintf
0x140004116  nop     dword ptr [rax+rax+00h]
0x14000411b  lea     rcx, aTpm; "          Tpm\n"
0x140004122  call    cs:__imp_wprintf
0x140004129  nop     dword ptr [rax+rax+00h]
0x14000412e  lea     rcx, aItAlsoSupports; "      * It also supports multiple areas"...
0x140004135  call    cs:__imp_wprintf
0x14000413c  nop     dword ptr [rax+rax+00h]
0x140004141  lea     rcx, aAutopilotDevic; "          Autopilot;DeviceEnrollment;Tp"...
0x140004148  call    cs:__imp_wprintf
0x14000414f  nop     dword ptr [rax+rax+00h]
0x140004154  lea     rcx, aPleaseFindAllP; "      * Please find all possible areas "...
0x14000415b  call    cs:__imp_wprintf
0x140004162  nop     dword ptr [rax+rax+00h]
0x140004167  lea     rcx, aHkeyLocalMachi; "          HKEY_LOCAL_MACHINE\\SOFTWARE"...
0x14000416e  call    cs:__imp_wprintf
0x140004175  nop     dword ptr [rax+rax+00h]
0x14000417a  mov     rdx, rbx
0x14000417d  lea     rcx, aEgWsAreaAutopi; "      eg: %ws -area Autopilot;Tpm -cab "...
0x140004184  call    cs:__imp_wprintf
0x14000418b  nop     dword ptr [rax+rax+00h]
0x140004190  mov     rcx, rdi; Format
0x140004193  call    cs:__imp_wprintf
0x14000419a  nop     dword ptr [rax+rax+00h]
0x14000419f  mov     rdx, rbx
0x1400041a2  lea     rcx, aUsage3WsAreaAr; "  Usage3: %ws -area <area name(s)> -zip"...
0x1400041a9  call    cs:__imp_wprintf
0x1400041b0  nop     dword ptr [rax+rax+00h]
0x1400041b5  lea     rcx, aCollectPredefi_0; "      * Collect predefined area logs an"...
0x1400041bc  call    cs:__imp_wprintf
0x1400041c3  nop     dword ptr [rax+rax+00h]
0x1400041c8  mov     rcx, rdi; Format
0x1400041cb  call    cs:__imp_wprintf
0x1400041d2  nop     dword ptr [rax+rax+00h]
0x1400041d7  mov     rdx, rbx
0x1400041da  lea     rcx, aUsage4WsXmlXml; "  Usage4: %ws -xml <xml file of informa"...
0x1400041e1  call    cs:__imp_wprintf
0x1400041e8  nop     dword ptr [rax+rax+00h]
0x1400041ed  lea     rcx, aCollectInforma; "      * Collect information specified i"...
0x1400041f4  call    cs:__imp_wprintf
0x1400041fb  nop     dword ptr [rax+rax+00h]
0x140004200  mov     rcx, rdi; Format
0x140004203  call    cs:__imp_wprintf
0x14000420a  nop     dword ptr [rax+rax+00h]
0x14000420f  mov     rdx, rbx
0x140004212  lea     rcx, aUsage5WsClean; "  Usage5: %ws -clean\n"
0x140004219  call    cs:__imp_wprintf
0x140004220  nop     dword ptr [rax+rax+00h]
0x140004225  lea     rcx, aCleansUpAllThe; "      * Cleans up all the diagnostic lo"...
0x14000422c  call    cs:__imp_wprintf
0x140004233  nop     dword ptr [rax+rax+00h]
0x140004238  mov     rcx, rdi
0x14000423b  mov     rbx, [rsp+28h+arg_0]
0x140004240  add     rsp, 20h
0x140004244  pop     rdi
0x140004245  jmp     cs:__imp_wprintf
```
