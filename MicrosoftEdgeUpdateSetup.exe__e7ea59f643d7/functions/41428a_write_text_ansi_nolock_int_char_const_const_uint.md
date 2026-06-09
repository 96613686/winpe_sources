# write_text_ansi_nolock(int,char const * const,uint)

- ea: `0x41428a`
- end: `0x414365`
- name: `?write_text_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z`
- size: `219`
- prototype: `DWORD *__cdecl(DWORD *, int, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x414672`

## callees

- `0x408c05`
- `0x41428a`
- `0x419430`

## import_xrefs

- `KERNEL32!WriteFile` at `0x414326`
- `KERNEL32!WriteFile` at `0x414326`
- `KERNEL32!GetLastError` at `0x41434c`
- `KERNEL32!GetLastError` at `0x41434c`

## pseudocode

```c
DWORD *__cdecl write_text_ansi_nolock(DWORD *a1, int a2, unsigned int a3, int a4)
{
  char *v4; // ecx
  unsigned int v5; // edx
  HANDLE v6; // edi
  char *v7; // esi
  char v8; // al
  DWORD v9; // esi
  HANDLE v10; // eax
  unsigned int v12; // [esp+Ch] [ebp-140Ch]
  HANDLE hFile; // [esp+10h] [ebp-1408h] BYREF
  _BYTE Buffer[5119]; // [esp+14h] [ebp-1404h] BYREF
  char v15; // [esp+1413h] [ebp-5h] BYREF
  char *v16; // [esp+1428h] [ebp+10h]

  v4 = (char *)a3;
  v5 = a3 + a4;
  hFile = *(HANDLE *)(dword_427018[a2 >> 6] + 56 * (a2 & 0x3F) + 24);
  *a1 = 0;
  v12 = a3 + a4;
  a1[1] = 0;
  a1[2] = 0;
  if ( a3 < a3 + a4 )
  {
    v6 = hFile;
    while ( 1 )
    {
      v7 = Buffer;
      do
      {
        if ( (unsigned int)v4 >= v5 )
          break;
        v8 = *v4++;
        if ( v8 == 10 )
        {
          ++a1[2];
          *v7++ = 13;
        }
        *v7++ = v8;
      }
      while ( v7 < &v15 );
      v16 = v4;
      v9 = v7 - Buffer;
      if ( !WriteFile(v6, Buffer, v9, (LPDWORD)&hFile, 0) )
        break;
      v10 = hFile;
      a1[1] += (DWORD)hFile;
      if ( (unsigned int)v10 >= v9 )
      {
        v4 = v16;
        v5 = v12;
        if ( (unsigned int)v16 < v12 )
          continue;
      }
      return a1;
    }
    *a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x41428a  mov     edi, edi
0x41428c  push    ebp
0x41428d  mov     ebp, esp
0x41428f  mov     eax, 140Ch
0x414294  call    __alloca_probe
0x414299  mov     eax, ___security_cookie
0x41429e  xor     eax, ebp
0x4142a0  mov     [ebp+var_4], eax
0x4142a3  mov     ecx, [ebp+arg_4]
0x4142a6  mov     eax, ecx
0x4142a8  mov     edx, [ebp+arg_C]
0x4142ab  and     ecx, 3Fh
0x4142ae  sar     eax, 6
0x4142b1  imul    ecx, 38h ; '8'
0x4142b4  push    ebx
0x4142b5  mov     ebx, [ebp+arg_0]
0x4142b8  mov     eax, dword_427018[eax*4]
0x4142bf  push    esi
0x4142c0  push    edi
0x4142c1  mov     edi, ebx
0x4142c3  mov     eax, [eax+ecx+18h]
0x4142c7  mov     ecx, [ebp+arg_8]
0x4142ca  add     edx, ecx
0x4142cc  mov     [ebp+hFile], eax
0x4142d2  xor     eax, eax
0x4142d4  stosd
0x4142d5  mov     [ebp+var_140C], edx
0x4142db  stosd
0x4142dc  stosd
0x4142dd  cmp     ecx, edx
0x4142df  jnb     short loc_414354
0x4142e1  mov     edi, [ebp+hFile]
0x4142e7  lea     esi, [ebp+Buffer]
0x4142ed  cmp     ecx, edx
0x4142ef  jnb     short loc_414309
0x4142f1  mov     al, [ecx]
0x4142f3  inc     ecx
0x4142f4  cmp     al, 0Ah
0x4142f6  jnz     short loc_4142FF
0x4142f8  inc     dword ptr [ebx+8]
0x4142fb  mov     byte ptr [esi], 0Dh
0x4142fe  inc     esi
0x4142ff  mov     [esi], al
0x414301  inc     esi
0x414302  lea     eax, [ebp+var_5]
0x414305  cmp     esi, eax
0x414307  jb      short loc_4142ED
0x414309  lea     eax, [ebp+Buffer]
0x41430f  mov     [ebp+arg_8], ecx
0x414312  sub     esi, eax
0x414314  lea     eax, [ebp+hFile]
0x41431a  push    0; lpOverlapped
0x41431c  push    eax; lpNumberOfBytesWritten
0x41431d  push    esi; nNumberOfBytesToWrite
0x41431e  lea     eax, [ebp+Buffer]
0x414324  push    eax; lpBuffer
0x414325  push    edi; hFile
0x414326  call    ds:WriteFile
0x41432c  test    eax, eax
0x41432e  jz      short loc_41434C
0x414330  mov     eax, [ebp+hFile]
0x414336  add     [ebx+4], eax
0x414339  cmp     eax, esi
0x41433b  jb      short loc_414354
0x41433d  mov     ecx, [ebp+arg_8]
0x414340  mov     edx, [ebp+var_140C]
0x414346  cmp     ecx, edx
0x414348  jb      short loc_4142E7
0x41434a  jmp     short loc_414354
0x41434c  call    ds:GetLastError
0x414352  mov     [ebx], eax
0x414354  mov     ecx, [ebp+var_4]
0x414357  mov     eax, ebx
0x414359  pop     edi
0x41435a  pop     esi
0x41435b  xor     ecx, ebp; StackCookie
0x41435d  pop     ebx
0x41435e  call    @__security_check_cookie@4
0x414363  leave
0x414364  retn
```
