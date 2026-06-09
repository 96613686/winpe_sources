# OOBEOneDriveOptin::GetFolderMoveStatuses(uint *,OneDriveKnownFolderMoveStatusEntry * *)

- ea: `0x18001a030`
- end: `0x18001a37f`
- name: `?GetFolderMoveStatuses@OOBEOneDriveOptin@@UEAAJPEAIPEAPEAUOneDriveKnownFolderMoveStatusEntry@@@Z`
- size: `847`
- prototype: `__int64 __fastcall(OOBEOneDriveOptin *__hidden this, unsigned int *, struct OneDriveKnownFolderMoveStatusEntry **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001a390`

## callees

- `0x1800032b0`
- `0x180007134`
- `0x180009f90`
- `0x18001136c`
- `0x180017d18`
- `0x180018554`
- `0x180019a0c`
- `0x18001a030`
- `0x18001d1d8`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a27c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a27c`

## string_xrefs

- `0x18001a07b`: `shell\oobe\user\dll\oobesyncengineapi.cpp`
- `0x18001a0dc`: `shell\oobe\user\dll\oobesyncengineapi.cpp`
- `0x18001a215`: `shell\oobe\user\dll\oobesyncengineapi.cpp`
- `0x18001a296`: `shell\oobe\user\dll\oobesyncengineapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OOBEOneDriveOptin::GetFolderMoveStatuses(
        OOBEOneDriveOptin *this,
        unsigned int *a2,
        struct OneDriveKnownFolderMoveStatusEntry **a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, unsigned int *, _QWORD *); // rbx
  int v11; // eax
  unsigned int i; // ebx
  __int64 v13; // rdi
  int v14; // esi
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rdx
  struct OneDriveKnownFolderMoveStatusEntry *v20; // r9
  unsigned int v21; // r11d
  __int64 v22; // r8
  __int64 v23; // r10
  int v24; // edx
  __int64 v25; // rcx
  int v26; // [rsp+20h] [rbp-60h] BYREF
  __int128 v27; // [rsp+28h] [rbp-58h] BYREF
  __int64 v28; // [rsp+38h] [rbp-48h]
  unsigned int v29; // [rsp+40h] [rbp-40h] BYREF
  __int64 v30; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v31[2]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v32; // [rsp+60h] [rbp-20h] BYREF
  int v33; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  *a2 = 0;
  *a3 = 0;
  v6 = OOBEOneDriveOptin::AttemptPopulateKfmSource((OOBEOneDriveOptin *)((char *)this - 8));
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
      (const char *)(unsigned int)v6,
      v26);
    return v7;
  }
  v9 = *((_QWORD *)this + 8);
  if ( !v9 )
    return 0;
  v29 = 0;
  v31[0] = 0;
  v31[1] = 0;
  v10 = *(__int64 (__fastcall **)(__int64, unsigned int *, _QWORD *))(*(_QWORD *)v9 + 56LL);
  wil::unique_any_array_ptr<IKFMEnrollmentStatus *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(v31);
  v11 = v10(v9, &v29, v31);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EA,
      (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
      (const char *)(unsigned int)v11,
      v26);
