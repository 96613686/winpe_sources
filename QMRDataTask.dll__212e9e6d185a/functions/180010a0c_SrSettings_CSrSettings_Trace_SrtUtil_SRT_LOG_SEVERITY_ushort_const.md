# SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)

- ea: `0x180010a0c`
- end: `0x180010aec`
- name: `?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ`
- size: `224`
- prototype: `__int64(_QWORD, _QWORD, _QWORD, ...)`
- caller_count: `27`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18000687c`
- `0x180006a60`
- `0x180006c00`
- `0x180006e00`
- `0x180006eb0`
- `0x180006f40`
- `0x180006fe0`
- `0x180007490`
- `0x180009494`
- `0x180009ec8`
- `0x18000a1c0`
- `0x18000a520`
- `0x18000a8c0`
- `0x18000ace0`
- `0x18000b290`
- `0x18000c260`
- `0x18000c410`
- `0x18000e074`
- `0x18000ea9c`
- `0x18000ebf8`
- `0x18000ef08`
- `0x18000f170`
- `0x18000f1f0`
- `0x18000f270`
- `0x18000f330`
- `0x18000f418`
- `0x180010400`

## callees

- `0x180002138`
- `0x180010a0c`
- `0x180015010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180010aaf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180010adb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180010aaf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180010adb`
- `msvcrt!_vsnwprintf` at `0x180010a7c`
- `msvcrt!_vsnwprintf` at `0x180010a7c`
- `msvcrt!_vscwprintf` at `0x180010a32`
- `msvcrt!_vscwprintf` at `0x180010a32`

## pseudocode

```c
void SrSettings::CSrSettings::Trace(__int64 a1, unsigned int a2, const wchar_t *a3, ...)
{
  wchar_t *v5; // rbx
  unsigned int v6; // eax
  unsigned __int64 v7; // rdi
  wchar_t *v8; // rax
  size_t v9; // rdi
  int v10; // eax
  int v11; // ecx
  void (__fastcall ***v12)(_QWORD, _QWORD, wchar_t *); // rcx
  va_list ArgList; // [rsp+78h] [rbp+20h] BYREF

  va_start(ArgList, a3);
  v5 = 0;
  v6 = _vscwprintf(a3, ArgList) + 1;
  if ( v6 )
  {
    v7 = v6;
    v8 = (wchar_t *)operator new[](saturated_mul(v6, 2u));
    v5 = v8;
    if ( v8 )
    {
      if ( v7 > 0x7FFFFFFF )
      {
        *v8 = 0;
LABEL_13:
        operator delete[](v5);
        v5 = 0;
        goto LABEL_14;
      }
      v9 = v7 - 1;
      v10 = _vsnwprintf(v8, v9, a3, ArgList);
      if ( v10 < 0 || v10 > v9 )
      {
        v11 = -2147024774;
      }
      else
      {
        v11 = 0;
        if ( v10 != v9 )
          goto LABEL_10;
      }
      v5[v9] = 0;
LABEL_10:
      if ( v11 >= 0 )
        goto LABEL_14;
      goto LABEL_13;
    }
  }
LABEL_14:
  if ( v5 )
  {
    v12 = *(void (__fastcall ****)(_QWORD, _QWORD, wchar_t *))(a1 + 3952);
    if ( v12 )
      (**v12)(v12, a2, v5);
    operator delete[](v5);
  }
}

```

## disassembly

```asm
0x180010a0c  mov     [rsp+Format], r8
0x180010a11  mov     qword ptr [rsp+ArgList], r9
0x180010a16  push    rbx
0x180010a17  push    rbp
0x180010a18  push    rsi
0x180010a19  push    rdi
0x180010a1a  push    r14
0x180010a1c  sub     rsp, 30h
0x180010a20  mov     ebp, edx
0x180010a22  lea     r14, [rsp+58h+ArgList]
0x180010a27  mov     rsi, rcx
0x180010a2a  mov     rdx, r14; ArgList
0x180010a2d  mov     rcx, r8; Format
0x180010a30  xor     ebx, ebx
0x180010a32  call    cs:__imp__vscwprintf
0x180010a38  add     eax, 1
0x180010a3b  jz      short loc_180010AB7
0x180010a3d  mov     edi, eax
0x180010a3f  lea     rcx, [rbx-1]
0x180010a43  lea     eax, [rbx+2]
0x180010a46  mul     rdi
0x180010a49  cmovb   rax, rcx
0x180010a4d  mov     rcx, rax; unsigned __int64
0x180010a50  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010a55  mov     rbx, rax
0x180010a58  test    rax, rax
0x180010a5b  jz      short loc_180010AB7
0x180010a5d  test    rdi, rdi
0x180010a60  jz      short loc_180010AAC
0x180010a62  cmp     rdi, 7FFFFFFFh
0x180010a69  ja      short loc_180010AA7
0x180010a6b  mov     r8, [rsp+58h+Format]; Format
0x180010a70  dec     rdi
0x180010a73  mov     rdx, rdi; BufferCount
0x180010a76  mov     r9, r14; Args
0x180010a79  mov     rcx, rax; Buffer
0x180010a7c  call    cs:__imp__vsnwprintf
0x180010a82  test    eax, eax
0x180010a84  js      short loc_180010A96
0x180010a86  cdqe
0x180010a88  cmp     rax, rdi
0x180010a8b  ja      short loc_180010A96
0x180010a8d  xor     ecx, ecx
0x180010a8f  cmp     rax, rdi
0x180010a92  jnz     short loc_180010AA1
0x180010a94  jmp     short loc_180010A9B
0x180010a96  mov     ecx, 8007007Ah
0x180010a9b  xor     eax, eax
0x180010a9d  mov     [rbx+rdi*2], ax
0x180010aa1  test    ecx, ecx
0x180010aa3  jns     short loc_180010AB7
0x180010aa5  jmp     short loc_180010AAC
0x180010aa7  xor     eax, eax
0x180010aa9  mov     [rbx], ax
0x180010aac  mov     rcx, rbx
0x180010aaf  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180010ab5  xor     ebx, ebx
0x180010ab7  test    rbx, rbx
0x180010aba  jz      short loc_180010AE1
0x180010abc  mov     rcx, [rsi+0F70h]
0x180010ac3  test    rcx, rcx
0x180010ac6  jz      short loc_180010AD8
0x180010ac8  mov     rax, [rcx]
0x180010acb  mov     r8, rbx
0x180010ace  mov     edx, ebp
0x180010ad0  mov     rax, [rax]
0x180010ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ad8  mov     rcx, rbx
0x180010adb  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180010ae1  add     rsp, 30h
0x180010ae5  pop     r14
0x180010ae7  pop     rdi
0x180010ae8  pop     rsi
0x180010ae9  pop     rbp
0x180010aea  pop     rbx
0x180010aeb  retn
```
