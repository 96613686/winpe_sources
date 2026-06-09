# DisplayUsage(ushort const *)

- ea: `0x140003e94`
- end: `0x140004002`
- name: `?DisplayUsage@@YAXPEBG@Z`
- size: `366`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008130`

## import_xrefs

- `msvcrt!wprintf` at `0x140003eab`
- `msvcrt!wprintf` at `0x140003ebb`
- `msvcrt!wprintf` at `0x140003ec8`
- `msvcrt!wprintf` at `0x140003ed8`
- `msvcrt!wprintf` at `0x140003ee1`
- `msvcrt!wprintf` at `0x140003ef1`
- `msvcrt!wprintf` at `0x140003efe`
- `msvcrt!wprintf` at `0x140003f0b`
- `msvcrt!wprintf` at `0x140003f18`
- `msvcrt!wprintf` at `0x140003f25`
- `msvcrt!wprintf` at `0x140003f32`
- `msvcrt!wprintf` at `0x140003f3f`
- `msvcrt!wprintf` at `0x140003f4c`
- `msvcrt!wprintf` at `0x140003f59`
- `msvcrt!wprintf` at `0x140003f66`
- `msvcrt!wprintf` at `0x140003f76`
- `msvcrt!wprintf` at `0x140003f7f`
- `msvcrt!wprintf` at `0x140003f8f`
- `msvcrt!wprintf` at `0x140003f9c`
- `msvcrt!wprintf` at `0x140003fa5`
- `msvcrt!wprintf` at `0x140003fb5`
- `msvcrt!wprintf` at `0x140003fc2`
- `msvcrt!wprintf` at `0x140003fcb`
- `msvcrt!wprintf` at `0x140003fdb`
- `msvcrt!wprintf` at `0x140003fe8`
- `msvcrt!wprintf` at `0x140003eab`
- `msvcrt!wprintf` at `0x140003ebb`
- `msvcrt!wprintf` at `0x140003ec8`
- `msvcrt!wprintf` at `0x140003ed8`
- `msvcrt!wprintf` at `0x140003ee1`
- `msvcrt!wprintf` at `0x140003ef1`
- `msvcrt!wprintf` at `0x140003efe`
- `msvcrt!wprintf` at `0x140003f0b`
- `msvcrt!wprintf` at `0x140003f18`
- `msvcrt!wprintf` at `0x140003f25`
- `msvcrt!wprintf` at `0x140003f32`
- `msvcrt!wprintf` at `0x140003f3f`
- `msvcrt!wprintf` at `0x140003f4c`
- `msvcrt!wprintf` at `0x140003f59`
- `msvcrt!wprintf` at `0x140003f66`
- `msvcrt!wprintf` at `0x140003f76`
- `msvcrt!wprintf` at `0x140003f7f`
- `msvcrt!wprintf` at `0x140003f8f`
- `msvcrt!wprintf` at `0x140003f9c`
- `msvcrt!wprintf` at `0x140003fa5`
- `msvcrt!wprintf` at `0x140003fb5`
- `msvcrt!wprintf` at `0x140003fc2`
- `msvcrt!wprintf` at `0x140003fcb`
- `msvcrt!wprintf` at `0x140003fdb`
- `msvcrt!wprintf` at `0x140003fe8`
- `msvcrt!wprintf` at `0x140003ffb`

## string_xrefs

- `0x140003eb4`: `  Usage1: %ws -out <output folder path>\n`
- `0x140003ec1`: `      * Output MDM diagnostics info only to given folder path specified in -out parameter.\n`
- `0x140003ed1`: `      eg: %ws -out c:\temp\outputfolder\n`
- `0x140003eea`: `  Usage2: %ws -area <area name(s)> -cab <output cab file path>\n`
- `0x140003ef7`: `      * Collect predefined area logs and create a log cab to given cab file.\n`
- `0x140003f52`: `      * Please find all possible areas in registry under:\n`
- `0x140003f6f`: `      eg: %ws -area Autopilot;Tpm -cab c:\temp\AutopilotDiag.cab\n`
- `0x140003f88`: `  Usage3: %ws -area <area name(s)> -zip <output zip file path>\n`
- `0x140003f95`: `      * Collect predefined area logs and create a log zip to given zip file. Areas supported are the same as Usage2 for creating cab\n`
- `0x140003fae`: `  Usage4: %ws -xml <xml file of information to gather> -zip <output zip file path> -server <MDM Server to alert>\n`
- `0x140003fbb`: `      * Collect information specified in the xml and create a log zip to given zip file. \n`

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
0x140003e94  mov     [rsp+arg_0], rbx
0x140003e99  push    rdi
0x140003e9a  sub     rsp, 20h
0x140003e9e  mov     rbx, rcx
0x140003ea1  lea     rdi, Format; "\n"
0x140003ea8  mov     rcx, rdi; Format
0x140003eab  call    cs:__imp_wprintf
0x140003eb1  mov     rdx, rbx
0x140003eb4  lea     rcx, aUsage1WsOutOut; "  Usage1: %ws -out <output folder path>"...
0x140003ebb  call    cs:__imp_wprintf
0x140003ec1  lea     rcx, aOutputMdmDiagn; "      * Output MDM diagnostics info onl"...
0x140003ec8  call    cs:__imp_wprintf
0x140003ece  mov     rdx, rbx
0x140003ed1  lea     rcx, aEgWsOutCTempOu; "      eg: %ws -out c:\\temp\\outputfold"...
0x140003ed8  call    cs:__imp_wprintf
0x140003ede  mov     rcx, rdi; Format
0x140003ee1  call    cs:__imp_wprintf
0x140003ee7  mov     rdx, rbx
0x140003eea  lea     rcx, aUsage2WsAreaAr; "  Usage2: %ws -area <area name(s)> -cab"...
0x140003ef1  call    cs:__imp_wprintf
0x140003ef7  lea     rcx, aCollectPredefi; "      * Collect predefined area logs an"...
0x140003efe  call    cs:__imp_wprintf
0x140003f04  lea     rcx, aSupportedAreaN; "      * Supported area name example:\n"
0x140003f0b  call    cs:__imp_wprintf
0x140003f11  lea     rcx, aAutopilot; "          Autopilot\n"
0x140003f18  call    cs:__imp_wprintf
0x140003f1e  lea     rcx, aDeviceprovisio; "          DeviceProvisioning\n"
0x140003f25  call    cs:__imp_wprintf
0x140003f2b  lea     rcx, aTpm; "          Tpm\n"
0x140003f32  call    cs:__imp_wprintf
0x140003f38  lea     rcx, aItAlsoSupports; "      * It also supports multiple areas"...
0x140003f3f  call    cs:__imp_wprintf
0x140003f45  lea     rcx, aAutopilotDevic; "          Autopilot;DeviceEnrollment;Tp"...
0x140003f4c  call    cs:__imp_wprintf
0x140003f52  lea     rcx, aPleaseFindAllP; "      * Please find all possible areas "...
0x140003f59  call    cs:__imp_wprintf
0x140003f5f  lea     rcx, aHkeyLocalMachi; "          HKEY_LOCAL_MACHINE\\SOFTWARE"...
0x140003f66  call    cs:__imp_wprintf
0x140003f6c  mov     rdx, rbx
0x140003f6f  lea     rcx, aEgWsAreaAutopi; "      eg: %ws -area Autopilot;Tpm -cab "...
0x140003f76  call    cs:__imp_wprintf
0x140003f7c  mov     rcx, rdi; Format
0x140003f7f  call    cs:__imp_wprintf
0x140003f85  mov     rdx, rbx
0x140003f88  lea     rcx, aUsage3WsAreaAr; "  Usage3: %ws -area <area name(s)> -zip"...
0x140003f8f  call    cs:__imp_wprintf
0x140003f95  lea     rcx, aCollectPredefi_0; "      * Collect predefined area logs an"...
0x140003f9c  call    cs:__imp_wprintf
0x140003fa2  mov     rcx, rdi; Format
0x140003fa5  call    cs:__imp_wprintf
0x140003fab  mov     rdx, rbx
0x140003fae  lea     rcx, aUsage4WsXmlXml; "  Usage4: %ws -xml <xml file of informa"...
0x140003fb5  call    cs:__imp_wprintf
0x140003fbb  lea     rcx, aCollectInforma; "      * Collect information specified i"...
0x140003fc2  call    cs:__imp_wprintf
0x140003fc8  mov     rcx, rdi; Format
0x140003fcb  call    cs:__imp_wprintf
0x140003fd1  mov     rdx, rbx
0x140003fd4  lea     rcx, aUsage5WsClean; "  Usage5: %ws -clean\n"
0x140003fdb  call    cs:__imp_wprintf
0x140003fe1  lea     rcx, aCleansUpAllThe; "      * Cleans up all the diagnostic lo"...
0x140003fe8  call    cs:__imp_wprintf
0x140003fee  mov     rcx, rdi
0x140003ff1  mov     rbx, [rsp+28h+arg_0]
0x140003ff6  add     rsp, 20h
0x140003ffa  pop     rdi
0x140003ffb  jmp     cs:__imp_wprintf
```
