# Windows::Rtl::DeltaDecompressBuffer(ulong,_LBLOB *,unsigned __int64,_LBLOB *,Windows::Rtl::AutoDeltaBlob *,Windows::Rtl::AutoDeltaBlob *)

- ea: `0x18000c890`
- end: `0x18000ca51`
- name: `?DeltaDecompressBuffer@Rtl@Windows@@YAJKPEAU_LBLOB@@_K0PEAVAutoDeltaBlob@12@2@Z`
- size: `449`
- prototype: `__int64 __fastcall(Windows::Rtl *__hidden this, unsigned int, struct _LBLOB *, unsigned __int64, struct _LBLOB *, struct Windows::Rtl::AutoDeltaBlob *, struct Windows::Rtl::AutoDeltaBlob *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c300`

## callees

- `0x18000c890`
- `0x18000cff8`
- `0x18001f1d8`
- `0x18002d2b0`
- `0x18007d794`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c9d0`
- `KERNEL32!GetLastError` at `0x18000ca2f`
- `KERNEL32!GetLastError` at `0x18000c9d0`
- `KERNEL32!GetLastError` at `0x18000ca2f`
- `ntdll!RtlRaiseStatus` at `0x18000ca44`
- `ntdll!RtlRaiseStatus` at `0x18000ca44`

## string_xrefs

- `0x18000c9b2`: `Windows::Rtl::DeltaDecompressBuffer`
- `0x18000c9f8`: `Windows::Rtl::DeltaDecompressBuffer`
- `0x18000c9ab`: `HeaderSize <= CompressedData->Length`
- `0x18000ca03`: `g_pfnApplyDeltaB(( (DELTA_FLAG_TYPE)0x00000000 ), ReferenceInput, CompressedInput, &UncompressedOutput)`

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
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  signed int LastError; // eax
  __int128 v13; // [rsp+30h] [rbp-49h] BYREF
  __int64 v14; // [rsp+40h] [rbp-39h]
  const char *v15; // [rsp+48h] [rbp-31h]
  __int128 v16; // [rsp+50h] [rbp-29h] BYREF
  __int64 v17; // [rsp+60h] [rbp-19h]
  __int128 v18; // [rsp+70h] [rbp-9h]
  __int64 v19; // [rsp+80h] [rbp+7h]
  __int128 v20; // [rsp+88h] [rbp+Fh] BYREF
  int v21; // [rsp+98h] [rbp+1Fh] BYREF

  v21 = 0;
  result = anonymous_namespace_::ValidateDeltaBufferCompressorInitialized();
  if ( (int)result >= 0 )
  {
    v8 = *a4;
    if ( (unsigned __int64)*a4 < 4 )
    {
      v14 = 441;
      *(_QWORD *)&v13 = "onecore\\base\\wcp\\rtllib\\win32lib\\delta_library.cpp";
      v15 = "HeaderSize <= CompressedData->Length";
      *((_QWORD *)&v13 + 1) = "Windows::Rtl::DeltaDecompressBuffer";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
               &v21,
               &v13);
    }
    else
    {
      *((_QWORD *)&v18 + 1) = *a2;
      v9 = a2[2];
      *((_QWORD *)&v16 + 1) = v8 - 4;
      *(_QWORD *)&v16 = a4[2] + 4;
      v20 = 0;
      *(_QWORD *)&v18 = v9;
      v19 = 0;
      v14 = 1;
      v13 = v16;
      v17 = 0;
      v16 = v18;
      if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, __int128 *, __int128 *, __int128 *))qword_1800D2E28)(
                           0,
                           &v16,
                           &v13,
                           &v20) )
      {
        v10 = *((_QWORD *)&v20 + 1);
        v11 = v20;
        *(_QWORD *)a5 = *((_QWORD *)&v20 + 1);
        *((_QWORD *)a5 + 1) = v10;
        result = 0;
        *((_QWORD *)a5 + 2) = v11;
        *a4 = 0;
      }
      else
      {
        if ( GetLastError() )
        {
          LastError = GetLastError();
          if ( !LastError )
            RtlRaiseStatus(-1073741595);
        }
        else
        {
          LastError = 14077;
        }
        v14 = 488;
        *(_QWORD *)&v13 = "onecore\\base\\wcp\\rtllib\\win32lib\\delta_library.cpp";
        *((_QWORD *)&v13 + 1) = "Windows::Rtl::DeltaDecompressBuffer";
        v15 = "g_pfnApplyDeltaB(( (DELTA_FLAG_TYPE)0x00000000 ), ReferenceInput, CompressedInput, &UncompressedOutput)";
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
                 &v21,
                 &v13,
                 (unsigned int)LastError);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c890  mov     [rsp-8+arg_0], rbx
0x18000c895  mov     [rsp-8+arg_10], rsi
0x18000c89a  push    rbp
0x18000c89b  push    rdi
0x18000c89c  push    r14
0x18000c89e  lea     rbp, [rsp-37h]
0x18000c8a3  sub     rsp, 0B0h
0x18000c8aa  mov     rax, cs:__security_cookie
0x18000c8b1  xor     rax, rsp
0x18000c8b4  mov     [rbp+47h+var_20], rax
0x18000c8b8  mov     rdi, [rbp+47h+arg_20]
0x18000c8bc  xor     r14d, r14d
0x18000c8bf  mov     [rbp+47h+var_28], r14d
0x18000c8c3  mov     rbx, r9
0x18000c8c6  mov     rsi, rdx
0x18000c8c9  call    _anonymous_namespace___ValidateDeltaBufferCompressorInitialized
0x18000c8ce  test    eax, eax
0x18000c8d0  js      loc_18000C973
0x18000c8d6  mov     rax, [rbx]
0x18000c8d9  cmp     rax, 4
0x18000c8dd  jb      loc_18000C998
0x18000c8e3  mov     rcx, [rsi]
0x18000c8e6  lea     r9, [rbp+47h+var_38]
0x18000c8ea  add     rax, 0FFFFFFFFFFFFFFFCh
0x18000c8ee  mov     qword ptr [rbp+47h+var_50+8], rcx
0x18000c8f2  mov     rcx, [rsi+10h]
0x18000c8f6  lea     r8, [rbp+47h+var_90]
0x18000c8fa  mov     qword ptr [rbp+47h+var_70+8], rax
0x18000c8fe  lea     rdx, [rbp+47h+var_70]
0x18000c902  mov     rax, [rbx+10h]
0x18000c906  xorps   xmm0, xmm0
0x18000c909  add     rax, 4
0x18000c90d  mov     [rbp+47h+var_60], 1
0x18000c915  movsd   xmm1, [rbp+47h+var_60]
0x18000c91a  mov     qword ptr [rbp+47h+var_70], rax
0x18000c91e  mov     rax, cs:qword_1800D2E28
0x18000c925  movups  [rbp+47h+var_38], xmm0
0x18000c929  mov     qword ptr [rbp+47h+var_50], rcx
0x18000c92d  xor     ecx, ecx
0x18000c92f  movups  xmm0, [rbp+47h+var_70]
0x18000c933  mov     [rbp+47h+var_40], r14
0x18000c937  movsd   [rbp+47h+var_80], xmm1
0x18000c93c  movsd   xmm1, [rbp+47h+var_40]
0x18000c941  movaps  [rbp+47h+var_90], xmm0
0x18000c945  movups  xmm0, [rbp+47h+var_50]
0x18000c949  movsd   [rbp+47h+var_60], xmm1
0x18000c94e  movaps  [rbp+47h+var_70], xmm0
0x18000c952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c957  test    eax, eax
0x18000c959  jz      short loc_18000C9D0
0x18000c95b  mov     rax, qword ptr [rbp+47h+var_38+8]
0x18000c95f  mov     rcx, qword ptr [rbp+47h+var_38]
0x18000c963  mov     [rdi], rax
0x18000c966  mov     [rdi+8], rax
0x18000c96a  xor     eax, eax
0x18000c96c  mov     [rdi+10h], rcx
0x18000c970  mov     [rbx], r14
0x18000c973  mov     rcx, [rbp+47h+var_20]
0x18000c977  xor     rcx, rsp; StackCookie
0x18000c97a  call    __security_check_cookie
0x18000c97f  lea     r11, [rsp+0C0h+var_10]
0x18000c987  mov     rbx, [r11+20h]
0x18000c98b  mov     rsi, [r11+30h]
0x18000c98f  mov     rsp, r11
0x18000c992  pop     r14
0x18000c994  pop     rdi
0x18000c995  pop     rbp
0x18000c996  retn
0x18000c998  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x18000c99f  mov     [rbp+47h+var_80], 1B9h
0x18000c9a7  mov     qword ptr [rbp+47h+var_90], rcx
0x18000c9ab  lea     rax, aHeadersizeComp; "HeaderSize <= CompressedData->Length"
0x18000c9b2  lea     rcx, aWindowsRtlDelt; "Windows::Rtl::DeltaDecompressBuffer"
0x18000c9b9  mov     [rbp+47h+var_78], rax
0x18000c9bd  mov     qword ptr [rbp+47h+var_90+8], rcx
0x18000c9c1  lea     rdx, [rbp+47h+var_90]
0x18000c9c5  lea     rcx, [rbp+47h+var_28]
0x18000c9c9  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18000c9ce  jmp     short loc_18000C973
0x18000c9d0  call    cs:__imp_GetLastError
0x18000c9d7  nop     dword ptr [rax+rax+00h]
0x18000c9dc  test    eax, eax
0x18000c9de  jnz     short loc_18000CA2F
0x18000c9e0  mov     eax, 36FDh
0x18000c9e5  mov     [rbp+47h+var_80], 1E8h
0x18000c9ed  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x18000c9f4  mov     qword ptr [rbp+47h+var_90], rcx
0x18000c9f8  lea     rcx, aWindowsRtlDelt; "Windows::Rtl::DeltaDecompressBuffer"
0x18000c9ff  mov     qword ptr [rbp+47h+var_90+8], rcx
0x18000ca03  lea     rcx, aGPfnapplydelta; "g_pfnApplyDeltaB(( (DELTA_FLAG_TYPE)0x0"...
0x18000ca0a  mov     [rbp+47h+var_78], rcx
0x18000ca0e  test    eax, eax
0x18000ca10  jle     short loc_18000CA1A
0x18000ca12  movzx   eax, ax
0x18000ca15  or      eax, 80070000h
0x18000ca1a  mov     r8d, eax
0x18000ca1d  lea     rdx, [rbp+47h+var_90]
0x18000ca21  lea     rcx, [rbp+47h+var_28]
0x18000ca25  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18000ca2a  jmp     loc_18000C973
0x18000ca2f  call    cs:__imp_GetLastError
0x18000ca36  nop     dword ptr [rax+rax+00h]
0x18000ca3b  test    eax, eax
0x18000ca3d  jnz     short loc_18000C9E5
0x18000ca3f  mov     ecx, 0C00000E5h; Status
0x18000ca44  call    cs:__imp_RtlRaiseStatus
0x18000ca4b  nop     dword ptr [rax+rax+00h]
0x18000ca50  int     3; Trap to Debugger
```
