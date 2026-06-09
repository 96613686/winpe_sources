# _CRT_INIT

- ea: `0x180001af0`
- end: `0x180001d15`
- name: `_CRT_INIT`
- size: `549`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001d64`

## callees

- `0x180001af0`
- `0x180002061`
- `0x1800020c0`
- `0x180002227`
- `0x180007cd0`

## import_xrefs

- `msvcrt!free` at `0x180001bcf`
- `msvcrt!free` at `0x180001bcf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180001b3b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180001c2f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180001b3b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180001c2f`

## pseudocode

```c
__int64 __fastcall CRT_INIT(__int64 a1, int a2, __int64 a3)
{
  int v5; // ebp
  PVOID StackBase; // rdi
  signed __int64 v7; // rax
  void (**v8)(void); // rsi
  void (**v9)(void); // rdi
  void *v10; // r15
  __int64 v11; // r14
  void (*v12)(void); // rax
  int v13; // esi
  PVOID v14; // rdi
  signed __int64 v15; // rax
  __int64 (**v16)(void); // rdi
  int v17; // eax

  if ( !a2 )
  {
    if ( dword_18000D180 > 0 )
    {
      --dword_18000D180;
      v5 = 0;
      StackBase = NtCurrentTeb()->NtTib.StackBase;
      while ( 1 )
      {
        v7 = _InterlockedCompareExchange64(&_native_startup_lock, (signed __int64)StackBase, 0);
        if ( !v7 )
          break;
        if ( (PVOID)v7 == StackBase )
        {
          v5 = 1;
          break;
        }
        Sleep(0x3E8u);
      }
      if ( _native_startup_state == 2 )
      {
        v8 = (void (**)(void))_onexitbegin;
        if ( _onexitbegin )
        {
          v9 = (void (**)(void))_onexitend;
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
                v8 = (void (**)(void))_onexitbegin;
                v11 = _onexitend;
                v9 = (void (**)(void))_onexitend;
              }
            }
          }
          free(v8);
          _onexitend = 0;
          _onexitbegin = 0;
        }
        _native_startup_state = 0;
        if ( !v5 )
          _InterlockedExchange64(&_native_startup_lock, 0);
      }
      else
      {
        amsg_exit_0(31);
      }
      return 1;
    }
    return 0;
  }
  if ( a2 == 1 )
  {
    v13 = 0;
    v14 = NtCurrentTeb()->NtTib.StackBase;
    while ( 1 )
    {
      v15 = _InterlockedCompareExchange64(&_native_startup_lock, (signed __int64)v14, 0);
      if ( !v15 )
        break;
      if ( (PVOID)v15 == v14 )
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
      v16 = (__int64 (**)(void))&_xi_a;
      _native_startup_state = 1;
      v17 = 0;
      if ( &_xi_a < &_xi_z )
      {
        while ( !v17 )
        {
          if ( *v16 )
            v17 = (*v16)();
          if ( ++v16 >= (__int64 (**)(void))&_xi_z )
          {
            if ( !v17 )
              goto LABEL_37;
            return 0;
          }
        }
        return 0;
      }
LABEL_37:
      initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
      _native_startup_state = 2;
    }
    if ( !v13 )
      _InterlockedExchange64(&_native_startup_lock, 0);
    if ( _dyn_tls_init_callback && (unsigned int)IsNonwritableInCurrentImage(&_dyn_tls_init_callback) )
      ((void (__fastcall *)(__int64, __int64, __int64))_dyn_tls_init_callback)(a1, 2, a3);
    ++dword_18000D180;
  }
  return 1;
}

