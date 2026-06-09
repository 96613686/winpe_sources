# IsGuidVolName(WSTRING *)

- ea: `0x18000957c`
- end: `0x1800096b2`
- name: `?IsGuidVolName@@YAEPEAVWSTRING@@@Z`
- size: `310`
- prototype: `unsigned __int8 __fastcall(struct WSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015d0`

## callees

- `0x18000957c`

## import_xrefs

- `ulib!?Stricmp@WSTRING@@QEBAJPEBV1@KKKK@Z` at `0x180009628`
- `ulib!?Stricmp@WSTRING@@QEBAJPEBV1@KKKK@Z` at `0x180009665`
- `ulib!?Stricmp@WSTRING@@QEBAJPEBV1@KKKK@Z` at `0x180009628`
- `ulib!?Stricmp@WSTRING@@QEBAJPEBV1@KKKK@Z` at `0x180009665`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x1800095b9`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x1800095d6`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x1800095b9`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x1800095d6`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x18000959a`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x1800095a4`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x18000959a`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x1800095a4`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180009673`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000967d`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000968b`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180009695`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180009673`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000967d`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000968b`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180009695`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x1800095e7`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x1800095f3`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x180009605`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x180009636`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x180009642`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x1800095e7`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x1800095f3`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x180009605`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x180009636`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x180009642`

## pseudocode

```c
unsigned __int8 __fastcall IsGuidVolName(struct WSTRING *a1)
{
  unsigned int ChCount; // ebx
  unsigned int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  _BYTE v7[48]; // [rsp+30h] [rbp-9h] BYREF
  _BYTE v8[48]; // [rsp+60h] [rbp+27h] BYREF

  DSTRING::DSTRING((DSTRING *)v7);
  DSTRING::DSTRING((DSTRING *)v8);
  if ( !WSTRING::Initialize((WSTRING *)v7, L"\\??\\", 0xFFFFFFFF)
    || !WSTRING::Initialize((WSTRING *)v8, L"Volume{", 0xFFFFFFFF)
    || (ChCount = WSTRING::QueryChCount(a1), ChCount <= WSTRING::QueryChCount((WSTRING *)v7))
    || (v3 = WSTRING::QueryChCount((WSTRING *)v7), WSTRING::Stricmp(
                                                     a1,
                                                     (const struct WSTRING *)v7,
                                                     0,
                                                     v3,
                                                     0,
                                                     0xFFFFFFFF))
    || (v4 = WSTRING::QueryChCount((WSTRING *)v8),
        v5 = WSTRING::QueryChCount((WSTRING *)v7),
        WSTRING::Stricmp(a1, (const struct WSTRING *)v8, v5, v4, 0, 0xFFFFFFFF)) )
  {
    DSTRING::~DSTRING((DSTRING *)v8);
    DSTRING::~DSTRING((DSTRING *)v7);
    return 0;
  }
  else
  {
    DSTRING::~DSTRING((DSTRING *)v8);
    DSTRING::~DSTRING((DSTRING *)v7);
    return 1;
  }
}

```

## disassembly

```asm
0x18000957c  mov     [rsp-8+arg_0], rbx
0x180009581  mov     [rsp-8+arg_8], rdi
0x180009586  push    rbp
0x180009587  lea     rbp, [rsp-57h]
0x18000958c  sub     rsp, 90h
0x180009593  mov     rdi, rcx
0x180009596  lea     rcx, [rbp+57h+var_60]
0x18000959a  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x1800095a0  lea     rcx, [rbp+57h+var_30]
0x1800095a4  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x1800095aa  or      r8d, 0FFFFFFFFh
0x1800095ae  lea     rdx, asc_18000BB40; "\\??\\"
0x1800095b5  lea     rcx, [rbp+57h+var_60]
0x1800095b9  call    cs:__imp_?Initialize@WSTRING@@QEAAEPEBGK@Z; WSTRING::Initialize(ushort const *,ulong)
0x1800095bf  test    al, al
0x1800095c1  jz      loc_180009687
0x1800095c7  or      r8d, 0FFFFFFFFh
0x1800095cb  lea     rdx, aVolume; "Volume{"
0x1800095d2  lea     rcx, [rbp+57h+var_30]
0x1800095d6  call    cs:__imp_?Initialize@WSTRING@@QEAAEPEBGK@Z; WSTRING::Initialize(ushort const *,ulong)
0x1800095dc  test    al, al
0x1800095de  jz      loc_180009687
0x1800095e4  mov     rcx, rdi
0x1800095e7  call    cs:__imp_?QueryChCount@WSTRING@@QEBAKXZ; WSTRING::QueryChCount(void)
0x1800095ed  lea     rcx, [rbp+57h+var_60]
0x1800095f1  mov     ebx, eax
0x1800095f3  call    cs:__imp_?QueryChCount@WSTRING@@QEBAKXZ; WSTRING::QueryChCount(void)
0x1800095f9  cmp     ebx, eax
0x1800095fb  jbe     loc_180009687
0x180009601  lea     rcx, [rbp+57h+var_60]
0x180009605  call    cs:__imp_?QueryChCount@WSTRING@@QEBAKXZ; WSTRING::QueryChCount(void)
0x18000960b  mov     [rsp+90h+var_68], 0FFFFFFFFh
0x180009613  lea     rdx, [rbp+57h+var_60]
0x180009617  mov     r9d, eax
0x18000961a  mov     [rsp+90h+var_70], 0
0x180009622  xor     r8d, r8d
0x180009625  mov     rcx, rdi
0x180009628  call    cs:__imp_?Stricmp@WSTRING@@QEBAJPEBV1@KKKK@Z; WSTRING::Stricmp(WSTRING const *,ulong,ulong,ulong,ulong)
0x18000962e  test    eax, eax
0x180009630  jnz     short loc_180009687
0x180009632  lea     rcx, [rbp+57h+var_30]
0x180009636  call    cs:__imp_?QueryChCount@WSTRING@@QEBAKXZ; WSTRING::QueryChCount(void)
0x18000963c  lea     rcx, [rbp+57h+var_60]
0x180009640  mov     ebx, eax
0x180009642  call    cs:__imp_?QueryChCount@WSTRING@@QEBAKXZ; WSTRING::QueryChCount(void)
0x180009648  mov     [rsp+90h+var_68], 0FFFFFFFFh
0x180009650  lea     rdx, [rbp+57h+var_30]
0x180009654  mov     r8d, eax
0x180009657  mov     [rsp+90h+var_70], 0
0x18000965f  mov     r9d, ebx
0x180009662  mov     rcx, rdi
0x180009665  call    cs:__imp_?Stricmp@WSTRING@@QEBAJPEBV1@KKKK@Z; WSTRING::Stricmp(WSTRING const *,ulong,ulong,ulong,ulong)
0x18000966b  test    eax, eax
0x18000966d  jnz     short loc_180009687
0x18000966f  lea     rcx, [rbp+57h+var_30]
0x180009673  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180009679  lea     rcx, [rbp+57h+var_60]
0x18000967d  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180009683  mov     al, 1
0x180009685  jmp     short loc_18000969D
0x180009687  lea     rcx, [rbp+57h+var_30]
0x18000968b  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180009691  lea     rcx, [rbp+57h+var_60]
0x180009695  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x18000969b  xor     al, al
0x18000969d  lea     r11, [rsp+90h+var_s0]
0x1800096a5  mov     rbx, [r11+10h]
0x1800096a9  mov     rdi, [r11+18h]
0x1800096ad  mov     rsp, r11
0x1800096b0  pop     rbp
0x1800096b1  retn
```
