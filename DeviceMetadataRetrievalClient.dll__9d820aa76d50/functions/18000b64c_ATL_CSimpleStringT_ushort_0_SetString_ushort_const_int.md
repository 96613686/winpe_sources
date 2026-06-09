# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x18000b64c`
- end: `0x18000b753`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `263`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180005018`
- `0x1800061c8`
- `0x180008544`
- `0x18000913c`

## callees

- `0x180005170`
- `0x18000823c`
- `0x18000b64c`
- `0x180014010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b725`
- `msvcrt!memcpy_s` at `0x18000b725`
- `msvcrt!memmove_s` at `0x18000b71a`
- `msvcrt!memmove_s` at `0x18000b71a`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(__int64 *a1, const void *a2, unsigned int a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  _QWORD *v7; // rdx
  __int64 v8; // rdi
  unsigned __int64 v9; // rbp
  unsigned __int64 v10; // r15
  char *v11; // rcx
  rsize_t v12; // r9
  rsize_t v13; // rdx

  v3 = (int)a3;
  if ( a3 )
  {
    if ( a2 )
    {
      v9 = ((__int64)a2 - *a1) >> 1;
      v10 = *(unsigned int *)(*a1 - 16);
      if ( (((*(_DWORD *)(*a1 - 12) - a3) | (1 - *(_DWORD *)(*a1 - 8))) & 0x80000000) != 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
      v11 = (char *)*a1;
      v12 = 2 * v3;
      v13 = 2 * v3;
      if ( v9 > v10 )
        memcpy_s(v11, v13, a2, v12);
      else
        memmove_s(v11, v13, &v11[2 * v9], v12);
      if ( (int)v3 >= 0 && (int)v3 <= *(_DWORD *)(*a1 - 12) )
      {
        *(_DWORD *)(*a1 - 16) = v3;
        result = 0;
        *(_WORD *)(2 * v3 + *a1) = 0;
        return result;
      }
    }
    goto LABEL_19;
  }
  result = *a1;
  v7 = (_QWORD *)(*a1 - 24);
  if ( !*((_DWORD *)v7 + 2) )
    return result;
  if ( *((int *)v7 + 4) < 0 )
  {
    if ( *(int *)(result - 12) >= 0 )
    {
      *(_DWORD *)(result - 16) = 0;
      result = 0;
      *(_WORD *)*a1 = 0;
      return result;
    }
LABEL_19:
    ATL::AtlThrowImpl(-2147024809);
  }
  v8 = *v7;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 8LL))(*v7);
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8) + 24;
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x18000b64c  push    rbx
0x18000b64e  push    rbp
0x18000b64f  push    rsi
0x18000b650  push    rdi
0x18000b651  push    r14
0x18000b653  push    r15
0x18000b655  sub     rsp, 28h
0x18000b659  movsxd  rdi, r8d
0x18000b65c  mov     r14, rdx
0x18000b65f  mov     rbx, rcx
0x18000b662  test    r8d, r8d
0x18000b665  jnz     short loc_18000B6D4
0x18000b667  mov     rax, [rcx]
0x18000b66a  lea     rdx, [rax-18h]
0x18000b66e  cmp     [rdx+8], r8d
0x18000b672  jz      short loc_18000B690
0x18000b674  cmp     [rdx+10h], r8d
0x18000b678  jge     short loc_18000B69D
0x18000b67a  cmp     [rax-0Ch], r8d
0x18000b67e  jl      loc_18000B748
0x18000b684  mov     [rax-10h], r8d
0x18000b688  xor     eax, eax
0x18000b68a  mov     rcx, [rcx]
0x18000b68d  mov     [rcx], ax
0x18000b690  add     rsp, 28h
0x18000b694  pop     r15
0x18000b696  pop     r14
0x18000b698  pop     rdi
0x18000b699  pop     rsi
0x18000b69a  pop     rbp
0x18000b69b  pop     rbx
0x18000b69c  retn
0x18000b69d  mov     rdi, [rdx]
0x18000b6a0  or      eax, 0FFFFFFFFh
0x18000b6a3  lock xadd [rdx+10h], eax
0x18000b6a8  sub     eax, 1
0x18000b6ab  jg      short loc_18000B6BC
0x18000b6ad  mov     rcx, [rdx]
0x18000b6b0  mov     rax, [rcx]
0x18000b6b3  mov     rax, [rax+8]
0x18000b6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6bc  mov     rax, [rdi]
0x18000b6bf  mov     rcx, rdi
0x18000b6c2  mov     rax, [rax+18h]
0x18000b6c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6cb  add     rax, 18h
0x18000b6cf  mov     [rbx], rax
0x18000b6d2  jmp     short loc_18000B690
0x18000b6d4  test    r14, r14
0x18000b6d7  jz      short loc_18000B748
0x18000b6d9  mov     rax, [rcx]
0x18000b6dc  mov     rbp, r14
0x18000b6df  sub     rbp, rax
0x18000b6e2  mov     ecx, 1
0x18000b6e7  sar     rbp, 1
0x18000b6ea  sub     ecx, [rax-8]
0x18000b6ed  mov     r15d, [rax-10h]
0x18000b6f1  mov     eax, [rax-0Ch]
0x18000b6f4  sub     eax, edi
0x18000b6f6  or      ecx, eax
0x18000b6f8  jge     short loc_18000B704
0x18000b6fa  mov     edx, edi
0x18000b6fc  mov     rcx, rbx
0x18000b6ff  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000b704  mov     rcx, [rbx]; Destination
0x18000b707  lea     rsi, [rdi+rdi]
0x18000b70b  mov     r9, rsi; SourceSize
0x18000b70e  mov     rdx, rsi; DestinationSize
0x18000b711  cmp     rbp, r15
0x18000b714  ja      short loc_18000B722
0x18000b716  lea     r8, [rcx+rbp*2]; Source
0x18000b71a  call    cs:__imp_memmove_s
0x18000b720  jmp     short loc_18000B72B
0x18000b722  mov     r8, r14; Source
0x18000b725  call    cs:__imp_memcpy_s
0x18000b72b  test    edi, edi
0x18000b72d  js      short loc_18000B748
0x18000b72f  mov     rax, [rbx]
0x18000b732  cmp     edi, [rax-0Ch]
0x18000b735  jg      short loc_18000B748
0x18000b737  mov     [rax-10h], edi
0x18000b73a  xor     eax, eax
0x18000b73c  mov     rcx, [rbx]
0x18000b73f  mov     [rsi+rcx], ax
0x18000b743  jmp     loc_18000B690
0x18000b748  mov     ecx, 80070057h; int
0x18000b74d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
