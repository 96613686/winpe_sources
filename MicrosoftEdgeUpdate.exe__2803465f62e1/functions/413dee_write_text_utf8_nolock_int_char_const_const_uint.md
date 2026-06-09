# write_text_utf8_nolock(int,char const * const,uint)

- ea: `0x413dee`
- end: `0x413f20`
- name: `?write_text_utf8_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z`
- size: `306`
- prototype: `DWORD *__cdecl(DWORD *, int, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x414012`

## callees

- `0x40b3e3`
- `0x410e05`
- `0x413dee`
- `0x416740`

## import_xrefs

- `KERNEL32!GetLastError` at `0x413f07`
- `KERNEL32!GetLastError` at `0x413f07`
- `KERNEL32!WriteFile` at `0x413ed7`
- `KERNEL32!WriteFile` at `0x413ed7`

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
  hFile = *(HANDLE *)(dword_4181B0[a2 >> 6] + 56 * (a2 & 0x3F) + 24);
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
0x413dee  mov     edi, edi
0x413df0  push    ebp
0x413df1  mov     ebp, esp
0x413df3  mov     eax, 1418h
0x413df8  call    __alloca_probe
0x413dfd  mov     eax, ___security_cookie
0x413e02  xor     eax, ebp
0x413e04  mov     [ebp+var_4], eax
0x413e07  mov     ecx, [ebp+arg_4]
0x413e0a  mov     eax, ecx
0x413e0c  mov     edx, [ebp+arg_8]
0x413e0f  and     ecx, 3Fh
0x413e12  sar     eax, 6
0x413e15  imul    ecx, 38h ; '8'
0x413e18  push    ebx
0x413e19  push    esi
0x413e1a  mov     eax, dword_4181B0[eax*4]
0x413e21  mov     esi, [ebp+arg_0]
0x413e24  push    edi
0x413e25  mov     edi, esi
0x413e27  mov     eax, [eax+ecx+18h]
0x413e2b  mov     ecx, [ebp+arg_C]
0x413e2e  mov     [ebp+hFile], eax
0x413e34  add     ecx, edx
0x413e36  xor     eax, eax
0x413e38  mov     [ebp+var_140C], ecx
0x413e3e  stosd
0x413e3f  stosd
0x413e40  stosd
0x413e41  mov     edi, edx
0x413e43  cmp     edx, ecx
0x413e45  jnb     loc_413F0F
0x413e4b  mov     esi, [ebp+var_140C]
0x413e51  lea     eax, [ebp+WideCharStr]
0x413e57  cmp     edi, esi
0x413e59  jnb     short loc_413E7C
0x413e5b  movzx   ecx, word ptr [edi]
0x413e5e  add     edi, 2
0x413e61  cmp     ecx, 0Ah
0x413e64  jnz     short loc_413E6F
0x413e66  push    0Dh
0x413e68  pop     edx
0x413e69  mov     [eax], dx
0x413e6c  add     eax, 2
0x413e6f  mov     [eax], cx
0x413e72  add     eax, 2
0x413e75  lea     ecx, [ebp+var_8]
0x413e78  cmp     eax, ecx
0x413e7a  jb      short loc_413E57
0x413e7c  push    0; int
0x413e7e  push    0; int
0x413e80  push    0D55h; cbMultiByte
0x413e85  lea     ecx, [ebp+MultiByteStr]
0x413e8b  push    ecx; lpMultiByteStr
0x413e8c  lea     ecx, [ebp+WideCharStr]
0x413e92  sub     eax, ecx
0x413e94  sar     eax, 1
0x413e96  push    eax; cchWideChar
0x413e97  mov     eax, ecx
0x413e99  push    eax; lpWideCharStr
0x413e9a  push    0; int
0x413e9c  push    0FDE9h; CodePage
0x413ea1  call    ___acrt_WideCharToMultiByte
0x413ea6  mov     esi, [ebp+arg_0]
0x413ea9  add     esp, 20h
0x413eac  mov     [ebp+var_1418], eax
0x413eb2  test    eax, eax
0x413eb4  jz      short loc_413F07
0x413eb6  xor     ebx, ebx
0x413eb8  test    eax, eax
0x413eba  jz      short loc_413EF1
0x413ebc  push    0; lpOverlapped
0x413ebe  lea     ecx, [ebp+NumberOfBytesWritten]
0x413ec4  sub     eax, ebx
0x413ec6  push    ecx; lpNumberOfBytesWritten
0x413ec7  push    eax; nNumberOfBytesToWrite
0x413ec8  lea     eax, [ebp+MultiByteStr]
0x413ece  add     eax, ebx
0x413ed0  push    eax; lpBuffer
0x413ed1  push    [ebp+hFile]; hFile
0x413ed7  call    ds:WriteFile
0x413edd  test    eax, eax
0x413edf  jz      short loc_413F07
0x413ee1  add     ebx, [ebp+NumberOfBytesWritten]
0x413ee7  mov     eax, [ebp+var_1418]
0x413eed  cmp     ebx, eax
0x413eef  jb      short loc_413EBC
0x413ef1  mov     eax, edi
0x413ef3  sub     eax, [ebp+arg_8]
0x413ef6  mov     [esi+4], eax
0x413ef9  cmp     edi, [ebp+var_140C]
0x413eff  jb      loc_413E4B
0x413f05  jmp     short loc_413F0F
0x413f07  call    ds:GetLastError
0x413f0d  mov     [esi], eax
0x413f0f  mov     ecx, [ebp+var_4]
0x413f12  mov     eax, esi
0x413f14  pop     edi
0x413f15  pop     esi
0x413f16  xor     ecx, ebp; StackCookie
0x413f18  pop     ebx
0x413f19  call    @__security_check_cookie@4
0x413f1e  leave
0x413f1f  retn
```
