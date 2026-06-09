# DMCSP_DevInfo_GetModel

- ea: `0x180009340`
- end: `0x180009389`
- name: `DMCSP_DevInfo_GetModel`
- size: `73`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005384`
- `0x1800080f8`
- `0x180009340`

## string_xrefs

- `0x180009355`: `SystemProductName`

## pseudocode

```c
int __fastcall DMCSP_DevInfo_GetModel(unsigned int a1, unsigned __int16 *a2)
{
  int result; // eax

  result = RegLookupHelper(L"SYSTEM\\CurrentControlSet\\Control\\SystemInformation", L"SystemProductName", a1, a2);
  if ( result < 0 )
    return StringCchCopyW(a2, a1, L"Unknown");
  return result;
}

```

## disassembly

```asm
0x180009340  mov     [rsp+arg_0], rbx
0x180009345  push    rdi
0x180009346  sub     rsp, 20h
0x18000934a  mov     rbx, rdx
0x18000934d  mov     edi, ecx
0x18000934f  mov     r9, rdx; unsigned __int16 *
0x180009352  mov     r8d, ecx; unsigned int
0x180009355  lea     rdx, aSystemproductn; "SystemProductName"
0x18000935c  lea     rcx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Sys"...
0x180009363  call    ?RegLookupHelper@@YAJPEBG0KPEAG@Z; RegLookupHelper(ushort const *,ushort const *,ulong,ushort *)
0x180009368  test    eax, eax
0x18000936a  jns     short loc_18000937D
0x18000936c  mov     edx, edi; unsigned __int64
0x18000936e  lea     r8, aUnknown; "Unknown"
0x180009375  mov     rcx, rbx; unsigned __int16 *
0x180009378  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000937d  mov     rbx, [rsp+28h+arg_0]
0x180009382  add     rsp, 20h
0x180009386  pop     rdi
0x180009387  retn
```
