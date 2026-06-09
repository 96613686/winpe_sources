# RfbDiskFolderWmiQuery::CreatePidl(_MI_Instance const *,wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)

- ea: `0x180013bb0`
- end: `0x18001404e`
- name: `?CreatePidl@RfbDiskFolderWmiQuery@@MEAAXPEBU_MI_Instance@@AEAV?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z`
- size: `1182`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, const struct _MI_Instance *, void **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002030`
- `0x18000591c`
- `0x180007c70`
- `0x180010a80`
- `0x180010bec`
- `0x180010d00`
- `0x180013484`
- `0x1800135b0`
- `0x180013bb0`
- `0x180016e88`
- `0x180016f04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180013c6a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180013c6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013bec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013ff5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013bec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013ff5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180013cbc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180013cbc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180013d4c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180013d4c`

## string_xrefs

- `0x180013f10`: `Compressed`

## pseudocode

```c
__int64 __fastcall RfbDiskFolderWmiQuery::CreatePidl(RTL_SRWLOCK *a1, const struct _MI_Instance *a2, void **a3)
{
  void *v6; // rcx
  int v7; // ebx
  bool v8; // si
  __int64 v9; // rcx
  const char *v10; // r9
  _QWORD *Ptr; // rdi
  __int64 v12; // rsi
  bool v13; // al
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  unsigned int v19; // ebx
  unsigned int v20; // edi
  int *v21; // rdx
  __int128 *v22; // rcx
  char *v23; // rax
  void *v24; // rcx
  __int64 result; // rax
  const char *v26; // r9
  int v27; // [rsp+30h] [rbp-F8h] BYREF
  __int128 v28; // [rsp+38h] [rbp-F0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-E0h]
  unsigned __int64 v30; // [rsp+50h] [rbp-D8h]
  int v31[4]; // [rsp+58h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-C0h]
  unsigned __int64 v33; // [rsp+70h] [rbp-B8h]
  int v34[4]; // [rsp+78h] [rbp-B0h] BYREF
  __m128i si128; // [rsp+88h] [rbp-A0h]
  __int128 v36; // [rsp+98h] [rbp-90h] BYREF
  unsigned __int64 v37[2]; // [rsp+A8h] [rbp-80h] BYREF
  bool v38[16]; // [rsp+B8h] [rbp-70h] BYREF
  _OWORD Src[2]; // [rsp+C8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v6 = *a3;
  *a3 = 0;
  if ( v6 )
    CoTaskMemFree(v6);
  v36 = 0;
  *(_OWORD *)v37 = 0;
  *(_OWORD *)v38 = 0;
  LODWORD(v36) = 1;
  *(_OWORD *)v34 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v34[0]) = 0;
  try
  {
    RfbWmiQuery::GetProperty<std::wstring>();
    _o_wcscpy_s((char *)&v36 + 4, 3);
    v27 = 0;
    RfbWmiQuery::GetProperty<unsigned long>(a2, L"DriveType", &v27);
    v7 = v27;
    if ( v27 == 2 )
    {
      v38[9] = 1;
    }
    else
    {
      v38[9] = 0;
      if ( v27 == 4 )
      {
        v38[10] = 1;
        v8 = 0;
        goto LABEL_22;
      }
    }
    v38[10] = 0;
    v8 = 0;
    if ( v27 == 5 )
    {
      AcquireSRWLockShared(a1 + 24);
      Ptr = a1[25].Ptr;
      v12 = Ptr[1];
      HIDWORD(v28) = 0;
      if ( !*(_BYTE *)(v12 + 25) )
      {
        do
        {
          v13 = LessIgnoreCase::operator()(v9, (__int64 *)(v12 + 32), (__int64 *)v34, v10);
          if ( !v13 )
            Ptr = (_QWORD *)v12;
          v9 = v12 + 16;
          if ( !v13 )
            v9 = v12;
          v12 = *(_QWORD *)v9;
        }
        while ( !*(_BYTE *)(*(_QWORD *)v9 + 25LL) );
      }
      v8 = !*((_BYTE *)Ptr + 25) && !LessIgnoreCase::operator()(v9, (__int64 *)v34, Ptr + 4, v10) && Ptr != a1[25].Ptr;
      if ( a1 != (RTL_SRWLOCK *)-192LL )
        ReleaseSRWLockShared(a1 + 24);
    }
LABEL_22:
    v27 = 0;
    RfbWmiQuery::GetProperty<unsigned long>(a2, L"MediaType", &v27);
    if ( !v7 )
      goto LABEL_63;
    v14 = v7 - 1;
    if ( !v14 )
      goto LABEL_63;
    v15 = v14 - 1;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( !v18 )
          {
            v20 = 10;
            v19 = v8 ? 59 : 11;
            goto LABEL_64;
          }
          if ( v18 == 1 )
          {
            v19 = 12;
            v20 = 11;
LABEL_64:
            *(_DWORD *)&v38[4] = v20;
            *(_DWORD *)v38 = v19;
            if ( v20 != 12 )
            {
              *(_OWORD *)v31 = 0;
              v32 = 0;
              v33 = 7;
              LOWORD(v31[0]) = 0;
              v28 = 0;
              v29 = 0;
              v30 = 7;
              LOWORD(v28) = 0;
              RfbWmiQuery::GetNullableProperty(a2, L"Size", v37);
              RfbWmiQuery::GetNullableProperty(a2, L"FreeSpace", &v37[1]);
              RfbWmiQuery::GetNullableProperty(a2, L"Compressed", &v38[8]);
              if ( !(unsigned __int8)RfbWmiQuery::GetNullableProperty(a2, L"ProviderName", v31) )
              {
                v21 = v31;
                if ( v33 > 7 )
                  v21 = *(int **)v31;
                v32 = 0;
                *(_WORD *)v21 = 0;
              }
              if ( !(unsigned __int8)RfbWmiQuery::GetNullableProperty(a2, L"VolumeName", &v28) )
              {
                v22 = &v28;
                if ( v30 > 7 )
                  v22 = (__int128 *)v28;
                v29 = 0;
                *(_WORD *)v22 = 0;
              }
              Src[0] = 0;
              Src[1] = _mm_load_si128((const __m128i *)&_xmm);
              LOWORD(Src[0]) = 0;
              DiskDataHelper::CreateDisplayName(v34, v20, v19, v31, &v28, Src);
              v23 = RfbPidlHelper<FileFixedData>::CreatePidl(Src, &v36);
              v24 = *a3;
              *a3 = v23;
              if ( v24 )
                CoTaskMemFree(v24);
              std::wstring::~wstring((char **)Src);
              std::wstring::~wstring((char **)&v28);
              std::wstring::~wstring((char **)v31);
            }
            return std::wstring::~wstring((char **)v34);
          }
LABEL_63:
          v20 = 12;
          v19 = 58;
          goto LABEL_64;
        }
        v19 = 9;
      }
      else
      {
        v19 = 8;
      }
