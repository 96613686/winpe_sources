# CSpDynamicString::operator=(ushort const *)

- ea: `0x180006e28`
- end: `0x180006ea1`
- name: `??4CSpDynamicString@@QEAAPEAGPEBG@Z`
- size: `121`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007b50`
- `0x18000d300`
- `0x18000d9e0`
- `0x18000e620`
- `0x180010420`
- `0x180012308`
- `0x180012e08`
- `0x180018888`
- `0x180018ac4`
- `0x180018b8c`

## callees

- `0x180006e28`
- `0x180019722`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006e3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006e3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006e6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006e6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006e7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006e7f`

## pseudocode

```c
LPVOID __fastcall CSpDynamicString::operator=(LPVOID *a1, _WORD *a2)
{
  __int64 v4; // rax
  SIZE_T v5; // rsi
  void *v6; // rax

  if ( a2 != *a1 )
  {
    CoTaskMemFree(*a1);
    *a1 = 0;
    if ( a2 )
    {
      v4 = -1;
      do
        ++v4;
      while ( a2[v4] );
      v5 = 2 * v4 + 2;
      if ( v5 == 2 * (_DWORD)v4 + 2 )
      {
        v6 = CoTaskMemAlloc(v5);
        *a1 = v6;
        if ( v6 )
          memcpy_0(v6, a2, v5);
        else
          SetLastError(0xEu);
      }
    }
  }
  return *a1;
}

```

## disassembly

```asm
0x180006e28  push    rbx
0x180006e2a  push    rbp
0x180006e2b  push    rsi
0x180006e2c  push    rdi
0x180006e2d  sub     rsp, 28h
0x180006e31  mov     rdi, rdx
0x180006e34  mov     rbx, rcx
0x180006e37  cmp     rdx, [rcx]
0x180006e3a  jz      short loc_180006E95
0x180006e3c  mov     rcx, [rcx]; pv
0x180006e3f  call    cs:__imp_CoTaskMemFree
0x180006e45  xor     ebp, ebp
0x180006e47  mov     [rbx], rbp
0x180006e4a  test    rdi, rdi
0x180006e4d  jz      short loc_180006E95
0x180006e4f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006e53  inc     rax
0x180006e56  cmp     [rdi+rax*2], bp
0x180006e5a  jnz     short loc_180006E53
0x180006e5c  lea     rsi, ds:2[rax*2]
0x180006e64  mov     eax, esi
0x180006e66  cmp     rsi, rax
0x180006e69  jnz     short loc_180006E95
0x180006e6b  mov     rcx, rsi; cb
0x180006e6e  call    cs:__imp_CoTaskMemAlloc
0x180006e74  mov     [rbx], rax
0x180006e77  test    rax, rax
0x180006e7a  jnz     short loc_180006E87
0x180006e7c  lea     ecx, [rax+0Eh]; dwErrCode
0x180006e7f  call    cs:__imp_SetLastError
0x180006e85  jmp     short loc_180006E95
0x180006e87  mov     r8, rsi; Size
0x180006e8a  mov     rdx, rdi; Src
0x180006e8d  mov     rcx, rax; void *
0x180006e90  call    memcpy_0
0x180006e95  mov     rax, [rbx]
0x180006e98  add     rsp, 28h
0x180006e9c  pop     rdi
0x180006e9d  pop     rsi
0x180006e9e  pop     rbp
0x180006e9f  pop     rbx
0x180006ea0  retn
```
