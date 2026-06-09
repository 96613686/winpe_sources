# HmacHashDataEx(_CAPI_FUNCTION_TABLE *,unsigned __int64,uchar *,ulong,uchar *,ulong,unsigned __int64,unsigned __int64 *)

- ea: `0x1800c4afc`
- end: `0x1800c4e09`
- name: `?HmacHashDataEx@@YAHPEAU_CAPI_FUNCTION_TABLE@@_KPEAEK2K1PEA_K@Z`
- size: `781`
- prototype: `__int64 __fastcall(struct _CAPI_FUNCTION_TABLE *, unsigned __int64, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int64, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800c5254`
- `0x1800c5670`

## callees

- `0x180004970`
- `0x180078c20`
- `0x1800c4afc`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4b83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4cd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4d6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4b83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4cd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4d6f`

## string_xrefs

- `0x1800c4ba5`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x1800c4c52`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x1800c4cf3`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x1800c4d91`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x1800c4bb0`: `Error %x during CryptCreateHash!`
- `0x1800c4cfe`: `Error %x during CryptHashData!`
- `0x1800c4d9c`: `Error %x during CryptHashData!`
- `0x1800c4c5d`: `Error %x during CryptSetHashParam!`

## pseudocode

```c
__int64 __fastcall HmacHashDataEx(
        struct _CAPI_FUNCTION_TABLE *a1,
        __int64 a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned __int64 a7,
        unsigned __int64 *a8)
{
  unsigned int (__fastcall *v10)(__int64, __int64, unsigned __int64, _QWORD, unsigned __int64 *); // rax
  unsigned int v12; // esi
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  DWORD v26; // [rsp+50h] [rbp-59h] BYREF
  int v27; // [rsp+54h] [rbp-55h] BYREF
  DWORD LastError; // [rsp+58h] [rbp-51h] BYREF
  const char *v29; // [rsp+60h] [rbp-49h] BYREF
  const char *v30; // [rsp+68h] [rbp-41h] BYREF
  const char *v31; // [rsp+70h] [rbp-39h] BYREF
  _OWORD v32[2]; // [rsp+78h] [rbp-31h] BYREF
  __int64 v33; // [rsp+98h] [rbp-11h]

  v33 = 0;
  v10 = (unsigned int (__fastcall *)(__int64, __int64, unsigned __int64, _QWORD, unsigned __int64 *))*((_QWORD *)a1 + 8);
  memset(v32, 0, sizeof(v32));
  LODWORD(v32[0]) = 32772;
  v12 = 0;
  if ( v10(a2, 32777, a7, 0, a8) )
  {
    if ( (*((unsigned int (__fastcall **)(_QWORD, __int64, _OWORD *))a1 + 10))(*a8, 5, v32) )
    {
      if ( (*((unsigned int (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, _QWORD))a1 + 9))(*a8, a3, a4, 0) )
      {
        if ( (*((unsigned int (__fastcall **)(_QWORD, unsigned __int8 *, __int64))a1 + 9))(*a8, a5, 4) )
        {
          return 1;
        }
        else if ( (unsigned int)CallbackContext > 2 )
        {
          v27 = 380;
          LastError = GetLastError();
          v31 = "HmacHashDataEx";
          v30 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\security\\tssecurity.cpp";
          v29 = "Error %x during CryptHashData!";
          v26 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v22,
            (unsigned int)byte_1801B89C9,
            v23,
            v24,
            (__int64)&v29,
            (__int64)&v26,
            (__int64)&v30,
            (__int64)&v27,
            (__int64)&v31,
            (__int64)&LastError);
        }
      }
      else if ( (unsigned int)CallbackContext > 2 )
      {
        v27 = 375;
        LastError = GetLastError();
        v31 = "HmacHashDataEx";
        v30 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\security\\tssecurity.cpp";
        v29 = "Error %x during CryptHashData!";
        v26 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v19,
          (unsigned int)&word_1801B8A1E,
          v20,
          v21,
          (__int64)&v29,
          (__int64)&v26,
          (__int64)&v30,
          (__int64)&v27,
          (__int64)&v31,
          (__int64)&LastError);
      }
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      v27 = 367;
      LastError = GetLastError();
      v31 = "HmacHashDataEx";
      v30 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\security\\tssecurity.cpp";
      v29 = "Error %x during CryptSetHashParam!";
      v26 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v16,
        (unsigned int)byte_1801B8A73,
        v17,
        v18,
        (__int64)&v29,
        (__int64)&v26,
        (__int64)&v30,
        (__int64)&v27,
        (__int64)&v31,
        (__int64)&LastError);
    }
  }
  else if ( (unsigned int)CallbackContext > 2 )
  {
    v27 = 362;
    v26 = GetLastError();
    v29 = "HmacHashDataEx";
    v30 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\security\\tssecurity.cpp";
    v31 = "Error %x during CryptCreateHash!";
    LastError = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v13,
      (unsigned int)qword_1801B8AC8,
      v14,
      v15,
      (__int64)&v31,
      (__int64)&LastError,
      (__int64)&v30,
      (__int64)&v27,
      (__int64)&v29,
      (__int64)&v26);
  }
  return v12;
}