LABEL_33:
      v20 = v19;
      goto LABEL_64;
    }
    if ( v27 > 13 )
    {
      if ( v27 > 20 )
      {
        if ( v27 == 21 )
          goto LABEL_62;
        if ( v27 != 22 )
        {
          if ( v27 != 23 && (unsigned int)(v27 - 24) >= 2 )
            goto LABEL_61;
          goto LABEL_62;
        }
      }
      else if ( v27 == 20 || v27 == 14 || v27 != 15 && v27 != 16 && (v27 == 17 || v27 == 18) )
      {
        goto LABEL_62;
      }
      v20 = 6;
    }
    else
    {
      if ( v27 == 13 )
        goto LABEL_62;
      v20 = 6;
      if ( v27 > 6 )
      {
        if ( v27 != 7 && v27 != 8 && (unsigned int)(v27 - 9) >= 2 )
          goto LABEL_61;
      }
      else if ( v27 != 6 )
      {
        if ( !v27 )
        {
LABEL_61:
          v19 = 7;
          goto LABEL_33;
        }
        if ( v27 != 1 )
        {
          if ( v27 != 2 && v27 != 3 && (unsigned int)(v27 - 4) >= 2 )
            goto LABEL_61;
LABEL_62:
          v19 = 6;
          v20 = 5;
          goto LABEL_64;
        }
      }
    }
    v19 = 5;
    goto LABEL_64;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0xE5,
             (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbdiskfolderwmiquery.cpp",
             v26);
  }
  return result;
}

