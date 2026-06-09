# CMetadataPngBkgdReaderWriter::GetValue(uint,tagPROPVARIANT *)

- ea: `0x1801b13d0`
- end: `0x1801b14bb`
- name: `?GetValue@CMetadataPngBkgdReaderWriter@@MEAAJIPEAUtagPROPVARIANT@@@Z`
- size: `235`
- prototype: `int(CMetadataPngBkgdReaderWriter *__hidden this, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800bb784`
- `0x18017b528`
- `0x1801b13d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b143e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b143e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b148d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b148d`

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
0x1801b13d0  mov     [rsp+arg_0], rbx
0x1801b13d5  mov     [rsp+arg_8], rsi
0x1801b13da  push    rdi
0x1801b13db  sub     rsp, 20h
0x1801b13df  mov     rsi, r8
0x1801b13e2  mov     rdi, rcx
0x1801b13e5  cmp     edx, 1
0x1801b13e8  jz      short loc_1801B1403
0x1801b13ea  mov     ebx, 80070057h
0x1801b13ef  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801b13f6  jz      loc_1801B14A9
0x1801b13fc  mov     ecx, ebx
0x1801b13fe  jmp     loc_1801B14A4
0x1801b1403  movzx   eax, word ptr [rcx+98h]
0x1801b140a  xor     ebx, ebx
0x1801b140c  mov     [r8], ax
0x1801b1410  movzx   eax, word ptr [rcx+98h]
0x1801b1417  cmp     ax, 12h
0x1801b141b  jnz     short loc_1801B142B
0x1801b141d  movzx   eax, word ptr [rcx+0A0h]
0x1801b1424  mov     [r8+8], ax
0x1801b1429  jmp     short loc_1801B14A9
0x1801b142b  mov     ecx, 1012h
0x1801b1430  cmp     ax, cx
0x1801b1433  jnz     short loc_1801B1478
0x1801b1435  mov     ecx, [rdi+0A0h]
0x1801b143b  add     rcx, rcx; cb
0x1801b143e  call    cs:__imp_CoTaskMemAlloc
0x1801b1444  mov     [rsi+10h], rax
0x1801b1448  mov     rcx, rax; void *
0x1801b144b  test    rax, rax
0x1801b144e  jnz     short loc_1801B1457
0x1801b1450  mov     ebx, 8007000Eh
0x1801b1455  jmp     short loc_1801B13EF
0x1801b1457  mov     eax, [rdi+0A0h]
0x1801b145d  mov     [rsi+8], eax
0x1801b1460  mov     r8d, [rdi+0A0h]
0x1801b1467  mov     rdx, [rdi+0A8h]; Src
0x1801b146e  add     r8, r8; Size
0x1801b1471  call    memcpy_0
0x1801b1476  jmp     short loc_1801B14A9
0x1801b1478  cmp     ax, 11h
0x1801b147c  jnz     short loc_1801B148A
0x1801b147e  mov     al, [rdi+0A0h]
0x1801b1484  mov     [r8+8], al
0x1801b1488  jmp     short loc_1801B14A9
0x1801b148a  mov     rcx, rsi; pvar
0x1801b148d  call    cs:__imp_PropVariantClear
0x1801b1493  mov     ebx, eax
0x1801b1495  test    eax, eax
0x1801b1497  jns     short loc_1801B14A9
0x1801b1499  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801b14a0  jz      short loc_1801B14A9
0x1801b14a2  mov     ecx, eax; int
0x1801b14a4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801b14a9  mov     rsi, [rsp+28h+arg_8]
0x1801b14ae  mov     eax, ebx
0x1801b14b0  mov     rbx, [rsp+28h+arg_0]
0x1801b14b5  add     rsp, 20h
0x1801b14b9  pop     rdi
0x1801b14ba  retn
```
