# _CxxThrowException

- ea: `0x180009408`
- end: `0x1800094af`
- name: `_CxxThrowException`
- size: `167`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002238`
- `0x180008494`
- `0x1800084b4`
- `0x180009af4`

## callees

- `0x180009408`
- `0x1800241c0`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180009499`
- `KERNEL32!RaiseException` at `0x180009499`
- `KERNEL32!RtlPcToFileHeader` at `0x180009458`
- `KERNEL32!RtlPcToFileHeader` at `0x180009458`

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
0x180009408  mov     [rsp+arg_10], rbx
0x18000940d  mov     [rsp+arg_18], rsi
0x180009412  push    rdi
0x180009413  sub     rsp, 50h
0x180009417  mov     rbx, rdx
0x18000941a  mov     rsi, rcx
0x18000941d  mov     edi, 19930520h
0x180009422  test    rdx, rdx
0x180009425  jz      short loc_180009444
0x180009427  test    byte ptr [rdx], 10h
0x18000942a  jz      short loc_180009444
0x18000942c  mov     rcx, [rcx]
0x18000942f  sub     rcx, 8
0x180009433  mov     rax, [rcx]
0x180009436  mov     rbx, [rax+30h]
0x18000943a  mov     rax, [rax+40h]
0x18000943e  call    cs:__guard_dispatch_icall_fptr
0x180009444  xor     eax, eax
0x180009446  mov     [rsp+58h+BaseOfImage], rax
0x18000944b  test    rbx, rbx
0x18000944e  jz      short loc_180009472
0x180009450  lea     rdx, [rsp+58h+BaseOfImage]; BaseOfImage
0x180009455  mov     rcx, rbx; PcValue
0x180009458  call    cs:__imp_RtlPcToFileHeader
0x18000945e  mov     [rsp+58h+BaseOfImage], rax
0x180009463  test    byte ptr [rbx], 8
0x180009466  jnz     short loc_18000946D
0x180009468  test    rax, rax
0x18000946b  jnz     short loc_180009472
0x18000946d  mov     edi, 1994000h
0x180009472  mov     edx, 1; dwExceptionFlags
0x180009477  mov     [rsp+58h+Arguments], rdi
0x18000947c  lea     r9, [rsp+58h+Arguments]; lpArguments
0x180009481  mov     [rsp+58h+var_28], rsi
0x180009486  mov     ecx, 0E06D7363h; dwExceptionCode
0x18000948b  mov     [rsp+58h+var_20], rbx
0x180009490  mov     [rsp+58h+var_18], rax
0x180009495  lea     r8d, [rdx+3]; nNumberOfArguments
0x180009499  call    cs:__imp_RaiseException
0x18000949f  mov     rbx, [rsp+58h+arg_10]
0x1800094a4  mov     rsi, [rsp+58h+arg_18]
0x1800094a9  add     rsp, 50h
0x1800094ad  pop     rdi
0x1800094ae  retn
```
