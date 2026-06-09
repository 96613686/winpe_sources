# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x180093900`
- end: `0x180093aba`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `442`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180093900`
- `0x18039e5b0`

## import_xrefs

- `MSVCP140!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x180093a10`
- `MSVCP140!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x180093a10`
- `MSVCP140!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x180093960`
- `MSVCP140!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x180093960`
- `MSVCP140!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x180093943`
- `MSVCP140!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x180093943`
- `MSVCP140!?setg@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXPEAD00@Z` at `0x1800939a4`
- `MSVCP140!?setg@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXPEAD00@Z` at `0x1800939a4`
- `MSVCP140!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x180093935`
- `MSVCP140!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18009394f`
- `MSVCP140!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x180093935`
- `MSVCP140!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18009394f`
- `MSVCP140!?eback@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x180093981`
- `MSVCP140!?eback@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x180093981`
- `api-ms-win-crt-stdio-l1-1-0!fputc` at `0x1800939be`
- `api-ms-win-crt-stdio-l1-1-0!fputc` at `0x180093a30`
- `api-ms-win-crt-stdio-l1-1-0!fputc` at `0x1800939be`
- `api-ms-win-crt-stdio-l1-1-0!fputc` at `0x180093a30`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x180093a6a`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x180093a6a`

## pseudocode

```c
__int64 __fastcall std::filebuf::overflow(__int64 a1, unsigned int a2)
{
  unsigned __int64 v5; // rbx
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ecx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // ecx
  __int64 v13; // rbx
  unsigned int v14; // ecx
  char v15; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v16[7]; // [rsp+41h] [rbp-47h] BYREF
  _BYTE *v17; // [rsp+48h] [rbp-40h] BYREF
  char *v18; // [rsp+50h] [rbp-38h] BYREF
  _BYTE Buffer[32]; // [rsp+58h] [rbp-30h] BYREF
  __int64 v20; // [rsp+78h] [rbp-10h] BYREF

  if ( a2 == -1 )
    return 0;
  if ( ((__int64 (*)(void))std::streambuf::pptr)() )
  {
    v5 = std::streambuf::epptr(a1);
    if ( std::streambuf::pptr(a1) < v5 )
    {
      _mm_lfence();
      *(_BYTE *)std::streambuf::_Pninc(a1) = a2;
      return a2;
    }
  }
  if ( !*(_QWORD *)(a1 + 128) )
    return 0xFFFFFFFFLL;
  if ( std::streambuf::eback(a1) == a1 + 112 )
    std::streambuf::setg(a1, *(_QWORD *)(a1 + 136), *(_QWORD *)(a1 + 136), *(_QWORD *)(a1 + 144));
  v6 = *(_QWORD *)(a1 + 104);
  if ( !v6 )
  {
    v7 = fputc((char)a2, *(FILE **)(a1 + 128));
    v8 = -1;
    if ( v7 != -1 )
      return a2;
    return v8;
  }
  v15 = a2;
  v9 = std::codecvt<char,char,_Mbstatet>::out(v6, a1 + 116, &v15, v16, &v18, Buffer, &v20, &v17);
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      if ( v10 == 2 )
      {
        v11 = fputc(v15, *(FILE **)(a1 + 128));
        v12 = -1;
        if ( v11 != -1 )
          return a2;
        return v12;
      }
      return 0xFFFFFFFFLL;
    }
  }
  if ( v17 != Buffer )
  {
    _mm_lfence();
    v13 = v17 - Buffer;
    if ( v13 != fwrite(Buffer, 1u, v17 - Buffer, *(FILE **)(a1 + 128)) )
      return 0xFFFFFFFFLL;
  }
  *(_BYTE *)(a1 + 113) = 1;
  v14 = -1;
  if ( v18 != &v15 )
    return a2;
  return v14;
}

