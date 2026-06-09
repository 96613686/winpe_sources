# CW32System::GetDraftModeFontInfo(short &,short &,ulong &)

- ea: `0x1801249d0`
- end: `0x180124aea`
- name: `?GetDraftModeFontInfo@CW32System@@SA_NAEAF0AEAK@Z`
- size: `282`
- prototype: `bool __fastcall(__int16 *, __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180022344`
- `0x180055400`
- `0x1800b58fc`

## callees

- `0x180029234`
- `0x1801249d0`
- `0x18012ac54`
- `0x18013bad0`
- `0x18013c916`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180124a3c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180124a3c`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x180124a97`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x180124a97`

## pseudocode

```c
bool __fastcall CW32System::GetDraftModeFontInfo(__int16 *a1, __int16 *a2, unsigned int *a3)
{
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rcx
  bool result; // al
  int pvParam; // [rsp+20h] [rbp-228h] BYREF
  _BYTE v13[404]; // [rsp+24h] [rbp-224h] BYREF
  int v14; // [rsp+1B8h] [rbp-90h]
  unsigned __int16 Src[38]; // [rsp+1D4h] [rbp-74h] BYREF

  if ( !CW32System::_draftModeFontInfo && !word_1802DF1EA )
  {
    memset_0(v13, 0, 0x1F4u);
    pvParam = 504;
    if ( SystemParametersInfoW(0x29u, 0x1F8u, &pvParam, 0) )
    {
      word_1802DF1EA = CFICache::GetFontNameIndex(Src, 1);
      v8 = (unsigned int)((1440 * v14) >> 31);
      v9 = 1440 * v14 / CW32System::_yPerInchScreenDC;
      v10 = (unsigned int)(v9 + 0x8000);
      if ( (unsigned int)v10 > 0xFFFF )
      {
        LODWORD(v8) = 1440 * v14 % CW32System::_yPerInchScreenDC;
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v10, v8, v6, v7);
      }
      word_1802DF1EC = 1440 * v14 / CW32System::_yPerInchScreenDC;
      if ( (__int16)v9 <= 0 )
        word_1802DF1EC = -(__int16)v9;
    }
    dword_1802DF1F0 = GetSysColor(8);
  }
  result = 1;
  *a1 = word_1802DF1EA;
  *a2 = word_1802DF1EC;
  *a3 = dword_1802DF1F0;
  return result;
}

```

## disassembly

```asm
0x1801249d0  mov     [rsp+arg_18], rbx
0x1801249d5  push    rbp
0x1801249d6  push    rsi
0x1801249d7  push    rdi
0x1801249d8  sub     rsp, 230h
0x1801249df  mov     rax, cs:__security_cookie
0x1801249e6  xor     rax, rsp
0x1801249e9  mov     [rsp+248h+var_28], rax
0x1801249f1  xor     ebp, ebp
0x1801249f3  mov     rsi, r8
0x1801249f6  cmp     cs:?_draftModeFontInfo@CW32System@@0UDraftModeFontInfo@1@A, bpl; CW32System::DraftModeFontInfo CW32System::_draftModeFontInfo
0x1801249fd  mov     rdi, rdx
0x180124a00  mov     rbx, rcx
0x180124a03  jnz     loc_180124AA3
0x180124a09  cmp     cs:word_1802DF1EA, bp
0x180124a10  jnz     loc_180124AA3
0x180124a16  xor     edx, edx; Val
0x180124a18  lea     rcx, [rsp+248h+var_224]; void *
0x180124a1d  mov     r8d, 1F4h; Size
0x180124a23  call    memset_0
0x180124a28  mov     edx, 1F8h; uiParam
0x180124a2d  lea     r8, [rsp+248h+pvParam]; pvParam
0x180124a32  xor     r9d, r9d; fWinIni
0x180124a35  mov     [rsp+248h+pvParam], edx
0x180124a39  lea     ecx, [rbp+29h]; uiAction
0x180124a3c  call    cs:__imp_SystemParametersInfoW
0x180124a42  test    eax, eax
0x180124a44  jz      short loc_180124A92
0x180124a46  mov     dl, 1; bool
0x180124a48  lea     rcx, [rsp+248h+Src]; Src
0x180124a50  call    ?GetFontNameIndex@CFICache@@SAFPEBG_N@Z; CFICache::GetFontNameIndex(ushort const *,bool)
0x180124a55  mov     cs:word_1802DF1EA, ax
0x180124a5c  imul    eax, [rsp+248h+var_90], 5A0h
0x180124a67  cdq
0x180124a68  idiv    cs:?_yPerInchScreenDC@CW32System@@0JA; long CW32System::_yPerInchScreenDC
0x180124a6e  lea     ecx, [rax+8000h]
0x180124a74  cmp     ecx, 0FFFFh
0x180124a7a  ja      short loc_180124AE4
0x180124a7c  mov     cs:word_1802DF1EC, ax
0x180124a83  test    ax, ax
0x180124a86  jg      short loc_180124A92
0x180124a88  neg     ax
0x180124a8b  mov     cs:word_1802DF1EC, ax
0x180124a92  mov     ecx, 8; nIndex
0x180124a97  call    cs:__imp_GetSysColor
0x180124a9d  mov     cs:dword_1802DF1F0, eax
0x180124aa3  movzx   ecx, cs:word_1802DF1EA
0x180124aaa  mov     al, 1
0x180124aac  mov     [rbx], cx
0x180124aaf  movzx   ecx, cs:word_1802DF1EC
0x180124ab6  mov     [rdi], cx
0x180124ab9  mov     ecx, cs:dword_1802DF1F0
0x180124abf  mov     [rsi], ecx
0x180124ac1  mov     rcx, [rsp+248h+var_28]
0x180124ac9  xor     rcx, rsp; StackCookie
0x180124acc  call    __security_check_cookie
0x180124ad1  mov     rbx, [rsp+248h+arg_18]
0x180124ad9  add     rsp, 230h
0x180124ae0  pop     rdi
0x180124ae1  pop     rsi
0x180124ae2  pop     rbp
0x180124ae3  retn
0x180124ae4  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
