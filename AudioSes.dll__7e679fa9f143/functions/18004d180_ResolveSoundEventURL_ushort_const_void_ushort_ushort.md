# ResolveSoundEventURL(ushort const *,void * *,ushort * *,ushort * *)

- ea: `0x18004d180`
- end: `0x18004d226`
- name: `?ResolveSoundEventURL@@YAJPEBGPEAPEAXPEAPEAG2@Z`
- size: `166`
- prototype: `int(const unsigned __int16 *, void **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800723d8`
- `0x1800c9440`
- `0x1800c9620`

## callees

- `0x18004d180`
- `0x18004d274`
- `0x18004d71c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d1ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d1f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d20a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d1ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d1f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d20a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d212`

## pseudocode

```c
__int64 __fastcall ResolveSoundEventURL(
        const unsigned __int16 *a1,
        void **a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  int SoundAliasNameFromURL; // eax
  unsigned __int16 *v8; // rbx
  unsigned int v9; // esi
  int v10; // eax
  void *v12; // rcx
  unsigned int v13; // [rsp+30h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int16 *v15; // [rsp+40h] [rbp-38h] BYREF

  v15 = 0;
  pv = 0;
  v13 = 0;
  SoundAliasNameFromURL = GetSoundAliasNameFromURL(a1, &v15, (unsigned __int16 **)&pv, &v13);
  v8 = v15;
  v9 = SoundAliasNameFromURL;
  if ( SoundAliasNameFromURL < 0 )
    goto LABEL_4;
  v10 = ResolveSoundAlias(v15, (const unsigned __int16 *)pv, v13, (__int64 *)a2, a3);
  if ( v10 < 0 )
  {
    v9 = v10;
LABEL_4:
    CoTaskMemFree(pv);
    CoTaskMemFree(v8);
    return v9;
  }
  v12 = pv;
  *a4 = v8;
  CoTaskMemFree(v12);
  CoTaskMemFree(0);
  return 0;
}

```

## disassembly

```asm
0x18004d180  mov     rax, rsp
0x18004d183  push    rbx
0x18004d184  push    rbp
0x18004d185  push    rsi
0x18004d186  push    r14
0x18004d188  push    r15
0x18004d18a  sub     rsp, 50h
0x18004d18e  mov     r14, r9
0x18004d191  mov     qword ptr [rax-38h], 0
0x18004d199  mov     rbp, r8
0x18004d19c  mov     qword ptr [rax-40h], 0
0x18004d1a4  mov     r15, rdx
0x18004d1a7  mov     dword ptr [rax-48h], 0
0x18004d1ae  lea     r9, [rax-48h]; unsigned int *
0x18004d1b2  lea     r8, [rax-40h]; unsigned __int16 **
0x18004d1b6  lea     rdx, [rax-38h]; unsigned __int16 **
0x18004d1ba  call    ?GetSoundAliasNameFromURL@@YAJPEBGPEAPEAG1PEAK@Z; GetSoundAliasNameFromURL(ushort const *,ushort * *,ushort * *,ulong *)
0x18004d1bf  mov     rbx, [rsp+78h+var_38]
0x18004d1c4  mov     esi, eax
0x18004d1c6  test    eax, eax
0x18004d1c8  js      short loc_18004D1EA
0x18004d1ca  mov     r8d, [rsp+78h+var_48]; unsigned int
0x18004d1cf  mov     r9, r15; __int64 *
0x18004d1d2  mov     rdx, [rsp+78h+pv]; unsigned __int16 *
0x18004d1d7  mov     rcx, rbx; unsigned __int16 *
0x18004d1da  mov     [rsp+78h+var_58], rbp; unsigned __int16 **
0x18004d1df  call    ?ResolveSoundAlias@@YAJPEBG0KPEA_JPEAPEAG@Z; ResolveSoundAlias(ushort const *,ushort const *,ulong,__int64 *,ushort * *)
0x18004d1e4  test    eax, eax
0x18004d1e6  jns     short loc_18004D202
0x18004d1e8  mov     esi, eax
0x18004d1ea  mov     rcx, [rsp+78h+pv]; pv
0x18004d1ef  call    cs:__imp_CoTaskMemFree
0x18004d1f5  mov     rcx, rbx; pv
0x18004d1f8  call    cs:__imp_CoTaskMemFree
0x18004d1fe  mov     eax, esi
0x18004d200  jmp     short loc_18004D21A
0x18004d202  mov     rcx, [rsp+78h+pv]; pv
0x18004d207  mov     [r14], rbx
0x18004d20a  call    cs:__imp_CoTaskMemFree
0x18004d210  xor     ecx, ecx; pv
0x18004d212  call    cs:__imp_CoTaskMemFree
0x18004d218  xor     eax, eax
0x18004d21a  add     rsp, 50h
0x18004d21e  pop     r15
0x18004d220  pop     r14
0x18004d222  pop     rsi
0x18004d223  pop     rbp
0x18004d224  pop     rbx
0x18004d225  retn
```
