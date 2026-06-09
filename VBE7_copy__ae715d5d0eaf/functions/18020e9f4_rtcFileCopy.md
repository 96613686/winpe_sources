# rtcFileCopy

- ea: `0x18020e9f4`
- end: `0x18020ebd7`
- name: `rtcFileCopy`
- size: `483`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x180102a4c`
- `0x1801426d8`
- `0x18014275c`
- `0x18020cfb4`
- `0x18020e9f4`
- `0x18020f03c`
- `0x18020f12c`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!_sopen_s` at `0x18020eaa2`
- `MSVCR100!_sopen_s` at `0x18020eaf6`
- `MSVCR100!_sopen_s` at `0x18020eaa2`
- `MSVCR100!_sopen_s` at `0x18020eaf6`
- `MSVCR100!_write` at `0x18020eb40`
- `MSVCR100!_write` at `0x18020eb40`
- `MSVCR100!_read` at `0x18020eb28`
- `MSVCR100!_read` at `0x18020eb28`
- `MSVCR100!_isatty` at `0x18020eabc`
- `MSVCR100!_isatty` at `0x18020eb07`
- `MSVCR100!_isatty` at `0x18020eabc`
- `MSVCR100!_isatty` at `0x18020eb07`
- `MSVCR100!_close` at `0x18020eb6e`
- `MSVCR100!_close` at `0x18020eb7f`
- `MSVCR100!_close` at `0x18020eb6e`
- `MSVCR100!_close` at `0x18020eb7f`

## pseudocode

```c
unsigned int __fastcall rtcFileCopy(wchar_t *a1, wchar_t *a2)
{
  unsigned int v2; // edi
  int v4; // r12d
  unsigned __int16 v5; // bx
  void *v6; // r15
  unsigned int v7; // eax
  int v8; // eax
  unsigned int result; // eax
  int FileHandle; // [rsp+30h] [rbp-D0h] BYREF
  int v11[3]; // [rsp+34h] [rbp-CCh] BYREF
  CHAR String1[2064]; // [rsp+40h] [rbp-C0h] BYREF
  char FileName[2064]; // [rsp+850h] [rbp+750h] BYREF

  v2 = 0;
  v4 = 1;
  CheckPathname(String1, a2, 2u);
  CheckPathname(FileName, a1, 1u);
  v5 = -512;
  while ( 1 )
  {
    v6 = (void *)ProfMemAlloc(v5);
    if ( v6 )
      break;
    v5 = (v5 >> 3) & 0x1F00;
    if ( !v5 )
    {
      v2 = 7;
      goto LABEL_24;
    }
  }
  FileHandle = 0;
  _sopen_s(&FileHandle, FileName, 0x8000, 32, 384);
  if ( FileHandle == -1 )
  {
    v2 = MapFileError();
  }
  else
  {
    if ( !_isatty(FileHandle) )
      goto LABEL_10;
    v2 = 5;
  }
  if ( !v2 )
  {
LABEL_10:
    v11[0] = 0;
    _sopen_s(v11, String1, 33537, 16, 128);
    if ( v11[0] == -1 )
      goto LABEL_16;
    if ( !_isatty(v11[0]) )
      goto LABEL_13;
    v2 = 5;
    while ( !v2 )
    {
LABEL_13:
      if ( !v4 )
        break;
      v7 = _read(FileHandle, v6, v5);
      v4 = v7;
      if ( v7 == -1 || (v8 = _write(v11[0], v6, v7), v8 == -1) )
      {
LABEL_16:
        v2 = MapFileError();
      }
      else if ( v8 != v4 )
      {
        v2 = 61;
      }
    }
    if ( v11[0] != -1 )
      _close(v11[0]);
  }
  if ( FileHandle != -1 )
    _close(FileHandle);
LABEL_24:
  ProfMemFree(v6);
  if ( v2 || (result = CopyFileInfo(FileName, String1), (v2 = result) != 0) )
    EbRaiseExceptionCode(v2);
  return result;
}

```

