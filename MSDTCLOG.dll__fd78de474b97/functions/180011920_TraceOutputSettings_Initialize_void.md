# TraceOutputSettings::Initialize(void *)

- ea: `0x180011920`
- end: `0x1800119e0`
- name: `?Initialize@TraceOutputSettings@@SAKPEAX@Z`
- size: `192`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001210`

## callees

- `0x180011920`
- `0x1800119e8`
- `0x1800127e6`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800119d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001441d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800119d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001441d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011936`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011936`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001196d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001196d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001198b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001198b`

## string_xrefs

- `0x180011984`: `Unable to open MSDTC\Tracing settings key\n`

## pseudocode

```c
__int64 __fastcall TraceOutputSettings::Initialize(void *a1)
{
  LSTATUS v1; // ebx
  __int64 v3; // [rsp+0h] [rbp-48h] BYREF
  __int64 *v4; // [rsp+30h] [rbp-18h]
  unsigned int v5; // [rsp+50h] [rbp+8h]

  v4 = &v3;
  EnterCriticalSection(&stru_18001FA50);
  if ( TraceOutputSettings::fInitialized )
    goto LABEL_8;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\MSDTC\\Tracing",
         0,
         0x20119u,
         &TraceOutputSettings::hkConfiguration);
  if ( !v1 )
  {
    TraceOutputSettings::ReadConfiguration_Locked();
    TraceOutputSettings::fInitialized = 1;
LABEL_8:
    LeaveCriticalSection(&stru_18001FA50);
    return 0;
  }
  TraceOutputSettings::hkConfiguration = 0;
  OutputDebugStringW(L"Unable to open MSDTC\\Tracing settings key\n");
  if ( v1 > 0 )
    v5 = (unsigned __int16)v1 | 0x80070000;
  else
    v5 = v1;
  local_unwind_0(v4, &loc_1800119B9);
  return v5;
}

```

## disassembly

```asm
0x180011920  mov     [rsp+arg_0], rcx
0x180011925  push    rbx
0x180011926  sub     rsp, 40h
0x18001192a  mov     [rsp+48h+var_18], rsp
0x18001192f  lea     rcx, stru_18001FA50; lpCriticalSection
0x180011936  call    cs:__imp_EnterCriticalSection
0x18001193c  nop
0x18001193d  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, 0; bool TraceOutputSettings::fInitialized
0x180011944  jnz     loc_1800119CF
0x18001194a  lea     rax, ?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; HKEY__ * TraceOutputSettings::hkConfiguration
0x180011951  mov     [rsp+48h+phkResult], rax; phkResult
0x180011956  mov     r9d, 20119h; samDesired
0x18001195c  xor     r8d, r8d; ulOptions
0x18001195f  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\MSDTC\\Tracing"
0x180011966  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001196d  call    cs:__imp_RegOpenKeyExW
0x180011973  mov     ebx, eax
0x180011975  test    eax, eax
0x180011977  jz      short loc_1800119C3
0x180011979  mov     cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA, 0; HKEY__ * TraceOutputSettings::hkConfiguration
0x180011984  lea     rcx, aUnableToOpenMs; "Unable to open MSDTC\\Tracing settings "...
0x18001198b  call    cs:__imp_OutputDebugStringW
0x180011991  test    ebx, ebx
0x180011993  jg      short loc_18001199B
0x180011995  mov     dword ptr [rsp+48h+arg_0], ebx
0x180011999  jmp     short loc_1800119A7
0x18001199b  movzx   eax, bx
0x18001199e  or      eax, 80070000h
0x1800119a3  mov     dword ptr [rsp+48h+arg_0], eax
0x1800119a7  lea     rdx, loc_1800119B9
0x1800119ae  mov     rcx, [rsp+48h+var_18]
0x1800119b3  call    _local_unwind_0
0x1800119b8  nop
0x1800119b9  mov     eax, dword ptr [rsp+48h+arg_0]
0x1800119bd  add     rsp, 40h
0x1800119c1  pop     rbx
0x1800119c2  retn
0x1800119c3  call    ?ReadConfiguration_Locked@TraceOutputSettings@@CAXXZ; TraceOutputSettings::ReadConfiguration_Locked(void)
0x1800119c8  mov     cs:?fInitialized@TraceOutputSettings@@0_NA, 1; bool TraceOutputSettings::fInitialized
0x1800119cf  lea     rcx, stru_18001FA50; lpCriticalSection
0x1800119d6  call    cs:__imp_LeaveCriticalSection
0x1800119dc  xor     eax, eax
0x1800119de  jmp     short loc_1800119BD
0x18001440d  push    rbp
0x18001440f  sub     rsp, 30h
0x180014413  mov     rbp, rdx
0x180014416  lea     rcx, stru_18001FA50; lpCriticalSection
0x18001441d  call    cs:__imp_LeaveCriticalSection
0x180014423  nop
0x180014424  add     rsp, 30h
0x180014428  pop     rbp
0x180014429  retn
```
