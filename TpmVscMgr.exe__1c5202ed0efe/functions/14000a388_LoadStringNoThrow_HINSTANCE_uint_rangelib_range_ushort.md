# LoadStringNoThrow(HINSTANCE__ *,uint,rangelib::range<ushort *> *)

- ea: `0x14000a388`
- end: `0x14000a756`
- name: `?LoadStringNoThrow@@YA?AV?$one_of@U?$typevec@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@Unil@typbldlib@@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@@typveclib@@U?$metavalue@$0A@@typbldlib@@U?$vec_size@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@Unil@typbldlib@@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@U56@@detail@2@U34@@oneoflib@@PEAUHINSTANCE__@@IPEAV?$range@PEAG@rangelib@@@Z`
- size: `974`
- prototype: `__int64 __fastcall(__int64, HINSTANCE, UINT, _QWORD *)`
- caller_count: `8`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x14000641c`
- `0x140008784`
- `0x140009dd8`
- `0x140009e94`
- `0x14000a75c`
- `0x14000e510`
- `0x14000e62c`
- `0x14000f54c`

## callees

- `0x1400016a0`
- `0x140001934`
- `0x14000196c`
- `0x1400071b0`
- `0x1400071d0`
- `0x140008454`
- `0x140008728`
- `0x140009f58`
- `0x14000a388`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000a41d`
- `KERNEL32!SetLastError` at `0x14000a41d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14000a449`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14000a449`

## pseudocode

```c
__int64 __fastcall LoadStringNoThrow(__int64 a1, HINSTANCE a2, UINT a3, _QWORD *a4)
{
  unsigned __int64 v4; // r14
  HINSTANCE v6; // r15
  unsigned __int64 v8; // r12
  unsigned __int64 v9; // rax
  WCHAR *v10; // rbx
  unsigned __int64 v11; // rdi
  int StringW; // eax
  __int64 v13; // r15
  WCHAR *v14; // rdx
  _DWORD *v15; // rdx
  int *v16; // rax
  bool v17; // zf
  __int64 v18; // rcx
  __int64 v19; // rdi
  int *v20; // rdx
  int v21; // r8d
  int v22; // r15d
  bool v23; // di
  unsigned int v24; // edx
  unsigned int v25; // edx
  float v26; // xmm0_4
  float v27; // xmm0_4
  unsigned __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rcx
  _DWORD *v31; // rax
  TpmVscMgrMeta *v33; // [rsp+20h] [rbp-59h] BYREF
  int v34; // [rsp+28h] [rbp-51h] BYREF
  int v35; // [rsp+2Ch] [rbp-4Dh]
  int v36; // [rsp+30h] [rbp-49h] BYREF
  int v37; // [rsp+34h] [rbp-45h]
  UINT uID; // [rsp+38h] [rbp-41h]
  _DWORD v39[2]; // [rsp+40h] [rbp-39h] BYREF
  _DWORD v40[2]; // [rsp+48h] [rbp-31h] BYREF
  _DWORD v41[2]; // [rsp+50h] [rbp-29h] BYREF
  _DWORD v42[2]; // [rsp+58h] [rbp-21h] BYREF
  WCHAR *v43; // [rsp+60h] [rbp-19h]
  HINSTANCE v44; // [rsp+68h] [rbp-11h]
  int v45; // [rsp+70h] [rbp-9h] BYREF
  int v46; // [rsp+74h] [rbp-5h]
  WCHAR *v47; // [rsp+78h] [rbp-1h]
  int v48; // [rsp+80h] [rbp+7h]

  v4 = 128;
  uID = a3;
  v44 = a2;
  v6 = a2;
  v33 = (TpmVscMgrMeta *)0x100000000LL;
  v8 = 2;
  while ( 1 )
  {
    v9 = v4 * v8;
    if ( !is_mul_ok(v4, v8) )
      v9 = -1;
    v43 = (WCHAR *)operator new[](v9, (const struct std::nothrow_t *)std::nothrow);
    v10 = v43;
    if ( !v43 )
      break;
    v35 = 1;
    *v43 = 0;
    v34 = 0;
    SetLastError(0);
    v11 = (__int64)(2 * v4) >> 1;
    if ( v11 > 0xFFFFFFFF )
      TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL);
    StringW = LoadStringW(v6, uID, v10, v11);
    v39[0] = 0;
    v13 = StringW;
    v39[1] = 1;
    errorlib::scoped_error<hresult_error::tag>::operator=(&v34, v39);
    v35 = 3;
    if ( v34 )
    {
      v45 = v34;
      v17 = v34 == 0;
      v46 = 2;
      v35 = 5;
      goto LABEL_18;
    }
    if ( !(_DWORD)v13 )
    {
      v40[0] = 1814;
      v40[1] = 1;
      errorlib::error_initiated<errorlib::scoped_error<winerror_error::tag>>();
      v15 = v40;
LABEL_10:
      v16 = (int *)errorlib::scoped_error<hresult_error::tag>::operator=(&v34, v15);
      v48 = 2;
      v45 = *v16;
      v46 = 2;
      v16[1] = 5;
      v17 = v45 == 0;
LABEL_18:
      if ( !v17 )
        errorlib::error_propagated<errorlib::scoped_error<winerror_error::tag>>();
      v48 = 0;
      goto LABEL_21;
    }
    if ( (int)v13 + 1 >= v11 )
    {
      v41[0] = 122;
      v41[1] = 1;
      errorlib::error_initiated<errorlib::scoped_error<winerror_error::tag>>();
      v15 = v41;
      goto LABEL_10;
    }
    v14 = &v10[v4];
    v10[v13] = 0;
    v18 = v13 - v11;
    if ( (__int64)(v13 - v11) < 0 )
    {
      v19 = -(__int64)v11;
      if ( v19 >= v18 )
        v18 = v19;
    }
    v46 = HIDWORD(v43);
    v47 = &v14[v18];
    v45 = (int)v10;
    v48 = 1;
LABEL_21:
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v34, (unsigned int)v14);
    v21 = v48;
    if ( v48 || (v46 = 3, !v45) )
    {
      if ( a4 )
      {
        v20 = 0;
        if ( v48 )
        {
          v20 = &v45;
          if ( v48 != 1 )
            v20 = 0;
        }
        v30 = *((_QWORD *)v20 + 1);
        *a4 = *(_QWORD *)v20;
        a4[1] = v30;
      }
      *(_QWORD *)a1 = v10;
      *(_DWORD *)(a1 + 8) = 1;
      if ( !v21 )
        errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(
          (__int64)&v45,
          (unsigned int)v20);
      v48 = 2;
      goto LABEL_52;
    }
    v8 = (unsigned int)(v48 + 2);
    v42[0] = v45;
    v22 = v48 + 5;
    v42[1] = v48 + 2;
    v46 = v48 + 5;
    errorlib::error_propagated<errorlib::scoped_error<winerror_error::tag>>();
    errorlib::scoped_error<hresult_error::tag>::operator=(&v33, v42);
    v36 = 122;
    v37 = 1;
    errorlib::error_initiated<errorlib::scoped_error<winerror_error::tag>>();
    v23 = (_DWORD)v33 == 122;
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v36, v24);
    if ( !v23 )
    {
      v29 = (int)v33;
      *(_DWORD *)a1 = (_DWORD)v33;
      *(_DWORD *)(a1 + 4) = v8;
      HIDWORD(v33) = v22;
      if ( v29 )
        errorlib::error_propagated<errorlib::scoped_error<winerror_error::tag>>();
      v17 = v48 == 0;
      *(_DWORD *)(a1 + 8) = 0;
      if ( v17 )
        errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v45, v25);
      v48 = v8;
      operator delete(v10);
      goto LABEL_52;
    }
    if ( (_DWORD)v33 == 87 || (_DWORD)v33 == 6 )
      TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)(unsigned int)v33);
    HIDWORD(v33) = 4;
    if ( (v4 & 0x8000000000000000uLL) != 0LL )
      v26 = (float)(int)(v4 & 1 | (v4 >> 1)) + (float)(int)(v4 & 1 | (v4 >> 1));
    else
      v26 = (float)(int)v4;
    v27 = v26 * 1.5;
    v28 = 0;
    if ( v27 >= 9.223372e18 )
    {
      v27 = v27 - 9.223372e18;
      if ( v27 < 9.223372e18 )
        v28 = 0x8000000000000000uLL;
    }
    v4 = v28 + (unsigned int)(int)v27 + 1LL;
    if ( !v48 )
      errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v45, v25);
    v48 = v8;
    operator delete(v10);
    v6 = v44;
  }
  v36 = 14;
  v37 = 1;
  errorlib::error_initiated<errorlib::scoped_error<winerror_error::tag>>();
  v31 = (_DWORD *)errorlib::scoped_error<hresult_error::tag>::operator=(&v33, &v36);
  *(_DWORD *)(a1 + 8) = v8;
  *(_DWORD *)a1 = *v31;
  *(_DWORD *)(a1 + 4) = v8;
  v31[1] = 5;
  if ( *(_DWORD *)a1 )
    errorlib::error_propagated<errorlib::scoped_error<winerror_error::tag>>();
  *(_DWORD *)(a1 + 8) = 0;
