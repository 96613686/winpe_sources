# PushButtonReset::Path::GetDrive(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort *)

- ea: `0x18004d8d0`
- end: `0x18004db7e`
- name: `?GetDrive@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAG@Z`
- size: `686`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x180019724`
- `0x180057ecc`

## callees

- `0x180003c68`
- `0x1800049a4`
- `0x180004af8`
- `0x180005cb0`
- `0x1800066f8`
- `0x18000d6f0`
- `0x18000d92c`
- `0x180033b18`
- `0x180037344`
- `0x18004d8d0`
- `0x18004e5a4`
- `0x18006c652`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004d97a`
- `KERNEL32!GetLastError` at `0x18004d987`
- `KERNEL32!GetLastError` at `0x18004d9ce`
- `KERNEL32!GetLastError` at `0x18004da4b`
- `KERNEL32!GetLastError` at `0x18004da92`
- `KERNEL32!GetLastError` at `0x18004d97a`
- `KERNEL32!GetLastError` at `0x18004d987`
- `KERNEL32!GetLastError` at `0x18004d9ce`
- `KERNEL32!GetLastError` at `0x18004da4b`
- `KERNEL32!GetLastError` at `0x18004da92`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18004d970`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18004da41`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18004d970`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18004da41`

## string_xrefs

