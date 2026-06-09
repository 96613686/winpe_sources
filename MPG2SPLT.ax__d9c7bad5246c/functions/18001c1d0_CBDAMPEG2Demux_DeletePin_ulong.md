# CBDAMPEG2Demux::DeletePin(ulong)

- ea: `0x18001c1d0`
- end: `0x18001c29c`
- name: `?DeletePin@CBDAMPEG2Demux@@UEAAJK@Z`
- size: `204`
- prototype: `__int64 __fastcall(CBDAMPEG2Demux *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001460`
- `0x180001f04`
- `0x18001c1d0`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001c240`
- `KERNEL32!LeaveCriticalSection` at `0x18001c240`
- `KERNEL32!EnterCriticalSection` at `0x18001c1fa`
- `KERNEL32!EnterCriticalSection` at `0x18001c1fa`

## pseudocode

```c
__int64 __fastcall CBDAMPEG2Demux::DeletePin(CBDAMPEG2Demux *this, unsigned int a2)
{
  unsigned int v2; // ebx
  __int64 v4; // rcx
  __int64 v5; // rax
  wchar_t Buffer[32]; // [rsp+20h] [rbp-58h] BYREF

  v2 = 0;
  if ( a2 )
  {
    swprintf_s(Buffer, 0x20u, L"%03d", a2);
    return (*(unsigned int (__fastcall **)(_QWORD, wchar_t *))(**(_QWORD **)(*((_QWORD *)this + 1) + 168LL) + 40LL))(
             *(_QWORD *)(*((_QWORD *)this + 1) + 168LL),
             Buffer);
  }
  else
  {
    EnterCriticalSection(*(LPCRITICAL_SECTION *)(*((_QWORD *)this + 1) + 80LL));
    v4 = *((_QWORD *)this + 1);
    v5 = *(_QWORD *)(v4 + 160);
    if ( !v5 || *(_QWORD *)(v5 + 48) )
    {
      v2 = -2147467259;
    }
    else
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(v5 + 24) + 16LL))(v5 + 24);
      *(_QWORD *)(*((_QWORD *)this + 1) + 160LL) = 0;
      v4 = *((_QWORD *)this + 1);
    }
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v4 + 80));
  }
  return v2;
}

```

## disassembly

```asm
0x18001c1d0  mov     [rsp+arg_10], rbx
0x18001c1d5  push    rdi
0x18001c1d6  sub     rsp, 70h
0x18001c1da  mov     rax, cs:__security_cookie
0x18001c1e1  xor     rax, rsp
0x18001c1e4  mov     [rsp+78h+var_18], rax
0x18001c1e9  xor     ebx, ebx
0x18001c1eb  mov     rdi, rcx
0x18001c1ee  test    edx, edx
0x18001c1f0  jnz     short loc_18001C248
0x18001c1f2  mov     rcx, [rcx+8]
0x18001c1f6  mov     rcx, [rcx+50h]; lpCriticalSection
0x18001c1fa  call    cs:__imp_EnterCriticalSection
0x18001c200  mov     rcx, [rdi+8]
0x18001c204  mov     rax, [rcx+0A0h]
0x18001c20b  test    rax, rax
0x18001c20e  jnz     short loc_18001C217
0x18001c210  mov     ebx, 80004005h
0x18001c215  jmp     short loc_18001C23C
0x18001c217  cmp     [rax+30h], rbx
0x18001c21b  jnz     short loc_18001C210
0x18001c21d  lea     rcx, [rax+18h]
0x18001c221  mov     rax, [rcx]
0x18001c224  mov     rax, [rax+10h]
0x18001c228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c22d  mov     rax, [rdi+8]
0x18001c231  mov     [rax+0A0h], rbx
0x18001c238  mov     rcx, [rdi+8]
0x18001c23c  mov     rcx, [rcx+50h]; lpCriticalSection
0x18001c240  call    cs:__imp_LeaveCriticalSection
0x18001c246  jmp     short loc_18001C27F
0x18001c248  mov     r9d, edx
0x18001c24b  lea     r8, a03d; "%03d"
0x18001c252  mov     edx, 20h ; ' '; BufferCount
0x18001c257  lea     rcx, [rsp+78h+Buffer]; Buffer
0x18001c25c  call    swprintf_s
0x18001c261  mov     rax, [rdi+8]
0x18001c265  lea     rdx, [rsp+78h+Buffer]
0x18001c26a  mov     rcx, [rax+0A8h]
0x18001c271  mov     rax, [rcx]
0x18001c274  mov     rax, [rax+28h]
0x18001c278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c27d  mov     ebx, eax
0x18001c27f  mov     eax, ebx
0x18001c281  mov     rcx, [rsp+78h+var_18]
0x18001c286  xor     rcx, rsp; StackCookie
0x18001c289  call    __security_check_cookie
0x18001c28e  mov     rbx, [rsp+78h+arg_10]
0x18001c296  add     rsp, 70h
0x18001c29a  pop     rdi
0x18001c29b  retn
```
