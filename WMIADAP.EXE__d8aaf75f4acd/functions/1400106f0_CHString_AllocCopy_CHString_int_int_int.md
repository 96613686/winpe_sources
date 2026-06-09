# CHString::AllocCopy(CHString &,int,int,int)

- ea: `0x1400106f0`
- end: `0x1400107af`
- name: `?AllocCopy@CHString@@IEBAXAEAV1@HHH@Z`
- size: `191`
- prototype: `void __fastcall(CHString *this, struct CHString *, int, int, int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140011370`
- `0x140011520`
- `0x140011710`

## callees

- `0x1400027e1`
- `0x1400061a0`
- `0x14000787c`
- `0x1400101e4`
- `0x140010630`
- `0x1400106f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140010727`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140010727`

## pseudocode

```c
void __fastcall CHString::AllocCopy(CHString *this, struct CHString *a2, int a3, int a4, int a5)
{
  __int64 v5; // rsi
  __int64 v9; // [rsp+20h] [rbp-38h] BYREF
  size_t Size[6]; // [rsp+28h] [rbp-30h] BYREF

  v5 = a4;
  if ( a3 < 0 || a4 < 0 || a5 < 0 )
    RaiseException(0x57u, 1u, 0, 0);
  SafeInt<unsigned __int64>::SafeInt<unsigned __int64>(&v9, (unsigned int)a3);
  SafeInt<unsigned __int64>::SafeInt<unsigned __int64>(Size, (unsigned int)a5);
  SafeInt<unsigned __int64>::operator+(&v9, Size, Size[0]);
  if ( Size[0] )
  {
    CHString::AllocBuffer(a2, Size[0]);
    SafeInt<unsigned __int64>::operator*<unsigned __int64>(&v9, (__int64)Size);
    memcpy_0(*(void **)a2, (const void *)(*(_QWORD *)this + 2 * v5), Size[0]);
  }
  else
  {
    *(_QWORD *)a2 = afxPchNil;
  }
}

```

## disassembly

```asm
0x1400106f0  push    rbx
0x1400106f2  push    rbp
0x1400106f3  push    rsi
0x1400106f4  push    r14
0x1400106f6  sub     rsp, 38h
0x1400106fa  movsxd  rsi, r9d
0x1400106fd  mov     ebp, r8d
0x140010700  mov     rbx, rdx
0x140010703  mov     r14, rcx
0x140010706  test    r8d, r8d
0x140010709  js      short loc_14001071A
0x14001070b  test    r9d, r9d
0x14001070e  js      short loc_14001071A
0x140010710  cmp     [rsp+58h+arg_20], 0
0x140010718  jge     short loc_14001072D
0x14001071a  xor     r9d, r9d; lpArguments
0x14001071d  xor     r8d, r8d; nNumberOfArguments
0x140010720  lea     edx, [r9+1]; dwExceptionFlags
0x140010724  lea     ecx, [rdx+56h]; dwExceptionCode
0x140010727  call    cs:__imp_RaiseException
0x14001072d  mov     edx, ebp
0x14001072f  lea     rcx, [rsp+58h+var_38]
0x140010734  call    ??$?0H@?$SafeInt@_K@@QEAA@H@Z; SafeInt<unsigned __int64>::SafeInt<unsigned __int64>(int)
0x140010739  mov     edx, [rsp+58h+arg_20]
0x140010740  lea     rcx, [rsp+58h+Size]
0x140010745  call    ??$?0H@?$SafeInt@_K@@QEAA@H@Z; SafeInt<unsigned __int64>::SafeInt<unsigned __int64>(int)
0x14001074a  mov     r8, [rsp+58h+Size]
0x14001074f  lea     rdx, [rsp+58h+Size]
0x140010754  lea     rcx, [rsp+58h+var_38]
0x140010759  call    ??H?$SafeInt@_K@@QEAA?AV0@V0@@Z; SafeInt<unsigned __int64>::operator+(SafeInt<unsigned __int64>)
0x14001075e  mov     rdx, [rsp+58h+Size]; int
0x140010763  test    rdx, rdx
0x140010766  jnz     short loc_140010774
0x140010768  mov     rax, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x14001076f  mov     [rbx], rax
0x140010772  jmp     short loc_1400107A5
0x140010774  mov     rcx, rbx; this
0x140010777  call    ?AllocBuffer@CHString@@IEAAXH@Z; CHString::AllocBuffer(int)
0x14001077c  mov     r8d, 2
0x140010782  lea     rdx, [rsp+58h+Size]
0x140010787  lea     rcx, [rsp+58h+var_38]
0x14001078c  call    ??$?D_K@?$SafeInt@_K@@QEAA?AV0@_K@Z; SafeInt<unsigned __int64>::operator*<unsigned __int64>(unsigned __int64)
0x140010791  mov     rax, [r14]
0x140010794  mov     r8, [rsp+58h+Size]; Size
0x140010799  mov     rcx, [rbx]; void *
0x14001079c  lea     rdx, [rax+rsi*2]; Src
0x1400107a0  call    memcpy_0
0x1400107a5  add     rsp, 38h
0x1400107a9  pop     r14
0x1400107ab  pop     rsi
0x1400107ac  pop     rbp
0x1400107ad  pop     rbx
0x1400107ae  retn
```
