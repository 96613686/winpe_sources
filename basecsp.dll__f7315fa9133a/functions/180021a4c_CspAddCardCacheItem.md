# CspAddCardCacheItem

- ea: `0x180021a4c`
- end: `0x180021b40`
- name: `CspAddCardCacheItem`
- size: `244`
- prototype: `__int64 __fastcall(struct _CARD_CACHE_QUERY_INFO *, void *Destination)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18001d568`
- `0x1800210a0`
- `0x180021928`
- `0x180021e64`
- `0x180022304`

## callees

- `0x180017bac`
- `0x18001f3a4`
- `0x18002140c`
- `0x1800215f0`
- `0x180021a4c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180021b11`
- `msvcrt!memcpy_s` at `0x180021b11`

## pseudocode

```c
__int64 __fastcall CspAddCardCacheItem(struct _CARD_CACHE_QUERY_INFO *a1, void *Destination)
{
  __int64 v4; // rcx
  _DWORD *v5; // rax
  unsigned int CardCacheFile; // edi
  int v7; // r9d
  bool v9; // zf
  DWORD v10; // eax
  _CRYPTOAPI_BLOB v11; // [rsp+30h] [rbp-38h] BYREF

  v4 = *(_QWORD *)a1;
  v5 = *(_DWORD **)(v4 + 8);
  if ( !v5 )
  {
    CardCacheFile = 87;
    WppTraceIndent(v4, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
        v7,
        (__int64)"pInfo->pCardState->pCardData");
    }
    return CardCacheFile;
  }
  if ( *v5 >= 6u && *(_DWORD *)(v4 + 696) == 3 && *((_DWORD *)a1 + 2) != 1 )
    return 0;
  v9 = *((_DWORD *)a1 + 3) == 0;
  *(&v11.cbData + 1) = 0;
  if ( !v9 )
  {
    if ( !*((_DWORD *)a1 + 137) )
    {
      CardCacheFile = I_CspReadCardCacheFile(
                        (struct _CARD_STATE *)v4,
                        (struct _CARD_CACHE_QUERY_INFO *)((char *)a1 + 540));
      if ( CardCacheFile )
        return CardCacheFile;
    }
    memcpy_s(Destination, 6u, (char *)a1 + 540, 6u);
  }
  v10 = *((_DWORD *)Destination + 3) + 16;
  v11.pbData = (BYTE *)Destination;
  v11.cbData = v10;
  return (unsigned int)MyCacheAddItem(a1, &v11);
}

```

## disassembly

```asm
0x180021a4c  push    rbx
0x180021a4e  push    rbp
0x180021a4f  push    rsi
0x180021a50  push    rdi
0x180021a51  sub     rsp, 48h
0x180021a55  mov     rbx, rcx
0x180021a58  mov     rsi, rdx
0x180021a5b  mov     rcx, [rcx]; struct _CARD_STATE *
0x180021a5e  mov     rax, [rcx+8]
0x180021a62  test    rax, rax
0x180021a65  jnz     short loc_180021ABE
0x180021a67  lea     edx, [rax+2]
0x180021a6a  lea     edi, [rax+57h]
0x180021a6d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a79  lea     rax, WPP_GLOBAL_Control
0x180021a80  cmp     rcx, rax
0x180021a83  jz      loc_180021B35
0x180021a89  test    byte ptr [rcx+1Ch], 1
0x180021a8d  jz      loc_180021B35
0x180021a93  cmp     byte ptr [rcx+19h], 2
0x180021a97  jb      loc_180021B35
0x180021a9d  mov     rcx, [rcx+10h]
0x180021aa1  lea     rax, aPinfoPcardstat; "pInfo->pCardState->pCardData"
0x180021aa8  lea     edx, [rdi-48h]
0x180021aab  mov     [rsp+68h+var_48], rax
0x180021ab0  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180021ab7  call    WPP_SF_ss
0x180021abc  jmp     short loc_180021B35
0x180021abe  cmp     dword ptr [rax], 6
0x180021ac1  jb      short loc_180021AD6
0x180021ac3  cmp     dword ptr [rcx+2B8h], 3
0x180021aca  jnz     short loc_180021AD6
0x180021acc  cmp     dword ptr [rbx+8], 1
0x180021ad0  jz      short loc_180021AD6
0x180021ad2  xor     eax, eax
0x180021ad4  jmp     short loc_180021B37
0x180021ad6  cmp     dword ptr [rbx+0Ch], 0
0x180021ada  mov     dword ptr [rsp+68h+var_38+4], 0
0x180021ae2  jz      short loc_180021B17
0x180021ae4  cmp     dword ptr [rbx+224h], 0
0x180021aeb  lea     rbp, [rbx+21Ch]
0x180021af2  jnz     short loc_180021B02
0x180021af4  mov     rdx, rbp; struct _CARD_CACHE_FILE_FORMAT *
0x180021af7  call    ?I_CspReadCardCacheFile@@YAKPEAU_CARD_STATE@@PEAU_CARD_CACHE_FILE_FORMAT@@@Z; I_CspReadCardCacheFile(_CARD_STATE *,_CARD_CACHE_FILE_FORMAT *)
0x180021afc  mov     edi, eax
0x180021afe  test    eax, eax
0x180021b00  jnz     short loc_180021B35
0x180021b02  mov     r9d, 6; SourceSize
0x180021b08  mov     r8, rbp; Source
0x180021b0b  mov     edx, r9d; DestinationSize
0x180021b0e  mov     rcx, rsi; Destination
0x180021b11  call    cs:__imp_memcpy_s
0x180021b17  mov     eax, [rsi+0Ch]
0x180021b1a  lea     rdx, [rsp+68h+var_38]; struct _CRYPTOAPI_BLOB *
0x180021b1f  add     eax, 10h
0x180021b22  mov     [rsp+68h+var_38.pbData], rsi
0x180021b27  mov     rcx, rbx; struct _CARD_CACHE_QUERY_INFO *
0x180021b2a  mov     [rsp+68h+var_38.cbData], eax
0x180021b2e  call    ?MyCacheAddItem@@YAKPEAU_CARD_CACHE_QUERY_INFO@@PEAU_CRYPTOAPI_BLOB@@@Z; MyCacheAddItem(_CARD_CACHE_QUERY_INFO *,_CRYPTOAPI_BLOB *)
0x180021b33  mov     edi, eax
0x180021b35  mov     eax, edi
0x180021b37  add     rsp, 48h
0x180021b3b  pop     rdi
0x180021b3c  pop     rsi
0x180021b3d  pop     rbp
0x180021b3e  pop     rbx
0x180021b3f  retn
```
