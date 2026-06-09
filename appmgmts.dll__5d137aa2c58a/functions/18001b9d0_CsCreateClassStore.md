# CsCreateClassStore

- ea: `0x18001b9d0`
- end: `0x18001bacb`
- name: `CsCreateClassStore`
- size: `251`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path`

## callees

- `0x180002b14`
- `0x18001b9d0`
- `0x18002371c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bab6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bab6`
- `adsldpc!BuildADsParentPath` at `0x18001ba16`
- `adsldpc!BuildADsParentPath` at `0x18001ba2e`
- `adsldpc!BuildADsParentPath` at `0x18001ba16`
- `adsldpc!BuildADsParentPath` at `0x18001ba2e`
- `adsldpc!FreeADsMem` at `0x18001ba45`
- `adsldpc!FreeADsMem` at `0x18001ba8f`
- `adsldpc!FreeADsMem` at `0x18001ba9e`
- `adsldpc!FreeADsMem` at `0x18001baad`
- `adsldpc!FreeADsMem` at `0x18001ba45`
- `adsldpc!FreeADsMem` at `0x18001ba8f`
- `adsldpc!FreeADsMem` at `0x18001ba9e`
- `adsldpc!FreeADsMem` at `0x18001baad`

## pseudocode

```c
__int64 __fastcall CsCreateClassStore(unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned __int16 *v3; // rbx
  int v4; // edi
  int Repository; // eax
  unsigned __int16 *v7; // [rsp+20h] [rbp-10h] BYREF
  LPVOID pMem; // [rsp+28h] [rbp-8h] BYREF
  unsigned __int16 *v9; // [rsp+58h] [rbp+28h] BYREF
  unsigned __int16 *v10; // [rsp+60h] [rbp+30h] BYREF
  unsigned __int16 *v11; // [rsp+68h] [rbp+38h] BYREF

  v10 = 0;
  v7 = 0;
  v3 = 0;
  v9 = 0;
  pMem = 0;
  v11 = 0;
  v4 = BuildADsParentPath(a2, &v10, &v7);
  if ( v4 >= 0 )
  {
    if ( (int)BuildADsParentPath(v10, &v9, (unsigned __int16 **)&pMem) < 0 )
      v9 = 0;
    if ( pMem )
      FreeADsMem(pMem);
    if ( !a1 || (v11 = StringDuplicate(a1), (v3 = v11) != 0) )
    {
      Repository = CreateRepository((struct CServerContext *)&v11, v10, v7, v9);
      v3 = v11;
      v4 = Repository;
    }
    else
    {
      v4 = -2147024882;
    }
  }
  if ( v9 )
    FreeADsMem(v9);
  if ( v10 )
    FreeADsMem(v10);
  if ( v7 )
    FreeADsMem(v7);
  LocalFree(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001b9d0  mov     [rsp-18h+arg_0], rbx
0x18001b9d5  push    rbp
0x18001b9d6  push    rsi
0x18001b9d7  push    rdi
0x18001b9d8  mov     rbp, rsp
0x18001b9db  sub     rsp, 30h
0x18001b9df  mov     rax, rdx
0x18001b9e2  mov     [rbp+arg_10], 0
0x18001b9ea  mov     rsi, rcx
0x18001b9ed  mov     [rbp+var_10], 0
0x18001b9f5  xor     ebx, ebx
0x18001b9f7  mov     [rbp+arg_8], 0
0x18001b9ff  mov     rcx, rax
0x18001ba02  mov     [rbp+pMem], 0
0x18001ba0a  lea     r8, [rbp+var_10]
0x18001ba0e  mov     [rbp+arg_18], rbx
0x18001ba12  lea     rdx, [rbp+arg_10]
0x18001ba16  call    cs:__imp_?BuildADsParentPath@@YAJPEAGPEAPEAG1@Z; BuildADsParentPath(ushort *,ushort * *,ushort * *)
0x18001ba1c  mov     edi, eax
0x18001ba1e  test    eax, eax
0x18001ba20  js      short loc_18001BA86
0x18001ba22  mov     rcx, [rbp+arg_10]
0x18001ba26  lea     r8, [rbp+pMem]
0x18001ba2a  lea     rdx, [rbp+arg_8]
0x18001ba2e  call    cs:__imp_?BuildADsParentPath@@YAJPEAGPEAPEAG1@Z; BuildADsParentPath(ushort *,ushort * *,ushort * *)
0x18001ba34  test    eax, eax
0x18001ba36  jns     short loc_18001BA3C
0x18001ba38  mov     [rbp+arg_8], rbx
0x18001ba3c  mov     rcx, [rbp+pMem]; pMem
0x18001ba40  test    rcx, rcx
0x18001ba43  jz      short loc_18001BA4B
0x18001ba45  call    cs:__imp_FreeADsMem
0x18001ba4b  test    rsi, rsi
0x18001ba4e  jz      short loc_18001BA6B
0x18001ba50  mov     rcx, rsi; unsigned __int16 *
0x18001ba53  call    ?StringDuplicate@@YAPEAGPEBG@Z; StringDuplicate(ushort const *)
0x18001ba58  mov     [rbp+arg_18], rax
0x18001ba5c  mov     rbx, rax
0x18001ba5f  test    rax, rax
0x18001ba62  jnz     short loc_18001BA6B
0x18001ba64  mov     edi, 8007000Eh
0x18001ba69  jmp     short loc_18001BA86
0x18001ba6b  mov     r9, [rbp+arg_8]; unsigned __int16 *
0x18001ba6f  lea     rcx, [rbp+arg_18]; struct CServerContext *
0x18001ba73  mov     r8, [rbp+var_10]; unsigned __int16 *
0x18001ba77  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x18001ba7b  call    ?CreateRepository@@YAJPEAVCServerContext@@PEBG11@Z; CreateRepository(CServerContext *,ushort const *,ushort const *,ushort const *)
0x18001ba80  mov     rbx, [rbp+arg_18]
0x18001ba84  mov     edi, eax
0x18001ba86  mov     rcx, [rbp+arg_8]; pMem
0x18001ba8a  test    rcx, rcx
0x18001ba8d  jz      short loc_18001BA95
0x18001ba8f  call    cs:__imp_FreeADsMem
0x18001ba95  mov     rcx, [rbp+arg_10]; pMem
0x18001ba99  test    rcx, rcx
0x18001ba9c  jz      short loc_18001BAA4
0x18001ba9e  call    cs:__imp_FreeADsMem
0x18001baa4  mov     rcx, [rbp+var_10]; pMem
0x18001baa8  test    rcx, rcx
0x18001baab  jz      short loc_18001BAB3
0x18001baad  call    cs:__imp_FreeADsMem
0x18001bab3  mov     rcx, rbx; hMem
0x18001bab6  call    cs:__imp_LocalFree
0x18001babc  mov     rbx, [rsp+30h+arg_0]
0x18001bac1  mov     eax, edi
0x18001bac3  add     rsp, 30h
0x18001bac7  pop     rdi
0x18001bac8  pop     rsi
0x18001bac9  pop     rbp
0x18001baca  retn
```
