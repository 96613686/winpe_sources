# ListReaders(ulong,ushort const *,CBuffer &)

- ea: `0x180009480`
- end: `0x180009c0a`
- name: `?ListReaders@@YAXKPEBGAEAVCBuffer@@@Z`
- size: `1930`
- prototype: `void(unsigned int, const unsigned __int16 *, struct CBuffer *)`
- caller_count: `5`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180007f40`
- `0x18000e110`
- `0x18000e980`
- `0x18001a270`
- `0x1800262f0`

## callees

- `0x180005150`
- `0x180009480`
- `0x18000aa80`
- `0x18000bcf0`
- `0x18000bd10`
- `0x18000bd60`
- `0x18000e3d0`
- `0x180010400`
- `0x18001b9b8`
- `0x18001ba04`
- `0x18002ef20`
- `0x18002ef38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000954b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009775`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800097f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009862`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000954b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009775`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800097f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009862`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800097b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009835`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800097b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009835`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800098ea`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800098ea`

## string_xrefs

- `0x1800094f3`: `SCard$AllReaders`
- `0x18000950a`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`
- `0x1800095c3`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`
- `0x180009b76`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`
- `0x1800095a9`: `SCard$DefaultReaders`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
void __fastcall ListReaders(unsigned int a1, const unsigned __int16 *a2, struct CBuffer *a3)
{
  const unsigned __int16 *v4; // r15
  unsigned __int16 *v6; // rsi
  unsigned __int64 v7; // rdx
  unsigned __int16 *v8; // rcx
  const unsigned __int16 *String; // rax
  unsigned int v10; // eax
  unsigned int v11; // r15d
  struct CBuffer *v12; // r13
  unsigned int v13; // ecx
  unsigned __int64 v14; // rdx
  void *v15; // r13
  const void **v16; // r14
  const unsigned __int16 *v17; // rax
  unsigned int v18; // eax
  unsigned int v19; // r10d
  unsigned int v20; // r15d
  void *v21; // r13
  __int64 j; // rax
  __int64 v23; // rax
  HKEY v24; // rax
  HKEY v25; // rax
  unsigned int *v26; // r9
  int v27; // eax
  unsigned int v28; // r10d
  _DWORD *v29; // rax
  unsigned int v30; // edx
  unsigned int v31; // r8d
  unsigned int v32; // r9d
  void *v33; // rax
  unsigned __int64 v34; // rdx
  _QWORD *v35; // r9
  void *v36; // rcx
  void *v37; // rax
  unsigned __int64 v38; // rdx
  void *v39; // rax
  unsigned __int64 v40; // rdx
  WCHAR *v41; // rcx
  unsigned __int64 v42; // rdx
  unsigned int i; // edx
  HKEY v44; // rcx
  unsigned int v45; // [rsp+30h] [rbp-128h]
  unsigned int v46; // [rsp+30h] [rbp-128h]
  unsigned int *v47; // [rsp+38h] [rbp-120h]
  struct CBuffer *v48; // [rsp+40h] [rbp-118h]
  const WCHAR *lpString; // [rsp+48h] [rbp-110h]
  HKEY v50; // [rsp+50h] [rbp-108h]
  HKEY v51; // [rsp+50h] [rbp-108h]
  void *v52; // [rsp+50h] [rbp-108h]
  const WCHAR *lpSubKey; // [rsp+58h] [rbp-100h]
  LPCWSTR lpSubKeya; // [rsp+58h] [rbp-100h]
  ulong v55; // [rsp+60h] [rbp-F8h] BYREF
  ulong v56; // [rsp+64h] [rbp-F4h] BYREF
  ulong pExceptionObject; // [rsp+68h] [rbp-F0h] BYREF
  ulong v58; // [rsp+6Ch] [rbp-ECh] BYREF
  ulong v59; // [rsp+70h] [rbp-E8h] BYREF
  ulong v60; // [rsp+74h] [rbp-E4h] BYREF
  ulong v61; // [rsp+78h] [rbp-E0h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-D8h] BYREF
  int v63; // [rsp+88h] [rbp-D0h]
  _QWORD v64[2]; // [rsp+90h] [rbp-C8h] BYREF
  __int64 v65; // [rsp+A0h] [rbp-B8h]
  LSTATUS v66; // [rsp+A8h] [rbp-B0h]
  HKEY hKey; // [rsp+B0h] [rbp-A8h] BYREF
  int v68; // [rsp+B8h] [rbp-A0h]
  const int *v69; // [rsp+C0h] [rbp-98h]
  void *v70; // [rsp+C8h] [rbp-90h]
  __int64 v71; // [rsp+D0h] [rbp-88h]
  LSTATUS v72; // [rsp+D8h] [rbp-80h]
  const int *v73; // [rsp+E0h] [rbp-78h] BYREF
  unsigned __int16 *v74; // [rsp+E8h] [rbp-70h]
  __int64 v75; // [rsp+F0h] [rbp-68h]
  const int *v76; // [rsp+F8h] [rbp-60h] BYREF
  void *v77; // [rsp+100h] [rbp-58h]
  __int64 v78; // [rsp+108h] [rbp-50h]
  _QWORD v79[9]; // [rsp+110h] [rbp-48h]
  size_t Size; // [rsp+178h] [rbp+20h] BYREF

  v4 = a2;
  v69 = &CBuffer::`vftable';
  v70 = 0;
  v71 = 0;
  hKey = 0;
  v72 = 1010;
  v73 = &CBuffer::`vftable';
  v6 = 0;
  v74 = 0;
  v75 = 0;
  v76 = &CBuffer::`vftable';
  v77 = 0;
  v78 = 0;
  if ( MStringCommon(a2, L"SCard$AllReaders", (struct CBuffer *)&v76) )
  {
    ListKnownKeys(a1, a3, L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers");
    goto LABEL_3;
  }
  v48 = a3;
  if ( !v4 || !*v4 )
    v4 = L"SCard$DefaultReaders";
  v47 = (unsigned int *)((char *)a3 + 16);
  *((_DWORD *)a3 + 4) = 0;
  ListKnownKeys(a1, &v73, L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers");
  v8 = (unsigned __int16 *)&WideCharStr;
  v6 = v74;
  if ( HIDWORD(v75) )
    v8 = v74;
  String = FirstString(v8);
LABEL_18:
  lpString = String;
  if ( String )
  {
    v64[0] = &CBuffer::`vftable';
    v64[1] = 0;
    v65 = 0;
    v44 = 0;
    phkResult = 0;
    v66 = 1010;
    v79[0] = L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers";
    v79[1] = 0;
    for ( i = 0; ; ++i )
    {
      v45 = i;
      if ( i >= 2 )
        break;
      lpSubKey = (const WCHAR *)v79[i];
      if ( lpSubKey )
      {
        for ( j = 0; ; j = (unsigned int)(Size + 1) )
        {
          LODWORD(Size) = j;
          if ( (unsigned int)j >= 2 )
            break;
          v23 = 2 * j;
          if ( dword_180038360[2 * v23] >= a1 )
          {
            v24 = *(HKEY *)&dword_180038360[2 * v23 + 2];
            v50 = v24;
            if ( v44 )
            {
              RegCloseKey(v44);
              phkResult = 0;
              v24 = v50;
            }
            v66 = 1010;
            LODWORD(v65) = 0;
            v66 = RegOpenKeyExW(v24, lpSubKey, 0, 0x20019u, &phkResult);
            v63 = 2;
            if ( !v66 )
            {
              v25 = phkResult;
              v51 = phkResult;
              if ( hKey )
              {
                RegCloseKey(hKey);
                hKey = 0;
                v25 = v51;
              }
              v72 = 1010;
              LODWORD(v71) = 0;
              v72 = RegOpenKeyExW(v25, lpString, 0, 0x20019u, &hKey);
              v68 = 2;
              if ( !v72 )
              {
                if ( phkResult )
                {
                  RegCloseKey(phkResult);
                  phkResult = 0;
                }
                v66 = 1010;
                LODWORD(v65) = 0;
                v64[0] = &CBuffer::`vftable';
                CBuffer::Clear((CBuffer *)v64);
                Size = 0;
                CRegistry::GetValue((CRegistry *)&hKey, L"Groups", (unsigned __int16 **)&Size, v26);
                if ( Size )
                {
                  if ( MStringCommon(v4, (const unsigned __int16 *)Size, (struct CBuffer *)&v76) )
                  {
                    v27 = lstrlenW(lpString);
                    v28 = 2 * v27 + 2;
                    LODWORD(Size) = v28;
                    if ( 2 * v27 != -2 )
                    {
                      v29 = (_DWORD *)((char *)a3 + 16);
                      v30 = *v47;
                      v31 = *v47 + v28;
                      v46 = v31;
                      v32 = *((_DWORD *)a3 + 5);
                      if ( *v47 )
                      {
                        if ( v32 >= v31 )
                        {
                          v35 = (_QWORD *)((char *)a3 + 8);
                        }
                        else
                        {
                          v41 = (WCHAR *)operator new[](v31);
                          lpSubKeya = v41;
                          if ( !v41 )
                          {
                            v55 = 14;
                            throw &v55;
                          }
                          memcpy_0(v41, *((const void **)a3 + 1), *v47);
                          operator delete(*((void **)a3 + 1), v42);
                          v35 = (_QWORD *)((char *)a3 + 8);
                          *((_QWORD *)a3 + 1) = lpSubKeya;
                          *((_DWORD *)a3 + 5) = v46;
                          v30 = *v47;
                          v28 = Size;
                        }
                      }
                      else
                      {
                        if ( v32 >= v31 )
                        {
                          v35 = (_QWORD *)((char *)a3 + 8);
                        }
                        else
                        {
                          v33 = operator new[](v31);
                          v52 = v33;
                          if ( !v33 )
                          {
                            v56 = 14;
                            throw &v56;
                          }
                          v35 = (_QWORD *)((char *)a3 + 8);
                          v36 = (void *)*((_QWORD *)a3 + 1);
                          if ( v36 )
                          {
                            operator delete(v36, v34);
                            v35 = (_QWORD *)((char *)a3 + 8);
                            v33 = v52;
                          }
                          *v35 = v33;
                          *((_DWORD *)a3 + 5) = v46;
                          v29 = (_DWORD *)((char *)a3 + 16);
                          v28 = Size;
                        }
                        *v29 = 0;
                        v30 = 0;
                      }
                      memcpy_0((void *)(*v35 + v30), lpString, v28);
                      *v47 += Size;
                    }
                  }
                }
                String = NextString(lpString);
                goto LABEL_18;
              }
            }
            v44 = phkResult;
          }
        }
        if ( a1 != 2 )
          break;
        i = v45;
      }
    }
    pExceptionObject = 2;
    throw &pExceptionObject;
  }
  v10 = *v47;
  v11 = *v47 + 4;
  v12 = a3;
  v13 = *((_DWORD *)a3 + 5);
  if ( *v47 )
  {
    if ( v13 >= v11 )
    {
      v16 = (const void **)((char *)a3 + 8);
    }
    else
    {
      v37 = operator new[](v11);
      Size = (size_t)v37;
      if ( !v37 )
      {
        v58 = 14;
        throw &v58;
      }
      v16 = (const void **)((char *)a3 + 8);
      memcpy_0(v37, *v16, *v47);
      operator delete((void *)*v16, v38);
      *v16 = (const void *)Size;
      *((_DWORD *)v48 + 5) = v11;
      v10 = *v47;
    }
  }
  else
  {
    if ( v13 >= v11 )
    {
      v16 = (const void **)((char *)a3 + 8);
    }
    else
    {
      v15 = operator new[](v11);
      if ( !v15 )
      {
        v59 = 14;
        throw &v59;
      }
      v16 = (const void **)((char *)a3 + 8);
      if ( *v16 )
        operator delete((void *)*v16, v14);
      *v16 = v15;
      v12 = v48;
      *((_DWORD *)v48 + 5) = v11;
    }
    *v47 = 0;
    v10 = 0;
  }
  *(_DWORD *)((char *)*v16 + v10) = 0;
  *v47 += 4;
  if ( *((_DWORD *)v12 + 5) )
    v17 = (const unsigned __int16 *)*v16;
  else
    v17 = &WideCharStr;
  v18 = MStrLen(v17);
  v20 = v18;
  if ( !*v47 )
  {
    if ( v19 < v18 )
    {
      v21 = operator new[](v18);
      if ( !v21 )
      {
        v61 = 14;
        throw &v61;
      }
      if ( *v16 )
        operator delete((void *)*v16, v7);
      *v16 = v21;
      *((_DWORD *)v48 + 5) = v20;
    }
    goto LABEL_34;
  }
  if ( v19 >= v18 )
  {
LABEL_34:
    *v47 = v20;
    goto LABEL_3;
  }
  v39 = operator new[](v18);
  Size = (size_t)v39;
  if ( !v39 )
  {
    v60 = 14;
    throw &v60;
  }
  memcpy_0(v39, *v16, *v47);
  operator delete((void *)*v16, v40);
  *v16 = (const void *)Size;
  *((_DWORD *)v12 + 5) = v20;
  *v47 = v20;
