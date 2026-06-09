# _CRT_INIT

- ea: `0x180007be0`
- end: `0x180007e05`
- name: `_CRT_INIT`
- size: `549`
- prototype: `int __fastcall(void *hDllHandle, unsigned int dwReason, void *lpreserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007e54`

## callees

- `0x180007be0`
- `0x180008174`
- `0x1800081d0`
- `0x180008343`
- `0x180020560`

## import_xrefs

- `msvcrt!free` at `0x180007cbf`
- `msvcrt!free` at `0x180007cbf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007c2b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007d1f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007c2b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007d1f`

## pseudocode

```c
__int64 __fastcall CRT_INIT(void *hDllHandle, unsigned int dwReason, void *lpreserved)
{
  int v5; // ebp
  void *StackBase; // rdi
  signed __int64 v7; // rax
  void (__fastcall **v8)(); // rsi
  void (**v9)(void); // rdi
  void (__fastcall **v10)(); // r15
  void (__fastcall **v11)(); // r14
  void (*v12)(void); // rax
  int v13; // esi
  void *v14; // rdi
  signed __int64 v15; // rax
  __int64 (**v16)(void); // rdi
  int v17; // eax

  if ( !dwReason )
  {
    if ( _proc_attached > 0 )
    {
      --_proc_attached;
      v5 = 0;
      StackBase = NtCurrentTeb()->NtTib.StackBase;
      while ( 1 )
      {
        v7 = _InterlockedCompareExchange64(
               (volatile signed __int64 *)&_native_startup_lock,
               (signed __int64)StackBase,
               0);
        if ( !v7 )
          break;
        if ( (void *)v7 == StackBase )
        {
          v5 = 1;
          break;
        }
        Sleep(0x3E8u);
      }
      if ( _native_startup_state == __initialized )
      {
        v8 = _onexitbegin;
        if ( _onexitbegin )
        {
          v9 = _onexitend;
          v10 = _onexitbegin;
          v11 = _onexitend;
          while ( --v9 >= v8 )
          {
            v12 = *v9;
            if ( *v9 )
            {
              *v9 = 0;
              v12();
              if ( v10 != _onexitbegin || v11 != _onexitend )
              {
                v10 = _onexitbegin;
                v8 = _onexitbegin;
                v11 = _onexitend;
                v9 = _onexitend;
              }
            }
          }
          free(v8);
          _onexitend = 0;
          _onexitbegin = 0;
        }
        _native_startup_state = __uninitialized;
        if ( !v5 )
          _InterlockedExchange64((volatile __int64 *)&_native_startup_lock, 0);
      }
      else
      {
        amsg_exit_0(31);
      }
      return 1;
    }
    return 0;
  }
  if ( dwReason == 1 )
  {
    v13 = 0;
    v14 = NtCurrentTeb()->NtTib.StackBase;
    while ( 1 )
    {
      v15 = _InterlockedCompareExchange64((volatile signed __int64 *)&_native_startup_lock, (signed __int64)v14, 0);
      if ( !v15 )
        break;
      if ( (void *)v15 == v14 )
      {
        v13 = 1;
        break;
      }
      Sleep(0x3E8u);
    }
    if ( _native_startup_state )
    {
      amsg_exit_0(31);
    }
    else
    {
      v16 = (__int64 (**)(void))_xi_a;
      _native_startup_state = __initializing;
      v17 = 0;
      if ( _xi_a < _xi_z )
      {
        while ( !v17 )
        {
          if ( *v16 )
            v17 = (*v16)();
          if ( ++v16 >= (__int64 (**)(void))_xi_z )
          {
            if ( !v17 )
              goto LABEL_37;
            return 0;
          }
        }
        return 0;
      }
LABEL_37:
      initterm_0(_xc_a, _xc_z);
      _native_startup_state = __initialized;
    }
    if ( !v13 )
      _InterlockedExchange64((volatile __int64 *)&_native_startup_lock, 0);
    if ( _dyn_tls_init_callback && IsNonwritableInCurrentImage((unsigned __int8 *)&_dyn_tls_init_callback) )
      _dyn_tls_init_callback(hDllHandle, 2u, lpreserved);
    ++_proc_attached;
  }
  return 1;
}

```

## disassembly

