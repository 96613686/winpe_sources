# BiSetRegistryValue

- ea: `0x14001fc5c`
- end: `0x14001fd74`
- name: `BiSetRegistryValue`
- size: `280`
- prototype: `__int64 __fastcall(unsigned __int64, const WCHAR *, const WCHAR *, ULONG, PVOID Data, ULONG DataSize)`
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140014130`
- `0x140018b54`
- `0x14001adb8`
- `0x14001af00`
- `0x14001b92c`
- `0x14001c03c`
- `0x14001c794`
- `0x1400207d4`
- `0x14002090c`
- `0x140021c10`

## callees

- `0x14001e5e4`
- `0x14001f980`
- `0x14001fc5c`

## import_xrefs

- `ntdll!ZwSetValueKey` at `0x14001fd04`
- `ntdll!ZwSetValueKey` at `0x14001fd04`
- `ntdll!RtlInitUnicodeString` at `0x14001fc95`
- `ntdll!RtlInitUnicodeString` at `0x14001fc95`

## pseudocode

```c
__int64 __fastcall BiSetRegistryValue(
        unsigned __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        ULONG a4,
        PVOID Data,
        ULONG DataSize)
{
  unsigned int i; // esi
  int v11; // edi
  HANDLE KeyHandle; // [rsp+38h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF

  DestinationString = 0;
  for ( i = 0; ; ++i )
  {
    RtlInitUnicodeString(&DestinationString, a2);
    a1 &= ~2uLL;
    KeyHandle = 0;
    if ( a3 )
    {
      v11 = BiOpenKey(a1, a3, 0x2001Fu, &KeyHandle);
      if ( v11 < 0 )
        goto LABEL_7;
    }
    else
    {
      KeyHandle = (HANDLE)a1;
    }
    v11 = ZwSetValueKey(KeyHandle, &DestinationString, 0, a4, Data, DataSize);
LABEL_7:
    if ( KeyHandle != (HANDLE)a1 && KeyHandle )
      BiCloseKey(KeyHandle);
    if ( v11 == -1073741443 )
    {
      __debugbreak();
      if ( i < 5 )
        continue;
    }
    break;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14001fc5c  mov     rax, rsp
0x14001fc5f  mov     [rax+20h], r9d
0x14001fc63  mov     [rax+18h], r8
0x14001fc67  mov     [rax+10h], rdx
0x14001fc6b  push    rbx
0x14001fc6c  push    rsi
0x14001fc6d  push    rdi
0x14001fc6e  push    r12
0x14001fc70  push    r14
0x14001fc72  push    r15
0x14001fc74  sub     rsp, 58h
0x14001fc78  mov     r12d, r9d
0x14001fc7b  mov     r14, r8
0x14001fc7e  mov     r15, rdx
0x14001fc81  mov     rbx, rcx
0x14001fc84  xorps   xmm0, xmm0
0x14001fc87  movups  xmmword ptr [rax-48h], xmm0
0x14001fc8b  xor     esi, esi
0x14001fc8d  mov     rdx, r15; SourceString
0x14001fc90  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x14001fc95  call    cs:__imp_RtlInitUnicodeString
0x14001fc9b  and     rbx, 0FFFFFFFFFFFFFFFDh
0x14001fc9f  mov     [rsp+88h+arg_0], rbx
0x14001fca7  mov     [rsp+88h+KeyHandle], 0
0x14001fcb0  test    r14, r14
0x14001fcb3  jz      short loc_14001FCD7
0x14001fcb5  lea     r9, [rsp+88h+KeyHandle]
0x14001fcba  mov     r8d, 2001Fh
0x14001fcc0  mov     rdx, r14
0x14001fcc3  mov     rcx, rbx
0x14001fcc6  call    BiOpenKey
0x14001fccb  mov     edi, eax
0x14001fccd  mov     [rsp+88h+var_58], eax
0x14001fcd1  test    eax, eax
0x14001fcd3  jns     short loc_14001FCDC
0x14001fcd5  jmp     short loc_14001FD10
0x14001fcd7  mov     [rsp+88h+KeyHandle], rbx
0x14001fcdc  mov     eax, [rsp+88h+arg_28]
0x14001fce3  mov     [rsp+88h+DataSize], eax; DataSize
0x14001fce7  mov     rax, [rsp+88h+arg_20]
0x14001fcef  mov     [rsp+88h+Data], rax; Data
0x14001fcf4  mov     r9d, r12d; Type
0x14001fcf7  xor     r8d, r8d; TitleIndex
0x14001fcfa  lea     rdx, [rsp+88h+DestinationString]; ValueName
0x14001fcff  mov     rcx, [rsp+88h+KeyHandle]; KeyHandle
0x14001fd04  call    cs:__imp_ZwSetValueKey
0x14001fd0a  mov     edi, eax
0x14001fd0c  mov     [rsp+88h+var_58], eax
0x14001fd10  mov     rcx, [rsp+88h+KeyHandle]; Handle
0x14001fd15  cmp     rcx, rbx
0x14001fd18  jz      short loc_14001FD24
0x14001fd1a  test    rcx, rcx
0x14001fd1d  jz      short loc_14001FD24
0x14001fd1f  call    BiCloseKey
0x14001fd24  cmp     edi, 0C000017Dh
0x14001fd2a  jnz     short loc_14001FD64
0x14001fd2c  int     3; Trap to Debugger
0x14001fd2d  jmp     short loc_14001FD58
0x14001fd2f  mov     esi, 5
0x14001fd34  mov     r12d, [rsp+88h+arg_18]
0x14001fd3c  mov     r14, [rsp+88h+arg_10]
0x14001fd44  mov     r15, [rsp+88h+arg_8]
0x14001fd4c  mov     rbx, [rsp+88h+arg_0]
0x14001fd54  mov     edi, [rsp+88h+var_58]
0x14001fd58  cmp     esi, 5
0x14001fd5b  jnb     short loc_14001FD64
0x14001fd5d  inc     esi
0x14001fd5f  jmp     loc_14001FC8D
0x14001fd64  mov     eax, edi
0x14001fd66  add     rsp, 58h
0x14001fd6a  pop     r15
0x14001fd6c  pop     r14
0x14001fd6e  pop     r12
0x14001fd70  pop     rdi
0x14001fd71  pop     rsi
0x14001fd72  pop     rbx
0x14001fd73  retn
```
