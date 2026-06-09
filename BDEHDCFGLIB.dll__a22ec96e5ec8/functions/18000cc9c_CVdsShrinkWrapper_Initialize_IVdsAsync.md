# CVdsShrinkWrapper::Initialize(IVdsAsync *)

- ea: `0x18000cc9c`
- end: `0x18000cd4a`
- name: `?Initialize@CVdsShrinkWrapper@@QEAAJPEAUIVdsAsync@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(CVdsShrinkWrapper *__hidden this, struct IVdsAsync *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006a48`

## callees

- `0x1800015c4`
- `0x18000cc9c`
- `0x180015010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18000cd07`
- `KERNEL32!CreateEventW` at `0x18000cd07`
- `KERNEL32!GetLastError` at `0x18000cd23`
- `KERNEL32!GetLastError` at `0x18000cd23`

## pseudocode

```c
__int64 __fastcall CVdsShrinkWrapper::Initialize(CVdsShrinkWrapper *this, struct IVdsAsync *a2)
{
  unsigned int v4; // ebx
  _DWORD *v5; // rax
  signed int LastError; // eax

  v4 = 0;
  v5 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    *(_QWORD *)v5 = 0;
    v5[2] = 0;
    *((_QWORD *)v5 + 6) = 0;
    v5[14] = 0;
    v5[15] = 1;
  }
  *((_QWORD *)this + 1) = v5;
  if ( v5 )
  {
    *(_QWORD *)v5 = a2;
    ((void (__fastcall *)(struct IVdsAsync *))a2->lpVtbl->AddRef)(a2);
    *(_QWORD *)(*((_QWORD *)this + 1) + 48LL) = CreateEventW(0, 0, 0, 0);
    if ( !*(_QWORD *)(*((_QWORD *)this + 1) + 48LL) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v4;
}

```

## disassembly

```asm
0x18000cc9c  mov     [rsp+arg_0], rbx
0x18000cca1  mov     [rsp+arg_8], rsi
0x18000cca6  push    rdi
0x18000cca7  sub     rsp, 20h
0x18000ccab  mov     rsi, rdx
0x18000ccae  mov     rdi, rcx
0x18000ccb1  xor     ebx, ebx
0x18000ccb3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ccba  lea     ecx, [rbx+40h]; unsigned __int64
0x18000ccbd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ccc2  test    rax, rax
0x18000ccc5  jz      short loc_18000CCDB
0x18000ccc7  mov     [rax], rbx
0x18000ccca  mov     [rax+8], ebx
0x18000cccd  mov     [rax+30h], rbx
0x18000ccd1  mov     [rax+38h], ebx
0x18000ccd4  mov     dword ptr [rax+3Ch], 1
0x18000ccdb  mov     [rdi+8], rax
0x18000ccdf  test    rax, rax
0x18000cce2  jnz     short loc_18000CCEB
0x18000cce4  mov     ebx, 8007000Eh
0x18000cce9  jmp     short loc_18000CD38
0x18000cceb  mov     [rax], rsi
0x18000ccee  mov     rax, [rsi]
0x18000ccf1  mov     rcx, rsi
0x18000ccf4  mov     rax, [rax+8]
0x18000ccf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccfd  xor     r9d, r9d; lpName
0x18000cd00  xor     r8d, r8d; bInitialState
0x18000cd03  xor     edx, edx; bManualReset
0x18000cd05  xor     ecx, ecx; lpEventAttributes
0x18000cd07  call    cs:__imp_CreateEventW
0x18000cd0d  mov     rcx, rax
0x18000cd10  mov     rax, [rdi+8]
0x18000cd14  mov     [rax+30h], rcx
0x18000cd18  mov     rax, [rdi+8]
0x18000cd1c  cmp     qword ptr [rax+30h], 0
0x18000cd21  jnz     short loc_18000CD38
0x18000cd23  call    cs:__imp_GetLastError
0x18000cd29  mov     ebx, eax
0x18000cd2b  test    eax, eax
0x18000cd2d  jle     short loc_18000CD38
0x18000cd2f  movzx   ebx, ax
0x18000cd32  or      ebx, 80070000h
0x18000cd38  mov     eax, ebx
0x18000cd3a  mov     rbx, [rsp+28h+arg_0]
0x18000cd3f  mov     rsi, [rsp+28h+arg_8]
0x18000cd44  add     rsp, 20h
0x18000cd48  pop     rdi
0x18000cd49  retn
0x180014149  push    rbp
0x18001414b  sub     rsp, 20h
0x18001414f  mov     rbp, rdx
0x180014152  add     rsp, 20h
0x180014156  pop     rbp
0x180014157  retn
```
