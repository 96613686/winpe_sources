# BthEnumCheckGuidAgainstRegistry

- ea: `0x14001df2c`
- end: `0x14001e02e`
- name: `BthEnumCheckGuidAgainstRegistry`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x14001e1e0`

## callees

- `0x1400013e8`
- `0x14000337c`
- `0x140007d00`
- `0x140008140`
- `0x14001df2c`
- `0x14001f520`
- `0x14001f6e4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14001e007`
- `ntoskrnl!ZwClose` at `0x14001e007`

## string_xrefs

- `0x14001df6f`: `\Registry\Machine\System\CurrentControlSet\Services\BTHPORT\Parameters\HciBypassServices`

## pseudocode

```c
NTSTATUS BthEnumCheckGuidAgainstRegistry()
{
  __int64 v0; // rcx
  NTSTATUS result; // eax
  int v2; // ebx
  int v3; // edx
  int KeyValueUlong; // edi
  int v5; // [rsp+28h] [rbp-61h]
  int v6; // [rsp+30h] [rbp-59h]
  HANDLE Handle; // [rsp+38h] [rbp-51h] BYREF
  WCHAR SourceString[48]; // [rsp+40h] [rbp-49h] BYREF
  int v9; // [rsp+A8h] [rbp+1Fh]

  memset(SourceString, 0, 0x5Eu);
  Handle = 0;
  v6 = 0;
  result = BthOpenKey(
             v0,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\BTHPORT\\Parameters\\HciBypassServices",
             &Handle);
  if ( result >= 0 )
  {
    v2 = 0;
    while ( 1 )
    {
      GS_Init(SourceString);
      v9 = 4;
      KeyValueUlong = BthQueryKeyValueUlong(Handle);
      if ( KeyValueUlong < 0 )
        break;
      if ( ++v2 )
        goto LABEL_8;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v5 = KeyValueUlong;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v3,
        3,
        40,
        (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids,
        v5,
        v6);
    }
LABEL_8:
    ZwClose(Handle);
    return KeyValueUlong;
  }
  return result;
}

```

## disassembly

```asm
0x14001df2c  push    rbp
0x14001df2e  push    rbx
0x14001df2f  push    rsi
0x14001df30  push    rdi
0x14001df31  lea     rbp, [rsp-3Fh]
0x14001df36  sub     rsp, 0C8h
0x14001df3d  mov     rax, cs:__security_cookie
0x14001df44  xor     rax, rsp
0x14001df47  mov     [rbp+57h+var_28], rax
0x14001df4b  xor     eax, eax
0x14001df4d  mov     rsi, rcx
0x14001df50  xor     edx, edx; Val
0x14001df52  mov     [rbp+57h+var_52], ax
0x14001df56  lea     rcx, [rbp+57h+SourceString]; void *
0x14001df5a  lea     r8d, [rax+5Eh]; Size
0x14001df5e  call    memset
0x14001df63  lea     r8, [rbp+57h+Handle]
0x14001df67  mov     [rbp+57h+Handle], 0
0x14001df6f  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14001df76  mov     [rbp+57h+var_B0], 0
0x14001df7d  call    BthOpenKey
0x14001df82  test    eax, eax
0x14001df84  js      loc_14001E015
0x14001df8a  xor     ebx, ebx
0x14001df8c  mov     edx, ebx
0x14001df8e  lea     rcx, [rbp+57h+SourceString]; SourceString
0x14001df92  shl     rdx, 4
0x14001df96  add     rdx, rsi
0x14001df99  call    GS_Init
0x14001df9e  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001dfa2  lea     r9, [rbp+57h+var_B0]
0x14001dfa6  lea     r8, [rbp+57h+var_40]
0x14001dfaa  mov     [rbp+57h+var_38], 4
0x14001dfb1  lea     rdx, [rbp+57h+SourceString]
0x14001dfb5  call    BthQueryKeyValueUlong
0x14001dfba  mov     edi, eax
0x14001dfbc  test    eax, eax
0x14001dfbe  js      short loc_14001DFC9
0x14001dfc0  inc     ebx
0x14001dfc2  cmp     ebx, 1
0x14001dfc5  jb      short loc_14001DF8C
0x14001dfc7  jmp     short loc_14001E003
0x14001dfc9  lea     rax, WPP_RECORDER_INITIALIZED
0x14001dfd0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001dfd7  jz      short loc_14001E003
0x14001dfd9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dfe0  lea     rax, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x14001dfe7  mov     r9d, 28h ; '('
0x14001dfed  mov     [rsp+0E0h+var_B8], edi
0x14001dff1  mov     [rsp+0E0h+var_C0], rax
0x14001dff6  mov     rcx, [rcx+40h]
0x14001dffa  lea     r8d, [r9-25h]
0x14001dffe  call    WPP_RECORDER_SF_d
0x14001e003  mov     rcx, [rbp+57h+Handle]; Handle
0x14001e007  call    cs:__imp_ZwClose
0x14001e00e  nop     dword ptr [rax+rax+00h]
0x14001e013  mov     eax, edi
0x14001e015  mov     rcx, [rbp+57h+var_28]
0x14001e019  xor     rcx, rsp; StackCookie
0x14001e01c  call    __security_check_cookie
0x14001e021  add     rsp, 0C8h
0x14001e028  pop     rdi
0x14001e029  pop     rsi
0x14001e02a  pop     rbx
0x14001e02b  pop     rbp
0x14001e02c  retn
```
