# fnInternetCallback

- ea: `0x1800468d0`
- end: `0x180048025`
- name: `fnInternetCallback`
- size: `5973`
- prototype: `void __fastcall(HINTERNET hInternet, __int64 *dwContext, DWORD dwInternetStatus, _DWORD *lpvStatusInformation, DWORD dwStatusInformationLength)`
- caller_count: `0`
- callee_count: `40`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003bc0`
- `0x180003f90`
- `0x1800040cc`
- `0x180004696`
- `0x180004710`
- `0x180004970`
- `0x180026f30`
- `0x180029d50`
- `0x18002c6e0`
- `0x18002ccc0`
- `0x18002ccd0`
- `0x18002ce10`
- `0x18002d6e0`
- `0x18002dee0`
- `0x18003aaa0`
- `0x18003f2a0`
- `0x180040360`
- `0x180040470`
- `0x180043230`
- `0x1800449e0`
- `0x180044d40`
- `0x180045a40`
- `0x180046330`
- `0x180046390`
- `0x180046590`
- `0x180046830`
- `0x1800468d0`
- `0x180048400`
- `0x1800488a0`
- `0x180049f60`
- `0x18004b360`
- `0x18004b950`
- `0x18004bcb0`
- `0x180057c20`
- `0x180057e0c`
- `0x180059a94`
- `0x18008f0e4`
- `0x18009000c`
- `0x180096908`
- `0x1800b9010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180046a80`
- `KERNEL32!GetLastError` at `0x180046e96`
- `KERNEL32!GetLastError` at `0x1800470d6`
- `KERNEL32!GetLastError` at `0x1800475fd`
- `KERNEL32!GetLastError` at `0x180047854`
- `KERNEL32!GetLastError` at `0x180046a80`
- `KERNEL32!GetLastError` at `0x180046e96`
- `KERNEL32!GetLastError` at `0x1800470d6`
- `KERNEL32!GetLastError` at `0x1800475fd`
- `KERNEL32!GetLastError` at `0x180047854`
- `WINHTTP!WinHttpReadData` at `0x1800470c8`
- `WINHTTP!WinHttpReadData` at `0x1800470c8`
- `WINHTTP!WinHttpQueryHeaders` at `0x180046a2e`
- `WINHTTP!WinHttpQueryHeaders` at `0x180046a72`
- `WINHTTP!WinHttpQueryHeaders` at `0x180046e44`
- `WINHTTP!WinHttpQueryHeaders` at `0x180046e88`
- `WINHTTP!WinHttpQueryHeaders` at `0x180046a2e`
- `WINHTTP!WinHttpQueryHeaders` at `0x180046a72`
- `WINHTTP!WinHttpQueryHeaders` at `0x180046e44`
- `WINHTTP!WinHttpQueryHeaders` at `0x180046e88`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800475ef`
- `WINHTTP!WinHttpReceiveResponse` at `0x180047846`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800475ef`
- `WINHTTP!WinHttpReceiveResponse` at `0x180047846`

## string_xrefs

- `0x18004736e`: `Received incomplete compressed stream`
- `0x180047ad5`: `Received incomplete compressed stream`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall fnInternetCallback(
        HINTERNET hInternet,
        __int64 *dwContext,
        DWORD dwInternetStatus,
        _DWORD *lpvStatusInformation,
        DWORD dwStatusInformationLength)
{
  volatile signed __int32 *v7; // rdx
  __m128i v8; // xmm6
  signed __int32 v9; // eax
  signed __int32 v10; // ett
  __m128i v11; // xmm0
  __int64 v12; // r14
  volatile signed __int32 *v13; // rdi
  DWORD v14; // ebx
  __int64 v15; // rax
  void *v16; // rcx
  __int16 v17; // cx
  void *v18; // rcx
  _QWORD *v19; // rax
  __int64 v20; // rax
  void *v21; // rcx
  void *v22; // rax
  __int64 v23; // rax
  DWORD LastError; // ebx
  __int64 v25; // rax
  void *v26; // rcx
  unsigned __int64 v27; // rsi
  void *v28; // rbx
  __int64 v29; // rax
  DWORD v30; // ebx
  __int64 v31; // rax
  void *v32; // rcx
  void *v33; // rcx
  char *v34; // rax
  __int64 v35; // rbx
  __int64 v36; // rax
  __int64 v37; // rcx
  volatile signed __int32 *v38; // rbx
  __int64 v39; // rbx
  __int64 v40; // rax
  __int64 v41; // rax
  volatile signed __int32 *v42; // rbx
  bool v43; // r12
  __int64 v44; // rbx
  __int64 v45; // rax
  __int64 v46; // rcx
  volatile signed __int32 *v47; // rbx
  int v48; // eax
  DWORD v49; // ebx
  __int64 v50; // rax
  unsigned int v51; // esi
  __int64 v52; // rax
  void *v53; // rcx
  __int64 v54; // r12
  __int64 v55; // rbx
  __int64 v56; // rax
  __int64 v57; // rcx
  volatile signed __int32 *v58; // rbx
  __int64 v59; // rax
  __int64 v60; // rdx
  int v61; // eax
  DWORD v62; // ebx
  __int64 v63; // rax
  void *v64; // rcx
  __int64 v65; // rbx
  __int64 v66; // rax
  __int64 v67; // rcx
  void *v68; // rcx
  unsigned __int64 v69; // rcx
  unsigned __int64 v70; // rax
  __int64 v71; // rax
  volatile signed __int32 *v72; // r14
  volatile signed __int32 *v73; // r14
  volatile signed __int32 *v74; // r14
  __int64 v75; // r8
  volatile signed __int32 *v76; // r14
  volatile signed __int32 *v77; // r14
  DWORD dwBufferLength[4]; // [rsp+30h] [rbp-1A8h] BYREF
  void *v79[2]; // [rsp+40h] [rbp-198h] BYREF
  LPVOID lpBuffer[2]; // [rsp+50h] [rbp-188h] BYREF
  __int128 v81; // [rsp+60h] [rbp-178h]
  __m128i v82; // [rsp+70h] [rbp-168h] BYREF
  __int64 v83; // [rsp+80h] [rbp-158h]
  volatile signed __int32 *v84; // [rsp+88h] [rbp-150h]
  char v85[8]; // [rsp+90h] [rbp-148h] BYREF
  volatile signed __int32 *v86; // [rsp+98h] [rbp-140h]
  _BYTE pExceptionObject[24]; // [rsp+A0h] [rbp-138h] BYREF
  _BYTE v88[24]; // [rsp+B8h] [rbp-120h] BYREF
  _BYTE v89[24]; // [rsp+D0h] [rbp-108h] BYREF
  void *Block[2]; // [rsp+E8h] [rbp-F0h] BYREF
  __int128 v91; // [rsp+F8h] [rbp-E0h]
  void *Src[2]; // [rsp+108h] [rbp-D0h] BYREF
  volatile signed __int32 *v93; // [rsp+118h] [rbp-C0h]
  unsigned __int64 v94; // [rsp+120h] [rbp-B8h]
  void **v95; // [rsp+130h] [rbp-A8h] BYREF
  __int128 v96; // [rsp+138h] [rbp-A0h] BYREF
  int v97; // [rsp+148h] [rbp-90h]
  __int64 (__fastcall ***v98)(); // [rsp+150h] [rbp-88h]
  void *v99[2]; // [rsp+158h] [rbp-80h] BYREF
  __int128 v100; // [rsp+168h] [rbp-70h]

  if ( !dwContext )
    return;
  v7 = (volatile signed __int32 *)dwContext[1];
  if ( dwInternetStatus == 2048 )
  {
    if ( v7 )
    {
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
    j_j_free_0(dwContext);
    return;
  }
  v8 = 0;
  v82 = 0;
  if ( v7 && (v9 = *((_DWORD *)v7 + 2)) != 0 )
  {
    while ( 1 )
    {
      v10 = v9;
      v9 = _InterlockedCompareExchange(v7 + 2, v9 + 1, v9);
      if ( v10 == v9 )
        break;
      if ( !v9 )
      {
        v11 = 0;
        goto LABEL_14;
      }
    }
    v12 = *dwContext;
    v82.m128i_i64[0] = *dwContext;
    v13 = (volatile signed __int32 *)dwContext[1];
    v82.m128i_i64[1] = (__int64)v13;
    v8 = _mm_load_si128(&v82);
  }
  else
  {
    v11 = 0;
LABEL_14:
    v12 = 0;
    v13 = (volatile signed __int32 *)_mm_srli_si128(v11, 8).m128i_u64[0];
  }
  if ( !v12 )
  {
    if ( !v13 )
      return;
LABEL_250:
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
    return;
  }
  if ( dwInternetStatus <= 0x40000 )
  {
    if ( dwInternetStatus != 0x40000 )
    {
      if ( dwInternetStatus == 16 )
      {
        sub_180049F60(v12);
        if ( !v13 )
          return;
        goto LABEL_250;
      }
      if ( dwInternetStatus == 0x4000 )
      {
        v23 = *(_QWORD *)(v12 + 128);
        if ( v23 )
        {
          *(_QWORD *)(v12 + 128) = v23 - 1;
          if ( !v13 )
            return;
          goto LABEL_250;
        }
        dwBufferLength[0] = 0;
        WinHttpQueryHeaders(hInternet, 0x16u, 0, 0, dwBufferLength, 0);
        *(_OWORD *)lpBuffer = 0;
        *(_QWORD *)&v81 = 0;
        sub_180026F30(lpBuffer, dwBufferLength[0]);
        if ( WinHttpQueryHeaders(hInternet, 0x16u, 0, lpBuffer[0], dwBufferLength, 0) )
        {
          sub_18004B360(hInternet);
          sub_18002CCD0(v12);
          sub_180046330(v12, 0, 0);
          sub_18002CE10(v12, 0);
          sub_180046830(v12);
        }
        else
        {
          LastError = GetLastError();
          *(_OWORD *)Block = 0;
          v79[0] = (void *)31;
          Block[0] = (void *)sub_180057C20(Block, v79);
          *(_QWORD *)&v91 = 19;
          *((void **)&v91 + 1) = v79[0];
          strcpy((char *)Block[0], "WinHttpQueryHeaders");
          v25 = sub_180046390(Src);
          sub_18002DEE0(v12, LastError, v25);
          sub_180059A94(Src);
          sub_180059A94(Block);
        }
        goto LABEL_66;
      }
      if ( dwInternetStatus != 0x10000 )
      {
        if ( dwInternetStatus == 0x20000 )
        {
          dwBufferLength[0] = 0;
          WinHttpQueryHeaders(hInternet, 0x16u, 0, 0, dwBufferLength, 0);
          *(_OWORD *)lpBuffer = 0;
          *(_QWORD *)&v81 = 0;
          sub_180026F30(lpBuffer, dwBufferLength[0]);
          if ( !WinHttpQueryHeaders(hInternet, 0x16u, 0, lpBuffer[0], dwBufferLength, 0) )
          {
            v14 = GetLastError();
            *(_OWORD *)Block = 0;
            v91 = 0u;
            sub_180057E0C(Block, "WinHttpQueryHeaders", 19);
            v15 = sub_180046390(Src);
            sub_18002DEE0(v12, v14, v15);
            sub_180059A94(Src);
            if ( *((_QWORD *)&v91 + 1) > 0xFu )
            {
              if ( (unsigned __int64)(*((_QWORD *)&v91 + 1) + 1LL) < 0x1000 )
              {
                v16 = Block[0];
              }
              else
              {
                v16 = (void *)*((_QWORD *)Block[0] - 1);
                if ( (unsigned __int64)((char *)Block[0] - (char *)v16 - 8) > 0x1F )
                  __fastfail(5u);
              }
              j_j_free_0(v16);
            }
LABEL_66:
            if ( !lpBuffer[0] )
              goto LABEL_72;
            if ( (unsigned __int64)v81 - (unsigned __int64)lpBuffer[0] < 0x1000 )
            {
              v26 = lpBuffer[0];
LABEL_71:
              j_j_free_0(v26);
              *(_OWORD *)lpBuffer = 0;
              *(_QWORD *)&v81 = 0;
LABEL_72:
              if ( v13 )
                sub_180096908(v13);
              return;
            }
            v26 = (void *)*((_QWORD *)lpBuffer[0] - 1);
            if ( (unsigned __int64)((char *)lpBuffer[0] - (char *)v26 - 8) <= 0x1F )
              goto LABEL_71;
LABEL_182:
            __fastfail(5u);
          }
          sub_18004B360(hInternet);
          v17 = *(_WORD *)(*(_QWORD *)(v12 + 40) + 136LL);
          if ( v17 == 401 || v17 == 407 )
          {
            if ( sub_1800488A0(hInternet, (const WCHAR *)&v82, 0) )
            {
              if ( lpBuffer[0] )
              {
                if ( (unsigned __int64)v81 - (unsigned __int64)lpBuffer[0] < 0x1000 )
                {
                  v18 = lpBuffer[0];
                }
                else
                {
                  v18 = (void *)*((_QWORD *)lpBuffer[0] - 1);
                  if ( (unsigned __int64)((char *)lpBuffer[0] - (char *)v18 - 8) > 0x1F )
                    goto LABEL_182;
                }
                j_j_free_0(v18);
                *(_OWORD *)lpBuffer = 0;
                *(_QWORD *)&v81 = 0;
              }
              goto LABEL_141;
            }
            v13 = (volatile signed __int32 *)v82.m128i_i64[1];
            v12 = v82.m128i_i64[0];
          }
          if ( (unsigned __int8)sub_18002D6E0(v12) )
          {
            if ( *(_QWORD *)(v12 + 96) && !*(_BYTE *)(sub_18002CCC0(*(_QWORD *)(v12 + 8)) + 424) )
            {
              v19 = (_QWORD *)sub_1800040CC(0x10u);
              v79[0] = v19;
              if ( v19 )
              {
                *v19 = 0;
                *((_DWORD *)v19 + 2) = 1;
                *((_BYTE *)v19 + 12) = 0;
              }
              else
              {
                v19 = 0;
              }
              v79[0] = v19;
              sub_18003AAA0(v12 + 320, v79);
              if ( v79[0] )
                j_j_free_0(v79[0]);
              *(_BYTE *)(v12 + 307) = 1;
            }
            sub_18002CCD0(v12);
            if ( (unsigned __int8)sub_180004970(*(_QWORD *)(v12 + 24) + 144LL, &qword_18011BE88) )
            {
              sub_180046330(v12, 0, 0);
              sub_18002CE10(v12, 0);
            }
            else
            {
              sub_18004B950(v12, 0, 1);
            }
          }
          goto LABEL_66;
        }
        goto LABEL_124;
      }
      v20 = sub_180048400(Src);
      v96 = 0;
      v95 = &web::http::http_exception::`vftable';
      v97 = 0;
      v98 = &off_180106020;
      *(_OWORD *)v99 = 0;
      v100 = 0u;
      v99[0] = *(void **)v20;
      v99[1] = *(void **)(v20 + 8);
      v100 = *(_OWORD *)(v20 + 16);
      *(_QWORD *)(v20 + 24) = 15;
      *(_BYTE *)v20 = 0;
      *(_QWORD *)(v20 + 16) = 0;
      *(_QWORD *)(v20 + 24) = 15;
      *(_BYTE *)v20 = 0;
      sub_180029D50(v12, &v95);
      if ( *((_QWORD *)&v100 + 1) > 0xFu )
      {
        v21 = v99[0];
        if ( (unsigned __int64)(*((_QWORD *)&v100 + 1) + 1LL) < 0x1000 )
        {
LABEL_58:
          j_j_free_0(v21);
          goto LABEL_59;
        }
        v22 = (void *)*((_QWORD *)v99[0] - 1);
        if ( (unsigned __int64)((char *)v99[0] - (char *)v22 - 8) > 0x1F )
          goto LABEL_182;
LABEL_57:
        v21 = v22;
        goto LABEL_58;
      }
      goto LABEL_59;
    }
    v27 = (unsigned int)*lpvStatusInformation;
    if ( (_DWORD)v27 )
    {
      if ( *(_QWORD *)(v12 + 96) )
      {
        if ( *(_QWORD *)(v12 + 272) - *(_QWORD *)(v12 + 256) < v27 )
          sub_18004BCB0(v12 + 256, (unsigned int)v27);
        v28 = *(void **)(v12 + 256);
      }
      else
      {
        sub_18002C6E0(v12, Block);
        if ( !Block[1] )
        {
          sub_18008F0E4(pExceptionObject, "Invalid streambuf object");
          throw (std::invalid_argument *)pExceptionObject;
        }
        v29 = (*(__int64 (__fastcall **)(void *, unsigned __int64))(*(_QWORD *)Block[1] + 224LL))(Block[1], v27);
        if ( v29 )
        {
          *(_QWORD *)(v12 + 248) = v27;
        }
        else
        {
          if ( v27 > *(_QWORD *)(v12 + 232) - *(_QWORD *)(v12 + 224) )
            sub_180026F30(v12 + 224, v27);
          v29 = 0;
        }
        *(_QWORD *)(v12 + 216) = v29;
        v28 = (void *)v29;
        if ( !v29 )
          v28 = *(void **)(v12 + 224);
        std::_Func_impl<std::_Callable_obj<_lambda_8b695f9820225e821433c25f6ed27cb8_,0>,std::allocator<std::_Func_class<Concurrency::task<bool>,bool>>,Concurrency::task<bool>,bool>::~_Func_impl<std::_Callable_obj<_lambda_8b695f9820225e821433c25f6ed27cb8_,0>,std::allocator<std::_Func_class<Concurrency::task<bool>,bool>>,Concurrency::task<bool>,bool>(Block);
      }
      if ( !WinHttpReadData(hInternet, v28, v27, 0) )
      {
        v30 = GetLastError();
        *(_QWORD *)&v91 = 15;
        *((_QWORD *)&v91 + 1) = 15;
        strcpy((char *)Block, "WinHttpReadData");
        v31 = sub_180046390(Src);
        sub_18002DEE0(v12, v30, v31);
        if ( v94 > 0xF )
        {
          if ( v94 + 1 < 0x1000 )
          {
            v32 = Src[0];
          }
          else
          {
            v32 = (void *)*((_QWORD *)Src[0] - 1);
            if ( (unsigned __int64)((char *)Src[0] - (char *)v32 - 8) > 0x1F )
              __fastfail(5u);
          }
          j_j_free_0(v32);
        }
        v93 = 0;
        v94 = 15;
        LOBYTE(Src[0]) = 0;
        if ( *((_QWORD *)&v91 + 1) > 0xFu )
        {
          if ( (unsigned __int64)(*((_QWORD *)&v91 + 1) + 1LL) < 0x1000 )
          {
            j_j_free_0(Block[0]);
          }
          else
          {
            v33 = (void *)*((_QWORD *)Block[0] - 1);
            if ( (unsigned __int64)((char *)Block[0] - (char *)v33 - 8) > 0x1F )
              goto LABEL_182;
            j_j_free_0(v33);
          }
        }
      }
      goto LABEL_249;
    }
    if ( *(_QWORD *)(v12 + 96) )
    {
      if ( *(_BYTE *)(v12 + 307) )
      {
        v34 = (char *)sub_1800040CC(0x30u);
        strcpy(v34, "Chunked response stream ended unexpectedly");
        v96 = 0;
        v95 = &web::http::http_exception::`vftable';
        v97 = 0;
        v98 = &off_180106020;
        v99[0] = v34;
        v99[1] = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        *(_QWORD *)&v100 = 42;
        *((_QWORD *)&v100 + 1) = 47;
        sub_180029D50(v12, &v95);
        if ( *((_QWORD *)&v100 + 1) > 0xFu )
        {
          v22 = v99[0];
          if ( (unsigned __int64)(*((_QWORD *)&v100 + 1) + 1LL) >= 0x1000 )
          {
            v21 = (void *)*((_QWORD *)v99[0] - 1);
            if ( (unsigned __int64)((char *)v99[0] - (char *)v21 - 8) > 0x1F )
              goto LABEL_182;
            goto LABEL_58;
          }
          goto LABEL_57;
        }
LABEL_59:
        *(_QWORD *)&v100 = 0;
        *((_QWORD *)&v100 + 1) = 15;
        LOBYTE(v99[0]) = 0;
        v95 = &std::exception::`vftable';
        _std_exception_destroy(&v96);
        if ( !v13 )
          return;
        goto LABEL_250;
      }
      if ( *(_BYTE *)(v12 + 305) && !*(_BYTE *)(v12 + 306) )
      {
        *(_OWORD *)Block = 0;
        v91 = 0u;
        sub_180057E0C(Block, "Received incomplete compressed stream", 37);
        v96 = 0;
        v95 = &web::http::http_exception::`vftable';
        v97 = 0;
        v98 = &off_180106020;
        *(_OWORD *)v99 = *(_OWORD *)Block;
        v100 = v91;
        sub_180029D50(v12, &v95);
        sub_180059A94(v99);
        v95 = &std::exception::`vftable';
        _std_exception_destroy(&v96);
        if ( v13 )
          sub_180096908(v13);
        return;
      }
    }
    v35 = *(_QWORD *)(v12 + 24);
    v36 = *(_QWORD *)(v35 + 720);
    if ( v36 )
      _InterlockedIncrement((volatile signed __int32 *)(v36 + 8));
    v37 = *(_QWORD *)(v35 + 712);
    v83 = v37;
    v38 = *(volatile signed __int32 **)(v35 + 720);
    v84 = v38;
    if ( v37 )
      sub_180043230(v37, 1);
    sub_18002CE10(v12, *(_QWORD *)(v12 + 64));
    if ( !v38 )
      goto LABEL_249;
