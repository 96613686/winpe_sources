# OrapiSetValCore(_msoreg const &,uchar const *,ulong)

- ea: `0x18009f3d8`
- end: `0x18009fbe8`
- name: `?OrapiSetValCore@@YAJAEBU_msoreg@@PEBEK@Z`
- size: `2064`
- prototype: `__int64 __fastcall(const struct _msoreg *, BYTE *lpData, unsigned int)`
- caller_count: `12`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180064258`
- `0x180064ee4`
- `0x18006afb4`
- `0x180099474`
- `0x18009bfe0`
- `0x18009c1a0`
- `0x1800a8af0`
- `0x1800a8d60`
- `0x1800fc600`
- `0x1800fce60`
- `0x18013d3b0`
- `0x18013d490`

## callees

- `0x180012aa0`
- `0x180012ccc`
- `0x180013080`
- `0x180023670`
- `0x1800236f0`
- `0x18009c4a8`
- `0x18009ced4`
- `0x18009e384`
- `0x18009f3d8`
- `0x1800a0000`
- `0x1800a10d0`
- `0x18056bd00`
- `0x18056dac4`
- `0x18056dce0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18009f54f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18009f54f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009f565`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009f7b3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009f997`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009f565`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009f7b3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009f997`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18009fb7a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18009fb7a`
- `ADVAPI32!RegQueryValueExW` at `0x18009f539`
- `ADVAPI32!RegQueryValueExW` at `0x18009f58c`
- `ADVAPI32!RegQueryValueExW` at `0x18009f539`
- `ADVAPI32!RegQueryValueExW` at `0x18009f58c`
- `ADVAPI32!RegSetValueExW` at `0x18009f877`
- `ADVAPI32!RegSetValueExW` at `0x18009f877`

## string_xrefs

- `0x18009f950`: `Failed to write registry value.`
- `0x18009f8d6`: `RegistryValueName`
- `0x18009fa4b`: `RegistryValueName`
- `0x18009f9e5`: `OrapiWriteFail: RegSetValueExW`
- `0x18009f77e`: `OrapiWriteFail: fWriteIt = false`
- `0x18009fb37`: `OrapiWriteFail: TryOpenKey in WriteValue`
- `0x18009f90a`: `KeyPath`
- `0x18009fae3`: `Failed to open registry key.`

## pseudocode

```c
__int64 __fastcall OrapiSetValCore(const struct _msoreg *a1, BYTE *lpData, DWORD a3)
{
  const BYTE *v3; // r13
  __int64 v5; // rdi
  unsigned int v6; // esi
  __int16 v7; // ax
  char v8; // r15
  bool v9; // cl
  BYTE *v10; // rbx
  int v11; // r12d
  LSTATUS *v12; // rax
  __int64 v13; // r13
  __int64 v14; // rcx
  __int64 v15; // rcx
  BYTE *v16; // rsi
  Mso::Orapi::KeyCache *v17; // rcx
  char v18; // al
  char v19; // r15
  int v20; // ecx
  BYTE *v21; // rax
  char *v22; // rdx
  unsigned __int16 v23; // cx
  int v24; // eax
  void *v25; // rdx
  bool v26; // zf
  unsigned __int64 v27; // rcx
  int v29; // r12d
  __m128i si128; // xmm6
  __m128i v31; // xmm7
  LSTATUS *v32; // rax
  __int64 v33; // r15
  __int64 v34; // rcx
  __int64 v35; // rcx
  LSTATUS v36; // eax
  __int64 v37; // r8
  int v38; // edx
  int v39; // r8d
  void *v40; // rcx
  unsigned __int64 v41; // rcx
  const wchar_t *v42; // rax
  Mso::Orapi::KeyCache *v43; // rcx
  char v44; // al
  __int64 v45; // rdx
  __int64 v46; // r8
  int v47; // edx
  int v48; // r8d
  __int64 v49; // rcx
  char v50; // [rsp+49h] [rbp-BFh]
  DWORD cbData; // [rsp+4Ch] [rbp-BCh] BYREF
  DWORD v52[2]; // [rsp+50h] [rbp-B8h]
  void *Buf2; // [rsp+58h] [rbp-B0h]
  DWORD Type[2]; // [rsp+60h] [rbp-A8h] BYREF
  void **v55; // [rsp+68h] [rbp-A0h] BYREF
  const wchar_t *v56; // [rsp+70h] [rbp-98h]
  unsigned int v57; // [rsp+78h] [rbp-90h]
  __int16 v58; // [rsp+7Ch] [rbp-8Ch]
  LSTATUS v59; // [rsp+80h] [rbp-88h] BYREF
  __int64 v60; // [rsp+88h] [rbp-80h]
  void **v61; // [rsp+90h] [rbp-78h] BYREF
  const wchar_t *v62; // [rsp+98h] [rbp-70h]
  __int64 v63; // [rsp+A0h] [rbp-68h]
  __int16 v64; // [rsp+A8h] [rbp-60h]
  _BYTE v65[16]; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v66; // [rsp+C0h] [rbp-48h] BYREF
  __m128i v67; // [rsp+D0h] [rbp-38h]
  void **v68; // [rsp+E0h] [rbp-28h] BYREF
  const wchar_t *v69; // [rsp+E8h] [rbp-20h]
  __int128 v70; // [rsp+F0h] [rbp-18h] BYREF
  __m128i v71; // [rsp+100h] [rbp-8h]
  __int16 v72; // [rsp+110h] [rbp+8h]

  v52[0] = a3;
  v3 = lpData;
  Buf2 = lpData;
  v5 = 0;
  v6 = 0;
  v7 = *((_WORD *)a1 + 14);
  v8 = (unsigned __int8)v7 >> 7;
  v50 = (unsigned __int8)v7 >> 7;
  if ( dword_1806BAA10 )
    v9 = dword_1806BAA10 == 2;
  else
    v9 = byte_1806BAA60 != 0;
  if ( v9 && (v7 & 0x30) != 0x20 || vfRunningRestricted || FRegValueExists(a1, 1) )
    return 0;
  v10 = 0;
  cbData = 0;
  Type[0] = 0;
  Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(
    v65,
    s_orapiCS);
  if ( v8 )
    goto LABEL_68;
  v11 = 0;
  do
  {
    if ( v11 >= 4 )
      break;
    v12 = sub_18009E384(&v59, *((HKEY *)a1 + 2), 0, 0, *((_BYTE *)a1 + 24));
    v6 = *v12;
    v13 = *((_QWORD *)v12 + 1);
    *((_QWORD *)v12 + 1) = 0;
    v14 = v5;
    v5 = v13;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    v15 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
    }
    if ( v6 )
      goto LABEL_27;
    v6 = RegQueryValueExW(*(HKEY *)(v13 + 16), *(LPCWSTR *)a1, 0, Type, 0, &cbData);
    if ( !v6 && cbData )
    {
      v16 = (BYTE *)malloc(cbData);
      if ( v16 )
      {
        if ( v10 )
          free(v10);
        v10 = v16;
        v6 = RegQueryValueExW(*(HKEY *)(v13 + 16), *(LPCWSTR *)a1, 0, Type, v16, &cbData);
      }
      else
      {
        v6 = 8;
      }
    }
    if ( v6 == 1010 || v6 == 1018 || v6 == 6 )
    {
      v17 = (Mso::Orapi::KeyCache *)*((_QWORD *)a1 + 2);
      *(&vrgPersistentKeys + 4 * (*((_WORD *)v17 + 5) & 0x1F)) = 0;
      Mso::Orapi::KeyCache::RemoveKey(v17, (const struct _orkey *)&_NULL_IMPORT_DESCRIPTOR);
      v18 = 1;
    }
    else
    {
LABEL_27:
      v18 = 0;
    }
    ++v11;
  }
  while ( v18 );
  v19 = v50;
  if ( v6 || !v10 )
  {
    v25 = (void *)*((_QWORD *)a1 + 1);
    if ( v25 != (void *)0xCCCCCCCCCCCCCCCCLL )
    {
      if ( (*((_WORD *)a1 + 14) & 0xF) != 1 && (*((_WORD *)a1 + 14) & 0xF) != 2 )
      {
        if ( (*((_WORD *)a1 + 14) & 0xF) == 4 )
        {
          if ( v52[0] != 4 )
            CrashWithRecovery(0x59948Eu, 0);
          v3 = (const BYTE *)Buf2;
          v26 = *(_DWORD *)Buf2 == *((_DWORD *)a1 + 2);
        }
        else
        {
          if ( (*((_WORD *)a1 + 14) & 0xF) != 0xB )
            CrashWithRecovery(0x599491u, 0);
          if ( v52[0] != 8 )
            CrashWithRecovery(0x59948Fu, 0);
          v3 = (const BYTE *)Buf2;
          v26 = *(_QWORD *)Buf2 == (_QWORD)v25;
        }
        if ( v26 )
          goto LABEL_35;
        goto LABEL_68;
      }
      if ( v52[0] < 2 )
        CrashWithRecovery(0x59948Du, 0);
      v3 = (const BYTE *)Buf2;
      if ( v25 == Buf2 )
        goto LABEL_35;
      goto LABEL_58;
    }
    v3 = (const BYTE *)Buf2;
LABEL_68:
    v29 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v31 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      if ( v29 >= 4 )
        goto LABEL_62;
      v32 = sub_18009E384(&v59, *((HKEY *)a1 + 2), 0, 4, *((_BYTE *)a1 + 24));
      v6 = *v32;
      v33 = *((_QWORD *)v32 + 1);
      *((_QWORD *)v32 + 1) = 0;
      v34 = v5;
      v5 = v33;
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
      v35 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
      }
      if ( v6 )
        break;
      v36 = RegSetValueExW(*(HKEY *)(v33 + 16), *(LPCWSTR *)a1, 0, *((_WORD *)a1 + 14) & 0xF, v3, v52[0]);
      v6 = v36;
      if ( v36 != 1010 && v36 != 1018 && v36 != 6 )
      {
        if ( v36 )
        {
          v55 = &Mso::Logging::StructuredErrorCode::`vftable';
          v56 = L"Win32ErrorCode";
          v57 = v36;
          v58 = 0;
          v61 = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
          v62 = L"RegistryValueName";
          v63 = *(_QWORD *)a1;
          v64 = 0;
          LOBYTE(v37) = v50;
          sub_18009CED4(&v66, *((_QWORD *)a1 + 2), v37);
          v68 = &Mso::Logging::StructuredObject<std::wstring,0>::`vftable';
          v69 = L"KeyPath";
          v70 = v66;
          v71 = v67;
          v67 = si128;
          LOWORD(v66) = 0;
          v72 = 0;
          Mso::Logging::MsoSendStructuredTraceTag<Mso::Logging::StructuredObject<std::wstring,0>,Mso::Logging::StructuredObject<wchar_t const *,1>,Mso::Logging::StructuredObject<int,1>>(
            23668940,
            v38,
            v39,
            (unsigned int)L"Failed to write registry value.",
            (__int64)&v68,
            (__int64)&v61,
            (__int64)&v55);
          if ( v71.m128i_i64[1] > 7uLL )
          {
            v40 = (void *)v70;
            if ( (unsigned __int64)(2 * v71.m128i_i64[1] + 2) >= 0x1000 )
            {
              v40 = *(void **)(v70 - 8);
              if ( (unsigned __int64)(v70 - (_QWORD)v40 - 8) > 0x1F )
                _invoke_watson(0, 0, 0, 0, 0);
            }
            free(v40);
          }
          *(_QWORD *)&v70 = 19937;
          v71 = v31;
          std::wstring::~wstring(&v66);
          v41 = (unsigned int)_InterlockedIncrement(&dword_1806BA6EC) % 0x32uLL;
          v42 = L"OrapiWriteFail: RegSetValueExW";
LABEL_88:
          v49 = 2 * v41;
          qword_1806BA6F8[v49] = (__int64)v42;
          dword_1806BA6F0[2 * v49] = v6;
        }
        v44 = 0;
        goto LABEL_90;
      }
      v43 = (Mso::Orapi::KeyCache *)*((_QWORD *)a1 + 2);
      *(&vrgPersistentKeys + 4 * (*((_WORD *)v43 + 5) & 0x1F)) = 0;
      Mso::Orapi::KeyCache::RemoveKey(v43, (const struct _orkey *)&_NULL_IMPORT_DESCRIPTOR);
      v44 = 1;
