# RfbServerFolderQuery::Query(ulong)

- ea: `0x1800132f0`
- end: `0x18001347d`
- name: `?Query@RfbServerFolderQuery@@UEAAXK@Z`
- size: `397`
- prototype: `void __fastcall(RfbServerFolderQuery *this, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000762c`
- `0x18000cd80`
- `0x18000d140`
- `0x18000ee58`
- `0x180013190`
- `0x1800132f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013434`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013434`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001332d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001332d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001341d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013468`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001341d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013468`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800133df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013453`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800133df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013453`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800133b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800133b8`

## pseudocode

```c
void __fastcall RfbServerFolderQuery::Query(RfbServerFolderQuery *this, int a2)
{
  __int64 v3; // rdi
  __int64 *v4; // rbx
  __int64 **v5; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v8; // rcx
  _QWORD *k; // rbx
  _QWORD *v10; // r12
  void **v11; // rdx
  void *v12; // r15
  __int128 v13; // [rsp+20h] [rbp-20h] BYREF
  __int64 v14; // [rsp+30h] [rbp-10h]
  void *v15; // [rsp+80h] [rbp+40h] BYREF
  int v16; // [rsp+88h] [rbp+48h]
  char *v17; // [rsp+90h] [rbp+50h]

  v16 = 0;
  *((_DWORD *)this + 16) = a2;
  v3 = *((_QWORD *)this + 9);
  v13 = 0;
  v14 = 0;
  v16 = 1;
  AcquireSRWLockShared((PSRWLOCK)v3);
  v15 = (void *)v3;
  v4 = **(__int64 ***)(v3 + 8);
  while ( !*((_BYTE *)v4 + 25) )
  {
    if ( *((_QWORD *)&v13 + 1) == v14 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v13, *((_QWORD *)&v13 + 1), v4 + 4);
    }
    else
    {
      std::wstring::wstring(*((__int64 *)&v13 + 1), (__int64)(v4 + 4));
      *((_QWORD *)&v13 + 1) += 32LL;
    }
    v5 = (__int64 **)v4[2];
    if ( *((_BYTE *)v5 + 25) )
    {
      for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 25) && v4 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v4 = i;
      v4 = i;
    }
    else
    {
      v4 = (__int64 *)v4[2];
      for ( j = *v5; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v4 = j;
    }
  }
  ReleaseSRWLockShared((PSRWLOCK)v3);
  v10 = (_QWORD *)*((_QWORD *)&v13 + 1);
  for ( k = (_QWORD *)v13; k != v10; k += 4 )
  {
    RfbServerFolderQuery::CreatePidl(v8, &v15, k);
    AcquireSRWLockExclusive((PSRWLOCK)this + 3);
    v17 = (char *)this + 24;
    v11 = (void **)*((_QWORD *)this + 5);
    if ( v11 == *((void ***)this + 6) )
    {
      std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Emplace_reallocate<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
        (void ***)this + 4,
        v11,
        (__int64 *)&v15);
      v12 = v15;
    }
    else
    {
      v12 = 0;
      *v11 = v15;
      *((_QWORD *)this + 5) += 8LL;
    }
    if ( this != (RfbServerFolderQuery *)-24LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 3);
    v15 = 0;
    if ( v12 )
      CoTaskMemFree(v12);
  }
  std::vector<std::wstring>::~vector<std::wstring>(&v13);
  AcquireSRWLockExclusive((PSRWLOCK)this + 1);
  *((_DWORD *)this + 4) = 2;
  if ( this != (RfbServerFolderQuery *)-8LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 1);
}

```

## disassembly

