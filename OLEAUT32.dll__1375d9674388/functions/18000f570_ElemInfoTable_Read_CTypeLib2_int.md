# ElemInfoTable::Read(CTypeLib2 *,int)

- ea: `0x18000f570`
- end: `0x18000f8fa`
- name: `?Read@ElemInfoTable@@QEAAJPEAVCTypeLib2@@H@Z`
- size: `906`
- prototype: `__int64 __fastcall(ElemInfoTable *__hidden this, struct CTypeLib2 *, int)`
- caller_count: `21`
- callee_count: `4`
- tags: ``

## callers

- `0x18000af80`
- `0x18000d530`
- `0x18000dd50`
- `0x18001144c`
- `0x180014040`
- `0x18001425c`
- `0x180015854`
- `0x180016c44`
- `0x18002e970`
- `0x18002fac0`
- `0x18002fca0`
- `0x180034f48`
- `0x1800352fc`
- `0x18003fce8`
- `0x18004bb90`
- `0x18004c750`
- `0x18004ca44`
- `0x18006e880`
- `0x18006e940`
- `0x18006f3a0`
- `0x18006f5c0`

## callees

- `0x18000f570`
- `0x18000f900`
- `0x18000f960`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f85b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f85b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f5a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f5a0`

## pseudocode

```c
__int64 __fastcall ElemInfoTable::Read(ElemInfoTable *this, struct CTypeLib2 *a2, int a3)
{
  int v4; // edi
  int v7; // eax
  bool v8; // zf
  int v9; // eax
  __int64 v10; // r9
  unsigned int *v11; // r9
  __int64 v12; // r15
  int v13; // ecx
  char v14; // al
  __int64 v15; // rax
  __int64 v16; // rcx
  unsigned int v17; // r9d
  int v18; // eax
  unsigned int v19; // ebp
  __int64 v20; // r8
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // r8
  unsigned int v24; // r15d
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // r8
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // r8
  int v32; // eax
  __int64 v34; // rcx
  int v35; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v36; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v37; // [rsp+80h] [rbp+18h] BYREF

  v37 = 0;
  v4 = 0;
  v36 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 608));
  if ( a3 )
  {
    if ( a3 != 1 )
      goto LABEL_26;
    v7 = *((_DWORD *)this + 3);
    v8 = (v7 & 4) == 0;
  }
  else
  {
    v7 = *((_DWORD *)this + 3);
    v8 = (v7 & 8) == 0;
  }
  if ( v8 )
  {
    v9 = v7 | 0x10;
    *((_DWORD *)this + 3) = v9;
    if ( *((_QWORD *)a2 + 64) )
    {
      v10 = *(unsigned int *)this;
      *((_DWORD *)this + 3) = v9 & 0xFFFFFFF3 | 8;
      v11 = (unsigned int *)(*((_QWORD *)a2 + 64) + v10);
    }
    else
    {
      v11 = 0;
      *((_DWORD *)this + 3) = v9 & 0xFFFFFFF3;
    }
    *((_QWORD *)this + 2) = v11;
    v12 = *((unsigned __int16 *)this + 12) + (unsigned int)*((unsigned __int16 *)this + 13);
    if ( !a3 && (_DWORD)v12 && (*((_BYTE *)this + 12) & 8) != 0 )
    {
      v34 = *v11;
      *((_QWORD *)this + 2) = v11 + 1;
      *((_DWORD *)this + 1) = v34;
      *((_DWORD *)this + 2) = -1;
      *((_QWORD *)this + 4) = (char *)v11 + v34 + 4;
      *((_QWORD *)this + 5) = (char *)&v11[v12 + 1] + (unsigned int)v34;
      *((_QWORD *)this + 6) = (char *)&v11[2 * v12 + 1] + (unsigned int)v34;
    }
    else
    {
      v13 = *(_DWORD *)this;
      *((_DWORD *)this + 3) |= 1u;
      v14 = *((_DWORD *)this + 3) | 2;
      *((_DWORD *)this + 1) = 0;
      *((_DWORD *)this + 2) = -1;
      *((_DWORD *)this + 3) = v14 & 3 | 0xC;
      *((_QWORD *)this + 2) = 0;
      if ( (_DWORD)v12 )
      {
        *((_DWORD *)a2 + 126) = v13;
        *((_DWORD *)a2 + 127) = 0;
        *((_QWORD *)this + 4) = MemAlloc(4LL * (unsigned int)v12);
        *((_QWORD *)this + 5) = MemAlloc(4LL * (unsigned int)v12);
        v15 = MemAlloc(4LL * (unsigned int)v12);
        *((_QWORD *)this + 6) = v15;
        if ( *((_QWORD *)this + 4) && *((_QWORD *)this + 5) && v15 )
        {
          v16 = *((_QWORD *)a2 + 60);
          v35 = 0;
          v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *, __int64, int *))(*(_QWORD *)v16 + 24LL))(
                 v16,
                 *((_QWORD *)a2 + 63),
                 &v37,
                 4,
                 &v35);
          if ( v4 >= 0 )
          {
            v18 = v35;
            *((_DWORD *)a2 + 126) += v35;
            if ( v18 != 4 )
              goto LABEL_25;
            v4 = HEAP::AllocChunk2(this, &v36, v37, v17);
            if ( v4 >= 0 )
            {
              v19 = v37;
              v20 = v36 >= *((_DWORD *)this + 1) ? 0LL : *((_QWORD *)this + 2) + v36;
              v21 = *((_QWORD *)a2 + 60);
              v35 = 0;
              v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int *))(*(_QWORD *)v21 + 24LL))(
                     v21,
                     *((_QWORD *)a2 + 63),
                     v20,
                     v37,
                     &v35);
              if ( v4 >= 0 )
              {
                v22 = v35;
                *((_DWORD *)a2 + 126) += v35;
                if ( v19 != v22 )
                  goto LABEL_25;
                v23 = *((_QWORD *)this + 4);
                *((_DWORD *)this + 7) = v12;
                v24 = 4 * v12;
                v25 = *((_QWORD *)a2 + 60);
                v35 = 0;
                v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int *))(*(_QWORD *)v25 + 24LL))(
                       v25,
                       *((_QWORD *)a2 + 63),
                       v23,
                       v24,
                       &v35);
                if ( v4 >= 0 )
                {
                  v26 = v35;
                  *((_DWORD *)a2 + 126) += v35;
                  if ( v24 != v26 )
                    goto LABEL_25;
                  v27 = *((_QWORD *)a2 + 60);
                  v28 = *((_QWORD *)this + 5);
                  v35 = 0;
                  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int *))(*(_QWORD *)v27 + 24LL))(
                         v27,
                         *((_QWORD *)a2 + 63),
                         v28,
                         v24,
                         &v35);
                  if ( v4 >= 0 )
                  {
                    v29 = v35;
                    *((_DWORD *)a2 + 126) += v35;
                    if ( v24 != v29
                      || (v30 = *((_QWORD *)a2 + 60),
                          v31 = *((_QWORD *)this + 6),
                          v35 = 0,
                          v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int *))(*(_QWORD *)v30 + 24LL))(
                                 v30,
                                 *((_QWORD *)a2 + 63),
                                 v31,
                                 v24,
                                 &v35),
                          v4 >= 0)
                      && (v32 = v35, *((_DWORD *)a2 + 126) += v35, v24 != v32) )
                    {
LABEL_25:
                      v4 = -2147287010;
                    }
                  }
                }
              }
            }
          }
        }
        else
        {
          v4 = -2147024882;
        }
      }
    }
  }
