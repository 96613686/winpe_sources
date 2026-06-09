# EnrollmentManager::EnumInstalledApplications(_GUID,_GUID,_GUID * *,ulong *,int,int)

- ea: `0x180019d8c`
- end: `0x18001a28f`
- name: `?EnumInstalledApplications@EnrollmentManager@@SAJU_GUID@@0PEAPEAU2@PEAKHH@Z`
- size: `1283`
- prototype: `static int(struct _GUID *__struct_ptr, struct _GUID *__struct_ptr, struct _GUID **, unsigned int *, int, int)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800038d0`
- `0x180003a30`
- `0x180007640`
- `0x1800149c8`
- `0x180017a68`

## callees

- `0x180001dc0`
- `0x1800194e8`
- `0x180019d8c`
- `0x18001bc28`
- `0x180066da6`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001a1f8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a209`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a1f8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a209`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019e54`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019e54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a1a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a1a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall EnrollmentManager::EnumInstalledApplications(
        struct _GUID *a1,
        struct _GUID *a2,
        struct _GUID **a3,
        unsigned int *a4,
        int a5,
        int a6)
{
  __int64 v9; // rdi
  struct _GUID *v10; // rbx
  HRESULT v11; // r14d
  int v12; // r13d
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rax
  struct _GUID *v16; // rax
  int v17; // r8d
  struct _GUID *i; // rax
  struct _GUID *v19; // rcx
  struct _GUID *v20; // rdi
  __int64 v22; // [rsp+30h] [rbp-C8h] BYREF
  int v23; // [rsp+38h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+40h] [rbp-B8h] BYREF
  int v25; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+50h] [rbp-A8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A0h] BYREF
  void *Buf2; // [rsp+60h] [rbp-98h]
  unsigned int *v29; // [rsp+68h] [rbp-90h]
  struct _GUID *v30; // [rsp+70h] [rbp-88h]
  __int64 v31; // [rsp+78h] [rbp-80h]
  __m256i Buf1; // [rsp+80h] [rbp-78h] BYREF
  __m256i v33; // [rsp+A0h] [rbp-58h] BYREF

  v29 = a4;
  Buf2 = a1;
  ppv = 0;
  v26 = 0;
  v24 = 0;
  Buf1.m256i_i64[0] = 6;
  memset(&Buf1.m256i_u64[1], 0, 24);
  v25 = 67108865;
  v9 = 0;
  v31 = 0;
  v10 = (struct _GUID *)std::_List_alloc<0,std::_List_base_types<_GUID>>::_Buynode0(a1, 0, 0);
  v30 = v10;
  if ( !a3 || !a4 )
  {
    v11 = -2147024809;
    goto LABEL_51;
  }
  v11 = CoCreateInstance(&CLSID_PMSvc, 0, 0x17u, &IID_IPMEnumerationManager, &ppv);
  if ( v11 >= 0 )
  {
    v12 = 0;
    if ( memcmp_0(a2, &GUID_NULL, 0x10u) )
    {
      v22 = 0;
      *(struct _GUID *)v33.m256i_i8 = *a2;
      v11 = (*(__int64 (__fastcall **)(LPVOID, __m256i *, __int64 *))(*(_QWORD *)ppv + 72LL))(ppv, &v33, &v22);
      if ( v11 < 0 )
      {
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        goto LABEL_51;
      }
      v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 408LL))(v22, &v25);
      if ( v11 < 0 )
      {
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        goto LABEL_51;
      }
      if ( v25 == 0x20000000 )
      {
        Buf1.m256i_i32[0] = 4;
        Buf1.m256i_i32[2] = 0x20000000;
        v12 = 1;
      }
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v33 = Buf1;
    v11 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __m256i *))(*(_QWORD *)ppv + 24LL))(ppv, &v26, &v33);
    if ( v11 < 0 )
      goto LABEL_51;
    if ( !v26 )
      goto LABEL_20;
    while ( 1 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 24LL))(v26, &v24);
      v11 = v13;
      if ( v13 == 1 )
      {
        v11 = 0;
        *v29 = v9;
        if ( !v9 )
        {
          *a3 = 0;
          break;
        }
        v16 = (struct _GUID *)CoTaskMemAlloc(16 * v9);
        *a3 = v16;
        if ( v16 )
        {
          v17 = 0;
          for ( i = *(struct _GUID **)&v10->Data1; i != v10; i = *(struct _GUID **)&i->Data1 )
            (*a3)[v17++] = i[1];
          break;
        }
LABEL_20:
        v11 = -2147024882;
        break;
      }
      LODWORD(v22) = 0;
      v23 = 0;
      *(_OWORD *)v33.m256i_i8 = 0;
      *(_OWORD *)Buf1.m256i_i8 = 0;
      if ( v13 < 0 )
        break;
      v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 80LL))(v24, &v22);
      if ( v11 < 0 )
        break;
      v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 88LL))(v24, &v23);
      if ( v11 < 0 )
        break;
      if ( v12 )
      {
        if ( !a6 && v23 != 1 )
          goto LABEL_28;
      }
      else if ( !a5 || !a6 && v23 != 1 || (v22 & 0xFFFFFFFD) != 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, __m256i *))(*(_QWORD *)v24 + 224LL))(v24, &Buf1);
        if ( v11 < 0 )
          break;
        if ( memcmp_0(&Buf1, Buf2, 0x10u) || !a6 && v23 != 1 || (_DWORD)v22 && (unsigned int)(v22 - 2) > 2 )
          goto LABEL_28;
      }
      v11 = (*(__int64 (__fastcall **)(__int64, __m256i *))(*(_QWORD *)v24 + 24LL))(v24, &v33);
      if ( v11 < 0 )
        break;
      try
      {
        v15 = std::_List_buy<_GUID>::_Buynode<_GUID const &>(v14, v10, *(_QWORD *)v10->Data4, &v33);
        if ( v9 == 0x7FFFFFFFFFFFFFELL )
          std::_Xlength_error("list<T> too long");
        v31 = ++v9;
        *(_QWORD *)v10->Data4 = v15;
        **(_QWORD **)(v15 + 8) = v15;
      }
      catch ( ... )
      {
        LODWORD(v22) = -2147024882;
        v11 = -2147024882;
        v10 = v30;
        break;
      }
LABEL_28:
      if ( v24 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        v24 = 0;
      }
    }
  }
LABEL_51:
  v19 = *(struct _GUID **)&v10->Data1;
  *(_QWORD *)&v10->Data1 = v10;
  *(_QWORD *)v10->Data4 = v10;
  if ( v19 != v10 )
  {
    do
    {
      v20 = *(struct _GUID **)&v19->Data1;
      operator delete(v19);
      v19 = v20;
    }
    while ( v20 != v10 );
  }
  operator delete(v10);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180019d8c  mov     r11, rsp
0x180019d8f  mov     [r11+8], rbx
0x180019d93  push    rdi
0x180019d94  push    r12
0x180019d96  push    r13
0x180019d98  push    r14
0x180019d9a  push    r15
0x180019d9c  sub     rsp, 0D0h
0x180019da3  mov     rax, cs:__security_cookie
0x180019daa  xor     rax, rsp
0x180019dad  mov     [rsp+0F8h+var_38], rax
0x180019db5  mov     r14, r9
0x180019db8  mov     [rsp+0F8h+var_90], r9
0x180019dbd  mov     r12, r8
0x180019dc0  mov     r15, rdx
0x180019dc3  mov     [rsp+0F8h+Buf2], rcx
0x180019dc8  mov     [rsp+0F8h+var_A0], 0
0x180019dd1  mov     [rsp+0F8h+var_A8], 0
0x180019dda  mov     [rsp+0F8h+var_B8], 0
0x180019de3  mov     qword ptr [r11-78h], 6
0x180019deb  mov     dword ptr [r11-70h], 0
0x180019df3  xorps   xmm0, xmm0
0x180019df6  xor     eax, eax
0x180019df8  movups  xmmword ptr [r11-6Ch], xmm0
0x180019dfd  mov     [r11-5Ch], eax
0x180019e01  mov     [rsp+0F8h+var_B0], 4000001h
0x180019e09  xor     edi, edi
0x180019e0b  mov     [r11-80h], rdi
0x180019e0f  xor     r8d, r8d
0x180019e12  xor     edx, edx
0x180019e14  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@@std@@QEAAPEAU?$_List_node@U_GUID@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<_GUID>>::_Buynode0(std::_List_node<_GUID,void *> *,std::_List_node<_GUID,void *> *)
0x180019e19  mov     rbx, rax
0x180019e1c  mov     [rsp+0F8h+var_88], rax
0x180019e21  test    r12, r12
0x180019e24  jnz     short loc_180019E31
0x180019e26  mov     r14d, 80070057h
0x180019e2c  jmp     loc_18001A1E6
0x180019e31  test    r14, r14
0x180019e34  jz      short loc_180019E26
0x180019e36  lea     rax, [rsp+0F8h+var_A0]
0x180019e3b  mov     [rsp+0F8h+ppv], rax; ppv
0x180019e40  lea     r9, IID_IPMEnumerationManager; riid
0x180019e47  xor     edx, edx; pUnkOuter
0x180019e49  lea     r8d, [rdx+17h]; dwClsContext
0x180019e4d  lea     rcx, CLSID_PMSvc; rclsid
0x180019e54  call    cs:__imp_CoCreateInstance
0x180019e5a  mov     r14d, eax
0x180019e5d  test    eax, eax
0x180019e5f  js      loc_18001A1E6
0x180019e65  xor     r13d, r13d
0x180019e68  lea     r8d, [r13+10h]; Size
0x180019e6c  lea     rdx, GUID_NULL; Buf2
0x180019e73  mov     rcx, r15; Buf1
0x180019e76  call    memcmp_0
0x180019e7b  test    eax, eax
0x180019e7d  jz      loc_180019F4C
0x180019e83  mov     [rsp+0F8h+var_C8], r13
0x180019e88  mov     rcx, [rsp+0F8h+var_A0]
0x180019e8d  movaps  xmm0, xmmword ptr [r15]
0x180019e91  movdqa  [rsp+0F8h+var_58], xmm0
0x180019e9a  mov     rax, [rcx]
0x180019e9d  lea     r8, [rsp+0F8h+var_C8]
0x180019ea2  lea     rdx, [rsp+0F8h+var_58]
0x180019eaa  mov     rax, [rax+48h]
0x180019eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019eb3  mov     r14d, eax
0x180019eb6  test    eax, eax
0x180019eb8  jns     short loc_180019ED6
0x180019eba  mov     rcx, [rsp+0F8h+var_C8]
0x180019ebf  test    rcx, rcx
0x180019ec2  jz      short loc_180019ED1
0x180019ec4  mov     rax, [rcx]
0x180019ec7  mov     rax, [rax+10h]
0x180019ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ed0  nop
0x180019ed1  jmp     loc_18001A1E6
0x180019ed6  mov     rcx, [rsp+0F8h+var_C8]
0x180019edb  mov     rax, [rcx]
0x180019ede  lea     rdx, [rsp+0F8h+var_B0]
0x180019ee3  mov     rax, [rax+198h]
0x180019eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019eef  mov     r14d, eax
0x180019ef2  test    eax, eax
0x180019ef4  jns     short loc_180019F12
0x180019ef6  mov     rcx, [rsp+0F8h+var_C8]
0x180019efb  test    rcx, rcx
0x180019efe  jz      short loc_180019F0D
0x180019f00  mov     rax, [rcx]
0x180019f03  mov     rax, [rax+10h]
0x180019f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f0c  nop
0x180019f0d  jmp     loc_18001A1E6
0x180019f12  mov     eax, 20000000h
0x180019f17  cmp     [rsp+0F8h+var_B0], eax
0x180019f1b  jnz     short loc_180019F35
0x180019f1d  mov     dword ptr [rsp+0F8h+Buf1], 4
0x180019f28  mov     dword ptr [rsp+0F8h+Buf1+8], eax
0x180019f2f  mov     r13d, 1
0x180019f35  mov     rcx, [rsp+0F8h+var_C8]
0x180019f3a  test    rcx, rcx
0x180019f3d  jz      short loc_180019F4C
0x180019f3f  mov     rax, [rcx]
0x180019f42  mov     rax, [rax+10h]
0x180019f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f4b  nop
0x180019f4c  mov     rcx, [rsp+0F8h+var_A0]
0x180019f51  movups  xmm0, [rsp+0F8h+Buf1]
0x180019f59  movaps  [rsp+0F8h+var_58], xmm0
0x180019f61  movups  xmm1, [rsp+0F8h+var_68]
0x180019f69  movaps  [rsp+0F8h+var_48], xmm1
0x180019f71  mov     rax, [rcx]
0x180019f74  lea     r8, [rsp+0F8h+var_58]
0x180019f7c  lea     rdx, [rsp+0F8h+var_A8]
0x180019f81  mov     rax, [rax+18h]
0x180019f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f8a  mov     r14d, eax
0x180019f8d  test    eax, eax
0x180019f8f  js      loc_18001A1E6
0x180019f95  mov     rcx, [rsp+0F8h+var_A8]
0x180019f9a  test    rcx, rcx
0x180019f9d  jnz     short loc_180019FAA
0x180019f9f  mov     r14d, 8007000Eh
0x180019fa5  jmp     loc_18001A1E6
0x180019faa  mov     rax, [rcx]
0x180019fad  lea     rdx, [rsp+0F8h+var_B8]
0x180019fb2  mov     rax, [rax+18h]
0x180019fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fbb  mov     r15d, [rsp+0F8h+arg_28]
0x180019fc3  mov     r14d, eax
0x180019fc6  cmp     eax, 1
0x180019fc9  jz      loc_18001A193
0x180019fcf  mov     dword ptr [rsp+0F8h+var_C8], 0
0x180019fd7  mov     [rsp+0F8h+var_C0], 0
0x180019fdf  xorps   xmm0, xmm0
0x180019fe2  movups  [rsp+0F8h+var_58], xmm0
0x180019fea  xorps   xmm1, xmm1
0x180019fed  movups  [rsp+0F8h+Buf1], xmm1
0x180019ff5  test    eax, eax
0x180019ff7  js      loc_18001A1E6
0x180019ffd  mov     rcx, [rsp+0F8h+var_B8]
0x18001a002  mov     rax, [rcx]
0x18001a005  lea     rdx, [rsp+0F8h+var_C8]
0x18001a00a  mov     rax, [rax+50h]
0x18001a00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a013  mov     r14d, eax
0x18001a016  test    eax, eax
0x18001a018  js      loc_18001A1E6
0x18001a01e  mov     rcx, [rsp+0F8h+var_B8]
0x18001a023  mov     rax, [rcx]
0x18001a026  lea     rdx, [rsp+0F8h+var_C0]
0x18001a02b  mov     rax, [rax+58h]
0x18001a02f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a034  mov     r14d, eax
0x18001a037  test    eax, eax
0x18001a039  js      loc_18001A1E6
0x18001a03f  test    r13d, r13d
0x18001a042  jz      short loc_18001A092
0x18001a044  test    r15d, r15d
0x18001a047  jnz     loc_18001A11D
0x18001a04d  cmp     [rsp+0F8h+var_C0], 1
0x18001a052  jz      loc_18001A11D
0x18001a058  mov     rcx, [rsp+0F8h+var_B8]
0x18001a05d  test    rcx, rcx
0x18001a060  jz      short loc_18001A077
0x18001a062  mov     rax, [rcx]
0x18001a065  mov     rax, [rax+10h]
0x18001a069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a06e  mov     [rsp+0F8h+var_B8], 0
0x18001a077  mov     rcx, [rsp+0F8h+var_A8]
0x18001a07c  mov     rax, [rcx]
0x18001a07f  lea     rdx, [rsp+0F8h+var_B8]
0x18001a084  mov     rax, [rax+18h]
0x18001a088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a08d  jmp     loc_180019FC3
0x18001a092  cmp     [rsp+0F8h+arg_20], 0
0x18001a09a  jz      short loc_18001A0B2
0x18001a09c  test    r15d, r15d
0x18001a09f  jnz     short loc_18001A0A8
0x18001a0a1  cmp     [rsp+0F8h+var_C0], 1
0x18001a0a6  jnz     short loc_18001A0B2
0x18001a0a8  test    dword ptr [rsp+0F8h+var_C8], 0FFFFFFFDh
0x18001a0b0  jz      short loc_18001A11D
0x18001a0b2  mov     rcx, [rsp+0F8h+var_B8]
0x18001a0b7  mov     rax, [rcx]
0x18001a0ba  lea     rdx, [rsp+0F8h+Buf1]
0x18001a0c2  mov     rax, [rax+0E0h]
0x18001a0c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0ce  mov     r14d, eax
0x18001a0d1  test    eax, eax
0x18001a0d3  js      loc_18001A1E6
0x18001a0d9  mov     r8d, 10h; Size
0x18001a0df  mov     rdx, [rsp+0F8h+Buf2]; Buf2
0x18001a0e4  lea     rcx, [rsp+0F8h+Buf1]; Buf1
0x18001a0ec  call    memcmp_0
0x18001a0f1  test    eax, eax
0x18001a0f3  jnz     loc_18001A058
0x18001a0f9  test    r15d, r15d
0x18001a0fc  jnz     short loc_18001A109
0x18001a0fe  cmp     [rsp+0F8h+var_C0], 1
0x18001a103  jnz     loc_18001A058
0x18001a109  mov     eax, dword ptr [rsp+0F8h+var_C8]
0x18001a10d  test    eax, eax
0x18001a10f  jz      short loc_18001A11D
0x18001a111  add     eax, 0FFFFFFFEh
0x18001a114  cmp     eax, 2
0x18001a117  ja      loc_18001A058
0x18001a11d  mov     rcx, [rsp+0F8h+var_B8]
0x18001a122  mov     rax, [rcx]
0x18001a125  lea     rdx, [rsp+0F8h+var_58]
0x18001a12d  mov     rax, [rax+18h]
0x18001a131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a136  mov     r14d, eax
0x18001a139  test    eax, eax
0x18001a13b  js      loc_18001A1E6
0x18001a141  lea     r9, [rsp+0F8h+var_58]
0x18001a149  mov     r8, [rbx+8]
0x18001a14d  mov     rdx, rbx
0x18001a150  call    ??$_Buynode@AEBU_GUID@@@?$_List_buy@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAAPEAU?$_List_node@U_GUID@@PEAX@1@PEAU21@0AEBU_GUID@@@Z; std::_List_buy<_GUID>::_Buynode<_GUID const &>(std::_List_node<_GUID,void *> *,std::_List_node<_GUID,void *> *,_GUID const &)
0x18001a155  mov     rdx, rax
0x18001a158  mov     rcx, 7FFFFFFFFFFFFFEh
0x18001a162  sub     rcx, rdi
0x18001a165  cmp     rcx, 1
0x18001a169  jb      loc_18001A281
0x18001a16f  inc     rdi
0x18001a172  mov     [rsp+0F8h+var_80], rdi
0x18001a177  mov     [rbx+8], rdx
0x18001a17b  mov     rax, [rax+8]
0x18001a17f  mov     [rax], rdx
0x18001a182  jmp     loc_18001A058
0x18001a187  mov     r14d, dword ptr [rsp+0F8h+var_C8]
0x18001a18c  mov     rbx, [rsp+0F8h+var_88]
0x18001a191  jmp     short loc_18001A1E6
0x18001a193  xor     r14d, r14d
0x18001a196  mov     rax, [rsp+0F8h+var_90]
0x18001a19b  mov     [rax], edi
0x18001a19d  test    rdi, rdi
0x18001a1a0  jz      short loc_18001A1E2
0x18001a1a2  shl     rdi, 4
0x18001a1a6  mov     rcx, rdi; cb
0x18001a1a9  call    cs:__imp_CoTaskMemAlloc
0x18001a1af  mov     [r12], rax
0x18001a1b3  test    rax, rax
0x18001a1b6  jz      loc_180019F9F
0x18001a1bc  xor     r8d, r8d
0x18001a1bf  mov     rax, [rbx]
0x18001a1c2  cmp     rax, rbx
0x18001a1c5  jz      short loc_18001A1E6
0x18001a1c7  movups  xmm0, xmmword ptr [rax+10h]
0x18001a1cb  movsxd  rdx, r8d
0x18001a1ce  add     rdx, rdx
0x18001a1d1  mov     rcx, [r12]
0x18001a1d5  movdqu  xmmword ptr [rcx+rdx*8], xmm0
0x18001a1da  inc     r8d
0x18001a1dd  mov     rax, [rax]
0x18001a1e0  jmp     short loc_18001A1C2
0x18001a1e2  mov     [r12], r14
0x18001a1e6  mov     rcx, [rbx]
0x18001a1e9  mov     [rbx], rbx
0x18001a1ec  mov     [rbx+8], rbx
0x18001a1f0  cmp     rcx, rbx
0x18001a1f3  jz      short loc_18001A206
0x18001a1f5  mov     rdi, [rcx]
0x18001a1f8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a1fe  mov     rcx, rdi
0x18001a201  cmp     rdi, rbx
0x18001a204  jnz     short loc_18001A1F5
0x18001a206  mov     rcx, rbx
0x18001a209  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a20f  nop
0x18001a210  mov     rcx, [rsp+0F8h+var_B8]
0x18001a215  test    rcx, rcx
0x18001a218  jz      short loc_18001A227
0x18001a21a  mov     rax, [rcx]
0x18001a21d  mov     rax, [rax+10h]
0x18001a221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a226  nop
0x18001a227  mov     rcx, [rsp+0F8h+var_A8]
0x18001a22c  test    rcx, rcx
0x18001a22f  jz      short loc_18001A23E
0x18001a231  mov     rax, [rcx]
0x18001a234  mov     rax, [rax+10h]
0x18001a238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a23d  nop
0x18001a23e  mov     rcx, [rsp+0F8h+var_A0]
0x18001a243  test    rcx, rcx
0x18001a246  jz      short loc_18001A255
0x18001a248  mov     rax, [rcx]
0x18001a24b  mov     rax, [rax+10h]
0x18001a24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a254  nop
0x18001a255  mov     eax, r14d
0x18001a258  mov     rcx, [rsp+0F8h+var_38]
0x18001a260  xor     rcx, rsp; StackCookie
0x18001a263  call    __security_check_cookie
0x18001a268  mov     rbx, [rsp+0F8h+arg_0]
0x18001a270  add     rsp, 0D0h
0x18001a277  pop     r15
0x18001a279  pop     r14
0x18001a27b  pop     r13
0x18001a27d  pop     r12
  ... truncated ...
```
