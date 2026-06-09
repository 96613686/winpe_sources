# ___acrt_WideCharToMultiByte

- ea: `0x410055`
- end: `0x41010c`
- name: `___acrt_WideCharToMultiByte`
- size: `183`
- prototype: `int __cdecl(UINT CodePage, int, LPCWCH lpWideCharStr, int cchWideChar, LPSTR lpMultiByteStr, int cbMultiByte, const CHAR *, BOOL *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x40ee5a`
- `0x40f5c2`
- `0x410143`
- `0x413934`
- `0x413e05`
- `0x41444e`
- `0x41b29e`

## callees

- `0x410055`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x410101`
- `KERNEL32!WideCharToMultiByte` at `0x410101`

## pseudocode

```c
int __cdecl __acrt_WideCharToMultiByte(
        UINT CodePage,
        int a2,
        LPCWCH lpWideCharStr,
        int cchWideChar,
        LPSTR lpMultiByteStr,
        int cbMultiByte,
        const CHAR *a7,
        BOOL *a8)
{
  bool v8; // bl
  bool v9; // zf
  DWORD v10; // ecx

  v8 = CodePage == 65000 || CodePage == 65001;
  if ( CodePage > 0xC435 )
  {
    if ( CodePage == 54936 )
      goto LABEL_19;
    if ( CodePage > 0xDEA9 )
    {
      if ( CodePage <= 0xDEB3 || CodePage == 65000 )
        goto LABEL_19;
      v9 = CodePage == 65001;
LABEL_17:
      if ( !v9 )
        goto LABEL_18;
LABEL_19:
      v10 = 0;
      goto LABEL_20;
    }
  }
  else
  {
    if ( CodePage == 50229 || CodePage == 42 )
      goto LABEL_19;
    if ( CodePage > 0xC42B )
    {
      if ( CodePage <= 0xC42E || CodePage == 50225 )
        goto LABEL_19;
      v9 = CodePage == 50227;
      goto LABEL_17;
    }
  }
LABEL_18:
  v10 = a2 & 0xFFFFFF7F;
LABEL_20:
  if ( v8 && a8 )
    *a8 = 0;
  return WideCharToMultiByte(
           CodePage,
           v10,
           lpWideCharStr,
           cchWideChar,
           lpMultiByteStr,
           cbMultiByte,
           !v8 ? a7 : 0,
           !v8 ? a8 : 0);
}

```

## disassembly

```asm
0x410055  mov     edi, edi
0x410057  push    ebp
0x410058  mov     ebp, esp
0x41005a  mov     eax, [ebp+CodePage]
0x41005d  mov     edx, 0FDE9h
0x410062  push    ebx
0x410063  push    esi
0x410064  push    edi
0x410065  lea     esi, [edx-1]
0x410068  cmp     eax, esi
0x41006a  jz      short loc_410074
0x41006c  cmp     eax, edx
0x41006e  jz      short loc_410074
0x410070  xor     bl, bl
0x410072  jmp     short loc_410076
0x410074  mov     bl, 1
0x410076  mov     ecx, 0C435h
0x41007b  cmp     eax, ecx
0x41007d  ja      short loc_4100A2
0x41007f  jz      short loc_4100CA
0x410081  cmp     eax, 2Ah ; '*'
0x410084  jz      short loc_4100CA
0x410086  cmp     eax, 0C42Bh
0x41008b  jbe     short loc_4100BF
0x41008d  cmp     eax, 0C42Eh
0x410092  jbe     short loc_4100CA
0x410094  cmp     eax, 0C431h
0x410099  jz      short loc_4100CA
0x41009b  cmp     eax, 0C433h
0x4100a0  jmp     short loc_4100BD
0x4100a2  cmp     eax, 0D698h
0x4100a7  jz      short loc_4100CA
0x4100a9  cmp     eax, 0DEA9h
0x4100ae  jbe     short loc_4100BF
0x4100b0  cmp     eax, 0DEB3h
0x4100b5  jbe     short loc_4100CA
0x4100b7  cmp     eax, esi
0x4100b9  jz      short loc_4100CA
0x4100bb  cmp     eax, edx
0x4100bd  jz      short loc_4100CA
0x4100bf  mov     ecx, [ebp+arg_4]
0x4100c2  and     ecx, 0FFFFFF7Fh
0x4100c8  jmp     short loc_4100CC
0x4100ca  xor     ecx, ecx
0x4100cc  mov     edi, [ebp+arg_1C]
0x4100cf  movzx   edx, bl
0x4100d2  neg     edx
0x4100d4  movzx   esi, bl
0x4100d7  sbb     edx, edx
0x4100d9  not     edx
0x4100db  and     edx, edi
0x4100dd  neg     esi
0x4100df  sbb     esi, esi
0x4100e1  not     esi
0x4100e3  and     esi, [ebp+arg_18]
0x4100e6  test    bl, bl
0x4100e8  jz      short loc_4100F1
0x4100ea  test    edi, edi
0x4100ec  jz      short loc_4100F1
0x4100ee  and     dword ptr [edi], 0
0x4100f1  push    edx; lpUsedDefaultChar
0x4100f2  push    esi; lpDefaultChar
0x4100f3  push    [ebp+cbMultiByte]; cbMultiByte
0x4100f6  push    [ebp+lpMultiByteStr]; lpMultiByteStr
0x4100f9  push    [ebp+cchWideChar]; cchWideChar
0x4100fc  push    [ebp+lpWideCharStr]; lpWideCharStr
0x4100ff  push    ecx; dwFlags
0x410100  push    eax; CodePage
0x410101  call    ds:WideCharToMultiByte
0x410107  pop     edi
0x410108  pop     esi
0x410109  pop     ebx
0x41010a  pop     ebp
0x41010b  retn
```