LABEL_90:
      ++v29;
      if ( !v44 )
        goto LABEL_62;
    }
    v55 = &Mso::Logging::StructuredErrorCode::`vftable';
    v56 = L"Win32ErrorCode";
    v57 = v6;
    v58 = 0;
    v61 = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
    v62 = L"RegistryValueName";
    v63 = *(_QWORD *)a1;
    v64 = 0;
    v45 = **((_QWORD **)a1 + 2);
    v66 = 0;
    v67 = 0;
    v46 = -1;
    do
      ++v46;
    while ( *(_WORD *)(v45 + 2 * v46) );
    std::wstring::_Construct<1,wchar_t *>(&v66, v45, v46);
    v68 = &Mso::Logging::StructuredObject<std::wstring,0>::`vftable';
    v69 = L"KeyName";
    v70 = v66;
    v71 = v67;
    v67 = si128;
    LOWORD(v66) = 0;
    v72 = 0;
    Mso::Logging::MsoSendStructuredTraceTag<Mso::Logging::StructuredObject<std::wstring,0>,Mso::Logging::StructuredObject<wchar_t const *,1>,Mso::Logging::StructuredObject<int,1>>(
      23668941,
      v47,
      v48,
      (unsigned int)L"Failed to open registry key.",
      (__int64)&v68,
      (__int64)&v61,
      (__int64)&v55);
    std::wstring::~wstring(&v70);
    std::wstring::~wstring(&v66);
    v41 = (unsigned int)_InterlockedIncrement(&dword_1806BA6EC) % 0x32uLL;
    v42 = L"OrapiWriteFail: TryOpenKey in WriteValue";
    goto LABEL_88;
  }
  v20 = *((_WORD *)a1 + 14) & 0xF;
  if ( Type[0] != v20 )
  {
    v3 = (const BYTE *)Buf2;
    goto LABEL_58;
  }
  if ( (unsigned int)(v20 - 1) < 2 )
  {
    v3 = (const BYTE *)Buf2;
    if ( !*(_WORD *)&v10[2 * ((unsigned __int64)cbData >> 1) - 2] )
    {
      v21 = v10;
      v22 = (char *)((_BYTE *)Buf2 - v10);
      while ( 1 )
      {
        v23 = *(_WORD *)v21;
        if ( *(_WORD *)v21 != *(_WORD *)&v22[(_QWORD)v21] )
          break;
        v21 += 2;
        if ( !v23 )
        {
          v24 = 0;
          goto LABEL_42;
        }
      }
      v24 = v23 < *(_WORD *)&v22[(_QWORD)v21] ? -1 : 1;
LABEL_42:
      if ( !v24 )
      {
LABEL_59:
        if ( !v19 )
        {
          if ( v6 )
          {
            v27 = 2 * ((unsigned int)_InterlockedIncrement(&dword_1806BA6EC) % 0x32uLL);
            dword_1806BA6F0[2 * v27] = v6;
            qword_1806BA6F8[v27] = (__int64)L"OrapiWriteFail: fWriteIt = false";
          }
          goto LABEL_62;
        }
        goto LABEL_68;
      }
    }
LABEL_58:
    v19 = 1;
    goto LABEL_59;
  }
  v3 = (const BYTE *)Buf2;
  if ( cbData != v52[0] || memcmp_0(v10, Buf2, cbData) )
    goto LABEL_58;