LABEL_52:
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)&v33, (unsigned int)v20);
  return a1;
}

```

## disassembly

```asm
0x14000a388  push    rbp
0x14000a38a  push    rbx
0x14000a38b  push    rsi
0x14000a38c  push    rdi
0x14000a38d  push    r12
0x14000a38f  push    r13
0x14000a391  push    r14
0x14000a393  push    r15
0x14000a395  lea     rbp, [rsp-1Fh]
0x14000a39a  sub     rsp, 98h
0x14000a3a1  mov     rax, cs:__security_cookie
0x14000a3a8  xor     rax, rsp
0x14000a3ab  mov     [rbp+57h+var_48], rax
0x14000a3af  mov     r14d, 80h
0x14000a3b5  mov     [rbp+57h+uID], r8d
0x14000a3b9  mov     r13, r9
0x14000a3bc  mov     [rbp+57h+var_68], rdx
0x14000a3c0  mov     r15, rdx
0x14000a3c3  mov     dword ptr [rbp+57h+var_B0], 0
0x14000a3ca  mov     rsi, rcx
0x14000a3cd  mov     dword ptr [rbp+57h+var_B0+4], 1
0x14000a3d4  lea     r12d, [r14-7Eh]
0x14000a3d8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000a3df  mov     rax, r12
0x14000a3e2  mul     r14
0x14000a3e5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000a3ec  cmovb   rax, rcx
0x14000a3f0  mov     rcx, rax; unsigned __int64
0x14000a3f3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000a3f8  mov     [rbp+57h+var_70], rax
0x14000a3fc  mov     rbx, rax
0x14000a3ff  test    rax, rax
0x14000a402  jz      loc_14000A6E6
0x14000a408  xor     eax, eax
0x14000a40a  mov     [rbp+57h+var_A4], 1
0x14000a411  xor     ecx, ecx; dwErrCode
0x14000a413  mov     [rbx], ax
0x14000a416  mov     [rbp+57h+var_A8], eax
0x14000a419  lea     r12, [r14+r14]
0x14000a41d  call    cs:__imp_SetLastError
0x14000a423  mov     rdi, r12
0x14000a426  mov     eax, 0FFFFFFFFh
0x14000a42b  sar     rdi, 1
0x14000a42e  cmp     rdi, rax
0x14000a431  jbe     short loc_14000A43D
0x14000a433  mov     ecx, 80004004h; this
0x14000a438  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x14000a43d  mov     edx, [rbp+57h+uID]; uID
0x14000a440  mov     r9d, edi; cchBufferMax
0x14000a443  mov     r8, rbx; lpBuffer
0x14000a446  mov     rcx, r15; hInstance
0x14000a449  call    cs:__imp_LoadStringW
0x14000a44f  lea     rdx, [rbp+57h+var_90]
0x14000a453  mov     [rbp+57h+var_90], 0
0x14000a45a  lea     rcx, [rbp+57h+var_A8]
0x14000a45e  movsxd  r15, eax
0x14000a461  mov     [rbp+57h+var_8C], 1
0x14000a468  call    ??4?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<hresult_error::tag>::operator=(errorlib::scoped_error<hresult_error::tag>)
0x14000a46d  mov     eax, [rbp+57h+var_A8]
0x14000a470  mov     [rbp+57h+var_A4], 3
0x14000a477  test    eax, eax
0x14000a479  jnz     loc_14000A526
0x14000a47f  test    r15d, r15d
0x14000a482  jnz     short loc_14000A4C7
0x14000a484  mov     [rbp+57h+var_88], 716h
0x14000a48b  mov     [rbp+57h+var_84], 1
0x14000a492  call    ??$error_initiated@V?$scoped_error@Utag@winerror_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@winerror_error@@@0@AEBUtag@winerror_error@@@Z; errorlib::error_initiated<errorlib::scoped_error<winerror_error::tag>>(errorlib::scoped_error<winerror_error::tag> const &,winerror_error::tag const &)
0x14000a497  lea     rdx, [rbp+57h+var_88]
0x14000a49b  lea     rcx, [rbp+57h+var_A8]
0x14000a49f  call    ??4?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<hresult_error::tag>::operator=(errorlib::scoped_error<hresult_error::tag>)
0x14000a4a4  mov     rcx, rax
0x14000a4a7  mov     [rbp+57h+var_50], 2
0x14000a4ae  mov     eax, [rax]
0x14000a4b0  mov     [rbp+57h+var_60], eax
0x14000a4b3  mov     [rbp+57h+var_5C], 2
0x14000a4ba  mov     dword ptr [rcx+4], 5
0x14000a4c1  cmp     [rbp+57h+var_60], 0
0x14000a4c5  jmp     short loc_14000A539
0x14000a4c7  lea     eax, [r15+1]
0x14000a4cb  movsxd  rcx, eax
0x14000a4ce  cmp     rcx, rdi
0x14000a4d1  jnb     short loc_14000A50A
0x14000a4d3  xor     eax, eax
0x14000a4d5  lea     rdx, [r12+rbx]
0x14000a4d9  mov     rcx, r15
0x14000a4dc  mov     [rbx+r15*2], ax
0x14000a4e1  sub     rcx, rdi
0x14000a4e4  jns     short loc_14000A4F0
0x14000a4e6  neg     rdi
0x14000a4e9  cmp     rdi, rcx
0x14000a4ec  cmovge  rcx, rdi
0x14000a4f0  mov     eax, dword ptr [rbp+57h+var_70+4]
0x14000a4f3  mov     [rbp+57h+var_5C], eax
0x14000a4f6  lea     rax, [rdx+rcx*2]
0x14000a4fa  mov     [rbp+57h+var_58], rax
0x14000a4fe  mov     [rbp+57h+var_60], ebx
0x14000a501  mov     [rbp+57h+var_50], 1
0x14000a508  jmp     short loc_14000A547
0x14000a50a  mov     [rbp+57h+var_80], 7Ah ; 'z'
0x14000a511  mov     [rbp+57h+var_7C], 1
0x14000a518  call    ??$error_initiated@V?$scoped_error@Utag@winerror_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@winerror_error@@@0@AEBUtag@winerror_error@@@Z; errorlib::error_initiated<errorlib::scoped_error<winerror_error::tag>>(errorlib::scoped_error<winerror_error::tag> const &,winerror_error::tag const &)
0x14000a51d  lea     rdx, [rbp+57h+var_80]
0x14000a521  jmp     loc_14000A49B
0x14000a526  mov     [rbp+57h+var_60], eax
0x14000a529  test    eax, eax
0x14000a52b  mov     [rbp+57h+var_5C], 2
0x14000a532  mov     [rbp+57h+var_A4], 5
0x14000a539  jz      short loc_14000A540
0x14000a53b  call    ??$error_propagated@V?$scoped_error@Utag@winerror_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@winerror_error@@@0@AEBUtag@winerror_error@@@Z; errorlib::error_propagated<errorlib::scoped_error<winerror_error::tag>>(errorlib::scoped_error<winerror_error::tag> const &,winerror_error::tag const &)
0x14000a540  mov     [rbp+57h+var_50], 0
0x14000a547  lea     rcx, [rbp+57h+var_A8]
0x14000a54b  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x14000a550  mov     r8d, [rbp+57h+var_50]
0x14000a554  test    r8d, r8d
0x14000a557  jnz     loc_14000A69C
0x14000a55d  mov     eax, [rbp+57h+var_60]
0x14000a560  mov     [rbp+57h+var_5C], 3
0x14000a567  test    eax, eax
0x14000a569  jz      loc_14000A69C
0x14000a56f  lea     r12d, [r8+2]
0x14000a573  mov     [rbp+57h+var_78], eax
0x14000a576  lea     r15d, [r8+5]
0x14000a57a  mov     [rbp+57h+var_74], r12d
0x14000a57e  mov     [rbp+57h+var_5C], r15d
0x14000a582  call    ??$error_propagated@V?$scoped_error@Utag@winerror_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@winerror_error@@@0@AEBUtag@winerror_error@@@Z; errorlib::error_propagated<errorlib::scoped_error<winerror_error::tag>>(errorlib::scoped_error<winerror_error::tag> const &,winerror_error::tag const &)
0x14000a587  lea     rdx, [rbp+57h+var_78]
0x14000a58b  lea     rcx, [rbp+57h+var_B0]
0x14000a58f  call    ??4?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<hresult_error::tag>::operator=(errorlib::scoped_error<hresult_error::tag>)
0x14000a594  mov     [rbp+57h+var_A0], 7Ah ; 'z'
0x14000a59b  mov     [rbp+57h+var_9C], 1
0x14000a5a2  call    ??$error_initiated@V?$scoped_error@Utag@winerror_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@winerror_error@@@0@AEBUtag@winerror_error@@@Z; errorlib::error_initiated<errorlib::scoped_error<winerror_error::tag>>(errorlib::scoped_error<winerror_error::tag> const &,winerror_error::tag const &)
0x14000a5a7  cmp     dword ptr [rbp+57h+var_B0], 7Ah ; 'z'
0x14000a5ab  lea     rcx, [rbp+57h+var_A0]
0x14000a5af  setz    dil
0x14000a5b3  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x14000a5b8  test    dil, dil
0x14000a5bb  jz      loc_14000A65F
0x14000a5c1  mov     ecx, dword ptr [rbp+57h+var_B0]; this
0x14000a5c4  cmp     ecx, 57h ; 'W'
0x14000a5c7  jz      short loc_14000A5CE
0x14000a5c9  cmp     ecx, 6
0x14000a5cc  jnz     short loc_14000A5D3
0x14000a5ce  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x14000a5d3  mov     dword ptr [rbp+57h+var_B0+4], 4
0x14000a5da  xorps   xmm0, xmm0
0x14000a5dd  test    r14, r14
0x14000a5e0  js      short loc_14000A5E9
0x14000a5e2  cvtsi2ss xmm0, r14
0x14000a5e7  jmp     short loc_14000A5FF
0x14000a5e9  mov     rax, r14
0x14000a5ec  and     r14d, 1
0x14000a5f0  shr     rax, 1
0x14000a5f3  or      rax, r14
0x14000a5f6  cvtsi2ss xmm0, rax
0x14000a5fb  addss   xmm0, xmm0
0x14000a5ff  mulss   xmm0, cs:__real@3fc00000
0x14000a607  xor     eax, eax
0x14000a609  comiss  xmm0, cs:__real@5f000000
0x14000a610  jb      short loc_14000A630
0x14000a612  subss   xmm0, cs:__real@5f000000
0x14000a61a  comiss  xmm0, cs:__real@5f000000
0x14000a621  jnb     short loc_14000A630
0x14000a623  mov     rcx, 8000000000000000h
0x14000a62d  mov     rax, rcx
0x14000a630  cvttss2si r14, xmm0
0x14000a635  inc     r14
0x14000a638  add     r14, rax
0x14000a63b  cmp     [rbp+57h+var_50], 0
0x14000a63f  jnz     short loc_14000A64A
0x14000a641  lea     rcx, [rbp+57h+var_60]
0x14000a645  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x14000a64a  mov     rcx, rbx; void *
0x14000a64d  mov     [rbp+57h+var_50], r12d
0x14000a651  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000a656  mov     r15, [rbp+57h+var_68]
0x14000a65a  jmp     loc_14000A3D8
0x14000a65f  mov     eax, dword ptr [rbp+57h+var_B0]
0x14000a662  mov     [rsi], eax
0x14000a664  mov     [rsi+4], r12d
0x14000a668  mov     dword ptr [rbp+57h+var_B0+4], r15d
0x14000a66c  test    eax, eax
0x14000a66e  jz      short loc_14000A675
0x14000a670  call    ??$error_propagated@V?$scoped_error@Utag@winerror_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@winerror_error@@@0@AEBUtag@winerror_error@@@Z; errorlib::error_propagated<errorlib::scoped_error<winerror_error::tag>>(errorlib::scoped_error<winerror_error::tag> const &,winerror_error::tag const &)
0x14000a675  cmp     [rbp+57h+var_50], 0
0x14000a679  mov     dword ptr [rsi+8], 0
0x14000a680  jnz     short loc_14000A68B
0x14000a682  lea     rcx, [rbp+57h+var_60]
0x14000a686  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x14000a68b  mov     rcx, rbx; void *
0x14000a68e  mov     [rbp+57h+var_50], r12d
0x14000a692  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000a697  jmp     loc_14000A72A
0x14000a69c  test    r13, r13
0x14000a69f  jz      short loc_14000A6C5
0x14000a6a1  xor     edx, edx
0x14000a6a3  test    r8d, r8d
0x14000a6a6  jz      short loc_14000A6B6
0x14000a6a8  xor     eax, eax
0x14000a6aa  lea     rdx, [rbp+57h+var_60]
0x14000a6ae  cmp     r8d, 1
0x14000a6b2  cmovnz  rdx, rax
0x14000a6b6  mov     rcx, [rdx+8]
0x14000a6ba  mov     rax, [rdx]
0x14000a6bd  mov     [r13+0], rax
0x14000a6c1  mov     [r13+8], rcx
0x14000a6c5  mov     [rsi], rbx
0x14000a6c8  mov     dword ptr [rsi+8], 1
0x14000a6cf  test    r8d, r8d
0x14000a6d2  jnz     short loc_14000A6DD
0x14000a6d4  lea     rcx, [rbp+57h+var_60]
0x14000a6d8  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x14000a6dd  mov     [rbp+57h+var_50], 2
0x14000a6e4  jmp     short loc_14000A72A
0x14000a6e6  mov     [rbp+57h+var_A0], 0Eh
0x14000a6ed  mov     [rbp+57h+var_9C], 1
0x14000a6f4  call    ??$error_initiated@V?$scoped_error@Utag@winerror_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@winerror_error@@@0@AEBUtag@winerror_error@@@Z; errorlib::error_initiated<errorlib::scoped_error<winerror_error::tag>>(errorlib::scoped_error<winerror_error::tag> const &,winerror_error::tag const &)
0x14000a6f9  lea     rdx, [rbp+57h+var_A0]
0x14000a6fd  lea     rcx, [rbp+57h+var_B0]
0x14000a701  call    ??4?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<hresult_error::tag>::operator=(errorlib::scoped_error<hresult_error::tag>)
0x14000a706  mov     [rsi+8], r12d
0x14000a70a  mov     ecx, [rax]
0x14000a70c  mov     [rsi], ecx
0x14000a70e  mov     [rsi+4], r12d
0x14000a712  mov     dword ptr [rax+4], 5
0x14000a719  cmp     dword ptr [rsi], 0
0x14000a71c  jz      short loc_14000A723
0x14000a71e  call    ??$error_propagated@V?$scoped_error@Utag@winerror_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@winerror_error@@@0@AEBUtag@winerror_error@@@Z; errorlib::error_propagated<errorlib::scoped_error<winerror_error::tag>>(errorlib::scoped_error<winerror_error::tag> const &,winerror_error::tag const &)
0x14000a723  mov     dword ptr [rsi+8], 0
0x14000a72a  lea     rcx, [rbp+57h+var_B0]
0x14000a72e  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x14000a733  mov     rax, rsi
0x14000a736  mov     rcx, [rbp+57h+var_48]
0x14000a73a  xor     rcx, rsp; StackCookie
0x14000a73d  call    __security_check_cookie
0x14000a742  add     rsp, 98h
0x14000a749  pop     r15
0x14000a74b  pop     r14
0x14000a74d  pop     r13
0x14000a74f  pop     r12
0x14000a751  pop     rdi
0x14000a752  pop     rsi
0x14000a753  pop     rbx
0x14000a754  pop     rbp
0x14000a755  retn
```
