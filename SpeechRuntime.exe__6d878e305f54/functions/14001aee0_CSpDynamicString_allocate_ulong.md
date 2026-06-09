# CSpDynamicString::_allocate(ulong)

- ea: `0x14001aee0`
- end: `0x14001af4a`
- name: `?_allocate@CSpDynamicString@@AEAAJK@Z`
- size: `106`
- prototype: `__int64 __fastcall(CSpDynamicString *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140019e28`
- `0x14001f188`

## callees

- `0x14001aee0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001af02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001af02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001af22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001af34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001af22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001af34`

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
0x14001aee0  mov     [rsp+arg_0], rbx
0x14001aee5  push    rdi
0x14001aee6  sub     rsp, 20h
0x14001aeea  mov     rdi, rcx
0x14001aeed  cmp     edx, 4FFFFFFFh
0x14001aef3  jnb     short loc_14001AF2F
0x14001aef5  lea     ecx, [rdx+1]
0x14001aef8  mov     ebx, edx
0x14001aefa  add     rcx, rcx; cb
0x14001aefd  cmp     rcx, rbx
0x14001af00  jbe     short loc_14001AF2F
0x14001af02  call    cs:__imp_CoTaskMemAlloc
0x14001af08  mov     [rdi], rax
0x14001af0b  mov     rdx, rax
0x14001af0e  test    rax, rax
0x14001af11  jz      short loc_14001AF1D
0x14001af13  xor     eax, eax
0x14001af15  xor     ecx, ecx
0x14001af17  mov     [rdx+rbx*2], cx
0x14001af1b  jmp     short loc_14001AF3F
0x14001af1d  mov     ecx, 0Eh; dwErrCode
0x14001af22  call    cs:__imp_SetLastError
0x14001af28  mov     eax, 8007000Eh
0x14001af2d  jmp     short loc_14001AF3F
0x14001af2f  mov     ecx, 216h; dwErrCode
0x14001af34  call    cs:__imp_SetLastError
0x14001af3a  mov     eax, 80070216h
0x14001af3f  mov     rbx, [rsp+28h+arg_0]
0x14001af44  add     rsp, 20h
0x14001af48  pop     rdi
0x14001af49  retn
```
