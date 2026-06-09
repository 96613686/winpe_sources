# CSoftDist::ActSetupAdvertise(int)

- ea: `0x1800b7700`
- end: `0x1800b7a37`
- name: `?ActSetupAdvertise@CSoftDist@@AEAAJH@Z`
- size: `823`
- prototype: `__int64 __fastcall(CSoftDist *__hidden this, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b7a58`

## callees

- `0x1800150e0`
- `0x180030880`
- `0x180044b84`
- `0x180058738`
- `0x18005cc10`
- `0x1800763a8`
- `0x1800b7700`
- `0x1800b8df0`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b78a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b78ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b7932`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b7977`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b79b8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b78a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b78ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b7932`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b7977`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b79b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b79f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b79f3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800b79e8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800b79e8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b7832`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b7832`

## string_xrefs

- `0x1800b77a3`: `Software\Microsoft\Active Setup\Installed Components`
- `0x1800b79e1`: `Precache`

## pseudocode

```c
__int64 __fastcall CSoftDist::ActSetupAdvertise(CSoftDist *this, int a2)
{
  const WCHAR *v3; // rcx
  signed int v4; // edi
  char *v5; // r14
  __int64 v6; // r15
  __int64 v7; // rax
  int v8; // edi
  char *v9; // rax
  unsigned __int64 v10; // rsi
  BOOL v11; // ebx
  int v12; // r9d
  __int64 v13; // rax
  LSTATUS v14; // esi
  const BYTE *v15; // rcx
  __int64 v16; // rax
  const BYTE *v17; // rcx
  __int64 v18; // rax
  const BYTE *v19; // rcx
  REGSAM samDesired; // [rsp+28h] [rbp-D8h]
  int lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+58h] [rbp-A8h]
  BYTE Data[16]; // [rsp+60h] [rbp-A0h] BYREF
  char v26; // [rsp+70h] [rbp-90h] BYREF

  v24 = a2;
  v3 = (const WCHAR *)*((_QWORD *)this + 2);
  hKey = 0;
  *(_QWORD *)Data = 0;
  v4 = Unicode2Ansi(v3);
  if ( v4 < 0 )
    return (unsigned int)v4;
  v5 = 0;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( *(_BYTE *)(*(_QWORD *)Data + v7) );
  v8 = v7 + 54;
  if ( (unsigned int)(v7 + 54) > 0x208 )
    v5 = (char *)operator new((unsigned int)v8);
  v9 = v5;
  if ( !v5 )
  {
    v5 = &v26;
    v8 = 520;
  }
  v10 = v8;
  v11 = v9 != 0;
  v4 = StringCchCopyA(v5, v8, "Software\\Microsoft\\Active Setup\\Installed Components");
  if ( v4 >= 0 )
  {
    v4 = StringCchCatA(v5, v10, "\\");
    if ( v4 >= 0 )
    {
      v4 = StringCchCatA(v5, v10, 0);
      if ( v4 >= 0 && !RegCreateKeyExA(HKEY_LOCAL_MACHINE, v5, 0, 0, 0, 0x2001Bu, 0, &hKey, 0) )
      {
        v12 = *((unsigned __int16 *)this + 13);
        lpSecurityAttributes = *((unsigned __int16 *)this + 14);
        samDesired = *((unsigned __int16 *)this + 15);
        *(_DWORD *)Data = 0;
        StringCchPrintfA(
          v5,
          v10,
          "%d,%d,%d,%d",
          v12,
          *((unsigned __int16 *)this + 12),
          samDesired,
          lpSecurityAttributes);
        v13 = -1;
        do
          ++v13;
        while ( v5[v13] );
        v14 = RegSetValueExA(hKey, "Version available", 0, 1u, (const BYTE *)v5, v13 + 1);
        if ( v24 || IsAbstractDifferent(hKey, *((char **)this + 9)) )
        {
          v14 = RegSetValueExA(hKey, "AdState", 0, 4u, Data, 4u);
          if ( v14 )
            goto LABEL_29;
          v15 = (const BYTE *)*((_QWORD *)this + 7);
          if ( v15 )
          {
            v16 = -1;
            do
              ++v16;
            while ( v15[v16] );
            v14 = RegSetValueExA(hKey, "Title available", 0, 1u, v15, v16 + 1);
            if ( v14 )
              goto LABEL_29;
          }
          v17 = (const BYTE *)*((_QWORD *)this + 9);
          if ( v17 )
          {
            v18 = -1;
            do
              ++v18;
            while ( v17[v18] );
            v14 = RegSetValueExA(hKey, "Abstract", 0, 1u, v17, v18 + 1);
            if ( v14 )
              goto LABEL_29;
          }
          v19 = (const BYTE *)*((_QWORD *)this + 10);
          if ( !v19 )
          {
LABEL_32:
            if ( v24 )
              RegDeleteValueA(hKey, "Precache");
            RegCloseKey(hKey);
            goto LABEL_35;
          }
          do
            ++v6;
          while ( v19[v6] );
          v14 = RegSetValueExA(hKey, "HREF available", 0, 1u, v19, v6 + 1);
        }
        if ( v14 )
        {
LABEL_29:
          if ( v14 > 0 )
            v4 = (unsigned __int16)v14 | 0x80070000;
          else
            v4 = v14;
          goto LABEL_32;
        }
        goto LABEL_32;
      }
    }
  }
LABEL_35:
  if ( v11 )
    operator delete(v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800b7700  push    rbp
0x1800b7702  push    rbx
0x1800b7703  push    rsi
0x1800b7704  push    rdi
0x1800b7705  push    r12
0x1800b7707  push    r13
0x1800b7709  push    r14
0x1800b770b  push    r15
0x1800b770d  lea     rbp, [rsp-198h]
0x1800b7715  sub     rsp, 298h
0x1800b771c  mov     rax, cs:__security_cookie
0x1800b7723  xor     rax, rsp
0x1800b7726  mov     [rbp+1D0h+var_50], rax
0x1800b772d  mov     [rsp+2D0h+var_278], edx
0x1800b7731  mov     r13, rcx
0x1800b7734  mov     rcx, [rcx+10h]; lpWideCharStr
0x1800b7738  lea     rdx, [rsp+2D0h+Data]
0x1800b773d  mov     [rsp+2D0h+hKey], 0
0x1800b7746  mov     qword ptr [rsp+2D0h+Data], 0
0x1800b774f  call    Unicode2Ansi
0x1800b7754  mov     r12, qword ptr [rsp+2D0h+Data]
0x1800b7759  mov     edi, eax
0x1800b775b  test    eax, eax
0x1800b775d  js      loc_1800B7A05
0x1800b7763  xor     r14d, r14d
0x1800b7766  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800b776a  mov     rax, r15
0x1800b776d  inc     rax
0x1800b7770  cmp     [r12+rax], r14b
0x1800b7774  jnz     short loc_1800B776D
0x1800b7776  lea     edi, [rax+36h]
0x1800b7779  mov     ebx, 208h
0x1800b777e  cmp     edi, ebx
0x1800b7780  jbe     short loc_1800B778C
0x1800b7782  mov     ecx, edi; Size
0x1800b7784  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b7789  mov     r14, rax
0x1800b778c  mov     rax, r14
0x1800b778f  test    r14, r14
0x1800b7792  jnz     short loc_1800B779B
0x1800b7794  lea     r14, [rsp+2D0h+var_260]
0x1800b7799  mov     edi, ebx
0x1800b779b  xor     ebx, ebx
0x1800b779d  movsxd  rsi, edi
0x1800b77a0  test    rax, rax
0x1800b77a3  lea     r8, aSoftwareMicros_54; "Software\\Microsoft\\Active Setup\\Inst"...
0x1800b77aa  mov     rdx, rsi; unsigned __int64
0x1800b77ad  mov     rcx, r14; char *
0x1800b77b0  setnz   bl
0x1800b77b3  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800b77b8  mov     edi, eax
0x1800b77ba  test    eax, eax
0x1800b77bc  js      loc_1800B79F9
0x1800b77c2  lea     r8, asc_18012AFD0; "\\"
0x1800b77c9  mov     rdx, rsi; unsigned __int64
0x1800b77cc  mov     rcx, r14; char *
0x1800b77cf  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800b77d4  mov     edi, eax
0x1800b77d6  test    eax, eax
0x1800b77d8  js      loc_1800B79F9
0x1800b77de  mov     r8, r12; char *
0x1800b77e1  mov     rdx, rsi; unsigned __int64
0x1800b77e4  mov     rcx, r14; char *
0x1800b77e7  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800b77ec  mov     edi, eax
0x1800b77ee  test    eax, eax
0x1800b77f0  js      loc_1800B79F9
0x1800b77f6  mov     [rsp+2D0h+lpdwDisposition], 0; lpdwDisposition
0x1800b77ff  lea     rax, [rsp+2D0h+hKey]
0x1800b7804  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800b7809  xor     r9d, r9d; lpClass
0x1800b780c  mov     [rsp+2D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800b7815  xor     r8d, r8d; Reserved
0x1800b7818  mov     [rsp+2D0h+samDesired], 2001Bh; samDesired
0x1800b7820  mov     rdx, r14; lpSubKey
0x1800b7823  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b782a  mov     [rsp+2D0h+dwOptions], 0; dwOptions
0x1800b7832  call    cs:__imp_RegCreateKeyExA
0x1800b7838  test    eax, eax
0x1800b783a  jnz     loc_1800B79F9
0x1800b7840  movzx   ecx, word ptr [r13+1Ch]
0x1800b7845  mov     rdx, rsi; unsigned __int64
0x1800b7848  movzx   r8d, word ptr [r13+1Eh]
0x1800b784d  movzx   r9d, word ptr [r13+1Ah]
0x1800b7852  mov     dword ptr [rsp+2D0h+lpSecurityAttributes], ecx
0x1800b7856  mov     rcx, r14; char *
0x1800b7859  mov     [rsp+2D0h+samDesired], r8d
0x1800b785e  lea     r8, aDDDD_0; "%d,%d,%d,%d"
0x1800b7865  mov     dword ptr [rsp+2D0h+Data], eax
0x1800b7869  movzx   eax, word ptr [r13+18h]
0x1800b786e  mov     [rsp+2D0h+dwOptions], eax
0x1800b7872  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800b7877  mov     rax, r15
0x1800b787a  inc     rax
0x1800b787d  cmp     byte ptr [r14+rax], 0
0x1800b7882  jnz     short loc_1800B787A
0x1800b7884  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800b7889  lea     rdx, aVersionAvailab; "Version available"
0x1800b7890  inc     eax
0x1800b7892  mov     r9d, 1; dwType
0x1800b7898  mov     [rsp+2D0h+samDesired], eax; cbData
0x1800b789c  xor     r8d, r8d; Reserved
0x1800b789f  mov     qword ptr [rsp+2D0h+dwOptions], r14; lpData
0x1800b78a4  call    cs:__imp_RegSetValueExA
0x1800b78aa  cmp     [rsp+2D0h+var_278], 0
0x1800b78af  mov     esi, eax
0x1800b78b1  jnz     short loc_1800B78C9
0x1800b78b3  mov     rdx, [r13+48h]; char *
0x1800b78b7  mov     rcx, [rsp+2D0h+hKey]; HKEY
0x1800b78bc  call    ?IsAbstractDifferent@@YAHPEAUHKEY__@@PEAD@Z; IsAbstractDifferent(HKEY__ *,char *)
0x1800b78c1  test    eax, eax
0x1800b78c3  jz      loc_1800B79C0
0x1800b78c9  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800b78ce  lea     rax, [rsp+2D0h+Data]
0x1800b78d3  mov     r9d, 4; dwType
0x1800b78d9  lea     rdx, aAdstate; "AdState"
0x1800b78e0  mov     [rsp+2D0h+samDesired], r9d; cbData
0x1800b78e5  xor     r8d, r8d; Reserved
0x1800b78e8  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x1800b78ed  call    cs:__imp_RegSetValueExA
0x1800b78f3  mov     esi, eax
0x1800b78f5  test    eax, eax
0x1800b78f7  jnz     loc_1800B79C4
0x1800b78fd  mov     rcx, [r13+38h]
0x1800b7901  test    rcx, rcx
0x1800b7904  jz      short loc_1800B7942
0x1800b7906  mov     rax, r15
0x1800b7909  inc     rax
0x1800b790c  cmp     byte ptr [rcx+rax], 0
0x1800b7910  jnz     short loc_1800B7909
0x1800b7912  inc     eax
0x1800b7914  lea     rdx, aTitleAvailable; "Title available"
0x1800b791b  mov     [rsp+2D0h+samDesired], eax; cbData
0x1800b791f  mov     r9d, 1; dwType
0x1800b7925  mov     qword ptr [rsp+2D0h+dwOptions], rcx; lpData
0x1800b792a  xor     r8d, r8d; Reserved
0x1800b792d  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800b7932  call    cs:__imp_RegSetValueExA
0x1800b7938  mov     esi, eax
0x1800b793a  test    eax, eax
0x1800b793c  jnz     loc_1800B79C4
0x1800b7942  mov     rcx, [r13+48h]
0x1800b7946  test    rcx, rcx
0x1800b7949  jz      short loc_1800B7983
0x1800b794b  mov     rax, r15
0x1800b794e  inc     rax
0x1800b7951  cmp     byte ptr [rcx+rax], 0
0x1800b7955  jnz     short loc_1800B794E
0x1800b7957  inc     eax
0x1800b7959  lea     rdx, aAbstract_0; "Abstract"
0x1800b7960  mov     [rsp+2D0h+samDesired], eax; cbData
0x1800b7964  mov     r9d, 1; dwType
0x1800b796a  mov     qword ptr [rsp+2D0h+dwOptions], rcx; lpData
0x1800b796f  xor     r8d, r8d; Reserved
0x1800b7972  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800b7977  call    cs:__imp_RegSetValueExA
0x1800b797d  mov     esi, eax
0x1800b797f  test    eax, eax
0x1800b7981  jnz     short loc_1800B79C4
0x1800b7983  mov     rcx, [r13+50h]
0x1800b7987  test    rcx, rcx
0x1800b798a  jz      short loc_1800B79D5
0x1800b798c  inc     r15
0x1800b798f  cmp     byte ptr [rcx+r15], 0
0x1800b7994  jnz     short loc_1800B798C
0x1800b7996  lea     eax, [r15+1]
0x1800b799a  mov     r9d, 1; dwType
0x1800b79a0  mov     [rsp+2D0h+samDesired], eax; cbData
0x1800b79a4  lea     rdx, aHrefAvailable; "HREF available"
0x1800b79ab  mov     qword ptr [rsp+2D0h+dwOptions], rcx; lpData
0x1800b79b0  xor     r8d, r8d; Reserved
0x1800b79b3  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800b79b8  call    cs:__imp_RegSetValueExA
0x1800b79be  mov     esi, eax
0x1800b79c0  test    esi, esi
0x1800b79c2  jz      short loc_1800B79D5
0x1800b79c4  test    esi, esi
0x1800b79c6  jg      short loc_1800B79CC
0x1800b79c8  mov     edi, esi
0x1800b79ca  jmp     short loc_1800B79D5
0x1800b79cc  movzx   edi, si
0x1800b79cf  or      edi, 80070000h
0x1800b79d5  cmp     [rsp+2D0h+var_278], 0
0x1800b79da  jz      short loc_1800B79EE
0x1800b79dc  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800b79e1  lea     rdx, aPrecache_0; "Precache"
0x1800b79e8  call    cs:__imp_RegDeleteValueA
0x1800b79ee  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800b79f3  call    cs:__imp_RegCloseKey
0x1800b79f9  test    ebx, ebx
0x1800b79fb  jz      short loc_1800B7A05
0x1800b79fd  mov     rcx, r14; void *
0x1800b7a00  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b7a05  test    r12, r12
0x1800b7a08  jz      short loc_1800B7A12
0x1800b7a0a  mov     rcx, r12; void *
0x1800b7a0d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b7a12  mov     eax, edi
0x1800b7a14  mov     rcx, [rbp+1D0h+var_50]
0x1800b7a1b  xor     rcx, rsp; StackCookie
0x1800b7a1e  call    __security_check_cookie
0x1800b7a23  add     rsp, 298h
0x1800b7a2a  pop     r15
0x1800b7a2c  pop     r14
0x1800b7a2e  pop     r13
0x1800b7a30  pop     r12
0x1800b7a32  pop     rdi
0x1800b7a33  pop     rsi
0x1800b7a34  pop     rbx
0x1800b7a35  pop     rbp
0x1800b7a36  retn
```
