# CASFUnknownContainer::WriteObjects(ulong,uchar *,ulong *)

- ea: `0x18001f440`
- end: `0x18001f5be`
- name: `?WriteObjects@CASFUnknownContainer@@UEAAJKPEAEPEAK@Z`
- size: `382`
- prototype: `__int64 __fastcall(CASFUnknownContainer *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800015d0`
- `0x18001df5c`
- `0x18001f440`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFUnknownContainer::WriteObjects(
        CASFUnknownContainer *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r14
  __int64 v8; // rax
  __int64 result; // rax
  int v10; // ecx
  unsigned int v11; // eax
  unsigned int v12; // ebp
  unsigned int v13; // ebx
  unsigned __int8 *v14; // r15
  __int64 v15; // rax
  __int64 v16; // rdi
  unsigned int v17; // [rsp+30h] [rbp-88h]
  unsigned __int64 v18; // [rsp+38h] [rbp-80h] BYREF
  int v19; // [rsp+40h] [rbp-78h] BYREF
  unsigned __int64 v20; // [rsp+48h] [rbp-70h] BYREF
  __int128 v21; // [rsp+50h] [rbp-68h] BYREF

  v4 = a2;
  if ( !a4 || a2 && !a3 )
    return 2147942487LL;
  v8 = *(_QWORD *)this;
  v20 = 0;
  result = (*(__int64 (__fastcall **)(CASFUnknownContainer *, unsigned __int64 *))(v8 + 88))(this, &v20);
  v10 = result;
  if ( (int)result >= 0 )
  {
    if ( v4 >= v20 )
    {
      v11 = *((_DWORD *)this + 58);
      v12 = 0;
      v13 = 0;
      v17 = v11;
      v14 = a3;
      while ( v13 < v11 )
      {
        v15 = CTDynArray<IASFUnknown *,20>::operator[]((char *)this + 16, v13);
        v16 = v15;
        if ( !v15 )
        {
          v10 = -2147418113;
          break;
        }
        v21 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v15 + 24LL))(v15, &v21);
        if ( v10 < 0 )
          break;
        v18 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64 *))(*(_QWORD *)v16 + 56LL))(v16, 0, &v18);
        if ( v10 < 0 )
          break;
        if ( v18 >= 0x100000000LL )
          return 3222079475LL;
        v19 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int8 *, int *))(*(_QWORD *)v16 + 72LL))(
                v16,
                (unsigned int)(v4 + (_DWORD)a3 - (_DWORD)v14),
                v14,
                &v19);
        if ( v10 < 0 )
          break;
        v12 += v18;
        v14 += (unsigned int)v18;
        v11 = v17;
        ++v13;
      }
      *a4 = v12;
      return (unsigned int)v10;
    }
    else
    {
      return 3222079441LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001f440  push    rbx
0x18001f442  push    rbp
0x18001f443  push    rsi
0x18001f444  push    rdi
0x18001f445  push    r12
0x18001f447  push    r13
0x18001f449  push    r14
0x18001f44b  push    r15
0x18001f44d  sub     rsp, 78h
0x18001f451  mov     rax, cs:__security_cookie
0x18001f458  xor     rax, rsp
0x18001f45b  mov     [rsp+0B8h+var_58], rax
0x18001f460  mov     r14d, edx
0x18001f463  mov     r13, r9
0x18001f466  mov     r12, r8
0x18001f469  mov     rsi, rcx
0x18001f46c  test    r9, r9
0x18001f46f  jz      loc_18001F59B
0x18001f475  test    edx, edx
0x18001f477  jz      short loc_18001F482
0x18001f479  test    r8, r8
0x18001f47c  jz      loc_18001F59B
0x18001f482  mov     rax, [rcx]
0x18001f485  lea     rdx, [rsp+0B8h+var_70]
0x18001f48a  mov     [rsp+0B8h+var_70], 0
0x18001f493  mov     rax, [rax+58h]
0x18001f497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f49c  mov     ecx, eax
0x18001f49e  test    eax, eax
0x18001f4a0  js      loc_18001F5A0
0x18001f4a6  cmp     r14, [rsp+0B8h+var_70]
0x18001f4ab  jnb     short loc_18001F4B7
0x18001f4ad  mov     eax, 0C00D07D1h
0x18001f4b2  jmp     loc_18001F5A0
0x18001f4b7  mov     eax, [rsi+0E8h]
0x18001f4bd  xor     ebp, ebp
0x18001f4bf  xor     ebx, ebx
0x18001f4c1  mov     [rsp+0B8h+var_88], eax
0x18001f4c5  mov     r15, r12
0x18001f4c8  cmp     ebx, eax
0x18001f4ca  jnb     loc_18001F593
0x18001f4d0  lea     rcx, [rsi+10h]
0x18001f4d4  mov     edx, ebx
0x18001f4d6  call    ??A?$CTDynArray@PEAUIASFUnknown@@$0BE@@@QEBAPEAUIASFUnknown@@K@Z; CTDynArray<IASFUnknown *,20>::operator[](ulong)
0x18001f4db  mov     rdi, rax
0x18001f4de  test    rax, rax
0x18001f4e1  jz      loc_18001F58E
0x18001f4e7  xorps   xmm0, xmm0
0x18001f4ea  lea     rdx, [rsp+0B8h+var_68]
0x18001f4ef  movups  [rsp+0B8h+var_68], xmm0
0x18001f4f4  mov     rcx, [rax]
0x18001f4f7  mov     rax, [rcx+18h]
0x18001f4fb  mov     rcx, rdi
0x18001f4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f503  mov     ecx, eax
0x18001f505  test    eax, eax
0x18001f507  js      loc_18001F593
0x18001f50d  mov     [rsp+0B8h+var_80], 0
0x18001f516  lea     r8, [rsp+0B8h+var_80]
0x18001f51b  mov     rax, [rdi]
0x18001f51e  xor     edx, edx
0x18001f520  mov     rcx, rdi
0x18001f523  mov     rax, [rax+38h]
0x18001f527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f52c  mov     ecx, eax
0x18001f52e  test    eax, eax
0x18001f530  js      short loc_18001F593
0x18001f532  mov     rax, 100000000h
0x18001f53c  cmp     [rsp+0B8h+var_80], rax
0x18001f541  jnb     short loc_18001F587
0x18001f543  mov     [rsp+0B8h+var_78], 0
0x18001f54b  lea     r9, [rsp+0B8h+var_78]
0x18001f550  mov     rax, [rdi]
0x18001f553  mov     edx, r12d
0x18001f556  sub     edx, r15d
0x18001f559  mov     r8, r15
0x18001f55c  add     edx, r14d
0x18001f55f  mov     rcx, rdi
0x18001f562  mov     rax, [rax+48h]
0x18001f566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f56b  mov     ecx, eax
0x18001f56d  test    eax, eax
0x18001f56f  js      short loc_18001F593
0x18001f571  mov     eax, dword ptr [rsp+0B8h+var_80]
0x18001f575  add     ebp, dword ptr [rsp+0B8h+var_80]
0x18001f579  add     r15, rax
0x18001f57c  mov     eax, [rsp+0B8h+var_88]
0x18001f580  inc     ebx
0x18001f582  jmp     loc_18001F4C8
0x18001f587  mov     eax, 0C00D07F3h
0x18001f58c  jmp     short loc_18001F5A0
0x18001f58e  mov     ecx, 8000FFFFh
0x18001f593  mov     [r13+0], ebp
0x18001f597  mov     eax, ecx
0x18001f599  jmp     short loc_18001F5A0
0x18001f59b  mov     eax, 80070057h
0x18001f5a0  mov     rcx, [rsp+0B8h+var_58]
0x18001f5a5  xor     rcx, rsp; StackCookie
0x18001f5a8  call    __security_check_cookie
0x18001f5ad  add     rsp, 78h
0x18001f5b1  pop     r15
0x18001f5b3  pop     r14
0x18001f5b5  pop     r13
0x18001f5b7  pop     r12
0x18001f5b9  pop     rdi
0x18001f5ba  pop     rsi
0x18001f5bb  pop     rbp
0x18001f5bc  pop     rbx
0x18001f5bd  retn
```
