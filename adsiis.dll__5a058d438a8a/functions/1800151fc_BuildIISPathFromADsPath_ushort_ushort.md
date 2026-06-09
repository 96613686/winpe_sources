# BuildIISPathFromADsPath(ushort *,ushort * *)

- ea: `0x1800151fc`
- end: `0x1800152e9`
- name: `?BuildIISPathFromADsPath@@YAJPEAGPEAPEAG@Z`
- size: `237`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180002e80`
- `0x1800031b0`
- `0x180003890`
- `0x180004624`

## callees

- `0x1800151fc`
- `0x1800152f0`
- `0x18001537c`
- `0x18001608c`
- `0x1800160d0`
- `0x18001d66a`
- `0x18001d6c0`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsStr` at `0x180015270`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180015270`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800152be`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800152be`

## pseudocode

```c
__int64 __fastcall BuildIISPathFromADsPath(unsigned __int16 *a1, unsigned __int16 **a2)
{
  int v4; // edi
  LPWSTR v5; // rax
  unsigned __int16 *v6; // rbx
  __int64 v7; // r8
  _BYTE v9[8]; // [rsp+20h] [rbp-278h] BYREF
  LPWSTR pStr; // [rsp+28h] [rbp-270h]
  _BYTE v11[560]; // [rsp+40h] [rbp-258h] BYREF

  memset_0(v11, 0, sizeof(v11));
  CLexer::CLexer((CLexer *)v9, a1);
  *a2 = 0;
  memset_0(v11, 0, sizeof(v11));
  v4 = ADsObject((struct CLexer *)v9, (struct _objectinfo *)v11);
  if ( v4 >= 0 )
  {
    v5 = AllocADsStr(a1);
    v6 = v5;
    if ( v5 )
    {
      v7 = -1;
      do
        ++v7;
      while ( v5[v7] );
      *v5 = 0;
      v4 = BuildIISPathFromADsPath((struct _objectinfo *)v11, v5, v7 + 1);
      if ( v4 >= 0 )
        *a2 = v6;
    }
    else
    {
      v4 = -2147024882;
    }
  }
  FreeObjectInfo((struct _objectinfo *)v11);
  FreeADsStr(pStr);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800151fc  mov     [rsp+arg_10], rbx
0x180015201  push    rbp
0x180015202  push    rsi
0x180015203  push    rdi
0x180015204  sub     rsp, 280h
0x18001520b  mov     rax, cs:__security_cookie
0x180015212  xor     rax, rsp
0x180015215  mov     [rsp+298h+var_28], rax
0x18001521d  mov     rsi, rdx
0x180015220  mov     rbx, rcx
0x180015223  mov     edi, 230h
0x180015228  lea     rcx, [rsp+298h+var_258]; void *
0x18001522d  mov     r8d, edi; Size
0x180015230  xor     edx, edx; Val
0x180015232  call    memset_0
0x180015237  mov     rdx, rbx; unsigned __int16 *
0x18001523a  lea     rcx, [rsp+298h+var_278]; this
0x18001523f  call    ??0CLexer@@QEAA@PEBG@Z; CLexer::CLexer(ushort const *)
0x180015244  xor     ebp, ebp
0x180015246  lea     rcx, [rsp+298h+var_258]; void *
0x18001524b  mov     r8d, edi; Size
0x18001524e  mov     [rsi], rbp
0x180015251  xor     edx, edx; Val
0x180015253  call    memset_0
0x180015258  lea     rdx, [rsp+298h+var_258]; struct _objectinfo *
0x18001525d  lea     rcx, [rsp+298h+var_278]; struct CLexer *
0x180015262  call    ?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ADsObject(CLexer *,_objectinfo *)
0x180015267  mov     edi, eax
0x180015269  test    eax, eax
0x18001526b  js      short loc_1800152AF
0x18001526d  mov     rcx, rbx; pStr
0x180015270  call    cs:__imp_AllocADsStr
0x180015276  mov     rbx, rax
0x180015279  test    rax, rax
0x18001527c  jnz     short loc_180015285
0x18001527e  mov     edi, 8007000Eh
0x180015283  jmp     short loc_1800152AF
0x180015285  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015289  inc     r8
0x18001528c  cmp     [rax+r8*2], bp
0x180015291  jnz     short loc_180015289
0x180015293  inc     r8; unsigned __int64
0x180015296  mov     [rax], bp
0x180015299  mov     rdx, rbx; unsigned __int16 *
0x18001529c  lea     rcx, [rsp+298h+var_258]; struct _objectinfo *
0x1800152a1  call    ?BuildIISPathFromADsPath@@YAJPEAU_objectinfo@@PEAG_K@Z; BuildIISPathFromADsPath(_objectinfo *,ushort *,unsigned __int64)
0x1800152a6  mov     edi, eax
0x1800152a8  test    eax, eax
0x1800152aa  js      short loc_1800152AF
0x1800152ac  mov     [rsi], rbx
0x1800152af  lea     rcx, [rsp+298h+var_258]; struct _objectinfo *
0x1800152b4  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x1800152b9  mov     rcx, [rsp+298h+pStr]; pStr
0x1800152be  call    cs:__imp_FreeADsStr
0x1800152c4  mov     eax, edi
0x1800152c6  mov     rcx, [rsp+298h+var_28]
0x1800152ce  xor     rcx, rsp; StackCookie
0x1800152d1  call    __security_check_cookie
0x1800152d6  mov     rbx, [rsp+298h+arg_10]
0x1800152de  add     rsp, 280h
0x1800152e5  pop     rdi
0x1800152e6  pop     rsi
0x1800152e7  pop     rbp
0x1800152e8  retn
```
