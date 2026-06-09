# CSpDynamicString::_allocate(ulong)

- ea: `0x18000d630`
- end: `0x18000d6ad`
- name: `?_allocate@CSpDynamicString@@AEAAJK@Z`
- size: `125`
- prototype: `__int64 __fastcall(CSpDynamicString *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007b44`
- `0x1800082d0`
- `0x18000e2c8`
- `0x18000f270`

## callees

- `0x18000d630`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000d678`
- `KERNEL32!SetLastError` at `0x18000d690`
- `KERNEL32!SetLastError` at `0x18000d678`
- `KERNEL32!SetLastError` at `0x18000d690`
- `ole32!CoTaskMemAlloc` at `0x18000d652`
- `ole32!CoTaskMemAlloc` at `0x18000d652`

## pseudocode

```c
__int64 __fastcall CSpDynamicString::_allocate(CSpDynamicString *this, unsigned int a2)
{
  __int64 v3; // rbx
  SIZE_T v4; // rcx
  _WORD *v5; // rax
  _WORD *v6; // rdx
  __int64 result; // rax

  if ( a2 >= 0x4FFFFFFF || (v3 = a2, v4 = 2LL * (a2 + 1), v4 <= a2) )
  {
    SetLastError(0x216u);
    return 2147942934LL;
  }
  else
  {
    v5 = CoTaskMemAlloc(v4);
    *(_QWORD *)this = v5;
    v6 = v5;
    if ( v5 )
    {
      result = 0;
      v6[v3] = 0;
    }
    else
    {
      SetLastError(0xEu);
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d630  mov     [rsp+arg_0], rbx
0x18000d635  push    rdi
0x18000d636  sub     rsp, 20h
0x18000d63a  mov     rdi, rcx
0x18000d63d  cmp     edx, 4FFFFFFFh
0x18000d643  jnb     short loc_18000D68B
0x18000d645  lea     ecx, [rdx+1]
0x18000d648  mov     ebx, edx
0x18000d64a  add     rcx, rcx; cb
0x18000d64d  cmp     rcx, rbx
0x18000d650  jbe     short loc_18000D68B
0x18000d652  call    cs:__imp_CoTaskMemAlloc
0x18000d659  nop     dword ptr [rax+rax+00h]
0x18000d65e  mov     [rdi], rax
0x18000d661  mov     rdx, rax
0x18000d664  test    rax, rax
0x18000d667  jz      short loc_18000D673
0x18000d669  xor     eax, eax
0x18000d66b  xor     ecx, ecx
0x18000d66d  mov     [rdx+rbx*2], cx
0x18000d671  jmp     short loc_18000D6A1
0x18000d673  mov     ecx, 0Eh; dwErrCode
0x18000d678  call    cs:__imp_SetLastError
0x18000d67f  nop     dword ptr [rax+rax+00h]
0x18000d684  mov     eax, 8007000Eh
0x18000d689  jmp     short loc_18000D6A1
0x18000d68b  mov     ecx, 216h; dwErrCode
0x18000d690  call    cs:__imp_SetLastError
0x18000d697  nop     dword ptr [rax+rax+00h]
0x18000d69c  mov     eax, 80070216h
0x18000d6a1  mov     rbx, [rsp+28h+arg_0]
0x18000d6a6  add     rsp, 20h
0x18000d6aa  pop     rdi
0x18000d6ab  retn
```
