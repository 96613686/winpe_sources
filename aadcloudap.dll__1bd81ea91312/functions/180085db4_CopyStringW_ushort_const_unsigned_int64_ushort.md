# CopyStringW(ushort const *,unsigned __int64,ushort * *)

- ea: `0x180085db4`
- end: `0x180085edf`
- name: `?CopyStringW@@YAJPEBG_KPEAPEAG@Z`
- size: `299`
- prototype: `__int64 __fastcall(const unsigned __int16 *Source, unsigned __int64, unsigned __int16 **)`
- caller_count: `13`
- callee_count: `6`
- tags: ``

## callers

- `0x180085cc4`
- `0x180085ee8`
- `0x180086454`
- `0x180087764`
- `0x1800909c4`
- `0x180095ee0`
- `0x18009746c`
- `0x180097bd8`
- `0x180099120`
- `0x18009a318`
- `0x18009d3a8`
- `0x18009e138`
- `0x18009e4ac`

## callees

- `0x1800049d0`
- `0x180005f24`
- `0x180085db4`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aecc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180085ecd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180085ecd`

## string_xrefs

- `0x180085dda`: `CopyStringW`
- `0x180085df4`: `CopyStringW`
- `0x180085e19`: `CopyStringW`
- `0x180085e63`: `CopyStringW`
- `0x180085e9a`: `CopyStringW`

## pseudocode

```c
__int64 __fastcall CopyStringW(const unsigned __int16 *Source, __int64 a2, unsigned __int16 **a3)
{
  unsigned __int16 *v3; // rdi
  signed int v7; // ebx
  const unsigned __int16 *v8; // rdx
  size_t v9; // rax
  unsigned __int16 *v10; // rax
  rsize_t v11; // r14
  unsigned int v12; // eax

  v3 = 0;
  if ( !a3 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringW", L"pDest");
    v8 = L"pDest";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringW", v8);
    goto LABEL_14;
  }
  *a3 = 0;
  if ( !Source )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringW", L"source");
    v8 = L"source";
    goto LABEL_3;
  }
  v9 = 2 * (a2 + 1);
  if ( !is_mul_ok(a2 + 1, 2u) )
    v9 = -1;
  v10 = (unsigned __int16 *)operator new[](v9, (const struct std::nothrow_t *)std::nothrow);
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
      v7 = 0;
      v3[v11 / 2] = 0;
      *a3 = v3;
      v3 = 0;
    }
  }
  else
  {
    v7 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"CopyStringW");
  }
LABEL_14:
  free(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180085db4  push    rbx
0x180085db6  push    rsi
0x180085db7  push    rdi
0x180085db8  push    r14
0x180085dba  sub     rsp, 28h
0x180085dbe  xor     edi, edi
0x180085dc0  mov     rsi, r8
0x180085dc3  mov     r14, rdx
0x180085dc6  mov     rbx, rcx
0x180085dc9  test    r8, r8
0x180085dcc  jnz     short loc_180085E05
0x180085dce  lea     r8, aPdest; "pDest"
0x180085dd5  mov     ebx, 80070057h
0x180085dda  lea     rdx, aCopystringw; "CopyStringW"
0x180085de1  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180085de8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180085ded  lea     rdx, aPdest; "pDest"
0x180085df4  lea     rcx, aCopystringw; "CopyStringW"
0x180085dfb  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180085e00  jmp     loc_180085ECA
0x180085e05  mov     [r8], rdi
0x180085e08  test    rbx, rbx
0x180085e0b  jnz     short loc_180085E35
0x180085e0d  lea     r8, aSource; "source"
0x180085e14  mov     ebx, 80070057h
0x180085e19  lea     rdx, aCopystringw; "CopyStringW"
0x180085e20  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180085e27  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180085e2c  lea     rdx, aSource; "source"
0x180085e33  jmp     short loc_180085DF4
0x180085e35  lea     rcx, [rdx+1]
0x180085e39  mov     eax, 2
0x180085e3e  mul     rcx
0x180085e41  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180085e48  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180085e4f  cmovb   rax, rcx
0x180085e53  mov     rcx, rax; unsigned __int64
0x180085e56  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180085e5b  mov     rdi, rax
0x180085e5e  test    rax, rax
0x180085e61  jnz     short loc_180085E7D
0x180085e63  lea     rdx, aCopystringw; "CopyStringW"
0x180085e6a  mov     ebx, 8007000Eh
0x180085e6f  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180085e76  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180085e7b  jmp     short loc_180085ECA
0x180085e7d  add     r14, r14
0x180085e80  mov     r8, rbx; Source
0x180085e83  mov     r9, r14; SourceSize
0x180085e86  mov     rdx, r14; DestinationSize
0x180085e89  mov     rcx, rdi; Destination
0x180085e8c  call    memcpy_s
0x180085e91  mov     ebx, eax
0x180085e93  test    eax, eax
0x180085e95  jz      short loc_180085EBC
0x180085e97  mov     r8d, eax
0x180085e9a  lea     rdx, aCopystringw; "CopyStringW"
0x180085ea1  lea     rcx, aSWmemcpySFaile; "%s: wmemcpy_s failed with error code: 0"...
0x180085ea8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180085ead  test    ebx, ebx
0x180085eaf  jle     short loc_180085ECA
0x180085eb1  movzx   ebx, bx
0x180085eb4  or      ebx, 80070000h
0x180085eba  jmp     short loc_180085ECA
0x180085ebc  xor     ecx, ecx
0x180085ebe  xor     ebx, ebx
0x180085ec0  mov     [r14+rdi], cx
0x180085ec5  mov     [rsi], rdi
0x180085ec8  xor     edi, edi
0x180085eca  mov     rcx, rdi; Block
0x180085ecd  call    cs:__imp_free
0x180085ed3  mov     eax, ebx
0x180085ed5  add     rsp, 28h
0x180085ed9  pop     r14
0x180085edb  pop     rdi
0x180085edc  pop     rsi
0x180085edd  pop     rbx
0x180085ede  retn
```
