# AesRNGState_init

- ea: `0x18004e9d8`
- end: `0x18004ea48`
- name: `AesRNGState_init`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004e884`

## callees

- `0x18002dee4`
- `0x18004e9d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004e9fa`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004e9fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ea24`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ea24`

## pseudocode

```c
__int64 __fastcall AesRNGState_init(__int64 a1, __int64 a2, __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v7; // ebx

  v3 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
  *(_DWORD *)a1 = 304;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
  if ( (unsigned int)SymCryptRngAesFips140_2Instantiate(a1 + 16, a2, 48) )
  {
    v7 = -1073741595;
    DeleteCriticalSection(v3);
  }
  else
  {
    v7 = 0;
    *(_QWORD *)(a1 + 120) = a3;
    *(_QWORD *)(a1 + 112) = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18004e9d8  push    rbx
0x18004e9da  push    rbp
0x18004e9db  push    rsi
0x18004e9dc  push    rdi
0x18004e9dd  sub     rsp, 28h
0x18004e9e1  lea     rsi, [rcx+80h]
0x18004e9e8  mov     dword ptr [rcx], 130h
0x18004e9ee  mov     rdi, rcx
0x18004e9f1  mov     rbp, r8
0x18004e9f4  mov     rcx, rsi; lpCriticalSection
0x18004e9f7  mov     rbx, rdx
0x18004e9fa  call    cs:__imp_InitializeCriticalSection
0x18004ea01  nop     dword ptr [rax+rax+00h]
0x18004ea06  lea     rcx, [rdi+10h]
0x18004ea0a  mov     r8d, 30h ; '0'
0x18004ea10  mov     rdx, rbx
0x18004ea13  call    SymCryptRngAesFips140_2Instantiate
0x18004ea18  test    eax, eax
0x18004ea1a  jz      short loc_18004EA32
0x18004ea1c  mov     rcx, rsi; lpCriticalSection
0x18004ea1f  mov     ebx, 0C00000E5h
0x18004ea24  call    cs:__imp_DeleteCriticalSection
0x18004ea2b  nop     dword ptr [rax+rax+00h]
0x18004ea30  jmp     short loc_18004EA3C
0x18004ea32  xor     ebx, ebx
0x18004ea34  mov     [rdi+78h], rbp
0x18004ea38  mov     [rdi+70h], rbx
0x18004ea3c  mov     eax, ebx
0x18004ea3e  add     rsp, 28h
0x18004ea42  pop     rdi
0x18004ea43  pop     rsi
0x18004ea44  pop     rbp
0x18004ea45  pop     rbx
0x18004ea46  retn
```