- `0x18004d92b`: `PushButtonReset::Path::GetDrive`
- `0x18004d9bb`: `PushButtonReset::Path::GetDrive`
- `0x18004da7f`: `PushButtonReset::Path::GetDrive`
- `0x18004d9a0`: `Failed to query path names for [%s]`
- `0x18004da64`: `Failed to read path names for [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PushButtonReset::Path::GetDrive(_QWORD *a1, _WORD *a2)
{
  unsigned int Volume; // edi
  const WCHAR *v5; // rbx
  signed int v6; // eax
  signed int v7; // eax
  DWORD v8; // edi
  void *v9; // rax
  DWORD v10; // edi
  WCHAR *v11; // rax
  signed int LastError; // eax
  signed int v13; // eax
  _WORD *i; // rdi
  __int64 v15; // rcx
  __int64 v16; // rax
  LPCWSTR lpszVolumeName; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v19[3]; // [rsp+48h] [rbp-18h] BYREF
  DWORD cchReturnLength; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v21; // [rsp+A8h] [rbp+48h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpszVolumeName);
  Volume = PushButtonReset::Path::GetVolume(a1, &lpszVolumeName);
  if ( (Volume & 0x80000000) == 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpszVolumeName, L"\\", 1);
    cchReturnLength = 0;
    v5 = lpszVolumeName;
    if ( GetVolumePathNamesForVolumeNameW(lpszVolumeName, 0, 0, &cchReturnLength) || GetLastError() == 234 )
    {
      v8 = 2 * cchReturnLength + 2;
      v19[1] = PbrHeapAlloc<void>(v8);
      v19[0] = &RAII::CAutoPbrHeapFree<unsigned short *>::`vftable';
      v9 = (void *)RAII::CAutoCleanupBase<void *>::operator->(v19);
      memset_0(v9, 0, v8);
      v10 = cchReturnLength;
      v11 = (WCHAR *)(*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 32LL))(v19);
      if ( GetVolumePathNamesForVolumeNameW(v5, v11, v10, &cchReturnLength) )
      {
        for ( i = (_WORD *)(*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 32LL))(v19); *i; i += v16 + 1 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64)&v21,
            (__int64)i);
          v15 = v21;
          if ( *(int *)(v21 - 16) > 1 )
          {
            if ( (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(&v21, 1) == 58 )
            {
              *a2 = ATL::CSimpleStringT<unsigned short,0>::GetAt(&v21, 0);
              ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
              v19[0] = &RAII::CAutoPbrHeapFree<unsigned short *>::`vftable';
              RAII::CAutoPbrHeapFree<unsigned short *>::Release(v19);
              Volume = 0;
              goto LABEL_25;
            }
            v15 = v21;
          }
          ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
          v16 = -1;
          do
            ++v16;
          while ( i[v16] );
        }
        v19[0] = &RAII::CAutoPbrHeapFree<unsigned short *>::`vftable';
        RAII::CAutoPbrHeapFree<unsigned short *>::Release(v19);
        Volume = -2147023728;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)LastError,
          "PushButtonReset::Path::GetDrive",
          "base\\reset\\util\\src\\filesystem.cpp",
          1406,
          L"Failed to read path names for [%s]",
          v5);
        v13 = GetLastError();
        Volume = v13;
        if ( v13 > 0 )
          Volume = (unsigned __int16)v13 | 0x80070000;
        v19[0] = &RAII::CAutoPbrHeapFree<unsigned short *>::`vftable';
        RAII::CAutoPbrHeapFree<unsigned short *>::Release(v19);
      }
    }
    else
    {
      v6 = GetLastError();
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v6,
        "PushButtonReset::Path::GetDrive",
        "base\\reset\\util\\src\\filesystem.cpp",
        1395,
        L"Failed to query path names for [%s]",
        v5);
      v7 = GetLastError();
      Volume = v7;
      if ( v7 > 0 )
        Volume = (unsigned __int16)v7 | 0x80070000;
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      Volume,
      "PushButtonReset::Path::GetDrive",
      "base\\reset\\util\\src\\filesystem.cpp",
      1385,
      L"Failed to get host volume for [%s]",
      *a1);
    v5 = lpszVolumeName;
  }
LABEL_25:
  ATL::CStringData::Release((ATL::CStringData *)(v5 - 12));
  return Volume;
}

```

## disassembly

```asm
0x18004d8d0  mov     [rsp-28h+arg_0], rbx
0x18004d8d5  push    rbp
0x18004d8d6  push    rsi
0x18004d8d7  push    rdi
0x18004d8d8  push    r12
0x18004d8da  push    r14
0x18004d8dc  mov     rbp, rsp
0x18004d8df  sub     rsp, 60h
0x18004d8e3  mov     rsi, rdx
0x18004d8e6  mov     rbx, rcx
0x18004d8e9  lea     rcx, [rbp+lpszVolumeName]
0x18004d8ed  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004d8f2  nop
0x18004d8f3  lea     rdx, [rbp+lpszVolumeName]
0x18004d8f7  mov     rcx, rbx
0x18004d8fa  call    ?GetVolume@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetVolume(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004d8ff  mov     edi, eax
0x18004d901  xor     r14d, r14d
0x18004d904  test    eax, eax
0x18004d906  jns     short loc_18004D946
0x18004d908  mov     rcx, [rbx]
0x18004d90b  mov     [rsp+60h+var_30], rcx
0x18004d910  lea     rax, aFailedToGetHos_0; "Failed to get host volume for [%s]"
0x18004d917  mov     [rsp+60h+var_38], rax
0x18004d91c  mov     [rsp+60h+var_40], 569h
0x18004d924  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004d92b  lea     r8, aPushbuttonrese_88; "PushButtonReset::Path::GetDrive"
0x18004d932  mov     edx, edi
0x18004d934  lea     ecx, [r14+2]
0x18004d938  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004d93d  mov     rbx, [rbp+lpszVolumeName]
0x18004d941  jmp     loc_18004DB5F
0x18004d946  mov     r8d, 1
0x18004d94c  lea     rdx, SubBlock; "\\"
0x18004d953  lea     rcx, [rbp+lpszVolumeName]
0x18004d957  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18004d95c  mov     [rbp+cchReturnLength], r14d
0x18004d960  lea     r9, [rbp+cchReturnLength]; lpcchReturnLength
0x18004d964  xor     r8d, r8d; cchBufferLength
0x18004d967  xor     edx, edx; lpszVolumePathNames
0x18004d969  mov     rbx, [rbp+lpszVolumeName]
0x18004d96d  mov     rcx, rbx; lpszVolumeName
0x18004d970  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18004d976  test    eax, eax
0x18004d978  jnz     short loc_18004D9E8
0x18004d97a  call    cs:__imp_GetLastError
0x18004d980  cmp     eax, 0EAh
0x18004d985  jz      short loc_18004D9E8
0x18004d987  call    cs:__imp_GetLastError
0x18004d98d  mov     esi, 80070000h
0x18004d992  test    eax, eax
0x18004d994  jle     short loc_18004D99B
0x18004d996  movzx   eax, ax
0x18004d999  or      eax, esi
0x18004d99b  mov     [rsp+60h+var_30], rbx
0x18004d9a0  lea     rcx, aFailedToQueryP; "Failed to query path names for [%s]"
0x18004d9a7  mov     [rsp+60h+var_38], rcx
0x18004d9ac  mov     [rsp+60h+var_40], 573h
0x18004d9b4  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004d9bb  lea     r8, aPushbuttonrese_88; "PushButtonReset::Path::GetDrive"
0x18004d9c2  mov     edx, eax
0x18004d9c4  mov     ecx, 2
0x18004d9c9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004d9ce  call    cs:__imp_GetLastError
0x18004d9d4  mov     edi, eax
0x18004d9d6  test    eax, eax
0x18004d9d8  jle     loc_18004DB5F
0x18004d9de  movzx   edi, ax
0x18004d9e1  or      edi, esi
0x18004d9e3  jmp     loc_18004DB5F
0x18004d9e8  mov     eax, [rbp+cchReturnLength]
0x18004d9eb  lea     eax, ds:2[rax*2]
0x18004d9f2  mov     edi, eax
0x18004d9f4  mov     ecx, eax
0x18004d9f6  call    ??$PbrHeapAlloc@X@@YAPEAX_K@Z; PbrHeapAlloc<void>(unsigned __int64)
0x18004d9fb  mov     [rbp+var_10], rax
0x18004d9ff  lea     r12, ??_7?$CAutoPbrHeapFree@PEAG@RAII@@6B@; const RAII::CAutoPbrHeapFree<ushort *>::`vftable'
0x18004da06  mov     [rbp+var_18], r12
0x18004da0a  lea     rcx, [rbp+var_18]
0x18004da0e  call    ??C?$CAutoCleanupBase@PEAX@RAII@@UEBAQEAXXZ; RAII::CAutoCleanupBase<void *>::operator->(void)
0x18004da13  mov     rcx, rax; void *
0x18004da16  mov     r8d, edi; Size
0x18004da19  xor     edx, edx; Val
0x18004da1b  call    memset_0
0x18004da20  mov     edi, [rbp+cchReturnLength]
0x18004da23  mov     rax, [rbp+var_18]
0x18004da27  lea     rcx, [rbp+var_18]
0x18004da2b  mov     rax, [rax+20h]
0x18004da2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da34  lea     r9, [rbp+cchReturnLength]; lpcchReturnLength
0x18004da38  mov     r8d, edi; cchBufferLength
0x18004da3b  mov     rdx, rax; lpszVolumePathNames
0x18004da3e  mov     rcx, rbx; lpszVolumeName
0x18004da41  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18004da47  test    eax, eax
0x18004da49  jnz     short loc_18004DAB5
0x18004da4b  call    cs:__imp_GetLastError
0x18004da51  mov     esi, 80070000h
0x18004da56  test    eax, eax
0x18004da58  jle     short loc_18004DA5F
0x18004da5a  movzx   eax, ax
0x18004da5d  or      eax, esi
0x18004da5f  mov     [rsp+60h+var_30], rbx
0x18004da64  lea     rcx, aFailedToReadPa; "Failed to read path names for [%s]"
0x18004da6b  mov     [rsp+60h+var_38], rcx
0x18004da70  mov     [rsp+60h+var_40], 57Eh
0x18004da78  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004da7f  lea     r8, aPushbuttonrese_88; "PushButtonReset::Path::GetDrive"
0x18004da86  mov     edx, eax
0x18004da88  mov     ecx, 2
0x18004da8d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004da92  call    cs:__imp_GetLastError
0x18004da98  mov     edi, eax
0x18004da9a  test    eax, eax
0x18004da9c  jle     short loc_18004DAA3
0x18004da9e  movzx   edi, ax
0x18004daa1  or      edi, esi
0x18004daa3  mov     [rbp+var_18], r12
0x18004daa7  lea     rcx, [rbp+var_18]
0x18004daab  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x18004dab0  jmp     loc_18004DB5F
0x18004dab5  mov     rax, [rbp+var_18]
0x18004dab9  lea     rcx, [rbp+var_18]
0x18004dabd  mov     rax, [rax+20h]
0x18004dac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dac6  mov     rdi, rax
0x18004dac9  cmp     [rdi], r14w
0x18004dacd  jz      short loc_18004DB4D
0x18004dacf  mov     rdx, rdi
0x18004dad2  lea     rcx, [rbp+arg_18]
0x18004dad6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18004dadb  nop
0x18004dadc  mov     rcx, [rbp+arg_18]
0x18004dae0  cmp     dword ptr [rcx-10h], 1
0x18004dae4  jle     short loc_18004DAFE
0x18004dae6  mov     edx, 1
0x18004daeb  lea     rcx, [rbp+arg_18]
0x18004daef  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18004daf4  cmp     ax, 3Ah ; ':'
0x18004daf8  jz      short loc_18004DB1F
0x18004dafa  mov     rcx, [rbp+arg_18]
0x18004dafe  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004db02  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004db07  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004db0b  inc     rax
0x18004db0e  cmp     [rdi+rax*2], r14w
0x18004db13  jnz     short loc_18004DB0B
0x18004db15  lea     rdi, [rdi+rax*2]
0x18004db19  add     rdi, 2
0x18004db1d  jmp     short loc_18004DAC9
0x18004db1f  xor     edx, edx
0x18004db21  lea     rcx, [rbp+arg_18]
0x18004db25  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18004db2a  mov     [rsi], ax
0x18004db2d  mov     rcx, [rbp+arg_18]
0x18004db31  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004db35  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004db3a  nop
0x18004db3b  mov     [rbp+var_18], r12
0x18004db3f  lea     rcx, [rbp+var_18]
0x18004db43  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x18004db48  mov     edi, r14d
0x18004db4b  jmp     short loc_18004DB5F
0x18004db4d  mov     [rbp+var_18], r12
0x18004db51  lea     rcx, [rbp+var_18]
0x18004db55  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x18004db5a  mov     edi, 80070490h
0x18004db5f  lea     rcx, [rbx-18h]; this
0x18004db63  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004db68  mov     eax, edi
0x18004db6a  mov     rbx, [rsp+60h+arg_0]
0x18004db72  add     rsp, 60h
0x18004db76  pop     r14
0x18004db78  pop     r12
0x18004db7a  pop     rdi
0x18004db7b  pop     rsi
0x18004db7c  pop     rbp
0x18004db7d  retn
```
