# TrustedHosts::IsHostTrusted(IRequestContext *,ushort const *,int *)

- ea: `0x1800bad58`
- end: `0x1800bb137`
- name: `?IsHostTrusted@TrustedHosts@@QEAAHPEAVIRequestContext@@PEBGPEAH@Z`
- size: `991`
- prototype: `int(TrustedHosts *__hidden this, struct IRequestContext *, const unsigned __int16 *, int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180060afc`
- `0x180071468`
- `0x1800bacec`

## callees

- `0x180005d10`
- `0x180008920`
- `0x18005f000`
- `0x1800621e0`
- `0x1800bad58`
- `0x18011a6d4`
- `0x18011d8c0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wcsrev` at `0x1800bafb4`
- `msvcrt!_wcsrev` at `0x1800bafc0`
- `msvcrt!_wcsrev` at `0x1800bafb4`
- `msvcrt!_wcsrev` at `0x1800bafc0`
- `msvcrt!iswspace` at `0x1800bae0e`
- `msvcrt!iswspace` at `0x1800bae0e`
- `msvcrt!wcschr` at `0x1800bae5a`
- `msvcrt!wcschr` at `0x1800bae6b`
- `msvcrt!wcschr` at `0x1800baea5`
- `msvcrt!wcschr` at `0x1800bae5a`
- `msvcrt!wcschr` at `0x1800bae6b`
- `msvcrt!wcschr` at `0x1800baea5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800baecc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800baf0c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800bafdd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800baecc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800baf0c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800bafdd`

## string_xrefs

