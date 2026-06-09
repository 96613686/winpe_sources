# _CxxThrowException

- ea: `0x180008e5c`
- end: `0x180008f03`
- name: `_CxxThrowException`
- size: `167`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800012f0`
- `0x180001b40`
- `0x180001d30`
- `0x180003850`
- `0x180003860`
- `0x180005d90`
- `0x180005e50`
- `0x180007be8`
- `0x180007c08`
- `0x1800095ac`

## callees

- `0x180008e5c`
- `0x18000b930`

## import_xrefs

- `KERNEL32!RtlPcToFileHeader` at `0x180008eac`
- `KERNEL32!RtlPcToFileHeader` at `0x180008eac`
- `KERNEL32!RaiseException` at `0x180008eed`
- `KERNEL32!RaiseException` at `0x180008eed`

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
0x180008e5c  mov     [rsp+arg_10], rbx
0x180008e61  mov     [rsp+arg_18], rsi
0x180008e66  push    rdi
0x180008e67  sub     rsp, 50h
0x180008e6b  mov     rbx, rdx
0x180008e6e  mov     rsi, rcx
0x180008e71  mov     edi, 19930520h
0x180008e76  test    rdx, rdx
0x180008e79  jz      short loc_180008E98
0x180008e7b  test    byte ptr [rdx], 10h
0x180008e7e  jz      short loc_180008E98
0x180008e80  mov     rcx, [rcx]
0x180008e83  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180008e87  mov     rax, [rcx]
0x180008e8a  mov     rbx, [rax+30h]
0x180008e8e  mov     rax, [rax+40h]
0x180008e92  call    cs:__guard_dispatch_icall_fptr
0x180008e98  xor     eax, eax
0x180008e9a  mov     [rsp+58h+BaseOfImage], rax
0x180008e9f  test    rbx, rbx
0x180008ea2  jz      short loc_180008EC6
0x180008ea4  lea     rdx, [rsp+58h+BaseOfImage]; BaseOfImage
0x180008ea9  mov     rcx, rbx; PcValue
0x180008eac  call    cs:__imp_RtlPcToFileHeader
0x180008eb2  mov     [rsp+58h+BaseOfImage], rax
0x180008eb7  test    byte ptr [rbx], 8
0x180008eba  jnz     short loc_180008EC1
0x180008ebc  test    rax, rax
0x180008ebf  jnz     short loc_180008EC6
0x180008ec1  mov     edi, 1994000h
0x180008ec6  mov     edx, 1; dwExceptionFlags
0x180008ecb  mov     [rsp+58h+Arguments], rdi
0x180008ed0  lea     r9, [rsp+58h+Arguments]; lpArguments
0x180008ed5  mov     [rsp+58h+var_28], rsi
0x180008eda  mov     ecx, 0E06D7363h; dwExceptionCode
0x180008edf  mov     [rsp+58h+var_20], rbx
0x180008ee4  mov     [rsp+58h+var_18], rax
0x180008ee9  lea     r8d, [rdx+3]; nNumberOfArguments
0x180008eed  call    cs:__imp_RaiseException
0x180008ef3  mov     rbx, [rsp+58h+arg_10]
0x180008ef8  mov     rsi, [rsp+58h+arg_18]
0x180008efd  add     rsp, 50h
0x180008f01  pop     rdi
0x180008f02  retn
```
