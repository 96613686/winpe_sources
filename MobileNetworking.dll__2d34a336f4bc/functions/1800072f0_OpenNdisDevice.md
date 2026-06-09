# OpenNdisDevice

- ea: `0x1800072f0`
- end: `0x18000736d`
- name: `OpenNdisDevice`
- size: `125`
- prototype: `void *__fastcall(struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006ee0`
- `0x180007170`

## callees

- `0x1800072f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007365`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007365`
- `ntdll!RtlNtStatusToDosError` at `0x18000735d`
- `ntdll!RtlNtStatusToDosError` at `0x18000735d`
- `ntdll!NtOpenFile` at `0x180007344`
- `ntdll!NtOpenFile` at `0x180007344`

## pseudocode

```c
void *__fastcall OpenNdisDevice(struct _UNICODE_STRING *a1)
{
  NTSTATUS v1; // eax
  DWORD v3; // eax
  struct _IO_STATUS_BLOCK v4; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES v5; // [rsp+40h] [rbp-38h] BYREF
  void *v6; // [rsp+80h] [rbp+8h] BYREF

  v5.ObjectName = a1;
  v5.RootDirectory = 0;
  *(_QWORD *)&v5.Length = 48;
  *(_QWORD *)&v5.Attributes = 64;
  v6 = 0;
  *(_OWORD *)&v5.SecurityDescriptor = 0;
  v4 = 0;
  v1 = NtOpenFile(&v6, 0x12019Fu, &v5, &v4, 7u, 0x20u);
  if ( v1 )
  {
    v3 = RtlNtStatusToDosError(v1);
    SetLastError(v3);
  }
  return v6;
}

```

## disassembly

```asm
0x1800072f0  mov     r11, rsp
0x1800072f3  sub     rsp, 78h
0x1800072f7  xor     eax, eax
0x1800072f9  mov     [r11-28h], rcx
0x1800072fd  xorps   xmm0, xmm0
0x180007300  mov     [r11-30h], rax
0x180007304  mov     qword ptr [r11-38h], 30h ; '0'
0x18000730c  lea     r9, [r11-48h]; IoStatusBlock
0x180007310  mov     qword ptr [r11-20h], 40h ; '@'
0x180007318  lea     r8, [r11-38h]; ObjectAttributes
0x18000731c  mov     [rsp+78h+OpenOptions], 20h ; ' '; OpenOptions
0x180007324  lea     rcx, [r11+8]; FileHandle
0x180007328  mov     edx, 12019Fh; DesiredAccess
0x18000732d  mov     [r11+8], rax
0x180007331  movdqu  [rsp+78h+var_18], xmm0
0x180007337  mov     [rsp+78h+ShareAccess], 7; ShareAccess
0x18000733f  movups  [rsp+78h+var_48], xmm0
0x180007344  call    cs:__imp_NtOpenFile
0x18000734a  test    eax, eax
0x18000734c  jnz     short loc_18000735B
0x18000734e  mov     rax, [rsp+78h+arg_0]
0x180007356  add     rsp, 78h
0x18000735a  retn
0x18000735b  mov     ecx, eax; Status
0x18000735d  call    cs:__imp_RtlNtStatusToDosError
0x180007363  mov     ecx, eax; dwErrCode
0x180007365  call    cs:__imp_SetLastError
0x18000736b  jmp     short loc_18000734E
```
