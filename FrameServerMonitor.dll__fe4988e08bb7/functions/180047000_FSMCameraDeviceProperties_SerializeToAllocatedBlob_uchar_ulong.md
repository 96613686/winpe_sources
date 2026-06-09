# FSMCameraDeviceProperties::SerializeToAllocatedBlob(uchar * *,ulong *)

- ea: `0x180047000`
- end: `0x180047353`
- name: `?SerializeToAllocatedBlob@FSMCameraDeviceProperties@@UEAAJPEAPEAEPEAK@Z`
- size: `851`
- prototype: `__int64 __fastcall(FSMCameraDeviceProperties *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800019f0`
- `0x1800060f8`
- `0x180006a98`
- `0x18003191c`
- `0x180031964`
- `0x180047000`
- `0x18004bf50`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004703f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004703f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047324`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047324`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800471b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004731a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800471b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004731a`

## pseudocode

```c
__int64 __fastcall FSMCameraDeviceProperties::SerializeToAllocatedBlob(
        FSMCameraDeviceProperties *this,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  unsigned __int8 *v6; // r15
  int v7; // edi
  int v8; // ecx
  __int64 v9; // rdx
  unsigned int v10; // eax
  unsigned int v11; // esi
  __int64 v12; // r12
  __int64 v13; // rax
  unsigned int v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  void **unique_cotaskmem; // rax
  void *v19; // rcx
  __int64 v20; // r13
  __int64 v21; // r12
  __int64 v22; // rax
  unsigned int v23; // edi
  int v24; // eax
  unsigned __int8 *v25; // rax
  unsigned int v27; // [rsp+30h] [rbp-39h]
  LPVOID pv; // [rsp+38h] [rbp-31h] BYREF
  unsigned __int8 *v29; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int8 **v30; // [rsp+48h] [rbp-21h]
  unsigned int *v31; // [rsp+50h] [rbp-19h]
  __int128 v32; // [rsp+58h] [rbp-11h] BYREF
  __int128 v33; // [rsp+68h] [rbp-1h]
  size_t Size[2]; // [rsp+78h] [rbp+Fh]

  v31 = a3;
  v30 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v6 = 0;
  v29 = 0;
  if ( !a2 )
  {
    v7 = -2147467261;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_52;
    v9 = 33;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids, this, v8);
    goto LABEL_52;
  }
  v10 = *((_DWORD *)this + 16);
  v27 = v10;
  *a2 = 0;
  if ( !a3 )
  {
    v7 = -2147467261;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_52;
    v9 = 34;
    goto LABEL_4;
  }
  v11 = 0;
  v7 = 0;
  *a3 = 0;
  v12 = 0;
  while ( 1 )
  {
    if ( (unsigned int)v12 >= v10 )
    {
      if ( !v11 )
        goto LABEL_52;
      unique_cotaskmem = (void **)wil::make_unique_cotaskmem_nothrow<unsigned char [0]>(&pv, v11);
      wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
        (void **)&v29,
        unique_cotaskmem);
      v19 = pv;
      pv = 0;
      if ( v19 )
        CoTaskMemFree(v19);
      v6 = v29;
      if ( v29 )
      {
        v20 = 0;
        v21 = 0;
        while ( 1 )
        {
          if ( (unsigned int)v21 >= v27 )
          {
            v25 = v6;
            v6 = 0;
            *v30 = v25;
            *v31 = v11;
            goto LABEL_52;
          }
          v22 = *((_QWORD *)this + 7);
          v32 = 0;
          v33 = 0;
          *(_OWORD *)Size = 0;
          v7 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(v22 + 8 * v21) + 64LL))(
                 *(_QWORD *)(v22 + 8 * v21),
                 &v32);
          if ( v7 < 0 )
            break;
          v23 = v20 + 48;
          if ( (int)v20 + 48 < (unsigned int)v20 )
          {
            v7 = -2147024362;
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_52;
            v16 = 41;
            goto LABEL_21;
          }
          if ( v23 + HIDWORD(Size[0]) < v23 )
          {
            v7 = -2147024362;
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_52;
            v16 = 42;
            goto LABEL_21;
          }
          if ( v11 < v23 + HIDWORD(Size[0]) )
          {
            v7 = -1072860816;
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_52;
            v17 = 43;
            goto LABEL_24;
          }
          *(_OWORD *)&v6[v20] = v32;
          *(_OWORD *)&v6[v20 + 16] = v33;
          *(_OWORD *)&v6[v20 + 32] = *(_OWORD *)Size;
          v24 = HIDWORD(Size[0]);
          if ( HIDWORD(Size[0]) )
          {
            memcpy_0(&v6[v23], (const void *)Size[1], HIDWORD(Size[0]));
            v24 = HIDWORD(Size[0]);
          }
          v20 = v23 + v24;
          if ( (unsigned int)v20 < v23 )
          {
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_18;
            v15 = 45;
            goto LABEL_17;
          }
          v21 = (unsigned int)(v21 + 1);
          v7 = 0;
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_52;
        v17 = 39;
      }
      else
      {
        v7 = -2147024882;
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_52;
        v17 = 38;
      }
