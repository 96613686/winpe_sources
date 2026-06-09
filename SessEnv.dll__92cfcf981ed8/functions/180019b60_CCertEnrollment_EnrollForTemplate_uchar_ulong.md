# CCertEnrollment::EnrollForTemplate(uchar *,ulong *)

- ea: `0x180019b60`
- end: `0x180019ce5`
- name: `?EnrollForTemplate@CCertEnrollment@@QEAAJPEAEPEAK@Z`
- size: `389`
- prototype: `int(CCertEnrollment *__hidden this, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003860`

## callees

- `0x180003f30`
- `0x180019b60`
- `0x180019cec`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ca2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019ba0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019ba0`
- `OLEAUT32!__imp_SysFreeString` at `0x180019cc6`
- `OLEAUT32!__imp_SysFreeString` at `0x180019cc6`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180019c52`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180019c52`
- `CRYPT32!CertCreateCertificateContext` at `0x180019c65`
- `CRYPT32!CertCreateCertificateContext` at `0x180019c65`
- `CRYPT32!CertFreeCertificateContext` at `0x180019cba`
- `CRYPT32!CertFreeCertificateContext` at `0x180019cba`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180019c98`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180019c98`

## string_xrefs

- `0x180019bb6`: `CCertEnrollment::EnrollForTemplate`
- `0x180019bac`: `spIX509Enrollment.CoCreateInstance failed: 0x%x in %s`
- `0x180019bf1`: `spIX509Enrollment->InitializeFromTemplateName failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCertEnrollment::EnrollForTemplate(CCertEnrollment *this, unsigned __int8 *a2, unsigned int *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  UINT v11; // eax
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v13; // rdi
  signed int v14; // eax
  signed int LastError; // eax
  BSTR bstr[7]; // [rsp+30h] [rbp-38h] BYREF
  LPVOID v18; // [rsp+88h] [rbp+20h] BYREF

  v18 = 0;
  bstr[0] = 0;
  v6 = CoCreateInstance(
         &GUID_884e2046_217d_11da_b2a4_000e7bbb2b09,
         0,
         1u,
         &GUID_728ab346_217d_11da_b2a4_000e7bbb2b09,
         &v18);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v18 + 64LL))(v18, 2, *((_QWORD *)this + 1));
    v7 = v8;
    if ( v8 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 88LL))(v18);
      v7 = v9;
      if ( v9 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, BSTR *))(*(_QWORD *)v18 + 176LL))(v18, 2, bstr);
        v7 = v10;
        if ( v10 >= 0 )
        {
          v11 = SysStringByteLen(bstr[0]);
          CertificateContext = CertCreateCertificateContext(0x10001u, (const BYTE *)bstr[0], v11);
          v13 = CertificateContext;
          if ( CertificateContext )
          {
            if ( !CertGetCertificateContextProperty(CertificateContext, 3u, a2, a3) )
            {
              LastError = GetLastError();
              v7 = LastError;
              if ( LastError > 0 )
                v7 = (unsigned __int16)LastError | 0x80070000;
            }
            CertFreeCertificateContext(v13);
          }
          else
          {
            v14 = GetLastError();
            v7 = v14;
            if ( v14 > 0 )
              v7 = (unsigned __int16)v14 | 0x80070000;
          }
        }
        else
        {
          _DbgPrintMessage(
            8,
            "spIX509Enrollment->get_Certificate failed: 0x%x in %s",
            (unsigned int)v10,
            "CCertEnrollment::EnrollForTemplate");
        }
      }
      else
      {
        _DbgPrintMessage(
          8,
          "spIX509Enrollment->Enroll failed: 0x%x in %s",
          (unsigned int)v9,
          "CCertEnrollment::EnrollForTemplate");
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "spIX509Enrollment->InitializeFromTemplateName failed: 0x%x in %s",
        (unsigned int)v8,
        "CCertEnrollment::EnrollForTemplate");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "spIX509Enrollment.CoCreateInstance failed: 0x%x in %s",
      (unsigned int)v6,
      "CCertEnrollment::EnrollForTemplate");
  }
  SysFreeString(bstr[0]);
  ATL::CComPtrBase<IDirectorySearch>::~CComPtrBase<IDirectorySearch>((__int64 *)&v18);
  return v7;
}

