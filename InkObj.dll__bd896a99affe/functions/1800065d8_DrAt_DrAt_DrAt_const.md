# DrAt::DrAt(DrAt const &)

- ea: `0x1800065d8`
- end: `0x180006b7a`
- name: `??0DrAt@@QEAA@AEBV0@@Z`
- size: `1442`
- prototype: `DrAt *__fastcall(DrAt *__hidden this, const struct DrAt *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18003b7e4`
- `0x1800882cc`

## callees

- `0x1800017f4`
- `0x180002740`
- `0x1800065d8`
- `0x180006b80`
- `0x180009200`
- `0x18004451c`
- `0x1800445e8`
- `0x180044658`
- `0x180044ab0`
- `0x180044ac6`
- `0x180044ad2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000669f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006753`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006834`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000669f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006753`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006834`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000692a`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000692a`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800069b2`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180006ab0`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800069b2`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180006ab0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
DrAt *__fastcall DrAt::DrAt(DrAt *this, const struct DrAt *a2)
{
  const struct DrAt *v2; // r14
  DrAt *v3; // rbx
  unsigned __int64 v4; // r13
  volatile signed __int32 *v5; // rax
  unsigned __int64 v6; // rsi
  __int64 v7; // r9
  char *v8; // rax
  char *v9; // rbp
  void *v10; // rcx
  unsigned __int64 v11; // r12
  __int64 v12; // r15
  unsigned __int64 v13; // r15
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rdi
  SIZE_T v16; // rsi
  struct WinHeap *Default; // rax
  DWORD v18; // edx
  LPVOID v19; // rax
  char v20; // al
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // r14
  _QWORD *v24; // rsi
  __int64 v25; // rax
  void **v26; // rdi
  SIZE_T v27; // rbp
  char *v28; // rax
  __int64 v29; // rdx
  char *v30; // r12
  size_t v31; // rsi
  unsigned __int64 v32; // rdx
  __int64 v33; // rdx
  size_t v34; // r8
  __int64 v36; // r8
  void *v37; // rcx
  __int64 v38; // r8
  void *v39; // rcx
  const struct DrAt *pExceptionObject; // [rsp+88h] [rbp+10h] BYREF
  unsigned __int64 v41; // [rsp+90h] [rbp+18h]
  __int64 v42; // [rsp+98h] [rbp+20h]

  pExceptionObject = a2;
  v2 = a2;
  v3 = this;
  v4 = 0;
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &DrAt::`vftable';
  v5 = (volatile signed __int32 *)*((_QWORD *)a2 + 2);
  *((_QWORD *)this + 2) = v5;
  if ( v5 )
    _InterlockedIncrement(v5);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  v6 = *((_QWORD *)a2 + 4);
  v7 = 4;
  if ( v6 )
  {
    if ( v6 > 0x7FFFFFFFFFFFFFFLL || 32 * v6 > 0xFFFFFFFF )
      goto LABEL_65;
    if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + (unsigned int)tls_index)
                                                                   + 4LL) )
    {
      Init_thread_header(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
      if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA == -1 )
      {
        `WinHeap::GetDefault'::`2'::s_WinHeap = 0;
        dwFlags = 0;
        `WinHeap::GetDefault'::`2'::s_WinHeap = HeapCreate(0, 0x10000u, 0);
        atexit(`WinHeap::GetDefault'::`2'::`dynamic atexit destructor for 's_WinHeap'');
        Init_thread_footer(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
      }
    }
    this = (DrAt *)`WinHeap::GetDefault'::`2'::s_WinHeap;
    if ( !`WinHeap::GetDefault'::`2'::s_WinHeap
      || (v8 = (char *)HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, 32 * v6), (v9 = v8) == 0) )
    {
LABEL_65:
      v38 = *((_QWORD *)v3 + 4);
      if ( v38 )
        Allocator<Pair<GuidPtr,Bytes>>::Destruct(this, *((_QWORD *)v3 + 3), v38, v7);
      v39 = (void *)*((_QWORD *)v3 + 3);
      if ( v39 )
      {
        WinFree(v39);
        *((_QWORD *)v3 + 3) = 0;
      }
      *((_QWORD *)v3 + 4) = 0;
      *((_QWORD *)v3 + 5) = 0;
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
    *((_QWORD *)v3 + 3) = v8;
    v10 = (void *)*((_QWORD *)v3 + 4);
  }
  else
  {
    v9 = 0;
    v10 = 0;
  }
  *((_QWORD *)v3 + 5) = v6;
  if ( v9 <= &v9[32 * (_QWORD)v10] )
  {
    v11 = *((_QWORD *)v2 + 3);
    v41 = v11;
    v12 = 32LL * *((_QWORD *)v2 + 4);
    if ( v11 <= v12 + v11 )
    {
      v13 = v12 >> 5;
      if ( v13 )
      {
        v14 = (unsigned __int64)v10 + v13;
        if ( (unsigned __int64)v10 + v13 <= v6 )
        {
LABEL_23:
          v21 = *((_QWORD *)v3 + 4);
          if ( v21 )
            memmove_0((void *)(*((_QWORD *)v3 + 3) + 32 * v13), *((const void **)v3 + 3), 32 * v21);
          v22 = *((_QWORD *)v3 + 3);
          v42 = v22;
          do
          {
            v23 = 32 * v4;
            v24 = (_QWORD *)(32 * v4 + v22);
            if ( v24 )
            {
              v25 = *(_QWORD *)(v23 + v11);
              *v24 = v25;
              if ( v25 )
                _InterlockedIncrement((volatile signed __int32 *)(v25 + 8));
              v26 = (void **)(v24 + 1);
              v24[1] = 0;
              v24[2] = 0;
              v24[3] = 0;
              v27 = *(_QWORD *)(v23 + v11 + 16);
              v28 = 0;
              if ( v27 )
              {
                if ( v27 > 0xFFFFFFFF )
                  goto LABEL_90;
                if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                 + (unsigned int)tls_index)
                                                                               + 4LL) )
                {
                  Init_thread_header(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
                  if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA == -1 )
                  {
                    `WinHeap::GetDefault'::`2'::s_WinHeap = 0;
                    dwFlags = 0;
                    `WinHeap::GetDefault'::`2'::s_WinHeap = HeapCreate(0, 0x10000u, 0);
                    atexit(`WinHeap::GetDefault'::`2'::`dynamic atexit destructor for 's_WinHeap'');
                    Init_thread_footer(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
                  }
                }
                v28 = `WinHeap::GetDefault'::`2'::s_WinHeap
                    ? (char *)HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v27)
                    : 0LL;
                if ( !v28 )
                {
LABEL_90:
                  if ( *v26 )
                  {
                    WinFree(*v26);
                    *v26 = 0;
                  }
                  v24[2] = 0;
                  v24[3] = 0;
                  LODWORD(pExceptionObject) = -2147024882;
                  throw (long *)&pExceptionObject;
                }
                *v26 = v28;
              }
              v24[3] = v27;
              v29 = v24[2];
              if ( v28 <= &v28[v29] )
              {
                v30 = *(char **)(v23 + v11 + 8);
                v31 = *(_QWORD *)(v23 + v41 + 16);
                if ( v30 <= &v30[v31] && v31 )
                {
                  v32 = v31 + v29;
                  if ( v32 <= v27
                    || (v32 < 0x20
                      ? (v32 >= 2
                       ? (v32 >= 4
                        ? (v32 >= 8
                         ? (v33 = (-(__int64)(v32 < 0x10) & 0xFFFFFFFFFFFFFFF0uLL) + 31)
                         : (v33 = 7))
                        : (v33 = 3))
                       : (v33 = 1))
                      : (v33 = v32 | 0xF),
                        (unsigned __int8)Vector<unsigned char,BasicAllocator<unsigned char>>::reserve(v26, v33)) )
                  {
                    v34 = (size_t)v26[1];
                    if ( v34 )
                      memmove_0((char *)*v26 + v31, *v26, v34);
                    memcpy_0(*v26, v30, v31);
                    v26[1] = (char *)v26[1] + v31;
                  }
                }
                v11 = v41;
              }
              v22 = v42;
            }
            ++v4;
          }
          while ( v4 < v13 );
          v2 = pExceptionObject;
          *((_QWORD *)v3 + 4) += v13;
          goto LABEL_50;
        }
        if ( v14 >= 0x20 )
        {
          v15 = v14 | 0xF;
        }
        else
        {
          if ( v14 < 2 )
          {
            v15 = 1;
            v16 = 32;
LABEL_17:
            Default = WinHeap::GetDefault();
            v10 = *(void **)Default;
            if ( *(_QWORD *)Default )
            {
              v18 = *((_DWORD *)Default + 2);
              v19 = v9 ? HeapReAlloc(v10, v18, v9, v16) : HeapAlloc(v10, v18, v16);
              if ( v19 )
              {
                *((_QWORD *)v3 + 3) = v19;
                v20 = 1;
                goto LABEL_22;
              }
            }
LABEL_58:
            v36 = *((_QWORD *)v3 + 4);
            if ( v36 )
              Allocator<Pair<GuidPtr,Bytes>>::Destruct(v10, *((_QWORD *)v3 + 3), v36, v7);
            v37 = (void *)*((_QWORD *)v3 + 3);
            if ( v37 )
            {
              WinFree(v37);
              *((_QWORD *)v3 + 3) = 0;
            }
            *((_QWORD *)v3 + 4) = 0;
            v20 = 0;
            v15 = 0;
LABEL_22:
            *((_QWORD *)v3 + 5) = v15;
            if ( !v20 )
              goto LABEL_50;
            goto LABEL_23;
          }
          if ( v14 < 4 )
          {
            v15 = 3;
            v16 = 96;
            goto LABEL_17;
          }
          if ( v14 < 8 )
          {
            v15 = 7;
            v16 = 224;
            goto LABEL_17;
          }
          if ( v14 < 0x10 )
          {
            v15 = 15;
            v16 = 480;
            goto LABEL_17;
          }
          v15 = 31;
        }
        if ( v15 > 0x7FFFFFFFFFFFFFFLL )
          goto LABEL_58;
        v16 = 32 * v15;
        if ( 32 * v15 > 0xFFFFFFFF )
          goto LABEL_58;
        goto LABEL_17;
      }
    }
  }
