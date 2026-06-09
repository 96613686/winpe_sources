# CMetadataPngBkgdReaderWriter::ReadFields(IStream *)

- ea: `0x1801b1510`
- end: `0x1801b17be`
- name: `?ReadFields@CMetadataPngBkgdReaderWriter@@MEAAJPEAUIStream@@@Z`
- size: `686`
- prototype: `__int64 __fastcall(CMetadataPngBkgdReaderWriter *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180023050`
- `0x1800bb784`
- `0x18017b540`
- `0x1801b1510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b16a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b16a7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b17a9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801b17a9`

## pseudocode

```c
__int64 __fastcall CMetadataPngBkgdReaderWriter::ReadFields(CMetadataPngBkgdReaderWriter *this, struct IStream *a2)
{
  CExternalStream *v3; // rcx
  int v4; // eax
  int v5; // ebx
  int v6; // ecx
  CExternalStream *v7; // rcx
  int v8; // esi
  bool v9; // zf
  int v10; // ecx
  unsigned __int16 v11; // ax
  unsigned __int16 v12; // cx
  LPVOID v13; // rax
  __int64 i; // rsi
  _BYTE Buf1[16]; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int16 v17; // [rsp+50h] [rbp+20h] BYREF
  size_t Size; // [rsp+60h] [rbp+30h] BYREF
  unsigned int v19; // [rsp+68h] [rbp+38h] BYREF

  LODWORD(Size) = 0;
  v19 = 0;
  v3 = (CExternalStream *)(*((_QWORD *)this + 15) + 16LL);
  v17 = 0;
  v4 = CExternalStream::Read(v3, &v19, 4u, (unsigned int *)&Size);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( (_DWORD)g_doStackCaptures )
    {
LABEL_3:
      v6 = v4;
LABEL_14:
      DoStackCapture(v6);
    }
LABEL_45:
    PropVariantClear((PROPVARIANT *)this + 19);
    return (unsigned int)v5;
  }
  if ( (_DWORD)Size != 4 )
  {
    v5 = -2003292304;
LABEL_27:
    v9 = (_DWORD)g_doStackCaptures == 0;
LABEL_12:
    if ( !v9 )
    {
LABEL_13:
      v6 = v5;
      goto LABEL_14;
    }
    goto LABEL_45;
  }
  v7 = (CExternalStream *)(*((_QWORD *)this + 15) + 16LL);
  v19 = (((v19 << 16) | v19 & 0xFF00) << 8) | ((HIWORD(v19) | v19 & 0xFF0000) >> 8);
  v4 = CExternalStream::Read(v7, Buf1, 4u, (unsigned int *)&Size);
  v8 = (int)g_doStackCaptures;
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_45;
    goto LABEL_3;
  }
  if ( (_DWORD)Size != 4 )
  {
    v5 = -2003292304;
LABEL_11:
    v9 = v8 == 0;
    goto LABEL_12;
  }
  if ( memcmp_0(Buf1, "bKGD", 4u) )
  {
    v5 = -2003292317;
    goto LABEL_11;
  }
  switch ( v19 )
  {
    case 2u:
      v4 = CExternalStream::Read((CExternalStream *)(*((_QWORD *)this + 15) + 16LL), &v17, 2u, (unsigned int *)&Size);
      v10 = (int)g_doStackCaptures;
      v5 = v4;
      if ( v4 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_45;
        goto LABEL_3;
      }
      if ( (_DWORD)Size != v19 )
      {
LABEL_22:
        v5 = -2003292304;
        v9 = v10 == 0;
        goto LABEL_12;
      }
      v11 = v17;
      v12 = v17;
      *((_WORD *)this + 76) = 18;
      *((_WORD *)this + 80) = (v11 << 8) | HIBYTE(v12);
      break;
    case 6u:
      *((_WORD *)this + 76) = 4114;
      *((_DWORD *)this + 40) = 3;
      v13 = CoTaskMemAlloc(6u);
      *((_QWORD *)this + 21) = v13;
      if ( !v13 )
      {
        v5 = -2147024882;
        goto LABEL_27;
      }
      for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
      {
        v5 = CExternalStream::Read((CExternalStream *)(*((_QWORD *)this + 15) + 16LL), &v17, 2u, (unsigned int *)&Size);
        if ( v5 < 0 )
        {
          if ( (_DWORD)g_doStackCaptures )
            goto LABEL_13;
          goto LABEL_45;
        }
        if ( (_DWORD)Size != 2 )
        {
          v5 = -2003292304;
          v9 = (_DWORD)g_doStackCaptures == 0;
          goto LABEL_12;
        }
        *(_WORD *)(*((_QWORD *)this + 21) + 2 * i) = (v17 << 8) | HIBYTE(v17);
      }
      break;
    case 1u:
      v4 = CExternalStream::Read(
             (CExternalStream *)(*((_QWORD *)this + 15) + 16LL),
             (char *)this + 160,
             1u,
             (unsigned int *)&Size);
      v10 = (int)g_doStackCaptures;
      v5 = v4;
      if ( v4 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_45;
        goto LABEL_3;
      }
      if ( (_DWORD)Size != v19 )
        goto LABEL_22;
      *((_WORD *)this + 76) = 17;
      break;
    default:
      v5 = -2003292317;
      if ( v8 )
        DoStackCapture(-2003292317);
      break;
  }
  if ( v5 < 0 )
    goto LABEL_45;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1801b1510  mov     [rsp-18h+arg_8], rbx
0x1801b1515  push    rbp
0x1801b1516  push    rsi
0x1801b1517  push    rdi
0x1801b1518  mov     rbp, rsp
0x1801b151b  sub     rsp, 30h
0x1801b151f  xor     eax, eax
0x1801b1521  mov     dword ptr [rbp+Size], 0
0x1801b1528  mov     rdi, rcx
0x1801b152b  mov     [rbp+arg_18], 0
0x1801b1532  mov     rcx, [rcx+78h]
0x1801b1536  lea     r9, [rbp+Size]; unsigned int *
0x1801b153a  add     rcx, 10h; this
0x1801b153e  mov     [rbp+arg_0], ax
0x1801b1542  lea     r8d, [rax+4]; unsigned int
0x1801b1546  lea     rdx, [rbp+arg_18]; void *
0x1801b154a  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x1801b154f  mov     ebx, eax
0x1801b1551  test    eax, eax
0x1801b1553  jns     short loc_1801B1569
0x1801b1555  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801b155c  jz      loc_1801B17A2
0x1801b1562  mov     ecx, eax
0x1801b1564  jmp     loc_1801B15EA
0x1801b1569  cmp     dword ptr [rbp+Size], 4
0x1801b156d  jz      short loc_1801B1579
0x1801b156f  mov     ebx, 88982F70h
0x1801b1574  jmp     loc_1801B16BE
0x1801b1579  mov     ecx, [rbp+arg_18]
0x1801b157c  lea     r9, [rbp+Size]; unsigned int *
0x1801b1580  mov     edx, ecx
0x1801b1582  mov     eax, ecx
0x1801b1584  shr     eax, 10h
0x1801b1587  and     edx, 0FF0000h
0x1801b158d  or      edx, eax
0x1801b158f  mov     r8d, 4; unsigned int
0x1801b1595  mov     eax, ecx
0x1801b1597  shr     edx, 8
0x1801b159a  shl     ecx, 10h
0x1801b159d  and     eax, 0FF00h
0x1801b15a2  or      eax, ecx
0x1801b15a4  mov     rcx, [rdi+78h]
0x1801b15a8  shl     eax, 8
0x1801b15ab  add     rcx, 10h; this
0x1801b15af  or      edx, eax
0x1801b15b1  mov     [rbp+arg_18], edx
0x1801b15b4  lea     rdx, [rbp+Buf1]; void *
0x1801b15b8  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x1801b15bd  mov     esi, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1801b15c3  mov     ebx, eax
0x1801b15c5  test    eax, eax
0x1801b15c7  jns     short loc_1801B15D5
0x1801b15c9  test    esi, esi
0x1801b15cb  jnz     short loc_1801B1562
0x1801b15cd  test    eax, eax
0x1801b15cf  js      loc_1801B17A2
0x1801b15d5  cmp     dword ptr [rbp+Size], 4
0x1801b15d9  jz      short loc_1801B15F4
0x1801b15db  mov     ebx, 88982F70h
0x1801b15e0  test    esi, esi
0x1801b15e2  jz      loc_1801B17A2
0x1801b15e8  mov     ecx, ebx; int
0x1801b15ea  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801b15ef  jmp     loc_1801B17A2
0x1801b15f4  mov     r8d, dword ptr [rbp+Size]; Size
0x1801b15f8  lea     rdx, aBkgd_0; "bKGD"
0x1801b15ff  lea     rcx, [rbp+Buf1]; Buf1
0x1801b1603  call    memcmp_0
0x1801b1608  test    eax, eax
0x1801b160a  jz      short loc_1801B1613
0x1801b160c  mov     ebx, 88982F63h
0x1801b1611  jmp     short loc_1801B15E0
0x1801b1613  mov     eax, [rbp+arg_18]
0x1801b1616  cmp     eax, 2
0x1801b1619  jnz     short loc_1801B1687
0x1801b161b  mov     rcx, [rdi+78h]
0x1801b161f  lea     r9, [rbp+Size]; unsigned int *
0x1801b1623  add     rcx, 10h; this
0x1801b1627  lea     rdx, [rbp+arg_0]; void *
0x1801b162b  mov     r8d, eax; unsigned int
0x1801b162e  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x1801b1633  mov     ecx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1801b1639  mov     ebx, eax
0x1801b163b  test    eax, eax
0x1801b163d  jns     short loc_1801B164F
0x1801b163f  test    ecx, ecx
0x1801b1641  jnz     loc_1801B1562
0x1801b1647  test    eax, eax
0x1801b1649  js      loc_1801B17A2
0x1801b164f  mov     eax, [rbp+arg_18]
0x1801b1652  cmp     dword ptr [rbp+Size], eax
0x1801b1655  jz      short loc_1801B1660
0x1801b1657  mov     ebx, 88982F70h
0x1801b165c  test    ecx, ecx
0x1801b165e  jmp     short loc_1801B15E2
0x1801b1660  movzx   eax, [rbp+arg_0]
0x1801b1664  movzx   ecx, ax
0x1801b1667  mov     word ptr [rdi+98h], 12h
0x1801b1670  shr     cx, 8
0x1801b1674  shl     ax, 8
0x1801b1678  or      cx, ax
0x1801b167b  mov     [rdi+0A0h], cx
0x1801b1682  jmp     loc_1801B179E
0x1801b1687  mov     ecx, 6; cb
0x1801b168c  cmp     eax, ecx
0x1801b168e  jnz     loc_1801B173F
0x1801b1694  mov     word ptr [rdi+98h], 1012h
0x1801b169d  mov     dword ptr [rdi+0A0h], 3
0x1801b16a7  call    cs:__imp_CoTaskMemAlloc
0x1801b16ad  mov     [rdi+0A8h], rax
0x1801b16b4  test    rax, rax
0x1801b16b7  jnz     short loc_1801B16CA
0x1801b16b9  mov     ebx, 8007000Eh
0x1801b16be  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801b16c5  jmp     loc_1801B15E2
0x1801b16ca  xor     esi, esi
0x1801b16cc  cmp     esi, 3
0x1801b16cf  jnb     loc_1801B179E
0x1801b16d5  mov     rcx, [rdi+78h]
0x1801b16d9  lea     r9, [rbp+Size]; unsigned int *
0x1801b16dd  add     rcx, 10h; this
0x1801b16e1  lea     rdx, [rbp+arg_0]; void *
0x1801b16e5  mov     r8d, 2; unsigned int
0x1801b16eb  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x1801b16f0  mov     ebx, eax
0x1801b16f2  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1801b16f8  test    ebx, ebx
0x1801b16fa  jns     short loc_1801B170C
0x1801b16fc  test    eax, eax
0x1801b16fe  jnz     loc_1801B15E8
0x1801b1704  test    ebx, ebx
0x1801b1706  js      loc_1801B17A2
0x1801b170c  cmp     dword ptr [rbp+Size], 2
0x1801b1710  jnz     short loc_1801B1733
0x1801b1712  movzx   eax, [rbp+arg_0]
0x1801b1716  movzx   edx, ax
0x1801b1719  shl     ax, 8
0x1801b171d  shr     dx, 8
0x1801b1721  or      dx, ax
0x1801b1724  mov     rax, [rdi+0A8h]
0x1801b172b  mov     [rax+rsi*2], dx
0x1801b172f  inc     esi
0x1801b1731  jmp     short loc_1801B16CC
0x1801b1733  mov     ebx, 88982F70h
0x1801b1738  test    eax, eax
0x1801b173a  jmp     loc_1801B15E2
0x1801b173f  cmp     eax, 1
0x1801b1742  jnz     short loc_1801B178E
0x1801b1744  mov     rcx, [rdi+78h]
0x1801b1748  lea     rdx, [rdi+0A0h]; void *
0x1801b174f  add     rcx, 10h; this
0x1801b1753  lea     r9, [rbp+Size]; unsigned int *
0x1801b1757  mov     r8d, eax; unsigned int
0x1801b175a  call    ?Read@CExternalStream@@UEAAJPEAXKPEAK@Z; CExternalStream::Read(void *,ulong,ulong *)
0x1801b175f  mov     ecx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1801b1765  mov     ebx, eax
0x1801b1767  test    eax, eax
0x1801b1769  jns     short loc_1801B1777
0x1801b176b  test    ecx, ecx
0x1801b176d  jnz     loc_1801B1562
0x1801b1773  test    eax, eax
0x1801b1775  js      short loc_1801B17A2
0x1801b1777  mov     eax, [rbp+arg_18]
0x1801b177a  cmp     dword ptr [rbp+Size], eax
0x1801b177d  jnz     loc_1801B1657
0x1801b1783  mov     word ptr [rdi+98h], 11h
0x1801b178c  jmp     short loc_1801B179E
0x1801b178e  mov     ebx, 88982F63h
0x1801b1793  test    esi, esi
0x1801b1795  jz      short loc_1801B179E
0x1801b1797  mov     ecx, ebx; int
0x1801b1799  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801b179e  test    ebx, ebx
0x1801b17a0  jns     short loc_1801B17AF
0x1801b17a2  lea     rcx, [rdi+98h]; pvar
0x1801b17a9  call    cs:__imp_PropVariantClear
0x1801b17af  mov     eax, ebx
0x1801b17b1  mov     rbx, [rsp+30h+arg_8]
0x1801b17b6  add     rsp, 30h
0x1801b17ba  pop     rdi
0x1801b17bb  pop     rsi
0x1801b17bc  pop     rbp
0x1801b17bd  retn
```
