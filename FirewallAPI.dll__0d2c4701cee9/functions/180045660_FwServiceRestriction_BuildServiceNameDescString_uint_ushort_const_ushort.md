# FwServiceRestriction::BuildServiceNameDescString(uint,ushort const *,ushort * *)

- ea: `0x180045660`
- end: `0x1800457f8`
- name: `?BuildServiceNameDescString@FwServiceRestriction@@AEAAJIPEBGPEAPEAG@Z`
- size: `408`
- prototype: `__int64 __fastcall(FwServiceRestriction *__hidden this, unsigned int, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180045344`

## callees

- `0x180005e0c`
- `0x1800294b0`
- `0x18003336c`
- `0x180045660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004573a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004573a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800457c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800457c3`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004572a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004572a`
- `fwbase!FwBaseFree` at `0x1800457d4`
- `fwbase!FwBaseFree` at `0x1800457d4`
- `fwbase!FwLoadString` at `0x1800456c8`
- `fwbase!FwLoadString` at `0x1800456c8`
- `fwbase!FwStringCopy` at `0x18004577d`
- `fwbase!FwStringCopy` at `0x18004577d`

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
0x180045660  push    rbx
0x180045662  push    rbp
0x180045663  push    rdi
0x180045664  sub     rsp, 60h
0x180045668  mov     rax, cs:__security_cookie
0x18004566f  xor     rax, rsp
0x180045672  mov     [rsp+78h+var_20], rax
0x180045677  mov     rdi, r9
0x18004567a  mov     [rsp+78h+var_28], r8
0x18004567f  mov     ebx, edx
0x180045681  mov     rcx, cs:WPP_GLOBAL_Control
0x180045688  lea     rbp, WPP_GLOBAL_Control
0x18004568f  cmp     rcx, rbp
0x180045692  jz      short loc_1800456AF
0x180045694  test    byte ptr [rcx+1Ch], 8
0x180045698  jz      short loc_1800456AF
0x18004569a  mov     rcx, [rcx+10h]
0x18004569e  lea     r8, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids
0x1800456a5  mov     edx, 24h ; '$'
0x1800456aa  call    WPP_SF_
0x1800456af  lea     rdx, [rsp+78h+lpSource]
0x1800456b4  mov     [rsp+78h+lpSource], 0
0x1800456bd  mov     ecx, ebx
0x1800456bf  mov     qword ptr [rsp+78h+Buffer], 0
0x1800456c8  call    cs:__imp_FwLoadString
0x1800456cf  nop     dword ptr [rax+rax+00h]
0x1800456d4  mov     ebx, eax
0x1800456d6  test    eax, eax
0x1800456d8  jns     short loc_1800456FE
0x1800456da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800456e1  cmp     rcx, rbp
0x1800456e4  jz      loc_1800457B9
0x1800456ea  test    byte ptr [rcx+1Ch], 1
0x1800456ee  jz      loc_1800457B9
0x1800456f4  mov     edx, 25h ; '%'
0x1800456f9  jmp     loc_1800457A6
0x1800456fe  mov     rdx, [rsp+78h+lpSource]; lpSource
0x180045703  lea     rax, [rsp+78h+var_28]
0x180045708  mov     [rsp+78h+Arguments], rax; Arguments
0x18004570d  xor     r9d, r9d; dwLanguageId
0x180045710  lea     rax, [rsp+78h+Buffer]
0x180045715  mov     [rsp+78h+nSize], 0; nSize
0x18004571d  xor     r8d, r8d; dwMessageId
0x180045720  mov     [rsp+78h+lpBuffer], rax; lpBuffer
0x180045725  mov     ecx, 2500h; dwFlags
0x18004572a  call    cs:__imp_FormatMessageW
0x180045731  nop     dword ptr [rax+rax+00h]
0x180045736  test    eax, eax
0x180045738  jnz     short loc_180045775
0x18004573a  call    cs:__imp_GetLastError
0x180045741  nop     dword ptr [rax+rax+00h]
0x180045746  mov     ebx, eax
0x180045748  test    eax, eax
0x18004574a  jle     short loc_180045755
0x18004574c  movzx   ebx, ax
0x18004574f  or      ebx, 80070000h
0x180045755  test    ebx, ebx
0x180045757  jns     short loc_180045775
0x180045759  mov     rcx, cs:WPP_GLOBAL_Control
0x180045760  cmp     rcx, rbp
0x180045763  jz      short loc_1800457B9
0x180045765  test    byte ptr [rcx+1Ch], 1
0x180045769  jz      short loc_1800457B9
0x18004576b  mov     edx, 26h ; '&'
0x180045770  mov     r9d, ebx
0x180045773  jmp     short loc_1800457A9
0x180045775  mov     rcx, qword ptr [rsp+78h+Buffer]
0x18004577a  mov     rdx, rdi
0x18004577d  call    cs:__imp_FwStringCopy
0x180045784  nop     dword ptr [rax+rax+00h]
0x180045789  mov     ebx, eax
0x18004578b  test    eax, eax
0x18004578d  jns     short loc_1800457B9
0x18004578f  mov     rcx, cs:WPP_GLOBAL_Control
0x180045796  cmp     rcx, rbp
0x180045799  jz      short loc_1800457B9
0x18004579b  test    byte ptr [rcx+1Ch], 1
0x18004579f  jz      short loc_1800457B9
0x1800457a1  mov     edx, 27h ; '''
0x1800457a6  mov     r9d, eax
0x1800457a9  mov     rcx, [rcx+10h]
0x1800457ad  lea     r8, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids
0x1800457b4  call    WPP_SF_d
0x1800457b9  mov     rcx, qword ptr [rsp+78h+Buffer]; hMem
0x1800457be  test    rcx, rcx
0x1800457c1  jz      short loc_1800457CF
0x1800457c3  call    cs:__imp_LocalFree
0x1800457ca  nop     dword ptr [rax+rax+00h]
0x1800457cf  mov     rcx, [rsp+78h+lpSource]
0x1800457d4  call    cs:__imp_FwBaseFree
0x1800457db  nop     dword ptr [rax+rax+00h]
0x1800457e0  mov     eax, ebx
0x1800457e2  mov     rcx, [rsp+78h+var_20]
0x1800457e7  xor     rcx, rsp; StackCookie
0x1800457ea  call    __security_check_cookie
0x1800457ef  add     rsp, 60h
0x1800457f3  pop     rdi
0x1800457f4  pop     rbp
0x1800457f5  pop     rbx
0x1800457f6  retn
```
