# uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,wchar_t const *)

- ea: `0x180002b10`
- end: `0x180002bcf`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEB_W@Z`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002db0`

## callees

- `0x180002b10`
- `0x180002bd8`
- `0x1800078ac`

## pseudocode

```c
__int64 __fastcall uus::Utility::FindFileInSubFolder(__int64 a1, struct std::filesystem::path *a2)
{
  std::filesystem::path *FileInSubFolder; // rax
  char v4; // bl
  _BYTE v6[32]; // [rsp+28h] [rbp-60h] BYREF
  char v7; // [rsp+48h] [rbp-40h]
  _BYTE v8[48]; // [rsp+50h] [rbp-38h] BYREF

  if ( *((_BYTE *)a2 + 32) )
  {
    FileInSubFolder = uus::Utility::FindFileInSubFolder((std::filesystem::path *)v8, a2);
    v4 = 5;
  }
  else
  {
    v7 = 0;
    FileInSubFolder = (std::filesystem::path *)v6;
    v4 = 6;
  }
  *(_BYTE *)(a1 + 32) = 0;
  if ( *((_BYTE *)FileInSubFolder + 32) )
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)FileInSubFolder;
    *(_OWORD *)(a1 + 16) = *((_OWORD *)FileInSubFolder + 1);
    *((_QWORD *)FileInSubFolder + 2) = 0;
    *((_QWORD *)FileInSubFolder + 3) = 7;
    *(_WORD *)FileInSubFolder = 0;
    *(_BYTE *)(a1 + 32) = 1;
  }
  if ( (v4 & 2) != 0 )
  {
    v4 &= ~2u;
    if ( v7 )
      std::wstring::~wstring(v6);
  }
  if ( (v4 & 1) != 0 && v8[32] )
    std::wstring::~wstring(v8);
  return a1;
}

```

## disassembly

```asm
0x180002b10  mov     [rsp+arg_0], rbx
0x180002b15  mov     [rsp+arg_8], rsi
0x180002b1a  push    rdi
0x180002b1b  sub     rsp, 80h
0x180002b22  xor     esi, esi
0x180002b24  mov     rdi, rcx
0x180002b27  mov     [rsp+88h+var_68], esi
0x180002b2b  cmp     [rdx+20h], sil
0x180002b2f  jz      short loc_180002B40
0x180002b31  lea     rcx, [rsp+88h+var_38]; this
0x180002b36  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEB_W@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,wchar_t const *)
0x180002b3b  lea     ebx, [rsi+5]
0x180002b3e  jmp     short loc_180002B4F
0x180002b40  mov     [rsp+88h+var_40], sil
0x180002b45  lea     rax, [rsp+88h+var_60]
0x180002b4a  mov     ebx, 6
0x180002b4f  mov     [rdi+20h], sil
0x180002b53  cmp     [rax+20h], sil
0x180002b57  jz      short loc_180002B88
0x180002b59  xorps   xmm0, xmm0
0x180002b5c  movups  xmmword ptr [rdi], xmm0
0x180002b5f  mov     [rdi+10h], rsi
0x180002b63  mov     [rdi+18h], rsi
0x180002b67  movups  xmm0, xmmword ptr [rax]
0x180002b6a  movups  xmmword ptr [rdi], xmm0
0x180002b6d  movups  xmm1, xmmword ptr [rax+10h]
0x180002b71  movups  xmmword ptr [rdi+10h], xmm1
0x180002b75  mov     [rax+10h], rsi
0x180002b79  mov     qword ptr [rax+18h], 7
0x180002b81  mov     [rax], si
0x180002b84  mov     byte ptr [rdi+20h], 1
0x180002b88  test    bl, 2
0x180002b8b  jz      short loc_180002BA1
0x180002b8d  and     ebx, 0FFFFFFFDh
0x180002b90  cmp     [rsp+88h+var_40], sil
0x180002b95  jz      short loc_180002BA1
0x180002b97  lea     rcx, [rsp+88h+var_60]
0x180002b9c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180002ba1  test    bl, 1
0x180002ba4  jz      short loc_180002BB7
0x180002ba6  cmp     [rsp+88h+var_18], sil
0x180002bab  jz      short loc_180002BB7
0x180002bad  lea     rcx, [rsp+88h+var_38]
0x180002bb2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180002bb7  lea     r11, [rsp+88h+var_8]
0x180002bbf  mov     rax, rdi
0x180002bc2  mov     rbx, [r11+10h]
0x180002bc6  mov     rsi, [r11+18h]
0x180002bca  mov     rsp, r11
0x180002bcd  pop     rdi
0x180002bce  retn
```