LABEL_246:
    if ( _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
      if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
    }
    goto LABEL_249;
  }
  if ( dwInternetStatus != 0x80000 )
  {
    switch ( dwInternetStatus )
    {
      case 0x100000u:
        v54 = (unsigned int)*lpvStatusInformation;
        if ( (_DWORD)v54 )
        {
          v55 = *(_QWORD *)(v12 + 24);
          v56 = *(_QWORD *)(v55 + 720);
          if ( v56 )
            _InterlockedIncrement((volatile signed __int32 *)(v56 + 8));
          v57 = *(_QWORD *)(v55 + 712);
          v83 = v57;
          v58 = *(volatile signed __int32 **)(v55 + 720);
          v84 = v58;
          if ( v57 )
          {
            *(_QWORD *)(v12 + 56) += v54;
            sub_180043230(v57, 0);
          }
          if ( v58 )
          {
            if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
              if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
            }
          }
        }
        if ( *(_QWORD *)(v12 + 216) )
        {
          v59 = sub_1800449E0(v12, Block);
          v60 = *(_QWORD *)(v12 + 216);
          if ( !v60 )
            v60 = *(_QWORD *)(v12 + 224);
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v59 + 248LL))(v59, v60, v54);
          std::_Func_impl<std::_Callable_obj<_lambda_8b695f9820225e821433c25f6ed27cb8_,0>,std::allocator<std::_Func_class<Concurrency::task<bool>,bool>>,Concurrency::task<bool>,bool>::~_Func_impl<std::_Callable_obj<_lambda_8b695f9820225e821433c25f6ed27cb8_,0>,std::allocator<std::_Func_class<Concurrency::task<bool>,bool>>,Concurrency::task<bool>,bool>(Block);
        }
        v61 = *(_DWORD *)(v12 + 136);
        if ( v61 == 2 )
        {
LABEL_146:
          sub_180045A40(v12);
          goto LABEL_249;
        }
        if ( v61 != 1 )
        {
          if ( !WinHttpReceiveResponse(hInternet, 0) )
          {
            v62 = GetLastError();
            *(_OWORD *)Block = 0;
            v79[0] = (void *)31;
            Block[0] = (void *)sub_180057C20(Block, v79);
            *(_QWORD *)&v91 = 22;
            *((void **)&v91 + 1) = v79[0];
            strcpy((char *)Block[0], "WinHttpReceiveResponse");
            v63 = sub_180046390(Src);
            sub_18002DEE0(v12, v62, v63);
            sub_180059A94(Src);
            if ( *((_QWORD *)&v91 + 1) > 0xFu )
            {
              if ( (unsigned __int64)(*((_QWORD *)&v91 + 1) + 1LL) < 0x1000 )
              {
                j_j_free_0(Block[0]);
              }
              else
              {
                v64 = (void *)*((_QWORD *)Block[0] - 1);
                if ( (unsigned __int64)((char *)Block[0] - (char *)v64 - 8) > 0x1F )
                  goto LABEL_182;
                j_j_free_0(v64);
              }
            }
          }
LABEL_249:
          if ( !v13 )
            return;
          goto LABEL_250;
        }
        break;
      case 0x200000u:
        v51 = lpvStatusInformation[2];
        if ( v51 == 12032 )
        {
          if ( sub_1800488A0(hInternet, (const WCHAR *)&v82, 0x2F00u) )
          {
LABEL_141:
            if ( v82.m128i_i64[1] )
              sub_180096908(v82.m128i_i64[1]);
            return;
          }
          v13 = (volatile signed __int32 *)v82.m128i_i64[1];
          v12 = v82.m128i_i64[0];
        }
        v52 = sub_180046590(Src);
        sub_18002DEE0(v12, v51, v52);
        if ( v94 > 0xF )
        {
          if ( v94 + 1 < 0x1000 )
          {
            v53 = Src[0];
          }
          else
          {
            v53 = (void *)*((_QWORD *)Src[0] - 1);
            if ( (unsigned __int64)((char *)Src[0] - (char *)v53 - 8) > 0x1F )
              goto LABEL_182;
          }
          j_j_free_0(v53);
        }
        if ( !v13 )
          return;
        goto LABEL_250;
      case 0x400000u:
        v39 = *(_QWORD *)(v12 + 24);
        v40 = *(_QWORD *)(v39 + 56);
        if ( v40 )
          _InterlockedIncrement((volatile signed __int32 *)(v40 + 8));
        v41 = *(_QWORD *)(v39 + 48);
        v42 = *(volatile signed __int32 **)(v39 + 56);
        v43 = !v41 || !*(_QWORD *)(v41 + 8);
        if ( v42 )
        {
          if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
            if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
          }
        }
        if ( v43 )
        {
          v44 = *(_QWORD *)(v12 + 24);
          v45 = *(_QWORD *)(v44 + 720);
          if ( v45 )
            _InterlockedIncrement((volatile signed __int32 *)(v45 + 8));
          v46 = *(_QWORD *)(v44 + 712);
          v83 = v46;
          v47 = *(volatile signed __int32 **)(v44 + 720);
          v84 = v47;
          if ( v46 )
            sub_180043230(v46, 0);
          if ( v47 )
            sub_180096908(v47);
        }
        v48 = *(_DWORD *)(v12 + 136);
        if ( v48 == 2 )
          goto LABEL_146;
        if ( v48 != 1 )
        {
          if ( !WinHttpReceiveResponse(hInternet, 0) )
          {
            v49 = GetLastError();
            *(_OWORD *)Src = 0;
            v93 = 0;
            v94 = 0;
            sub_180057E0C(Src, &xmmword_1800CE850, 22);
            v50 = sub_180046390(Block);
            sub_18002DEE0(v12, v49, v50);
            sub_180059A94(Block);
            sub_180059A94(Src);
          }
          goto LABEL_249;
        }
        break;
      default:
