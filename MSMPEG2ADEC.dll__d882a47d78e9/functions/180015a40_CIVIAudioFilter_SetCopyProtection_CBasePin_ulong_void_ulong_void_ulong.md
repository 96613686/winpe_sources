# CIVIAudioFilter::SetCopyProtection(CBasePin *,ulong,void *,ulong,void *,ulong)

- ea: `0x180015a40`
- end: `0x18001656d`
- name: `?SetCopyProtection@CIVIAudioFilter@@AEAAJPEAVCBasePin@@KPEAXK1K@Z`
- size: `2861`
- prototype: `__int64 __fastcall(CIVIAudioFilter *__hidden this, struct CBasePin *, unsigned int, void *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180013ba0`

## callees

- `0x1800017b0`
- `0x180015a40`
- `0x180018450`
- `0x1800205b0`
- `0x180024290`
- `0x18005a530`
- `0x18005c430`
- `0x18005eaa0`
- `0x180060ca0`
- `0x180064740`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015c1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015dfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015fea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800161da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001640a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015c1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015dfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015fea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800161da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001640a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180015bff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180015ddf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180015fcf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800161bf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800163ef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180015bff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180015ddf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180015fcf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800161bf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800163ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001602b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001621b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001644b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001602b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001621b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001644b`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180015bdd`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180015dbd`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180015fad`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18001619d`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800163cd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015ada`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015cb9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015ea5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001608f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800162bf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015ada`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015cb9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015ea5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001608f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800162bf`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180015b8f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180015d6f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180015f5f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18001614f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18001637f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180015b8f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180015d6f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180015f5f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18001614f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18001637f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001651b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001651b`

## string_xrefs

- `0x180015bf8`: `ntdll.dll`
- `0x180015dd8`: `ntdll.dll`
- `0x180015fc8`: `ntdll.dll`
- `0x1800161b8`: `ntdll.dll`
- `0x1800163e8`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall CIVIAudioFilter::SetCopyProtection(
        CIVIAudioFilter *this,
        struct CBasePin *a2,
        int a3,
        void *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7)
{
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  unsigned int v13; // r15d
  const CHAR *v14; // rbx
  HANDLE FileA; // rax
  HMODULE v16; // rax
  FARPROC v17; // rax
  int v18; // ebx
  unsigned int v19; // r15d
  const CHAR *v20; // rbx
  HMODULE v21; // rax
  FARPROC v22; // rax
  unsigned int v23; // r15d
  const CHAR *v24; // rbx
  HMODULE v25; // rax
  FARPROC v26; // rax
  unsigned int v27; // r15d
  const CHAR *v28; // rbx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v31; // ebx
  unsigned int v32; // esi
  unsigned int v33; // r15d
  const CHAR *v34; // rbx
  HMODULE v35; // rax
  FARPROC v36; // rax
  _WORD v37[2]; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int8 v38[4]; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned __int8 v39; // [rsp+48h] [rbp-38h]
  int v40; // [rsp+50h] [rbp-30h] BYREF
  int v41; // [rsp+54h] [rbp-2Ch]
  int v42; // [rsp+58h] [rbp-28h]
  int v43; // [rsp+5Ch] [rbp-24h]
  int v44; // [rsp+60h] [rbp-20h]
  int v45; // [rsp+64h] [rbp-1Ch]
  int v46; // [rsp+68h] [rbp-18h]
  int v47; // [rsp+6Ch] [rbp-14h]
  char v48; // [rsp+70h] [rbp-10h]

  if ( !*((_DWORD *)this + 10) )
    return 2147746343LL;
  if ( !a6 )
    return 2147500035LL;
  v9 = a3 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( !v10 )
    {
      if ( IsDebuggerPresent() )
        goto LABEL_96;
      v40 = -1540288806;
      v27 = 0;
      v41 = -938834218;
      v42 = -626301380;
      v43 = -878431986;
      v44 = 2043543707;
      v45 = 249220523;
      v46 = -1681152975;
      v47 = 573627668;
      v48 = -50;
      while ( 1 )
      {
        v28 = (char *)&v40 + 11 * v27;
        *v28 ^= 0x86u;
        *((_BYTE *)v28 + 1) ^= 0x52u;
        *((_BYTE *)v28 + 2) ^= 0x1Fu;
        *((_BYTE *)v28 + 3) ^= 0xF8u;
        *((_BYTE *)v28 + 4) ^= 0x98u;
        *((_BYTE *)v28 + 5) ^= 0xD2u;
        *((_BYTE *)v28 + 6) ^= 0x43u;
        *((_BYTE *)v28 + 7) ^= 0x8Bu;
        *((_BYTE *)v28 + 8) ^= 0x79u;
        *((_BYTE *)v28 + 9) ^= 0x66u;
        *((_BYTE *)v28 + 10) ^= 0xCEu;
        FileA = CreateFileA(v28, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
        *v28 ^= 0x86u;
        *((_BYTE *)v28 + 1) ^= 0x52u;
        *((_BYTE *)v28 + 2) ^= 0x1Fu;
        *((_BYTE *)v28 + 3) ^= 0xF8u;
        *((_BYTE *)v28 + 4) ^= 0x98u;
        *((_BYTE *)v28 + 5) ^= 0xD2u;
        *((_BYTE *)v28 + 6) ^= 0x43u;
        *((_BYTE *)v28 + 7) ^= 0x8Bu;
        *((_BYTE *)v28 + 8) ^= 0x79u;
        *((_BYTE *)v28 + 9) ^= 0x66u;
        *((_BYTE *)v28 + 10) ^= 0xCEu;
        if ( FileA != (HANDLE)-1LL )
          goto LABEL_95;
        if ( (int)++v27 >= 3 )
        {
          if ( (_BYTE)UnhandledExceptionFilter == 0xCC )
            goto LABEL_96;
          v37[0] = 257;
          Library = LoadLibraryExA("ntdll.dll", 0, 0);
          if ( Library && (ProcAddress = GetProcAddress(Library, "NtQuerySystemInformation")) != 0 )
          {
            *(_DWORD *)v38 = -1;
            if ( !((unsigned int (__fastcall *)(__int64, _WORD *, __int64, unsigned __int8 *))ProcAddress)(
                    35,
                    v37,
                    2,
                    v38)
              && LOBYTE(v37[0]) )
            {
              goto LABEL_96;
            }
          }
          else
          {
            GetLastError();
          }
          if ( a7 < 6 )
            return 2147942487LL;
          *((_BYTE *)this + 17206) = *a6;
          *((_BYTE *)this + 17205) = a6[1];
          *((_BYTE *)this + 17204) = a6[2];
          *((_BYTE *)this + 17203) = a6[3];
          *((_BYTE *)this + 17202) = a6[4];
          if ( !(unsigned int)WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Decrypt() )
          {
            v31 = DRM_Drv_Auth(
                    *((void **)this + 2148),
                    (unsigned __int8 *)this + 17192,
                    (unsigned __int8 *)this + 17202);
            if ( !(unsigned int)WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Encrypt() )
            {
              if ( v31 )
                return 0;
              return 2147942450LL;
            }
          }
          return 2147549183LL;
        }
      }
    }
    v11 = v10 - 2;
    if ( v11 )
    {
      v12 = v11 - 3;
      if ( v12 )
      {
        if ( v12 != 121 )
          return 2147943568LL;
        if ( a7 >= 0x800 )
        {
          if ( IsDebuggerPresent() )
            goto LABEL_96;
          v40 = -1540288806;
          v13 = 0;
          v41 = -938834218;
          v42 = -626301380;
          v43 = -878431986;
          v44 = 2043543707;
          v45 = 249220523;
          v46 = -1681152975;
          v47 = 573627668;
          v48 = -50;
          while ( 1 )
          {
            v14 = (char *)&v40 + 11 * v13;
            *v14 ^= 0x86u;
            *((_BYTE *)v14 + 1) ^= 0x52u;
            *((_BYTE *)v14 + 2) ^= 0x1Fu;
            *((_BYTE *)v14 + 3) ^= 0xF8u;
            *((_BYTE *)v14 + 4) ^= 0x98u;
            *((_BYTE *)v14 + 5) ^= 0xD2u;
            *((_BYTE *)v14 + 6) ^= 0x43u;
            *((_BYTE *)v14 + 7) ^= 0x8Bu;
            *((_BYTE *)v14 + 8) ^= 0x79u;
            *((_BYTE *)v14 + 9) ^= 0x66u;
            *((_BYTE *)v14 + 10) ^= 0xCEu;
            FileA = CreateFileA(v14, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
            *v14 ^= 0x86u;
            *((_BYTE *)v14 + 1) ^= 0x52u;
            *((_BYTE *)v14 + 2) ^= 0x1Fu;
            *((_BYTE *)v14 + 3) ^= 0xF8u;
            *((_BYTE *)v14 + 4) ^= 0x98u;
            *((_BYTE *)v14 + 5) ^= 0xD2u;
            *((_BYTE *)v14 + 6) ^= 0x43u;
            *((_BYTE *)v14 + 7) ^= 0x8Bu;
            *((_BYTE *)v14 + 8) ^= 0x79u;
            *((_BYTE *)v14 + 9) ^= 0x66u;
            *((_BYTE *)v14 + 10) ^= 0xCEu;
            if ( FileA != (HANDLE)-1LL )
              goto LABEL_95;
            if ( (int)++v13 >= 3 )
            {
              if ( (_BYTE)UnhandledExceptionFilter == 0xCC )
                goto LABEL_96;
              v37[0] = 257;
              v16 = LoadLibraryExA("ntdll.dll", 0, 0);
              if ( v16 && (v17 = GetProcAddress(v16, "NtQuerySystemInformation")) != 0 )
              {
                *(_DWORD *)v38 = -1;
                if ( !((unsigned int (__fastcall *)(__int64, _WORD *, __int64, unsigned __int8 *))v17)(35, v37, 2, v38)
                  && LOBYTE(v37[0]) )
                {
                  goto LABEL_96;
                }
              }
              else
              {
                GetLastError();
              }
              *((_DWORD *)this + 4451) = 0;
              if ( !(unsigned int)WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Decrypt() )
              {
                v18 = DRM_LookupDiscKey(*((void **)this + 2148), a6);
                if ( !(unsigned int)WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Encrypt() )
                {
                  if ( !v18 )
                    *((_DWORD *)this + 4451) = 1;
                  return 0;
                }
              }
              return 2147549183LL;
            }
          }
        }
      }
      else if ( a7 >= 4 )
      {
        if ( IsDebuggerPresent() )
          goto LABEL_96;
        v40 = -1540288806;
        v19 = 0;
        v41 = -938834218;
        v42 = -626301380;
        v43 = -878431986;
        v44 = 2043543707;
        v45 = 249220523;
        v46 = -1681152975;
        v47 = 573627668;
        v48 = -50;
        while ( 1 )
        {
          v20 = (char *)&v40 + 11 * v19;
          *v20 ^= 0x86u;
          *((_BYTE *)v20 + 1) ^= 0x52u;
          *((_BYTE *)v20 + 2) ^= 0x1Fu;
          *((_BYTE *)v20 + 3) ^= 0xF8u;
          *((_BYTE *)v20 + 4) ^= 0x98u;
          *((_BYTE *)v20 + 5) ^= 0xD2u;
          *((_BYTE *)v20 + 6) ^= 0x43u;
          *((_BYTE *)v20 + 7) ^= 0x8Bu;
          *((_BYTE *)v20 + 8) ^= 0x79u;
          *((_BYTE *)v20 + 9) ^= 0x66u;
          *((_BYTE *)v20 + 10) ^= 0xCEu;
          FileA = CreateFileA(v20, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
          *v20 ^= 0x86u;
          *((_BYTE *)v20 + 1) ^= 0x52u;
          *((_BYTE *)v20 + 2) ^= 0x1Fu;
          *((_BYTE *)v20 + 3) ^= 0xF8u;
          *((_BYTE *)v20 + 4) ^= 0x98u;
          *((_BYTE *)v20 + 5) ^= 0xD2u;
          *((_BYTE *)v20 + 6) ^= 0x43u;
          *((_BYTE *)v20 + 7) ^= 0x8Bu;
          *((_BYTE *)v20 + 8) ^= 0x79u;
          *((_BYTE *)v20 + 9) ^= 0x66u;
          *((_BYTE *)v20 + 10) ^= 0xCEu;
          if ( FileA != (HANDLE)-1LL )
            goto LABEL_95;
          if ( (int)++v19 >= 3 )
          {
            if ( (_BYTE)UnhandledExceptionFilter == 0xCC )
              goto LABEL_96;
            v37[0] = 257;
            v21 = LoadLibraryExA("ntdll.dll", 0, 0);
            if ( v21 && (v22 = GetProcAddress(v21, "NtQuerySystemInformation")) != 0 )
            {
              *(_DWORD *)v38 = -1;
              if ( !((unsigned int (__fastcall *)(__int64, _WORD *, __int64, unsigned __int8 *))v22)(35, v37, 2, v38)
                && LOBYTE(v37[0]) )
              {
                goto LABEL_96;
              }
            }
            else
            {
              GetLastError();
            }
            switch ( *(_DWORD *)a6 )
            {
              case 0:
                goto LABEL_45;
              case 1:
                return 0;
              case 2:
LABEL_45:
                *((_DWORD *)this + 4306) = 0;
                return 0;
              case 3:
                return 0;
              case 4:
                *((_DWORD *)this + 4306) = 1;
                return 0;
            }
            return 2147943568LL;
          }
        }
      }
      return 2147942487LL;
    }
    if ( a7 < 0x14 )
      return 2147942487LL;
    if ( *((_DWORD *)this + 4451) )
      return 2147942450LL;
    if ( IsDebuggerPresent() )
      goto LABEL_96;
    v40 = -1540288806;
    v23 = 0;
    v41 = -938834218;
    v42 = -626301380;
    v43 = -878431986;
    v44 = 2043543707;
    v45 = 249220523;
    v46 = -1681152975;
    v47 = 573627668;
    v48 = -50;
    while ( 1 )
    {
      v24 = (char *)&v40 + 11 * v23;
      *v24 ^= 0x86u;
      *((_BYTE *)v24 + 1) ^= 0x52u;
      *((_BYTE *)v24 + 2) ^= 0x1Fu;
      *((_BYTE *)v24 + 3) ^= 0xF8u;
      *((_BYTE *)v24 + 4) ^= 0x98u;
      *((_BYTE *)v24 + 5) ^= 0xD2u;
      *((_BYTE *)v24 + 6) ^= 0x43u;
      *((_BYTE *)v24 + 7) ^= 0x8Bu;
      *((_BYTE *)v24 + 8) ^= 0x79u;
      *((_BYTE *)v24 + 9) ^= 0x66u;
      *((_BYTE *)v24 + 10) ^= 0xCEu;
      FileA = CreateFileA(v24, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
      *v24 ^= 0x86u;
      *((_BYTE *)v24 + 1) ^= 0x52u;
      *((_BYTE *)v24 + 2) ^= 0x1Fu;
      *((_BYTE *)v24 + 3) ^= 0xF8u;
      *((_BYTE *)v24 + 4) ^= 0x98u;
      *((_BYTE *)v24 + 5) ^= 0xD2u;
      *((_BYTE *)v24 + 6) ^= 0x43u;
      *((_BYTE *)v24 + 7) ^= 0x8Bu;
      *((_BYTE *)v24 + 8) ^= 0x79u;
      *((_BYTE *)v24 + 9) ^= 0x66u;
      *((_BYTE *)v24 + 10) ^= 0xCEu;
      if ( FileA != (HANDLE)-1LL )
        break;
      if ( (int)++v23 >= 3 )
      {
        if ( (_BYTE)UnhandledExceptionFilter == 0xCC )
          goto LABEL_96;
        v37[0] = 257;
        v25 = LoadLibraryExA("ntdll.dll", 0, 0);
        if ( v25 && (v26 = GetProcAddress(v25, "NtQuerySystemInformation")) != 0 )
        {
          *(_DWORD *)v38 = -1;
          if ( !((unsigned int (__fastcall *)(__int64, _WORD *, __int64, unsigned __int8 *))v26)(35, v37, 2, v38)
            && LOBYTE(v37[0]) )
          {
            goto LABEL_96;
          }
        }
        else
        {
          GetLastError();
        }
        v39 = a6[12];
        v38[3] = a6[13];
        v38[2] = a6[14];
        v38[1] = a6[15];
        v38[0] = a6[16];
        if ( !(unsigned int)WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Decrypt() )
        {
          DRM_LookupTitleKey(*((void **)this + 2148), v38);
          if ( !(unsigned int)WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Encrypt() )
            return 0;
        }
        return 2147549183LL;
      }
    }
  }
  else
  {
    if ( a7 < 0xC )
      return 2147942487LL;
    if ( IsDebuggerPresent() )
      goto LABEL_96;
    v32 = 0;
    v40 = -1540288806;
    v33 = 0;
    v41 = -938834218;
    v42 = -626301380;
    v43 = -878431986;
    v44 = 2043543707;
    v45 = 249220523;
    v46 = -1681152975;
    v47 = 573627668;
    v48 = -50;
    while ( 1 )
    {
      v34 = (char *)&v40 + 11 * v33;
      *v34 ^= 0x86u;
      *((_BYTE *)v34 + 1) ^= 0x52u;
      *((_BYTE *)v34 + 2) ^= 0x1Fu;
      *((_BYTE *)v34 + 3) ^= 0xF8u;
      *((_BYTE *)v34 + 4) ^= 0x98u;
      *((_BYTE *)v34 + 5) ^= 0xD2u;
      *((_BYTE *)v34 + 6) ^= 0x43u;
      *((_BYTE *)v34 + 7) ^= 0x8Bu;
      *((_BYTE *)v34 + 8) ^= 0x79u;
      *((_BYTE *)v34 + 9) ^= 0x66u;
      *((_BYTE *)v34 + 10) ^= 0xCEu;
      FileA = CreateFileA(v34, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
      *v34 ^= 0x86u;
      *((_BYTE *)v34 + 1) ^= 0x52u;
      *((_BYTE *)v34 + 2) ^= 0x1Fu;
      *((_BYTE *)v34 + 3) ^= 0xF8u;
      *((_BYTE *)v34 + 4) ^= 0x98u;
      *((_BYTE *)v34 + 5) ^= 0xD2u;
      *((_BYTE *)v34 + 6) ^= 0x43u;
      *((_BYTE *)v34 + 7) ^= 0x8Bu;
      *((_BYTE *)v34 + 8) ^= 0x79u;
      *((_BYTE *)v34 + 9) ^= 0x66u;
      *((_BYTE *)v34 + 10) ^= 0xCEu;
      if ( FileA != (HANDLE)-1LL )
        break;
      if ( (int)++v33 >= 3 )
      {
        if ( (_BYTE)UnhandledExceptionFilter == 0xCC )
          goto LABEL_96;
        v37[0] = 257;
        v35 = LoadLibraryExA("ntdll.dll", 0, 0);
        if ( v35 && (v36 = GetProcAddress(v35, "NtQuerySystemInformation")) != 0 )
        {
          *(_DWORD *)v38 = -1;
          if ( !((unsigned int (__fastcall *)(__int64, _WORD *, __int64, unsigned __int8 *))v36)(35, v37, 2, v38)
            && LOBYTE(v37[0]) )
          {
            goto LABEL_96;
          }
        }
        else
        {
          GetLastError();
        }
        *((_BYTE *)this + 17216) = *a6;
        *((_BYTE *)this + 17215) = a6[1];
        *((_BYTE *)this + 17214) = a6[2];
        *((_BYTE *)this + 17213) = a6[3];
        *((_BYTE *)this + 17212) = a6[4];
        *((_BYTE *)this + 17211) = a6[5];
        *((_BYTE *)this + 17210) = a6[6];
        *((_BYTE *)this + 17209) = a6[7];
        *((_BYTE *)this + 17208) = a6[8];
        *((_BYTE *)this + 17207) = a6[9];
        if ( (unsigned int)WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Decrypt() )
          return 2147549183LL;
        DRM_Dec_Auth(*((void **)this + 2148), (unsigned __int8 *)this + 17207, (unsigned __int8 *)this + 17217);
        DRM_Key_Share(*((void **)this + 2148), (unsigned __int8 *)this + 17202, (unsigned __int8 *)this + 17217);
        if ( (unsigned int)WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Encrypt() )
          return (unsigned int)-2147418113;
        return v32;
      }
    }
  }
LABEL_95:
  CloseHandle(FileA);
LABEL_96:
  CMFSampleProtection::UpdateInputInfo((CMFSampleProtection *)(*((_QWORD *)this + 27) + 320LL));
  return 0;
}

```

