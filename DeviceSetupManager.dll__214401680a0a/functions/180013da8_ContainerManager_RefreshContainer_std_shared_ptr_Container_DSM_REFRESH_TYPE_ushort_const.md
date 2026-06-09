# ContainerManager::_RefreshContainer(std::shared_ptr<Container>,DSM_REFRESH_TYPE,ushort const *)

- ea: `0x180013da8`
- end: `0x180014183`
- name: `?_RefreshContainer@ContainerManager@@AEAAJV?$shared_ptr@VContainer@@@std@@W4DSM_REFRESH_TYPE@@PEBG@Z`
- size: `987`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, RTL_SRWLOCK **, __int64, const char *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001580c`
- `0x18001870c`

## callees

- `0x1800112a4`
- `0x180012570`
- `0x18001370c`
- `0x180013864`
- `0x180013da8`
- `0x180015474`
- `0x18001985c`
- `0x18001af70`
- `0x18001b3f0`
- `0x18001bc4c`
- `0x18001bcb4`
- `0x1800273d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014050`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014050`

## string_xrefs

- `0x180014092`: `onecoreuap\base\devices\setup\dsm\service\containermanager.cpp`

## pseudocode

```c
__int64 __fastcall ContainerManager::_RefreshContainer(RTL_SRWLOCK *a1, RTL_SRWLOCK **a2, __int64 a3, const char *a4)
{
  __int64 v4; // rdi
  int v5; // r13d
  __int64 v7; // rbx
  int v8; // r12d
  std::_Ref_count_base *v9; // rcx
  __int64 result; // rax
  RTL_SRWLOCK *v11; // rdi
  RTL_SRWLOCK *v12; // rbx
  std::_Ref_count_base *v13; // rcx
  unsigned int v14; // ebx
  std::_Ref_count_base *v15; // rcx
  std::_Ref_count_base *v16; // rcx
  int v17; // [rsp+20h] [rbp-98h]
  __m128i *p_si128; // [rsp+40h] [rbp-78h] BYREF
  __int8 *v19; // [rsp+48h] [rbp-70h]
  const char *v20; // [rsp+50h] [rbp-68h]
  PSRWLOCK SRWLock; // [rsp+58h] [rbp-60h]
  RTL_SRWLOCK **v22; // [rsp+60h] [rbp-58h]
  __m128i si128; // [rsp+68h] [rbp-50h] BYREF
  __int64 v24; // [rsp+78h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  try
  {
    v4 = (__int64)a4;
    v20 = a4;
    v5 = a3;
    SRWLock = a1;
    v22 = a2;
    v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    if ( dword_18005A498 > *(_DWORD *)(v7 + 4) )
    {
      Init_thread_header(&dword_18005A498);
      if ( dword_18005A498 == -1 )
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        p_si128 = &si128;
        v19 = (__int8 *)&v24;
        std::vector<enum JobType>::vector<enum JobType>(&qword_18005A4A0, &p_si128);
        atexit(ContainerManager::_RefreshContainer_::_3_::_dynamic_atexit_destructor_for__jobsForFullRefresh__);
        Init_thread_footer(&dword_18005A498);
      }
    }
    if ( dword_18005A4B8 > *(_DWORD *)(v7 + 4) )
    {
      Init_thread_header(&dword_18005A4B8);
      if ( dword_18005A4B8 == -1 )
      {
        si128.m128i_i64[0] = 0x400000005LL;
        p_si128 = &si128;
        v19 = &si128.m128i_i8[8];
        std::vector<enum JobType>::vector<enum JobType>(&qword_18005A4C0, &p_si128);
        atexit(ContainerManager::_RefreshContainer_::_3_::_dynamic_atexit_destructor_for__jobsForPropertyRefresh__);
        Init_thread_footer(&dword_18005A4B8);
      }
    }
    if ( dword_18005A4D8 > *(_DWORD *)(v7 + 4) )
    {
      Init_thread_header(&dword_18005A4D8);
      if ( dword_18005A4D8 == -1 )
      {
        si128.m128i_i32[0] = 3;
        p_si128 = &si128;
        v19 = &si128.m128i_i8[4];
        std::vector<enum JobType>::vector<enum JobType>(&qword_18005A4E0, &p_si128);
        atexit(ContainerManager::_RefreshContainer_::_3_::_dynamic_atexit_destructor_for__jobsForCtaAppUpdatesRefresh__);
        Init_thread_footer(&dword_18005A4D8);
      }
    }
    if ( dword_18005A4F8 > *(_DWORD *)(v7 + 4) )
    {
      Init_thread_header(&dword_18005A4F8);
      if ( dword_18005A4F8 == -1 )
      {
        si128.m128i_i64[0] = 0x500000002LL;
        si128.m128i_i32[2] = 4;
        p_si128 = &si128;
        v19 = &si128.m128i_i8[12];
        std::vector<enum JobType>::vector<enum JobType>(&qword_18005A500, &p_si128);
        atexit(ContainerManager::_RefreshContainer_::_3_::_dynamic_atexit_destructor_for__jobsForCtaWindowsUpdatesRefresh__);
        Init_thread_footer(&dword_18005A4F8);
      }
    }
    v8 = ((v5 & 0xFFFFFFFB) != 0) + 1;
    if ( v5 )
    {
      if ( v5 == 1 )
        goto LABEL_31;
      if ( v5 != 2 )
      {
        if ( v5 == 3 )
        {
          v8 |= 0x10u;
          goto LABEL_31;
        }
        if ( v5 != 4 && v5 != 5 )
        {
          if ( v5 != 6 && (unsigned int)(v5 - 7) >= 2 )
          {
            v9 = (std::_Ref_count_base *)a2[1];
            if ( v9 )
              std::_Ref_count_base::_Decref(v9);
            return 2147942487LL;
          }
          goto LABEL_31;
        }
      }
      v11 = *a2;
      v12 = *a2 + 18;
      AcquireSRWLockExclusive(v12);
      si128.m128i_i64[0] = (__int64)v12;
      LODWORD(v11[60].Ptr) = 0;
      *(_DWORD *)((char *)&v11[60].Ptr + 5) = 0;
      BYTE1(v11[61].Ptr) = 0;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&si128);
      v4 = (__int64)v20;
LABEL_31:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_L_guid_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)&WPP_12025944dd5e3a7e3168b2cc2e6c0bb5_Traceguids,
          v5,
          (__int64)&(*a2)[2]);
      }
      std::shared_ptr<Container>::shared_ptr<Container>(&p_si128, a2, a3, a4);
      v14 = ContainerManager::_PostJobs(SRWLock, v17, v8, 0, v4);
      v15 = (std::_Ref_count_base *)a2[1];
      if ( v15 )
        std::_Ref_count_base::_Decref(v15);
      return v14;
    }
    if ( v4 )
      goto LABEL_31;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\containermanager.cpp",
      (const char *)0x80070057LL,
      v17);
    v13 = (std::_Ref_count_base *)a2[1];
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    result = 2147942487LL;
  }
  catch ( ... )
  {
    si128.m128i_i32[0] = wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x271,
                           (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\containermanager.cpp",
                           a4);
    v16 = (std::_Ref_count_base *)v22[1];
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    return si128.m128i_u32[0];
  }
  return result;
}

```