```

## disassembly

```asm
0x1800c4afc  push    rbp
0x1800c4afe  push    rbx
0x1800c4aff  push    rsi
0x1800c4b00  push    rdi
0x1800c4b01  push    r12
0x1800c4b03  push    r14
0x1800c4b05  push    r15
0x1800c4b07  lea     rbp, [rsp-7]
0x1800c4b0c  sub     rsp, 0B0h
0x1800c4b13  mov     rax, cs:__security_cookie
0x1800c4b1a  xor     rax, rsp
0x1800c4b1d  mov     [rbp+37h+var_40], rax
0x1800c4b21  mov     rdi, [rbp+37h+arg_38]
0x1800c4b25  mov     rbx, rcx
0x1800c4b28  mov     r14, [rbp+37h+arg_20]
0x1800c4b2c  mov     rax, rdx
0x1800c4b2f  xor     ecx, ecx
0x1800c4b31  mov     [rsp+0E0h+var_C0], rdi
0x1800c4b36  xorps   xmm0, xmm0
0x1800c4b39  mov     [rbp+37h+var_48], rcx
0x1800c4b3d  mov     rcx, rax
0x1800c4b40  mov     r12d, r9d
0x1800c4b43  mov     rax, [rbx+40h]
0x1800c4b47  mov     r15, r8
0x1800c4b4a  mov     r8, [rbp+37h+arg_30]
0x1800c4b4e  xor     r9d, r9d
0x1800c4b51  movups  [rbp+37h+var_68], xmm0
0x1800c4b55  mov     edx, 8009h
0x1800c4b5a  mov     dword ptr [rbp+37h+var_68], 8004h
0x1800c4b61  xor     esi, esi
0x1800c4b63  movups  [rbp+37h+var_58], xmm0
0x1800c4b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4b6c  test    eax, eax
0x1800c4b6e  jnz     loc_1800C4C02
0x1800c4b74  mov     eax, cs:CallbackContext
0x1800c4b7a  cmp     eax, 2
0x1800c4b7d  jbe     loc_1800C4DE9
0x1800c4b83  call    cs:__imp_GetLastError
0x1800c4b89  mov     [rbp+37h+var_8C], 16Ah
0x1800c4b90  lea     rdx, qword_1801B8AC8
0x1800c4b97  mov     [rbp+37h+var_90], eax
0x1800c4b9a  lea     rax, aHmachashdataex_0; "HmacHashDataEx"
0x1800c4ba1  mov     [rbp+37h+var_80], rax
0x1800c4ba5  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800c4bac  mov     [rbp+37h+var_78], rax
0x1800c4bb0  lea     rax, Format; "Error %x during CryptCreateHash!"
0x1800c4bb7  mov     [rbp+37h+var_70], rax
0x1800c4bbb  lea     rax, [rbp+37h+var_90]
0x1800c4bbf  mov     [rsp+0E0h+var_98], rax
0x1800c4bc4  lea     rax, [rbp+37h+var_80]
0x1800c4bc8  mov     [rsp+0E0h+var_A0], rax
0x1800c4bcd  lea     rax, [rbp+37h+var_8C]
0x1800c4bd1  mov     [rsp+0E0h+var_A8], rax
0x1800c4bd6  lea     rax, [rbp+37h+var_78]
0x1800c4bda  mov     [rsp+0E0h+var_B0], rax
0x1800c4bdf  lea     rax, [rbp+37h+var_88]
0x1800c4be3  mov     [rsp+0E0h+var_B8], rax
0x1800c4be8  lea     rax, [rbp+37h+var_70]
0x1800c4bec  mov     [rbp+37h+var_88], 80004005h
0x1800c4bf3  mov     [rsp+0E0h+var_C0], rax
0x1800c4bf8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800c4bfd  jmp     loc_1800C4DE9
0x1800c4c02  mov     rcx, [rdi]
0x1800c4c05  lea     r8, [rbp+37h+var_68]
0x1800c4c09  mov     rax, [rbx+50h]
0x1800c4c0d  xor     r9d, r9d
0x1800c4c10  lea     edx, [r9+5]
0x1800c4c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4c19  test    eax, eax
0x1800c4c1b  jnz     loc_1800C4CA5
0x1800c4c21  mov     eax, cs:CallbackContext
0x1800c4c27  cmp     eax, 2
0x1800c4c2a  jbe     loc_1800C4DE9
0x1800c4c30  call    cs:__imp_GetLastError
0x1800c4c36  mov     [rbp+37h+var_8C], 16Fh
0x1800c4c3d  lea     rdx, byte_1801B8A73
0x1800c4c44  mov     [rbp+37h+var_88], eax
0x1800c4c47  lea     rax, aHmachashdataex_0; "HmacHashDataEx"
0x1800c4c4e  mov     [rbp+37h+var_70], rax
0x1800c4c52  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800c4c59  mov     [rbp+37h+var_78], rax
0x1800c4c5d  lea     rax, aErrorXDuringCr_5; "Error %x during CryptSetHashParam!"
0x1800c4c64  mov     [rbp+37h+var_80], rax
0x1800c4c68  lea     rax, [rbp+37h+var_88]
0x1800c4c6c  mov     [rsp+0E0h+var_98], rax
0x1800c4c71  lea     rax, [rbp+37h+var_70]
0x1800c4c75  mov     [rsp+0E0h+var_A0], rax
0x1800c4c7a  lea     rax, [rbp+37h+var_8C]
0x1800c4c7e  mov     [rsp+0E0h+var_A8], rax
0x1800c4c83  lea     rax, [rbp+37h+var_78]
0x1800c4c87  mov     [rsp+0E0h+var_B0], rax
0x1800c4c8c  lea     rax, [rbp+37h+var_90]
0x1800c4c90  mov     [rsp+0E0h+var_B8], rax
0x1800c4c95  lea     rax, [rbp+37h+var_80]
0x1800c4c99  mov     [rbp+37h+var_90], 80004005h
0x1800c4ca0  jmp     loc_1800C4BF3
0x1800c4ca5  mov     rcx, [rdi]
0x1800c4ca8  xor     r9d, r9d
0x1800c4cab  mov     rax, [rbx+48h]
0x1800c4caf  mov     r8d, r12d
0x1800c4cb2  mov     rdx, r15
0x1800c4cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4cba  test    eax, eax
0x1800c4cbc  jnz     loc_1800C4D46
0x1800c4cc2  mov     eax, cs:CallbackContext
0x1800c4cc8  cmp     eax, 2
0x1800c4ccb  jbe     loc_1800C4DE9
0x1800c4cd1  call    cs:__imp_GetLastError
0x1800c4cd7  mov     [rbp+37h+var_8C], 177h
0x1800c4cde  lea     rdx, word_1801B8A1E
0x1800c4ce5  mov     [rbp+37h+var_88], eax
0x1800c4ce8  lea     rax, aHmachashdataex_0; "HmacHashDataEx"
0x1800c4cef  mov     [rbp+37h+var_70], rax
0x1800c4cf3  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800c4cfa  mov     [rbp+37h+var_78], rax
0x1800c4cfe  lea     rax, aErrorXDuringCr; "Error %x during CryptHashData!"
0x1800c4d05  mov     [rbp+37h+var_80], rax
0x1800c4d09  lea     rax, [rbp+37h+var_88]
0x1800c4d0d  mov     [rsp+0E0h+var_98], rax
0x1800c4d12  lea     rax, [rbp+37h+var_70]
0x1800c4d16  mov     [rsp+0E0h+var_A0], rax
0x1800c4d1b  lea     rax, [rbp+37h+var_8C]
0x1800c4d1f  mov     [rsp+0E0h+var_A8], rax
0x1800c4d24  lea     rax, [rbp+37h+var_78]
0x1800c4d28  mov     [rsp+0E0h+var_B0], rax
0x1800c4d2d  lea     rax, [rbp+37h+var_90]
0x1800c4d31  mov     [rsp+0E0h+var_B8], rax
0x1800c4d36  lea     rax, [rbp+37h+var_80]
0x1800c4d3a  mov     [rbp+37h+var_90], 80004005h
0x1800c4d41  jmp     loc_1800C4BF3
0x1800c4d46  mov     rcx, [rdi]
0x1800c4d49  xor     r9d, r9d
0x1800c4d4c  mov     rax, [rbx+48h]
0x1800c4d50  mov     rdx, r14
0x1800c4d53  lea     r8d, [r9+4]
0x1800c4d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4d5c  test    eax, eax
0x1800c4d5e  jnz     loc_1800C4DE4
0x1800c4d64  mov     eax, cs:CallbackContext
0x1800c4d6a  cmp     eax, 2
0x1800c4d6d  jbe     short loc_1800C4DE9
0x1800c4d6f  call    cs:__imp_GetLastError
0x1800c4d75  mov     [rbp+37h+var_8C], 17Ch
0x1800c4d7c  lea     rdx, byte_1801B89C9
0x1800c4d83  mov     [rbp+37h+var_88], eax
0x1800c4d86  lea     rax, aHmachashdataex_0; "HmacHashDataEx"
0x1800c4d8d  mov     [rbp+37h+var_70], rax
0x1800c4d91  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800c4d98  mov     [rbp+37h+var_78], rax
0x1800c4d9c  lea     rax, aErrorXDuringCr; "Error %x during CryptHashData!"
0x1800c4da3  mov     [rbp+37h+var_80], rax
0x1800c4da7  lea     rax, [rbp+37h+var_88]
0x1800c4dab  mov     [rsp+0E0h+var_98], rax
0x1800c4db0  lea     rax, [rbp+37h+var_70]
0x1800c4db4  mov     [rsp+0E0h+var_A0], rax
0x1800c4db9  lea     rax, [rbp+37h+var_8C]
0x1800c4dbd  mov     [rsp+0E0h+var_A8], rax
0x1800c4dc2  lea     rax, [rbp+37h+var_78]
0x1800c4dc6  mov     [rsp+0E0h+var_B0], rax
0x1800c4dcb  lea     rax, [rbp+37h+var_90]
0x1800c4dcf  mov     [rsp+0E0h+var_B8], rax
0x1800c4dd4  lea     rax, [rbp+37h+var_80]
0x1800c4dd8  mov     [rbp+37h+var_90], 80004005h
0x1800c4ddf  jmp     loc_1800C4BF3
0x1800c4de4  mov     esi, 1
0x1800c4de9  mov     eax, esi
0x1800c4deb  mov     rcx, [rbp+37h+var_40]
0x1800c4def  xor     rcx, rsp; StackCookie
0x1800c4df2  call    __security_check_cookie
0x1800c4df7  add     rsp, 0B0h
0x1800c4dfe  pop     r15
0x1800c4e00  pop     r14
0x1800c4e02  pop     r12
0x1800c4e04  pop     rdi
0x1800c4e05  pop     rsi
0x1800c4e06  pop     rbx
0x1800c4e07  pop     rbp
0x1800c4e08  retn
```
