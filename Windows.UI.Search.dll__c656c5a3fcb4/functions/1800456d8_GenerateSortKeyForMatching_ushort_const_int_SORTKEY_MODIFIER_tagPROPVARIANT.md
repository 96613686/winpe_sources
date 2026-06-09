# GenerateSortKeyForMatching(ushort const *,int,SORTKEY_MODIFIER,tagPROPVARIANT *)

- ea: `0x1800456d8`
- end: `0x18004581d`
- name: `?GenerateSortKeyForMatching@@YAHPEBGHW4SORTKEY_MODIFIER@@PEAUtagPROPVARIANT@@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800485b8`

## callees

- `0x180012f44`
- `0x1800456d8`
- `0x1800460d0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180045772`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800457b6`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180045772`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800457b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800457fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800457fb`

## pseudocode

```c
__int64 __fastcall GenerateSortKeyForMatching(void *a1, int a2, int a3, __int64 a4)
{
  unsigned int v8; // ebx
  int cchDest; // esi
  LPWSTR v10; // rdi
  DWORD v11; // ebp
  int v12; // eax
  void *v13; // rcx
  int i; // eax
  __int64 v15; // rcx
  char v16; // al
  LPWSTR lpDestStr[11]; // [rsp+30h] [rbp-58h] BYREF

  lpDestStr[0] = 0;
  *(_OWORD *)a4 = 0;
  *(_QWORD *)(a4 + 16) = 0;
  if ( a3 == 3 )
  {
    v8 = 1;
    cchDest = 1;
    CTCoAllocPolicy::Alloc(a1, 1, 1u, (void **)lpDestStr);
LABEL_3:
    v10 = lpDestStr[0];
    goto LABEL_4;
  }
  v11 = ~(unsigned __int8)GetSystemNormalization() & 2 | 0x8030409;
  v12 = LCMapStringW(0x400u, v11, (LPCWSTR)a1, a2, 0, 0);
  cchDest = v12;
  if ( v12 <= 0 )
    return 0;
  v8 = 1;
  if ( (int)CTCoAllocPolicy::Alloc(v13, 1, v12, (void **)lpDestStr) < 0 )
    goto LABEL_3;
  v10 = lpDestStr[0];
  if ( LCMapStringW(0x400u, v11, (LPCWSTR)a1, a2, lpDestStr[0], cchDest) )
  {
    if ( (unsigned int)(a3 - 1) <= 1 )
    {
      for ( i = 1; i < cchDest; ++i )
      {
        v15 = i;
        if ( *((_BYTE *)v10 + i) == 1 )
        {
          v16 = -1;
          if ( a3 != 1 )
            v16 = 1;
          *((_BYTE *)v10 + v15 - 1) += v16;
          break;
        }
      }
    }
  }
  else
  {
    cchDest = 0;
    CoTaskMemFree(v10);
    v10 = 0;
  }
LABEL_4:
  if ( !v10 )
    return 0;
  *(_WORD *)a4 = 65;
  *(_DWORD *)(a4 + 8) = cchDest;
  *(_QWORD *)(a4 + 16) = v10;
  return v8;
}

