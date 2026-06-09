# uus::Utility::FindFileInArchFolder(std::filesystem::path const &,ushort const *)

- ea: `0x180009b34`
- end: `0x180009c33`
- name: `?FindFileInArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z`
- size: `255`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000865c`

## callees

- `0x180002200`
- `0x180008f20`
- `0x180009b34`
- `0x180009c3c`
- `0x180009d10`
- `0x180009fc8`
- `0x18000a060`

## pseudocode

```c
__int64 __fastcall uus::Utility::FindFileInArchFolder(__int64 a1, __int64 a2)
{
  struct std::filesystem::path *GuestOrNativeArchFolder; // rax
  __int64 HostArchFolder; // rax
  __int16 v7; // [rsp+20h] [rbp-39h] BYREF
  __int64 v8; // [rsp+22h] [rbp-37h]
  int v9; // [rsp+2Ah] [rbp-2Fh]
  __int16 v10; // [rsp+2Eh] [rbp-2Bh]
  __m128i si128; // [rsp+30h] [rbp-29h]
  char v12; // [rsp+40h] [rbp-19h]
  __int64 v13; // [rsp+50h] [rbp-9h]
  _BYTE v14[40]; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v15[32]; // [rsp+80h] [rbp+27h] BYREF

  v13 = a1;
  GuestOrNativeArchFolder = (struct std::filesystem::path *)uus::Utility::GetGuestOrNativeArchFolder(v15, a2);
  uus::Utility::FindFileInSubFolder((std::filesystem::path *)&v7, GuestOrNativeArchFolder);
  std::wstring::~wstring(v15);
  if ( v12 )
  {
    *(_OWORD *)a1 = 0;
    *(_WORD *)a1 = v7;
    *(_QWORD *)(a1 + 2) = v8;
    *(_DWORD *)(a1 + 10) = v9;
    *(_WORD *)(a1 + 14) = v10;
    *(__m128i *)(a1 + 16) = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v7 = 0;
    *(_BYTE *)(a1 + 32) = 1;
LABEL_6:
    std::wstring::~wstring(&v7);
    return a1;
  }
  HostArchFolder = uus::Utility::GetHostArchFolder(v14, a2);
  uus::Utility::FindFileInSubFolder(a1, HostArchFolder);
  if ( v14[32] )
    std::wstring::~wstring(v14);
  if ( v12 )
    goto LABEL_6;
  return a1;
}

```

## disassembly

```asm
0x180009b34  mov     [rsp-8+arg_10], rbx
0x180009b39  mov     [rsp-8+arg_18], rdi
0x180009b3e  push    rbp
0x180009b3f  lea     rbp, [rsp-57h]
0x180009b44  sub     rsp, 0B0h
0x180009b4b  mov     rax, cs:__security_cookie
0x180009b52  xor     rax, rsp
0x180009b55  mov     [rbp+57h+var_10], rax
0x180009b59  mov     rdi, rdx
0x180009b5c  mov     rbx, rcx
0x180009b5f  mov     [rbp+57h+var_60], rcx
0x180009b63  lea     rcx, [rbp+57h+var_30]
0x180009b67  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x180009b6c  nop
0x180009b6d  mov     rdx, rax; struct std::filesystem::path *
0x180009b70  lea     rcx, [rbp+57h+var_90]; this
0x180009b74  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)
0x180009b79  nop
0x180009b7a  lea     rcx, [rbp+57h+var_30]
0x180009b7e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009b83  cmp     [rbp+57h+var_70], 0
0x180009b87  jz      short loc_180009BD7
0x180009b89  xorps   xmm0, xmm0
0x180009b8c  movups  xmmword ptr [rbx], xmm0
0x180009b8f  movzx   eax, [rbp+57h+var_90]
0x180009b93  mov     [rbx], ax
0x180009b96  movsd   xmm0, [rbp+57h+var_8E]
0x180009b9b  movsd   qword ptr [rbx+2], xmm0
0x180009ba0  mov     eax, [rbp+57h+var_86]
0x180009ba3  mov     [rbx+0Ah], eax
0x180009ba6  movzx   eax, [rbp+57h+var_82]
0x180009baa  mov     [rbx+0Eh], ax
0x180009bae  mov     rcx, qword ptr [rbp+57h+var_80]
0x180009bb2  mov     [rbx+10h], rcx
0x180009bb6  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x180009bba  mov     [rbx+18h], rcx
0x180009bbe  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180009bc6  movdqu  [rbp+57h+var_80], xmm0
0x180009bcb  xor     ecx, ecx
0x180009bcd  mov     [rbp+57h+var_90], cx
0x180009bd1  mov     byte ptr [rbx+20h], 1
0x180009bd5  jmp     short loc_180009C06
0x180009bd7  mov     rdx, rdi
0x180009bda  lea     rcx, [rbp+57h+var_58]
0x180009bde  call    ?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z; uus::Utility::GetHostArchFolder(std::filesystem::path const &)
0x180009be3  nop
0x180009be4  mov     rdx, rax
0x180009be7  mov     rcx, rbx
0x180009bea  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEBG@Z; uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,ushort const *)
0x180009bef  nop
0x180009bf0  cmp     [rbp+57h+var_38], 0
0x180009bf4  jz      short loc_180009C00
0x180009bf6  lea     rcx, [rbp+57h+var_58]
0x180009bfa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009bff  nop
0x180009c00  cmp     [rbp+57h+var_70], 0
0x180009c04  jz      short loc_180009C0F
0x180009c06  lea     rcx, [rbp+57h+var_90]
0x180009c0a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009c0f  mov     rax, rbx
0x180009c12  mov     rcx, [rbp+57h+var_10]
0x180009c16  xor     rcx, rsp; StackCookie
0x180009c19  call    __security_check_cookie
0x180009c1e  lea     r11, [rsp+0B0h+var_s0]
0x180009c26  mov     rbx, [r11+20h]
0x180009c2a  mov     rdi, [r11+28h]
0x180009c2e  mov     rsp, r11
0x180009c31  pop     rbp
0x180009c32  retn
```
