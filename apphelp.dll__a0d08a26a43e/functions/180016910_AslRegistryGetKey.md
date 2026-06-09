# AslRegistryGetKey

- ea: `0x180016910`
- end: `0x180016aa1`
- name: `AslRegistryGetKey`
- size: `401`
- prototype: `__int64 __fastcall(void **, const WCHAR *, ACCESS_MASK, int, int)`
- caller_count: `11`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800032ec`
- `0x180003a64`
- `0x180003c7c`
- `0x180016718`
- `0x180016814`
- `0x180017334`
- `0x18003f210`
- `0x1800422b0`
- `0x180046c40`
- `0x180046f10`
- `0x18004b480`

## callees

- `0x18000f114`
- `0x180016910`
- `0x180016aa8`
- `0x18002ab0c`

## import_xrefs

- `ntdll!ZwCreateKey` at `0x180016a73`
- `ntdll!ZwCreateKey` at `0x180016a73`
- `ntdll!ZwOpenKey` at `0x1800169a6`
- `ntdll!ZwOpenKey` at `0x1800169a6`
- `ntdll!RtlFreeHeap` at `0x1800169d5`
- `ntdll!RtlFreeHeap` at `0x1800169d5`

## string_xrefs

- `0x180016a22`: `AslRegistryBuildMachinePath failed %x for %ws`
- `0x180016a34`: `AslRegistryGetKey`
- `0x180016a13`: `AslRegistryBuildUserPath failed %x for %ws`
- `0x180016a83`: `NtCreateKey failed %x for %ws`
- `0x180016a92`: `NtOpenKey failed %x for %ws`

## pseudocode

```c
__int64 __fastcall AslRegistryGetKey(void **a1, const WCHAR *a2, ACCESS_MASK a3, int a4, int a5)
{
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  const char *v11; // r9
  __int64 v12; // r8
  PUNICODE_STRING Class; // [rsp+20h] [rbp-60h]
  PVOID P[2]; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+20h] BYREF
  ULONG Disposition; // [rsp+B8h] [rbp+38h] BYREF

  *a1 = 0;
  Disposition = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)P = 0;
  if ( a4 )
  {
    v8 = AslRegistryBuildMachinePath((PUNICODE_STRING)P, a2);
    v9 = v8;
    if ( v8 < 0 )
    {
      v11 = "AslRegistryBuildMachinePath failed %x for %ws";
      v12 = 1718;
      goto LABEL_13;
    }
  }
  else
  {
    v8 = AslRegistryBuildUserPath((PUNICODE_STRING)P, a2);
    v9 = v8;
    if ( v8 < 0 )
    {
      v11 = "AslRegistryBuildUserPath failed %x for %ws";
      v12 = 1725;
      goto LABEL_13;
    }
  }
  ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  if ( !a5 )
  {
    v8 = ZwOpenKey(&KeyHandle, a3, &ObjectAttributes);
    v9 = v8;
    if ( v8 < 0 )
    {
      if ( v8 == -1073741772 )
        goto LABEL_6;
      v11 = "NtOpenKey failed %x for %ws";
      v12 = 1761;
      goto LABEL_13;
    }
LABEL_9:
    v9 = 0;
    *a1 = KeyHandle;
    KeyHandle = 0;
    goto LABEL_6;
  }
  v8 = ZwCreateKey(&KeyHandle, a3 | 0x2010F, &ObjectAttributes, 0, 0, 0, &Disposition);
  v9 = v8;
  if ( v8 >= 0 )
    goto LABEL_9;
  v11 = "NtCreateKey failed %x for %ws";
  v12 = 1753;
LABEL_13:
  LODWORD(Class) = v8;
  AslLogCallPrintf(1, "AslRegistryGetKey", v12, v11, Class, a2);
