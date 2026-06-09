# EditStreamCopy

- ea: `0x1800131e0`
- end: `0x180013270`
- name: `EditStreamCopy`
- size: `144`
- prototype: `HRESULT __stdcall(PAVISTREAM pavi, LONG *plStart, LONG *plLength, PAVISTREAM *ppResult)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001460`
- `0x1800131e0`
- `0x180018010`

## pseudocode

```c
HRESULT __stdcall EditStreamCopy(PAVISTREAM pavi, LONG *plStart, LONG *plLength, PAVISTREAM *ppResult)
{
  struct IAVIStreamVtbl *lpVtbl; // rax
  HRESULT v9; // ebx
  __int64 v10; // [rsp+30h] [rbp-28h] BYREF

  lpVtbl = pavi->lpVtbl;
  v10 = 0;
  ((void (__fastcall *)(PAVISTREAM, GUID *, __int64 *))lpVtbl->QueryInterface)(pavi, &IID_IAVIEditStream, &v10);
  if ( !v10 )
    return -2147467262;
  v9 = (*(__int64 (__fastcall **)(__int64, LONG *, LONG *, PAVISTREAM *))(*(_QWORD *)v10 + 32LL))(
         v10,
         plStart,
         plLength,
         ppResult);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return v9;
}

```

## disassembly

```asm
0x1800131e0  push    rbx
0x1800131e2  push    rsi
0x1800131e3  push    rdi
0x1800131e4  sub     rsp, 40h
0x1800131e8  mov     rax, cs:__security_cookie
0x1800131ef  xor     rax, rsp
0x1800131f2  mov     [rsp+58h+var_20], rax
0x1800131f7  mov     rax, [rcx]
0x1800131fa  mov     rdi, r8
0x1800131fd  mov     rbx, rdx
0x180013200  mov     [rsp+58h+var_28], 0
0x180013209  lea     r8, [rsp+58h+var_28]
0x18001320e  mov     rsi, r9
0x180013211  lea     rdx, IID_IAVIEditStream
0x180013218  mov     rax, [rax]
0x18001321b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013220  mov     rcx, [rsp+58h+var_28]
0x180013225  test    rcx, rcx
0x180013228  jnz     short loc_180013231
0x18001322a  mov     eax, 80004002h
0x18001322f  jmp     short loc_18001325B
0x180013231  mov     rax, [rcx]
0x180013234  mov     r9, rsi
0x180013237  mov     r8, rdi
0x18001323a  mov     rdx, rbx
0x18001323d  mov     rax, [rax+20h]
0x180013241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013246  mov     rcx, [rsp+58h+var_28]
0x18001324b  mov     ebx, eax
0x18001324d  mov     rdx, [rcx]
0x180013250  mov     rax, [rdx+10h]
0x180013254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013259  mov     eax, ebx
0x18001325b  mov     rcx, [rsp+58h+var_20]
0x180013260  xor     rcx, rsp; StackCookie
0x180013263  call    __security_check_cookie
0x180013268  add     rsp, 40h
0x18001326c  pop     rdi
0x18001326d  pop     rsi
0x18001326e  pop     rbx
0x18001326f  retn
```
