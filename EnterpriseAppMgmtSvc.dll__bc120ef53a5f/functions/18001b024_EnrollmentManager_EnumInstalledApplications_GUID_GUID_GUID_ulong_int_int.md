# EnrollmentManager::EnumInstalledApplications(_GUID,_GUID,_GUID * *,ulong *,int,int)

- ea: `0x18001b024`
- end: `0x18001b540`
- name: `?EnumInstalledApplications@EnrollmentManager@@SAJU_GUID@@0PEAPEAU2@PEAKHH@Z`
- size: `1308`
- prototype: `static int(struct _GUID *__struct_ptr, struct _GUID *__struct_ptr, struct _GUID **, unsigned int *, int, int)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800039e0`
- `0x180003b40`
- `0x1800078f0`
- `0x180015634`
- `0x180018840`

## callees

- `0x180001df0`
- `0x18001a734`
- `0x18001b024`
- `0x18001ce70`
- `0x18006c8c6`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001b49c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b4b3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b49c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b4b3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b0ec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b0ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b447`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b447`

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
0x18001b024  mov     r11, rsp
0x18001b027  mov     [r11+8], rbx
0x18001b02b  push    rdi
0x18001b02c  push    r12
0x18001b02e  push    r13
0x18001b030  push    r14
0x18001b032  push    r15
0x18001b034  sub     rsp, 0D0h
0x18001b03b  mov     rax, cs:__security_cookie
0x18001b042  xor     rax, rsp
0x18001b045  mov     [rsp+0F8h+var_38], rax
0x18001b04d  mov     r14, r9
0x18001b050  mov     [rsp+0F8h+var_90], r9
0x18001b055  mov     r12, r8
0x18001b058  mov     r15, rdx
0x18001b05b  mov     [rsp+0F8h+Buf2], rcx
0x18001b060  mov     [rsp+0F8h+var_A0], 0
0x18001b069  mov     [rsp+0F8h+var_A8], 0
0x18001b072  mov     [rsp+0F8h+var_B8], 0
0x18001b07b  mov     qword ptr [r11-78h], 6
0x18001b083  mov     dword ptr [r11-70h], 0
0x18001b08b  xorps   xmm0, xmm0
0x18001b08e  xor     eax, eax
0x18001b090  movups  xmmword ptr [r11-6Ch], xmm0
0x18001b095  mov     [r11-5Ch], eax
0x18001b099  mov     [rsp+0F8h+var_B0], 4000001h
0x18001b0a1  xor     edi, edi
0x18001b0a3  mov     [r11-80h], rdi
0x18001b0a7  xor     r8d, r8d
0x18001b0aa  xor     edx, edx
0x18001b0ac  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@@std@@QEAAPEAU?$_List_node@U_GUID@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<_GUID>>::_Buynode0(std::_List_node<_GUID,void *> *,std::_List_node<_GUID,void *> *)
0x18001b0b1  mov     rbx, rax
0x18001b0b4  mov     [rsp+0F8h+var_88], rax
0x18001b0b9  test    r12, r12
0x18001b0bc  jnz     short loc_18001B0C9
0x18001b0be  mov     r14d, 80070057h
0x18001b0c4  jmp     loc_18001B48A
0x18001b0c9  test    r14, r14
0x18001b0cc  jz      short loc_18001B0BE
0x18001b0ce  lea     rax, [rsp+0F8h+var_A0]
0x18001b0d3  mov     [rsp+0F8h+ppv], rax; ppv
0x18001b0d8  lea     r9, IID_IPMEnumerationManager; riid
0x18001b0df  xor     edx, edx; pUnkOuter
0x18001b0e1  lea     r8d, [rdx+17h]; dwClsContext
0x18001b0e5  lea     rcx, CLSID_PMSvc; rclsid
0x18001b0ec  call    cs:__imp_CoCreateInstance
0x18001b0f3  nop     dword ptr [rax+rax+00h]
0x18001b0f8  mov     r14d, eax
0x18001b0fb  test    eax, eax
0x18001b0fd  js      loc_18001B48A
0x18001b103  xor     r13d, r13d
0x18001b106  lea     r8d, [r13+10h]; Size
0x18001b10a  lea     rdx, GUID_NULL; Buf2
0x18001b111  mov     rcx, r15; Buf1
0x18001b114  call    memcmp_0
0x18001b119  test    eax, eax
0x18001b11b  jz      loc_18001B1EA
0x18001b121  mov     [rsp+0F8h+var_C8], r13
0x18001b126  mov     rcx, [rsp+0F8h+var_A0]
0x18001b12b  movaps  xmm0, xmmword ptr [r15]
0x18001b12f  movdqa  [rsp+0F8h+var_58], xmm0
0x18001b138  mov     rax, [rcx]
0x18001b13b  lea     r8, [rsp+0F8h+var_C8]
0x18001b140  lea     rdx, [rsp+0F8h+var_58]
0x18001b148  mov     rax, [rax+48h]
0x18001b14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b151  mov     r14d, eax
0x18001b154  test    eax, eax
0x18001b156  jns     short loc_18001B174
0x18001b158  mov     rcx, [rsp+0F8h+var_C8]
0x18001b15d  test    rcx, rcx
0x18001b160  jz      short loc_18001B16F
0x18001b162  mov     rax, [rcx]
0x18001b165  mov     rax, [rax+10h]
0x18001b169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b16e  nop
0x18001b16f  jmp     loc_18001B48A
0x18001b174  mov     rcx, [rsp+0F8h+var_C8]
0x18001b179  mov     rax, [rcx]
0x18001b17c  lea     rdx, [rsp+0F8h+var_B0]
0x18001b181  mov     rax, [rax+198h]
0x18001b188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b18d  mov     r14d, eax
0x18001b190  test    eax, eax
0x18001b192  jns     short loc_18001B1B0
0x18001b194  mov     rcx, [rsp+0F8h+var_C8]
0x18001b199  test    rcx, rcx
0x18001b19c  jz      short loc_18001B1AB
0x18001b19e  mov     rax, [rcx]
0x18001b1a1  mov     rax, [rax+10h]
0x18001b1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1aa  nop
0x18001b1ab  jmp     loc_18001B48A
0x18001b1b0  mov     eax, 20000000h
0x18001b1b5  cmp     [rsp+0F8h+var_B0], eax
0x18001b1b9  jnz     short loc_18001B1D3
0x18001b1bb  mov     dword ptr [rsp+0F8h+Buf1], 4
0x18001b1c6  mov     dword ptr [rsp+0F8h+Buf1+8], eax
0x18001b1cd  mov     r13d, 1
0x18001b1d3  mov     rcx, [rsp+0F8h+var_C8]
0x18001b1d8  test    rcx, rcx
0x18001b1db  jz      short loc_18001B1EA
0x18001b1dd  mov     rax, [rcx]
0x18001b1e0  mov     rax, [rax+10h]
0x18001b1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1e9  nop
0x18001b1ea  mov     rcx, [rsp+0F8h+var_A0]
0x18001b1ef  movups  xmm0, [rsp+0F8h+Buf1]
0x18001b1f7  movaps  [rsp+0F8h+var_58], xmm0
0x18001b1ff  movups  xmm1, [rsp+0F8h+var_68]
0x18001b207  movaps  [rsp+0F8h+var_48], xmm1
0x18001b20f  mov     rax, [rcx]
0x18001b212  lea     r8, [rsp+0F8h+var_58]
0x18001b21a  lea     rdx, [rsp+0F8h+var_A8]
0x18001b21f  mov     rax, [rax+18h]
0x18001b223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b228  mov     r14d, eax
0x18001b22b  test    eax, eax
0x18001b22d  js      loc_18001B48A
0x18001b233  mov     rcx, [rsp+0F8h+var_A8]
0x18001b238  test    rcx, rcx
0x18001b23b  jnz     short loc_18001B248
0x18001b23d  mov     r14d, 8007000Eh
0x18001b243  jmp     loc_18001B48A
0x18001b248  mov     rax, [rcx]
0x18001b24b  lea     rdx, [rsp+0F8h+var_B8]
0x18001b250  mov     rax, [rax+18h]
0x18001b254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b259  mov     r15d, [rsp+0F8h+arg_28]
0x18001b261  mov     r14d, eax
0x18001b264  cmp     eax, 1
0x18001b267  jz      loc_18001B431
0x18001b26d  mov     dword ptr [rsp+0F8h+var_C8], 0
0x18001b275  mov     [rsp+0F8h+var_C0], 0
0x18001b27d  xorps   xmm0, xmm0
0x18001b280  movups  [rsp+0F8h+var_58], xmm0
0x18001b288  xorps   xmm1, xmm1
0x18001b28b  movups  [rsp+0F8h+Buf1], xmm1
0x18001b293  test    eax, eax
0x18001b295  js      loc_18001B48A
0x18001b29b  mov     rcx, [rsp+0F8h+var_B8]
0x18001b2a0  mov     rax, [rcx]
0x18001b2a3  lea     rdx, [rsp+0F8h+var_C8]
0x18001b2a8  mov     rax, [rax+50h]
0x18001b2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2b1  mov     r14d, eax
0x18001b2b4  test    eax, eax
0x18001b2b6  js      loc_18001B48A
0x18001b2bc  mov     rcx, [rsp+0F8h+var_B8]
0x18001b2c1  mov     rax, [rcx]
0x18001b2c4  lea     rdx, [rsp+0F8h+var_C0]
0x18001b2c9  mov     rax, [rax+58h]
0x18001b2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2d2  mov     r14d, eax
0x18001b2d5  test    eax, eax
0x18001b2d7  js      loc_18001B48A
0x18001b2dd  test    r13d, r13d
0x18001b2e0  jz      short loc_18001B330
0x18001b2e2  test    r15d, r15d
0x18001b2e5  jnz     loc_18001B3BB
0x18001b2eb  cmp     [rsp+0F8h+var_C0], 1
0x18001b2f0  jz      loc_18001B3BB
0x18001b2f6  mov     rcx, [rsp+0F8h+var_B8]
0x18001b2fb  test    rcx, rcx
0x18001b2fe  jz      short loc_18001B315
0x18001b300  mov     rax, [rcx]
0x18001b303  mov     rax, [rax+10h]
0x18001b307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b30c  mov     [rsp+0F8h+var_B8], 0
0x18001b315  mov     rcx, [rsp+0F8h+var_A8]
0x18001b31a  mov     rax, [rcx]
0x18001b31d  lea     rdx, [rsp+0F8h+var_B8]
0x18001b322  mov     rax, [rax+18h]
0x18001b326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b32b  jmp     loc_18001B261
0x18001b330  cmp     [rsp+0F8h+arg_20], 0
0x18001b338  jz      short loc_18001B350
0x18001b33a  test    r15d, r15d
0x18001b33d  jnz     short loc_18001B346
0x18001b33f  cmp     [rsp+0F8h+var_C0], 1
0x18001b344  jnz     short loc_18001B350
0x18001b346  test    dword ptr [rsp+0F8h+var_C8], 0FFFFFFFDh
0x18001b34e  jz      short loc_18001B3BB
0x18001b350  mov     rcx, [rsp+0F8h+var_B8]
0x18001b355  mov     rax, [rcx]
0x18001b358  lea     rdx, [rsp+0F8h+Buf1]
0x18001b360  mov     rax, [rax+0E0h]
0x18001b367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b36c  mov     r14d, eax
0x18001b36f  test    eax, eax
0x18001b371  js      loc_18001B48A
0x18001b377  mov     r8d, 10h; Size
0x18001b37d  mov     rdx, [rsp+0F8h+Buf2]; Buf2
0x18001b382  lea     rcx, [rsp+0F8h+Buf1]; Buf1
0x18001b38a  call    memcmp_0
0x18001b38f  test    eax, eax
0x18001b391  jnz     loc_18001B2F6
0x18001b397  test    r15d, r15d
0x18001b39a  jnz     short loc_18001B3A7
0x18001b39c  cmp     [rsp+0F8h+var_C0], 1
0x18001b3a1  jnz     loc_18001B2F6
0x18001b3a7  mov     eax, dword ptr [rsp+0F8h+var_C8]
0x18001b3ab  test    eax, eax
0x18001b3ad  jz      short loc_18001B3BB
0x18001b3af  add     eax, 0FFFFFFFEh
0x18001b3b2  cmp     eax, 2
0x18001b3b5  ja      loc_18001B2F6
0x18001b3bb  mov     rcx, [rsp+0F8h+var_B8]
0x18001b3c0  mov     rax, [rcx]
0x18001b3c3  lea     rdx, [rsp+0F8h+var_58]
0x18001b3cb  mov     rax, [rax+18h]
0x18001b3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3d4  mov     r14d, eax
0x18001b3d7  test    eax, eax
0x18001b3d9  js      loc_18001B48A
0x18001b3df  lea     r9, [rsp+0F8h+var_58]
0x18001b3e7  mov     r8, [rbx+8]
0x18001b3eb  mov     rdx, rbx
0x18001b3ee  call    ??$_Buynode@AEBU_GUID@@@?$_List_buy@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAAPEAU?$_List_node@U_GUID@@PEAX@1@PEAU21@0AEBU_GUID@@@Z; std::_List_buy<_GUID>::_Buynode<_GUID const &>(std::_List_node<_GUID,void *> *,std::_List_node<_GUID,void *> *,_GUID const &)
0x18001b3f3  mov     rdx, rax
0x18001b3f6  mov     rcx, 7FFFFFFFFFFFFFEh
0x18001b400  sub     rcx, rdi
0x18001b403  cmp     rcx, 1
0x18001b407  jb      loc_18001B532
0x18001b40d  inc     rdi
0x18001b410  mov     [rsp+0F8h+var_80], rdi
0x18001b415  mov     [rbx+8], rdx
0x18001b419  mov     rax, [rax+8]
0x18001b41d  mov     [rax], rdx
0x18001b420  jmp     loc_18001B2F6
0x18001b425  mov     r14d, dword ptr [rsp+0F8h+var_C8]
0x18001b42a  mov     rbx, [rsp+0F8h+var_88]
0x18001b42f  jmp     short loc_18001B48A
0x18001b431  xor     r14d, r14d
0x18001b434  mov     rax, [rsp+0F8h+var_90]
0x18001b439  mov     [rax], edi
0x18001b43b  test    rdi, rdi
0x18001b43e  jz      short loc_18001B486
0x18001b440  shl     rdi, 4
0x18001b444  mov     rcx, rdi; cb
0x18001b447  call    cs:__imp_CoTaskMemAlloc
0x18001b44e  nop     dword ptr [rax+rax+00h]
0x18001b453  mov     [r12], rax
0x18001b457  test    rax, rax
0x18001b45a  jz      loc_18001B23D
0x18001b460  xor     r8d, r8d
0x18001b463  mov     rax, [rbx]
0x18001b466  cmp     rax, rbx
0x18001b469  jz      short loc_18001B48A
0x18001b46b  movups  xmm0, xmmword ptr [rax+10h]
0x18001b46f  movsxd  rdx, r8d
0x18001b472  add     rdx, rdx
0x18001b475  mov     rcx, [r12]
0x18001b479  movdqu  xmmword ptr [rcx+rdx*8], xmm0
0x18001b47e  inc     r8d
0x18001b481  mov     rax, [rax]
0x18001b484  jmp     short loc_18001B466
0x18001b486  mov     [r12], r14
0x18001b48a  mov     rcx, [rbx]
0x18001b48d  mov     [rbx], rbx
0x18001b490  mov     [rbx+8], rbx
0x18001b494  cmp     rcx, rbx
0x18001b497  jz      short loc_18001B4B0
0x18001b499  mov     rdi, [rcx]
0x18001b49c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b4a3  nop     dword ptr [rax+rax+00h]
0x18001b4a8  mov     rcx, rdi
0x18001b4ab  cmp     rdi, rbx
0x18001b4ae  jnz     short loc_18001B499
0x18001b4b0  mov     rcx, rbx
0x18001b4b3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b4ba  nop     dword ptr [rax+rax+00h]
0x18001b4bf  nop
0x18001b4c0  mov     rcx, [rsp+0F8h+var_B8]
0x18001b4c5  test    rcx, rcx
0x18001b4c8  jz      short loc_18001B4D7
0x18001b4ca  mov     rax, [rcx]
0x18001b4cd  mov     rax, [rax+10h]
0x18001b4d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4d6  nop
0x18001b4d7  mov     rcx, [rsp+0F8h+var_A8]
0x18001b4dc  test    rcx, rcx
0x18001b4df  jz      short loc_18001B4EE
0x18001b4e1  mov     rax, [rcx]
0x18001b4e4  mov     rax, [rax+10h]
0x18001b4e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4ed  nop
0x18001b4ee  mov     rcx, [rsp+0F8h+var_A0]
0x18001b4f3  test    rcx, rcx
0x18001b4f6  jz      short loc_18001B505
0x18001b4f8  mov     rax, [rcx]
0x18001b4fb  mov     rax, [rax+10h]
0x18001b4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b504  nop
0x18001b505  mov     eax, r14d
0x18001b508  mov     rcx, [rsp+0F8h+var_38]
0x18001b510  xor     rcx, rsp; StackCookie
0x18001b513  call    __security_check_cookie
0x18001b518  mov     rbx, [rsp+0F8h+arg_0]
0x18001b520  add     rsp, 0D0h
  ... truncated ...
```
