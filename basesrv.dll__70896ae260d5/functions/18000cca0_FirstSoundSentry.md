# FirstSoundSentry

- ea: `0x18000cca0`
- end: `0x18000cd2d`
- name: `FirstSoundSentry`
- size: `141`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000cca0`
- `0x18000e010`

## import_xrefs

- `ntdll!LdrGetDllHandle` at `0x18000cceb`
- `ntdll!LdrGetDllHandle` at `0x18000cceb`
- `ntdll!LdrGetProcedureAddress` at `0x18000cd0a`
- `ntdll!LdrGetProcedureAddress` at `0x18000cd0a`

## pseudocode

```c
__int64 FirstSoundSentry()
{
  struct _UNICODE_STRING DllName; // [rsp+20h] [rbp-20h] BYREF
  struct _STRING Name; // [rsp+30h] [rbp-10h] BYREF
  PVOID DllHandle; // [rsp+50h] [rbp+10h] BYREF
  PVOID ProcedureAddress; // [rsp+58h] [rbp+18h] BYREF

  DllHandle = 0;
  DllName.Buffer = (PWSTR)L"user32";
  *(_QWORD *)&DllName.Length = 917516;
  Name.Buffer = "SoundSentry";
  *(_QWORD *)&Name.Length = 786443;
  ProcedureAddress = FailSoundSentry;
  if ( LdrGetDllHandle(0, 0, &DllName, &DllHandle) >= 0 )
    LdrGetProcedureAddress(DllHandle, &Name, 0, &ProcedureAddress);
  UserSoundSentry = (__int64 (__fastcall *)())ProcedureAddress;
  return ((__int64 (__fastcall *)())ProcedureAddress)();
}

```

## disassembly

```asm
0x18000cca0  push    rbp
0x18000cca2  mov     rbp, rsp
0x18000cca5  sub     rsp, 40h
0x18000cca9  and     [rbp+DllHandle], 0
0x18000ccae  lea     rax, aUser32; "user32"
0x18000ccb5  mov     [rbp+DllName.Buffer], rax
0x18000ccb9  lea     r9, [rbp+DllHandle]; DllHandle
0x18000ccbd  lea     rax, aSoundsentry; "SoundSentry"
0x18000ccc4  mov     qword ptr [rbp+DllName.Length], 0E000Ch
0x18000cccc  mov     [rbp+Name.Buffer], rax
0x18000ccd0  lea     r8, [rbp+DllName]; DllName
0x18000ccd4  lea     rax, FailSoundSentry
0x18000ccdb  mov     qword ptr [rbp+Name.Length], 0C000Bh
0x18000cce3  xor     edx, edx; DllCharacteristics
0x18000cce5  mov     [rbp+ProcedureAddress], rax
0x18000cce9  xor     ecx, ecx; DllPath
0x18000cceb  call    cs:__imp_LdrGetDllHandle
0x18000ccf2  nop     dword ptr [rax+rax+00h]
0x18000ccf7  test    eax, eax
0x18000ccf9  js      short loc_18000CD16
0x18000ccfb  mov     rcx, [rbp+DllHandle]; BaseAddress
0x18000ccff  lea     r9, [rbp+ProcedureAddress]; ProcedureAddress
0x18000cd03  xor     r8d, r8d; Ordinal
0x18000cd06  lea     rdx, [rbp+Name]; Name
0x18000cd0a  call    cs:__imp_LdrGetProcedureAddress
0x18000cd11  nop     dword ptr [rax+rax+00h]
0x18000cd16  mov     rax, [rbp+ProcedureAddress]
0x18000cd1a  mov     cs:_UserSoundSentry, rax
0x18000cd21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd26  add     rsp, 40h
0x18000cd2a  pop     rbp
0x18000cd2b  retn
```
