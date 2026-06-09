# __delayLoadHelper2

- ea: `0x18002fe00`
- end: `0x18002ff60`
- name: `__delayLoadHelper2`
- size: `352`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005aa26`
- `0x18005ace2`
- `0x18005ae0f`
- `0x18005b1ca`
- `0x18005b29d`
- `0x18005b328`

## callees

- `0x18002fe00`
- `0x18004f9fc`
- `0x18005a8bc`
- `0x18005ab30`
- `0x18005ab60`
- `0x180130010`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x18002feae`
- `KERNEL32!LoadLibraryExA` at `0x18002feae`
- `KERNEL32!DelayLoadFailureHook` at `0x18002ff3b`
- `KERNEL32!DelayLoadFailureHook` at `0x18002ff3b`

## pseudocode

```c
__int64 __fastcall _delayLoadHelper2(unsigned int *a1, FARPROC *a2)
{
  __int64 v2; // rsi
  __int64 v4; // r15
  __int64 v5; // r12
  HMODULE v6; // rdi
  __int64 result; // rax
  __int64 v8; // rbx
  const CHAR *v9; // rbp
  __int64 v10; // rdx
  const CHAR *v11; // rsi
  HMODULE Library; // rax
  signed __int64 v13; // rbx
  FARPROC ProcAddress_0; // rax
  struct DelayLoadInfo v15; // [rsp+20h] [rbp-78h] BYREF
  char v16; // [rsp+A0h] [rbp+8h] BYREF
  HMODULE *v17; // [rsp+B0h] [rbp+18h]

  v2 = a1[1];
  v4 = a1[3];
  v5 = a1[4];
  v17 = (HMODULE *)((char *)&_ImageBase + a1[2]);
  v16 = 0;
  v6 = *v17;
  result = Dload__delayLoadHelper2(a1, a2, &v16);
  v8 = result;
  if ( !v16 )
  {
    v9 = (char *)&_ImageBase + v2;
    v10 = v5 + 8LL * (unsigned int)(((char *)a2 - v4 - (char *)&_ImageBase) >> 3);
    if ( *(__int64 *)((char *)&_ImageBase + v10) < 0 )
      v11 = (const CHAR *)*(unsigned __int16 *)((char *)&_ImageBase + v10);
    else
      v11 = (char *)&word_180000002 + *(unsigned int *)((char *)&_ImageBase + v10);
    if ( !v6 )
    {
      Library = LoadLibraryExA(v9, 0, 0);
      v6 = Library;
      if ( !Library )
      {
        if ( v8 )
          return v8;
        return DelayLoadFailureHook(v9, v11);
      }
      v13 = _InterlockedCompareExchange64((volatile signed __int64 *)v17, (signed __int64)Library, 0);
      if ( v13 )
      {
        FreeLibrary_0(Library);
        v6 = (HMODULE)v13;
      }
      else
      {
        memset_0(&v15, 0, sizeof(v15));
        v15.cb = 72;
        v15.szDll = v9;
        v15.hmodCur = v6;
        if ( _pfnDliNotifyHook2 )
          _pfnDliNotifyHook2(5u, &v15);
      }
    }
    ProcAddress_0 = GetProcAddress_0(v6, v11);
    v8 = (__int64)ProcAddress_0;
    if ( ProcAddress_0 )
    {
      *a2 = ProcAddress_0;
      return v8;
    }
    return DelayLoadFailureHook(v9, v11);
  }
  return result;
}

```

## disassembly

