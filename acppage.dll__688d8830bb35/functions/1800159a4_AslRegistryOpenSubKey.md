# AslRegistryOpenSubKey

- ea: `0x1800159a4`
- end: `0x180015a44`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012d8c`

## callees

- `0x180015220`
- `0x1800159a4`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x1800159d5`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800159d5`
- `ntdll!ZwOpenKey` at `0x180015a35`
- `ntdll!ZwOpenKey` at `0x180015a35`

## string_xrefs

- `0x1800159f2`: `AslRegistryOpenSubKey`
- `0x1800159e1`: `AslRegistryOpenSubKey passed bad Path [%x]`

## pseudocode

```c
NTSTATUS __fastcall AslRegistryOpenSubKey(PHANDLE KeyHandle, void *a2, const WCHAR *a3)
{
  NTSTATUS inited; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  *KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  inited = RtlInitUnicodeStringEx(&DestinationString, a3);
  if ( inited >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = a2;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    return ZwOpenKey(KeyHandle, 0x20019u, &ObjectAttributes);
  }
  else
  {
    AslLogCallPrintf(1, "AslRegistryOpenSubKey", 958, "AslRegistryOpenSubKey passed bad Path [%x]");
    return inited;
  }
}

```

## disassembly

```asm
0x1800159a4  push    rbp
0x1800159a6  push    rbx
0x1800159a7  push    rsi
0x1800159a8  push    rdi
0x1800159a9  mov     rbp, rsp
0x1800159ac  sub     rsp, 78h
0x1800159b0  xorps   xmm0, xmm0
0x1800159b3  xor     eax, eax
0x1800159b5  mov     [rcx], rax
0x1800159b8  mov     rsi, rdx
0x1800159bb  mov     rdi, rcx
0x1800159be  mov     rdx, r8; SourceString
0x1800159c1  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800159c5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800159c9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800159cd  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800159d1  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800159d5  call    cs:__imp_RtlInitUnicodeStringEx
0x1800159db  mov     ebx, eax
0x1800159dd  test    eax, eax
0x1800159df  jns     short loc_180015A07
0x1800159e1  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x1800159e8  mov     [rsp+78h+var_58], eax
0x1800159ec  mov     r8d, 3BEh
0x1800159f2  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x1800159f9  mov     ecx, 1
0x1800159fe  call    AslLogCallPrintf
0x180015a03  mov     eax, ebx
0x180015a05  jmp     short loc_180015A3B
0x180015a07  lea     rax, [rbp+DestinationString]
0x180015a0b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180015a12  xorps   xmm0, xmm0
0x180015a15  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180015a19  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180015a1d  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x180015a21  mov     edx, 20019h; DesiredAccess
0x180015a26  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180015a2d  mov     rcx, rdi; KeyHandle
0x180015a30  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180015a35  call    cs:__imp_ZwOpenKey
0x180015a3b  add     rsp, 78h
0x180015a3f  pop     rdi
0x180015a40  pop     rsi
0x180015a41  pop     rbx
0x180015a42  pop     rbp
0x180015a43  retn
```
