# GetUserStorageArea

- ea: `0x18000be6c`
- end: `0x18000bfd2`
- name: `GetUserStorageArea`
- size: `358`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a9f0`
- `0x18000b960`

## callees

- `0x180001630`
- `0x180001f58`
- `0x18000be6c`
- `0x180010920`
- `0x180010950`
- `0x18001a450`
- `0x18001a6ac`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000bead`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000bee4`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000bead`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000bee4`

## string_xrefs

- `0x18000bebf`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`
- `0x18000bf6e`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`

## pseudocode

```c
__int64 __fastcall GetUserStorageArea(__int64 a1, int a2, _QWORD *a3)
{
  int BasicProfileFolderPath; // eax
  unsigned int v5; // ebx
  unsigned int v6; // r9d
  unsigned int v7; // ecx
  __int64 v8; // rax
  unsigned __int64 v9; // rsi
  void *v10; // rax
  void *v11; // rdi
  wchar_t Destination[264]; // [rsp+20h] [rbp-238h] BYREF

  if ( a2 )
  {
    BasicProfileFolderPath = GetBasicProfileFolderPath(6, a1, Destination, 261);
    v5 = BasicProfileFolderPath;
    if ( BasicProfileFolderPath < 0 )
    {
      v6 = 88;
LABEL_4:
      v7 = BasicProfileFolderPath;
LABEL_5:
      SidKeyDebugTraceError(v7, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx", v6);
      return v5;
    }
  }
  else
  {
    BasicProfileFolderPath = GetBasicProfileFolderPath(5, a1, Destination, 261);
    v5 = BasicProfileFolderPath;
    if ( BasicProfileFolderPath < 0 )
    {
      v6 = 103;
      goto LABEL_4;
    }
    if ( wcscat_s(Destination, 0x105u, L"\\AppData\\Local") )
    {
      v5 = -2147467259;
      v6 = 113;
      v7 = -2147467259;
      goto LABEL_5;
    }
  }
  v8 = -1;
  do
    ++v8;
  while ( Destination[v8] );
  v9 = 2 * v8 + 2;
  v10 = SIDKeyProvAlloc(v9);
  v11 = v10;
  if ( !v10 )
  {
    v5 = -2147024882;
    v6 = 124;
    v7 = -2147024882;
    goto LABEL_5;
  }
  if ( v9 <= 0x20A )
  {
    memcpy_0(v10, Destination, v9);
    *a3 = v11;
  }
  else
  {
    SidKeyDebugTraceError(
      0x80004005,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
      0x83u);
    SIDKeyProvFree(v11);
    return (unsigned int)-2147467259;
  }
  return v5;
}

```

## disassembly

```asm
0x18000be6c  mov     [rsp+arg_8], rbx
0x18000be71  mov     [rsp+arg_18], rbp
0x18000be76  push    rsi
0x18000be77  push    rdi
0x18000be78  push    r14
0x18000be7a  sub     rsp, 240h
0x18000be81  mov     rax, cs:__security_cookie
0x18000be88  xor     rax, rsp
0x18000be8b  mov     [rsp+258h+var_28], rax
0x18000be93  xor     ebp, ebp
0x18000be95  mov     r14, r8
0x18000be98  test    edx, edx
0x18000be9a  lea     r8, [rsp+258h+Destination]
0x18000be9f  mov     rdx, rcx
0x18000bea2  jz      short loc_18000BED7
0x18000bea4  mov     r9d, 105h
0x18000beaa  lea     ecx, [rbp+6]
0x18000bead  call    cs:__imp_GetBasicProfileFolderPath
0x18000beb3  mov     ebx, eax
0x18000beb5  test    eax, eax
0x18000beb7  jns     short loc_18000BF22
0x18000beb9  lea     r9d, [rbp+58h]; unsigned int
0x18000bebd  mov     ecx, eax; unsigned int
0x18000bebf  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000bec6  lea     rdx, aHr; "hr"
0x18000becd  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000bed2  jmp     loc_18000BFA8
0x18000bed7  mov     edi, 105h
0x18000bedc  mov     ecx, 5
0x18000bee1  mov     r9d, edi
0x18000bee4  call    cs:__imp_GetBasicProfileFolderPath
0x18000beea  mov     ebx, eax
0x18000beec  test    eax, eax
0x18000beee  jns     short loc_18000BEF8
0x18000bef0  mov     r9d, 67h ; 'g'
0x18000bef6  jmp     short loc_18000BEBD
0x18000bef8  lea     r8, aAppdataLocal; "\\AppData\\Local"
0x18000beff  mov     rdx, rdi; SizeInWords
0x18000bf02  lea     rcx, [rsp+258h+Destination]; Destination
0x18000bf07  call    wcscat_s
0x18000bf0c  test    eax, eax
0x18000bf0e  jz      short loc_18000BF22
0x18000bf10  mov     ebx, 80004005h
0x18000bf15  mov     r9d, 71h ; 'q'
0x18000bf1b  mov     ecx, 80004005h
0x18000bf20  jmp     short loc_18000BEBF
0x18000bf22  lea     rcx, [rsp+258h+Destination]
0x18000bf27  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bf2b  inc     rax
0x18000bf2e  cmp     [rcx+rax*2], bp
0x18000bf32  jnz     short loc_18000BF2B
0x18000bf34  lea     rsi, ds:2[rax*2]
0x18000bf3c  mov     rcx, rsi; unsigned __int64
0x18000bf3f  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000bf44  mov     rdi, rax
0x18000bf47  test    rax, rax
0x18000bf4a  jnz     short loc_18000BF5F
0x18000bf4c  mov     ebx, 8007000Eh
0x18000bf51  lea     r9d, [rax+7Ch]
0x18000bf55  mov     ecx, 8007000Eh
0x18000bf5a  jmp     loc_18000BEBF
0x18000bf5f  cmp     rsi, 20Ah
0x18000bf66  jbe     short loc_18000BF95
0x18000bf68  mov     r9d, 83h; unsigned int
0x18000bf6e  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000bf75  lea     rdx, aHr; "hr"
0x18000bf7c  mov     ecx, 80004005h; unsigned int
0x18000bf81  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000bf86  mov     rcx, rdi; lpMem
0x18000bf89  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000bf8e  mov     ebx, 80004005h
0x18000bf93  jmp     short loc_18000BFA8
0x18000bf95  mov     r8, rsi; Size
0x18000bf98  lea     rdx, [rsp+258h+Destination]; Src
0x18000bf9d  mov     rcx, rdi; void *
0x18000bfa0  call    memcpy_0
0x18000bfa5  mov     [r14], rdi
0x18000bfa8  mov     eax, ebx
0x18000bfaa  mov     rcx, [rsp+258h+var_28]
0x18000bfb2  xor     rcx, rsp; StackCookie
0x18000bfb5  call    __security_check_cookie
0x18000bfba  lea     r11, [rsp+258h+var_18]
0x18000bfc2  mov     rbx, [r11+28h]
0x18000bfc6  mov     rbp, [r11+38h]
0x18000bfca  mov     rsp, r11
0x18000bfcd  pop     r14
0x18000bfcf  pop     rdi
0x18000bfd0  pop     rsi
0x18000bfd1  retn
```
