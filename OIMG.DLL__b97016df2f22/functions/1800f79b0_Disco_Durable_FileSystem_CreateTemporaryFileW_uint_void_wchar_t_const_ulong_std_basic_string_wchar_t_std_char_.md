# Disco::Durable::FileSystem::CreateTemporaryFileW(uint,void * &,wchar_t const *,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,ulong)

- ea: `0x1800f79b0`
- end: `0x1800f7f0e`
- name: `?CreateTemporaryFileW@FileSystem@Durable@Disco@@UEAAKIAEAPEAXPEB_WKPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z`
- size: `1374`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x180012aa0`
- `0x180012ccc`
- `0x1800dd938`
- `0x1800dd9bc`
- `0x1800de8a8`
- `0x1800ec6f4`
- `0x1800ed8a8`
- `0x1800f0020`
- `0x1800f1528`
- `0x1800f1780`
- `0x1800f79b0`
- `0x18056bd00`
- `0x18056d14c`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800f7a00`
- `KERNEL32!SetLastError` at `0x1800f7a00`
- `KERNEL32!GetLastError` at `0x1800f7bc7`
- `KERNEL32!GetLastError` at `0x1800f7bc7`
- `KERNEL32!CreateDirectoryW` at `0x1800f7b1e`
- `KERNEL32!CreateDirectoryW` at `0x1800f7b1e`
- `KERNEL32!GetTempFileNameW` at `0x1800f7bbb`
- `KERNEL32!GetTempFileNameW` at `0x1800f7bbb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800f7b01`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800f7e83`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800f7b01`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800f7e83`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800f7af7`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800f7e7c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800f7af7`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800f7e7c`

## string_xrefs

- `0x1800f7d8d`: `CreateTemporaryFileW failed to create the temp file name`
- `0x1800f7eb5`: `CreateTemporaryFileW succeeded`
- `0x1800f7a77`: `CreateTemporaryFileW failed to get the temp path`
- `0x1800f7c02`: `CreateTemporaryFileW failed to get the temp file name`

## pseudocode

```c
__int64 __fastcall Disco::Durable::FileSystem::CreateTemporaryFileW(
        __int64 a1,
        unsigned int a2,
        const char *a3,
        void **a4,
        int a5,
        __int64 a6,
        int a7)
{
  Storage *v10; // rcx
  unsigned int v11; // eax
  int v12; // edx
  unsigned int v13; // ebx
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  void *v16; // rdx
  void **v18; // rcx
  __int64 v19; // r15
  void **v20; // rbx
  int v21; // eax
  int v22; // eax
  int v23; // edx
  DWORD LastError; // ebx
  unsigned int v25; // r8d
  unsigned int StorageErrorAndReturn; // eax
  __int64 v27; // rax
  int v28; // edx
  unsigned int v29; // ebx
  unsigned int v30; // r8d
  __int64 v31; // r8
  __int128 v32; // xmm2
  __int128 v33; // xmm3
  void *v34; // rcx
  const char *v35; // [rsp+50h] [rbp-B0h] BYREF
  void **v36; // [rsp+58h] [rbp-A8h] BYREF
  char **v37; // [rsp+60h] [rbp-A0h]
  __int64 v38; // [rsp+68h] [rbp-98h]
  const char *v39; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v40[8]; // [rsp+78h] [rbp-88h] BYREF
  char v41; // [rsp+B8h] [rbp-48h]
  __int128 v42; // [rsp+C0h] [rbp-40h]
  void *Block[2]; // [rsp+D0h] [rbp-30h] BYREF
  __m128i si128; // [rsp+E0h] [rbp-20h]
  void *v45[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v46; // [rsp+100h] [rbp+0h]
  WCHAR TempFileName[264]; // [rsp+110h] [rbp+10h] BYREF

  v39 = a3;
  Storage::Oscilloscope::Record(0x1F345847u, 0);
  SetLastError(0);
  Storage::ClearLastStorageError(v10);
  *(_OWORD *)Block = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Block[0]) = 0;
  if ( a4 )
  {
LABEL_12:
    v19 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    while ( 1 )
    {
      while ( 1 )
      {
        memset_0(TempFileName, 0, 0x20Au);
        if ( a4 )
        {
          v20 = a4;
        }
        else
        {
          v20 = Block;
          if ( si128.m128i_i64[1] > 7uLL )
            v20 = (void **)Block[0];
        }
        v21 = *(_DWORD *)(v19 + 528);
        if ( (v21 & 1) == 0 )
        {
          *(_DWORD *)(v19 + 528) = v21 | 1;
          *(_OWORD *)(v19 + 496) = 0;
          *(_OWORD *)(v19 + 512) = 0;
          Storage::Random::Local::Local((Storage::Random::Local *)(v19 + 496));
        }
        v35 = (const char *)(v19 + 496);
        v22 = std::_Rng_from_urng_v2<unsigned __int64,Storage::Random::Implementation::Xoshiro256>::operator()(
                &v35,
                0xFFFFFFFFLL);
        if ( GetTempFileNameW((LPCWSTR)v20, L"DSC", v22 + 1, TempFileName) )
          break;
        LastError = GetLastError();
        if ( LastError == 267 )
          LastError = 3;
        if ( LastError != 80 )
        {
          v36 = &Storage::Trace::Value::Win32Error::`vftable';
          v37 = Storage::Trace::Value::Win32Error::c_default;
          LODWORD(v38) = LastError;
          v35 = "CreateTemporaryFileW failed to get the temp file name";
          sub_1800F1528(508913174, v23, 15, (unsigned int)&v35, (__int64)&v36);
          StorageErrorAndReturn = Storage::SetLastStorageErrorAndReturn((Storage *)0x1E5128C6, LastError, v25);
