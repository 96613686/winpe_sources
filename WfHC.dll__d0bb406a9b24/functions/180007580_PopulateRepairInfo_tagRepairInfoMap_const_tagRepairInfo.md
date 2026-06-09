# PopulateRepairInfo(tagRepairInfoMap const *,tagRepairInfo *)

- ea: `0x180007580`
- end: `0x180007669`
- name: `?PopulateRepairInfo@@YAJPEBUtagRepairInfoMap@@PEAUtagRepairInfo@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(const struct tagRepairInfoMap *, struct tagRepairInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800040b0`

## callees

- `0x180002576`
- `0x180007580`

## import_xrefs

- `msvcrt!wcsnlen` at `0x1800075cf`
- `msvcrt!wcsnlen` at `0x1800075cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800075e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000760d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800075e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000760d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007650`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007638`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000762e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000762e`

## pseudocode

```c
__int64 __fastcall PopulateRepairInfo(const struct tagRepairInfoMap *a1, struct tagRepairInfo *a2)
{
  SIZE_T v4; // rbp
  WCHAR *v5; // rax
  WCHAR *v6; // rdi
  unsigned int v7; // ebx
  WCHAR *v8; // rax
  WCHAR *v9; // rdi
  signed int LastError; // eax

  *a2 = *(struct tagRepairInfo *)((char *)a1 + 8);
  v4 = 2 * wcsnlen(*((const wchar_t **)a1 + 3), 0x100u) + 2;
  v5 = (WCHAR *)CoTaskMemAlloc(v4);
  v6 = v5;
  if ( v5
    && (memcpy_0(v5, *((const void **)a1 + 3), v4),
        a2->pwszClassName = v6,
        v8 = (WCHAR *)CoTaskMemAlloc(0x800u),
        (v9 = v8) != 0) )
  {
    if ( LoadStringW(hInstance, *((_DWORD *)a1 + 1), v8, 1024) )
    {
      v7 = 0;
      a2->pwszDescription = v9;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      CoTaskMemFree(v9);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x180007580  push    rbx
0x180007582  push    rbp
0x180007583  push    rsi
0x180007584  push    rdi
0x180007585  sub     rsp, 28h
0x180007589  movups  xmm0, xmmword ptr [rcx+8]
0x18000758d  mov     rsi, rdx
0x180007590  mov     rbx, rcx
0x180007593  movups  xmmword ptr [rdx], xmm0
0x180007596  movups  xmm1, xmmword ptr [rcx+18h]
0x18000759a  movups  xmmword ptr [rdx+10h], xmm1
0x18000759e  movups  xmm0, xmmword ptr [rcx+28h]
0x1800075a2  movups  xmmword ptr [rdx+20h], xmm0
0x1800075a6  movups  xmm1, xmmword ptr [rcx+38h]
0x1800075aa  movups  xmmword ptr [rdx+30h], xmm1
0x1800075ae  movups  xmm0, xmmword ptr [rcx+48h]
0x1800075b2  movups  xmmword ptr [rdx+40h], xmm0
0x1800075b6  movups  xmm1, xmmword ptr [rcx+58h]
0x1800075ba  movups  xmmword ptr [rdx+50h], xmm1
0x1800075be  movups  xmm0, xmmword ptr [rcx+68h]
0x1800075c2  movups  xmmword ptr [rdx+60h], xmm0
0x1800075c6  mov     rcx, [rcx+18h]; Source
0x1800075ca  mov     edx, 100h; MaxCount
0x1800075cf  call    cs:__imp_wcsnlen
0x1800075d5  lea     rbp, ds:2[rax*2]
0x1800075dd  mov     rcx, rbp; cb
0x1800075e0  call    cs:__imp_CoTaskMemAlloc
0x1800075e6  mov     rdi, rax
0x1800075e9  test    rax, rax
0x1800075ec  jnz     short loc_1800075F5
0x1800075ee  mov     ebx, 8007000Eh
0x1800075f3  jmp     short loc_18000765E
0x1800075f5  mov     rdx, [rbx+18h]; Src
0x1800075f9  mov     r8, rbp; Size
0x1800075fc  mov     rcx, rdi; void *
0x1800075ff  call    memcpy_0
0x180007604  mov     ecx, 800h; cb
0x180007609  mov     [rsi+10h], rdi
0x18000760d  call    cs:__imp_CoTaskMemAlloc
0x180007613  mov     rdi, rax
0x180007616  test    rax, rax
0x180007619  jz      short loc_1800075EE
0x18000761b  mov     edx, [rbx+4]; uID
0x18000761e  mov     r9d, 400h; cchBufferMax
0x180007624  mov     rcx, cs:hInstance; hInstance
0x18000762b  mov     r8, rax; lpBuffer
0x18000762e  call    cs:__imp_LoadStringW
0x180007634  test    eax, eax
0x180007636  jnz     short loc_180007658
0x180007638  call    cs:__imp_GetLastError
0x18000763e  mov     ebx, eax
0x180007640  test    eax, eax
0x180007642  jle     short loc_18000764D
0x180007644  movzx   ebx, ax
0x180007647  or      ebx, 80070000h
0x18000764d  mov     rcx, rdi; pv
0x180007650  call    cs:__imp_CoTaskMemFree
0x180007656  jmp     short loc_18000765E
0x180007658  xor     ebx, ebx
0x18000765a  mov     [rsi+18h], rdi
0x18000765e  mov     eax, ebx
0x180007660  add     rsp, 28h
0x180007664  pop     rdi
0x180007665  pop     rsi
0x180007666  pop     rbp
0x180007667  pop     rbx
0x180007668  retn
```
