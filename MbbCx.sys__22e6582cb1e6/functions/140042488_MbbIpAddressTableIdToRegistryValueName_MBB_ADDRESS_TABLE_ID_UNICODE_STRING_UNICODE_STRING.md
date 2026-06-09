# MbbIpAddressTableIdToRegistryValueName(MBB_ADDRESS_TABLE_ID,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x140042488`
- end: `0x140042536`
- name: `?MbbIpAddressTableIdToRegistryValueName@@YAXW4MBB_ADDRESS_TABLE_ID@@PEAU_UNICODE_STRING@@1@Z`
- size: `174`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140043eb4`
- `0x140045688`

## callees

- `0x140042488`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400424a4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400424b5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400424a4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400424b5`

## pseudocode

```c
void __fastcall MbbIpAddressTableIdToRegistryValueName(int a1, struct _UNICODE_STRING *a2, struct _UNICODE_STRING *a3)
{
  int v6; // ebx
  const wchar_t *v7; // rax
  const wchar_t *v8; // rdx

  RtlInitUnicodeString(a2, 0);
  RtlInitUnicodeString(a3, 0);
  if ( !a1 )
  {
    v8 = L"LastIPv4";
    v7 = L"LastIPv6";
    goto LABEL_7;
  }
  v6 = a1 - 1;
  if ( !v6 )
  {
    v8 = L"LastGWv4";
    v7 = L"LastGWv6";
LABEL_7:
    *(_QWORD *)&a2->Length = 1179664;
    a2->Buffer = (wchar_t *)v8;
    *(_QWORD *)&a3->Length = 1179664;
    goto LABEL_8;
  }
  if ( v6 != 1 )
    return;
  *(_QWORD *)&a2->Length = 1310738;
  a2->Buffer = L"LastDNSv4";
  v7 = L"LastDNSv6";
  *(_QWORD *)&a3->Length = 1310738;
LABEL_8:
  a3->Buffer = (wchar_t *)v7;
}

```

## disassembly

```asm
0x140042488  mov     [rsp+arg_0], rbx
0x14004248d  mov     [rsp+arg_8], rsi
0x140042492  push    rdi
0x140042493  sub     rsp, 20h
0x140042497  mov     rsi, rdx
0x14004249a  mov     ebx, ecx
0x14004249c  mov     rcx, rsi; DestinationString
0x14004249f  xor     edx, edx; SourceString
0x1400424a1  mov     rdi, r8
0x1400424a4  call    cs:__imp_RtlInitUnicodeString
0x1400424ab  nop     dword ptr [rax+rax+00h]
0x1400424b0  xor     edx, edx; SourceString
0x1400424b2  mov     rcx, rdi; DestinationString
0x1400424b5  call    cs:__imp_RtlInitUnicodeString
0x1400424bc  nop     dword ptr [rax+rax+00h]
0x1400424c1  test    ebx, ebx
0x1400424c3  jz      short loc_140042501
0x1400424c5  sub     ebx, 1
0x1400424c8  jz      short loc_1400424F1
0x1400424ca  cmp     ebx, 1
0x1400424cd  jnz     short loc_140042525
0x1400424cf  lea     rcx, aLastdnsv4; "LastDNSv4"
0x1400424d6  mov     qword ptr [rsi], 140012h
0x1400424dd  mov     [rsi+8], rcx
0x1400424e1  lea     rax, aLastdnsv6; "LastDNSv6"
0x1400424e8  mov     qword ptr [rdi], 140012h
0x1400424ef  jmp     short loc_140042521
0x1400424f1  lea     rdx, aLastgwv4; "LastGWv4"
0x1400424f8  lea     rax, aLastgwv6; "LastGWv6"
0x1400424ff  jmp     short loc_14004250F
0x140042501  lea     rdx, aLastipv4; "LastIPv4"
0x140042508  lea     rax, aLastipv6; "LastIPv6"
0x14004250f  mov     qword ptr [rsi], 120010h
0x140042516  mov     [rsi+8], rdx
0x14004251a  mov     qword ptr [rdi], 120010h
0x140042521  mov     [rdi+8], rax
0x140042525  mov     rbx, [rsp+28h+arg_0]
0x14004252a  mov     rsi, [rsp+28h+arg_8]
0x14004252f  add     rsp, 20h
0x140042533  pop     rdi
0x140042534  retn
```
