# CMetadataPngBkgdReaderWriter::GetValue(uint,tagPROPVARIANT *)

- ea: `0x1801b4ac0`
- end: `0x1801b4bbb`
- name: `?GetValue@CMetadataPngBkgdReaderWriter@@MEAAJIPEAUtagPROPVARIANT@@@Z`
- size: `251`
- prototype: `int(CMetadataPngBkgdReaderWriter *__hidden this, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800bd9d4`
- `0x18017e438`
- `0x1801b4ac0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b4b31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b4b31`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b4b86`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b4b86`

## pseudocode

```c
__int64 __fastcall CMetadataPngBkgdReaderWriter::GetValue(CMetadataPngBkgdReaderWriter *this, int a2, PROPVARIANT *a3)
{
  unsigned int v5; // ebx
  int v6; // ecx
  __int16 v7; // ax
  BYTE *v8; // rax
  HRESULT v9; // eax

  if ( a2 != 1 )
  {
    v5 = -2147024809;
LABEL_3:
    if ( (_DWORD)g_doStackCaptures )
    {
      v6 = v5;
LABEL_16:
      DoStackCapture(v6);
      return v5;
    }
    return v5;
  }
  v5 = 0;
  *(_WORD *)a3 = *((_WORD *)this + 76);
  v7 = *((_WORD *)this + 76);
  switch ( v7 )
  {
    case 18:
      *((_WORD *)a3 + 4) = *((_WORD *)this + 80);
      return v5;
    case 4114:
      v8 = (BYTE *)CoTaskMemAlloc(2LL * *((unsigned int *)this + 40));
      a3[2] = v8;
      if ( v8 )
      {
        *((_DWORD *)a3 + 2) = *((_DWORD *)this + 40);
        memcpy_0(v8, *((const void **)this + 21), 2LL * *((unsigned int *)this + 40));
        return v5;
      }
      v5 = -2147024882;
      goto LABEL_3;
    case 17:
      *((_BYTE *)a3 + 8) = *((_BYTE *)this + 160);
      break;
    default:
      v9 = PropVariantClear(a3);
      v5 = v9;
      if ( v9 < 0 && (_DWORD)g_doStackCaptures )
      {
        v6 = v9;
        goto LABEL_16;
      }
      break;
  }
  return v5;
}

```

## disassembly

```asm
0x1801b4ac0  mov     [rsp+arg_0], rbx
0x1801b4ac5  mov     [rsp+arg_8], rsi
0x1801b4aca  push    rdi
0x1801b4acb  sub     rsp, 20h
0x1801b4acf  mov     rsi, r8
0x1801b4ad2  mov     rdi, rcx
0x1801b4ad5  cmp     edx, 1
0x1801b4ad8  jz      short loc_1801B4AF3
0x1801b4ada  mov     ebx, 80070057h
0x1801b4adf  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801b4ae6  jz      loc_1801B4BA8
0x1801b4aec  mov     ecx, ebx
0x1801b4aee  jmp     loc_1801B4BA3
0x1801b4af3  movzx   eax, word ptr [rcx+98h]
0x1801b4afa  xor     ebx, ebx
0x1801b4afc  mov     [r8], ax
0x1801b4b00  movzx   eax, word ptr [rcx+98h]
0x1801b4b07  cmp     ax, 12h
0x1801b4b0b  jnz     short loc_1801B4B1E
0x1801b4b0d  movzx   eax, word ptr [rcx+0A0h]
0x1801b4b14  mov     [r8+8], ax
0x1801b4b19  jmp     loc_1801B4BA8
0x1801b4b1e  mov     ecx, 1012h
0x1801b4b23  cmp     ax, cx
0x1801b4b26  jnz     short loc_1801B4B71
0x1801b4b28  mov     ecx, [rdi+0A0h]
0x1801b4b2e  add     rcx, rcx; cb
0x1801b4b31  call    cs:__imp_CoTaskMemAlloc
0x1801b4b38  nop     dword ptr [rax+rax+00h]
0x1801b4b3d  mov     [rsi+10h], rax
0x1801b4b41  mov     rcx, rax; void *
0x1801b4b44  test    rax, rax
0x1801b4b47  jnz     short loc_1801B4B50
0x1801b4b49  mov     ebx, 8007000Eh
0x1801b4b4e  jmp     short loc_1801B4ADF
0x1801b4b50  mov     eax, [rdi+0A0h]
0x1801b4b56  mov     [rsi+8], eax
0x1801b4b59  mov     r8d, [rdi+0A0h]
0x1801b4b60  mov     rdx, [rdi+0A8h]; Src
0x1801b4b67  add     r8, r8; Size
0x1801b4b6a  call    memcpy_0
0x1801b4b6f  jmp     short loc_1801B4BA8
0x1801b4b71  cmp     ax, 11h
0x1801b4b75  jnz     short loc_1801B4B83
0x1801b4b77  mov     al, [rdi+0A0h]
0x1801b4b7d  mov     [r8+8], al
0x1801b4b81  jmp     short loc_1801B4BA8
0x1801b4b83  mov     rcx, rsi; pvar
0x1801b4b86  call    cs:__imp_PropVariantClear
0x1801b4b8d  nop     dword ptr [rax+rax+00h]
0x1801b4b92  mov     ebx, eax
0x1801b4b94  test    eax, eax
0x1801b4b96  jns     short loc_1801B4BA8
0x1801b4b98  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801b4b9f  jz      short loc_1801B4BA8
0x1801b4ba1  mov     ecx, eax; int
0x1801b4ba3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801b4ba8  mov     rsi, [rsp+28h+arg_8]
0x1801b4bad  mov     eax, ebx
0x1801b4baf  mov     rbx, [rsp+28h+arg_0]
0x1801b4bb4  add     rsp, 20h
0x1801b4bb8  pop     rdi
0x1801b4bb9  retn
```
