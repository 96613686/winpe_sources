# CertificateStore::Open(CertificateStore::StoreProviderTypes,ushort const *)

- ea: `0x180080bb4`
- end: `0x180080cc4`
- name: `?Open@CertificateStore@@QEAAJW4StoreProviderTypes@1@PEBG@Z`
- size: `272`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18002a9a8`
- `0x180031f04`
- `0x18004d6fc`
- `0x18004f134`
- `0x180050b44`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180071e14`
- `0x1800802e0`
- `0x180080bb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c49`
- `CRYPT32!CertOpenStore` at `0x180080c3b`
- `CRYPT32!CertOpenStore` at `0x180080c3b`

## string_xrefs

- `0x180080bd5`: `CertificateStore::Open`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CertificateStore::Open(CertificateStore *a1, DWORD a2, const void *a3)
{
  signed int LastError; // eax
  HCERTSTORE v7; // rax
  unsigned int v8; // ebx
  void *pvPara; // [rsp+20h] [rbp-88h]
  int v11; // [rsp+30h] [rbp-78h]
  const char *v12[11]; // [rsp+50h] [rbp-58h] BYREF
  signed int v13; // [rsp+B0h] [rbp+8h] BYREF

  v13 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v12,
    (int)"certificatestore.cpp",
    (int)"CertificateStore::Open",
    (int)&v13);
  if ( *(_QWORD *)a1 )
  {
    LastError = CertificateStore::Close(a1);
    v13 = LastError;
    if ( LastError < 0 )
    {
      v11 = 31;
LABEL_9:
      LODWORD(pvPara) = LastError;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, pvPara, "certificatestore.cpp", v11, "HRESULT", &base);
      goto LABEL_10;
    }
  }
  v7 = CertOpenStore((LPCSTR)0xA, 0, 0, a2, a3);
  *(_QWORD *)a1 = v7;
  if ( !v7 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = LastError;
    if ( LastError < 0 )
    {
      v11 = 38;
      goto LABEL_9;
    }
  }
LABEL_10:
  v8 = v13;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v12);
  return v8;
}

```

## disassembly

```asm
0x180080bb4  mov     rax, rsp
0x180080bb7  push    rbx
0x180080bb8  push    rbp
0x180080bb9  push    rsi
0x180080bba  push    rdi
0x180080bbb  sub     rsp, 88h
0x180080bc2  mov     rdi, r8
0x180080bc5  mov     esi, edx
0x180080bc7  mov     rbx, rcx
0x180080bca  mov     dword ptr [rax+8], 0
0x180080bd1  lea     r9, [rax+8]
0x180080bd5  lea     r8, aCertificatesto; "CertificateStore::Open"
0x180080bdc  lea     rbp, aOnecoreuapDsEx_71+20h; "certificatestore.cpp"
0x180080be3  mov     rdx, rbp
0x180080be6  lea     rcx, [rax-58h]
0x180080bea  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180080bef  nop
0x180080bf0  cmp     qword ptr [rbx], 0
0x180080bf4  jz      short loc_180080C2B
0x180080bf6  mov     rcx, rbx; this
0x180080bf9  call    ?Close@CertificateStore@@QEAAJXZ; CertificateStore::Close(void)
0x180080bfe  mov     [rsp+0A8h+arg_0], eax
0x180080c05  test    eax, eax
0x180080c07  jns     short loc_180080C2B
0x180080c09  lea     rcx, base
0x180080c10  mov     [rsp+0A8h+var_68], rcx
0x180080c15  lea     rcx, aHresult; "HRESULT"
0x180080c1c  mov     [rsp+0A8h+var_70], rcx
0x180080c21  mov     [rsp+0A8h+var_78], 1Fh
0x180080c29  jmp     short loc_180080C86
0x180080c2b  mov     [rsp+0A8h+pvPara], rdi; pvPara
0x180080c30  mov     r9d, esi; dwFlags
0x180080c33  xor     r8d, r8d; hCryptProv
0x180080c36  xor     edx, edx; dwEncodingType
0x180080c38  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180080c3b  call    cs:__imp_CertOpenStore
0x180080c41  mov     [rbx], rax
0x180080c44  test    rax, rax
0x180080c47  jnz     short loc_180080CA5
0x180080c49  call    cs:__imp_GetLastError
0x180080c4f  test    eax, eax
0x180080c51  jle     short loc_180080C5B
0x180080c53  movzx   eax, ax
0x180080c56  or      eax, 80070000h
0x180080c5b  mov     [rsp+0A8h+arg_0], eax
0x180080c62  test    eax, eax
0x180080c64  jns     short loc_180080CA5
0x180080c66  lea     rcx, base
0x180080c6d  mov     [rsp+0A8h+var_68], rcx
0x180080c72  lea     rcx, aHresult; "HRESULT"
0x180080c79  mov     [rsp+0A8h+var_70], rcx
0x180080c7e  mov     [rsp+0A8h+var_78], 26h ; '&'
0x180080c86  mov     [rsp+0A8h+var_80], rbp
0x180080c8b  mov     ecx, 2
0x180080c90  mov     dword ptr [rsp+0A8h+pvPara], eax
0x180080c94  mov     r9d, ecx
0x180080c97  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180080c9e  xor     edx, edx
0x180080ca0  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180080ca5  mov     ebx, [rsp+0A8h+arg_0]
0x180080cac  lea     rcx, [rsp+0A8h+var_58]
0x180080cb1  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x180080cb6  mov     eax, ebx
0x180080cb8  add     rsp, 88h
0x180080cbf  pop     rdi
0x180080cc0  pop     rsi
0x180080cc1  pop     rbp
0x180080cc2  pop     rbx
0x180080cc3  retn
```