```

## disassembly

```asm
0x180013bb0  push    rbx
0x180013bb2  push    rsi
0x180013bb3  push    rdi
0x180013bb4  push    r12
0x180013bb6  push    r13
0x180013bb8  push    r14
0x180013bba  push    r15
0x180013bbc  sub     rsp, 0F0h
0x180013bc3  mov     rax, cs:__security_cookie
0x180013bca  xor     rax, rsp
0x180013bcd  mov     [rsp+128h+var_40], rax
0x180013bd5  mov     r12, r8
0x180013bd8  mov     r14, rdx
0x180013bdb  mov     r13, rcx
0x180013bde  mov     rcx, [r8]; pv
0x180013be1  xor     r15d, r15d
0x180013be4  mov     [r8], r15
0x180013be7  test    rcx, rcx
0x180013bea  jz      short loc_180013BF3
0x180013bec  call    cs:__imp_CoTaskMemFree
0x180013bf2  nop
0x180013bf3  xorps   xmm0, xmm0
0x180013bf6  movups  [rsp+128h+var_90], xmm0
0x180013bfe  movups  xmmword ptr [rsp+128h+var_80], xmm0
0x180013c06  movups  xmmword ptr [rsp+128h+var_70], xmm0
0x180013c0e  mov     dword ptr [rsp+128h+var_90], 1
0x180013c19  movups  xmmword ptr [rsp+128h+var_B0], xmm0
0x180013c1e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180013c26  movdqu  [rsp+128h+var_A0], xmm1
0x180013c2f  mov     word ptr [rsp+128h+var_B0], r15w
0x180013c35  lea     r8, [rsp+128h+var_B0]
0x180013c3a  lea     rdx, aDeviceid; "DeviceID"
0x180013c41  mov     rcx, r14
0x180013c44  call    ??$GetProperty@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@RfbWmiQuery@@KAXPEBU_MI_Instance@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RfbWmiQuery::GetProperty<std::wstring>(_MI_Instance const *,ushort const *,std::wstring *)
0x180013c49  lea     r8, [rsp+128h+var_B0]
0x180013c4e  cmp     qword ptr [rsp+128h+var_A0+8], 7
0x180013c57  cmova   r8, qword ptr [rsp+128h+var_B0]
0x180013c5d  mov     edx, 3
0x180013c62  lea     rcx, [rsp+128h+var_90+4]
0x180013c6a  call    cs:__imp__o_wcscpy_s
0x180013c70  mov     [rsp+128h+var_F8], r15d
0x180013c75  lea     r8, [rsp+128h+var_F8]
0x180013c7a  lea     rdx, aDrivetype; "DriveType"
0x180013c81  mov     rcx, r14
0x180013c84  call    ??$GetProperty@K@RfbWmiQuery@@KAXPEBU_MI_Instance@@PEBGPEAK@Z; RfbWmiQuery::GetProperty<ulong>(_MI_Instance const *,ushort const *,ulong *)
0x180013c89  mov     ebx, [rsp+128h+var_F8]
0x180013c8d  cmp     ebx, 2
0x180013c90  jnz     loc_180013D23
0x180013c96  mov     [rsp+128h+var_70+9], 1
0x180013c9e  mov     [rsp+128h+var_70+0Ah], r15b
0x180013ca6  mov     sil, r15b
0x180013ca9  cmp     ebx, 5
0x180013cac  jnz     loc_180013D55
0x180013cb2  lea     r15, [r13+0C0h]
0x180013cb9  mov     rcx, r15; SRWLock
0x180013cbc  call    cs:__imp_AcquireSRWLockShared
0x180013cc2  mov     rdi, [r13+0C8h]
0x180013cc9  mov     rsi, [rdi+8]
0x180013ccd  xor     eax, eax
0x180013ccf  mov     [rsp+128h+var_E4], eax
0x180013cd3  cmp     [rsi+19h], al
0x180013cd6  jnz     short loc_180013CFD
0x180013cd8  lea     rdx, [rsi+20h]
0x180013cdc  lea     r8, [rsp+128h+var_B0]
0x180013ce1  call    ??RLessIgnoreCase@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; LessIgnoreCase::operator()(std::wstring const &,std::wstring const &)
0x180013ce6  test    al, al
0x180013ce8  cmovz   rdi, rsi
0x180013cec  lea     rcx, [rsi+10h]
0x180013cf0  cmovz   rcx, rsi
0x180013cf4  mov     rsi, [rcx]
0x180013cf7  cmp     byte ptr [rsi+19h], 0
0x180013cfb  jz      short loc_180013CD8
0x180013cfd  cmp     byte ptr [rdi+19h], 0
0x180013d01  jnz     short loc_180013D41
0x180013d03  lea     r8, [rdi+20h]
0x180013d07  lea     rdx, [rsp+128h+var_B0]
0x180013d0c  call    ??RLessIgnoreCase@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; LessIgnoreCase::operator()(std::wstring const &,std::wstring const &)
0x180013d11  test    al, al
0x180013d13  jnz     short loc_180013D41
0x180013d15  cmp     rdi, [r13+0C8h]
0x180013d1c  jz      short loc_180013D41
0x180013d1e  mov     sil, 1
0x180013d21  jmp     short loc_180013D44
0x180013d23  mov     [rsp+128h+var_70+9], r15b
0x180013d2b  cmp     ebx, 4
0x180013d2e  jnz     loc_180013C9E
0x180013d34  mov     [rsp+128h+var_70+0Ah], 1
0x180013d3c  mov     sil, r15b
0x180013d3f  jmp     short loc_180013D55
0x180013d41  xor     sil, sil
0x180013d44  test    r15, r15
0x180013d47  jz      short loc_180013D52
0x180013d49  mov     rcx, r15; SRWLock
0x180013d4c  call    cs:__imp_ReleaseSRWLockShared
0x180013d52  xor     r15d, r15d
0x180013d55  mov     [rsp+128h+var_F8], r15d
0x180013d5a  lea     r8, [rsp+128h+var_F8]
0x180013d5f  lea     rdx, aMediatype; "MediaType"
0x180013d66  mov     rcx, r14
0x180013d69  call    ??$GetProperty@K@RfbWmiQuery@@KAXPEBU_MI_Instance@@PEBGPEAK@Z; RfbWmiQuery::GetProperty<ulong>(_MI_Instance const *,ushort const *,ulong *)
0x180013d6e  test    ebx, ebx
0x180013d70  jz      loc_180013E86
0x180013d76  sub     ebx, 1
0x180013d79  jz      loc_180013E86
0x180013d7f  sub     ebx, 1
0x180013d82  jz      short loc_180013DD1
0x180013d84  sub     ebx, 1
0x180013d87  jz      short loc_180013DC5
0x180013d89  sub     ebx, 1
0x180013d8c  jz      short loc_180013DBE
0x180013d8e  sub     ebx, 1
0x180013d91  jz      short loc_180013DA9
0x180013d93  cmp     ebx, 1
0x180013d96  jnz     loc_180013E86
0x180013d9c  mov     ebx, 0Ch
0x180013da1  lea     edi, [rbx-1]
0x180013da4  jmp     loc_180013E8E
0x180013da9  mov     edi, 0Ah
0x180013dae  neg     sil
0x180013db1  sbb     ebx, ebx
0x180013db3  and     ebx, 30h
0x180013db6  add     ebx, 0Bh
0x180013db9  jmp     loc_180013E8E
0x180013dbe  mov     ebx, 9
0x180013dc3  jmp     short loc_180013DCA
0x180013dc5  mov     ebx, 8
0x180013dca  mov     edi, ebx
0x180013dcc  jmp     loc_180013E8E
0x180013dd1  mov     ecx, [rsp+128h+var_F8]
0x180013dd5  cmp     ecx, 0Dh
0x180013dd8  jg      short loc_180013E24
0x180013dda  jz      loc_180013E78
0x180013de0  mov     edi, 6
0x180013de5  cmp     ecx, edi
0x180013de7  jg      short loc_180013E0E
0x180013de9  jz      short loc_180013E4E
0x180013deb  test    ecx, ecx
0x180013ded  jz      short loc_180013E6E
0x180013def  sub     ecx, 1
0x180013df2  jz      short loc_180013E4E
0x180013df4  sub     ecx, 1
0x180013df7  jz      loc_180013E7D
0x180013dfd  sub     ecx, 1
0x180013e00  jz      short loc_180013E7D
0x180013e02  sub     ecx, 1
0x180013e05  jz      short loc_180013E7D
0x180013e07  cmp     ecx, 1
0x180013e0a  jz      short loc_180013E7D
0x180013e0c  jmp     short loc_180013E6E
0x180013e0e  sub     ecx, 7
0x180013e11  jz      short loc_180013E4E
0x180013e13  sub     ecx, 1
0x180013e16  jz      short loc_180013E4E
0x180013e18  sub     ecx, 1
0x180013e1b  jz      short loc_180013E4E
0x180013e1d  cmp     ecx, 1
0x180013e20  jz      short loc_180013E4E
0x180013e22  jmp     short loc_180013E6E
0x180013e24  cmp     ecx, 14h
0x180013e27  jg      short loc_180013E55
0x180013e29  jz      short loc_180013E78
0x180013e2b  sub     ecx, 0Eh
0x180013e2e  jz      short loc_180013E78
0x180013e30  sub     ecx, 1
0x180013e33  jz      short loc_180013E49
0x180013e35  sub     ecx, 1
0x180013e38  jz      short loc_180013E49
0x180013e3a  sub     ecx, 1
0x180013e3d  jz      short loc_180013E78
0x180013e3f  sub     ecx, 1
0x180013e42  jz      short loc_180013E78
0x180013e44  cmp     ecx, 1
0x180013e47  jnz     short loc_180013E6E
0x180013e49  mov     edi, 6
0x180013e4e  mov     ebx, 5
0x180013e53  jmp     short loc_180013E8E
0x180013e55  sub     ecx, 15h
0x180013e58  jz      short loc_180013E78
0x180013e5a  sub     ecx, 1
0x180013e5d  jz      short loc_180013E49
0x180013e5f  sub     ecx, 1
0x180013e62  jz      short loc_180013E78
0x180013e64  sub     ecx, 1
0x180013e67  jz      short loc_180013E78
0x180013e69  cmp     ecx, 1
0x180013e6c  jz      short loc_180013E78
0x180013e6e  mov     ebx, 7
0x180013e73  jmp     loc_180013DCA
0x180013e78  mov     edi, 6
0x180013e7d  mov     ebx, edi
0x180013e7f  mov     edi, 5
0x180013e84  jmp     short loc_180013E8E
0x180013e86  mov     edi, 0Ch
0x180013e8b  lea     ebx, [rdi+2Eh]
0x180013e8e  mov     dword ptr [rsp+128h+var_70+4], edi
0x180013e95  mov     dword ptr [rsp+128h+var_70], ebx
0x180013e9c  cmp     edi, 0Ch
0x180013e9f  jz      loc_180014020
0x180013ea5  xorps   xmm0, xmm0
0x180013ea8  movups  xmmword ptr [rsp+128h+var_D0], xmm0
0x180013ead  mov     [rsp+128h+var_C0], r15
0x180013eb2  mov     [rsp+128h+var_B8], 7
0x180013ebb  mov     word ptr [rsp+128h+var_D0], r15w
0x180013ec1  movups  xmmword ptr [rsp+38h], xmm0
0x180013ec6  mov     [rsp+128h+var_E0], r15
0x180013ecb  mov     [rsp+128h+var_D8], 7
0x180013ed4  mov     word ptr [rsp+128h+var_F0], r15w
0x180013eda  lea     r8, [rsp+128h+var_80]; unsigned __int64 *
0x180013ee2  lea     rdx, aSize; "Size"
0x180013ee9  mov     rcx, r14; struct _MI_Instance *
0x180013eec  call    ?GetNullableProperty@RfbWmiQuery@@KA_NPEBU_MI_Instance@@PEBGPEA_K@Z; RfbWmiQuery::GetNullableProperty(_MI_Instance const *,ushort const *,unsigned __int64 *)
0x180013ef1  lea     r8, [rsp+128h+var_80+8]; unsigned __int64 *
0x180013ef9  lea     rdx, aFreespace; "FreeSpace"
0x180013f00  mov     rcx, r14; struct _MI_Instance *
0x180013f03  call    ?GetNullableProperty@RfbWmiQuery@@KA_NPEBU_MI_Instance@@PEBGPEA_K@Z; RfbWmiQuery::GetNullableProperty(_MI_Instance const *,ushort const *,unsigned __int64 *)
0x180013f08  lea     r8, [rsp+128h+var_70+8]; bool *
0x180013f10  lea     rdx, aCompressed; "Compressed"
0x180013f17  mov     rcx, r14; struct _MI_Instance *
0x180013f1a  call    ?GetNullableProperty@RfbWmiQuery@@KA_NPEBU_MI_Instance@@PEBGPEA_N@Z; RfbWmiQuery::GetNullableProperty(_MI_Instance const *,ushort const *,bool *)
0x180013f1f  lea     r8, [rsp+128h+var_D0]
0x180013f24  lea     rdx, aProvidername; "ProviderName"
0x180013f2b  mov     rcx, r14
0x180013f2e  call    ?GetNullableProperty@RfbWmiQuery@@KA_NPEBU_MI_Instance@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RfbWmiQuery::GetNullableProperty(_MI_Instance const *,ushort const *,std::wstring *)
0x180013f33  test    al, al
0x180013f35  jnz     short loc_180013F51
0x180013f37  lea     rdx, [rsp+128h+var_D0]
0x180013f3c  cmp     [rsp+128h+var_B8], 7
0x180013f42  cmova   rdx, qword ptr [rsp+128h+var_D0]
0x180013f48  mov     [rsp+128h+var_C0], r15
0x180013f4d  mov     [rdx], r15w
0x180013f51  lea     r8, [rsp+128h+var_F0]
0x180013f56  lea     rdx, aVolumename; "VolumeName"
0x180013f5d  mov     rcx, r14
0x180013f60  call    ?GetNullableProperty@RfbWmiQuery@@KA_NPEBU_MI_Instance@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RfbWmiQuery::GetNullableProperty(_MI_Instance const *,ushort const *,std::wstring *)
0x180013f65  test    al, al
0x180013f67  jnz     short loc_180013F83
0x180013f69  lea     rcx, [rsp+128h+var_F0]
0x180013f6e  cmp     [rsp+128h+var_D8], 7
0x180013f74  cmova   rcx, [rsp+128h+var_F0]
0x180013f7a  mov     [rsp+128h+var_E0], r15
0x180013f7f  mov     [rcx], r15w
0x180013f83  xorps   xmm0, xmm0
0x180013f86  movups  [rsp+128h+Src], xmm0
0x180013f8e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180013f96  movdqu  [rsp+128h+var_50], xmm1
0x180013f9f  mov     word ptr [rsp+128h+Src], r15w
0x180013fa8  lea     rax, [rsp+128h+Src]
0x180013fb0  mov     [rsp+128h+var_100], rax; Src
0x180013fb5  lea     rax, [rsp+128h+var_F0]
0x180013fba  mov     [rsp+128h+var_108], rax; __int64
0x180013fbf  lea     r9, [rsp+128h+var_D0]; int
0x180013fc4  mov     r8d, ebx; int
0x180013fc7  mov     edx, edi; int
0x180013fc9  lea     rcx, [rsp+128h+var_B0]; int
0x180013fce  call    ?CreateDisplayName@DiskDataHelper@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KH00AEAV23@@Z; DiskDataHelper::CreateDisplayName(std::wstring const &,ulong,int,std::wstring const &,std::wstring const &,std::wstring &)
0x180013fd3  lea     rdx, [rsp+128h+var_90]
0x180013fdb  lea     rcx, [rsp+128h+Src]; Src
0x180013fe3  call    ?CreatePidl@?$RfbPidlHelper@UFileFixedData@@@@SAPEFBU_ITEMIDLIST@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUFileFixedData@@@Z; RfbPidlHelper<FileFixedData>::CreatePidl(std::wstring const &,FileFixedData const &)
0x180013fe8  mov     rcx, [r12]; pv
0x180013fec  mov     [r12], rax
0x180013ff0  test    rcx, rcx
0x180013ff3  jz      short loc_180013FFC
0x180013ff5  call    cs:__imp_CoTaskMemFree
0x180013ffb  nop
0x180013ffc  lea     rcx, [rsp+128h+Src]
0x180014004  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014009  nop
0x18001400a  lea     rcx, [rsp+128h+var_F0]
0x18001400f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014014  nop
0x180014015  lea     rcx, [rsp+128h+var_D0]
0x18001401a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001401f  nop
0x180014020  lea     rcx, [rsp+128h+var_B0]
0x180014025  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001402a  nop
0x18001402b  mov     rcx, [rsp+128h+var_40]
0x180014033  xor     rcx, rsp; StackCookie
0x180014036  call    __security_check_cookie
0x18001403b  add     rsp, 0F0h
0x180014042  pop     r15
0x180014044  pop     r14
0x180014046  pop     r13
0x180014048  pop     r12
0x18001404a  pop     rdi
0x18001404b  pop     rsi
0x18001404c  pop     rbx
0x18001404d  retn
```
