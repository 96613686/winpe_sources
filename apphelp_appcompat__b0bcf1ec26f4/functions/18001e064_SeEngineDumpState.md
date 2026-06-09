# SeEngineDumpState

- ea: `0x18001e064`
- end: `0x18001e190`
- name: `SeEngineDumpState`
- size: `300`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001c580`
- `0x180053290`

## callees

- `0x180008068`
- `0x18001e064`
- `0x180056c34`
- `0x180056f50`
- `0x180057a8c`
- `0x180057c10`
- `0x180057cec`
- `0x180059270`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e0c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e0c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001e0b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001e0b7`

## string_xrefs

- `0x18001e0df`: ` xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"`
- `0x18001e0f7`: ` xmlns="urn:schemas.microsoft.com/appcompat/2010/03/shimengstate">\n`
- `0x18001e0eb`: ` xsi:schemaLocation="urn:schemas.microsoft.com/appcompat/2010/03/shimengstate EngineState.xsd"`

## pseudocode

```c
struct _ASL_LOG *SeEngineDumpState()
{
  struct _ASL_LOG *result; // rax
  _QWORD *v1; // rbx
  __int64 v2; // r9
  __int64 v3; // r8
  __int64 v4; // rdx
  __int64 v5; // rcx
  WCHAR Filename[264]; // [rsp+20h] [rbp-228h] BYREF

  result = g_StateLog;
  if ( g_StateLog )
  {
    result = *(struct _ASL_LOG **)g_StateLog;
    if ( (*(_BYTE *)(*(_QWORD *)g_StateLog + 80LL) & 5) != 0 )
    {
      v1 = (_QWORD *)g_Engine;
      Filename[0] = 0;
      if ( !GetModuleFileNameW(0, Filename, 0x104u) )
        Filename[0] = 0;
      GetCurrentProcessId();
      SeStatePrintf("<SHIMENGSTATE PID=\"%ld\" FILENAME=\"%S\"");
      SeStatePrintf(" xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\"");
      SeStatePrintf(" xsi:schemaLocation=\"urn:schemas.microsoft.com/appcompat/2010/03/shimengstate EngineState.xsd\"");
      SeStatePrintf(" xmlns=\"urn:schemas.microsoft.com/appcompat/2010/03/shimengstate\">\r\n");
      ++g_StateIndent;
      SepEngineDumpCompatEnvironment();
      SeInExDumpState(*(_QWORD *)(v1[3] + 48LL));
      SeStatePrintf("<FIXES>\r\n");
      v2 = v1[7];
      v3 = v1[4];
      v4 = v1[3];
      v5 = v1[2];
      ++g_StateIndent;
      SeShimManagerDumpState(v5, v4, v3, v2);
      SeFlagManagerDumpState(*v1);
      SeQuirkManagerDumpState(v1[1]);
      --g_StateIndent;
      SeStatePrintf("</FIXES>\r\n");
      --g_StateIndent;
      return (struct _ASL_LOG *)SeStatePrintf("</SHIMENGSTATE>\r\n");
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001e064  push    rbx
0x18001e066  sub     rsp, 240h
0x18001e06d  mov     rax, cs:__security_cookie
0x18001e074  xor     rax, rsp
0x18001e077  mov     [rsp+248h+var_18], rax
0x18001e07f  mov     rax, cs:g_StateLog
0x18001e086  test    rax, rax
0x18001e089  jz      loc_18001E177
0x18001e08f  mov     rax, [rax]
0x18001e092  test    byte ptr [rax+50h], 5
0x18001e096  jz      loc_18001E177
0x18001e09c  mov     rbx, cs:g_Engine
0x18001e0a3  lea     rdx, [rsp+248h+Filename]; lpFilename
0x18001e0a8  xor     eax, eax
0x18001e0aa  mov     r8d, 104h; nSize
0x18001e0b0  xor     ecx, ecx; hModule
0x18001e0b2  mov     [rsp+248h+Filename], ax
0x18001e0b7  call    cs:__imp_GetModuleFileNameW
0x18001e0bd  test    eax, eax
0x18001e0bf  jnz     short loc_18001E0C6
0x18001e0c1  mov     [rsp+248h+Filename], ax
0x18001e0c6  call    cs:__imp_GetCurrentProcessId
0x18001e0cc  mov     edx, eax
0x18001e0ce  lea     r8, [rsp+248h+Filename]
0x18001e0d3  lea     rcx, aShimengstatePi; "<SHIMENGSTATE PID=\"%ld\" FILENAME=\"%S"...
0x18001e0da  call    SeStatePrintf
0x18001e0df  lea     rcx, aXmlnsXsiHttpWw; " xmlns:xsi=\"http://www.w3.org/2001/XML"...
0x18001e0e6  call    SeStatePrintf
0x18001e0eb  lea     rcx, aXsiSchemalocat; " xsi:schemaLocation=\"urn:schemas.micro"...
0x18001e0f2  call    SeStatePrintf
0x18001e0f7  lea     rcx, aXmlnsUrnSchema; " xmlns=\"urn:schemas.microsoft.com/appc"...
0x18001e0fe  call    SeStatePrintf
0x18001e103  inc     cs:g_StateIndent
0x18001e109  call    SepEngineDumpCompatEnvironment
0x18001e10e  mov     rcx, [rbx+18h]
0x18001e112  mov     rcx, [rcx+30h]
0x18001e116  call    SeInExDumpState
0x18001e11b  lea     rcx, aFixes; "<FIXES>\r\n"
0x18001e122  call    SeStatePrintf
0x18001e127  mov     r9, [rbx+38h]
0x18001e12b  mov     r8, [rbx+20h]
0x18001e12f  mov     rdx, [rbx+18h]
0x18001e133  mov     rcx, [rbx+10h]
0x18001e137  inc     cs:g_StateIndent
0x18001e13d  call    SeShimManagerDumpState
0x18001e142  mov     rcx, [rbx]
0x18001e145  call    SeFlagManagerDumpState
0x18001e14a  mov     rcx, [rbx+8]
0x18001e14e  call    SeQuirkManagerDumpState
0x18001e153  dec     cs:g_StateIndent
0x18001e159  lea     rcx, aFixes_0; "</FIXES>\r\n"
0x18001e160  call    SeStatePrintf
0x18001e165  dec     cs:g_StateIndent
0x18001e16b  lea     rcx, aShimengstate; "</SHIMENGSTATE>\r\n"
0x18001e172  call    SeStatePrintf
0x18001e177  mov     rcx, [rsp+248h+var_18]
0x18001e17f  xor     rcx, rsp; StackCookie
0x18001e182  call    __security_check_cookie
0x18001e187  add     rsp, 240h
0x18001e18e  pop     rbx
0x18001e18f  retn
```