- `0x1800badcf`: `onecore\admin\wmi\wmx\config\trustedhosts.cpp`
- `0x1800bb04e`: `StringCchCopy`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TrustedHosts::IsHostTrusted(
        const wchar_t ****this,
        struct IRequestContext *a2,
        const unsigned __int16 *a3,
        int *a4)
{
  const unsigned __int16 *i; // rdi
  const wchar_t ***v10; // rax
  const wchar_t **v11; // rsi
  const wchar_t **v12; // rax
  const unsigned __int16 *v13; // r15
  wchar_t *v14; // rax
  __int64 cchCount2; // rbx
  int v16; // ebx
  __int64 v17; // rax
  int v18; // r13d
  unsigned __int16 *v19; // rbx
  unsigned __int16 *v20; // rdi
  int v21; // eax
  __int64 v22; // r9
  int v23; // eax
  wchar_t *v24; // rbx
  wchar_t *v25; // rax
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rax
  __int64 v28; // rdx
  unsigned __int16 *v29; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t **j; // [rsp+38h] [rbp-40h]
  unsigned __int16 *v31; // [rsp+88h] [rbp+10h] BYREF
  int *v32; // [rsp+98h] [rbp+20h]

  v32 = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_d1bb1550caba3f3b1ee77d3ec9bfc5b4_Traceguids, this);
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\trustedhosts.cpp", 113, L"113", 0x54Fu, 0);
    return 0;
  }
  if ( !a4 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\trustedhosts.cpp", 114, L"114", 0x54Fu, a2);
    return 0;
  }
  if ( !a3 )
  {
LABEL_57:
    v28 = 87;
    goto LABEL_58;
  }
  for ( i = a3; ; ++i )
  {
    if ( !*i )
      goto LABEL_57;
    if ( !iswspace(*i) )
      break;
  }
  if ( !this[3] || !this[4] )
  {
    v28 = 14;
LABEL_58:
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, v28);
    return 0;
  }
  *a4 = 0;
  if ( !*((_DWORD *)this + 5) )
    return 1;
  if ( *((_DWORD *)this + 5) != 1 && (wcschr(a3, 0x2Eu) || wcschr(a3, 0x3Au) || *((_DWORD *)this + 5) != 3) )
  {
    v10 = this[3];
    v11 = *v10;
    v12 = v10[1];
    for ( j = v12; ; v12 = j )
    {
      if ( v11 == v12 )
        return 1;
      v13 = *v11;
      if ( !*v11 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\trustedhosts.cpp", 160, L"160", 0x54Fu, a2);
        return 0;
      }
      v14 = wcschr(*v11, 0x2Au);
      if ( v14 )
      {
        cchCount2 = v14 - v13;
        if ( !(_DWORD)cchCount2 || CompareStringW(0x7Fu, 1u, v13, cchCount2, a3, cchCount2) == 2 )
        {
          v16 = ~(_DWORD)cchCount2;
          v17 = -1;
          do
            ++v17;
          while ( v13[v17] );
          v18 = v16 + v17;
          if ( v16 + (_DWORD)v17 )
          {
            v19 = (unsigned __int16 *)WSManMemory::Alloc(4096, 0, 0);
            v31 = v19;
            if ( !v19 )
            {
              (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
              goto LABEL_49;
            }
            v20 = (unsigned __int16 *)WSManMemory::Alloc(20480, 0, 0);
            v29 = v20;
            if ( !v20 )
            {
              (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
LABEL_48:
              AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v29);
LABEL_49:
              AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v31);
              return 0;
            }
            v21 = StringCchCopyW(v19, 0x800u, a3);
            v22 = (unsigned int)v21;
            if ( v21 < 0 || (v23 = StringCchCopyW(v20, 0x2800u, v13), v22 = (unsigned int)v23, v23 < 0) )
            {
              (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, __int64))(*(_QWORD *)a2 + 88LL))(
                a2,
                1077134178,
                L"StringCchCopy",
                v22);
              goto LABEL_48;
            }
            v24 = _wcsrev(v19);
            v25 = _wcsrev(v20);
            if ( CompareStringW(0x7Fu, 1u, v25, v18, v24, v18) != 2 )
            {
              AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v29);
              AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v31);
              goto LABEL_46;
            }
            AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v29);
            AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v31);
          }
          v26 = -1;
          do
            ++v26;
          while ( v13[v26] );
          v27 = -1;
          do
            ++v27;
          while ( a3[v27] );
          if ( v27 >= v26 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
              WPP_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                14,
                (unsigned int)WPP_d1bb1550caba3f3b1ee77d3ec9bfc5b4_Traceguids,
                (_DWORD)a3,
                (__int64)v13);
            break;
          }
        }
      }
      else if ( CompareStringW(0x7Fu, 1u, v13, -1, a3, -1) == 2 )
      {
        break;
      }
LABEL_46:
      ++v11;
    }
  }
  *v32 = 1;
  return 1;
}

