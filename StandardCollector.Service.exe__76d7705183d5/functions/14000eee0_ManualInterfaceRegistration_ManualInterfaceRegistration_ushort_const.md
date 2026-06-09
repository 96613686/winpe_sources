# ManualInterfaceRegistration::ManualInterfaceRegistration(ushort const *)

- ea: `0x14000eee0`
- end: `0x14000eff1`
- name: `??0ManualInterfaceRegistration@@QEAA@PEBG@Z`
- size: `273`
- prototype: `ManualInterfaceRegistration *__fastcall(ManualInterfaceRegistration *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000edcc`

## callees

- `0x14000eee0`
- `0x140014c70`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000ef3c`
- `KERNEL32!GetProcAddress` at `0x14000ef93`
- `KERNEL32!GetProcAddress` at `0x14000ef3c`
- `KERNEL32!GetProcAddress` at `0x14000ef93`
- `KERNEL32!LoadLibraryExW` at `0x14000ef20`
- `KERNEL32!LoadLibraryExW` at `0x14000ef77`
- `KERNEL32!LoadLibraryExW` at `0x14000ef20`
- `KERNEL32!LoadLibraryExW` at `0x14000ef77`
- `KERNEL32!GetLastError` at `0x14000ef4e`
- `KERNEL32!GetLastError` at `0x14000efa5`
- `KERNEL32!GetLastError` at `0x14000ef4e`
- `KERNEL32!GetLastError` at `0x14000efa5`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x14000efc1`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x14000efc1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ManualInterfaceRegistration *__fastcall ManualInterfaceRegistration::ManualInterfaceRegistration(
        ManualInterfaceRegistration *this,
        const unsigned __int16 *a2)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v6; // rax
  FARPROC v7; // rax
  void (*v8)(void); // rax

  *(_QWORD *)this = &ManualInterfaceRegistration::`vftable';
  *((_BYTE *)this + 8) = 1;
  *((_QWORD *)this + 67) = 0;
  *((_DWORD *)this + 136) = 0;
  Library = LoadLibraryExW(a2, 0, 0);
  *((_QWORD *)this + 69) = Library;
  if ( !Library
    || (ProcAddress = GetProcAddress(Library, "ManualRegisterInterfaces"), (*((_QWORD *)this + 67) = ProcAddress) == 0) )
  {
    *((_DWORD *)this + 136) = GetLastError();
  }
  *((_QWORD *)this + 70) = 0;
  *((_DWORD *)this + 142) = 0;
  v6 = LoadLibraryExW(a2, 0, 0);
  *((_QWORD *)this + 72) = v6;
  if ( !v6 || (v7 = GetProcAddress(v6, "ManualUnregisterInterfaces"), (*((_QWORD *)this + 70) = v7) == 0) )
    *((_DWORD *)this + 142) = GetLastError();
  wcsncpy_s((wchar_t *)this + 5, 0x105u, a2, 0xFFFFFFFFFFFFFFFFuLL);
  if ( !*((_DWORD *)this + 136) )
  {
    v8 = (void (*)(void))*((_QWORD *)this + 67);
    if ( v8 )
      v8();
  }
  return this;
}

```

## disassembly

```asm
0x14000eee0  mov     [rsp+arg_8], rbx
0x14000eee5  mov     [rsp+arg_0], rcx
0x14000eeea  push    rdi
0x14000eeeb  sub     rsp, 20h
0x14000eeef  mov     rdi, rdx
0x14000eef2  mov     rbx, rcx
0x14000eef5  lea     rax, ??_7ManualInterfaceRegistration@@6B@; const ManualInterfaceRegistration::`vftable'
0x14000eefc  mov     [rcx], rax
0x14000eeff  mov     byte ptr [rcx+8], 1
0x14000ef03  mov     qword ptr [rcx+218h], 0
0x14000ef0e  mov     dword ptr [rcx+220h], 0
0x14000ef18  xor     r8d, r8d; dwFlags
0x14000ef1b  xor     edx, edx; hFile
0x14000ef1d  mov     rcx, rdi; lpLibFileName
0x14000ef20  call    cs:__imp_LoadLibraryExW
0x14000ef26  mov     [rbx+228h], rax
0x14000ef2d  test    rax, rax
0x14000ef30  jz      short loc_14000EF4E
0x14000ef32  lea     rdx, aManualregister; "ManualRegisterInterfaces"
0x14000ef39  mov     rcx, rax; hModule
0x14000ef3c  call    cs:__imp_GetProcAddress
0x14000ef42  mov     [rbx+218h], rax
0x14000ef49  test    rax, rax
0x14000ef4c  jnz     short loc_14000EF5A
0x14000ef4e  call    cs:__imp_GetLastError
0x14000ef54  mov     [rbx+220h], eax
0x14000ef5a  mov     qword ptr [rbx+230h], 0
0x14000ef65  mov     dword ptr [rbx+238h], 0
0x14000ef6f  xor     r8d, r8d; dwFlags
0x14000ef72  xor     edx, edx; hFile
0x14000ef74  mov     rcx, rdi; lpLibFileName
0x14000ef77  call    cs:__imp_LoadLibraryExW
0x14000ef7d  mov     [rbx+240h], rax
0x14000ef84  test    rax, rax
0x14000ef87  jz      short loc_14000EFA5
0x14000ef89  lea     rdx, aManualunregist; "ManualUnregisterInterfaces"
0x14000ef90  mov     rcx, rax; hModule
0x14000ef93  call    cs:__imp_GetProcAddress
0x14000ef99  mov     [rbx+230h], rax
0x14000efa0  test    rax, rax
0x14000efa3  jnz     short loc_14000EFB1
0x14000efa5  call    cs:__imp_GetLastError
0x14000efab  mov     [rbx+238h], eax
0x14000efb1  lea     rcx, [rbx+0Ah]; Destination
0x14000efb5  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000efb9  mov     r8, rdi; Source
0x14000efbc  mov     edx, 105h; SizeInWords
0x14000efc1  call    cs:__imp_wcsncpy_s
0x14000efc7  cmp     dword ptr [rbx+220h], 0
0x14000efce  jnz     short loc_14000EFE3
0x14000efd0  mov     rax, [rbx+218h]
0x14000efd7  test    rax, rax
0x14000efda  jz      short loc_14000EFE3
0x14000efdc  call    cs:__guard_dispatch_icall_fptr
0x14000efe2  nop
0x14000efe3  mov     rax, rbx
0x14000efe6  mov     rbx, [rsp+28h+arg_8]
0x14000efeb  add     rsp, 20h
0x14000efef  pop     rdi
0x14000eff0  retn
```