```

## disassembly

```asm
0x180001af0  push    rbp
0x180001af2  push    rsi
0x180001af3  push    rdi
0x180001af4  push    r14
0x180001af6  push    r15
0x180001af8  sub     rsp, 20h
0x180001afc  mov     rbp, r8
0x180001aff  mov     r14, rcx
0x180001b02  test    edx, edx
0x180001b04  jnz     loc_180001C0B
0x180001b0a  mov     eax, cs:dword_18000D180
0x180001b10  test    eax, eax
0x180001b12  jle     loc_180001C9E
0x180001b18  dec     eax
0x180001b1a  mov     cs:dword_18000D180, eax
0x180001b20  xor     ebp, ebp
0x180001b22  mov     rax, gs:30h
0x180001b2b  mov     rdi, [rax+8]
0x180001b2f  jmp     short loc_180001B41
0x180001b31  cmp     rax, rdi
0x180001b34  jz      short loc_180001B50
0x180001b36  mov     ecx, 3E8h; dwMilliseconds
0x180001b3b  call    cs:__imp_Sleep
0x180001b41  xor     eax, eax
0x180001b43  lock cmpxchg cs:__native_startup_lock, rdi
0x180001b4c  jnz     short loc_180001B31
0x180001b4e  jmp     short loc_180001B55
0x180001b50  mov     ebp, 1
0x180001b55  mov     eax, cs:__native_startup_state
0x180001b5b  cmp     eax, 2
0x180001b5e  jz      short loc_180001B6F
0x180001b60  mov     ecx, 1Fh
0x180001b65  call    _amsg_exit_0
0x180001b6a  jmp     loc_180001D04
0x180001b6f  mov     rsi, cs:__onexitbegin
0x180001b76  test    rsi, rsi
0x180001b79  jz      short loc_180001BEB
0x180001b7b  mov     rdi, cs:__onexitend
0x180001b82  mov     r15, rsi
0x180001b85  mov     r14, rdi
0x180001b88  sub     rdi, 8
0x180001b8c  cmp     rdi, rsi
0x180001b8f  jb      short loc_180001BCC
0x180001b91  mov     rax, [rdi]
0x180001b94  test    rax, rax
0x180001b97  jz      short loc_180001B88
0x180001b99  mov     qword ptr [rdi], 0
0x180001ba0  call    cs:__guard_dispatch_icall_fptr
0x180001ba6  mov     rcx, cs:__onexitbegin
0x180001bad  mov     rax, cs:__onexitend
0x180001bb4  cmp     r15, rcx
0x180001bb7  jnz     short loc_180001BBE
0x180001bb9  cmp     r14, rax
0x180001bbc  jz      short loc_180001B88
0x180001bbe  mov     r15, rcx
0x180001bc1  mov     rsi, rcx
0x180001bc4  mov     r14, rax
0x180001bc7  mov     rdi, rax
0x180001bca  jmp     short loc_180001B88
0x180001bcc  mov     rcx, rsi; Block
0x180001bcf  call    cs:__imp_free
0x180001bd5  mov     cs:__onexitend, 0
0x180001be0  mov     cs:__onexitbegin, 0
0x180001beb  mov     cs:__native_startup_state, 0
0x180001bf5  test    ebp, ebp
0x180001bf7  jnz     loc_180001D04
0x180001bfd  xor     eax, eax
0x180001bff  xchg    rax, cs:__native_startup_lock
0x180001c06  jmp     loc_180001D04
0x180001c0b  cmp     edx, 1
0x180001c0e  jnz     loc_180001D04
0x180001c14  mov     rax, gs:30h
0x180001c1d  xor     esi, esi
0x180001c1f  mov     rdi, [rax+8]
0x180001c23  jmp     short loc_180001C35
0x180001c25  cmp     rax, rdi
0x180001c28  jz      short loc_180001C44
0x180001c2a  mov     ecx, 3E8h; dwMilliseconds
0x180001c2f  call    cs:__imp_Sleep
0x180001c35  xor     eax, eax
0x180001c37  lock cmpxchg cs:__native_startup_lock, rdi
0x180001c40  jnz     short loc_180001C25
0x180001c42  jmp     short loc_180001C49
0x180001c44  mov     esi, 1
0x180001c49  mov     eax, cs:__native_startup_state
0x180001c4f  test    eax, eax
0x180001c51  jz      short loc_180001C5F
0x180001c53  mov     ecx, 1Fh
0x180001c58  call    _amsg_exit_0
0x180001c5d  jmp     short loc_180001CBF
0x180001c5f  lea     rdi, __xi_a
0x180001c66  mov     cs:__native_startup_state, 1
0x180001c70  xor     eax, eax
0x180001c72  lea     r15, __xi_z
0x180001c79  cmp     rdi, r15
0x180001c7c  jnb     short loc_180001CA2
0x180001c7e  test    eax, eax
0x180001c80  jnz     short loc_180001C9E
0x180001c82  cmp     qword ptr [rdi], 0
0x180001c86  jz      short loc_180001C91
0x180001c88  mov     rax, [rdi]
0x180001c8b  call    cs:__guard_dispatch_icall_fptr
0x180001c91  add     rdi, 8
0x180001c95  cmp     rdi, r15
0x180001c98  jb      short loc_180001C7E
0x180001c9a  test    eax, eax
0x180001c9c  jz      short loc_180001CA2
0x180001c9e  xor     eax, eax
0x180001ca0  jmp     short loc_180001D09
0x180001ca2  lea     rdx, __xc_z; Last
0x180001ca9  lea     rcx, __xc_a; First
0x180001cb0  call    _initterm_0
0x180001cb5  mov     cs:__native_startup_state, 2
0x180001cbf  test    esi, esi
0x180001cc1  jnz     short loc_180001CCC
0x180001cc3  xor     eax, eax
0x180001cc5  xchg    rax, cs:__native_startup_lock
0x180001ccc  cmp     cs:__dyn_tls_init_callback, 0
0x180001cd4  jz      short loc_180001CFE
0x180001cd6  lea     rcx, __dyn_tls_init_callback
0x180001cdd  call    _IsNonwritableInCurrentImage
0x180001ce2  test    eax, eax
0x180001ce4  jz      short loc_180001CFE
0x180001ce6  mov     rax, cs:__dyn_tls_init_callback
0x180001ced  mov     r8, rbp
0x180001cf0  mov     edx, 2
0x180001cf5  mov     rcx, r14
0x180001cf8  call    cs:__guard_dispatch_icall_fptr
0x180001cfe  inc     cs:dword_18000D180
0x180001d04  mov     eax, 1
0x180001d09  add     rsp, 20h
0x180001d0d  pop     r15
0x180001d0f  pop     r14
0x180001d11  pop     rdi
0x180001d12  pop     rsi
0x180001d13  pop     rbp
0x180001d14  retn
```
