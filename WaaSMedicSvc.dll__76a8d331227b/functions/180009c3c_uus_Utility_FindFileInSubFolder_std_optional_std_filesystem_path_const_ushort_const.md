# uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,ushort const *)

- ea: `0x180009c3c`
- end: `0x180009d07`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEBG@Z`
- size: `203`
- prototype: `__int64 __fastcall(__int64, struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009b34`

## callees

- `0x180008f20`
- `0x180009c3c`
- `0x180009d10`

## pseudocode

```c
__int64 __fastcall uus::Utility::FindFileInSubFolder(__int64 a1, struct std::filesystem::path *a2)
{
  std::filesystem::path *FileInSubFolder; // rcx
  char v4; // bl
  _BYTE v6[32]; // [rsp+28h] [rbp-60h] BYREF
  char v7; // [rsp+48h] [rbp-40h]
  _BYTE v8[56]; // [rsp+50h] [rbp-38h] BYREF

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
0x180009c3c  mov     [rsp+arg_0], rbx
0x180009c41  push    rdi
0x180009c42  sub     rsp, 80h
0x180009c49  cmp     byte ptr [rdx+20h], 0
0x180009c4d  mov     rdi, rcx
0x180009c50  mov     [rsp+88h+var_68], 0
0x180009c58  jz      short loc_180009C6E
0x180009c5a  lea     rcx, [rsp+88h+var_38]; this
0x180009c5f  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)
0x180009c64  mov     rcx, rax
0x180009c67  mov     ebx, 5
0x180009c6c  jmp     short loc_180009C7D
0x180009c6e  mov     [rsp+88h+var_40], 0
0x180009c73  lea     rcx, [rsp+88h+var_60]
0x180009c78  mov     ebx, 6
0x180009c7d  mov     byte ptr [rdi+20h], 0
0x180009c81  cmp     byte ptr [rcx+20h], 0
0x180009c85  jz      short loc_180009CC4
0x180009c87  xorps   xmm0, xmm0
0x180009c8a  xor     eax, eax
0x180009c8c  movups  xmmword ptr [rdi], xmm0
0x180009c8f  mov     qword ptr [rdi+10h], 0
0x180009c97  mov     qword ptr [rdi+18h], 0
0x180009c9f  movups  xmm0, xmmword ptr [rcx]
0x180009ca2  movups  xmmword ptr [rdi], xmm0
0x180009ca5  movups  xmm1, xmmword ptr [rcx+10h]
0x180009ca9  movups  xmmword ptr [rdi+10h], xmm1
0x180009cad  mov     qword ptr [rcx+10h], 0
0x180009cb5  mov     qword ptr [rcx+18h], 7
0x180009cbd  mov     [rcx], ax
0x180009cc0  mov     byte ptr [rdi+20h], 1
0x180009cc4  test    bl, 2
0x180009cc7  jz      short loc_180009CDD
0x180009cc9  and     ebx, 0FFFFFFFDh
0x180009ccc  cmp     [rsp+88h+var_40], 0
0x180009cd1  jz      short loc_180009CDD
0x180009cd3  lea     rcx, [rsp+88h+var_60]
0x180009cd8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009cdd  test    bl, 1
0x180009ce0  jz      short loc_180009CF3
0x180009ce2  cmp     [rsp+88h+var_18], 0
0x180009ce7  jz      short loc_180009CF3
0x180009ce9  lea     rcx, [rsp+88h+var_38]
0x180009cee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009cf3  mov     rbx, [rsp+88h+arg_0]
0x180009cfb  mov     rax, rdi
0x180009cfe  add     rsp, 80h
0x180009d05  pop     rdi
0x180009d06  retn
```
