# GameInputModule::IsXbox(void)

- ea: `0x1400066d0`
- end: `0x14000674a`
- name: `?IsXbox@GameInputModule@@CA_NXZ`
- size: `122`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400068e0`
- `0x140006a78`

## callees

- `0x1400066d0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1400066f7`
- `ntdll!RtlInitUnicodeString` at `0x1400066f7`
- `ntdll!NtQueryLicenseValue` at `0x140006719`
- `ntdll!NtQueryLicenseValue` at `0x140006719`

## pseudocode

```c
bool GameInputModule::IsXbox(void)
{
  struct _UNICODE_STRING v1; // [rsp+30h] [rbp-18h] BYREF
  int v2; // [rsp+50h] [rbp+8h] BYREF
  int v3; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  v3 = 0;
  v1 = 0;
  RtlInitUnicodeString(&v1, L"Kernel-ProductInfo");
  if ( (int)NtQueryLicenseValue(&v1, 0, &v2, 4, &v3) < 0 )
    return 0;
  if ( ((v2 - 192) & 0xFFFFFFFD) != 0 )
    return v2 == 195;
  return 1;
}

```

## disassembly

```asm
0x1400066d0  mov     rax, rsp
0x1400066d3  sub     rsp, 48h
0x1400066d7  xorps   xmm0, xmm0
0x1400066da  mov     dword ptr [rax+8], 0
0x1400066e1  lea     rdx, SourceString; "Kernel-ProductInfo"
0x1400066e8  mov     dword ptr [rax+10h], 0
0x1400066ef  lea     rcx, [rax-18h]; DestinationString
0x1400066f3  movups  xmmword ptr [rax-18h], xmm0
0x1400066f7  call    cs:__imp_RtlInitUnicodeString
0x1400066fd  lea     rax, [rsp+48h+arg_8]
0x140006702  mov     r9d, 4
0x140006708  lea     r8, [rsp+48h+arg_0]
0x14000670d  mov     [rsp+48h+var_28], rax
0x140006712  xor     edx, edx
0x140006714  lea     rcx, [rsp+48h+var_18]
0x140006719  call    cs:__imp_NtQueryLicenseValue
0x14000671f  test    eax, eax
0x140006721  js      short loc_140006743
0x140006723  mov     ecx, [rsp+48h+arg_0]
0x140006727  lea     eax, [rcx-0C0h]
0x14000672d  test    eax, 0FFFFFFFDh
0x140006732  jz      short loc_14000673F
0x140006734  cmp     ecx, 0C3h
0x14000673a  setz    al
0x14000673d  jmp     short loc_140006745
0x14000673f  mov     al, 1
0x140006741  jmp     short loc_140006745
0x140006743  xor     al, al
0x140006745  add     rsp, 48h
0x140006749  retn
```
