# sub_1000EAFC

- ea: `0x1000eafc`
- end: `0x1000ec26`
- name: `sub_1000EAFC`
- size: `298`
- prototype: `int __stdcall(LPCWSTR szFolder, DWORD pcchPathBuf)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, installer_update`

## callers

- `0x100020f7`
- `0x10003e9c`

## callees

- `0x1000a19e`
- `0x1000a95b`
- `0x1000ad15`
- `0x1000d4f2`
- `0x1000da66`
- `0x1000eafc`
- `0x10020fe6`

## string_xrefs

- `0x1000eb72`: `Failed to allocate string for target path of folder: '%ls'`
- `0x1000ec08`: `Failed to get target path for folder '%ls'`

## pseudocode

```c
int __stdcall sub_1000EAFC(LPCWSTR szFolder, LPCVOID *pcchPathBuf)
{
  const WCHAR *v2; // edi
  LPCVOID *v3; // ebx
  MSIHANDLE v4; // eax
  signed int TargetPathW; // eax
  signed int symbolic_link; // esi
  bool v7; // sf
  int v8; // eax
  MSIHANDLE v9; // eax
  signed int v10; // eax
  MSIHANDLE v11; // eax
  WCHAR *v13; // [esp-Ch] [ebp-14h]
  WCHAR *v14; // [esp-Ch] [ebp-14h]

  v2 = szFolder;
  if ( szFolder )
  {
    if ( *szFolder )
    {
      v3 = pcchPathBuf;
      if ( pcchPathBuf )
      {
        pcchPathBuf = 0;
        if ( *v3 )
        {
          v8 = sub_1000A95B(*v3, (int)&pcchPathBuf);
          symbolic_link = v8;
          if ( v8 < 0 )
          {
            sub_1000DA66(v8, "Failed to get previous size of string");
            return symbolic_link;
          }
          goto LABEL_15;
        }
        LOWORD(szFolder) = 0;
        v4 = sub_1000D4F2();
        TargetPathW = MsiGetTargetPathW(v4, v2, (LPWSTR)&szFolder, (LPDWORD)&pcchPathBuf);
        symbolic_link = TargetPathW;
        if ( TargetPathW == 234 || (v7 = TargetPathW < 0, !TargetPathW) )
        {
          pcchPathBuf = (LPCVOID *)((char *)pcchPathBuf + 1);
          symbolic_link = __std_fs_create_symbolic_link(v3, pcchPathBuf);
        }
        else
        {
          if ( TargetPathW <= 0 )
            goto LABEL_11;
          symbolic_link = (unsigned __int16)TargetPathW | 0x80070000;
        }
        v7 = symbolic_link < 0;
LABEL_11:
        if ( v7 )
        {
LABEL_12:
          sub_1000DA66(symbolic_link, "Failed to allocate string for target path of folder: '%ls'");
          return symbolic_link;
        }
LABEL_15:
        v13 = (WCHAR *)*v3;
        v9 = sub_1000D4F2();
        v10 = MsiGetTargetPathW(v9, v2, v13, (LPDWORD)&pcchPathBuf);
        if ( v10 == 234 )
        {
          pcchPathBuf = (LPCVOID *)((char *)pcchPathBuf + 1);
          symbolic_link = __std_fs_create_symbolic_link(v3, pcchPathBuf);
          if ( symbolic_link < 0 )
            goto LABEL_12;
          v14 = (WCHAR *)*v3;
          v11 = sub_1000D4F2();
          v10 = MsiGetTargetPathW(v11, v2, v14, (LPDWORD)&pcchPathBuf);
        }
        if ( v10 )
        {
          if ( v10 > 0 )
            symbolic_link = (unsigned __int16)v10 | 0x80070000;
          else
            symbolic_link = v10;
          nullsub_1("d:\\a\\_work\\1\\s\\src\\libs\\wcautil\\wcawrap.cpp", 654, symbolic_link);
          sub_1000DA66(symbolic_link, "Failed to get target path for folder '%ls'");
        }
        return symbolic_link;
      }
    }
  }
  return -2147024809;
}

```

## disassembly