LABEL_34:
          v15 = StorageErrorAndReturn;
          std::wstring::~wstring(Block);
          return v15;
        }
      }
      _InterlockedIncrement(&Storage::Oscilloscope::s_skipping);
      if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, WCHAR *))(*(_QWORD *)a1 + 80LL))(a1, a2, TempFileName) == 2 )
      {
        v29 = (*(__int64 (__fastcall **)(__int64, _QWORD, const char *, WCHAR *, int, int, int, int))(*(_QWORD *)a1 + 24LL))(
                a1,
                a2,
                v39,
                TempFileName,
                -1073676288,
                a7,
                1,
                a5);
        if ( !v29 )
        {
          if ( a6 )
          {
            *(_OWORD *)v45 = 0;
            v46 = 0;
            v31 = -1;
            do
              ++v31;
            while ( TempFileName[v31] );
            std::wstring::_Construct<1,wchar_t *>(v45, TempFileName, v31);
            if ( v45 != (void **)a6 )
            {
              v32 = *(_OWORD *)v45;
              v33 = v46;
              *(_OWORD *)v45 = *(_OWORD *)a6;
              v46 = *(_OWORD *)(a6 + 16);
              *(_OWORD *)a6 = v32;
              *(_OWORD *)(a6 + 16) = v33;
            }
            if ( *((_QWORD *)&v46 + 1) > 7u )
            {
              v34 = v45[0];
              if ( (unsigned __int64)(2LL * *((_QWORD *)&v46 + 1) + 2) >= 0x1000 )
              {
                v34 = (void *)*((_QWORD *)v45[0] - 1);
                if ( (unsigned __int64)((char *)v45[0] - (char *)v34 - 8) > 0x1F )
                  _invoke_watson(0, 0, 0, 0, 0);
              }
              free(v34);
            }
          }
          _InterlockedDecrement(&Storage::Oscilloscope::s_skipping);
          v36 = &Storage::Trace::Value::Handle::`vftable';
          v37 = Storage::Trace::Value::Handle::c_default;
          v38 = *(_QWORD *)v39;
          v35 = "CreateTemporaryFileW succeeded";
          sub_1800F1528(508913171, v28, 200, (unsigned int)&v35, (__int64)&v36);
          std::wstring::~wstring(Block);
          return 0;
        }
        if ( v29 != 183 && v29 != 80 && v29 != 5 )
        {
          v36 = &Storage::Trace::Value::Win32Error::`vftable';
          v37 = Storage::Trace::Value::Win32Error::c_default;
          LODWORD(v38) = v29;
          v35 = "CreateTemporaryFileW failed to create the temp file name";
          sub_1800F1528(508913172, v28, 15, (unsigned int)&v35, (__int64)&v36);
          StorageErrorAndReturn = Storage::SetLastStorageErrorAndReturn((Storage *)0x1E5128C5, v29, v30);
          _InterlockedDecrement(&Storage::Oscilloscope::s_skipping);
          goto LABEL_34;
        }
      }
      else
      {
        v40[0] = &Storage::Trace::Value::GenericPath::`vftable';
        v40[1] = &Storage::Trace::Value::GenericPath::c_path;
        v27 = -1;
        do
          ++v27;
        while ( TempFileName[v27] );
        v40[2] = TempFileName;
        v40[3] = v27;
        v41 = 0;
        v42 = 0;
        v36 = &Storage::Trace::Value::Tag::`vftable';
        v37 = Storage::Trace::Value::Tag::c_default;
        LODWORD(v38) = a2;
        v35 = "DoesFileExistW failed , trying again";
        sub_1800F1780(508913173, 2193, 200, (unsigned int)&v35, (__int64)&v36, (__int64)v40);
        Storage::Trace::Value::GenericPath::~GenericPath((Storage::Trace::Value::GenericPath *)v40);
      }
      _InterlockedDecrement(&Storage::Oscilloscope::s_skipping);
    }
  }
  _InterlockedIncrement(&Storage::Oscilloscope::s_skipping);
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)a1 + 152LL))(a1, a2, Block);
  v13 = v11;
  if ( !v11 )
  {
    v18 = Block;
    if ( si128.m128i_i64[1] > 7uLL )
      v18 = (void **)Block[0];
    CreateDirectoryW((LPCWSTR)v18, 0);
    _InterlockedDecrement(&Storage::Oscilloscope::s_skipping);
    goto LABEL_12;
  }
  v36 = &Storage::Trace::Value::Win32Error::`vftable';
  v37 = Storage::Trace::Value::Win32Error::c_default;
  LODWORD(v38) = v11;
  v39 = "CreateTemporaryFileW failed to get the temp path";
  sub_1800F1528(508913175, v12, 15, (unsigned int)&v39, (__int64)&v36);
  v15 = Storage::SetLastStorageErrorAndReturn((Storage *)0x1E5128C7, v13, v14);
  _InterlockedDecrement(&Storage::Oscilloscope::s_skipping);
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v16 = Block[0];
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v16 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v16 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v16);
  }
  return v15;
}

```

