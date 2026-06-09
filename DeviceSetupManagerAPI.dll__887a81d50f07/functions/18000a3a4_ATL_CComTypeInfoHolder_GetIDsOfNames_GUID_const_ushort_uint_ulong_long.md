# ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x18000a3a4`
- end: `0x18000a481`
- name: `?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `221`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, LCID lcid, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a390`
- `0x18000bf30`

## callees

- `0x18000a3a4`
- `0x18000a584`
- `0x18000e44c`
- `0x18000f010`

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
0x18000a3a4  push    rbx
0x18000a3a6  push    rbp
0x18000a3a7  push    rsi
0x18000a3a8  push    rdi
0x18000a3a9  push    r12
0x18000a3ab  push    r13
0x18000a3ad  push    r14
0x18000a3af  push    r15
0x18000a3b1  sub     rsp, 38h
0x18000a3b5  xor     edx, edx
0x18000a3b7  mov     r12d, r9d
0x18000a3ba  mov     r13, r8
0x18000a3bd  mov     rdi, rcx
0x18000a3c0  cmp     [rcx+18h], rdx
0x18000a3c4  jz      short loc_18000A3D0
0x18000a3c6  cmp     [rcx+28h], rdx
0x18000a3ca  jz      short loc_18000A3D0
0x18000a3cc  mov     eax, edx
0x18000a3ce  jmp     short loc_18000A3DE
0x18000a3d0  mov     edx, [rsp+78h+lcid]; lcid
0x18000a3d7  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000a3dc  xor     edx, edx
0x18000a3de  mov     r15, [rdi+18h]
0x18000a3e2  test    r15, r15
0x18000a3e5  jz      short loc_18000A45E
0x18000a3e7  mov     rbp, [rdi+28h]
0x18000a3eb  test    rbp, rbp
0x18000a3ee  jz      short loc_18000A441
0x18000a3f0  cmp     r12d, 1
0x18000a3f4  jnz     short loc_18000A441
0x18000a3f6  mov     r14, [r13+0]
0x18000a3fa  test    r14, r14
0x18000a3fd  jnz     short loc_18000A403
0x18000a3ff  mov     esi, edx
0x18000a401  jmp     short loc_18000A411
0x18000a403  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a407  inc     rsi
0x18000a40a  cmp     [r14+rsi*2], dx
0x18000a40f  jnz     short loc_18000A407
0x18000a411  mov     ebx, [rdi+30h]
0x18000a414  jmp     short loc_18000A43C
0x18000a416  mov     edi, ebx
0x18000a418  add     rdi, rdi
0x18000a41b  cmp     esi, [rbp+rdi*8+8]
0x18000a41f  jnz     short loc_18000A43C
0x18000a421  movsxd  r8, dword ptr [rbp+rdi*8+8]
0x18000a426  mov     rdx, r14; Buf2
0x18000a429  mov     rcx, [rbp+rdi*8+0]; Buf1
0x18000a42e  add     r8, r8; Size
0x18000a431  call    memcmp_0
0x18000a436  xor     edx, edx
0x18000a438  test    eax, eax
0x18000a43a  jz      short loc_18000A46F
0x18000a43c  sub     ebx, 1
0x18000a43f  jns     short loc_18000A416
0x18000a441  mov     rax, [r15]
0x18000a444  mov     r8d, r12d
0x18000a447  mov     r9, [rsp+78h+arg_28]
0x18000a44f  mov     rdx, r13
0x18000a452  mov     rcx, r15
0x18000a455  mov     rax, [rax+50h]
0x18000a459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a45e  add     rsp, 38h
0x18000a462  pop     r15
0x18000a464  pop     r14
0x18000a466  pop     r13
0x18000a468  pop     r12
0x18000a46a  pop     rdi
0x18000a46b  pop     rsi
0x18000a46c  pop     rbp
0x18000a46d  pop     rbx
0x18000a46e  retn
0x18000a46f  mov     rax, [rsp+78h+arg_28]
0x18000a477  mov     ecx, [rbp+rdi*8+0Ch]
0x18000a47b  mov     [rax], ecx
0x18000a47d  mov     eax, edx
0x18000a47f  jmp     short loc_18000A45E
```
