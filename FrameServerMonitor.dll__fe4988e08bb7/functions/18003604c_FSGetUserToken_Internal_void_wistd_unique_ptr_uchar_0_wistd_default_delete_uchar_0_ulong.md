# FSGetUserToken_Internal(void *,wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &,ulong &)

- ea: `0x18003604c`
- end: `0x18003615e`
- name: `?FSGetUserToken_Internal@@YAJPEAXAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@AEAK@Z`
- size: `274`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPVOID *, DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180035f40`

## callees

- `0x1800060f8`
- `0x180006a98`
- `0x180006cc0`
- `0x18000723c`
- `0x18000d1e0`
- `0x18003604c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003610e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003610e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003607b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180036104`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003607b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180036104`

## pseudocode

```c
__int64 __fastcall FSGetUserToken_Internal(HANDLE TokenHandle, LPVOID *a2, DWORD *a3)
{
  signed int v6; // ebx
  signed int LastError; // eax
  __int64 v8; // rdx
  const struct std::nothrow_t *unique; // rax
  int v10; // r8d
  signed int v11; // eax
  __int64 v13; // [rsp+70h] [rbp+18h] BYREF

  v6 = 0;
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(a2);
  *a3 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, a3) )
    goto LABEL_9;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError != -2147024774 )
    v6 = LastError;
  if ( v6 >= 0 )
  {
LABEL_9:
    unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v13, *a3);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(a2, unique);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v13);
    if ( *a2 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenUser, *a2, *a3, a3) )
      {
        v11 = GetLastError();
        v6 = v11;
        if ( v11 > 0 )
          v6 = (unsigned __int16)v11 | 0x80070000;
        if ( v6 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v8 = 35;
          goto LABEL_18;
        }
      }
    }
    else
    {
      v6 = -2147024882;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v8 = (unsigned int)(v10 + 34);
        goto LABEL_18;
      }
    }
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() >= 8u )
  {
    v8 = 33;
LABEL_18:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003604c  push    rbx
0x18003604e  push    rbp
0x18003604f  push    rsi
0x180036050  push    rdi
0x180036051  sub     rsp, 38h
0x180036055  mov     rbp, rcx
0x180036058  mov     rdi, r8
0x18003605b  mov     rcx, rdx
0x18003605e  mov     rsi, rdx
0x180036061  xor     ebx, ebx
0x180036063  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180036068  xor     r9d, r9d; TokenInformationLength
0x18003606b  mov     [rdi], ebx
0x18003606d  xor     r8d, r8d; TokenInformation
0x180036070  mov     [rsp+58h+ReturnLength], rdi; ReturnLength
0x180036075  lea     edx, [rbx+1]; TokenInformationClass
0x180036078  mov     rcx, rbp; TokenHandle
0x18003607b  call    cs:__imp_GetTokenInformation
0x180036081  test    eax, eax
0x180036083  jnz     short loc_1800360B7
0x180036085  call    cs:__imp_GetLastError
0x18003608b  test    eax, eax
0x18003608d  jle     short loc_180036097
0x18003608f  movzx   eax, ax
0x180036092  or      eax, 80070000h
0x180036097  cmp     eax, 8007007Ah
0x18003609c  cmovnz  ebx, eax
0x18003609f  test    ebx, ebx
0x1800360a1  jns     short loc_1800360B7
0x1800360a3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800360a8  cmp     al, 8
0x1800360aa  jb      loc_180036153
0x1800360b0  mov     edx, 21h ; '!'
0x1800360b5  jmp     short loc_180036135
0x1800360b7  mov     edx, [rdi]
0x1800360b9  lea     rcx, [rsp+58h+arg_10]
0x1800360be  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x1800360c3  mov     rdx, rax
0x1800360c6  mov     rcx, rsi
0x1800360c9  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x1800360ce  lea     rcx, [rsp+58h+arg_10]
0x1800360d3  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x1800360d8  mov     r8, [rsi]; TokenInformation
0x1800360db  test    r8, r8
0x1800360de  jnz     short loc_1800360F4
0x1800360e0  mov     ebx, 8007000Eh
0x1800360e5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800360ea  cmp     al, 1
0x1800360ec  jb      short loc_180036153
0x1800360ee  lea     edx, [r8+22h]
0x1800360f2  jmp     short loc_180036135
0x1800360f4  mov     r9d, [rdi]; TokenInformationLength
0x1800360f7  mov     edx, 1; TokenInformationClass
0x1800360fc  mov     rcx, rbp; TokenHandle
0x1800360ff  mov     [rsp+58h+ReturnLength], rdi; ReturnLength
0x180036104  call    cs:__imp_GetTokenInformation
0x18003610a  test    eax, eax
0x18003610c  jnz     short loc_180036153
0x18003610e  call    cs:__imp_GetLastError
0x180036114  mov     ebx, eax
0x180036116  test    eax, eax
0x180036118  jle     short loc_180036123
0x18003611a  movzx   ebx, ax
0x18003611d  or      ebx, 80070000h
0x180036123  test    ebx, ebx
0x180036125  jns     short loc_180036153
0x180036127  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003612c  cmp     al, 1
0x18003612e  jb      short loc_180036153
0x180036130  mov     edx, 23h ; '#'
0x180036135  mov     rcx, cs:WPP_GLOBAL_Control
0x18003613c  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180036143  xor     r9d, r9d
0x180036146  mov     dword ptr [rsp+58h+ReturnLength], ebx
0x18003614a  mov     rcx, [rcx+10h]
0x18003614e  call    WPP_SF_qD
0x180036153  mov     eax, ebx
0x180036155  add     rsp, 38h
0x180036159  pop     rdi
0x18003615a  pop     rsi
0x18003615b  pop     rbp
0x18003615c  pop     rbx
0x18003615d  retn
```
