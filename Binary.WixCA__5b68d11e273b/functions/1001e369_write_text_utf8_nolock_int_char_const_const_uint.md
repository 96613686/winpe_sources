# write_text_utf8_nolock(int,char const * const,uint)

- ea: `0x1001e369`
- end: `0x1001e49d`
- name: `?write_text_utf8_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1001e585`

## callees

- `0x10010720`
- `0x10010ae0`
- `0x10019f50`
- `0x1001e369`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1001e482`
- `KERNEL32!GetLastError` at `0x1001e482`
- `KERNEL32!WriteFile` at `0x1001e452`
- `KERNEL32!WriteFile` at `0x1001e452`

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
  hFile = *(HANDLE *)(dword_10034F30[a2 >> 6] + 56 * (a2 & 0x3F) + 24);
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
0x1001e369  mov     edi, edi
0x1001e36b  push    ebp
0x1001e36c  mov     ebp, esp
0x1001e36e  mov     eax, 1418h
0x1001e373  call    __alloca_probe
0x1001e378  mov     eax, ___security_cookie
0x1001e37d  xor     eax, ebp
0x1001e37f  mov     [ebp+var_4], eax
0x1001e382  mov     ecx, [ebp+arg_4]
0x1001e385  mov     eax, ecx
0x1001e387  mov     edx, [ebp+arg_8]
0x1001e38a  and     ecx, 3Fh
0x1001e38d  sar     eax, 6
0x1001e390  imul    ecx, 38h ; '8'
0x1001e393  push    ebx
0x1001e394  push    esi
0x1001e395  mov     eax, dword_10034F30[eax*4]
0x1001e39c  mov     esi, [ebp+arg_0]
0x1001e39f  push    edi
0x1001e3a0  mov     edi, esi
0x1001e3a2  mov     eax, [eax+ecx+18h]
0x1001e3a6  mov     ecx, [ebp+arg_C]
0x1001e3a9  mov     [ebp+hFile], eax
0x1001e3af  add     ecx, edx
0x1001e3b1  xor     eax, eax
0x1001e3b3  mov     [ebp+var_140C], ecx
0x1001e3b9  stosd
0x1001e3ba  stosd
0x1001e3bb  stosd
0x1001e3bc  mov     edi, edx
0x1001e3be  cmp     edx, ecx
0x1001e3c0  jnb     loc_1001E48A
0x1001e3c6  mov     esi, [ebp+var_140C]
0x1001e3cc  lea     eax, [ebp+WideCharStr]
0x1001e3d2  cmp     edi, esi
0x1001e3d4  jnb     short loc_1001E3F7
0x1001e3d6  movzx   ecx, word ptr [edi]
0x1001e3d9  add     edi, 2
0x1001e3dc  cmp     ecx, 0Ah
0x1001e3df  jnz     short loc_1001E3EA
0x1001e3e1  push    0Dh
0x1001e3e3  pop     edx
0x1001e3e4  mov     [eax], dx
0x1001e3e7  add     eax, 2
0x1001e3ea  mov     [eax], cx
0x1001e3ed  add     eax, 2
0x1001e3f0  lea     ecx, [ebp+var_8]
0x1001e3f3  cmp     eax, ecx
0x1001e3f5  jb      short loc_1001E3D2
0x1001e3f7  push    0; int
0x1001e3f9  push    0; int
0x1001e3fb  push    0D55h; cbMultiByte
0x1001e400  lea     ecx, [ebp+MultiByteStr]
0x1001e406  push    ecx; lpMultiByteStr
0x1001e407  lea     ecx, [ebp+WideCharStr]
0x1001e40d  sub     eax, ecx
0x1001e40f  sar     eax, 1
0x1001e411  push    eax; cchWideChar
0x1001e412  mov     eax, ecx
0x1001e414  push    eax; lpWideCharStr
0x1001e415  push    0; int
0x1001e417  push    0FDE9h; CodePage
0x1001e41c  call    ___acrt_WideCharToMultiByte
0x1001e421  mov     esi, [ebp+arg_0]
0x1001e424  add     esp, 20h
0x1001e427  mov     [ebp+var_1418], eax
0x1001e42d  test    eax, eax
0x1001e42f  jz      short loc_1001E482
0x1001e431  xor     ebx, ebx
0x1001e433  test    eax, eax
0x1001e435  jz      short loc_1001E46C
0x1001e437  push    0; lpOverlapped
0x1001e439  lea     ecx, [ebp+NumberOfBytesWritten]
0x1001e43f  sub     eax, ebx
0x1001e441  push    ecx; lpNumberOfBytesWritten
0x1001e442  push    eax; nNumberOfBytesToWrite
0x1001e443  lea     eax, [ebp+MultiByteStr]
0x1001e449  add     eax, ebx
0x1001e44b  push    eax; lpBuffer
0x1001e44c  push    [ebp+hFile]; hFile
0x1001e452  call    ds:WriteFile
0x1001e458  test    eax, eax
0x1001e45a  jz      short loc_1001E482
0x1001e45c  add     ebx, [ebp+NumberOfBytesWritten]
0x1001e462  mov     eax, [ebp+var_1418]
0x1001e468  cmp     ebx, eax
0x1001e46a  jb      short loc_1001E437
0x1001e46c  mov     eax, edi
0x1001e46e  sub     eax, [ebp+arg_8]
0x1001e471  mov     [esi+4], eax
0x1001e474  cmp     edi, [ebp+var_140C]
0x1001e47a  jb      loc_1001E3C6
0x1001e480  jmp     short loc_1001E48A
0x1001e482  call    ds:GetLastError
0x1001e488  mov     [esi], eax
0x1001e48a  mov     ecx, [ebp+var_4]
0x1001e48d  mov     eax, esi
0x1001e48f  pop     edi
0x1001e490  pop     esi
0x1001e491  xor     ecx, ebp; StackCookie
0x1001e493  pop     ebx
0x1001e494  call    @__security_check_cookie@4
0x1001e499  mov     esp, ebp
0x1001e49b  pop     ebp
0x1001e49c  retn
```
