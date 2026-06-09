# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x14000cb50`
- end: `0x14000cc5e`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64 *, const void *, int)`
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x14000c19c`
- `0x14000c68c`
- `0x14000c8b4`
- `0x14000ce48`
- `0x14000d334`
- `0x14000d3a0`
- `0x14000ddb0`
- `0x14000ee8c`
- `0x140010c6c`
- `0x140011204`
- `0x1400116c4`
- `0x140011a40`

## callees

- `0x140004890`
- `0x140007560`
- `0x14000cb50`
- `0x140017010`

## import_xrefs

- `msvcrt!memmove_s` at `0x14000cc1e`
- `msvcrt!memmove_s` at `0x14000cc1e`
- `msvcrt!memcpy_s` at `0x14000cc30`
- `msvcrt!memcpy_s` at `0x14000cc30`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(__int64 *a1, const void *a2, int a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  _QWORD *v7; // rdx
  __int64 v8; // rdi
  unsigned __int64 v9; // r15
  unsigned __int64 v10; // rbp
  char *v11; // rcx

  v3 = a3;
  if ( a3 )
  {
    if ( a2 )
    {
      v9 = *(unsigned int *)(*a1 - 16);
      v10 = ((__int64)a2 - *a1) >> 1;
      if ( ((*(_DWORD *)(*a1 - 12) - a3) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
      v11 = (char *)*a1;
      if ( v10 > v9 )
        memcpy_s(v11, 2 * v3, a2, 2 * v3);
      else
        memmove_s(v11, 2 * v3, &v11[2 * v10], 2 * v3);
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
0x14000cb50  push    rbx
0x14000cb52  push    rbp
0x14000cb53  push    rsi
0x14000cb54  push    rdi
0x14000cb55  push    r14
0x14000cb57  push    r15
0x14000cb59  sub     rsp, 28h
0x14000cb5d  movsxd  rdi, r8d
0x14000cb60  mov     r14, rdx
0x14000cb63  mov     rbx, rcx
0x14000cb66  test    r8d, r8d
0x14000cb69  jnz     short loc_14000CBD8
0x14000cb6b  mov     rax, [rcx]
0x14000cb6e  lea     rdx, [rax-18h]
0x14000cb72  cmp     [rdx+8], r8d
0x14000cb76  jz      short loc_14000CB94
0x14000cb78  cmp     [rdx+10h], r8d
0x14000cb7c  jge     short loc_14000CBA1
0x14000cb7e  cmp     [rax-0Ch], r8d
0x14000cb82  jl      loc_14000CC53
0x14000cb88  mov     [rax-10h], r8d
0x14000cb8c  mov     rcx, [rcx]
0x14000cb8f  xor     eax, eax
0x14000cb91  mov     [rcx], ax
0x14000cb94  add     rsp, 28h
0x14000cb98  pop     r15
0x14000cb9a  pop     r14
0x14000cb9c  pop     rdi
0x14000cb9d  pop     rsi
0x14000cb9e  pop     rbp
0x14000cb9f  pop     rbx
0x14000cba0  retn
0x14000cba1  mov     rdi, [rdx]
0x14000cba4  or      eax, 0FFFFFFFFh
0x14000cba7  lock xadd [rdx+10h], eax
0x14000cbac  sub     eax, 1
0x14000cbaf  jg      short loc_14000CBC0
0x14000cbb1  mov     rcx, [rdx]
0x14000cbb4  mov     rax, [rcx]
0x14000cbb7  mov     rax, [rax+8]
0x14000cbbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cbc0  mov     rax, [rdi]
0x14000cbc3  mov     rcx, rdi
0x14000cbc6  mov     rax, [rax+18h]
0x14000cbca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cbcf  add     rax, 18h
0x14000cbd3  mov     [rbx], rax
0x14000cbd6  jmp     short loc_14000CB94
0x14000cbd8  test    r14, r14
0x14000cbdb  jz      short loc_14000CC53
0x14000cbdd  mov     rax, [rcx]
0x14000cbe0  mov     r15d, [rax-10h]
0x14000cbe4  mov     rbp, r14
0x14000cbe7  sub     rbp, rax
0x14000cbea  sar     rbp, 1
0x14000cbed  mov     ecx, 1
0x14000cbf2  sub     ecx, [rax-8]
0x14000cbf5  mov     eax, [rax-0Ch]
0x14000cbf8  sub     eax, edi
0x14000cbfa  or      ecx, eax
0x14000cbfc  jge     short loc_14000CC08
0x14000cbfe  mov     edx, edi
0x14000cc00  mov     rcx, rbx
0x14000cc03  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14000cc08  mov     rcx, [rbx]; Destination
0x14000cc0b  lea     rsi, [rdi+rdi]
0x14000cc0f  cmp     rbp, r15
0x14000cc12  ja      short loc_14000CC27
0x14000cc14  lea     r8, [rcx+rbp*2]; Source
0x14000cc18  mov     r9, rsi; SourceSize
0x14000cc1b  mov     rdx, rsi; DestinationSize
0x14000cc1e  call    cs:__imp_memmove_s
0x14000cc24  nop
0x14000cc25  jmp     short loc_14000CC36
0x14000cc27  mov     r9, rsi; SourceSize
0x14000cc2a  mov     r8, r14; Source
0x14000cc2d  mov     rdx, rsi; DestinationSize
0x14000cc30  call    cs:__imp_memcpy_s
0x14000cc36  test    edi, edi
0x14000cc38  js      short loc_14000CC53
0x14000cc3a  mov     rax, [rbx]
0x14000cc3d  cmp     edi, [rax-0Ch]
0x14000cc40  jg      short loc_14000CC53
0x14000cc42  mov     [rax-10h], edi
0x14000cc45  mov     rcx, [rbx]
0x14000cc48  xor     eax, eax
0x14000cc4a  mov     [rsi+rcx], ax
0x14000cc4e  jmp     loc_14000CB94
0x14000cc53  mov     ecx, 80070057h; int
0x14000cc58  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
