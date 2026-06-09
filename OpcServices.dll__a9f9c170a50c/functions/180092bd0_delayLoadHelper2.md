# __delayLoadHelper2

- ea: `0x180092bd0`
- end: `0x180092d3a`
- name: `__delayLoadHelper2`
- size: `362`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800cd9d0`
- `0x1800cdacd`
- `0x1800d0a0a`
- `0x1800d0b7f`
- `0x1800d0c0a`
- `0x1800d0ccb`
- `0x1800d0e8c`

## callees

- `0x180092bd0`
- `0x180092d40`
- `0x1800cdaa9`
- `0x1800cdab5`
- `0x1800d5fe4`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180092c93`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180092c93`
- `KERNEL32!DelayLoadFailureHook` at `0x180092d18`
- `KERNEL32!DelayLoadFailureHook` at `0x180092c22`
- `KERNEL32!DelayLoadFailureHook` at `0x180092d18`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(unsigned int *a1, FARPROC *a2)
{
  __int64 v2; // rsi
  __int64 v3; // rbp
  __int64 v5; // r15
  HMODULE v7; // rbx
  FARPROC result; // rax
  const CHAR *v9; // rsi
  __int64 v10; // rdx
  const CHAR *v11; // rdi
  HMODULE Library; // rax
  signed __int64 v13; // rbp
  struct DelayLoadInfo v14; // [rsp+40h] [rbp-78h] BYREF
  volatile signed __int64 *v15; // [rsp+C0h] [rbp+8h]

  v2 = a1[1];
  v3 = a1[3];
  v5 = a1[4];
  v15 = (volatile signed __int64 *)((char *)&_ImageBase + a1[2]);
  v7 = (HMODULE)*v15;
  if ( (unsigned __int8)DloadResolve() )
    return (FARPROC)((__int64 (__fastcall *)(__int16 *, unsigned int *, __int64, __int64 (__fastcall *)(_QWORD, _QWORD), FARPROC *, _DWORD))DloadResolveDelayLoadedAPI)(
                      &_ImageBase,
                      a1,
                      _pfnDefaultDliFailureHook2,
                      DelayLoadFailureHook,
                      a2,
                      0);
  v9 = (char *)&_ImageBase + v2;
  v10 = v5 + 8LL * (unsigned int)(((char *)a2 - v3 - (char *)&_ImageBase) >> 3);
  if ( *(__int64 *)((char *)&_ImageBase + v10) < 0 )
    v11 = (const CHAR *)*(unsigned __int16 *)((char *)&_ImageBase + v10);
  else
    v11 = (char *)&word_180000002 + *(unsigned int *)((char *)&_ImageBase + v10);
  if ( !v7 )
  {
    Library = LoadLibraryExA(v9, 0, 0);
    v7 = Library;
    if ( !Library )
      return (FARPROC)DelayLoadFailureHook(v9, v11);
    v13 = _InterlockedCompareExchange64(v15, (signed __int64)Library, 0);
    if ( v13 )
    {
      FreeLibrary_0(Library);
      v7 = (HMODULE)v13;
    }
    else
    {
      memset_0(&v14, 0, sizeof(v14));
      v14.cb = 72;
      v14.szDll = v9;
      v14.hmodCur = v7;
      if ( _pfnDliNotifyHook2 )
        _pfnDliNotifyHook2(5u, &v14);
    }
  }
  result = GetProcAddress_0(v7, v11);
  if ( result )
  {
    *a2 = result;
    return result;
  }
  return (FARPROC)DelayLoadFailureHook(v9, v11);
}

```

## disassembly