## disassembly

```asm
0x1800f79b0  push    rbp
0x1800f79b2  push    rbx
0x1800f79b3  push    rsi
0x1800f79b4  push    rdi
0x1800f79b5  push    r12
0x1800f79b7  push    r13
0x1800f79b9  push    r14
0x1800f79bb  push    r15
0x1800f79bd  lea     rbp, [rsp-238h]
0x1800f79c5  sub     rsp, 338h
0x1800f79cc  mov     rax, cs:__security_cookie
0x1800f79d3  xor     rax, rsp
0x1800f79d6  mov     [rbp+270h+var_50], rax
0x1800f79dd  mov     r13, r9
0x1800f79e0  mov     [rsp+370h+var_300], r8
0x1800f79e5  mov     r12d, edx
0x1800f79e8  mov     r14, rcx
0x1800f79eb  mov     rdi, [rbp+270h+arg_28]
0x1800f79f2  xor     edx, edx; __int64
0x1800f79f4  mov     ecx, 1F345847h; unsigned int
0x1800f79f9  call    ?Record@Oscilloscope@Storage@@SAXI_J@Z; Storage::Oscilloscope::Record(uint,__int64)
0x1800f79fe  xor     ecx, ecx; dwErrCode
0x1800f7a00  call    cs:__imp_SetLastError
0x1800f7a06  call    ?ClearLastStorageError@Storage@@YAXXZ; Storage::ClearLastStorageError(void)
0x1800f7a0b  xorps   xmm0, xmm0
0x1800f7a0e  movups  xmmword ptr [rbp+270h+Block], xmm0
0x1800f7a12  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800f7a1a  movdqu  [rbp+270h+var_290], xmm1
0x1800f7a1f  xor     ebx, ebx
0x1800f7a21  mov     word ptr [rbp+270h+Block], bx
0x1800f7a25  test    r13, r13
0x1800f7a28  jnz     loc_1800F7B2B
0x1800f7a2e  lock inc cs:?s_skipping@Oscilloscope@Storage@@0U?$atomic@K@std@@A; std::atomic<ulong> Storage::Oscilloscope::s_skipping
0x1800f7a35  mov     rax, [r14]
0x1800f7a38  lea     r8, [rbp+270h+Block]
0x1800f7a3c  mov     edx, r12d
0x1800f7a3f  mov     rcx, r14
0x1800f7a42  mov     rax, [rax+98h]
0x1800f7a49  call    cs:__guard_dispatch_icall_fptr
0x1800f7a4f  mov     ebx, eax
0x1800f7a51  xor     esi, esi
0x1800f7a53  test    eax, eax
0x1800f7a55  jz      loc_1800F7B0E
0x1800f7a5b  lea     rcx, ??_7Win32Error@Value@Trace@Storage@@6B@; const Storage::Trace::Value::Win32Error::`vftable'
0x1800f7a62  mov     [rsp+370h+var_318], rcx
0x1800f7a67  lea     rcx, ?c_default@Win32Error@Value@Trace@Storage@@0V?$StringLiteral@D@StringLiterals@Mso@@B; Mso::StringLiterals::StringLiteral<char> const Storage::Trace::Value::Win32Error::c_default
0x1800f7a6e  mov     [rsp+370h+var_310], rcx
0x1800f7a73  mov     dword ptr [rsp+370h+var_308], eax
0x1800f7a77  lea     rax, aCreatetemporar; "CreateTemporaryFileW failed to get the "...
0x1800f7a7e  mov     [rsp+370h+var_300], rax
0x1800f7a83  lea     rax, [rsp+370h+var_318]
0x1800f7a88  mov     [rsp+370h+Reserved], rax
0x1800f7a8d  lea     r9, [rsp+370h+var_300]
0x1800f7a92  mov     ecx, 1E556617h
0x1800f7a97  lea     r8d, [r13+0Fh]
0x1800f7a9b  call    sub_1800F1528
0x1800f7aa0  mov     edx, ebx; unsigned int
0x1800f7aa2  mov     ecx, 1E5128C7h; this
0x1800f7aa7  call    ?SetLastStorageErrorAndReturn@Storage@@YAKIK@Z; Storage::SetLastStorageErrorAndReturn(uint,ulong)
0x1800f7aac  mov     ebx, eax
0x1800f7aae  lock dec cs:?s_skipping@Oscilloscope@Storage@@0U?$atomic@K@std@@A; std::atomic<ulong> Storage::Oscilloscope::s_skipping
0x1800f7ab5  mov     rcx, qword ptr [rbp+270h+var_290+8]
0x1800f7ab9  cmp     rcx, 7
0x1800f7abd  jbe     short loc_1800F7B07
0x1800f7abf  mov     rdx, [rbp+270h+Block]
0x1800f7ac3  mov     rax, rdx
0x1800f7ac6  lea     rcx, ds:2[rcx*2]
0x1800f7ace  cmp     rcx, 1000h
0x1800f7ad5  jb      short loc_1800F7AFE
0x1800f7ad7  mov     rdx, [rdx-8]
0x1800f7adb  sub     rax, rdx
0x1800f7ade  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800f7ae2  cmp     rax, 1Fh
0x1800f7ae6  jbe     short loc_1800F7AFE
0x1800f7ae8  mov     [rsp+370h+Reserved], rsi; Reserved
0x1800f7aed  xor     r9d, r9d; LineNo
0x1800f7af0  xor     r8d, r8d; FileName
0x1800f7af3  xor     edx, edx; FunctionName
0x1800f7af5  xor     ecx, ecx; Expression
0x1800f7af7  call    cs:__imp__invoke_watson
0x1800f7afe  mov     rcx, rdx; Block
0x1800f7b01  call    cs:__imp_free
0x1800f7b07  mov     eax, ebx
0x1800f7b09  jmp     loc_1800F7EEB
0x1800f7b0e  lea     rcx, [rbp+270h+Block]
0x1800f7b12  cmp     qword ptr [rbp+270h+var_290+8], 7
0x1800f7b17  cmova   rcx, [rbp+270h+Block]; lpPathName
0x1800f7b1c  xor     edx, edx; lpSecurityAttributes
0x1800f7b1e  call    cs:__imp_CreateDirectoryW
0x1800f7b24  lock dec cs:?s_skipping@Oscilloscope@Storage@@0U?$atomic@K@std@@A; std::atomic<ulong> Storage::Oscilloscope::s_skipping
0x1800f7b2b  mov     ecx, cs:_tls_index
0x1800f7b31  mov     rax, gs:58h
0x1800f7b3a  mov     r15, [rax+rcx*8]
0x1800f7b3e  mov     esi, 1F0h
0x1800f7b43  add     rsi, r15
0x1800f7b46  xor     edx, edx; Val
0x1800f7b48  mov     r8d, 20Ah; Size
0x1800f7b4e  lea     rcx, [rbp+270h+TempFileName]; void *
0x1800f7b52  call    memset_0
0x1800f7b57  test    r13, r13
0x1800f7b5a  jz      short loc_1800F7B61
0x1800f7b5c  mov     rbx, r13
0x1800f7b5f  jmp     short loc_1800F7B6F
0x1800f7b61  lea     rbx, [rbp+270h+Block]
0x1800f7b65  cmp     qword ptr [rbp+270h+var_290+8], 7
0x1800f7b6a  cmova   rbx, [rbp+270h+Block]
0x1800f7b6f  mov     ecx, 210h
0x1800f7b74  mov     eax, [rcx+r15]
0x1800f7b78  test    al, 1
0x1800f7b7a  jnz     short loc_1800F7B95
0x1800f7b7c  or      eax, 1
0x1800f7b7f  mov     [rcx+r15], eax
0x1800f7b83  xorps   xmm0, xmm0
0x1800f7b86  movups  xmmword ptr [rsi], xmm0
0x1800f7b89  movups  xmmword ptr [rsi+10h], xmm0
0x1800f7b8d  mov     rcx, rsi; this
0x1800f7b90  call    ??0Local@Random@Storage@@QEAA@XZ; Storage::Random::Local::Local(void)
0x1800f7b95  mov     [rsp+370h+var_320], rsi
0x1800f7b9a  mov     edx, 0FFFFFFFFh
0x1800f7b9f  lea     rcx, [rsp+370h+var_320]
0x1800f7ba4  call    ??R?$_Rng_from_urng_v2@_KUXoshiro256@Implementation@Random@Storage@@@std@@QEAA_K_K@Z; std::_Rng_from_urng_v2<unsigned __int64,Storage::Random::Implementation::Xoshiro256>::operator()(unsigned __int64)
0x1800f7ba9  lea     r8d, [rax+1]; uUnique
0x1800f7bad  lea     r9, [rbp+270h+TempFileName]; lpTempFileName
0x1800f7bb1  lea     rdx, PrefixString; "DSC"
0x1800f7bb8  mov     rcx, rbx; lpPathName
0x1800f7bbb  call    cs:__imp_GetTempFileNameW
0x1800f7bc1  xor     ebx, ebx
0x1800f7bc3  test    eax, eax
0x1800f7bc5  jnz     short loc_1800F7C3E
0x1800f7bc7  call    cs:__imp_GetLastError
0x1800f7bcd  mov     ebx, eax
0x1800f7bcf  mov     eax, 3
0x1800f7bd4  cmp     ebx, 10Bh
0x1800f7bda  cmovz   ebx, eax
0x1800f7bdd  cmp     ebx, 50h ; 'P'
0x1800f7be0  jz      loc_1800F7B46
0x1800f7be6  lea     rcx, ??_7Win32Error@Value@Trace@Storage@@6B@; const Storage::Trace::Value::Win32Error::`vftable'
0x1800f7bed  mov     [rsp+370h+var_318], rcx
0x1800f7bf2  lea     rcx, ?c_default@Win32Error@Value@Trace@Storage@@0V?$StringLiteral@D@StringLiterals@Mso@@B; Mso::StringLiterals::StringLiteral<char> const Storage::Trace::Value::Win32Error::c_default
0x1800f7bf9  mov     [rsp+370h+var_310], rcx
0x1800f7bfe  mov     dword ptr [rsp+370h+var_308], ebx
0x1800f7c02  lea     rax, aCreatetemporar_1; "CreateTemporaryFileW failed to get the "...
0x1800f7c09  mov     [rsp+370h+var_320], rax
0x1800f7c0e  lea     rax, [rsp+370h+var_318]
0x1800f7c13  mov     [rsp+370h+Reserved], rax
0x1800f7c18  lea     r9, [rsp+370h+var_320]
0x1800f7c1d  mov     ecx, 1E556616h
0x1800f7c22  mov     r8d, 0Fh
0x1800f7c28  call    sub_1800F1528
0x1800f7c2d  mov     edx, ebx; unsigned int
0x1800f7c2f  mov     ecx, 1E5128C6h; this
0x1800f7c34  call    ?SetLastStorageErrorAndReturn@Storage@@YAKIK@Z; Storage::SetLastStorageErrorAndReturn(uint,ulong)
0x1800f7c39  jmp     loc_1800F7DCB
0x1800f7c3e  lock inc cs:?s_skipping@Oscilloscope@Storage@@0U?$atomic@K@std@@A; std::atomic<ulong> Storage::Oscilloscope::s_skipping
0x1800f7c45  mov     rax, [r14]
0x1800f7c48  lea     r8, [rbp+270h+TempFileName]
0x1800f7c4c  mov     edx, r12d
0x1800f7c4f  mov     rcx, r14
0x1800f7c52  mov     rax, [rax+50h]
0x1800f7c56  call    cs:__guard_dispatch_icall_fptr
0x1800f7c5c  cmp     eax, 2
0x1800f7c5f  jz      loc_1800F7D07
0x1800f7c65  lea     rax, ??_7GenericPath@Value@Trace@Storage@@6B@; const Storage::Trace::Value::GenericPath::`vftable'
0x1800f7c6c  mov     [rsp+370h+var_2F8], rax
0x1800f7c71  lea     rax, ?c_path@GenericPath@Value@Trace@Storage@@0V?$StringLiteral@D@StringLiterals@Mso@@B; Mso::StringLiterals::StringLiteral<char> const Storage::Trace::Value::GenericPath::c_path
0x1800f7c78  mov     [rbp+270h+var_2F0], rax
0x1800f7c7c  lea     rcx, [rbp+270h+TempFileName]
0x1800f7c80  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f7c84  inc     rax
0x1800f7c87  cmp     [rcx+rax*2], bx
0x1800f7c8b  jnz     short loc_1800F7C84
0x1800f7c8d  lea     rcx, [rbp+270h+TempFileName]
0x1800f7c91  mov     [rbp+270h+var_2E8], rcx
0x1800f7c95  mov     [rbp+270h+var_2E0], rax
0x1800f7c99  mov     [rbp+270h+var_2B8], bl
0x1800f7c9c  xorps   xmm0, xmm0
0x1800f7c9f  movdqu  [rbp+270h+var_2B0], xmm0
0x1800f7ca4  lea     rax, ??_7Tag@Value@Trace@Storage@@6B@; const Storage::Trace::Value::Tag::`vftable'
0x1800f7cab  mov     [rsp+370h+var_318], rax
0x1800f7cb0  lea     rax, ?c_default@Tag@Value@Trace@Storage@@0V?$StringLiteral@D@StringLiterals@Mso@@B; Mso::StringLiterals::StringLiteral<char> const Storage::Trace::Value::Tag::c_default
0x1800f7cb7  mov     [rsp+370h+var_310], rax
0x1800f7cbc  mov     dword ptr [rsp+370h+var_308], r12d
0x1800f7cc1  lea     rax, aDoesfileexistw_0; "DoesFileExistW failed , trying again"
0x1800f7cc8  mov     [rsp+370h+var_320], rax
0x1800f7ccd  lea     rax, [rsp+370h+var_2F8]
0x1800f7cd2  mov     [rsp+370h+var_348], rax
0x1800f7cd7  lea     rax, [rsp+370h+var_318]
0x1800f7cdc  mov     [rsp+370h+Reserved], rax
0x1800f7ce1  lea     r9, [rsp+370h+var_320]
0x1800f7ce6  mov     edx, 891h
0x1800f7ceb  mov     ecx, 1E556615h
0x1800f7cf0  mov     r8d, 0C8h
0x1800f7cf6  call    sub_1800F1780
0x1800f7cfb  lea     rcx, [rsp+370h+var_2F8]; this
0x1800f7d00  call    ??1GenericPath@Value@Trace@Storage@@UEAA@XZ; Storage::Trace::Value::GenericPath::~GenericPath(void)
0x1800f7d05  jmp     short loc_1800F7D65
0x1800f7d07  mov     rax, [r14]
0x1800f7d0a  mov     ecx, [rbp+270h+arg_20]
0x1800f7d10  mov     [rsp+370h+var_338], ecx
0x1800f7d14  mov     [rsp+370h+var_340], 1
0x1800f7d1c  mov     ecx, [rbp+270h+arg_30]
0x1800f7d22  mov     dword ptr [rsp+370h+var_348], ecx
0x1800f7d26  mov     dword ptr [rsp+370h+Reserved], 0C0010000h
0x1800f7d2e  lea     r9, [rbp+270h+TempFileName]
0x1800f7d32  mov     r8, [rsp+370h+var_300]
0x1800f7d37  mov     edx, r12d
0x1800f7d3a  mov     rcx, r14
0x1800f7d3d  mov     rax, [rax+18h]
0x1800f7d41  call    cs:__guard_dispatch_icall_fptr
0x1800f7d47  mov     ebx, eax
0x1800f7d49  xor     eax, eax
0x1800f7d4b  test    ebx, ebx
0x1800f7d4d  jz      loc_1800F7DDB
0x1800f7d53  cmp     ebx, 0B7h
0x1800f7d59  jz      short loc_1800F7D65
0x1800f7d5b  cmp     ebx, 50h ; 'P'
0x1800f7d5e  jz      short loc_1800F7D65
0x1800f7d60  cmp     ebx, 5
0x1800f7d63  jnz     short loc_1800F7D71
0x1800f7d65  lock dec cs:?s_skipping@Oscilloscope@Storage@@0U?$atomic@K@std@@A; std::atomic<ulong> Storage::Oscilloscope::s_skipping
0x1800f7d6c  jmp     loc_1800F7B46
0x1800f7d71  lea     rcx, ??_7Win32Error@Value@Trace@Storage@@6B@; const Storage::Trace::Value::Win32Error::`vftable'
0x1800f7d78  mov     [rsp+370h+var_318], rcx
0x1800f7d7d  lea     rcx, ?c_default@Win32Error@Value@Trace@Storage@@0V?$StringLiteral@D@StringLiterals@Mso@@B; Mso::StringLiterals::StringLiteral<char> const Storage::Trace::Value::Win32Error::c_default
0x1800f7d84  mov     [rsp+370h+var_310], rcx
0x1800f7d89  mov     dword ptr [rsp+370h+var_308], ebx
0x1800f7d8d  lea     rax, aCreatetemporar_2; "CreateTemporaryFileW failed to create t"...
0x1800f7d94  mov     [rsp+370h+var_320], rax
0x1800f7d99  lea     rax, [rsp+370h+var_318]
0x1800f7d9e  mov     [rsp+370h+Reserved], rax
0x1800f7da3  lea     r9, [rsp+370h+var_320]
0x1800f7da8  mov     ecx, 1E556614h
0x1800f7dad  mov     r8d, 0Fh
0x1800f7db3  call    sub_1800F1528
0x1800f7db8  mov     edx, ebx; unsigned int
0x1800f7dba  mov     ecx, 1E5128C5h; this
0x1800f7dbf  call    ?SetLastStorageErrorAndReturn@Storage@@YAKIK@Z; Storage::SetLastStorageErrorAndReturn(uint,ulong)
0x1800f7dc4  lock dec cs:?s_skipping@Oscilloscope@Storage@@0U?$atomic@K@std@@A; std::atomic<ulong> Storage::Oscilloscope::s_skipping
0x1800f7dcb  mov     ebx, eax
0x1800f7dcd  lea     rcx, [rbp+270h+Block]; void *
0x1800f7dd1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f7dd6  jmp     loc_1800F7B07
0x1800f7ddb  test    rdi, rdi
0x1800f7dde  jz      loc_1800F7E89
0x1800f7de4  xorps   xmm0, xmm0
0x1800f7de7  movups  xmmword ptr [rbp+270h+var_280], xmm0
0x1800f7deb  xorps   xmm1, xmm1
0x1800f7dee  movdqu  [rbp+270h+var_270], xmm1
0x1800f7df3  lea     rcx, [rbp+270h+TempFileName]
0x1800f7df7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800f7dfb  inc     r8
0x1800f7dfe  cmp     [rcx+r8*2], ax
0x1800f7e03  jnz     short loc_1800F7DFB
0x1800f7e05  lea     rdx, [rbp+270h+TempFileName]
0x1800f7e09  lea     rcx, [rbp+270h+var_280]
0x1800f7e0d  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1800f7e12  lea     rax, [rbp+270h+var_280]
0x1800f7e16  cmp     rax, rdi
0x1800f7e19  jz      short loc_1800F7E39
0x1800f7e1b  movups  xmm2, xmmword ptr [rbp+270h+var_280]
0x1800f7e1f  movups  xmm3, [rbp+270h+var_270]
0x1800f7e23  movups  xmm0, xmmword ptr [rdi]
0x1800f7e26  movups  xmmword ptr [rbp+270h+var_280], xmm0
0x1800f7e2a  movups  xmm1, xmmword ptr [rdi+10h]
0x1800f7e2e  movups  [rbp+270h+var_270], xmm1
0x1800f7e32  movups  xmmword ptr [rdi], xmm2
0x1800f7e35  movups  xmmword ptr [rdi+10h], xmm3
0x1800f7e39  mov     rax, qword ptr [rbp+270h+var_270+8]
0x1800f7e3d  cmp     rax, 7
0x1800f7e41  jbe     short loc_1800F7E89
0x1800f7e43  mov     rcx, [rbp+270h+var_280]; Block
0x1800f7e47  mov     rdx, rcx
0x1800f7e4a  lea     rax, ds:2[rax*2]
0x1800f7e52  cmp     rax, 1000h
0x1800f7e58  jb      short loc_1800F7E83
0x1800f7e5a  mov     rcx, [rcx-8]
0x1800f7e5e  sub     rdx, rcx
0x1800f7e61  lea     rax, [rdx-8]
0x1800f7e65  cmp     rax, 1Fh
0x1800f7e69  jbe     short loc_1800F7E83
0x1800f7e6b  xor     esi, esi
0x1800f7e6d  mov     [rsp+370h+Reserved], rsi; Reserved
0x1800f7e72  xor     r9d, r9d; LineNo
0x1800f7e75  xor     r8d, r8d; FileName
0x1800f7e78  xor     edx, edx; FunctionName
0x1800f7e7a  xor     ecx, ecx; Expression
0x1800f7e7c  call    cs:__imp__invoke_watson
0x1800f7e83  call    cs:__imp_free
0x1800f7e89  lock dec cs:?s_skipping@Oscilloscope@Storage@@0U?$atomic@K@std@@A; std::atomic<ulong> Storage::Oscilloscope::s_skipping
0x1800f7e90  lea     rax, ??_7Handle@Value@Trace@Storage@@6B@; const Storage::Trace::Value::Handle::`vftable'
0x1800f7e97  mov     [rsp+370h+var_318], rax
0x1800f7e9c  lea     rax, ?c_default@Handle@Value@Trace@Storage@@0V?$StringLiteral@D@StringLiterals@Mso@@B; Mso::StringLiterals::StringLiteral<char> const Storage::Trace::Value::Handle::c_default
0x1800f7ea3  mov     [rsp+370h+var_310], rax
0x1800f7ea8  mov     rax, [rsp+370h+var_300]
0x1800f7ead  mov     rax, [rax]
0x1800f7eb0  mov     [rsp+370h+var_308], rax
0x1800f7eb5  lea     rax, aCreatetemporar_0; "CreateTemporaryFileW succeeded"
0x1800f7ebc  mov     [rsp+370h+var_320], rax
0x1800f7ec1  lea     rax, [rsp+370h+var_318]
0x1800f7ec6  mov     [rsp+370h+Reserved], rax
  ... truncated ...
```
