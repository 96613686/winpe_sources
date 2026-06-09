# ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180003d44`
- end: `0x180003e21`
- name: `?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `221`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, LCID lcid, int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003cf0`
- `0x180003d10`
- `0x180003d30`

## callees

- `0x180003d44`
- `0x180003e28`
- `0x180009417`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetIDsOfNames(
        ATL::CComTypeInfoHolder *this,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        LCID lcid,
        int *a6)
{
  __int64 result; // rax
  __int64 v10; // r15
  __int64 v11; // rbp
  _WORD *v12; // r14
  __int64 v13; // rsi
  unsigned int v14; // ebx

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    result = 0;
  else
    result = ATL::CComTypeInfoHolder::GetTI(this, lcid);
  v10 = *((_QWORD *)this + 3);
  if ( v10 )
  {
    v11 = *((_QWORD *)this + 5);
    if ( v11 && a4 == 1 )
    {
      v12 = *a3;
      if ( *a3 )
      {
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
      }
      else
      {
        LODWORD(v13) = 0;
      }
      v14 = *((_DWORD *)this + 12);
      while ( (--v14 & 0x80000000) == 0 )
      {
        if ( (_DWORD)v13 == *(_DWORD *)(v11 + 16LL * v14 + 8)
          && !memcmp_0(*(const void **)(v11 + 16LL * v14), v12, 2LL * *(int *)(v11 + 16LL * v14 + 8)) )
        {
          *a6 = *(_DWORD *)(v11 + 16LL * v14 + 12);
          return 0;
        }
      }
    }
    return (*(__int64 (__fastcall **)(__int64, unsigned __int16 **, _QWORD, int *))(*(_QWORD *)v10 + 80LL))(
             v10,
             a3,
             a4,
             a6);
  }
  return result;
}

```

## disassembly

```asm
0x180003d44  push    rbx
0x180003d46  push    rbp
0x180003d47  push    rsi
0x180003d48  push    rdi
0x180003d49  push    r12
0x180003d4b  push    r13
0x180003d4d  push    r14
0x180003d4f  push    r15
0x180003d51  sub     rsp, 38h
0x180003d55  xor     edx, edx
0x180003d57  mov     r12d, r9d
0x180003d5a  mov     r13, r8
0x180003d5d  mov     rdi, rcx
0x180003d60  cmp     [rcx+18h], rdx
0x180003d64  jz      short loc_180003D70
0x180003d66  cmp     [rcx+28h], rdx
0x180003d6a  jz      short loc_180003D70
0x180003d6c  mov     eax, edx
0x180003d6e  jmp     short loc_180003D7E
0x180003d70  mov     edx, [rsp+78h+lcid]; lcid
0x180003d77  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180003d7c  xor     edx, edx
0x180003d7e  mov     r15, [rdi+18h]
0x180003d82  test    r15, r15
0x180003d85  jz      short loc_180003DFE
0x180003d87  mov     rbp, [rdi+28h]
0x180003d8b  test    rbp, rbp
0x180003d8e  jz      short loc_180003DE1
0x180003d90  cmp     r12d, 1
0x180003d94  jnz     short loc_180003DE1
0x180003d96  mov     r14, [r13+0]
0x180003d9a  test    r14, r14
0x180003d9d  jnz     short loc_180003DA3
0x180003d9f  mov     esi, edx
0x180003da1  jmp     short loc_180003DB1
0x180003da3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003da7  inc     rsi
0x180003daa  cmp     [r14+rsi*2], dx
0x180003daf  jnz     short loc_180003DA7
0x180003db1  mov     ebx, [rdi+30h]
0x180003db4  jmp     short loc_180003DDC
0x180003db6  mov     edi, ebx
0x180003db8  add     rdi, rdi
0x180003dbb  cmp     esi, [rbp+rdi*8+8]
0x180003dbf  jnz     short loc_180003DDC
0x180003dc1  movsxd  r8, dword ptr [rbp+rdi*8+8]
0x180003dc6  mov     rdx, r14; Buf2
0x180003dc9  mov     rcx, [rbp+rdi*8+0]; Buf1
0x180003dce  add     r8, r8; Size
0x180003dd1  call    memcmp_0
0x180003dd6  xor     edx, edx
0x180003dd8  test    eax, eax
0x180003dda  jz      short loc_180003E0F
0x180003ddc  sub     ebx, 1
0x180003ddf  jns     short loc_180003DB6
0x180003de1  mov     rax, [r15]
0x180003de4  mov     r8d, r12d
0x180003de7  mov     r9, [rsp+78h+arg_28]
0x180003def  mov     rdx, r13
0x180003df2  mov     rcx, r15
0x180003df5  mov     rax, [rax+50h]
0x180003df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dfe  add     rsp, 38h
0x180003e02  pop     r15
0x180003e04  pop     r14
0x180003e06  pop     r13
0x180003e08  pop     r12
0x180003e0a  pop     rdi
0x180003e0b  pop     rsi
0x180003e0c  pop     rbp
0x180003e0d  pop     rbx
0x180003e0e  retn
0x180003e0f  mov     rax, [rsp+78h+arg_28]
0x180003e17  mov     ecx, [rbp+rdi*8+0Ch]
0x180003e1b  mov     [rax], ecx
0x180003e1d  mov     eax, edx
0x180003e1f  jmp     short loc_180003DFE
```