LABEL_3:
  if ( v77 )
    operator delete(v77, v7);
  if ( v6 )
    operator delete(v6, v7);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v72 = 1010;
  LODWORD(v71) = 0;
  v69 = &CBuffer::`vftable';
  if ( v70 )
    operator delete(v70, v7);
}

```

## disassembly

```asm
0x180009480  mov     rax, rsp
0x180009483  mov     [rax+18h], r8
0x180009487  mov     [rax+10h], rdx
0x18000948b  mov     [rax+8], ecx
0x18000948e  push    rbx
0x18000948f  push    rsi
0x180009490  push    rdi
0x180009491  push    r12
0x180009493  push    r13
0x180009495  push    r14
0x180009497  push    r15
0x180009499  sub     rsp, 120h
0x1800094a0  mov     r14, r8
0x1800094a3  mov     r15, rdx
0x1800094a6  mov     r12d, ecx
0x1800094a9  lea     rdi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800094b0  mov     [rax-98h], rdi
0x1800094b7  xor     ebx, ebx
0x1800094b9  mov     [rax-90h], rbx
0x1800094c0  mov     [rax-88h], rbx
0x1800094c7  mov     [rax-0A8h], rbx
0x1800094ce  mov     dword ptr [rax-80h], 3F2h
0x1800094d5  mov     [rax-78h], rdi
0x1800094d9  mov     esi, ebx
0x1800094db  mov     [rax-70h], rbx
0x1800094df  mov     [rax-68h], rbx
0x1800094e3  mov     [rax-60h], rdi
0x1800094e7  mov     [rax-58h], rbx
0x1800094eb  mov     [rax-50h], rbx
0x1800094ef  lea     r8, [rax-60h]; struct CBuffer *
0x1800094f3  lea     rdx, aScardAllreader; "SCard$AllReaders"
0x1800094fa  mov     rcx, r15; unsigned __int16 *
0x1800094fd  call    ?MStringCommon@@YAKPEBG0AEAVCBuffer@@@Z; MStringCommon(ushort const *,ushort const *,CBuffer &)
0x180009502  test    eax, eax
0x180009504  jz      loc_180009599
0x18000950a  lea     r8, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x180009511  mov     rdx, r14
0x180009514  mov     ecx, r12d
0x180009517  call    ListKnownKeys
0x18000951c  nop
0x18000951d  mov     rcx, [rsp+158h+var_58]; void *
0x180009525  test    rcx, rcx
0x180009528  jz      short loc_180009530
0x18000952a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000952f  nop
0x180009530  test    rsi, rsi
0x180009533  jz      short loc_18000953E
0x180009535  mov     rcx, rsi; void *
0x180009538  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000953d  nop
0x18000953e  mov     rcx, [rsp+158h+hKey]; hKey
0x180009546  test    rcx, rcx
0x180009549  jz      short loc_180009559
0x18000954b  call    cs:__imp_RegCloseKey
0x180009551  mov     [rsp+158h+hKey], rbx
0x180009559  mov     [rsp+158h+var_80], 3F2h
0x180009564  mov     dword ptr [rsp+158h+var_88], ebx
0x18000956b  mov     [rsp+158h+var_98], rdi
0x180009573  mov     rcx, [rsp+158h+var_90]; void *
0x18000957b  test    rcx, rcx
0x18000957e  jz      short loc_180009586
0x180009580  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009585  nop
0x180009586  add     rsp, 120h
0x18000958d  pop     r15
0x18000958f  pop     r14
0x180009591  pop     r13
0x180009593  pop     r12
0x180009595  pop     rdi
0x180009596  pop     rsi
0x180009597  pop     rbx
0x180009598  retn
0x180009599  mov     [rsp+158h+var_118], r14
0x18000959e  test    r15, r15
0x1800095a1  jz      short loc_1800095A9
0x1800095a3  cmp     bx, [r15]
0x1800095a7  jnz     short loc_1800095B8
0x1800095a9  lea     r15, aScardDefaultre; "SCard$DefaultReaders"
0x1800095b0  mov     [rsp+158h+arg_8], r15
0x1800095b8  lea     rax, [r14+10h]
0x1800095bc  mov     [rsp+158h+var_120], rax
0x1800095c1  mov     [rax], ebx
0x1800095c3  lea     r13, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x1800095ca  mov     r8, r13
0x1800095cd  lea     rdx, [rsp+158h+var_78]
0x1800095d5  mov     ecx, r12d
0x1800095d8  call    ListKnownKeys
0x1800095dd  lea     rcx, WideCharStr
0x1800095e4  mov     rsi, [rsp+158h+var_70]
0x1800095ec  cmp     [rsp+158h+var_64], 0
0x1800095f4  cmova   rcx, rsi; unsigned __int16 *
0x1800095f8  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x1800095fd  lea     r8, dword_180038360
0x180009604  mov     [rsp+158h+lpString], rax
0x180009609  test    rax, rax
0x18000960c  jnz     loc_1800096DE
0x180009612  mov     r12, [rsp+158h+var_120]
0x180009617  mov     eax, [r12]
0x18000961b  lea     r15d, [rax+4]
0x18000961f  mov     r13, [rsp+158h+var_118]
0x180009624  mov     ecx, [r13+14h]
0x180009628  test    eax, eax
0x18000962a  jnz     loc_1800099B8
0x180009630  cmp     ecx, r15d
0x180009633  jnb     loc_180009A5E
0x180009639  mov     ecx, r15d; unsigned __int64
0x18000963c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009641  mov     r13, rax
0x180009644  test    rax, rax
0x180009647  jz      loc_180009BBC
0x18000964d  add     r14, 8
0x180009651  mov     rcx, [r14]; void *
0x180009654  test    rcx, rcx
0x180009657  jz      short loc_18000965E
0x180009659  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000965e  mov     [r14], r13
0x180009661  mov     r13, [rsp+158h+var_118]
0x180009666  mov     [r13+14h], r15d
0x18000966a  mov     [r12], ebx
0x18000966e  mov     eax, ebx
0x180009670  mov     ecx, eax
0x180009672  mov     rax, [r14]
0x180009675  mov     [rcx+rax], ebx
0x180009678  add     dword ptr [r12], 4
0x18000967d  mov     r10d, [r13+14h]
0x180009681  test    r10d, r10d
0x180009684  jz      loc_180009AE6
0x18000968a  mov     rax, [r14]
0x18000968d  mov     rcx, rax; unsigned __int16 *
0x180009690  call    ?MStrLen@@YAKPEBG@Z; MStrLen(ushort const *)
0x180009695  mov     r15d, eax
0x180009698  cmp     dword ptr [r12], 0
0x18000969d  ja      loc_180009A0D
0x1800096a3  cmp     r10d, r15d
0x1800096a6  jnb     short loc_1800096D5
0x1800096a8  mov     ecx, r15d; unsigned __int64
0x1800096ab  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800096b0  mov     r13, rax
0x1800096b3  test    rax, rax
0x1800096b6  jz      loc_180009BF0
0x1800096bc  mov     rcx, [r14]; void *
0x1800096bf  test    rcx, rcx
0x1800096c2  jz      short loc_1800096C9
0x1800096c4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800096c9  mov     [r14], r13
0x1800096cc  mov     rax, [rsp+158h+var_118]
0x1800096d1  mov     [rax+14h], r15d
0x1800096d5  mov     [r12], r15d
0x1800096d9  jmp     loc_18000951D
0x1800096de  mov     [rsp+158h+var_C8], rdi
0x1800096e6  mov     [rsp+158h+var_C0], rbx
0x1800096ee  mov     [rsp+158h+var_B8], 0
0x1800096fa  mov     rcx, rbx; hKey
0x1800096fd  mov     [rsp+158h+var_D8], rbx
0x180009705  mov     [rsp+158h+var_B0], 3F2h
0x180009710  mov     [rsp+158h+var_48], r13
0x180009718  mov     [rsp+158h+var_40], rbx
0x180009720  mov     edx, ebx
0x180009722  mov     [rsp+158h+var_128], edx
0x180009726  cmp     edx, 2
0x180009729  jnb     loc_180009B03
0x18000972f  mov     eax, edx
0x180009731  mov     rax, [rsp+rax*8+158h+var_48]
0x180009739  mov     [rsp+158h+lpSubKey], rax
0x18000973e  test    rax, rax
0x180009741  jz      loc_180009AFC
0x180009747  mov     eax, ebx
0x180009749  mov     dword ptr [rsp+158h+Size], eax
0x180009750  cmp     eax, 2
0x180009753  jnb     loc_180009AF2
0x180009759  add     rax, rax
0x18000975c  cmp     [r8+rax*8], r12d
0x180009760  jb      loc_180009B5F
0x180009766  mov     rax, [r8+rax*8+8]
0x18000976b  mov     [rsp+158h+var_108], rax
0x180009770  test    rcx, rcx
0x180009773  jz      short loc_180009788
0x180009775  call    cs:__imp_RegCloseKey
0x18000977b  mov     [rsp+158h+var_D8], rbx
0x180009783  mov     rax, [rsp+158h+var_108]
0x180009788  mov     [rsp+158h+var_B0], 3F2h
0x180009793  mov     dword ptr [rsp+158h+var_B8], ebx
0x18000979a  lea     rcx, [rsp+158h+var_D8]
0x1800097a2  mov     [rsp+158h+phkResult], rcx; phkResult
0x1800097a7  mov     r9d, 20019h; samDesired
0x1800097ad  xor     r8d, r8d; ulOptions
0x1800097b0  mov     rdx, [rsp+158h+lpSubKey]; lpSubKey
0x1800097b5  mov     rcx, rax; hKey
0x1800097b8  call    cs:__imp_RegOpenKeyExW
0x1800097be  mov     [rsp+158h+var_B0], eax
0x1800097c5  mov     [rsp+158h+var_D0], 2
0x1800097d0  test    eax, eax
0x1800097d2  jnz     loc_180009B50
0x1800097d8  mov     rax, [rsp+158h+var_D8]
0x1800097e0  mov     [rsp+158h+var_108], rax
0x1800097e5  mov     rcx, [rsp+158h+hKey]; hKey
0x1800097ed  test    rcx, rcx
0x1800097f0  jz      short loc_180009805
0x1800097f2  call    cs:__imp_RegCloseKey
0x1800097f8  mov     [rsp+158h+hKey], rbx
0x180009800  mov     rax, [rsp+158h+var_108]
0x180009805  mov     [rsp+158h+var_80], 3F2h
0x180009810  mov     dword ptr [rsp+158h+var_88], ebx
0x180009817  lea     rcx, [rsp+158h+hKey]
0x18000981f  mov     [rsp+158h+phkResult], rcx; phkResult
0x180009824  mov     r9d, 20019h; samDesired
0x18000982a  xor     r8d, r8d; ulOptions
0x18000982d  mov     rdx, [rsp+158h+lpString]; lpSubKey
0x180009832  mov     rcx, rax; hKey
0x180009835  call    cs:__imp_RegOpenKeyExW
0x18000983b  mov     [rsp+158h+var_80], eax
0x180009842  mov     [rsp+158h+var_A0], 2
0x18000984d  test    eax, eax
0x18000984f  jnz     loc_180009B50
0x180009855  mov     rcx, [rsp+158h+var_D8]; hKey
0x18000985d  test    rcx, rcx
0x180009860  jz      short loc_180009870
0x180009862  call    cs:__imp_RegCloseKey
0x180009868  mov     [rsp+158h+var_D8], rbx
0x180009870  mov     [rsp+158h+var_B0], 3F2h
0x18000987b  mov     dword ptr [rsp+158h+var_B8], ebx
0x180009882  mov     [rsp+158h+var_C8], rdi
0x18000988a  lea     rcx, [rsp+158h+var_C8]; this
0x180009892  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180009897  nop
0x180009898  mov     [rsp+158h+Size], rbx
0x1800098a0  lea     r8, [rsp+158h+Size]; unsigned __int16 **
0x1800098a8  lea     rdx, aGroups_0; "Groups"
0x1800098af  lea     rcx, [rsp+158h+hKey]; this
0x1800098b7  call    ?GetValue@CRegistry@@QEAAXPEBGPEAPEAGPEAK@Z; CRegistry::GetValue(ushort const *,ushort * *,ulong *)
0x1800098bc  mov     rdx, [rsp+158h+Size]; unsigned __int16 *
0x1800098c4  test    rdx, rdx
0x1800098c7  jz      loc_1800099A9
0x1800098cd  lea     r8, [rsp+158h+var_60]; struct CBuffer *
0x1800098d5  mov     rcx, r15; unsigned __int16 *
0x1800098d8  call    ?MStringCommon@@YAKPEBG0AEAVCBuffer@@@Z; MStringCommon(ushort const *,ushort const *,CBuffer &)
0x1800098dd  test    eax, eax
0x1800098df  jz      loc_1800099A9
0x1800098e5  mov     rcx, [rsp+158h+lpString]; lpString
0x1800098ea  call    cs:__imp_lstrlenW
0x1800098f0  lea     r10d, ds:2[rax*2]
0x1800098f8  mov     dword ptr [rsp+158h+Size], r10d
0x180009900  test    r10d, r10d
0x180009903  jz      loc_1800099A9
0x180009909  mov     rax, [rsp+158h+var_120]
0x18000990e  mov     edx, [rax]
0x180009910  lea     r8d, [rdx+r10]
0x180009914  mov     [rsp+158h+var_128], r8d
0x180009919  mov     rcx, [rsp+158h+var_118]
0x18000991e  mov     r9d, [rcx+14h]
0x180009922  test    edx, edx
0x180009924  jnz     loc_180009A67
0x18000992a  cmp     r9d, r8d
0x18000992d  jnb     loc_180009ACB
0x180009933  mov     ecx, r8d; unsigned __int64
0x180009936  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000993b  mov     [rsp+158h+var_108], rax
0x180009940  test    rax, rax
0x180009943  jz      loc_180009B36
0x180009949  lea     r9, [r14+8]
0x18000994d  mov     [rsp+158h+lpSubKey], r9
0x180009952  mov     rcx, [r9]; void *
0x180009955  test    rcx, rcx
0x180009958  jz      short loc_180009969
0x18000995a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000995f  mov     r9, [rsp+158h+lpSubKey]
0x180009964  mov     rax, [rsp+158h+var_108]
0x180009969  mov     [r9], rax
0x18000996c  mov     rax, [rsp+158h+var_118]
0x180009971  mov     ecx, [rsp+158h+var_128]
0x180009975  mov     [rax+14h], ecx
0x180009978  mov     rax, [rsp+158h+var_120]
0x18000997d  mov     r10d, dword ptr [rsp+158h+Size]
0x180009985  mov     [rax], ebx
0x180009987  mov     edx, ebx
0x180009989  mov     r8d, r10d; Size
0x18000998c  mov     ecx, edx
0x18000998e  add     rcx, [r9]; void *
0x180009991  mov     rdx, [rsp+158h+lpString]; Src
0x180009996  call    memcpy_0
0x18000999b  mov     rax, [rsp+158h+var_120]
0x1800099a0  mov     ecx, dword ptr [rsp+158h+Size]
0x1800099a7  add     [rax], ecx
0x1800099a9  mov     rcx, [rsp+158h+lpString]; unsigned __int16 *
0x1800099ae  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x1800099b3  jmp     loc_1800095FD
0x1800099b8  cmp     ecx, r15d
0x1800099bb  jnb     loc_180009AD4
0x1800099c1  mov     ecx, r15d; unsigned __int64
0x1800099c4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800099c9  mov     [rsp+158h+Size], rax
0x1800099d1  test    rax, rax
0x1800099d4  jz      loc_180009BA2
0x1800099da  add     r14, 8
0x1800099de  mov     r8d, [r12]; Size
0x1800099e2  mov     rdx, [r14]; Src
0x1800099e5  mov     rcx, rax; void *
0x1800099e8  call    memcpy_0
0x1800099ed  mov     rcx, [r14]; void *
0x1800099f0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
  ... truncated ...
```
