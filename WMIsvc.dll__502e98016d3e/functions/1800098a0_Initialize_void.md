# Initialize(void *)

- ea: `0x1800098a0`
- end: `0x1800099bf`
- name: `?Initialize@@YAHPEAX@Z`
- size: `287`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008510`

## callees

- `0x1800098a0`
- `0x1800099c8`
- `0x180009b18`
- `0x180009ba4`
- `0x180009c28`
- `0x180009ce8`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000992a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000992a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000994a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000994a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180009960`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800099b4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180009960`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800099b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800098ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800098ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800098ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800098ba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800098fb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800098fb`
- `wbemcomn!GetMemLogObject` at `0x1800098f0`
- `wbemcomn!GetMemLogObject` at `0x1800098f0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800098e4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800098e4`

## string_xrefs

- `0x180009921`: `wbemcore.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Initialize(void *a1)
{
  UINT v1; // eax
  void *v2; // rdx
  int ContextSwitcher; // ebx
  CMemoryLog *MemLogObject; // rax
  HMODULE v6; // rbx
  FARPROC ProcAddress; // rax
  _PROG_RESOURCES *v8; // rcx
  HMODULE phModule; // [rsp+30h] [rbp+8h] BYREF
  HMODULE v10; // [rsp+38h] [rbp+10h]

  if ( !a1 )
    return 0;
  v1 = SetErrorMode(0);
  SetErrorMode(v1 | 0x8001);
  if ( !(unsigned int)InitHotMofStuff((struct _PROG_RESOURCES *)&g_ProgRes)
    || !(unsigned int)_PROG_RESOURCES::Phase2Build((_PROG_RESOURCES *)&g_ProgRes, v2) )
  {
    return 0;
  }
  ContextSwitcher = CoInitializeEx(0, 0);
  if ( ContextSwitcher < 0 )
    goto LABEL_5;
  g_ProgRes = 1;
  phModule = 0;
  if ( GetModuleHandleExW(0, L"wbemcore.dll", &phModule) )
  {
    v6 = phModule;
    v10 = phModule;
    ProcAddress = GetProcAddress(phModule, "Reinitialize");
    if ( !ProcAddress )
    {
      FreeLibrary(v6);
      return 0;
    }
    ((void (__fastcall *)(_QWORD))ProcAddress)(0);
    FreeLibrary(v6);
  }
  ContextSwitcher = _PROG_RESOURCES::CreateContextSwitcher((LPVOID *)&g_ProgRes);
  if ( ContextSwitcher < 0 )
  {
LABEL_5:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, ContextSwitcher);
    return 0;
  }
  if ( !(unsigned int)_PROG_RESOURCES::RegisterLogin(v8)
    || !(unsigned int)_PROG_RESOURCES::RegisterBackup((_PROG_RESOURCES *)&g_ProgRes) )
  {
    return 0;
  }
  dword_180032CC8 = 4;
  return 1;
}

```

## disassembly

```asm
0x1800098a0  push    rbx
0x1800098a2  sub     rsp, 20h
0x1800098a6  test    rcx, rcx
0x1800098a9  jz      short loc_180009901
0x1800098ab  xor     ecx, ecx; uMode
0x1800098ad  call    cs:__imp_SetErrorMode
0x1800098b3  or      eax, 8001h
0x1800098b8  mov     ecx, eax; uMode
0x1800098ba  call    cs:__imp_SetErrorMode
0x1800098c0  lea     rcx, ?g_ProgRes@@3U_PROG_RESOURCES@@A; struct _PROG_RESOURCES *
0x1800098c7  call    ?InitHotMofStuff@@YAHPEAU_PROG_RESOURCES@@@Z; InitHotMofStuff(_PROG_RESOURCES *)
0x1800098cc  test    eax, eax
0x1800098ce  jz      short loc_180009901
0x1800098d0  lea     rcx, ?g_ProgRes@@3U_PROG_RESOURCES@@A; this
0x1800098d7  call    ?Phase2Build@_PROG_RESOURCES@@QEAAHPEAX@Z; _PROG_RESOURCES::Phase2Build(void *)
0x1800098dc  test    eax, eax
0x1800098de  jz      short loc_180009901
0x1800098e0  xor     edx, edx; dwCoInit
0x1800098e2  xor     ecx, ecx; pvReserved
0x1800098e4  call    cs:__imp_CoInitializeEx
0x1800098ea  mov     ebx, eax
0x1800098ec  test    eax, eax
0x1800098ee  jns     short loc_180009909
0x1800098f0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800098f6  mov     edx, ebx
0x1800098f8  mov     rcx, rax
0x1800098fb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009901  xor     eax, eax
0x180009903  add     rsp, 20h
0x180009907  pop     rbx
0x180009908  retn
0x180009909  mov     dword ptr cs:?g_ProgRes@@3U_PROG_RESOURCES@@A, 1; _PROG_RESOURCES g_ProgRes
0x180009913  mov     [rsp+28h+phModule], 0
0x18000991c  lea     r8, [rsp+28h+phModule]; phModule
0x180009921  lea     rdx, ModuleName; "wbemcore.dll"
0x180009928  xor     ecx, ecx; dwFlags
0x18000992a  call    cs:__imp_GetModuleHandleExW
0x180009930  test    eax, eax
0x180009932  jz      short loc_180009966
0x180009934  mov     rbx, [rsp+28h+phModule]
0x180009939  mov     [rsp+28h+arg_8], rbx
0x18000993e  lea     rdx, ProcName; "Reinitialize"
0x180009945  mov     rcx, [rsp+28h+phModule]; hModule
0x18000994a  call    cs:__imp_GetProcAddress
0x180009950  test    rax, rax
0x180009953  jz      short loc_1800099B1
0x180009955  xor     ecx, ecx
0x180009957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000995c  nop
0x18000995d  mov     rcx, rbx; hLibModule
0x180009960  call    cs:__imp_FreeLibrary
0x180009966  lea     rcx, ?g_ProgRes@@3U_PROG_RESOURCES@@A; this
0x18000996d  call    ?CreateContextSwitcher@_PROG_RESOURCES@@QEAAJXZ; _PROG_RESOURCES::CreateContextSwitcher(void)
0x180009972  mov     ebx, eax
0x180009974  test    eax, eax
0x180009976  js      loc_1800098F0
0x18000997c  call    ?RegisterLogin@_PROG_RESOURCES@@QEAAHXZ; _PROG_RESOURCES::RegisterLogin(void)
0x180009981  test    eax, eax
0x180009983  jz      loc_180009901
0x180009989  lea     rcx, ?g_ProgRes@@3U_PROG_RESOURCES@@A; this
0x180009990  call    ?RegisterBackup@_PROG_RESOURCES@@QEAAHXZ; _PROG_RESOURCES::RegisterBackup(void)
0x180009995  test    eax, eax
0x180009997  jz      loc_180009901
0x18000999d  mov     cs:dword_180032CC8, 4
0x1800099a7  mov     eax, 1
0x1800099ac  jmp     loc_180009903
0x1800099b1  mov     rcx, rbx; hLibModule
0x1800099b4  call    cs:__imp_FreeLibrary
0x1800099ba  jmp     loc_180009901
```
