# StorageAdapterAddRecord

- ea: `0x14000fd00`
- end: `0x140010195`
- name: `StorageAdapterAddRecord`
- size: `1173`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000a2e4`
- `0x14000a420`
- `0x14000fd00`
- `0x14001019c`
- `0x140010204`
- `0x14001101c`
- `0x1400115c0`
- `0x140011b1c`
- `0x14001cb78`
- `0x140058624`
- `0x140058810`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010044`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010064`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400100c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400100e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001010e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001012e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010044`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010064`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400100c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400100e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001010e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001012e`

## string_xrefs

- `0x14000fd47`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14000fd76`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14000fda7`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14000fdf0`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14000fe1f`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14000fe50`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14000fe83`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14000feab`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x140010020`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x1400100a4`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14001014b`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`
- `0x14001016d`: `onecore\ds\security\biometrics\service\trustlet\exe\securestorageadapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StorageAdapterAddRecord(__int64 a1, struct _WINBIO_IDENTITY **a2)
{
  struct _WINBIO_IDENTITY *v4; // rdx
  __int64 v5; // rcx
  __int64 result; // rax
  unsigned __int8 v7; // r8
  struct _WINBIO_IDENTITY *v8; // rax
  int v9; // eax
  unsigned int v10; // edi
  const char *v11; // r9
  __int64 v12; // r14
  char *v13; // rcx
  struct _WINBIO_IDENTITY *v14; // rax
  struct _WINBIO_IDENTITY *v15; // r8
  size_t v16; // r8
  struct CacheBuffer *v17; // rdi
  int FileHeader; // eax
  unsigned int v19; // ebx
  HLOCAL v20; // rcx
  HLOCAL v21; // rcx
  int v22; // eax
  unsigned int v23; // ebx
  HLOCAL v24; // rcx
  HLOCAL v25; // rcx
  HLOCAL v26; // rcx
  HLOCAL v27; // rcx
  int v28; // [rsp+20h] [rbp-28h] BYREF
  std::_Ref_count_base *v29; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HLOCAL v31; // [rsp+50h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp+18h] BYREF

  if ( a1 && a2 && (v4 = *a2) != 0 )
  {
    v5 = *(_QWORD *)(a1 + 64);
    if ( v5 )
    {
      if ( v4->Type - 2 <= 1 )
      {
        v7 = *((_BYTE *)a2 + 8);
        if ( ((v7 + 1) & 0xFE) != 0 )
        {
          if ( a2[5] && a2[4] )
          {
            if ( !a2[7] || a2[6] )
            {
              v8 = a2[3];
              if ( v8 == *(struct _WINBIO_IDENTITY **)(v5 + 16) )
              {
                if ( !v8 || a2[2] )
                {
                  try
                  {
                    v9 = StorageAdapterQueryBySubject(a1, v4, v7);
                    v10 = v9;
                    if ( v9 < 0 )
                    {
                      if ( v9 == -2146861025 )
                      {
                        v12 = (__int64)a2[5] + 4 * (_QWORD)&a2[3]->Value.AccountSid.Data[30] + (_QWORD)a2[7];
                        wil::make_unique_hlocal<unsigned char [0]>(&v31, v12);
                        v13 = (char *)v31;
                        *(_OWORD *)v31 = xmmword_14008EBE8;
                        v14 = *a2;
                        *(_OWORD *)(v13 + 72) = *(_OWORD *)&(*a2)->Type;
                        *(_OWORD *)(v13 + 88) = *(_OWORD *)&v14->Value.AccountSid.Data[8];
                        *(_OWORD *)(v13 + 104) = *(_OWORD *)&v14->Value.AccountSid.Data[24];
                        *(_OWORD *)(v13 + 120) = *(_OWORD *)&v14->Value.AccountSid.Data[40];
                        *(_OWORD *)(v13 + 132) = *(_OWORD *)&v14->Value.AccountSid.Data[52];
                        *((_QWORD *)v13 + 3) = (unsigned int)v12;
                        *((_QWORD *)v13 + 4) = 4LL * (_QWORD)a2[3] + 152;
                        *((_QWORD *)v13 + 8) = a2[3];
                        *((_QWORD *)v13 + 5) = a2[5];
                        *((_QWORD *)v13 + 7) = a2[7];
                        v13[148] = *((_BYTE *)a2 + 8);
                        v15 = a2[3];
                        if ( v15 )
                          memcpy_0((char *)v31 + 152, a2[2], 4LL * (_QWORD)v15);
                        memcpy_0((char *)v31 + 4 * (_QWORD)a2[3] + 152, a2[4], (size_t)a2[5]);
                        v16 = (size_t)a2[7];
                        if ( v16 )
                          memcpy_0((char *)&a2[5][2].Type + 4 * (_QWORD)a2[3] + (_QWORD)v31, a2[6], v16);
                        v17 = (struct CacheBuffer *)(*(_QWORD *)WinBioFramework::PipelineToPipelineObject(&v28, a1)
                                                   + 1296LL);
                        if ( v29 )
                          std::_Ref_count_base::_Decref(v29);
                        CacheAddRecord(v17, (unsigned __int8 *)v31, v12);
                        wil::make_unique_hlocal<_LOCK_BOX_FILE_HEADER,>(&hMem);
                        FileHeader = CacheGetFileHeader(v17, (struct _LOCK_BOX_FILE_HEADER *)hMem);
                        v19 = FileHeader;
                        if ( FileHeader >= 0 )
                        {
                          ++*((_QWORD *)hMem + 9);
                          *((_QWORD *)hMem + 12) += v12;
                          v22 = CacheReplaceFileHeader(v17, (struct _LOCK_BOX_FILE_HEADER *)hMem);
                          v23 = v22;
                          if ( v22 >= 0 )
                          {
                            v26 = hMem;
                            hMem = 0;
                            if ( v26 )
                              LocalFree(v26);
                            v27 = v31;
                            v31 = 0;
                            if ( v27 )
                              LocalFree(v27);
                            result = 0;
                          }
                          else
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x45F,
                              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
                              (const char *)(unsigned int)v22,
                              v28);
                            v24 = hMem;
                            hMem = 0;
                            if ( v24 )
                              LocalFree(v24);
                            v25 = v31;
                            v31 = 0;
                            if ( v25 )
                              LocalFree(v25);
                            result = v23;
                          }
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x457,
                            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
                            (const char *)(unsigned int)FileHeader,
                            v28);
                          v20 = hMem;
                          hMem = 0;
                          if ( v20 )
                            LocalFree(v20);
                          v21 = v31;
                          v31 = 0;
                          if ( v21 )
                            LocalFree(v21);
                          result = v19;
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x410,
                          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
                          (const char *)(unsigned int)v9,
                          v28);
                        result = v10;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x40C,
                        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
                        (const char *)0x8009801CLL,
                        v28);
                      result = 2148106268LL;
                    }
                  }
                  catch ( ... )
                  {
                    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                                           retaddr,
                                           (void *)0x463,
                                           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secu"
                                                         "restorageadapter.cpp",
                                           v11);
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x403,
                    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
                    (const char *)0x80004003LL,
                    v28);
                  return 2147500035LL;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x3FE,
                  (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
                  (const char *)0x80098022LL,
                  v28);
                return 2148106274LL;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3FA,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
                (const char *)0x80070057LL,
                v28);
              return 2147942487LL;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3F5,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
              (const char *)0x80070057LL,
              v28);
            return 2147942487LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3F0,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
            (const char *)0x80070057LL,
            v28);
          return 2147942487LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3EB,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
          (const char *)0x80070057LL,
          v28);
        return 2147942487LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E6,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
        (const char *)0x8009800FLL,
        v28);
      return 2148106255LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E1,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\securestorageadapter.cpp",
      (const char *)0x80004003LL,
      v28);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x14000fd00  mov     [rsp+arg_8], rbx
