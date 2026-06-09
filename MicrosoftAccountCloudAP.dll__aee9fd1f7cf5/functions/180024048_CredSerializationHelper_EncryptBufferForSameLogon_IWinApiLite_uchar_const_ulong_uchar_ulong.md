# CredSerializationHelper::EncryptBufferForSameLogon(IWinApiLite *,uchar * const,ulong,uchar * *,ulong *)

- ea: `0x180024048`
- end: `0x180024250`
- name: `?EncryptBufferForSameLogon@CredSerializationHelper@@SAJPEAVIWinApiLite@@QEAEKPEAPEAEPEAK@Z`
- size: `520`
- prototype: `__int64 __fastcall(struct IWinApiLite *, unsigned __int8 *const, unsigned int, char **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800244b0`

## callees

- `0x180003b14`
- `0x180007eb8`
- `0x180008440`
- `0x18000baac`
- `0x18000fcf4`
- `0x18001254c`
- `0x180023b5c`
- `0x180023c04`
- `0x180024048`
- `0x180026c8c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024175`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024175`

## string_xrefs

- `0x1800241c4`: `hr = SafeCopyMemory(pBuffer, bufferSize, pData, dataSize)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CredSerializationHelper::EncryptBufferForSameLogon(
        struct IWinApiLite *a1,
        unsigned __int8 *const a2,
        unsigned int a3,
        char **a4,
        unsigned int *a5)
{
  rsize_t v6; // rdi
  unsigned int *v8; // r13
  unsigned int v9; // esi
  unsigned int v10; // r14d
  char *v11; // rbx
  signed int LastError; // eax
  int v13; // r9d
  const char *v14; // rax
  unsigned int v15; // r8d
  unsigned int v16; // ebx
  __int64 v17; // rdx
  int v18; // r8d
  char *v20; // [rsp+20h] [rbp-60h]
  char *v21; // [rsp+30h] [rbp-50h] BYREF
  int *v22[4]; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v23[5]; // [rsp+58h] [rbp-28h] BYREF
  int v26; // [rsp+D8h] [rbp+58h] BYREF

  v6 = a3;
  v26 = 0;
  v23[0] = "CredSerializationHelper::EncryptBufferForSameLogon";
  v23[1] = &v26;
  v23[2] = 0;
  v23[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\serialization\\credserializationhelper.cpp",
    "CredSerializationHelper::EncryptBufferForSameLogon",
    (const char *)0x1C,
    0,
    (const unsigned __int16 *)v20);
  v21 = 0;
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v22,
    "CredSerializationHelper::EncryptBufferForSameLogon",
    &v26,
    10,
    &qword_18003F518);
  *a4 = 0;
  v8 = a5;
  *a5 = 0;
  if ( !a2 || !(_DWORD)v6 )
  {
    v13 = -2147024883;
    v14 = "pData != nullptr && dataSize != 0";
    v15 = 42;
    goto LABEL_14;
  }
  v9 = 16 - (v6 & 0xF);
  v10 = v9 + v6;
  v11 = (char *)LiveAllocate(v9 + (unsigned int)v6);
  if ( !v11 )
  {
    v26 = -2147024882;
    goto LABEL_15;
  }
  CMIDLPtr<unsigned short *>::Clear(&v21);
  v21 = v11;
  if ( memcpy_s_0(v11, v10, a2, v6) )
  {
    v13 = -2147418113;
    v14 = "hr = SafeCopyMemory(pBuffer, bufferSize, pData, dataSize)";
    v15 = 67;
LABEL_14:
    v26 = v13;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\serialization\\credserializationhelper.cpp",
      "CredSerializationHelper::EncryptBufferForSameLogon",
      v15,
      v13,
      v14);
    goto LABEL_15;
  }
  v26 = 0;
  memset_0(&v11[v6], (unsigned __int8)v9, v9);
  if ( (*(unsigned int (__fastcall **)(struct IWinApiLite *, char *, _QWORD, __int64))(*(_QWORD *)a1 + 24LL))(
         a1,
         v11,
         v10,
         2) )
  {
    goto LABEL_11;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v26 = LastError;
  if ( LastError >= 0 )
  {
LABEL_11:
    v21 = 0;
    *a4 = v11;
    *v8 = v10;
    v26 = 0;
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\serialization\\credserializationhelper.cpp",
      "CredSerializationHelper::EncryptBufferForSameLogon",
      0x52u,
      LastError,
      "hr = HRESULT_FROM_WIN32(GetLastError())");
  }
