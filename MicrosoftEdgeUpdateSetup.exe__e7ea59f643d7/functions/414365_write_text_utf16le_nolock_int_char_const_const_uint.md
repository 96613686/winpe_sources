# write_text_utf16le_nolock(int,char const * const,uint)

- ea: `0x414365`
- end: `0x41444e`
- name: `?write_text_utf16le_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z`
- size: `233`
- prototype: `DWORD *__cdecl(DWORD *, int, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x414672`

## callees

- `0x408c05`
- `0x414365`
- `0x419430`

## import_xrefs

- `KERNEL32!WriteFile` at `0x41440f`
- `KERNEL32!WriteFile` at `0x41440f`
- `KERNEL32!GetLastError` at `0x414435`
- `KERNEL32!GetLastError` at `0x414435`

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
  hFile = *(HANDLE *)(dword_427018[a2 >> 6] + 56 * (a2 & 0x3F) + 24);
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
0x414365  mov     edi, edi
0x414367  push    ebp
0x414368  mov     ebp, esp
0x41436a  mov     eax, 1410h
0x41436f  call    __alloca_probe
0x414374  mov     eax, ___security_cookie
0x414379  xor     eax, ebp
0x41437b  mov     [ebp+var_4], eax
0x41437e  mov     ecx, [ebp+arg_4]
0x414381  mov     eax, ecx
0x414383  mov     edx, [ebp+arg_C]
0x414386  and     ecx, 3Fh
0x414389  sar     eax, 6
0x41438c  imul    ecx, 38h ; '8'
0x41438f  push    ebx
0x414390  mov     ebx, [ebp+arg_0]
0x414393  mov     eax, dword_427018[eax*4]
0x41439a  push    esi
0x41439b  push    edi
0x41439c  mov     edi, ebx
0x41439e  mov     eax, [eax+ecx+18h]
0x4143a2  mov     ecx, [ebp+arg_8]
0x4143a5  add     edx, ecx
0x4143a7  mov     [ebp+hFile], eax
0x4143ad  xor     eax, eax
0x4143af  stosd
0x4143b0  mov     [ebp+var_1410], edx
0x4143b6  stosd
0x4143b7  stosd
0x4143b8  jmp     short loc_41442F
0x4143ba  lea     esi, [ebp+Buffer]
0x4143c0  cmp     ecx, edx
0x4143c2  jnb     short loc_4143E9
0x4143c4  movzx   eax, word ptr [ecx]
0x4143c7  add     ecx, 2
0x4143ca  cmp     eax, 0Ah
0x4143cd  jnz     short loc_4143DC
0x4143cf  add     dword ptr [ebx+8], 2
0x4143d3  push    0Dh
0x4143d5  pop     edi
0x4143d6  mov     [esi], di
0x4143d9  add     esi, 2
0x4143dc  mov     [esi], ax
0x4143df  add     esi, 2
0x4143e2  lea     eax, [ebp+var_6]
0x4143e5  cmp     esi, eax
0x4143e7  jb      short loc_4143C0
0x4143e9  mov     edi, [ebp+hFile]
0x4143ef  lea     eax, [ebp+Buffer]
0x4143f5  sub     esi, eax
0x4143f7  mov     [ebp+arg_8], ecx
0x4143fa  push    0; lpOverlapped
0x4143fc  lea     eax, [ebp+NumberOfBytesWritten]
0x414402  and     esi, 0FFFFFFFEh
0x414405  push    eax; lpNumberOfBytesWritten
0x414406  push    esi; nNumberOfBytesToWrite
0x414407  lea     eax, [ebp+Buffer]
0x41440d  push    eax; lpBuffer
0x41440e  push    edi; hFile
0x41440f  call    ds:WriteFile
0x414415  test    eax, eax
0x414417  jz      short loc_414435
0x414419  mov     eax, [ebp+NumberOfBytesWritten]
0x41441f  add     [ebx+4], eax
0x414422  cmp     eax, esi
0x414424  jb      short loc_41443D
0x414426  mov     ecx, [ebp+arg_8]
0x414429  mov     edx, [ebp+var_1410]
0x41442f  cmp     ecx, edx
0x414431  jb      short loc_4143BA
0x414433  jmp     short loc_41443D
0x414435  call    ds:GetLastError
0x41443b  mov     [ebx], eax
0x41443d  mov     ecx, [ebp+var_4]
0x414440  mov     eax, ebx
0x414442  pop     edi
0x414443  pop     esi
0x414444  xor     ecx, ebp; StackCookie
0x414446  pop     ebx
0x414447  call    @__security_check_cookie@4
0x41444c  leave
0x41444d  retn
```
