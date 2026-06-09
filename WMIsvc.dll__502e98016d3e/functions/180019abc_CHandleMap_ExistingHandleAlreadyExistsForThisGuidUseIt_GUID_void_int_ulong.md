# CHandleMap::ExistingHandleAlreadyExistsForThisGuidUseIt(_GUID,void * &,int &,ulong)

- ea: `0x180019abc`
- end: `0x180019b46`
- name: `?ExistingHandleAlreadyExistsForThisGuidUseIt@CHandleMap@@QEAAHU_GUID@@AEAPEAXAEAHK@Z`
- size: `138`
- prototype: `__int64 __fastcall(CHandleMap *__hidden this, struct _GUID *, void **, int *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000abc0`

## callees

- `0x180019abc`

## import_xrefs

- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180019afe`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180019afe`

## pseudocode

```c
__int64 __fastcall CHandleMap::ExistingHandleAlreadyExistsForThisGuidUseIt(
        CHandleMap *this,
        struct _GUID *a2,
        void **a3,
        int *a4,
        unsigned int a5)
{
  unsigned int v9; // edi
  unsigned int i; // ebx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax

  *a3 = 0;
  *a4 = 1;
  v9 = 50;
  for ( i = 0; (signed int)i < *(_DWORD *)this; ++i )
  {
    v11 = CFlexArray::operator[](this, i);
    v12 = *(_QWORD *)v11;
    v13 = *(_QWORD *)(*(_QWORD *)v11 + 8LL) - *(_QWORD *)&a2->Data1;
    if ( !v13 )
      v13 = *(_QWORD *)(v12 + 16) - *(_QWORD *)a2->Data4;
    if ( !v13 && *(_DWORD *)(v12 + 24) == a5 )
    {
      *a3 = *(void **)v12;
      _InterlockedIncrement((volatile signed __int32 *)(v12 + 28));
      v9 = 0;
      *a4 = 0;
      return v9;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180019abc  push    rbx
0x180019abe  push    rbp
0x180019abf  push    rsi
0x180019ac0  push    rdi
0x180019ac1  push    r12
0x180019ac3  push    r14
0x180019ac5  push    r15
0x180019ac7  sub     rsp, 20h
0x180019acb  mov     r12d, [rsp+58h+arg_20]
0x180019ad3  mov     rsi, r9
0x180019ad6  mov     qword ptr [r8], 0
0x180019add  mov     r14, r8
0x180019ae0  mov     dword ptr [r9], 1
0x180019ae7  mov     r15, rdx
0x180019aea  mov     rbp, rcx
0x180019aed  mov     edi, 32h ; '2'
0x180019af2  xor     ebx, ebx
0x180019af4  cmp     ebx, [rbp+0]
0x180019af7  jge     short loc_180019B35
0x180019af9  mov     edx, ebx
0x180019afb  mov     rcx, rbp
0x180019afe  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x180019b04  mov     rcx, [rax]
0x180019b07  mov     rax, [rcx+8]
0x180019b0b  sub     rax, [r15]
0x180019b0e  jnz     short loc_180019B18
0x180019b10  mov     rax, [rcx+10h]
0x180019b14  sub     rax, [r15+8]
0x180019b18  test    rax, rax
0x180019b1b  jnz     short loc_180019B23
0x180019b1d  cmp     [rcx+18h], r12d
0x180019b21  jz      short loc_180019B27
0x180019b23  inc     ebx
0x180019b25  jmp     short loc_180019AF4
0x180019b27  mov     rax, [rcx]
0x180019b2a  mov     [r14], rax
0x180019b2d  lock inc dword ptr [rcx+1Ch]
0x180019b31  xor     edi, edi
0x180019b33  mov     [rsi], edi
0x180019b35  mov     eax, edi
0x180019b37  add     rsp, 20h
0x180019b3b  pop     r15
0x180019b3d  pop     r14
0x180019b3f  pop     r12
0x180019b41  pop     rdi
0x180019b42  pop     rsi
0x180019b43  pop     rbp
0x180019b44  pop     rbx
0x180019b45  retn
```