LABEL_15:
  v16 = v26;
  ErrorVerifier::CheckAgainstList((PPTraceStatus *)v22[3], *v22[2], (unsigned __int64)v22[1], v22[0]);
  CMIDLPtr<unsigned short *>::Clear(&v21);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v23, v17, v18);
  return v16;
}

```

## disassembly

```asm
0x180024048  mov     [rsp-38h+arg_10], rbx
0x18002404d  mov     [rsp-38h+Source], rdx
0x180024052  mov     [rsp-38h+arg_0], rcx
0x180024057  push    rbp
0x180024058  push    rsi
0x180024059  push    rdi
0x18002405a  push    r12
0x18002405c  push    r13
0x18002405e  push    r14
0x180024060  push    r15
0x180024062  mov     rbp, rsp
0x180024065  sub     rsp, 80h
0x18002406c  mov     r12, r9
0x18002406f  mov     edi, r8d
0x180024072  mov     rbx, rdx
0x180024075  xor     esi, esi
0x180024077  mov     [rbp+arg_18], esi
0x18002407a  lea     r14, aCredserializat_3; "CredSerializationHelper::EncryptBufferF"...
0x180024081  mov     [rbp+var_28], r14
0x180024085  lea     rax, [rbp+arg_18]
0x180024089  mov     [rbp+var_20], rax
0x18002408d  mov     [rbp+var_18], rsi
0x180024091  mov     [rbp+var_10], rsi
0x180024095  xor     r9d, r9d; unsigned int
0x180024098  lea     r8d, [rsi+1Ch]; char *
0x18002409c  mov     rdx, r14; char *
0x18002409f  lea     rcx, aOnecoreuapDsEx_12; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800240a6  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800240ab  nop
0x1800240ac  mov     [rbp+var_50], rsi
0x1800240b0  lea     rax, qword_18003F518
0x1800240b7  mov     [rsp+80h+var_60], rax; int *
0x1800240bc  lea     r9d, [rsi+0Ah]; unsigned __int64
0x1800240c0  lea     r8, [rbp+arg_18]; int *
0x1800240c4  mov     rdx, r14; char *
0x1800240c7  lea     rcx, [rbp+var_48]; this
0x1800240cb  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x1800240d0  nop
0x1800240d1  mov     [r12], rsi
0x1800240d5  mov     r13, [rbp+arg_20]
0x1800240d9  mov     [r13+0], esi
0x1800240dd  test    rbx, rbx
0x1800240e0  jz      loc_1800241DA
0x1800240e6  test    edi, edi
0x1800240e8  jz      loc_1800241DA
0x1800240ee  mov     eax, edi
0x1800240f0  and     eax, 0Fh
0x1800240f3  mov     esi, 10h
0x1800240f8  sub     esi, eax
0x1800240fa  lea     r14d, [rsi+rdi]
0x1800240fe  mov     r15d, r14d
0x180024101  mov     ecx, r14d; unsigned __int64
0x180024104  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x180024109  mov     rbx, rax
0x18002410c  test    rax, rax
0x18002410f  jnz     short loc_18002411D
0x180024111  mov     [rbp+arg_18], 8007000Eh
0x180024118  jmp     loc_180024205
0x18002411d  lea     rcx, [rbp+var_50]
0x180024121  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x180024126  mov     [rbp+var_50], rbx
0x18002412a  mov     r9, rdi; SourceSize
0x18002412d  mov     r8, [rbp+Source]; Source
0x180024131  mov     rdx, r15; DestinationSize
0x180024134  mov     rcx, rbx; Destination
0x180024137  call    memcpy_s_0
0x18002413c  xor     r15d, r15d
0x18002413f  test    eax, eax
0x180024141  jnz     short loc_1800241BE
0x180024143  mov     [rbp+arg_18], r15d
0x180024147  mov     r8d, esi; Size
0x18002414a  movzx   edx, sil; Val
0x18002414e  lea     rcx, [rdi+rbx]; void *
0x180024152  call    memset_0
0x180024157  mov     rcx, [rbp+arg_0]
0x18002415b  mov     rax, [rcx]
0x18002415e  lea     r9d, [r15+2]
0x180024162  mov     r8d, r14d
0x180024165  mov     rdx, rbx
0x180024168  mov     rax, [rax+18h]
0x18002416c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024171  test    eax, eax
0x180024173  jnz     short loc_1800241AC
0x180024175  call    cs:__imp_GetLastError
0x18002417b  test    eax, eax
0x18002417d  jle     short loc_180024187
0x18002417f  movzx   eax, ax
0x180024182  or      eax, 80070000h
0x180024187  mov     [rbp+arg_18], eax
0x18002418a  test    eax, eax
0x18002418c  jns     short loc_1800241AC
0x18002418e  lea     r8, aHrHresultFromW_1; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180024195  mov     [rsp+80h+var_60], r8
0x18002419a  mov     r9d, eax
0x18002419d  mov     r8d, 52h ; 'R'
0x1800241a3  lea     rdx, aCredserializat_3; "CredSerializationHelper::EncryptBufferF"...
0x1800241aa  jmp     short loc_1800241F9
0x1800241ac  mov     [rbp+var_50], r15
0x1800241b0  mov     [r12], rbx
0x1800241b4  mov     [r13+0], r14d
0x1800241b8  mov     [rbp+arg_18], r15d
0x1800241bc  jmp     short loc_180024205
0x1800241be  mov     r9d, 8000FFFFh
0x1800241c4  lea     rax, aHrSafecopymemo_5; "hr = SafeCopyMemory(pBuffer, bufferSize"...
0x1800241cb  mov     r8d, 43h ; 'C'
0x1800241d1  lea     rdx, aCredserializat_3; "CredSerializationHelper::EncryptBufferF"...
0x1800241d8  jmp     short loc_1800241F0
0x1800241da  mov     r9d, 8007000Dh; int
0x1800241e0  lea     rax, aPdataNullptrDa; "pData != nullptr && dataSize != 0"
0x1800241e7  mov     r8d, 2Ah ; '*'; unsigned int
0x1800241ed  mov     rdx, r14; char *
0x1800241f0  mov     [rsp+80h+var_60], rax; char *
0x1800241f5  mov     [rbp+arg_18], r9d
0x1800241f9  lea     rcx, aOnecoreuapDsEx_12; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180024200  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180024205  mov     ebx, [rbp+arg_18]
0x180024208  mov     r9, [rbp+var_48]; int *
0x18002420c  mov     r8, [rbp+var_40]; unsigned __int64
0x180024210  mov     rdx, [rbp+var_38]
0x180024214  mov     edx, [rdx]; int
0x180024216  mov     rcx, [rbp+var_30]; char *
0x18002421a  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x18002421f  nop
0x180024220  lea     rcx, [rbp+var_50]
0x180024224  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x180024229  nop
0x18002422a  lea     rcx, [rbp+var_28]
0x18002422e  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180024233  mov     eax, ebx
0x180024235  mov     rbx, [rsp+80h+arg_10]
0x18002423d  add     rsp, 80h
0x180024244  pop     r15
0x180024246  pop     r14
0x180024248  pop     r13
0x18002424a  pop     r12
0x18002424c  pop     rdi
0x18002424d  pop     rsi
0x18002424e  pop     rbp
0x18002424f  retn
```
