# AslRegistryGetKey

- ea: `0x1800155ac`
- end: `0x18001569d`
- name: `AslRegistryGetKey`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013b84`

## callees

- `0x1800152d0`
- `0x1800154c4`
- `0x1800155ac`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x180015645`
- `ntdll!ZwOpenKey` at `0x180015645`
- `ntdll!RtlFreeHeap` at `0x18001568c`
- `ntdll!RtlFreeHeap` at `0x18001568c`

## string_xrefs

- `0x1800155e9`: `AslRegistryBuildMachinePath failed %x for %ws`
- `0x1800155fb`: `AslRegistryGetKey`
- `0x180015658`: `NtOpenKey failed %x for %ws`

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
0x1800155ac  push    rbp
0x1800155ae  push    rbx
0x1800155af  push    rsi
0x1800155b0  push    rdi
0x1800155b1  mov     rbp, rsp
0x1800155b4  sub     rsp, 78h
0x1800155b8  xorps   xmm0, xmm0
0x1800155bb  xor     eax, eax
0x1800155bd  mov     [rcx], rax
0x1800155c0  mov     rsi, rcx
0x1800155c3  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800155c7  lea     rcx, [rbp+P]; Destination
0x1800155cb  mov     [rbp+KeyHandle], rax
0x1800155cf  mov     rdi, rdx
0x1800155d2  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800155d6  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800155da  movups  xmmword ptr [rbp+P], xmm0
0x1800155de  call    AslRegistryBuildMachinePath
0x1800155e3  mov     ebx, eax
0x1800155e5  test    eax, eax
0x1800155e7  jns     short loc_180015612
0x1800155e9  lea     r9, aAslregistrybui; "AslRegistryBuildMachinePath failed %x f"...
0x1800155f0  mov     r8d, 6B6h
0x1800155f6  mov     [rsp+78h+var_50], rdi
0x1800155fb  lea     rdx, aAslregistryget; "AslRegistryGetKey"
0x180015602  mov     ecx, 1
0x180015607  mov     [rsp+78h+var_58], eax
0x18001560b  call    AslLogCallPrintf
0x180015610  jmp     short loc_180015674
0x180015612  lea     rax, [rbp+P]
0x180015616  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001561d  xorps   xmm0, xmm0
0x180015620  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180015624  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180015628  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180015630  mov     edx, 1; DesiredAccess
0x180015635  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18001563c  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180015640  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180015645  call    cs:__imp_ZwOpenKey
0x18001564b  mov     ebx, eax
0x18001564d  test    eax, eax
0x18001564f  jns     short loc_180015667
0x180015651  cmp     eax, 0C0000034h
0x180015656  jz      short loc_180015674
0x180015658  lea     r9, aNtopenkeyFaile; "NtOpenKey failed %x for %ws"
0x18001565f  mov     r8d, 6E1h
0x180015665  jmp     short loc_1800155F6
0x180015667  mov     rax, [rbp+KeyHandle]
0x18001566b  xor     ebx, ebx
0x18001566d  mov     [rsi], rax
0x180015670  mov     [rbp+KeyHandle], rbx
0x180015674  mov     r8, [rbp+P+8]; P
0x180015678  test    r8, r8
0x18001567b  jz      short loc_180015692
0x18001567d  mov     rcx, gs:60h
0x180015686  xor     edx, edx; Flags
0x180015688  mov     rcx, [rcx+30h]; HeapHandle
0x18001568c  call    cs:__imp_RtlFreeHeap
0x180015692  mov     eax, ebx
0x180015694  add     rsp, 78h
0x180015698  pop     rdi
0x180015699  pop     rsi
0x18001569a  pop     rbx
0x18001569b  pop     rbp
0x18001569c  retn
```