LABEL_30:
    wil::unique_any_array_ptr<IKFMEnrollmentStatus *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(v31);
    return v7;
  }
  if ( !v29 )
    goto LABEL_37;
  v27 = 0;
  v28 = 0;
  for ( i = 0; i < v29; ++i )
  {
    wil::com_ptr_t<IKFMEnrollmentStatus,wil::err_exception_policy>::com_ptr_t<IKFMEnrollmentStatus,wil::err_exception_policy>(
      &v30,
      *(_QWORD *)(v31[0] + 8LL * i));
    v26 = 0;
    v13 = v30;
    v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 24LL))(v30, &v26);
    if ( v14 < 0 )
    {
      v19 = 505;
      goto LABEL_24;
    }
    if ( !v26 )
      goto LABEL_18;
    v32 = 0;
    v33 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v13 + 32LL))(v13, &v32);
    if ( v14 < 0 )
    {
      v19 = 509;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
        (const char *)(unsigned int)v14,
        v26);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v30);
      if ( (_QWORD)v27 )
      {
        std::_Deallocate<16>(v27, 4 * ((v28 - (__int64)v27) >> 2));
        v27 = 0;
        v28 = 0;
      }
      v7 = v14;
      goto LABEL_30;
    }
    if ( v26 == 3 )
      v33 = 2;
    else
      v33 = v26 == 2;
    v15 = *((_QWORD *)&v27 + 1);
    if ( *((_QWORD *)&v27 + 1) == v28 )
    {
      std::vector<OneDriveKnownFolderMoveStatusEntry>::_Emplace_reallocate<OneDriveKnownFolderMoveStatusEntry const &>(
        &v27,
        *((_QWORD *)&v27 + 1),
        &v32);
    }
    else
    {
      **((_OWORD **)&v27 + 1) = v32;
      *(_DWORD *)(v15 + 16) = v33;
      *((_QWORD *)&v27 + 1) += 20LL;
    }
LABEL_18:
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v30);
  }
  v16 = v27;
  v17 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v27 + 1) - v27) >> 2);
  if ( !(_DWORD)v17 )
  {
    if ( !(_QWORD)v27 )
      goto LABEL_37;
    v18 = v28 - v27;
    goto LABEL_36;
  }
  v20 = (struct OneDriveKnownFolderMoveStatusEntry *)CoTaskMemAlloc(20LL * (unsigned int)v17);
  if ( !v20 )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20B,
      (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
      (const char *)0x8007000ELL,
      v26);
    if ( (_QWORD)v27 )
    {
      std::_Deallocate<16>(v27, 4 * ((v28 - (__int64)v27) >> 2));
      v27 = 0;
      v28 = 0;
    }
    goto LABEL_30;
  }
  v21 = 0;
  v23 = *((_QWORD *)&v27 + 1);
  v22 = v27;
  if ( (_QWORD)v27 != *((_QWORD *)&v27 + 1) )
  {
    do
    {
      v24 = *(_DWORD *)(v22 + 16);
      v25 = 5LL * v21;
      *(_OWORD *)((char *)v20 + 4 * v25) = *(_OWORD *)v22;
      *((_DWORD *)v20 + v25 + 4) = v24;
      ++v21;
      v22 += 20;
    }
    while ( v22 != v23 );
    v22 = v27;
  }
  *a2 = v17;
  *a3 = v20;
  if ( v22 )
  {
    v18 = v28 - v22;
    v16 = v22;
LABEL_36:
    std::_Deallocate<16>(v16, 4 * (v18 >> 2));
    v28 = 0;
    v27 = 0;
  }
LABEL_37:
  wil::unique_any_array_ptr<IKFMEnrollmentStatus *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(v31);
  return 0;
}

