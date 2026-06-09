# V4ConnectionFiles::CreateV4ConnectionFileStruct(HKEY__ *,V4ConnectionFiles * *)

- ea: `0x180047790`
- end: `0x180047adf`
- name: `?CreateV4ConnectionFileStruct@V4ConnectionFiles@@SAJPEAUHKEY__@@PEAPEAU1@@Z`
- size: `847`
- prototype: `__int64 __fastcall(HKEY hkey, struct V4ConnectionFiles **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18004723c`

## callees

- `0x180033504`
- `0x180035b04`
- `0x180047724`
- `0x180047790`
- `0x1800487e0`
- `0x180048d98`
- `0x1800491dc`
- `0x1800491e8`
- `0x180052350`
- `0x180056ba0`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x1800479a1`
- `ADVAPI32!RegEnumValueW` at `0x1800479a1`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800478cd`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800478cd`

## pseudocode

```c
__int64 __fastcall V4ConnectionFiles::CreateV4ConnectionFileStruct(HKEY hkey, struct V4ConnectionFiles **a2)
{
  DWORD v2; // esi
  HKEY v4; // rdi
  V4ConnectionFiles *v6; // rax
  struct V4ConnectionFiles *v7; // rbx
  int v8; // r13d
  int ConnectionSpecificDirectory; // ebx
  HRESULT v10; // eax
  WCHAR *v11; // r14
  BYTE *v12; // r15
  LSTATUS v13; // eax
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rax
  LSTATUS v16; // eax
  unsigned int v17; // edx
  WCHAR *v18; // rcx
  int v19; // eax
  int v20; // r8d
  __int64 v21; // rbx
  __int64 v22; // rdi
  unsigned __int64 v23; // rax
  wchar_t *v24; // rax
  HRESULT v25; // eax
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cValues; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbData; // [rsp+6Ch] [rbp-94h] BYREF
  size_t pcchLength; // [rsp+70h] [rbp-90h] BYREF
  size_t cchDest; // [rsp+78h] [rbp-88h]
  HKEY v32; // [rsp+80h] [rbp-80h]
  wchar_t pszDest[264]; // [rsp+90h] [rbp-70h] BYREF

  v2 = 0;
  v32 = hkey;
  v4 = hkey;
  if ( !a2 )
    return 2147942487LL;
  v6 = (V4ConnectionFiles *)operator new(0x68u, (const struct std::nothrow_t *)byte_18007F401);
  v7 = v6;
  if ( v6 )
  {
    V4ConnectionFiles::ResetV4ConnectionFileStruct(v6, 0);
    *a2 = v7;
    memset_0(pszDest, 0, 0x208u);
    pcchLength = 0;
    v8 = 0;
    ConnectionSpecificDirectory = GetConnectionSpecificDirectory(v4, (BYTE *)pszDest, 0x104u);
    if ( ConnectionSpecificDirectory >= 0 )
    {
      ConnectionSpecificDirectory = StringCchCatW(pszDest, 0x104u, L"\\");
      if ( ConnectionSpecificDirectory >= 0 )
      {
        v10 = StringLengthWorkerW(pszDest, 0x104u, &pcchLength);
        v8 = pcchLength;
        ConnectionSpecificDirectory = v10;
        if ( v10 < 0 )
          v8 = 0;
      }
    }
    cValues = 0;
    v11 = 0;
    cbMaxValueNameLen = 0;
    v12 = 0;
    cbMaxValueLen = 0;
    if ( ConnectionSpecificDirectory >= 0 )
    {
      v13 = RegQueryInfoKeyW(v4, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
      if ( v13 )
      {
        if ( v13 > 0 )
          ConnectionSpecificDirectory = (unsigned __int16)v13 | 0x80070000;
        else
          ConnectionSpecificDirectory = v13;
      }
      else
      {
        v14 = 2LL * (cbMaxValueNameLen + 1);
        if ( !is_mul_ok(cbMaxValueNameLen + 1, 2u) )
          v14 = -1;
        v11 = (WCHAR *)operator new(v14, (const struct std::nothrow_t *)byte_18007F401);
        v15 = 2 * ((unsigned __int64)cbMaxValueLen >> 1);
        if ( !is_mul_ok((unsigned __int64)cbMaxValueLen >> 1, 2u) )
          v15 = -1;
        v12 = (BYTE *)operator new(v15, (const struct std::nothrow_t *)byte_18007F401);
        if ( !v12 || !v11 )
          ConnectionSpecificDirectory = -2147024882;
      }
      while ( ConnectionSpecificDirectory >= 0 )
      {
LABEL_20:
        if ( v2 >= cValues )
          break;
        LODWORD(pcchLength) = cbMaxValueNameLen + 1;
        cbData = cbMaxValueLen;
        v16 = RegEnumValueW(v4, v2, v11, (LPDWORD)&pcchLength, 0, 0, v12, &cbData);
        if ( v16 )
        {
          if ( v16 > 0 )
            ConnectionSpecificDirectory = (unsigned __int16)v16 | 0x80070000;
          else
            ConnectionSpecificDirectory = v16;
        }
        else
        {
          *(_WORD *)&v12[2 * ((unsigned __int64)cbMaxValueLen >> 1) - 2] = 0;
          v11[cbMaxValueNameLen] = 0;
        }
        if ( ConnectionSpecificDirectory >= 0 )
        {
          v17 = 0;
          while ( 1 )
          {
            v18 = v11;
            do
            {
              v19 = *(WCHAR *)((char *)v18 + *((_QWORD *)&V4ConnectionFiles::s_connectionFiles + 2 * v17) - (_QWORD)v11);
              v20 = *v18 - v19;
              if ( v20 )
                break;
              ++v18;
            }
            while ( v19 );
            if ( !v20 )
              break;
            if ( ++v17 >= 0xD )
            {
              ++v2;
              goto LABEL_20;
            }
          }
          v21 = (__int64)*a2;
          cchDest = v8 + (cbData >> 1);
          v22 = *((_QWORD *)&V4ConnectionFiles::s_connectionFiles + 2 * v17 + 1);
          v23 = 2 * cchDest;
          if ( !is_mul_ok(cchDest, 2u) )
            v23 = -1;
          v24 = (wchar_t *)operator new(v23, (const struct std::nothrow_t *)byte_18007F401);
          *(_QWORD *)(v22 + v21) = v24;
          if ( !v24 )
          {
            ConnectionSpecificDirectory = -2147024882;
            break;
          }
          v25 = StringCchPrintfW(v24, cchDest, L"%ws%ws", pszDest, v12);
          v4 = v32;
          ConnectionSpecificDirectory = v25;
        }
        ++v2;
      }
    }
    operator delete(v12);
    operator delete(v11);
    return (unsigned int)ConnectionSpecificDirectory;
  }
  else
  {
    *a2 = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180047790  mov     [rsp-8+arg_10], rbx
0x180047795  push    rbp
0x180047796  push    rsi
0x180047797  push    rdi
0x180047798  push    r12
0x18004779a  push    r13
0x18004779c  push    r14
0x18004779e  push    r15
0x1800477a0  lea     rbp, [rsp-1B0h]
0x1800477a8  sub     rsp, 2B0h
0x1800477af  mov     rax, cs:__security_cookie
0x1800477b6  xor     rax, rsp
0x1800477b9  mov     [rbp+1E0h+var_40], rax
0x1800477c0  xor     esi, esi
0x1800477c2  mov     [rbp+1E0h+var_260], rcx
0x1800477c6  mov     r12, rdx
0x1800477c9  mov     rdi, rcx
0x1800477cc  test    rdx, rdx
0x1800477cf  jnz     short loc_1800477DB
0x1800477d1  mov     eax, 80070057h
0x1800477d6  jmp     loc_180047AB5
0x1800477db  lea     rdx, byte_18007F401; struct std::nothrow_t *
0x1800477e2  mov     ecx, 68h ; 'h'; unsigned __int64
0x1800477e7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800477ec  mov     rbx, rax
0x1800477ef  test    rax, rax
0x1800477f2  jz      loc_180047AAC
0x1800477f8  xor     edx, edx; bool
0x1800477fa  mov     rcx, rax; this
0x1800477fd  call    ?ResetV4ConnectionFileStruct@V4ConnectionFiles@@AEAAX_N@Z; V4ConnectionFiles::ResetV4ConnectionFileStruct(bool)
0x180047802  xor     edx, edx; Val
0x180047804  mov     [r12], rbx
0x180047808  mov     r8d, 208h; Size
0x18004780e  lea     rcx, [rbp+1E0h+pszDest]; void *
0x180047812  call    memset_0
0x180047817  mov     r14d, 104h
0x18004781d  mov     [rsp+2E0h+pcchLength], rsi
0x180047822  mov     r8d, r14d; cchDest
0x180047825  lea     rdx, [rbp+1E0h+pszDest]; pszDest
0x180047829  mov     rcx, rdi; hkey
0x18004782c  mov     r13, rsi
0x18004782f  call    ?GetConnectionSpecificDirectory@@YAJPEAUHKEY__@@PEAGK@Z; GetConnectionSpecificDirectory(HKEY__ *,ushort *,ulong)
0x180047834  mov     ebx, eax
0x180047836  test    eax, eax
0x180047838  js      short loc_180047871
0x18004783a  lea     r8, asc_180080C28; "\\"
0x180047841  mov     edx, r14d; cchDest
0x180047844  lea     rcx, [rbp+1E0h+pszDest]; pszDest
0x180047848  call    StringCchCatW
0x18004784d  mov     ebx, eax
0x18004784f  test    eax, eax
0x180047851  js      short loc_180047871
0x180047853  lea     r8, [rsp+2E0h+pcchLength]; pcchLength
0x180047858  mov     edx, r14d; cchMax
0x18004785b  lea     rcx, [rbp+1E0h+pszDest]; psz
0x18004785f  call    StringLengthWorkerW
0x180047864  mov     r13, [rsp+2E0h+pcchLength]
0x180047869  test    eax, eax
0x18004786b  mov     ebx, eax
0x18004786d  cmovs   r13, rsi
0x180047871  mov     [rsp+2E0h+cValues], esi
0x180047875  mov     r14, rsi
0x180047878  mov     [rsp+2E0h+cbMaxValueNameLen], esi
0x18004787c  mov     r15, rsi
0x18004787f  mov     [rsp+2E0h+cbMaxValueLen], esi
0x180047883  test    ebx, ebx
0x180047885  js      loc_180047A98
0x18004788b  mov     [rsp+2E0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180047890  lea     rax, [rsp+2E0h+cbMaxValueLen]
0x180047895  mov     [rsp+2E0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18004789a  xor     r9d, r9d; lpReserved
0x18004789d  mov     [rsp+2E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800478a2  xor     r8d, r8d; lpcchClass
0x1800478a5  lea     rax, [rsp+2E0h+cbMaxValueNameLen]
0x1800478aa  xor     edx, edx; lpClass
0x1800478ac  mov     [rsp+2E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800478b1  mov     rcx, rdi; hKey
0x1800478b4  lea     rax, [rsp+2E0h+cValues]
0x1800478b9  mov     [rsp+2E0h+lpcValues], rax; lpcValues
0x1800478be  mov     [rsp+2E0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1800478c3  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x1800478c8  mov     [rsp+2E0h+lpcSubKeys], rsi; lpcSubKeys
0x1800478cd  call    cs:__imp_RegQueryInfoKeyW
0x1800478d3  test    eax, eax
0x1800478d5  jnz     short loc_180047940
0x1800478d7  mov     ecx, [rsp+2E0h+cbMaxValueNameLen]
0x1800478db  lea     r15d, [rax+2]
0x1800478df  inc     ecx
0x1800478e1  mov     eax, r15d
0x1800478e4  mul     rcx
0x1800478e7  lea     rcx, [r15-3]
0x1800478eb  lea     rdx, byte_18007F401; struct std::nothrow_t *
0x1800478f2  cmovb   rax, rcx
0x1800478f6  mov     rcx, rax; unsigned __int64
0x1800478f9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800478fe  mov     ecx, [rsp+2E0h+cbMaxValueLen]
0x180047902  mov     r14, rax
0x180047905  shr     rcx, 1
0x180047908  mov     eax, r15d
0x18004790b  mul     rcx
0x18004790e  lea     rcx, [r15-3]
0x180047912  lea     rdx, byte_18007F401; struct std::nothrow_t *
0x180047919  cmovb   rax, rcx
0x18004791d  mov     rcx, rax; unsigned __int64
0x180047920  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180047925  mov     r15, rax
0x180047928  test    rax, rax
0x18004792b  jz      short loc_180047936
0x18004792d  test    r14, r14
0x180047930  jnz     loc_180047A89
0x180047936  mov     ebx, 8007000Eh
0x18004793b  jmp     loc_180047A89
0x180047940  jg      short loc_180047949
0x180047942  mov     ebx, eax
0x180047944  jmp     loc_180047A89
0x180047949  movzx   ebx, ax
0x18004794c  or      ebx, 80070000h
0x180047952  jmp     loc_180047A89
0x180047957  cmp     esi, [rsp+2E0h+cValues]
0x18004795b  jnb     loc_180047A98
0x180047961  mov     eax, [rsp+2E0h+cbMaxValueNameLen]
0x180047965  lea     r9, [rsp+2E0h+pcchLength]; lpcchValueName
0x18004796a  inc     eax
0x18004796c  mov     r8, r14; lpValueName
0x18004796f  mov     dword ptr [rsp+2E0h+pcchLength], eax
0x180047973  mov     edx, esi; dwIndex
0x180047975  mov     eax, [rsp+2E0h+cbMaxValueLen]
0x180047979  mov     rcx, rdi; hKey
0x18004797c  mov     [rsp+2E0h+cbData], eax
0x180047980  lea     rax, [rsp+2E0h+cbData]
0x180047985  mov     [rsp+2E0h+lpcValues], rax; lpcbData
0x18004798a  mov     [rsp+2E0h+lpcbMaxClassLen], r15; lpData
0x18004798f  mov     [rsp+2E0h+lpcbMaxSubKeyLen], 0; lpType
0x180047998  mov     [rsp+2E0h+lpcSubKeys], 0; lpReserved
0x1800479a1  call    cs:__imp_RegEnumValueW
0x1800479a7  test    eax, eax
0x1800479a9  jz      short loc_1800479BC
0x1800479ab  jg      short loc_1800479B1
0x1800479ad  mov     ebx, eax
0x1800479af  jmp     short loc_1800479D4
0x1800479b1  movzx   ebx, ax
0x1800479b4  or      ebx, 80070000h
0x1800479ba  jmp     short loc_1800479D4
0x1800479bc  mov     ecx, [rsp+2E0h+cbMaxValueLen]
0x1800479c0  shr     rcx, 1
0x1800479c3  xor     eax, eax
0x1800479c5  mov     [r15+rcx*2-2], ax
0x1800479cb  mov     ecx, [rsp+2E0h+cbMaxValueNameLen]
0x1800479cf  mov     [r14+rcx*2], ax
0x1800479d4  test    ebx, ebx
0x1800479d6  js      loc_180047A87
0x1800479dc  xor     edx, edx
0x1800479de  lea     r10, ?s_connectionFiles@V4ConnectionFiles@@0QBUConnectionFileToRetrieve@1@B; V4ConnectionFiles::ConnectionFileToRetrieve const near * const V4ConnectionFiles::s_connectionFiles
0x1800479e5  mov     eax, edx
0x1800479e7  mov     rcx, r14
0x1800479ea  add     rax, rax
0x1800479ed  mov     r9, [r10+rax*8]
0x1800479f1  sub     r9, r14
0x1800479f4  movzx   r8d, word ptr [rcx]
0x1800479f8  movzx   eax, word ptr [rcx+r9]
0x1800479fd  sub     r8d, eax
0x180047a00  jnz     short loc_180047A0A
0x180047a02  add     rcx, 2
0x180047a06  test    eax, eax
0x180047a08  jnz     short loc_1800479F4
0x180047a0a  test    r8d, r8d
0x180047a0d  jz      short loc_180047A1D
0x180047a0f  inc     edx
0x180047a11  cmp     edx, 0Dh
0x180047a14  jb      short loc_1800479E5
0x180047a16  inc     esi
0x180047a18  jmp     loc_180047957
0x180047a1d  mov     ecx, [rsp+2E0h+cbData]
0x180047a21  mov     rbx, [r12]
0x180047a25  shr     ecx, 1
0x180047a27  add     ecx, r13d
0x180047a2a  mov     eax, edx
0x180047a2c  add     rax, rax
0x180047a2f  mov     [rsp+2E0h+cchDest], rcx
0x180047a34  mov     rdi, [r10+rax*8+8]
0x180047a39  mov     eax, 2
0x180047a3e  mul     rcx
0x180047a41  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180047a48  lea     rdx, byte_18007F401; struct std::nothrow_t *
0x180047a4f  cmovb   rax, rcx
0x180047a53  mov     rcx, rax; unsigned __int64
0x180047a56  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180047a5b  mov     [rdi+rbx], rax
0x180047a5f  test    rax, rax
0x180047a62  jz      short loc_180047A93
0x180047a64  mov     rdx, [rsp+2E0h+cchDest]; cchDest
0x180047a69  lea     r9, [rbp+1E0h+pszDest]
0x180047a6d  lea     r8, aWsWs; "%ws%ws"
0x180047a74  mov     [rsp+2E0h+lpcSubKeys], r15
0x180047a79  mov     rcx, rax; pszDest
0x180047a7c  call    StringCchPrintfW
0x180047a81  mov     rdi, [rbp+1E0h+var_260]
0x180047a85  mov     ebx, eax
0x180047a87  inc     esi
0x180047a89  test    ebx, ebx
0x180047a8b  jns     loc_180047957
0x180047a91  jmp     short loc_180047A98
0x180047a93  mov     ebx, 8007000Eh
0x180047a98  mov     rcx, r15; Block
0x180047a9b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180047aa0  mov     rcx, r14; Block
0x180047aa3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180047aa8  mov     eax, ebx
0x180047aaa  jmp     short loc_180047AB5
0x180047aac  mov     [r12], rsi
0x180047ab0  mov     eax, 8007000Eh
0x180047ab5  mov     rcx, [rbp+1E0h+var_40]
0x180047abc  xor     rcx, rsp; StackCookie
0x180047abf  call    __security_check_cookie
0x180047ac4  mov     rbx, [rsp+2E0h+arg_10]
0x180047acc  add     rsp, 2B0h
0x180047ad3  pop     r15
0x180047ad5  pop     r14
0x180047ad7  pop     r13
0x180047ad9  pop     r12
0x180047adb  pop     rdi
0x180047adc  pop     rsi
0x180047add  pop     rbp
0x180047ade  retn
```