LABEL_124:
        if ( !v13 )
          return;
        goto LABEL_250;
    }
    sub_180044D40(v12);
    goto LABEL_249;
  }
  v65 = *(_QWORD *)(v12 + 24);
  v66 = *(_QWORD *)(v65 + 720);
  if ( v66 )
    _InterlockedIncrement((volatile signed __int32 *)(v66 + 8));
  v83 = *(_QWORD *)(v65 + 712);
  v67 = v83;
  v38 = *(volatile signed __int32 **)(v65 + 720);
  v84 = v38;
  *(_QWORD *)(v12 + 64) += dwStatusInformationLength;
  if ( v67 )
    sub_180043230(v67, 1);
  if ( dwStatusInformationLength )
  {
    sub_18002C6E0(v12, Block);
    if ( *(_QWORD *)(v12 + 96) )
    {
      v69 = *(_QWORD *)(sub_18002CCC0(*(_QWORD *)(v12 + 8)) + 416);
      if ( !v69 )
        v69 = 0x10000;
      v70 = dwStatusInformationLength;
      if ( dwStatusInformationLength < v69 )
        v70 = v69;
      *(_QWORD *)(v12 + 288) = dwStatusInformationLength;
      *(_QWORD *)(v12 + 312) = 0;
      if ( v13 )
        _InterlockedIncrement(v13 + 2);
      *(__m128i *)v79 = v8;
      *(_OWORD *)Src = 0;
      if ( v13 )
        _InterlockedIncrement(v13 + 2);
      Src[0] = (void *)v12;
      Src[1] = (void *)v13;
      v93 = (volatile signed __int32 *)v70;
      v94 = v70;
      v71 = sub_18003F2A0(lpBuffer, Src);
      sub_180040360(v71, v85, v79);
      v72 = v86;
      if ( v86 )
      {
        if ( _InterlockedExchangeAdd(v86 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v72)(v72);
          if ( _InterlockedExchangeAdd(v72 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v72 + 8LL))(v72);
        }
      }
      v73 = (volatile signed __int32 *)lpBuffer[1];
      if ( lpBuffer[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpBuffer[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v73)(v73);
          if ( _InterlockedExchangeAdd(v73 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v73 + 8LL))(v73);
        }
      }
      v74 = (volatile signed __int32 *)v79[1];
    }
    else
    {
      if ( *(_QWORD *)(v12 + 216) )
      {
        if ( !Block[1] )
        {
          sub_18008F0E4(v88, "Invalid streambuf object");
          throw (std::invalid_argument *)v88;
        }
        (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)Block[1] + 232LL))(Block[1], dwStatusInformationLength);
        sub_18004B950(v12, dwStatusInformationLength, 0);
        goto LABEL_244;
      }
      Src[0] = hInternet;
      if ( v13 )
        _InterlockedIncrement(v13 + 2);
      Src[1] = (void *)v12;
      v93 = v13;
      LODWORD(v94) = dwStatusInformationLength;
      v75 = *(_QWORD *)(v12 + 216);
      if ( !v75 )
        v75 = *(_QWORD *)(v12 + 224);
      if ( !Block[1] )
      {
        sub_18008F0E4(v89, "Invalid streambuf object");
        throw (std::invalid_argument *)v89;
      }
      (*(void (__fastcall **)(void *, void **, __int64, _QWORD))(*(_QWORD *)Block[1] + 112LL))(
        Block[1],
        v79,
        v75,
        dwStatusInformationLength);
      sub_180040470(v79, lpBuffer, Src);
      v76 = (volatile signed __int32 *)lpBuffer[1];
      if ( lpBuffer[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpBuffer[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
          if ( _InterlockedExchangeAdd(v76 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
        }
      }
      v77 = (volatile signed __int32 *)v79[1];
      if ( v79[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v79[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v77)(v77);
          if ( _InterlockedExchangeAdd(v77 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v77 + 8LL))(v77);
        }
      }
      v74 = v93;
    }
    if ( v74 )
    {
      if ( _InterlockedExchangeAdd(v74 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v74)(v74);
        if ( _InterlockedExchangeAdd(v74 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v74 + 8LL))(v74);
      }
    }
LABEL_244:
    std::_Func_impl<std::_Callable_obj<_lambda_8b695f9820225e821433c25f6ed27cb8_,0>,std::allocator<std::_Func_class<Concurrency::task<bool>,bool>>,Concurrency::task<bool>,bool>::~_Func_impl<std::_Callable_obj<_lambda_8b695f9820225e821433c25f6ed27cb8_,0>,std::allocator<std::_Func_class<Concurrency::task<bool>,bool>>,Concurrency::task<bool>,bool>(Block);
LABEL_245:
    if ( !v38 )
      goto LABEL_249;
    goto LABEL_246;
  }
  if ( !*(_QWORD *)(v12 + 96) )
    goto LABEL_204;
  if ( *(_BYTE *)(v12 + 307) )
  {
    lpBuffer[1] = 0;
    lpBuffer[0] = (LPVOID)sub_1800040CC(0x30u);
    *(_QWORD *)&v81 = 42;
    *((_QWORD *)&v81 + 1) = 47;
    strcpy((char *)lpBuffer[0], "Chunked response stream ended unexpectedly");
    v96 = 0;
    v95 = &web::http::http_exception::`vftable';
    v97 = 0;
    v98 = &off_180106020;
    *(_OWORD *)v99 = *(_OWORD *)lpBuffer;
    v100 = v81;
    sub_180029D50(v12, &v95);
    sub_180059A94(v99);
    v95 = &std::exception::`vftable';
    _std_exception_destroy(&v96);
    goto LABEL_245;
  }
  if ( !*(_BYTE *)(v12 + 305) || *(_BYTE *)(v12 + 306) )
  {
LABEL_204:
    sub_18002CE10(v12, *(_QWORD *)(v12 + 64));
    goto LABEL_245;
  }
  *(_OWORD *)lpBuffer = 0;
  v81 = 0u;
  sub_180057E0C(lpBuffer, "Received incomplete compressed stream", 37);
  v96 = 0;
  v95 = &web::http::http_exception::`vftable';
  v97 = 0;
  v98 = &off_180106020;
  v99[0] = lpBuffer[0];
  v99[1] = lpBuffer[1];
  v100 = v81;
  sub_180029D50(v12, &v95);
  if ( *((_QWORD *)&v100 + 1) > 0xFu )
  {
    if ( (unsigned __int64)(*((_QWORD *)&v100 + 1) + 1LL) < 0x1000 )
    {
      v68 = v99[0];
    }
    else
    {
      v68 = (void *)*((_QWORD *)v99[0] - 1);
      if ( (unsigned __int64)((char *)v99[0] - (char *)v68 - 8) > 0x1F )
        __fastfail(5u);
    }
    j_j_free_0(v68);
  }
  *(_QWORD *)&v100 = 0;
  *((_QWORD *)&v100 + 1) = 15;
  LOBYTE(v99[0]) = 0;
  v95 = &std::exception::`vftable';
  _std_exception_destroy(&v96);
  if ( v38 )
    sub_180096908(v38);
  if ( v13 )
    sub_180096908(v13);
}

