# DriverEntry

- ea: `0x18010a230`
- end: `0x18010a2be`
- name: `DriverEntry`
- size: `142`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18005b6c0`
- `0x18010a230`
- `0x18010a2c4`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax

  if ( (int)sub_18010A2C4() >= 0 )
  {
    result = ((__int64 (__fastcall *)(PDRIVER_OBJECT, PUNICODE_STRING))(0x180000000LL + (unsigned int)dword_1800DA2D8))(
               DriverObject,
               RegistryPath);
    if ( result >= 0 )
    {
      qword_1800DB720 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)sub_1800332D0;
    }
    else if ( dword_1800DAEC8 )
    {
      dword_1800DAEC8 = 0;
    }
  }
  else
  {
    if ( dword_1800DAEC8 )
      dword_1800DAEC8 = 0;
    return -1073740955;
  }
  return result;
}

```

## disassembly

```asm
0x18010a230  mov     [rsp+arg_0], rbx
0x18010a235  push    rdi
0x18010a236  sub     rsp, 20h
0x18010a23a  mov     rdi, rdx
0x18010a23d  mov     rbx, rcx
0x18010a240  call    sub_18010A2C4
0x18010a245  test    eax, eax
0x18010a247  jns     short loc_18010A263
0x18010a249  cmp     cs:dword_1800DAEC8, 0
0x18010a250  jz      short loc_18010A25C
0x18010a252  mov     cs:dword_1800DAEC8, 0
0x18010a25c  mov     eax, 0C0000365h
0x18010a261  jmp     short loc_18010A2B2
0x18010a263  mov     eax, cs:dword_1800DA2D8
0x18010a269  lea     rcx, cs:180000000h
0x18010a270  add     rax, rcx
0x18010a273  mov     rdx, rdi
0x18010a276  mov     rcx, rbx
0x18010a279  call    cs:__guard_dispatch_icall_fptr
0x18010a27f  mov     ecx, eax
0x18010a281  test    eax, eax
0x18010a283  jns     short loc_18010A29A
0x18010a285  cmp     cs:dword_1800DAEC8, 0
0x18010a28c  jz      short loc_18010A2B2
0x18010a28e  mov     cs:dword_1800DAEC8, 0
0x18010a298  jmp     short loc_18010A2B2
0x18010a29a  mov     rax, [rbx+68h]
0x18010a29e  mov     cs:qword_1800DB720, rax
0x18010a2a5  lea     rax, sub_1800332D0
0x18010a2ac  mov     [rbx+68h], rax
0x18010a2b0  mov     eax, ecx
0x18010a2b2  mov     rbx, [rsp+28h+arg_0]
0x18010a2b7  add     rsp, 20h
0x18010a2bb  pop     rdi
0x18010a2bc  retn
```
