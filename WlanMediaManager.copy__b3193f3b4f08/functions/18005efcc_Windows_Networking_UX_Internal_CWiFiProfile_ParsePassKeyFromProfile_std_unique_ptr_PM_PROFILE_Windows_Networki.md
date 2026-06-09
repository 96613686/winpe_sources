# Windows::Networking::UX::Internal::CWiFiProfile::_ParsePassKeyFromProfile(std::unique_ptr<_PM_PROFILE,Windows::Networking::UX::Internal::ppm_profile_deleter> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18005efcc`
- end: `0x18005f1e9`
- name: `?_ParsePassKeyFromProfile@CWiFiProfile@Internal@UX@Networking@Windows@@AEAAJAEBV?$unique_ptr@U_PM_PROFILE@@Uppm_profile_deleter@Internal@UX@Networking@Windows@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005c610`

## callees

- `0x180009794`
- `0x1800097b4`
- `0x18000e928`
- `0x18001caf8`
- `0x18005b9d4`
- `0x18005efcc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005f03b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005f08b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005f03b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005f08b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f0c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f1ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f0c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f1ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::Internal::CWiFiProfile::_ParsePassKeyFromProfile(
        WCHAR *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rbx
  int v5; // eax
  const CHAR *v6; // r8
  int v7; // eax
  const char *v8; // r9
  int cchWideChar; // edi
  __int64 result; // rax
  const char *v11; // r9
  int v12; // eax
  const char *v13; // r9
  unsigned int LastError; // ebx
  LPWSTR v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // r14
  __int64 v19; // rdi
  __int64 i; // r11
  __int64 v21; // r10
  __int64 v22; // r8
  __int64 v23; // rcx
  LPWSTR v24; // rcx
  bool v25; // zf
  int lpWideCharStr; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPWSTR v28; // [rsp+60h] [rbp+8h] BYREF

  v28 = a1;
  try
  {
    v4 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 552LL) + 32LL) + 424LL);
    v5 = *(_DWORD *)(v4 + 64);
    if ( !v5 || (v6 = *(const CHAR **)(v4 + 72)) == 0 || (*(_BYTE *)v4 & 1) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x285,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
        (const char *)0x80070057LL,
        lpWideCharStr);
      return 2147942487LL;
    }
    if ( (*(_BYTE *)v4 & 2) != 0 )
    {
      v7 = MultiByteToWideChar(0xFDE9u, 0, v6, v5, 0, 0);
      cchWideChar = v7;
      if ( !v7 )
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x28B,
                 (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
                 v8);
      wil::make_unique_cotaskmem<unsigned short [0]>(&v28, (unsigned int)(v7 + 1));
      v12 = MultiByteToWideChar(0xFDE9u, 0, *(LPCCH *)(v4 + 72), *(_DWORD *)(v4 + 64), v28, cchWideChar);
      if ( !v12 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x290,
                      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
                      v13);
        v15 = v28;
        v28 = 0;
        if ( v15 )
          CoTaskMemFree(v15);
        return LastError;
      }
      v28[v12] = 0;
      v16 = std::_WChar_traits<unsigned short>::length(v28);
      std::wstring::_Assign<unsigned short>(a3, v17, v16);
    }
    else
    {
      wil::make_unique_cotaskmem<unsigned short [0]>(&v28, (unsigned int)(2 * v5 + 1));
      v18 = *(_QWORD *)(v4 + 72);
      v19 = 0;
      for ( i = 0; (unsigned int)v19 < *(_DWORD *)(v4 + 64); v19 = (unsigned int)(v19 + 1) )
      {
        v21 = (unsigned int)(i + 1);
        v28[(unsigned int)i] = (*(_BYTE *)(v19 + v18) >> 4)
                             + 55
                             + ((unsigned __int8)(*(_BYTE *)(v19 + v18) >> 4) < 0xAu ? 0xFFF9 : 0);
        i = (unsigned int)(i + 2);
        v28[v21] = (*(_BYTE *)(v19 + v18) & 0xF) + ((*(_BYTE *)(v19 + v18) & 0xFu) < 0xA ? 48 : 55);
      }
      v28[i] = 0;
      v22 = std::_WChar_traits<unsigned short>::length(v28);
      std::wstring::_Assign<unsigned short>(a3, v23, v22);
    }
    v24 = v28;
    v25 = v28 == 0;
    v28 = 0;
    if ( !v25 )
      CoTaskMemFree(v24);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2AD,
                           (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x18005efcc  mov     [rsp+arg_0], rcx
0x18005efd1  push    rbx
0x18005efd2  push    rsi
0x18005efd3  push    rdi
0x18005efd4  push    r14
0x18005efd6  sub     rsp, 38h
0x18005efda  mov     rsi, r8
0x18005efdd  mov     rax, [rdx]
0x18005efe0  mov     rcx, [rax+228h]
0x18005efe7  mov     rax, [rcx+20h]
0x18005efeb  mov     rbx, [rax+1A8h]
0x18005eff2  mov     eax, [rbx+40h]
0x18005eff5  test    eax, eax
0x18005eff7  jz      loc_18005F1B8
0x18005effd  mov     r8, [rbx+48h]; lpMultiByteStr
0x18005f001  test    r8, r8
0x18005f004  jz      loc_18005F1B8
0x18005f00a  test    byte ptr [rbx], 1
0x18005f00d  jnz     loc_18005F1B8
0x18005f013  test    byte ptr [rbx], 2
0x18005f016  jz      loc_18005F0F8
0x18005f01c  mov     [rsp+58h+cchWideChar], 0; cchWideChar
0x18005f024  mov     [rsp+58h+lpWideCharStr], 0; lpWideCharStr
0x18005f02d  mov     r9d, eax; cbMultiByte
0x18005f030  xor     edx, edx; dwFlags
0x18005f032  mov     r14d, 0FDE9h
0x18005f038  mov     ecx, r14d; CodePage
0x18005f03b  call    cs:__imp_MultiByteToWideChar
0x18005f041  mov     edi, eax
0x18005f043  test    eax, eax
0x18005f045  jnz     short loc_18005F062
0x18005f047  mov     rcx, [rsp+58h]; this
0x18005f04c  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005f053  mov     edx, 28Bh; void *
0x18005f058  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005f05d  jmp     loc_18005F1DE
0x18005f062  lea     edx, [rax+1]
0x18005f065  lea     rcx, [rsp+58h+arg_0]
0x18005f06a  call    ??$make_unique_cotaskmem@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<ushort [0]>(unsigned __int64)
0x18005f06f  nop
0x18005f070  mov     rax, [rsp+58h+arg_0]
0x18005f075  mov     [rsp+58h+cchWideChar], edi; cchWideChar
0x18005f079  mov     [rsp+58h+lpWideCharStr], rax; lpWideCharStr
0x18005f07e  mov     r9d, [rbx+40h]; cbMultiByte
0x18005f082  mov     r8, [rbx+48h]; lpMultiByteStr
0x18005f086  xor     edx, edx; dwFlags
0x18005f088  mov     ecx, r14d; CodePage
0x18005f08b  call    cs:__imp_MultiByteToWideChar
0x18005f091  test    eax, eax
0x18005f093  jnz     short loc_18005F0CD
0x18005f095  mov     rcx, [rsp+58h]; this
0x18005f09a  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005f0a1  mov     edx, 290h; void *
0x18005f0a6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005f0ab  mov     ebx, eax
0x18005f0ad  mov     rcx, [rsp+58h+arg_0]; pv
0x18005f0b2  mov     [rsp+58h+arg_0], 0
0x18005f0bb  test    rcx, rcx
0x18005f0be  jz      short loc_18005F0C6
0x18005f0c0  call    cs:__imp_CoTaskMemFree
0x18005f0c6  mov     eax, ebx
0x18005f0c8  jmp     loc_18005F1DE
0x18005f0cd  mov     edx, eax
0x18005f0cf  xor     ecx, ecx
0x18005f0d1  mov     rax, [rsp+58h+arg_0]
0x18005f0d6  mov     [rax+rdx*2], cx
0x18005f0da  mov     rcx, [rsp+58h+arg_0]
0x18005f0df  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18005f0e4  mov     r8, rax
0x18005f0e7  mov     rdx, rcx
0x18005f0ea  mov     rcx, rsi
0x18005f0ed  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005f0f2  nop
0x18005f0f3  jmp     loc_18005F19B
0x18005f0f8  lea     edx, ds:1[rax*2]
0x18005f0ff  lea     rcx, [rsp+58h+arg_0]
0x18005f104  call    ??$make_unique_cotaskmem@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<ushort [0]>(unsigned __int64)
0x18005f109  nop
0x18005f10a  mov     r14, [rbx+48h]
0x18005f10e  xor     edi, edi
0x18005f110  xor     r11d, r11d
0x18005f113  cmp     [rbx+40h], edi
0x18005f116  jbe     short loc_18005F176
0x18005f118  mov     al, [rdi+r14]
0x18005f11c  shr     al, 4
0x18005f11f  movzx   edx, al
0x18005f122  mov     r8d, r11d
0x18005f125  inc     r11d
0x18005f128  mov     r10d, r11d
0x18005f12b  cmp     dl, 0Ah
0x18005f12e  sbb     cx, cx
0x18005f131  and     cx, 0FFF9h
0x18005f136  add     dx, 37h ; '7'
0x18005f13a  add     cx, dx
0x18005f13d  mov     rax, [rsp+58h+arg_0]
0x18005f142  mov     [rax+r8*2], cx
0x18005f147  mov     al, [rdi+r14]
0x18005f14b  and     al, 0Fh
0x18005f14d  movzx   ecx, al
0x18005f150  inc     r11d
0x18005f153  cmp     cl, 0Ah
0x18005f156  sbb     dx, dx
0x18005f159  and     dx, 0FFF9h
0x18005f15e  add     dx, 37h ; '7'
0x18005f162  add     dx, cx
0x18005f165  mov     rax, [rsp+58h+arg_0]
0x18005f16a  mov     [rax+r10*2], dx
0x18005f16f  inc     edi
0x18005f171  cmp     edi, [rbx+40h]
0x18005f174  jb      short loc_18005F118
0x18005f176  xor     ecx, ecx
0x18005f178  mov     rax, [rsp+58h+arg_0]
0x18005f17d  mov     [rax+r11*2], cx
0x18005f182  mov     rcx, [rsp+58h+arg_0]
0x18005f187  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18005f18c  mov     r8, rax
0x18005f18f  mov     rdx, rcx
0x18005f192  mov     rcx, rsi
0x18005f195  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005f19a  nop
0x18005f19b  mov     rcx, [rsp+58h+arg_0]; pv
0x18005f1a0  test    rcx, rcx
0x18005f1a3  mov     [rsp+58h+arg_0], 0
0x18005f1ac  jz      short loc_18005F1B4
0x18005f1ae  call    cs:__imp_CoTaskMemFree
0x18005f1b4  xor     eax, eax
0x18005f1b6  jmp     short loc_18005F1DE
0x18005f1b8  mov     rcx, [rsp+58h]; this
0x18005f1bd  mov     ebx, 80070057h
0x18005f1c2  mov     r9d, ebx; char *
0x18005f1c5  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005f1cc  mov     edx, 285h; void *
0x18005f1d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f1d6  mov     eax, ebx
0x18005f1d8  jmp     short loc_18005F1DE
0x18005f1da  mov     eax, dword ptr [rsp+58h+arg_0]
0x18005f1de  add     rsp, 38h
0x18005f1e2  pop     r14
0x18005f1e4  pop     rdi
0x18005f1e5  pop     rsi
0x18005f1e6  pop     rbx
0x18005f1e7  retn
```
