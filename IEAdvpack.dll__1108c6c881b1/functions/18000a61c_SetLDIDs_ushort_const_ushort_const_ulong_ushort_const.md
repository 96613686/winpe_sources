# SetLDIDs(ushort const *,ushort const *,ulong,ushort const *)

- ea: `0x18000a61c`
- end: `0x18000a8b6`
- name: `?SetLDIDs@@YAJPEBG0K0@Z`
- size: `666`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180004754`
- `0x180004880`
- `0x18000c0c0`
- `0x180010710`
- `0x1800108a0`

## callees

- `0x1800022bc`
- `0x1800053f0`
- `0x1800063c4`
- `0x1800071c0`
- `0x180007454`
- `0x180008a6c`
- `0x180009478`
- `0x18000a61c`
- `0x18000ef90`
- `0x18001b980`

## import_xrefs

- `USER32!CharNextW` at `0x18000a70b`
- `USER32!CharNextW` at `0x18000a70b`
- `KERNEL32!CompareStringW` at `0x18000a793`
- `KERNEL32!CompareStringW` at `0x18000a793`
- `SHLWAPI!StrChrW` at `0x18000a6f8`
- `SHLWAPI!StrChrW` at `0x18000a6f8`

## pseudocode

```c
__int64 __fastcall SetLDIDs(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  int DestinationDir; // edi
  unsigned int v8; // r9d
  WCHAR *i; // rbx
  __int64 v10; // rax
  WCHAR *v11; // rsi
  const WCHAR *v12; // rax
  const WCHAR *v13; // r14
  const unsigned __int16 *v14; // rax
  unsigned int v15; // r14d
  unsigned int j; // ebx
  DWORD v17; // ecx
  char v18; // r8
  bool v19; // zf
  unsigned int cchCount2; // [rsp+28h] [rbp-D8h]
  PCNZWCH lpString1; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int Id[6]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR AppName[256]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v25[264]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v26[256]; // [rsp+470h] [rbp+370h] BYREF
  WCHAR pszStart[512]; // [rsp+670h] [rbp+570h] BYREF

  lpString1 = 0;
  *(_OWORD *)Id = 0;
  if ( (int)GetTranslatedString(a1, a2, L"CustomDestination", AppName, 0x100u, 0) < 0 )
    return 0;
  SetSysPathsInReg(0);
  SetSysPathsInReg(0x200u);
  if ( GetTranslatedSection(a1, AppName, pszStart, v8) )
  {
    DestinationDir = 0;
    for ( i = pszStart; ; i = v11 )
    {
      if ( !*i )
        return (unsigned int)DestinationDir;
      v10 = -1;
      do
        ++v10;
      while ( i[v10] );
      v11 = &i[v10 + 1];
      if ( *i != 59 )
      {
        v12 = StrChrW(i, 0x3Du);
        v13 = v12;
        if ( v12 )
        {
          v14 = CharNextW(v12);
          StringCchCopyW(v26, 0x100u, v14);
          *v13 = 0;
          v15 = ParseDestinationLine(i, v26, (unsigned __int16 **)&lpString1, Id, &Id[1], &Id[2], &Id[3]);
          if ( v15 == -1 )
          {
            MsgBox2Param(hWnd, 0x45Du, AppName, 0, 0x10u, 0);
            return (unsigned int)-2147467259;
          }
          if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"SourceDir", -1) == 2 )
          {
            if ( !a4 )
              continue;
            StringCchCopyW(v25, 0x106u, a4);
          }
          else
          {
            if ( a4 )
              continue;
            DestinationDir = GetDestinationDir(a1, lpString1, v15, a3, v25, cchCount2);
            if ( DestinationDir < 0 )
              return (unsigned int)DestinationDir;
          }
          for ( j = 0; j < 4; ++j )
          {
            v17 = Id[j];
            if ( v17 )
            {
              if ( (!j || (v18 = 0, j == 3)) && (v18 = 2, !j) || j == 2 )
              {
                if ( (v15 & 0x11) == 1 )
                {
                  v18 |= 1u;
                  if ( j )
                    v19 = Id[1] == 0;
                  else
                    v19 = Id[3] == 0;
                  if ( !v19 )
                    v18 |= 4u;
                }
              }
              DestinationDir = CtlSetLddPath(v17, v25, v18);
              if ( DestinationDir < 0 )
                return (unsigned int)DestinationDir;
            }
          }
        }
      }
    }
  }
  MsgBox2Param(hWnd, 0x45Du, AppName, 0, 0x10u, 0);
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x18000a61c  push    rbp
0x18000a61e  push    rbx
0x18000a61f  push    rsi
0x18000a620  push    rdi
0x18000a621  push    r12
0x18000a623  push    r13
0x18000a625  push    r14
0x18000a627  push    r15
0x18000a629  lea     rbp, [rsp-988h]
0x18000a631  sub     rsp, 0A88h
0x18000a638  mov     rax, cs:__security_cookie
0x18000a63f  xor     rax, rsp
0x18000a642  mov     [rbp+9C0h+var_50], rax
0x18000a649  xor     ebx, ebx
0x18000a64b  mov     r15, r9
0x18000a64e  mov     r13d, r8d
0x18000a651  mov     qword ptr [rsp+0AC0h+cchCount2], rbx; unsigned int *
0x18000a656  xorps   xmm0, xmm0
0x18000a659  mov     dword ptr [rsp+0AC0h+lpString2], 100h; unsigned int
0x18000a661  lea     r9, [rsp+0AC0h+AppName]; unsigned __int16 *
0x18000a666  mov     [rsp+0AC0h+lpString1], rbx
0x18000a66b  lea     r8, aCustomdestinat; "CustomDestination"
0x18000a672  mov     r12, rcx
0x18000a675  movups  xmmword ptr [rsp+0AC0h+Id], xmm0
0x18000a67a  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000a67f  test    eax, eax
0x18000a681  jns     short loc_18000A68A
0x18000a683  mov     edi, ebx
0x18000a685  jmp     loc_18000A891
0x18000a68a  xor     ecx, ecx; unsigned int
0x18000a68c  call    ?SetSysPathsInReg@@YAXK@Z; SetSysPathsInReg(ulong)
0x18000a691  mov     ecx, 200h; unsigned int
0x18000a696  call    ?SetSysPathsInReg@@YAXK@Z; SetSysPathsInReg(ulong)
0x18000a69b  lea     r8, [rbp+9C0h+pszStart]; lpReturnedString
0x18000a6a2  mov     rcx, r12; lpFileName
0x18000a6a5  lea     rdx, [rsp+0AC0h+AppName]; lpAppName
0x18000a6aa  call    ?GetTranslatedSection@@YAKPEBG0PEAGK@Z; GetTranslatedSection(ushort const *,ushort const *,ushort *,ulong)
0x18000a6af  xor     edx, edx
0x18000a6b1  test    eax, eax
0x18000a6b3  jnz     short loc_18000A6BE
0x18000a6b5  mov     [rsp+0AC0h+cchCount2], edx
0x18000a6b9  jmp     loc_18000A86B
0x18000a6be  mov     edi, edx
0x18000a6c0  lea     rbx, [rbp+9C0h+pszStart]
0x18000a6c7  cmp     [rbx], dx
0x18000a6ca  jz      loc_18000A891
0x18000a6d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a6d4  inc     rax
0x18000a6d7  cmp     [rbx+rax*2], dx
0x18000a6db  jnz     short loc_18000A6D4
0x18000a6dd  cmp     word ptr [rbx], 3Bh ; ';'
0x18000a6e1  lea     rsi, [rax+1]
0x18000a6e5  lea     rsi, [rbx+rsi*2]
0x18000a6e9  jnz     short loc_18000A6F0
0x18000a6eb  mov     rbx, rsi
0x18000a6ee  jmp     short loc_18000A6C7
0x18000a6f0  mov     edx, 3Dh ; '='; wMatch
0x18000a6f5  mov     rcx, rbx; pszStart
0x18000a6f8  call    cs:__imp_StrChrW
0x18000a6fe  xor     edx, edx
0x18000a700  mov     r14, rax
0x18000a703  test    rax, rax
0x18000a706  jz      short loc_18000A6EB
0x18000a708  mov     rcx, rax; lpsz
0x18000a70b  call    cs:__imp_CharNextW
0x18000a711  mov     edx, 100h; unsigned __int64
0x18000a716  lea     rcx, [rbp+9C0h+var_650]; unsigned __int16 *
0x18000a71d  mov     r8, rax; unsigned __int16 *
0x18000a720  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a725  lea     rax, [rsp+0AC0h+Id+0Ch]
0x18000a72a  xor     r11d, r11d
0x18000a72d  mov     [rsp+0AC0h+var_A90], rax; unsigned int *
0x18000a732  lea     r9, [rsp+0AC0h+Id]; unsigned int *
0x18000a737  lea     rax, [rsp+0AC0h+Id+8]
0x18000a73c  mov     [r14], r11w
0x18000a740  mov     qword ptr [rsp+0AC0h+cchCount2], rax; unsigned int *
0x18000a745  lea     r8, [rsp+0AC0h+lpString1]; unsigned __int16 **
0x18000a74a  lea     rax, [rsp+0AC0h+Id+4]
0x18000a74f  mov     rcx, rbx; unsigned __int16 *
0x18000a752  lea     rdx, [rbp+9C0h+var_650]; unsigned __int16 *
0x18000a759  mov     [rsp+0AC0h+lpString2], rax; unsigned int *
0x18000a75e  call    ?ParseDestinationLine@@YAKPEAG0PEAPEAGPEAK222@Z; ParseDestinationLine(ushort *,ushort *,ushort * *,ulong *,ulong *,ulong *,ulong *)
0x18000a763  mov     r14d, eax
0x18000a766  cmp     eax, 0FFFFFFFFh
0x18000a769  jz      loc_18000A863
0x18000a76f  mov     r8, [rsp+0AC0h+lpString1]; lpString1
0x18000a774  lea     rax, aSourcedir; "SourceDir"
0x18000a77b  or      r9d, 0FFFFFFFFh; cchCount1
0x18000a77f  mov     [rsp+0AC0h+cchCount2], 0FFFFFFFFh; unsigned int
0x18000a787  mov     [rsp+0AC0h+lpString2], rax; lpString2
0x18000a78c  lea     edx, [r9+2]; dwCmpFlags
0x18000a790  lea     ecx, [rdx+7Eh]; Locale
0x18000a793  call    cs:__imp_CompareStringW
0x18000a799  xor     edx, edx
0x18000a79b  cmp     eax, 2
0x18000a79e  jnz     short loc_18000A7C1
0x18000a7a0  test    r15, r15
0x18000a7a3  jz      loc_18000A6EB
0x18000a7a9  mov     r8, r15; unsigned __int16 *
0x18000a7ac  lea     rcx, [rbp+9C0h+var_860]; unsigned __int16 *
0x18000a7b3  mov     edx, 106h; unsigned __int64
0x18000a7b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a7bd  xor     edx, edx
0x18000a7bf  jmp     short loc_18000A7F5
0x18000a7c1  test    r15, r15
0x18000a7c4  jnz     loc_18000A6EB
0x18000a7ca  mov     rdx, [rsp+0AC0h+lpString1]; unsigned __int16 *
0x18000a7cf  lea     rax, [rbp+9C0h+var_860]
0x18000a7d6  mov     r9d, r13d; unsigned int
0x18000a7d9  mov     [rsp+0AC0h+lpString2], rax; unsigned __int16 *
0x18000a7de  mov     r8d, r14d; unsigned int
0x18000a7e1  mov     rcx, r12; unsigned __int16 *
0x18000a7e4  call    ?GetDestinationDir@@YAJPEBG0KKPEAGK@Z; GetDestinationDir(ushort const *,ushort const *,ulong,ulong,ushort *,ulong)
0x18000a7e9  xor     edx, edx
0x18000a7eb  mov     edi, eax
0x18000a7ed  test    eax, eax
0x18000a7ef  js      loc_18000A891
0x18000a7f5  mov     ebx, edx
0x18000a7f7  cmp     ebx, 4
0x18000a7fa  jnb     loc_18000A6EB
0x18000a800  mov     ecx, ebx
0x18000a802  mov     ecx, [rsp+rcx*4+0AC0h+Id]; Id
0x18000a806  test    ecx, ecx
0x18000a808  jz      short loc_18000A85F
0x18000a80a  test    ebx, ebx
0x18000a80c  jz      short loc_18000A816
0x18000a80e  mov     r8d, edx
0x18000a811  cmp     ebx, 3
0x18000a814  jnz     short loc_18000A820
0x18000a816  mov     r8d, 2
0x18000a81c  test    ebx, ebx
0x18000a81e  jz      short loc_18000A825
0x18000a820  cmp     ebx, 2
0x18000a823  jnz     short loc_18000A84B
0x18000a825  mov     eax, r14d
0x18000a828  and     al, 11h
0x18000a82a  cmp     al, 1
0x18000a82c  jnz     short loc_18000A84B
0x18000a82e  or      r8d, 1
0x18000a832  test    ebx, ebx
0x18000a834  jnz     short loc_18000A83C
0x18000a836  cmp     [rsp+0AC0h+Id+0Ch], edx
0x18000a83a  jmp     short loc_18000A845
0x18000a83c  cmp     ebx, 2
0x18000a83f  jnz     short loc_18000A84B
0x18000a841  cmp     [rsp+0AC0h+Id+4], edx
0x18000a845  jz      short loc_18000A84B
0x18000a847  or      r8d, 4; unsigned int
0x18000a84b  lea     rdx, [rbp+9C0h+var_860]; unsigned __int16 *
0x18000a852  call    ?CtlSetLddPath@@YAJIPEBGK@Z; CtlSetLddPath(uint,ushort const *,ulong)
0x18000a857  xor     edx, edx
0x18000a859  mov     edi, eax
0x18000a85b  test    eax, eax
0x18000a85d  js      short loc_18000A891
0x18000a85f  inc     ebx
0x18000a861  jmp     short loc_18000A7F7
0x18000a863  mov     [rsp+0AC0h+cchCount2], 0; unsigned int
0x18000a86b  mov     rcx, cs:hWnd; hWnd
0x18000a872  lea     r8, [rsp+0AC0h+AppName]; unsigned __int16 *
0x18000a877  xor     r9d, r9d; unsigned __int16 *
0x18000a87a  mov     dword ptr [rsp+0AC0h+lpString2], 10h; unsigned int
0x18000a882  mov     edx, 45Dh; uID
0x18000a887  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x18000a88c  mov     edi, 80004005h
0x18000a891  mov     eax, edi
0x18000a893  mov     rcx, [rbp+9C0h+var_50]
0x18000a89a  xor     rcx, rsp; StackCookie
0x18000a89d  call    __security_check_cookie
0x18000a8a2  add     rsp, 0A88h
0x18000a8a9  pop     r15
0x18000a8ab  pop     r14
0x18000a8ad  pop     r13
0x18000a8af  pop     r12
0x18000a8b1  pop     rdi
0x18000a8b2  pop     rsi
0x18000a8b3  pop     rbx
0x18000a8b4  pop     rbp
0x18000a8b5  retn
```