LABEL_26:
  *((_DWORD *)this + 3) &= ~0x10u;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 608));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000f570  push    rbx
0x18000f572  push    rbp
0x18000f573  push    rsi
0x18000f574  push    rdi
0x18000f575  push    r12
0x18000f577  push    r14
0x18000f579  sub     rsp, 38h
0x18000f57d  xor     r12d, r12d
0x18000f580  mov     rbx, rcx
0x18000f583  lea     rcx, [rdx+260h]; lpCriticalSection
0x18000f58a  mov     [rsp+68h+arg_10], r12d
0x18000f592  mov     edi, r12d
0x18000f595  mov     [rsp+68h+arg_8], r12d
0x18000f59a  mov     ebp, r8d
0x18000f59d  mov     rsi, rdx
0x18000f5a0  call    cs:__imp_EnterCriticalSection
0x18000f5a6  test    ebp, ebp
0x18000f5a8  jz      loc_18000F870
0x18000f5ae  cmp     ebp, 1
0x18000f5b1  jnz     loc_18000F850
0x18000f5b7  mov     eax, [rbx+0Ch]
0x18000f5ba  test    al, 4
0x18000f5bc  jnz     loc_18000F850
0x18000f5c2  or      eax, 10h
0x18000f5c5  mov     [rsp+68h+var_38], r15
0x18000f5ca  mov     [rbx+0Ch], eax
0x18000f5cd  cmp     [rsi+200h], rdi
0x18000f5d4  jz      loc_18000F889
0x18000f5da  mov     r9d, [rbx]
0x18000f5dd  or      eax, 8
0x18000f5e0  and     eax, 0FFFFFFFBh
0x18000f5e3  mov     [rbx+0Ch], eax
0x18000f5e6  add     r9, [rsi+200h]
0x18000f5ed  mov     [rbx+10h], r9
0x18000f5f1  movzx   r15d, word ptr [rbx+1Ah]
0x18000f5f6  movzx   eax, word ptr [rbx+18h]
0x18000f5fa  add     r15d, eax
0x18000f5fd  test    ebp, ebp
0x18000f5ff  jz      loc_18000F89A
0x18000f605  mov     ecx, [rbx]
0x18000f607  or      dword ptr [rbx+0Ch], 1
0x18000f60b  mov     eax, [rbx+0Ch]
0x18000f60e  or      eax, 2
0x18000f611  mov     [rbx+4], r12d
0x18000f615  or      eax, 4
0x18000f618  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x18000f61f  or      eax, 8
0x18000f622  and     eax, 0FFFFFFEFh
0x18000f625  and     eax, 1Fh
0x18000f628  mov     [rbx+0Ch], eax
0x18000f62b  mov     [rbx+10h], r12
0x18000f62f  test    r15d, r15d
0x18000f632  jz      loc_18000F84B
0x18000f638  mov     [rsi+1F8h], ecx
0x18000f63e  mov     edi, r15d
0x18000f641  shl     rdi, 2
0x18000f645  mov     rcx, rdi
0x18000f648  mov     [rsi+1FCh], r12d
0x18000f64f  call    MemAlloc
0x18000f654  mov     rcx, rdi
0x18000f657  mov     [rbx+20h], rax
0x18000f65b  call    MemAlloc
0x18000f660  mov     rcx, rdi
0x18000f663  mov     [rbx+28h], rax
0x18000f667  call    MemAlloc
0x18000f66c  mov     [rbx+30h], rax
0x18000f670  cmp     [rbx+20h], r12
0x18000f674  jz      loc_18000F87A
0x18000f67a  cmp     [rbx+28h], r12
0x18000f67e  jz      loc_18000F87A
0x18000f684  test    rax, rax
0x18000f687  jz      loc_18000F87A
0x18000f68d  mov     rcx, [rsi+1E0h]
0x18000f694  lea     rdx, [rsp+68h+arg_0]
0x18000f699  mov     [rsp+68h+arg_0], r12d
0x18000f69e  lea     r8, [rsp+68h+arg_10]
0x18000f6a6  mov     [rsp+68h+var_48], rdx
0x18000f6ab  mov     r9d, 4
0x18000f6b1  mov     rdx, [rsi+1F8h]
0x18000f6b8  mov     rax, [rcx]
0x18000f6bb  mov     rax, [rax+18h]
0x18000f6bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6c4  mov     edi, eax
0x18000f6c6  test    eax, eax
0x18000f6c8  js      loc_18000F84B
0x18000f6ce  mov     eax, [rsp+68h+arg_0]
0x18000f6d2  add     [rsi+1F8h], eax
0x18000f6d8  cmp     eax, 4
0x18000f6db  jnz     loc_18000F846
0x18000f6e1  mov     r8d, [rsp+68h+arg_10]; unsigned int
0x18000f6e9  lea     rdx, [rsp+68h+arg_8]; unsigned int *
0x18000f6ee  mov     rcx, rbx; this
0x18000f6f1  call    ?AllocChunk2@HEAP@@AEAAJPEAKKK@Z; HEAP::AllocChunk2(ulong *,ulong,ulong)
0x18000f6f6  mov     edi, eax
0x18000f6f8  test    eax, eax
0x18000f6fa  js      loc_18000F84B
0x18000f700  mov     eax, [rsp+68h+arg_8]
0x18000f704  mov     ebp, [rsp+68h+arg_10]
0x18000f70b  cmp     eax, [rbx+4]
0x18000f70e  jnb     loc_18000F881
0x18000f714  mov     r8d, eax
0x18000f717  add     r8, [rbx+10h]
0x18000f71b  mov     rcx, [rsi+1E0h]
0x18000f722  lea     rdx, [rsp+68h+arg_0]
0x18000f727  mov     [rsp+68h+arg_0], r12d
0x18000f72c  mov     r9d, ebp
0x18000f72f  mov     [rsp+68h+var_48], rdx
0x18000f734  mov     rdx, [rsi+1F8h]
0x18000f73b  mov     rax, [rcx]
0x18000f73e  mov     rax, [rax+18h]
0x18000f742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f747  mov     edi, eax
0x18000f749  test    eax, eax
0x18000f74b  js      loc_18000F84B
0x18000f751  mov     eax, [rsp+68h+arg_0]
0x18000f755  add     [rsi+1F8h], eax
0x18000f75b  cmp     ebp, eax
0x18000f75d  jnz     loc_18000F846
0x18000f763  mov     r8, [rbx+20h]
0x18000f767  lea     rdx, [rsp+68h+arg_0]
0x18000f76c  mov     [rbx+1Ch], r15d
0x18000f770  lea     r15d, ds:0[r15*4]
0x18000f778  mov     rcx, [rsi+1E0h]
0x18000f77f  mov     r9d, r15d
0x18000f782  mov     [rsp+68h+arg_0], r12d
0x18000f787  mov     [rsp+68h+var_48], rdx
0x18000f78c  mov     rdx, [rsi+1F8h]
0x18000f793  mov     rax, [rcx]
0x18000f796  mov     rax, [rax+18h]
0x18000f79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f79f  mov     edi, eax
0x18000f7a1  test    eax, eax
0x18000f7a3  js      loc_18000F84B
0x18000f7a9  mov     eax, [rsp+68h+arg_0]
0x18000f7ad  add     [rsi+1F8h], eax
0x18000f7b3  cmp     r15d, eax
0x18000f7b6  jnz     loc_18000F846
0x18000f7bc  mov     rcx, [rsi+1E0h]
0x18000f7c3  lea     rdx, [rsp+68h+arg_0]
0x18000f7c8  mov     r8, [rbx+28h]
0x18000f7cc  mov     r9d, r15d
0x18000f7cf  mov     [rsp+68h+arg_0], r12d
0x18000f7d4  mov     [rsp+68h+var_48], rdx
0x18000f7d9  mov     rax, [rcx]
0x18000f7dc  mov     rdx, [rsi+1F8h]
0x18000f7e3  mov     rax, [rax+18h]
0x18000f7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7ec  mov     edi, eax
0x18000f7ee  test    eax, eax
0x18000f7f0  js      short loc_18000F84B
0x18000f7f2  mov     eax, [rsp+68h+arg_0]
0x18000f7f6  add     [rsi+1F8h], eax
0x18000f7fc  cmp     r15d, eax
0x18000f7ff  jnz     short loc_18000F846
0x18000f801  mov     rcx, [rsi+1E0h]
0x18000f808  lea     rdx, [rsp+68h+arg_0]
0x18000f80d  mov     r8, [rbx+30h]
0x18000f811  mov     r9d, r15d
0x18000f814  mov     [rsp+68h+arg_0], r12d
0x18000f819  mov     [rsp+68h+var_48], rdx
0x18000f81e  mov     rax, [rcx]
0x18000f821  mov     rdx, [rsi+1F8h]
0x18000f828  mov     rax, [rax+18h]
0x18000f82c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f831  mov     edi, eax
0x18000f833  test    eax, eax
0x18000f835  js      short loc_18000F84B
0x18000f837  mov     eax, [rsp+68h+arg_0]
0x18000f83b  add     [rsi+1F8h], eax
0x18000f841  cmp     r15d, eax
0x18000f844  jz      short loc_18000F84B
0x18000f846  mov     edi, 8003001Eh
0x18000f84b  mov     r15, [rsp+68h+var_38]
0x18000f850  and     dword ptr [rbx+0Ch], 0FFFFFFEFh
0x18000f854  lea     rcx, [rsi+260h]; lpCriticalSection
0x18000f85b  call    cs:__imp_LeaveCriticalSection
0x18000f861  mov     eax, edi
0x18000f863  add     rsp, 38h
0x18000f867  pop     r14
0x18000f869  pop     r12
0x18000f86b  pop     rdi
0x18000f86c  pop     rsi
0x18000f86d  pop     rbp
0x18000f86e  pop     rbx
0x18000f86f  retn
0x18000f870  mov     eax, [rbx+0Ch]
0x18000f873  test    al, 8
0x18000f875  jmp     loc_18000F5BC
0x18000f87a  mov     edi, 8007000Eh
0x18000f87f  jmp     short loc_18000F84B
0x18000f881  mov     r8, r12
0x18000f884  jmp     loc_18000F71B
0x18000f889  and     eax, 0FFFFFFFBh
0x18000f88c  mov     r9, r12
0x18000f88f  and     eax, 0FFFFFFF7h
0x18000f892  mov     [rbx+0Ch], eax
0x18000f895  jmp     loc_18000F5ED
0x18000f89a  test    r15d, r15d
0x18000f89d  jz      loc_18000F605
0x18000f8a3  test    byte ptr [rbx+0Ch], 8
0x18000f8a7  jz      loc_18000F605
0x18000f8ad  mov     ecx, [r9]
0x18000f8b0  lea     rax, [r9+4]
0x18000f8b4  mov     [rbx+10h], rax
0x18000f8b8  lea     rdx, ds:0[r15*4]
0x18000f8c0  mov     r8d, ecx
0x18000f8c3  mov     [rbx+4], ecx
0x18000f8c6  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x18000f8cd  lea     rax, [rcx+4]
0x18000f8d1  add     rax, r9
0x18000f8d4  lea     rcx, [rdx+4]
0x18000f8d8  mov     [rbx+20h], rax
0x18000f8dc  add     rcx, r8
0x18000f8df  add     rcx, r9
0x18000f8e2  lea     rax, [rdx+2]
0x18000f8e6  lea     rax, [r8+rax*2]
0x18000f8ea  mov     [rbx+28h], rcx
0x18000f8ee  add     rax, r9
0x18000f8f1  mov     [rbx+30h], rax
0x18000f8f5  jmp     loc_18000F84B
```