```asm
0x18002fe00  mov     r11, rsp
0x18002fe03  mov     [r11+10h], rbx
0x18002fe07  mov     [r11+20h], rbp
0x18002fe0b  push    rsi
0x18002fe0c  push    rdi
0x18002fe0d  push    r12
0x18002fe0f  push    r14
0x18002fe11  push    r15
0x18002fe13  sub     rsp, 70h
0x18002fe17  mov     eax, [rcx+8]
0x18002fe1a  lea     r8, [r11+8]
0x18002fe1e  mov     esi, [rcx+4]
0x18002fe21  mov     r14, rdx
0x18002fe24  mov     r15d, [rcx+0Ch]
0x18002fe28  lea     rdx, __ImageBase
0x18002fe2f  mov     r12d, [rcx+10h]
0x18002fe33  add     rax, rdx
0x18002fe36  mov     [rsp+98h+arg_10], rax
0x18002fe3e  mov     rdx, r14
0x18002fe41  mov     rax, [rsp+98h+arg_10]
0x18002fe49  mov     byte ptr [r11+8], 0
0x18002fe4e  mov     rdi, [rax]
0x18002fe51  call    Dload__delayLoadHelper2
0x18002fe56  cmp     [rsp+98h+arg_0], 0
0x18002fe5e  mov     rbx, rax
0x18002fe61  jnz     loc_18002FF47
0x18002fe67  lea     r8, __ImageBase
0x18002fe6e  mov     rcx, r14
0x18002fe71  sub     rcx, r15
0x18002fe74  lea     rbp, [r8+rsi]
0x18002fe78  sub     rcx, r8
0x18002fe7b  sar     rcx, 3
0x18002fe7f  mov     ecx, ecx
0x18002fe81  lea     rdx, [r12+rcx*8]
0x18002fe85  cmp     qword ptr [rdx+r8], 0
0x18002fe8a  jl      short loc_18002FE9C
0x18002fe8c  mov     esi, [rdx+r8]
0x18002fe90  lea     rax, word_180000002
0x18002fe97  add     rsi, rax
0x18002fe9a  jmp     short loc_18002FEA1
0x18002fe9c  movzx   esi, word ptr [rdx+r8]
0x18002fea1  test    rdi, rdi
0x18002fea4  jnz     short loc_18002FF0B
0x18002fea6  xor     r8d, r8d; dwFlags
0x18002fea9  xor     edx, edx; hFile
0x18002feab  mov     rcx, rbp; lpLibFileName
0x18002feae  call    cs:__imp_LoadLibraryExA
0x18002feb4  mov     rdi, rax
0x18002feb7  test    rax, rax
0x18002feba  jz      short loc_18002FF30
0x18002febc  mov     rcx, [rsp+98h+arg_10]
0x18002fec4  xor     eax, eax
0x18002fec6  lock cmpxchg [rcx], rdi
0x18002fecb  mov     rbx, rax
0x18002fece  jnz     short loc_18002FF23
0x18002fed0  mov     ebx, 48h ; 'H'
0x18002fed5  lea     rcx, [rsp+98h+var_78]; void *
0x18002feda  mov     r8d, ebx; Size
0x18002fedd  xor     edx, edx; Val
0x18002fedf  call    memset_0
0x18002fee4  mov     rax, cs:__pfnDliNotifyHook2
0x18002feeb  mov     [rsp+98h+var_78], ebx
0x18002feef  mov     [rsp+98h+var_60], rbp
0x18002fef4  mov     [rsp+98h+var_48], rdi
0x18002fef9  test    rax, rax
0x18002fefc  jz      short loc_18002FF0B
0x18002fefe  lea     rdx, [rsp+98h+var_78]
0x18002ff03  lea     ecx, [rbx-43h]
0x18002ff06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff0b  mov     rdx, rsi; lpProcName
0x18002ff0e  mov     rcx, rdi; hModule
0x18002ff11  call    GetProcAddress_0
0x18002ff16  mov     rbx, rax
0x18002ff19  test    rax, rax
0x18002ff1c  jz      short loc_18002FF35
0x18002ff1e  mov     [r14], rax
0x18002ff21  jmp     short loc_18002FF44
0x18002ff23  mov     rcx, rdi; hLibModule
0x18002ff26  call    FreeLibrary_0
0x18002ff2b  mov     rdi, rbx
0x18002ff2e  jmp     short loc_18002FF0B
0x18002ff30  test    rbx, rbx
0x18002ff33  jnz     short loc_18002FF44
0x18002ff35  mov     rdx, rsi
0x18002ff38  mov     rcx, rbp
0x18002ff3b  call    cs:__imp_DelayLoadFailureHook
0x18002ff41  mov     rbx, rax
0x18002ff44  mov     rax, rbx
0x18002ff47  lea     r11, [rsp+98h+var_28]
0x18002ff4c  mov     rbx, [r11+38h]
0x18002ff50  mov     rbp, [r11+48h]
0x18002ff54  mov     rsp, r11
0x18002ff57  pop     r15
0x18002ff59  pop     r14
0x18002ff5b  pop     r12
0x18002ff5d  pop     rdi
0x18002ff5e  pop     rsi
0x18002ff5f  retn
```
