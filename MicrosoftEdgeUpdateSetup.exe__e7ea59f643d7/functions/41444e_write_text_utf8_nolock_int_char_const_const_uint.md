# write_text_utf8_nolock(int,char const * const,uint)

- ea: `0x41444e`
- end: `0x414580`
- name: `?write_text_utf8_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z`
- size: `306`
- prototype: `DWORD *__cdecl(DWORD *, int, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x414672`

## callees

- `0x408c05`
- `0x410055`
- `0x41444e`
- `0x419430`

## import_xrefs

- `KERNEL32!WriteFile` at `0x414537`
- `KERNEL32!WriteFile` at `0x414537`
- `KERNEL32!GetLastError` at `0x414567`
- `KERNEL32!GetLastError` at `0x414567`

## pseudocode

```c
DWORD *__cdecl write_text_utf8_nolock(DWORD *a1, int a2, unsigned int a3, int a4)
{
  DWORD *v4; // esi
  unsigned __int16 *v5; // edi
  unsigned int v6; // esi
  WCHAR *v7; // eax
  int v8; // ecx
  int v9; // eax
  unsigned int v10; // ebx
  unsigned int v12; // [esp+Ch] [ebp-1418h]
  DWORD NumberOfBytesWritten; // [esp+10h] [ebp-1414h] BYREF
  HANDLE hFile; // [esp+14h] [ebp-1410h]
  unsigned int v15; // [esp+18h] [ebp-140Ch]
  CHAR MultiByteStr[3416]; // [esp+1Ch] [ebp-1408h] BYREF
  WCHAR WideCharStr[852]; // [esp+D74h] [ebp-6B0h] BYREF
  char v18; // [esp+141Ch] [ebp-8h] BYREF

  v4 = a1;
  hFile = *(HANDLE *)(dword_427018[a2 >> 6] + 56 * (a2 & 0x3F) + 24);
  v15 = a3 + a4;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v5 = (unsigned __int16 *)a3;
  if ( a3 < a3 + a4 )
  {
LABEL_2:
    v6 = v15;
    v7 = WideCharStr;
    do
    {
      if ( (unsigned int)v5 >= v6 )
        break;
      v8 = *v5++;
      if ( v8 == 10 )
        *v7++ = 13;
      *v7++ = v8;
    }
    while ( v7 < (WCHAR *)&v18 );
    v9 = __acrt_WideCharToMultiByte(0xFDE9u, 0, WideCharStr, v7 - WideCharStr, MultiByteStr, 3413, 0, 0);
    v4 = a1;
    v12 = v9;
    if ( v9 )
    {
      v10 = 0;
      while ( WriteFile(hFile, &MultiByteStr[v10], v9 - v10, &NumberOfBytesWritten, 0) )
      {
        v10 += NumberOfBytesWritten;
        v9 = v12;
        if ( v10 >= v12 )
        {
          a1[1] = (DWORD)v5 - a3;
          if ( (unsigned int)v5 < v15 )
            goto LABEL_2;
          return v4;
        }
      }
    }
    *a1 = GetLastError();
  }
  return v4;
}

```

## disassembly

