# JobHelper::GetDownloadLocation(_Job &)

- ea: `0x140018e48`
- end: `0x14001904c`
- name: `?GetDownloadLocation@JobHelper@@SAJAEAU_Job@@@Z`
- size: `516`
- prototype: `__int64 __fastcall(struct _Job *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x14000d898`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x14000740c`
- `0x140009598`
- `0x140011c90`
- `0x140011d58`
- `0x14001668c`
- `0x1400168b4`
- `0x140018e48`
- `0x140019fcc`
- `0x14001a8d0`

## import_xrefs

- `ole32!CoCreateGuid` at `0x140018f67`
- `ole32!CoCreateGuid` at `0x140018f67`
- `ole32!StringFromGUID2` at `0x140018fdb`
- `ole32!StringFromGUID2` at `0x140018fdb`

## pseudocode

```c
__int64 __fastcall JobHelper::GetDownloadLocation(struct _Job *a1)
{
  struct _Job *v1; // rbx
  char v2; // r14
  char *v3; // r15
  int MdmTempFolder; // edi
  __int64 v5; // rdx
  bool v6; // di
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v10; // rax
  __int64 v11; // rdx
  _WORD v12[8]; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h]
  __int64 v14; // [rsp+40h] [rbp-C0h]
  GUID pguid; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR v16[8]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v17; // [rsp+78h] [rbp-88h]
  __int64 v18; // [rsp+80h] [rbp-80h]
  _BYTE v19[40]; // [rsp+88h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+B0h] [rbp-50h] BYREF

  v1 = a1;
  v2 = 0;
  v18 = 7;
  v17 = 0;
  v16[0] = 0;
  v3 = (char *)a1 + 32;
  MdmTempFolder = GetMdmTempFolder((__int64)a1 + 32, *((_DWORD *)a1 + 16), v16);
  if ( MdmTempFolder < 0 )
    goto LABEL_13;
  std::wstring::operator=((char *)v1 + 200, v16);
  std::wstring::append((char *)v1 + 200, L"\\");
  v14 = 7;
  v13 = 0;
  v12[0] = 0;
  v6 = 0;
  if ( *((_BYTE *)v1 + 388) )
  {
    std::wstring::wstring(&pguid, L"PackageName");
    v2 = 1;
    if ( (int)GetProductInfoFromMsi((LPCWSTR)v1 + 36, (LPCWSTR)&pguid) >= 0 )
      v6 = 1;
  }
  if ( (v2 & 1) != 0 )
  {
    LOBYTE(v5) = 1;
    std::wstring::_Tidy(&pguid, v5, 0);
  }
  if ( v6 )
  {
    std::wstring::append((char *)v1 + 200, v12, 0, -1);
    goto LABEL_18;
  }
  pguid = 0;
  MdmTempFolder = CoCreateGuid(&pguid);
  if ( MdmTempFolder >= 0 )
  {
    StringFromGUID2(&pguid, sz, 39);
    v10 = std::wstring::wstring(v19, sz);
    std::wstring::append((char *)v1 + 200, v10, 0, -1);
    LOBYTE(v11) = 1;
    std::wstring::_Tidy(v19, v11, 0);
    std::wstring::append((char *)v1 + 200, L".msi");
LABEL_18:
    MdmTempFolder = JobHelper::UpdateDownloadLocation(v1, v3, (char *)v1 + 200);
    LOBYTE(v7) = 1;
    if ( MdmTempFolder >= 0 )
    {
      std::wstring::_Tidy(v12, v7, 0);
      goto LABEL_16;
    }
    goto LABEL_12;
  }
  LOBYTE(v7) = 1;
LABEL_12:
  std::wstring::_Tidy(v12, v7, 0);
LABEL_13:
  if ( *((_QWORD *)v1 + 3) >= 8u )
    v1 = *(struct _Job **)v1;
  LogError(L"GetDownloadLocation failed for job %1. Error = 0x%2!x!.", v1, (unsigned int)MdmTempFolder);
LABEL_16:
  LOBYTE(v8) = 1;
  std::wstring::_Tidy(v16, v8, 0);
  return (unsigned int)MdmTempFolder;
}

