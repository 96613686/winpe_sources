# EURL::Initialize(ulong,int *)

- ea: `0x180002048`
- end: `0x180002246`
- name: `?Initialize@EURL@@SAJKPEAH@Z`
- size: `510`
- prototype: `__int64 __fastcall(unsigned int, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001ad0`

## callees

- `0x180001fa4`
- `0x180002048`
- `0x1800030d4`
- `0x1800031c4`
- `0x1800031fc`
- `0x180003950`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x1800021a0`
- `KERNEL32!MultiByteToWideChar` at `0x1800021cd`
- `KERNEL32!MultiByteToWideChar` at `0x1800021a0`
- `KERNEL32!MultiByteToWideChar` at `0x1800021cd`
- `KERNEL32!lstrlenW` at `0x180002238`
- `KERNEL32!lstrlenW` at `0x180002238`
- `KERNEL32!lstrlenA` at `0x18000214f`
- `KERNEL32!lstrlenA` at `0x18000214f`
- `KERNEL32!GetLastError` at `0x1800021aa`
- `KERNEL32!GetLastError` at `0x1800021aa`
- `ole32!CoCreateGuid` at `0x1800020b4`
- `ole32!CoCreateGuid` at `0x1800020b4`

## pseudocode

```c
__int64 __fastcall EURL::Initialize(unsigned int a1, int *a2)
{
  unsigned int LastWin32Error; // ebx
  CHAR *v3; // rdi
  unsigned __int16 *v4; // rsi
  int EnableExtensionlessUrlsRegKey; // eax
  CHAR *v7; // rax
  GUID *p_pguid; // r9
  _BYTE *v9; // r8
  char v10; // al
  unsigned __int8 v11; // dl
  unsigned __int8 v12; // cl
  _BYTE *v13; // r8
  char v14; // al
  int v15; // r14d
  int cchWideChar; // ebp
  WCHAR *lpWideCharStr; // rax
  GUID pguid; // [rsp+30h] [rbp-38h] BYREF
  GUID v20; // [rsp+40h] [rbp-28h] BYREF

  LastWin32Error = 0;
  v3 = 0;
  v4 = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  *a2 = 0;
  if ( a1 >= 6 )
  {
    if ( a1 == 6 )
    {
      EURL::sm_fIIS6 = 1;
      EURL::sm_fNeedToCheckScriptMap = 1;
    }
    EnableExtensionlessUrlsRegKey = EURL::GetEnableExtensionlessUrlsRegKey();
    *a2 = EnableExtensionlessUrlsRegKey;
    if ( EnableExtensionlessUrlsRegKey )
    {
      LastWin32Error = CoCreateGuid(&pguid);
      if ( !LastWin32Error )
      {
        v7 = (CHAR *)MemAllocClear(0x2Bu);
        v3 = v7;
        if ( !v7 )
          return (unsigned int)-2147024882;
        qmemcpy(v7, "/eurl.axd/", 10);
        p_pguid = &pguid;
        v9 = v7 + 10;
        do
        {
          v10 = 48;
          v11 = p_pguid->Data1 & 0xF;
          v12 = LOBYTE(p_pguid->Data1) >> 4;
          if ( v12 > 9u )
            v10 = 87;
          *v9 = v12 + v10;
          v13 = v9 + 1;
          v14 = 48;
          if ( v11 > 9u )
            v14 = 87;
          p_pguid = (GUID *)((char *)p_pguid + 1);
          *v13 = v11 + v14;
          v9 = v13 + 1;
        }
        while ( p_pguid < &v20 );
        *v9 = 0;
        v15 = lstrlenA(v3);
        cchWideChar = v15 + 1;
        lpWideCharStr = (WCHAR *)MemAllocClear(saturated_mul((unsigned int)(v15 + 1), 2u));
        v4 = lpWideCharStr;
        if ( !lpWideCharStr )
        {
          LastWin32Error = -2147024882;
LABEL_26:
          MemFree(v3);
          return LastWin32Error;
        }
        if ( MultiByteToWideChar(0xFDE9u, 8u, v3, cchWideChar, lpWideCharStr, cchWideChar)
          || GetLastError() == 1113 && MultiByteToWideChar(0, 9u, v3, cchWideChar, v4, cchWideChar) )
        {
          EURL::sm_pszEURLAppendage = v3;
          LODWORD(EURL::sm_cchEURLAppendage) = v15;
          EURL::sm_pszEURLAppendageW = v4;
          EURL::sm_cchEURLAppendageW = lstrlenW(v4);
          return LastWin32Error;
        }
        LastWin32Error = GetLastWin32Error();
      }
      if ( (LastWin32Error & 0x80000000) != 0 )
      {
        if ( v4 )
          MemFree(v4);
        if ( v3 )
          goto LABEL_26;
      }
    }
  }
  return LastWin32Error;
}

