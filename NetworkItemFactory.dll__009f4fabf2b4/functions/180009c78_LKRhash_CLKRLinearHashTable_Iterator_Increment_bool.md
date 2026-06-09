# LKRhash::CLKRLinearHashTable_Iterator::_Increment(bool)

- ea: `0x180009c78`
- end: `0x180009e7e`
- name: `?_Increment@CLKRLinearHashTable_Iterator@LKRhash@@IEAA_N_N@Z`
- size: `518`
- prototype: `bool __fastcall(LKRhash::CLKRLinearHashTable_Iterator *__hidden this, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008070`
- `0x180009b98`

## callees

- `0x1800075f0`
- `0x180009c78`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180009d42`
- `KERNEL32!GetCurrentThreadId` at `0x180009d42`

## pseudocode

```c
char __fastcall LKRhash::CLKRLinearHashTable_Iterator::_Increment(LKRhash::CLKRLinearHashTable_Iterator *this, char a2)
{
  char *v3; // rbp
  _QWORD *v4; // r8
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  _QWORD *v8; // r14
  __int64 v9; // rcx
  __int64 v10; // rbx
  unsigned int v11; // eax
  volatile signed __int32 *v12; // rsi
  int v13; // ebx
  bool v14; // dl
  char v15; // al
  signed __int32 v16; // edx
  signed __int32 v17; // edx
  bool i; // zf
  signed __int32 v19; // edx
  signed __int32 v20; // edx
  bool j; // zf
  signed __int32 v22; // edx
  char result; // al

  if ( a2 && *(_QWORD *)this && *((_WORD *)this + 10) != 0xFFFF )
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)this + 56LL))(
      *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * *((__int16 *)this + 10) + 24),
      0xFFFFFFFFLL);
  v3 = (char *)this + 8;
LABEL_6:
  v4 = v3;
  while ( 1 )
  {
    v5 = *((__int16 *)this + 10);
    *((_WORD *)this + 10) = v5 + 1;
    if ( (_WORD)v5 != 3 )
    {
      v6 = *(_QWORD *)(*v4 + 8 * v5 + 32);
      if ( v6 )
        break;
    }
    v7 = *v4;
    v8 = v4;
    *((_WORD *)this + 10) = -1;
    v3 = (char *)v4;
    v9 = *(_QWORD *)(v7 + 16);
    *v4 = v9;
    if ( !v9 )
    {
      ++*((_DWORD *)this + 4);
      v10 = *(_QWORD *)this;
      v11 = *((_DWORD *)this + 4);
      if ( v11 < *(_DWORD *)(*(_QWORD *)this + 124LL) )
      {
        v12 = (volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v10 + 104)
                                                    + 8 * ((unsigned __int64)v11 >> *(_DWORD *)(v10 + 68)))
                                        + ((unsigned __int64)(v11 & *(_DWORD *)(v10 + 76)) << 6));
        if ( *(_BYTE *)(v10 + 153) )
        {
          v13 = *(_DWORD *)(v10 + 28);
          v14 = ((v13 ^ GetCurrentThreadId()) & 0xFFFFFFFC) == 0;
        }
        else
        {
          v14 = 1;
        }
        v15 = *(_BYTE *)(*(_QWORD *)this + 153LL);
        if ( v14 )
        {
          if ( v15 )
          {
            if ( (unsigned __int16)*v12
              || (v16 = *v12, v16 != _InterlockedCompareExchange(v12, (v16 + 0x10000) | 0xFFFF, v16)) )
            {
              do
                v17 = *v12;
              while ( v17 != _InterlockedCompareExchange(v12, v17 + 0x10000, v17) );
              CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v12, 1);
            }
          }
          for ( i = *(_BYTE *)(*(_QWORD *)this + 153LL) == 0;
                !i;
                i = v19 == _InterlockedCompareExchange(v12, (v19 - 0x10000) & 0xFFFF0000, v19) )
          {
            v19 = *v12;
          }
        }
        else if ( !v15 || (*(_DWORD *)(*(_QWORD *)this + 24LL) & 0x7FFF) != 0 )
        {
          if ( *(_BYTE *)(*(_QWORD *)this + 153LL) )
          {
            if ( (*v12 & 0xFFFF8000) != 0 || (v20 = *v12, v20 != _InterlockedCompareExchange(v12, v20 + 1, v20)) )
              CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v12, 0);
          }
          for ( j = *(_BYTE *)(*(_QWORD *)this + 153LL) == 0; !j; j = v22 == _InterlockedCompareExchange(
                                                                               v12,
                                                                               v22 - 1,
                                                                               v22) )
            v22 = *v12;
        }
        *v8 = v12 + 2;
      }
      if ( *((_DWORD *)this + 4) >= *(_DWORD *)(*(_QWORD *)this + 124LL) )
      {
        result = 0;
        *(_QWORD *)this = 0;
        *((_WORD *)this + 10) = 0;
        *v8 = 0;
        *((_DWORD *)this + 4) = 0;
        return result;
      }
      goto LABEL_6;
    }
  }
  if ( *(_QWORD *)this && (_WORD)v5 != 0xFFFE )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)this + 56LL))(v6, 1);
  return 1;
}

