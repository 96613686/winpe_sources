# MpClearFileStateGenericTable

- ea: `0x14006cfc8`
- end: `0x14006d058`
- name: `MpClearFileStateGenericTable`
- size: `144`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14006cb28`
- `0x14006ce34`
- `0x14006cec4`

## callees

- `0x14006cfc8`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTable` at `0x14006d00d`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x14006d00d`
- `ntoskrnl!RtlIsGenericTableEmpty` at `0x14006d01c`
- `ntoskrnl!RtlIsGenericTableEmpty` at `0x14006d01c`
- `ntoskrnl!RtlGetElementGenericTable` at `0x14006cff6`
- `ntoskrnl!RtlGetElementGenericTable` at `0x14006cff6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d034`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d034`

## pseudocode

```c
void __fastcall MpClearFileStateGenericTable(__int64 *a1)
{
  __int64 v1; // rdi
  PVOID ElementGenericTable; // rax

  if ( a1 )
  {
    v1 = *a1;
    if ( *a1 )
    {
      while ( !RtlIsGenericTableEmpty((PRTL_GENERIC_TABLE)(v1 + 16)) )
      {
        ElementGenericTable = RtlGetElementGenericTable((PRTL_GENERIC_TABLE)(v1 + 16), 0);
        if ( !ElementGenericTable )
          break;
        RtlDeleteElementGenericTable((PRTL_GENERIC_TABLE)(v1 + 16), ElementGenericTable);
      }
      ExFreePoolWithTag((PVOID)v1, 0x6574504Du);
      *a1 = 0;
    }
  }
}

```

## disassembly

```asm
0x14006cfc8  test    rcx, rcx
0x14006cfcb  jz      locret_14006D056
0x14006cfd1  mov     [rsp+arg_0], rbx
0x14006cfd6  mov     [rsp+arg_8], rsi
0x14006cfdb  push    rdi
0x14006cfdc  sub     rsp, 20h
0x14006cfe0  mov     rdi, [rcx]
0x14006cfe3  mov     rbx, rcx
0x14006cfe6  test    rdi, rdi
0x14006cfe9  jz      short loc_14006D047
0x14006cfeb  lea     rsi, [rdi+10h]
0x14006cfef  jmp     short loc_14006D019
0x14006cff1  xor     edx, edx; I
0x14006cff3  mov     rcx, rsi; Table
0x14006cff6  call    cs:__imp_RtlGetElementGenericTable
0x14006cffd  nop     dword ptr [rax+rax+00h]
0x14006d002  test    rax, rax
0x14006d005  jz      short loc_14006D02C
0x14006d007  mov     rdx, rax; Buffer
0x14006d00a  mov     rcx, rsi; Table
0x14006d00d  call    cs:__imp_RtlDeleteElementGenericTable
0x14006d014  nop     dword ptr [rax+rax+00h]
0x14006d019  mov     rcx, rsi; Table
0x14006d01c  call    cs:__imp_RtlIsGenericTableEmpty
0x14006d023  nop     dword ptr [rax+rax+00h]
0x14006d028  test    al, al
0x14006d02a  jz      short loc_14006CFF1
0x14006d02c  mov     edx, 6574504Dh; Tag
0x14006d031  mov     rcx, rdi; P
0x14006d034  call    cs:__imp_ExFreePoolWithTag
0x14006d03b  nop     dword ptr [rax+rax+00h]
0x14006d040  mov     qword ptr [rbx], 0
0x14006d047  mov     rbx, [rsp+28h+arg_0]
0x14006d04c  mov     rsi, [rsp+28h+arg_8]
0x14006d051  add     rsp, 20h
0x14006d055  pop     rdi
0x14006d056  retn
```
