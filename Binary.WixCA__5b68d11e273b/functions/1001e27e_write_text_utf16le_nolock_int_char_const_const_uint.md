# write_text_utf16le_nolock(int,char const * const,uint)

- ea: `0x1001e27e`
- end: `0x1001e369`
- name: `?write_text_utf16le_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1001e585`

## callees

- `0x10010720`
- `0x10010ae0`
- `0x1001e27e`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1001e34e`
- `KERNEL32!GetLastError` at `0x1001e34e`
- `KERNEL32!WriteFile` at `0x1001e328`
- `KERNEL32!WriteFile` at `0x1001e328`

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
  hFile = *(HANDLE *)(dword_10034F30[a2 >> 6] + 56 * (a2 & 0x3F) + 24);
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
0x1001e27e  mov     edi, edi
0x1001e280  push    ebp
0x1001e281  mov     ebp, esp
0x1001e283  mov     eax, 1410h
0x1001e288  call    __alloca_probe
0x1001e28d  mov     eax, ___security_cookie
0x1001e292  xor     eax, ebp
0x1001e294  mov     [ebp+var_4], eax
0x1001e297  mov     ecx, [ebp+arg_4]
0x1001e29a  mov     eax, ecx
0x1001e29c  mov     edx, [ebp+arg_C]
0x1001e29f  and     ecx, 3Fh
0x1001e2a2  sar     eax, 6
0x1001e2a5  imul    ecx, 38h ; '8'
0x1001e2a8  push    ebx
0x1001e2a9  mov     ebx, [ebp+arg_0]
0x1001e2ac  mov     eax, dword_10034F30[eax*4]
0x1001e2b3  push    esi
0x1001e2b4  push    edi
0x1001e2b5  mov     edi, ebx
0x1001e2b7  mov     eax, [eax+ecx+18h]
0x1001e2bb  mov     ecx, [ebp+arg_8]
0x1001e2be  add     edx, ecx
0x1001e2c0  mov     [ebp+hFile], eax
0x1001e2c6  xor     eax, eax
0x1001e2c8  stosd
0x1001e2c9  mov     [ebp+var_1410], edx
0x1001e2cf  stosd
0x1001e2d0  stosd
0x1001e2d1  jmp     short loc_1001E348
0x1001e2d3  lea     esi, [ebp+Buffer]
0x1001e2d9  cmp     ecx, edx
0x1001e2db  jnb     short loc_1001E302
0x1001e2dd  movzx   eax, word ptr [ecx]
0x1001e2e0  add     ecx, 2
0x1001e2e3  cmp     eax, 0Ah
0x1001e2e6  jnz     short loc_1001E2F5
0x1001e2e8  add     dword ptr [ebx+8], 2
0x1001e2ec  push    0Dh
0x1001e2ee  pop     edi
0x1001e2ef  mov     [esi], di
0x1001e2f2  add     esi, 2
0x1001e2f5  mov     [esi], ax
0x1001e2f8  add     esi, 2
0x1001e2fb  lea     eax, [ebp+var_6]
0x1001e2fe  cmp     esi, eax
0x1001e300  jb      short loc_1001E2D9
0x1001e302  mov     edi, [ebp+hFile]
0x1001e308  lea     eax, [ebp+Buffer]
0x1001e30e  sub     esi, eax
0x1001e310  mov     [ebp+arg_8], ecx
0x1001e313  push    0; lpOverlapped
0x1001e315  lea     eax, [ebp+NumberOfBytesWritten]
0x1001e31b  and     esi, 0FFFFFFFEh
0x1001e31e  push    eax; lpNumberOfBytesWritten
0x1001e31f  push    esi; nNumberOfBytesToWrite
0x1001e320  lea     eax, [ebp+Buffer]
0x1001e326  push    eax; lpBuffer
0x1001e327  push    edi; hFile
0x1001e328  call    ds:WriteFile
0x1001e32e  test    eax, eax
0x1001e330  jz      short loc_1001E34E
0x1001e332  mov     eax, [ebp+NumberOfBytesWritten]
0x1001e338  add     [ebx+4], eax
0x1001e33b  cmp     eax, esi
0x1001e33d  jb      short loc_1001E356
0x1001e33f  mov     ecx, [ebp+arg_8]
0x1001e342  mov     edx, [ebp+var_1410]
0x1001e348  cmp     ecx, edx
0x1001e34a  jb      short loc_1001E2D3
0x1001e34c  jmp     short loc_1001E356
0x1001e34e  call    ds:GetLastError
0x1001e354  mov     [ebx], eax
0x1001e356  mov     ecx, [ebp+var_4]
0x1001e359  mov     eax, ebx
0x1001e35b  pop     edi
0x1001e35c  pop     esi
0x1001e35d  xor     ecx, ebp; StackCookie
0x1001e35f  pop     ebx
0x1001e360  call    @__security_check_cookie@4
0x1001e365  mov     esp, ebp
0x1001e367  pop     ebp
0x1001e368  retn
```
