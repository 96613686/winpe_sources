# SharingToken::Materialize(JET_RETRIEVECOLUMN *)

- ea: `0x180011d20`
- end: `0x180011ebe`
- name: `?Materialize@SharingToken@@UEAAJPEAUJET_RETRIEVECOLUMN@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(SharingToken *__hidden this, struct JET_RETRIEVECOLUMN *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180013e00`

## callees

- `0x180006e2c`
- `0x180006f78`
- `0x18000bf80`
- `0x18000c774`
- `0x18000f218`
- `0x18000f468`
- `0x180011d20`
- `0x180019824`
- `0x1800198a0`

## string_xrefs

- `0x180011e09`: `SharingToken::Materialize failed. HR=0x%x`
- `0x180011e1a`: `SharingToken::Materialize`

## pseudocode

```c
__int64 __fastcall SharingToken::Materialize(SharingToken *this, struct JET_RETRIEVECOLUMN *a2)
{
  const double *v4; // rdx
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int128 v7; // xmm6
  void *pvData; // rsi
  __int128 v9; // xmm7
  int v10; // r14d
  const double *v11; // rdx
  int v12; // r15d
  int v13; // ebx
  int *v14; // rax
  const struct _FILETIME *v15; // r8
  int FileTimeSpanInMilliSeconds; // eax
  __int128 v17; // xmm1
  __int64 v18; // r9
  int v19; // edx
  int v20; // ecx
  struct _FILETIME v22[4]; // [rsp+38h] [rbp-39h] BYREF
  _BYTE v23[8]; // [rsp+58h] [rbp-19h] BYREF
  _BYTE v24[16]; // [rsp+60h] [rbp-11h] BYREF

  memset(v22, 0, sizeof(v22));
  ShareAccessControl::ShareAccessControl((ShareAccessControl *)v23);
  if ( !a2 )
  {
    v6 = -2147024809;
LABEL_8:
    v14 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v5);
    DSLogger::LogError(
      (DSLogger *)v14,
      L"SharingToken::Materialize",
      294,
      L"SharingToken::Materialize failed. HR=0x%x",
      v6);
    goto LABEL_12;
  }
  v7 = *(_OWORD *)a2->pvData;
  if ( a2[2].err == 1004 )
    pvData = 0;
  else
    pvData = a2[2].pvData;
  v9 = *(_OWORD *)a2[3].pvData;
  v10 = *(_DWORD *)a2[4].pvData;
  v22[2] = *(struct _FILETIME *)a2[5].pvData;
  v22[0] = DSUtils::GetFileTimeFromDaysSince1900((DSUtils *)&v22[2], v4);
  v22[3] = *(struct _FILETIME *)a2[6].pvData;
  v22[1] = DSUtils::GetFileTimeFromDaysSince1900((DSUtils *)&v22[3], v11);
  v12 = *(_DWORD *)a2[7].pvData;
  v13 = *(_DWORD *)a2[8].pvData;
  *(_OWORD *)((char *)this + 12) = v7;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 32,
                           pvData) )
  {
    v6 = -2147024882;
    goto LABEL_8;
  }
  *((_OWORD *)this + 4) = v9;
  *((_DWORD *)this + 20) = v10;
  tlx::_LazyImpl<TokenLifeManager,tlx::lazy_construct<TokenLifeManager>,tlx::static_lazy<TokenLifeManager,0,tlx::lazy_construct<TokenLifeManager>>>::get(v5);
  FileTimeSpanInMilliSeconds = DSUtils::GetFileTimeSpanInMilliSeconds((DSUtils *)v22, &v22[1], v15);
  v17 = *(_OWORD *)&v22[2].dwLowDateTime;
  v19 = FileTimeSpanInMilliSeconds / 1000 - *(_DWORD *)(v18 + 4);
  *(_OWORD *)((char *)this + 88) = *(_OWORD *)&v22[0].dwLowDateTime;
  v20 = -v19;
  *(_OWORD *)((char *)this + 104) = v17;
  if ( v19 > 0 )
    v20 = v19;
  *((_DWORD *)this + 21) = v20 <= 1;
  *((_DWORD *)this + 31) = v13;
  v6 = 0;
  *((_DWORD *)this + 30) = v12;
LABEL_12:
  utl::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::clear(v24);
  return v6;
}

```

## disassembly

