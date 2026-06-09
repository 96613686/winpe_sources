# uus::Utility::FindFileInArchFolder(std::filesystem::path const &,ushort const *)

- ea: `0x1400091b4`
- end: `0x1400092b3`
- name: `?FindFileInArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z`
- size: `255`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140007ec8`

## callees

- `0x140002120`
- `0x1400087e4`
- `0x1400091b4`
- `0x1400092bc`
- `0x140009390`
- `0x1400095d8`
- `0x14000966c`

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
0x1400091b4  mov     [rsp-8+arg_10], rbx
0x1400091b9  mov     [rsp-8+arg_18], rdi
0x1400091be  push    rbp
0x1400091bf  lea     rbp, [rsp-57h]
0x1400091c4  sub     rsp, 0B0h
0x1400091cb  mov     rax, cs:__security_cookie
0x1400091d2  xor     rax, rsp
0x1400091d5  mov     [rbp+57h+var_10], rax
0x1400091d9  mov     rdi, rdx
0x1400091dc  mov     rbx, rcx
0x1400091df  mov     [rbp+57h+var_60], rcx
0x1400091e3  lea     rcx, [rbp+57h+var_30]
0x1400091e7  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x1400091ec  nop
0x1400091ed  mov     rdx, rax; struct std::filesystem::path *
0x1400091f0  lea     rcx, [rbp+57h+var_90]; this
0x1400091f4  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)
0x1400091f9  nop
0x1400091fa  lea     rcx, [rbp+57h+var_30]
0x1400091fe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140009203  cmp     [rbp+57h+var_70], 0
0x140009207  jz      short loc_140009257
0x140009209  xorps   xmm0, xmm0
0x14000920c  movups  xmmword ptr [rbx], xmm0
0x14000920f  movzx   eax, [rbp+57h+var_90]
0x140009213  mov     [rbx], ax
0x140009216  movsd   xmm0, [rbp+57h+var_8E]
0x14000921b  movsd   qword ptr [rbx+2], xmm0
0x140009220  mov     eax, [rbp+57h+var_86]
0x140009223  mov     [rbx+0Ah], eax
0x140009226  movzx   eax, [rbp+57h+var_82]
0x14000922a  mov     [rbx+0Eh], ax
0x14000922e  mov     rcx, qword ptr [rbp+57h+var_80]
0x140009232  mov     [rbx+10h], rcx
0x140009236  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x14000923a  mov     [rbx+18h], rcx
0x14000923e  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140009246  movdqu  [rbp+57h+var_80], xmm0
0x14000924b  xor     ecx, ecx
0x14000924d  mov     [rbp+57h+var_90], cx
0x140009251  mov     byte ptr [rbx+20h], 1
0x140009255  jmp     short loc_140009286
0x140009257  mov     rdx, rdi
0x14000925a  lea     rcx, [rbp+57h+var_58]
0x14000925e  call    ?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z; uus::Utility::GetHostArchFolder(std::filesystem::path const &)
0x140009263  nop
0x140009264  mov     rdx, rax
0x140009267  mov     rcx, rbx
0x14000926a  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEBG@Z; uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,ushort const *)
0x14000926f  nop
0x140009270  cmp     [rbp+57h+var_38], 0
0x140009274  jz      short loc_140009280
0x140009276  lea     rcx, [rbp+57h+var_58]
0x14000927a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000927f  nop
0x140009280  cmp     [rbp+57h+var_70], 0
0x140009284  jz      short loc_14000928F
0x140009286  lea     rcx, [rbp+57h+var_90]
0x14000928a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000928f  mov     rax, rbx
0x140009292  mov     rcx, [rbp+57h+var_10]
0x140009296  xor     rcx, rsp; StackCookie
0x140009299  call    __security_check_cookie
0x14000929e  lea     r11, [rsp+0B0h+var_s0]
0x1400092a6  mov     rbx, [r11+20h]
0x1400092aa  mov     rdi, [r11+28h]
0x1400092ae  mov     rsp, r11
0x1400092b1  pop     rbp
0x1400092b2  retn
```
