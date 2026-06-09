# GetCallerPackageSIDAsString(AadContextFunctions *,void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18002904c`
- end: `0x18002927b`
- name: `?GetCallerPackageSIDAsString@@YAJPEAVAadContextFunctions@@PEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(struct AadContextFunctions *, void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000da08`
- `0x18002a6f4`

## callees

- `0x1800065e8`
- `0x18000685c`
- `0x180006908`
- `0x1800069c0`
- `0x180006ac4`
- `0x18002904c`
- `0x180029284`
- `0x180071e14`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029183`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002918b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029183`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002918b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002916f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002916f`

## string_xrefs

- `0x18002908a`: `GetCallerPackageSIDAsString`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCallerPackageSIDAsString(struct AadContextFunctions *a1, void *a2, __int64 a3)
{
  PSID v6; // rbx
  int CallerPackageSid; // eax
  signed int LastError; // eax
  unsigned int v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  int v13; // [rsp+30h] [rbp-29h]
  LPWSTR StringSid; // [rsp+50h] [rbp-9h] BYREF
  const char *v15[11]; // [rsp+58h] [rbp-1h] BYREF
  int v16; // [rsp+C0h] [rbp+67h] BYREF
  PSID Sid; // [rsp+D8h] [rbp+7Fh] BYREF

  v16 = 0;
  v6 = 0;
  Sid = 0;
  StringSid = 0;
  ATL::CSimpleStringT<unsigned short,0>::Empty(a3);
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v15,
    (int)"login.cpp",
    (int)"GetCallerPackageSIDAsString",
    (int)&v16);
  if ( !a1 || !a2 )
  {
    v16 = -1073741811;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, -1073741811, "login.cpp", 2611, "NTSTATUS", &base);
    if ( !a1 )
      goto LABEL_20;
    goto LABEL_16;
  }
  CallerPackageSid = GetCallerPackageSid(a1, a2, &Sid);
  v16 = CallerPackageSid;
  if ( CallerPackageSid >= 0 )
  {
    v6 = Sid;
    if ( Sid )
    {
      if ( ConvertSidToStringSidW(Sid, &StringSid)
        || ((int)GetLastError() > 0
          ? (LastError = (unsigned __int16)GetLastError() | 0xC0070000)
          : (LastError = GetLastError()),
            v16 = LastError,
            LastError >= 0) )
      {
        v9 = ATL::CSimpleStringT<unsigned short,0>::StringLength(StringSid);
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3, v10, v9);
        goto LABEL_16;
      }
      v13 = 2623;
    }
    else
    {
      LastError = -1073741595;
      v16 = -1073741595;
      v13 = 2618;
    }
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, LastError, "login.cpp", v13, "NTSTATUS", &base);
  }
  else
  {
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, CallerPackageSid, "login.cpp", 2614, "NTSTATUS", &base);
    v6 = Sid;
  }
LABEL_16:
  if ( v6 )
    (*(void (__fastcall **)(struct AadContextFunctions *, PSID))(*(_QWORD *)a1 + 32LL))(a1, v6);
  if ( StringSid )
    (*(void (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 16LL))(a1);
LABEL_20:
  v11 = v16;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v15);
  return v11;
}

```

## disassembly