```asm
0x1000eafc  push    ebp
0x1000eafd  mov     ebp, esp
0x1000eaff  push    ebx
0x1000eb00  push    edi
0x1000eb01  mov     edi, [ebp+szFolder]
0x1000eb04  test    edi, edi
0x1000eb06  jz      loc_1000EC1B
0x1000eb0c  xor     eax, eax
0x1000eb0e  cmp     [edi], ax
0x1000eb11  jz      loc_1000EC1B
0x1000eb17  mov     ebx, [ebp+pcchPathBuf]
0x1000eb1a  test    ebx, ebx
0x1000eb1c  jz      loc_1000EC1B
0x1000eb22  push    esi
0x1000eb23  mov     [ebp+pcchPathBuf], eax
0x1000eb26  cmp     [ebx], eax
0x1000eb28  jnz     short loc_1000EB7C
0x1000eb2a  mov     word ptr [ebp+szFolder], ax
0x1000eb2e  lea     eax, [ebp+pcchPathBuf]
0x1000eb31  push    eax; pcchPathBuf
0x1000eb32  lea     eax, [ebp+szFolder]
0x1000eb35  push    eax; szPathBuf
0x1000eb36  push    edi; szFolder
0x1000eb37  call    sub_1000D4F2
0x1000eb3c  push    eax; hInstall
0x1000eb3d  call    MsiGetTargetPathW
0x1000eb42  mov     esi, eax
0x1000eb44  cmp     esi, 0EAh
0x1000eb4a  jz      short loc_1000EB5D
0x1000eb4c  test    esi, esi
0x1000eb4e  jz      short loc_1000EB5D
0x1000eb50  jle     short loc_1000EB6F
0x1000eb52  movzx   esi, si
0x1000eb55  or      esi, 80070000h
0x1000eb5b  jmp     short loc_1000EB6D
0x1000eb5d  mov     eax, [ebp+pcchPathBuf]
0x1000eb60  inc     eax
0x1000eb61  push    eax
0x1000eb62  push    ebx
0x1000eb63  mov     [ebp+pcchPathBuf], eax
0x1000eb66  call    ___std_fs_create_symbolic_link@8; __std_fs_create_symbolic_link(x,x)
0x1000eb6b  mov     esi, eax
0x1000eb6d  test    esi, esi
0x1000eb6f  jns     short loc_1000EB9C
0x1000eb71  push    edi
0x1000eb72  push    offset aFailedToAlloca_20; "Failed to allocate string for target pa"...
0x1000eb77  jmp     loc_1000EC0D
0x1000eb7c  lea     eax, [ebp+pcchPathBuf]
0x1000eb7f  push    eax; int
0x1000eb80  push    dword ptr [ebx]; lpMem
0x1000eb82  call    sub_1000A95B
0x1000eb87  mov     esi, eax
0x1000eb89  test    esi, esi
0x1000eb8b  jns     short loc_1000EB9C
0x1000eb8d  push    offset aFailedToGetPre_1; "Failed to get previous size of string"
0x1000eb92  push    esi
0x1000eb93  call    sub_1000DA66
0x1000eb98  pop     ecx
0x1000eb99  pop     ecx
0x1000eb9a  jmp     short loc_1000EC16
0x1000eb9c  lea     eax, [ebp+pcchPathBuf]
0x1000eb9f  push    eax; pcchPathBuf
0x1000eba0  push    dword ptr [ebx]; szPathBuf
0x1000eba2  push    edi; szFolder
0x1000eba3  call    sub_1000D4F2
0x1000eba8  push    eax; hInstall
0x1000eba9  call    MsiGetTargetPathW
0x1000ebae  cmp     eax, 0EAh
0x1000ebb3  jnz     short loc_1000EBDB
0x1000ebb5  mov     eax, [ebp+pcchPathBuf]
0x1000ebb8  inc     eax
0x1000ebb9  push    eax
0x1000ebba  push    ebx
0x1000ebbb  mov     [ebp+pcchPathBuf], eax
0x1000ebbe  call    ___std_fs_create_symbolic_link@8; __std_fs_create_symbolic_link(x,x)
0x1000ebc3  mov     esi, eax
0x1000ebc5  test    esi, esi
0x1000ebc7  js      short loc_1000EB71
0x1000ebc9  lea     eax, [ebp+pcchPathBuf]
0x1000ebcc  push    eax; pcchPathBuf
0x1000ebcd  push    dword ptr [ebx]; szPathBuf
0x1000ebcf  push    edi; szFolder
0x1000ebd0  call    sub_1000D4F2
0x1000ebd5  push    eax; hInstall
0x1000ebd6  call    MsiGetTargetPathW
0x1000ebdb  test    eax, eax
0x1000ebdd  jz      short loc_1000EC16
0x1000ebdf  jg      short loc_1000EBE5
0x1000ebe1  mov     esi, eax
0x1000ebe3  jmp     short loc_1000EBEE
0x1000ebe5  movzx   esi, ax
0x1000ebe8  or      esi, 80070000h
0x1000ebee  test    esi, esi
0x1000ebf0  js      short loc_1000EBF7
0x1000ebf2  mov     esi, 80004005h
0x1000ebf7  push    esi
0x1000ebf8  push    28Eh
0x1000ebfd  push    offset aDAWork1SSrcLib_10; "d:\\a\\_work\\1\\s\\src\\libs\\wcautil"...
0x1000ec02  call    nullsub_1
0x1000ec07  push    edi
0x1000ec08  push    offset aFailedToGetTar_3; "Failed to get target path for folder '%"...
0x1000ec0d  push    esi
0x1000ec0e  call    sub_1000DA66
0x1000ec13  add     esp, 0Ch
0x1000ec16  mov     eax, esi
0x1000ec18  pop     esi
0x1000ec19  jmp     short loc_1000EC20
0x1000ec1b  mov     eax, 80070057h
0x1000ec20  pop     edi
0x1000ec21  pop     ebx
0x1000ec22  pop     ebp
0x1000ec23  retn    8
```
