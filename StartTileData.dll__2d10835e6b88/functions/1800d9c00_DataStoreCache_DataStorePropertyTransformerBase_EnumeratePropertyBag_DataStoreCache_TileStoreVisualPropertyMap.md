# DataStoreCache::DataStorePropertyTransformerBase::EnumeratePropertyBag<DataStoreCache::TileStoreVisualPropertyMapEntry,31,_lambda_30c3877965ffbeb76f72e09197e1202c_>(DataStoreCache::IDataStorePropertyBag *,DataStoreCache::TileStoreVisualPropertyMapEntry const (&)[31],_lambda_30c3877965ffbeb76f72e09197e1202c_ const &)

- ea: `0x1800d9c00`
- end: `0x1800da180`
- name: `??$EnumeratePropertyBag@UTileStoreVisualPropertyMapEntry@DataStoreCache@@$0BP@V_lambda_30c3877965ffbeb76f72e09197e1202c_@@@DataStorePropertyTransformerBase@DataStoreCache@@CA_KPEAUIDataStorePropertyBag@1@AEAY0BP@$$CBUTileStoreVisualPropertyMapEntry@1@AEBV_lambda_30c3877965ffbeb76f72e09197e1202c_@@@Z`
- size: `1408`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800d9b4c`

## callees

- `0x18001dac0`
- `0x1800d9c00`
- `0x1800da188`
- `0x1801593b0`
- `0x180201e50`
- `0x1802028aa`
- `0x18020295c`
- `0x18020c3d2`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800d9e4b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800d9e5e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800d9ebb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800d9f31`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800d9fa6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800da0a0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800da10b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800da14e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800d9e4b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800d9e5e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800d9ebb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800d9f31`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800d9fa6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800da0a0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800da10b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800da14e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9cac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9d1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9cac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9d1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d9cdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d9cdf`

## string_xrefs

