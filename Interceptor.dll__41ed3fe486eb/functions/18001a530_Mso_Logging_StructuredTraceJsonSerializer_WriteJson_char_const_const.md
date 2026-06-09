# Mso::Logging::StructuredTraceJsonSerializer::WriteJson(char const * const &)

- ea: `0x18001a530`
- end: `0x18001a670`
- name: `?WriteJson@StructuredTraceJsonSerializer@Logging@Mso@@AEAA_NAEBQEBD@Z`
- size: `320`
- prototype: `bool __fastcall(Mso::Logging::StructuredTraceJsonSerializer *__hidden this, const char *const *)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800173f0`
- `0x180017500`
- `0x180018c50`
- `0x180018da0`

## callees

- `0x18000ab0c`
- `0x18000ac10`
- `0x180012318`
- `0x18001a530`
- `0x18001e970`
- `0x18002b3c0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001a5c5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001a5c5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001a60a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001a60a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Mso::Logging::StructuredTraceJsonSerializer::WriteJson(
        Mso::Logging::StructuredTraceJsonSerializer *this,
        LPCCH *a2)
{
  const CHAR *v4; // rcx
  char v5; // bl
  __int64 v6; // rcx
  __int64 v8; // rcx
  int v9; // ebp
  WCHAR *v10; // rax
  WCHAR *v11; // rsi
  __int64 v12; // rcx

  v4 = *a2;
  v5 = 0;
  if ( *a2 )
  {
    if ( *v4 )
    {
      v9 = MsoSzToWz(v4, 0, 0) + 1;
      v10 = (WCHAR *)malloc(saturated_mul(v9, 2u));
      v11 = v10;
      if ( !v10 )
        std::_Xbad_alloc();
      if ( (int)MsoSzToWz(*a2, v10, v9) <= 0 )
      {
        MsoShipAssertTagProc(7463971);
      }
      else
      {
        v12 = *((_QWORD *)this + 1);
        if ( !v12 )
          CrashWithRecovery(0x1E3C3840u, 0);
        _mm_lfence();
        v5 = (*(__int64 (__fastcall **)(__int64, WCHAR *))(*(_QWORD *)v12 + 56LL))(v12, v11);
      }
      free(v11);
      return v5;
    }
    else
    {
      v8 = *((_QWORD *)this + 1);
      if ( !v8 )
        CrashWithRecovery(0x1E3C3840u, 0);
      return (*(__int64 (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)v8 + 56LL))(v8, &Src);
    }
  }
  else
  {
    v6 = *((_QWORD *)this + 1);
    if ( !v6 )
      CrashWithRecovery(0x1E3C3840u, 0);
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 104LL))(v6);
  }
}

```

## disassembly

```asm
0x18001a530  mov     rax, rsp
0x18001a533  mov     [rax+8], rbx
0x18001a537  mov     [rax+10h], rbp
0x18001a53b  mov     [rax+18h], rsi
0x18001a53f  mov     [rax+20h], rdi
0x18001a543  push    r14
0x18001a545  sub     rsp, 20h
0x18001a549  mov     r14, rdx
0x18001a54c  mov     rdi, rcx
0x18001a54f  mov     rcx, [rdx]; lpMultiByteStr
0x18001a552  xor     ebx, ebx
0x18001a554  test    rcx, rcx
0x18001a557  jnz     short loc_18001A578
0x18001a559  mov     rcx, [rdi+8]
0x18001a55d  test    rcx, rcx
0x18001a560  jz      loc_18001A63D
0x18001a566  mov     rax, [rcx]
0x18001a569  mov     rax, [rax+68h]
0x18001a56d  call    cs:__guard_dispatch_icall_fptr
0x18001a573  jmp     loc_18001A612
0x18001a578  cmp     [rcx], bl
0x18001a57a  jnz     short loc_18001A59F
0x18001a57c  mov     rcx, [rdi+8]
0x18001a580  test    rcx, rcx
0x18001a583  jz      loc_18001A64D
0x18001a589  mov     rax, [rcx]
0x18001a58c  lea     rdx, Src
0x18001a593  mov     rax, [rax+38h]
0x18001a597  call    cs:__guard_dispatch_icall_fptr
0x18001a59d  jmp     short loc_18001A612
0x18001a59f  xor     r8d, r8d; cchWideChar
0x18001a5a2  xor     edx, edx; lpWideCharStr
0x18001a5a4  call    MsoSzToWz
0x18001a5a9  lea     ebp, [rax+1]
0x18001a5ac  movsxd  rcx, ebp
0x18001a5af  mov     eax, 2
0x18001a5b4  mul     rcx
0x18001a5b7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001a5be  cmovb   rax, rcx
0x18001a5c2  mov     rcx, rax; Size
0x18001a5c5  call    cs:__imp_malloc
0x18001a5cb  mov     rsi, rax
0x18001a5ce  test    rax, rax
0x18001a5d1  jz      loc_18001A65D
0x18001a5d7  mov     r8d, ebp; cchWideChar
0x18001a5da  mov     rdx, rax; lpWideCharStr
0x18001a5dd  mov     rcx, [r14]; lpMultiByteStr
0x18001a5e0  call    MsoSzToWz
0x18001a5e5  test    eax, eax
0x18001a5e7  jle     short loc_18001A663
0x18001a5e9  mov     rcx, [rdi+8]
0x18001a5ed  test    rcx, rcx
0x18001a5f0  jz      short loc_18001A62D
0x18001a5f2  lfence
0x18001a5f5  mov     rax, [rcx]
0x18001a5f8  mov     rdx, rsi
0x18001a5fb  mov     rax, [rax+38h]
0x18001a5ff  call    cs:__guard_dispatch_icall_fptr
0x18001a605  mov     bl, al
0x18001a607  mov     rcx, rsi; Block
0x18001a60a  call    cs:__imp_free
0x18001a610  mov     al, bl
0x18001a612  mov     rbx, [rsp+28h+arg_0]
0x18001a617  mov     rbp, [rsp+28h+arg_8]
0x18001a61c  mov     rsi, [rsp+28h+arg_10]
0x18001a621  mov     rdi, [rsp+28h+arg_18]
0x18001a626  add     rsp, 20h
0x18001a62a  pop     r14
0x18001a62c  retn
0x18001a62d  xor     edx, edx; struct CrashContext *
0x18001a62f  mov     ecx, 1E3C3840h; unsigned int
0x18001a634  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18001a63a  jmp     short $+2
0x18001a63c  nop
0x18001a63d  xor     edx, edx; struct CrashContext *
0x18001a63f  mov     ecx, 1E3C3840h; unsigned int
0x18001a644  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18001a64a  jmp     short $+2
0x18001a64c  nop
0x18001a64d  xor     edx, edx; struct CrashContext *
0x18001a64f  mov     ecx, 1E3C3840h; unsigned int
0x18001a654  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18001a65a  jmp     short $+2
0x18001a65c  nop
0x18001a65d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18001a663  mov     ecx, 71E423h
0x18001a668  call    MsoShipAssertTagProc
0x18001a66d  jmp     short loc_18001A607
```
