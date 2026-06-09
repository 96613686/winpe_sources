# CMetadataAPEReaderWriter::GetValue(uint,tagPROPVARIANT *)

- ea: `0x1801ad4d0`
- end: `0x1801ad5ad`
- name: `?GetValue@CMetadataAPEReaderWriter@@MEAAJIPEAUtagPROPVARIANT@@@Z`
- size: `221`
- prototype: `int(CMetadataAPEReaderWriter *__hidden this, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800bd9d4`
- `0x18017e438`
- `0x1801ad4d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801ad50c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801ad50c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ad54a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ad54a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801ad58e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801ad58e`

## pseudocode

```c
__int64 __fastcall CMetadataAPEReaderWriter::GetValue(CMetadataAPEReaderWriter *this, int a2, PROPVARIANT *a3)
{
  unsigned int v3; // ebx
  int v6; // edx
  HRESULT v7; // eax
  int v8; // ecx
  BYTE *v9; // rax

  v3 = 0;
  v6 = a2 - 1;
  if ( !v6 )
  {
    if ( !*((_DWORD *)this + 41) )
    {
      PropVariantClear(a3);
      return v3;
    }
    *((_DWORD *)a3 + 2) = 11;
    v9 = (BYTE *)CoTaskMemAlloc(0xBu);
    a3[2] = v9;
    if ( v9 )
    {
      memcpy_0(v9, (char *)this + 152, *((unsigned int *)a3 + 2));
      return v3;
    }
    v3 = -2147024882;
LABEL_12:
    if ( (_DWORD)g_doStackCaptures )
    {
      v8 = v3;
      goto LABEL_14;
    }
    return v3;
  }
  if ( v6 != 1 )
  {
    v3 = -2147024809;
    goto LABEL_12;
  }
  if ( *((_WORD *)this + 84) == 4113 )
  {
    v7 = PropVariantCopy(a3, (const PROPVARIANT *)this + 21);
    v3 = v7;
    if ( v7 < 0 && (_DWORD)g_doStackCaptures )
    {
      v8 = v7;
LABEL_14:
      DoStackCapture(v8);
    }
  }
  else
  {
    *(_WORD *)a3 = 4113;
    *((_DWORD *)a3 + 2) = 0;
    a3[2] = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x1801ad4d0  mov     [rsp+arg_0], rbx
0x1801ad4d5  mov     [rsp+arg_8], rsi
0x1801ad4da  push    rdi
0x1801ad4db  sub     rsp, 20h
0x1801ad4df  xor     ebx, ebx
0x1801ad4e1  mov     rdi, r8
0x1801ad4e4  mov     rsi, rcx
0x1801ad4e7  sub     edx, 1
0x1801ad4ea  jz      short loc_1801AD539
0x1801ad4ec  cmp     edx, 1
0x1801ad4ef  jz      short loc_1801AD4F8
0x1801ad4f1  mov     ebx, 80070057h
0x1801ad4f6  jmp     short loc_1801AD564
0x1801ad4f8  lea     rdx, [rcx+0A8h]; pvarSrc
0x1801ad4ff  mov     eax, 1011h
0x1801ad504  cmp     [rdx], ax
0x1801ad507  jnz     short loc_1801AD52B
0x1801ad509  mov     rcx, rdi; pvarDest
0x1801ad50c  call    cs:__imp_PropVariantCopy
0x1801ad513  nop     dword ptr [rax+rax+00h]
0x1801ad518  mov     ebx, eax
0x1801ad51a  test    eax, eax
0x1801ad51c  jns     short loc_1801AD59A
0x1801ad51e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801ad525  jz      short loc_1801AD59A
0x1801ad527  mov     ecx, eax
0x1801ad529  jmp     short loc_1801AD56F
0x1801ad52b  mov     [r8], ax
0x1801ad52f  mov     [r8+8], ebx
0x1801ad533  mov     [r8+10h], rbx
0x1801ad537  jmp     short loc_1801AD59A
0x1801ad539  cmp     [rcx+0A4h], ebx
0x1801ad53f  jz      short loc_1801AD58B
0x1801ad541  mov     ecx, 0Bh; cb
0x1801ad546  mov     [r8+8], ecx
0x1801ad54a  call    cs:__imp_CoTaskMemAlloc
0x1801ad551  nop     dword ptr [rax+rax+00h]
0x1801ad556  mov     [rdi+10h], rax
0x1801ad55a  test    rax, rax
0x1801ad55d  jnz     short loc_1801AD576
0x1801ad55f  mov     ebx, 8007000Eh
0x1801ad564  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801ad56b  jz      short loc_1801AD59A
0x1801ad56d  mov     ecx, ebx; int
0x1801ad56f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801ad574  jmp     short loc_1801AD59A
0x1801ad576  mov     r8d, [rdi+8]; Size
0x1801ad57a  lea     rdx, [rsi+98h]; Src
0x1801ad581  mov     rcx, rax; void *
0x1801ad584  call    memcpy_0
0x1801ad589  jmp     short loc_1801AD59A
0x1801ad58b  mov     rcx, rdi; pvar
0x1801ad58e  call    cs:__imp_PropVariantClear
0x1801ad595  nop     dword ptr [rax+rax+00h]
0x1801ad59a  mov     rsi, [rsp+28h+arg_8]
0x1801ad59f  mov     eax, ebx
0x1801ad5a1  mov     rbx, [rsp+28h+arg_0]
0x1801ad5a6  add     rsp, 20h
0x1801ad5aa  pop     rdi
0x1801ad5ab  retn
```