```

## disassembly

```asm
0x180019b60  mov     r11, rsp
0x180019b63  push    rbx
0x180019b64  push    rbp
0x180019b65  push    rsi
0x180019b66  push    rdi
0x180019b67  sub     rsp, 48h
0x180019b6b  mov     rsi, r8
0x180019b6e  mov     rbp, rdx
0x180019b71  mov     rdi, rcx
0x180019b74  mov     qword ptr [r11+20h], 0
0x180019b7c  mov     qword ptr [r11-38h], 0
0x180019b84  lea     rax, [r11+20h]
0x180019b88  mov     [r11-48h], rax
0x180019b8c  lea     r9, _GUID_728ab346_217d_11da_b2a4_000e7bbb2b09; riid
0x180019b93  xor     edx, edx; pUnkOuter
0x180019b95  lea     r8d, [rdx+1]; dwClsContext
0x180019b99  lea     rcx, _GUID_884e2046_217d_11da_b2a4_000e7bbb2b09; rclsid
0x180019ba0  call    cs:__imp_CoCreateInstance
0x180019ba6  mov     ebx, eax
0x180019ba8  test    eax, eax
0x180019baa  jns     short loc_180019BCC
0x180019bac  lea     rdx, aSpix509enrollm_0; "spIX509Enrollment.CoCreateInstance fail"...
0x180019bb3  mov     r8d, eax
0x180019bb6  lea     r9, aCcertenrollmen_2; "CCertEnrollment::EnrollForTemplate"
0x180019bbd  mov     ecx, 8; int
0x180019bc2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019bc7  jmp     loc_180019CC1
0x180019bcc  mov     rcx, [rsp+68h+arg_18]
0x180019bd4  mov     rax, [rcx]
0x180019bd7  mov     r8, [rdi+8]
0x180019bdb  mov     edi, 2
0x180019be0  mov     edx, edi
0x180019be2  mov     rax, [rax+40h]
0x180019be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019beb  mov     ebx, eax
0x180019bed  test    eax, eax
0x180019bef  jns     short loc_180019BFA
0x180019bf1  lea     rdx, aSpix509enrollm_1; "spIX509Enrollment->InitializeFromTempla"...
0x180019bf8  jmp     short loc_180019BB3
0x180019bfa  mov     rcx, [rsp+68h+arg_18]
0x180019c02  mov     rax, [rcx]
0x180019c05  mov     rax, [rax+58h]
0x180019c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c0e  mov     ebx, eax
0x180019c10  test    eax, eax
0x180019c12  jns     short loc_180019C1D
0x180019c14  lea     rdx, aSpix509enrollm; "spIX509Enrollment->Enroll failed: 0x%x "...
0x180019c1b  jmp     short loc_180019BB3
0x180019c1d  mov     rcx, [rsp+68h+arg_18]
0x180019c25  mov     rax, [rcx]
0x180019c28  lea     r8, [rsp+68h+bstr]
0x180019c2d  mov     edx, edi
0x180019c2f  mov     rax, [rax+0B0h]
0x180019c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c3b  mov     ebx, eax
0x180019c3d  test    eax, eax
0x180019c3f  jns     short loc_180019C4D
0x180019c41  lea     rdx, aSpix509enrollm_2; "spIX509Enrollment->get_Certificate fail"...
0x180019c48  jmp     loc_180019BB3
0x180019c4d  mov     rcx, [rsp+68h+bstr]; bstr
0x180019c52  call    cs:__imp_SysStringByteLen
0x180019c58  mov     r8d, eax; cbCertEncoded
0x180019c5b  mov     rdx, [rsp+68h+bstr]; pbCertEncoded
0x180019c60  mov     ecx, 10001h; dwCertEncodingType
0x180019c65  call    cs:__imp_CertCreateCertificateContext
0x180019c6b  mov     rdi, rax
0x180019c6e  test    rax, rax
0x180019c71  jnz     short loc_180019C8A
0x180019c73  call    cs:__imp_GetLastError
0x180019c79  mov     ebx, eax
0x180019c7b  test    eax, eax
0x180019c7d  jle     short loc_180019CC1
0x180019c7f  movzx   ebx, ax
0x180019c82  or      ebx, 80070000h
0x180019c88  jmp     short loc_180019CC1
0x180019c8a  mov     r9, rsi; pcbData
0x180019c8d  mov     r8, rbp; pvData
0x180019c90  mov     edx, 3; dwPropId
0x180019c95  mov     rcx, rdi; pCertContext
0x180019c98  call    cs:__imp_CertGetCertificateContextProperty
0x180019c9e  test    eax, eax
0x180019ca0  jnz     short loc_180019CB7
0x180019ca2  call    cs:__imp_GetLastError
0x180019ca8  mov     ebx, eax
0x180019caa  test    eax, eax
0x180019cac  jle     short loc_180019CB7
0x180019cae  movzx   ebx, ax
0x180019cb1  or      ebx, 80070000h
0x180019cb7  mov     rcx, rdi; pCertContext
0x180019cba  call    cs:__imp_CertFreeCertificateContext
0x180019cc0  nop
0x180019cc1  mov     rcx, [rsp+68h+bstr]; bstrString
0x180019cc6  call    cs:__imp_SysFreeString
0x180019ccc  nop
0x180019ccd  lea     rcx, [rsp+68h+arg_18]
0x180019cd5  call    ??1?$CComPtrBase@UIDirectorySearch@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDirectorySearch>::~CComPtrBase<IDirectorySearch>(void)
0x180019cda  mov     eax, ebx
0x180019cdc  add     rsp, 48h
0x180019ce0  pop     rdi
0x180019ce1  pop     rsi
0x180019ce2  pop     rbp
0x180019ce3  pop     rbx
0x180019ce4  retn
```
