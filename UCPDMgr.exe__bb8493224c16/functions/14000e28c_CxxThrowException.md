# _CxxThrowException

- ea: `0x14000e28c`
- end: `0x14000e332`
- name: `_CxxThrowException`
- size: `166`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002580`
- `0x1400025a0`
- `0x14000c4a4`

## callees

- `0x14000e28c`
- `0x14000f4d0`

## import_xrefs

- `KERNEL32!RtlPcToFileHeader` at `0x14000e2db`
- `KERNEL32!RtlPcToFileHeader` at `0x14000e2db`
- `KERNEL32!RaiseException` at `0x14000e31c`
- `KERNEL32!RaiseException` at `0x14000e31c`

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
0x14000e28c  mov     [rsp+arg_10], rbx
0x14000e291  mov     [rsp+arg_18], rsi
0x14000e296  push    rdi
0x14000e297  sub     rsp, 50h
0x14000e29b  mov     rbx, rdx
0x14000e29e  mov     rsi, rcx
0x14000e2a1  mov     edi, 19930520h
0x14000e2a6  test    rdx, rdx
0x14000e2a9  jz      short loc_14000E2C7
0x14000e2ab  test    byte ptr [rdx], 10h
0x14000e2ae  jz      short loc_14000E2C7
0x14000e2b0  mov     rcx, [rcx]
0x14000e2b3  add     rcx, 0FFFFFFFFFFFFFFF8h
0x14000e2b7  mov     rax, [rcx]
0x14000e2ba  mov     rbx, [rax+30h]
0x14000e2be  mov     rax, [rax+40h]
0x14000e2c2  call    _guard_dispatch_icall
0x14000e2c7  xor     eax, eax
0x14000e2c9  mov     [rsp+58h+BaseOfImage], rax
0x14000e2ce  test    rbx, rbx
0x14000e2d1  jz      short loc_14000E2F5
0x14000e2d3  lea     rdx, [rsp+58h+BaseOfImage]; BaseOfImage
0x14000e2d8  mov     rcx, rbx; PcValue
0x14000e2db  call    cs:__imp_RtlPcToFileHeader
0x14000e2e1  mov     [rsp+58h+BaseOfImage], rax
0x14000e2e6  test    byte ptr [rbx], 8
0x14000e2e9  jnz     short loc_14000E2F0
0x14000e2eb  test    rax, rax
0x14000e2ee  jnz     short loc_14000E2F5
0x14000e2f0  mov     edi, 1994000h
0x14000e2f5  mov     edx, 1; dwExceptionFlags
0x14000e2fa  mov     [rsp+58h+Arguments], rdi
0x14000e2ff  lea     r9, [rsp+58h+Arguments]; lpArguments
0x14000e304  mov     [rsp+58h+var_28], rsi
0x14000e309  mov     ecx, 0E06D7363h; dwExceptionCode
0x14000e30e  mov     [rsp+58h+var_20], rbx
0x14000e313  mov     [rsp+58h+var_18], rax
0x14000e318  lea     r8d, [rdx+3]; nNumberOfArguments
0x14000e31c  call    cs:__imp_RaiseException
0x14000e322  mov     rbx, [rsp+58h+arg_10]
0x14000e327  mov     rsi, [rsp+58h+arg_18]
0x14000e32c  add     rsp, 50h
0x14000e330  pop     rdi
0x14000e331  retn
```
