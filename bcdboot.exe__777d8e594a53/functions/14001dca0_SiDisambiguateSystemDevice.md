# SiDisambiguateSystemDevice

- ea: `0x14001dca0`
- end: `0x14001dd5d`
- name: `SiDisambiguateSystemDevice`
- size: `189`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x14001dd64`

## callees

- `0x14001ce84`
- `0x14001d260`
- `0x14001dca0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x14001dd47`
- `ntdll!RtlFreeHeap` at `0x14001dd47`

## string_xrefs

- `0x14001dcc0`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\Syspart`
- `0x14001dcda`: `SystemPartition`

## pseudocode

```c
__int64 __fastcall SiDisambiguateSystemDevice(_DWORD *a1, _DWORD *a2, __int64 a3, int a4)
{
  int RegistryValue; // ebx
  int v8; // [rsp+30h] [rbp-10h] BYREF
  PVOID P; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v10; // [rsp+70h] [rbp+30h] BYREF
  int v11; // [rsp+78h] [rbp+38h] BYREF

  v11 = 0;
  v8 = 0;
  v10 = 0;
  P = 0;
  RegistryValue = SiGetRegistryValue(
                    (_DWORD)a1,
                    (unsigned int)L"SystemPartition",
                    (unsigned int)L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\Syspart",
                    a4,
                    (__int64)&P,
                    (__int64)&v10);
  if ( RegistryValue >= 0 )
  {
    if ( v10 >= 4 )
    {
      RegistryValue = SiGetDeviceNumberInformation(P, &v11, &v8);
      if ( RegistryValue >= 0 )
      {
        *a1 = v11;
        *a2 = v8;
      }
    }
    else
    {
      RegistryValue = -1073741823;
    }
  }
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return (unsigned int)RegistryValue;
}

```

## disassembly

```asm
0x14001dca0  mov     [rsp-18h+arg_0], rbx
0x14001dca5  push    rbp
0x14001dca6  push    rsi
0x14001dca7  push    r14
0x14001dca9  mov     rbp, rsp
0x14001dcac  sub     rsp, 40h
0x14001dcb0  lea     rax, [rbp+arg_10]
0x14001dcb4  mov     [rbp+arg_18], 0
0x14001dcbb  mov     [rsp+40h+var_18], rax
0x14001dcc0  lea     r8, aRegistryMachin_3; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14001dcc7  lea     rax, [rbp+P]
0x14001dccb  mov     [rbp+var_10], 0
0x14001dcd2  mov     rsi, rdx
0x14001dcd5  mov     [rsp+40h+var_20], rax
0x14001dcda  lea     rdx, aSystempartitio; "SystemPartition"
0x14001dce1  mov     [rbp+arg_10], 0
0x14001dce8  mov     r14, rcx
0x14001dceb  mov     [rbp+P], 0
0x14001dcf3  call    SiGetRegistryValue
0x14001dcf8  mov     ebx, eax
0x14001dcfa  test    eax, eax
0x14001dcfc  js      short loc_14001DD2D
0x14001dcfe  cmp     [rbp+arg_10], 4
0x14001dd02  jnb     short loc_14001DD0B
0x14001dd04  mov     ebx, 0C0000001h
0x14001dd09  jmp     short loc_14001DD2D
0x14001dd0b  mov     rcx, [rbp+P]
0x14001dd0f  lea     r8, [rbp+var_10]
0x14001dd13  lea     rdx, [rbp+arg_18]
0x14001dd17  call    SiGetDeviceNumberInformation
0x14001dd1c  mov     ebx, eax
0x14001dd1e  test    eax, eax
0x14001dd20  js      short loc_14001DD2D
0x14001dd22  mov     eax, [rbp+arg_18]
0x14001dd25  mov     [r14], eax
0x14001dd28  mov     eax, [rbp+var_10]
0x14001dd2b  mov     [rsi], eax
0x14001dd2d  cmp     [rbp+P], 0
0x14001dd32  jz      short loc_14001DD4D
0x14001dd34  mov     rcx, gs:60h
0x14001dd3d  xor     edx, edx; Flags
0x14001dd3f  mov     r8, [rbp+P]; P
0x14001dd43  mov     rcx, [rcx+30h]; HeapHandle
0x14001dd47  call    cs:__imp_RtlFreeHeap
0x14001dd4d  mov     eax, ebx
0x14001dd4f  mov     rbx, [rsp+40h+arg_0]
0x14001dd54  add     rsp, 40h
0x14001dd58  pop     r14
0x14001dd5a  pop     rsi
0x14001dd5b  pop     rbp
0x14001dd5c  retn
```
