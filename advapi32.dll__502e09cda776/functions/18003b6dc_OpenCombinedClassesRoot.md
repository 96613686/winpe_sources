# OpenCombinedClassesRoot

- ea: `0x18003b6dc`
- end: `0x18003b815`
- name: `OpenCombinedClassesRoot`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006d3f0`

## callees

- `0x180026e34`
- `0x18003b6dc`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x18003b779`
- `ntdll!RtlCopyUnicodeString` at `0x18003b779`
- `ntdll!RtlAppendUnicodeToString` at `0x18003b790`
- `ntdll!RtlAppendUnicodeToString` at `0x18003b790`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18003b70e`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18003b70e`
- `ntdll!RtlFreeUnicodeString` at `0x18003b75b`
- `ntdll!RtlFreeUnicodeString` at `0x18003b7d9`
- `ntdll!RtlFreeUnicodeString` at `0x18003b7e9`
- `ntdll!RtlFreeUnicodeString` at `0x18003b75b`
- `ntdll!RtlFreeUnicodeString` at `0x18003b7d9`
- `ntdll!RtlFreeUnicodeString` at `0x18003b7e9`
- `ntdll!RtlAllocateHeap` at `0x18003b742`
- `ntdll!RtlAllocateHeap` at `0x18003b742`

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
0x18003b6dc  mov     [rsp-8+arg_0], rbx
0x18003b6e1  mov     [rsp-8+arg_8], rdi
0x18003b6e6  push    rbp
0x18003b6e7  mov     rbp, rsp
0x18003b6ea  sub     rsp, 80h
0x18003b6f1  xor     eax, eax
0x18003b6f3  lea     rcx, [rbp+KeyPath]; KeyPath
0x18003b6f7  xorps   xmm0, xmm0
0x18003b6fa  mov     [rbp+var_2C], eax
0x18003b6fd  xorps   xmm1, xmm1
0x18003b700  mov     [rbp+var_14], eax
0x18003b703  movups  xmmword ptr [rbp+KeyPath.Length], xmm0
0x18003b707  mov     rbx, rdx
0x18003b70a  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x18003b70e  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18003b715  nop     dword ptr [rax+rax+00h]
0x18003b71a  test    eax, eax
0x18003b71c  js      loc_18003B7FF
0x18003b722  movzx   eax, [rbp+KeyPath.MaximumLength]
0x18003b726  xor     edx, edx; Flags
0x18003b728  add     ax, 12h
0x18003b72c  movzx   r8d, ax; Size
0x18003b730  mov     [rbp+DestinationString.MaximumLength], r8w
0x18003b735  mov     rcx, gs:60h
0x18003b73e  mov     rcx, [rcx+30h]; HeapHandle
0x18003b742  call    cs:__imp_RtlAllocateHeap
0x18003b749  nop     dword ptr [rax+rax+00h]
0x18003b74e  mov     [rbp+DestinationString.Buffer], rax
0x18003b752  test    rax, rax
0x18003b755  jnz     short loc_18003B771
0x18003b757  lea     rcx, [rbp+KeyPath]; UnicodeString
0x18003b75b  call    cs:__imp_RtlFreeUnicodeString
0x18003b762  nop     dword ptr [rax+rax+00h]
0x18003b767  mov     eax, 0C000009Ah
0x18003b76c  jmp     loc_18003B7FF
0x18003b771  lea     rdx, [rbp+KeyPath]; SourceString
0x18003b775  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003b779  call    cs:__imp_RtlCopyUnicodeString
0x18003b780  nop     dword ptr [rax+rax+00h]
0x18003b785  lea     rdx, aClasses_0; "_Classes"
0x18003b78c  lea     rcx, [rbp+DestinationString]; Destination
0x18003b790  call    cs:__imp_RtlAppendUnicodeToString
0x18003b797  nop     dword ptr [rax+rax+00h]
0x18003b79c  lea     rax, [rbp+DestinationString]
0x18003b7a0  mov     [rbp+var_30], 30h ; '0'
0x18003b7a7  xorps   xmm0, xmm0
0x18003b7aa  mov     [rbp+var_20], rax
0x18003b7ae  lea     r8, [rbp+var_30]; int
0x18003b7b2  mov     [rbp+var_28], 0
0x18003b7ba  mov     edx, 2000000h; int
0x18003b7bf  mov     [rbp+var_18], 40h ; '@'
0x18003b7c6  mov     rcx, rbx; int
0x18003b7c9  movdqu  [rbp+var_10], xmm0
0x18003b7ce  call    Wow64NtOpenKey
0x18003b7d3  lea     rcx, [rbp+DestinationString]; UnicodeString
0x18003b7d7  mov     edi, eax
0x18003b7d9  call    cs:__imp_RtlFreeUnicodeString
0x18003b7e0  nop     dword ptr [rax+rax+00h]
0x18003b7e5  lea     rcx, [rbp+KeyPath]; UnicodeString
0x18003b7e9  call    cs:__imp_RtlFreeUnicodeString
0x18003b7f0  nop     dword ptr [rax+rax+00h]
0x18003b7f5  test    edi, edi
0x18003b7f7  js      short loc_18003B7FD
0x18003b7f9  or      qword ptr [rbx], 2
0x18003b7fd  mov     eax, edi
0x18003b7ff  lea     r11, [rsp+80h+var_s0]
0x18003b807  mov     rbx, [r11+10h]
0x18003b80b  mov     rdi, [r11+18h]
0x18003b80f  mov     rsp, r11
0x18003b812  pop     rbp
0x18003b813  retn
```
