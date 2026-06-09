# _CxxThrowException

- ea: `0x180010f24`
- end: `0x180010fca`
- name: `_CxxThrowException`
- size: `166`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x1800018d8`
- `0x180001c5c`
- `0x180002788`
- `0x1800028b4`
- `0x1800079e8`
- `0x1800088d8`
- `0x180008920`
- `0x180008940`
- `0x180008a80`
- `0x18000dc5c`
- `0x18000dcc8`
- `0x18000f710`
- `0x180011b5c`
- `0x18001205c`

## callees

- `0x180010f24`
- `0x180015430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010fb4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010fb4`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlPcToFileHeader` at `0x180010f73`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlPcToFileHeader` at `0x180010f73`

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
0x180010f24  mov     [rsp+arg_10], rbx
0x180010f29  mov     [rsp+arg_18], rsi
0x180010f2e  push    rdi
0x180010f2f  sub     rsp, 50h
0x180010f33  mov     rbx, rdx
0x180010f36  mov     rsi, rcx
0x180010f39  mov     edi, 19930520h
0x180010f3e  test    rdx, rdx
0x180010f41  jz      short loc_180010F5F
0x180010f43  test    byte ptr [rdx], 10h
0x180010f46  jz      short loc_180010F5F
0x180010f48  mov     rcx, [rcx]
0x180010f4b  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180010f4f  mov     rax, [rcx]
0x180010f52  mov     rbx, [rax+30h]
0x180010f56  mov     rax, [rax+40h]
0x180010f5a  call    _guard_dispatch_icall
0x180010f5f  xor     eax, eax
0x180010f61  mov     [rsp+58h+BaseOfImage], rax
0x180010f66  test    rbx, rbx
0x180010f69  jz      short loc_180010F8D
0x180010f6b  lea     rdx, [rsp+58h+BaseOfImage]; BaseOfImage
0x180010f70  mov     rcx, rbx; PcValue
0x180010f73  call    cs:__imp_RtlPcToFileHeader
0x180010f79  mov     [rsp+58h+BaseOfImage], rax
0x180010f7e  test    byte ptr [rbx], 8
0x180010f81  jnz     short loc_180010F88
0x180010f83  test    rax, rax
0x180010f86  jnz     short loc_180010F8D
0x180010f88  mov     edi, 1994000h
0x180010f8d  mov     edx, 1; dwExceptionFlags
0x180010f92  mov     [rsp+58h+Arguments], rdi
0x180010f97  lea     r9, [rsp+58h+Arguments]; lpArguments
0x180010f9c  mov     [rsp+58h+var_28], rsi
0x180010fa1  mov     ecx, 0E06D7363h; dwExceptionCode
0x180010fa6  mov     [rsp+58h+var_20], rbx
0x180010fab  mov     [rsp+58h+var_18], rax
0x180010fb0  lea     r8d, [rdx+3]; nNumberOfArguments
0x180010fb4  call    cs:__imp_RaiseException
0x180010fba  mov     rbx, [rsp+58h+arg_10]
0x180010fbf  mov     rsi, [rsp+58h+arg_18]
0x180010fc4  add     rsp, 50h
0x180010fc8  pop     rdi
0x180010fc9  retn
```