```

## disassembly

```asm
0x180009c78  push    rbx
0x180009c7a  push    rbp
0x180009c7b  push    rsi
0x180009c7c  push    rdi
0x180009c7d  push    r12
0x180009c7f  push    r13
0x180009c81  push    r14
0x180009c83  sub     rsp, 20h
0x180009c87  or      r13d, 0FFFFFFFFh
0x180009c8b  mov     rdi, rcx
0x180009c8e  test    dl, dl
0x180009c90  jz      short loc_180009CBB
0x180009c92  mov     r8, [rcx]
0x180009c95  test    r8, r8
0x180009c98  jz      short loc_180009CBB
0x180009c9a  cmp     [rcx+14h], r13w
0x180009c9f  jz      short loc_180009CBB
0x180009ca1  movsx   rax, word ptr [rcx+14h]
0x180009ca6  mov     edx, r13d
0x180009ca9  mov     rcx, [rcx+8]
0x180009cad  mov     rcx, [rcx+rax*8+18h]
0x180009cb2  mov     rax, [r8+38h]
0x180009cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cbb  lea     rbp, [rdi+8]
0x180009cbf  mov     r12d, 1
0x180009cc5  mov     r8, rbp
0x180009cc8  movsx   rax, word ptr [rdi+14h]
0x180009ccd  lea     edx, [r12+rax]
0x180009cd1  mov     [rdi+14h], dx
0x180009cd5  cmp     dx, 4
0x180009cd9  jz      short loc_180009CEF
0x180009cdb  mov     rcx, rax
0x180009cde  mov     rax, [r8]
0x180009ce1  mov     rcx, [rax+rcx*8+20h]
0x180009ce6  test    rcx, rcx
0x180009ce9  jnz     loc_180009E5F
0x180009cef  mov     rax, [r8]
0x180009cf2  mov     r14, r8
0x180009cf5  mov     [rdi+14h], r13w
0x180009cfa  mov     rbp, r8
0x180009cfd  mov     rcx, [rax+10h]
0x180009d01  mov     [r8], rcx
0x180009d04  test    rcx, rcx
0x180009d07  jnz     short loc_180009CC8
0x180009d09  add     [rdi+10h], r12d
0x180009d0d  mov     rbx, [rdi]
0x180009d10  mov     eax, [rdi+10h]
0x180009d13  cmp     eax, [rbx+7Ch]
0x180009d16  jnb     loc_180009E26
0x180009d1c  mov     ecx, [rbx+44h]
0x180009d1f  mov     edx, eax
0x180009d21  mov     esi, [rbx+4Ch]
0x180009d24  shr     rdx, cl
0x180009d27  and     rsi, rax
0x180009d2a  mov     rcx, [rbx+68h]
0x180009d2e  shl     rsi, 6
0x180009d32  add     rsi, [rcx+rdx*8]
0x180009d36  cmp     byte ptr [rbx+99h], 0
0x180009d3d  jz      short loc_180009D54
0x180009d3f  mov     ebx, [rbx+1Ch]
0x180009d42  call    cs:__imp_GetCurrentThreadId
0x180009d48  xor     eax, ebx
0x180009d4a  test    eax, 0FFFFFFFCh
0x180009d4f  setz    dl
0x180009d52  jmp     short loc_180009D57
0x180009d54  mov     dl, r12b
0x180009d57  mov     rcx, [rdi]
0x180009d5a  mov     al, [rcx+99h]
0x180009d60  test    dl, dl
0x180009d62  jz      short loc_180009DC6
0x180009d64  test    al, al
0x180009d66  jz      short loc_180009DA2
0x180009d68  mov     edx, [rsi]
0x180009d6a  test    dx, dx
0x180009d6d  jnz     short loc_180009D85
0x180009d6f  lea     ecx, [rdx+10000h]
0x180009d75  mov     eax, edx
0x180009d77  or      ecx, 0FFFFh
0x180009d7d  lock cmpxchg [rsi], ecx
0x180009d81  cmp     edx, eax
0x180009d83  jz      short loc_180009DA2
0x180009d85  mov     edx, [rsi]
0x180009d87  mov     eax, edx
0x180009d89  lea     ecx, [rdx+10000h]
0x180009d8f  lock cmpxchg [rsi], ecx
0x180009d93  cmp     edx, eax
0x180009d95  jnz     short loc_180009D85
0x180009d97  mov     dl, r12b; bool
0x180009d9a  mov     rcx, rsi; this
0x180009d9d  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180009da2  mov     rax, [rdi]
0x180009da5  cmp     byte ptr [rax+99h], 0
0x180009dac  jz      short loc_180009E1F
0x180009dae  mov     edx, [rsi]
0x180009db0  mov     eax, edx
0x180009db2  lea     ecx, [rdx-10000h]
0x180009db8  and     ecx, 0FFFF0000h
0x180009dbe  lock cmpxchg [rsi], ecx
0x180009dc2  cmp     edx, eax
0x180009dc4  jmp     short loc_180009DAC
0x180009dc6  test    al, al
0x180009dc8  jz      short loc_180009DD7
0x180009dca  mov     eax, [rcx+18h]
0x180009dcd  and     eax, 7FFFh
0x180009dd2  cmp     eax, r12d
0x180009dd5  jb      short loc_180009E1F
0x180009dd7  mov     rax, [rdi]
0x180009dda  cmp     byte ptr [rax+99h], 0
0x180009de1  jz      short loc_180009E04
0x180009de3  mov     edx, [rsi]
0x180009de5  test    edx, 0FFFF8000h
0x180009deb  jnz     short loc_180009DFA
0x180009ded  lea     ecx, [rdx+1]
0x180009df0  mov     eax, edx
0x180009df2  lock cmpxchg [rsi], ecx
0x180009df6  cmp     edx, eax
0x180009df8  jz      short loc_180009E04
0x180009dfa  xor     edx, edx; bool
0x180009dfc  mov     rcx, rsi; this
0x180009dff  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180009e04  mov     rax, [rdi]
0x180009e07  cmp     byte ptr [rax+99h], 0
0x180009e0e  jz      short loc_180009E1F
0x180009e10  mov     edx, [rsi]
0x180009e12  mov     eax, edx
0x180009e14  lea     ecx, [rdx-1]
0x180009e17  lock cmpxchg [rsi], ecx
0x180009e1b  cmp     edx, eax
0x180009e1d  jmp     short loc_180009E0E
0x180009e1f  lea     rax, [rsi+8]
0x180009e23  mov     [r14], rax
0x180009e26  mov     rax, [rdi]
0x180009e29  mov     ecx, [rax+7Ch]
0x180009e2c  cmp     [rdi+10h], ecx
0x180009e2f  jb      loc_180009CC5
0x180009e35  xor     eax, eax
0x180009e37  mov     qword ptr [rdi], 0
0x180009e3e  mov     [rdi+14h], ax
0x180009e42  mov     qword ptr [r14], 0
0x180009e49  mov     dword ptr [rdi+10h], 0
0x180009e50  add     rsp, 20h
0x180009e54  pop     r14
0x180009e56  pop     r13
0x180009e58  pop     r12
0x180009e5a  pop     rdi
0x180009e5b  pop     rsi
0x180009e5c  pop     rbp
0x180009e5d  pop     rbx
0x180009e5e  retn
0x180009e5f  mov     rax, [rdi]
0x180009e62  test    rax, rax
0x180009e65  jz      short loc_180009E79
0x180009e67  cmp     dx, r13w
0x180009e6b  jz      short loc_180009E79
0x180009e6d  mov     rax, [rax+38h]
0x180009e71  mov     edx, r12d
0x180009e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e79  mov     al, r12b
0x180009e7c  jmp     short loc_180009E50
```
