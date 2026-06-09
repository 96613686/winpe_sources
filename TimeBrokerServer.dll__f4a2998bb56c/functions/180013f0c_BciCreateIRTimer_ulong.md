# BciCreateIRTimer(ulong)

- ea: `0x180013f0c`
- end: `0x180013f57`
- name: `?BciCreateIRTimer@@YAPEAXK@Z`
- size: `75`
- prototype: `__int64 __fastcall()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180017e64`

## callees

- `0x180013f0c`

## import_xrefs

- `ntdll!NtCreateIRTimer` at `0x180013f33`
- `ntdll!NtCreateIRTimer` at `0x180013f33`
- `ntdll!RtlNtStatusToDosError` at `0x180013f3f`
- `ntdll!RtlNtStatusToDosError` at `0x180013f3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013f47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013f47`

## pseudocode

```c
__int64 __fastcall BciCreateIRTimer()
{
  NTSTATUS v0; // eax
  DWORD v1; // eax
  int v3; // [rsp+30h] [rbp+8h] BYREF
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 3;
  v0 = NtCreateIRTimer(&v4, &v3, 2031619);
  if ( v0 < 0 )
  {
    v1 = RtlNtStatusToDosError(v0);
    SetLastError(v1);
  }
  return v4;
}

```

## disassembly

```asm
0x180013f0c  mov     rax, rsp
0x180013f0f  mov     [rax+8], ecx
0x180013f12  sub     rsp, 28h
0x180013f16  mov     r8d, 1F0003h
0x180013f1c  mov     qword ptr [rax+10h], 0
0x180013f24  lea     rdx, [rax+8]
0x180013f28  mov     dword ptr [rax+8], 3
0x180013f2f  lea     rcx, [rax+10h]
0x180013f33  call    cs:__imp_NtCreateIRTimer
0x180013f39  test    eax, eax
0x180013f3b  jns     short loc_180013F4D
0x180013f3d  mov     ecx, eax; Status
0x180013f3f  call    cs:__imp_RtlNtStatusToDosError
0x180013f45  mov     ecx, eax; dwErrCode
0x180013f47  call    cs:__imp_SetLastError
0x180013f4d  mov     rax, [rsp+28h+arg_8]
0x180013f52  add     rsp, 28h
0x180013f56  retn
```
