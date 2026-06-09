# GetExecutablePathFromCommandLine(ushort const *,ushort * *)

- ea: `0x40777d`
- end: `0x407845`
- name: `?GetExecutablePathFromCommandLine@@YGJPBGPAPAG@Z`
- size: `200`
- prototype: `int __fastcall(const wchar_t *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x403d84`

## callees

- `0x406c66`
- `0x40777d`

## import_xrefs

- `msvcrt!wcsrchr` at `0x4077dc`
- `msvcrt!wcsrchr` at `0x4077dc`

## pseudocode

```c
int __fastcall GetExecutablePathFromCommandLine(const wchar_t *a1, _DWORD *a2)
{
  wchar_t v3; // ax
  wchar_t *v4; // esi
  wchar_t v5; // cx
  wchar_t *v6; // eax
  wchar_t v7; // cx
  wchar_t v8; // bx
  int result; // eax

  while ( 1 )
  {
    v3 = *a1;
    if ( *a1 != 32 && v3 != 9 )
      break;
    ++a1;
  }
  if ( v3 == 34 )
  {
    v4 = (wchar_t *)++a1;
    if ( *a1 )
    {
      v5 = *a1;
      do
      {
        if ( v5 == 34 )
          break;
        v5 = *++v4;
      }
      while ( *v4 );
    }
  }
  else
  {
    v6 = _wcsrchr(a1, 0x5Cu);
    v4 = v6 + 1;
    if ( !v6 )
      v4 = (wchar_t *)a1;
    if ( *v4 )
    {
      v7 = *v4;
      do
      {
        if ( v7 == 32 )
          break;
        if ( *v4 == 9 )
          break;
        v7 = *++v4;
      }
      while ( *v4 );
    }
  }
  v8 = *v4;
  *v4 = 0;
  result = DuplicateString((size_t)a1, a2);
  if ( result >= 0 && !*a2 )
    result = -2147024809;
  *v4 = v8;
  return result;
}

```

## disassembly

```asm
0x40777d  mov     edi, edi
0x40777f  push    ebp
0x407780  mov     ebp, esp
0x407782  push    ecx
0x407783  push    ecx
0x407784  push    ebx
0x407785  push    esi; unsigned __int16 **
0x407786  push    edi; unsigned __int16 *
0x407787  push    20h ; ' '
0x407789  mov     [ebp+var_8], edx
0x40778c  mov     edi, ecx
0x40778e  pop     edx
0x40778f  push    9
0x407791  pop     ecx
0x407792  push    2
0x407794  pop     ebx
0x407795  movzx   eax, word ptr [edi]
0x407798  cmp     dx, ax
0x40779b  jz      short loc_4077A2
0x40779d  cmp     cx, ax
0x4077a0  jnz     short loc_4077A6
0x4077a2  add     edi, ebx
0x4077a4  jmp     short loc_407795
0x4077a6  push    22h ; '"'
0x4077a8  pop     edx
0x4077a9  mov     [ebp+var_4], edi
0x4077ac  cmp     dx, ax
0x4077af  jnz     short loc_4077D9
0x4077b1  add     edi, ebx
0x4077b3  xor     ecx, ecx
0x4077b5  mov     esi, edi
0x4077b7  movzx   eax, word ptr [edi]
0x4077ba  cmp     cx, ax
0x4077bd  jz      short loc_407819
0x4077bf  mov     ecx, eax
0x4077c1  cmp     dx, cx
0x4077c4  jz      short loc_407819
0x4077c6  add     esi, ebx
0x4077c8  xor     edx, edx
0x4077ca  push    22h ; '"'
0x4077cc  movzx   eax, word ptr [esi]
0x4077cf  cmp     dx, ax
0x4077d2  mov     ecx, eax
0x4077d4  pop     edx
0x4077d5  jnz     short loc_4077C1
0x4077d7  jmp     short loc_407819
0x4077d9  push    5Ch ; '\'; Ch
0x4077db  push    edi; Str
0x4077dc  call    ds:__imp__wcsrchr
0x4077e2  test    eax, eax
0x4077e4  pop     ecx
0x4077e5  pop     ecx
0x4077e6  lea     esi, [eax+2]
0x4077e9  cmovz   esi, edi
0x4077ec  xor     ecx, ecx
0x4077ee  movzx   eax, word ptr [esi]
0x4077f1  cmp     cx, ax
0x4077f4  jz      short loc_407819
0x4077f6  push    9
0x4077f8  mov     ecx, eax
0x4077fa  pop     edi
0x4077fb  push    20h ; ' '
0x4077fd  pop     eax
0x4077fe  cmp     ax, cx
0x407801  jz      short loc_407816
0x407803  cmp     di, [esi]
0x407806  jz      short loc_407816
0x407808  add     esi, ebx
0x40780a  xor     edx, edx
0x40780c  movzx   eax, word ptr [esi]
0x40780f  mov     ecx, eax
0x407811  cmp     dx, ax
0x407814  jnz     short loc_4077FB
0x407816  mov     edi, [ebp+var_4]
0x407819  movzx   ebx, word ptr [esi]
0x40781c  xor     eax, eax
0x40781e  mov     edx, [ebp+var_8]
0x407821  mov     ecx, edi
0x407823  mov     [esi], ax
0x407826  call    ?DuplicateString@@YGJPBGPAPAG@Z; DuplicateString(ushort const *,ushort * *)
0x40782b  test    eax, eax
0x40782d  js      short loc_40783D
0x40782f  mov     ecx, [ebp+var_8]
0x407832  mov     edx, 80070057h
0x407837  cmp     dword ptr [ecx], 0
0x40783a  cmovz   eax, edx
0x40783d  pop     edi
0x40783e  mov     [esi], bx
0x407841  pop     esi
0x407842  pop     ebx
0x407843  leave
0x407844  retn
```
