# USBSTOR_InRootContainer

- ea: `0x1400208c0`
- end: `0x1400209ec`
- name: `USBSTOR_InRootContainer`
- size: `300`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14001f964`
- `0x14001fca8`

## callees

- `0x140013950`
- `0x140013d40`
- `0x1400208c0`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140020961`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140020961`
- `ntoskrnl!IoGetDeviceProperty` at `0x14002098d`
- `ntoskrnl!IoGetDeviceProperty` at `0x14002098d`
- `ntoskrnl!_wcsnicmp` at `0x1400209ac`
- `ntoskrnl!_wcsnicmp` at `0x1400209ac`

## string_xrefs

- `0x14002093c`: `\Registry\Machine\System\CurrentControlSet\Enum\HTREE\ROOT\0`

## pseudocode

```c
__int64 __fastcall USBSTOR_InRootContainer(PDEVICE_OBJECT DeviceObject, bool *a2)
{
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v6[3]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v7[22]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Str2[80]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t PropertyBuffer[80]; // [rsp+1A0h] [rbp+A0h] BYREF

  v6[0] = 10092544;
  ResultLength = 0;
  memset(v7, 0, 0xA8u);
  LODWORD(v7[1]) = 292;
  v6[1] = Str2;
  LODWORD(v7[4]) = 0x1000000;
  v7[2] = L"ContainerID";
  v7[3] = v6;
  if ( (int)RtlQueryRegistryValuesEx(0, L"\\Registry\\Machine\\System\\CurrentControlSet\\Enum\\HTREE\\ROOT\\0", v7) < 0
    || IoGetDeviceProperty(DeviceObject, DevicePropertyContainerID, 0x9Au, PropertyBuffer, &ResultLength) < 0 )
  {
    return 3221226021LL;
  }
  *a2 = _wcsnicmp(PropertyBuffer, Str2, 0x4Du) == 0;
  return 0;
}

```

## disassembly

```asm
0x1400208c0  mov     [rsp-8+arg_10], rbx
0x1400208c5  push    rbp
0x1400208c6  push    rdi
0x1400208c7  push    r14
0x1400208c9  lea     rbp, [rsp-150h]
0x1400208d1  sub     rsp, 250h
0x1400208d8  mov     rax, cs:__security_cookie
0x1400208df  xor     rax, rsp
0x1400208e2  mov     [rbp+160h+var_20], rax
0x1400208e9  mov     rbx, rdx
0x1400208ec  mov     [rsp+260h+var_228], 9A0000h
0x1400208f5  mov     rdi, rcx
0x1400208f8  mov     [rsp+260h+var_230], 0
0x140020900  xor     edx, edx; Val
0x140020902  lea     rcx, [rsp+260h+var_210]; void *
0x140020907  mov     r8d, 0A8h; Size
0x14002090d  call    memset
0x140020912  lea     rax, [rbp+160h+Str2]
0x140020916  mov     [rsp+260h+var_208], 124h
0x14002091e  mov     [rsp+260h+var_220], rax
0x140020923  lea     r8, [rsp+260h+var_210]
0x140020928  lea     rax, aContainerid; "ContainerID"
0x14002092f  mov     [rsp+260h+var_1F0], 1000000h
0x140020937  mov     [rsp+260h+var_200], rax
0x14002093c  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\System\\CurrentCon"...
0x140020943  lea     rax, [rsp+260h+var_228]
0x140020948  mov     [rsp+260h+ResultLength], 0
0x140020951  xor     r9d, r9d
0x140020954  mov     [rsp+260h+var_1F8], rax
0x140020959  xor     ecx, ecx
0x14002095b  mov     r14d, 9Ah
0x140020961  call    cs:__imp_RtlQueryRegistryValuesEx
0x140020968  nop     dword ptr [rax+rax+00h]
0x14002096d  test    eax, eax
0x14002096f  js      short loc_1400209C3
0x140020971  lea     rax, [rsp+260h+var_230]
0x140020976  mov     r8d, r14d; BufferLength
0x140020979  lea     r9, [rbp+160h+PropertyBuffer]; PropertyBuffer
0x140020980  mov     [rsp+260h+ResultLength], rax; ResultLength
0x140020985  mov     edx, 16h; DeviceProperty
0x14002098a  mov     rcx, rdi; DeviceObject
0x14002098d  call    cs:__imp_IoGetDeviceProperty
0x140020994  nop     dword ptr [rax+rax+00h]
0x140020999  test    eax, eax
0x14002099b  js      short loc_1400209C3
0x14002099d  lea     r8d, [r14-4Dh]; MaxCount
0x1400209a1  lea     rdx, [rbp+160h+Str2]; Str2
0x1400209a5  lea     rcx, [rbp+160h+PropertyBuffer]; Str1
0x1400209ac  call    cs:__imp__wcsnicmp
0x1400209b3  nop     dword ptr [rax+rax+00h]
0x1400209b8  test    eax, eax
0x1400209ba  setz    al
0x1400209bd  mov     [rbx], al
0x1400209bf  xor     eax, eax
0x1400209c1  jmp     short loc_1400209C8
0x1400209c3  mov     eax, 0C0000225h
0x1400209c8  mov     rcx, [rbp+160h+var_20]
0x1400209cf  xor     rcx, rsp; StackCookie
0x1400209d2  call    __security_check_cookie
0x1400209d7  mov     rbx, [rsp+260h+arg_10]
0x1400209df  add     rsp, 250h
0x1400209e6  pop     r14
0x1400209e8  pop     rdi
0x1400209e9  pop     rbp
0x1400209ea  retn
```
