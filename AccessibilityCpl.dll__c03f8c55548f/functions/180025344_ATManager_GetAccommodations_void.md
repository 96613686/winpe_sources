# ATManager::GetAccommodations(void)

- ea: `0x180025344`
- end: `0x18002547b`
- name: `?GetAccommodations@ATManager@@QEAAAEBV?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@XZ`
- size: `311`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001d070`
- `0x18001f1b4`
- `0x18001f820`
- `0x18001f9d8`
- `0x180022724`
- `0x1800256a0`
- `0x180025a18`
- `0x1800288dc`

## callees

- `0x1800055c0`
- `0x180014828`
- `0x180020edc`
- `0x180025344`
- `0x180025484`
- `0x18002d220`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180025441`
- `ADVAPI32!RegEnumKeyExW` at `0x180025441`

## string_xrefs

- `0x180025387`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATManager::GetAccommodations(__int64 a1)
{
  DWORD v2; // esi
  DWORD i; // edx
  __int64 v4; // rax
  __int64 *v5; // rcx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct Accommodation *v9; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[64]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  if ( !(unsigned int)ATL::CRegKey::Open(
                        (ATL::CRegKey *)hKey,
                        HKEY_LOCAL_MACHINE,
                        L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATs",
                        0x20019u) )
  {
    v2 = 0;
    for ( i = 0; ; i = v2 )
    {
      cchName = 64;
      if ( RegEnumKeyExW(hKey[0], i, Name, &cchName, 0, 0, 0, 0) == 259 )
        break;
      v9 = Accommodation::Open(Name);
      if ( v9 )
      {
        v4 = ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::NewNode(
               a1 + 304,
               &v9,
               *(_QWORD *)(a1 + 312));
        v5 = *(__int64 **)(a1 + 312);
        if ( v5 )
          *v5 = v4;
        else
          *(_QWORD *)(a1 + 304) = v4;
        *(_QWORD *)(a1 + 312) = v4;
      }
      ++v2;
    }
  }
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return a1 + 304;
}

```

## disassembly

```asm
0x180025344  push    rbp
0x180025346  push    rbx
0x180025347  push    rsi
0x180025348  push    rdi
0x180025349  lea     rbp, [rsp-8]
0x18002534e  sub     rsp, 108h
0x180025355  mov     rax, cs:__security_cookie
0x18002535c  xor     rax, rsp
0x18002535f  mov     [rbp+20h+var_30], rax
0x180025363  mov     rdi, rcx
0x180025366  mov     [rsp+120h+hKey], 0
0x18002536f  mov     [rsp+120h+var_D0], 0
0x180025378  mov     [rsp+120h+var_C8], 0
0x180025381  mov     r9d, 20019h; unsigned int
0x180025387  lea     r8, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002538e  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180025395  lea     rcx, [rsp+120h+hKey]; this
0x18002539a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002539f  test    eax, eax
0x1800253a1  jnz     loc_180025452
0x1800253a7  xor     esi, esi
0x1800253a9  mov     [rsp+120h+lpftLastWriteTime], rsi
0x1800253ae  mov     [rsp+120h+lpcchClass], rsi
0x1800253b3  mov     [rsp+120h+lpClass], rsi
0x1800253b8  mov     [rsp+120h+lpReserved], rsi
0x1800253bd  xor     edx, edx
0x1800253bf  jmp     short loc_18002542A
0x1800253c1  lea     rcx, [rsp+120h+Name]; unsigned __int16 *
0x1800253c6  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x1800253cb  mov     [rsp+120h+var_C0], rax
0x1800253d0  test    rax, rax
0x1800253d3  jz      short loc_180025402
0x1800253d5  lea     rbx, [rdi+130h]
0x1800253dc  mov     r8, [rbx+8]
0x1800253e0  lea     rdx, [rsp+120h+var_C0]
0x1800253e5  mov     rcx, rbx
0x1800253e8  call    ?NewNode@?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@AEAAPEAVCNode@12@AEBQEAVAccommodation@@PEAV312@1@Z; ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::NewNode(Accommodation * const &,ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::CNode *,ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::CNode *)
0x1800253ed  mov     rcx, [rbx+8]
0x1800253f1  test    rcx, rcx
0x1800253f4  jz      short loc_1800253FB
0x1800253f6  mov     [rcx], rax
0x1800253f9  jmp     short loc_1800253FE
0x1800253fb  mov     [rbx], rax
0x1800253fe  mov     [rbx+8], rax
0x180025402  inc     esi
0x180025404  mov     [rsp+120h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18002540d  mov     [rsp+120h+lpcchClass], 0; lpcchClass
0x180025416  mov     [rsp+120h+lpClass], 0; lpClass
0x18002541f  mov     [rsp+120h+lpReserved], 0; lpReserved
0x180025428  mov     edx, esi; dwIndex
0x18002542a  mov     [rsp+120h+cchName], 40h ; '@'
0x180025432  lea     r9, [rsp+120h+cchName]; lpcchName
0x180025437  lea     r8, [rsp+120h+Name]; lpName
0x18002543c  mov     rcx, [rsp+120h+hKey]; hKey
0x180025441  call    cs:__imp_RegEnumKeyExW
0x180025447  cmp     eax, 103h
0x18002544c  jnz     loc_1800253C1
0x180025452  lea     rcx, [rsp+120h+hKey]; this
0x180025457  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002545c  lea     rax, [rdi+130h]
0x180025463  mov     rcx, [rbp+20h+var_30]
0x180025467  xor     rcx, rsp; StackCookie
0x18002546a  call    __security_check_cookie
0x18002546f  add     rsp, 108h
0x180025476  pop     rdi
0x180025477  pop     rsi
0x180025478  pop     rbx
0x180025479  pop     rbp
0x18002547a  retn
```