```asm
0x18002904c  mov     [rsp-8+arg_8], rbx
0x180029051  push    rbp
0x180029052  push    rsi
0x180029053  push    rdi
0x180029054  push    r14
0x180029056  push    r15
0x180029058  lea     rbp, [rsp-37h]
0x18002905d  sub     rsp, 90h
0x180029064  mov     r14, r8
0x180029067  mov     rsi, rdx
0x18002906a  mov     rdi, rcx
0x18002906d  mov     [rbp+57h+arg_0], 0
0x180029074  xor     ebx, ebx
0x180029076  mov     [rbp+57h+Sid], rbx
0x18002907a  mov     [rbp+57h+StringSid], rbx
0x18002907e  mov     rcx, r8
0x180029081  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180029086  lea     r9, [rbp+57h+arg_0]
0x18002908a  lea     r8, aGetcallerpacka; "GetCallerPackageSIDAsString"
0x180029091  lea     r15, aOnecoreuapDsEx_25+21h; "login.cpp"
0x180029098  mov     rdx, r15
0x18002909b  lea     rcx, [rbp+57h+var_58]
0x18002909f  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x1800290a4  nop
0x1800290a5  test    rdi, rdi
0x1800290a8  jz      loc_1800291DB
0x1800290ae  test    rsi, rsi
0x1800290b1  jz      loc_1800291DB
0x1800290b7  lea     r8, [rbp+57h+Sid]; void **
0x1800290bb  mov     rdx, rsi; void *
0x1800290be  mov     rcx, rdi; struct AadContextFunctions *
0x1800290c1  call    ?GetCallerPackageSid@@YAJPEAVAadContextFunctions@@PEAXPEAPEAX@Z; GetCallerPackageSid(AadContextFunctions *,void *,void * *)
0x1800290c6  mov     [rbp+57h+arg_0], eax
0x1800290c9  test    eax, eax
0x1800290cb  jns     short loc_180029113
0x1800290cd  lea     rcx, base
0x1800290d4  mov     [rsp+0B0h+var_70], rcx
0x1800290d9  lea     rcx, aNtstatus; "NTSTATUS"
0x1800290e0  mov     [rsp+0B0h+var_78], rcx
0x1800290e5  mov     [rsp+0B0h+var_80], 0A36h
0x1800290ed  mov     [rsp+0B0h+var_88], r15
0x1800290f2  mov     [rsp+0B0h+var_90], eax
0x1800290f6  lea     ecx, [rbx+2]
0x1800290f9  mov     r9d, ecx
0x1800290fc  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180029103  xor     edx, edx
0x180029105  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18002910a  mov     rbx, [rbp+57h+Sid]
0x18002910e  jmp     loc_180029227
0x180029113  mov     rbx, [rbp+57h+Sid]
0x180029117  test    rbx, rbx
0x18002911a  jnz     short loc_180029168
0x18002911c  mov     eax, 0C00000E5h
0x180029121  mov     [rbp+57h+arg_0], eax
0x180029124  lea     rcx, base
0x18002912b  mov     [rsp+0B0h+var_70], rcx
0x180029130  lea     rcx, aNtstatus; "NTSTATUS"
0x180029137  mov     [rsp+0B0h+var_78], rcx
0x18002913c  mov     [rsp+0B0h+var_80], 0A3Ah
0x180029144  mov     [rsp+0B0h+var_88], r15
0x180029149  mov     [rsp+0B0h+var_90], eax
0x18002914d  mov     ecx, 2
0x180029152  mov     r9d, ecx
0x180029155  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18002915c  xor     edx, edx
0x18002915e  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180029163  jmp     loc_180029227
0x180029168  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18002916c  mov     rcx, rbx; Sid
0x18002916f  call    cs:__imp_ConvertSidToStringSidW
0x180029175  test    eax, eax
0x180029177  jnz     short loc_1800291C2
0x180029179  call    cs:__imp_GetLastError
0x18002917f  test    eax, eax
0x180029181  jg      short loc_18002918B
0x180029183  call    cs:__imp_GetLastError
0x180029189  jmp     short loc_180029199
0x18002918b  call    cs:__imp_GetLastError
0x180029191  movzx   eax, ax
0x180029194  or      eax, 0C0070000h
0x180029199  mov     [rbp+57h+arg_0], eax
0x18002919c  test    eax, eax
0x18002919e  jns     short loc_1800291C2
0x1800291a0  lea     rcx, base
0x1800291a7  mov     [rsp+0B0h+var_70], rcx
0x1800291ac  lea     rcx, aNtstatus; "NTSTATUS"
0x1800291b3  mov     [rsp+0B0h+var_78], rcx
0x1800291b8  mov     [rsp+0B0h+var_80], 0A3Fh
0x1800291c0  jmp     short loc_180029144
0x1800291c2  mov     rcx, [rbp+57h+StringSid]
0x1800291c6  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x1800291cb  mov     r8d, eax
0x1800291ce  mov     rdx, rcx
0x1800291d1  mov     rcx, r14
0x1800291d4  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800291d9  jmp     short loc_180029227
0x1800291db  mov     eax, 0C000000Dh
0x1800291e0  mov     [rbp+57h+arg_0], eax
0x1800291e3  lea     rcx, base
0x1800291ea  mov     [rsp+0B0h+var_70], rcx
0x1800291ef  lea     rcx, aNtstatus; "NTSTATUS"
0x1800291f6  mov     [rsp+0B0h+var_78], rcx
0x1800291fb  mov     [rsp+0B0h+var_80], 0A33h
0x180029203  mov     [rsp+0B0h+var_88], r15
0x180029208  mov     [rsp+0B0h+var_90], eax
0x18002920c  mov     ecx, 2
0x180029211  mov     r9d, ecx
0x180029214  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18002921b  xor     edx, edx
0x18002921d  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180029222  test    rdi, rdi
0x180029225  jz      short loc_180029256
0x180029227  test    rbx, rbx
0x18002922a  jz      short loc_18002923E
0x18002922c  mov     rax, [rdi]
0x18002922f  mov     rdx, rbx
0x180029232  mov     rcx, rdi
0x180029235  mov     rax, [rax+20h]
0x180029239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002923e  mov     rdx, [rbp+57h+StringSid]
0x180029242  test    rdx, rdx
0x180029245  jz      short loc_180029256
0x180029247  mov     rax, [rdi]
0x18002924a  mov     rcx, rdi
0x18002924d  mov     rax, [rax+10h]
0x180029251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029256  mov     ebx, [rbp+57h+arg_0]
0x180029259  lea     rcx, [rbp+57h+var_58]
0x18002925d  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x180029262  mov     eax, ebx
0x180029264  mov     rbx, [rsp+0B0h+arg_8]
0x18002926c  add     rsp, 90h
0x180029273  pop     r15
0x180029275  pop     r14
0x180029277  pop     rdi
0x180029278  pop     rsi
0x180029279  pop     rbp
0x18002927a  retn
```