LABEL_35:
  v6 = 0;
LABEL_62:
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::~TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(v65);
  if ( v10 )
    free(v10);
  return v6;
}

```

## disassembly

```asm
0x18009f3d8  mov     rax, rsp
0x18009f3db  mov     [rax+20h], rbx
0x18009f3df  push    rbp
0x18009f3e0  push    rsi
0x18009f3e1  push    rdi
0x18009f3e2  push    r12
0x18009f3e4  push    r13
0x18009f3e6  push    r14
0x18009f3e8  push    r15
0x18009f3ea  lea     rbp, [rax-78h]
0x18009f3ee  sub     rsp, 140h
0x18009f3f5  movaps  xmmword ptr [rax-48h], xmm6
0x18009f3f9  movaps  xmmword ptr [rax-58h], xmm7
0x18009f3fd  mov     rax, cs:__security_cookie
0x18009f404  xor     rax, rsp
0x18009f407  mov     [rbp+70h+var_60], rax
0x18009f40b  mov     [rsp+170h+var_128], r8d
0x18009f410  mov     r13, rdx
0x18009f413  mov     [rsp+170h+Buf2], rdx
0x18009f418  mov     r14, rcx
0x18009f41b  xor     edi, edi
0x18009f41d  mov     esi, edi
0x18009f41f  movzx   eax, word ptr [rcx+1Ch]
0x18009f423  mov     r15b, al
0x18009f426  shr     r15b, 7
0x18009f42a  and     r15b, 1
0x18009f42e  mov     byte ptr [rsp+170h+var_130+1], r15b
0x18009f433  mov     ecx, cs:dword_1806BAA10
0x18009f439  test    ecx, ecx
0x18009f43b  jz      short loc_18009F445
0x18009f43d  cmp     ecx, 2
0x18009f440  setz    cl
0x18009f443  jmp     short loc_18009F44F
0x18009f445  cmp     cs:byte_1806BAA60, dil
0x18009f44c  setnz   cl
0x18009f44f  test    cl, cl
0x18009f451  jz      short loc_18009F45D
0x18009f453  and     al, 30h
0x18009f455  cmp     al, 20h ; ' '
0x18009f457  jnz     loc_18009FB81
0x18009f45d  cmp     cs:?vfRunningRestricted@@3HA, edi; int vfRunningRestricted
0x18009f463  jnz     loc_18009FB81
0x18009f469  mov     dl, 1; bool
0x18009f46b  mov     rcx, r14; struct _msoreg *
0x18009f46e  call    ?FRegValueExists@@YA_NPEBU_msoreg@@_N@Z; FRegValueExists(_msoreg const *,bool)
0x18009f473  test    al, al
0x18009f475  jnz     loc_18009FB81
0x18009f47b  mov     rbx, rdi
0x18009f47e  mov     [rsp+170h+cbData], edi
0x18009f482  mov     [rsp+170h+Type], edi
0x18009f486  lea     rdx, ?s_orapiCS@@3V?$Lockable@V?$AlwaysInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@Mso@@A; Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded> s_orapiCS
0x18009f48d  lea     rcx, [rbp+70h+var_C8]
0x18009f491  call    ??0?$TLocker@V?$Lockable@V?$AlwaysInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@Mso@@VZeroOrOneThreaded@2@@Mso@@QEAA@AEAV?$Lockable@V?$AlwaysInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@1@@Z; Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded> &)
0x18009f496  lea     r12, __NULL_IMPORT_DESCRIPTOR
0x18009f49d  test    r15b, r15b
0x18009f4a0  jnz     loc_18009F7C5
0x18009f4a6  xor     r15d, r15d
0x18009f4a9  mov     r12d, r15d
0x18009f4ac  cmp     r12d, 4
0x18009f4b0  jge     loc_18009F5E5
0x18009f4b6  mov     [rsp+170h+lpcbData], r15
0x18009f4bb  mov     al, [r14+18h]
0x18009f4bf  mov     byte ptr [rsp+170h+lpData], al
0x18009f4c3  xor     r9d, r9d
0x18009f4c6  xor     r8d, r8d
0x18009f4c9  mov     rdx, [r14+10h]
0x18009f4cd  lea     rcx, [rsp+170h+var_F8]
0x18009f4d2  call    sub_18009E384
0x18009f4d7  mov     esi, [rax]
0x18009f4d9  mov     r13, [rax+8]
0x18009f4dd  mov     [rax+8], r15
0x18009f4e1  mov     rcx, rdi
0x18009f4e4  mov     rdi, r13
0x18009f4e7  test    rcx, rcx
0x18009f4ea  jz      short loc_18009F4F9
0x18009f4ec  mov     rax, [rcx]
0x18009f4ef  mov     rax, [rax+8]
0x18009f4f3  call    cs:__guard_dispatch_icall_fptr
0x18009f4f9  mov     rcx, [rbp+70h+var_F0]
0x18009f4fd  test    rcx, rcx
0x18009f500  jz      short loc_18009F513
0x18009f502  mov     [rbp+70h+var_F0], r15
0x18009f506  mov     rax, [rcx]
0x18009f509  mov     rax, [rax+8]
0x18009f50d  call    cs:__guard_dispatch_icall_fptr
0x18009f513  test    esi, esi
0x18009f515  jnz     loc_18009F5D7
0x18009f51b  lea     rax, [rsp+170h+cbData]
0x18009f520  mov     [rsp+170h+lpcbData], rax; lpcbData
0x18009f525  mov     [rsp+170h+lpData], r15; lpData
0x18009f52a  lea     r9, [rsp+170h+Type]; lpType
0x18009f52f  xor     r8d, r8d; lpReserved
0x18009f532  mov     rdx, [r14]; lpValueName
0x18009f535  mov     rcx, [r13+10h]; hKey
0x18009f539  call    cs:__imp_RegQueryValueExW
0x18009f53f  mov     esi, eax
0x18009f541  test    eax, eax
0x18009f543  jnz     short loc_18009F59B
0x18009f545  mov     eax, [rsp+170h+cbData]
0x18009f549  test    eax, eax
0x18009f54b  jz      short loc_18009F59B
0x18009f54d  mov     ecx, eax; Size
0x18009f54f  call    cs:__imp_malloc
0x18009f555  mov     rsi, rax
0x18009f558  test    rax, rax
0x18009f55b  jz      short loc_18009F596
0x18009f55d  test    rbx, rbx
0x18009f560  jz      short loc_18009F56B
0x18009f562  mov     rcx, rbx; Block
0x18009f565  call    cs:__imp_free
0x18009f56b  mov     rbx, rsi
0x18009f56e  lea     rax, [rsp+170h+cbData]
0x18009f573  mov     [rsp+170h+lpcbData], rax; lpcbData
0x18009f578  mov     [rsp+170h+lpData], rbx; lpData
0x18009f57d  lea     r9, [rsp+170h+Type]; lpType
0x18009f582  xor     r8d, r8d; lpReserved
0x18009f585  mov     rdx, [r14]; lpValueName
0x18009f588  mov     rcx, [r13+10h]; hKey
0x18009f58c  call    cs:__imp_RegQueryValueExW
0x18009f592  mov     esi, eax
0x18009f594  jmp     short loc_18009F59B
0x18009f596  mov     esi, 8
0x18009f59b  cmp     esi, 3F2h
0x18009f5a1  jz      short loc_18009F5B0
0x18009f5a3  cmp     esi, 3FAh
0x18009f5a9  jz      short loc_18009F5B0
0x18009f5ab  cmp     esi, 6
0x18009f5ae  jnz     short loc_18009F5D7
0x18009f5b0  mov     rcx, [r14+10h]; this
0x18009f5b4  movzx   eax, word ptr [rcx+0Ah]
0x18009f5b8  and     eax, 1Fh
0x18009f5bb  shl     rax, 5
0x18009f5bf  lea     rdx, __NULL_IMPORT_DESCRIPTOR; struct _orkey *
0x18009f5c6  mov     [rax+rdx+6A1370h], r15
0x18009f5ce  call    ?RemoveKey@KeyCache@Orapi@Mso@@YAXAEBU_orkey@@@Z; Mso::Orapi::KeyCache::RemoveKey(_orkey const &)
0x18009f5d3  mov     al, 1
0x18009f5d5  jmp     short loc_18009F5DA
0x18009f5d7  mov     al, r15b
0x18009f5da  inc     r12d
0x18009f5dd  test    al, al
0x18009f5df  jnz     loc_18009F4AC
0x18009f5e5  test    esi, esi
0x18009f5e7  mov     r15b, byte ptr [rsp+170h+var_130+1]
0x18009f5ec  jnz     loc_18009F6A2
0x18009f5f2  xor     r8d, r8d
0x18009f5f5  test    rbx, rbx
0x18009f5f8  jz      loc_18009F6A2
0x18009f5fe  movzx   ecx, word ptr [r14+1Ch]
0x18009f603  and     ecx, 0Fh
0x18009f606  cmp     [rsp+170h+Type], ecx
0x18009f60a  jnz     loc_18009F698
0x18009f610  sub     ecx, 1
0x18009f613  jz      short loc_18009F64E
0x18009f615  cmp     ecx, 1
0x18009f618  jz      short loc_18009F64E
0x18009f61a  mov     eax, [rsp+170h+cbData]
0x18009f61e  mov     r13, [rsp+170h+Buf2]
0x18009f623  cmp     eax, [rsp+170h+var_128]
0x18009f627  jnz     loc_18009F72A
0x18009f62d  mov     r8d, eax; Size
0x18009f630  mov     rdx, r13; Buf2
0x18009f633  mov     rcx, rbx; Buf1
0x18009f636  call    memcmp_0
0x18009f63b  xor     r15d, r15d
0x18009f63e  test    eax, eax
0x18009f640  jnz     loc_18009F72A
0x18009f646  mov     esi, r15d
0x18009f649  jmp     loc_18009F78D
0x18009f64e  mov     eax, [rsp+170h+cbData]
0x18009f652  shr     rax, 1
0x18009f655  mov     r13, [rsp+170h+Buf2]
0x18009f65a  cmp     [rbx+rax*2-2], r8w
0x18009f660  jnz     loc_18009F72A
0x18009f666  mov     rax, rbx
0x18009f669  mov     rdx, r13
0x18009f66c  sub     rdx, rbx
0x18009f66f  movzx   ecx, word ptr [rax]
0x18009f672  cmp     cx, [rax+rdx]
0x18009f676  jnz     short loc_18009F686
0x18009f678  add     rax, 2
0x18009f67c  test    cx, cx
0x18009f67f  jnz     short loc_18009F66F
0x18009f681  mov     eax, r8d
0x18009f684  jmp     short loc_18009F68B
0x18009f686  sbb     eax, eax
0x18009f688  or      eax, 1
0x18009f68b  test    eax, eax
0x18009f68d  jz      loc_18009F72D
0x18009f693  jmp     loc_18009F72A
0x18009f698  mov     r13, [rsp+170h+Buf2]
0x18009f69d  jmp     loc_18009F72A
0x18009f6a2  mov     rdx, [r14+8]
0x18009f6a6  mov     rax, 0CCCCCCCCCCCCCCCCh
0x18009f6b0  cmp     rdx, rax
0x18009f6b3  jz      loc_18009F7C0
0x18009f6b9  movzx   ecx, word ptr [r14+1Ch]
0x18009f6be  and     ecx, 0Fh
0x18009f6c1  sub     ecx, 1
0x18009f6c4  jz      short loc_18009F715
0x18009f6c6  sub     ecx, 1
0x18009f6c9  jz      short loc_18009F715
0x18009f6cb  sub     ecx, 2
0x18009f6ce  jz      short loc_18009F6FB
0x18009f6d0  cmp     ecx, 7
0x18009f6d3  jnz     loc_18009FBC1
0x18009f6d9  cmp     [rsp+170h+var_128], 8
0x18009f6de  jnz     loc_18009FBCE
0x18009f6e4  mov     r13, [rsp+170h+Buf2]
0x18009f6e9  cmp     [r13+0], rdx
0x18009f6ed  jnz     loc_18009F7C5
0x18009f6f3  xor     r15d, r15d
0x18009f6f6  jmp     loc_18009F646
0x18009f6fb  cmp     [rsp+170h+var_128], 4
0x18009f700  jnz     loc_18009FBDB
0x18009f706  mov     eax, [r14+8]
0x18009f70a  mov     r13, [rsp+170h+Buf2]
0x18009f70f  cmp     [r13+0], eax
0x18009f713  jmp     short loc_18009F6ED
0x18009f715  cmp     [rsp+170h+var_128], 2
0x18009f71a  jb      loc_18009FBB4
0x18009f720  mov     r13, [rsp+170h+Buf2]
0x18009f725  cmp     rdx, r13
0x18009f728  jz      short loc_18009F6F3
0x18009f72a  mov     r15b, 1
0x18009f72d  lea     r12, __NULL_IMPORT_DESCRIPTOR
0x18009f734  test    r15b, r15b
0x18009f737  jnz     loc_18009F7C5
0x18009f73d  test    esi, esi
0x18009f73f  jz      short loc_18009F78D
0x18009f741  mov     ecx, 1
0x18009f746  lock xadd cs:dword_1806BA6EC, ecx
0x18009f74e  inc     ecx
0x18009f750  mov     rax, 47AE147AE147AE15h
0x18009f75a  mul     rcx
0x18009f75d  mov     eax, ecx
0x18009f75f  sub     rax, rdx
0x18009f762  shr     rax, 1
0x18009f765  add     rax, rdx
0x18009f768  shr     rax, 5
0x18009f76c  imul    rax, 32h ; '2'
0x18009f770  sub     rcx, rax
0x18009f773  add     rcx, rcx
0x18009f776  mov     rva dword_1806BA6F0[r12+rcx*8], esi
0x18009f77e  lea     rax, aOrapiwritefail_0; "OrapiWriteFail: fWriteIt = false"
0x18009f785  mov     rva qword_1806BA6F8[r12+rcx*8], rax
0x18009f78d  test    rdi, rdi
0x18009f790  jz      short loc_18009F7A2
0x18009f792  mov     rax, [rdi]
0x18009f795  mov     rcx, rdi
0x18009f798  mov     rax, [rax+8]
0x18009f79c  call    cs:__guard_dispatch_icall_fptr
0x18009f7a2  lea     rcx, [rbp+70h+var_C8]
0x18009f7a6  call    ??1?$TLocker@V?$Lockable@V?$AlwaysInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@Mso@@VZeroOrOneThreaded@2@@Mso@@QEAA@XZ; Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::~TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(void)
0x18009f7ab  test    rbx, rbx
0x18009f7ae  jz      short loc_18009F7B9
0x18009f7b0  mov     rcx, rbx; Block
0x18009f7b3  call    cs:__imp_free
0x18009f7b9  mov     eax, esi
0x18009f7bb  jmp     loc_18009FB83
0x18009f7c0  mov     r13, [rsp+170h+Buf2]
0x18009f7c5  xor     r15d, r15d
0x18009f7c8  mov     r12d, r15d
0x18009f7cb  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18009f7d3  movdqa  xmm7, cs:__xmm@000000000000000f0000000000000000
0x18009f7db  cmp     r12d, 4
0x18009f7df  jge     short loc_18009F78D
0x18009f7e1  mov     byte ptr [rsp+170h+var_130], r15b
0x18009f7e6  mov     [rsp+170h+lpcbData], r15
0x18009f7eb  mov     al, [r14+18h]
0x18009f7ef  mov     byte ptr [rsp+170h+lpData], al
0x18009f7f3  mov     r9d, 4
0x18009f7f9  xor     r8d, r8d
0x18009f7fc  mov     rdx, [r14+10h]
0x18009f800  lea     rcx, [rsp+170h+var_F8]
0x18009f805  call    sub_18009E384
0x18009f80a  mov     esi, [rax]
0x18009f80c  mov     r15, [rax+8]
0x18009f810  xor     r9d, r9d
0x18009f813  mov     [rax+8], r9
0x18009f817  mov     rcx, rdi
0x18009f81a  mov     rdi, r15
0x18009f81d  test    rcx, rcx
0x18009f820  jz      short loc_18009F832
0x18009f822  mov     rax, [rcx]
0x18009f825  mov     rax, [rax+8]
0x18009f829  call    cs:__guard_dispatch_icall_fptr
0x18009f82f  xor     r9d, r9d
0x18009f832  mov     rcx, [rbp+70h+var_F0]
0x18009f836  test    rcx, rcx
0x18009f839  jz      short loc_18009F84F
0x18009f83b  mov     [rbp+70h+var_F0], r9
0x18009f83f  mov     rax, [rcx]
0x18009f842  mov     rax, [rax+8]
0x18009f846  call    cs:__guard_dispatch_icall_fptr
0x18009f84c  xor     r9d, r9d
0x18009f84f  test    esi, esi
0x18009f851  jnz     loc_18009FA1E
0x18009f857  movzx   r9d, word ptr [r14+1Ch]
0x18009f85c  and     r9d, 0Fh; dwType
0x18009f860  mov     eax, [rsp+170h+var_128]
  ... truncated ...
```