0x14000fd05  push    rsi
0x14000fd06  push    rdi
0x14000fd07  push    r14
0x14000fd09  sub     rsp, 30h
0x14000fd0d  mov     rbx, rdx
0x14000fd10  mov     rsi, rcx
0x14000fd13  test    rcx, rcx
0x14000fd16  jz      loc_140010160
0x14000fd1c  test    rdx, rdx
0x14000fd1f  jz      loc_140010160
0x14000fd25  mov     rdx, [rdx]
0x14000fd28  test    rdx, rdx
0x14000fd2b  jz      loc_140010160
0x14000fd31  mov     rcx, [rcx+40h]
0x14000fd35  test    rcx, rcx
0x14000fd38  jnz     short loc_14000FD5F
0x14000fd3a  mov     rcx, [rsp+48h]; this
0x14000fd3f  mov     ebx, 8009800Fh
0x14000fd44  mov     r9d, ebx; char *
0x14000fd47  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14000fd4e  mov     edx, 3E6h; void *
0x14000fd53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fd58  mov     eax, ebx
0x14000fd5a  jmp     loc_140010186
0x14000fd5f  mov     eax, [rdx]
0x14000fd61  sub     eax, 2
0x14000fd64  cmp     eax, 1
0x14000fd67  jbe     short loc_14000FD8E
0x14000fd69  mov     rcx, [rsp+48h]; this
0x14000fd6e  mov     ebx, 80070057h
0x14000fd73  mov     r9d, ebx; char *
0x14000fd76  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14000fd7d  mov     edx, 3EBh; void *
0x14000fd82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fd87  mov     eax, ebx
0x14000fd89  jmp     loc_140010186
0x14000fd8e  mov     r8b, [rbx+8]
0x14000fd92  lea     eax, [r8+1]
0x14000fd96  test    al, 0FEh
0x14000fd98  jnz     short loc_14000FDBF
0x14000fd9a  mov     rcx, [rsp+48h]; this
0x14000fd9f  mov     ebx, 80070057h
0x14000fda4  mov     r9d, ebx; char *
0x14000fda7  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14000fdae  mov     edx, 3F0h; void *
0x14000fdb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fdb8  mov     eax, ebx
0x14000fdba  jmp     loc_140010186
0x14000fdbf  cmp     qword ptr [rbx+28h], 0
0x14000fdc4  jz      loc_14001013E
0x14000fdca  cmp     qword ptr [rbx+20h], 0
0x14000fdcf  jz      loc_14001013E
0x14000fdd5  cmp     qword ptr [rbx+38h], 0
0x14000fdda  jbe     short loc_14000FE08
0x14000fddc  cmp     qword ptr [rbx+30h], 0
0x14000fde1  jnz     short loc_14000FE08
0x14000fde3  mov     rcx, [rsp+48h]; this
0x14000fde8  mov     ebx, 80070057h
0x14000fded  mov     r9d, ebx; char *
0x14000fdf0  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14000fdf7  mov     edx, 3FAh; void *
0x14000fdfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fe01  mov     eax, ebx
0x14000fe03  jmp     loc_140010186
0x14000fe08  mov     rax, [rbx+18h]
0x14000fe0c  cmp     rax, [rcx+10h]
0x14000fe10  jz      short loc_14000FE37
0x14000fe12  mov     rcx, [rsp+48h]; this
0x14000fe17  mov     ebx, 80098022h
0x14000fe1c  mov     r9d, ebx; char *
0x14000fe1f  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14000fe26  mov     edx, 3FEh; void *
0x14000fe2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fe30  mov     eax, ebx
0x14000fe32  jmp     loc_140010186
0x14000fe37  test    rax, rax
0x14000fe3a  jz      short loc_14000FE68
0x14000fe3c  cmp     qword ptr [rbx+10h], 0
0x14000fe41  jnz     short loc_14000FE68
0x14000fe43  mov     rcx, [rsp+48h]; this
0x14000fe48  mov     ebx, 80004003h
0x14000fe4d  mov     r9d, ebx; char *
0x14000fe50  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14000fe57  mov     edx, 403h; void *
0x14000fe5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fe61  mov     eax, ebx
0x14000fe63  jmp     loc_140010186
0x14000fe68  mov     rcx, rsi
0x14000fe6b  call    StorageAdapterQueryBySubject
0x14000fe70  mov     edi, eax
0x14000fe72  test    eax, eax
0x14000fe74  js      short loc_14000FE9B
0x14000fe76  mov     rcx, [rsp+48h]; this
0x14000fe7b  mov     ebx, 8009801Ch
0x14000fe80  mov     r9d, ebx; char *
0x14000fe83  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14000fe8a  mov     edx, 40Ch; void *
0x14000fe8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fe94  mov     eax, ebx
0x14000fe96  jmp     loc_140010186
0x14000fe9b  cmp     edi, 8009801Fh
0x14000fea1  jz      short loc_14000FEC3
0x14000fea3  mov     rcx, [rsp+48h]; this
0x14000fea8  mov     r9d, edi; char *
0x14000feab  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x14000feb2  mov     edx, 410h; void *
0x14000feb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000febc  mov     eax, edi
0x14000febe  jmp     loc_140010186
0x14000fec3  mov     rcx, [rbx+18h]
0x14000fec7  mov     rax, [rbx+28h]
0x14000fecb  add     rcx, 26h ; '&'
0x14000fecf  lea     r14, [rax+rcx*4]
0x14000fed3  add     r14, [rbx+38h]
0x14000fed7  mov     rdx, r14
0x14000feda  lea     rcx, [rsp+48h+arg_0]
0x14000fedf  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x14000fee4  nop
0x14000fee5  mov     rcx, [rsp+48h+arg_0]
0x14000feea  movups  xmm0, cs:xmmword_14008EBE8
0x14000fef1  movdqu  xmmword ptr [rcx], xmm0
0x14000fef5  mov     rax, [rbx]
0x14000fef8  movups  xmm0, xmmword ptr [rax]
0x14000fefb  movups  xmmword ptr [rcx+48h], xmm0
0x14000feff  movups  xmm1, xmmword ptr [rax+10h]
0x14000ff03  movups  xmmword ptr [rcx+58h], xmm1
0x14000ff07  movups  xmm0, xmmword ptr [rax+20h]
0x14000ff0b  movups  xmmword ptr [rcx+68h], xmm0
0x14000ff0f  movups  xmm1, xmmword ptr [rax+30h]
0x14000ff13  movups  xmmword ptr [rcx+78h], xmm1
0x14000ff17  movups  xmm0, xmmword ptr [rax+3Ch]
0x14000ff1b  movups  xmmword ptr [rcx+84h], xmm0
0x14000ff22  mov     eax, r14d
0x14000ff25  mov     [rcx+18h], rax
0x14000ff29  mov     rax, [rbx+18h]
0x14000ff2d  lea     rax, ds:98h[rax*4]
0x14000ff35  mov     [rcx+20h], rax
0x14000ff39  mov     rax, [rbx+18h]
0x14000ff3d  mov     [rcx+40h], rax
0x14000ff41  mov     rax, [rbx+28h]
0x14000ff45  mov     [rcx+28h], rax
0x14000ff49  mov     rax, [rbx+38h]
0x14000ff4d  mov     [rcx+38h], rax
0x14000ff51  mov     al, [rbx+8]
0x14000ff54  mov     [rcx+94h], al
0x14000ff5a  mov     r8, [rbx+18h]
0x14000ff5e  test    r8, r8
0x14000ff61  jz      short loc_14000FF7C
0x14000ff63  shl     r8, 2; Size
0x14000ff67  mov     rcx, [rsp+48h+arg_0]
0x14000ff6c  add     rcx, 98h; void *
0x14000ff73  mov     rdx, [rbx+10h]; Src
0x14000ff77  call    memcpy_0
0x14000ff7c  mov     rcx, [rbx+18h]
0x14000ff80  mov     rax, [rsp+48h+arg_0]
0x14000ff85  add     rax, 98h
0x14000ff8b  lea     rcx, [rax+rcx*4]; void *
0x14000ff8f  mov     r8, [rbx+28h]; Size
0x14000ff93  mov     rdx, [rbx+20h]; Src
0x14000ff97  call    memcpy_0
0x14000ff9c  mov     r8, [rbx+38h]; Size
0x14000ffa0  test    r8, r8
0x14000ffa3  jz      short loc_14000FFC5
0x14000ffa5  mov     rcx, [rbx+18h]
0x14000ffa9  mov     rax, [rbx+28h]
0x14000ffad  add     rax, 98h
0x14000ffb3  lea     rcx, [rax+rcx*4]
0x14000ffb7  add     rcx, [rsp+48h+arg_0]; void *
0x14000ffbc  mov     rdx, [rbx+30h]; Src
0x14000ffc0  call    memcpy_0
0x14000ffc5  mov     rdx, rsi
0x14000ffc8  lea     rcx, [rsp+48h+var_28]
0x14000ffcd  call    WinBioFramework__PipelineToPipelineObject
0x14000ffd2  mov     rdi, [rax]
0x14000ffd5  add     rdi, 510h
0x14000ffdc  mov     rcx, [rsp+48h+var_20]; this
0x14000ffe1  test    rcx, rcx
0x14000ffe4  jz      short loc_14000FFEB
0x14000ffe6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000ffeb  mov     r8, r14; unsigned __int64
0x14000ffee  mov     rdx, [rsp+48h+arg_0]; unsigned __int8 *
0x14000fff3  mov     rcx, rdi; struct CacheBuffer *
0x14000fff6  call    ?CacheAddRecord@@YAJPEAVCacheBuffer@@PEAE_K@Z; CacheAddRecord(CacheBuffer *,uchar *,unsigned __int64)
0x14000fffb  lea     rcx, [rsp+48h+hMem]
0x140010000  call    ??$make_unique_hlocal@U_LOCK_BOX_FILE_HEADER@@$$V@wil@@YA?AV?$unique_ptr@U_LOCK_BOX_FILE_HEADER@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@XZ; wil::make_unique_hlocal<_LOCK_BOX_FILE_HEADER,>(void)
0x140010005  mov     rdx, [rsp+48h+hMem]; struct _LOCK_BOX_FILE_HEADER *
0x14001000a  mov     rcx, rdi; struct CacheBuffer *
0x14001000d  call    ?CacheGetFileHeader@@YAJPEAVCacheBuffer@@PEAU_LOCK_BOX_FILE_HEADER@@@Z; CacheGetFileHeader(CacheBuffer *,_LOCK_BOX_FILE_HEADER *)
0x140010012  mov     ebx, eax
0x140010014  test    eax, eax
0x140010016  jns     short loc_140010077
0x140010018  mov     rcx, [rsp+48h]; this
0x14001001d  mov     r9d, eax; char *
0x140010020  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140010027  mov     edx, 457h; void *
0x14001002c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010031  mov     rcx, [rsp+48h+hMem]; hMem
0x140010036  mov     [rsp+48h+hMem], 0
0x14001003f  test    rcx, rcx
0x140010042  jz      short loc_140010051
0x140010044  call    cs:__imp_LocalFree
0x14001004b  nop     dword ptr [rax+rax+00h]
0x140010050  nop
0x140010051  mov     rcx, [rsp+48h+arg_0]; hMem
0x140010056  mov     [rsp+48h+arg_0], 0
0x14001005f  test    rcx, rcx
0x140010062  jz      short loc_140010070
0x140010064  call    cs:__imp_LocalFree
0x14001006b  nop     dword ptr [rax+rax+00h]
0x140010070  mov     eax, ebx
0x140010072  jmp     loc_140010186
0x140010077  mov     rax, [rsp+48h+hMem]
0x14001007c  inc     qword ptr [rax+48h]
0x140010080  mov     rax, [rsp+48h+hMem]
0x140010085  add     [rax+60h], r14
0x140010089  mov     rdx, [rsp+48h+hMem]; struct _LOCK_BOX_FILE_HEADER *
0x14001008e  mov     rcx, rdi; struct CacheBuffer *
0x140010091  call    ?CacheReplaceFileHeader@@YAJPEAVCacheBuffer@@PEAU_LOCK_BOX_FILE_HEADER@@@Z; CacheReplaceFileHeader(CacheBuffer *,_LOCK_BOX_FILE_HEADER *)
0x140010096  mov     ebx, eax
0x140010098  test    eax, eax
0x14001009a  jns     short loc_1400100FB
0x14001009c  mov     rcx, [rsp+48h]; this
0x1400100a1  mov     r9d, eax; char *
0x1400100a4  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x1400100ab  mov     edx, 45Fh; void *
0x1400100b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400100b5  mov     rcx, [rsp+48h+hMem]; hMem
0x1400100ba  mov     [rsp+48h+hMem], 0
0x1400100c3  test    rcx, rcx
0x1400100c6  jz      short loc_1400100D5
0x1400100c8  call    cs:__imp_LocalFree
0x1400100cf  nop     dword ptr [rax+rax+00h]
0x1400100d4  nop
0x1400100d5  mov     rcx, [rsp+48h+arg_0]; hMem
0x1400100da  mov     [rsp+48h+arg_0], 0
0x1400100e3  test    rcx, rcx
0x1400100e6  jz      short loc_1400100F4
0x1400100e8  call    cs:__imp_LocalFree
0x1400100ef  nop     dword ptr [rax+rax+00h]
0x1400100f4  mov     eax, ebx
0x1400100f6  jmp     loc_140010186
0x1400100fb  mov     rcx, [rsp+48h+hMem]; hMem
0x140010100  mov     [rsp+48h+hMem], 0
0x140010109  test    rcx, rcx
0x14001010c  jz      short loc_14001011B
0x14001010e  call    cs:__imp_LocalFree
0x140010115  nop     dword ptr [rax+rax+00h]
0x14001011a  nop
0x14001011b  mov     rcx, [rsp+48h+arg_0]; hMem
0x140010120  mov     [rsp+48h+arg_0], 0
0x140010129  test    rcx, rcx
0x14001012c  jz      short loc_14001013A
0x14001012e  call    cs:__imp_LocalFree
0x140010135  nop     dword ptr [rax+rax+00h]
0x14001013a  xor     eax, eax
0x14001013c  jmp     short loc_140010186
0x14001013e  mov     rcx, [rsp+48h]; this
0x140010143  mov     ebx, 80070057h
0x140010148  mov     r9d, ebx; char *
0x14001014b  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140010152  mov     edx, 3F5h; void *
0x140010157  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001015c  mov     eax, ebx
0x14001015e  jmp     short loc_140010186
0x140010160  mov     rcx, [rsp+48h]; this
0x140010165  mov     ebx, 80004003h
0x14001016a  mov     r9d, ebx; char *
0x14001016d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\biometrics\\serv"...
0x140010174  mov     edx, 3E1h; void *
0x140010179  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001017e  mov     eax, ebx
0x140010180  jmp     short loc_140010186
0x140010182  mov     eax, dword ptr [rsp+48h+arg_0]
0x140010186  mov     rbx, [rsp+48h+arg_8]
0x14001018b  add     rsp, 30h
0x14001018f  pop     r14
0x140010191  pop     rdi
0x140010192  pop     rsi
0x140010193  retn
```