LABEL_24:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids, this, v7);
      goto LABEL_52;
    }
    v13 = *((_QWORD *)this + 7);
    v32 = 0;
    v33 = 0;
    *(_OWORD *)Size = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(v13 + 8 * v12) + 64LL))(
           *(_QWORD *)(v13 + 8 * v12),
           &v32);
    if ( v7 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_52;
      v17 = 35;
      goto LABEL_24;
    }
    v14 = v11 + 48;
    if ( v11 + 48 < v11 )
      break;
    v11 = v14 + HIDWORD(Size[0]);
    if ( v14 + HIDWORD(Size[0]) < v14 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v15 = 37;
LABEL_17:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v15,
          WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids,
          this,
          -2147024362);
      }
LABEL_18:
      v7 = -2147024362;
      goto LABEL_52;
    }
    v10 = v27;
    v12 = (unsigned int)(v12 + 1);
    v7 = 0;
  }
  v7 = -2147024362;
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v16 = 36;
LABEL_21:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids,
      this,
      -2147024362);
  }
LABEL_52:
  if ( v6 )
    CoTaskMemFree(v6);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180047000  mov     [rsp-8+arg_18], rbx
0x180047005  push    rbp
0x180047006  push    rsi
0x180047007  push    rdi
0x180047008  push    r12
0x18004700a  push    r13
0x18004700c  push    r14
0x18004700e  push    r15
0x180047010  lea     rbp, [rsp-27h]
0x180047015  sub     rsp, 90h
0x18004701c  mov     rax, cs:__security_cookie
0x180047023  xor     rax, rsp
0x180047026  mov     [rbp+57h+var_38], rax
0x18004702a  mov     r14, rcx
0x18004702d  mov     [rbp+57h+var_70], r8
0x180047031  add     rcx, 10h; lpCriticalSection
0x180047035  mov     [rbp+57h+var_78], rdx
0x180047039  mov     r12, r8
0x18004703c  mov     rdi, rdx
0x18004703f  call    cs:__imp_EnterCriticalSection
0x180047045  xor     r15d, r15d
0x180047048  mov     [rbp+57h+var_80], r15
0x18004704c  test    rdi, rdi
0x18004704f  jnz     short loc_18004708C
0x180047051  mov     ecx, 80004003h
0x180047056  mov     edi, ecx
0x180047058  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004705d  cmp     al, 1
0x18004705f  jb      loc_180047312
0x180047065  lea     edx, [r15+21h]
0x180047069  mov     [rsp+0C0h+var_A0], ecx
0x18004706d  mov     rcx, cs:WPP_GLOBAL_Control
0x180047074  lea     r8, WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids
0x18004707b  mov     r9, r14
0x18004707e  mov     rcx, [rcx+10h]
0x180047082  call    WPP_SF_qD
0x180047087  jmp     loc_180047312
0x18004708c  mov     eax, [r14+40h]
0x180047090  mov     [rbp+57h+var_90], eax
0x180047093  mov     [rdi], r15
0x180047096  test    r12, r12
0x180047099  jnz     short loc_1800470B6
0x18004709b  mov     ecx, 80004003h
0x1800470a0  mov     edi, ecx
0x1800470a2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800470a7  cmp     al, 1
0x1800470a9  jb      loc_180047312
0x1800470af  lea     edx, [r12+22h]
0x1800470b4  jmp     short loc_180047069
0x1800470b6  xor     esi, esi
0x1800470b8  xor     edi, edi
0x1800470ba  mov     [r12], esi
0x1800470be  xor     r12d, r12d
0x1800470c1  cmp     r12d, eax
0x1800470c4  jnb     loc_180047186
0x1800470ca  mov     rax, [r14+38h]
0x1800470ce  lea     rdx, [rbp+57h+var_68]
0x1800470d2  xorps   xmm0, xmm0
0x1800470d5  movups  [rbp+57h+var_68], xmm0
0x1800470d9  movups  [rbp+57h+var_58], xmm0
0x1800470dd  movups  xmmword ptr [rbp+57h+Size], xmm0
0x1800470e1  mov     rcx, [rax+r12*8]
0x1800470e5  mov     rax, [rcx]
0x1800470e8  mov     rax, [rax+40h]
0x1800470ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470f1  mov     edi, eax
0x1800470f3  test    eax, eax
0x1800470f5  js      short loc_18004716B
0x1800470f7  lea     ecx, [rsi+30h]
0x1800470fa  cmp     ecx, esi
0x1800470fc  jb      short loc_180047149
0x1800470fe  mov     esi, dword ptr [rbp+57h+Size+4]
0x180047101  add     esi, ecx
0x180047103  cmp     esi, ecx
0x180047105  jb      short loc_180047111
0x180047107  mov     eax, [rbp+57h+var_90]
0x18004710a  inc     r12d
0x18004710d  xor     edi, edi
0x18004710f  jmp     short loc_1800470C1
0x180047111  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047116  mov     esi, 80070216h
0x18004711b  cmp     al, 1
0x18004711d  jb      short loc_180047142
0x18004711f  mov     edx, 25h ; '%'
0x180047124  mov     rcx, cs:WPP_GLOBAL_Control
0x18004712b  lea     r8, WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids
0x180047132  mov     r9, r14
0x180047135  mov     [rsp+0C0h+var_A0], esi
0x180047139  mov     rcx, [rcx+10h]
0x18004713d  call    WPP_SF_qD
0x180047142  mov     edi, esi
0x180047144  jmp     loc_180047312
0x180047149  mov     esi, 80070216h
0x18004714e  mov     edi, esi
0x180047150  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047155  cmp     al, 1
0x180047157  jb      loc_180047312
0x18004715d  mov     edx, 24h ; '$'
0x180047162  mov     [rsp+0C0h+var_A0], esi
0x180047166  jmp     loc_18004706D
0x18004716b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047170  cmp     al, 1
0x180047172  jb      loc_180047312
0x180047178  mov     edx, 23h ; '#'
0x18004717d  mov     [rsp+0C0h+var_A0], edi
0x180047181  jmp     loc_18004706D
0x180047186  test    esi, esi
0x180047188  jz      loc_180047312
0x18004718e  mov     edx, esi
0x180047190  lea     rcx, [rbp+57h+pv]
0x180047194  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<uchar [0]>(unsigned __int64)
0x180047199  mov     rdx, rax
0x18004719c  lea     rcx, [rbp+57h+var_80]
0x1800471a0  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x1800471a5  mov     rcx, [rbp+57h+pv]; pv
0x1800471a9  mov     [rbp+57h+pv], r15
0x1800471ad  test    rcx, rcx
0x1800471b0  jz      short loc_1800471B8
0x1800471b2  call    cs:__imp_CoTaskMemFree
0x1800471b8  mov     r15, [rbp+57h+var_80]
0x1800471bc  test    r15, r15
0x1800471bf  jnz     short loc_1800471D9
0x1800471c1  mov     edi, 8007000Eh
0x1800471c6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800471cb  cmp     al, 1
0x1800471cd  jb      loc_180047312
0x1800471d3  lea     edx, [r15+26h]
0x1800471d7  jmp     short loc_18004717D
0x1800471d9  xor     r13d, r13d
0x1800471dc  xor     r12d, r12d
0x1800471df  cmp     r12d, [rbp+57h+var_90]
0x1800471e3  jnb     loc_1800472FF
0x1800471e9  mov     rax, [r14+38h]
0x1800471ed  lea     rdx, [rbp+57h+var_68]
0x1800471f1  xorps   xmm0, xmm0
0x1800471f4  movups  [rbp+57h+var_68], xmm0
0x1800471f8  movups  [rbp+57h+var_58], xmm0
0x1800471fc  movups  xmmword ptr [rbp+57h+Size], xmm0
0x180047200  mov     rcx, [rax+r12*8]
0x180047204  mov     rax, [rcx]
0x180047207  mov     rax, [rax+40h]
0x18004720b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047210  mov     edi, eax
0x180047212  test    eax, eax
0x180047214  js      loc_1800472EC
0x18004721a  lea     edi, [r13+30h]
0x18004721e  cmp     edi, r13d
0x180047221  jb      loc_1800472D2
0x180047227  mov     ecx, dword ptr [rbp+57h+Size+4]
0x18004722a  add     ecx, edi
0x18004722c  cmp     ecx, edi
0x18004722e  jb      loc_1800472B8
0x180047234  cmp     esi, ecx
0x180047236  jb      short loc_1800472A0
0x180047238  movups  xmm0, [rbp+57h+var_68]
0x18004723c  movups  xmmword ptr [r13+r15+0], xmm0
0x180047242  movups  xmm1, [rbp+57h+var_58]
0x180047246  movups  xmmword ptr [r13+r15+10h], xmm1
0x18004724c  movups  xmm0, xmmword ptr [rbp+57h+Size]
0x180047250  movups  xmmword ptr [r13+r15+20h], xmm0
0x180047256  mov     eax, dword ptr [rbp+57h+Size+4]
0x180047259  test    eax, eax
0x18004725b  jz      short loc_180047271
0x18004725d  mov     rdx, [rbp+57h+Size+8]; Src
0x180047261  mov     r8d, eax; Size
0x180047264  mov     ecx, edi
0x180047266  add     rcx, r15; void *
0x180047269  call    memcpy_0
0x18004726e  mov     eax, dword ptr [rbp+57h+Size+4]
0x180047271  lea     r13d, [rdi+rax]
0x180047275  cmp     r13d, edi
0x180047278  jb      short loc_180047284
0x18004727a  inc     r12d
0x18004727d  xor     edi, edi
0x18004727f  jmp     loc_1800471DF
0x180047284  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047289  mov     esi, 80070216h
0x18004728e  cmp     al, 1
0x180047290  jb      loc_180047142
0x180047296  mov     edx, 2Dh ; '-'
0x18004729b  jmp     loc_180047124
0x1800472a0  mov     edi, 0C00D7170h
0x1800472a5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800472aa  cmp     al, 1
0x1800472ac  jb      short loc_180047312
0x1800472ae  mov     edx, 2Bh ; '+'
0x1800472b3  jmp     loc_18004717D
0x1800472b8  mov     esi, 80070216h
0x1800472bd  mov     edi, esi
0x1800472bf  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800472c4  cmp     al, 1
0x1800472c6  jb      short loc_180047312
0x1800472c8  mov     edx, 2Ah ; '*'
0x1800472cd  jmp     loc_180047162
0x1800472d2  mov     esi, 80070216h
0x1800472d7  mov     edi, esi
0x1800472d9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800472de  cmp     al, 1
0x1800472e0  jb      short loc_180047312
0x1800472e2  mov     edx, 29h ; ')'
0x1800472e7  jmp     loc_180047162
0x1800472ec  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800472f1  cmp     al, 1
0x1800472f3  jb      short loc_180047312
0x1800472f5  mov     edx, 27h ; '''
0x1800472fa  jmp     loc_18004717D
0x1800472ff  mov     rcx, [rbp+57h+var_78]
0x180047303  mov     rax, r15
0x180047306  xor     r15d, r15d
0x180047309  mov     [rcx], rax
0x18004730c  mov     rax, [rbp+57h+var_70]
0x180047310  mov     [rax], esi
0x180047312  test    r15, r15
0x180047315  jz      short loc_180047320
0x180047317  mov     rcx, r15; pv
0x18004731a  call    cs:__imp_CoTaskMemFree
0x180047320  lea     rcx, [r14+10h]; lpCriticalSection
0x180047324  call    cs:__imp_LeaveCriticalSection
0x18004732a  mov     eax, edi
0x18004732c  mov     rcx, [rbp+57h+var_38]
0x180047330  xor     rcx, rsp; StackCookie
0x180047333  call    __security_check_cookie
0x180047338  mov     rbx, [rsp+0C0h+arg_18]
0x180047340  add     rsp, 90h
0x180047347  pop     r15
0x180047349  pop     r14
0x18004734b  pop     r13
0x18004734d  pop     r12
0x18004734f  pop     rdi
0x180047350  pop     rsi
0x180047351  pop     rbp
0x180047352  retn
```
