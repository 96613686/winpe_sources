# CSystemMSIController::_EnumerateSystemMsi(_IMAGELIST *,void *)

- ea: `0x18003ea60`
- end: `0x18003ec4b`
- name: `?_EnumerateSystemMsi@CSystemMSIController@@AEAAJPEAU_IMAGELIST@@PEAX@Z`
- size: `491`
- prototype: `int(CSystemMSIController *__hidden this, struct _IMAGELIST *, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180032730`

## callees

- `0x18000b2dc`
- `0x18003ea60`
- `0x18003ed08`
- `0x18003ee48`
- `0x18005610c`
- `0x180056264`
- `0x1800565e8`
- `0x1800582a2`
- `0x1800582e0`

## import_xrefs

- `SHELL32!SHGetFileInfoW` at `0x18003ebba`
- `SHELL32!SHGetFileInfoW` at `0x18003ebba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ebe1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ebec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ebf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ebfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ebe1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ebec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ebf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ebfc`

## pseudocode

```c
__int64 __fastcall CSystemMSIController::_EnumerateSystemMsi(
        CSystemMSIController *this,
        struct _IMAGELIST *a2,
        void *a3)
{
  HDPA v5; // rax
  CSystemMSIController *v6; // rcx
  int v7; // ebx
  unsigned int i; // r14d
  unsigned int SystemMSIComponent; // edi
  void *v10; // r15
  unsigned __int64 v11; // rdx
  _QWORD *v12; // rax
  _QWORD *v13; // rsi
  unsigned __int16 *v14; // rcx
  unsigned __int16 **uFlags; // [rsp+20h] [rbp-E0h]
  unsigned __int16 **v17; // [rsp+28h] [rbp-D8h]
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 *v20; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  HIMAGELIST himl; // [rsp+58h] [rbp-A8h]
  SHFILEINFOW psfi; // [rsp+60h] [rbp-A0h] BYREF

  himl = a2;
  v5 = DPA_Create(1);
  *((_QWORD *)this + 3) = v5;
  if ( v5 )
  {
    v7 = 0;
    for ( i = 0; ; ++i )
    {
      pv = 0;
      SystemMSIComponent = CSystemMSIController::_GetSystemMSIComponent(v6, i, (unsigned __int16 **)&pv);
      if ( !SystemMSIComponent )
      {
        v10 = pv;
        v19 = 0;
        v18 = 0;
        v20 = 0;
        SystemMSIComponent = CSystemMSIController::_GetSystemMSIComponentInfo(
                               v6,
                               a3,
                               (unsigned __int16 *)pv,
                               &v20,
                               uFlags,
                               v17,
                               &v19,
                               &v18);
        if ( SystemMSIComponent || v18 != 1 )
        {
          CoTaskMemFree(v10);
          CoTaskMemFree(v20);
          CoTaskMemFree(0);
        }
        else
        {
          v12 = DirectUI::HAllocAndZero((DirectUI *)0x50, v11);
          v13 = v12;
          if ( v12 )
          {
            v14 = v20;
            v12[5] = 0;
            *((_BYTE *)v12 + 48) = 0;
            *((_DWORD *)v12 + 13) = 0;
            *v12 = &CSystemMSIDescriptor::`vftable';
            v12[3] = v14;
            LODWORD(v14) = v19;
            v12[4] = 0;
            v12[7] = 0;
            *((_DWORD *)v12 + 18) = (_DWORD)v14;
            v12[2] = v10;
            v7 = 0;
            if ( DPA_InsertPtr(*((HDPA *)this + 3), 0x7FFFFFFF, v12) == -1 )
            {
              v7 = -2147024882;
            }
            else
            {
              memset_0(&psfi, 0, sizeof(psfi));
              SHGetFileInfoW(&WindowName, 0, &psfi, 0x2B8u, 0x101u);
              *((_DWORD *)v13 + 2) = ImageList_ReplaceIcon(himl, -1, psfi.hIcon);
            }
          }
          else
          {
            SystemMSIComponent = 8;
          }
        }
        CoTaskMemFree(0);
        if ( v7 < 0 )
          break;
      }
      if ( SystemMSIComponent )
      {
        if ( SystemMSIComponent == 259 )
          return (unsigned int)v7;
        return (unsigned int)-2147467259;
      }
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003ea60  mov     [rsp-8+arg_18], rbx
0x18003ea65  push    rbp
0x18003ea66  push    rsi
0x18003ea67  push    rdi
0x18003ea68  push    r12
0x18003ea6a  push    r13
0x18003ea6c  push    r14
0x18003ea6e  push    r15
0x18003ea70  lea     rbp, [rsp-230h]
0x18003ea78  sub     rsp, 330h
0x18003ea7f  mov     rax, cs:__security_cookie
0x18003ea86  xor     rax, rsp
0x18003ea89  mov     [rbp+260h+var_40], rax
0x18003ea90  mov     r13, rcx
0x18003ea93  mov     [rsp+360h+himl], rdx
0x18003ea98  mov     ecx, 1; cItemGrow
0x18003ea9d  mov     r12, r8
0x18003eaa0  call    DPA_Create
0x18003eaa5  mov     [r13+18h], rax
0x18003eaa9  test    rax, rax
0x18003eaac  jz      loc_18003EC1A
0x18003eab2  xor     ebx, ebx
0x18003eab4  xor     r14d, r14d
0x18003eab7  lea     r8, [rsp+360h+pv]; unsigned __int16 **
0x18003eabc  mov     [rsp+360h+pv], 0
0x18003eac5  mov     edx, r14d; unsigned int
0x18003eac8  call    ?_GetSystemMSIComponent@CSystemMSIController@@AEAAKKPEAPEAG@Z
0x18003eacd  mov     edi, eax
0x18003eacf  test    eax, eax
0x18003ead1  jnz     loc_18003EC06
0x18003ead7  mov     r15, [rsp+360h+pv]
0x18003eadc  lea     r9, [rsp+360h+var_318]; unsigned __int16 **
0x18003eae1  mov     [rsp+360h+var_31C], eax
0x18003eae5  mov     r8, r15; unsigned __int16 *
0x18003eae8  mov     [rsp+360h+var_320], eax
0x18003eaec  mov     rdx, r12; void *
0x18003eaef  lea     rax, [rsp+360h+var_320]
0x18003eaf4  mov     [rsp+360h+var_318], 0
0x18003eafd  mov     [rsp+360h+var_328], rax; unsigned int *
0x18003eb02  lea     rax, [rsp+360h+var_31C]
0x18003eb07  mov     [rsp+360h+var_330], rax; int *
0x18003eb0c  call    ?_GetSystemMSIComponentInfo@CSystemMSIController@@AEAAKPEAXPEAGPEAPEAG22PEAHPEAK@Z
0x18003eb11  mov     edi, eax
0x18003eb13  test    eax, eax
0x18003eb15  jnz     loc_18003EBDE
0x18003eb1b  cmp     [rsp+360h+var_320], 1
0x18003eb20  jnz     loc_18003EBDE
0x18003eb26  lea     ecx, [rax+50h]; this
0x18003eb29  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z
0x18003eb2e  xor     edx, edx
0x18003eb30  mov     rsi, rax
0x18003eb33  test    rax, rax
0x18003eb36  jz      loc_18003EBD7
0x18003eb3c  mov     rcx, [rsp+360h+var_318]
0x18003eb41  mov     r8, rsi; p
0x18003eb44  mov     [rax+28h], rdx
0x18003eb48  mov     [rax+30h], dl
0x18003eb4b  mov     [rax+34h], edx
0x18003eb4e  lea     rax, ??_7CSystemMSIDescriptor@@6B@
0x18003eb55  mov     [rsi], rax
0x18003eb58  mov     [rsi+18h], rcx
0x18003eb5c  mov     ecx, [rsp+360h+var_31C]
0x18003eb60  mov     [rsi+20h], rdx
0x18003eb64  mov     [rsi+38h], rdx
0x18003eb68  mov     edx, 7FFFFFFFh; i
0x18003eb6d  mov     [rsi+48h], ecx
0x18003eb70  mov     [rsi+10h], r15
0x18003eb74  mov     rcx, [r13+18h]; hdpa
0x18003eb78  call    DPA_InsertPtr
0x18003eb7d  xor     ebx, ebx
0x18003eb7f  mov     ecx, 8007000Eh
0x18003eb84  cmp     eax, 0FFFFFFFFh
0x18003eb87  cmovz   ebx, ecx
0x18003eb8a  jz      short loc_18003EBFA
0x18003eb8c  mov     r15d, 2B8h
0x18003eb92  lea     rcx, [rsp+360h+psfi]; void *
0x18003eb97  mov     r8d, r15d; Size
0x18003eb9a  xor     edx, edx; Val
0x18003eb9c  call    memset_0
0x18003eba1  mov     r9d, r15d; cbFileInfo
0x18003eba4  mov     dword ptr [rsp+360h+uFlags], 101h; uFlags
0x18003ebac  lea     r8, [rsp+360h+psfi]; psfi
0x18003ebb1  xor     edx, edx; dwFileAttributes
0x18003ebb3  lea     rcx, WindowName; pszPath
0x18003ebba  call    cs:__imp_SHGetFileInfoW
0x18003ebc0  mov     r8, [rsp+360h+psfi.hIcon]; hicon
0x18003ebc5  or      edx, 0FFFFFFFFh; i
0x18003ebc8  mov     rcx, [rsp+360h+himl]; himl
0x18003ebcd  call    ImageList_ReplaceIcon
0x18003ebd2  mov     [rsi+8], eax
0x18003ebd5  jmp     short loc_18003EBFA
0x18003ebd7  mov     edi, 8
0x18003ebdc  jmp     short loc_18003EBFA
0x18003ebde  mov     rcx, r15; pv
0x18003ebe1  call    cs:__imp_CoTaskMemFree
0x18003ebe7  mov     rcx, [rsp+360h+var_318]; pv
0x18003ebec  call    cs:__imp_CoTaskMemFree
0x18003ebf2  xor     ecx, ecx; pv
0x18003ebf4  call    cs:__imp_CoTaskMemFree
0x18003ebfa  xor     ecx, ecx; pv
0x18003ebfc  call    cs:__imp_CoTaskMemFree
0x18003ec02  test    ebx, ebx
0x18003ec04  js      short loc_18003EC1F
0x18003ec06  test    edi, edi
0x18003ec08  jnz     short loc_18003EC12
0x18003ec0a  inc     r14d
0x18003ec0d  jmp     loc_18003EAB7
0x18003ec12  cmp     edi, 103h
0x18003ec18  jz      short loc_18003EC1F
0x18003ec1a  mov     ebx, 80004005h
0x18003ec1f  mov     eax, ebx
0x18003ec21  mov     rcx, [rbp+260h+var_40]
0x18003ec28  xor     rcx, rsp; StackCookie
0x18003ec2b  call    __security_check_cookie
0x18003ec30  mov     rbx, [rsp+360h+arg_18]
0x18003ec38  add     rsp, 330h
0x18003ec3f  pop     r15
0x18003ec41  pop     r14
0x18003ec43  pop     r13
0x18003ec45  pop     r12
0x18003ec47  pop     rdi
0x18003ec48  pop     rsi
0x18003ec49  pop     rbp
0x18003ec4a  retn
```