```asm
0x180092bd0  mov     [rsp+arg_8], rbx
0x180092bd5  mov     [rsp+arg_10], rbp
0x180092bda  push    rsi
0x180092bdb  push    rdi
0x180092bdc  push    r12
0x180092bde  push    r14
0x180092be0  push    r15
0x180092be2  sub     rsp, 90h
0x180092be9  mov     eax, [rcx+8]
0x180092bec  lea     r12, __ImageBase
0x180092bf3  mov     esi, [rcx+4]
0x180092bf6  add     rax, r12
0x180092bf9  mov     ebp, [rcx+0Ch]
0x180092bfc  mov     r14, rdx
0x180092bff  mov     r15d, [rcx+10h]
0x180092c03  mov     rdi, rcx
0x180092c06  mov     [rsp+0B8h+arg_0], rax
0x180092c0e  mov     rax, [rsp+0B8h+arg_0]
0x180092c16  mov     rbx, [rax]
0x180092c19  call    DloadResolve
0x180092c1e  test    al, al
0x180092c20  jz      short loc_180092C54
0x180092c22  mov     r9, cs:__imp_DelayLoadFailureHook
0x180092c29  mov     rdx, rdi
0x180092c2c  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180092c33  mov     rcx, r12
0x180092c36  mov     rax, cs:DloadResolveDelayLoadedAPI
0x180092c3d  mov     [rsp+0B8h+var_90], 0
0x180092c45  mov     [rsp+0B8h+var_98], r14
0x180092c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092c4f  jmp     loc_180092D1E
0x180092c54  mov     rcx, r14
0x180092c57  add     rsi, r12
0x180092c5a  sub     rcx, rbp
0x180092c5d  sub     rcx, r12
0x180092c60  sar     rcx, 3
0x180092c64  mov     ecx, ecx
0x180092c66  lea     rdx, [r15+rcx*8]
0x180092c6a  cmp     qword ptr [rdx+r12], 0
0x180092c6f  jl      short loc_180092C81
0x180092c71  mov     edi, [rdx+r12]
0x180092c75  lea     rax, word_180000002
0x180092c7c  add     rdi, rax
0x180092c7f  jmp     short loc_180092C86
0x180092c81  movzx   edi, word ptr [rdx+r12]
0x180092c86  test    rbx, rbx
0x180092c89  jnz     short loc_180092CFD
0x180092c8b  xor     r8d, r8d; dwFlags
0x180092c8e  xor     edx, edx; hFile
0x180092c90  mov     rcx, rsi; lpLibFileName
0x180092c93  call    cs:__imp_LoadLibraryExA
0x180092c99  mov     rbx, rax
0x180092c9c  test    rax, rax
0x180092c9f  jz      short loc_180092D12
0x180092ca1  mov     rcx, [rsp+0B8h+arg_0]
0x180092ca9  xor     eax, eax
0x180092cab  lock cmpxchg [rcx], rbx
0x180092cb0  mov     rbp, rax
0x180092cb3  jnz     short loc_180092CF2
0x180092cb5  mov     ebp, 48h ; 'H'
0x180092cba  lea     rcx, [rsp+0B8h+var_78]; void *
0x180092cbf  mov     r8d, ebp; Size
0x180092cc2  xor     edx, edx; Val
0x180092cc4  call    memset_0
0x180092cc9  mov     rax, cs:__pfnDliNotifyHook2
0x180092cd0  mov     [rsp+0B8h+var_78], ebp
0x180092cd4  mov     [rsp+0B8h+var_60], rsi
0x180092cd9  mov     [rsp+0B8h+var_48], rbx
0x180092cde  test    rax, rax
0x180092ce1  jz      short loc_180092CFD
0x180092ce3  lea     rdx, [rsp+0B8h+var_78]
0x180092ce8  lea     ecx, [rbp-43h]
0x180092ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092cf0  jmp     short loc_180092CFD
0x180092cf2  mov     rcx, rbx; hLibModule
0x180092cf5  call    FreeLibrary_0
0x180092cfa  mov     rbx, rbp
0x180092cfd  mov     rdx, rdi; lpProcName
0x180092d00  mov     rcx, rbx; hModule
0x180092d03  call    GetProcAddress_0
0x180092d08  test    rax, rax
0x180092d0b  jz      short loc_180092D12
0x180092d0d  mov     [r14], rax
0x180092d10  jmp     short loc_180092D1E
0x180092d12  mov     rdx, rdi
0x180092d15  mov     rcx, rsi
0x180092d18  call    cs:__imp_DelayLoadFailureHook
0x180092d1e  lea     r11, [rsp+0B8h+var_28]
0x180092d26  mov     rbx, [r11+38h]
0x180092d2a  mov     rbp, [r11+40h]
0x180092d2e  mov     rsp, r11
0x180092d31  pop     r15
0x180092d33  pop     r14
0x180092d35  pop     r12
0x180092d37  pop     rdi
0x180092d38  pop     rsi
0x180092d39  retn
```
