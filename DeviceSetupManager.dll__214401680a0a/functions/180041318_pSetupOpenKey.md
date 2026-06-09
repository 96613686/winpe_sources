# pSetupOpenKey

- ea: `0x180041318`
- end: `0x1800413f3`
- name: `pSetupOpenKey`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800413fc`

## callees

- `0x1800412b4`
- `0x180041318`
- `0x180041418`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1800413b6`
- `ntdll!NtOpenKey` at `0x1800413b6`
- `ntdll!RtlInitUnicodeString` at `0x18004137c`
- `ntdll!RtlInitUnicodeString` at `0x18004137c`
- `ntdll!RtlNtStatusToDosError` at `0x1800413c2`
- `ntdll!RtlNtStatusToDosError` at `0x1800413c2`

## pseudocode

```c
__int64 __fastcall pSetupOpenKey(void *a1, const WCHAR *a2, __int64 a3, ACCESS_MASK a4, _QWORD *a5)
{
  void *v5; // rbx
  void *v8; // rsi
  ULONG v9; // edi
  ULONG v10; // eax
  int v11; // eax
  void *KeyHandle; // [rsp+20h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-50h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-40h] BYREF
  void *v16; // [rsp+B0h] [rbp+38h] BYREF

  KeyHandle = 0;
  v5 = 0;
  v16 = 0;
  v8 = a1;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (unsigned __int64)a1 + 0x80000000 <= 7 )
  {
    v10 = pSetupOpenPredefinedKey(a1, &v16);
    v5 = v16;
    v9 = v10;
    if ( v10 )
      goto LABEL_9;
  }
  else
  {
    v9 = 0;
  }
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  if ( v5 )
    v8 = v5;
  ObjectAttributes.RootDirectory = v8;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = NtOpenKey(&KeyHandle, a4, &ObjectAttributes);
  if ( v11 >= 0 )
    *a5 = (int)KeyHandle;
  else
    v9 = RtlNtStatusToDosError(v11);
LABEL_9:
  if ( v5 )
    pSetupCloseKey(v5);
  return v9;
}

```

## disassembly

```asm
0x180041318  push    rbp
0x18004131a  push    rbx
0x18004131b  push    rsi
0x18004131c  push    rdi
0x18004131d  push    r14
0x18004131f  push    r15
0x180041321  mov     rbp, rsp
0x180041324  sub     rsp, 78h
0x180041328  xor     eax, eax
0x18004132a  xorps   xmm0, xmm0
0x18004132d  mov     [rbp+KeyHandle], rax
0x180041331  xor     ebx, ebx
0x180041333  mov     eax, 80000000h
0x180041338  mov     [rbp+arg_0], rbx
0x18004133c  add     rax, rcx
0x18004133f  mov     r14d, r9d
0x180041342  mov     r15, rdx
0x180041345  mov     rsi, rcx
0x180041348  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18004134c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180041350  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180041354  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180041358  cmp     rax, 7
0x18004135c  jbe     short loc_180041362
0x18004135e  xor     edi, edi
0x180041360  jmp     short loc_180041375
0x180041362  lea     rdx, [rbp+arg_0]
0x180041366  call    pSetupOpenPredefinedKey
0x18004136b  mov     rbx, [rbp+arg_0]
0x18004136f  mov     edi, eax
0x180041371  test    eax, eax
0x180041373  jnz     short loc_1800413D7
0x180041375  mov     rdx, r15; SourceString
0x180041378  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004137c  call    cs:__imp_RtlInitUnicodeString
0x180041382  lea     rax, [rbp+DestinationString]
0x180041386  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18004138d  xorps   xmm0, xmm0
0x180041390  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180041397  test    rbx, rbx
0x18004139a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18004139e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800413a2  mov     edx, r14d; DesiredAccess
0x1800413a5  cmovnz  rsi, rbx
0x1800413a9  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1800413ad  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x1800413b1  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800413b6  call    cs:__imp_NtOpenKey
0x1800413bc  test    eax, eax
0x1800413be  jns     short loc_1800413CC
0x1800413c0  mov     ecx, eax; Status
0x1800413c2  call    cs:__imp_RtlNtStatusToDosError
0x1800413c8  mov     edi, eax
0x1800413ca  jmp     short loc_1800413D7
0x1800413cc  mov     rax, [rbp+arg_20]
0x1800413d0  movsxd  rcx, dword ptr [rbp+KeyHandle]
0x1800413d4  mov     [rax], rcx
0x1800413d7  test    rbx, rbx
0x1800413da  jz      short loc_1800413E4
0x1800413dc  mov     rcx, rbx
0x1800413df  call    pSetupCloseKey
0x1800413e4  mov     eax, edi
0x1800413e6  add     rsp, 78h
0x1800413ea  pop     r15
0x1800413ec  pop     r14
0x1800413ee  pop     rdi
0x1800413ef  pop     rsi
0x1800413f0  pop     rbx
0x1800413f1  pop     rbp
0x1800413f2  retn
```
