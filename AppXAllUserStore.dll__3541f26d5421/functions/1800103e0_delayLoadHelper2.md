# __delayLoadHelper2

- ea: `0x1800103e0`
- end: `0x180010542`
- name: `__delayLoadHelper2`
- size: `354`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180023040`
- `0x1800230cb`
- `0x180023168`
- `0x18002323b`

## callees

- `0x1800103e0`
- `0x180010548`
- `0x18004c98a`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18001048e`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18001048e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180010507`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180010507`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800104f1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800104f1`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18001051d`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18001051d`

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
  FARPROC ProcAddress; // rax
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
        FreeLibrary(Library);
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
    ProcAddress = GetProcAddress(v6, v11);
    v8 = (__int64)ProcAddress;
    if ( ProcAddress )
    {
      *a2 = ProcAddress;
      return v8;
    }
    return DelayLoadFailureHook(v9, v11);
  }
  return result;
}

```

## disassembly

```asm
0x1800103e0  mov     r11, rsp
0x1800103e3  mov     [r11+10h], rbx
0x1800103e7  mov     [r11+20h], rbp
0x1800103eb  push    rsi
0x1800103ec  push    rdi
0x1800103ed  push    r12
0x1800103ef  push    r14
0x1800103f1  push    r15
0x1800103f3  sub     rsp, 70h
0x1800103f7  mov     eax, [rcx+8]
0x1800103fa  lea     r8, [r11+8]
0x1800103fe  mov     esi, [rcx+4]
0x180010401  mov     r14, rdx
0x180010404  mov     r15d, [rcx+0Ch]
0x180010408  lea     rdx, __ImageBase
0x18001040f  mov     r12d, [rcx+10h]
0x180010413  add     rax, rdx
0x180010416  mov     [rsp+98h+arg_10], rax
0x18001041e  mov     rdx, r14
0x180010421  mov     rax, [rsp+98h+arg_10]
0x180010429  mov     byte ptr [r11+8], 0
0x18001042e  mov     rdi, [rax]
0x180010431  call    Dload__delayLoadHelper2
0x180010436  cmp     [rsp+98h+arg_0], 0
0x18001043e  mov     rbx, rax
0x180010441  jnz     loc_180010529
0x180010447  lea     r8, __ImageBase
0x18001044e  mov     rcx, r14
0x180010451  sub     rcx, r15
0x180010454  lea     rbp, [r8+rsi]
0x180010458  sub     rcx, r8
0x18001045b  sar     rcx, 3
0x18001045f  mov     ecx, ecx
0x180010461  lea     rdx, [r12+rcx*8]
0x180010465  cmp     qword ptr [rdx+r8], 0
0x18001046a  jl      short loc_18001047C
0x18001046c  mov     esi, [rdx+r8]
0x180010470  lea     rax, word_180000002
0x180010477  add     rsi, rax
0x18001047a  jmp     short loc_180010481
0x18001047c  movzx   esi, word ptr [rdx+r8]
0x180010481  test    rdi, rdi
0x180010484  jnz     short loc_1800104EB
0x180010486  xor     r8d, r8d; dwFlags
0x180010489  xor     edx, edx; hFile
0x18001048b  mov     rcx, rbp; lpLibFileName
0x18001048e  call    cs:__imp_LoadLibraryExA
0x180010494  mov     rdi, rax
0x180010497  test    rax, rax
0x18001049a  jz      short loc_180010512
0x18001049c  mov     rcx, [rsp+98h+arg_10]
0x1800104a4  xor     eax, eax
0x1800104a6  lock cmpxchg [rcx], rdi
0x1800104ab  mov     rbx, rax
0x1800104ae  jnz     short loc_180010504
0x1800104b0  mov     ebx, 48h ; 'H'
0x1800104b5  lea     rcx, [rsp+98h+var_78]; void *
0x1800104ba  mov     r8d, ebx; Size
0x1800104bd  xor     edx, edx; Val
0x1800104bf  call    memset_0
0x1800104c4  mov     rax, cs:__pfnDliNotifyHook2
0x1800104cb  mov     [rsp+98h+var_78], ebx
0x1800104cf  mov     [rsp+98h+var_60], rbp
0x1800104d4  mov     [rsp+98h+var_48], rdi
0x1800104d9  test    rax, rax
0x1800104dc  jz      short loc_1800104EB
0x1800104de  lea     rdx, [rsp+98h+var_78]
0x1800104e3  lea     ecx, [rbx-43h]
0x1800104e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104eb  mov     rdx, rsi; lpProcName
0x1800104ee  mov     rcx, rdi; hModule
0x1800104f1  call    cs:__imp_GetProcAddress
0x1800104f7  mov     rbx, rax
0x1800104fa  test    rax, rax
0x1800104fd  jz      short loc_180010517
0x1800104ff  mov     [r14], rax
0x180010502  jmp     short loc_180010526
0x180010504  mov     rcx, rdi; hLibModule
0x180010507  call    cs:__imp_FreeLibrary
0x18001050d  mov     rdi, rbx
0x180010510  jmp     short loc_1800104EB
0x180010512  test    rbx, rbx
0x180010515  jnz     short loc_180010526
0x180010517  mov     rdx, rsi
0x18001051a  mov     rcx, rbp
0x18001051d  call    cs:__imp_DelayLoadFailureHook
0x180010523  mov     rbx, rax
0x180010526  mov     rax, rbx
0x180010529  lea     r11, [rsp+98h+var_28]
0x18001052e  mov     rbx, [r11+38h]
0x180010532  mov     rbp, [r11+48h]
0x180010536  mov     rsp, r11
0x180010539  pop     r15
0x18001053b  pop     r14
0x18001053d  pop     r12
0x18001053f  pop     rdi
0x180010540  pop     rsi
0x180010541  retn
```