- `0x1800d9da2`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`
- `0x1800d9e36`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`
- `0x1800d9e6e`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`
- `0x1800d9ee4`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`
- `0x1800d9f5a`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`
- `0x1800d9fcf`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`
- `0x1800da0c9`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`
- `0x1800da12e`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`
- `0x1800da16e`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DataStoreCache::DataStorePropertyTransformerBase::EnumeratePropertyBag<DataStoreCache::TileStoreVisualPropertyMapEntry,31,_lambda_30c3877965ffbeb76f72e09197e1202c_>(
        __int64 a1,
        __int64 a2,
        void ***a3)
{
  __int64 v5; // rbx
  unsigned __int64 i; // r13
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  __int64 (__fastcall *v14)(__int64, _QWORD, HSTRING *); // rbx
  char v15; // r12
  const char *v16; // r9
  PCWSTR StringRawBuffer; // r15
  UINT32 v18; // ebx
  _DWORD *v19; // rcx
  _BYTE *v21; // rcx
  HSTRING *v22; // rcx
  HSTRING *v23; // rcx
  _OWORD *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rdx
  HSTRING *v27; // rcx
  void **v28; // rcx
  _DWORD *v29; // rcx
  int v30; // [rsp+20h] [rbp-50h]
  _BYTE v31[4]; // [rsp+30h] [rbp-40h] BYREF
  UINT32 length; // [rsp+34h] [rbp-3Ch] BYREF
  __int64 v33; // [rsp+38h] [rbp-38h]
  HSTRING string[2]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v5 = 0;
  v33 = 0;
  for ( i = 0; i < 0x1F; ++i )
  {
    v7 = *((_DWORD *)&DataStoreCache::c_TileStoreVisualPropertyMap + 4 * i + 3);
    if ( !v7 )
    {
      string[0] = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)a1 + 32LL))(
              a1,
              *((_QWORD *)&DataStoreCache::c_TileStoreVisualPropertyMap + 2 * i),
              string);
      if ( v15 )
      {
        v25 = -1;
        do
          ++v25;
        while ( *((_WORD *)string[0] + v25) );
        v26 = (unsigned int)(2 * v25 + 2);
      }
      else
      {
        v26 = 0;
      }
      LOBYTE(v30) = v15;
      _lambda_30c3877965ffbeb76f72e09197e1202c_::operator()(a3, v26, string[0], (unsigned int)v26);
      goto LABEL_14;
    }
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( v12 )
            {
              v13 = v12 - 1;
              if ( !v13 )
              {
                string[0] = 0;
                v14 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)a1 + 32LL);
                WindowsDeleteString(0);
                string[0] = 0;
                v15 = v14(a1, *((_QWORD *)&DataStoreCache::c_TileStoreVisualPropertyMap + 2 * i), string);
                length = 0;
                StringRawBuffer = WindowsGetStringRawBuffer(string[0], &length);
                if ( v15 )
                {
                  v18 = 2 * length;
                  if ( 2 * length )
                  {
                    v29 = **a3;
                    if ( v29 )
                    {
                      *v29 = v18;
                    }
                    else
                    {
                      *(_DWORD *)_o__errno(0) = 22;
                      invalid_parameter_noinfo();
                    }
                    **a3 = (char *)**a3 + 4;
                    v28 = (void **)**a3;
                    if ( v28 > a3[1] )
                      wil::details::in1diag3::_FailFast_Unexpected(
                        retaddr,
                        (void *)0x1D6,
                        (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
                        v16);
                    if ( v28 )
                    {
                      if ( StringRawBuffer )
                      {
                        memcpy_0(v28, StringRawBuffer, v18);
                        goto LABEL_12;
                      }
                      memset_0(v28, 0, v18);
                    }
                    *(_DWORD *)_o__errno(v28) = 22;
                    invalid_parameter_noinfo();
                  }
LABEL_12:
                  **a3 = (char *)**a3 + v18;
                  if ( **a3 > a3[1] )
                    wil::details::in1diag3::_FailFast_Unexpected(
                      retaddr,
                      (void *)0x1DB,
                      (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
                      (const char *)retaddr);
                }
                WindowsDeleteString(string[0]);
                v5 = v33;
LABEL_14:
                if ( !v15 )
                  continue;
                goto LABEL_15;
              }
              if ( v13 != 1 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x239,
                  (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
                  (const char *)0x8000FFFFLL,
                  v30);
              string[0] = 0;
              if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, __int64, HSTRING *))(*(_QWORD *)a1 + 24LL))(
                     a1,
                     *((_QWORD *)&DataStoreCache::c_TileStoreVisualPropertyMap + 2 * i),
                     8,
                     string) )
              {
                v27 = (HSTRING *)**a3;
                if ( v27 )
                {
                  *v27 = string[0];
                }
                else
                {
                  *(_DWORD *)_o__errno(0) = 22;
                  invalid_parameter_noinfo();
                }
                **a3 = (char *)**a3 + 8;
                if ( **a3 > a3[1] )
                  wil::details::in1diag3::_FailFast_Unexpected(
                    retaddr,
                    (void *)0x1DB,
                    (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
                    (const char *)retaddr);
LABEL_15:
                v5 |= 1LL << *(_DWORD *)(*((_QWORD *)&DataStoreCache::c_TileStoreVisualPropertyMap + 2 * i) + 8LL);
                v33 = v5;
                continue;
              }
            }
            else
            {
              *(_OWORD *)string = 0;
              if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, __int64, HSTRING *))(*(_QWORD *)a1 + 24LL))(
                     a1,
                     *((_QWORD *)&DataStoreCache::c_TileStoreVisualPropertyMap + 2 * i),
                     16,
                     string) )
              {
                v24 = **a3;
                if ( v24 )
                {
                  *v24 = *(_OWORD *)string;
                }
                else
                {
                  *(_DWORD *)_o__errno(0) = 22;
                  invalid_parameter_noinfo();
                }
                **a3 = (char *)**a3 + 16;
                if ( **a3 > a3[1] )
                  wil::details::in1diag3::_FailFast_Unexpected(
                    retaddr,
                    (void *)0x1DB,
                    (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
                    (const char *)retaddr);
                goto LABEL_15;
              }
            }
          }
          else
          {
            string[0] = 0;
            if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, __int64, HSTRING *))(*(_QWORD *)a1 + 24LL))(
                   a1,
                   *((_QWORD *)&DataStoreCache::c_TileStoreVisualPropertyMap + 2 * i),
                   8,
                   string) )
            {
              v23 = (HSTRING *)**a3;
              if ( v23 )
              {
                *v23 = string[0];
              }
              else
              {
                *(_DWORD *)_o__errno(0) = 22;
                invalid_parameter_noinfo();
              }
              **a3 = (char *)**a3 + 8;
              if ( **a3 > a3[1] )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x1DB,
                  (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
                  (const char *)retaddr);
              goto LABEL_15;
            }
          }
        }
        else
        {
          string[0] = 0;
          if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, __int64, HSTRING *))(*(_QWORD *)a1 + 24LL))(
                 a1,
                 *((_QWORD *)&DataStoreCache::c_TileStoreVisualPropertyMap + 2 * i),
                 8,
                 string) )
          {
            v22 = (HSTRING *)**a3;
            if ( v22 )
            {
              *v22 = string[0];
            }
            else
            {
              *(_DWORD *)_o__errno(0) = 22;
              invalid_parameter_noinfo();
            }
            **a3 = (char *)**a3 + 8;
            if ( **a3 > a3[1] )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x1DB,
                (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
                (const char *)retaddr);
            goto LABEL_15;
          }
        }
      }
      else
      {
        LODWORD(string[0]) = 0;
        if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, __int64, HSTRING *))(*(_QWORD *)a1 + 24LL))(
               a1,
               *((_QWORD *)&DataStoreCache::c_TileStoreVisualPropertyMap + 2 * i),
               4,
               string) )
        {
          v19 = **a3;
          if ( v19 )
          {
            *v19 = string[0];
          }
          else
          {
            *(_DWORD *)_o__errno(0) = 22;
            invalid_parameter_noinfo();
          }
          **a3 = (char *)**a3 + 4;
          if ( **a3 > a3[1] )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x1DB,
              (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
              (const char *)retaddr);
          goto LABEL_15;
        }
      }
    }
    else
    {
      v31[0] = 0;
      if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)a1 + 24LL))(
             a1,
             *((_QWORD *)&DataStoreCache::c_TileStoreVisualPropertyMap + 2 * i),
             1,
             v31) )
      {
        v21 = **a3;
        if ( v21 )
        {
          *v21 = v31[0];
        }
        else
        {
          *(_DWORD *)_o__errno(0) = 22;
          invalid_parameter_noinfo();
        }
        **a3 = (char *)**a3 + 1;
        if ( **a3 > a3[1] )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x1DB,
            (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
            (const char *)retaddr);
        goto LABEL_15;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800d9c00  mov     [rsp-38h+arg_8], rbx
0x1800d9c05  push    rbp
0x1800d9c06  push    rsi
0x1800d9c07  push    rdi
0x1800d9c08  push    r12
0x1800d9c0a  push    r13
0x1800d9c0c  push    r14
0x1800d9c0e  push    r15
0x1800d9c10  mov     rbp, rsp
0x1800d9c13  sub     rsp, 70h
0x1800d9c17  movaps  [rsp+70h+var_10], xmm6
0x1800d9c1c  mov     rax, cs:__security_cookie
0x1800d9c23  xor     rax, rsp
0x1800d9c26  mov     [rbp+var_20], rax
0x1800d9c2a  mov     rdi, r8
0x1800d9c2d  mov     r14, rcx
0x1800d9c30  xor     r15d, r15d
0x1800d9c33  mov     ebx, r15d
0x1800d9c36  mov     [rbp+var_38], rbx
0x1800d9c3a  mov     r13d, r15d
0x1800d9c3d  xorps   xmm6, xmm6
0x1800d9c40  mov     r12d, 16h
0x1800d9c46  cmp     r13, 1Fh
0x1800d9c4a  jnb     loc_1800D9DB7
0x1800d9c50  mov     rsi, r13
0x1800d9c53  add     rsi, rsi
0x1800d9c56  lea     rdx, ?c_TileStoreVisualPropertyMap@DataStoreCache@@3QBUTileStoreVisualPropertyMapEntry@1@B; DataStoreCache::TileStoreVisualPropertyMapEntry const near * const DataStoreCache::c_TileStoreVisualPropertyMap
0x1800d9c5d  mov     ecx, [rdx+rsi*8+0Ch]
0x1800d9c61  test    ecx, ecx
0x1800d9c63  jz      loc_1800DA006
0x1800d9c69  sub     ecx, 1
0x1800d9c6c  jz      loc_1800D9DE3
0x1800d9c72  sub     ecx, 1
0x1800d9c75  jz      loc_1800D9D52
0x1800d9c7b  sub     ecx, 1
0x1800d9c7e  jz      loc_1800D9E83
0x1800d9c84  sub     ecx, 1
0x1800d9c87  jz      loc_1800D9EF9
0x1800d9c8d  sub     ecx, 1
0x1800d9c90  jz      loc_1800D9F6F
0x1800d9c96  sub     ecx, 1
0x1800d9c99  jnz     loc_1800DA056
0x1800d9c9f  mov     [rbp+string], r15
0x1800d9ca3  mov     rax, [r14]
0x1800d9ca6  mov     rbx, [rax+20h]
0x1800d9caa  xor     ecx, ecx; string
0x1800d9cac  call    cs:__imp_WindowsDeleteString
0x1800d9cb2  mov     [rbp+string], r15
0x1800d9cb6  lea     r8, [rbp+string]
0x1800d9cba  lea     rdx, ?c_TileStoreVisualPropertyMap@DataStoreCache@@3QBUTileStoreVisualPropertyMapEntry@1@B; DataStoreCache::TileStoreVisualPropertyMapEntry const near * const DataStoreCache::c_TileStoreVisualPropertyMap
0x1800d9cc1  mov     rdx, [rdx+rsi*8]
0x1800d9cc5  mov     rcx, r14
0x1800d9cc8  mov     rax, rbx
0x1800d9ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9cd0  mov     r12b, al
0x1800d9cd3  mov     [rbp+length], r15d
0x1800d9cd7  lea     rdx, [rbp+length]; length
0x1800d9cdb  mov     rcx, [rbp+string]; string
0x1800d9cdf  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d9ce5  mov     r15, rax
0x1800d9ce8  test    r12b, r12b
0x1800d9ceb  jz      short loc_1800D9D17
0x1800d9ced  mov     eax, [rbp+length]
0x1800d9cf0  lea     ebx, [rax+rax]
0x1800d9cf3  test    ebx, ebx
0x1800d9cf5  jnz     loc_1800DA143
0x1800d9cfb  mov     rcx, [rdi]
0x1800d9cfe  mov     eax, ebx
0x1800d9d00  add     [rcx], rax
0x1800d9d03  mov     r9, [rbp+38h]; char *
0x1800d9d07  mov     rcx, [rdi]
0x1800d9d0a  mov     rax, [rdi+8]
0x1800d9d0e  cmp     [rcx], rax
0x1800d9d11  ja      loc_1800D9E6E
0x1800d9d17  mov     rcx, [rbp+string]; string
0x1800d9d1b  call    cs:__imp_WindowsDeleteString
0x1800d9d21  mov     rbx, [rbp+var_38]
0x1800d9d25  xor     r15d, r15d
0x1800d9d28  test    r12b, r12b
0x1800d9d2b  jz      short loc_1800D9D4A
0x1800d9d2d  lea     rax, ?c_TileStoreVisualPropertyMap@DataStoreCache@@3QBUTileStoreVisualPropertyMapEntry@1@B; DataStoreCache::TileStoreVisualPropertyMapEntry const near * const DataStoreCache::c_TileStoreVisualPropertyMap
0x1800d9d34  mov     rcx, [rax+rsi*8]
0x1800d9d38  mov     ecx, [rcx+8]
0x1800d9d3b  mov     eax, 1
0x1800d9d40  shl     rax, cl
0x1800d9d43  or      rbx, rax
0x1800d9d46  mov     [rbp+var_38], rbx
0x1800d9d4a  inc     r13
0x1800d9d4d  jmp     loc_1800D9C40
0x1800d9d52  mov     dword ptr [rbp+string], r15d
0x1800d9d56  mov     rax, [r14]
0x1800d9d59  lea     r9, [rbp+string]
0x1800d9d5d  mov     r8d, 4
0x1800d9d63  mov     rdx, [rdx+rsi*8]
0x1800d9d67  mov     rcx, r14
0x1800d9d6a  mov     rax, [rax+18h]
0x1800d9d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9d73  test    al, al
0x1800d9d75  jz      short loc_1800D9D4A
0x1800d9d77  mov     rax, [rdi]
0x1800d9d7a  mov     rcx, [rax]
0x1800d9d7d  test    rcx, rcx
0x1800d9d80  jz      loc_1800D9E4B
0x1800d9d86  mov     eax, dword ptr [rbp+string]
0x1800d9d89  mov     [rcx], eax
0x1800d9d8b  mov     rax, [rdi]
0x1800d9d8e  add     qword ptr [rax], 4
0x1800d9d92  mov     r9, [rbp+38h]; char *
0x1800d9d96  mov     rcx, [rdi]
0x1800d9d99  mov     rax, [rdi+8]
0x1800d9d9d  cmp     [rcx], rax
0x1800d9da0  jbe     short loc_1800D9D2D
0x1800d9da2  lea     r8, aShellcommonShe_96; "shellcommon\\shell\\DataStoreCache\\Tra"...
0x1800d9da9  mov     edx, 1DBh; void *
0x1800d9dae  mov     rcx, r9; this
0x1800d9db1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800d9db7  mov     rax, rbx
0x1800d9dba  mov     rcx, [rbp+var_20]
0x1800d9dbe  xor     rcx, rsp; StackCookie
0x1800d9dc1  call    __security_check_cookie
0x1800d9dc6  mov     rbx, [rsp+70h+arg_8]
0x1800d9dce  movaps  xmm6, [rsp+70h+var_10]
0x1800d9dd3  add     rsp, 70h
0x1800d9dd7  pop     r15
0x1800d9dd9  pop     r14
0x1800d9ddb  pop     r13
0x1800d9ddd  pop     r12
0x1800d9ddf  pop     rdi
0x1800d9de0  pop     rsi
0x1800d9de1  pop     rbp
0x1800d9de2  retn
0x1800d9de3  mov     [rbp+var_40], r15b
0x1800d9de7  mov     rax, [r14]
0x1800d9dea  lea     r9, [rbp+var_40]
0x1800d9dee  mov     r8d, 1
0x1800d9df4  mov     rdx, [rdx+rsi*8]
0x1800d9df8  mov     rcx, r14
0x1800d9dfb  mov     rax, [rax+18h]
0x1800d9dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9e04  test    al, al
0x1800d9e06  jz      loc_1800D9D4A
0x1800d9e0c  mov     rax, [rdi]
0x1800d9e0f  mov     rcx, [rax]
0x1800d9e12  test    rcx, rcx
0x1800d9e15  jz      short loc_1800D9E5E
0x1800d9e17  mov     al, [rbp+var_40]
0x1800d9e1a  mov     [rcx], al
0x1800d9e1c  mov     rax, [rdi]
0x1800d9e1f  inc     qword ptr [rax]
0x1800d9e22  mov     r9, [rbp+38h]; char *
0x1800d9e26  mov     rcx, [rdi]
0x1800d9e29  mov     rax, [rdi+8]
0x1800d9e2d  cmp     [rcx], rax
0x1800d9e30  jbe     loc_1800D9D2D
0x1800d9e36  lea     r8, aShellcommonShe_96; "shellcommon\\shell\\DataStoreCache\\Tra"...
0x1800d9e3d  mov     edx, 1DBh; void *
0x1800d9e42  mov     rcx, r9; this
0x1800d9e45  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800d9e4b  call    cs:__imp__o__errno
0x1800d9e51  mov     [rax], r12d
0x1800d9e54  call    _invalid_parameter_noinfo
0x1800d9e59  jmp     loc_1800D9D8B
0x1800d9e5e  call    cs:__imp__o__errno
0x1800d9e64  mov     [rax], r12d
0x1800d9e67  call    _invalid_parameter_noinfo
0x1800d9e6c  jmp     short loc_1800D9E1C
0x1800d9e6e  lea     r8, aShellcommonShe_96; "shellcommon\\shell\\DataStoreCache\\Tra"...
0x1800d9e75  mov     edx, 1DBh; void *
0x1800d9e7a  mov     rcx, r9; this
0x1800d9e7d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800d9e83  mov     [rbp+string], r15
0x1800d9e87  mov     rax, [r14]
0x1800d9e8a  lea     r9, [rbp+string]
0x1800d9e8e  mov     r8d, 8
0x1800d9e94  mov     rdx, [rdx+rsi*8]
0x1800d9e98  mov     rcx, r14
0x1800d9e9b  mov     rax, [rax+18h]
0x1800d9e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9ea4  test    al, al
0x1800d9ea6  jz      loc_1800D9D4A
0x1800d9eac  mov     rax, [rdi]
0x1800d9eaf  mov     rcx, [rax]
0x1800d9eb2  test    rcx, rcx
0x1800d9eb5  jnz     loc_1800D9FE4
0x1800d9ebb  call    cs:__imp__o__errno
0x1800d9ec1  mov     [rax], r12d
0x1800d9ec4  call    _invalid_parameter_noinfo
0x1800d9ec9  mov     rax, [rdi]
0x1800d9ecc  add     qword ptr [rax], 8
0x1800d9ed0  mov     r9, [rbp+38h]; char *
0x1800d9ed4  mov     rcx, [rdi]
0x1800d9ed7  mov     rax, [rdi+8]
0x1800d9edb  cmp     [rcx], rax
0x1800d9ede  jbe     loc_1800D9D2D
0x1800d9ee4  lea     r8, aShellcommonShe_96; "shellcommon\\shell\\DataStoreCache\\Tra"...
0x1800d9eeb  mov     edx, 1DBh; void *
0x1800d9ef0  mov     rcx, r9; this
0x1800d9ef3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800d9ef9  mov     [rbp+string], r15
0x1800d9efd  mov     rax, [r14]
0x1800d9f00  lea     r9, [rbp+string]
0x1800d9f04  mov     r8d, 8
0x1800d9f0a  mov     rdx, [rdx+rsi*8]
0x1800d9f0e  mov     rcx, r14
0x1800d9f11  mov     rax, [rax+18h]
0x1800d9f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9f1a  test    al, al
0x1800d9f1c  jz      loc_1800D9D4A
0x1800d9f22  mov     rax, [rdi]
0x1800d9f25  mov     rcx, [rax]
0x1800d9f28  test    rcx, rcx
0x1800d9f2b  jnz     loc_1800D9FF0
0x1800d9f31  call    cs:__imp__o__errno
0x1800d9f37  mov     [rax], r12d
0x1800d9f3a  call    _invalid_parameter_noinfo
0x1800d9f3f  mov     rax, [rdi]
0x1800d9f42  add     qword ptr [rax], 8
0x1800d9f46  mov     r9, [rbp+38h]; char *
0x1800d9f4a  mov     rcx, [rdi]
0x1800d9f4d  mov     rax, [rdi+8]
0x1800d9f51  cmp     [rcx], rax
0x1800d9f54  jbe     loc_1800D9D2D
0x1800d9f5a  lea     r8, aShellcommonShe_96; "shellcommon\\shell\\DataStoreCache\\Tra"...
0x1800d9f61  mov     edx, 1DBh; void *
0x1800d9f66  mov     rcx, r9; this
0x1800d9f69  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800d9f6f  xorps   xmm0, xmm0
0x1800d9f72  movups  xmmword ptr [rbp+string], xmm0
0x1800d9f76  mov     rax, [r14]
0x1800d9f79  lea     r9, [rbp+string]
0x1800d9f7d  mov     r8d, 10h
0x1800d9f83  mov     rdx, [rdx+rsi*8]
0x1800d9f87  mov     rcx, r14
0x1800d9f8a  mov     rax, [rax+18h]
0x1800d9f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9f93  test    al, al
0x1800d9f95  jz      loc_1800D9D4A
0x1800d9f9b  mov     rax, [rdi]
0x1800d9f9e  mov     rcx, [rax]
0x1800d9fa1  test    rcx, rcx
0x1800d9fa4  jnz     short loc_1800D9FFC
0x1800d9fa6  call    cs:__imp__o__errno
0x1800d9fac  mov     [rax], r12d
0x1800d9faf  call    _invalid_parameter_noinfo
0x1800d9fb4  mov     rax, [rdi]
0x1800d9fb7  add     qword ptr [rax], 10h
0x1800d9fbb  mov     r9, [rbp+38h]; char *
0x1800d9fbf  mov     rcx, [rdi]
0x1800d9fc2  mov     rax, [rdi+8]
0x1800d9fc6  cmp     [rcx], rax
0x1800d9fc9  jbe     loc_1800D9D2D
0x1800d9fcf  lea     r8, aShellcommonShe_96; "shellcommon\\shell\\DataStoreCache\\Tra"...
0x1800d9fd6  mov     edx, 1DBh; void *
0x1800d9fdb  mov     rcx, r9; this
0x1800d9fde  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800d9fe4  mov     rax, [rbp+string]
0x1800d9fe8  mov     [rcx], rax
0x1800d9feb  jmp     loc_1800D9EC9
0x1800d9ff0  mov     rax, [rbp+string]
0x1800d9ff4  mov     [rcx], rax
0x1800d9ff7  jmp     loc_1800D9F3F
0x1800d9ffc  movups  xmm0, xmmword ptr [rbp+string]
0x1800da000  movdqu  xmmword ptr [rcx], xmm0
0x1800da004  jmp     short loc_1800D9FB4
0x1800da006  mov     [rbp+string], r15
0x1800da00a  mov     rax, [r14]
0x1800da00d  lea     r8, [rbp+string]
0x1800da011  mov     rdx, [rdx+rsi*8]
0x1800da015  mov     rcx, r14
0x1800da018  mov     rax, [rax+20h]
0x1800da01c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da021  mov     r12b, al
0x1800da024  mov     r8, [rbp+string]
0x1800da028  test    al, al
0x1800da02a  jz      short loc_1800DA09B
0x1800da02c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800da030  inc     rax
0x1800da033  cmp     [r8+rax*2], r15w
0x1800da038  jnz     short loc_1800DA030
0x1800da03a  lea     edx, ds:2[rax*2]
0x1800da041  mov     r9d, edx
0x1800da044  mov     byte ptr [rsp+70h+var_50], r12b
0x1800da049  mov     rcx, rdi
0x1800da04c  call    ??R_lambda_30c3877965ffbeb76f72e09197e1202c_@@QEBA@IQEAX_K_N@Z; _lambda_30c3877965ffbeb76f72e09197e1202c_::operator()(uint,void * const,unsigned __int64,bool)
0x1800da051  jmp     loc_1800D9D28
0x1800da056  cmp     ecx, 1
0x1800da059  jnz     loc_1800DA164
0x1800da05f  movsd   [rbp+string], xmm6
0x1800da064  mov     rax, [r14]
0x1800da067  lea     r9, [rbp+string]
0x1800da06b  lea     r8d, [rcx+7]
0x1800da06f  mov     rdx, [rdx+rsi*8]
0x1800da073  mov     rcx, r14
0x1800da076  mov     rax, [rax+18h]
0x1800da07a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da07f  test    al, al
0x1800da081  jz      loc_1800D9D4A
0x1800da087  mov     rax, [rdi]
0x1800da08a  mov     rcx, [rax]
0x1800da08d  test    rcx, rcx
  ... truncated ...
```
