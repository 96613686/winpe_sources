# CIMRequestRAEvent::GetKeyExportString(unsigned __int64,unsigned __int64,ulong,ushort * *,ulong *)

- ea: `0x140014388`
- end: `0x140014502`
- name: `?GetKeyExportString@CIMRequestRAEvent@@QEAAJ_K0KPEAPEAGPEAK@Z`
- size: `378`
- prototype: `__int64 __fastcall(CIMRequestRAEvent *this, const struct _EVENT_DESCRIPTOR *, HCRYPTKEY, DWORD, unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140013ef8`
- `0x140014ccc`

## callees

- `0x140013a88`
- `0x140014388`
- `0x140015240`

## import_xrefs

- `ADVAPI32!CryptExportKey` at `0x140014407`
- `ADVAPI32!CryptExportKey` at `0x140014477`
- `ADVAPI32!CryptExportKey` at `0x140014407`
- `ADVAPI32!CryptExportKey` at `0x140014477`
- `KERNEL32!GetLastError` at `0x140014411`
- `KERNEL32!GetLastError` at `0x140014481`
- `KERNEL32!GetLastError` at `0x140014411`
- `KERNEL32!GetLastError` at `0x140014481`
- `msvcrt!malloc` at `0x140014436`
- `msvcrt!malloc` at `0x140014436`
- `msvcrt!free` at `0x1400144e7`
- `msvcrt!free` at `0x1400144e7`

## string_xrefs

- `0x1400143d2`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`
- `0x1400144d3`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`

## pseudocode

```c
__int64 __fastcall CIMRequestRAEvent::GetKeyExportString(
        CIMRequestRAEvent *this,
        const struct _EVENT_DESCRIPTOR *a2,
        HCRYPTKEY a3,
        DWORD a4,
        unsigned __int16 **a5,
        unsigned int *a6)
{
  unsigned __int16 **v6; // rbx
  unsigned int v10; // ebx
  signed int v11; // eax
  const struct _EVENT_DESCRIPTOR *v12; // rdx
  CEventLogger *v13; // rcx
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  CEventLogger *v15; // rcx
  unsigned __int8 *pbData; // rdi
  CIMRequestRAEvent *v17; // rcx
  signed int LastError; // eax
  const struct _EVENT_DESCRIPTOR *v19; // rdx
  CEventLogger *v20; // rcx
  signed int v21; // eax
  const struct _EVENT_DESCRIPTOR *v22; // rdx
  CEventLogger *v23; // rcx
  DWORD pdwDataLen; // [rsp+50h] [rbp+8h] BYREF
  int v26; // [rsp+54h] [rbp+Ch]

  v26 = HIDWORD(this);
  v6 = a5;
  pdwDataLen = 0;
  if ( a5 )
  {
    if ( CryptExportKey((HCRYPTKEY)a2, a3, a4, 0, 0, &pdwDataLen) )
    {
      pbData = (unsigned __int8 *)malloc(pdwDataLen);
      if ( pbData )
      {
        if ( CryptExportKey((HCRYPTKEY)a2, a3, a4, 0, pbData, &pdwDataLen) )
        {
          v21 = CIMRequestRAEvent::BinaryToString(v17, pbData, pdwDataLen, v6, a6);
          v10 = v21;
          if ( v21 < 0 )
            CEventLogger::LogError(
              v23,
              v22,
              L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
              0x13Fu,
              L"CIMRequestRAEvent::GetKeyExportString",
              v21);
        }
        else
        {
          LastError = GetLastError();
          v10 = LastError;
          if ( LastError > 0 )
            v10 = (unsigned __int16)LastError | 0x80070000;
          CEventLogger::LogError(
            v20,
            v19,
            L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
            0x136u,
            L"CIMRequestRAEvent::GetKeyExportString",
            v10);
        }
        free(pbData);
      }
      else
      {
        v10 = -2147024882;
        CEventLogger::LogError(
          v15,
          v14,
          L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
          0x127u,
          L"CIMRequestRAEvent::GetKeyExportString",
          0x8007000E);
      }
    }
    else
    {
      v11 = GetLastError();
      v10 = v11;
      if ( v11 > 0 )
        v10 = (unsigned __int16)v11 | 0x80070000;
      CEventLogger::LogError(
        v13,
        v12,
        L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
        0x120u,
        L"CIMRequestRAEvent::GetKeyExportString",
        v10);
    }
  }
  else
  {
    v10 = -2147024809;
    CEventLogger::LogError(
      this,
      a2,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      0x10Du,
      L"CIMRequestRAEvent::GetKeyExportString",
      0x80070057);
  }
  return v10;
}

```

## disassembly