LABEL_50:
  *((_BYTE *)v3 + 48) = *((_BYTE *)v2 + 48);
  *((_DWORD *)v3 + 14) = *((_DWORD *)v2 + 14);
  return v3;
}

```

## disassembly

```asm
0x1800065d8  mov     [rsp+pExceptionObject], rdx
0x1800065dd  mov     [rsp+arg_0], rcx
0x1800065e2  push    rbx
0x1800065e3  push    rbp
0x1800065e4  push    rsi
0x1800065e5  push    rdi
0x1800065e6  push    r12
0x1800065e8  push    r13
0x1800065ea  push    r14
0x1800065ec  push    r15
0x1800065ee  sub     rsp, 38h
0x1800065f2  mov     r14, rdx
0x1800065f5  mov     rbx, rcx
0x1800065f8  xor     r13d, r13d
0x1800065fb  mov     [rcx+8], r13d
0x1800065ff  lea     rax, ??_7DrAt@@6B@; const DrAt::`vftable'
0x180006606  mov     [rcx], rax
0x180006609  mov     rax, [rdx+10h]
0x18000660d  mov     [rcx+10h], rax
0x180006611  test    rax, rax
0x180006614  jz      short loc_180006619
0x180006616  lock inc dword ptr [rax]
0x180006619  mov     [rcx+18h], r13
0x18000661d  mov     [rcx+20h], r13
0x180006621  mov     [rcx+28h], r13
0x180006625  mov     rsi, [rdx+20h]
0x180006629  mov     rdx, 7FFFFFFFFFFFFFFh
0x180006633  mov     r8d, 0FFFFFFFFh
0x180006639  mov     r9d, 4
0x18000663f  mov     eax, cs:_tls_index
0x180006645  test    rsi, rsi
0x180006648  jz      loc_180006902
0x18000664e  cmp     rsi, rdx
0x180006651  ja      loc_1800069DC
0x180006657  mov     rdi, rsi
0x18000665a  shl     rdi, 5
0x18000665e  cmp     rdi, r8
0x180006661  ja      loc_1800069DC
0x180006667  mov     ecx, eax
0x180006669  mov     rax, gs:58h
0x180006672  mov     rax, [rax+rcx*8]
0x180006676  mov     eax, [r9+rax]
0x18000667a  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x180006680  jg      loc_180006981
0x180006686  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x18000668d  test    rcx, rcx
0x180006690  jz      loc_1800069DC
0x180006696  mov     r8, rdi; dwBytes
0x180006699  mov     edx, cs:dwFlags; dwFlags
0x18000669f  call    cs:__imp_HeapAlloc
0x1800066a5  mov     rbp, rax
0x1800066a8  test    rax, rax
0x1800066ab  jz      loc_1800069DC
0x1800066b1  mov     [rbx+18h], rax
0x1800066b5  mov     rcx, [rbx+20h]
0x1800066b9  mov     rdx, 7FFFFFFFFFFFFFFh
0x1800066c3  mov     r8d, 0FFFFFFFFh
0x1800066c9  mov     [rbx+28h], rsi
0x1800066cd  mov     rax, rcx
0x1800066d0  shl     rax, 5
0x1800066d4  add     rax, rbp
0x1800066d7  cmp     rbp, rax
0x1800066da  ja      loc_1800068E0
0x1800066e0  mov     r12, [r14+18h]
0x1800066e4  mov     [rsp+78h+arg_10], r12
0x1800066ec  mov     r15, [r14+20h]
0x1800066f0  shl     r15, 5
0x1800066f4  lea     rax, [r15+r12]
0x1800066f8  cmp     r12, rax
0x1800066fb  ja      loc_1800068E0
0x180006701  sar     r15, 5
0x180006705  test    r15, r15
0x180006708  jz      loc_1800068E0
0x18000670e  lea     rdi, [rcx+r15]
0x180006712  cmp     rdi, rsi
0x180006715  jbe     short loc_180006774
0x180006717  cmp     rdi, 20h ; ' '
0x18000671b  jnb     loc_180006935
0x180006721  cmp     rdi, 2
0x180006725  jnb     loc_18000690D
0x18000672b  mov     edi, 1
0x180006730  lea     esi, [rdi+1Fh]
0x180006733  call    ?GetDefault@WinHeap@@SAAEAV1@XZ; WinHeap::GetDefault(void)
0x180006738  mov     rcx, [rax]; hHeap
0x18000673b  test    rcx, rcx
0x18000673e  jz      loc_18000694E
0x180006744  mov     edx, [rax+8]; dwFlags
0x180006747  test    rbp, rbp
0x18000674a  jnz     loc_180006924
0x180006750  mov     r8, rsi; dwBytes
0x180006753  call    cs:__imp_HeapAlloc
0x180006759  test    rax, rax
0x18000675c  jz      loc_18000694E
0x180006762  mov     [rbx+18h], rax
0x180006766  mov     al, 1
0x180006768  mov     [rbx+28h], rdi
0x18000676c  test    al, al
0x18000676e  jz      loc_1800068E0
0x180006774  mov     r8, [rbx+20h]
0x180006778  test    r8, r8
0x18000677b  jnz     loc_180006A5C
0x180006781  mov     rax, [rbx+18h]
0x180006785  mov     [rsp+78h+arg_18], rax
0x18000678d  test    r15, r15
0x180006790  jz      loc_1800068DC
0x180006796  mov     r14, r13
0x180006799  shl     r14, 5
0x18000679d  lea     rsi, [r14+rax]
0x1800067a1  test    rsi, rsi
0x1800067a4  jz      loc_1800068C8
0x1800067aa  mov     [rsp+78h+var_58], rsi
0x1800067af  mov     rax, [r14+r12]
0x1800067b3  mov     [rsi], rax
0x1800067b6  test    rax, rax
0x1800067b9  jz      short loc_1800067BF
0x1800067bb  lock inc dword ptr [rax+8]
0x1800067bf  lea     rdi, [rsi+8]
0x1800067c3  mov     qword ptr [rdi], 0
0x1800067ca  mov     qword ptr [rsi+10h], 0
0x1800067d2  mov     qword ptr [rsi+18h], 0
0x1800067da  mov     rbp, [r14+r12+10h]
0x1800067df  xor     eax, eax
0x1800067e1  test    rbp, rbp
0x1800067e4  jz      short loc_180006846
0x1800067e6  mov     eax, 0FFFFFFFFh
0x1800067eb  cmp     rbp, rax
0x1800067ee  ja      loc_180006B36
0x1800067f4  mov     ecx, cs:_tls_index
0x1800067fa  mov     rax, gs:58h
0x180006803  mov     edx, 4
0x180006808  mov     rax, [rax+rcx*8]
0x18000680c  mov     eax, [rdx+rax]
0x18000680f  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x180006815  jg      loc_180006A78
0x18000681b  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x180006822  test    rcx, rcx
0x180006825  jz      loc_180006ADA
0x18000682b  mov     r8, rbp; dwBytes
0x18000682e  mov     edx, cs:dwFlags; dwFlags
0x180006834  call    cs:__imp_HeapAlloc
0x18000683a  test    rax, rax
0x18000683d  jz      loc_180006B36
0x180006843  mov     [rdi], rax
0x180006846  mov     [rsi+18h], rbp
0x18000684a  mov     rdx, [rdi+8]
0x18000684e  lea     rcx, [rdx+rax]
0x180006852  cmp     rax, rcx
0x180006855  ja      short loc_1800068C0
0x180006857  mov     r12, [r14+r12+8]
0x18000685c  mov     rsi, [rsp+78h+arg_10]
0x180006864  mov     rsi, [r14+rsi+10h]
0x180006869  lea     rax, [r12+rsi]
0x18000686d  cmp     r12, rax
0x180006870  ja      short loc_1800068B8
0x180006872  test    rsi, rsi
0x180006875  jz      short loc_1800068B8
0x180006877  add     rdx, rsi
0x18000687a  cmp     rdx, rbp
0x18000687d  jbe     short loc_180006899
0x18000687f  cmp     rdx, 20h ; ' '
0x180006883  jb      loc_180006AE1
0x180006889  or      rdx, 0Fh
0x18000688d  mov     rcx, rdi
0x180006890  call    ?reserve@?$Vector@EV?$BasicAllocator@E@@@@QEAA_N_K@Z; Vector<uchar,BasicAllocator<uchar>>::reserve(unsigned __int64)
0x180006895  test    al, al
0x180006897  jz      short loc_1800068B8
0x180006899  mov     r8, [rdi+8]; Size
0x18000689d  test    r8, r8
0x1800068a0  jnz     loc_180006B25
0x1800068a6  mov     r8, rsi; Size
0x1800068a9  mov     rdx, r12; Src
0x1800068ac  mov     rcx, [rdi]; void *
0x1800068af  call    memcpy_0
0x1800068b4  add     [rdi+8], rsi
0x1800068b8  mov     r12, [rsp+78h+arg_10]
0x1800068c0  mov     rax, [rsp+78h+arg_18]
0x1800068c8  inc     r13
0x1800068cb  cmp     r13, r15
0x1800068ce  jb      loc_180006796
0x1800068d4  mov     r14, [rsp+78h+pExceptionObject]
0x1800068dc  add     [rbx+20h], r15
0x1800068e0  mov     al, [r14+30h]
0x1800068e4  mov     [rbx+30h], al
0x1800068e7  mov     eax, [r14+38h]
0x1800068eb  mov     [rbx+38h], eax
0x1800068ee  mov     rax, rbx
0x1800068f1  add     rsp, 38h
0x1800068f5  pop     r15
0x1800068f7  pop     r14
0x1800068f9  pop     r13
0x1800068fb  pop     r12
0x1800068fd  pop     rdi
0x1800068fe  pop     rsi
0x1800068ff  pop     rbp
0x180006900  pop     rbx
0x180006901  retn
0x180006902  mov     rbp, r13
0x180006905  mov     rcx, r13
0x180006908  jmp     loc_1800066C9
0x18000690d  cmp     rdi, 4
0x180006911  jnb     loc_180006A28
0x180006917  mov     edi, 3
0x18000691c  lea     esi, [rdi+5Dh]
0x18000691f  jmp     loc_180006733
0x180006924  mov     r9, rsi; dwBytes
0x180006927  mov     r8, rbp; lpMem
0x18000692a  call    cs:__imp_HeapReAlloc
0x180006930  jmp     loc_180006759
0x180006935  or      rdi, 0Fh
0x180006939  cmp     rdi, rdx
0x18000693c  ja      short loc_18000694E
0x18000693e  mov     rsi, rdi
0x180006941  shl     rsi, 5
0x180006945  cmp     rsi, r8
0x180006948  jbe     loc_180006733
0x18000694e  mov     r8, [rbx+20h]
0x180006952  test    r8, r8
0x180006955  jz      short loc_180006960
0x180006957  mov     rdx, [rbx+18h]
0x18000695b  call    ?Destruct@?$Allocator@V?$Pair@VGuidPtr@@VBytes@@@@@@QEAAXPEAV?$Pair@VGuidPtr@@VBytes@@@@_K@Z; Allocator<Pair<GuidPtr,Bytes>>::Destruct(Pair<GuidPtr,Bytes> *,unsigned __int64)
0x180006960  mov     rcx, [rbx+18h]; void *
0x180006964  test    rcx, rcx
0x180006967  jz      short loc_180006972
0x180006969  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x18000696e  mov     [rbx+18h], r13
0x180006972  mov     [rbx+20h], r13
0x180006976  mov     al, r13b
0x180006979  mov     rdi, r13
0x18000697c  jmp     loc_180006768
0x180006981  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180006988  call    _Init_thread_header
0x18000698d  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x180006994  jnz     loc_180006686
0x18000699a  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, r13; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x1800069a1  mov     cs:dwFlags, r13d
0x1800069a8  xor     r8d, r8d; dwMaximumSize
0x1800069ab  mov     edx, 10000h; dwInitialSize
0x1800069b0  xor     ecx, ecx; flOptions
0x1800069b2  call    cs:__imp_HeapCreate
0x1800069b8  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x1800069bf  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x1800069c6  call    atexit
0x1800069cb  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x1800069d2  call    _Init_thread_footer
0x1800069d7  jmp     loc_180006686
0x1800069dc  mov     r8, [rbx+20h]
0x1800069e0  test    r8, r8
0x1800069e3  jz      short loc_1800069EE
0x1800069e5  mov     rdx, [rbx+18h]
0x1800069e9  call    ?Destruct@?$Allocator@V?$Pair@VGuidPtr@@VBytes@@@@@@QEAAXPEAV?$Pair@VGuidPtr@@VBytes@@@@_K@Z; Allocator<Pair<GuidPtr,Bytes>>::Destruct(Pair<GuidPtr,Bytes> *,unsigned __int64)
0x1800069ee  mov     rcx, [rbx+18h]; void *
0x1800069f2  test    rcx, rcx
0x1800069f5  jz      short loc_180006A00
0x1800069f7  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x1800069fc  mov     [rbx+18h], r13
0x180006a00  mov     [rbx+20h], r13
0x180006a04  mov     [rbx+28h], r13
0x180006a08  mov     dword ptr [rsp+78h+pExceptionObject], 8007000Eh
0x180006a13  lea     rdx, _TI1J; pThrowInfo
0x180006a1a  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180006a22  call    _CxxThrowException_0
0x180006a28  cmp     rdi, 8
0x180006a2c  jnb     short loc_180006A3D
0x180006a2e  mov     edi, 7
0x180006a33  mov     esi, 0E0h
0x180006a38  jmp     loc_180006733
0x180006a3d  cmp     rdi, 10h
0x180006a41  jnb     short loc_180006A52
0x180006a43  mov     edi, 0Fh
0x180006a48  mov     esi, 1E0h
0x180006a4d  jmp     loc_180006733
0x180006a52  mov     edi, 1Fh
0x180006a57  jmp     loc_180006939
0x180006a5c  mov     rdx, [rbx+18h]; Src
0x180006a60  shl     r8, 5; Size
0x180006a64  mov     rcx, r15
0x180006a67  shl     rcx, 5
0x180006a6b  add     rcx, rdx; void *
0x180006a6e  call    memmove_0
0x180006a73  jmp     loc_180006781
0x180006a78  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180006a7f  call    _Init_thread_header
0x180006a84  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x180006a8b  jnz     loc_18000681B
0x180006a91  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, 0; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180006a9c  mov     cs:dwFlags, 0
0x180006aa6  xor     r8d, r8d; dwMaximumSize
0x180006aa9  mov     edx, 10000h; dwInitialSize
0x180006aae  xor     ecx, ecx; flOptions
0x180006ab0  call    cs:__imp_HeapCreate
0x180006ab6  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180006abd  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x180006ac4  call    atexit
0x180006ac9  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x180006ad0  call    _Init_thread_footer
0x180006ad5  jmp     loc_18000681B
0x180006ada  xor     eax, eax
0x180006adc  jmp     loc_18000683A
0x180006ae1  cmp     rdx, 2
0x180006ae5  jnb     short loc_180006AF1
  ... truncated ...
```
