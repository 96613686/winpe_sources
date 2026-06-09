# Enrollments::StageEnrollment(uchar const *,unsigned __int64,void * const,uchar const *,unsigned __int64,uchar const *,unsigned __int64,uchar const *,unsigned __int64,uchar const *,unsigned __int64,uchar const *,unsigned __int64)

- ea: `0x14006216c`
- end: `0x140062534`
- name: `?StageEnrollment@Enrollments@@QEAAJPEBE_KQEAX0101010101@Z`
- size: `968`
- prototype: `__int64 __usercall@<rax>(Enrollments *__hidden this@<rcx>, const unsigned __int8 *@<rdx>, unsigned __int64@<r8>, void *const@<r9>, const unsigned __int8 *Buf2, size_t Size, const unsigned __int8 *, unsigned __int64, const unsigned __int8 *, unsigned __int64, const unsigned __int8 *, unsigned __int64, const unsigned __int8 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14006253c`

## callees

- `0x14000a420`
- `0x14000ae0c`
- `0x14001cb6c`
- `0x140040504`
- `0x1400408d0`
- `0x140040efc`
- `0x14005e858`
- `0x14005e8a8`
- `0x14005ea74`
- `0x14005f608`
- `0x14005f67c`
- `0x14005f810`
- `0x1400611d0`
- `0x14006216c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400621c4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400621c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140062509`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140062509`

## string_xrefs

- `0x1400622fc`: `onecore\ds\security\biometrics\service\trustlet\exe\secureenrollments.cpp`
- `0x1400622ae`: `StageEnrollment: Enrollment complete`
- `0x1400623fd`: `StageEnrollment: Enrollment not complete, bio already present`
- `0x14006243f`: `StageEnrollment: Enrollment not complete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Enrollments::StageEnrollment(
        Enrollments *this,
        const unsigned __int8 *a2,
        __int64 a3,
        char *a4,
        const unsigned __int8 *Buf2,
        size_t Size,
        const unsigned __int8 *a7,
        unsigned __int64 a8,
        const unsigned __int8 *a9,
        unsigned __int64 a10,
        const unsigned __int8 *a11,
        size_t a12,
        const unsigned __int8 *a13,
        size_t a14)
{
  __int64 v16; // r8
  __int64 v17; // r10
  DWORD LengthSid; // eax
  __int64 v19; // r8
  __int64 v20; // rdx
  int v21; // eax
  unsigned int v22; // ebx
  __int64 v23; // r9
  __int64 v24; // rdx
  _DWORD *v25; // rsi
  const void *v26; // rcx
  const void *v27; // rcx
  const void *v28; // rcx
  int v30[8]; // [rsp+20h] [rbp-A1h] BYREF
  int v31; // [rsp+40h] [rbp-81h] BYREF
  _BYTE v32[24]; // [rsp+48h] [rbp-79h] BYREF
  _BYTE v33[24]; // [rsp+60h] [rbp-61h] BYREF
  _BYTE v34[24]; // [rsp+78h] [rbp-49h] BYREF
  _BYTE v35[24]; // [rsp+90h] [rbp-31h] BYREF
  _BYTE v36[56]; // [rsp+A8h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+27h]

  anonymous_namespace_::Enrollment::Enrollment_0(&v31);
  v31 = 1;
  std::vector<unsigned char>::vector<unsigned char>(v30, v17, v17 + v16);
  std::vector<unsigned char>::operator=(v32, v30);
  std::vector<unsigned char>::_Tidy((__int64)v30);
  LengthSid = GetLengthSid(a4);
  std::vector<unsigned char>::vector<unsigned char>(v30, a4, &a4[LengthSid]);
  std::vector<unsigned char>::operator=(v33, v30);
  std::vector<unsigned char>::_Tidy((__int64)v30);
  std::vector<unsigned char>::vector<unsigned char>(v30, a7, &a7[a8]);
  std::vector<unsigned char>::operator=(v35, v30);
  std::vector<unsigned char>::_Tidy((__int64)v30);
  std::vector<unsigned char>::vector<unsigned char>(v30, a9, &a9[a10]);
  std::vector<unsigned char>::operator=(v36, v30);
  std::vector<unsigned char>::_Tidy((__int64)v30);
  v19 = *((_QWORD *)this + 22);
  v20 = *((_QWORD *)this + 21);
  if ( v20 == v19 )
  {
    v25 = (_DWORD *)*((_QWORD *)this + 18);
    if ( v25 == *((_DWORD **)this + 19) )
    {
      BioIsoProvider::TraceLoggingInfo("StageEnrollment: Enrollment not complete");
      if ( *((_QWORD *)this + 19) == *((_QWORD *)this + 20) )
      {
        std::vector__anonymous_namespace_::Enrollment_std::allocator__anonymous_namespace_::Enrollment___::_Emplace_reallocate__anonymous_namespace_::Enrollment_(
          (char *)this + 144,
          *((_QWORD *)this + 19),
          &v31);
      }
      else
      {
        anonymous_namespace_::Enrollment::Enrollment(*((_QWORD *)this + 19), &v31);
        *((_QWORD *)this + 19) += 128LL;
      }
      std::vector<unsigned char>::vector<unsigned char>(v30, Buf2, &Buf2[Size]);
      std::vector<unsigned char>::operator=((char *)this + 72, v30);
      std::vector<unsigned char>::_Tidy((__int64)v30);
      std::vector<unsigned char>::vector<unsigned char>(v30, a11, &a11[a12]);
      std::vector<unsigned char>::operator=((char *)this + 96, v30);
      std::vector<unsigned char>::_Tidy((__int64)v30);
      std::vector<unsigned char>::vector<unsigned char>(v30, a13, &a13[a14]);
      std::vector<unsigned char>::operator=((char *)this + 120, v30);
      std::vector<unsigned char>::_Tidy((__int64)v30);
    }
    else
    {
      if ( *v25 != v31 )
      {
        v24 = 572;
LABEL_10:
        v22 = -2146861026;
        v23 = 2148106270LL;
        goto LABEL_11;
      }
      if ( !(unsigned __int8)std::operator==<unsigned char,std::allocator<unsigned char>>(v25 + 8, v33) )
      {
        v24 = 573;
        goto LABEL_10;
      }
      if ( !(unsigned __int8)std::operator==<unsigned char,std::allocator<unsigned char>>(v25 + 20, v35) )
      {
        v24 = 574;
        goto LABEL_10;
      }
      if ( !(unsigned __int8)std::operator==<unsigned char,std::allocator<unsigned char>>(v25 + 26, v36) )
      {
        v24 = 575;
        goto LABEL_10;
      }
      v26 = (const void *)*((_QWORD *)this + 9);
      if ( *((_QWORD *)this + 10) - (_QWORD)v26 != Size )
      {
        v24 = 577;
        goto LABEL_10;
      }
      if ( memcmp_0(v26, Buf2, Size) )
      {
        v24 = 578;
        goto LABEL_10;
      }
      v27 = (const void *)*((_QWORD *)this + 12);
      if ( *((_QWORD *)this + 13) - (_QWORD)v27 != a12 )
      {
        v24 = 579;
        goto LABEL_10;
      }
      if ( memcmp_0(v27, a11, a12) )
      {
        v24 = 580;
        goto LABEL_10;
      }
      v28 = (const void *)*((_QWORD *)this + 15);
      if ( *((_QWORD *)this + 16) - (_QWORD)v28 != a14 )
      {
        v24 = 581;
        goto LABEL_10;
      }
      if ( memcmp_0(v28, a13, a14) )
      {
        v24 = 582;
        goto LABEL_10;
      }
      BioIsoProvider::TraceLoggingInfo("StageEnrollment: Enrollment not complete, bio already present");
      if ( *((_QWORD *)this + 19) == *((_QWORD *)this + 20) )
      {
        std::vector__anonymous_namespace_::Enrollment_std::allocator__anonymous_namespace_::Enrollment___::_Emplace_reallocate__anonymous_namespace_::Enrollment_(
          (char *)this + 144,
          *((_QWORD *)this + 19),
          &v31);
      }
      else
      {
        anonymous_namespace_::Enrollment::Enrollment(*((_QWORD *)this + 19), &v31);
        *((_QWORD *)this + 19) += 128LL;
      }
    }
    *((_QWORD *)this + 8) = GetTickCount64();
LABEL_38:
    v22 = 0;
    goto LABEL_39;
  }
  std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(v34, v20, v19 - v20);
  if ( *((_QWORD *)this + 19) == *((_QWORD *)this + 20) )
  {
    std::vector__anonymous_namespace_::Enrollment_std::allocator__anonymous_namespace_::Enrollment___::_Emplace_reallocate__anonymous_namespace_::Enrollment_(
      (char *)this + 144,
      *((_QWORD *)this + 19),
      &v31);
  }
  else
  {
    anonymous_namespace_::Enrollment::Enrollment(*((_QWORD *)this + 19), &v31);
    *((_QWORD *)this + 19) += 128LL;
  }
  BioIsoProvider::TraceLoggingInfo("StageEnrollment: Enrollment complete");
  v21 = (unsigned int)Enrollments::Enroll(this);
  v22 = v21;
  if ( v21 >= 0 )
    goto LABEL_38;
  v23 = (unsigned int)v21;
  v24 = 566;
LABEL_11:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v24,
    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureenrollments.cpp",
    (const char *)v23,
    v30[0]);
