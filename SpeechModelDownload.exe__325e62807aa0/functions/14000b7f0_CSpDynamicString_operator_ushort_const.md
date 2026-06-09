# CSpDynamicString::operator=(ushort const *)

- ea: `0x14000b7f0`
- end: `0x14000b87a`
- name: `??4CSpDynamicString@@QEAAPEAGPEBG@Z`
- size: `138`
- prototype: `__int64 __fastcall(CSpDynamicString *, _WORD *)`
- caller_count: `9`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140001fc0`
- `0x140001ff0`
- `0x140002020`
- `0x140002050`
- `0x140002080`
- `0x1400020b0`
- `0x1400020e0`
- `0x14000f920`
- `0x140013aec`

## callees

- `0x14000b7f0`
- `0x1400131e4`
- `0x14001bb9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b866`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b866`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000b836`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000b836`

## pseudocode

```c
__int64 __fastcall CSpDynamicString::operator=(CSpDynamicString *a1, _WORD *a2)
{
  __int64 v4; // rbx
  SIZE_T v5; // rcx
  _WORD *v6; // rax
  DWORD v7; // ecx

  if ( a2 != *(_WORD **)a1 )
  {
    CSpDynamicString::_free(a1);
    if ( a2 )
    {
      v4 = -1;
      do
        ++v4;
      while ( a2[v4] );
      if ( (unsigned int)v4 >= 0x4FFFFFFF || (v5 = 2LL * (unsigned int)(v4 + 1), v5 <= (unsigned int)v4) )
      {
        v7 = 534;
      }
      else
      {
        v6 = CoTaskMemAlloc(v5);
        *(_QWORD *)a1 = v6;
        if ( v6 )
        {
          v6[(unsigned int)v4] = 0;
          memcpy_0(*(void **)a1, a2, 2 * v4);
          return *(_QWORD *)a1;
        }
        v7 = 14;
      }
      SetLastError(v7);
    }
  }
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x14000b7f0  push    rbx
0x14000b7f2  push    rbp
0x14000b7f3  push    rsi
0x14000b7f4  push    rdi
0x14000b7f5  push    r14
0x14000b7f7  sub     rsp, 20h
0x14000b7fb  mov     rsi, rdx
0x14000b7fe  mov     rdi, rcx
0x14000b801  cmp     rdx, [rcx]
0x14000b804  jz      short loc_14000B86C
0x14000b806  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x14000b80b  xor     r14d, r14d
0x14000b80e  test    rsi, rsi
0x14000b811  jz      short loc_14000B86C
0x14000b813  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000b817  inc     rbx
0x14000b81a  cmp     [rsi+rbx*2], r14w
0x14000b81f  jnz     short loc_14000B817
0x14000b821  cmp     ebx, 4FFFFFFFh
0x14000b827  jnb     short loc_14000B861
0x14000b829  lea     ecx, [rbx+1]
0x14000b82c  mov     ebp, ebx
0x14000b82e  add     rcx, rcx; cb
0x14000b831  cmp     rcx, rbp
0x14000b834  jbe     short loc_14000B861
0x14000b836  call    cs:__imp_CoTaskMemAlloc
0x14000b83c  mov     [rdi], rax
0x14000b83f  test    rax, rax
0x14000b842  jz      short loc_14000B85A
0x14000b844  mov     [rax+rbp*2], r14w
0x14000b849  lea     r8, [rbx+rbx]; Size
0x14000b84d  mov     rcx, [rdi]; void *
0x14000b850  mov     rdx, rsi; Src
0x14000b853  call    memcpy_0
0x14000b858  jmp     short loc_14000B86C
0x14000b85a  mov     ecx, 0Eh
0x14000b85f  jmp     short loc_14000B866
0x14000b861  mov     ecx, 216h; dwErrCode
0x14000b866  call    cs:__imp_SetLastError
0x14000b86c  mov     rax, [rdi]
0x14000b86f  add     rsp, 20h
0x14000b873  pop     r14
0x14000b875  pop     rdi
0x14000b876  pop     rsi
0x14000b877  pop     rbp
0x14000b878  pop     rbx
0x14000b879  retn
```