```

## disassembly

```asm
0x140018e48  push    rbp
0x140018e4a  push    rbx
0x140018e4b  push    rsi
0x140018e4c  push    rdi
0x140018e4d  push    r14
0x140018e4f  push    r15
0x140018e51  lea     rbp, [rsp-18h]
0x140018e56  sub     rsp, 118h
0x140018e5d  mov     rax, cs:__security_cookie
0x140018e64  xor     rax, rsp
0x140018e67  mov     [rbp+40h+var_40], rax
0x140018e6b  mov     rbx, rcx
0x140018e6e  xor     r14d, r14d
0x140018e71  mov     [rsp+140h+var_120], r14d
0x140018e76  mov     [rbp+40h+var_C0], 7
0x140018e7e  mov     [rsp+140h+var_C8], r14
0x140018e83  xor     eax, eax
0x140018e85  mov     [rsp+140h+var_D8], ax
0x140018e8a  lea     r15, [rcx+20h]
0x140018e8e  lea     r8, [rsp+140h+var_D8]
0x140018e93  mov     edx, [rcx+40h]
0x140018e96  mov     rcx, r15
0x140018e99  call    ?GetMdmTempFolder@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEAV12@@Z; GetMdmTempFolder(std::wstring const &,ulong,std::wstring &)
0x140018e9e  mov     edi, eax
0x140018ea0  test    eax, eax
0x140018ea2  js      loc_140018F82
0x140018ea8  lea     rsi, [rbx+0C8h]
0x140018eaf  lea     rdx, [rsp+140h+var_D8]
0x140018eb4  mov     rcx, rsi
0x140018eb7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140018ebc  lea     rdx, asc_140020C3C; "\\"
0x140018ec3  mov     rcx, rsi
0x140018ec6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x140018ecb  mov     [rsp+140h+var_100], 7
0x140018ed4  mov     [rsp+140h+var_108], r14
0x140018ed9  xor     eax, eax
0x140018edb  mov     [rsp+140h+var_118], ax
0x140018ee0  cmp     [rbx+184h], al
0x140018ee6  jz      short loc_140018F24
0x140018ee8  lea     rdx, aPackagename; "PackageName"
0x140018eef  lea     rcx, [rsp+140h+pguid]
0x140018ef4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140018ef9  nop
0x140018efa  mov     r14d, 1
0x140018f00  mov     [rsp+140h+var_120], r14d
0x140018f05  lea     rcx, [rbx+48h]; szProduct
0x140018f09  mov     r9, r15
0x140018f0c  lea     r8, [rsp+140h+var_118]
0x140018f11  lea     rdx, [rsp+140h+pguid]; szAttribute
0x140018f16  call    ?GetProductInfoFromMsi@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV12@0@Z; GetProductInfoFromMsi(std::wstring const &,std::wstring const &,std::wstring &,std::wstring const &)
0x140018f1b  test    eax, eax
0x140018f1d  js      short loc_140018F24
0x140018f1f  mov     dil, r14b
0x140018f22  jmp     short loc_140018F27
0x140018f24  xor     dil, dil
0x140018f27  test    r14b, 1
0x140018f2b  jz      short loc_140018F3C
0x140018f2d  xor     r8d, r8d
0x140018f30  mov     dl, 1
0x140018f32  lea     rcx, [rsp+140h+pguid]
0x140018f37  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140018f3c  test    dil, dil
0x140018f3f  jz      short loc_140018F5A
0x140018f41  or      r9, 0FFFFFFFFFFFFFFFFh
0x140018f45  xor     r8d, r8d
0x140018f48  lea     rdx, [rsp+140h+var_118]
0x140018f4d  mov     rcx, rsi
0x140018f50  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x140018f55  jmp     loc_14001901F
0x140018f5a  xorps   xmm0, xmm0
0x140018f5d  movups  xmmword ptr [rsp+140h+pguid.Data1], xmm0
0x140018f62  lea     rcx, [rsp+140h+pguid]; pguid
0x140018f67  call    cs:__imp_CoCreateGuid
0x140018f6d  mov     edi, eax
0x140018f6f  test    eax, eax
0x140018f71  jns     short loc_140018FCC
0x140018f73  xor     r8d, r8d
0x140018f76  mov     dl, 1
0x140018f78  lea     rcx, [rsp+140h+var_118]
0x140018f7d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140018f82  cmp     qword ptr [rbx+18h], 8
0x140018f87  jb      short loc_140018F8C
0x140018f89  mov     rbx, [rbx]
0x140018f8c  mov     r8d, edi
0x140018f8f  mov     rdx, rbx
0x140018f92  lea     rcx, aGetdownloadloc; "GetDownloadLocation failed for job %1. "...
0x140018f99  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140018f9e  nop
0x140018f9f  xor     r8d, r8d
0x140018fa2  mov     dl, 1
0x140018fa4  lea     rcx, [rsp+140h+var_D8]
0x140018fa9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140018fae  mov     eax, edi
0x140018fb0  mov     rcx, [rbp+40h+var_40]
0x140018fb4  xor     rcx, rsp; StackCookie
0x140018fb7  call    __security_check_cookie
0x140018fbc  add     rsp, 118h
0x140018fc3  pop     r15
0x140018fc5  pop     r14
0x140018fc7  pop     rdi
0x140018fc8  pop     rsi
0x140018fc9  pop     rbx
0x140018fca  pop     rbp
0x140018fcb  retn
0x140018fcc  mov     r8d, 27h ; '''; cchMax
0x140018fd2  lea     rdx, [rbp+40h+sz]; lpsz
0x140018fd6  lea     rcx, [rsp+140h+pguid]; rguid
0x140018fdb  call    cs:__imp_StringFromGUID2
0x140018fe1  lea     rdx, [rbp+40h+sz]
0x140018fe5  lea     rcx, [rbp+40h+var_B8]
0x140018fe9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140018fee  nop
0x140018fef  or      r9, 0FFFFFFFFFFFFFFFFh
0x140018ff3  xor     r8d, r8d
0x140018ff6  mov     rdx, rax
0x140018ff9  mov     rcx, rsi
0x140018ffc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x140019001  nop
0x140019002  xor     r8d, r8d
0x140019005  mov     dl, 1
0x140019007  lea     rcx, [rbp+40h+var_B8]
0x14001900b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140019010  lea     rdx, aMsi; ".msi"
0x140019017  mov     rcx, rsi
0x14001901a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14001901f  mov     r8, rsi
0x140019022  mov     rdx, r15
0x140019025  mov     rcx, rbx
0x140019028  call    ?UpdateDownloadLocation@JobHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@0@Z; JobHelper::UpdateDownloadLocation(std::wstring const &,std::wstring &,std::wstring const &)
0x14001902d  mov     edi, eax
0x14001902f  xor     r8d, r8d
0x140019032  mov     dl, 1
0x140019034  lea     rcx, [rsp+140h+var_118]
0x140019039  test    eax, eax
0x14001903b  js      loc_140018F7D
0x140019041  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140019046  jmp     loc_140018F9F
```
