# CopyStringW(ushort const *,unsigned __int64,ushort * *)

- ea: `0x18000ad2c`
- end: `0x18000ae58`
- name: `?CopyStringW@@YAJPEBG_KPEAPEAG@Z`
- size: `300`
- prototype: `__int64 __fastcall(const unsigned __int16 *Source, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001a0a4`

## callees

- `0x18000ad2c`
- `0x18000ae60`
- `0x18000b3c4`
- `0x18000ede8`
- `0x180019bd8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ae46`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ae46`
- `msvcrt!memcpy_s` at `0x18000ae04`
- `msvcrt!memcpy_s` at `0x18000ae04`

## string_xrefs

- `0x18000ad52`: `CopyStringW`
- `0x18000ad6c`: `CopyStringW`
- `0x18000ad91`: `CopyStringW`
- `0x18000addb`: `CopyStringW`
- `0x18000ae13`: `CopyStringW`

## pseudocode

```c
__int64 __fastcall CopyStringW(const unsigned __int16 *Source, __int64 a2, unsigned __int16 **a3)
{
  unsigned __int16 *v3; // rdi
  signed int v7; // ebx
  const unsigned __int16 *v8; // rdx
  unsigned __int64 v9; // rax
  unsigned __int16 *v10; // rax
  rsize_t v11; // r14
  unsigned int v12; // eax

  v3 = 0;
  if ( !a3 )
  {
    v7 = -2147024809;
    Logger::TraceError((const unsigned __int16 *)&stru_18001E5B8.hCertStore, L"CopyStringW", L"pDest");
    v8 = L"pDest";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringW", v8);
    goto LABEL_14;
  }
  *a3 = 0;
  if ( !Source )
  {
    v7 = -2147024809;
    Logger::TraceError((const unsigned __int16 *)&stru_18001E5B8.hCertStore, L"CopyStringW", L"source");
    v8 = L"source";
    goto LABEL_3;
  }
  v9 = 2 * (a2 + 1);
  if ( !is_mul_ok(a2 + 1, 2u) )
    v9 = -1;
  v10 = (unsigned __int16 *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v10;
  if ( v10 )
  {
    v11 = 2 * a2;
    v12 = memcpy_s(v10, v11, Source, v11);
    v7 = v12;
    if ( v12 )
    {
      Logger::TraceError(L"%s: wmemcpy_s failed with error code: 0x%08x.", L"CopyStringW", v12);
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
    }
    else
    {
      *a3 = v3;
      v7 = 0;
      v3[v11 / 2] = 0;
      v3 = 0;
    }
  }
  else
  {
    v7 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"CopyStringW");
  }
LABEL_14:
  operator delete(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000ad2c  push    rbx
0x18000ad2e  push    rsi
0x18000ad2f  push    rdi
0x18000ad30  push    r14
0x18000ad32  sub     rsp, 28h
0x18000ad36  xor     edi, edi
0x18000ad38  mov     rsi, r8
0x18000ad3b  mov     r14, rdx
0x18000ad3e  mov     rbx, rcx
0x18000ad41  test    r8, r8
0x18000ad44  jnz     short loc_18000AD7D
0x18000ad46  lea     r8, aPdest; "pDest"
0x18000ad4d  mov     ebx, 80070057h
0x18000ad52  lea     rdx, aCopystringw; "CopyStringW"
0x18000ad59  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x18000ad60  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000ad65  lea     rdx, aPdest; "pDest"
0x18000ad6c  lea     rcx, aCopystringw; "CopyStringW"
0x18000ad73  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18000ad78  jmp     loc_18000AE43
0x18000ad7d  mov     [r8], rdi
0x18000ad80  test    rbx, rbx
0x18000ad83  jnz     short loc_18000ADAD
0x18000ad85  lea     r8, aSource; "source"
0x18000ad8c  mov     ebx, 80070057h
0x18000ad91  lea     rdx, aCopystringw; "CopyStringW"
0x18000ad98  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x18000ad9f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000ada4  lea     rdx, aSource; "source"
0x18000adab  jmp     short loc_18000AD6C
0x18000adad  lea     rcx, [rdx+1]
0x18000adb1  mov     eax, 2
0x18000adb6  mul     rcx
0x18000adb9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000adc0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000adc7  cmovb   rax, rcx
0x18000adcb  mov     rcx, rax; unsigned __int64
0x18000adce  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000add3  mov     rdi, rax
0x18000add6  test    rax, rax
0x18000add9  jnz     short loc_18000ADF5
0x18000addb  lea     rdx, aCopystringw; "CopyStringW"
0x18000ade2  mov     ebx, 8007000Eh
0x18000ade7  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18000adee  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18000adf3  jmp     short loc_18000AE43
0x18000adf5  add     r14, r14
0x18000adf8  mov     r8, rbx; Source
0x18000adfb  mov     r9, r14; SourceSize
0x18000adfe  mov     rdx, r14; DestinationSize
0x18000ae01  mov     rcx, rdi; Destination
0x18000ae04  call    cs:__imp_memcpy_s
0x18000ae0a  mov     ebx, eax
0x18000ae0c  test    eax, eax
0x18000ae0e  jz      short loc_18000AE35
0x18000ae10  mov     r8d, eax
0x18000ae13  lea     rdx, aCopystringw; "CopyStringW"
0x18000ae1a  lea     rcx, aSWmemcpySFaile; "%s: wmemcpy_s failed with error code: 0"...
0x18000ae21  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000ae26  test    ebx, ebx
0x18000ae28  jle     short loc_18000AE43
0x18000ae2a  movzx   ebx, bx
0x18000ae2d  or      ebx, 80070000h
0x18000ae33  jmp     short loc_18000AE43
0x18000ae35  xor     ecx, ecx
0x18000ae37  mov     [rsi], rdi
0x18000ae3a  xor     ebx, ebx
0x18000ae3c  mov     [r14+rdi], cx
0x18000ae41  xor     edi, edi
0x18000ae43  mov     rcx, rdi
0x18000ae46  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ae4c  mov     eax, ebx
0x18000ae4e  add     rsp, 28h
0x18000ae52  pop     r14
0x18000ae54  pop     rdi
0x18000ae55  pop     rsi
0x18000ae56  pop     rbx
0x18000ae57  retn
```
