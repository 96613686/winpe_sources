# _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)

- ea: `0x180006e1c`
- end: `0x180006fbd`
- name: `?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z`
- size: `417`
- prototype: `void __fastcall(const struct _EVENT_DESCRIPTOR *, struct _GUID *, unsigned int, unsigned int)`
- caller_count: `10`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003040`
- `0x1800036c4`
- `0x18000387c`
- `0x180003aec`
- `0x180003cd0`
- `0x180004500`
- `0x180004f94`
- `0x180006290`
- `0x180006610`
- `0x180006670`

## callees

- `0x180001480`
- `0x180006e1c`
- `0x180006fc4`
- `0x180008010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180006eb0`
- `KERNEL32!GetProcAddress` at `0x180006f69`
- `KERNEL32!GetProcAddress` at `0x180006eb0`
- `KERNEL32!GetProcAddress` at `0x180006f69`
- `KERNEL32!FreeLibrary` at `0x180006e9c`
- `KERNEL32!FreeLibrary` at `0x180006f55`
- `KERNEL32!FreeLibrary` at `0x180006e9c`
- `KERNEL32!FreeLibrary` at `0x180006f55`

## string_xrefs

- `0x180006f62`: `WinSqmEventWrite`

## pseudocode

```c
void __fastcall _WinSqmDWORDEvent(const struct _EVENT_DESCRIPTOR *a1, struct _GUID *a2, int a3, int a4)
{
  unsigned int (__fastcall *v5)(const struct _EVENT_DESCRIPTOR *, _QWORD); // rax
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  void (__fastcall *v8)(const struct _EVENT_DESCRIPTOR *, __int64, GUID **); // rax
  HMODULE v9; // rax
  FARPROC v10; // rax
  GUID *v11; // [rsp+20h] [rbp-40h] BYREF
  __int128 v12; // [rsp+28h] [rbp-38h]
  __int128 v13; // [rsp+38h] [rbp-28h]
  __int64 v14; // [rsp+48h] [rbp-18h]
  int v15; // [rsp+80h] [rbp+20h] BYREF
  int v16; // [rsp+88h] [rbp+28h] BYREF

  v16 = a4;
  v15 = a3;
  v11 = 0;
  v14 = 0;
  v12 = 0;
  v13 = 0;
  if ( dword_18000D1C0 )
  {
    v5 = (unsigned int (__fastcall *)(const struct _EVENT_DESCRIPTOR *, _QWORD))qword_18000D2D8;
    if ( !qword_18000D2D8 )
    {
      if ( !hModule )
      {
        LibraryW = IsolationAwareLoadLibraryW();
        if ( !LibraryW )
          goto LABEL_17;
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hModule, (signed __int64)LibraryW, 0) )
          FreeLibrary(LibraryW);
      }
      ProcAddress = GetProcAddress(hModule, "WinSqmEventEnabled");
      if ( !ProcAddress )
        goto LABEL_17;
      _InterlockedCompareExchange64(&qword_18000D2D8, (signed __int64)ProcAddress, 0);
      v5 = (unsigned int (__fastcall *)(const struct _EVENT_DESCRIPTOR *, _QWORD))qword_18000D2D8;
    }
    if ( v5(a1, 0) )
    {
      v11 = &g_WinSqmGlobalSession;
      *((_QWORD *)&v12 + 1) = &v15;
      *((_QWORD *)&v13 + 1) = &v16;
      *(_QWORD *)&v12 = 16;
      *(_QWORD *)&v13 = 4;
      v14 = 4;
      if ( dword_18000D1C0 )
      {
        v8 = (void (__fastcall *)(const struct _EVENT_DESCRIPTOR *, __int64, GUID **))qword_18000D2D0;
        if ( qword_18000D2D0 )
        {
LABEL_19:
          v8(a1, 3, &v11);
          return;
        }
        if ( hModule )
        {
LABEL_16:
          v10 = GetProcAddress(hModule, "WinSqmEventWrite");
          if ( !v10 )
            goto LABEL_17;
          _InterlockedCompareExchange64(&qword_18000D2D0, (signed __int64)v10, 0);
          v8 = (void (__fastcall *)(const struct _EVENT_DESCRIPTOR *, __int64, GUID **))qword_18000D2D0;
          goto LABEL_19;
        }
        v9 = IsolationAwareLoadLibraryW();
        if ( v9 )
        {
          if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hModule, (signed __int64)v9, 0) )
            FreeLibrary(v9);
          goto LABEL_16;
        }
LABEL_17:
        dword_18000D1C0 = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x180006e1c  mov     [rsp-8+arg_8], rbx
