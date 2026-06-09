# CDriveConfiguration::CancelConfiguration_Thread(void)

- ea: `0x18000f280`
- end: `0x18000f34e`
- name: `?CancelConfiguration_Thread@CDriveConfiguration@@AEAAJXZ`
- size: `206`
- prototype: `__int64 __fastcall(CDriveConfiguration *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f240`

## callees

- `0x18000f280`
- `0x180015010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f298`
- `KERNEL32!EnterCriticalSection` at `0x18000f298`
- `KERNEL32!LeaveCriticalSection` at `0x18000f2eb`
- `KERNEL32!LeaveCriticalSection` at `0x18000f2eb`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::CancelConfiguration_Thread(CDriveConfiguration *this)
{
  unsigned int v2; // ebp
  __int64 v3; // rdi
  __int64 v4; // rbx
  __int64 v5; // rcx
  void (*v6)(void); // rax
  __int64 v7; // rcx

  v2 = 0;
  v3 = 0;
  v4 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( !*((_DWORD *)this + 4) )
  {
    v5 = *((_QWORD *)this + 159);
    if ( !v5 )
      goto LABEL_9;
    v3 = *((_QWORD *)this + 159);
    v6 = *(void (**)(void))(*(_QWORD *)v5 + 8LL);
LABEL_7:
    v6();
    goto LABEL_9;
  }
  if ( *((_DWORD *)this + 4) == 1 )
  {
    v7 = *((_QWORD *)this + 160);
    if ( !v7 )
      goto LABEL_9;
    v4 = *((_QWORD *)this + 160);
    v6 = *(void (**)(void))(*(_QWORD *)v7 + 32LL);
    goto LABEL_7;
  }
  v2 = -1063256037;
LABEL_9:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 24LL))(v3);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 40LL))(v4);
  return v2;
}

```

## disassembly

```asm
0x18000f280  push    rbx
0x18000f282  push    rbp
0x18000f283  push    rsi
0x18000f284  push    rdi
0x18000f285  push    r14
0x18000f287  sub     rsp, 20h
0x18000f28b  mov     rsi, rcx
0x18000f28e  xor     ebp, ebp
0x18000f290  add     rcx, 18h; lpCriticalSection
0x18000f294  xor     edi, edi
0x18000f296  xor     ebx, ebx
0x18000f298  call    cs:__imp_EnterCriticalSection
0x18000f29e  mov     eax, [rsi+10h]
0x18000f2a1  test    eax, eax
0x18000f2a3  jnz     short loc_18000F2BD
0x18000f2a5  mov     rcx, [rsi+4F8h]
0x18000f2ac  test    rcx, rcx
0x18000f2af  jz      short loc_18000F2E7
0x18000f2b1  mov     rax, [rcx]
0x18000f2b4  mov     rdi, rcx
0x18000f2b7  mov     rax, [rax+8]
0x18000f2bb  jmp     short loc_18000F2DB
0x18000f2bd  mov     eax, [rsi+10h]
0x18000f2c0  cmp     eax, 1
0x18000f2c3  jnz     short loc_18000F2E2
0x18000f2c5  mov     rcx, [rsi+500h]
0x18000f2cc  test    rcx, rcx
0x18000f2cf  jz      short loc_18000F2E7
0x18000f2d1  mov     rax, [rcx]
0x18000f2d4  mov     rbx, rcx
0x18000f2d7  mov     rax, [rax+20h]
0x18000f2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2e0  jmp     short loc_18000F2E7
0x18000f2e2  mov     ebp, 0C0A0001Bh
0x18000f2e7  lea     rcx, [rsi+18h]; lpCriticalSection
0x18000f2eb  call    cs:__imp_LeaveCriticalSection
0x18000f2f1  test    rdi, rdi
0x18000f2f4  jz      short loc_18000F305
0x18000f2f6  mov     rax, [rdi]
0x18000f2f9  mov     rcx, rdi
0x18000f2fc  mov     rax, [rax+18h]
0x18000f300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f305  test    rbx, rbx
0x18000f308  jz      short loc_18000F319
0x18000f30a  mov     rax, [rbx]
0x18000f30d  mov     rcx, rbx
0x18000f310  mov     rax, [rax+8]
0x18000f314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f319  test    rdi, rdi
0x18000f31c  jz      short loc_18000F32D
0x18000f31e  mov     rax, [rdi]
0x18000f321  mov     rcx, rdi
0x18000f324  mov     rax, [rax+10h]
0x18000f328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f32d  test    rbx, rbx
0x18000f330  jz      short loc_18000F341
0x18000f332  mov     rdx, [rbx]
0x18000f335  mov     rcx, rbx
0x18000f338  mov     rax, [rdx+28h]
0x18000f33c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f341  mov     eax, ebp
0x18000f343  add     rsp, 20h
0x18000f347  pop     r14
0x18000f349  pop     rdi
0x18000f34a  pop     rsi
0x18000f34b  pop     rbp
0x18000f34c  pop     rbx
0x18000f34d  retn
```
