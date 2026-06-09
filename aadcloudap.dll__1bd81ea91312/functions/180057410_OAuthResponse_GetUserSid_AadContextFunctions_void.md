# OAuthResponse::GetUserSid(AadContextFunctions *,void * *)

- ea: `0x180057410`
- end: `0x1800575b2`
- name: `?GetUserSid@OAuthResponse@@UEAAJPEAVAadContextFunctions@@PEAPEAX@Z`
- size: `418`
- prototype: `int(OAuthResponse *__hidden this, struct AadContextFunctions *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180057410`
- `0x180071e14`
- `0x180078780`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057497`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057586`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057586`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18005748d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18005748d`

## string_xrefs

- `0x180057444`: `OAuthResponse::GetUserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OAuthResponse::GetUserSid(OAuthResponse *this, struct AadContextFunctions *a2, void **a3)
{
  const WCHAR *v6; // rcx
  signed int LastError; // eax
  unsigned int v8; // ebx
  signed int v10; // [rsp+20h] [rbp-60h]
  int v11; // [rsp+20h] [rbp-60h]
  int v12; // [rsp+30h] [rbp-50h]
  int v13; // [rsp+30h] [rbp-50h]
  const char *v14[6]; // [rsp+50h] [rbp-30h] BYREF
  int v15; // [rsp+A8h] [rbp+28h] BYREF
  PSID Sid; // [rsp+B8h] [rbp+38h] BYREF

  v15 = 0;
  Sid = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v14,
    (int)"oauthresponse.cpp",
    (int)"OAuthResponse::GetUserSid",
    (int)&v15);
  if ( !a2 || !a3 )
  {
    v15 = -2147024809;
    v13 = 1009;
    v11 = -2147024809;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v11, "oauthresponse.cpp", v13, "HRESULT", &base);
    if ( !a2 )
      goto LABEL_15;
    goto LABEL_13;
  }
  *a3 = 0;
  v6 = (const WCHAR *)*((_QWORD *)this + 44);
  if ( *((_DWORD *)v6 - 4) )
  {
    if ( !ConvertStringSidToSidW(v6, &Sid) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v15 = LastError;
      if ( LastError < 0 )
      {
        v12 = 1018;
LABEL_9:
        v10 = LastError;
        WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v10, "oauthresponse.cpp", v12, "HRESULT", &base);
        goto LABEL_13;
      }
    }
    if ( DuplicateSID(a2, Sid, a3) < 0 )
    {
      LastError = -2147187625;
      v15 = -2147187625;
      v12 = 1022;
      goto LABEL_9;
    }
  }
LABEL_13:
  if ( Sid )
    LocalFree(Sid);
LABEL_15:
  v8 = v15;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v14);
  return v8;
}

```

## disassembly