```

## disassembly

```asm
0x1800468d0  test    rdx, rdx
0x1800468d3  jz      locret_180047FA9
0x1800468d9  push    rbx
0x1800468da  push    rsi
0x1800468db  push    rdi
0x1800468dc  push    r12
0x1800468de  push    r13
0x1800468e0  push    r14
0x1800468e2  push    r15
0x1800468e4  sub     rsp, 1A0h
0x1800468eb  movaps  [rsp+1D8h+var_48], xmm6
0x1800468f3  mov     rax, cs:__security_cookie
0x1800468fa  xor     rax, rsp
0x1800468fd  mov     [rsp+1D8h+var_58], rax
0x180046905  mov     rbx, r9
0x180046908  mov     rdi, rdx
0x18004690b  mov     r15, rcx
0x18004690e  xor     r13d, r13d
0x180046911  mov     rdx, [rdx+8]
0x180046915  cmp     r8d, 800h
0x18004691c  jnz     short loc_180046953
0x18004691e  test    rdx, rdx
0x180046921  jz      short loc_180046941
0x180046923  mov     esi, 0FFFFFFFFh
0x180046928  lock xadd [rdx+0Ch], esi
0x18004692d  cmp     esi, 1
0x180046930  jnz     short loc_180046941
0x180046932  mov     rax, [rdx]
0x180046935  mov     rcx, rdx
0x180046938  mov     rax, [rax+8]
0x18004693c  call    j__guard_dispatch_icall
0x180046941  mov     edx, 10h
0x180046946  mov     rcx, rdi; Block
0x180046949  call    j_j_free_0
0x18004694e  jmp     loc_180047F7F
0x180046953  xorps   xmm6, xmm6
0x180046956  movdqa  [rsp+1D8h+var_168], xmm6
0x18004695c  test    rdx, rdx
0x18004695f  jz      short loc_18004699D
0x180046961  mov     eax, [rdx+8]
0x180046964  test    eax, eax
0x180046966  jz      short loc_18004699D
0x180046968  nop     dword ptr [rax+rax+00000000h]
0x180046970  lea     ecx, [rax+1]
0x180046973  lock cmpxchg [rdx+8], ecx
0x180046978  jz      short loc_180046984
0x18004697a  test    eax, eax
0x18004697c  jnz     short loc_180046970
0x18004697e  movdqa  xmm0, xmm6
0x180046982  jmp     short loc_1800469A0
0x180046984  mov     r14, [rdi]
0x180046987  mov     qword ptr [rsp+1D8h+var_168], r14
0x18004698c  mov     rdi, [rdi+8]
0x180046990  mov     qword ptr [rsp+1D8h+var_168+8], rdi
0x180046995  movdqa  xmm6, [rsp+1D8h+var_168]
0x18004699b  jmp     short loc_1800469AF
0x18004699d  xorps   xmm0, xmm0
0x1800469a0  psrldq  xmm0, 8
0x1800469a5  movq    r14, xmm6
0x1800469aa  movq    rdi, xmm0
0x1800469af  test    r14, r14
0x1800469b2  jnz     short loc_1800469C7
0x1800469b4  test    rdi, rdi
0x1800469b7  jz      loc_180047F7F
0x1800469bd  mov     esi, 0FFFFFFFFh
0x1800469c2  jmp     loc_180047F4C
0x1800469c7  cmp     r8d, 40000h
0x1800469ce  ja      loc_180047490
0x1800469d4  jz      loc_180046FF7
0x1800469da  cmp     r8d, 10h
0x1800469de  jz      loc_180046FDB
0x1800469e4  cmp     r8d, 4000h
0x1800469eb  jz      loc_180046DF9
0x1800469f1  mov     eax, 10000h
0x1800469f6  cmp     r8d, eax
0x1800469f9  jz      loc_180046CB4
0x1800469ff  cmp     r8d, 20000h
0x180046a06  jnz     loc_1800474C0
0x180046a0c  mov     [rsp+1D8h+dwBufferLength], r13d
0x180046a11  mov     [rsp+1D8h+lpdwIndex], r13; lpdwIndex
0x180046a16  lea     rax, [rsp+1D8h+dwBufferLength]
0x180046a1b  mov     [rsp+1D8h+lpdwBufferLength], rax; lpdwBufferLength
0x180046a20  xor     r9d, r9d; lpBuffer
0x180046a23  xor     r8d, r8d; pwszName
0x180046a26  mov     edx, 16h; dwInfoLevel
0x180046a2b  mov     rcx, r15; hRequest
0x180046a2e  call    cs:WinHttpQueryHeaders
0x180046a34  xorps   xmm0, xmm0
0x180046a37  movdqu  xmmword ptr [rsp+1D8h+lpBuffer], xmm0
0x180046a3d  mov     qword ptr [rsp+1D8h+var_178], r13
0x180046a42  mov     edx, [rsp+1D8h+dwBufferLength]
0x180046a46  lea     rcx, [rsp+1D8h+lpBuffer]
0x180046a4b  call    sub_180026F30
0x180046a50  mov     rsi, [rsp+1D8h+lpBuffer]
0x180046a55  mov     [rsp+1D8h+lpdwIndex], r13; lpdwIndex
0x180046a5a  lea     rax, [rsp+1D8h+dwBufferLength]
0x180046a5f  mov     [rsp+1D8h+lpdwBufferLength], rax; lpdwBufferLength
0x180046a64  mov     r9, rsi; lpBuffer
0x180046a67  xor     r8d, r8d; pwszName
0x180046a6a  mov     edx, 16h; dwInfoLevel
0x180046a6f  mov     rcx, r15; hRequest
0x180046a72  call    cs:WinHttpQueryHeaders
0x180046a78  test    eax, eax
0x180046a7a  jnz     loc_180046B40
0x180046a80  call    cs:GetLastError
0x180046a86  mov     ebx, eax
0x180046a88  xorps   xmm0, xmm0
0x180046a8b  movups  xmmword ptr [rsp+1D8h+Block], xmm0
0x180046a93  mov     qword ptr [rsp+1D8h+var_E0], r13
0x180046a9b  mov     qword ptr [rsp+1D8h+var_E0+8], r13
0x180046aa3  mov     r8d, 13h
0x180046aa9  lea     rdx, aWinhttpqueryhe; "WinHttpQueryHeaders"
0x180046ab0  lea     rcx, [rsp+1D8h+Block]
0x180046ab8  call    sub_180057E0C
0x180046abd  nop
0x180046abe  lea     r8, [rsp+1D8h+Block]
0x180046ac6  mov     edx, ebx
0x180046ac8  lea     rcx, [rsp+1D8h+Src]; Src
0x180046ad0  call    sub_180046390
0x180046ad5  nop
0x180046ad6  mov     r8, rax
0x180046ad9  mov     edx, ebx
0x180046adb  mov     rcx, r14
0x180046ade  call    sub_18002DEE0
0x180046ae3  nop
0x180046ae4  lea     rcx, [rsp+1D8h+Src]
0x180046aec  call    sub_180059A94
0x180046af1  nop
0x180046af2  mov     rdx, qword ptr [rsp+1D8h+var_E0+8]
0x180046afa  cmp     rdx, 0Fh
0x180046afe  jbe     short loc_180046B3B
0x180046b00  mov     rax, [rsp+1D8h+Block]
0x180046b08  inc     rdx
0x180046b0b  cmp     rdx, 1000h
0x180046b12  jb      short loc_180046B32
0x180046b14  mov     rcx, [rax-8]
0x180046b18  sub     rax, rcx
0x180046b1b  sub     rax, 8
0x180046b1f  cmp     rax, 1Fh
0x180046b23  ja      short loc_180046B2B
0x180046b25  add     rdx, 27h ; '''
0x180046b29  jmp     short loc_180046B35
0x180046b2b  mov     ecx, 5
0x180046b30  int     29h; Win8: RtlFailFast(ecx)
0x180046b32  mov     rcx, rax; Block
0x180046b35  call    j_j_free_0
0x180046b3a  nop
0x180046b3b  jmp     loc_180046F3E
0x180046b40  lea     r8, [r14+28h]
0x180046b44  mov     rdx, rsi
0x180046b47  mov     rcx, r15; hRequest
0x180046b4a  call    sub_18004B360
0x180046b4f  mov     rax, [r14+28h]
0x180046b53  movzx   ecx, word ptr [rax+88h]
0x180046b5a  mov     eax, 191h
0x180046b5f  cmp     cx, ax
0x180046b62  jz      short loc_180046B6E
0x180046b64  mov     eax, 197h
0x180046b69  cmp     cx, ax
0x180046b6c  jnz     short loc_180046BE1
0x180046b6e  xor     r8d, r8d
0x180046b71  lea     rdx, [rsp+1D8h+var_168]
0x180046b76  mov     rcx, r15
0x180046b79  call    sub_1800488A0
0x180046b7e  test    al, al
0x180046b80  jz      short loc_180046BD7
0x180046b82  mov     rax, [rsp+1D8h+lpBuffer]
0x180046b87  test    rax, rax
0x180046b8a  jz      loc_18004759A
0x180046b90  mov     rdx, qword ptr [rsp+1D8h+var_178]
0x180046b95  sub     rdx, rax
0x180046b98  cmp     rdx, 1000h
0x180046b9f  jb      short loc_180046BBC
0x180046ba1  mov     rcx, [rax-8]
0x180046ba5  sub     rax, rcx
0x180046ba8  sub     rax, 8
0x180046bac  cmp     rax, 1Fh
0x180046bb0  ja      loc_180047937
0x180046bb6  add     rdx, 27h ; '''
0x180046bba  jmp     short loc_180046BBF
0x180046bbc  mov     rcx, rax; Block
0x180046bbf  call    j_j_free_0
0x180046bc4  xorps   xmm0, xmm0
0x180046bc7  movdqu  xmmword ptr [rsp+1D8h+lpBuffer], xmm0
0x180046bcd  mov     qword ptr [rsp+1D8h+var_178], r13
0x180046bd2  jmp     loc_18004759A
0x180046bd7  mov     rdi, qword ptr [rsp+1D8h+var_168+8]
0x180046bdc  mov     r14, qword ptr [rsp+1D8h+var_168]
0x180046be1  mov     rcx, r14
0x180046be4  call    sub_18002D6E0
0x180046be9  test    al, al
0x180046beb  jnz     short loc_180046BF2
0x180046bed  jmp     loc_180046F3E
0x180046bf2  cmp     qword ptr [r14+60h], 0
0x180046bf7  jz      short loc_180046C64
0x180046bf9  mov     rcx, [r14+8]
0x180046bfd  call    sub_18002CCC0
0x180046c02  cmp     byte ptr [rax+1A8h], 0
0x180046c09  jnz     short loc_180046C64
0x180046c0b  mov     ecx, 10h; Size
0x180046c10  call    sub_1800040CC
0x180046c15  mov     [rsp+1D8h+var_198], rax
0x180046c1a  test    rax, rax
0x180046c1d  jz      short loc_180046C2F
0x180046c1f  mov     [rax], r13
0x180046c22  mov     dword ptr [rax+8], 1
0x180046c29  mov     byte ptr [rax+0Ch], 0
0x180046c2d  jmp     short loc_180046C32
0x180046c2f  mov     rax, r13
0x180046c32  mov     [rsp+1D8h+var_198], rax
0x180046c37  lea     rcx, [r14+140h]
0x180046c3e  lea     rdx, [rsp+1D8h+var_198]
0x180046c43  call    sub_18003AAA0
0x180046c48  mov     rcx, [rsp+1D8h+var_198]; Block
0x180046c4d  test    rcx, rcx
0x180046c50  jz      short loc_180046C5C
0x180046c52  mov     edx, 10h
0x180046c57  call    j_j_free_0
0x180046c5c  mov     byte ptr [r14+133h], 1
0x180046c64  mov     rcx, r14
0x180046c67  call    sub_18002CCD0
0x180046c6c  mov     rcx, [r14+18h]
0x180046c70  add     rcx, 90h
0x180046c77  lea     rdx, qword_18011BE88
0x180046c7e  call    sub_180004970
0x180046c83  mov     rcx, r14
0x180046c86  test    al, al
0x180046c88  jz      short loc_180046CA4
0x180046c8a  xor     r8d, r8d
0x180046c8d  xor     edx, edx
0x180046c8f  call    sub_180046330
0x180046c94  xor     edx, edx
0x180046c96  mov     rcx, r14
0x180046c99  call    sub_18002CE10
0x180046c9e  nop
0x180046c9f  jmp     loc_180046F3E
0x180046ca4  mov     r8b, 1
0x180046ca7  xor     edx, edx
0x180046ca9  call    sub_18004B950
0x180046cae  nop
0x180046caf  jmp     loc_180046F3E
0x180046cb4  mov     edx, [r9]
0x180046cb7  lea     rcx, [rsp+1D8h+Src]; Src
0x180046cbf  call    sub_180048400
0x180046cc4  mov     rdx, rax
0x180046cc7  xorps   xmm0, xmm0
0x180046cca  movups  [rsp+1D8h+var_A0], xmm0
0x180046cd2  lea     rcx, ??_7http_exception@http@web@@6B@; const web::http::http_exception::`vftable'
0x180046cd9  mov     [rsp+1D8h+var_A8], rcx
0x180046ce1  mov     [rsp+1D8h+var_90], r13d
0x180046ce9  lea     rcx, off_180106020
0x180046cf0  mov     [rsp+1D8h+var_88], rcx
0x180046cf8  movups  xmmword ptr [rsp+1D8h+var_80], xmm0
0x180046d00  mov     qword ptr [rsp+1D8h+var_70], r13
0x180046d08  mov     qword ptr [rsp+1D8h+var_70+8], r13
0x180046d10  mov     rcx, [rax]
0x180046d13  mov     [rsp+1D8h+var_80], rcx
0x180046d1b  mov     rcx, [rax+8]
0x180046d1f  mov     [rsp+1D8h+var_80+8], rcx
0x180046d27  mov     rax, [rax+10h]
0x180046d2b  mov     qword ptr [rsp+1D8h+var_70], rax
0x180046d33  mov     rax, [rdx+18h]
0x180046d37  mov     qword ptr [rsp+1D8h+var_70+8], rax
0x180046d3f  mov     qword ptr [rdx+18h], 0Fh
0x180046d47  mov     byte ptr [rdx], 0
0x180046d4a  mov     [rdx+10h], r13
0x180046d4e  mov     qword ptr [rdx+18h], 0Fh
0x180046d56  mov     byte ptr [rdx], 0
0x180046d59  lea     rdx, [rsp+1D8h+var_A8]
0x180046d61  mov     rcx, r14
0x180046d64  call    sub_180029D50
0x180046d69  nop
0x180046d6a  mov     rdx, qword ptr [rsp+1D8h+var_70+8]
0x180046d72  cmp     rdx, 0Fh
0x180046d76  jbe     short loc_180046DAD
0x180046d78  inc     rdx
0x180046d7b  mov     rcx, [rsp+1D8h+var_80]
0x180046d83  cmp     rdx, 1000h
0x180046d8a  jb      short loc_180046DA8
0x180046d8c  mov     rax, [rcx-8]
0x180046d90  sub     rcx, rax
0x180046d93  sub     rcx, 8
0x180046d97  cmp     rcx, 1Fh
0x180046d9b  ja      loc_180047937
0x180046da1  add     rdx, 27h ; '''
0x180046da5  mov     rcx, rax; Block
0x180046da8  call    j_j_free_0
0x180046dad  mov     qword ptr [rsp+1D8h+var_70], r13
0x180046db5  mov     qword ptr [rsp+1D8h+var_70+8], 0Fh
0x180046dc1  mov     byte ptr [rsp+1D8h+var_80], 0
0x180046dc9  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180046dd0  mov     [rsp+1D8h+var_A8], rax
0x180046dd8  lea     rcx, [rsp+1D8h+var_A0]
0x180046de0  call    __std_exception_destroy
0x180046de5  nop
0x180046de6  test    rdi, rdi
0x180046de9  jz      loc_180047F7F
0x180046def  mov     esi, 0FFFFFFFFh
0x180046df4  jmp     loc_180047F4C
0x180046df9  mov     rax, [r14+80h]
  ... truncated ...
```
