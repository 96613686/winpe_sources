# FwFieldParserDynamicKeywordAddress(ushort const *,_tag_FW_DYNAMIC_KEYWORD_ADDRESS_ID_LIST *)

- ea: `0x1800262a8`
- end: `0x180026379`
- name: `?FwFieldParserDynamicKeywordAddress@@YAJPEBGPEAU_tag_FW_DYNAMIC_KEYWORD_ADDRESS_ID_LIST@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(LPCOLESTR lpsz, const void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026540`

## callees

- `0x1800042c4`
- `0x1800262a8`
- `0x180039bb8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180026325`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180026325`
- `fwbase!FwFree` at `0x180026355`
- `fwbase!FwFree` at `0x180026366`
- `fwbase!FwFree` at `0x180026355`
- `fwbase!FwFree` at `0x180026366`
- `fwbase!FwAlloc` at `0x1800262c4`
- `fwbase!FwAlloc` at `0x1800262c4`

## pseudocode

```c
__int64 __fastcall FwFieldParserDynamicKeywordAddress(LPCOLESTR lpsz, const void **a2)
{
  __int64 v2; // rbx
  int v5; // ebp
  GUID *v6; // rax
  GUID *v7; // rsi
  HRESULT v8; // ebx
  LPCOLESTR v9; // rcx
  __int64 v10; // rdx

  v2 = *(unsigned int *)a2;
  v5 = v2 + 1;
  v6 = (GUID *)FwAlloc(16LL * (unsigned int)(v2 + 1));
  v7 = v6;
  if ( v6 )
  {
    memcpy_0(v6, a2[1], 16LL * *(unsigned int *)a2);
    v8 = CLSIDFromString(lpsz, &v7[v2]);
    if ( v8 >= 0 )
    {
      FwFree(a2[1]);
      a2[1] = v7;
      v7 = 0;
      *(_DWORD *)a2 = v5;
      goto LABEL_11;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v10 = 24;
      goto LABEL_5;
    }
  }
  else
  {
    v8 = -2147024882;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v10 = 23;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids, (unsigned int)v8);
    }
  }
LABEL_11:
  FwFree(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800262a8  push    rbx
0x1800262aa  push    rbp
0x1800262ab  push    rsi
0x1800262ac  push    rdi
0x1800262ad  push    r14
0x1800262af  sub     rsp, 20h
0x1800262b3  mov     ebx, [rdx]
0x1800262b5  mov     r14, rcx
0x1800262b8  mov     rdi, rdx
0x1800262bb  lea     ebp, [rbx+1]
0x1800262be  mov     ecx, ebp
0x1800262c0  shl     rcx, 4
0x1800262c4  call    cs:__imp_FwAlloc
0x1800262ca  mov     rsi, rax
0x1800262cd  test    rax, rax
0x1800262d0  jnz     short loc_180026308
0x1800262d2  mov     ebx, 8007000Eh
0x1800262d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262de  lea     rax, WPP_GLOBAL_Control
0x1800262e5  cmp     rcx, rax
0x1800262e8  jz      short loc_180026363
0x1800262ea  test    byte ptr [rcx+1Ch], 1
0x1800262ee  jz      short loc_180026363
0x1800262f0  lea     edx, [rsi+17h]
0x1800262f3  mov     rcx, [rcx+10h]
0x1800262f7  lea     r8, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids
0x1800262fe  mov     r9d, ebx
0x180026301  call    WPP_SF_d
0x180026306  jmp     short loc_180026363
0x180026308  mov     r8d, [rdi]
0x18002630b  mov     rcx, rsi; void *
0x18002630e  mov     rdx, [rdi+8]; Src
0x180026312  shl     r8, 4; Size
0x180026316  call    memcpy_0
0x18002631b  add     rbx, rbx
0x18002631e  mov     rcx, r14; lpsz
0x180026321  lea     rdx, [rsi+rbx*8]; pclsid
0x180026325  call    cs:__imp_CLSIDFromString
0x18002632b  mov     ebx, eax
0x18002632d  test    eax, eax
0x18002632f  jns     short loc_180026351
0x180026331  mov     rcx, cs:WPP_GLOBAL_Control
0x180026338  lea     rax, WPP_GLOBAL_Control
0x18002633f  cmp     rcx, rax
0x180026342  jz      short loc_180026363
0x180026344  test    byte ptr [rcx+1Ch], 1
0x180026348  jz      short loc_180026363
0x18002634a  mov     edx, 18h
0x18002634f  jmp     short loc_1800262F3
0x180026351  mov     rcx, [rdi+8]
0x180026355  call    cs:__imp_FwFree
0x18002635b  mov     [rdi+8], rsi
0x18002635f  xor     esi, esi
0x180026361  mov     [rdi], ebp
0x180026363  mov     rcx, rsi
0x180026366  call    cs:__imp_FwFree
0x18002636c  mov     eax, ebx
0x18002636e  add     rsp, 20h
0x180026372  pop     r14
0x180026374  pop     rdi
0x180026375  pop     rsi
0x180026376  pop     rbp
0x180026377  pop     rbx
0x180026378  retn
```
