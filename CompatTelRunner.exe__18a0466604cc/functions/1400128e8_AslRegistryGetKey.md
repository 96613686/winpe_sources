# AslRegistryGetKey

- ea: `0x1400128e8`
- end: `0x1400129d9`
- name: `AslRegistryGetKey`
- size: `241`
- prototype: `__int64 __fastcall(void **, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400150e8`

## callees

- `0x140012800`
- `0x1400128e8`
- `0x1400151b0`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x140012981`
- `ntdll!ZwOpenKey` at `0x140012981`
- `ntdll!RtlFreeHeap` at `0x1400129c8`
- `ntdll!RtlFreeHeap` at `0x1400129c8`

## string_xrefs

- `0x140012925`: `AslRegistryBuildMachinePath failed %x for %ws`
- `0x140012937`: `AslRegistryGetKey`
- `0x140012994`: `NtOpenKey failed %x for %ws`

## pseudocode

```c
__int64 __fastcall AslRegistryGetKey(void **a1, const WCHAR *a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 v7; // r8
  PVOID P[2]; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+28h] BYREF

  *a1 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)P = 0;
  v4 = AslRegistryBuildMachinePath((PUNICODE_STRING)P, a2);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = "AslRegistryBuildMachinePath failed %x for %ws";
    v7 = 1718;
LABEL_3:
    AslLogCallPrintf(1, "AslRegistryGetKey", v7, v6, v4, a2);
    goto LABEL_8;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v5 = 0;
    *a1 = KeyHandle;
    KeyHandle = 0;
  }
  else if ( v4 != -1073741772 )
  {
    v6 = "NtOpenKey failed %x for %ws";
    v7 = 1761;
    goto LABEL_3;
  }
LABEL_8:
  if ( P[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
  return v5;
}

```

## disassembly

```asm
0x1400128e8  push    rbp
0x1400128ea  push    rbx
0x1400128eb  push    rsi
0x1400128ec  push    rdi
0x1400128ed  mov     rbp, rsp
0x1400128f0  sub     rsp, 78h
0x1400128f4  xorps   xmm0, xmm0
0x1400128f7  xor     eax, eax
0x1400128f9  mov     [rcx], rax
0x1400128fc  mov     rsi, rcx
0x1400128ff  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140012903  lea     rcx, [rbp+P]; Destination
0x140012907  mov     [rbp+KeyHandle], rax
0x14001290b  mov     rdi, rdx
0x14001290e  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140012912  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140012916  movups  xmmword ptr [rbp+P], xmm0
0x14001291a  call    AslRegistryBuildMachinePath
0x14001291f  mov     ebx, eax
0x140012921  test    eax, eax
0x140012923  jns     short loc_14001294E
0x140012925  lea     r9, aAslregistrybui; "AslRegistryBuildMachinePath failed %x f"...
0x14001292c  mov     r8d, 6B6h
0x140012932  mov     [rsp+78h+var_50], rdi
0x140012937  lea     rdx, aAslregistryget; "AslRegistryGetKey"
0x14001293e  mov     ecx, 1
0x140012943  mov     [rsp+78h+var_58], eax
0x140012947  call    AslLogCallPrintf
0x14001294c  jmp     short loc_1400129B0
0x14001294e  lea     rax, [rbp+P]
0x140012952  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140012959  xorps   xmm0, xmm0
0x14001295c  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140012960  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140012964  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14001296c  mov     edx, 1; DesiredAccess
0x140012971  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140012978  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14001297c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140012981  call    cs:__imp_ZwOpenKey
0x140012987  mov     ebx, eax
0x140012989  test    eax, eax
0x14001298b  jns     short loc_1400129A3
0x14001298d  cmp     eax, 0C0000034h
0x140012992  jz      short loc_1400129B0
0x140012994  lea     r9, aNtopenkeyFaile; "NtOpenKey failed %x for %ws"
0x14001299b  mov     r8d, 6E1h
0x1400129a1  jmp     short loc_140012932
0x1400129a3  mov     rax, [rbp+KeyHandle]
0x1400129a7  xor     ebx, ebx
0x1400129a9  mov     [rsi], rax
0x1400129ac  mov     [rbp+KeyHandle], rbx
0x1400129b0  mov     r8, [rbp+P+8]; P
0x1400129b4  test    r8, r8
0x1400129b7  jz      short loc_1400129CE
0x1400129b9  mov     rcx, gs:60h
0x1400129c2  xor     edx, edx; Flags
0x1400129c4  mov     rcx, [rcx+30h]; HeapHandle
0x1400129c8  call    cs:__imp_RtlFreeHeap
0x1400129ce  mov     eax, ebx
0x1400129d0  add     rsp, 78h
0x1400129d4  pop     rdi
0x1400129d5  pop     rsi
0x1400129d6  pop     rbx
0x1400129d7  pop     rbp
0x1400129d8  retn
```
