# GetTranslatedLine(ushort const *,ushort const *,ulong,ushort * *,ulong *)

- ea: `0x180006e54`
- end: `0x1800071b7`
- name: `?GetTranslatedLine@@YAJPEBG0KPEAPEAGPEAK@Z`
- size: `867`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR lpAppName, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `6`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180005584`
- `0x1800063c4`
- `0x180008cf0`
- `0x180009928`
- `0x180009c14`
- `0x18000da30`

## callees

- `0x180001fd8`
- `0x1800021dc`
- `0x1800045e8`
- `0x180006068`
- `0x180006af8`
- `0x180006e54`
- `0x180007968`
- `0x180008a6c`
- `0x180009580`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800070cb`
- `KERNEL32!GetLastError` at `0x180007144`
- `KERNEL32!GetLastError` at `0x1800070cb`
- `KERNEL32!GetLastError` at `0x180007144`
- `KERNEL32!LocalFree` at `0x1800070ab`
- `KERNEL32!LocalFree` at `0x18000710a`
- `KERNEL32!LocalFree` at `0x180007184`
- `KERNEL32!LocalFree` at `0x18000719e`
- `KERNEL32!LocalFree` at `0x1800070ab`
- `KERNEL32!LocalFree` at `0x18000710a`
- `KERNEL32!LocalFree` at `0x180007184`
- `KERNEL32!LocalFree` at `0x18000719e`
- `KERNEL32!LocalAlloc` at `0x180006f08`
- `KERNEL32!LocalAlloc` at `0x180006f18`
- `KERNEL32!LocalAlloc` at `0x1800070bd`
- `KERNEL32!LocalAlloc` at `0x180006f08`
- `KERNEL32!LocalAlloc` at `0x180006f18`
- `KERNEL32!LocalAlloc` at `0x1800070bd`
- `KERNEL32!LocalReAlloc` at `0x18000712f`
- `KERNEL32!LocalReAlloc` at `0x18000712f`

## pseudocode