```asm
0x180007be0  push    rbp
0x180007be2  push    rsi
0x180007be3  push    rdi
0x180007be4  push    r14
0x180007be6  push    r15
0x180007be8  sub     rsp, 20h
0x180007bec  mov     rbp, lpreserved
0x180007bef  mov     r14, hDllHandle
0x180007bf2  test    dwReason, dwReason
0x180007bf4  jnz     loc_180007CFB
0x180007bfa  mov     eax, cs:__proc_attached
0x180007c00  test    eax, eax
0x180007c02  jle     loc_180007D8E
0x180007c08  dec     eax
0x180007c0a  mov     cs:__proc_attached, eax
0x180007c10  xor     ebp, ebp
0x180007c12  mov     rax, gs:30h
0x180007c1b  mov     rdi, [rax+8]
0x180007c1f  jmp     short loc_180007C31
0x180007c21  cmp     rax, rdi
0x180007c24  jz      short loc_180007C40
0x180007c26  mov     ecx, 3E8h; dwMilliseconds
0x180007c2b  call    cs:__imp_Sleep
0x180007c31  xor     eax, eax
0x180007c33  lock cmpxchg cs:__native_startup_lock, rdi
0x180007c3c  jnz     short loc_180007C21
0x180007c3e  jmp     short loc_180007C45
0x180007c40  mov     ebp, 1
0x180007c45  mov     eax, cs:__native_startup_state
0x180007c4b  cmp     eax, 2
0x180007c4e  jz      short loc_180007C5F
0x180007c50  mov     ecx, 1Fh
0x180007c55  call    _amsg_exit_0
0x180007c5a  jmp     loc_180007DF4
0x180007c5f  mov     rsi, cs:__onexitbegin
0x180007c66  test    rsi, rsi
0x180007c69  jz      short loc_180007CDB
0x180007c6b  mov     rdi, cs:__onexitend
0x180007c72  mov     r15, rsi
0x180007c75  mov     r14, rdi
0x180007c78  sub     rdi, 8
0x180007c7c  cmp     rdi, rsi
0x180007c7f  jb      short loc_180007CBC
0x180007c81  mov     rax, [rdi]
0x180007c84  test    rax, rax
0x180007c87  jz      short loc_180007C78
0x180007c89  mov     qword ptr [rdi], 0
0x180007c90  call    cs:__guard_dispatch_icall_fptr
0x180007c96  mov     hDllHandle, cs:__onexitbegin
0x180007c9d  mov     rax, cs:__onexitend
0x180007ca4  cmp     r15, hDllHandle
0x180007ca7  jnz     short loc_180007CAE
0x180007ca9  cmp     r14, rax
0x180007cac  jz      short loc_180007C78
0x180007cae  mov     r15, hDllHandle
0x180007cb1  mov     rsi, hDllHandle
0x180007cb4  mov     r14, rax
0x180007cb7  mov     rdi, rax
0x180007cba  jmp     short loc_180007C78
0x180007cbc  mov     hDllHandle, rsi; Block
0x180007cbf  call    cs:__imp_free
0x180007cc5  mov     cs:__onexitend, 0
0x180007cd0  mov     cs:__onexitbegin, 0
0x180007cdb  mov     cs:__native_startup_state, 0
0x180007ce5  test    ebp, ebp
0x180007ce7  jnz     loc_180007DF4
0x180007ced  xor     eax, eax
0x180007cef  xchg    rax, cs:__native_startup_lock
0x180007cf6  jmp     loc_180007DF4
0x180007cfb  cmp     dwReason, 1
0x180007cfe  jnz     loc_180007DF4
0x180007d04  mov     rax, gs:30h
0x180007d0d  xor     esi, esi
0x180007d0f  mov     rdi, [rax+8]
0x180007d13  jmp     short loc_180007D25
0x180007d15  cmp     rax, rdi
0x180007d18  jz      short loc_180007D34
0x180007d1a  mov     ecx, 3E8h; dwMilliseconds
0x180007d1f  call    cs:__imp_Sleep
0x180007d25  xor     eax, eax
0x180007d27  lock cmpxchg cs:__native_startup_lock, rdi
0x180007d30  jnz     short loc_180007D15
0x180007d32  jmp     short loc_180007D39
0x180007d34  mov     esi, 1
0x180007d39  mov     eax, cs:__native_startup_state
0x180007d3f  test    eax, eax
0x180007d41  jz      short loc_180007D4F
0x180007d43  mov     ecx, 1Fh
0x180007d48  call    _amsg_exit_0
0x180007d4d  jmp     short loc_180007DAF
0x180007d4f  lea     rdi, __xi_a
0x180007d56  mov     cs:__native_startup_state, 1
0x180007d60  xor     eax, eax
0x180007d62  lea     r15, __xi_z
0x180007d69  cmp     rdi, r15
0x180007d6c  jnb     short loc_180007D92
0x180007d6e  test    eax, eax
0x180007d70  jnz     short loc_180007D8E
0x180007d72  cmp     qword ptr [rdi], 0
0x180007d76  jz      short loc_180007D81
0x180007d78  mov     rax, [rdi]
0x180007d7b  call    cs:__guard_dispatch_icall_fptr
0x180007d81  add     rdi, 8
0x180007d85  cmp     rdi, r15
0x180007d88  jb      short loc_180007D6E
0x180007d8a  test    eax, eax
0x180007d8c  jz      short loc_180007D92
0x180007d8e  xor     eax, eax
0x180007d90  jmp     short loc_180007DF9
0x180007d92  lea     rdx, __xc_z; Last
0x180007d99  lea     hDllHandle, __xc_a; First
0x180007da0  call    _initterm_0
0x180007da5  mov     cs:__native_startup_state, 2
0x180007daf  test    esi, esi
0x180007db1  jnz     short loc_180007DBC
0x180007db3  xor     eax, eax
0x180007db5  xchg    rax, cs:__native_startup_lock
0x180007dbc  cmp     cs:__dyn_tls_init_callback, 0
0x180007dc4  jz      short loc_180007DEE
0x180007dc6  lea     hDllHandle, __dyn_tls_init_callback; pTarget
0x180007dcd  call    _IsNonwritableInCurrentImage
0x180007dd2  test    eax, eax
0x180007dd4  jz      short loc_180007DEE
0x180007dd6  mov     rax, cs:__dyn_tls_init_callback
0x180007ddd  mov     lpreserved, rbp
0x180007de0  mov     dwReason, 2
0x180007de5  mov     hDllHandle, r14
0x180007de8  call    cs:__guard_dispatch_icall_fptr
0x180007dee  inc     cs:__proc_attached
0x180007df4  mov     eax, 1
0x180007df9  add     rsp, 20h
0x180007dfd  pop     r15
0x180007dff  pop     r14
0x180007e01  pop     rdi
0x180007e02  pop     rsi
0x180007e03  pop     rbp
0x180007e04  retn
```