## disassembly

```asm
0x18020e9f4  mov     [rsp-8+arg_10], rbx
0x18020e9f9  mov     [rsp-8+arg_18], rdi
0x18020e9fe  push    rbp
0x18020e9ff  push    r12
0x18020ea01  push    r15
0x18020ea03  lea     rbp, [rsp-0F70h]
0x18020ea0b  mov     eax, 1070h
0x18020ea10  call    _alloca_probe
0x18020ea15  sub     rsp, rax
0x18020ea18  mov     rax, cs:__security_cookie
0x18020ea1f  xor     rax, rsp
0x18020ea22  mov     [rbp+0F80h+var_20], rax
0x18020ea29  xor     edi, edi
0x18020ea2b  mov     rbx, rcx
0x18020ea2e  lea     rcx, [rsp+1080h+String1]; lpString1
0x18020ea33  lea     r8d, [rdi+2]; unsigned __int16
0x18020ea37  lea     r12d, [rdi+1]
0x18020ea3b  call    ?CheckPathname@@YAXPEADPEA_WG@Z; CheckPathname(char *,wchar_t *,ushort)
0x18020ea40  lea     rcx, [rbp+0F80h+FileName]; lpString1
0x18020ea47  mov     r8d, r12d; unsigned __int16
0x18020ea4a  mov     rdx, rbx; wchar_t *
0x18020ea4d  call    ?CheckPathname@@YAXPEADPEA_WG@Z; CheckPathname(char *,wchar_t *,ushort)
0x18020ea52  mov     ebx, 0FE00h
0x18020ea57  movzx   ecx, bx
0x18020ea5a  call    ProfMemAlloc
0x18020ea5f  mov     r15, rax
0x18020ea62  test    rax, rax
0x18020ea65  jnz     short loc_18020EA7E
0x18020ea67  shr     bx, 3
0x18020ea6b  mov     eax, 1F00h
0x18020ea70  and     bx, ax
0x18020ea73  jnz     short loc_18020EA57
0x18020ea75  lea     edi, [r15+7]
0x18020ea79  jmp     loc_18020EB85
0x18020ea7e  and     [rsp+1080h+FileHandle], edi
0x18020ea82  lea     rdx, [rbp+0F80h+FileName]; FileName
0x18020ea89  lea     rcx, [rsp+1080h+FileHandle]; FileHandle
0x18020ea8e  mov     r9d, 20h ; ' '; ShareFlag
0x18020ea94  mov     r8d, 8000h; OpenFlag
0x18020ea9a  mov     [rsp+1080h+PermissionMode], 180h; PermissionMode
0x18020eaa2  call    cs:__imp__sopen_s
0x18020eaa8  cmp     [rsp+1080h+FileHandle], 0FFFFFFFFh
0x18020eaad  jnz     short loc_18020EAB8
0x18020eaaf  call    ?MapFileError@@YAIXZ; MapFileError(void)
0x18020eab4  mov     edi, eax
0x18020eab6  jmp     short loc_18020EACB
0x18020eab8  mov     ecx, [rsp+1080h+FileHandle]; FileHandle
0x18020eabc  call    cs:__imp__isatty
0x18020eac2  test    eax, eax
0x18020eac4  jz      short loc_18020EAD3
0x18020eac6  mov     edi, 5
0x18020eacb  test    edi, edi
0x18020eacd  jnz     loc_18020EB74
0x18020ead3  and     [rsp+1080h+var_104C], 0
0x18020ead8  lea     rdx, [rsp+1080h+String1]; FileName
0x18020eadd  lea     rcx, [rsp+1080h+var_104C]; FileHandle
0x18020eae2  mov     r9d, 10h; ShareFlag
0x18020eae8  mov     r8d, 8301h; OpenFlag
0x18020eaee  mov     [rsp+1080h+PermissionMode], 80h; PermissionMode
0x18020eaf6  call    cs:__imp__sopen_s
0x18020eafc  cmp     [rsp+1080h+var_104C], 0FFFFFFFFh
0x18020eb01  jz      short loc_18020EB4B
0x18020eb03  mov     ecx, [rsp+1080h+var_104C]; FileHandle
0x18020eb07  call    cs:__imp__isatty
0x18020eb0d  test    eax, eax
0x18020eb0f  jz      short loc_18020EB18
0x18020eb11  mov     edi, 5
0x18020eb16  jmp     short loc_18020EB5F
0x18020eb18  test    r12d, r12d
0x18020eb1b  jz      short loc_18020EB63
0x18020eb1d  mov     ecx, [rsp+1080h+FileHandle]; FileHandle
0x18020eb21  movzx   r8d, bx; MaxCharCount
0x18020eb25  mov     rdx, r15; DstBuf
0x18020eb28  call    cs:__imp__read
0x18020eb2e  mov     r12d, eax
0x18020eb31  cmp     eax, 0FFFFFFFFh
0x18020eb34  jz      short loc_18020EB4B
0x18020eb36  mov     ecx, [rsp+1080h+var_104C]; FileHandle
0x18020eb3a  mov     r8d, eax; MaxCharCount
0x18020eb3d  mov     rdx, r15; Buf
0x18020eb40  call    cs:__imp__write
0x18020eb46  cmp     eax, 0FFFFFFFFh
0x18020eb49  jnz     short loc_18020EB54
0x18020eb4b  call    ?MapFileError@@YAIXZ; MapFileError(void)
0x18020eb50  mov     edi, eax
0x18020eb52  jmp     short loc_18020EB5F
0x18020eb54  mov     ecx, 3Dh ; '='
0x18020eb59  cmp     eax, r12d
0x18020eb5c  cmovnz  edi, ecx
0x18020eb5f  test    edi, edi
0x18020eb61  jz      short loc_18020EB18
0x18020eb63  cmp     [rsp+1080h+var_104C], 0FFFFFFFFh
0x18020eb68  jz      short loc_18020EB74
0x18020eb6a  mov     ecx, [rsp+1080h+var_104C]; FileHandle
0x18020eb6e  call    cs:__imp__close
0x18020eb74  cmp     [rsp+1080h+FileHandle], 0FFFFFFFFh
0x18020eb79  jz      short loc_18020EB85
0x18020eb7b  mov     ecx, [rsp+1080h+FileHandle]; FileHandle
0x18020eb7f  call    cs:__imp__close
0x18020eb85  mov     rcx, r15
0x18020eb88  call    ProfMemFree
0x18020eb8d  test    edi, edi
0x18020eb8f  jnz     short loc_18020EBA8
0x18020eb91  lea     rdx, [rsp+1080h+String1]; char *
0x18020eb96  lea     rcx, [rbp+0F80h+FileName]; char *
0x18020eb9d  call    ?CopyFileInfo@@YAIPEAD0@Z; CopyFileInfo(char *,char *)
0x18020eba2  mov     edi, eax
0x18020eba4  test    eax, eax
0x18020eba6  jz      short loc_18020EBAF
0x18020eba8  mov     ecx, edi
0x18020ebaa  call    EbRaiseExceptionCode
0x18020ebaf  mov     rcx, [rbp+0F80h+var_20]
0x18020ebb6  xor     rcx, rsp; StackCookie
0x18020ebb9  call    __security_check_cookie
0x18020ebbe  lea     r11, [rsp+1080h+var_10]
0x18020ebc6  mov     rbx, [r11+30h]
0x18020ebca  mov     rdi, [r11+38h]
0x18020ebce  mov     rsp, r11
0x18020ebd1  pop     r15
0x18020ebd3  pop     r12
0x18020ebd5  pop     rbp
0x18020ebd6  retn
```
