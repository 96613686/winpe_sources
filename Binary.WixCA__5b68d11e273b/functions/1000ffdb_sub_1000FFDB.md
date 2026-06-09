# sub_1000FFDB

- ea: `0x1000ffdb`
- end: `0x10010343`
- name: `sub_1000FFDB`
- size: `872`
- prototype: `int __stdcall(int, HANDLE hFile)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x10010343`

## callees

- `0x1000a538`
- `0x1000a63e`
- `0x1000a655`
- `0x1000a793`
- `0x1000a952`
- `0x1000aa85`
- `0x1000ad15`
- `0x1000ae3a`
- `0x1000aeff`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000ffdb`
- `0x10011390`
- `0x10012264`
- `0x10015edb`
- `0x10015f0f`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1001006b`
- `KERNEL32!GetLastError` at `0x10010076`
- `KERNEL32!GetLastError` at `0x1001006b`
- `KERNEL32!GetLastError` at `0x10010076`
- `KERNEL32!ReadFile` at `0x10010061`
- `KERNEL32!ReadFile` at `0x10010061`

## string_xrefs

- `0x1001030c`: `Failed to read from handle.`
- `0x1001032e`: `Failed to allocate copy of string`

## pseudocode

```c
int __stdcall sub_1000FFDB(int a1, HANDLE hFile)
{
  int v2; // edi
  signed int v3; // esi
  unsigned __int8 *v4; // ebx
  signed int LastError; // eax
  bool v6; // sf
  int v7; // eax
  wchar_t *v8; // esi
  wchar_t *v9; // edi
  wchar_t *v10; // eax
  const wchar_t *v11; // edi
  int v13; // [esp+Ch] [ebp-1Ch]
  int v14; // [esp+10h] [ebp-18h]
  DWORD NumberOfBytesRead; // [esp+14h] [ebp-14h] BYREF
  LPCWCH lpWideCharStr; // [esp+18h] [ebp-10h] BYREF
  int v17; // [esp+1Ch] [ebp-Ch] BYREF
  LPCWSTR lpString; // [esp+20h] [ebp-8h] BYREF
  wchar_t *Str; // [esp+24h] [ebp-4h] BYREF

  Str = 0;
  lpString = 0;
  v2 = 1;
  lpWideCharStr = 0;
  v17 = 0;
  v3 = 0;
  NumberOfBytesRead = 1024;
  v13 = 1;
  v14 = 1;
  v4 = (unsigned __int8 *)sub_1000AE3A(0x400u, 0);
  if ( v4 )
  {
    do
    {
      memset(v4, 0, 0x400u);
      if ( !ReadFile(hFile, v4, 0x3FFu, &NumberOfBytesRead, 0) && GetLastError() != 109 )
      {
        LastError = GetLastError();
        v3 = LastError;
        v6 = LastError < 0;
        if ( LastError > 0 )
        {
          v3 = (unsigned __int16)LastError | 0x80070000;
          v6 = 1;
        }
        if ( v6 )
        {
          nullsub_1("d:\\a\\_work\\1\\s\\src\\libs\\wcautil\\qtexec.cpp", 126, v3);
          sub_1000DA66(v3, "Failed to read from handle.");
          goto LABEL_46;
        }
      }
      if ( a1 )
      {
        if ( v2 )
        {
          if ( sub_10015EDB(*v4) && sub_10015EDB(v4[1])
            || sub_10015EDB(*v4) && sub_10015F0F(v4[1])
            || sub_10015F0F(*v4) && sub_10015EDB(v4[1])
            || sub_10015F0F(*v4) && sub_10015F0F(v4[1]) )
          {
            v14 = 0;
          }
          v13 = 0;
        }
        if ( v14 )
        {
          v7 = sub_1000A538(&Str, v4, 0);
        }
        else
        {
          v3 = sub_1000A655((int)&lpString, (LPCCH)v4, 0, 1u);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "Failed to allocate output string");
            goto LABEL_46;
          }
          v7 = sub_1000A538(&Str, lpString, 0);
        }
        v3 = v7;
        if ( v7 < 0 )
        {
          sub_1000DA66(v7, "Failed to concatenate output strings");
          goto LABEL_46;
        }
        v8 = Str;
        v9 = wcschr(Str, 0xDu);
        if ( v9 )
          goto LABEL_27;
        v10 = wcschr(Str, 0xAu);
LABEL_36:
        v9 = v10;
        if ( v10 )
        {
LABEL_27:
          while ( *v9 )
          {
            *v9 = 0;
            v11 = v9 + 1;
            if ( *v11 == 13 || *v11 == 10 )
              ++v11;
            v3 = sub_1000A63E((int)&lpWideCharStr, v8, 0);
            if ( v3 < 0 )
            {
              sub_1000DA66(v3, "Failed to allocate copy of string");
              goto LABEL_46;
            }
            v3 = sub_1000AA85((int)&lpWideCharStr, (wchar_t *)L"%", (int)L"%%");
            if ( v3 < 0 )
              goto LABEL_59;
            v3 = sub_1000A793((int)&v17, lpWideCharStr, 0, 1u);
            if ( v3 < 0 )
              goto LABEL_58;
            sub_1000D9AB(2, v17);
            v8 = (wchar_t *)v11;
            v9 = wcschr(v11, 0xDu);
            if ( !v9 )
            {
              v10 = wcschr(v8, 0xAu);
              goto LABEL_36;
            }
          }
        }
        v3 = sub_1000A63E((int)&lpString, v8, 0);
        if ( v3 < 0 || (v3 = sub_1000A63E((int)&Str, lpString, 0), v3 < 0) )
        {
          sub_1000DA66(v3, "Failed to allocate string");
          goto LABEL_46;
        }
        v2 = v13;
      }
    }
    while ( NumberOfBytesRead );
    if ( Str && *Str )
    {
      v3 = sub_1000AA85((int)&Str, (wchar_t *)L"%", (int)L"%%");
      if ( v3 < 0 )
      {
LABEL_59:
        sub_1000DA66(v3, "Failed to escape percent signs in string");
      }
      else
      {
        v3 = sub_1000A793((int)&v17, Str, 0, 1u);
        if ( v3 < 0 )
LABEL_58:
          sub_1000DA66(v3, "Failed to convert output to ANSI");
        else
          sub_1000D9AB(1, v17);
      }
    }
LABEL_46:
    sub_1000AEFF(v4);
  }
  else
  {
    v3 = -2147024882;
    nullsub_1("d:\\a\\_work\\1\\s\\src\\libs\\wcautil\\qtexec.cpp", 119, -2147024882);
    sub_1000DA66(-2147024882, "Failed to allocate buffer for output.");
  }
  if ( Str )
    sub_1000A952(Str);
  if ( lpString )
    sub_1000A952(lpString);
  if ( v17 )
    sub_1000A952(v17);
  if ( lpWideCharStr )
    sub_1000A952(lpWideCharStr);
  return v3;
}

```