```

## disassembly

```asm
0x180093900  mov     [rsp+arg_18], rsi
0x180093905  push    rdi
0x180093906  sub     rsp, 80h
0x18009390d  mov     rax, cs:__security_cookie
0x180093914  xor     rax, rsp
0x180093917  mov     [rsp+88h+var_10], rax
0x18009391c  mov     esi, edx
0x18009391e  mov     rdi, rcx
0x180093921  cmp     edx, 0FFFFFFFFh
0x180093924  jnz     short loc_18009392D
0x180093926  xor     eax, eax
0x180093928  jmp     loc_180093A9C
0x18009392d  mov     [rsp+88h+arg_10], rbx
0x180093935  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x18009393b  test    rax, rax
0x18009393e  jz      short loc_180093970
0x180093940  mov     rcx, rdi
0x180093943  call    cs:__imp_?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::epptr(void)
0x180093949  mov     rcx, rdi
0x18009394c  mov     rbx, rax
0x18009394f  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x180093955  cmp     rax, rbx
0x180093958  jnb     short loc_180093970
0x18009395a  lfence
0x18009395d  mov     rcx, rdi
0x180093960  call    cs:__imp_?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ; std::streambuf::_Pninc(void)
0x180093966  mov     [rax], sil
0x180093969  mov     eax, esi
0x18009396b  jmp     loc_180093A94
0x180093970  cmp     qword ptr [rdi+80h], 0
0x180093978  jz      loc_180093A8F
0x18009397e  mov     rcx, rdi
0x180093981  call    cs:__imp_?eback@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::eback(void)
0x180093987  lea     rcx, [rdi+70h]
0x18009398b  cmp     rax, rcx
0x18009398e  jnz     short loc_1800939AA
0x180093990  mov     rdx, [rdi+88h]
0x180093997  mov     rcx, rdi
0x18009399a  mov     r9, [rdi+90h]
0x1800939a1  mov     r8, rdx
0x1800939a4  call    cs:__imp_?setg@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXPEAD00@Z; std::streambuf::setg(char *,char *,char *)
0x1800939aa  mov     rcx, [rdi+68h]
0x1800939ae  test    rcx, rcx
0x1800939b1  jnz     short loc_1800939D5
0x1800939b3  mov     rdx, [rdi+80h]; Stream
0x1800939ba  movsx   ecx, sil; Character
0x1800939be  call    cs:__imp_fputc
0x1800939c4  mov     ecx, 0FFFFFFFFh
0x1800939c9  cmp     eax, ecx
0x1800939cb  cmovnz  ecx, esi
0x1800939ce  mov     eax, ecx
0x1800939d0  jmp     loc_180093A94
0x1800939d5  lea     rax, [rsp+88h+var_40]
0x1800939da  mov     [rsp+88h+var_48], sil
0x1800939df  mov     [rsp+88h+var_50], rax
0x1800939e4  lea     rdx, [rdi+74h]
0x1800939e8  lea     rax, [rsp+88h+var_10]
0x1800939ed  mov     [rsp+88h+var_58], rax
0x1800939f2  lea     r9, [rsp+88h+var_47]
0x1800939f7  lea     rax, [rsp+88h+Buffer]
0x1800939fc  mov     [rsp+88h+var_60], rax
0x180093a01  lea     r8, [rsp+88h+var_48]
0x180093a06  lea     rax, [rsp+88h+var_38]
0x180093a0b  mov     [rsp+88h+var_68], rax
0x180093a10  call    cs:__imp_?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::out(_Mbstatet &,char const *,char const *,char const * &,char *,char *,char * &)
0x180093a16  test    eax, eax
0x180093a18  jz      short loc_180093A44
0x180093a1a  sub     eax, 1
0x180093a1d  jz      short loc_180093A44
0x180093a1f  cmp     eax, 2
0x180093a22  jnz     short loc_180093A8F
0x180093a24  movsx   ecx, [rsp+88h+var_48]; Character
0x180093a29  mov     rdx, [rdi+80h]; Stream
0x180093a30  call    cs:__imp_fputc
0x180093a36  mov     ecx, 0FFFFFFFFh
0x180093a3b  cmp     eax, ecx
0x180093a3d  cmovnz  ecx, esi
0x180093a40  mov     eax, ecx
0x180093a42  jmp     short loc_180093A94
0x180093a44  mov     rbx, [rsp+88h+var_40]
0x180093a49  lea     rax, [rsp+88h+Buffer]
0x180093a4e  sub     rbx, rax
0x180093a51  jz      short loc_180093A75
0x180093a53  lfence
0x180093a56  mov     r9, [rdi+80h]; Stream
0x180093a5d  lea     rcx, [rsp+88h+Buffer]; Buffer
0x180093a62  mov     r8, rbx; ElementCount
0x180093a65  mov     edx, 1; ElementSize
0x180093a6a  call    cs:__imp_fwrite
0x180093a70  cmp     rbx, rax
0x180093a73  jnz     short loc_180093A8F
0x180093a75  lea     rax, [rsp+88h+var_48]
0x180093a7a  mov     byte ptr [rdi+71h], 1
0x180093a7e  cmp     [rsp+88h+var_38], rax
0x180093a83  mov     ecx, 0FFFFFFFFh
0x180093a88  cmovnz  ecx, esi
0x180093a8b  mov     eax, ecx
0x180093a8d  jmp     short loc_180093A94
0x180093a8f  mov     eax, 0FFFFFFFFh
0x180093a94  mov     rbx, [rsp+88h+arg_10]
0x180093a9c  mov     rcx, [rsp+88h+var_10]
0x180093aa1  xor     rcx, rsp; StackCookie
0x180093aa4  call    __security_check_cookie
0x180093aa9  mov     rsi, [rsp+88h+arg_18]
0x180093ab1  add     rsp, 80h
0x180093ab8  pop     rdi
0x180093ab9  retn
```
