# USBSTOR_GlobalSelectiveSuspendSetting

- ea: `0x140027500`
- end: `0x1400275ab`
- name: `USBSTOR_GlobalSelectiveSuspendSetting`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140026f6c`

## callees

- `0x140013d40`
- `0x140027500`
- `0x1400275b4`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14002757f`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14002757f`

## string_xrefs

- `0x14002755e`: `\Registry\Machine\System\CurrentControlSet\Control\StorageDevicePolicies`

## pseudocode

```c
__int64 __fastcall USBSTOR_GlobalSelectiveSuspendSetting(__int64 a1)
{
  __int64 result; // rax
  _QWORD v3[14]; // [rsp+30h] [rbp-19h] BYREF
  int IsPlatformMobileOrAoac; // [rsp+B8h] [rbp+6Fh] BYREF

  IsPlatformMobileOrAoac = 0;
  IsPlatformMobileOrAoac = (unsigned __int8)USBSTOR_IsPlatformMobileOrAoac();
  memset(v3, 0, sizeof(v3));
  LODWORD(v3[1]) = 292;
  v3[2] = L"SelectiveSuspend";
  LODWORD(v3[4]) = 67108868;
  v3[3] = &IsPlatformMobileOrAoac;
  v3[5] = 0;
  LODWORD(v3[6]) = 0;
  result = RtlQueryRegistryValuesEx(
             0,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\StorageDevicePolicies",
             v3);
  if ( IsPlatformMobileOrAoac )
    *(_DWORD *)(a1 + 132) |= 0x80u;
  return result;
}

```

## disassembly

```asm
0x140027500  mov     [rsp-8+arg_0], rbx
0x140027505  push    rbp
0x140027506  lea     rbp, [rsp-57h]
0x14002750b  sub     rsp, 0A0h
0x140027512  mov     rbx, rcx
0x140027515  mov     [rbp+57h+arg_8], 0
0x14002751c  call    USBSTOR_IsPlatformMobileOrAoac
0x140027521  xor     edx, edx; Val
0x140027523  movzx   eax, al
0x140027526  lea     rcx, [rbp+57h+var_70]; void *
0x14002752a  mov     [rbp+57h+arg_8], eax
0x14002752d  lea     r8d, [rdx+70h]; Size
0x140027531  call    memset
0x140027536  lea     rax, aSelectivesuspe; "SelectiveSuspend"
0x14002753d  mov     [rbp+57h+var_68], 124h
0x140027544  mov     [rbp+57h+var_60], rax
0x140027548  lea     r8, [rbp+57h+var_70]
0x14002754c  lea     rax, [rbp+57h+arg_8]
0x140027550  mov     [rbp+57h+var_50], 4000004h
0x140027557  xor     r9d, r9d
0x14002755a  mov     [rbp+57h+var_58], rax
0x14002755e  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140027565  mov     [rbp+57h+var_48], 0
0x14002756d  xor     ecx, ecx
0x14002756f  mov     [rbp+57h+var_40], 0
0x140027576  mov     [rsp+0A0h+var_80], 0
0x14002757f  call    cs:__imp_RtlQueryRegistryValuesEx
0x140027586  nop     dword ptr [rax+rax+00h]
0x14002758b  cmp     [rbp+57h+arg_8], 0
0x14002758f  jz      short loc_140027599
0x140027591  bts     dword ptr [rbx+84h], 7
0x140027599  mov     rbx, [rsp+0A0h+arg_0]
0x1400275a1  add     rsp, 0A0h
0x1400275a8  pop     rbp
0x1400275a9  retn
```
