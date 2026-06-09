# AslRegistryGetKey

- ea: `0x14003c618`
- end: `0x14003c740`
- name: `AslRegistryGetKey`
- size: `296`
- prototype: `__int64 __fastcall(void **, const WCHAR *, ACCESS_MASK, int)`
- caller_count: `5`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140038174`
- `0x1400385dc`
- `0x140038d3c`
- `0x14003a6e8`
- `0x14003fba0`

## callees

- `0x14003bf18`
- `0x14003c368`
- `0x14003c388`
- `0x14003c470`
- `0x14003c618`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x14003c6da`
- `ntdll!ZwOpenKey` at `0x14003c6da`

## string_xrefs

- `0x14003c678`: `AslRegistryGetKey`
- `0x14003c666`: `AslRegistryBuildMachinePath failed %x for %ws`
- `0x14003c69a`: `AslRegistryBuildUserPath failed %x for %ws`
- `0x14003c6ed`: `NtOpenKey failed %x for %ws`

## pseudocode

```c
__int64 __fastcall AslRegistryGetKey(void **a1, const WCHAR *a2, ACCESS_MASK a3, int a4)
{
  NTSTATUS v7; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 v10; // r8
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+90h] [rbp+20h] BYREF

  *a1 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  Destination = 0;
  if ( a4 )
  {
    v7 = AslRegistryBuildMachinePath(&Destination, a2);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = "AslRegistryBuildMachinePath failed %x for %ws";
      v10 = 1718;
LABEL_4:
      AslLogCallPrintf(1, "AslRegistryGetKey", v10, v9, v7, a2, *(_QWORD *)&Destination.Length);
      goto LABEL_11;
    }
  }
  else
  {
    v7 = AslRegistryBuildUserPath(&Destination, a2);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = "AslRegistryBuildUserPath failed %x for %ws";
      v10 = 1725;
      goto LABEL_4;
    }
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwOpenKey(&KeyHandle, a3, &ObjectAttributes);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v8 = 0;
    *a1 = KeyHandle;
    KeyHandle = 0;
  }
  else if ( v7 != -1073741772 )
  {
    v9 = "NtOpenKey failed %x for %ws";
    v10 = 1761;
    goto LABEL_4;
  }
LABEL_11:
  if ( Destination.Buffer )
    AslFree(NtCurrentPeb()->ProcessHeap, Destination.Buffer);
  return v8;
}

```

## disassembly

```asm
0x14003c618  mov     [rsp-18h+arg_8], rbx
0x14003c61d  mov     [rsp-18h+arg_10], rsi
0x14003c622  push    rbp
0x14003c623  push    rdi
0x14003c624  push    r14
0x14003c626  mov     rbp, rsp
0x14003c629  sub     rsp, 70h
0x14003c62d  xorps   xmm0, xmm0
0x14003c630  xor     eax, eax
0x14003c632  mov     [rcx], rax
0x14003c635  mov     rsi, rcx
0x14003c638  mov     [rbp+KeyHandle], rax
0x14003c63c  lea     rcx, [rbp+Destination]; Destination
0x14003c640  mov     r14d, r8d
0x14003c643  mov     rdi, rdx
0x14003c646  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14003c64a  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14003c64e  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14003c652  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x14003c656  test    r9d, r9d
0x14003c659  jz      short loc_14003C68F
0x14003c65b  call    AslRegistryBuildMachinePath
0x14003c660  mov     ebx, eax
0x14003c662  test    eax, eax
0x14003c664  jns     short loc_14003C6A9
0x14003c666  lea     r9, aAslregistrybui; "AslRegistryBuildMachinePath failed %x f"...
0x14003c66d  mov     r8d, 6B6h
0x14003c673  mov     [rsp+70h+var_48], rdi
0x14003c678  lea     rdx, aAslregistryget; "AslRegistryGetKey"
0x14003c67f  mov     ecx, 1
0x14003c684  mov     [rsp+70h+var_50], eax
0x14003c688  call    AslLogCallPrintf
0x14003c68d  jmp     short loc_14003C70C
0x14003c68f  call    AslRegistryBuildUserPath
0x14003c694  mov     ebx, eax
0x14003c696  test    eax, eax
0x14003c698  jns     short loc_14003C6A9
0x14003c69a  lea     r9, aAslregistrybui_2; "AslRegistryBuildUserPath failed %x for "...
0x14003c6a1  mov     r8d, 6BDh
0x14003c6a7  jmp     short loc_14003C673
0x14003c6a9  lea     rax, [rbp+Destination]
0x14003c6ad  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14003c6b4  xorps   xmm0, xmm0
0x14003c6b7  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14003c6bb  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14003c6bf  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14003c6c7  mov     edx, r14d; DesiredAccess
0x14003c6ca  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14003c6d1  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14003c6d5  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14003c6da  call    cs:__imp_ZwOpenKey
0x14003c6e0  mov     ebx, eax
0x14003c6e2  test    eax, eax
0x14003c6e4  jns     short loc_14003C6FF
0x14003c6e6  cmp     eax, 0C0000034h
0x14003c6eb  jz      short loc_14003C70C
0x14003c6ed  lea     r9, aNtopenkeyFaile; "NtOpenKey failed %x for %ws"
0x14003c6f4  mov     r8d, 6E1h
0x14003c6fa  jmp     loc_14003C673
0x14003c6ff  mov     rax, [rbp+KeyHandle]
0x14003c703  xor     ebx, ebx
0x14003c705  mov     [rsi], rax
0x14003c708  mov     [rbp+KeyHandle], rbx
0x14003c70c  cmp     [rbp+Destination.Buffer], 0
0x14003c711  jz      short loc_14003C729
0x14003c713  mov     rcx, gs:60h
0x14003c71c  mov     rdx, [rbp+Destination.Buffer]
0x14003c720  mov     rcx, [rcx+30h]
0x14003c724  call    AslFree
0x14003c729  lea     r11, [rsp+70h+var_s0]
0x14003c72e  mov     eax, ebx
0x14003c730  mov     rbx, [r11+28h]
0x14003c734  mov     rsi, [r11+30h]
0x14003c738  mov     rsp, r11
0x14003c73b  pop     r14
0x14003c73d  pop     rdi
0x14003c73e  pop     rbp
0x14003c73f  retn
```
