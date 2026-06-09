# CCoMemString::Assign(ushort const *)

- ea: `0x180007800`
- end: `0x1800078d0`
- name: `?Assign@CCoMemString@@QEAAJPEBG@Z`
- size: `208`
- prototype: `int(CCoMemString *__hidden this, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800061f0`
- `0x180006770`
- `0x18003493c`
- `0x18003598c`
- `0x180035ba8`

## callees

- `0x180007800`
- `0x180027678`
- `0x1800276d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007857`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007857`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800078a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800078bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800078a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800078bd`

## pseudocode

```c
__int64 __fastcall CCoMemString::Assign(LPVOID *this, const unsigned __int16 *a2)
{
  void *v4; // rcx
  __int64 v5; // rax
  SIZE_T v7; // rbp
  const wchar_t *v8; // rax
  size_t v9; // r8
  unsigned int v10; // edi
  size_t v12; // rbp
  HRESULT v13; // eax
  size_t v14; // rdx
  wchar_t *v15; // rcx
  size_t *v16; // r8
  size_t v17; // [rsp+20h] [rbp-18h]

  v4 = *this;
  if ( v4 )
    CoTaskMemFree(v4);
  *this = 0;
  if ( a2 )
  {
    v5 = -1;
    while ( a2[++v5] != 0 )
      ;
    v7 = 2 * v5 + 2;
    v8 = (const wchar_t *)CoTaskMemAlloc(v7);
    *this = (LPVOID)v8;
    if ( !v8 )
      return (unsigned int)-2147024882;
    v12 = v7 >> 1;
    v13 = StringValidateDestW(v8, v12, v9);
    v10 = v13;
    if ( v13 < 0 )
    {
      if ( v12 )
      {
        *v15 = 0;
        goto LABEL_15;
      }
    }
    else
    {
      v13 = StringCopyWorkerW_0(v15, v14, v16, a2, v17);
    }
    v10 = v13;
    if ( !v13 )
      return v10;
LABEL_15:
    CoTaskMemFree(*this);
    *this = 0;
    return v10;
  }
  return 0;
}

```

## disassembly

```asm
0x180007800  mov     [rsp+arg_10], rbx
0x180007805  push    rsi
0x180007806  sub     rsp, 30h
0x18000780a  mov     rsi, rcx
0x18000780d  mov     rbx, rdx
0x180007810  mov     rcx, [rcx]; pv
0x180007813  test    rcx, rcx
0x180007816  jnz     loc_1800078A5
0x18000781c  mov     qword ptr [rsi], 0
0x180007823  test    rbx, rbx
0x180007826  jz      loc_1800078CC
0x18000782c  mov     [rsp+38h+arg_0], rbp
0x180007831  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180007838  mov     [rsp+38h+arg_8], rdi
0x18000783d  nop     dword ptr [rax]
0x180007840  cmp     word ptr [rbx+rax*2+2], 0
0x180007846  lea     rax, [rax+1]
0x18000784a  jnz     short loc_180007840
0x18000784c  lea     rbp, ds:2[rax*2]
0x180007854  mov     rcx, rbp; cb
0x180007857  call    cs:__imp_CoTaskMemAlloc
0x18000785d  mov     [rsi], rax
0x180007860  mov     rcx, rax; pszDest
0x180007863  test    rax, rax
0x180007866  jnz     short loc_180007884
0x180007868  mov     edi, 8007000Eh
0x18000786d  mov     rbp, [rsp+38h+arg_0]
0x180007872  mov     eax, edi
0x180007874  mov     rdi, [rsp+38h+arg_8]
0x180007879  mov     rbx, [rsp+38h+arg_10]
0x18000787e  add     rsp, 30h
0x180007882  pop     rsi
0x180007883  retn
0x180007884  shr     rbp, 1
0x180007887  mov     rdx, rbp; cchDest
0x18000788a  call    StringValidateDestW
0x18000788f  mov     edi, eax
0x180007891  test    eax, eax
0x180007893  js      short loc_1800078B0
0x180007895  mov     r9, rbx; pszSrc
0x180007898  call    StringCopyWorkerW_0
0x18000789d  mov     edi, eax
0x18000789f  test    eax, eax
0x1800078a1  jz      short loc_18000786D
0x1800078a3  jmp     short loc_1800078BA
0x1800078a5  call    cs:__imp_CoTaskMemFree
0x1800078ab  jmp     loc_18000781C
0x1800078b0  test    rbp, rbp
0x1800078b3  jz      short loc_18000789D
0x1800078b5  xor     eax, eax
0x1800078b7  mov     [rcx], ax
0x1800078ba  mov     rcx, [rsi]; pv
0x1800078bd  call    cs:__imp_CoTaskMemFree
0x1800078c3  mov     qword ptr [rsi], 0
0x1800078ca  jmp     short loc_18000786D
0x1800078cc  xor     eax, eax
0x1800078ce  jmp     short loc_180007879
```
