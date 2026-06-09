# CUITrace::DoesTraceDirectoryExist(void)

- ea: `0x1800987fc`
- end: `0x180098916`
- name: `?DoesTraceDirectoryExist@CUITrace@@AEAAJXZ`
- size: `282`
- prototype: `__int64 __fastcall(CUITrace *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007ba8`

## callees

- `0x1800063b0`
- `0x180008a50`
- `0x18001d268`
- `0x1800987fc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180098872`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180098872`

## string_xrefs

- `0x180098828`: `com\complus\dtc\dtc\trace\src\uitrace.cpp`
- `0x1800988bf`: `com\complus\dtc\dtc\trace\src\uitrace.cpp`
- `0x1800988e6`: `com\complus\dtc\dtc\trace\src\uitrace.cpp`
- `0x18009889f`: `Either the TraceDirectory does not exist or could not access it`
- `0x180098883`: `TraceDirectory already exists`
- `0x180098819`: `CUITrace::DoesTraceDirectoryExist`

## pseudocode

```c
__int64 __fastcall CUITrace::DoesTraceDirectoryExist(CUITrace *this)
{
  unsigned __int16 *DefaultLogPath; // rax
  DWORD FileAttributesW; // eax
  unsigned int v3; // ebx
  __int64 v5; // [rsp+28h] [rbp-20h]

  TraceStringInline(
    14,
    6,
    L"com\\complus\\dtc\\dtc\\trace\\src\\uitrace.cpp",
    130,
    L"CUITrace::DoesTraceDirectoryExist",
    0,
    L"In");
  DefaultLogPath = GetDefaultLogPath();
  StringCchPrintfW(&word_18015D4F8, 0x304u, L"%s\\%s", DefaultLogPath, L"trace");
  FileAttributesW = GetFileAttributesW(&word_18015D4F8);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    v3 = -2147467259;
    LODWORD(v5) = -2147467259;
    TraceStringInline(
      14,
      1,
      L"com\\complus\\dtc\\dtc\\trace\\src\\uitrace.cpp",
      147,
      L"CUITrace::DoesTraceDirectoryExist",
      v5,
      L"Either the TraceDirectory does not exist or could not access it");
  }
  else
  {
    v3 = 0;
    TraceStringInline(
      14,
      3,
      L"com\\complus\\dtc\\dtc\\trace\\src\\uitrace.cpp",
      141,
      L"CUITrace::DoesTraceDirectoryExist",
      0,
      L"TraceDirectory already exists");
  }
  TraceStringInline(
    14,
    6,
    L"com\\complus\\dtc\\dtc\\trace\\src\\uitrace.cpp",
    152,
    L"CUITrace::DoesTraceDirectoryExist",
    0,
    L"Out");
  return v3;
}

```

## disassembly

```asm
0x1800987fc  mov     r11, rsp
0x1800987ff  mov     [r11+8], rbx
0x180098803  push    rbp
0x180098804  sub     rsp, 40h
0x180098808  mov     r9d, 82h
0x18009880e  lea     rax, aIn_0; "In"
0x180098815  mov     [r11-18h], rax
0x180098819  lea     rbp, aCuitraceDoestr; "CUITrace::DoesTraceDirectoryExist"
0x180098820  mov     qword ptr [r11-20h], 0
0x180098828  lea     r8, aComComplusDtcD_23; "com\\complus\\dtc\\dtc\\trace\\src\\uit"...
0x18009882f  mov     [r11-28h], rbp
0x180098833  lea     edx, [r9-7Ch]
0x180098837  lea     ecx, [rdx+8]
0x18009883a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009883f  call    ?GetDefaultLogPath@@YAPEAGXZ; GetDefaultLogPath(void)
0x180098844  lea     rcx, aTrace; "trace"
0x18009884b  mov     r9, rax
0x18009884e  mov     [rsp+48h+var_28], rcx
0x180098853  lea     r8, aSS_1; "%s\\%s"
0x18009885a  lea     rcx, word_18015D4F8; unsigned __int16 *
0x180098861  mov     edx, 304h; unsigned __int64
0x180098866  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009886b  lea     rcx, word_18015D4F8; lpFileName
0x180098872  call    cs:__imp_GetFileAttributesW
0x180098878  cmp     eax, 0FFFFFFFFh
0x18009887b  jz      short loc_18009889F
0x18009887d  test    al, 10h
0x18009887f  jz      short loc_18009889F
0x180098881  xor     ebx, ebx
0x180098883  lea     rax, aTracedirectory; "TraceDirectory already exists"
0x18009888a  mov     [rsp+48h+var_18], rax
0x18009888f  mov     r9d, 8Dh
0x180098895  mov     [rsp+48h+var_20], rbx
0x18009889a  lea     edx, [rbx+3]
0x18009889d  jmp     short loc_1800988BF
0x18009889f  lea     rax, aEitherTheTrace; "Either the TraceDirectory does not exis"...
0x1800988a6  mov     ebx, 80004005h
0x1800988ab  mov     [rsp+48h+var_18], rax
0x1800988b0  mov     r9d, 93h
0x1800988b6  mov     dword ptr [rsp+48h+var_20], ebx
0x1800988ba  mov     edx, 1
0x1800988bf  lea     r8, aComComplusDtcD_23; "com\\complus\\dtc\\dtc\\trace\\src\\uit"...
0x1800988c6  mov     [rsp+48h+var_28], rbp
0x1800988cb  mov     ecx, 0Eh
0x1800988d0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800988d5  mov     edx, 6
0x1800988da  lea     rax, aOut; "Out"
0x1800988e1  mov     [rsp+48h+var_18], rax
0x1800988e6  lea     r8, aComComplusDtcD_23; "com\\complus\\dtc\\dtc\\trace\\src\\uit"...
0x1800988ed  mov     [rsp+48h+var_20], 0
0x1800988f6  mov     r9d, 98h
0x1800988fc  mov     [rsp+48h+var_28], rbp
0x180098901  lea     ecx, [rdx+8]
0x180098904  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180098909  mov     eax, ebx
0x18009890b  mov     rbx, [rsp+48h+arg_0]
0x180098910  add     rsp, 40h
0x180098914  pop     rbp
0x180098915  retn
```
