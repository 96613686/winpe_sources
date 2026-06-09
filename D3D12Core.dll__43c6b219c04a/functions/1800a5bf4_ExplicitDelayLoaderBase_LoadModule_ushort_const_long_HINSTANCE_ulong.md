# ExplicitDelayLoaderBase::LoadModule(ushort const *,long (*)(HINSTANCE__ *),ulong)

- ea: `0x1800a5bf4`
- end: `0x1800a5ca3`
- name: `?LoadModule@ExplicitDelayLoaderBase@@IEAAJPEBGP6AJPEAUHINSTANCE__@@@ZK@Z`
- size: `175`
- prototype: `int(ExplicitDelayLoaderBase *__hidden this, const unsigned __int16 *, int (*)(HINSTANCE), unsigned int)`
- caller_count: `10`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180056da0`
- `0x1800628cc`
- `0x180068380`
- `0x180153a20`
- `0x180153aa0`
- `0x180153b20`
- `0x180153b80`
- `0x180153be0`
- `0x180154890`
- `0x180224c4c`

## callees

- `0x18000ac4c`
- `0x1800a5bf4`
- `0x180262020`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800a5c88`
- `msvcp_win!_Mtx_unlock` at `0x1800a5c88`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a5c39`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a5c39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5c5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5c5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ExplicitDelayLoaderBase::LoadModule(
        ExplicitDelayLoaderBase *this,
        const unsigned __int16 *a2,
        __int64 (__fastcall *a3)(HMODULE),
        DWORD a4)
{
  HMODULE Library; // rax
  signed int v9; // ebx
  signed int LastError; // eax

  std::_Mutex_base::lock((std::_Mutex_base *)&ExplicitDelayLoaderBase::g_loaderLock);
  if ( *(_BYTE *)this )
  {
    if ( *((_BYTE *)this + 1) )
      v9 = -2147467263;
    else
      v9 = 0;
  }
  else
  {
    *(_WORD *)this = 257;
    Library = LoadLibraryExW(a2, 0, a4);
    *((_QWORD *)this + 1) = Library;
    if ( Library )
    {
      v9 = a3(Library);
      *((_BYTE *)this + 1) = v9 < 0;
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  _Mtx_unlock((_Mtx_t)&ExplicitDelayLoaderBase::g_loaderLock);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800a5bf4  mov     [rsp+arg_8], rbx
0x1800a5bf9  mov     [rsp+arg_10], rbp
0x1800a5bfe  push    rsi
0x1800a5bff  push    rdi
0x1800a5c00  push    r14
0x1800a5c02  sub     rsp, 20h
0x1800a5c06  mov     ebx, r9d
0x1800a5c09  mov     rbp, r8
0x1800a5c0c  mov     rsi, rdx
0x1800a5c0f  mov     rdi, rcx
0x1800a5c12  lea     r14, ?g_loaderLock@ExplicitDelayLoaderBase@@0Vmutex@std@@A; std::mutex ExplicitDelayLoaderBase::g_loaderLock
0x1800a5c19  mov     [rsp+38h+arg_0], r14
0x1800a5c1e  mov     rcx, r14; this
0x1800a5c21  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800a5c26  nop
0x1800a5c27  cmp     byte ptr [rdi], 0
0x1800a5c2a  jnz     short loc_1800A5C76
0x1800a5c2c  mov     word ptr [rdi], 101h
0x1800a5c31  mov     r8d, ebx; dwFlags
0x1800a5c34  xor     edx, edx; hFile
0x1800a5c36  mov     rcx, rsi; lpLibFileName
0x1800a5c39  call    cs:__imp_LoadLibraryExW
0x1800a5c3f  mov     [rdi+8], rax
0x1800a5c43  test    rax, rax
0x1800a5c46  jz      short loc_1800A5C5F
0x1800a5c48  mov     rcx, rax
0x1800a5c4b  mov     rax, rbp
0x1800a5c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5c53  mov     ebx, eax
0x1800a5c55  mov     ecx, eax
0x1800a5c57  shr     ecx, 1Fh
0x1800a5c5a  mov     [rdi+1], cl
0x1800a5c5d  jmp     short loc_1800A5C85
0x1800a5c5f  call    cs:__imp_GetLastError
0x1800a5c65  mov     ebx, eax
0x1800a5c67  test    eax, eax
0x1800a5c69  jle     short loc_1800A5C85
0x1800a5c6b  movzx   ebx, ax
0x1800a5c6e  or      ebx, 80070000h
0x1800a5c74  jmp     short loc_1800A5C85
0x1800a5c76  cmp     byte ptr [rdi+1], 0
0x1800a5c7a  jz      short loc_1800A5C83
0x1800a5c7c  mov     ebx, 80004001h
0x1800a5c81  jmp     short loc_1800A5C85
0x1800a5c83  xor     ebx, ebx
0x1800a5c85  mov     rcx, r14; _Mtx_t
0x1800a5c88  call    cs:__imp__Mtx_unlock
0x1800a5c8e  mov     eax, ebx
0x1800a5c90  mov     rbx, [rsp+38h+arg_8]
0x1800a5c95  mov     rbp, [rsp+38h+arg_10]
0x1800a5c9a  add     rsp, 20h
0x1800a5c9e  pop     r14
0x1800a5ca0  pop     rdi
0x1800a5ca1  pop     rsi
0x1800a5ca2  retn
```
