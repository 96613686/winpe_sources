# uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)

- ea: `0x180009fc8`
- end: `0x18000a059`
- name: `?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z`
- size: `145`
- prototype: `void *__fastcall(void *, struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180009b34`
- `0x18000aa84`

## callees

- `0x180002200`
- `0x180007940`
- `0x180008f20`
- `0x180009208`
- `0x180009fc8`

## pseudocode

```c
void *__fastcall uus::Utility::GetGuestOrNativeArchFolder(void *a1, struct std::filesystem::path *a2)
{
  __int64 v4; // r8
  __int128 v6; // [rsp+30h] [rbp-38h] BYREF
  __int64 v7; // [rsp+40h] [rbp-28h]
  __int64 v8; // [rsp+48h] [rbp-20h]

  v4 = -1;
  do
    ++v4;
  while ( uus::Const::archX64[v4] );
  v6 = 0;
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v6, uus::Const::archX64);
  std::filesystem::operator/(a1, a2, (std::filesystem *)&v6);
  std::wstring::~wstring(&v6);
  return a1;
}

```

## disassembly

```asm
0x180009fc8  mov     [rsp+arg_10], rbx
0x180009fcd  push    rdi
0x180009fce  sub     rsp, 60h
0x180009fd2  mov     rax, cs:__security_cookie
0x180009fd9  xor     rax, rsp
0x180009fdc  mov     [rsp+68h+var_18], rax
0x180009fe1  mov     rdi, rdx
0x180009fe4  mov     rbx, rcx
0x180009fe7  mov     [rsp+68h+var_40], rcx
0x180009fec  xor     ecx, ecx
0x180009fee  mov     rdx, cs:?archX64@Const@uus@@2PEBGEB; ushort const * const uus::Const::archX64
0x180009ff5  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009ff9  inc     r8
0x180009ffc  cmp     [rdx+r8*2], cx
0x18000a001  jnz     short loc_180009FF9
0x18000a003  xorps   xmm0, xmm0
0x18000a006  movups  [rsp+68h+var_38], xmm0
0x18000a00b  mov     [rsp+68h+var_28], rcx
0x18000a010  mov     [rsp+68h+var_20], rcx
0x18000a015  lea     rcx, [rsp+68h+var_38]
0x18000a01a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000a01f  nop
0x18000a020  lea     r8, [rsp+68h+var_38]; this
0x18000a025  mov     rdx, rdi; struct std::filesystem::path *
0x18000a028  mov     rcx, rbx; Src
0x18000a02b  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18000a030  nop
0x18000a031  lea     rcx, [rsp+68h+var_38]
0x18000a036  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a03b  mov     rax, rbx
0x18000a03e  mov     rcx, [rsp+68h+var_18]
0x18000a043  xor     rcx, rsp; StackCookie
0x18000a046  call    __security_check_cookie
0x18000a04b  mov     rbx, [rsp+68h+arg_10]
0x18000a053  add     rsp, 60h
0x18000a057  pop     rdi
0x18000a058  retn
```
