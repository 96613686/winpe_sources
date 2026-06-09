# write_text_ansi_nolock(int,char const * const,uint)

- ea: `0x413c2a`
- end: `0x413d05`
- name: `?write_text_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z`
- size: `219`
- prototype: `DWORD *__cdecl(DWORD *, int, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x414012`

## callees

- `0x40b3e3`
- `0x413c2a`
- `0x416740`

## import_xrefs

- `KERNEL32!GetLastError` at `0x413cec`
- `KERNEL32!GetLastError` at `0x413cec`
- `KERNEL32!WriteFile` at `0x413cc6`
- `KERNEL32!WriteFile` at `0x413cc6`

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
  hFile = *(HANDLE *)(dword_4181B0[a2 >> 6] + 56 * (a2 & 0x3F) + 24);
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
0x413c2a  mov     edi, edi
0x413c2c  push    ebp
0x413c2d  mov     ebp, esp
0x413c2f  mov     eax, 140Ch
0x413c34  call    __alloca_probe
0x413c39  mov     eax, ___security_cookie
0x413c3e  xor     eax, ebp
0x413c40  mov     [ebp+var_4], eax
0x413c43  mov     ecx, [ebp+arg_4]
0x413c46  mov     eax, ecx
0x413c48  mov     edx, [ebp+arg_C]
0x413c4b  and     ecx, 3Fh
0x413c4e  sar     eax, 6
0x413c51  imul    ecx, 38h ; '8'
0x413c54  push    ebx
0x413c55  mov     ebx, [ebp+arg_0]
0x413c58  mov     eax, dword_4181B0[eax*4]
0x413c5f  push    esi
0x413c60  push    edi
0x413c61  mov     edi, ebx
0x413c63  mov     eax, [eax+ecx+18h]
0x413c67  mov     ecx, [ebp+arg_8]
0x413c6a  add     edx, ecx
0x413c6c  mov     [ebp+hFile], eax
0x413c72  xor     eax, eax
0x413c74  stosd
0x413c75  mov     [ebp+var_140C], edx
0x413c7b  stosd
0x413c7c  stosd
0x413c7d  cmp     ecx, edx
0x413c7f  jnb     short loc_413CF4
0x413c81  mov     edi, [ebp+hFile]
0x413c87  lea     esi, [ebp+Buffer]
0x413c8d  cmp     ecx, edx
0x413c8f  jnb     short loc_413CA9
0x413c91  mov     al, [ecx]
0x413c93  inc     ecx
0x413c94  cmp     al, 0Ah
0x413c96  jnz     short loc_413C9F
0x413c98  inc     dword ptr [ebx+8]
0x413c9b  mov     byte ptr [esi], 0Dh
0x413c9e  inc     esi
0x413c9f  mov     [esi], al
0x413ca1  inc     esi
0x413ca2  lea     eax, [ebp+var_5]
0x413ca5  cmp     esi, eax
0x413ca7  jb      short loc_413C8D
0x413ca9  lea     eax, [ebp+Buffer]
0x413caf  mov     [ebp+arg_8], ecx
0x413cb2  sub     esi, eax
0x413cb4  lea     eax, [ebp+hFile]
0x413cba  push    0; lpOverlapped
0x413cbc  push    eax; lpNumberOfBytesWritten
0x413cbd  push    esi; nNumberOfBytesToWrite
0x413cbe  lea     eax, [ebp+Buffer]
0x413cc4  push    eax; lpBuffer
0x413cc5  push    edi; hFile
0x413cc6  call    ds:WriteFile
0x413ccc  test    eax, eax
0x413cce  jz      short loc_413CEC
0x413cd0  mov     eax, [ebp+hFile]
0x413cd6  add     [ebx+4], eax
0x413cd9  cmp     eax, esi
0x413cdb  jb      short loc_413CF4
0x413cdd  mov     ecx, [ebp+arg_8]
0x413ce0  mov     edx, [ebp+var_140C]
0x413ce6  cmp     ecx, edx
0x413ce8  jb      short loc_413C87
0x413cea  jmp     short loc_413CF4
0x413cec  call    ds:GetLastError
0x413cf2  mov     [ebx], eax
0x413cf4  mov     ecx, [ebp+var_4]
0x413cf7  mov     eax, ebx
0x413cf9  pop     edi
0x413cfa  pop     esi
0x413cfb  xor     ecx, ebp; StackCookie
0x413cfd  pop     ebx
0x413cfe  call    @__security_check_cookie@4
0x413d03  leave
0x413d04  retn
```
