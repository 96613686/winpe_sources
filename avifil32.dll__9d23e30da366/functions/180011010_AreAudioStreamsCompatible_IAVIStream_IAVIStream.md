# AreAudioStreamsCompatible(IAVIStream *,IAVIStream *)

- ea: `0x180011010`
- end: `0x180011189`
- name: `?AreAudioStreamsCompatible@@YAHPEAUIAVIStream@@0@Z`
- size: `377`
- prototype: `__int64 __fastcall(PAVISTREAM pavi, PAVISTREAM)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180012224`

## callees

- `0x180001460`
- `0x1800086a0`
- `0x180011010`
- `0x18001734d`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001114e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001114e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800110bc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800110bc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180011145`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180011157`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180011145`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180011157`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800110b3`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800110b3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180011160`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180011160`

## pseudocode

```c
_BOOL8 __fastcall AreAudioStreamsCompatible(PAVISTREAM pavi, PAVISTREAM a2)
{
  unsigned int v4; // eax
  unsigned int v5; // eax
  HGLOBAL v6; // rax
  char *v7; // rdi
  unsigned int v8; // eax
  char *v9; // rbx
  unsigned int v10; // eax
  BOOL v11; // ebx
  HGLOBAL v12; // rax
  HGLOBAL v13; // rax
  size_t Size; // [rsp+30h] [rbp-18h] BYREF

  Size = 0;
  v4 = AVIStreamStart(pavi);
  if ( ((int (__fastcall *)(PAVISTREAM, _QWORD, _QWORD, size_t *))pavi->lpVtbl->ReadFormat)(pavi, v4, 0, &Size) < 0 )
    return 0;
  v5 = AVIStreamStart(a2);
  if ( ((int (__fastcall *)(PAVISTREAM, _QWORD, _QWORD, char *))a2->lpVtbl->ReadFormat)(a2, v5, 0, (char *)&Size + 4) < 0 )
    return 0;
  if ( (_DWORD)Size != HIDWORD(Size) )
    return 0;
  v6 = GlobalAlloc(0x42u, HIDWORD(Size) + (int)Size);
  v7 = (char *)GlobalLock(v6);
  if ( !v7 )
    return 0;
  v8 = AVIStreamStart(pavi);
  if ( ((int (__fastcall *)(PAVISTREAM, _QWORD, char *, size_t *))pavi->lpVtbl->ReadFormat)(pavi, v8, v7, &Size) < 0 )
    return 0;
  v9 = &v7[(int)Size];
  v10 = AVIStreamStart(a2);
  if ( ((int (__fastcall *)(PAVISTREAM, _QWORD, char *, char *))a2->lpVtbl->ReadFormat)(a2, v10, v9, (char *)&Size + 4) < 0 )
    return 0;
  v11 = memcmp_0(v7, &v7[(int)Size], (unsigned int)Size) == 0;
  v12 = GlobalHandle(v7);
  GlobalUnlock(v12);
  v13 = GlobalHandle(v7);
  GlobalFree(v13);
  return v11;
}

