# DwRemoveLinkageKeys

- ea: `0x18009408c`
- end: `0x1800943bf`
- name: `DwRemoveLinkageKeys`
- size: `819`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003ee98`
- `0x1800921fc`
- `0x1800924d0`
- `0x1800927a4`
- `0x180092950`
- `0x180092d2c`

## callees

- `0x180092ed8`
- `0x180093380`
- `0x18009408c`
- `0x1800ad750`
- `0x1800e71ee`
- `0x1800e7206`
- `0x1800e7260`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800942e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800942e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094131`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094131`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094371`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094371`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009435f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009435f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800942d4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800942d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009437f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009438d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009437f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009438d`

## string_xrefs

- `0x180094167`: `DwRemoveLinkageKeys: RegOpenKeyExW: failed %d`
- `0x180094143`: `DwRemoveLinkageKeys: RegOpenKeyExW: failed %d`
- `0x1800941f2`: `DwRemoveLinkageKeys: RegQueryValueWithAllocW: failed %d`
- `0x1800941d3`: `DwRemoveLinkageKeys: RegQueryValueWithAllocW: failed %d`

## pseudocode

```c
__int64 __fastcall DwRemoveLinkageKeys(
        char *a1,
        const WCHAR *a2,
        const WCHAR *a3,
        __int64 a4,
        _DWORD *a5,
        unsigned int a6)
{
  void *v8; // rdi
  BYTE *v9; // r14
  __int64 v10; // r13
  LSTATUS v11; // eax
  unsigned int v12; // r8d
  unsigned int v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // r15d
  _WORD *v16; // rsi
  __int64 v17; // r12
  unsigned __int64 v18; // rax
  char *v19; // rcx
  char *v20; // rax
  char *v21; // rcx
  int v22; // edx
  int v23; // r8d
  unsigned int v24; // ebx
  SIZE_T v25; // rdx
  BYTE *v26; // rax
  DWORD LastError; // eax
  const WCHAR *v28; // rdx
  DWORD cbData; // [rsp+28h] [rbp-D8h]
  SIZE_T uBytes; // [rsp+40h] [rbp-C0h] BYREF
  void *Src; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v34; // [rsp+58h] [rbp-A8h] BYREF
  char *v35; // [rsp+60h] [rbp-A0h]
  __int64 v36; // [rsp+68h] [rbp-98h]
  _DWORD *v37; // [rsp+70h] [rbp-90h]
  LPCWSTR lpValueName; // [rsp+78h] [rbp-88h]
  int v39; // [rsp+80h] [rbp-80h] BYREF
  char v40[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  lpValueName = a3;
  v35 = a1;
  v37 = a5;
  Src = 0;
  hKey = 0;
  v8 = 0;
  LODWORD(uBytes) = 0;
  v9 = 0;
  v34 = 0;
  v39 = 0;
  v10 = a4;
  v36 = a4;
  memset_0(v40, 0, sizeof(v40));
  *a5 = 0;
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 3u, &hKey);
  v13 = v11;
  if ( v11 )
  {
    TraceIt(a6, "DwRemoveLinkageKeys: RegOpenKeyExW: failed %d", v11);
    if ( qword_18010ED20 )
    {
      LOWORD(v39) = 0;
      FormatRRASErrorString(&v39, L"DwRemoveLinkageKeys: RegOpenKeyExW: failed %d", v13);
      ((void (__fastcall *)(__int64, __int64, int *))gRegHelpTemplateFunc)(gRegHelpEtwContext, qword_18010ED20, &v39);
    }
  }
  else
  {
    v14 = RegQueryValueWithAllocW(hKey, a3, v12, (unsigned __int8 **)&Src, &v34, (unsigned int *)&uBytes, a6);
    v13 = v14;
    if ( v14 )
    {
      TraceIt(a6, "DwRemoveLinkageKeys: RegQueryValueWithAllocW: failed %d", v14);
      if ( qword_18010ED20 )
      {
        LOWORD(v39) = 0;
        FormatRRASErrorString(&v39, L"DwRemoveLinkageKeys: RegQueryValueWithAllocW: failed %d", v13);
        ((void (__fastcall *)(__int64, __int64, int *))gRegHelpTemplateFunc)(gRegHelpEtwContext, qword_18010ED20, &v39);
      }
      v8 = Src;
    }
    else
    {
      v8 = Src;
      v15 = 0;
      v16 = Src;
      if ( *(_WORD *)Src )
      {
        while ( 1 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v16[v17] );
          v18 = -1;
          do
            ++v18;
          while ( *(_WORD *)(v10 + 2 * v18) );
          if ( (unsigned int)v17 >= v18 )
          {
            v19 = (char *)&v16[v18];
            if ( *(_WORD *)v19 == 123 )
            {
              v20 = v35;
              v21 = (char *)(v19 - v35);
              do
              {
                v22 = *(unsigned __int16 *)&v21[(_QWORD)v20];
                v23 = *(unsigned __int16 *)v20 - v22;
                if ( v23 )
                  break;
                v20 += 2;
              }
              while ( v22 );
              if ( !v23 )
                break;
            }
          }
          v15 += v17 + 1;
          v16 += (unsigned int)v17 + 1;
          if ( !*v16 )
            goto LABEL_29;
          v10 = v36;
        }
        v24 = uBytes;
        v25 = (unsigned int)uBytes;
        *v37 = 1;
        v26 = (BYTE *)LocalAlloc(0x40u, v25);
        v9 = v26;
        if ( v26 )
        {
          if ( v15 )
            memcpy_0(v26, v8, 2LL * v15);
          if ( (v24 >> 1) - v15 - (_DWORD)v17 != 1 )
            memcpy_0(&v9[2 * v15], &v16[(unsigned int)v17 + 1], 2LL * ((v24 >> 1) - v15 - (unsigned int)v17 - 1));
          v28 = lpValueName;
          cbData = v24 - 2 * v17 - 2;
          *(_WORD *)&v9[2 * ((unsigned __int64)cbData >> 1) - 2] = 0;
          LastError = RegSetValueExW(hKey, v28, 0, 7u, v9, cbData);
        }
        else
        {
          LastError = GetLastError();
        }
        v13 = LastError;
      }
    }
  }
LABEL_29:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v8 )
    LocalFree(v8);
  if ( v9 )
    LocalFree(v9);
  return v13;
}

```