```asm
0x1800132f0  push    rbp
0x1800132f2  push    rbx
0x1800132f3  push    rsi
0x1800132f4  push    rdi
0x1800132f5  push    r12
0x1800132f7  push    r14
0x1800132f9  push    r15
0x1800132fb  mov     rbp, rsp
0x1800132fe  sub     rsp, 40h
0x180013302  mov     rsi, rcx
0x180013305  mov     [rbp+arg_8], 0
0x18001330c  mov     [rcx+40h], edx
0x18001330f  mov     rdi, [rcx+48h]
0x180013313  xorps   xmm0, xmm0
0x180013316  movdqu  [rbp+var_20], xmm0
0x18001331b  mov     [rbp+var_10], 0
0x180013323  mov     [rbp+arg_8], 1
0x18001332a  mov     rcx, rdi; SRWLock
0x18001332d  call    cs:__imp_AcquireSRWLockShared
0x180013333  mov     [rbp+arg_0], rdi
0x180013337  mov     rbx, [rdi+8]
0x18001333b  mov     rbx, [rbx]
0x18001333e  cmp     byte ptr [rbx+19h], 0
0x180013342  jnz     short loc_1800133B5
0x180013344  lea     r8, [rbx+20h]
0x180013348  mov     rax, qword ptr [rbp+var_20+8]
0x18001334c  cmp     rax, [rbp+var_10]
0x180013350  jz      short loc_180013364
0x180013352  mov     rdx, r8
0x180013355  mov     rcx, rax
0x180013358  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001335d  add     qword ptr [rbp+var_20+8], 20h ; ' '
0x180013362  jmp     short loc_180013370
0x180013364  mov     rdx, rax
0x180013367  lea     rcx, [rbp+var_20]
0x18001336b  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180013370  mov     rcx, [rbx+10h]
0x180013374  cmp     byte ptr [rcx+19h], 0
0x180013378  jz      short loc_180013398
0x18001337a  mov     rax, [rbx+8]
0x18001337e  jmp     short loc_18001338D
0x180013380  cmp     rbx, [rax+10h]
0x180013384  jnz     short loc_180013393
0x180013386  mov     rbx, rax
0x180013389  mov     rax, [rax+8]
0x18001338d  cmp     byte ptr [rax+19h], 0
0x180013391  jz      short loc_180013380
0x180013393  mov     rbx, rax
0x180013396  jmp     short loc_18001333E
0x180013398  mov     rbx, rcx
0x18001339b  mov     rcx, [rcx]
0x18001339e  cmp     byte ptr [rcx+19h], 0
0x1800133a2  jnz     short loc_18001333E
0x1800133a4  mov     rbx, rcx
0x1800133a7  mov     rax, [rcx]
0x1800133aa  mov     rcx, rax
0x1800133ad  cmp     byte ptr [rax+19h], 0
0x1800133b1  jz      short loc_1800133A4
0x1800133b3  jmp     short loc_18001333E
0x1800133b5  mov     rcx, rdi; SRWLock
0x1800133b8  call    cs:__imp_ReleaseSRWLockShared
0x1800133be  mov     rbx, qword ptr [rbp+var_20]
0x1800133c2  mov     r12, qword ptr [rbp+var_20+8]
0x1800133c6  cmp     rbx, r12
0x1800133c9  jz      short loc_180013443
0x1800133cb  lea     r14, [rsi+18h]
0x1800133cf  mov     r8, rbx
0x1800133d2  lea     rdx, [rbp+arg_0]
0x1800133d6  call    ?CreatePidl@RfbServerFolderQuery@@IEAA?AV?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RfbServerFolderQuery::CreatePidl(std::wstring const &)
0x1800133db  nop
0x1800133dc  mov     rcx, r14; SRWLock
0x1800133df  call    cs:__imp_AcquireSRWLockExclusive
0x1800133e5  mov     [rbp+arg_10], r14
0x1800133e9  mov     rdx, [rsi+28h]
0x1800133ed  cmp     rdx, [rsi+30h]
0x1800133f1  jz      short loc_180013404
0x1800133f3  mov     rax, [rbp+arg_0]
0x1800133f7  xor     r15d, r15d
0x1800133fa  mov     [rdx], rax
0x1800133fd  add     qword ptr [rsi+28h], 8
0x180013402  jmp     short loc_180013415
0x180013404  lea     r8, [rbp+arg_0]
0x180013408  lea     rcx, [rsi+20h]
0x18001340c  call    ??$_Emplace_reallocate@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@?$vector@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAPEAV?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAV23@$$QEAV23@@Z; std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Emplace_reallocate<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> * const,wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180013411  mov     r15, [rbp+arg_0]
0x180013415  test    r14, r14
0x180013418  jz      short loc_180013424
0x18001341a  mov     rcx, r14; SRWLock
0x18001341d  call    cs:__imp_ReleaseSRWLockExclusive
0x180013423  nop
0x180013424  mov     [rbp+arg_0], 0
0x18001342c  test    r15, r15
0x18001342f  jz      short loc_18001343A
0x180013431  mov     rcx, r15; pv
0x180013434  call    cs:__imp_CoTaskMemFree
0x18001343a  add     rbx, 20h ; ' '
0x18001343e  cmp     rbx, r12
0x180013441  jnz     short loc_1800133CF
0x180013443  lea     rcx, [rbp+var_20]
0x180013447  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x18001344c  lea     rbx, [rsi+8]
0x180013450  mov     rcx, rbx; SRWLock
0x180013453  call    cs:__imp_AcquireSRWLockExclusive
0x180013459  mov     dword ptr [rsi+10h], 2
0x180013460  test    rbx, rbx
0x180013463  jz      short loc_18001346E
0x180013465  mov     rcx, rbx; SRWLock
0x180013468  call    cs:__imp_ReleaseSRWLockExclusive
0x18001346e  add     rsp, 40h
0x180013472  pop     r15
0x180013474  pop     r14
0x180013476  pop     r12
0x180013478  pop     rdi
0x180013479  pop     rsi
0x18001347a  pop     rbx
0x18001347b  pop     rbp
0x18001347c  retn
```
