# Decoder_CreateInstance(_GUID const &,void * *)

- ea: `0x180002090`
- end: `0x180002174`
- name: `?Decoder_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `228`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001424`
- `0x180002090`
- `0x1800029b4`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000213b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000213b`

## pseudocode

```c
__int64 __fastcall Decoder_CreateInstance(const struct _GUID *a1, void **a2)
{
  unsigned int v4; // edi
  char *v5; // rbx

  if ( a2 )
  {
    if ( (unsigned int)IsLicensedAMRSKU() )
    {
      v5 = (char *)operator new(0xA8u);
      *(_QWORD *)v5 = &CAMRNBDecoder::`vftable';
      *((_QWORD *)v5 + 1) = 0;
      *((_DWORD *)v5 + 4) = 1;
      *((_QWORD *)v5 + 3) = 0;
      *((_QWORD *)v5 + 4) = 0;
      *((_QWORD *)v5 + 5) = 0;
      *((_QWORD *)v5 + 11) = 0;
      *((_QWORD *)v5 + 12) = 0;
      *((_QWORD *)v5 + 13) = 0;
      *((_QWORD *)v5 + 14) = 0;
      *((_QWORD *)v5 + 15) = 0;
      *((_QWORD *)v5 + 16) = 0;
      *((_QWORD *)v5 + 17) = 0;
      *((_QWORD *)v5 + 18) = 0;
      *((_DWORD *)v5 + 38) = 0;
      *((_DWORD *)v5 + 39) = 2000;
      _InterlockedIncrement(&g_cRefModule);
      *((_DWORD *)v5 + 40) = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v5 + 48));
      *a2 = 0;
      v4 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v5)(v5, a1, a2);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
    }
    else
    {
      return (unsigned int)-1073418223;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v4;
}

```

## disassembly

```asm
0x180002090  push    rbx
0x180002092  push    rbp
0x180002093  push    rsi
0x180002094  push    rdi
0x180002095  sub     rsp, 28h
0x180002099  xor     ebp, ebp
0x18000209b  mov     rdi, rdx
0x18000209e  mov     rsi, rcx
0x1800020a1  test    rdx, rdx
0x1800020a4  jnz     short loc_1800020B0
0x1800020a6  mov     edi, 80004003h
0x1800020ab  jmp     loc_180002169
0x1800020b0  call    ?IsLicensedAMRSKU@@YAHXZ; IsLicensedAMRSKU(void)
0x1800020b5  test    eax, eax
0x1800020b7  jnz     short loc_1800020C3
0x1800020b9  mov     edi, 0C004F011h
0x1800020be  jmp     loc_180002169
0x1800020c3  mov     ecx, 0A8h; Size
0x1800020c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800020cd  mov     rbx, rax
0x1800020d0  lea     rax, ??_7CAMRNBDecoder@@6B@; const CAMRNBDecoder::`vftable'
0x1800020d7  mov     [rbx], rax
0x1800020da  mov     [rbx+8], rbp
0x1800020de  mov     dword ptr [rbx+10h], 1
0x1800020e5  mov     [rbx+18h], rbp
0x1800020e9  mov     [rbx+20h], rbp
0x1800020ed  mov     [rbx+28h], rbp
0x1800020f1  mov     [rbx+58h], rbp
0x1800020f5  mov     [rbx+60h], rbp
0x1800020f9  mov     [rbx+68h], rbp
0x1800020fd  mov     [rbx+70h], rbp
0x180002101  mov     [rbx+78h], rbp
0x180002105  mov     [rbx+80h], rbp
0x18000210c  mov     [rbx+88h], rbp
0x180002113  mov     [rbx+90h], rbp
0x18000211a  mov     [rbx+98h], ebp
0x180002120  mov     dword ptr [rbx+9Ch], 7D0h
0x18000212a  lock inc cs:?g_cRefModule@@3JA; long g_cRefModule
0x180002131  lea     rcx, [rbx+30h]; lpCriticalSection
0x180002135  mov     [rbx+0A0h], ebp
0x18000213b  call    cs:__imp_InitializeCriticalSection
0x180002141  mov     [rdi], rbp
0x180002144  mov     r8, rdi
0x180002147  mov     rax, [rbx]
0x18000214a  mov     rdx, rsi
0x18000214d  mov     rcx, rbx
0x180002150  mov     rax, [rax]
0x180002153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002158  mov     rcx, [rbx]
0x18000215b  mov     edi, eax
0x18000215d  mov     rax, [rcx+10h]
0x180002161  mov     rcx, rbx
0x180002164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002169  mov     eax, edi
0x18000216b  add     rsp, 28h
0x18000216f  pop     rdi
0x180002170  pop     rsi
0x180002171  pop     rbp
0x180002172  pop     rbx
0x180002173  retn
```
