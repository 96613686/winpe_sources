# AslRegistryGetKey

- ea: `0x180027118`
- end: `0x180027250`
- name: `AslRegistryGetKey`
- size: `312`
- prototype: `__int64 __fastcall(void **, const WCHAR *, ACCESS_MASK, int)`
- caller_count: `6`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027028`
- `0x18006ff68`
- `0x180119a60`
- `0x180119ec8`
- `0x18011a61c`
- `0x18012517c`

## callees

- `0x1800197d4`
- `0x18001cce4`
- `0x180027118`
- `0x180027258`
- `0x18006c764`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18002719b`
- `ntdll!ZwOpenKey` at `0x18002719b`

## string_xrefs

- `0x1800271d6`: `AslRegistryBuildMachinePath failed %x for %ws`
- `0x1800271f7`: `AslRegistryGetKey`
- `0x18002721d`: `AslRegistryBuildUserPath failed %x for %ws`
- `0x1800271e5`: `NtOpenKey failed %x for %ws`

## pseudocode

```c
__int64 __fastcall AslRegistryGetKey(void **a1, const WCHAR *a2, ACCESS_MASK a3, int a4)
{
  int v6; // ebx
  NTSTATUS v7; // eax
  const char *v9; // r9
  int v10; // r8d
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+90h] [rbp+20h] BYREF

  *a1 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  Destination = 0;
  if ( a4 )
  {
    v6 = AslRegistryBuildMachinePath(&Destination, a2);
    if ( v6 >= 0 )
      goto LABEL_3;
    v9 = "AslRegistryBuildMachinePath failed %x for %ws";
    v10 = 1718;
LABEL_9:
    AslLogCallPrintf(1, (unsigned int)"AslRegistryGetKey", v10, (_DWORD)v9);
    goto LABEL_5;
  }
  v6 = AslRegistryBuildUserPath(&Destination, a2);
  if ( v6 < 0 )
  {
    v9 = "AslRegistryBuildUserPath failed %x for %ws";
    v10 = 1725;
    goto LABEL_9;
  }
LABEL_3:
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwOpenKey(&KeyHandle, a3, &ObjectAttributes);
  v6 = v7;
  if ( v7 >= 0 )
  {
    v6 = 0;
    *a1 = KeyHandle;
    KeyHandle = 0;
    goto LABEL_5;
  }
  if ( v7 != -1073741772 )
  {
    v9 = "NtOpenKey failed %x for %ws";
    v10 = 1761;
    goto LABEL_9;
  }
LABEL_5:
  if ( Destination.Buffer )
    AslFree(NtCurrentPeb()->ProcessHeap, Destination.Buffer);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180027118  mov     [rsp-18h+arg_8], rbx
0x18002711d  mov     [rsp-18h+arg_10], rsi
0x180027122  push    rbp
0x180027123  push    rdi
0x180027124  push    r14
0x180027126  mov     rbp, rsp
0x180027129  sub     rsp, 70h
0x18002712d  xorps   xmm0, xmm0
0x180027130  xor     eax, eax
0x180027132  mov     [rcx], rax
0x180027135  mov     rsi, rcx
0x180027138  mov     [rbp+KeyHandle], rax
0x18002713c  lea     rcx, [rbp+Destination]; Destination
0x180027140  mov     r14d, r8d
0x180027143  mov     rdi, rdx
0x180027146  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18002714a  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18002714e  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180027152  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x180027156  test    r9d, r9d
0x180027159  jz      loc_18002720E
0x18002715f  call    AslRegistryBuildMachinePath
0x180027164  mov     ebx, eax
0x180027166  test    eax, eax
0x180027168  js      short loc_1800271D6
0x18002716a  lea     rax, [rbp+Destination]
0x18002716e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180027175  xorps   xmm0, xmm0
0x180027178  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18002717c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180027180  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180027188  mov     edx, r14d; DesiredAccess
0x18002718b  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180027192  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180027196  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002719b  call    cs:__imp_ZwOpenKey
0x1800271a1  mov     ebx, eax
0x1800271a3  test    eax, eax
0x1800271a5  js      loc_18002722C
0x1800271ab  mov     rax, [rbp+KeyHandle]
0x1800271af  xor     ebx, ebx
0x1800271b1  mov     [rsi], rax
0x1800271b4  mov     [rbp+KeyHandle], rbx
0x1800271b8  cmp     [rbp+Destination.Buffer], 0
0x1800271bd  jnz     short loc_180027235
0x1800271bf  lea     r11, [rsp+70h+var_s0]
0x1800271c4  mov     eax, ebx
0x1800271c6  mov     rbx, [r11+28h]
0x1800271ca  mov     rsi, [r11+30h]
0x1800271ce  mov     rsp, r11
0x1800271d1  pop     r14
0x1800271d3  pop     rdi
0x1800271d4  pop     rbp
0x1800271d5  retn
0x1800271d6  lea     r9, aAslregistrybui; "AslRegistryBuildMachinePath failed %x f"...
0x1800271dd  mov     r8d, 6B6h
0x1800271e3  jmp     short loc_1800271F2
0x1800271e5  lea     r9, aNtopenkeyFaile; "NtOpenKey failed %x for %ws"
0x1800271ec  mov     r8d, 6E1h
0x1800271f2  mov     [rsp+70h+var_48], rdi
0x1800271f7  lea     rdx, aAslregistryget; "AslRegistryGetKey"
0x1800271fe  mov     ecx, 1
0x180027203  mov     [rsp+70h+var_50], eax
0x180027207  call    AslLogCallPrintf
0x18002720c  jmp     short loc_1800271B8
0x18002720e  call    AslRegistryBuildUserPath
0x180027213  mov     ebx, eax
0x180027215  test    eax, eax
0x180027217  jns     loc_18002716A
0x18002721d  lea     r9, aAslregistrybui_2; "AslRegistryBuildUserPath failed %x for "...
0x180027224  mov     r8d, 6BDh
0x18002722a  jmp     short loc_1800271F2
0x18002722c  cmp     eax, 0C0000034h
0x180027231  jz      short loc_1800271B8
0x180027233  jmp     short loc_1800271E5
0x180027235  mov     rcx, gs:60h
0x18002723e  mov     rdx, [rbp+Destination.Buffer]
0x180027242  mov     rcx, [rcx+30h]
0x180027246  call    AslFree
0x18002724b  jmp     loc_1800271BF
```