LABEL_39:
  anonymous_namespace_::Enrollment::_Enrollment(&v31);
  return v22;
}

```

## disassembly

```asm
0x14006216c  push    rbp
0x14006216e  push    rbx
0x14006216f  push    rsi
0x140062170  push    rdi
0x140062171  lea     rbp, [rsp-7]
0x140062176  sub     rsp, 0C8h
0x14006217d  mov     rbx, r9
0x140062180  mov     r10, rdx
0x140062183  mov     rdi, rcx
0x140062186  lea     rcx, [rsp+0E0h+var_A0]
0x14006218b  call    _anonymous_namespace___Enrollment__Enrollment_0
0x140062190  nop
0x140062191  mov     [rsp+0E0h+var_A0], 1
0x140062199  add     r8, r10
0x14006219c  mov     rdx, r10
0x14006219f  lea     rcx, [rsp+0E0h+var_C0]
0x1400621a4  call    ??$?0PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEBE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar const *,uchar const *,std::allocator<uchar> const &)
0x1400621a9  lea     rdx, [rsp+0E0h+var_C0]
0x1400621ae  lea     rcx, [rbp+1Fh+var_98]
0x1400621b2  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1400621b7  lea     rcx, [rsp+0E0h+var_C0]
0x1400621bc  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400621c1  mov     rcx, rbx; pSid
0x1400621c4  call    cs:__imp_GetLengthSid
0x1400621cb  nop     dword ptr [rax+rax+00h]
0x1400621d0  mov     r8d, eax
0x1400621d3  add     r8, rbx
0x1400621d6  mov     rdx, rbx
0x1400621d9  lea     rcx, [rsp+0E0h+var_C0]
0x1400621de  call    ??$?0PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEBE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar const *,uchar const *,std::allocator<uchar> const &)
0x1400621e3  lea     rdx, [rsp+0E0h+var_C0]
0x1400621e8  lea     rcx, [rbp+1Fh+var_80]
0x1400621ec  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1400621f1  lea     rcx, [rsp+0E0h+var_C0]
0x1400621f6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400621fb  mov     rdx, [rbp+1Fh+arg_30]
0x1400621ff  mov     r8, [rbp+1Fh+arg_38]
0x140062203  add     r8, rdx
0x140062206  lea     rcx, [rsp+0E0h+var_C0]
0x14006220b  call    ??$?0PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEBE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar const *,uchar const *,std::allocator<uchar> const &)
0x140062210  lea     rdx, [rsp+0E0h+var_C0]
0x140062215  lea     rcx, [rbp+1Fh+var_50]
0x140062219  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x14006221e  lea     rcx, [rsp+0E0h+var_C0]
0x140062223  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140062228  mov     rdx, [rbp+1Fh+arg_40]
0x14006222c  mov     r8, [rbp+1Fh+arg_48]
0x140062230  add     r8, rdx
0x140062233  lea     rcx, [rsp+0E0h+var_C0]
0x140062238  call    ??$?0PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEBE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar const *,uchar const *,std::allocator<uchar> const &)
0x14006223d  lea     rdx, [rsp+0E0h+var_C0]
0x140062242  lea     rcx, [rbp+1Fh+var_38]
0x140062246  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x14006224b  lea     rcx, [rsp+0E0h+var_C0]
0x140062250  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140062255  mov     r8, [rdi+0B0h]
0x14006225c  mov     rdx, [rdi+0A8h]
0x140062263  cmp     rdx, r8
0x140062266  setnz   al
0x140062269  lea     rbx, [rdi+90h]
0x140062270  test    al, al
0x140062272  jz      short loc_1400622D6
0x140062274  sub     r8, rdx
0x140062277  lea     rcx, [rbp+1Fh+var_68]
0x14006227b  call    ??$_Assign_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEBE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x140062280  mov     rax, [rbx+8]
0x140062284  cmp     rax, [rbx+10h]
0x140062288  jz      short loc_14006229E
0x14006228a  lea     rdx, [rsp+0E0h+var_A0]
0x14006228f  mov     rcx, rax
0x140062292  call    _anonymous_namespace___Enrollment__Enrollment
0x140062297  sub     qword ptr [rbx+8], 0FFFFFFFFFFFFFF80h
0x14006229c  jmp     short loc_1400622AE
0x14006229e  lea     r8, [rsp+0E0h+var_A0]
0x1400622a3  mov     rdx, rax
0x1400622a6  mov     rcx, rbx
0x1400622a9  call    std__vector__anonymous_namespace___Enrollment_std__allocator__anonymous_namespace___Enrollment______Emplace_reallocate__anonymous_namespace___Enrollment_
0x1400622ae  lea     rcx, aStageenrollmen; "StageEnrollment: Enrollment complete"
0x1400622b5  call    ?TraceLoggingInfo@BioIsoProvider@@SAXPEBDZZ; BioIsoProvider::TraceLoggingInfo(char const *,...)
0x1400622ba  mov     rcx, rdi; this
0x1400622bd  call    ?Enroll@Enrollments@@AEAAJXZ; Enrollments::Enroll(void)
0x1400622c2  mov     ebx, eax
0x1400622c4  test    eax, eax
0x1400622c6  jns     loc_140062519
0x1400622cc  mov     r9d, eax
0x1400622cf  mov     edx, 236h
0x1400622d4  jmp     short loc_1400622F8
0x1400622d6  mov     rsi, [rbx]
0x1400622d9  cmp     rsi, [rbx+8]
0x1400622dd  jz      loc_14006243F
0x1400622e3  mov     eax, [rsp+0E0h+var_A0]
0x1400622e7  cmp     [rsi], eax
0x1400622e9  jz      short loc_14006230D
0x1400622eb  mov     edx, 23Ch; void *
0x1400622f0  mov     ebx, 8009801Eh
0x1400622f5  mov     r9d, ebx; char *
0x1400622f8  mov     rcx, [rbp+27h]; this
0x1400622fc  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\biometrics\\serv"...
0x140062303  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140062308  jmp     loc_14006251B
0x14006230d  lea     rcx, [rsi+20h]
0x140062311  lea     rdx, [rbp+1Fh+var_80]
0x140062315  call    ??$?8EV?$allocator@E@std@@@std@@YA_NAEBV?$vector@EV?$allocator@E@std@@@0@0@Z; std::operator==<uchar,std::allocator<uchar>>(std::vector<uchar> const &,std::vector<uchar> const &)
0x14006231a  test    al, al
0x14006231c  jnz     short loc_140062325
0x14006231e  mov     edx, 23Dh
0x140062323  jmp     short loc_1400622F0
0x140062325  lea     rcx, [rsi+50h]
0x140062329  lea     rdx, [rbp+1Fh+var_50]
0x14006232d  call    ??$?8EV?$allocator@E@std@@@std@@YA_NAEBV?$vector@EV?$allocator@E@std@@@0@0@Z; std::operator==<uchar,std::allocator<uchar>>(std::vector<uchar> const &,std::vector<uchar> const &)
0x140062332  test    al, al
0x140062334  jnz     short loc_14006233D
0x140062336  mov     edx, 23Eh
0x14006233b  jmp     short loc_1400622F0
0x14006233d  lea     rcx, [rsi+68h]
0x140062341  lea     rdx, [rbp+1Fh+var_38]
0x140062345  call    ??$?8EV?$allocator@E@std@@@std@@YA_NAEBV?$vector@EV?$allocator@E@std@@@0@0@Z; std::operator==<uchar,std::allocator<uchar>>(std::vector<uchar> const &,std::vector<uchar> const &)
0x14006234a  test    al, al
0x14006234c  jnz     short loc_140062355
0x14006234e  mov     edx, 23Fh
0x140062353  jmp     short loc_1400622F0
0x140062355  mov     rcx, [rdi+48h]; Buf1
0x140062359  mov     rax, [rdi+50h]
0x14006235d  sub     rax, rcx
0x140062360  mov     r8, [rbp+1Fh+Size]; Size
0x140062364  cmp     rax, r8
0x140062367  jz      short loc_140062370
0x140062369  mov     edx, 241h
0x14006236e  jmp     short loc_1400622F0
0x140062370  mov     rdx, [rbp+1Fh+Buf2]; Buf2
0x140062374  call    memcmp_0
0x140062379  test    eax, eax
0x14006237b  jz      short loc_140062387
0x14006237d  mov     edx, 242h
0x140062382  jmp     loc_1400622F0
0x140062387  mov     rcx, [rdi+60h]; Buf1
0x14006238b  mov     rax, [rdi+68h]
0x14006238f  sub     rax, rcx
0x140062392  mov     r8, [rbp+1Fh+arg_58]; Size
0x140062399  cmp     rax, r8
0x14006239c  jz      short loc_1400623A8
0x14006239e  mov     edx, 243h
0x1400623a3  jmp     loc_1400622F0
0x1400623a8  mov     rdx, [rbp+1Fh+arg_50]; Buf2
0x1400623ac  call    memcmp_0
0x1400623b1  test    eax, eax
0x1400623b3  jz      short loc_1400623BF
0x1400623b5  mov     edx, 244h
0x1400623ba  jmp     loc_1400622F0
0x1400623bf  mov     rcx, [rdi+78h]; Buf1
0x1400623c3  mov     rax, [rdi+80h]
0x1400623ca  sub     rax, rcx
0x1400623cd  mov     r8, [rbp+1Fh+arg_68]; Size
0x1400623d4  cmp     rax, r8
0x1400623d7  jz      short loc_1400623E3
0x1400623d9  mov     edx, 245h
0x1400623de  jmp     loc_1400622F0
0x1400623e3  mov     rdx, [rbp+1Fh+arg_60]; Buf2
0x1400623ea  call    memcmp_0
0x1400623ef  test    eax, eax
0x1400623f1  jz      short loc_1400623FD
0x1400623f3  mov     edx, 246h
0x1400623f8  jmp     loc_1400622F0
0x1400623fd  lea     rcx, aStageenrollmen_0; "StageEnrollment: Enrollment not complet"...
0x140062404  call    ?TraceLoggingInfo@BioIsoProvider@@SAXPEBDZZ; BioIsoProvider::TraceLoggingInfo(char const *,...)
0x140062409  mov     rax, [rbx+8]
0x14006240d  cmp     rax, [rbx+10h]
0x140062411  jz      short loc_14006242A
0x140062413  lea     rdx, [rsp+0E0h+var_A0]
0x140062418  mov     rcx, rax
0x14006241b  call    _anonymous_namespace___Enrollment__Enrollment
0x140062420  sub     qword ptr [rbx+8], 0FFFFFFFFFFFFFF80h
0x140062425  jmp     loc_140062509
0x14006242a  lea     r8, [rsp+0E0h+var_A0]
0x14006242f  mov     rdx, rax
0x140062432  mov     rcx, rbx
0x140062435  call    std__vector__anonymous_namespace___Enrollment_std__allocator__anonymous_namespace___Enrollment______Emplace_reallocate__anonymous_namespace___Enrollment_
0x14006243a  jmp     loc_140062509
0x14006243f  lea     rcx, aStageenrollmen_1; "StageEnrollment: Enrollment not complet"...
0x140062446  call    ?TraceLoggingInfo@BioIsoProvider@@SAXPEBDZZ; BioIsoProvider::TraceLoggingInfo(char const *,...)
0x14006244b  mov     rax, [rbx+8]
0x14006244f  cmp     rax, [rbx+10h]
0x140062453  jz      short loc_140062469
0x140062455  lea     rdx, [rsp+0E0h+var_A0]
0x14006245a  mov     rcx, rax
0x14006245d  call    _anonymous_namespace___Enrollment__Enrollment
0x140062462  sub     qword ptr [rbx+8], 0FFFFFFFFFFFFFF80h
0x140062467  jmp     short loc_140062479
0x140062469  lea     r8, [rsp+0E0h+var_A0]
0x14006246e  mov     rdx, rax
0x140062471  mov     rcx, rbx
0x140062474  call    std__vector__anonymous_namespace___Enrollment_std__allocator__anonymous_namespace___Enrollment______Emplace_reallocate__anonymous_namespace___Enrollment_
0x140062479  mov     rdx, [rbp+1Fh+Buf2]
0x14006247d  mov     r8, [rbp+1Fh+Size]
0x140062481  add     r8, rdx
0x140062484  lea     rcx, [rsp+0E0h+var_C0]
0x140062489  call    ??$?0PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEBE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar const *,uchar const *,std::allocator<uchar> const &)
0x14006248e  lea     rcx, [rdi+48h]
0x140062492  lea     rdx, [rsp+0E0h+var_C0]
0x140062497  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x14006249c  lea     rcx, [rsp+0E0h+var_C0]
0x1400624a1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400624a6  mov     rdx, [rbp+1Fh+arg_50]
0x1400624aa  mov     r8, [rbp+1Fh+arg_58]
0x1400624b1  add     r8, rdx
0x1400624b4  lea     rcx, [rsp+0E0h+var_C0]
0x1400624b9  call    ??$?0PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEBE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar const *,uchar const *,std::allocator<uchar> const &)
0x1400624be  lea     rcx, [rdi+60h]
0x1400624c2  lea     rdx, [rsp+0E0h+var_C0]
0x1400624c7  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1400624cc  lea     rcx, [rsp+0E0h+var_C0]
0x1400624d1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400624d6  mov     rdx, [rbp+1Fh+arg_60]
0x1400624dd  mov     r8, [rbp+1Fh+arg_68]
0x1400624e4  add     r8, rdx
0x1400624e7  lea     rcx, [rsp+0E0h+var_C0]
0x1400624ec  call    ??$?0PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEBE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar const *,uchar const *,std::allocator<uchar> const &)
0x1400624f1  lea     rcx, [rdi+78h]
0x1400624f5  lea     rdx, [rsp+0E0h+var_C0]
0x1400624fa  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1400624ff  lea     rcx, [rsp+0E0h+var_C0]
0x140062504  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140062509  call    cs:__imp_GetTickCount64
0x140062510  nop     dword ptr [rax+rax+00h]
0x140062515  mov     [rdi+40h], rax
0x140062519  xor     ebx, ebx
0x14006251b  lea     rcx, [rsp+0E0h+var_A0]
0x140062520  call    _anonymous_namespace___Enrollment___Enrollment
0x140062525  mov     eax, ebx
0x140062527  add     rsp, 0C8h
0x14006252e  pop     rdi
0x14006252f  pop     rsi
0x140062530  pop     rbx
0x140062531  pop     rbp
0x140062532  retn
```
