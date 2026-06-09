# write_text_utf16le_nolock(int,char const * const,uint)

- ea: `0x418d2a`
- end: `0x418e13`
- name: `?write_text_utf16le_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z`
- size: `233`
- prototype: `DWORD *__cdecl(DWORD *, int, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x419037`

## callees

- `0x40d08d`
- `0x418d2a`
- `0x41dcf0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x418dd4`
- `KERNEL32!WriteFile` at `0x418dd4`
- `KERNEL32!GetLastError` at `0x418dfa`
- `KERNEL32!GetLastError` at `0x418dfa`

## pseudocode

```c
DWORD *__cdecl write_text_utf16le_nolock(DWORD *a1, int a2, unsigned __int16 *a3, int a4)
{
  unsigned __int16 *v4; // ecx
  unsigned int v5; // edx
  char *v6; // esi
  int v7; // eax
  DWORD v8; // esi
  DWORD v9; // eax
  char *v11; // [esp+Ch] [ebp-1410h]
  DWORD NumberOfBytesWritten; // [esp+10h] [ebp-140Ch] BYREF
  HANDLE hFile; // [esp+14h] [ebp-1408h]
  _BYTE Buffer[5118]; // [esp+18h] [ebp-1404h] BYREF
  char v15; // [esp+1416h] [ebp-6h] BYREF
  unsigned __int16 *v16; // [esp+142Ch] [ebp+10h]

  v4 = a3;
  v5 = (unsigned int)a3 + a4;
  hFile = *(HANDLE *)(dword_43E588[a2 >> 6] + 56 * (a2 & 0x3F) + 24);
  *a1 = 0;
  v11 = (char *)a3 + a4;
  a1[1] = 0;
  a1[2] = 0;
  while ( (unsigned int)v4 < v5 )
  {
    v6 = Buffer;
    do
    {
      if ( (unsigned int)v4 >= v5 )
        break;
      v7 = *v4++;
      if ( v7 == 10 )
      {
        a1[2] += 2;
        *(_WORD *)v6 = 13;
        v6 += 2;
      }
      *(_WORD *)v6 = v7;
      v6 += 2;
    }
    while ( v6 < &v15 );
    v16 = v4;
    v8 = (v6 - Buffer) & 0xFFFFFFFE;
    if ( !WriteFile(hFile, Buffer, v8, &NumberOfBytesWritten, 0) )
    {
      *a1 = GetLastError();
      return a1;
    }
    v9 = NumberOfBytesWritten;
    a1[1] += NumberOfBytesWritten;
    if ( v9 < v8 )
      return a1;
    v4 = v16;
    v5 = (unsigned int)v11;
  }
  return a1;
}

```

## disassembly

```asm
0x418d2a  mov     edi, edi
0x418d2c  push    ebp
0x418d2d  mov     ebp, esp
0x418d2f  mov     eax, 1410h
0x418d34  call    __alloca_probe
0x418d39  mov     eax, ___security_cookie
0x418d3e  xor     eax, ebp
0x418d40  mov     [ebp+var_4], eax
0x418d43  mov     ecx, [ebp+arg_4]
0x418d46  mov     eax, ecx
0x418d48  mov     edx, [ebp+arg_C]
0x418d4b  and     ecx, 3Fh
0x418d4e  sar     eax, 6
0x418d51  imul    ecx, 38h ; '8'
0x418d54  push    ebx
0x418d55  mov     ebx, [ebp+arg_0]
0x418d58  mov     eax, dword_43E588[eax*4]
0x418d5f  push    esi
0x418d60  push    edi
0x418d61  mov     edi, ebx
0x418d63  mov     eax, [eax+ecx+18h]
0x418d67  mov     ecx, [ebp+arg_8]
0x418d6a  add     edx, ecx
0x418d6c  mov     [ebp+hFile], eax
0x418d72  xor     eax, eax
0x418d74  stosd
0x418d75  mov     [ebp+var_1410], edx
0x418d7b  stosd
0x418d7c  stosd
0x418d7d  jmp     short loc_418DF4
0x418d7f  lea     esi, [ebp+Buffer]
0x418d85  cmp     ecx, edx
0x418d87  jnb     short loc_418DAE
0x418d89  movzx   eax, word ptr [ecx]
0x418d8c  add     ecx, 2
0x418d8f  cmp     eax, 0Ah
0x418d92  jnz     short loc_418DA1
0x418d94  add     dword ptr [ebx+8], 2
0x418d98  push    0Dh
0x418d9a  pop     edi
0x418d9b  mov     [esi], di
0x418d9e  add     esi, 2
0x418da1  mov     [esi], ax
0x418da4  add     esi, 2
0x418da7  lea     eax, [ebp+var_6]
0x418daa  cmp     esi, eax
0x418dac  jb      short loc_418D85
0x418dae  mov     edi, [ebp+hFile]
0x418db4  lea     eax, [ebp+Buffer]
0x418dba  sub     esi, eax
0x418dbc  mov     [ebp+arg_8], ecx
0x418dbf  push    0; lpOverlapped
0x418dc1  lea     eax, [ebp+NumberOfBytesWritten]
0x418dc7  and     esi, 0FFFFFFFEh
0x418dca  push    eax; lpNumberOfBytesWritten
0x418dcb  push    esi; nNumberOfBytesToWrite
0x418dcc  lea     eax, [ebp+Buffer]
0x418dd2  push    eax; lpBuffer
0x418dd3  push    edi; hFile
0x418dd4  call    ds:WriteFile
0x418dda  test    eax, eax
0x418ddc  jz      short loc_418DFA
0x418dde  mov     eax, [ebp+NumberOfBytesWritten]
0x418de4  add     [ebx+4], eax
0x418de7  cmp     eax, esi
0x418de9  jb      short loc_418E02
0x418deb  mov     ecx, [ebp+arg_8]
0x418dee  mov     edx, [ebp+var_1410]
0x418df4  cmp     ecx, edx
0x418df6  jb      short loc_418D7F
0x418df8  jmp     short loc_418E02
0x418dfa  call    ds:GetLastError
0x418e00  mov     [ebx], eax
0x418e02  mov     ecx, [ebp+var_4]
0x418e05  mov     eax, ebx
0x418e07  pop     edi
0x418e08  pop     esi
0x418e09  xor     ecx, ebp; StackCookie
0x418e0b  pop     ebx
0x418e0c  call    @__security_check_cookie@4
0x418e11  leave
0x418e12  retn
```
