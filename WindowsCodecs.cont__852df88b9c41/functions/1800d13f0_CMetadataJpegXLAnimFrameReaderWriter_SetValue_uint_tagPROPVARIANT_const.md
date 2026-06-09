# CMetadataJpegXLAnimFrameReaderWriter::SetValue(uint,tagPROPVARIANT const *)

- ea: `0x1800d13f0`
- end: `0x1800d14ed`
- name: `?SetValue@CMetadataJpegXLAnimFrameReaderWriter@@MEAAJIPEBUtagPROPVARIANT@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(LPVOID *this, int, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800bb784`
- `0x1800d13f0`
- `0x1800d15b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d142b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d148a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d142b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d148a`

## pseudocode

```c
__int64 __fastcall CMetadataJpegXLAnimFrameReaderWriter::SetValue(
        LPVOID *this,
        int a2,
        const struct tagPROPVARIANT *a3)
{
  unsigned int v5; // ebx
  int v6; // edx
  _QWORD *v7; // r14
  LARGE_INTEGER hVal; // r8
  __int64 v9; // rsi
  __int64 v10; // r9
  int v11; // eax
  int v12; // ecx
  int v13; // esi

  v5 = 0;
  v6 = a2 - 1;
  if ( v6 )
  {
    if ( v6 == 1 )
    {
      if ( a3->vt == 31 )
      {
        v7 = this + 22;
        CoTaskMemFree(this[22]);
        *v7 = 0;
        hVal = a3->hVal;
        v9 = -1;
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)(hVal.QuadPart + 2 * v10) );
        v11 = _AllocStringWorker<CTCoAllocPolicy>();
        v5 = v11;
        if ( v11 < 0 )
        {
          if ( !(_DWORD)g_doStackCaptures )
            return v5;
          v12 = v11;
          goto LABEL_21;
        }
        do
          ++v9;
        while ( *(_WORD *)(*v7 + 2 * v9) );
        v13 = 2 * v9 + 2;
        goto LABEL_14;
      }
      if ( !a3->vt )
      {
        CoTaskMemFree(this[22]);
        this[22] = 0;
        v13 = 0;
LABEL_14:
        *((_DWORD *)this + 41) = v13;
        return v5;
      }
    }
  }
  else
  {
    if ( a3->vt == 19 )
    {
      *((_DWORD *)this + 39) = a3->lVal;
      *((_BYTE *)this + 168) = 1;
      return v5;
    }
    if ( !a3->vt )
    {
      *((_BYTE *)this + 168) = 0;
      return v5;
    }
  }
  v5 = -2147024809;
  if ( (_DWORD)g_doStackCaptures )
  {
    v12 = -2147024809;
LABEL_21:
    DoStackCapture(v12);
  }
  return v5;
}

```

## disassembly

```asm
0x1800d13f0  push    rbx
0x1800d13f2  push    rbp
0x1800d13f3  push    rsi
0x1800d13f4  push    rdi
0x1800d13f5  push    r14
0x1800d13f7  sub     rsp, 30h
0x1800d13fb  xor     ebp, ebp
0x1800d13fd  mov     rsi, r8
0x1800d1400  mov     rdi, rcx
0x1800d1403  mov     ebx, ebp
0x1800d1405  sub     edx, 1
0x1800d1408  jz      loc_1800D14A3
0x1800d140e  cmp     edx, 1
0x1800d1411  jnz     loc_1800D14CC
0x1800d1417  movzx   eax, word ptr [r8]
0x1800d141b  cmp     ax, 1Fh
0x1800d141f  jnz     short loc_1800D147E
0x1800d1421  lea     r14, [rcx+0B0h]
0x1800d1428  mov     rcx, [r14]; pv
0x1800d142b  call    cs:__imp_CoTaskMemFree
0x1800d1431  mov     [r14], rbp
0x1800d1434  mov     r8, [rsi+8]
0x1800d1438  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800d143c  mov     r9, rsi
0x1800d143f  inc     r9
0x1800d1442  cmp     [r8+r9*2], bp
0x1800d1447  jnz     short loc_1800D143F
0x1800d1449  mov     [rsp+58h+var_30], r14
0x1800d144e  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800d1453  mov     ebx, eax
0x1800d1455  test    eax, eax
0x1800d1457  jns     short loc_1800D1469
0x1800d1459  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x1800d145f  jz      short loc_1800D1465
0x1800d1461  mov     ecx, eax
0x1800d1463  jmp     short loc_1800D14DB
0x1800d1465  test    eax, eax
0x1800d1467  js      short loc_1800D14E0
0x1800d1469  mov     rax, [r14]
0x1800d146c  inc     rsi
0x1800d146f  cmp     [rax+rsi*2], bp
0x1800d1473  jnz     short loc_1800D146C
0x1800d1475  lea     esi, ds:2[rsi*2]
0x1800d147c  jmp     short loc_1800D1499
0x1800d147e  test    ax, ax
0x1800d1481  jnz     short loc_1800D14CC
0x1800d1483  mov     rcx, [rcx+0B0h]; pv
0x1800d148a  call    cs:__imp_CoTaskMemFree
0x1800d1490  mov     [rdi+0B0h], rbp
0x1800d1497  mov     esi, ebp
0x1800d1499  mov     eax, 0A4h
0x1800d149e  mov     [rax+rdi], esi
0x1800d14a1  jmp     short loc_1800D14E0
0x1800d14a3  cmp     word ptr [r8], 13h
0x1800d14a8  jnz     short loc_1800D14BD
0x1800d14aa  mov     eax, [r8+8]
0x1800d14ae  mov     [rcx+9Ch], eax
0x1800d14b4  mov     byte ptr [rcx+0A8h], 1
0x1800d14bb  jmp     short loc_1800D14E0
0x1800d14bd  cmp     [r8], bp
0x1800d14c1  jnz     short loc_1800D14CC
0x1800d14c3  mov     [rcx+0A8h], bpl
0x1800d14ca  jmp     short loc_1800D14E0
0x1800d14cc  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x1800d14d2  mov     ebx, 80070057h
0x1800d14d7  jz      short loc_1800D14E0
0x1800d14d9  mov     ecx, ebx; int
0x1800d14db  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d14e0  mov     eax, ebx
0x1800d14e2  add     rsp, 30h
0x1800d14e6  pop     r14
0x1800d14e8  pop     rdi
0x1800d14e9  pop     rsi
0x1800d14ea  pop     rbp
0x1800d14eb  pop     rbx
0x1800d14ec  retn
```
