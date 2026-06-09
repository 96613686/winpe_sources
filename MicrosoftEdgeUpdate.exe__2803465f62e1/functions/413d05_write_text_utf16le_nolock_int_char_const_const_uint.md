# write_text_utf16le_nolock(int,char const * const,uint)

- ea: `0x413d05`
- end: `0x413dee`
- name: `?write_text_utf16le_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z`
- size: `233`
- prototype: `DWORD *__cdecl(DWORD *, int, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x414012`

## callees

- `0x40b3e3`
- `0x413d05`
- `0x416740`

## import_xrefs

- `KERNEL32!GetLastError` at `0x413dd5`
- `KERNEL32!GetLastError` at `0x413dd5`
- `KERNEL32!WriteFile` at `0x413daf`
- `KERNEL32!WriteFile` at `0x413daf`

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
  hFile = *(HANDLE *)(dword_4181B0[a2 >> 6] + 56 * (a2 & 0x3F) + 24);
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
0x413d05  mov     edi, edi
0x413d07  push    ebp
0x413d08  mov     ebp, esp
0x413d0a  mov     eax, 1410h
0x413d0f  call    __alloca_probe
0x413d14  mov     eax, ___security_cookie
0x413d19  xor     eax, ebp
0x413d1b  mov     [ebp+var_4], eax
0x413d1e  mov     ecx, [ebp+arg_4]
0x413d21  mov     eax, ecx
0x413d23  mov     edx, [ebp+arg_C]
0x413d26  and     ecx, 3Fh
0x413d29  sar     eax, 6
0x413d2c  imul    ecx, 38h ; '8'
0x413d2f  push    ebx
0x413d30  mov     ebx, [ebp+arg_0]
0x413d33  mov     eax, dword_4181B0[eax*4]
0x413d3a  push    esi
0x413d3b  push    edi
0x413d3c  mov     edi, ebx
0x413d3e  mov     eax, [eax+ecx+18h]
0x413d42  mov     ecx, [ebp+arg_8]
0x413d45  add     edx, ecx
0x413d47  mov     [ebp+hFile], eax
0x413d4d  xor     eax, eax
0x413d4f  stosd
0x413d50  mov     [ebp+var_1410], edx
0x413d56  stosd
0x413d57  stosd
0x413d58  jmp     short loc_413DCF
0x413d5a  lea     esi, [ebp+Buffer]
0x413d60  cmp     ecx, edx
0x413d62  jnb     short loc_413D89
0x413d64  movzx   eax, word ptr [ecx]
0x413d67  add     ecx, 2
0x413d6a  cmp     eax, 0Ah
0x413d6d  jnz     short loc_413D7C
0x413d6f  add     dword ptr [ebx+8], 2
0x413d73  push    0Dh
0x413d75  pop     edi
0x413d76  mov     [esi], di
0x413d79  add     esi, 2
0x413d7c  mov     [esi], ax
0x413d7f  add     esi, 2
0x413d82  lea     eax, [ebp+var_6]
0x413d85  cmp     esi, eax
0x413d87  jb      short loc_413D60
0x413d89  mov     edi, [ebp+hFile]
0x413d8f  lea     eax, [ebp+Buffer]
0x413d95  sub     esi, eax
0x413d97  mov     [ebp+arg_8], ecx
0x413d9a  push    0; lpOverlapped
0x413d9c  lea     eax, [ebp+NumberOfBytesWritten]
0x413da2  and     esi, 0FFFFFFFEh
0x413da5  push    eax; lpNumberOfBytesWritten
0x413da6  push    esi; nNumberOfBytesToWrite
0x413da7  lea     eax, [ebp+Buffer]
0x413dad  push    eax; lpBuffer
0x413dae  push    edi; hFile
0x413daf  call    ds:WriteFile
0x413db5  test    eax, eax
0x413db7  jz      short loc_413DD5
0x413db9  mov     eax, [ebp+NumberOfBytesWritten]
0x413dbf  add     [ebx+4], eax
0x413dc2  cmp     eax, esi
0x413dc4  jb      short loc_413DDD
0x413dc6  mov     ecx, [ebp+arg_8]
0x413dc9  mov     edx, [ebp+var_1410]
0x413dcf  cmp     ecx, edx
0x413dd1  jb      short loc_413D5A
0x413dd3  jmp     short loc_413DDD
0x413dd5  call    ds:GetLastError
0x413ddb  mov     [ebx], eax
0x413ddd  mov     ecx, [ebp+var_4]
0x413de0  mov     eax, ebx
0x413de2  pop     edi
0x413de3  pop     esi
0x413de4  xor     ecx, ebp; StackCookie
0x413de6  pop     ebx
0x413de7  call    @__security_check_cookie@4
0x413dec  leave
0x413ded  retn
```
