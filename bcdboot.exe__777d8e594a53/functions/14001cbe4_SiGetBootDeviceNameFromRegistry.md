# SiGetBootDeviceNameFromRegistry

- ea: `0x14001cbe4`
- end: `0x14001cc83`
- name: `SiGetBootDeviceNameFromRegistry`
- size: `159`
- prototype: `__int64 __fastcall(int, wchar_t **, __int64, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001cb14`
- `0x1400254d0`

## callees

- `0x14001cbe4`
- `0x14001d260`

## import_xrefs

- `msvcrt!_wcslwr` at `0x14001cc68`
- `msvcrt!_wcslwr` at `0x14001cc68`

## string_xrefs

- `0x14001cc0d`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control`

## pseudocode

```c
__int64 __fastcall SiGetBootDeviceNameFromRegistry(int a1, wchar_t **a2, __int64 a3, int a4)
{
  int RegistryValue; // edi
  wchar_t *v6; // rbx
  _QWORD v8[5]; // [rsp+30h] [rbp-28h]
  unsigned int v9; // [rsp+60h] [rbp+8h] BYREF
  wchar_t *String; // [rsp+70h] [rbp+18h] BYREF

  String = 0;
  v8[0] = L"FirmwareBootDevice";
  v9 = 0;
  v8[1] = L"SystemBootDevice";
  v8[2] = L"WindowsSysPartDevice";
  RegistryValue = SiGetRegistryValue(
                    a1,
                    v8[a1],
                    (unsigned int)L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control",
                    a4,
                    (__int64)&String,
                    (__int64)&v9);
  if ( RegistryValue >= 0 )
  {
    if ( v9 >= 4 )
    {
      v6 = String;
      _wcslwr(String);
      *a2 = v6;
    }
    else
    {
      return (unsigned int)-1073741823;
    }
  }
  return (unsigned int)RegistryValue;
}

```

## disassembly

```asm
0x14001cbe4  mov     r11, rsp
0x14001cbe7  mov     [r11+10h], rbx
0x14001cbeb  mov     [r11+20h], rsi
0x14001cbef  push    rdi
0x14001cbf0  sub     rsp, 50h
0x14001cbf4  mov     rsi, rdx
0x14001cbf7  mov     qword ptr [r11+18h], 0
0x14001cbff  lea     rax, aFirmwarebootde; "FirmwareBootDevice"
0x14001cc06  movsxd  rdx, ecx
0x14001cc09  mov     [r11-28h], rax
0x14001cc0d  lea     r8, aRegistryMachin_0; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14001cc14  lea     rax, aSystembootdevi; "SystemBootDevice"
0x14001cc1b  mov     [rsp+58h+arg_0], 0
0x14001cc23  mov     [r11-20h], rax
0x14001cc27  lea     rax, aWindowssyspart; "WindowsSysPartDevice"
0x14001cc2e  mov     [r11-18h], rax
0x14001cc32  lea     rax, [r11+8]
0x14001cc36  mov     rdx, [rsp+rdx*8+58h+var_28]
0x14001cc3b  mov     [r11-30h], rax
0x14001cc3f  lea     rax, [r11+18h]
0x14001cc43  mov     [r11-38h], rax
0x14001cc47  call    SiGetRegistryValue
0x14001cc4c  mov     edi, eax
0x14001cc4e  test    eax, eax
0x14001cc50  js      short loc_14001CC71
0x14001cc52  cmp     [rsp+58h+arg_0], 4
0x14001cc57  jnb     short loc_14001CC60
0x14001cc59  mov     edi, 0C0000001h
0x14001cc5e  jmp     short loc_14001CC71
0x14001cc60  mov     rbx, [rsp+58h+String]
0x14001cc65  mov     rcx, rbx; String
0x14001cc68  call    cs:__imp__wcslwr
0x14001cc6e  mov     [rsi], rbx
0x14001cc71  mov     rbx, [rsp+58h+arg_8]
0x14001cc76  mov     eax, edi
0x14001cc78  mov     rsi, [rsp+58h+arg_18]
0x14001cc7d  add     rsp, 50h
0x14001cc81  pop     rdi
0x14001cc82  retn
```
