# IsPrinterSI(IShellItem2 *)

- ea: `0x180008750`
- end: `0x18000880c`
- name: `?IsPrinterSI@@YAHPEAUIShellItem2@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(struct IShellItem2 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007a10`

## callees

- `0x180008750`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800087f8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800087f8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800087db`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800087db`

## pseudocode

```c
__int64 __fastcall IsPrinterSI(struct IShellItem2 *a1)
{
  struct IShellItem2Vtbl *lpVtbl; // rax
  unsigned int v2; // esi
  unsigned int ulVal; // edi
  int v4; // ebx
  BYTE *pData; // r14
  const WCHAR *v6; // rcx
  unsigned __int64 v7; // rax
  PROPVARIANT pvar; // [rsp+30h] [rbp-48h] BYREF

  lpVtbl = a1->lpVtbl;
  v2 = 0;
  memset(&pvar, 0, sizeof(pvar));
  if ( ((int (__fastcall *)(struct IShellItem2 *, const PROPERTYKEY *, PROPVARIANT *))lpVtbl->GetProperty)(
         a1,
         &PKEY_Devices_InterfacePaths,
         &pvar) >= 0
    && pvar.vt == 4127 )
  {
    ulVal = pvar.ulVal;
    v4 = 0;
    pData = pvar.bstrblobVal.pData;
    if ( pvar.lVal )
    {
      while ( 1 )
      {
        v6 = *(const WCHAR **)&pData[8 * v4];
        v7 = -1;
        do
          ++v7;
        while ( v6[v7] );
        if ( v7 > 0x26 && CompareStringOrdinal(v6, 38, L"{0ecef634-6ef0-472a-8085-5ad023ecbccd}", 38, 1) == 2 )
          break;
        if ( ++v4 >= ulVal )
          goto LABEL_11;
      }
      v2 = 1;
    }
  }
LABEL_11:
  PropVariantClear(&pvar);
  return v2;
}

```

## disassembly

```asm
0x180008750  push    rbx
0x180008752  push    rsi
0x180008753  push    rdi
0x180008754  push    r14
0x180008756  push    r15
0x180008758  sub     rsp, 50h
0x18000875c  xor     eax, eax
0x18000875e  lea     r8, [rsp+78h+pvar]
0x180008763  mov     qword ptr [rsp+78h+pvar+10h], rax
0x180008768  lea     rdx, PKEY_Devices_InterfacePaths
0x18000876f  mov     rax, [rcx]
0x180008772  xorps   xmm0, xmm0
0x180008775  xor     r15d, r15d
0x180008778  mov     esi, r15d
0x18000877b  movups  xmmword ptr [rsp+78h+pvar], xmm0
0x180008780  mov     rax, [rax+68h]
0x180008784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008789  test    eax, eax
0x18000878b  js      short loc_1800087F3
0x18000878d  mov     eax, 101Fh
0x180008792  cmp     word ptr [rsp+78h+pvar], ax
0x180008797  jnz     short loc_1800087F3
0x180008799  mov     edi, dword ptr [rsp+78h+pvar+8]
0x18000879d  mov     ebx, r15d
0x1800087a0  mov     r14, qword ptr [rsp+78h+pvar+10h]
0x1800087a5  test    edi, edi
0x1800087a7  jz      short loc_1800087F3
0x1800087a9  mov     eax, ebx
0x1800087ab  mov     rcx, [r14+rax*8]; lpString1
0x1800087af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800087b3  inc     rax
0x1800087b6  cmp     [rcx+rax*2], r15w
0x1800087bb  jnz     short loc_1800087B3
0x1800087bd  cmp     rax, 26h ; '&'
0x1800087c1  jbe     short loc_1800087E6
0x1800087c3  mov     r9d, 26h ; '&'; cchCount2
0x1800087c9  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x1800087d1  mov     edx, r9d; cchCount1
0x1800087d4  lea     r8, a0ecef6346ef047; "{0ecef634-6ef0-472a-8085-5ad023ecbccd}"
0x1800087db  call    cs:__imp_CompareStringOrdinal
0x1800087e1  cmp     eax, 2
0x1800087e4  jz      short loc_1800087EE
0x1800087e6  inc     ebx
0x1800087e8  cmp     ebx, edi
0x1800087ea  jb      short loc_1800087A9
0x1800087ec  jmp     short loc_1800087F3
0x1800087ee  mov     esi, 1
0x1800087f3  lea     rcx, [rsp+78h+pvar]; pvar
0x1800087f8  call    cs:__imp_PropVariantClear
0x1800087fe  mov     eax, esi
0x180008800  add     rsp, 50h
0x180008804  pop     r15
0x180008806  pop     r14
0x180008808  pop     rdi
0x180008809  pop     rsi
0x18000880a  pop     rbx
0x18000880b  retn
```
