# CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRemoveSBCPToken(CodeIntegrity::Management::AuthorizationToken const &)

- ea: `0x18001417c`
- end: `0x1800144b9`
- name: `?InstrumentRemoveSBCPToken@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVAuthorizationToken@45@@Z`
- size: `829`
- prototype: `void __fastcall(CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *__hidden this, const struct CodeIntegrity::Management::AuthorizationToken *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011d00`

## callees

- `0x1800019bc`
- `0x180001c28`
- `0x18000387c`
- `0x18000828c`
- `0x18000830c`
- `0x18000e7d8`
- `0x18001417c`
- `0x180014ce4`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRemoveSBCPToken(
        CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *this,
        const struct CodeIntegrity::Management::AuthorizationToken *a2)
{
  __int64 v4; // rdx
  unsigned __int64 v5; // rdi
  __int64 v6; // rdx
  unsigned __int64 v7; // rdi
  __int64 v8; // rdx
  unsigned __int64 v9; // rdi
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  int *v13; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v14; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v15; // [rsp+70h] [rbp-98h] BYREF
  __int16 v16; // [rsp+78h] [rbp-90h]
  __int64 v17; // [rsp+88h] [rbp-80h] BYREF
  __int16 v18; // [rsp+90h] [rbp-78h]
  __int64 v19; // [rsp+A0h] [rbp-68h] BYREF
  __int16 v20; // [rsp+A8h] [rbp-60h]
  __int64 v21; // [rsp+B8h] [rbp-50h] BYREF
  __int16 v22; // [rsp+C0h] [rbp-48h]
  __int64 v23; // [rsp+C8h] [rbp-40h] BYREF
  __int16 v24; // [rsp+D0h] [rbp-38h]
  __int64 v25; // [rsp+D8h] [rbp-30h] BYREF
  __int16 v26; // [rsp+E0h] [rbp-28h]
  char v27; // [rsp+118h] [rbp+10h] BYREF
  int v28; // [rsp+120h] [rbp+18h] BYREF
  int *v29; // [rsp+128h] [rbp+20h] BYREF

  v27 = 0;
  std::vector<unsigned char>::vector<unsigned char>(
    &v19,
    (*((_QWORD *)a2 + 18) - *((_QWORD *)a2 + 17)) & 0xFFFFFFFFFFFFFFE0uLL,
    &v27);
  v27 = 0;
  std::vector<unsigned char>::vector<unsigned char>(
    &v17,
    16 * ((__int64)(*((_QWORD *)a2 + 21) - *((_QWORD *)a2 + 20)) >> 4),
    &v27);
  v27 = 0;
  std::vector<unsigned char>::vector<unsigned char>(
    &v15,
    (*((_QWORD *)a2 + 24) - *((_QWORD *)a2 + 23)) & 0xFFFFFFFFFFFFFFC0uLL,
    &v27);
  v4 = *((_QWORD *)a2 + 17);
  if ( (*((_QWORD *)a2 + 18) - v4) >> 5 )
  {
    v5 = 0;
    do
    {
      memmove_0((void *)(v19 + 32 * v5), (const void *)(32 * v5 + v4), 0x20u);
      ++v5;
      v4 = *((_QWORD *)a2 + 17);
    }
    while ( v5 < (*((_QWORD *)a2 + 18) - v4) >> 5 );
  }
  v6 = *((_QWORD *)a2 + 20);
  if ( 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)a2 + 21) - v6) >> 4) )
  {
    v7 = 0;
    do
    {
      memmove_0((void *)(v17 + 48 * v7), (const void *)(48 * v7 + v6), 0x30u);
      ++v7;
      v6 = *((_QWORD *)a2 + 20);
    }
    while ( v7 < 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)a2 + 21) - v6) >> 4) );
  }
  v8 = *((_QWORD *)a2 + 23);
  if ( (*((_QWORD *)a2 + 24) - v8) >> 6 )
  {
    v9 = 0;
    do
    {
      memmove_0((void *)(v15 + (v9 << 6)), (const void *)((v9 << 6) + v8), 0x40u);
      ++v9;
      v8 = *((_QWORD *)a2 + 23);
    }
    while ( v9 < (*((_QWORD *)a2 + 24) - v8) >> 6 );
  }
  v10 = CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider();
  if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL, v11) )
  {
    v28 = 0;
    v21 = v15;
    v22 = v16 - v15;
    v23 = v17;
    v24 = v18 - v17;
    v25 = v19;
    v26 = v20 - v19;
    v27 = *((_BYTE *)a2 + 224);
    v29 = (int *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v13 = (int *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v14 = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(
      v12,
      (__int64)&byte_1800318AF,
      *((_QWORD *)this + 34) + 8LL,
      v12,
      (__int64)&v14,
      &v13,
      &v29,
      (__int64)&v27,
      &v25,
      &v23,
      &v21,
      (__int64)&v28);
  }
  std::vector<unsigned char>::_Tidy((__int64)&v15);
  std::vector<unsigned char>::_Tidy((__int64)&v17);
  std::vector<unsigned char>::_Tidy((__int64)&v19);
}

```

## disassembly

```asm
0x18001417c  mov     rax, rsp
0x18001417f  mov     [rax+8], rbx
0x180014183  push    rsi
0x180014184  push    rdi
0x180014185  push    r15
0x180014187  sub     rsp, 0F0h
0x18001418e  mov     rbx, rdx
0x180014191  mov     rsi, rcx
0x180014194  mov     byte ptr [rax+10h], 0
0x180014198  mov     rdx, [rdx+90h]
0x18001419f  sub     rdx, [rbx+88h]
0x1800141a6  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800141aa  lea     r8, [rax+10h]
0x1800141ae  lea     rcx, [rax-68h]
0x1800141b2  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x1800141b7  nop
0x1800141b8  mov     [rsp+108h+arg_8], 0
0x1800141c0  mov     rax, [rbx+0A8h]
0x1800141c7  sub     rax, [rbx+0A0h]
0x1800141ce  sar     rax, 4
0x1800141d2  mov     r15, 0AAAAAAAAAAAAAAABh
0x1800141dc  imul    rax, r15
0x1800141e0  lea     rdx, [rax+rax*2]
0x1800141e4  shl     rdx, 4
0x1800141e8  lea     r8, [rsp+108h+arg_8]
0x1800141f0  lea     rcx, [rsp+108h+var_80]
0x1800141f8  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x1800141fd  nop
0x1800141fe  mov     [rsp+108h+arg_8], 0
0x180014206  mov     rdx, [rbx+0C0h]
0x18001420d  sub     rdx, [rbx+0B8h]
0x180014214  and     rdx, 0FFFFFFFFFFFFFFC0h
0x180014218  lea     r8, [rsp+108h+arg_8]
0x180014220  lea     rcx, [rsp+108h+var_98]
0x180014225  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x18001422a  mov     rdx, [rbx+88h]
0x180014231  mov     rax, [rbx+90h]
0x180014238  sub     rax, rdx
0x18001423b  sar     rax, 5
0x18001423f  test    rax, rax
0x180014242  jz      short loc_180014280
0x180014244  xor     edi, edi
0x180014246  mov     rcx, rdi
0x180014249  shl     rcx, 5
0x18001424d  add     rdx, rcx; Src
0x180014250  add     rcx, [rsp+108h+var_68]; void *
0x180014258  mov     r8d, 20h ; ' '; Size
0x18001425e  call    memmove_0
0x180014263  inc     rdi
0x180014266  mov     rdx, [rbx+88h]
0x18001426d  mov     rax, [rbx+90h]
0x180014274  sub     rax, rdx
0x180014277  sar     rax, 5
0x18001427b  cmp     rdi, rax
0x18001427e  jb      short loc_180014246
0x180014280  mov     rdx, [rbx+0A0h]
0x180014287  mov     rax, [rbx+0A8h]
0x18001428e  sub     rax, rdx
0x180014291  sar     rax, 4
0x180014295  imul    rax, r15
0x180014299  test    rax, rax
0x18001429c  jz      short loc_1800142DF
0x18001429e  xor     edi, edi
0x1800142a0  lea     rcx, [rdi+rdi*2]
0x1800142a4  shl     rcx, 4
0x1800142a8  add     rdx, rcx; Src
0x1800142ab  add     rcx, [rsp+108h+var_80]; void *
0x1800142b3  mov     r8d, 30h ; '0'; Size
0x1800142b9  call    memmove_0
0x1800142be  inc     rdi
0x1800142c1  mov     rdx, [rbx+0A0h]
0x1800142c8  mov     rax, [rbx+0A8h]
0x1800142cf  sub     rax, rdx
0x1800142d2  sar     rax, 4
0x1800142d6  imul    rax, r15
0x1800142da  cmp     rdi, rax
0x1800142dd  jb      short loc_1800142A0
0x1800142df  mov     rdx, [rbx+0B8h]
0x1800142e6  mov     rax, [rbx+0C0h]
0x1800142ed  sub     rax, rdx
0x1800142f0  sar     rax, 6
0x1800142f4  test    rax, rax
0x1800142f7  jz      short loc_180014332
0x1800142f9  xor     edi, edi
0x1800142fb  mov     rcx, rdi
0x1800142fe  shl     rcx, 6
0x180014302  add     rdx, rcx; Src
0x180014305  add     rcx, [rsp+108h+var_98]; void *
0x18001430a  mov     r8d, 40h ; '@'; Size
0x180014310  call    memmove_0
0x180014315  inc     rdi
0x180014318  mov     rdx, [rbx+0B8h]
0x18001431f  mov     rax, [rbx+0C0h]
0x180014326  sub     rax, rdx
0x180014329  sar     rax, 6
0x18001432d  cmp     rdi, rax
0x180014330  jb      short loc_1800142FB
0x180014332  call    ?Provider@ManageCIProvider@Telemetry@Management@CodeIntegrity@@SAPEBU_tlgProvider_t@@XZ; CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider(void)
0x180014337  mov     r9, rax
0x18001433a  mov     ecx, [rax]
0x18001433c  cmp     ecx, 5
0x18001433f  jbe     loc_18001447E
0x180014345  mov     rdx, 400000000000h
0x18001434f  mov     rcx, rax
0x180014352  call    _tlgKeywordOn
0x180014357  test    al, al
0x180014359  jz      loc_18001447E
0x18001435f  mov     [rsp+108h+arg_10], 0
0x18001436a  mov     rcx, [rsp+108h+var_98]
0x18001436f  mov     [rsp+108h+var_50], rcx
0x180014377  movzx   eax, [rsp+108h+var_90]
0x18001437c  sub     ax, cx
0x18001437f  mov     [rsp+108h+var_48], ax
0x180014387  mov     rcx, [rsp+108h+var_80]
0x18001438f  mov     [rsp+108h+var_40], rcx
0x180014397  movzx   eax, [rsp+108h+var_78]
0x18001439f  sub     ax, cx
0x1800143a2  mov     [rsp+108h+var_38], ax
0x1800143aa  mov     rcx, [rsp+108h+var_68]
0x1800143b2  mov     [rsp+108h+var_30], rcx
0x1800143ba  movzx   eax, [rsp+108h+var_60]
0x1800143c2  sub     ax, cx
0x1800143c5  mov     [rsp+108h+var_28], ax
0x1800143cd  mov     al, [rbx+0E0h]
0x1800143d3  mov     [rsp+108h+arg_8], al
0x1800143da  lea     rcx, [rbx+18h]
0x1800143de  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800143e3  mov     [rsp+108h+arg_18], rax
0x1800143eb  lea     rcx, [rbx+38h]
0x1800143ef  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800143f4  mov     [rsp+108h+var_A8], rax
0x1800143f9  mov     [rsp+108h+var_A0], 2000000h
0x180014402  mov     r8, [rsi+110h]
0x180014409  add     r8, 8
0x18001440d  lea     rax, [rsp+108h+arg_10]
0x180014415  mov     [rsp+108h+var_B0], rax
0x18001441a  lea     rax, [rsp+108h+var_50]
0x180014422  mov     [rsp+108h+var_B8], rax
0x180014427  lea     rax, [rsp+108h+var_40]
0x18001442f  mov     [rsp+108h+var_C0], rax
0x180014434  lea     rax, [rsp+108h+var_30]
0x18001443c  mov     [rsp+108h+var_C8], rax
0x180014441  lea     rax, [rsp+108h+arg_8]
0x180014449  mov     [rsp+108h+var_D0], rax
0x18001444e  lea     rax, [rsp+108h+arg_18]
0x180014456  mov     [rsp+108h+var_D8], rax
0x18001445b  lea     rax, [rsp+108h+var_A8]
0x180014460  mov     [rsp+108h+var_E0], rax
0x180014465  lea     rax, [rsp+108h+var_A0]
0x18001446a  mov     [rsp+108h+var_E8], rax
0x18001446f  lea     rdx, byte_1800318AF
0x180014476  mov     rcx, r9
0x180014479  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperArray@$00@@U4@U4@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperArray@$00@@66AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &)
0x18001447e  lea     rcx, [rsp+108h+var_98]
0x180014483  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180014488  nop
0x180014489  lea     rcx, [rsp+108h+var_80]
0x180014491  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180014496  nop
0x180014497  lea     rcx, [rsp+108h+var_68]
0x18001449f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800144a4  nop
0x1800144a5  mov     rbx, [rsp+108h+arg_0]
0x1800144ad  add     rsp, 0F0h
0x1800144b4  pop     r15
0x1800144b6  pop     rdi
0x1800144b7  pop     rsi
0x1800144b8  retn
```
