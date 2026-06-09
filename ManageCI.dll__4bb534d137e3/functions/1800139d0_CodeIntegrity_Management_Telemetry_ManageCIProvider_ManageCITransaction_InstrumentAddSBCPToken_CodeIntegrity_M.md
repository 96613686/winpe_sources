# CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentAddSBCPToken(CodeIntegrity::Management::AuthorizationToken const &)

- ea: `0x1800139d0`
- end: `0x180013d0d`
- name: `?InstrumentAddSBCPToken@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVAuthorizationToken@45@@Z`
- size: `829`
- prototype: `void __fastcall(CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *__hidden this, const struct CodeIntegrity::Management::AuthorizationToken *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011f20`

## callees

- `0x1800019bc`
- `0x180001c28`
- `0x18000387c`
- `0x18000828c`
- `0x18000830c`
- `0x18000e7d8`
- `0x1800139d0`
- `0x180014ce4`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentAddSBCPToken(
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
  try
  {
    ((void (*)(void))std::vector<unsigned char>::vector<unsigned char>)();
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
        (__int64)byte_180031793,
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
  catch ( std::exception )
  {
  }
}

```

## disassembly

```asm
0x1800139d0  mov     rax, rsp
0x1800139d3  mov     [rax+8], rbx
0x1800139d7  push    rsi
0x1800139d8  push    rdi
0x1800139d9  push    r15
0x1800139db  sub     rsp, 0F0h
0x1800139e2  mov     rbx, rdx
0x1800139e5  mov     rsi, rcx
0x1800139e8  mov     byte ptr [rax+10h], 0
0x1800139ec  mov     rdx, [rdx+90h]
0x1800139f3  sub     rdx, [rbx+88h]
0x1800139fa  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800139fe  lea     r8, [rax+10h]
0x180013a02  lea     rcx, [rax-68h]
0x180013a06  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x180013a0b  nop
0x180013a0c  mov     [rsp+108h+arg_8], 0
0x180013a14  mov     rax, [rbx+0A8h]
0x180013a1b  sub     rax, [rbx+0A0h]
0x180013a22  sar     rax, 4
0x180013a26  mov     r15, 0AAAAAAAAAAAAAAABh
0x180013a30  imul    rax, r15
0x180013a34  lea     rdx, [rax+rax*2]
0x180013a38  shl     rdx, 4
0x180013a3c  lea     r8, [rsp+108h+arg_8]
0x180013a44  lea     rcx, [rsp+108h+var_80]
0x180013a4c  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x180013a51  nop
0x180013a52  mov     [rsp+108h+arg_8], 0
0x180013a5a  mov     rdx, [rbx+0C0h]
0x180013a61  sub     rdx, [rbx+0B8h]
0x180013a68  and     rdx, 0FFFFFFFFFFFFFFC0h
0x180013a6c  lea     r8, [rsp+108h+arg_8]
0x180013a74  lea     rcx, [rsp+108h+var_98]
0x180013a79  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x180013a7e  mov     rdx, [rbx+88h]
0x180013a85  mov     rax, [rbx+90h]
0x180013a8c  sub     rax, rdx
0x180013a8f  sar     rax, 5
0x180013a93  test    rax, rax
0x180013a96  jz      short loc_180013AD4
0x180013a98  xor     edi, edi
0x180013a9a  mov     rcx, rdi
0x180013a9d  shl     rcx, 5
0x180013aa1  add     rdx, rcx; Src
0x180013aa4  add     rcx, [rsp+108h+var_68]; void *
0x180013aac  mov     r8d, 20h ; ' '; Size
0x180013ab2  call    memmove_0
0x180013ab7  inc     rdi
0x180013aba  mov     rdx, [rbx+88h]
0x180013ac1  mov     rax, [rbx+90h]
0x180013ac8  sub     rax, rdx
0x180013acb  sar     rax, 5
0x180013acf  cmp     rdi, rax
0x180013ad2  jb      short loc_180013A9A
0x180013ad4  mov     rdx, [rbx+0A0h]
0x180013adb  mov     rax, [rbx+0A8h]
0x180013ae2  sub     rax, rdx
0x180013ae5  sar     rax, 4
0x180013ae9  imul    rax, r15
0x180013aed  test    rax, rax
0x180013af0  jz      short loc_180013B33
0x180013af2  xor     edi, edi
0x180013af4  lea     rcx, [rdi+rdi*2]
0x180013af8  shl     rcx, 4
0x180013afc  add     rdx, rcx; Src
0x180013aff  add     rcx, [rsp+108h+var_80]; void *
0x180013b07  mov     r8d, 30h ; '0'; Size
0x180013b0d  call    memmove_0
0x180013b12  inc     rdi
0x180013b15  mov     rdx, [rbx+0A0h]
0x180013b1c  mov     rax, [rbx+0A8h]
0x180013b23  sub     rax, rdx
0x180013b26  sar     rax, 4
0x180013b2a  imul    rax, r15
0x180013b2e  cmp     rdi, rax
0x180013b31  jb      short loc_180013AF4
0x180013b33  mov     rdx, [rbx+0B8h]
0x180013b3a  mov     rax, [rbx+0C0h]
0x180013b41  sub     rax, rdx
0x180013b44  sar     rax, 6
0x180013b48  test    rax, rax
0x180013b4b  jz      short loc_180013B86
0x180013b4d  xor     edi, edi
0x180013b4f  mov     rcx, rdi
0x180013b52  shl     rcx, 6
0x180013b56  add     rdx, rcx; Src
0x180013b59  add     rcx, [rsp+108h+var_98]; void *
0x180013b5e  mov     r8d, 40h ; '@'; Size
0x180013b64  call    memmove_0
0x180013b69  inc     rdi
0x180013b6c  mov     rdx, [rbx+0B8h]
0x180013b73  mov     rax, [rbx+0C0h]
0x180013b7a  sub     rax, rdx
0x180013b7d  sar     rax, 6
0x180013b81  cmp     rdi, rax
0x180013b84  jb      short loc_180013B4F
0x180013b86  call    ?Provider@ManageCIProvider@Telemetry@Management@CodeIntegrity@@SAPEBU_tlgProvider_t@@XZ; CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider(void)
0x180013b8b  mov     r9, rax
0x180013b8e  mov     ecx, [rax]
0x180013b90  cmp     ecx, 5
0x180013b93  jbe     loc_180013CD2
0x180013b99  mov     rdx, 400000000000h
0x180013ba3  mov     rcx, rax
0x180013ba6  call    _tlgKeywordOn
0x180013bab  test    al, al
0x180013bad  jz      loc_180013CD2
0x180013bb3  mov     [rsp+108h+arg_10], 0
0x180013bbe  mov     rcx, [rsp+108h+var_98]
0x180013bc3  mov     [rsp+108h+var_50], rcx
0x180013bcb  movzx   eax, [rsp+108h+var_90]
0x180013bd0  sub     ax, cx
0x180013bd3  mov     [rsp+108h+var_48], ax
0x180013bdb  mov     rcx, [rsp+108h+var_80]
0x180013be3  mov     [rsp+108h+var_40], rcx
0x180013beb  movzx   eax, [rsp+108h+var_78]
0x180013bf3  sub     ax, cx
0x180013bf6  mov     [rsp+108h+var_38], ax
0x180013bfe  mov     rcx, [rsp+108h+var_68]
0x180013c06  mov     [rsp+108h+var_30], rcx
0x180013c0e  movzx   eax, [rsp+108h+var_60]
0x180013c16  sub     ax, cx
0x180013c19  mov     [rsp+108h+var_28], ax
0x180013c21  mov     al, [rbx+0E0h]
0x180013c27  mov     [rsp+108h+arg_8], al
0x180013c2e  lea     rcx, [rbx+18h]
0x180013c32  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013c37  mov     [rsp+108h+arg_18], rax
0x180013c3f  lea     rcx, [rbx+38h]
0x180013c43  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013c48  mov     [rsp+108h+var_A8], rax
0x180013c4d  mov     [rsp+108h+var_A0], 2000000h
0x180013c56  mov     r8, [rsi+110h]
0x180013c5d  add     r8, 8
0x180013c61  lea     rax, [rsp+108h+arg_10]
0x180013c69  mov     [rsp+108h+var_B0], rax
0x180013c6e  lea     rax, [rsp+108h+var_50]
0x180013c76  mov     [rsp+108h+var_B8], rax
0x180013c7b  lea     rax, [rsp+108h+var_40]
0x180013c83  mov     [rsp+108h+var_C0], rax
0x180013c88  lea     rax, [rsp+108h+var_30]
0x180013c90  mov     [rsp+108h+var_C8], rax
0x180013c95  lea     rax, [rsp+108h+arg_8]
0x180013c9d  mov     [rsp+108h+var_D0], rax
0x180013ca2  lea     rax, [rsp+108h+arg_18]
0x180013caa  mov     [rsp+108h+var_D8], rax
0x180013caf  lea     rax, [rsp+108h+var_A8]
0x180013cb4  mov     [rsp+108h+var_E0], rax
0x180013cb9  lea     rax, [rsp+108h+var_A0]
0x180013cbe  mov     [rsp+108h+var_E8], rax
0x180013cc3  lea     rdx, byte_180031793
0x180013cca  mov     rcx, r9
0x180013ccd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperArray@$00@@U4@U4@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperArray@$00@@66AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &)
0x180013cd2  lea     rcx, [rsp+108h+var_98]
0x180013cd7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180013cdc  nop
0x180013cdd  lea     rcx, [rsp+108h+var_80]
0x180013ce5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180013cea  nop
0x180013ceb  lea     rcx, [rsp+108h+var_68]
0x180013cf3  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180013cf8  nop
0x180013cf9  mov     rbx, [rsp+108h+arg_0]
0x180013d01  add     rsp, 0F0h
0x180013d08  pop     r15
0x180013d0a  pop     rdi
0x180013d0b  pop     rsi
0x180013d0c  retn
```
