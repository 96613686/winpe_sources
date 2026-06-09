# NLG::COMDll::MapEntryPoints(void)

- ea: `0x1800525e0`
- end: `0x18005265a`
- name: `?MapEntryPoints@COMDll@NLG@@IEAA_NXZ`
- size: `122`
- prototype: `bool __fastcall(NLG::COMDll *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003b5c0`
- `0x18004e320`
- `0x18004ede0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800525f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005260c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052624`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005263c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800525f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005260c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052624`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005263c`

## string_xrefs

- `0x1800525e9`: `DllGetClassObject`
- `0x1800525fe`: `DllCanUnloadNow`
- `0x180052616`: `DllRegisterServer`
- `0x18005262e`: `DllUnregisterServer`

## pseudocode

```c
bool __fastcall NLG::COMDll::MapEntryPoints(HMODULE *this)
{
  FARPROC ProcAddress; // rax
  HMODULE v3; // rcx
  FARPROC v4; // rax
  HMODULE v5; // rcx
  FARPROC v6; // rax
  HMODULE v7; // rcx
  FARPROC v8; // rax
  bool v9; // zf

  ProcAddress = GetProcAddress(this[1], "DllGetClassObject");
  v3 = this[1];
  this[70] = (HMODULE)ProcAddress;
  v4 = GetProcAddress(v3, "DllCanUnloadNow");
  v5 = this[1];
  this[71] = (HMODULE)v4;
  v6 = GetProcAddress(v5, "DllRegisterServer");
  v7 = this[1];
  this[72] = (HMODULE)v6;
  v8 = GetProcAddress(v7, "DllUnregisterServer");
  v9 = this[70] == 0;
  this[73] = (HMODULE)v8;
  return !v9;
}

```

## disassembly

```asm
0x1800525e0  push    rbx
0x1800525e2  sub     rsp, 20h
0x1800525e6  mov     rbx, rcx
0x1800525e9  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x1800525f0  mov     rcx, [rcx+8]; hModule
0x1800525f4  call    cs:__imp_GetProcAddress
0x1800525fa  mov     rcx, [rbx+8]; hModule
0x1800525fe  lea     rdx, aDllcanunloadno_0; "DllCanUnloadNow"
0x180052605  mov     [rbx+230h], rax
0x18005260c  call    cs:__imp_GetProcAddress
0x180052612  mov     rcx, [rbx+8]; hModule
0x180052616  lea     rdx, aDllregisterser_0; "DllRegisterServer"
0x18005261d  mov     [rbx+238h], rax
0x180052624  call    cs:__imp_GetProcAddress
0x18005262a  mov     rcx, [rbx+8]; hModule
0x18005262e  lea     rdx, aDllunregisters_0; "DllUnregisterServer"
0x180052635  mov     [rbx+240h], rax
0x18005263c  call    cs:__imp_GetProcAddress
0x180052642  cmp     qword ptr [rbx+230h], 0
0x18005264a  mov     [rbx+248h], rax
0x180052651  setnz   al
0x180052654  add     rsp, 20h
0x180052658  pop     rbx
0x180052659  retn
```
