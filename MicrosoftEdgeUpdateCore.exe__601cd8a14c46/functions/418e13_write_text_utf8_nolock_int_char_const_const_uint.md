# write_text_utf8_nolock(int,char const * const,uint)

- ea: `0x418e13`
- end: `0x418f45`
- name: `?write_text_utf8_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z`
- size: `306`
- prototype: `DWORD *__cdecl(DWORD *, int, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x419037`

## callees

- `0x40d08d`
- `0x414c89`
- `0x418e13`
- `0x41dcf0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x418efc`
- `KERNEL32!WriteFile` at `0x418efc`
- `KERNEL32!GetLastError` at `0x418f2c`
- `KERNEL32!GetLastError` at `0x418f2c`

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
  hFile = *(HANDLE *)(dword_43E588[a2 >> 6] + 56 * (a2 & 0x3F) + 24);
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
0x418e13  mov     edi, edi
0x418e15  push    ebp
0x418e16  mov     ebp, esp
0x418e18  mov     eax, 1418h
0x418e1d  call    __alloca_probe
0x418e22  mov     eax, ___security_cookie
0x418e27  xor     eax, ebp
0x418e29  mov     [ebp+var_4], eax
0x418e2c  mov     ecx, [ebp+arg_4]
0x418e2f  mov     eax, ecx
0x418e31  mov     edx, [ebp+arg_8]
0x418e34  and     ecx, 3Fh
0x418e37  sar     eax, 6
0x418e3a  imul    ecx, 38h ; '8'
0x418e3d  push    ebx
0x418e3e  push    esi
0x418e3f  mov     eax, dword_43E588[eax*4]
0x418e46  mov     esi, [ebp+arg_0]
0x418e49  push    edi
0x418e4a  mov     edi, esi
0x418e4c  mov     eax, [eax+ecx+18h]
0x418e50  mov     ecx, [ebp+arg_C]
0x418e53  mov     [ebp+hFile], eax
0x418e59  add     ecx, edx
0x418e5b  xor     eax, eax
0x418e5d  mov     [ebp+var_140C], ecx
0x418e63  stosd
0x418e64  stosd
0x418e65  stosd
0x418e66  mov     edi, edx
0x418e68  cmp     edx, ecx
0x418e6a  jnb     loc_418F34
0x418e70  mov     esi, [ebp+var_140C]
0x418e76  lea     eax, [ebp+WideCharStr]
0x418e7c  cmp     edi, esi
0x418e7e  jnb     short loc_418EA1
0x418e80  movzx   ecx, word ptr [edi]
0x418e83  add     edi, 2
0x418e86  cmp     ecx, 0Ah
0x418e89  jnz     short loc_418E94
0x418e8b  push    0Dh
0x418e8d  pop     edx
0x418e8e  mov     [eax], dx
0x418e91  add     eax, 2
0x418e94  mov     [eax], cx
0x418e97  add     eax, 2
0x418e9a  lea     ecx, [ebp+var_8]
0x418e9d  cmp     eax, ecx
0x418e9f  jb      short loc_418E7C
0x418ea1  push    0; int
0x418ea3  push    0; int
0x418ea5  push    0D55h; cbMultiByte
0x418eaa  lea     ecx, [ebp+MultiByteStr]
0x418eb0  push    ecx; lpMultiByteStr
0x418eb1  lea     ecx, [ebp+WideCharStr]
0x418eb7  sub     eax, ecx
0x418eb9  sar     eax, 1
0x418ebb  push    eax; cchWideChar
0x418ebc  mov     eax, ecx
0x418ebe  push    eax; lpWideCharStr
0x418ebf  push    0; int
0x418ec1  push    0FDE9h; CodePage
0x418ec6  call    ___acrt_WideCharToMultiByte
0x418ecb  mov     esi, [ebp+arg_0]
0x418ece  add     esp, 20h
0x418ed1  mov     [ebp+var_1418], eax
0x418ed7  test    eax, eax
0x418ed9  jz      short loc_418F2C
0x418edb  xor     ebx, ebx
0x418edd  test    eax, eax
0x418edf  jz      short loc_418F16
0x418ee1  push    0; lpOverlapped
0x418ee3  lea     ecx, [ebp+NumberOfBytesWritten]
0x418ee9  sub     eax, ebx
0x418eeb  push    ecx; lpNumberOfBytesWritten
0x418eec  push    eax; nNumberOfBytesToWrite
0x418eed  lea     eax, [ebp+MultiByteStr]
0x418ef3  add     eax, ebx
0x418ef5  push    eax; lpBuffer
0x418ef6  push    [ebp+hFile]; hFile
0x418efc  call    ds:WriteFile
0x418f02  test    eax, eax
0x418f04  jz      short loc_418F2C
0x418f06  add     ebx, [ebp+NumberOfBytesWritten]
0x418f0c  mov     eax, [ebp+var_1418]
0x418f12  cmp     ebx, eax
0x418f14  jb      short loc_418EE1
0x418f16  mov     eax, edi
0x418f18  sub     eax, [ebp+arg_8]
0x418f1b  mov     [esi+4], eax
0x418f1e  cmp     edi, [ebp+var_140C]
0x418f24  jb      loc_418E70
0x418f2a  jmp     short loc_418F34
0x418f2c  call    ds:GetLastError
0x418f32  mov     [esi], eax
0x418f34  mov     ecx, [ebp+var_4]
0x418f37  mov     eax, esi
0x418f39  pop     edi
0x418f3a  pop     esi
0x418f3b  xor     ecx, ebp; StackCookie
0x418f3d  pop     ebx
0x418f3e  call    @__security_check_cookie@4
0x418f43  leave
0x418f44  retn
```