```asm
0x180057410  mov     [rsp-18h+arg_0], rbx
0x180057415  mov     [rsp-18h+arg_10], rsi
0x18005741a  push    rbp
0x18005741b  push    rdi
0x18005741c  push    r15
0x18005741e  mov     rbp, rsp
0x180057421  sub     rsp, 80h
0x180057428  mov     rbx, r8
0x18005742b  mov     rdi, rdx
0x18005742e  mov     rsi, rcx
0x180057431  mov     [rbp+arg_8], 0
0x180057438  mov     [rbp+Sid], 0
0x180057440  lea     r9, [rbp+arg_8]
0x180057444  lea     r8, aOauthresponseG; "OAuthResponse::GetUserSid"
0x18005744b  lea     r15, aOnecoreuapDsEx_66+21h; "oauthresponse.cpp"
0x180057452  mov     rdx, r15
0x180057455  lea     rcx, [rbp+var_30]
0x180057459  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18005745e  nop
0x18005745f  test    rdi, rdi
0x180057462  jz      loc_180057531
0x180057468  test    rbx, rbx
0x18005746b  jz      loc_180057531
0x180057471  mov     qword ptr [rbx], 0
0x180057478  mov     rcx, [rsi+160h]; StringSid
0x18005747f  cmp     dword ptr [rcx-10h], 0
0x180057483  jz      loc_18005757D
0x180057489  lea     rdx, [rbp+Sid]; Sid
0x18005748d  call    cs:__imp_ConvertStringSidToSidW
0x180057493  test    eax, eax
0x180057495  jnz     short loc_1800574F4
0x180057497  call    cs:__imp_GetLastError
0x18005749d  test    eax, eax
0x18005749f  jle     short loc_1800574A9
0x1800574a1  movzx   eax, ax
0x1800574a4  or      eax, 80070000h
0x1800574a9  mov     [rbp+arg_8], eax
0x1800574ac  test    eax, eax
0x1800574ae  jns     short loc_1800574F4
0x1800574b0  lea     rcx, base
0x1800574b7  mov     [rsp+80h+var_40], rcx
0x1800574bc  lea     rcx, aHresult; "HRESULT"
0x1800574c3  mov     [rsp+80h+var_48], rcx
0x1800574c8  mov     [rsp+80h+var_50], 3FAh
0x1800574d0  mov     [rsp+80h+var_58], r15
0x1800574d5  mov     [rsp+80h+var_60], eax
0x1800574d9  mov     ecx, 2
0x1800574de  mov     r9d, ecx
0x1800574e1  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800574e8  xor     edx, edx
0x1800574ea  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800574ef  jmp     loc_18005757D
0x1800574f4  mov     r8, rbx; void **
0x1800574f7  mov     rdx, [rbp+Sid]; void *
0x1800574fb  mov     rcx, rdi; struct AadContextFunctions *
0x1800574fe  call    ?DuplicateSID@@YAJPEAVAadContextFunctions@@PEAXPEAPEAX@Z; DuplicateSID(AadContextFunctions *,void *,void * *)
0x180057503  test    eax, eax
0x180057505  jns     short loc_18005757D
0x180057507  mov     eax, 80048457h
0x18005750c  mov     [rbp+arg_8], eax
0x18005750f  lea     rcx, base
0x180057516  mov     [rsp+80h+var_40], rcx
0x18005751b  lea     rcx, aHresult; "HRESULT"
0x180057522  mov     [rsp+80h+var_48], rcx
0x180057527  mov     [rsp+80h+var_50], 3FEh
0x18005752f  jmp     short loc_1800574D0
0x180057531  mov     eax, 80070057h
0x180057536  mov     [rbp+arg_8], eax
0x180057539  lea     rcx, base
0x180057540  mov     [rsp+80h+var_40], rcx
0x180057545  lea     rcx, aHresult; "HRESULT"
0x18005754c  mov     [rsp+80h+var_48], rcx
0x180057551  mov     [rsp+80h+var_50], 3F1h
0x180057559  mov     [rsp+80h+var_58], r15
0x18005755e  mov     [rsp+80h+var_60], eax
0x180057562  mov     ecx, 2
0x180057567  mov     r9d, ecx
0x18005756a  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180057571  xor     edx, edx
0x180057573  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180057578  test    rdi, rdi
0x18005757b  jz      short loc_18005758C
0x18005757d  mov     rcx, [rbp+Sid]; hMem
0x180057581  test    rcx, rcx
0x180057584  jz      short loc_18005758C
0x180057586  call    cs:__imp_LocalFree
0x18005758c  mov     ebx, [rbp+arg_8]
0x18005758f  lea     rcx, [rbp+var_30]
0x180057593  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x180057598  mov     eax, ebx
0x18005759a  lea     r11, [rsp+80h+var_s0]
0x1800575a2  mov     rbx, [r11+20h]
0x1800575a6  mov     rsi, [r11+30h]
0x1800575aa  mov     rsp, r11
0x1800575ad  pop     r15
0x1800575af  pop     rdi
0x1800575b0  pop     rbp
0x1800575b1  retn
```
