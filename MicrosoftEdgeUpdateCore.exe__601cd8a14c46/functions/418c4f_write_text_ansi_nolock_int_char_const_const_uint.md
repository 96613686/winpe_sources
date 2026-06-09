# write_text_ansi_nolock(int,char const * const,uint)

- ea: `0x418c4f`
- end: `0x418d2a`
- name: `?write_text_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z`
- size: `219`
- prototype: `DWORD *__cdecl(DWORD *, int, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x419037`

## callees

- `0x40d08d`
- `0x418c4f`
- `0x41dcf0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x418ceb`
- `KERNEL32!WriteFile` at `0x418ceb`
- `KERNEL32!GetLastError` at `0x418d11`
- `KERNEL32!GetLastError` at `0x418d11`

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
  hFile = *(HANDLE *)(dword_43E588[a2 >> 6] + 56 * (a2 & 0x3F) + 24);
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
0x418c4f  mov     edi, edi
0x418c51  push    ebp
0x418c52  mov     ebp, esp
0x418c54  mov     eax, 140Ch
0x418c59  call    __alloca_probe
0x418c5e  mov     eax, ___security_cookie
0x418c63  xor     eax, ebp
0x418c65  mov     [ebp+var_4], eax
0x418c68  mov     ecx, [ebp+arg_4]
0x418c6b  mov     eax, ecx
0x418c6d  mov     edx, [ebp+arg_C]
0x418c70  and     ecx, 3Fh
0x418c73  sar     eax, 6
0x418c76  imul    ecx, 38h ; '8'
0x418c79  push    ebx
0x418c7a  mov     ebx, [ebp+arg_0]
0x418c7d  mov     eax, dword_43E588[eax*4]
0x418c84  push    esi
0x418c85  push    edi
0x418c86  mov     edi, ebx
0x418c88  mov     eax, [eax+ecx+18h]
0x418c8c  mov     ecx, [ebp+arg_8]
0x418c8f  add     edx, ecx
0x418c91  mov     [ebp+hFile], eax
0x418c97  xor     eax, eax
0x418c99  stosd
0x418c9a  mov     [ebp+var_140C], edx
0x418ca0  stosd
0x418ca1  stosd
0x418ca2  cmp     ecx, edx
0x418ca4  jnb     short loc_418D19
0x418ca6  mov     edi, [ebp+hFile]
0x418cac  lea     esi, [ebp+Buffer]
0x418cb2  cmp     ecx, edx
0x418cb4  jnb     short loc_418CCE
0x418cb6  mov     al, [ecx]
0x418cb8  inc     ecx
0x418cb9  cmp     al, 0Ah
0x418cbb  jnz     short loc_418CC4
0x418cbd  inc     dword ptr [ebx+8]
0x418cc0  mov     byte ptr [esi], 0Dh
0x418cc3  inc     esi
0x418cc4  mov     [esi], al
0x418cc6  inc     esi
0x418cc7  lea     eax, [ebp+var_5]
0x418cca  cmp     esi, eax
0x418ccc  jb      short loc_418CB2
0x418cce  lea     eax, [ebp+Buffer]
0x418cd4  mov     [ebp+arg_8], ecx
0x418cd7  sub     esi, eax
0x418cd9  lea     eax, [ebp+hFile]
0x418cdf  push    0; lpOverlapped
0x418ce1  push    eax; lpNumberOfBytesWritten
0x418ce2  push    esi; nNumberOfBytesToWrite
0x418ce3  lea     eax, [ebp+Buffer]
0x418ce9  push    eax; lpBuffer
0x418cea  push    edi; hFile
0x418ceb  call    ds:WriteFile
0x418cf1  test    eax, eax
0x418cf3  jz      short loc_418D11
0x418cf5  mov     eax, [ebp+hFile]
0x418cfb  add     [ebx+4], eax
0x418cfe  cmp     eax, esi
0x418d00  jb      short loc_418D19
0x418d02  mov     ecx, [ebp+arg_8]
0x418d05  mov     edx, [ebp+var_140C]
0x418d0b  cmp     ecx, edx
0x418d0d  jb      short loc_418CAC
0x418d0f  jmp     short loc_418D19
0x418d11  call    ds:GetLastError
0x418d17  mov     [ebx], eax
0x418d19  mov     ecx, [ebp+var_4]
0x418d1c  mov     eax, ebx
0x418d1e  pop     edi
0x418d1f  pop     esi
0x418d20  xor     ecx, ebp; StackCookie
0x418d22  pop     ebx
0x418d23  call    @__security_check_cookie@4
0x418d28  leave
0x418d29  retn
```