```

## disassembly

```asm
0x1800bad58  mov     [rsp+arg_0], rbx
0x1800bad5d  mov     [rsp+arg_18], r9
0x1800bad62  push    rbp
0x1800bad63  push    rsi
0x1800bad64  push    rdi
0x1800bad65  push    r12
0x1800bad67  push    r13
0x1800bad69  push    r14
0x1800bad6b  push    r15
0x1800bad6d  sub     rsp, 40h
0x1800bad71  mov     rbp, r9
0x1800bad74  mov     r12, r8
0x1800bad77  mov     r14, rdx
0x1800bad7a  mov     rbx, rcx
0x1800bad7d  lea     rax, WPP_GLOBAL_Control
0x1800bad84  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bad8b  cmp     rcx, rax
0x1800bad8e  jz      short loc_1800BADB1
0x1800bad90  test    dword ptr [rcx+1Ch], 200000h
0x1800bad97  jz      short loc_1800BADB1
0x1800bad99  mov     edx, 0Dh
0x1800bad9e  mov     r9, rbx
0x1800bada1  lea     r8, WPP_d1bb1550caba3f3b1ee77d3ec9bfc5b4_Traceguids
0x1800bada8  mov     rcx, [rcx+10h]
0x1800badac  call    WPP_SF_q
0x1800badb1  xor     r13d, r13d
0x1800badb4  test    r14, r14
0x1800badb7  jnz     short loc_1800BADE0
0x1800badb9  mov     [rsp+78h+lpString2], r13; struct IRequestContext *
0x1800badbe  lea     r8, a113; "113"
0x1800badc5  lea     edx, [r13+71h]; unsigned int
0x1800badc9  mov     r9d, 54Fh; unsigned int
0x1800badcf  lea     rcx, aOnecoreAdminWm_151; "onecore\\admin\\wmi\\wmx\\config\\trust"...
0x1800badd6  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800baddb  jmp     loc_1800BB11D
0x1800bade0  test    rbp, rbp
0x1800bade3  jnz     short loc_1800BADF6
0x1800bade5  mov     [rsp+78h+lpString2], r14
0x1800badea  lea     r8, a114; "114"
0x1800badf1  lea     edx, [rbp+72h]
0x1800badf4  jmp     short loc_1800BADC9
0x1800badf6  test    r12, r12
0x1800badf9  jz      loc_1800BB109
0x1800badff  mov     rdi, r12
0x1800bae02  movzx   ecx, word ptr [rdi]; C
0x1800bae05  test    cx, cx
0x1800bae08  jz      loc_1800BB109
0x1800bae0e  call    cs:__imp_iswspace
0x1800bae14  test    eax, eax
0x1800bae16  jz      short loc_1800BAE1E
0x1800bae18  add     rdi, 2
0x1800bae1c  jmp     short loc_1800BAE02
0x1800bae1e  cmp     [rbx+18h], r13
0x1800bae22  jz      loc_1800BB102
0x1800bae28  cmp     [rbx+20h], r13
0x1800bae2c  jz      loc_1800BB102
0x1800bae32  mov     [rbp+0], r13d
0x1800bae36  cmp     [rbx+14h], r13d
0x1800bae3a  jnz     short loc_1800BAE46
0x1800bae3c  mov     eax, 1
0x1800bae41  jmp     loc_1800BB11F
0x1800bae46  mov     ebp, 1
0x1800bae4b  cmp     [rbx+14h], ebp
0x1800bae4e  jz      loc_1800BAEDB
0x1800bae54  lea     edx, [rbp+2Dh]; Ch
0x1800bae57  mov     rcx, r12; Str
0x1800bae5a  call    cs:__imp_wcschr
0x1800bae60  test    rax, rax
0x1800bae63  jnz     short loc_1800BAE7C
0x1800bae65  lea     edx, [rbp+39h]; Ch
0x1800bae68  mov     rcx, r12; Str
0x1800bae6b  call    cs:__imp_wcschr
0x1800bae71  test    rax, rax
0x1800bae74  jnz     short loc_1800BAE7C
0x1800bae76  cmp     dword ptr [rbx+14h], 3
0x1800bae7a  jz      short loc_1800BAEDB
0x1800bae7c  mov     rax, [rbx+18h]
0x1800bae80  mov     rsi, [rax]
0x1800bae83  mov     rax, [rax+8]
0x1800bae87  mov     [rsp+78h+var_40], rax
0x1800bae8c  cmp     rsi, rax
0x1800bae8f  jz      short loc_1800BAEE5
0x1800bae91  mov     r15, [rsi]
0x1800bae94  test    r15, r15
0x1800bae97  jz      loc_1800BB0EC
0x1800bae9d  mov     edx, 2Ah ; '*'; Ch
0x1800baea2  mov     rcx, r15; Str
0x1800baea5  call    cs:__imp_wcschr
0x1800baeab  mov     rbx, rax
0x1800baeae  test    rax, rax
0x1800baeb1  jnz     short loc_1800BAEEC
0x1800baeb3  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800baebb  mov     [rsp+78h+lpString2], r12; lpString2
0x1800baec0  or      r9d, 0FFFFFFFFh; cchCount1
0x1800baec4  mov     r8, r15; lpString1
0x1800baec7  mov     edx, ebp; dwCmpFlags
0x1800baec9  lea     ecx, [rax+7Fh]; Locale
0x1800baecc  call    cs:__imp_CompareStringW
0x1800baed2  cmp     eax, 2
0x1800baed5  jnz     loc_1800BB03D
0x1800baedb  mov     rax, [rsp+78h+arg_18]
0x1800baee3  mov     [rax], ebp
0x1800baee5  mov     eax, ebp
0x1800baee7  jmp     loc_1800BB11F
0x1800baeec  sub     rbx, r15
0x1800baeef  sar     rbx, 1
0x1800baef2  test    ebx, ebx
0x1800baef4  jz      short loc_1800BAF1B
0x1800baef6  mov     [rsp+78h+cchCount2], ebx; cchCount2
0x1800baefa  mov     [rsp+78h+lpString2], r12; lpString2
0x1800baeff  mov     r9d, ebx; cchCount1
0x1800baf02  mov     r8, r15; lpString1
0x1800baf05  mov     edx, ebp; dwCmpFlags
0x1800baf07  mov     ecx, 7Fh; Locale
0x1800baf0c  call    cs:__imp_CompareStringW
0x1800baf12  cmp     eax, 2
0x1800baf15  jnz     loc_1800BB03D
0x1800baf1b  not     ebx
0x1800baf1d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800baf21  inc     rax
0x1800baf24  cmp     [r15+rax*2], r13w
0x1800baf29  jnz     short loc_1800BAF21
0x1800baf2b  lea     r13d, [rbx+rax]
0x1800baf2f  test    r13d, r13d
0x1800baf32  jz      loc_1800BB019
0x1800baf38  xor     r8d, r8d
0x1800baf3b  xor     edx, edx
0x1800baf3d  mov     ecx, 1000h
0x1800baf42  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1800baf47  mov     rbx, rax
0x1800baf4a  mov     [rsp+78h+arg_8], rax
0x1800baf52  test    rax, rax
0x1800baf55  jz      loc_1800BB095
0x1800baf5b  xor     r8d, r8d
0x1800baf5e  xor     edx, edx
0x1800baf60  mov     ecx, 5000h
0x1800baf65  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1800baf6a  mov     rdi, rax
0x1800baf6d  mov     [rsp+78h+var_48], rax
0x1800baf72  test    rax, rax
0x1800baf75  jz      loc_1800BB084
0x1800baf7b  mov     r8, r12; unsigned __int16 *
0x1800baf7e  mov     edx, 800h; unsigned __int64
0x1800baf83  mov     rcx, rbx; unsigned __int16 *
0x1800baf86  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800baf8b  mov     r9d, eax
0x1800baf8e  test    eax, eax
0x1800baf90  js      loc_1800BB04B
0x1800baf96  mov     r8, r15; unsigned __int16 *
0x1800baf99  mov     edx, 2800h; unsigned __int64
0x1800baf9e  mov     rcx, rdi; unsigned __int16 *
0x1800bafa1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bafa6  mov     r9d, eax
0x1800bafa9  test    eax, eax
0x1800bafab  js      loc_1800BB04B
0x1800bafb1  mov     rcx, rbx; String
0x1800bafb4  call    cs:__imp__wcsrev
0x1800bafba  mov     rbx, rax
0x1800bafbd  mov     rcx, rdi; String
0x1800bafc0  call    cs:__imp__wcsrev
0x1800bafc6  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x1800bafcb  mov     [rsp+78h+lpString2], rbx; lpString2
0x1800bafd0  mov     r9d, r13d; cchCount1
0x1800bafd3  mov     r8, rax; lpString1
0x1800bafd6  mov     edx, ebp; dwCmpFlags
0x1800bafd8  mov     ecx, 7Fh; Locale
0x1800bafdd  call    cs:__imp_CompareStringW
0x1800bafe3  nop
0x1800bafe4  lea     rcx, [rsp+78h+var_48]
0x1800bafe9  cmp     eax, 2
0x1800bafec  jz      short loc_1800BB006
0x1800bafee  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800baff3  nop
0x1800baff4  lea     rcx, [rsp+78h+arg_8]
0x1800baffc  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800bb001  xor     r13d, r13d
0x1800bb004  jmp     short loc_1800BB03D
0x1800bb006  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800bb00b  nop
0x1800bb00c  lea     rcx, [rsp+78h+arg_8]
0x1800bb014  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800bb019  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800bb01d  xor     r13d, r13d
0x1800bb020  inc     rcx
0x1800bb023  cmp     [r15+rcx*2], r13w
0x1800bb028  jnz     short loc_1800BB020
0x1800bb02a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bb02e  inc     rax
0x1800bb031  cmp     [r12+rax*2], r13w
0x1800bb036  jnz     short loc_1800BB02E
0x1800bb038  cmp     rax, rcx
0x1800bb03b  jnb     short loc_1800BB0A6
0x1800bb03d  add     rsi, 8
0x1800bb041  mov     rax, [rsp+78h+var_40]
0x1800bb046  jmp     loc_1800BAE8C
0x1800bb04b  mov     rax, [r14]
0x1800bb04e  lea     r8, aStringcchcopy; "StringCchCopy"
0x1800bb055  mov     edx, 4033C362h
0x1800bb05a  mov     rcx, r14
0x1800bb05d  mov     rax, [rax+58h]
0x1800bb061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb066  nop
0x1800bb067  lea     rcx, [rsp+78h+var_48]
0x1800bb06c  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800bb071  nop
0x1800bb072  lea     rcx, [rsp+78h+arg_8]
0x1800bb07a  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800bb07f  jmp     loc_1800BB11D
0x1800bb084  mov     rax, [r14]
0x1800bb087  mov     rcx, r14
0x1800bb08a  mov     rax, [rax+18h]
0x1800bb08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb093  jmp     short loc_1800BB067
0x1800bb095  mov     rax, [r14]
0x1800bb098  mov     rcx, r14
0x1800bb09b  mov     rax, [rax+18h]
0x1800bb09f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb0a4  jmp     short loc_1800BB072
0x1800bb0a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb0ad  lea     rax, WPP_GLOBAL_Control
0x1800bb0b4  cmp     rcx, rax
0x1800bb0b7  jz      loc_1800BAEDB
0x1800bb0bd  test    dword ptr [rcx+1Ch], 200000h
0x1800bb0c4  jz      loc_1800BAEDB
0x1800bb0ca  mov     edx, 0Eh
0x1800bb0cf  mov     [rsp+78h+lpString2], r15
0x1800bb0d4  mov     r9, r12
0x1800bb0d7  lea     r8, WPP_d1bb1550caba3f3b1ee77d3ec9bfc5b4_Traceguids
0x1800bb0de  mov     rcx, [rcx+10h]
0x1800bb0e2  call    WPP_SF_SS
0x1800bb0e7  jmp     loc_1800BAEDB
0x1800bb0ec  mov     [rsp+78h+lpString2], r14
0x1800bb0f1  lea     r8, a160; "160"
0x1800bb0f8  mov     edx, 0A0h
0x1800bb0fd  jmp     loc_1800BADC9
0x1800bb102  mov     edx, 0Eh
0x1800bb107  jmp     short loc_1800BB10E
0x1800bb109  mov     edx, 57h ; 'W'
0x1800bb10e  mov     rax, [r14]
0x1800bb111  mov     rcx, r14
0x1800bb114  mov     rax, [rax+48h]
0x1800bb118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb11d  xor     eax, eax
0x1800bb11f  mov     rbx, [rsp+78h+arg_0]
0x1800bb127  add     rsp, 40h
0x1800bb12b  pop     r15
0x1800bb12d  pop     r14
0x1800bb12f  pop     r13
0x1800bb131  pop     r12
0x1800bb133  pop     rdi
0x1800bb134  pop     rsi
0x1800bb135  pop     rbp
0x1800bb136  retn
```