LABEL_6:
  if ( P[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
  return v9;
}

```

## disassembly

```asm
0x180016910  mov     [rsp-18h+arg_8], rbx
0x180016915  mov     [rsp-18h+arg_10], rsi
0x18001691a  push    rbp
0x18001691b  push    rdi
0x18001691c  push    r14
0x18001691e  mov     rbp, rsp
0x180016921  sub     rsp, 80h
0x180016928  xor     eax, eax
0x18001692a  xorps   xmm0, xmm0
0x18001692d  mov     [rcx], rax
0x180016930  mov     r14, rcx
0x180016933  mov     [rbp+arg_18], eax
0x180016936  lea     rcx, [rbp+P]; Destination
0x18001693a  mov     [rbp+KeyHandle], rax
0x18001693e  mov     esi, r8d
0x180016941  mov     rdi, rdx
0x180016944  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180016948  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18001694c  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180016950  movups  xmmword ptr [rbp+P], xmm0
0x180016954  test    r9d, r9d
0x180016957  jz      loc_180016A04
0x18001695d  call    AslRegistryBuildMachinePath
0x180016962  mov     ebx, eax
0x180016964  test    eax, eax
0x180016966  js      loc_180016A22
0x18001696c  cmp     [rbp+arg_20], 0
0x180016970  lea     rax, [rbp+P]
0x180016974  xorps   xmm0, xmm0
0x180016977  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18001697b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180016980  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180016987  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18001698b  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180016993  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180016997  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18001699e  jnz     loc_180016A4E
0x1800169a4  mov     edx, esi; DesiredAccess
0x1800169a6  call    cs:__imp_ZwOpenKey
0x1800169ac  mov     ebx, eax
0x1800169ae  test    eax, eax
0x1800169b0  jns     short loc_1800169F5
0x1800169b2  cmp     eax, 0C0000034h
0x1800169b7  jnz     loc_180016A92
0x1800169bd  mov     r8, [rbp+P+8]; P
0x1800169c1  test    r8, r8
0x1800169c4  jz      short loc_1800169DB
0x1800169c6  mov     rcx, gs:60h
0x1800169cf  xor     edx, edx; Flags
0x1800169d1  mov     rcx, [rcx+30h]; HeapHandle
0x1800169d5  call    cs:__imp_RtlFreeHeap
0x1800169db  lea     r11, [rsp+80h+var_s0]
0x1800169e3  mov     eax, ebx
0x1800169e5  mov     rbx, [r11+28h]
0x1800169e9  mov     rsi, [r11+30h]
0x1800169ed  mov     rsp, r11
0x1800169f0  pop     r14
0x1800169f2  pop     rdi
0x1800169f3  pop     rbp
0x1800169f4  retn
0x1800169f5  mov     rax, [rbp+KeyHandle]
0x1800169f9  xor     ebx, ebx
0x1800169fb  mov     [r14], rax
0x1800169fe  mov     [rbp+KeyHandle], rbx
0x180016a02  jmp     short loc_1800169BD
0x180016a04  call    AslRegistryBuildUserPath
0x180016a09  mov     ebx, eax
0x180016a0b  test    eax, eax
0x180016a0d  jns     loc_18001696C
0x180016a13  lea     r9, aAslregistrybui_2; "AslRegistryBuildUserPath failed %x for "...
0x180016a1a  mov     r8d, 6BDh
0x180016a20  jmp     short loc_180016A2F
0x180016a22  lea     r9, aAslregistrybui; "AslRegistryBuildMachinePath failed %x f"...
0x180016a29  mov     r8d, 6B6h
0x180016a2f  mov     qword ptr [rsp+80h+CreateOptions], rdi
0x180016a34  lea     rdx, aAslregistryget; "AslRegistryGetKey"
0x180016a3b  mov     ecx, 1
0x180016a40  mov     dword ptr [rsp+80h+Class], eax
0x180016a44  call    AslLogCallPrintf
0x180016a49  jmp     loc_1800169BD
0x180016a4e  lea     rax, [rbp+arg_18]
0x180016a52  or      esi, 2010Fh
0x180016a58  mov     [rsp+80h+Disposition], rax; Disposition
0x180016a5d  xor     r9d, r9d; TitleIndex
0x180016a60  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x180016a68  mov     edx, esi; DesiredAccess
0x180016a6a  mov     [rsp+80h+Class], 0; Class
0x180016a73  call    cs:__imp_ZwCreateKey
0x180016a79  mov     ebx, eax
0x180016a7b  test    eax, eax
0x180016a7d  jns     loc_1800169F5
0x180016a83  lea     r9, aNtcreatekeyFai; "NtCreateKey failed %x for %ws"
0x180016a8a  mov     r8d, 6D9h
0x180016a90  jmp     short loc_180016A2F
0x180016a92  lea     r9, aNtopenkeyFaile; "NtOpenKey failed %x for %ws"
0x180016a99  mov     r8d, 6E1h
0x180016a9f  jmp     short loc_180016A2F
```
