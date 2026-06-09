# RoutingMgr::GetRegisteredPaymentApplications(ulong *,_PaymentApplicationInformation * *)

- ea: `0x180031018`
- end: `0x1800313dd`
- name: `?GetRegisteredPaymentApplications@RoutingMgr@@QEAAJPEAKPEAPEAU_PaymentApplicationInformation@@@Z`
- size: `965`
- prototype: `__int64 __fastcall(RoutingMgr *__hidden this, unsigned int *, struct _PaymentApplicationInformation **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011680`

## callees

- `0x1800057c6`
- `0x180005840`
- `0x180005858`
- `0x18002f124`
- `0x180031018`
- `0x180031d0c`
- `0x180035cec`
- `0x18003ee30`
- `0x18007cfb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003135c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003135c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031398`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800313ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031398`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800313ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003113a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031302`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003113a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031302`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800313b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800313b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031059`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031059`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RoutingMgr::GetRegisteredPaymentApplications(
        RoutingMgr *this,
        unsigned int *a2,
        struct _PaymentApplicationInformation **a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r12
  struct _PaymentApplicationInformation *v7; // r14
  int v8; // ebx
  bool IsLegacyUiccSelectionAvailable; // al
  unsigned int v10; // r8d
  __int64 v11; // rbx
  __int64 v12; // r13
  LPVOID v13; // rax
  _QWORD *v14; // r15
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  void *v20; // rbx
  SIZE_T v21; // rsi
  struct _PaymentApplicationInformation *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  LPVOID *v26; // rdi
  LPVOID *v27; // rsi
  void *Src[2]; // [rsp+20h] [rbp-118h] BYREF
  __int64 v30; // [rsp+30h] [rbp-108h]
  struct _RTL_CRITICAL_SECTION *v31; // [rsp+38h] [rbp-100h]
  char v32; // [rsp+40h] [rbp-F8h]
  _BYTE v33[160]; // [rsp+50h] [rbp-E8h] BYREF
  __int64 v34; // [rsp+F0h] [rbp-48h]

  *(_OWORD *)Src = 0;
  v30 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 80);
  v31 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 80);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  v32 = 1;
  v7 = 0;
  if ( !a2 || !a3 )
  {
    v8 = -2147467261;
    goto LABEL_30;
  }
  if ( !*((_BYTE *)this + 177) )
  {
    v8 = -2147019873;
    goto LABEL_30;
  }
  if ( !*((_BYTE *)this + 176) )
    RoutingMgr::IsLegacyUiccSelectionAvailable(this);
  IsLegacyUiccSelectionAvailable = RoutingMgr::IsLegacyUiccSelectionAvailable(this);
  v11 = v10 + 1;
  if ( !IsLegacyUiccSelectionAvailable )
    v11 = v10;
  v12 = 160;
  memset_0(v33, 0, sizeof(v33));
  try
  {
    v34 = 0;
    std::vector<_PaymentApplicationInformation>::push_back(Src, v33);
    memset_0(Src[0], 0, 0x82u);
    *(GUID *)((char *)Src[0] + 132) = GUID_NULL;
    *((_BYTE *)Src[0] + 148) = *((_WORD *)this + 98) == 0;
    *((_DWORD *)Src[0] + 38) = v11;
    v13 = CoTaskMemAlloc(160 * v11);
  }
  catch ( std::bad_alloc )
  {
    v7 = 0;
    v8 = -2147024882;
    v6 = v31;
    goto LABEL_30;
  }
  *((_QWORD *)Src[0] + 20) = v13;
  if ( !*((_QWORD *)Src[0] + 20) )
    goto LABEL_12;
  if ( *((_BYTE *)this + 176) || !RoutingMgr::IsLegacyUiccSelectionAvailable(this) )
  {
    v14 = (_QWORD *)((char *)this + 180);
    v16 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)((char *)this + 180);
    if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)((char *)this + 180) )
      v16 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)((char *)this + 188);
    v17 = *((_QWORD *)Src[0] + 20);
    *(_BYTE *)(v17 + 149) = 1;
    *(_DWORD *)(v17 + 156) = 0;
    *(_BYTE *)(v17 + 148) = v16 == 0;
    *(GUID *)(v17 + 132) = GUID_NULL;
    *(_DWORD *)(v17 + 152) = 2;
    memset_0((void *)v17, 0, 0x82u);
    v15 = 312;
  }
  else
  {
    v14 = (_QWORD *)((char *)this + 180);
    v12 = 0;
    v15 = 152;
  }
  if ( RoutingMgr::IsLegacyUiccSelectionAvailable(this) )
  {
    v18 = NFC_PAYMENT_APPLICATION_LEGACY_UICC_GUID - *v14;
    if ( (_QWORD)NFC_PAYMENT_APPLICATION_LEGACY_UICC_GUID == *v14 )
      v18 = *((_QWORD *)&NFC_PAYMENT_APPLICATION_LEGACY_UICC_GUID + 1) - v14[1];
    v19 = v12 + *((_QWORD *)Src[0] + 20);
    *(_BYTE *)(v19 + 149) = 1;
    *(_DWORD *)(v19 + 156) = 0;
    *(_BYTE *)(v19 + 148) = v18 == 0;
    *(_OWORD *)(v19 + 132) = NFC_PAYMENT_APPLICATION_LEGACY_UICC_GUID;
    *(_DWORD *)(v19 + 152) = 2;
    memset_0((void *)v19, 0, 0x82u);
    *(_DWORD *)(v15 + *((_QWORD *)Src[0] + 20)) = 1;
    v20 = (void *)(v12 + *((_QWORD *)Src[0] + 20));
    memset_0(v20, 0, 0x82u);
    NfcRegUtils::GetString(
      (const struct NfcRegistryLocation *)&qword_1800A1C08,
      L"UICCApplicationName",
      (unsigned __int16 *)v20,
      0x41u);
  }
  v8 = RoutingRegistrationStore::AddPaymentApplicationsToList(*((_QWORD *)this + 19), v14, Src);
  if ( v8 < 0 )
    goto LABEL_30;
  v21 = 8 * (unsigned int)(((char *)Src[1] - (char *)Src[0]) >> 3);
  v22 = (struct _PaymentApplicationInformation *)CoTaskMemAlloc(v21);
  v7 = v22;
  if ( v22 )
  {
    if ( !v21 )
    {
LABEL_28:
      *a2 = 1022611261 * (((char *)Src[1] - (char *)Src[0]) >> 3);
      *a3 = v7;
      goto LABEL_34;
    }
    if ( Src[0] )
    {
      memcpy_0(v22, Src[0], (unsigned int)v21);
      goto LABEL_28;
    }
    memset_0(v22, 0, (unsigned int)v21);
    *(_DWORD *)_o__errno(v24, v23, v25) = 22;
    invalid_parameter_noinfo();
    v8 = -2147418113;
  }
  else
  {
LABEL_12:
    v8 = -2147024882;
  }
LABEL_30:
  v26 = (LPVOID *)Src[0];
  v27 = (LPVOID *)Src[1];
  while ( v26 != v27 )
  {
    CoTaskMemFree(v26[20]);
    v26 += 21;
  }
  CoTaskMemFree(v7);
LABEL_34:
  LeaveCriticalSection(v6);
  std::vector<_PaymentApplicationInformation>::~vector<_PaymentApplicationInformation>(Src);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180031018  mov     [rsp+arg_10], r8
0x18003101d  mov     [rsp+arg_8], rdx
0x180031022  push    rbx
0x180031023  push    rsi
0x180031024  push    rdi
0x180031025  push    r12
0x180031027  push    r13
0x180031029  push    r14
0x18003102b  push    r15
0x18003102d  sub     rsp, 100h
0x180031034  mov     rbx, r8
0x180031037  mov     r15, rdx
0x18003103a  mov     rsi, rcx
0x18003103d  xorps   xmm0, xmm0
0x180031040  movdqu  xmmword ptr [rsp+138h+Src], xmm0
0x180031046  xor     edi, edi
0x180031048  mov     [rsp+138h+var_108], rdi
0x18003104d  lea     r12, [rcx+50h]
0x180031051  mov     [rsp+138h+var_100], r12
0x180031056  mov     rcx, r12; lpCriticalSection
0x180031059  call    cs:__imp_EnterCriticalSection
0x18003105f  mov     [rsp+138h+var_F8], 1
0x180031064  mov     r14d, edi
0x180031067  test    r15, r15
0x18003106a  jnz     short loc_180031076
0x18003106c  mov     ebx, 80004003h
0x180031071  jmp     loc_180031385
0x180031076  test    rbx, rbx
0x180031079  jz      short loc_18003106C
0x18003107b  cmp     [rsi+0B1h], dil
0x180031082  jnz     short loc_18003108E
0x180031084  mov     ebx, 8007139Fh
0x180031089  jmp     loc_180031385
0x18003108e  cmp     [rsi+0B0h], dil
0x180031095  jnz     short loc_1800310A6
0x180031097  mov     rcx, rsi; this
0x18003109a  call    ?IsLegacyUiccSelectionAvailable@RoutingMgr@@AEAA_NXZ; RoutingMgr::IsLegacyUiccSelectionAvailable(void)
0x18003109f  test    al, al
0x1800310a1  mov     r8d, edi
0x1800310a4  jnz     short loc_1800310AC
0x1800310a6  mov     r8d, 1
0x1800310ac  mov     rcx, rsi; this
0x1800310af  call    ?IsLegacyUiccSelectionAvailable@RoutingMgr@@AEAA_NXZ; RoutingMgr::IsLegacyUiccSelectionAvailable(void)
0x1800310b4  nop
0x1800310b5  lea     ebx, [r8+1]
0x1800310b9  test    al, al
0x1800310bb  cmovz   ebx, r8d
0x1800310bf  mov     r13d, 0A0h
0x1800310c5  mov     r8d, r13d; Size
0x1800310c8  xor     edx, edx; Val
0x1800310ca  lea     rcx, [rsp+138h+var_E8]; void *
0x1800310cf  call    memset_0
0x1800310d4  mov     [rsp+138h+var_48], rdi
0x1800310dc  lea     rdx, [rsp+138h+var_E8]
0x1800310e1  lea     rcx, [rsp+138h+Src]
0x1800310e6  call    ?push_back@?$vector@U_PaymentApplicationInformation@@V?$allocator@U_PaymentApplicationInformation@@@std@@@std@@QEAAXAEBU_PaymentApplicationInformation@@@Z; std::vector<_PaymentApplicationInformation>::push_back(_PaymentApplicationInformation const &)
0x1800310eb  nop
0x1800310ec  xor     edx, edx; Val
0x1800310ee  mov     r8d, 82h; Size
0x1800310f4  mov     rcx, [rsp+138h+Src]; void *
0x1800310f9  call    memset_0
0x1800310fe  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180031105  mov     rax, [rsp+138h+Src]
0x18003110a  movdqu  xmmword ptr [rax+84h], xmm0
0x180031112  cmp     [rsi+0C4h], di
0x180031119  setz    cl
0x18003111c  mov     rax, [rsp+138h+Src]
0x180031121  mov     [rax+94h], cl
0x180031127  mov     rax, [rsp+138h+Src]
0x18003112c  mov     [rax+98h], ebx
0x180031132  lea     rcx, [rbx+rbx*4]
0x180031136  shl     rcx, 5; cb
0x18003113a  call    cs:__imp_CoTaskMemAlloc
0x180031140  mov     rcx, rax
0x180031143  mov     rax, [rsp+138h+Src]
0x180031148  mov     [rax+0A0h], rcx
0x18003114f  mov     rax, [rsp+138h+Src]
0x180031154  cmp     [rax+0A0h], rdi
0x18003115b  jnz     short loc_180031167
0x18003115d  mov     ebx, 8007000Eh
0x180031162  jmp     loc_180031385
0x180031167  cmp     [rsi+0B0h], dil
0x18003116e  jnz     short loc_18003118D
0x180031170  mov     rcx, rsi; this
0x180031173  call    ?IsLegacyUiccSelectionAvailable@RoutingMgr@@AEAA_NXZ; RoutingMgr::IsLegacyUiccSelectionAvailable(void)
0x180031178  test    al, al
0x18003117a  jz      short loc_18003118D
0x18003117c  lea     r15, [rsi+0B4h]
0x180031183  mov     r13, rdi
0x180031186  mov     ebx, 98h
0x18003118b  jmp     short loc_1800311FB
0x18003118d  lea     r15, [rsi+0B4h]
0x180031194  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18003119b  sub     rax, [r15]
0x18003119e  jnz     short loc_1800311AB
0x1800311a0  mov     rax, qword ptr cs:GUID_NULL.Data4
0x1800311a7  sub     rax, [r15+8]
0x1800311ab  test    rax, rax
0x1800311ae  setz    dl
0x1800311b1  mov     rax, [rsp+138h+Src]
0x1800311b6  mov     rcx, [rax+0A0h]; void *
0x1800311bd  mov     byte ptr [rcx+95h], 1
0x1800311c4  mov     [rcx+9Ch], edi
0x1800311ca  mov     [rcx+94h], dl
0x1800311d0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800311d7  movdqu  xmmword ptr [rcx+84h], xmm0
0x1800311df  mov     dword ptr [rcx+98h], 2
0x1800311e9  xor     edx, edx; Val
0x1800311eb  mov     r8d, 82h; Size
0x1800311f1  call    memset_0
0x1800311f6  mov     ebx, 138h
0x1800311fb  mov     rcx, rsi; this
0x1800311fe  call    ?IsLegacyUiccSelectionAvailable@RoutingMgr@@AEAA_NXZ; RoutingMgr::IsLegacyUiccSelectionAvailable(void)
0x180031203  test    al, al
0x180031205  jz      loc_1800312BE
0x18003120b  mov     rax, qword ptr cs:NFC_PAYMENT_APPLICATION_LEGACY_UICC_GUID
0x180031212  sub     rax, [r15]
0x180031215  jnz     short loc_180031222
0x180031217  mov     rax, qword ptr cs:NFC_PAYMENT_APPLICATION_LEGACY_UICC_GUID+8
0x18003121e  sub     rax, [r15+8]
0x180031222  test    rax, rax
0x180031225  setz    dl
0x180031228  mov     rax, [rsp+138h+Src]
0x18003122d  mov     rcx, [rax+0A0h]
0x180031234  add     rcx, r13; void *
0x180031237  mov     byte ptr [rcx+95h], 1
0x18003123e  mov     [rcx+9Ch], edi
0x180031244  mov     [rcx+94h], dl
0x18003124a  movups  xmm0, cs:NFC_PAYMENT_APPLICATION_LEGACY_UICC_GUID
0x180031251  movdqu  xmmword ptr [rcx+84h], xmm0
0x180031259  mov     dword ptr [rcx+98h], 2
0x180031263  xor     edx, edx; Val
0x180031265  mov     r8d, 82h; Size
0x18003126b  call    memset_0
0x180031270  mov     rax, [rsp+138h+Src]
0x180031275  mov     rcx, [rax+0A0h]
0x18003127c  mov     dword ptr [rbx+rcx], 1
0x180031283  mov     rax, [rsp+138h+Src]
0x180031288  mov     rbx, [rax+0A0h]
0x18003128f  add     rbx, r13
0x180031292  xor     edx, edx; Val
0x180031294  mov     r8d, 82h; Size
0x18003129a  mov     rcx, rbx; void *
0x18003129d  call    memset_0
0x1800312a2  mov     r9d, 41h ; 'A'; unsigned int
0x1800312a8  mov     r8, rbx; unsigned __int16 *
0x1800312ab  lea     rdx, aUiccapplicatio; "UICCApplicationName"
0x1800312b2  lea     rcx, qword_1800A1C08; struct NfcRegistryLocation *
0x1800312b9  call    ?GetString@NfcRegUtils@@SAJAEBUNfcRegistryLocation@@PEBGPEAGK@Z; NfcRegUtils::GetString(NfcRegistryLocation const &,ushort const *,ushort *,ulong)
0x1800312be  lea     r8, [rsp+138h+Src]
0x1800312c3  mov     rdx, r15
0x1800312c6  mov     rcx, [rsi+98h]
0x1800312cd  call    ?AddPaymentApplicationsToList@RoutingRegistrationStore@@QEAAJAEBUPaymentSelection@@AEAV?$vector@U_PaymentApplicationInformation@@V?$allocator@U_PaymentApplicationInformation@@@std@@@std@@@Z; RoutingRegistrationStore::AddPaymentApplicationsToList(PaymentSelection const &,std::vector<_PaymentApplicationInformation> &)
0x1800312d2  mov     ebx, eax
0x1800312d4  test    eax, eax
0x1800312d6  js      loc_180031385
0x1800312dc  mov     rax, [rsp+138h+Src+8]
0x1800312e1  sub     rax, [rsp+138h+Src]
0x1800312e6  sar     rax, 3
0x1800312ea  mov     r15, 0CF3CF3CF3CF3CF3Dh
0x1800312f4  imul    rax, r15
0x1800312f8  imul    eax, 0A8h
0x1800312fe  mov     esi, eax
0x180031300  mov     ecx, eax; cb
0x180031302  call    cs:__imp_CoTaskMemAlloc
0x180031308  mov     r14, rax
0x18003130b  test    rax, rax
0x18003130e  jz      loc_18003115D
0x180031314  test    rsi, rsi
0x180031317  jz      short loc_18003132E
0x180031319  mov     rdx, [rsp+138h+Src]; Val
0x18003131e  mov     r8d, esi; Size
0x180031321  mov     rcx, rax; void *
0x180031324  test    rdx, rdx
0x180031327  jz      short loc_180031357
0x180031329  call    memcpy_0
0x18003132e  mov     rax, [rsp+138h+Src+8]
0x180031333  sub     rax, [rsp+138h+Src]
0x180031338  sar     rax, 3
0x18003133c  imul    rax, r15
0x180031340  mov     rcx, [rsp+138h+arg_8]
0x180031348  mov     [rcx], eax
0x18003134a  mov     rax, [rsp+138h+arg_10]
0x180031352  mov     [rax], r14
0x180031355  jmp     short loc_1800313B4
0x180031357  call    memset_0
0x18003135c  call    cs:__imp__o__errno
0x180031362  mov     dword ptr [rax], 16h
0x180031368  call    _invalid_parameter_noinfo
0x18003136d  mov     ebx, 8000FFFFh
0x180031372  jmp     short loc_180031385
0x180031374  xor     edi, edi
0x180031376  mov     r14d, edi
0x180031379  mov     ebx, [rsp+138h+arg_0]
0x180031380  mov     r12, [rsp+138h+var_100]
0x180031385  mov     rdi, [rsp+138h+Src]
0x18003138a  mov     rsi, [rsp+138h+Src+8]
0x18003138f  jmp     short loc_1800313A5
0x180031391  mov     rcx, [rdi+0A0h]; pv
0x180031398  call    cs:__imp_CoTaskMemFree
0x18003139e  add     rdi, 0A8h
0x1800313a5  cmp     rdi, rsi
0x1800313a8  jnz     short loc_180031391
0x1800313aa  mov     rcx, r14; pv
0x1800313ad  call    cs:__imp_CoTaskMemFree
0x1800313b3  nop
0x1800313b4  mov     rcx, r12; lpCriticalSection
0x1800313b7  call    cs:__imp_LeaveCriticalSection
0x1800313bd  nop
0x1800313be  lea     rcx, [rsp+138h+Src]
0x1800313c3  call    ??1?$vector@U_PaymentApplicationInformation@@V?$allocator@U_PaymentApplicationInformation@@@std@@@std@@QEAA@XZ; std::vector<_PaymentApplicationInformation>::~vector<_PaymentApplicationInformation>(void)
0x1800313c8  mov     eax, ebx
0x1800313ca  add     rsp, 100h
0x1800313d1  pop     r15
0x1800313d3  pop     r14
0x1800313d5  pop     r13
0x1800313d7  pop     r12
0x1800313d9  pop     rdi
0x1800313da  pop     rsi
0x1800313db  pop     rbx
0x1800313dc  retn
```
