# FwServiceRestriction::BuildServiceNameDescString(uint,ushort const *,ushort * *)

- ea: `0x1800422f4`
- end: `0x180042467`
- name: `?BuildServiceNameDescString@FwServiceRestriction@@AEAAJIPEBGPEAPEAG@Z`
- size: `371`
- prototype: `__int64 __fastcall(FwServiceRestriction *__hidden this, unsigned int, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180042004`

## callees

- `0x180005954`
- `0x1800277b0`
- `0x18003104c`
- `0x1800422f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800423c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800423c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004243f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004243f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800423b8`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800423b8`
- `fwbase!FwBaseFree` at `0x18004244a`
- `fwbase!FwBaseFree` at `0x18004244a`
- `fwbase!FwLoadString` at `0x18004235c`
- `fwbase!FwLoadString` at `0x18004235c`
- `fwbase!FwStringCopy` at `0x1800423ff`
- `fwbase!FwStringCopy` at `0x1800423ff`

## pseudocode

```c
__int64 __fastcall FwServiceRestriction::BuildServiceNameDescString(
        FwServiceRestriction *this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  FwPolicy2 *v8; // rcx
  __int64 v9; // rdx
  signed int LastError; // eax
  __int64 v11; // r9
  WCHAR Buffer[4]; // [rsp+40h] [rbp-38h] BYREF
  LPCVOID lpSource; // [rsp+48h] [rbp-30h] BYREF
  va_list Arguments; // [rsp+50h] [rbp-28h] BYREF

  Arguments = (va_list)a3;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids);
  lpSource = 0;
  *(_QWORD *)Buffer = 0;
  v6 = FwLoadString(a2, &lpSource);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( FormatMessageW(0x2500u, lpSource, 0, 0, Buffer, 0, &Arguments) )
      goto LABEL_15;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (v7 & 0x80000000) == 0 )
    {
LABEL_15:
      v6 = FwStringCopy(*(_QWORD *)Buffer, a4);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v9 = 39;
          goto LABEL_19;
        }
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 38;
        v11 = v7;
LABEL_20:
        WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids, v11);
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 37;
LABEL_19:
      v11 = (unsigned int)v6;
      goto LABEL_20;
    }
  }
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  FwBaseFree(lpSource);
  return v7;
}

```

## disassembly

```asm
0x1800422f4  push    rbx
0x1800422f6  push    rbp
0x1800422f7  push    rdi
0x1800422f8  sub     rsp, 60h
0x1800422fc  mov     rax, cs:__security_cookie
0x180042303  xor     rax, rsp
0x180042306  mov     [rsp+78h+var_20], rax
0x18004230b  mov     rdi, r9
0x18004230e  mov     [rsp+78h+var_28], r8
0x180042313  mov     ebx, edx
0x180042315  mov     rcx, cs:WPP_GLOBAL_Control
0x18004231c  lea     rbp, WPP_GLOBAL_Control
0x180042323  cmp     rcx, rbp
0x180042326  jz      short loc_180042343
0x180042328  test    byte ptr [rcx+1Ch], 8
0x18004232c  jz      short loc_180042343
0x18004232e  mov     rcx, [rcx+10h]
0x180042332  lea     r8, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids
0x180042339  mov     edx, 24h ; '$'
0x18004233e  call    WPP_SF_
0x180042343  lea     rdx, [rsp+78h+lpSource]
0x180042348  mov     [rsp+78h+lpSource], 0
0x180042351  mov     ecx, ebx
0x180042353  mov     qword ptr [rsp+78h+Buffer], 0
0x18004235c  call    cs:__imp_FwLoadString
0x180042362  mov     ebx, eax
0x180042364  test    eax, eax
0x180042366  jns     short loc_18004238C
0x180042368  mov     rcx, cs:WPP_GLOBAL_Control
0x18004236f  cmp     rcx, rbp
0x180042372  jz      loc_180042435
0x180042378  test    byte ptr [rcx+1Ch], 1
0x18004237c  jz      loc_180042435
0x180042382  mov     edx, 25h ; '%'
0x180042387  jmp     loc_180042422
0x18004238c  mov     rdx, [rsp+78h+lpSource]; lpSource
0x180042391  lea     rax, [rsp+78h+var_28]
0x180042396  mov     [rsp+78h+Arguments], rax; Arguments
0x18004239b  xor     r9d, r9d; dwLanguageId
0x18004239e  lea     rax, [rsp+78h+Buffer]
0x1800423a3  mov     [rsp+78h+nSize], 0; nSize
0x1800423ab  xor     r8d, r8d; dwMessageId
0x1800423ae  mov     [rsp+78h+lpBuffer], rax; lpBuffer
0x1800423b3  mov     ecx, 2500h; dwFlags
0x1800423b8  call    cs:__imp_FormatMessageW
0x1800423be  test    eax, eax
0x1800423c0  jnz     short loc_1800423F7
0x1800423c2  call    cs:__imp_GetLastError
0x1800423c8  mov     ebx, eax
0x1800423ca  test    eax, eax
0x1800423cc  jle     short loc_1800423D7
0x1800423ce  movzx   ebx, ax
0x1800423d1  or      ebx, 80070000h
0x1800423d7  test    ebx, ebx
0x1800423d9  jns     short loc_1800423F7
0x1800423db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800423e2  cmp     rcx, rbp
0x1800423e5  jz      short loc_180042435
0x1800423e7  test    byte ptr [rcx+1Ch], 1
0x1800423eb  jz      short loc_180042435
0x1800423ed  mov     edx, 26h ; '&'
0x1800423f2  mov     r9d, ebx
0x1800423f5  jmp     short loc_180042425
0x1800423f7  mov     rcx, qword ptr [rsp+78h+Buffer]
0x1800423fc  mov     rdx, rdi
0x1800423ff  call    cs:__imp_FwStringCopy
0x180042405  mov     ebx, eax
0x180042407  test    eax, eax
0x180042409  jns     short loc_180042435
0x18004240b  mov     rcx, cs:WPP_GLOBAL_Control
0x180042412  cmp     rcx, rbp
0x180042415  jz      short loc_180042435
0x180042417  test    byte ptr [rcx+1Ch], 1
0x18004241b  jz      short loc_180042435
0x18004241d  mov     edx, 27h ; '''
0x180042422  mov     r9d, eax
0x180042425  mov     rcx, [rcx+10h]
0x180042429  lea     r8, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids
0x180042430  call    WPP_SF_d
0x180042435  mov     rcx, qword ptr [rsp+78h+Buffer]; hMem
0x18004243a  test    rcx, rcx
0x18004243d  jz      short loc_180042445
0x18004243f  call    cs:__imp_LocalFree
0x180042445  mov     rcx, [rsp+78h+lpSource]
0x18004244a  call    cs:__imp_FwBaseFree
0x180042450  mov     eax, ebx
0x180042452  mov     rcx, [rsp+78h+var_20]
0x180042457  xor     rcx, rsp; StackCookie
0x18004245a  call    __security_check_cookie
0x18004245f  add     rsp, 60h
0x180042463  pop     rdi
0x180042464  pop     rbp
0x180042465  pop     rbx
0x180042466  retn
```