```asm
0x180011d20  mov     rax, rsp
0x180011d23  push    rbp
0x180011d24  push    rbx
0x180011d25  push    rsi
0x180011d26  push    rdi
0x180011d27  push    r14
0x180011d29  push    r15
0x180011d2b  lea     rbp, [rax-5Fh]
0x180011d2f  sub     rsp, 98h
0x180011d36  xorps   xmm0, xmm0
0x180011d39  movaps  xmmword ptr [rax-48h], xmm6
0x180011d3d  mov     rdi, rcx
0x180011d40  movaps  xmmword ptr [rax-58h], xmm7
0x180011d44  movups  xmmword ptr [rbp+57h+var_90.dwHighDateTime], xmm0
0x180011d48  lea     rcx, [rbp+57h+var_70]; this
0x180011d4c  mov     [rbp+57h+var_90.dwLowDateTime], 0
0x180011d53  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180011d57  mov     rbx, rdx
0x180011d5a  call    ??0ShareAccessControl@@QEAA@XZ; ShareAccessControl::ShareAccessControl(void)
0x180011d5f  test    rbx, rbx
0x180011d62  jnz     short loc_180011D6E
0x180011d64  mov     ebx, 80070057h
0x180011d69  jmp     loc_180011E04
0x180011d6e  cmp     dword ptr [rbx+88h], 3ECh
0x180011d78  mov     rax, [rbx+8]
0x180011d7c  movups  xmm6, xmmword ptr [rax]
0x180011d7f  jz      short loc_180011D87
0x180011d81  mov     rsi, [rbx+68h]
0x180011d85  jmp     short loc_180011D89
0x180011d87  xor     esi, esi
0x180011d89  mov     rax, [rbx+98h]
0x180011d90  lea     rcx, [rbp+57h+var_80]; this
0x180011d94  movups  xmm7, xmmword ptr [rax]
0x180011d97  mov     rax, [rbx+0C8h]
0x180011d9e  mov     r14d, [rax]
0x180011da1  mov     rax, [rbx+0F8h]
0x180011da8  movsd   xmm0, qword ptr [rax]
0x180011dac  movsd   qword ptr [rbp+57h+var_80], xmm0
0x180011db1  call    ?GetFileTimeFromDaysSince1900@DSUtils@@YA?AU_FILETIME@@AEBN@Z; DSUtils::GetFileTimeFromDaysSince1900(double const &)
0x180011db6  mov     qword ptr [rbp+57h+var_90.dwLowDateTime], rax
0x180011dba  lea     rcx, [rbp+57h+var_78]; this
0x180011dbe  mov     rax, [rbx+128h]
0x180011dc5  movsd   xmm0, qword ptr [rax]
0x180011dc9  movsd   [rbp+57h+var_78], xmm0
0x180011dce  call    ?GetFileTimeFromDaysSince1900@DSUtils@@YA?AU_FILETIME@@AEBN@Z; DSUtils::GetFileTimeFromDaysSince1900(double const &)
0x180011dd3  mov     qword ptr [rbp+57h+var_90.dwLowDateTime+8], rax
0x180011dd7  lea     rcx, [rdi+20h]
0x180011ddb  mov     rax, [rbx+158h]
0x180011de2  mov     rdx, rsi
0x180011de5  mov     r15d, [rax]
0x180011de8  mov     rax, [rbx+188h]
0x180011def  mov     ebx, [rax]
0x180011df1  movdqu  xmmword ptr [rdi+0Ch], xmm6
0x180011df6  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180011dfb  test    al, al
0x180011dfd  jnz     short loc_180011E2B
0x180011dff  mov     ebx, 8007000Eh
0x180011e04  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180011e09  lea     r9, aSharingtokenMa; "SharingToken::Materialize failed. HR=0x"...
0x180011e10  mov     [rsp+20h], ebx
0x180011e14  mov     r8d, 126h; unsigned int
0x180011e1a  lea     rdx, aSharingtokenMa_0; "SharingToken::Materialize"
0x180011e21  mov     rcx, rax; this
0x180011e24  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180011e29  jmp     short loc_180011E96
0x180011e2b  movdqu  xmmword ptr [rdi+40h], xmm7
0x180011e30  mov     [rdi+50h], r14d
0x180011e34  call    ?get@?$_LazyImpl@VTokenLifeManager@@V?$lazy_construct@VTokenLifeManager@@@tlx@@V?$static_lazy@VTokenLifeManager@@$0A@V?$lazy_construct@VTokenLifeManager@@@tlx@@@3@@tlx@@QEAAAEAVTokenLifeManager@@XZ; tlx::_LazyImpl<TokenLifeManager,tlx::lazy_construct<TokenLifeManager>,tlx::static_lazy<TokenLifeManager,0,tlx::lazy_construct<TokenLifeManager>>>::get(void)
0x180011e39  lea     rdx, [rbp+57h+var_90.dwLowDateTime+8]; struct _FILETIME *
0x180011e3d  mov     r9, rax
0x180011e40  lea     rcx, [rbp+57h+var_90]; this
0x180011e44  call    ?GetFileTimeSpanInMilliSeconds@DSUtils@@YA_JAEBU_FILETIME@@0@Z; DSUtils::GetFileTimeSpanInMilliSeconds(_FILETIME const &,_FILETIME const &)
0x180011e49  movups  xmm0, xmmword ptr [rbp+57h+var_90.dwLowDateTime]
0x180011e4d  mov     r8, rax
0x180011e50  mov     rax, 20C49BA5E353F7CFh
0x180011e5a  movups  xmm1, xmmword ptr [rbp-29h]
0x180011e5e  imul    r8
0x180011e61  sar     rdx, 7
0x180011e65  mov     rcx, rdx
0x180011e68  shr     rcx, 3Fh
0x180011e6c  add     rdx, rcx
0x180011e6f  sub     edx, [r9+4]
0x180011e73  movups  xmmword ptr [rdi+58h], xmm0
0x180011e77  mov     ecx, edx
0x180011e79  neg     ecx
0x180011e7b  movups  xmmword ptr [rdi+68h], xmm1
0x180011e7f  cmovs   ecx, edx
0x180011e82  xor     eax, eax
0x180011e84  cmp     ecx, 1
0x180011e87  setle   al
0x180011e8a  mov     [rdi+54h], eax
0x180011e8d  mov     [rdi+7Ch], ebx
0x180011e90  xor     ebx, ebx
0x180011e92  mov     [rdi+78h], r15d
0x180011e96  lea     rcx, [rbp+57h+var_68]
0x180011e9a  call    ?clear@?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAAXXZ; utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::clear(void)
0x180011e9f  movaps  xmm6, [rsp+0C0h+var_48+8]
0x180011ea7  mov     eax, ebx
0x180011ea9  movaps  xmm7, [rsp+0C0h+var_58+8]
0x180011eae  add     rsp, 98h
0x180011eb5  pop     r15
0x180011eb7  pop     r14
0x180011eb9  pop     rdi
0x180011eba  pop     rsi
0x180011ebb  pop     rbx
0x180011ebc  pop     rbp
0x180011ebd  retn
```
