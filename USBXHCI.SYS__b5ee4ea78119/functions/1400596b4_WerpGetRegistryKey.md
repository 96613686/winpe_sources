# WerpGetRegistryKey

- ea: `0x1400596b4`
- end: `0x1400597a1`
- name: `WerpGetRegistryKey`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140058c20`

## callees

- `0x1400596b4`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140059758`
- `ntoskrnl!DbgPrintEx` at `0x14005977d`
- `ntoskrnl!DbgPrintEx` at `0x140059758`
- `ntoskrnl!DbgPrintEx` at `0x14005977d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400596f5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400596f5`
- `ntoskrnl!ZwOpenKey` at `0x14005972f`
- `ntoskrnl!ZwOpenKey` at `0x14005972f`

## string_xrefs

- `0x14005974b`: `WERLIVEKERNELREPORTING:%u: ERROR ZwOpenKey failed with scode 0x%x\n`

## pseudocode

```c
__int64 __fastcall WerpGetRegistryKey(void *a1, __int64 a2, __int64 a3, void **a4)
{
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( a4 )
  {
    RtlInitUnicodeString(&DestinationString, L"Busy");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = a1;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = ZwOpenKey(a4, 0x20000u, &ObjectAttributes);
    v7 = v6;
    if ( v6 >= 0 )
      return 0;
    else
      DbgPrintEx(0x96u, 0, "WERLIVEKERNELREPORTING:%u: ERROR ZwOpenKey failed with scode 0x%x\n", 169, v6);
    return v7;
  }
  else
  {
    DbgPrintEx(0x96u, 0, "WERLIVEKERNELREPORTING:%u: ERROR Invalid params\n", 150);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x1400596b4  mov     [rsp-8+arg_0], rbx
0x1400596b9  mov     [rsp-8+arg_8], rdi
0x1400596be  push    rbp
0x1400596bf  mov     rbp, rsp
0x1400596c2  sub     rsp, 70h
0x1400596c6  xorps   xmm0, xmm0
0x1400596c9  xor     eax, eax
0x1400596cb  mov     rbx, r9
0x1400596ce  mov     rdi, rcx
0x1400596d1  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400596d5  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400596d9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400596dd  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400596e1  test    r9, r9
0x1400596e4  jz      loc_14005976C
0x1400596ea  lea     rdx, aBusy; "Busy"
0x1400596f1  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400596f5  call    cs:__imp_RtlInitUnicodeString
0x1400596fc  nop     dword ptr [rax+rax+00h]
0x140059701  lea     rax, [rbp+DestinationString]
0x140059705  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14005970c  xorps   xmm0, xmm0
0x14005970f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140059713  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140059717  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x14005971b  mov     edx, 20000h; DesiredAccess
0x140059720  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140059727  mov     rcx, rbx; KeyHandle
0x14005972a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14005972f  call    cs:__imp_ZwOpenKey
0x140059736  nop     dword ptr [rax+rax+00h]
0x14005973b  mov     ebx, eax
0x14005973d  test    eax, eax
0x14005973f  jns     short loc_140059766
0x140059741  mov     r9d, 0A9h
0x140059747  mov     [rsp+70h+var_50], eax
0x14005974b  lea     r8, aWerlivekernelr_22; "WERLIVEKERNELREPORTING:%u: ERROR ZwOpen"...
0x140059752  xor     edx, edx; Level
0x140059754  lea     ecx, [r9-13h]; ComponentId
0x140059758  call    cs:__imp_DbgPrintEx
0x14005975f  nop     dword ptr [rax+rax+00h]
0x140059764  jmp     short loc_140059768
0x140059766  xor     ebx, ebx
0x140059768  mov     eax, ebx
0x14005976a  jmp     short loc_14005978E
0x14005976c  mov     ecx, 96h; ComponentId
0x140059771  lea     r8, aWerlivekernelr_23; "WERLIVEKERNELREPORTING:%u: ERROR Invali"...
0x140059778  mov     r9d, ecx
0x14005977b  xor     edx, edx; Level
0x14005977d  call    cs:__imp_DbgPrintEx
0x140059784  nop     dword ptr [rax+rax+00h]
0x140059789  mov     eax, 0C000000Dh
0x14005978e  lea     r11, [rsp+70h+var_s0]
0x140059793  mov     rbx, [r11+10h]
0x140059797  mov     rdi, [r11+18h]
0x14005979b  mov     rsp, r11
0x14005979e  pop     rbp
0x14005979f  retn
```