## disassembly

```asm
0x180013da8  push    rbx
0x180013daa  push    rsi
0x180013dab  push    rdi
0x180013dac  push    r12
0x180013dae  push    r13
0x180013db0  push    r14
0x180013db2  push    r15
0x180013db4  sub     rsp, 80h
0x180013dbb  mov     rax, cs:__security_cookie
0x180013dc2  xor     rax, rsp
0x180013dc5  mov     [rsp+0B8h+var_40], rax
0x180013dca  mov     rdi, r9
0x180013dcd  mov     [rsp+0B8h+var_68], r9
0x180013dd2  mov     r13d, r8d
0x180013dd5  mov     r15, rdx
0x180013dd8  mov     [rsp+0B8h+SRWLock], rcx
0x180013ddd  mov     [rsp+0B8h+var_58], rdx
0x180013de2  mov     ecx, cs:_tls_index
0x180013de8  mov     rax, gs:58h
0x180013df1  mov     esi, 4
0x180013df6  mov     rbx, [rax+rcx*8]
0x180013dfa  mov     eax, [rbx+rsi]
0x180013dfd  cmp     cs:dword_18005A498, eax
0x180013e03  jle     short loc_180013E66
0x180013e05  lea     rcx, dword_18005A498
0x180013e0c  call    _Init_thread_header
0x180013e11  cmp     cs:dword_18005A498, 0FFFFFFFFh
0x180013e18  jnz     short loc_180013E66
0x180013e1a  movdqa  xmm0, cs:__xmm@00000004000000050000000300000002
0x180013e22  movdqu  [rsp+0B8h+var_50], xmm0
0x180013e28  lea     rax, [rsp+0B8h+var_50]
0x180013e2d  mov     [rsp+0B8h+var_78], rax
0x180013e32  lea     rax, [rsp+0B8h+var_40]
0x180013e37  mov     [rsp+0B8h+var_70], rax
0x180013e3c  lea     rdx, [rsp+0B8h+var_78]
0x180013e41  lea     rcx, qword_18005A4A0
0x180013e48  call    ??0?$vector@W4JobType@@V?$allocator@W4JobType@@@std@@@std@@QEAA@V?$initializer_list@W4JobType@@@1@AEBV?$allocator@W4JobType@@@1@@Z; std::vector<JobType>::vector<JobType>(std::initializer_list<JobType>,std::allocator<JobType> const &)
0x180013e4d  lea     rcx, _ContainerManager___RefreshContainer____3____dynamic_atexit_destructor_for__jobsForFullRefresh__; void (__cdecl *)()
0x180013e54  call    atexit
0x180013e59  nop
0x180013e5a  lea     rcx, dword_18005A498
0x180013e61  call    _Init_thread_footer
0x180013e66  mov     eax, [rbx+rsi]
0x180013e69  cmp     cs:dword_18005A4B8, eax
0x180013e6f  jle     short loc_180013ED4
0x180013e71  lea     rcx, dword_18005A4B8
0x180013e78  call    _Init_thread_header
0x180013e7d  cmp     cs:dword_18005A4B8, 0FFFFFFFFh
0x180013e84  jnz     short loc_180013ED4
0x180013e86  mov     dword ptr [rsp+0B8h+var_50], 5
0x180013e8e  mov     dword ptr [rsp+0B8h+var_50+4], 4
0x180013e96  lea     rax, [rsp+0B8h+var_50]
0x180013e9b  mov     [rsp+0B8h+var_78], rax
0x180013ea0  lea     rax, [rsp+0B8h+var_50+8]
0x180013ea5  mov     [rsp+0B8h+var_70], rax
0x180013eaa  lea     rdx, [rsp+0B8h+var_78]
0x180013eaf  lea     rcx, qword_18005A4C0
0x180013eb6  call    ??0?$vector@W4JobType@@V?$allocator@W4JobType@@@std@@@std@@QEAA@V?$initializer_list@W4JobType@@@1@AEBV?$allocator@W4JobType@@@1@@Z; std::vector<JobType>::vector<JobType>(std::initializer_list<JobType>,std::allocator<JobType> const &)
0x180013ebb  lea     rcx, _ContainerManager___RefreshContainer____3____dynamic_atexit_destructor_for__jobsForPropertyRefresh__; void (__cdecl *)()
0x180013ec2  call    atexit
0x180013ec7  nop
0x180013ec8  lea     rcx, dword_18005A4B8
0x180013ecf  call    _Init_thread_footer
0x180013ed4  mov     eax, [rbx+rsi]
0x180013ed7  cmp     cs:dword_18005A4D8, eax
0x180013edd  jle     short loc_180013F3A
0x180013edf  lea     rcx, dword_18005A4D8
0x180013ee6  call    _Init_thread_header
0x180013eeb  cmp     cs:dword_18005A4D8, 0FFFFFFFFh
0x180013ef2  jnz     short loc_180013F3A
0x180013ef4  mov     dword ptr [rsp+0B8h+var_50], 3
0x180013efc  lea     rax, [rsp+0B8h+var_50]
0x180013f01  mov     [rsp+0B8h+var_78], rax
0x180013f06  lea     rax, [rsp+0B8h+var_50+4]
0x180013f0b  mov     [rsp+0B8h+var_70], rax
0x180013f10  lea     rdx, [rsp+0B8h+var_78]
0x180013f15  lea     rcx, qword_18005A4E0
0x180013f1c  call    ??0?$vector@W4JobType@@V?$allocator@W4JobType@@@std@@@std@@QEAA@V?$initializer_list@W4JobType@@@1@AEBV?$allocator@W4JobType@@@1@@Z; std::vector<JobType>::vector<JobType>(std::initializer_list<JobType>,std::allocator<JobType> const &)
0x180013f21  lea     rcx, _ContainerManager___RefreshContainer____3____dynamic_atexit_destructor_for__jobsForCtaAppUpdatesRefresh__; void (__cdecl *)()
0x180013f28  call    atexit
0x180013f2d  nop
0x180013f2e  lea     rcx, dword_18005A4D8
0x180013f35  call    _Init_thread_footer
0x180013f3a  mov     eax, [rbx+rsi]
0x180013f3d  cmp     cs:dword_18005A4F8, eax
0x180013f43  jle     short loc_180013FB5
0x180013f45  lea     rcx, dword_18005A4F8
0x180013f4c  call    _Init_thread_header
0x180013f51  cmp     cs:dword_18005A4F8, 0FFFFFFFFh
0x180013f58  jnz     short loc_180013FB5
0x180013f5a  mov     dword ptr [rsp+0B8h+var_50], 2
0x180013f62  mov     dword ptr [rsp+0B8h+var_50+4], 5
0x180013f6a  mov     dword ptr [rsp+0B8h+var_50+8], 4
0x180013f72  lea     rax, [rsp+0B8h+var_50]
0x180013f77  mov     [rsp+0B8h+var_78], rax
0x180013f7c  lea     rax, [rsp+0B8h+var_50+0Ch]
0x180013f81  mov     [rsp+0B8h+var_70], rax
0x180013f86  lea     rdx, [rsp+0B8h+var_78]
0x180013f8b  lea     r14, qword_18005A500
0x180013f92  mov     rcx, r14
0x180013f95  call    ??0?$vector@W4JobType@@V?$allocator@W4JobType@@@std@@@std@@QEAA@V?$initializer_list@W4JobType@@@1@AEBV?$allocator@W4JobType@@@1@@Z; std::vector<JobType>::vector<JobType>(std::initializer_list<JobType>,std::allocator<JobType> const &)
0x180013f9a  lea     rcx, _ContainerManager___RefreshContainer____3____dynamic_atexit_destructor_for__jobsForCtaWindowsUpdatesRefresh__; void (__cdecl *)()
0x180013fa1  call    atexit
0x180013fa6  nop
0x180013fa7  lea     rcx, dword_18005A4F8
0x180013fae  call    _Init_thread_footer
0x180013fb3  jmp     short loc_180013FBC
0x180013fb5  lea     r14, qword_18005A500
0x180013fbc  mov     eax, r13d
0x180013fbf  and     eax, 0FFFFFFFBh
0x180013fc2  neg     eax
0x180013fc4  sbb     r12d, r12d
0x180013fc7  neg     r12d
0x180013fca  inc     r12d
0x180013fcd  mov     ecx, r13d
0x180013fd0  xor     esi, esi
0x180013fd2  test    r13d, r13d
0x180013fd5  jz      loc_18001407F
0x180013fdb  sub     ecx, 1
0x180013fde  jz      loc_1800140BC
0x180013fe4  sub     ecx, 1
0x180013fe7  jz      short loc_18001403C
0x180013fe9  sub     ecx, 1
0x180013fec  jz      short loc_180014033
0x180013fee  sub     ecx, 1
0x180013ff1  jz      short loc_18001403C
0x180013ff3  sub     ecx, 1
0x180013ff6  jz      short loc_18001403C
0x180013ff8  sub     ecx, 1
0x180013ffb  jz      loc_1800140BC
0x180014001  sub     ecx, 1
0x180014004  jz      short loc_180014027
0x180014006  cmp     ecx, 1
0x180014009  jz      loc_1800140C3
0x18001400f  mov     rcx, [r15+8]; this
0x180014013  test    rcx, rcx
0x180014016  jz      short loc_18001401D
0x180014018  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001401d  mov     eax, 80070057h
0x180014022  jmp     loc_180014163
0x180014027  lea     r14, qword_18005A4E0
0x18001402e  jmp     loc_1800140C3
0x180014033  or      r12d, 10h
0x180014037  jmp     loc_1800140BC
0x18001403c  lea     r14, qword_18005A4A0
0x180014043  mov     rdi, [r15]
0x180014046  lea     rbx, [rdi+90h]
0x18001404d  mov     rcx, rbx; SRWLock
0x180014050  call    cs:__imp_AcquireSRWLockExclusive
0x180014056  mov     qword ptr [rsp+0B8h+var_50], rbx
0x18001405b  mov     [rdi+1E0h], esi
0x180014061  mov     [rdi+1E5h], esi
0x180014067  mov     [rdi+1E9h], sil
0x18001406e  lea     rcx, [rsp+0B8h+var_50]
0x180014073  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014078  mov     rdi, [rsp+0B8h+var_68]
0x18001407d  jmp     short loc_1800140C3
0x18001407f  test    rdi, rdi
0x180014082  jnz     short loc_1800140BC
0x180014084  mov     rcx, [rsp+0B8h]; this
0x18001408c  mov     r9d, 80070057h; char *
0x180014092  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180014099  mov     edx, 249h; void *
0x18001409e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800140a3  nop
0x1800140a4  mov     rcx, [r15+8]; this
0x1800140a8  test    rcx, rcx
0x1800140ab  jz      short loc_1800140B2
0x1800140ad  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800140b2  mov     eax, 80070057h
0x1800140b7  jmp     loc_180014163
0x1800140bc  lea     r14, qword_18005A4C0
0x1800140c3  lea     rax, WPP_GLOBAL_Control
0x1800140ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140d1  cmp     rcx, rax
0x1800140d4  jz      short loc_180014109
0x1800140d6  test    dword ptr [rcx+1Ch], 100h
0x1800140dd  jz      short loc_180014109
0x1800140df  cmp     byte ptr [rcx+19h], 4
0x1800140e3  jb      short loc_180014109
0x1800140e5  mov     rax, [r15]
0x1800140e8  add     rax, 10h
0x1800140ec  mov     edx, 13h
0x1800140f1  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x1800140f6  mov     r9d, r13d
0x1800140f9  lea     r8, WPP_12025944dd5e3a7e3168b2cc2e6c0bb5_Traceguids
0x180014100  mov     rcx, [rcx+10h]
0x180014104  call    WPP_SF_L_guid_
0x180014109  mov     rdx, r15
0x18001410c  lea     rcx, [rsp+0B8h+var_78]
0x180014111  call    ??0?$shared_ptr@VContainer@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Container>::shared_ptr<Container>(std::shared_ptr<Container> const &)
0x180014116  mov     [rsp+0B8h+var_80], rdi; __int64
0x18001411b  mov     [rsp+0B8h+var_88], rsi; __int64
0x180014120  mov     [rsp+0B8h+var_90], r12d; int
0x180014125  xor     r9d, r9d
0x180014128  mov     r8, r14
0x18001412b  mov     rdx, rax
0x18001412e  mov     rcx, [rsp+0B8h+SRWLock]; SRWLock
0x180014133  call    ?_PostJobs@ContainerManager@@AEAAJV?$shared_ptr@VContainer@@@std@@AEBV?$vector@W4JobType@@V?$allocator@W4JobType@@@std@@@3@PEBGW4JobObjectType@@W4JobAttributes@@PEBX2@Z; ContainerManager::_PostJobs(std::shared_ptr<Container>,std::vector<JobType> const &,ushort const *,JobObjectType,JobAttributes,void const *,ushort const *)
0x180014138  mov     ebx, eax
0x18001413a  mov     rcx, [r15+8]; this
0x18001413e  test    rcx, rcx
0x180014141  jz      short loc_180014148
0x180014143  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014148  mov     eax, ebx
0x18001414a  jmp     short loc_180014163
0x18001414c  mov     rax, [rsp+0B8h+var_58]
0x180014151  mov     rcx, [rax+8]; this
0x180014155  test    rcx, rcx
0x180014158  jz      short loc_18001415F
0x18001415a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001415f  mov     eax, dword ptr [rsp+0B8h+var_50]
0x180014163  mov     rcx, [rsp+0B8h+var_40]
0x180014168  xor     rcx, rsp; StackCookie
0x18001416b  call    __security_check_cookie
0x180014170  add     rsp, 80h
0x180014177  pop     r15
0x180014179  pop     r14
0x18001417b  pop     r13
0x18001417d  pop     r12
0x18001417f  pop     rdi
0x180014180  pop     rsi
0x180014181  pop     rbx
0x180014182  retn
```