```

## disassembly

```asm
0x18001a030  push    rbp
0x18001a032  push    rbx
0x18001a033  push    rsi
0x18001a034  push    rdi
0x18001a035  push    r12
0x18001a037  push    r14
0x18001a039  push    r15
0x18001a03b  mov     rbp, rsp
0x18001a03e  sub     rsp, 80h
0x18001a045  mov     rax, cs:__security_cookie
0x18001a04c  xor     rax, rsp
0x18001a04f  mov     [rbp+var_8], rax
0x18001a053  mov     r15, r8
0x18001a056  mov     r14, rdx
0x18001a059  mov     rdi, rcx
0x18001a05c  xor     r12d, r12d
0x18001a05f  mov     [rdx], r12d
0x18001a062  mov     [r8], r12
0x18001a065  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x18001a069  call    ?AttemptPopulateKfmSource@OOBEOneDriveOptin@@AEAAJXZ; OOBEOneDriveOptin::AttemptPopulateKfmSource(void)
0x18001a06e  mov     ebx, eax
0x18001a070  test    eax, eax
0x18001a072  jns     short loc_18001A093
0x18001a074  mov     rcx, [rbp+38h]; this
0x18001a078  mov     r9d, eax; char *
0x18001a07b  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001a082  mov     edx, 1E1h; void *
0x18001a087  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a08c  mov     eax, ebx
0x18001a08e  jmp     loc_18001A361
0x18001a093  mov     rdi, [rdi+40h]
0x18001a097  test    rdi, rdi
0x18001a09a  jz      loc_18001A35F
0x18001a0a0  mov     [rbp+var_40], r12d
0x18001a0a4  mov     [rbp+var_30], r12
0x18001a0a8  mov     [rbp+var_28], r12
0x18001a0ac  mov     rax, [rdi]
0x18001a0af  mov     rbx, [rax+38h]
0x18001a0b3  lea     rcx, [rbp+var_30]
0x18001a0b7  call    ?reset@?$unique_any_array_ptr@PEAUIKFMEnrollmentStatus@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<IKFMEnrollmentStatus *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(void)
0x18001a0bc  lea     r8, [rbp+var_30]
0x18001a0c0  lea     rdx, [rbp+var_40]
0x18001a0c4  mov     rcx, rdi
0x18001a0c7  mov     rax, rbx
0x18001a0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0cf  mov     ebx, eax
0x18001a0d1  test    eax, eax
0x18001a0d3  jns     short loc_18001A0F2
0x18001a0d5  mov     rcx, [rbp+38h]; this
0x18001a0d9  mov     r9d, eax; char *
0x18001a0dc  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001a0e3  mov     edx, 1EAh; void *
0x18001a0e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a0ed  jmp     loc_18001A2D9
0x18001a0f2  mov     ecx, [rbp+var_40]
0x18001a0f5  test    ecx, ecx
0x18001a0f7  jz      loc_18001A356
0x18001a0fd  xorps   xmm0, xmm0
0x18001a100  movdqu  [rbp+var_58], xmm0
0x18001a105  mov     rax, r12
0x18001a108  mov     [rbp+var_48], rax
0x18001a10c  mov     ebx, r12d
0x18001a10f  mov     eax, ebx
0x18001a111  mov     rdx, [rbp+var_30]
0x18001a115  mov     rdx, [rdx+rax*8]
0x18001a119  lea     rcx, [rbp+var_38]
0x18001a11d  call    ??0?$com_ptr_t@UIKFMEnrollmentStatus@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIKFMEnrollmentStatus@@@Z; wil::com_ptr_t<IKFMEnrollmentStatus,wil::err_exception_policy>::com_ptr_t<IKFMEnrollmentStatus,wil::err_exception_policy>(IKFMEnrollmentStatus *)
0x18001a122  nop
0x18001a123  mov     [rbp+var_60], r12d
0x18001a127  mov     rdi, [rbp+var_38]
0x18001a12b  mov     rax, [rdi]
0x18001a12e  lea     rdx, [rbp+var_60]
0x18001a132  mov     rcx, rdi
0x18001a135  mov     rax, [rax+18h]
0x18001a139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a13e  mov     esi, eax
0x18001a140  test    eax, eax
0x18001a142  js      loc_18001A210
0x18001a148  cmp     [rbp+var_60], r12d
0x18001a14c  jz      short loc_18001A1BF
0x18001a14e  xorps   xmm0, xmm0
0x18001a151  xor     eax, eax
0x18001a153  movups  [rbp+var_20], xmm0
0x18001a157  mov     [rbp+var_10], eax
0x18001a15a  mov     rax, [rdi]
0x18001a15d  lea     rdx, [rbp+var_20]
0x18001a161  mov     rcx, rdi
0x18001a164  mov     rax, [rax+20h]
0x18001a168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a16d  mov     esi, eax
0x18001a16f  test    eax, eax
0x18001a171  js      loc_18001A209
0x18001a177  cmp     [rbp+var_60], 3
0x18001a17b  jnz     short loc_18001A186
0x18001a17d  mov     [rbp+var_10], 2
0x18001a184  jmp     short loc_18001A193
0x18001a186  mov     eax, r12d
0x18001a189  cmp     [rbp+var_60], 2
0x18001a18d  setz    al
0x18001a190  mov     [rbp+var_10], eax
0x18001a193  mov     rdx, qword ptr [rbp+var_58+8]
0x18001a197  cmp     rdx, [rbp+var_48]
0x18001a19b  jz      short loc_18001A1B1
0x18001a19d  movups  xmm0, [rbp+var_20]
0x18001a1a1  movups  xmmword ptr [rdx], xmm0
0x18001a1a4  mov     eax, [rbp+var_10]
0x18001a1a7  mov     [rdx+10h], eax
0x18001a1aa  add     qword ptr [rbp+var_58+8], 14h
0x18001a1af  jmp     short loc_18001A1BF
0x18001a1b1  lea     r8, [rbp+var_20]
0x18001a1b5  lea     rcx, [rbp+var_58]
0x18001a1b9  call    ??$_Emplace_reallocate@AEBUOneDriveKnownFolderMoveStatusEntry@@@?$vector@UOneDriveKnownFolderMoveStatusEntry@@V?$allocator@UOneDriveKnownFolderMoveStatusEntry@@@std@@@std@@AEAAPEAUOneDriveKnownFolderMoveStatusEntry@@QEAU2@AEBU2@@Z; std::vector<OneDriveKnownFolderMoveStatusEntry>::_Emplace_reallocate<OneDriveKnownFolderMoveStatusEntry const &>(OneDriveKnownFolderMoveStatusEntry * const,OneDriveKnownFolderMoveStatusEntry const &)
0x18001a1be  nop
0x18001a1bf  lea     rcx, [rbp+var_38]
0x18001a1c3  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001a1c8  inc     ebx
0x18001a1ca  cmp     ebx, [rbp+var_40]
0x18001a1cd  jb      loc_18001A10F
0x18001a1d3  mov     rax, [rbp+var_48]
0x18001a1d7  mov     rcx, qword ptr [rbp+var_58]
0x18001a1db  mov     rbx, qword ptr [rbp+var_58+8]
0x18001a1df  sub     rbx, rcx
0x18001a1e2  sar     rbx, 2
0x18001a1e6  mov     rdi, 0CCCCCCCCCCCCCCCDh
0x18001a1f0  imul    rbx, rdi
0x18001a1f4  test    ebx, ebx
0x18001a1f6  jnz     short loc_18001A272
0x18001a1f8  test    rcx, rcx
0x18001a1fb  jz      loc_18001A356
0x18001a201  sub     rax, rcx
0x18001a204  jmp     loc_18001A335
0x18001a209  mov     edx, 1FDh
0x18001a20e  jmp     short loc_18001A215
0x18001a210  mov     edx, 1F9h; void *
0x18001a215  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001a21c  mov     r9d, esi; char *
0x18001a21f  mov     rcx, [rbp+38h]; this
0x18001a223  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a228  nop
0x18001a229  lea     rcx, [rbp+var_38]
0x18001a22d  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001a232  nop
0x18001a233  mov     rcx, qword ptr [rbp+var_58]
0x18001a237  test    rcx, rcx
0x18001a23a  jz      short loc_18001A26E
0x18001a23c  mov     rax, [rbp+var_48]
0x18001a240  sub     rax, rcx
0x18001a243  sar     rax, 2
0x18001a247  mov     rdi, 0CCCCCCCCCCCCCCCDh
0x18001a251  imul    rax, rdi
0x18001a255  lea     rdx, [rax+rax*4]
0x18001a259  shl     rdx, 2
0x18001a25d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001a262  xorps   xmm0, xmm0
0x18001a265  movdqu  [rbp+var_58], xmm0
0x18001a26a  mov     [rbp+var_48], r12
0x18001a26e  mov     ebx, esi
0x18001a270  jmp     short loc_18001A2D9
0x18001a272  mov     eax, ebx
0x18001a274  lea     rcx, [rax+rax*4]
0x18001a278  shl     rcx, 2; cb
0x18001a27c  call    cs:__imp_CoTaskMemAlloc
0x18001a282  mov     r9, rax
0x18001a285  test    rax, rax
0x18001a288  jnz     short loc_18001A2E7
0x18001a28a  mov     rcx, [rbp+38h]; this
0x18001a28e  mov     ebx, 8007000Eh
0x18001a293  mov     r9d, ebx; char *
0x18001a296  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001a29d  mov     edx, 20Bh; void *
0x18001a2a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a2a7  nop
0x18001a2a8  mov     rcx, qword ptr [rbp+var_58]
0x18001a2ac  test    rcx, rcx
0x18001a2af  jz      short loc_18001A2D9
0x18001a2b1  mov     rax, [rbp+var_48]
0x18001a2b5  sub     rax, rcx
0x18001a2b8  sar     rax, 2
0x18001a2bc  imul    rax, rdi
0x18001a2c0  lea     rdx, [rax+rax*4]
0x18001a2c4  shl     rdx, 2
0x18001a2c8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001a2cd  xorps   xmm0, xmm0
0x18001a2d0  movdqu  [rbp+var_58], xmm0
0x18001a2d5  mov     [rbp+var_48], r12
0x18001a2d9  lea     rcx, [rbp+var_30]
0x18001a2dd  call    ?reset@?$unique_any_array_ptr@PEAUIKFMEnrollmentStatus@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<IKFMEnrollmentStatus *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(void)
0x18001a2e2  jmp     loc_18001A08C
0x18001a2e7  mov     r11d, r12d
0x18001a2ea  mov     r8, qword ptr [rbp+var_58]
0x18001a2ee  mov     r10, qword ptr [rbp+var_58+8]
0x18001a2f2  cmp     r8, r10
0x18001a2f5  jz      short loc_18001A320
0x18001a2f7  movups  xmm0, xmmword ptr [r8]
0x18001a2fb  mov     edx, [r8+10h]
0x18001a2ff  mov     eax, r11d
0x18001a302  lea     rcx, [rax+rax*4]
0x18001a306  movups  xmmword ptr [r9+rcx*4], xmm0
0x18001a30b  mov     [r9+rcx*4+10h], edx
0x18001a310  inc     r11d
0x18001a313  add     r8, 14h
0x18001a317  cmp     r8, r10
0x18001a31a  jnz     short loc_18001A2F7
0x18001a31c  mov     r8, qword ptr [rbp+var_58]
0x18001a320  mov     [r14], ebx
0x18001a323  mov     [r15], r9
0x18001a326  test    r8, r8
0x18001a329  jz      short loc_18001A356
0x18001a32b  mov     rax, [rbp+var_48]
0x18001a32f  sub     rax, r8
0x18001a332  mov     rcx, r8
0x18001a335  sar     rax, 2
0x18001a339  imul    rax, rdi
0x18001a33d  lea     rdx, [rax+rax*4]
0x18001a341  shl     rdx, 2
0x18001a345  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001a34a  xorps   xmm0, xmm0
0x18001a34d  mov     [rbp+var_48], r12
0x18001a351  movdqu  [rbp+var_58], xmm0
0x18001a356  lea     rcx, [rbp+var_30]
0x18001a35a  call    ?reset@?$unique_any_array_ptr@PEAUIKFMEnrollmentStatus@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<IKFMEnrollmentStatus *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(void)
0x18001a35f  xor     eax, eax
0x18001a361  mov     rcx, [rbp+var_8]
0x18001a365  xor     rcx, rsp; StackCookie
0x18001a368  call    __security_check_cookie
0x18001a36d  add     rsp, 80h
0x18001a374  pop     r15
0x18001a376  pop     r14
0x18001a378  pop     r12
0x18001a37a  pop     rdi
0x18001a37b  pop     rsi
0x18001a37c  pop     rbx
0x18001a37d  pop     rbp
0x18001a37e  retn
```
