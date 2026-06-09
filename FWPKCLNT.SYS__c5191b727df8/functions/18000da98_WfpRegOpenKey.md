# WfpRegOpenKey

- ea: `0x18000da98`
- end: `0x18000db72`
- name: `WfpRegOpenKey`
- size: `218`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000cbb0`
- `0x18000cd94`
- `0x18000dffc`

## callees

- `0x180004904`
- `0x18000c9b4`
- `0x18000da98`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x18000db13`
- `ntoskrnl!ZwOpenKey` at `0x18000db13`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000dad3`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000dad3`

## string_xrefs

- `0x18000daad`: `\Registry\Machine\System\CurrentControlSet\Services\BFE\Parameters`
- `0x18000db31`: `ZwOpenKey`
- `0x18000db45`: `WfpRegOpenKey`

## pseudocode

```c
__int64 __fastcall WfpRegOpenKey(PHANDLE KeyHandle, __int64 a2, _DWORD *a3)
{
  NTSTATUS v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rbx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  *(_OWORD *)&ObjectAttributes.ObjectName = 0;
  *a3 = 0;
  *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
  *(_OWORD *)&ObjectAttributes.Length = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\BFE\\Parameters");
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenKey(KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v5 >= 0 )
  {
    if ( !v5 )
    {
      *a3 = 1;
      return 0;
    }
  }
  else if ( v5 == -1073741772 )
  {
    return 0;
  }
  v7 = WfpReportSysErrorAsNtStatus(v6, (int)"ZwOpenKey", v5);
  v8 = v7;
  if ( v7 )
    WfpReportError(v7, (int)"WfpRegOpenKey");
  return v8;
}

```

## disassembly

```asm
0x18000da98  mov     [rsp-8+arg_0], rbx
0x18000da9d  mov     [rsp-8+arg_8], rdi
0x18000daa2  push    rbp
0x18000daa3  mov     rbp, rsp
0x18000daa6  sub     rsp, 60h
0x18000daaa  xorps   xmm0, xmm0
0x18000daad  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000dab4  mov     rbx, rcx
0x18000dab7  xor     eax, eax
0x18000dab9  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000dabd  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000dac1  mov     [r8], eax
0x18000dac4  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18000dac8  mov     rdi, r8
0x18000dacb  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000dacf  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000dad3  call    cs:__imp_RtlInitUnicodeString
0x18000dada  nop     dword ptr [rax+rax+00h]
0x18000dadf  lea     rax, [rbp+DestinationString]
0x18000dae3  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000daeb  xorps   xmm0, xmm0
0x18000daee  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000daf2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000daf6  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x18000dafe  mov     edx, 20019h; DesiredAccess
0x18000db03  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18000db0b  mov     rcx, rbx; KeyHandle
0x18000db0e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000db13  call    cs:__imp_ZwOpenKey
0x18000db1a  nop     dword ptr [rax+rax+00h]
0x18000db1f  test    eax, eax
0x18000db21  jns     short loc_18000DB2C
0x18000db23  cmp     eax, 0C0000034h
0x18000db28  jnz     short loc_18000DB2E
0x18000db2a  jmp     short loc_18000DB5C
0x18000db2c  jz      short loc_18000DB56
0x18000db2e  mov     r8d, eax
0x18000db31  lea     rdx, aZwopenkey; "ZwOpenKey"
0x18000db38  call    WfpReportSysErrorAsNtStatus
0x18000db3d  mov     rbx, rax
0x18000db40  test    rax, rax
0x18000db43  jz      short loc_18000DB5E
0x18000db45  lea     rdx, aWfpregopenkey; "WfpRegOpenKey"
0x18000db4c  mov     rcx, rax
0x18000db4f  call    WfpReportError
0x18000db54  jmp     short loc_18000DB5E
0x18000db56  mov     dword ptr [rdi], 1
0x18000db5c  xor     ebx, ebx
0x18000db5e  mov     rdi, [rsp+60h+arg_8]
0x18000db63  mov     rax, rbx
0x18000db66  mov     rbx, [rsp+60h+arg_0]
0x18000db6b  add     rsp, 60h
0x18000db6f  pop     rbp
0x18000db70  retn
```
