# sub_14000BECC

- ea: `0x14000becc`
- end: `0x14000bf73`
- name: `sub_14000BECC`
- size: `167`
- prototype: `void __fastcall(_QWORD *, _BYTE *)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002974`
- `0x140002a14`
- `0x140009f18`
- `0x14000aa6c`
- `0x14000cd5c`
- `0x14000d260`
- `0x140029af8`

## callees

- `0x14000becc`
- `0x140029bd0`

## import_xrefs

- `ntdll!RtlPcToFileHeader` at `0x14000bf1c`
- `ntdll!RtlPcToFileHeader` at `0x14000bf1c`
- `KERNEL32!RaiseException` at `0x14000bf5d`
- `KERNEL32!RaiseException` at `0x14000bf5d`

## pseudocode

```c
void __fastcall sub_14000BECC(_QWORD *a1, _BYTE *a2)
{
  _BYTE *v2; // rbx
  ULONG_PTR v4; // rdi
  __int64 v5; // rcx
  PVOID v6; // rax
  PVOID BaseOfImage; // [rsp+20h] [rbp-38h] BYREF
  ULONG_PTR Arguments[6]; // [rsp+28h] [rbp-30h] BYREF

  v2 = a2;
  v4 = 429065504;
  if ( a2 && (*a2 & 0x10) != 0 )
  {
    v5 = *a1 - 8LL;
    v2 = *(_BYTE **)(*(_QWORD *)v5 + 48LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 64LL))(v5);
  }
  v6 = 0;
  BaseOfImage = 0;
  if ( v2 )
  {
    v6 = RtlPcToFileHeader(v2, &BaseOfImage);
    BaseOfImage = v6;
    if ( (*v2 & 8) != 0 || !v6 )
      v4 = 26820608;
  }
  Arguments[0] = v4;
  Arguments[1] = (ULONG_PTR)a1;
  Arguments[2] = (ULONG_PTR)v2;
  Arguments[3] = (ULONG_PTR)v6;
  RaiseException(0xE06D7363, 1u, 4u, Arguments);
}

```

## disassembly

```asm
0x14000becc  mov     [rsp+arg_10], rbx
0x14000bed1  mov     [rsp+arg_18], rsi
0x14000bed6  push    rdi
0x14000bed7  sub     rsp, 50h
0x14000bedb  mov     rbx, rdx
0x14000bede  mov     rsi, rcx
0x14000bee1  mov     edi, 19930520h
0x14000bee6  test    rdx, rdx
0x14000bee9  jz      short loc_14000BF08
0x14000beeb  test    byte ptr [rdx], 10h
0x14000beee  jz      short loc_14000BF08
0x14000bef0  mov     rcx, [rcx]
0x14000bef3  add     rcx, 0FFFFFFFFFFFFFFF8h
0x14000bef7  mov     rax, [rcx]
0x14000befa  mov     rbx, [rax+30h]
0x14000befe  mov     rax, [rax+40h]
0x14000bf02  call    cs:__guard_dispatch_icall_fptr
0x14000bf08  xor     eax, eax
0x14000bf0a  mov     [rsp+58h+BaseOfImage], rax
0x14000bf0f  test    rbx, rbx
0x14000bf12  jz      short loc_14000BF36
0x14000bf14  lea     rdx, [rsp+58h+BaseOfImage]; BaseOfImage
0x14000bf19  mov     rcx, rbx; PcValue
0x14000bf1c  call    cs:RtlPcToFileHeader
0x14000bf22  mov     [rsp+58h+BaseOfImage], rax
0x14000bf27  test    byte ptr [rbx], 8
0x14000bf2a  jnz     short loc_14000BF31
0x14000bf2c  test    rax, rax
0x14000bf2f  jnz     short loc_14000BF36
0x14000bf31  mov     edi, 1994000h
0x14000bf36  mov     edx, 1; dwExceptionFlags
0x14000bf3b  mov     [rsp+58h+Arguments], rdi
0x14000bf40  lea     r9, [rsp+58h+Arguments]; lpArguments
0x14000bf45  mov     [rsp+58h+var_28], rsi
0x14000bf4a  mov     ecx, 0E06D7363h; dwExceptionCode
0x14000bf4f  mov     [rsp+58h+var_20], rbx
0x14000bf54  mov     [rsp+58h+var_18], rax
0x14000bf59  lea     r8d, [rdx+3]; nNumberOfArguments
0x14000bf5d  call    cs:RaiseException
0x14000bf63  mov     rbx, [rsp+58h+arg_10]
0x14000bf68  mov     rsi, [rsp+58h+arg_18]
0x14000bf6d  add     rsp, 50h
0x14000bf71  pop     rdi
0x14000bf72  retn
```
