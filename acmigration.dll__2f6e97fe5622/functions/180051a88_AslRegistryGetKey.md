# AslRegistryGetKey

- ea: `0x180051a88`
- end: `0x180051b8f`
- name: `AslRegistryGetKey`
- size: `263`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800542d8`
- `0x18005f30c`
- `0x18005f728`
- `0x18005ff28`

## callees

- `0x1800519a0`
- `0x180051a88`
- `0x1800543c0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180051b72`
- `ntdll!RtlFreeHeap` at `0x180051b72`
- `ntdll!ZwOpenKey` at `0x180051b2b`
- `ntdll!ZwOpenKey` at `0x180051b2b`

## string_xrefs

- `0x180051ad1`: `AslRegistryBuildMachinePath failed %x for %ws`
- `0x180051ae3`: `AslRegistryGetKey`
- `0x180051b3e`: `NtOpenKey failed %x for %ws`

## pseudocode

```c
__int64 __fastcall AslRegistryGetKey(void **a1, const WCHAR *a2, ACCESS_MASK a3)
{
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 v9; // r8
  PVOID P[2]; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+90h] [rbp+20h] BYREF

  *a1 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)P = 0;
  v6 = AslRegistryBuildMachinePath((PUNICODE_STRING)P, a2);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = "AslRegistryBuildMachinePath failed %x for %ws";
    v9 = 1718;
LABEL_3:
    AslLogCallPrintf(1, "AslRegistryGetKey", v9, v8, v6, a2);
    goto LABEL_8;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwOpenKey(&KeyHandle, a3, &ObjectAttributes);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v7 = 0;
    *a1 = KeyHandle;
    KeyHandle = 0;
  }
  else if ( v6 != -1073741772 )
  {
    v8 = "NtOpenKey failed %x for %ws";
    v9 = 1761;
    goto LABEL_3;
  }
LABEL_8:
  if ( P[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
  return v7;
}

```

## disassembly

```asm
0x180051a88  mov     [rsp-18h+arg_8], rbx
0x180051a8d  mov     [rsp-18h+arg_10], rsi
0x180051a92  push    rbp
0x180051a93  push    rdi
0x180051a94  push    r14
0x180051a96  mov     rbp, rsp
0x180051a99  sub     rsp, 70h
0x180051a9d  xorps   xmm0, xmm0
0x180051aa0  xor     eax, eax
0x180051aa2  mov     [rcx], rax
0x180051aa5  mov     rsi, rcx
0x180051aa8  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180051aac  lea     rcx, [rbp+P]; Destination
0x180051ab0  mov     [rbp+KeyHandle], rax
0x180051ab4  mov     r14d, r8d
0x180051ab7  mov     rdi, rdx
0x180051aba  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180051abe  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180051ac2  movups  xmmword ptr [rbp+P], xmm0
0x180051ac6  call    AslRegistryBuildMachinePath
0x180051acb  mov     ebx, eax
0x180051acd  test    eax, eax
0x180051acf  jns     short loc_180051AFA
0x180051ad1  lea     r9, aAslregistrybui; "AslRegistryBuildMachinePath failed %x f"...
0x180051ad8  mov     r8d, 6B6h
0x180051ade  mov     [rsp+70h+var_48], rdi
0x180051ae3  lea     rdx, aAslregistryget; "AslRegistryGetKey"
0x180051aea  mov     ecx, 1
0x180051aef  mov     [rsp+70h+var_50], eax
0x180051af3  call    AslLogCallPrintf
0x180051af8  jmp     short loc_180051B5A
0x180051afa  lea     rax, [rbp+P]
0x180051afe  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180051b05  xorps   xmm0, xmm0
0x180051b08  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180051b0c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180051b10  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180051b18  mov     edx, r14d; DesiredAccess
0x180051b1b  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180051b22  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180051b26  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180051b2b  call    cs:__imp_ZwOpenKey
0x180051b31  mov     ebx, eax
0x180051b33  test    eax, eax
0x180051b35  jns     short loc_180051B4D
0x180051b37  cmp     eax, 0C0000034h
0x180051b3c  jz      short loc_180051B5A
0x180051b3e  lea     r9, aNtopenkeyFaile; "NtOpenKey failed %x for %ws"
0x180051b45  mov     r8d, 6E1h
0x180051b4b  jmp     short loc_180051ADE
0x180051b4d  mov     rax, [rbp+KeyHandle]
0x180051b51  xor     ebx, ebx
0x180051b53  mov     [rsi], rax
0x180051b56  mov     [rbp+KeyHandle], rbx
0x180051b5a  mov     r8, [rbp+P+8]; P
0x180051b5e  test    r8, r8
0x180051b61  jz      short loc_180051B78
0x180051b63  mov     rcx, gs:60h
0x180051b6c  xor     edx, edx; Flags
0x180051b6e  mov     rcx, [rcx+30h]; HeapHandle
0x180051b72  call    cs:__imp_RtlFreeHeap
0x180051b78  lea     r11, [rsp+70h+var_s0]
0x180051b7d  mov     eax, ebx
0x180051b7f  mov     rbx, [r11+28h]
0x180051b83  mov     rsi, [r11+30h]
0x180051b87  mov     rsp, r11
0x180051b8a  pop     r14
0x180051b8c  pop     rdi
0x180051b8d  pop     rbp
0x180051b8e  retn
```