```

## disassembly

```asm
0x1800456d8  push    rbx
0x1800456da  push    rbp
0x1800456db  push    rsi
0x1800456dc  push    rdi
0x1800456dd  push    r12
0x1800456df  push    r13
0x1800456e1  push    r14
0x1800456e3  push    r15
0x1800456e5  sub     rsp, 48h
0x1800456e9  xor     eax, eax
0x1800456eb  xorps   xmm0, xmm0
0x1800456ee  mov     [rsp+88h+var_58], rax
0x1800456f3  mov     r14, r9
0x1800456f6  mov     r15d, r8d
0x1800456f9  mov     r12d, edx
0x1800456fc  mov     r13, rcx
0x1800456ff  movups  xmmword ptr [r9], xmm0
0x180045703  mov     [r9+10h], rax
0x180045707  cmp     r8d, 3
0x18004570b  jnz     short loc_180045742
0x18004570d  lea     ebx, [rax+1]
0x180045710  mov     r8d, ebx; unsigned __int64
0x180045713  lea     r9, [rsp+88h+var_58]; void **
0x180045718  mov     edx, ebx; unsigned int
0x18004571a  mov     esi, ebx
0x18004571c  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180045721  mov     rdi, [rsp+88h+var_58]
0x180045726  test    rdi, rdi
0x180045729  jz      loc_180045808
0x18004572f  mov     word ptr [r14], 41h ; 'A'
0x180045735  mov     [r14+8], esi
0x180045739  mov     [r14+10h], rdi
0x18004573d  jmp     loc_18004580A
0x180045742  call    ?GetSystemNormalization@@YAKXZ; GetSystemNormalization(void)
0x180045747  mov     ebp, eax
0x180045749  mov     [rsp+88h+cchDest], 0; cchDest
0x180045751  not     ebp
0x180045753  mov     [rsp+88h+lpDestStr], 0; lpDestStr
0x18004575c  and     ebp, 2
0x18004575f  mov     r9d, r12d; cchSrc
0x180045762  or      ebp, 8030409h
0x180045768  mov     r8, r13; lpSrcStr
0x18004576b  mov     edx, ebp; dwMapFlags
0x18004576d  mov     ecx, 400h; Locale
0x180045772  call    cs:__imp_LCMapStringW
0x180045778  movsxd  rsi, eax
0x18004577b  test    eax, eax
0x18004577d  jle     loc_180045808
0x180045783  mov     ebx, 1
0x180045788  lea     r9, [rsp+88h+var_58]; void **
0x18004578d  mov     edx, ebx; unsigned int
0x18004578f  mov     r8, rsi; unsigned __int64
0x180045792  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180045797  test    eax, eax
0x180045799  js      short loc_180045721
0x18004579b  mov     rdi, [rsp+88h+var_58]
0x1800457a0  mov     r9d, r12d; cchSrc
0x1800457a3  mov     [rsp+88h+cchDest], esi; cchDest
0x1800457a7  mov     r8, r13; lpSrcStr
0x1800457aa  mov     edx, ebp; dwMapFlags
0x1800457ac  mov     [rsp+88h+lpDestStr], rdi; lpDestStr
0x1800457b1  mov     ecx, 400h; Locale
0x1800457b6  call    cs:__imp_LCMapStringW
0x1800457bc  test    eax, eax
0x1800457be  jz      short loc_1800457F6
0x1800457c0  lea     eax, [r15-1]
0x1800457c4  cmp     eax, ebx
0x1800457c6  ja      loc_180045726
0x1800457cc  mov     eax, ebx
0x1800457ce  cmp     eax, esi
0x1800457d0  jge     loc_180045726
0x1800457d6  movsxd  rcx, eax
0x1800457d9  cmp     [rcx+rdi], bl
0x1800457dc  jz      short loc_1800457E2
0x1800457de  add     eax, ebx
0x1800457e0  jmp     short loc_1800457CE
0x1800457e2  cmp     r15d, ebx
0x1800457e5  mov     eax, 0FFh
0x1800457ea  cmovnz  eax, ebx
0x1800457ed  add     [rcx+rdi-1], al
0x1800457f1  jmp     loc_180045726
0x1800457f6  mov     rcx, rdi; pv
0x1800457f9  xor     esi, esi
0x1800457fb  call    cs:__imp_CoTaskMemFree
0x180045801  xor     edi, edi
0x180045803  jmp     loc_180045726
0x180045808  xor     ebx, ebx
0x18004580a  mov     eax, ebx
0x18004580c  add     rsp, 48h
0x180045810  pop     r15
0x180045812  pop     r14
0x180045814  pop     r13
0x180045816  pop     r12
0x180045818  pop     rdi
0x180045819  pop     rsi
0x18004581a  pop     rbp
0x18004581b  pop     rbx
0x18004581c  retn
```