```c
__int64 __fastcall GetTranslatedLine(
        LPCWSTR lpFileName,
        LPCWSTR lpAppName,
        unsigned int a3,
        unsigned __int16 **a4,
        unsigned int *a5)
{
  signed int v9; // ebx
  WCHAR *v10; // r14
  unsigned __int16 *StringField; // rdi
  unsigned __int16 *v12; // rax
  __int64 v13; // rbp
  unsigned __int16 v14; // ax
  const unsigned __int16 *v15; // rcx
  __int64 v16; // rax
  _WORD *v17; // rdx
  unsigned int i; // r8d
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  int LineByIndex; // eax
  signed int LastError; // eax
  unsigned __int16 *v24; // rax
  unsigned int PrivateProfileSection; // [rsp+30h] [rbp-68h] BYREF
  int v27; // [rsp+34h] [rbp-64h]
  int v28; // [rsp+38h] [rbp-60h]
  unsigned __int16 *v29; // [rsp+40h] [rbp-58h] BYREF

  PrivateProfileSection = 0;
  v27 = 0;
  v28 = 0;
  v9 = 0;
  if ( hLibModule )
  {
    if ( !InfHandle )
      MySetupOpenInfFile(lpFileName);
    goto LABEL_11;
  }
  if ( !(unsigned int)CheckOSVersion() || !ctx )
  {
    v28 = dword_1800257F8;
    dword_1800257F8 = 1;
    v27 = 1;
    goto LABEL_11;
  }
  v10 = 0;
  dword_1800257F8 = 0;
  StringField = 0;
  if ( !(unsigned int)InitializeSetupAPI() )
  {
    v9 = -2147024809;
    goto LABEL_57;
  }
  v9 = MySetupOpenInfFile(lpFileName);
  if ( v9 >= 0 )
  {
LABEL_11:
    if ( a4 )
      *a4 = 0;
    v10 = (WCHAR *)LocalAlloc(0x40u, 0x4000u);
    v12 = (unsigned __int16 *)LocalAlloc(0x40u, 0x2000u);
    StringField = v12;
    if ( v10 && v12 )
    {
      v13 = -1;
      if ( dword_1800257F8 == 1 )
      {
        PrivateProfileSection = RO_GetPrivateProfileSection(lpAppName, v10, 0x2000u, lpFileName);
        if ( PrivateProfileSection == 8190 )
        {
          MsgBox2Param(hWnd, 0x45Du, lpAppName, 0, 0x10u, 0);
          v9 = -2147024809;
          goto LABEL_55;
        }
        v14 = *v10;
        v15 = v10;
        if ( *v10 == 59 )
        {
          do
          {
            v16 = -1;
            do
              ++v16;
            while ( v15[v16] );
            v15 += v16 + 1;
            v14 = *v15;
          }
          while ( *v15 == 59 );
          v17 = v15;
        }
        else
        {
          v17 = v10;
        }
        for ( i = 0; i < a3; ++i )
        {
          v19 = -1;
          do
            ++v19;
          while ( v17[v19] );
          v15 = &v17[v19 + 1];
          v14 = *v15;
          if ( !*v15 )
            goto LABEL_34;
          while ( v14 == 59 )
          {
            v20 = -1;
            do
              ++v20;
            while ( v15[v20] );
            v15 += v20 + 1;
            v14 = *v15;
          }
          v17 = v15;
        }
        if ( !v14 )
        {
LABEL_34:
          v9 = -2147024637;
          goto LABEL_55;
        }
        if ( hLibModule )
        {
          v9 = -2147418113;
          goto LABEL_55;
        }
        FormStrWithoutPlaceHolders(v15, StringField, i, lpFileName);
        v29 = StringField;
        StringField = GetStringField(&v29, (unsigned __int16 *)&dword_18001E82C, 34, 1);
        v21 = -1;
        do
          ++v21;
        while ( StringField[v21] );
        PrivateProfileSection = v21 + 1;
LABEL_47:
        if ( a4 )
        {
          do
            ++v13;
          while ( StringField[v13] );
          v24 = (unsigned __int16 *)LocalReAlloc(StringField, 2 * v13 + 2, 2u);
          *a4 = v24;
          if ( !v24 )
            *a4 = StringField;
        }
        else
        {
          LocalFree(StringField);
        }
        goto LABEL_55;
      }
      LineByIndex = MySetupGetLineByIndex(lpAppName, a3, v12, 0x1000u, &PrivateProfileSection);
      v9 = LineByIndex;
      if ( LineByIndex >= 0 )
        goto LABEL_47;
      if ( LineByIndex == -2147024774 )
      {
        LocalFree(StringField);
        StringField = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * PrivateProfileSection);
        if ( !StringField )
        {
          LastError = GetLastError();
          goto LABEL_53;
        }
        v9 = MySetupGetLineByIndex(lpAppName, a3, StringField, PrivateProfileSection, &PrivateProfileSection);
        if ( v9 >= 0 )
          goto LABEL_47;
      }
LABEL_55:
      if ( v27 )
        dword_1800257F8 = v28;
      goto LABEL_57;
    }
    LastError = GetLastError();
LABEL_53:
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_55;
  }
LABEL_57:
  if ( a5 )
    *a5 = PrivateProfileSection;
  if ( v10 )
    LocalFree(v10);
  if ( v9 < 0 && StringField )
  {
    if ( a4 )
      *a4 = 0;
    LocalFree(StringField);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180006e54  push    rbx
0x180006e56  push    rbp
0x180006e57  push    rsi
0x180006e58  push    rdi
0x180006e59  push    r12
0x180006e5b  push    r13
0x180006e5d  push    r14
0x180006e5f  push    r15
0x180006e61  sub     rsp, 58h
0x180006e65  xor     ebp, ebp
0x180006e67  mov     r15, r9
0x180006e6a  cmp     cs:hLibModule, rbp
0x180006e71  mov     r13d, r8d
0x180006e74  mov     rsi, rdx
0x180006e77  mov     [rsp+98h+var_68], ebp
0x180006e7b  mov     r12, rcx
0x180006e7e  mov     [rsp+98h+var_64], ebp
0x180006e82  lea     edi, [rbp+1]
0x180006e85  mov     [rsp+98h+var_60], ebp
0x180006e89  mov     ebx, ebp
0x180006e8b  jnz     short loc_180006EE6
0x180006e8d  call    ?CheckOSVersion@@YAHXZ; CheckOSVersion(void)
0x180006e92  test    eax, eax
0x180006e94  jz      short loc_180006ED0
0x180006e96  cmp     cs:?ctx@@3UADVCONTEXTW@@A, bp; ADVCONTEXTW ctx
0x180006e9d  jz      short loc_180006ED0
0x180006e9f  mov     r14d, ebp
0x180006ea2  mov     cs:dword_1800257F8, ebp
0x180006ea8  mov     edi, ebp
0x180006eaa  call    ?InitializeSetupAPI@@YAHXZ; InitializeSetupAPI(void)
0x180006eaf  test    eax, eax
0x180006eb1  jz      short loc_180006EC6
0x180006eb3  mov     rcx, r12; unsigned __int16 *
0x180006eb6  call    ?MySetupOpenInfFile@@YAJPEBG@Z; MySetupOpenInfFile(ushort const *)
0x180006ebb  mov     ebx, eax
0x180006ebd  test    eax, eax
0x180006ebf  jns     short loc_180006EF4
0x180006ec1  jmp     loc_180007169
0x180006ec6  mov     ebx, 80070057h
0x180006ecb  jmp     loc_180007169
0x180006ed0  mov     eax, cs:dword_1800257F8
0x180006ed6  mov     [rsp+98h+var_60], eax
0x180006eda  mov     cs:dword_1800257F8, edi
0x180006ee0  mov     [rsp+98h+var_64], edi
0x180006ee4  jmp     short loc_180006EF4
0x180006ee6  cmp     cs:InfHandle, rbp
0x180006eed  jnz     short loc_180006EF4
0x180006eef  call    ?MySetupOpenInfFile@@YAJPEBG@Z; MySetupOpenInfFile(ushort const *)
0x180006ef4  test    r15, r15
0x180006ef7  jz      short loc_180006EFC
0x180006ef9  mov     [r15], rbp
0x180006efc  mov     edi, 40h ; '@'
0x180006f01  mov     edx, 4000h; uBytes
0x180006f06  mov     ecx, edi; uFlags
0x180006f08  call    cs:__imp_LocalAlloc
0x180006f0e  mov     edx, 2000h; uBytes
0x180006f13  mov     ecx, edi; uFlags
0x180006f15  mov     r14, rax
0x180006f18  call    cs:__imp_LocalAlloc
0x180006f1e  mov     rdi, rax
0x180006f21  test    r14, r14
0x180006f24  jz      loc_180007144
0x180006f2a  test    rax, rax
0x180006f2d  jz      loc_180007144
0x180006f33  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180006f37  mov     rcx, rsi; Section
0x180006f3a  cmp     cs:dword_1800257F8, 1
0x180006f41  jnz     loc_18000707C
0x180006f47  mov     r9, r12; lpFileName
0x180006f4a  mov     r8d, 2000h; nSize
0x180006f50  mov     rdx, r14; lpReturnedString
0x180006f53  call    ?RO_GetPrivateProfileSection@@YAKPEBGPEAGK0@Z; RO_GetPrivateProfileSection(ushort const *,ushort *,ulong,ushort const *)
0x180006f58  mov     [rsp+98h+var_68], eax
0x180006f5c  cmp     eax, 1FFEh
0x180006f61  jnz     short loc_180006F92
0x180006f63  mov     rcx, cs:hWnd; hWnd
0x180006f6a  xor     ebp, ebp
0x180006f6c  mov     [rsp+98h+var_70], ebp; unsigned int
0x180006f70  xor     r9d, r9d; unsigned __int16 *
0x180006f73  mov     r8, rsi; unsigned __int16 *
0x180006f76  mov     dword ptr [rsp+98h+var_78], 10h; unsigned int
0x180006f7e  mov     edx, 45Dh; uID
0x180006f83  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x180006f88  mov     ebx, 80070057h
0x180006f8d  jmp     loc_180007159
0x180006f92  movzx   eax, word ptr [r14]
0x180006f96  mov     r9w, 3Bh ; ';'
0x180006f9b  xor     esi, esi
0x180006f9d  mov     rcx, r14; unsigned __int16 *
0x180006fa0  cmp     ax, r9w
0x180006fa4  jnz     short loc_180006FC8
0x180006fa6  mov     rax, rbp
0x180006fa9  inc     rax
0x180006fac  cmp     [rcx+rax*2], si
0x180006fb0  jnz     short loc_180006FA9
0x180006fb2  lea     rcx, [rcx+rax*2]
0x180006fb6  add     rcx, 2
0x180006fba  movzx   eax, word ptr [rcx]
0x180006fbd  cmp     ax, r9w
0x180006fc1  jz      short loc_180006FA6
0x180006fc3  mov     rdx, rcx
0x180006fc6  jmp     short loc_180006FCB
0x180006fc8  mov     rdx, r14
0x180006fcb  mov     r8d, esi; int
0x180006fce  cmp     r8d, r13d
0x180006fd1  jnb     short loc_180007022
0x180006fd3  mov     rax, rbp
0x180006fd6  inc     rax
0x180006fd9  cmp     [rdx+rax*2], si
0x180006fdd  jnz     short loc_180006FD6
0x180006fdf  lea     rcx, [rax+1]
0x180006fe3  lea     rcx, [rdx+rcx*2]
0x180006fe7  movzx   eax, word ptr [rcx]
0x180006fea  test    ax, ax
0x180006fed  jz      short loc_180007016
0x180006fef  cmp     ax, r9w
0x180006ff3  jnz     short loc_18000700E
0x180006ff5  mov     rax, rbp
0x180006ff8  inc     rax
0x180006ffb  cmp     [rcx+rax*2], si
0x180006fff  jnz     short loc_180006FF8
0x180007001  lea     rcx, [rcx+rax*2]
0x180007005  add     rcx, 2
0x180007009  movzx   eax, word ptr [rcx]
0x18000700c  jmp     short loc_180006FEF
0x18000700e  mov     rdx, rcx
0x180007011  inc     r8d
0x180007014  jmp     short loc_180006FCE
0x180007016  mov     ebx, 80070103h
0x18000701b  xor     ebp, ebp
0x18000701d  jmp     loc_180007159
0x180007022  test    ax, ax
0x180007025  jz      short loc_180007016
0x180007027  cmp     cs:hLibModule, rsi
0x18000702e  jz      short loc_180007037
0x180007030  mov     ebx, 8000FFFFh
0x180007035  jmp     short loc_18000701B
0x180007037  mov     r9, r12; unsigned __int16 *
0x18000703a  mov     rdx, rdi; unsigned __int16 *
0x18000703d  call    ?FormStrWithoutPlaceHolders@@YAKPEBGPEAGH0@Z; FormStrWithoutPlaceHolders(ushort const *,ushort *,int,ushort const *)
0x180007042  mov     r8d, 22h ; '"'; unsigned __int16
0x180007048  mov     [rsp+98h+var_58], rdi
0x18000704d  lea     rdx, dword_18001E82C; unsigned __int16 *
0x180007054  lea     rcx, [rsp+98h+var_58]; unsigned __int16 **
0x180007059  lea     r9d, [r8-21h]; int
0x18000705d  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x180007062  mov     rdi, rax
0x180007065  mov     rax, rbp
0x180007068  inc     rax
0x18000706b  cmp     [rdi+rax*2], si
0x18000706f  jnz     short loc_180007068
0x180007071  inc     eax
0x180007073  mov     [rsp+98h+var_68], eax
0x180007077  jmp     loc_180007102
0x18000707c  lea     rax, [rsp+98h+var_68]
0x180007081  mov     r9d, 1000h; unsigned int
0x180007087  mov     r8, rdi; unsigned __int16 *
0x18000708a  mov     [rsp+98h+var_78], rax; unsigned int *
0x18000708f  mov     edx, r13d; unsigned int
0x180007092  call    ?MySetupGetLineByIndex@@YAJPEBGKPEAGKPEAK@Z; MySetupGetLineByIndex(ushort const *,ulong,ushort *,ulong,ulong *)
0x180007097  mov     ebx, eax
0x180007099  test    eax, eax
0x18000709b  jns     short loc_180007100
0x18000709d  cmp     eax, 8007007Ah
0x1800070a2  jnz     loc_18000701B
0x1800070a8  mov     rcx, rdi; hMem
0x1800070ab  call    cs:__imp_LocalFree
0x1800070b1  mov     edx, [rsp+98h+var_68]
0x1800070b5  mov     ecx, 40h ; '@'; uFlags
0x1800070ba  add     rdx, rdx; uBytes
0x1800070bd  call    cs:__imp_LocalAlloc
0x1800070c3  mov     rdi, rax
0x1800070c6  test    rax, rax
0x1800070c9  jnz     short loc_1800070D5
0x1800070cb  call    cs:__imp_GetLastError
0x1800070d1  xor     ebp, ebp
0x1800070d3  jmp     short loc_18000714A
0x1800070d5  mov     r9d, [rsp+98h+var_68]; unsigned int
0x1800070da  lea     rax, [rsp+98h+var_68]
0x1800070df  mov     r8, rdi; unsigned __int16 *
0x1800070e2  mov     [rsp+98h+var_78], rax; unsigned int *
0x1800070e7  mov     edx, r13d; unsigned int
0x1800070ea  mov     rcx, rsi; Section
0x1800070ed  call    ?MySetupGetLineByIndex@@YAJPEBGKPEAGKPEAK@Z; MySetupGetLineByIndex(ushort const *,ulong,ushort *,ulong,ulong *)
0x1800070f2  xor     esi, esi
0x1800070f4  mov     ebx, eax
0x1800070f6  test    eax, eax
0x1800070f8  js      loc_18000701B
0x1800070fe  jmp     short loc_180007102
0x180007100  xor     esi, esi
0x180007102  test    r15, r15
0x180007105  jnz     short loc_180007115
0x180007107  mov     rcx, rdi; hMem
0x18000710a  call    cs:__imp_LocalFree
0x180007110  jmp     loc_18000701B
0x180007115  inc     rbp
0x180007118  cmp     [rdi+rbp*2], si
0x18000711c  jnz     short loc_180007115
0x18000711e  lea     rdx, ds:2[rbp*2]; uBytes
0x180007126  mov     r8d, 2; uFlags
0x18000712c  mov     rcx, rdi; hMem
0x18000712f  call    cs:__imp_LocalReAlloc
0x180007135  xor     ebp, ebp
0x180007137  mov     [r15], rax
0x18000713a  test    rax, rax
0x18000713d  jnz     short loc_180007159
0x18000713f  mov     [r15], rdi
0x180007142  jmp     short loc_180007159
0x180007144  call    cs:__imp_GetLastError
0x18000714a  mov     ebx, eax
0x18000714c  test    eax, eax
0x18000714e  jle     short loc_180007159
0x180007150  movzx   ebx, ax
0x180007153  or      ebx, 80070000h
0x180007159  cmp     [rsp+98h+var_64], ebp
0x18000715d  jz      short loc_180007169
0x18000715f  mov     eax, [rsp+98h+var_60]
0x180007163  mov     cs:dword_1800257F8, eax
0x180007169  mov     rcx, [rsp+98h+arg_20]
0x180007171  test    rcx, rcx
0x180007174  jz      short loc_18000717C
0x180007176  mov     eax, [rsp+98h+var_68]
0x18000717a  mov     [rcx], eax
0x18000717c  test    r14, r14
0x18000717f  jz      short loc_18000718A
0x180007181  mov     rcx, r14; hMem
0x180007184  call    cs:__imp_LocalFree
0x18000718a  test    ebx, ebx
0x18000718c  jns     short loc_1800071A4
0x18000718e  test    rdi, rdi
0x180007191  jz      short loc_1800071A4
0x180007193  test    r15, r15
0x180007196  jz      short loc_18000719B
0x180007198  mov     [r15], rbp
0x18000719b  mov     rcx, rdi; hMem
0x18000719e  call    cs:__imp_LocalFree
0x1800071a4  mov     eax, ebx
0x1800071a6  add     rsp, 58h
0x1800071aa  pop     r15
0x1800071ac  pop     r14
0x1800071ae  pop     r13
0x1800071b0  pop     r12
0x1800071b2  pop     rdi
0x1800071b3  pop     rsi
0x1800071b4  pop     rbp
0x1800071b5  pop     rbx
0x1800071b6  retn
```