## disassembly

```asm
0x18009408c  mov     [rsp-8+arg_0], rbx
0x180094091  push    rbp
0x180094092  push    rsi
0x180094093  push    rdi
0x180094094  push    r12
0x180094096  push    r13
0x180094098  push    r14
0x18009409a  push    r15
0x18009409c  lea     rbp, [rsp-790h]
0x1800940a4  sub     rsp, 890h
0x1800940ab  mov     rax, cs:__security_cookie
0x1800940b2  xor     rax, rsp
0x1800940b5  mov     [rbp+7C0h+var_40], rax
0x1800940bc  mov     rsi, [rbp+7C0h+arg_20]
0x1800940c3  xor     r12d, r12d
0x1800940c6  mov     r15, r8
0x1800940c9  mov     [rsp+8C0h+lpValueName], r8
0x1800940ce  mov     rbx, rdx
0x1800940d1  mov     [rsp+8C0h+var_860], rcx
0x1800940d6  xor     edx, edx; Val
0x1800940d8  mov     [rsp+8C0h+var_850], rsi
0x1800940dd  mov     r8d, 7FCh; Size
0x1800940e3  mov     [rsp+8C0h+Src], r12
0x1800940e8  lea     rcx, [rbp+7C0h+var_83C]; void *
0x1800940ec  mov     [rsp+8C0h+hKey], r12
0x1800940f1  mov     edi, r12d
0x1800940f4  mov     dword ptr [rsp+8C0h+uBytes], r12d
0x1800940f9  mov     r14d, r12d
0x1800940fc  mov     [rsp+8C0h+var_868], r12d
0x180094101  mov     [rbp+7C0h+var_840], r12d
0x180094105  mov     r13, r9
0x180094108  mov     [rsp+8C0h+var_858], r9
0x18009410d  call    memset_0
0x180094112  lea     rax, [rsp+8C0h+hKey]
0x180094117  mov     [rsi], r12d
0x18009411a  lea     r9d, [r12+3]; samDesired
0x18009411f  mov     [rsp+8C0h+phkResult], rax; phkResult
0x180094124  xor     r8d, r8d; ulOptions
0x180094127  mov     rdx, rbx; lpSubKey
0x18009412a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180094131  call    cs:__imp_RegOpenKeyExW
0x180094137  mov     ebx, eax
0x180094139  test    eax, eax
0x18009413b  jz      short loc_18009419A
0x18009413d  mov     ecx, [rbp+7C0h+arg_28]; unsigned int
0x180094143  lea     rdx, aDwremovelinkag; "DwRemoveLinkageKeys: RegOpenKeyExW: fai"...
0x18009414a  mov     r8d, eax
0x18009414d  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x180094152  cmp     cs:qword_18010ED20, r12
0x180094159  jz      loc_180094367
0x18009415f  mov     r8d, ebx
0x180094162  mov     word ptr [rbp+7C0h+var_840], r12w
0x180094167  lea     rdx, aDwremovelinkag_1; "DwRemoveLinkageKeys: RegOpenKeyExW: fai"...
0x18009416e  lea     rcx, [rbp+7C0h+var_840]
0x180094172  call    FormatRRASErrorString
0x180094177  mov     rdx, cs:qword_18010ED20
0x18009417e  lea     r8, [rbp+7C0h+var_840]
0x180094182  mov     rcx, cs:gRegHelpEtwContext
0x180094189  mov     rax, cs:gRegHelpTemplateFunc
0x180094190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094195  jmp     loc_180094367
0x18009419a  mov     edi, [rbp+7C0h+arg_28]
0x1800941a0  lea     rax, [rsp+8C0h+uBytes]
0x1800941a5  mov     rcx, [rsp+8C0h+hKey]; hKey
0x1800941aa  lea     r9, [rsp+8C0h+Src]; unsigned __int8 **
0x1800941af  mov     [rsp+8C0h+var_890], edi; unsigned int
0x1800941b3  mov     rdx, r15; lpValueName
0x1800941b6  mov     qword ptr [rsp+8C0h+cbData], rax; unsigned int *
0x1800941bb  lea     rax, [rsp+8C0h+var_868]
0x1800941c0  mov     [rsp+8C0h+phkResult], rax; unsigned int *
0x1800941c5  call    ?RegQueryValueWithAllocW@@YAKPEAUHKEY__@@PEAGKPEAPEAEPEAK3K@Z; RegQueryValueWithAllocW(HKEY__ *,ushort *,ulong,uchar * *,ulong *,ulong *,ulong)
0x1800941ca  mov     ebx, eax
0x1800941cc  test    eax, eax
0x1800941ce  jz      short loc_18009422A
0x1800941d0  mov     r8d, eax
0x1800941d3  lea     rdx, aDwremovelinkag_0; "DwRemoveLinkageKeys: RegQueryValueWithA"...
0x1800941da  mov     ecx, edi; unsigned int
0x1800941dc  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x1800941e1  cmp     cs:qword_18010ED20, r12
0x1800941e8  jz      short loc_180094220
0x1800941ea  mov     r8d, ebx
0x1800941ed  mov     word ptr [rbp+7C0h+var_840], r12w
0x1800941f2  lea     rdx, aDwremovelinkag_2; "DwRemoveLinkageKeys: RegQueryValueWithA"...
0x1800941f9  lea     rcx, [rbp+7C0h+var_840]
0x1800941fd  call    FormatRRASErrorString
0x180094202  mov     rdx, cs:qword_18010ED20
0x180094209  lea     r8, [rbp+7C0h+var_840]
0x18009420d  mov     rcx, cs:gRegHelpEtwContext
0x180094214  mov     rax, cs:gRegHelpTemplateFunc
0x18009421b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094220  mov     rdi, [rsp+8C0h+Src]
0x180094225  jmp     loc_180094367
0x18009422a  mov     rdi, [rsp+8C0h+Src]
0x18009422f  mov     r15d, r12d
0x180094232  mov     rsi, rdi
0x180094235  cmp     [rdi], r12w
0x180094239  jz      loc_180094367
0x18009423f  mov     r9, [rsp+8C0h+var_860]
0x180094244  or      r11, 0FFFFFFFFFFFFFFFFh
0x180094248  mov     r12, r11
0x18009424b  xor     r10d, r10d
0x18009424e  inc     r12
0x180094251  cmp     [rsi+r12*2], r10w
0x180094256  jnz     short loc_18009424E
0x180094258  mov     rax, r11
0x18009425b  inc     rax
0x18009425e  cmp     [r13+rax*2+0], r10w
0x180094264  jnz     short loc_18009425B
0x180094266  mov     r13d, r12d
0x180094269  cmp     r13, rax
0x18009426c  jb      short loc_18009429C
0x18009426e  lea     rcx, [rsi+rax*2]
0x180094272  mov     eax, 7Bh ; '{'
0x180094277  cmp     ax, [rcx]
0x18009427a  jnz     short loc_18009429C
0x18009427c  mov     rax, r9
0x18009427f  sub     rcx, r9
0x180094282  movzx   r8d, word ptr [rax]
0x180094286  movzx   edx, word ptr [rax+rcx]
0x18009428a  sub     r8d, edx
0x18009428d  jnz     short loc_180094297
0x18009428f  add     rax, 2
0x180094293  test    edx, edx
0x180094295  jnz     short loc_180094282
0x180094297  test    r8d, r8d
0x18009429a  jz      short loc_1800942BE
0x18009429c  inc     r12d
0x18009429f  lea     rsi, [rsi+r13*2]
0x1800942a3  add     r15d, r12d
0x1800942a6  add     rsi, 2
0x1800942aa  xor     r12d, r12d
0x1800942ad  cmp     [rsi], r12w
0x1800942b1  jz      loc_180094367
0x1800942b7  mov     r13, [rsp+8C0h+var_858]
0x1800942bc  jmp     short loc_180094248
0x1800942be  mov     rax, [rsp+8C0h+var_850]
0x1800942c3  mov     ecx, 40h ; '@'; uFlags
0x1800942c8  mov     ebx, dword ptr [rsp+8C0h+uBytes]
0x1800942cc  mov     edx, ebx; uBytes
0x1800942ce  mov     dword ptr [rax], 1
0x1800942d4  call    cs:__imp_LocalAlloc
0x1800942da  mov     r14, rax
0x1800942dd  test    rax, rax
0x1800942e0  jnz     short loc_1800942EA
0x1800942e2  call    cs:__imp_GetLastError
0x1800942e8  jmp     short loc_180094365
0x1800942ea  test    r15d, r15d
0x1800942ed  jz      short loc_180094300
0x1800942ef  mov     r8d, r15d
0x1800942f2  mov     rdx, rdi; Src
0x1800942f5  add     r8, r8; Size
0x1800942f8  mov     rcx, r14; void *
0x1800942fb  call    memcpy_0
0x180094300  mov     eax, ebx
0x180094302  shr     eax, 1
0x180094304  sub     eax, r15d
0x180094307  sub     eax, r12d
0x18009430a  sub     eax, 1
0x18009430d  jz      short loc_180094329
0x18009430f  mov     r8d, eax
0x180094312  lea     rdx, [r13+1]
0x180094316  mov     eax, r15d
0x180094319  lea     rdx, [rsi+rdx*2]; Src
0x18009431d  add     r8, r8; Size
0x180094320  lea     rcx, [r14+rax*2]; void *
0x180094324  call    memcpy_0
0x180094329  mov     rdx, [rsp+8C0h+lpValueName]; lpValueName
0x18009432e  lea     eax, [r12+r12]
0x180094332  xor     r12d, r12d
0x180094335  sub     ebx, eax
0x180094337  sub     ebx, 2
0x18009433a  mov     r8d, ebx
0x18009433d  mov     [rsp+8C0h+cbData], r8d; cbData
0x180094342  xor     r8d, r8d; Reserved
0x180094345  mov     ecx, ebx
0x180094347  lea     r9d, [r12+7]; dwType
0x18009434c  shr     rcx, 1
0x18009434f  mov     [rsp+8C0h+phkResult], r14; lpData
0x180094354  mov     [r14+rcx*2-2], r12w
0x18009435a  mov     rcx, [rsp+8C0h+hKey]; hKey
0x18009435f  call    cs:__imp_RegSetValueExW
0x180094365  mov     ebx, eax
0x180094367  mov     rcx, [rsp+8C0h+hKey]; hKey
0x18009436c  test    rcx, rcx
0x18009436f  jz      short loc_180094377
0x180094371  call    cs:__imp_RegCloseKey
0x180094377  test    rdi, rdi
0x18009437a  jz      short loc_180094385
0x18009437c  mov     rcx, rdi; hMem
0x18009437f  call    cs:__imp_LocalFree
0x180094385  test    r14, r14
0x180094388  jz      short loc_180094393
0x18009438a  mov     rcx, r14; hMem
0x18009438d  call    cs:__imp_LocalFree
0x180094393  mov     eax, ebx
0x180094395  mov     rcx, [rbp+7C0h+var_40]
0x18009439c  xor     rcx, rsp; StackCookie
0x18009439f  call    __security_check_cookie
0x1800943a4  mov     rbx, [rsp+8C0h+arg_0]
0x1800943ac  add     rsp, 890h
0x1800943b3  pop     r15
0x1800943b5  pop     r14
0x1800943b7  pop     r13
0x1800943b9  pop     r12
0x1800943bb  pop     rdi
0x1800943bc  pop     rsi
0x1800943bd  pop     rbp
0x1800943be  retn
```