```

## disassembly

```asm
0x180011010  mov     [rsp+arg_10], rbx
0x180011015  mov     [rsp+arg_18], rsi
0x18001101a  push    rdi
0x18001101b  sub     rsp, 40h
0x18001101f  mov     rax, cs:__security_cookie
0x180011026  xor     rax, rsp
0x180011029  mov     [rsp+48h+var_10], rax
0x18001102e  mov     rsi, rdx
0x180011031  mov     dword ptr [rsp+48h+Size], 0
0x180011039  mov     rbx, rcx
0x18001103c  mov     dword ptr [rsp+48h+Size+4], 0
0x180011044  call    AVIStreamStart
0x180011049  mov     rcx, [rbx]
0x18001104c  lea     r9, [rsp+48h+Size]
0x180011051  mov     edx, eax
0x180011053  xor     r8d, r8d
0x180011056  mov     r10, [rcx+30h]
0x18001105a  mov     rcx, rbx
0x18001105d  mov     rax, r10
0x180011060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011065  test    eax, eax
0x180011067  js      loc_18001116A
0x18001106d  mov     rcx, rsi; pavi
0x180011070  call    AVIStreamStart
0x180011075  mov     rcx, [rsi]
0x180011078  lea     r9, [rsp+48h+Size+4]
0x18001107d  mov     edx, eax
0x18001107f  xor     r8d, r8d
0x180011082  mov     r10, [rcx+30h]
0x180011086  mov     rcx, rsi
0x180011089  mov     rax, r10
0x18001108c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011091  test    eax, eax
0x180011093  js      loc_18001116A
0x180011099  mov     eax, dword ptr [rsp+48h+Size]
0x18001109d  mov     ecx, dword ptr [rsp+48h+Size+4]
0x1800110a1  cmp     eax, ecx
0x1800110a3  jnz     loc_18001116A
0x1800110a9  add     eax, ecx
0x1800110ab  mov     ecx, 42h ; 'B'; uFlags
0x1800110b0  movsxd  rdx, eax; dwBytes
0x1800110b3  call    cs:__imp_GlobalAlloc
0x1800110b9  mov     rcx, rax; hMem
0x1800110bc  call    cs:__imp_GlobalLock
0x1800110c2  mov     rdi, rax
0x1800110c5  test    rax, rax
0x1800110c8  jz      loc_18001116A
0x1800110ce  mov     rcx, rbx; pavi
0x1800110d1  call    AVIStreamStart
0x1800110d6  mov     rdx, [rbx]
0x1800110d9  lea     r9, [rsp+48h+Size]
0x1800110de  mov     r8, rdi
0x1800110e1  mov     rcx, rbx
0x1800110e4  mov     r10, [rdx+30h]
0x1800110e8  mov     edx, eax
0x1800110ea  mov     rax, r10
0x1800110ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110f2  test    eax, eax
0x1800110f4  js      short loc_18001116A
0x1800110f6  movsxd  rbx, dword ptr [rsp+48h+Size]
0x1800110fb  mov     rcx, rsi; pavi
0x1800110fe  add     rbx, rdi
0x180011101  call    AVIStreamStart
0x180011106  mov     rdx, [rsi]
0x180011109  lea     r9, [rsp+48h+Size+4]
0x18001110e  mov     r8, rbx
0x180011111  mov     rcx, rsi
0x180011114  mov     r10, [rdx+30h]
0x180011118  mov     edx, eax
0x18001111a  mov     rax, r10
0x18001111d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011122  test    eax, eax
0x180011124  js      short loc_18001116A
0x180011126  movsxd  rdx, dword ptr [rsp+48h+Size]
0x18001112b  mov     rcx, rdi; Buf1
0x18001112e  mov     r8d, dword ptr [rsp+48h+Size]; Size
0x180011133  add     rdx, rdi; Buf2
0x180011136  call    memcmp_0
0x18001113b  xor     ebx, ebx
0x18001113d  mov     rcx, rdi; pMem
0x180011140  test    eax, eax
0x180011142  setz    bl
0x180011145  call    cs:__imp_GlobalHandle
0x18001114b  mov     rcx, rax; hMem
0x18001114e  call    cs:__imp_GlobalUnlock
0x180011154  mov     rcx, rdi; pMem
0x180011157  call    cs:__imp_GlobalHandle
0x18001115d  mov     rcx, rax; hMem
0x180011160  call    cs:__imp_GlobalFree
0x180011166  mov     eax, ebx
0x180011168  jmp     short loc_18001116C
0x18001116a  xor     eax, eax
0x18001116c  mov     rcx, [rsp+48h+var_10]
0x180011171  xor     rcx, rsp; StackCookie
0x180011174  call    __security_check_cookie
0x180011179  mov     rbx, [rsp+48h+arg_10]
0x18001117e  mov     rsi, [rsp+48h+arg_18]
0x180011183  add     rsp, 40h
0x180011187  pop     rdi
0x180011188  retn
```