## disassembly

```asm
0x180015a40  push    rbp
0x180015a42  push    rdi
0x180015a43  push    r14
0x180015a45  mov     rbp, rsp
0x180015a48  sub     rsp, 80h
0x180015a4f  mov     rax, cs:__security_cookie
0x180015a56  xor     rax, rsp
0x180015a59  mov     [rbp+var_8], rax
0x180015a5d  cmp     dword ptr [rcx+28h], 0
0x180015a61  mov     rdi, rcx
0x180015a64  mov     r14, [rbp+arg_28]
0x180015a68  jnz     short loc_180015A74
0x180015a6a  mov     eax, 80040227h
0x180015a6f  jmp     loc_180016554
0x180015a74  test    r14, r14
0x180015a77  jnz     short loc_180015A83
0x180015a79  mov     eax, 80004003h
0x180015a7e  jmp     loc_180016554
0x180015a83  mov     [rsp+80h+arg_8], rbx
0x180015a8b  mov     [rsp+80h+arg_10], rsi
0x180015a93  mov     [rsp+80h+arg_18], r15
0x180015a9b  sub     r8d, 1
0x180015a9f  jz      loc_1800162AF
0x180015aa5  sub     r8d, 1
0x180015aa9  jz      loc_18001608F
0x180015aaf  sub     r8d, 2
0x180015ab3  jz      loc_180015E8E
0x180015ab9  sub     r8d, 3
0x180015abd  jz      loc_180015CAF
0x180015ac3  cmp     r8d, 79h ; 'y'
0x180015ac7  jnz     loc_180015E6A
0x180015acd  cmp     [rbp+arg_30], 800h
0x180015ad4  jb      loc_1800162B5
0x180015ada  call    cs:__imp_IsDebuggerPresent
0x180015ae1  nop     dword ptr [rax+rax+00h]
0x180015ae6  test    eax, eax
0x180015ae8  jnz     loc_180016527
0x180015aee  xor     esi, esi
0x180015af0  mov     [rbp+var_30], 0A4310EDAh
0x180015af7  mov     r15d, esi
0x180015afa  mov     [rbp+var_2C], 0C80A86D6h
0x180015b01  mov     [rbp+var_28], 0DAAB663Ch
0x180015b08  mov     [rbp+var_24], 0CBA4310Eh
0x180015b0f  mov     [rbp+var_20], 79CE009Bh
0x180015b16  mov     [rbp+var_1C], 0EDACDABh
0x180015b1d  mov     [rbp+var_18], 9BCBA431h
0x180015b24  mov     [rbp+var_14], 2230DD14h
0x180015b2b  mov     [rbp+var_10], 0CEh
0x180015b2f  nop
0x180015b30  mov     eax, r15d
0x180015b33  lea     rbx, [rbp+var_30]
0x180015b37  imul    rcx, rax, 0Bh
0x180015b3b  mov     [rsp+80h+hTemplateFile], rsi; hTemplateFile
0x180015b40  xor     r9d, r9d; lpSecurityAttributes
0x180015b43  add     rbx, rcx
0x180015b46  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180015b4e  mov     edx, 0C0000000h; dwDesiredAccess
0x180015b53  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x180015b5b  mov     r8d, 3; dwShareMode
0x180015b61  mov     rcx, rbx; lpFileName
0x180015b64  xor     byte ptr [rbx], 86h
0x180015b67  xor     byte ptr [rbx+1], 52h
0x180015b6b  xor     byte ptr [rbx+2], 1Fh
0x180015b6f  xor     byte ptr [rbx+3], 0F8h
0x180015b73  xor     byte ptr [rbx+4], 98h
0x180015b77  xor     byte ptr [rbx+5], 0D2h
0x180015b7b  xor     byte ptr [rbx+6], 43h
0x180015b7f  xor     byte ptr [rbx+7], 8Bh
0x180015b83  xor     byte ptr [rbx+8], 79h
0x180015b87  xor     byte ptr [rbx+9], 66h
0x180015b8b  xor     byte ptr [rbx+0Ah], 0CEh
0x180015b8f  call    cs:__imp_CreateFileA
0x180015b96  nop     dword ptr [rax+rax+00h]
0x180015b9b  xor     byte ptr [rbx], 86h
0x180015b9e  xor     byte ptr [rbx+1], 52h
0x180015ba2  xor     byte ptr [rbx+2], 1Fh
0x180015ba6  xor     byte ptr [rbx+3], 0F8h
0x180015baa  xor     byte ptr [rbx+4], 98h
0x180015bae  xor     byte ptr [rbx+5], 0D2h
0x180015bb2  xor     byte ptr [rbx+6], 43h
0x180015bb6  xor     byte ptr [rbx+7], 8Bh
0x180015bba  xor     byte ptr [rbx+8], 79h
0x180015bbe  xor     byte ptr [rbx+9], 66h
0x180015bc2  xor     byte ptr [rbx+0Ah], 0CEh
0x180015bc6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015bca  jnz     loc_180016518
0x180015bd0  inc     r15d
0x180015bd3  cmp     r15d, 3
0x180015bd7  jl      loc_180015B30
0x180015bdd  mov     rax, cs:__imp_UnhandledExceptionFilter
0x180015be4  cmp     byte ptr [rax], 0CCh
0x180015be7  jz      loc_180016527
0x180015bed  xor     r8d, r8d; dwFlags
0x180015bf0  mov     [rbp+var_40], 101h
0x180015bf6  xor     edx, edx; hFile
0x180015bf8  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180015bff  call    cs:__imp_LoadLibraryExA
0x180015c06  nop     dword ptr [rax+rax+00h]
0x180015c0b  test    rax, rax
0x180015c0e  jz      short loc_180015C5B
0x180015c10  lea     rdx, aNtquerysystemi; "NtQuerySystemInformation"
0x180015c17  mov     rcx, rax; hModule
0x180015c1a  call    cs:__imp_GetProcAddress
0x180015c21  nop     dword ptr [rax+rax+00h]
0x180015c26  test    rax, rax
0x180015c29  jz      short loc_180015C5B
0x180015c2b  lea     r9, [rbp+var_3C]
0x180015c2f  mov     dword ptr [rbp+var_3C], 0FFFFFFFFh
0x180015c36  mov     r8d, 2
0x180015c3c  lea     rdx, [rbp+var_40]
0x180015c40  mov     ecx, 23h ; '#'
0x180015c45  call    cs:__guard_dispatch_icall_fptr
0x180015c4b  test    eax, eax
0x180015c4d  jnz     short loc_180015C67
0x180015c4f  cmp     byte ptr [rbp+var_40], sil
0x180015c53  jnz     loc_180016527
0x180015c59  jmp     short loc_180015C67
0x180015c5b  call    cs:__imp_GetLastError
0x180015c62  nop     dword ptr [rax+rax+00h]
0x180015c67  mov     [rdi+458Ch], esi
0x180015c6d  call    ?Decrypt@?$CEncryption@$01V?$CCipherFeistel64@$0A@$0GD@$0FH@$0OH@$0BF@$0LC@$0LB@$0BN@$0N@$0DK@$0FJ@$0ID@$0BB@$0LD@$0OK@$0FA@$0BD@$0LL@$0MF@$0MH@$02$0EA@$0JO@$01$01$0PL@$0GM@$0KE@$0P@$0LK@$0EI@$0NL@$0BC@$09$0CK@$0LM@$0BO@$0GO@$0HK@$0DC@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$00$0BKGBKNDEJDGFEBEE@@2@UENCRYPTED_SEGMENT_DATA_CONST_3@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_3@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_3@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_3@2@@Z; WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Decrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3 *)
0x180015c72  test    eax, eax
0x180015c74  jnz     loc_180016085
0x180015c7a  mov     rcx, [rdi+4320h]; void *
0x180015c81  mov     rdx, r14; unsigned __int8 *
0x180015c84  call    ?DRM_LookupDiscKey@@YAHPEAXPEAE@Z; DRM_LookupDiscKey(void *,uchar *)
0x180015c89  mov     ebx, eax
0x180015c8b  call    ?Encrypt@?$CEncryption@$01V?$CCipherFeistel64@$0A@$0GD@$0FH@$0OH@$0BF@$0LC@$0LB@$0BN@$0N@$0DK@$0FJ@$0ID@$0BB@$0LD@$0OK@$0FA@$0BD@$0LL@$0MF@$0MH@$02$0EA@$0JO@$01$01$0PL@$0GM@$0KE@$0P@$0LK@$0EI@$0NL@$0BC@$09$0CK@$0LM@$0BO@$0GO@$0HK@$0DC@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$00$0BKGBKNDEJDGFEBEE@@2@UENCRYPTED_SEGMENT_DATA_CONST_3@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_3@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_3@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_3@2@@Z; WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Encrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3 *)
0x180015c90  test    eax, eax
0x180015c92  jnz     loc_180016085
0x180015c98  test    ebx, ebx
0x180015c9a  jnz     loc_18001653A
0x180015ca0  mov     dword ptr [rdi+458Ch], 1
0x180015caa  jmp     loc_18001653A
0x180015caf  cmp     [rbp+arg_30], 4
0x180015cb3  jb      loc_1800162B5
0x180015cb9  call    cs:__imp_IsDebuggerPresent
0x180015cc0  nop     dword ptr [rax+rax+00h]
0x180015cc5  test    eax, eax
0x180015cc7  jnz     loc_180016527
0x180015ccd  xor     esi, esi
0x180015ccf  mov     [rbp+var_30], 0A4310EDAh
0x180015cd6  mov     r15d, esi
0x180015cd9  mov     [rbp+var_2C], 0C80A86D6h
0x180015ce0  mov     [rbp+var_28], 0DAAB663Ch
0x180015ce7  mov     [rbp+var_24], 0CBA4310Eh
0x180015cee  mov     [rbp+var_20], 79CE009Bh
0x180015cf5  mov     [rbp+var_1C], 0EDACDABh
0x180015cfc  mov     [rbp+var_18], 9BCBA431h
0x180015d03  mov     [rbp+var_14], 2230DD14h
0x180015d0a  mov     [rbp+var_10], 0CEh
0x180015d0e  xchg    ax, ax
0x180015d10  mov     eax, r15d
0x180015d13  lea     rbx, [rbp+var_30]
0x180015d17  imul    rcx, rax, 0Bh
0x180015d1b  mov     [rsp+80h+hTemplateFile], rsi; hTemplateFile
0x180015d20  xor     r9d, r9d; lpSecurityAttributes
0x180015d23  add     rbx, rcx
0x180015d26  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180015d2e  mov     edx, 0C0000000h; dwDesiredAccess
0x180015d33  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x180015d3b  mov     r8d, 3; dwShareMode
0x180015d41  mov     rcx, rbx; lpFileName
0x180015d44  xor     byte ptr [rbx], 86h
0x180015d47  xor     byte ptr [rbx+1], 52h
0x180015d4b  xor     byte ptr [rbx+2], 1Fh
0x180015d4f  xor     byte ptr [rbx+3], 0F8h
0x180015d53  xor     byte ptr [rbx+4], 98h
0x180015d57  xor     byte ptr [rbx+5], 0D2h
0x180015d5b  xor     byte ptr [rbx+6], 43h
0x180015d5f  xor     byte ptr [rbx+7], 8Bh
0x180015d63  xor     byte ptr [rbx+8], 79h
0x180015d67  xor     byte ptr [rbx+9], 66h
0x180015d6b  xor     byte ptr [rbx+0Ah], 0CEh
0x180015d6f  call    cs:__imp_CreateFileA
0x180015d76  nop     dword ptr [rax+rax+00h]
0x180015d7b  xor     byte ptr [rbx], 86h
0x180015d7e  xor     byte ptr [rbx+1], 52h
0x180015d82  xor     byte ptr [rbx+2], 1Fh
0x180015d86  xor     byte ptr [rbx+3], 0F8h
0x180015d8a  xor     byte ptr [rbx+4], 98h
0x180015d8e  xor     byte ptr [rbx+5], 0D2h
0x180015d92  xor     byte ptr [rbx+6], 43h
0x180015d96  xor     byte ptr [rbx+7], 8Bh
0x180015d9a  xor     byte ptr [rbx+8], 79h
0x180015d9e  xor     byte ptr [rbx+9], 66h
0x180015da2  xor     byte ptr [rbx+0Ah], 0CEh
0x180015da6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015daa  jnz     loc_180016518
0x180015db0  inc     r15d
0x180015db3  cmp     r15d, 3
0x180015db7  jl      loc_180015D10
0x180015dbd  mov     rax, cs:__imp_UnhandledExceptionFilter
0x180015dc4  cmp     byte ptr [rax], 0CCh
0x180015dc7  jz      loc_180016527
0x180015dcd  xor     r8d, r8d; dwFlags
0x180015dd0  mov     [rbp+var_40], 101h
0x180015dd6  xor     edx, edx; hFile
0x180015dd8  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180015ddf  call    cs:__imp_LoadLibraryExA
0x180015de6  nop     dword ptr [rax+rax+00h]
0x180015deb  test    rax, rax
0x180015dee  jz      short loc_180015E3B
0x180015df0  lea     rdx, aNtquerysystemi; "NtQuerySystemInformation"
0x180015df7  mov     rcx, rax; hModule
0x180015dfa  call    cs:__imp_GetProcAddress
0x180015e01  nop     dword ptr [rax+rax+00h]
0x180015e06  test    rax, rax
0x180015e09  jz      short loc_180015E3B
0x180015e0b  lea     r9, [rbp+var_3C]
0x180015e0f  mov     dword ptr [rbp+var_3C], 0FFFFFFFFh
0x180015e16  mov     r8d, 2
0x180015e1c  lea     rdx, [rbp+var_40]
0x180015e20  mov     ecx, 23h ; '#'
0x180015e25  call    cs:__guard_dispatch_icall_fptr
0x180015e2b  test    eax, eax
0x180015e2d  jnz     short loc_180015E47
0x180015e2f  cmp     byte ptr [rbp+var_40], sil
0x180015e33  jnz     loc_180016527
0x180015e39  jmp     short loc_180015E47
0x180015e3b  call    cs:__imp_GetLastError
0x180015e42  nop     dword ptr [rax+rax+00h]
0x180015e47  mov     ecx, [r14]
0x180015e4a  test    ecx, ecx
0x180015e4c  jz      short loc_180015E83
0x180015e4e  sub     ecx, 1
0x180015e51  jz      loc_18001653A
0x180015e57  sub     ecx, 1
0x180015e5a  jz      short loc_180015E83
0x180015e5c  sub     ecx, 1
0x180015e5f  jz      loc_18001653A
0x180015e65  cmp     ecx, 1
0x180015e68  jz      short loc_180015E74
0x180015e6a  mov     eax, 80070490h
0x180015e6f  jmp     loc_18001653C
0x180015e74  mov     dword ptr [rdi+4348h], 1
0x180015e7e  jmp     loc_18001653A
0x180015e83  mov     [rdi+4348h], esi
0x180015e89  jmp     loc_18001653A
0x180015e8e  cmp     [rbp+arg_30], 14h
0x180015e92  jb      loc_1800162B5
0x180015e98  cmp     dword ptr [rcx+458Ch], 0
0x180015e9f  jnz     loc_1800162A5
0x180015ea5  call    cs:__imp_IsDebuggerPresent
0x180015eac  nop     dword ptr [rax+rax+00h]
0x180015eb1  test    eax, eax
0x180015eb3  jnz     loc_180016527
0x180015eb9  xor     esi, esi
0x180015ebb  mov     [rbp+var_30], 0A4310EDAh
0x180015ec2  mov     r15d, esi
0x180015ec5  mov     [rbp+var_2C], 0C80A86D6h
0x180015ecc  mov     [rbp+var_28], 0DAAB663Ch
0x180015ed3  mov     [rbp+var_24], 0CBA4310Eh
0x180015eda  mov     [rbp+var_20], 79CE009Bh
0x180015ee1  mov     [rbp+var_1C], 0EDACDABh
0x180015ee8  mov     [rbp+var_18], 9BCBA431h
0x180015eef  mov     [rbp+var_14], 2230DD14h
0x180015ef6  mov     [rbp+var_10], 0CEh
0x180015efa  nop     word ptr [rax+rax+00h]
0x180015f00  mov     eax, r15d
0x180015f03  lea     rbx, [rbp+var_30]
0x180015f07  imul    rcx, rax, 0Bh
0x180015f0b  mov     [rsp+80h+hTemplateFile], rsi; hTemplateFile
0x180015f10  xor     r9d, r9d; lpSecurityAttributes
0x180015f13  add     rbx, rcx
0x180015f16  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180015f1e  mov     edx, 0C0000000h; dwDesiredAccess
0x180015f23  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x180015f2b  mov     r8d, 3; dwShareMode
0x180015f31  mov     rcx, rbx; lpFileName
0x180015f34  xor     byte ptr [rbx], 86h
0x180015f37  xor     byte ptr [rbx+1], 52h
0x180015f3b  xor     byte ptr [rbx+2], 1Fh
0x180015f3f  xor     byte ptr [rbx+3], 0F8h
0x180015f43  xor     byte ptr [rbx+4], 98h
0x180015f47  xor     byte ptr [rbx+5], 0D2h
0x180015f4b  xor     byte ptr [rbx+6], 43h
0x180015f4f  xor     byte ptr [rbx+7], 8Bh
0x180015f53  xor     byte ptr [rbx+8], 79h
0x180015f57  xor     byte ptr [rbx+9], 66h
0x180015f5b  xor     byte ptr [rbx+0Ah], 0CEh
0x180015f5f  call    cs:__imp_CreateFileA
0x180015f66  nop     dword ptr [rax+rax+00h]
0x180015f6b  xor     byte ptr [rbx], 86h
0x180015f6e  xor     byte ptr [rbx+1], 52h
0x180015f72  xor     byte ptr [rbx+2], 1Fh
0x180015f76  xor     byte ptr [rbx+3], 0F8h
0x180015f7a  xor     byte ptr [rbx+4], 98h
0x180015f7e  xor     byte ptr [rbx+5], 0D2h
0x180015f82  xor     byte ptr [rbx+6], 43h
0x180015f86  xor     byte ptr [rbx+7], 8Bh
0x180015f8a  xor     byte ptr [rbx+8], 79h
0x180015f8e  xor     byte ptr [rbx+9], 66h
0x180015f92  xor     byte ptr [rbx+0Ah], 0CEh
0x180015f96  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015f9a  jnz     loc_180016518
0x180015fa0  inc     r15d
0x180015fa3  cmp     r15d, 3
0x180015fa7  jl      loc_180015F00
0x180015fad  mov     rax, cs:__imp_UnhandledExceptionFilter
  ... truncated ...
```
