# XcAddChildElementHexBinary(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,uchar *,ulong,IXMLDOMNode * *)

- ea: `0x1800123d4`
- end: `0x1800124b3`
- name: `?XcAddChildElementHexBinary@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2PEAEKPEAPEAU2@@Z`
- size: `223`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, OLECHAR *psz, OLECHAR *, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a298`
- `0x18000b060`

## callees

- `0x180011f90`
- `0x1800123d4`
- `0x1800133f8`
- `0x180013458`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001240b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001240b`

## pseudocode

```c
__int64 __fastcall XcAddChildElementHexBinary(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        OLECHAR *psz,
        OLECHAR *a4,
        unsigned __int8 *a5,
        unsigned int a6)
{
  OLECHAR *v10; // rbx
  unsigned int v11; // edi
  __int64 v12; // r9
  __int64 i; // r10
  __int64 v14; // r9
  __int16 v15; // cx

  v10 = (OLECHAR *)Xc_Process_user_allocate(2LL * (2 * a6 + 1));
  if ( v10 )
  {
    v12 = 0;
    for ( i = 0; (unsigned int)i < a6; v12 = (unsigned int)(v14 + 1) )
    {
      v10[v12] = (a5[i] >> 4) + 55 + ((unsigned __int8)(a5[i] >> 4) < 0xAu ? 0xFFF9 : 0);
      v14 = (unsigned int)(v12 + 1);
      v15 = a5[i] & 0xF;
      i = (unsigned int)(i + 1);
      v10[v14] = v15 + ((unsigned __int8)v15 < 0xAu ? 48 : 55);
    }
    v10[v12] = 0;
    v11 = XcAddChildElement(a1, a2, psz, a4, v10, 0);
    Xc_Process_user_free(v10);
  }
  else
  {
    return GetLastError();
  }
  return v11;
}

```

## disassembly

```asm
0x1800123d4  push    rbx
0x1800123d6  push    rbp
0x1800123d7  push    rsi
0x1800123d8  push    rdi
0x1800123d9  push    r14
0x1800123db  push    r15
0x1800123dd  sub     rsp, 38h
0x1800123e1  mov     edi, [rsp+68h+arg_28]
0x1800123e8  mov     r15, rcx
0x1800123eb  mov     rsi, r9
0x1800123ee  mov     rbp, r8
0x1800123f1  mov     r14, rdx
0x1800123f4  lea     ecx, ds:1[rdi*2]
0x1800123fb  add     rcx, rcx; dwBytes
0x1800123fe  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x180012403  mov     rbx, rax
0x180012406  test    rax, rax
0x180012409  jnz     short loc_180012418
0x18001240b  call    cs:__imp_GetLastError
0x180012411  mov     edi, eax
0x180012413  jmp     loc_1800124A4
0x180012418  mov     r11, [rsp+68h+arg_20]
0x180012420  xor     r9d, r9d
0x180012423  xor     r10d, r10d
0x180012426  test    edi, edi
0x180012428  jz      short loc_180012478
0x18001242a  mov     al, [r10+r11]
0x18001242e  shr     al, 4
0x180012431  movzx   ecx, al
0x180012434  cmp     cl, 0Ah
0x180012437  sbb     dx, dx
0x18001243a  add     cx, 37h ; '7'
0x18001243e  and     dx, 0FFF9h
0x180012443  add     dx, cx
0x180012446  mov     [rbx+r9*2], dx
0x18001244b  inc     r9d
0x18001244e  mov     al, [r10+r11]
0x180012452  and     al, 0Fh
0x180012454  movzx   ecx, al
0x180012457  cmp     cl, 0Ah
0x18001245a  sbb     ax, ax
0x18001245d  inc     r10d
0x180012460  and     ax, 0FFF9h
0x180012464  add     ax, 37h ; '7'
0x180012468  add     ax, cx
0x18001246b  mov     [rbx+r9*2], ax
0x180012470  inc     r9d
0x180012473  cmp     r10d, edi
0x180012476  jb      short loc_18001242A
0x180012478  xor     eax, eax
0x18001247a  mov     r8, rbp; psz
0x18001247d  mov     [rbx+r9*2], ax
0x180012482  mov     rdx, r14; struct IXMLDOMNode *
0x180012485  mov     [rsp+68h+var_40], rax; struct IXMLDOMNode **
0x18001248a  mov     r9, rsi; OLECHAR *
0x18001248d  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180012490  mov     [rsp+68h+var_48], rbx; OLECHAR *
0x180012495  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18001249a  mov     edi, eax
0x18001249c  mov     rcx, rbx; lpMem
0x18001249f  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x1800124a4  mov     eax, edi
0x1800124a6  add     rsp, 38h
0x1800124aa  pop     r15
0x1800124ac  pop     r14
0x1800124ae  pop     rdi
0x1800124af  pop     rsi
0x1800124b0  pop     rbp
0x1800124b1  pop     rbx
0x1800124b2  retn
```
