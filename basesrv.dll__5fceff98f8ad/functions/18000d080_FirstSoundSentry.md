# FirstSoundSentry

- ea: `0x18000d080`
- end: `0x18000d110`
- name: `FirstSoundSentry`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000d080`
- `0x18000e010`

## import_xrefs

- `ntdll!LdrGetDllHandle` at `0x18000d0ce`
- `ntdll!LdrGetDllHandle` at `0x18000d0ce`
- `ntdll!LdrGetProcedureAddress` at `0x18000d0ed`
- `ntdll!LdrGetProcedureAddress` at `0x18000d0ed`

## pseudocode

```c
__int64 FirstSoundSentry()
{
  struct _UNICODE_STRING DllName; // [rsp+20h] [rbp-20h] BYREF
  struct _STRING Name; // [rsp+30h] [rbp-10h] BYREF
  PVOID DllHandle; // [rsp+50h] [rbp+10h] BYREF
  PVOID ProcedureAddress; // [rsp+58h] [rbp+18h] BYREF

  *(_QWORD *)&DllName.Length = 917516;
  DllName.Buffer = (PWSTR)L"user32";
  *(_QWORD *)&Name.Length = 786443;
  Name.Buffer = "SoundSentry";
  DllHandle = 0;
  ProcedureAddress = FailSoundSentry;
  if ( LdrGetDllHandle(0, 0, &DllName, &DllHandle) >= 0 )
    LdrGetProcedureAddress(DllHandle, &Name, 0, &ProcedureAddress);
  UserSoundSentry = (__int64 (__fastcall *)())ProcedureAddress;
  return ((__int64 (__fastcall *)())ProcedureAddress)();
}

```

## disassembly

```asm
0x18000d080  push    rbp
0x18000d082  mov     rbp, rsp
0x18000d085  sub     rsp, 40h
0x18000d089  lea     rax, aUser32; "user32"
0x18000d090  mov     qword ptr [rbp+DllName.Length], 0E000Ch
0x18000d098  mov     [rbp+DllName.Buffer], rax
0x18000d09c  lea     r9, [rbp+DllHandle]; DllHandle
0x18000d0a0  lea     rax, aSoundsentry; "SoundSentry"
0x18000d0a7  mov     qword ptr [rbp+Name.Length], 0C000Bh
0x18000d0af  mov     [rbp+Name.Buffer], rax
0x18000d0b3  lea     r8, [rbp+DllName]; DllName
0x18000d0b7  lea     rax, FailSoundSentry
0x18000d0be  mov     [rbp+DllHandle], 0
0x18000d0c6  xor     edx, edx; DllCharacteristics
0x18000d0c8  mov     [rbp+ProcedureAddress], rax
0x18000d0cc  xor     ecx, ecx; DllPath
0x18000d0ce  call    cs:__imp_LdrGetDllHandle
0x18000d0d5  nop     dword ptr [rax+rax+00h]
0x18000d0da  test    eax, eax
0x18000d0dc  js      short loc_18000D0F9
0x18000d0de  mov     rcx, [rbp+DllHandle]; BaseAddress
0x18000d0e2  lea     r9, [rbp+ProcedureAddress]; ProcedureAddress
0x18000d0e6  xor     r8d, r8d; Ordinal
0x18000d0e9  lea     rdx, [rbp+Name]; Name
0x18000d0ed  call    cs:__imp_LdrGetProcedureAddress
0x18000d0f4  nop     dword ptr [rax+rax+00h]
0x18000d0f9  mov     rax, [rbp+ProcedureAddress]
0x18000d0fd  mov     cs:_UserSoundSentry, rax
0x18000d104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d109  add     rsp, 40h
0x18000d10d  pop     rbp
0x18000d10e  retn
```
