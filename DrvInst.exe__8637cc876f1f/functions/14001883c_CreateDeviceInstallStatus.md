# CreateDeviceInstallStatus

- ea: `0x14001883c`
- end: `0x140018b2f`
- name: `CreateDeviceInstallStatus`
- size: `755`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140018dc0`

## callees

- `0x1400070bc`
- `0x14000bcbc`
- `0x14000c354`
- `0x14001883c`
- `0x140024944`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400188d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400188d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140018b05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140018b05`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001889d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001889d`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x1400189b7`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140018a0b`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140018a5f`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140018ab3`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x1400189b7`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140018a0b`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140018a5f`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140018ab3`
- `drvstore!DriverStoreOpenW` at `0x1400188ca`
- `drvstore!DriverStoreOpenW` at `0x1400188ca`
- `drvstore!DriverStoreClose` at `0x140018afd`
- `drvstore!DriverStoreClose` at `0x140018afd`

## pseudocode

```c
_WORD *__fastcall CreateDeviceInstallStatus(int a1, size_t *a2, size_t *a3, unsigned __int16 *a4)
{
  _WORD *v8; // rax
  _WORD *v9; // rbx
  DWORD LastError; // edi
  __int64 v11; // r14
  _WORD *v12; // r11
  __int64 FileTitle; // r12
  unsigned __int16 v15[264]; // [rsp+70h] [rbp-90h] BYREF

  v8 = LocalAlloc(0x40u, 0xBB0u);
  v9 = v8;
  if ( v8 )
  {
    memset_0(v8, 0, 0xBB0u);
    v11 = DriverStoreOpenW(0, 0, 0, 0);
    if ( v11 )
    {
      *(_DWORD *)v9 = a1;
      if ( (int)StringCchCopyW(v9 + 2, 0xC8u, a2) < 0 )
        v9[2] = 0;
      if ( a3 && a4 )
      {
        LastError = 0;
        if ( (int)StringCchCopyW(v9 + 462, 0x104u, a3) < 0 )
          *v12 = 0;
        *((_QWORD *)v9 + 181) = a4;
        if ( (int)StringCchCopyW(v15, 0x104u, a3) >= 0 && (unsigned int)pSetupTrimFileTitle(v15) )
        {
          FileTitle = pSetupGetFileTitle(v15);
          DriverStoreGetObjectPropertyW(v11, 2, FileTitle, DEVPKEY_DriverPackage_DriverDate);
          *((_QWORD *)v9 + 184) = 0;
          DriverStoreGetObjectPropertyW(v11, 2, FileTitle, DEVPKEY_DriverPackage_DriverVersion);
          *((_QWORD *)v9 + 185) = 0;
          DriverStoreGetObjectPropertyW(v11, 2, FileTitle, DEVPKEY_DriverPackage_ProviderName);
          v9[744] = 0;
          DriverStoreGetObjectPropertyW(v11, 2, FileTitle, DEVPKEY_DriverPackage_ClassGuid);
          *((_OWORD *)v9 + 91) = 0;
        }
        DrvUtilsEnumDriversFromStrongNames(a4);
      }
      else
      {
        *((_DWORD *)v9 + 732) = 1;
        LastError = 0;
      }
      DriverStoreClose(v11);
    }
    else
    {
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = 8;
  }
  SetLastError(LastError);
  return v9;
}

```

## disassembly

```asm
0x14001883c  push    rbp
0x14001883e  push    rbx
0x14001883f  push    rsi
0x140018840  push    rdi
0x140018841  push    r12
0x140018843  push    r14
0x140018845  push    r15
0x140018847  lea     rbp, [rsp-190h]
0x14001884f  sub     rsp, 290h
0x140018856  mov     rax, cs:__security_cookie
0x14001885d  xor     rax, rsp
0x140018860  mov     [rbp+1C0h+var_40], rax
0x140018867  xor     eax, eax
0x140018869  mov     [rsp+2C0h+var_270], 0
0x140018871  mov     r12, rdx
0x140018874  mov     [rsp+2C0h+var_26C], 0
0x14001887c  mov     edi, ecx
0x14001887e  mov     [rsp+2C0h+var_258], rax
0x140018883  xorps   xmm0, xmm0
0x140018886  mov     r14d, 0BB0h
0x14001888c  lea     ecx, [rax+40h]; uFlags
0x14001888f  mov     edx, r14d; uBytes
0x140018892  mov     r15, r9
0x140018895  mov     rsi, r8
0x140018898  movups  [rsp+2C0h+var_268], xmm0
0x14001889d  call    cs:__imp_LocalAlloc
0x1400188a3  mov     rbx, rax
0x1400188a6  test    rax, rax
0x1400188a9  jnz     short loc_1400188B3
0x1400188ab  lea     edi, [rax+8]
0x1400188ae  jmp     loc_140018B03
0x1400188b3  mov     r8, r14; Size
0x1400188b6  xor     edx, edx; Val
0x1400188b8  mov     rcx, rbx; void *
0x1400188bb  call    memset_0
0x1400188c0  xor     r9d, r9d
0x1400188c3  xor     r8d, r8d
0x1400188c6  xor     edx, edx
0x1400188c8  xor     ecx, ecx
0x1400188ca  call    cs:__imp_DriverStoreOpenW
0x1400188d0  mov     r14, rax
0x1400188d3  test    rax, rax
0x1400188d6  jnz     short loc_1400188E5
0x1400188d8  call    cs:__imp_GetLastError
0x1400188de  mov     edi, eax
0x1400188e0  jmp     loc_140018B03
0x1400188e5  mov     r8, r12; unsigned __int16 *
0x1400188e8  mov     [rbx], edi
0x1400188ea  mov     edx, 0C8h; unsigned __int64
0x1400188ef  lea     rcx, [rbx+4]; unsigned __int16 *
0x1400188f3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400188f8  test    eax, eax
0x1400188fa  jns     short loc_140018902
0x1400188fc  xor     eax, eax
0x1400188fe  mov     [rbx+4], ax
0x140018902  test    rsi, rsi
0x140018905  jz      loc_140018AEE
0x14001890b  test    r15, r15
0x14001890e  jz      loc_140018AEE
0x140018914  lea     r11, [rbx+39Ch]
0x14001891b  mov     r12d, 104h
0x140018921  mov     edx, r12d; unsigned __int64
0x140018924  mov     rcx, r11; unsigned __int16 *
0x140018927  mov     r8, rsi; unsigned __int16 *
0x14001892a  xor     edi, edi
0x14001892c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140018931  test    eax, eax
0x140018933  jns     short loc_14001893B
0x140018935  xor     eax, eax
0x140018937  mov     [r11], ax
0x14001893b  mov     r8, rsi; unsigned __int16 *
0x14001893e  mov     [rbx+5A8h], r15
0x140018945  mov     rdx, r12; unsigned __int64
0x140018948  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x14001894d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140018952  test    eax, eax
0x140018954  js      loc_140018ACA
0x14001895a  lea     rcx, [rsp+2C0h+var_250]
0x14001895f  call    pSetupTrimFileTitle
0x140018964  test    eax, eax
0x140018966  jz      loc_140018ACA
0x14001896c  lea     rcx, [rsp+2C0h+var_250]
0x140018971  call    pSetupGetFileTitle
0x140018976  mov     r12, rax
0x140018979  mov     [rsp+2C0h+var_280], edi
0x14001897d  lea     rax, [rsp+2C0h+var_26C]
0x140018982  mov     r8, r12
0x140018985  mov     [rsp+2C0h+var_288], rax
0x14001898a  lea     rsi, [rbx+5C0h]
0x140018991  mov     [rsp+2C0h+var_290], 8
0x140018999  lea     rax, [rsp+2C0h+var_270]
0x14001899e  mov     [rsp+2C0h+var_298], rsi
0x1400189a3  lea     r9, DEVPKEY_DriverPackage_DriverDate
0x1400189aa  mov     edx, 2
0x1400189af  mov     [rsp+2C0h+var_2A0], rax
0x1400189b4  mov     rcx, r14
0x1400189b7  call    cs:__imp_DriverStoreGetObjectPropertyW
0x1400189bd  test    eax, eax
0x1400189bf  jz      short loc_1400189C8
0x1400189c1  cmp     [rsp+2C0h+var_270], 10h
0x1400189c6  jz      short loc_1400189CD
0x1400189c8  xor     eax, eax
0x1400189ca  mov     [rsi], rax
0x1400189cd  mov     [rsp+2C0h+var_280], edi
0x1400189d1  lea     rax, [rsp+2C0h+var_26C]
0x1400189d6  mov     [rsp+2C0h+var_288], rax
0x1400189db  lea     rsi, [rbx+5C8h]
0x1400189e2  mov     [rsp+2C0h+var_290], 8
0x1400189ea  lea     rax, [rsp+2C0h+var_270]
0x1400189ef  mov     [rsp+2C0h+var_298], rsi
0x1400189f4  lea     r9, DEVPKEY_DriverPackage_DriverVersion
0x1400189fb  mov     r8, r12
0x1400189fe  mov     [rsp+2C0h+var_2A0], rax
0x140018a03  mov     edx, 2
0x140018a08  mov     rcx, r14
0x140018a0b  call    cs:__imp_DriverStoreGetObjectPropertyW
0x140018a11  test    eax, eax
0x140018a13  jz      short loc_140018A1C
0x140018a15  cmp     [rsp+2C0h+var_270], 9
0x140018a1a  jz      short loc_140018A21
0x140018a1c  xor     eax, eax
0x140018a1e  mov     [rsi], rax
0x140018a21  mov     [rsp+2C0h+var_280], edi
0x140018a25  lea     rax, [rsp+2C0h+var_26C]
0x140018a2a  mov     [rsp+2C0h+var_288], rax
0x140018a2f  lea     rsi, [rbx+5D0h]
0x140018a36  mov     [rsp+2C0h+var_290], 208h
0x140018a3e  lea     rax, [rsp+2C0h+var_270]
0x140018a43  mov     [rsp+2C0h+var_298], rsi
0x140018a48  lea     r9, DEVPKEY_DriverPackage_ProviderName
0x140018a4f  mov     r8, r12
0x140018a52  mov     [rsp+2C0h+var_2A0], rax
0x140018a57  mov     edx, 2
0x140018a5c  mov     rcx, r14
0x140018a5f  call    cs:__imp_DriverStoreGetObjectPropertyW
0x140018a65  test    eax, eax
0x140018a67  jz      short loc_140018A70
0x140018a69  cmp     [rsp+2C0h+var_270], 12h
0x140018a6e  jz      short loc_140018A75
0x140018a70  xor     eax, eax
0x140018a72  mov     [rsi], ax
0x140018a75  mov     [rsp+2C0h+var_280], edi
0x140018a79  lea     rax, [rsp+2C0h+var_26C]
0x140018a7e  mov     [rsp+2C0h+var_288], rax
0x140018a83  lea     rsi, [rbx+5B0h]
0x140018a8a  mov     [rsp+2C0h+var_290], 10h
0x140018a92  lea     rax, [rsp+2C0h+var_270]
0x140018a97  mov     [rsp+2C0h+var_298], rsi
0x140018a9c  lea     r9, DEVPKEY_DriverPackage_ClassGuid
0x140018aa3  mov     r8, r12
0x140018aa6  mov     [rsp+2C0h+var_2A0], rax
0x140018aab  mov     edx, 2
0x140018ab0  mov     rcx, r14
0x140018ab3  call    cs:__imp_DriverStoreGetObjectPropertyW
0x140018ab9  test    eax, eax
0x140018abb  jz      short loc_140018AC4
0x140018abd  cmp     [rsp+2C0h+var_270], 0Dh
0x140018ac2  jz      short loc_140018ACA
0x140018ac4  xorps   xmm0, xmm0
0x140018ac7  movups  xmmword ptr [rsi], xmm0
0x140018aca  lea     r8, [rsp+2C0h+var_268]
0x140018acf  mov     qword ptr [rsp+2C0h+var_268], rbx
0x140018ad4  lea     rdx, EnumStrongNameDriver
0x140018adb  mov     qword ptr [rsp+2C0h+var_268+8], rdi
0x140018ae0  mov     rcx, r15; unsigned __int16 *
0x140018ae3  mov     dword ptr [rsp+2C0h+var_258], edi
0x140018ae7  call    DrvUtilsEnumDriversFromStrongNames
0x140018aec  jmp     short loc_140018AFA
0x140018aee  mov     dword ptr [rbx+0B70h], 1
0x140018af8  xor     edi, edi
0x140018afa  mov     rcx, r14
0x140018afd  call    cs:__imp_DriverStoreClose
0x140018b03  mov     ecx, edi; dwErrCode
0x140018b05  call    cs:__imp_SetLastError
0x140018b0b  mov     rax, rbx
0x140018b0e  mov     rcx, [rbp+1C0h+var_40]
0x140018b15  xor     rcx, rsp; StackCookie
0x140018b18  call    __security_check_cookie
0x140018b1d  add     rsp, 290h
0x140018b24  pop     r15
0x140018b26  pop     r14
0x140018b28  pop     r12
0x140018b2a  pop     rdi
0x140018b2b  pop     rsi
0x140018b2c  pop     rbx
0x140018b2d  pop     rbp
0x140018b2e  retn
```
