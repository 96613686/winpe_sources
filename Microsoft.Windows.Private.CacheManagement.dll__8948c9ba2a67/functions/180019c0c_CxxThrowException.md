# _CxxThrowException

- ea: `0x180019c0c`
- end: `0x180019cb3`
- name: `_CxxThrowException`
- size: `167`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `24`
- callee_count: `2`
- tags: ``

## callers

- `0x1800025b0`
- `0x180003a20`
- `0x180003ee0`
- `0x180007c40`
- `0x180008b70`
- `0x180008c70`
- `0x180009df0`
- `0x18000f1e0`
- `0x180013be0`
- `0x180013c30`
- `0x180013c40`
- `0x180013d80`
- `0x180014360`
- `0x1800163f4`
- `0x180016414`
- `0x18001700c`
- `0x180017d9c`
- `0x180018eb8`
- `0x18001a5ec`
- `0x18001c7a0`
- `0x18001ca20`
- `0x18001f896`
- `0x18001f91a`
- `0x18001fa07`

## callees

- `0x180019c0c`
- `0x18001cdf0`

## import_xrefs

- `KERNEL32!RtlPcToFileHeader` at `0x180019c5c`
- `KERNEL32!RtlPcToFileHeader` at `0x180019c5c`
- `KERNEL32!RaiseException` at `0x180019c9d`
- `KERNEL32!RaiseException` at `0x180019c9d`

## pseudocode

```c
void __stdcall __noreturn CxxThrowException(void *pExceptionObject, _ThrowInfo *pThrowInfo)
{
  _ThrowInfo *v2; // rbx
  ULONG_PTR v4; // rdi
  __int64 v5; // rcx
  PVOID v6; // rax
  PVOID BaseOfImage; // [rsp+20h] [rbp-38h] BYREF
  ULONG_PTR Arguments[6]; // [rsp+28h] [rbp-30h] BYREF

  v2 = pThrowInfo;
  v4 = 429065504;
  if ( pThrowInfo && (pThrowInfo->attributes & 0x10) != 0 )
  {
    v5 = *(_QWORD *)pExceptionObject - 8LL;
    v2 = *(_ThrowInfo **)(*(_QWORD *)v5 + 48LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 64LL))(v5);
  }
  v6 = 0;
  BaseOfImage = 0;
  if ( v2 )
  {
    v6 = RtlPcToFileHeader(v2, &BaseOfImage);
    BaseOfImage = v6;
    if ( (v2->attributes & 8) != 0 || !v6 )
      v4 = 26820608;
  }
  Arguments[0] = v4;
  Arguments[1] = (ULONG_PTR)pExceptionObject;
  Arguments[2] = (ULONG_PTR)v2;
  Arguments[3] = (ULONG_PTR)v6;
  RaiseException(0xE06D7363, 1u, 4u, Arguments);
}

```

## disassembly

```asm
0x180019c0c  mov     [rsp+arg_10], rbx
0x180019c11  mov     [rsp+arg_18], rsi
0x180019c16  push    rdi
0x180019c17  sub     rsp, 50h
0x180019c1b  mov     rbx, rdx
0x180019c1e  mov     rsi, rcx
0x180019c21  mov     edi, 19930520h
0x180019c26  test    rdx, rdx
0x180019c29  jz      short loc_180019C48
0x180019c2b  test    byte ptr [rdx], 10h
0x180019c2e  jz      short loc_180019C48
0x180019c30  mov     rcx, [rcx]
0x180019c33  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180019c37  mov     rax, [rcx]
0x180019c3a  mov     rbx, [rax+30h]
0x180019c3e  mov     rax, [rax+40h]
0x180019c42  call    cs:__guard_dispatch_icall_fptr
0x180019c48  xor     eax, eax
0x180019c4a  mov     [rsp+58h+BaseOfImage], rax
0x180019c4f  test    rbx, rbx
0x180019c52  jz      short loc_180019C76
0x180019c54  lea     rdx, [rsp+58h+BaseOfImage]; BaseOfImage
0x180019c59  mov     rcx, rbx; PcValue
0x180019c5c  call    cs:__imp_RtlPcToFileHeader
0x180019c62  mov     [rsp+58h+BaseOfImage], rax
0x180019c67  test    byte ptr [rbx], 8
0x180019c6a  jnz     short loc_180019C71
0x180019c6c  test    rax, rax
0x180019c6f  jnz     short loc_180019C76
0x180019c71  mov     edi, 1994000h
0x180019c76  mov     edx, 1; dwExceptionFlags
0x180019c7b  mov     [rsp+58h+Arguments], rdi
0x180019c80  lea     r9, [rsp+58h+Arguments]; lpArguments
0x180019c85  mov     [rsp+58h+var_28], rsi
0x180019c8a  mov     ecx, 0E06D7363h; dwExceptionCode
0x180019c8f  mov     [rsp+58h+var_20], rbx
0x180019c94  mov     [rsp+58h+var_18], rax
0x180019c99  lea     r8d, [rdx+3]; nNumberOfArguments
0x180019c9d  call    cs:__imp_RaiseException
0x180019ca3  mov     rbx, [rsp+58h+arg_10]
0x180019ca8  mov     rsi, [rsp+58h+arg_18]
0x180019cad  add     rsp, 50h
0x180019cb1  pop     rdi
0x180019cb2  retn
```
