# CertificateStore::Delete(_CERT_CONTEXT const *)

- ea: `0x1800803bc`
- end: `0x180080520`
- name: `?Delete@CertificateStore@@QEAAJPEBU_CERT_CONTEXT@@@Z`
- size: `356`
- prototype: `int(CertificateStore *__hidden this, const struct _CERT_CONTEXT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18004e678`
- `0x180050b44`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180071e14`
- `0x1800803bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080471`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180080411`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180080411`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180080463`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180080463`

## string_xrefs

- `0x1800803e0`: `CertificateStore::Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CertificateStore::Delete(CertificateStore *this, const struct _CERT_CONTEXT *a2)
{
  const CERT_CONTEXT *v4; // rbx
  signed int LastError; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+30h] [rbp-58h]
  const char *v9[6]; // [rsp+50h] [rbp-38h] BYREF
  int v10; // [rsp+90h] [rbp+8h] BYREF

  v10 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v9,
    (int)"certificatestore.cpp",
    (int)"CertificateStore::Delete",
    (int)&v10);
  if ( !*(_QWORD *)this || !a2 )
  {
    LastError = -2147024809;
    v10 = -2147024809;
    v8 = 91;
    goto LABEL_14;
  }
  v4 = CertDuplicateCertificateContext(a2);
  if ( !v4 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = LastError;
    if ( LastError < 0 )
    {
      v8 = 99;
LABEL_14:
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, LastError, "certificatestore.cpp", v8, "HRESULT", &base);
      goto LABEL_15;
    }
  }
  if ( !CertDeleteCertificateFromStore(v4) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = LastError;
    if ( LastError < 0 )
    {
      v8 = 104;
      goto LABEL_14;
    }
  }
LABEL_15:
  v6 = v10;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v9);
  return v6;
}

```

## disassembly

```asm
0x1800803bc  mov     rax, rsp
0x1800803bf  mov     [rax+10h], rbx
0x1800803c3  mov     [rax+18h], rsi
0x1800803c7  push    rdi
0x1800803c8  sub     rsp, 80h
0x1800803cf  mov     rdi, rdx
0x1800803d2  mov     rbx, rcx
0x1800803d5  mov     dword ptr [rax+8], 0
0x1800803dc  lea     r9, [rax+8]
0x1800803e0  lea     r8, aCertificatesto_4; "CertificateStore::Delete"
0x1800803e7  lea     rsi, aOnecoreuapDsEx_71+20h; "certificatestore.cpp"
0x1800803ee  mov     rdx, rsi
0x1800803f1  lea     rcx, [rax-38h]
0x1800803f5  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x1800803fa  nop
0x1800803fb  cmp     qword ptr [rbx], 0
0x1800803ff  jz      loc_1800804AD
0x180080405  test    rdi, rdi
0x180080408  jz      loc_1800804AD
0x18008040e  mov     rcx, rdi; pCertContext
0x180080411  call    cs:__imp_CertDuplicateCertificateContext
0x180080417  mov     rbx, rax
0x18008041a  mov     edi, 80070000h
0x18008041f  test    rax, rax
0x180080422  jnz     short loc_180080460
0x180080424  call    cs:__imp_GetLastError
0x18008042a  test    eax, eax
0x18008042c  jle     short loc_180080433
0x18008042e  movzx   eax, ax
0x180080431  or      eax, edi
0x180080433  mov     [rsp+88h+arg_0], eax
0x18008043a  test    eax, eax
0x18008043c  jns     short loc_180080460
0x18008043e  lea     rcx, base
0x180080445  mov     [rsp+88h+var_48], rcx
0x18008044a  lea     rcx, aHresult; "HRESULT"
0x180080451  mov     [rsp+88h+var_50], rcx
0x180080456  mov     [rsp+88h+var_58], 63h ; 'c'
0x18008045e  jmp     short loc_1800804D9
0x180080460  mov     rcx, rbx; pCertContext
0x180080463  call    cs:__imp_CertDeleteCertificateFromStore
0x180080469  test    eax, eax
0x18008046b  jnz     loc_1800804F8
0x180080471  call    cs:__imp_GetLastError
0x180080477  test    eax, eax
0x180080479  jle     short loc_180080480
0x18008047b  movzx   eax, ax
0x18008047e  or      eax, edi
0x180080480  mov     [rsp+88h+arg_0], eax
0x180080487  test    eax, eax
0x180080489  jns     short loc_1800804F8
0x18008048b  lea     rcx, base
0x180080492  mov     [rsp+88h+var_48], rcx
0x180080497  lea     rcx, aHresult; "HRESULT"
0x18008049e  mov     [rsp+88h+var_50], rcx
0x1800804a3  mov     [rsp+88h+var_58], 68h ; 'h'
0x1800804ab  jmp     short loc_1800804D9
0x1800804ad  mov     eax, 80070057h
0x1800804b2  mov     [rsp+88h+arg_0], eax
0x1800804b9  lea     rcx, base
0x1800804c0  mov     [rsp+88h+var_48], rcx
0x1800804c5  lea     rcx, aHresult; "HRESULT"
0x1800804cc  mov     [rsp+88h+var_50], rcx
0x1800804d1  mov     [rsp+88h+var_58], 5Bh ; '['
0x1800804d9  mov     [rsp+88h+var_60], rsi
0x1800804de  mov     ecx, 2
0x1800804e3  mov     [rsp+88h+var_68], eax
0x1800804e7  mov     r9d, ecx
0x1800804ea  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800804f1  xor     edx, edx
0x1800804f3  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800804f8  mov     ebx, [rsp+88h+arg_0]
0x1800804ff  lea     rcx, [rsp+88h+var_38]
0x180080504  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x180080509  mov     eax, ebx
0x18008050b  lea     r11, [rsp+88h+var_8]
0x180080513  mov     rbx, [r11+18h]
0x180080517  mov     rsi, [r11+20h]
0x18008051b  mov     rsp, r11
0x18008051e  pop     rdi
0x18008051f  retn
```