0x180006e21  mov     [rsp-8+arg_18], r9d
0x180006e26  mov     [rsp-8+arg_10], r8d
0x180006e2b  push    rbp
0x180006e2c  mov     rbp, rsp
0x180006e2f  sub     rsp, 60h
0x180006e33  mov     rax, cs:__security_cookie
0x180006e3a  xor     rax, rsp
0x180006e3d  mov     [rbp+var_10], rax
0x180006e41  xor     eax, eax
0x180006e43  mov     [rbp+var_40], 0
0x180006e4b  cmp     cs:dword_18000D1C0, eax
0x180006e51  xorps   xmm0, xmm0
0x180006e54  mov     rbx, rcx
0x180006e57  mov     [rbp+var_18], rax
0x180006e5b  movups  [rbp+var_38], xmm0
0x180006e5f  movups  [rbp+var_28], xmm0
0x180006e63  jz      loc_180006FA6
0x180006e69  mov     rax, cs:qword_18000D2D8
0x180006e70  test    rax, rax
0x180006e73  jnz     short loc_180006ED4
0x180006e75  cmp     cs:hModule, rax
0x180006e7c  jnz     short loc_180006EA2
0x180006e7e  call    IsolationAwareLoadLibraryW
0x180006e83  mov     rcx, rax; hLibModule
0x180006e86  test    rax, rax
0x180006e89  jz      loc_180006F77
0x180006e8f  xor     eax, eax
0x180006e91  lock cmpxchg cs:hModule, rcx
0x180006e9a  jz      short loc_180006EA2
0x180006e9c  call    cs:__imp_FreeLibrary
0x180006ea2  mov     rcx, cs:hModule; hModule
0x180006ea9  lea     rdx, aWinsqmeventena; "WinSqmEventEnabled"
0x180006eb0  call    cs:__imp_GetProcAddress
0x180006eb6  mov     rcx, rax
0x180006eb9  test    rax, rax
0x180006ebc  jz      loc_180006F77
0x180006ec2  xor     eax, eax
0x180006ec4  lock cmpxchg cs:qword_18000D2D8, rcx
0x180006ecd  mov     rax, cs:qword_18000D2D8
0x180006ed4  xor     edx, edx
0x180006ed6  mov     rcx, rbx
0x180006ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ede  test    eax, eax
0x180006ee0  jz      loc_180006FA6
0x180006ee6  cmp     cs:dword_18000D1C0, 0
0x180006eed  lea     rax, ?g_WinSqmGlobalSession@@3U_GUID@@B; _GUID const g_WinSqmGlobalSession
0x180006ef4  mov     [rbp+var_40], rax
0x180006ef8  lea     rax, [rbp+arg_10]
0x180006efc  mov     qword ptr [rbp+var_38+8], rax
0x180006f00  lea     rax, [rbp+arg_18]
0x180006f04  mov     qword ptr [rbp+var_28+8], rax
0x180006f08  mov     qword ptr [rbp+var_38], 10h
0x180006f10  mov     qword ptr [rbp+var_28], 4
0x180006f18  mov     [rbp+var_18], 4
0x180006f20  jz      loc_180006FA6
0x180006f26  mov     rax, cs:qword_18000D2D0
0x180006f2d  test    rax, rax
0x180006f30  jnz     short loc_180006F95
0x180006f32  cmp     cs:hModule, rax
0x180006f39  jnz     short loc_180006F5B
0x180006f3b  call    IsolationAwareLoadLibraryW
0x180006f40  mov     rcx, rax; hLibModule
0x180006f43  test    rax, rax
0x180006f46  jz      short loc_180006F77
0x180006f48  xor     eax, eax
0x180006f4a  lock cmpxchg cs:hModule, rcx
0x180006f53  jz      short loc_180006F5B
0x180006f55  call    cs:__imp_FreeLibrary
0x180006f5b  mov     rcx, cs:hModule; hModule
0x180006f62  lea     rdx, aWinsqmeventwri; "WinSqmEventWrite"
0x180006f69  call    cs:__imp_GetProcAddress
0x180006f6f  mov     rcx, rax
0x180006f72  test    rax, rax
0x180006f75  jnz     short loc_180006F83
0x180006f77  mov     cs:dword_18000D1C0, 0
0x180006f81  jmp     short loc_180006FA6
0x180006f83  xor     eax, eax
0x180006f85  lock cmpxchg cs:qword_18000D2D0, rcx
0x180006f8e  mov     rax, cs:qword_18000D2D0
0x180006f95  lea     r8, [rbp+var_40]
0x180006f99  mov     edx, 3
0x180006f9e  mov     rcx, rbx
0x180006fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fa6  mov     rcx, [rbp+var_10]
0x180006faa  xor     rcx, rsp; StackCookie
0x180006fad  call    __security_check_cookie
0x180006fb2  mov     rbx, [rsp+60h+arg_8]
0x180006fb7  add     rsp, 60h
0x180006fbb  pop     rbp
0x180006fbc  retn
```