```asm
0x41444e  mov     edi, edi
0x414450  push    ebp
0x414451  mov     ebp, esp
0x414453  mov     eax, 1418h
0x414458  call    __alloca_probe
0x41445d  mov     eax, ___security_cookie
0x414462  xor     eax, ebp
0x414464  mov     [ebp+var_4], eax
0x414467  mov     ecx, [ebp+arg_4]
0x41446a  mov     eax, ecx
0x41446c  mov     edx, [ebp+arg_8]
0x41446f  and     ecx, 3Fh
0x414472  sar     eax, 6
0x414475  imul    ecx, 38h ; '8'
0x414478  push    ebx
0x414479  push    esi
0x41447a  mov     eax, dword_427018[eax*4]
0x414481  mov     esi, [ebp+arg_0]
0x414484  push    edi
0x414485  mov     edi, esi
0x414487  mov     eax, [eax+ecx+18h]
0x41448b  mov     ecx, [ebp+arg_C]
0x41448e  mov     [ebp+hFile], eax
0x414494  add     ecx, edx
0x414496  xor     eax, eax
0x414498  mov     [ebp+var_140C], ecx
0x41449e  stosd
0x41449f  stosd
0x4144a0  stosd
0x4144a1  mov     edi, edx
0x4144a3  cmp     edx, ecx
0x4144a5  jnb     loc_41456F
0x4144ab  mov     esi, [ebp+var_140C]
0x4144b1  lea     eax, [ebp+WideCharStr]
0x4144b7  cmp     edi, esi
0x4144b9  jnb     short loc_4144DC
0x4144bb  movzx   ecx, word ptr [edi]
0x4144be  add     edi, 2
0x4144c1  cmp     ecx, 0Ah
0x4144c4  jnz     short loc_4144CF
0x4144c6  push    0Dh
0x4144c8  pop     edx
0x4144c9  mov     [eax], dx
0x4144cc  add     eax, 2
0x4144cf  mov     [eax], cx
0x4144d2  add     eax, 2
0x4144d5  lea     ecx, [ebp+var_8]
0x4144d8  cmp     eax, ecx
0x4144da  jb      short loc_4144B7
0x4144dc  push    0; int
0x4144de  push    0; int
0x4144e0  push    0D55h; cbMultiByte
0x4144e5  lea     ecx, [ebp+MultiByteStr]
0x4144eb  push    ecx; lpMultiByteStr
0x4144ec  lea     ecx, [ebp+WideCharStr]
0x4144f2  sub     eax, ecx
0x4144f4  sar     eax, 1
0x4144f6  push    eax; cchWideChar
0x4144f7  mov     eax, ecx
0x4144f9  push    eax; lpWideCharStr
0x4144fa  push    0; int
0x4144fc  push    0FDE9h; CodePage
0x414501  call    ___acrt_WideCharToMultiByte
0x414506  mov     esi, [ebp+arg_0]
0x414509  add     esp, 20h
0x41450c  mov     [ebp+var_1418], eax
0x414512  test    eax, eax
0x414514  jz      short loc_414567
0x414516  xor     ebx, ebx
0x414518  test    eax, eax
0x41451a  jz      short loc_414551
0x41451c  push    0; lpOverlapped
0x41451e  lea     ecx, [ebp+NumberOfBytesWritten]
0x414524  sub     eax, ebx
0x414526  push    ecx; lpNumberOfBytesWritten
0x414527  push    eax; nNumberOfBytesToWrite
0x414528  lea     eax, [ebp+MultiByteStr]
0x41452e  add     eax, ebx
0x414530  push    eax; lpBuffer
0x414531  push    [ebp+hFile]; hFile
0x414537  call    ds:WriteFile
0x41453d  test    eax, eax
0x41453f  jz      short loc_414567
0x414541  add     ebx, [ebp+NumberOfBytesWritten]
0x414547  mov     eax, [ebp+var_1418]
0x41454d  cmp     ebx, eax
0x41454f  jb      short loc_41451C
0x414551  mov     eax, edi
0x414553  sub     eax, [ebp+arg_8]
0x414556  mov     [esi+4], eax
0x414559  cmp     edi, [ebp+var_140C]
0x41455f  jb      loc_4144AB
0x414565  jmp     short loc_41456F
0x414567  call    ds:GetLastError
0x41456d  mov     [esi], eax
0x41456f  mov     ecx, [ebp+var_4]
0x414572  mov     eax, esi
0x414574  pop     edi
0x414575  pop     esi
0x414576  xor     ecx, ebp; StackCookie
0x414578  pop     ebx
0x414579  call    @__security_check_cookie@4
0x41457e  leave
0x41457f  retn
```
