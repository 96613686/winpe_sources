# Windows::Rtl::DeltaDecompressBuffer(ulong,_LBLOB *,unsigned __int64,_LBLOB *,Windows::Rtl::AutoDeltaBlob *,Windows::Rtl::AutoDeltaBlob *)

- ea: `0x180010f70`
- end: `0x180011145`
- name: `?DeltaDecompressBuffer@Rtl@Windows@@YAJKPEAU_LBLOB@@_K0PEAVAutoDeltaBlob@12@2@Z`
- size: `469`
- prototype: `__int64 __fastcall(Windows::Rtl *__hidden this, unsigned int, struct _LBLOB *, unsigned __int64, struct _LBLOB *, struct Windows::Rtl::AutoDeltaBlob *, struct Windows::Rtl::AutoDeltaBlob *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001dae0`

## callees

- `0x180002434`
- `0x1800031e0`
- `0x180010f70`
- `0x18001c320`
- `0x18001fd10`
- `0x1800293a0`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001107e`
- `KERNEL32!GetLastError` at `0x1800110e8`
- `KERNEL32!GetLastError` at `0x18001107e`
- `KERNEL32!GetLastError` at `0x1800110e8`

## string_xrefs

- `0x180010fcc`: `Windows::Rtl::DeltaDecompressBuffer`
- `0x1800110a6`: `Windows::Rtl::DeltaDecompressBuffer`
- `0x180010fc5`: `HeaderSize <= CompressedData->Length`
- `0x1800110b1`: `g_pfnApplyDeltaB(( (DELTA_FLAG_TYPE)0x00000000 ), ReferenceInput, CompressedInput, &UncompressedOutput)`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::DeltaDecompressBuffer(
        Windows::Rtl *this,
        _QWORD *a2,
        struct _LBLOB *a3,
        __int64 *a4,
        struct _LBLOB *a5)
{
  __int64 result; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  signed int LastError; // eax
  unsigned int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int128 v14; // [rsp+30h] [rbp-39h] BYREF
  __int64 v15; // [rsp+40h] [rbp-29h]
  const char *v16; // [rsp+48h] [rbp-21h]
  __int128 v17; // [rsp+50h] [rbp-19h] BYREF
  __int64 v18; // [rsp+60h] [rbp-9h]
  __int128 v19; // [rsp+70h] [rbp+7h]
  __int64 v20; // [rsp+80h] [rbp+17h]
  __int128 v21; // [rsp+88h] [rbp+1Fh] BYREF

  result = anonymous_namespace_::ValidateDeltaBufferCompressorInitialized();
  if ( (int)result >= 0 )
  {
    v8 = *a4;
    if ( (unsigned __int64)*a4 >= 4 )
    {
      *((_QWORD *)&v19 + 1) = *a2;
      *(_QWORD *)&v19 = a2[2];
      v18 = 1;
      *((_QWORD *)&v17 + 1) = v8 - 4;
      v9 = a4[2];
      v15 = 1;
      *(_QWORD *)&v17 = v9 + 4;
      v21 = 0;
      v20 = 0;
      v14 = v17;
      v18 = 0;
      v17 = v19;
      if ( (unsigned int)qword_1800D4E08(0, &v17, &v14, &v21) )
      {
        v12 = *((_QWORD *)&v21 + 1);
        v13 = v21;
        *(_QWORD *)a5 = *((_QWORD *)&v21 + 1);
        *((_QWORD *)a5 + 1) = v12;
        result = 0;
        *((_QWORD *)a5 + 2) = v13;
        *a4 = 0;
      }
      else
      {
        if ( GetLastError() )
        {
          LastError = GetLastError();
          if ( !LastError )
          {
            INTERNAL_ERROR_ACTION(-1073741595);
            JUMPOUT(0x180011144LL);
          }
        }
        else
        {
          LastError = 14077;
        }
        v15 = 488;
        *(_QWORD *)&v14 = "onecore\\base\\wcp\\rtllib\\win32lib\\delta_library.cpp";
        *((_QWORD *)&v14 + 1) = "Windows::Rtl::DeltaDecompressBuffer";
        v16 = "g_pfnApplyDeltaB(( (DELTA_FLAG_TYPE)0x00000000 ), ReferenceInput, CompressedInput, &UncompressedOutput)";
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v11 = ConvertHResultToNtStatus((unsigned int)LastError);
        RtlReportErrorOrigination(&v14, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, v11);
        return v11;
      }
    }
    else
    {
      v15 = 441;
      *(_QWORD *)&v14 = "onecore\\base\\wcp\\rtllib\\win32lib\\delta_library.cpp";
      v16 = "HeaderSize <= CompressedData->Length";
      *((_QWORD *)&v14 + 1) = "Windows::Rtl::DeltaDecompressBuffer";
      RtlReportErrorOrigination(&v14, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
      return 3221225485LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010f70  mov     [rsp-8+arg_10], rbx
0x180010f75  push    rbp
0x180010f76  push    rsi
0x180010f77  push    rdi
0x180010f78  lea     rbp, [rsp-37h]
0x180010f7d  sub     rsp, 0A0h
0x180010f84  mov     rax, cs:__security_cookie
0x180010f8b  xor     rax, rsp
0x180010f8e  mov     [rbp+47h+var_18], rax
0x180010f92  mov     rbx, [rbp+47h+arg_20]
0x180010f96  mov     rdi, r9
0x180010f99  mov     rsi, rdx
0x180010f9c  call    _anonymous_namespace___ValidateDeltaBufferCompressorInitialized
0x180010fa1  test    eax, eax
0x180010fa3  js      loc_18001111A
0x180010fa9  mov     rcx, [rdi]
0x180010fac  cmp     rcx, 4
0x180010fb0  jnb     short loc_180010FFB
0x180010fb2  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x180010fb9  mov     [rbp+47h+var_70], 1B9h
0x180010fc1  mov     qword ptr [rbp+47h+var_80], rcx
0x180010fc5  lea     rax, aHeadersizeComp; "HeaderSize <= CompressedData->Length"
0x180010fcc  lea     rcx, aWindowsRtlDelt; "Windows::Rtl::DeltaDecompressBuffer"
0x180010fd3  mov     [rbp+47h+var_68], rax
0x180010fd7  mov     qword ptr [rbp+47h+var_80+8], rcx
0x180010fdb  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180010fe2  lea     rcx, [rbp+47h+var_80]
0x180010fe6  mov     r8d, 0C000000Dh
0x180010fec  call    RtlReportErrorOrigination
0x180010ff1  mov     eax, 0C000000Dh
0x180010ff6  jmp     loc_18001111A
0x180010ffb  mov     rax, [rsi]
0x180010ffe  lea     r9, [rbp+47h+var_28]
0x180011002  mov     qword ptr [rbp+47h+var_40+8], rax
0x180011006  lea     r8, [rbp+47h+var_80]
0x18001100a  mov     rax, [rsi+10h]
0x18001100e  lea     rdx, [rbp+47h+var_60]
0x180011012  mov     qword ptr [rbp+47h+var_40], rax
0x180011016  xorps   xmm0, xmm0
0x180011019  lea     rax, [rcx-4]
0x18001101d  mov     [rbp+47h+var_50], 1
0x180011025  movsd   xmm1, [rbp+47h+var_50]
0x18001102a  xor     ecx, ecx
0x18001102c  mov     qword ptr [rbp+47h+var_60+8], rax
0x180011030  mov     rax, [rdi+10h]
0x180011034  add     rax, 4
0x180011038  movsd   [rbp+47h+var_70], xmm1
0x18001103d  mov     qword ptr [rbp+47h+var_60], rax
0x180011041  mov     rax, cs:qword_1800D4E08
0x180011048  movups  [rbp+47h+var_28], xmm0
0x18001104c  mov     [rsp+0B0h+arg_0], r14
0x180011054  xor     r14d, r14d
0x180011057  movups  xmm0, [rbp+47h+var_60]
0x18001105b  mov     [rbp+47h+var_30], r14
0x18001105f  movsd   xmm1, [rbp+47h+var_30]
0x180011064  movaps  [rbp+47h+var_80], xmm0
0x180011068  movups  xmm0, [rbp+47h+var_40]
0x18001106c  movsd   [rbp+47h+var_50], xmm1
0x180011071  movaps  [rbp+47h+var_60], xmm0
0x180011075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001107a  test    eax, eax
0x18001107c  jnz     short loc_1800110FA
0x18001107e  call    cs:__imp_GetLastError
0x180011085  nop     dword ptr [rax+rax+00h]
0x18001108a  test    eax, eax
0x18001108c  jnz     short loc_1800110E8
0x18001108e  mov     eax, 36FDh
0x180011093  mov     [rbp+47h+var_70], 1E8h
0x18001109b  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x1800110a2  mov     qword ptr [rbp+47h+var_80], rcx
0x1800110a6  lea     rcx, aWindowsRtlDelt; "Windows::Rtl::DeltaDecompressBuffer"
0x1800110ad  mov     qword ptr [rbp+47h+var_80+8], rcx
0x1800110b1  lea     rcx, aGPfnapplydelta; "g_pfnApplyDeltaB(( (DELTA_FLAG_TYPE)0x0"...
0x1800110b8  mov     [rbp+47h+var_68], rcx
0x1800110bc  test    eax, eax
0x1800110be  jle     short loc_1800110C8
0x1800110c0  movzx   eax, ax
0x1800110c3  or      eax, 80070000h
0x1800110c8  mov     ecx, eax
0x1800110ca  call    ConvertHResultToNtStatus
0x1800110cf  mov     r8d, eax
0x1800110d2  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1800110d9  lea     rcx, [rbp+47h+var_80]
0x1800110dd  mov     ebx, eax
0x1800110df  call    RtlReportErrorOrigination
0x1800110e4  mov     eax, ebx
0x1800110e6  jmp     short loc_180011112
0x1800110e8  call    cs:__imp_GetLastError
0x1800110ef  nop     dword ptr [rax+rax+00h]
0x1800110f4  test    eax, eax
0x1800110f6  jz      short loc_18001113A
0x1800110f8  jmp     short loc_180011093
0x1800110fa  mov     rax, qword ptr [rbp+47h+var_28+8]
0x1800110fe  mov     rcx, qword ptr [rbp+47h+var_28]
0x180011102  mov     [rbx], rax
0x180011105  mov     [rbx+8], rax
0x180011109  xor     eax, eax
0x18001110b  mov     [rbx+10h], rcx
0x18001110f  mov     [rdi], r14
0x180011112  mov     r14, [rsp+0B0h+arg_0]
0x18001111a  mov     rcx, [rbp+47h+var_18]
0x18001111e  xor     rcx, rsp; StackCookie
0x180011121  call    __security_check_cookie
0x180011126  mov     rbx, [rsp+0B0h+arg_10]
0x18001112e  add     rsp, 0A0h
0x180011135  pop     rdi
0x180011136  pop     rsi
0x180011137  pop     rbp
0x180011138  retn
0x18001113a  mov     ecx, 0C00000E5h; int
0x18001113f  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
