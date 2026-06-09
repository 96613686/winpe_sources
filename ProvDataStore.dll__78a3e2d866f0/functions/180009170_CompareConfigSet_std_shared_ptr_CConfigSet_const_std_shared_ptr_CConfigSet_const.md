# CompareConfigSet(std::shared_ptr<CConfigSet const>,std::shared_ptr<CConfigSet const>)

- ea: `0x180009170`
- end: `0x18000934e`
- name: `?CompareConfigSet@@YAHV?$shared_ptr@$$CBVCConfigSet@@@std@@0@Z`
- size: `478`
- prototype: `_BOOL8 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009170`
- `0x180012010`

## pseudocode

```c
_BOOL8 __fastcall CompareConfigSet(_QWORD *a1, _QWORD *a2)
{
  _DWORD *v3; // rdx
  unsigned int v4; // r8d
  __int64 v5; // rax
  unsigned int v6; // r9d
  unsigned int v7; // r8d
  unsigned int v8; // r9d
  BOOL v9; // ebp
  volatile signed __int32 *v10; // rdi
  volatile signed __int32 *v11; // rdi
  volatile signed __int32 *v12; // rdi
  volatile signed __int32 *v13; // rdi
  volatile signed __int32 *v14; // rdi
  volatile signed __int32 *v15; // rdi

  v3 = (_DWORD *)*a2;
  v4 = v3[27];
  v5 = *a1;
  v6 = *(_DWORD *)(*a1 + 108LL);
  if ( v6 == v4 )
  {
    v7 = v3[28];
    v8 = *(_DWORD *)(v5 + 112);
    if ( v8 == v7 )
    {
      v9 = *(_DWORD *)(v5 + 116) > v3[29];
      v10 = (volatile signed __int32 *)a1[1];
      if ( v10 )
      {
        if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
          if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        }
      }
      v11 = (volatile signed __int32 *)a2[1];
      if ( v11 )
      {
        if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
          if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        }
      }
    }
    else
    {
      v9 = v8 < v7;
      v12 = (volatile signed __int32 *)a1[1];
      if ( v12 )
      {
        if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      v13 = (volatile signed __int32 *)a2[1];
      if ( v13 )
      {
        if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
    }
  }
  else
  {
    v9 = v6 < v4;
    v14 = (volatile signed __int32 *)a1[1];
    if ( v14 )
    {
      if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
    v15 = (volatile signed __int32 *)a2[1];
    if ( v15 )
    {
      if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180009170  push    rbx
0x180009172  push    rbp
0x180009173  push    rsi
0x180009174  push    rdi
0x180009175  sub     rsp, 28h
0x180009179  mov     rsi, rdx
0x18000917c  mov     rdx, [rdx]
0x18000917f  mov     r8d, [rdx+6Ch]
0x180009183  mov     rax, [rcx]
0x180009186  mov     r9d, [rax+6Ch]
0x18000918a  cmp     r9d, r8d
0x18000918d  jnz     loc_1800092BD
0x180009193  mov     r8d, [rdx+70h]
0x180009197  mov     r9d, [rax+70h]
0x18000919b  cmp     r9d, r8d
0x18000919e  jnz     loc_180009232
0x1800091a4  mov     eax, [rax+74h]
0x1800091a7  xor     ebp, ebp
0x1800091a9  cmp     eax, [rdx+74h]
0x1800091ac  setnbe  bpl
0x1800091b0  mov     rdi, [rcx+8]
0x1800091b4  or      ebx, 0FFFFFFFFh
0x1800091b7  test    rdi, rdi
0x1800091ba  jz      short loc_1800091F0
0x1800091bc  mov     eax, ebx
0x1800091be  lock xadd [rdi+8], eax
0x1800091c3  add     eax, ebx
0x1800091c5  jnz     short loc_1800091F0
0x1800091c7  mov     rax, [rdi]
0x1800091ca  mov     rcx, rdi
0x1800091cd  mov     rax, [rax]
0x1800091d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091d5  mov     eax, ebx
0x1800091d7  lock xadd [rdi+0Ch], eax
0x1800091dc  add     eax, ebx
0x1800091de  jnz     short loc_1800091F0
0x1800091e0  mov     rax, [rdi]
0x1800091e3  mov     rcx, rdi
0x1800091e6  mov     rax, [rax+8]
0x1800091ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091ef  nop
0x1800091f0  mov     rdi, [rsi+8]
0x1800091f4  test    rdi, rdi
0x1800091f7  jz      short loc_18000922D
0x1800091f9  mov     eax, ebx
0x1800091fb  lock xadd [rdi+8], eax
0x180009200  add     eax, ebx
0x180009202  jnz     short loc_18000922D
0x180009204  mov     rax, [rdi]
0x180009207  mov     rcx, rdi
0x18000920a  mov     rax, [rax]
0x18000920d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009212  mov     edx, ebx
0x180009214  lock xadd [rdi+0Ch], edx
0x180009219  add     edx, ebx
0x18000921b  jnz     short loc_18000922D
0x18000921d  mov     rdx, [rdi]
0x180009220  mov     rcx, rdi
0x180009223  mov     rax, [rdx+8]
0x180009227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000922c  nop
0x18000922d  jmp     loc_180009343
0x180009232  xor     ebp, ebp
0x180009234  cmp     r9d, r8d
0x180009237  setb    bpl
0x18000923b  mov     rdi, [rcx+8]
0x18000923f  or      ebx, 0FFFFFFFFh
0x180009242  test    rdi, rdi
0x180009245  jz      short loc_18000927B
0x180009247  mov     eax, ebx
0x180009249  lock xadd [rdi+8], eax
0x18000924e  add     eax, ebx
0x180009250  jnz     short loc_18000927B
0x180009252  mov     rax, [rdi]
0x180009255  mov     rcx, rdi
0x180009258  mov     rax, [rax]
0x18000925b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009260  mov     eax, ebx
0x180009262  lock xadd [rdi+0Ch], eax
0x180009267  add     eax, ebx
0x180009269  jnz     short loc_18000927B
0x18000926b  mov     rax, [rdi]
0x18000926e  mov     rcx, rdi
0x180009271  mov     rax, [rax+8]
0x180009275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000927a  nop
0x18000927b  mov     rdi, [rsi+8]
0x18000927f  test    rdi, rdi
0x180009282  jz      short loc_1800092B8
0x180009284  mov     eax, ebx
0x180009286  lock xadd [rdi+8], eax
0x18000928b  add     eax, ebx
0x18000928d  jnz     short loc_1800092B8
0x18000928f  mov     rax, [rdi]
0x180009292  mov     rcx, rdi
0x180009295  mov     rax, [rax]
0x180009298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000929d  mov     edx, ebx
0x18000929f  lock xadd [rdi+0Ch], edx
0x1800092a4  add     edx, ebx
0x1800092a6  jnz     short loc_1800092B8
0x1800092a8  mov     rdx, [rdi]
0x1800092ab  mov     rcx, rdi
0x1800092ae  mov     rax, [rdx+8]
0x1800092b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092b7  nop
0x1800092b8  jmp     loc_180009343
0x1800092bd  xor     ebp, ebp
0x1800092bf  cmp     r9d, r8d
0x1800092c2  setb    bpl
0x1800092c6  mov     rdi, [rcx+8]
0x1800092ca  or      ebx, 0FFFFFFFFh
0x1800092cd  test    rdi, rdi
0x1800092d0  jz      short loc_180009306
0x1800092d2  mov     eax, ebx
0x1800092d4  lock xadd [rdi+8], eax
0x1800092d9  add     eax, ebx
0x1800092db  jnz     short loc_180009306
0x1800092dd  mov     rax, [rdi]
0x1800092e0  mov     rcx, rdi
0x1800092e3  mov     rax, [rax]
0x1800092e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092eb  mov     eax, ebx
0x1800092ed  lock xadd [rdi+0Ch], eax
0x1800092f2  add     eax, ebx
0x1800092f4  jnz     short loc_180009306
0x1800092f6  mov     rax, [rdi]
0x1800092f9  mov     rcx, rdi
0x1800092fc  mov     rax, [rax+8]
0x180009300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009305  nop
0x180009306  mov     rdi, [rsi+8]
0x18000930a  test    rdi, rdi
0x18000930d  jz      short loc_180009343
0x18000930f  mov     eax, ebx
0x180009311  lock xadd [rdi+8], eax
0x180009316  add     eax, ebx
0x180009318  jnz     short loc_180009343
0x18000931a  mov     rax, [rdi]
0x18000931d  mov     rcx, rdi
0x180009320  mov     rax, [rax]
0x180009323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009328  mov     edx, ebx
0x18000932a  lock xadd [rdi+0Ch], edx
0x18000932f  add     edx, ebx
0x180009331  jnz     short loc_180009343
0x180009333  mov     rdx, [rdi]
0x180009336  mov     rcx, rdi
0x180009339  mov     rax, [rdx+8]
0x18000933d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009342  nop
0x180009343  mov     eax, ebp
0x180009345  add     rsp, 28h
0x180009349  pop     rdi
0x18000934a  pop     rsi
0x18000934b  pop     rbp
0x18000934c  pop     rbx
0x18000934d  retn
```