```

## disassembly

```asm
0x180002048  mov     [rsp+arg_0], rbx
0x18000204d  mov     [rsp+arg_10], rbp
0x180002052  push    rsi
0x180002053  push    rdi
0x180002054  push    r14
0x180002056  sub     rsp, 50h
0x18000205a  mov     rax, cs:__security_cookie
0x180002061  xor     rax, rsp
0x180002064  mov     qword ptr [rsp+68h+var_28.Data1], rax
0x180002069  xor     ebx, ebx
0x18000206b  xor     edi, edi
0x18000206d  xor     esi, esi
0x18000206f  mov     r14, rdx
0x180002072  test    rdx, rdx
0x180002075  jnz     short loc_180002081
0x180002077  mov     ebx, 80070057h
0x18000207c  jmp     loc_1800021FC
0x180002081  and     [rdx], ebx
0x180002083  cmp     ecx, 6
0x180002086  jb      loc_1800021FC
0x18000208c  mov     ebp, 1
0x180002091  jnz     short loc_18000209F
0x180002093  mov     cs:?sm_fIIS6@EURL@@0HA, ebp; int EURL::sm_fIIS6
0x180002099  mov     cs:?sm_fNeedToCheckScriptMap@EURL@@0HC, ebp; int volatile EURL::sm_fNeedToCheckScriptMap
0x18000209f  call    ?GetEnableExtensionlessUrlsRegKey@EURL@@CAHXZ; EURL::GetEnableExtensionlessUrlsRegKey(void)
0x1800020a4  mov     [r14], eax
0x1800020a7  test    eax, eax
0x1800020a9  jz      loc_1800021FC
0x1800020af  lea     rcx, [rsp+68h+pguid]; pguid
0x1800020b4  call    cs:__imp_CoCreateGuid
0x1800020ba  mov     ebx, eax
0x1800020bc  test    eax, eax
0x1800020be  jnz     loc_1800021DE
0x1800020c4  lea     ecx, [rax+2Bh]; unsigned __int64
0x1800020c7  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x1800020cc  mov     rdi, rax
0x1800020cf  test    rax, rax
0x1800020d2  jnz     short loc_1800020DE
0x1800020d4  mov     ebx, 8007000Eh
0x1800020d9  jmp     loc_1800021FC
0x1800020de  movsd   xmm0, qword ptr cs:aEurlAxd; "/eurl.axd"
0x1800020e6  lea     r8, [rdi+9]
0x1800020ea  movsd   qword ptr [rax], xmm0
0x1800020ee  lea     r9, [rsp+68h+pguid]
0x1800020f3  mov     al, byte ptr cs:aEurlAxd+8; "d"
0x1800020f9  mov     r10d, 30h ; '0'
0x1800020ff  mov     [rdi+8], al
0x180002102  mov     byte ptr [r8], 2Fh ; '/'
0x180002106  add     r8, rbp
0x180002109  lea     r11d, [r10+27h]
0x18000210d  mov     dl, [r9]
0x180002110  mov     eax, r10d
0x180002113  mov     cl, dl
0x180002115  and     dl, 0Fh
0x180002118  shr     cl, 4
0x18000211b  cmp     cl, 9
0x18000211e  cmova   eax, r11d
0x180002122  add     al, cl
0x180002124  mov     [r8], al
0x180002127  add     r8, rbp
0x18000212a  cmp     dl, 9
0x18000212d  mov     eax, r10d
0x180002130  cmova   eax, r11d
0x180002134  add     r9, rbp
0x180002137  add     al, dl
0x180002139  mov     [r8], al
0x18000213c  add     r8, rbp
0x18000213f  lea     rax, [rsp+68h+var_28]
0x180002144  cmp     r9, rax
0x180002147  jb      short loc_18000210D
0x180002149  mov     rcx, rdi; lpString
0x18000214c  mov     [r8], sil
0x18000214f  call    cs:__imp_lstrlenA
0x180002155  mov     r14d, eax
0x180002158  lea     ebp, [rax+1]
0x18000215b  mov     eax, 2
0x180002160  mov     ecx, ebp
0x180002162  mul     rcx
0x180002165  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000216c  cmovo   rax, rcx
0x180002170  mov     rcx, rax; unsigned __int64
0x180002173  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180002178  mov     rsi, rax
0x18000217b  test    rax, rax
0x18000217e  jnz     short loc_180002187
0x180002180  mov     ebx, 8007000Eh
0x180002185  jmp     short loc_1800021F4
0x180002187  mov     [rsp+68h+cchWideChar], ebp; cchWideChar
0x18000218b  mov     r9d, ebp; cbMultiByte
0x18000218e  mov     r8, rdi; lpMultiByteStr
0x180002191  mov     [rsp+68h+lpWideCharStr], rsi; lpWideCharStr
0x180002196  mov     edx, 8; dwFlags
0x18000219b  mov     ecx, 0FDE9h; CodePage
0x1800021a0  call    cs:__imp_MultiByteToWideChar
0x1800021a6  test    eax, eax
0x1800021a8  jnz     short loc_180002220
0x1800021aa  call    cs:__imp_GetLastError
0x1800021b0  cmp     eax, 459h
0x1800021b5  jnz     short loc_1800021D7
0x1800021b7  mov     [rsp+68h+cchWideChar], ebp; cchWideChar
0x1800021bb  mov     r9d, ebp; cbMultiByte
0x1800021be  mov     r8, rdi; lpMultiByteStr
0x1800021c1  mov     [rsp+68h+lpWideCharStr], rsi; lpWideCharStr
0x1800021c6  mov     edx, 9; dwFlags
0x1800021cb  xor     ecx, ecx; CodePage
0x1800021cd  call    cs:__imp_MultiByteToWideChar
0x1800021d3  test    eax, eax
0x1800021d5  jnz     short loc_180002220
0x1800021d7  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800021dc  mov     ebx, eax
0x1800021de  test    ebx, ebx
0x1800021e0  jns     short loc_1800021FC
0x1800021e2  test    rsi, rsi
0x1800021e5  jz      short loc_1800021EF
0x1800021e7  mov     rcx, rsi; lpMem
0x1800021ea  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800021ef  test    rdi, rdi
0x1800021f2  jz      short loc_1800021FC
0x1800021f4  mov     rcx, rdi; lpMem
0x1800021f7  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800021fc  mov     eax, ebx
0x1800021fe  mov     rcx, qword ptr [rsp+68h+var_28.Data1]
0x180002203  xor     rcx, rsp; StackCookie
0x180002206  call    __security_check_cookie
0x18000220b  lea     r11, [rsp+68h+var_18]
0x180002210  mov     rbx, [r11+20h]
0x180002214  mov     rbp, [r11+30h]
0x180002218  mov     rsp, r11
0x18000221b  pop     r14
0x18000221d  pop     rdi
0x18000221e  pop     rsi
0x18000221f  retn
0x180002220  mov     rcx, rsi; lpString
0x180002223  mov     cs:?sm_pszEURLAppendage@EURL@@0PEADEA, rdi; char * EURL::sm_pszEURLAppendage
0x18000222a  mov     cs:?sm_cchEURLAppendage@EURL@@0KA, r14d; ulong EURL::sm_cchEURLAppendage
0x180002231  mov     cs:?sm_pszEURLAppendageW@EURL@@0PEAGEA, rsi; ushort * EURL::sm_pszEURLAppendageW
0x180002238  call    cs:__imp_lstrlenW
0x18000223e  mov     cs:?sm_cchEURLAppendageW@EURL@@0KA, eax; ulong EURL::sm_cchEURLAppendageW
0x180002244  jmp     short loc_1800021FC
```
