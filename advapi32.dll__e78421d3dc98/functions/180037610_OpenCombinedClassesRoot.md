# OpenCombinedClassesRoot

- ea: `0x180037610`
- end: `0x18003771b`
- name: `OpenCombinedClassesRoot`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800609d8`

## callees

- `0x1800245f0`
- `0x180037610`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x180037698`
- `ntdll!RtlCopyUnicodeString` at `0x180037698`
- `ntdll!RtlAppendUnicodeToString` at `0x1800376a9`
- `ntdll!RtlAppendUnicodeToString` at `0x1800376a9`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180037642`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180037642`
- `ntdll!RtlFreeUnicodeString` at `0x180037683`
- `ntdll!RtlFreeUnicodeString` at `0x1800376ec`
- `ntdll!RtlFreeUnicodeString` at `0x1800376f6`
- `ntdll!RtlFreeUnicodeString` at `0x180037683`
- `ntdll!RtlFreeUnicodeString` at `0x1800376ec`
- `ntdll!RtlFreeUnicodeString` at `0x1800376f6`
- `ntdll!RtlAllocateHeap` at `0x180037670`
- `ntdll!RtlAllocateHeap` at `0x180037670`

## pseudocode

```c
NTSTATUS __fastcall OpenCombinedClassesRoot(__int64 a1, _QWORD *a2)
{
  NTSTATUS result; // eax
  int v4; // r9d
  int v5; // edi
  void *v6; // [rsp+20h] [rbp-60h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+40h] [rbp-40h] BYREF
  int v9[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v10; // [rsp+58h] [rbp-28h]
  struct _UNICODE_STRING *p_DestinationString; // [rsp+60h] [rbp-20h]
  int v12; // [rsp+68h] [rbp-18h]
  int v13; // [rsp+6Ch] [rbp-14h]
  __int128 v14; // [rsp+70h] [rbp-10h]

  v9[1] = 0;
  v13 = 0;
  KeyPath = 0;
  DestinationString = 0;
  result = RtlFormatCurrentUserKeyPath(&KeyPath);
  if ( result >= 0 )
  {
    DestinationString.MaximumLength = KeyPath.MaximumLength + 18;
    DestinationString.Buffer = (PWSTR)RtlAllocateHeap(
                                        NtCurrentPeb()->ProcessHeap,
                                        0,
                                        (unsigned __int16)(KeyPath.MaximumLength + 18));
    if ( DestinationString.Buffer )
    {
      RtlCopyUnicodeString(&DestinationString, &KeyPath);
      RtlAppendUnicodeToString(&DestinationString, L"_Classes");
      v9[0] = 48;
      p_DestinationString = &DestinationString;
      v10 = 0;
      v12 = 64;
      v14 = 0;
      v5 = Wow64NtOpenKey((int)a2, 0x2000000, (int)v9, v4, v6);
      RtlFreeUnicodeString(&DestinationString);
      RtlFreeUnicodeString(&KeyPath);
      if ( v5 >= 0 )
        *a2 |= 2uLL;
      return v5;
    }
    else
    {
      RtlFreeUnicodeString(&KeyPath);
      return -1073741670;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180037610  mov     [rsp-8+arg_0], rbx
0x180037615  mov     [rsp-8+arg_8], rdi
0x18003761a  push    rbp
0x18003761b  mov     rbp, rsp
0x18003761e  sub     rsp, 80h
0x180037625  xor     eax, eax
0x180037627  lea     rcx, [rbp+KeyPath]; KeyPath
0x18003762b  xorps   xmm0, xmm0
0x18003762e  mov     [rbp+var_2C], eax
0x180037631  xorps   xmm1, xmm1
0x180037634  mov     [rbp+var_14], eax
0x180037637  movups  xmmword ptr [rbp+KeyPath.Length], xmm0
0x18003763b  mov     rbx, rdx
0x18003763e  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x180037642  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x180037648  test    eax, eax
0x18003764a  js      loc_180037706
0x180037650  movzx   eax, [rbp+KeyPath.MaximumLength]
0x180037654  xor     edx, edx; Flags
0x180037656  add     ax, 12h
0x18003765a  movzx   r8d, ax; Size
0x18003765e  mov     [rbp+DestinationString.MaximumLength], r8w
0x180037663  mov     rcx, gs:60h
0x18003766c  mov     rcx, [rcx+30h]; HeapHandle
0x180037670  call    cs:__imp_RtlAllocateHeap
0x180037676  mov     [rbp+DestinationString.Buffer], rax
0x18003767a  test    rax, rax
0x18003767d  jnz     short loc_180037690
0x18003767f  lea     rcx, [rbp+KeyPath]; UnicodeString
0x180037683  call    cs:__imp_RtlFreeUnicodeString
0x180037689  mov     eax, 0C000009Ah
0x18003768e  jmp     short loc_180037706
0x180037690  lea     rdx, [rbp+KeyPath]; SourceString
0x180037694  lea     rcx, [rbp+DestinationString]; DestinationString
0x180037698  call    cs:__imp_RtlCopyUnicodeString
0x18003769e  lea     rdx, aClasses_0; "_Classes"
0x1800376a5  lea     rcx, [rbp+DestinationString]; Destination
0x1800376a9  call    cs:__imp_RtlAppendUnicodeToString
0x1800376af  lea     rax, [rbp+DestinationString]
0x1800376b3  mov     [rbp+var_30], 30h ; '0'
0x1800376ba  xorps   xmm0, xmm0
0x1800376bd  mov     [rbp+var_20], rax
0x1800376c1  lea     r8, [rbp+var_30]; int
0x1800376c5  mov     [rbp+var_28], 0
0x1800376cd  mov     edx, 2000000h; int
0x1800376d2  mov     [rbp+var_18], 40h ; '@'
0x1800376d9  mov     rcx, rbx; int
0x1800376dc  movdqu  [rbp+var_10], xmm0
0x1800376e1  call    Wow64NtOpenKey
0x1800376e6  lea     rcx, [rbp+DestinationString]; UnicodeString
0x1800376ea  mov     edi, eax
0x1800376ec  call    cs:__imp_RtlFreeUnicodeString
0x1800376f2  lea     rcx, [rbp+KeyPath]; UnicodeString
0x1800376f6  call    cs:__imp_RtlFreeUnicodeString
0x1800376fc  test    edi, edi
0x1800376fe  js      short loc_180037704
0x180037700  or      qword ptr [rbx], 2
0x180037704  mov     eax, edi
0x180037706  lea     r11, [rsp+80h+var_s0]
0x18003770e  mov     rbx, [r11+10h]
0x180037712  mov     rdi, [r11+18h]
0x180037716  mov     rsp, r11
0x180037719  pop     rbp
0x18003771a  retn
```
