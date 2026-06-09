# write_text_ansi_nolock(int,char const * const,uint)

- ea: `0x1001e1a1`
- end: `0x1001e27e`
- name: `?write_text_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1001e585`

## callees

- `0x10010720`
- `0x10010ae0`
- `0x1001e1a1`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1001e263`
- `KERNEL32!GetLastError` at `0x1001e263`
- `KERNEL32!WriteFile` at `0x1001e23d`
- `KERNEL32!WriteFile` at `0x1001e23d`

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
  hFile = *(HANDLE *)(dword_10034F30[a2 >> 6] + 56 * (a2 & 0x3F) + 24);
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
0x1001e1a1  mov     edi, edi
0x1001e1a3  push    ebp
0x1001e1a4  mov     ebp, esp
0x1001e1a6  mov     eax, 140Ch
0x1001e1ab  call    __alloca_probe
0x1001e1b0  mov     eax, ___security_cookie
0x1001e1b5  xor     eax, ebp
0x1001e1b7  mov     [ebp+var_4], eax
0x1001e1ba  mov     ecx, [ebp+arg_4]
0x1001e1bd  mov     eax, ecx
0x1001e1bf  mov     edx, [ebp+arg_C]
0x1001e1c2  and     ecx, 3Fh
0x1001e1c5  sar     eax, 6
0x1001e1c8  imul    ecx, 38h ; '8'
0x1001e1cb  push    ebx
0x1001e1cc  mov     ebx, [ebp+arg_0]
0x1001e1cf  mov     eax, dword_10034F30[eax*4]
0x1001e1d6  push    esi
0x1001e1d7  push    edi
0x1001e1d8  mov     edi, ebx
0x1001e1da  mov     eax, [eax+ecx+18h]
0x1001e1de  mov     ecx, [ebp+arg_8]
0x1001e1e1  add     edx, ecx
0x1001e1e3  mov     [ebp+hFile], eax
0x1001e1e9  xor     eax, eax
0x1001e1eb  stosd
0x1001e1ec  mov     [ebp+var_140C], edx
0x1001e1f2  stosd
0x1001e1f3  stosd
0x1001e1f4  cmp     ecx, edx
0x1001e1f6  jnb     short loc_1001E26B
0x1001e1f8  mov     edi, [ebp+hFile]
0x1001e1fe  lea     esi, [ebp+Buffer]
0x1001e204  cmp     ecx, edx
0x1001e206  jnb     short loc_1001E220
0x1001e208  mov     al, [ecx]
0x1001e20a  inc     ecx
0x1001e20b  cmp     al, 0Ah
0x1001e20d  jnz     short loc_1001E216
0x1001e20f  inc     dword ptr [ebx+8]
0x1001e212  mov     byte ptr [esi], 0Dh
0x1001e215  inc     esi
0x1001e216  mov     [esi], al
0x1001e218  inc     esi
0x1001e219  lea     eax, [ebp+var_5]
0x1001e21c  cmp     esi, eax
0x1001e21e  jb      short loc_1001E204
0x1001e220  lea     eax, [ebp+Buffer]
0x1001e226  mov     [ebp+arg_8], ecx
0x1001e229  sub     esi, eax
0x1001e22b  lea     eax, [ebp+hFile]
0x1001e231  push    0; lpOverlapped
0x1001e233  push    eax; lpNumberOfBytesWritten
0x1001e234  push    esi; nNumberOfBytesToWrite
0x1001e235  lea     eax, [ebp+Buffer]
0x1001e23b  push    eax; lpBuffer
0x1001e23c  push    edi; hFile
0x1001e23d  call    ds:WriteFile
0x1001e243  test    eax, eax
0x1001e245  jz      short loc_1001E263
0x1001e247  mov     eax, [ebp+hFile]
0x1001e24d  add     [ebx+4], eax
0x1001e250  cmp     eax, esi
0x1001e252  jb      short loc_1001E26B
0x1001e254  mov     ecx, [ebp+arg_8]
0x1001e257  mov     edx, [ebp+var_140C]
0x1001e25d  cmp     ecx, edx
0x1001e25f  jb      short loc_1001E1FE
0x1001e261  jmp     short loc_1001E26B
0x1001e263  call    ds:GetLastError
0x1001e269  mov     [ebx], eax
0x1001e26b  mov     ecx, [ebp+var_4]
0x1001e26e  mov     eax, ebx
0x1001e270  pop     edi
0x1001e271  pop     esi
0x1001e272  xor     ecx, ebp; StackCookie
0x1001e274  pop     ebx
0x1001e275  call    @__security_check_cookie@4
0x1001e27a  mov     esp, ebp
0x1001e27c  pop     ebp
0x1001e27d  retn
```