## disassembly

```asm
0x1000ffdb  push    ebp
0x1000ffdc  mov     ebp, esp
0x1000ffde  sub     esp, 1Ch
0x1000ffe1  push    ebx
0x1000ffe2  push    esi
0x1000ffe3  xor     eax, eax
0x1000ffe5  xor     ecx, ecx
0x1000ffe7  push    edi
0x1000ffe8  inc     ecx
0x1000ffe9  mov     [ebp+Str], eax
0x1000ffec  mov     edx, 400h
0x1000fff1  mov     [ebp+lpString], eax
0x1000fff4  push    eax; int
0x1000fff5  mov     edi, ecx
0x1000fff7  mov     [ebp+lpWideCharStr], eax
0x1000fffa  push    edx; dwBytes
0x1000fffb  mov     [ebp+var_C], eax
0x1000fffe  mov     esi, eax
0x10010000  mov     [ebp+NumberOfBytesRead], edx
0x10010003  mov     [ebp+var_1C], edi
0x10010006  mov     [ebp+var_18], ecx
0x10010009  call    sub_1000AE3A
0x1001000e  mov     ebx, eax
0x10010010  test    ebx, ebx
0x10010012  jnz     short loc_10010038
0x10010014  mov     esi, 8007000Eh
0x10010019  push    esi
0x1001001a  push    77h ; 'w'
0x1001001c  push    offset aDAWork1SSrcLib_12; "d:\\a\\_work\\1\\s\\src\\libs\\wcautil"...
0x10010021  call    nullsub_1
0x10010026  push    offset aFailedToAlloca_28; "Failed to allocate buffer for output."
0x1001002b  push    esi
0x1001002c  call    sub_1000DA66
0x10010031  pop     ecx
0x10010032  pop     ecx
0x10010033  jmp     loc_100102BE
0x10010038  cmp     [ebp+NumberOfBytesRead], esi
0x1001003b  jz      loc_1001026C
0x10010041  push    400h; Size
0x10010046  push    0; Val
0x10010048  push    ebx; void *
0x10010049  call    _memset
0x1001004e  add     esp, 0Ch
0x10010051  xor     eax, eax
0x10010053  push    eax; lpOverlapped
0x10010054  lea     eax, [ebp+NumberOfBytesRead]
0x10010057  push    eax; lpNumberOfBytesRead
0x10010058  push    3FFh; nNumberOfBytesToRead
0x1001005d  push    ebx; lpBuffer
0x1001005e  push    [ebp+hFile]; hFile
0x10010061  call    ds:ReadFile
0x10010067  test    eax, eax
0x10010069  jnz     short loc_10010093
0x1001006b  call    ds:GetLastError
0x10010071  cmp     eax, 6Dh ; 'm'
0x10010074  jz      short loc_10010093
0x10010076  call    ds:GetLastError
0x1001007c  mov     esi, eax
0x1001007e  test    esi, esi
0x10010080  jle     short loc_1001008D
0x10010082  movzx   esi, si
0x10010085  or      esi, 80070000h
0x1001008b  test    esi, esi
0x1001008d  js      loc_100102FF
0x10010093  cmp     [ebp+arg_0], 0
0x10010097  jz      loc_10010262
0x1001009d  test    edi, edi
0x1001009f  jz      loc_10010127
0x100100a5  movzx   eax, byte ptr [ebx]
0x100100a8  push    eax; Char_value
0x100100a9  call    sub_10015EDB
0x100100ae  pop     ecx
0x100100af  test    eax, eax
0x100100b1  jz      short loc_100100C2
0x100100b3  movzx   eax, byte ptr [ebx+1]
0x100100b7  push    eax; Char_value
0x100100b8  call    sub_10015EDB
0x100100bd  pop     ecx
0x100100be  test    eax, eax
0x100100c0  jnz     short loc_10010119
0x100100c2  movzx   eax, byte ptr [ebx]
0x100100c5  push    eax; Char_value
0x100100c6  call    sub_10015EDB
0x100100cb  pop     ecx
0x100100cc  test    eax, eax
0x100100ce  jz      short loc_100100DF
0x100100d0  movzx   eax, byte ptr [ebx+1]
0x100100d4  push    eax; Char_value
0x100100d5  call    sub_10015F0F
0x100100da  pop     ecx
0x100100db  test    eax, eax
0x100100dd  jnz     short loc_10010119
0x100100df  movzx   eax, byte ptr [ebx]
0x100100e2  push    eax; Char_value
0x100100e3  call    sub_10015F0F
0x100100e8  pop     ecx
0x100100e9  test    eax, eax
0x100100eb  jz      short loc_100100FC
0x100100ed  movzx   eax, byte ptr [ebx+1]
0x100100f1  push    eax; Char_value
0x100100f2  call    sub_10015EDB
0x100100f7  pop     ecx
0x100100f8  test    eax, eax
0x100100fa  jnz     short loc_10010119
0x100100fc  movzx   eax, byte ptr [ebx]
0x100100ff  push    eax; Char_value
0x10010100  call    sub_10015F0F
0x10010105  pop     ecx
0x10010106  test    eax, eax
0x10010108  jz      short loc_10010120
0x1001010a  movzx   eax, byte ptr [ebx+1]
0x1001010e  push    eax; Char_value
0x1001010f  call    sub_10015F0F
0x10010114  pop     ecx
0x10010115  test    eax, eax
0x10010117  jz      short loc_10010120
0x10010119  xor     edi, edi
0x1001011b  mov     [ebp+var_18], edi
0x1001011e  jmp     short loc_10010122
0x10010120  xor     edi, edi
0x10010122  mov     [ebp+var_1C], edi
0x10010125  jmp     short loc_10010129
0x10010127  xor     edi, edi
0x10010129  cmp     [ebp+var_18], 0
0x1001012d  jz      short loc_10010133
0x1001012f  push    edi
0x10010130  push    ebx
0x10010131  jmp     short loc_1001014E
0x10010133  push    1; CodePage
0x10010135  push    edi; cbMultiByte
0x10010136  push    ebx; lpMultiByteStr
0x10010137  lea     eax, [ebp+lpString]
0x1001013a  push    eax; int
0x1001013b  call    sub_1000A655
0x10010140  mov     esi, eax
0x10010142  test    esi, esi
0x10010144  js      loc_1001033C
0x1001014a  push    edi
0x1001014b  push    [ebp+lpString]
0x1001014e  lea     eax, [ebp+Str]
0x10010151  push    eax
0x10010152  call    sub_1000A538
0x10010157  mov     esi, eax
0x10010159  test    esi, esi
0x1001015b  js      loc_10010319
0x10010161  mov     esi, [ebp+Str]
0x10010164  push    0Dh
0x10010166  pop     eax
0x10010167  push    eax; Ch
0x10010168  push    esi; Str
0x10010169  call    _wcschr
0x1001016e  mov     edi, eax
0x10010170  pop     ecx
0x10010171  pop     ecx
0x10010172  test    edi, edi
0x10010174  jnz     short loc_10010182
0x10010176  push    0Ah
0x10010178  pop     eax
0x10010179  push    eax
0x1001017a  push    [ebp+Str]
0x1001017d  jmp     loc_10010220
0x10010182  xor     ecx, ecx
0x10010184  cmp     [edi], cx
0x10010187  jz      loc_10010231
0x1001018d  xor     eax, eax
0x1001018f  mov     [edi], ax
0x10010192  add     edi, 2
0x10010195  push    0Dh
0x10010197  pop     edx
0x10010198  movzx   eax, word ptr [edi]
0x1001019b  cmp     ax, dx
0x1001019e  jz      short loc_100101A8
0x100101a0  push    0Ah
0x100101a2  pop     edx
0x100101a3  cmp     ax, dx
0x100101a6  jnz     short loc_100101AB
0x100101a8  add     edi, 2
0x100101ab  push    ecx; int
0x100101ac  push    esi; lpString
0x100101ad  lea     eax, [ebp+lpWideCharStr]
0x100101b0  push    eax; int
0x100101b1  call    sub_1000A63E
0x100101b6  mov     esi, eax
0x100101b8  test    esi, esi
0x100101ba  js      loc_1001032E
0x100101c0  push    offset asc_1002B35C; "%%"
0x100101c5  push    offset asc_1002B364; "%"
0x100101ca  lea     eax, [ebp+lpWideCharStr]
0x100101cd  push    eax; int
0x100101ce  call    sub_1000AA85
0x100101d3  mov     esi, eax
0x100101d5  test    esi, esi
0x100101d7  js      loc_10010327
0x100101dd  push    1; CodePage
0x100101df  xor     eax, eax
0x100101e1  push    eax; cchWideChar
0x100101e2  push    [ebp+lpWideCharStr]; lpWideCharStr
0x100101e5  lea     eax, [ebp+var_C]
0x100101e8  push    eax; int
0x100101e9  call    sub_1000A793
0x100101ee  mov     esi, eax
0x100101f0  test    esi, esi
0x100101f2  js      loc_10010320
0x100101f8  push    [ebp+var_C]
0x100101fb  push    2
0x100101fd  call    sub_1000D9AB
0x10010202  push    0Dh
0x10010204  pop     eax
0x10010205  push    eax; Ch
0x10010206  push    edi; Str
0x10010207  mov     esi, edi
0x10010209  call    _wcschr
0x1001020e  mov     edi, eax
0x10010210  add     esp, 10h
0x10010213  test    edi, edi
0x10010215  jnz     loc_10010182
0x1001021b  push    0Ah
0x1001021d  pop     eax
0x1001021e  push    eax; Ch
0x1001021f  push    esi; Str
0x10010220  call    _wcschr
0x10010225  mov     edi, eax
0x10010227  pop     ecx
0x10010228  pop     ecx
0x10010229  test    edi, edi
0x1001022b  jnz     loc_10010182
0x10010231  xor     edi, edi
0x10010233  lea     eax, [ebp+lpString]
0x10010236  push    edi; int
0x10010237  push    esi; lpString
0x10010238  push    eax; int
0x10010239  call    sub_1000A63E
0x1001023e  mov     esi, eax
0x10010240  test    esi, esi
0x10010242  js      loc_10010335
0x10010248  push    edi; int
0x10010249  push    [ebp+lpString]; lpString
0x1001024c  lea     eax, [ebp+Str]
0x1001024f  push    eax; int
0x10010250  call    sub_1000A63E
0x10010255  mov     esi, eax
0x10010257  test    esi, esi
0x10010259  js      loc_10010335
0x1001025f  mov     edi, [ebp+var_1C]
0x10010262  cmp     [ebp+NumberOfBytesRead], 0
0x10010266  jnz     loc_10010041
0x1001026c  mov     eax, [ebp+Str]
0x1001026f  test    eax, eax
0x10010271  jz      short loc_100102B8
0x10010273  xor     edi, edi
0x10010275  cmp     [eax], di
0x10010278  jz      short loc_100102B8
0x1001027a  push    offset asc_1002B35C; "%%"
0x1001027f  push    offset asc_1002B364; "%"
0x10010284  lea     eax, [ebp+Str]
0x10010287  push    eax; int
0x10010288  call    sub_1000AA85
0x1001028d  mov     esi, eax
0x1001028f  test    esi, esi
0x10010291  js      loc_10010327
0x10010297  push    1; CodePage
0x10010299  push    edi; cchWideChar
0x1001029a  push    [ebp+Str]; lpWideCharStr
0x1001029d  lea     eax, [ebp+var_C]
0x100102a0  push    eax; int
0x100102a1  call    sub_1000A793
0x100102a6  mov     esi, eax
0x100102a8  test    esi, esi
0x100102aa  js      short loc_10010320
0x100102ac  push    [ebp+var_C]
0x100102af  push    1
0x100102b1  call    sub_1000D9AB
0x100102b6  pop     ecx
0x100102b7  pop     ecx
0x100102b8  push    ebx; lpMem
0x100102b9  call    sub_1000AEFF
0x100102be  cmp     [ebp+Str], 0
0x100102c2  jz      short loc_100102CC
0x100102c4  push    [ebp+Str]
0x100102c7  call    sub_1000A952
0x100102cc  cmp     [ebp+lpString], 0
0x100102d0  jz      short loc_100102DA
0x100102d2  push    [ebp+lpString]
0x100102d5  call    sub_1000A952
0x100102da  cmp     [ebp+var_C], 0
0x100102de  jz      short loc_100102E8
0x100102e0  push    [ebp+var_C]
0x100102e3  call    sub_1000A952
0x100102e8  cmp     [ebp+lpWideCharStr], 0
0x100102ec  jz      short loc_100102F6
0x100102ee  push    [ebp+lpWideCharStr]
0x100102f1  call    sub_1000A952
0x100102f6  pop     edi
0x100102f7  mov     eax, esi
0x100102f9  pop     esi
0x100102fa  pop     ebx
0x100102fb  leave
0x100102fc  retn    8
0x100102ff  push    esi
0x10010300  push    7Eh ; '~'
  ... truncated ...
```
