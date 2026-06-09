# ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,wchar_t * *,uint,ulong,long *)

- ea: `0x18000f944`
- end: `0x18000fa21`
- name: `?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEA_WIKPEAJ@Z`
- size: `221`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, const struct _GUID *, wchar_t **, unsigned int, LCID lcid, int *)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f8b0`
- `0x18000f8d0`
- `0x18000f8f0`
- `0x18000f910`
- `0x18000f930`

## callees

- `0x18000f944`
- `0x18000fc68`
- `0x180016dd0`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetIDsOfNames(
        ATL::CComTypeInfoHolder *this,
        const struct _GUID *a2,
        wchar_t **a3,
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
    return (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD, int *))(*(_QWORD *)v10 + 80LL))(v10, a3, a4, a6);
  }
  return result;
}

```

## disassembly

```asm
0x18000f944  push    rbx
0x18000f946  push    rbp
0x18000f947  push    rsi
0x18000f948  push    rdi
0x18000f949  push    r12
0x18000f94b  push    r13
0x18000f94d  push    r14
0x18000f94f  push    r15
0x18000f951  sub     rsp, 38h
0x18000f955  xor     edx, edx
0x18000f957  mov     r12d, r9d
0x18000f95a  mov     r13, r8
0x18000f95d  mov     rdi, rcx
0x18000f960  cmp     [rcx+18h], rdx
0x18000f964  jz      short loc_18000F970
0x18000f966  cmp     [rcx+28h], rdx
0x18000f96a  jz      short loc_18000F970
0x18000f96c  mov     eax, edx
0x18000f96e  jmp     short loc_18000F97E
0x18000f970  mov     edx, [rsp+78h+lcid]; lcid
0x18000f977  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000f97c  xor     edx, edx
0x18000f97e  mov     r15, [rdi+18h]
0x18000f982  test    r15, r15
0x18000f985  jz      short loc_18000F9FE
0x18000f987  mov     rbp, [rdi+28h]
0x18000f98b  test    rbp, rbp
0x18000f98e  jz      short loc_18000F9E1
0x18000f990  cmp     r12d, 1
0x18000f994  jnz     short loc_18000F9E1
0x18000f996  mov     r14, [r13+0]
0x18000f99a  test    r14, r14
0x18000f99d  jnz     short loc_18000F9A3
0x18000f99f  mov     esi, edx
0x18000f9a1  jmp     short loc_18000F9B1
0x18000f9a3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000f9a7  inc     rsi
0x18000f9aa  cmp     [r14+rsi*2], dx
0x18000f9af  jnz     short loc_18000F9A7
0x18000f9b1  mov     ebx, [rdi+30h]
0x18000f9b4  jmp     short loc_18000F9DC
0x18000f9b6  mov     edi, ebx
0x18000f9b8  add     rdi, rdi
0x18000f9bb  cmp     esi, [rbp+rdi*8+8]
0x18000f9bf  jnz     short loc_18000F9DC
0x18000f9c1  movsxd  r8, dword ptr [rbp+rdi*8+8]
0x18000f9c6  mov     rdx, r14; Buf2
0x18000f9c9  mov     rcx, [rbp+rdi*8+0]; Buf1
0x18000f9ce  add     r8, r8; Size
0x18000f9d1  call    memcmp_0
0x18000f9d6  xor     edx, edx
0x18000f9d8  test    eax, eax
0x18000f9da  jz      short loc_18000FA0F
0x18000f9dc  sub     ebx, 1
0x18000f9df  jns     short loc_18000F9B6
0x18000f9e1  mov     rax, [r15]
0x18000f9e4  mov     r8d, r12d
0x18000f9e7  mov     r9, [rsp+78h+arg_28]
0x18000f9ef  mov     rdx, r13
0x18000f9f2  mov     rcx, r15
0x18000f9f5  mov     rax, [rax+50h]
0x18000f9f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9fe  add     rsp, 38h
0x18000fa02  pop     r15
0x18000fa04  pop     r14
0x18000fa06  pop     r13
0x18000fa08  pop     r12
0x18000fa0a  pop     rdi
0x18000fa0b  pop     rsi
0x18000fa0c  pop     rbp
0x18000fa0d  pop     rbx
0x18000fa0e  retn
0x18000fa0f  mov     rax, [rsp+78h+arg_28]
0x18000fa17  mov     ecx, [rbp+rdi*8+0Ch]
0x18000fa1b  mov     [rax], ecx
0x18000fa1d  mov     eax, edx
0x18000fa1f  jmp     short loc_18000F9FE
```