```asm
0x140014388  mov     rax, rsp
0x14001438b  mov     [rax+10h], rbx
0x14001438f  mov     [rax+18h], rbp
0x140014393  mov     [rax+8], rcx
0x140014397  push    rsi
0x140014398  push    rdi
0x140014399  push    r14
0x14001439b  sub     rsp, 30h
0x14001439f  mov     rbx, [rsp+48h+arg_20]
0x1400143a4  mov     esi, r9d
0x1400143a7  mov     dword ptr [rax+8], 0
0x1400143ae  mov     rbp, r8
0x1400143b1  mov     r14, rdx
0x1400143b4  test    rbx, rbx
0x1400143b7  jnz     short loc_1400143E8
0x1400143b9  mov     ebx, 80070057h
0x1400143be  mov     dword ptr [rax-20h], 80070057h
0x1400143c5  mov     r9d, 10Dh; unsigned int
0x1400143cb  lea     rax, aCimrequestraev_8; "CIMRequestRAEvent::GetKeyExportString"
0x1400143d2  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x1400143d9  mov     [rsp+48h+pbData], rax; unsigned __int16 *
0x1400143de  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400143e3  jmp     loc_1400144ED
0x1400143e8  lea     rax, [rsp+48h+arg_0]
0x1400143ed  xor     r9d, r9d; dwFlags
0x1400143f0  mov     [rsp+48h+pdwDataLen], rax; pdwDataLen
0x1400143f5  mov     r8d, esi; dwBlobType
0x1400143f8  mov     rdx, rbp; hExpKey
0x1400143fb  mov     [rsp+48h+pbData], 0; pbData
0x140014404  mov     rcx, r14; hKey
0x140014407  call    cs:__imp_CryptExportKey
0x14001440d  test    eax, eax
0x14001440f  jnz     short loc_140014432
0x140014411  call    cs:__imp_GetLastError
0x140014417  mov     ebx, eax
0x140014419  test    eax, eax
0x14001441b  jle     short loc_140014426
0x14001441d  movzx   ebx, ax
0x140014420  or      ebx, 80070000h
0x140014426  mov     dword ptr [rsp+48h+pdwDataLen], ebx
0x14001442a  mov     r9d, 120h
0x140014430  jmp     short loc_1400143CB
0x140014432  mov     ecx, [rsp+48h+arg_0]; Size
0x140014436  call    cs:__imp_malloc
0x14001443c  mov     rdi, rax
0x14001443f  test    rax, rax
0x140014442  jnz     short loc_14001445C
0x140014444  mov     ebx, 8007000Eh
0x140014449  mov     dword ptr [rsp+48h+pdwDataLen], 8007000Eh
0x140014451  mov     r9d, 127h
0x140014457  jmp     loc_1400143CB
0x14001445c  lea     rax, [rsp+48h+arg_0]
0x140014461  xor     r9d, r9d; dwFlags
0x140014464  mov     [rsp+48h+pdwDataLen], rax; pdwDataLen
0x140014469  mov     r8d, esi; dwBlobType
0x14001446c  mov     rdx, rbp; hExpKey
0x14001446f  mov     [rsp+48h+pbData], rdi; pbData
0x140014474  mov     rcx, r14; hKey
0x140014477  call    cs:__imp_CryptExportKey
0x14001447d  test    eax, eax
0x14001447f  jnz     short loc_1400144A2
0x140014481  call    cs:__imp_GetLastError
0x140014487  mov     ebx, eax
0x140014489  test    eax, eax
0x14001448b  jle     short loc_140014496
0x14001448d  movzx   ebx, ax
0x140014490  or      ebx, 80070000h
0x140014496  mov     dword ptr [rsp+48h+pdwDataLen], ebx
0x14001449a  mov     r9d, 136h
0x1400144a0  jmp     short loc_1400144CC
0x1400144a2  mov     rax, [rsp+48h+arg_28]
0x1400144a7  mov     r9, rbx; unsigned __int16 **
0x1400144aa  mov     r8d, [rsp+48h+arg_0]; unsigned int
0x1400144af  mov     rdx, rdi; unsigned __int8 *
0x1400144b2  mov     [rsp+48h+pbData], rax; unsigned int *
0x1400144b7  call    ?BinaryToString@CIMRequestRAEvent@@QEAAJPEAEKPEAPEAGPEAK@Z; CIMRequestRAEvent::BinaryToString(uchar *,ulong,ushort * *,ulong *)
0x1400144bc  mov     ebx, eax
0x1400144be  test    eax, eax
0x1400144c0  jns     short loc_1400144E4
0x1400144c2  mov     dword ptr [rsp+48h+pdwDataLen], eax; unsigned int
0x1400144c6  mov     r9d, 13Fh; unsigned int
0x1400144cc  lea     rax, aCimrequestraev_8; "CIMRequestRAEvent::GetKeyExportString"
0x1400144d3  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x1400144da  mov     [rsp+48h+pbData], rax; unsigned __int16 *
0x1400144df  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400144e4  mov     rcx, rdi; Block
0x1400144e7  call    cs:__imp_free
0x1400144ed  mov     rbp, [rsp+48h+arg_10]
0x1400144f2  mov     eax, ebx
0x1400144f4  mov     rbx, [rsp+48h+arg_8]
0x1400144f9  add     rsp, 30h
0x1400144fd  pop     r14
0x1400144ff  pop     rdi
0x140014500  pop     rsi
0x140014501  retn
```
