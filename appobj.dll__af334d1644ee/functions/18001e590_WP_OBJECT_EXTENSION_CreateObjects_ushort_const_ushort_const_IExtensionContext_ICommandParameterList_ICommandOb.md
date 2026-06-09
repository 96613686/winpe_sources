# WP_OBJECT_EXTENSION::CreateObjects(ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x18001e590`
- end: `0x18001ea3c`
- name: `?CreateObjects@WP_OBJECT_EXTENSION@@UEAAJPEBG0PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `1196`
- prototype: `__int64 __fastcall(__int64 **this, unsigned __int16 *, const unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180005440`
- `0x18001e418`
- `0x18001e590`
- `0x18001ebd0`
- `0x18002b564`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!wcstoul` at `0x18001e817`
- `msvcrt!wcstoul` at `0x18001e817`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e9a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e9a9`

## pseudocode

```c
__int64 __fastcall WP_OBJECT_EXTENSION::CreateObjects(
        __int64 **this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IExtensionContext *a4,
        struct ICommandParameterList *a5,
        struct ICommandObjectList *a6)
{
  COMMAND_OBJECT *v9; // rsi
  int v11; // edi
  APP_OBJECT_UTILS *v12; // rcx
  int v13; // r12d
  __int64 *v14; // rcx
  __int64 v15; // r9
  int v16; // eax
  unsigned int v17; // eax
  __int64 *v18; // rcx
  unsigned int v19; // r13d
  __int64 v20; // r9
  __int64 v21; // rax
  unsigned int v22; // r14d
  __int64 v23; // rbx
  unsigned int v25; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  int v27; // [rsp+50h] [rbp-B0h] BYREF
  struct ICommandParameterList *v28; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int16 *v31; // [rsp+68h] [rbp-98h] BYREF
  struct ICommandObjectList *v32; // [rsp+70h] [rbp-90h]
  __int128 v33; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v34[32]; // [rsp+88h] [rbp-78h] BYREF
  __int16 *v35; // [rsp+A8h] [rbp-58h]
  int v36; // [rsp+B0h] [rbp-50h]
  __int16 v37; // [rsp+B4h] [rbp-4Ch]
  int v38; // [rsp+B8h] [rbp-48h]
  _BYTE v39[32]; // [rsp+C0h] [rbp-40h] BYREF
  const unsigned __int16 *v40; // [rsp+E0h] [rbp-20h]
  int v41; // [rsp+E8h] [rbp-18h]
  __int16 v42; // [rsp+ECh] [rbp-14h]
  int v43; // [rsp+F0h] [rbp-10h]
  __int16 v44; // [rsp+100h] [rbp+0h] BYREF
  char v45[510]; // [rsp+102h] [rbp+2h] BYREF
  __int16 v46; // [rsp+300h] [rbp+200h] BYREF
  char v47[510]; // [rsp+302h] [rbp+202h] BYREF

  v32 = a6;
  v31 = 0;
  pv = 0;
  v25 = 0;
  v27 = 0;
  v30 = 0;
  v9 = 0;
  v33 = 0;
  memset_0(v45, 0, sizeof(v45));
  v41 = 512;
  v40 = (const unsigned __int16 *)&v44;
  v42 = 256;
  v43 = 0;
  v44 = 0;
  memset_0(v47, 0, sizeof(v47));
  v36 = 512;
  v37 = 256;
  v35 = &v46;
  v38 = 0;
  v46 = 0;
  v28 = 0;
  if ( !a2 || (a2 = 0, !a3) || !a4 || !a5 || !a6 )
  {
    v11 = -2147024809;
    goto LABEL_42;
  }
  if ( (int)WP_OBJECT_EXTENSION::InitializeRSCA((WP_OBJECT_EXTENSION *)this) < 0 || !this[6] )
  {
    v11 = -2147024846;
    (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, _DWORD))(*(_QWORD *)a4 + 144LL))(
      a4,
      2147942450LL,
      3221226496LL,
      &v33,
      0);
    goto LABEL_42;
  }
  v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a5 + 80LL))(
          a5,
          &v28);
  if ( v11 < 0 )
    goto LABEL_42;
  if ( !*a3 )
  {
    v11 = APP_OBJECT_UTILS::PopParameter(v12, a4, v28, L"WP.NAME", (struct STRU *)v39, 0, 1);
    if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147023483 )
      goto LABEL_42;
    a3 = v40;
    if ( !*v40 )
    {
      v11 = APP_OBJECT_UTILS::PopParameter(v12, a4, v28, L"APPPOOL.NAME", (struct STRU *)v34, 0, 1);
      if ( ((v11 + 0x80000000) & 0x80000000) != 0 || v11 == -2147023483 )
      {
        v13 = 0;
        v14 = this[6];
        v29 = 0;
        v15 = *v14;
        if ( v38 )
        {
          if ( (*(int (__fastcall **)(__int64 *, __int16 *, unsigned __int16 **))(v15 + 32))(v14, v35, &v31) < 0 )
          {
            v11 = 0;
            goto LABEL_42;
          }
          v16 = (*(__int64 (__fastcall **)(unsigned __int16 *, unsigned int *, LPVOID *))(*(_QWORD *)v31 + 72LL))(
                  v31,
                  &v25,
                  &pv);
        }
        else
        {
          v16 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, LPVOID *))(v15 + 56))(v14, &v25, &pv);
        }
        v11 = v16;
        if ( v16 >= 0 )
          goto LABEL_26;
      }
LABEL_42:
      if ( pv != a2 )
      {
        v22 = (unsigned int)a2;
        if ( v25 > (unsigned int)a2 )
        {
          do
          {
            v23 = v22;
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)pv + v22) + 16LL))(*((_QWORD *)pv + v22));
            ++v22;
            *((_QWORD *)pv + v23) = 0;
          }
          while ( v22 < v25 );
          a2 = 0;
        }
        CoTaskMemFree(pv);
        pv = a2;
      }
      if ( v9 )
        (*(void (__fastcall **)(COMMAND_OBJECT *))(*(_QWORD *)v9 + 16LL))(v9);
      goto LABEL_49;
    }
  }
  v11 = APP_OBJECT_UTILS::ValidateEmptyParameters(v12, a4, v28);
  if ( v11 < 0 )
    goto LABEL_42;
  v17 = wcstoul(a3, 0, 10);
  v18 = this[6];
  v29 = v17;
  v11 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, LPVOID *))(*v18 + 56))(v18, &v25, &pv);
  if ( v11 < 0 )
    goto LABEL_42;
  v13 = 1;
LABEL_26:
  if ( pv )
  {
    v19 = v29;
    while ( 1 )
    {
      v9 = 0;
      if ( (unsigned int)a2 >= v25 )
      {
LABEL_37:
        a2 = 0;
        goto LABEL_42;
      }
      if ( !v13 )
        goto LABEL_32;
      v11 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)pv + (unsigned int)a2) + 24LL))(
              *((_QWORD *)pv + (unsigned int)a2),
              &v30);
      if ( v11 < 0 )
        goto LABEL_40;
      if ( v30 == v19 )
      {
LABEL_32:
        v9 = (COMMAND_OBJECT *)operator new(0xE0u);
        if ( !v9 )
        {
          v11 = -2147024888;
LABEL_40:
          a2 = 0;
          v9 = 0;
          goto LABEL_42;
        }
        COMMAND_OBJECT::COMMAND_OBJECT(v9);
        *((_QWORD *)v9 + 27) = v20;
        *(_QWORD *)v9 = &WP_OBJECT::`vftable';
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
        v11 = WP_OBJECT::Create(v9);
        if ( v11 < 0 )
          goto LABEL_37;
        v21 = *(_QWORD *)a4;
        v27 = 0;
        v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, COMMAND_OBJECT *, struct ICommandParameterList *, int *))(v21 + 152))(
                a4,
                v9,
                v28,
                &v27);
        if ( v11 < 0 )
          goto LABEL_37;
        if ( v27 )
        {
          v11 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, COMMAND_OBJECT *))(*(_QWORD *)v32 + 24LL))(
                  v32,
                  v9);
          if ( v11 < 0 )
            goto LABEL_37;
        }
      }
      LODWORD(a2) = (_DWORD)a2 + 1;
    }
  }
LABEL_49:
  if ( v31 )
  {
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = a2;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = (struct ICommandParameterList *)a2;
  }
  BUFFER::~BUFFER((BUFFER *)v34);
  BUFFER::~BUFFER((BUFFER *)v39);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001e590  mov     [rsp-8+arg_8], rbx
0x18001e595  push    rbp
0x18001e596  push    rsi
0x18001e597  push    rdi
0x18001e598  push    r12
0x18001e59a  push    r13
0x18001e59c  push    r14
0x18001e59e  push    r15
0x18001e5a0  lea     rbp, [rsp-410h]
0x18001e5a8  sub     rsp, 510h
0x18001e5af  mov     rax, cs:__security_cookie
0x18001e5b6  xor     rax, rsp
0x18001e5b9  mov     [rbp+440h+var_40], rax
0x18001e5c0  mov     r12, [rbp+440h+arg_28]
0x18001e5c7  xor     eax, eax
0x18001e5c9  mov     rdi, [rbp+440h+arg_20]
0x18001e5d0  mov     r15, r8
0x18001e5d3  mov     rbx, rdx
0x18001e5d6  mov     [rsp+540h+var_4D0], r12
0x18001e5db  mov     r13, rcx
0x18001e5de  mov     [rsp+540h+var_4D8], rax
0x18001e5e3  xorps   xmm0, xmm0
0x18001e5e6  mov     [rsp+540h+pv], rax
0x18001e5eb  xor     edx, edx; Val
0x18001e5ed  mov     [rsp+540h+var_500], eax
0x18001e5f1  mov     r8d, 1FEh; Size
0x18001e5f7  mov     [rsp+540h+var_4F0], eax
0x18001e5fb  lea     rcx, [rbp+440h+var_43E]; void *
0x18001e5ff  mov     [rsp+540h+var_4DC], eax
0x18001e603  mov     esi, eax
0x18001e605  mov     r14, r9
0x18001e608  movups  [rsp+540h+var_4C8], xmm0
0x18001e60d  call    memset_0
0x18001e612  lea     rax, [rbp+440h+var_440]
0x18001e616  mov     [rbp+440h+var_458], 200h
0x18001e61d  mov     [rbp+440h+var_460], rax
0x18001e621  lea     rcx, [rbp+440h+var_23E]; void *
0x18001e628  xor     eax, eax
0x18001e62a  mov     [rbp+440h+var_454], 100h
0x18001e630  xor     edx, edx; Val
0x18001e632  mov     [rbp+440h+var_450], eax
0x18001e635  mov     r8d, 1FEh; Size
0x18001e63b  mov     [rbp+440h+var_440], ax
0x18001e63f  call    memset_0
0x18001e644  xor     ecx, ecx
0x18001e646  mov     [rbp+440h+var_490], 200h
0x18001e64d  mov     [rbp+440h+var_48C], 100h
0x18001e653  lea     rax, [rbp+440h+var_240]
0x18001e65a  mov     [rbp+440h+var_498], rax
0x18001e65e  mov     [rbp+440h+var_488], ecx
0x18001e661  mov     [rbp+440h+var_240], cx
0x18001e668  mov     [rsp+540h+var_4E8], rcx
0x18001e66d  test    rbx, rbx
0x18001e670  jz      loc_18001E95E
0x18001e676  xor     ebx, ebx
0x18001e678  test    r15, r15
0x18001e67b  jz      loc_18001E95E
0x18001e681  test    r14, r14
0x18001e684  jz      loc_18001E95E
0x18001e68a  test    rdi, rdi
0x18001e68d  jz      loc_18001E95E
0x18001e693  test    r12, r12
0x18001e696  jz      loc_18001E95E
0x18001e69c  mov     rcx, r13; this
0x18001e69f  call    ?InitializeRSCA@WP_OBJECT_EXTENSION@@AEAAJXZ; WP_OBJECT_EXTENSION::InitializeRSCA(void)
0x18001e6a4  test    eax, eax
0x18001e6a6  jns     short loc_18001E6D5
0x18001e6a8  mov     rax, [r14]
0x18001e6ab  lea     r9, [rsp+540h+var_4C8]
0x18001e6b0  mov     edx, 80070032h
0x18001e6b5  mov     dword ptr [rsp+540h+var_520], ebx
0x18001e6b9  mov     r8d, 0C0000400h
0x18001e6bf  mov     rcx, r14
0x18001e6c2  mov     edi, edx
0x18001e6c4  mov     rax, [rax+90h]
0x18001e6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6d0  jmp     loc_18001E963
0x18001e6d5  cmp     [r13+30h], rbx
0x18001e6d9  jz      short loc_18001E6A8
0x18001e6db  mov     rax, [rdi]
0x18001e6de  lea     rdx, [rsp+540h+var_4E8]
0x18001e6e3  mov     rcx, rdi
0x18001e6e6  mov     rax, [rax+50h]
0x18001e6ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6ef  mov     edi, eax
0x18001e6f1  test    eax, eax
0x18001e6f3  js      loc_18001E963
0x18001e6f9  cmp     [r15], bx
0x18001e6fd  jnz     loc_18001E7F7
0x18001e703  mov     r8, [rsp+540h+var_4E8]; struct ICommandParameterList *
0x18001e708  lea     rax, [rbp+440h+var_480]
0x18001e70c  mov     [rsp+540h+var_510], 1; int
0x18001e714  lea     r9, aWpName_0; "WP.NAME"
0x18001e71b  mov     [rsp+540h+var_518], ebx; int
0x18001e71f  mov     rdx, r14; struct IExtensionContext *
0x18001e722  mov     [rsp+540h+var_520], rax; struct STRU *
0x18001e727  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001e72c  mov     r12d, 80000000h
0x18001e732  mov     edi, eax
0x18001e734  add     eax, r12d
0x18001e737  test    r12d, eax
0x18001e73a  jnz     short loc_18001E748
0x18001e73c  cmp     edi, 80070585h
0x18001e742  jnz     loc_18001E963
0x18001e748  mov     r15, [rbp+440h+var_460]
0x18001e74c  cmp     [r15], bx
0x18001e750  jnz     loc_18001E7F7
0x18001e756  mov     r8, [rsp+540h+var_4E8]; struct ICommandParameterList *
0x18001e75b  lea     rax, [rbp+440h+var_4B8]
0x18001e75f  mov     [rsp+540h+var_510], 1; int
0x18001e767  lea     r9, aApppoolName; "APPPOOL.NAME"
0x18001e76e  mov     [rsp+540h+var_518], ebx; int
0x18001e772  mov     rdx, r14; struct IExtensionContext *
0x18001e775  mov     [rsp+540h+var_520], rax; struct STRU *
0x18001e77a  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001e77f  mov     edi, eax
0x18001e781  add     eax, r12d
0x18001e784  test    r12d, eax
0x18001e787  jnz     short loc_18001E795
0x18001e789  cmp     edi, 80070585h
0x18001e78f  jnz     loc_18001E963
0x18001e795  cmp     [rbp+440h+var_488], ebx
0x18001e798  mov     r12d, ebx
0x18001e79b  mov     rcx, [r13+30h]
0x18001e79f  setz    al
0x18001e7a2  mov     [rsp+540h+var_4E0], ebx
0x18001e7a6  mov     r9, [rcx]
0x18001e7a9  test    al, al
0x18001e7ab  jnz     short loc_18001E7F1
0x18001e7ad  mov     rdx, [rbp+440h+var_498]
0x18001e7b1  lea     r8, [rsp+540h+var_4D8]
0x18001e7b6  mov     rax, [r9+20h]
0x18001e7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7bf  test    eax, eax
0x18001e7c1  jns     short loc_18001E7CA
0x18001e7c3  mov     edi, ebx
0x18001e7c5  jmp     loc_18001E963
0x18001e7ca  mov     rcx, [rsp+540h+var_4D8]
0x18001e7cf  mov     rax, [rcx]
0x18001e7d2  mov     rax, [rax+48h]
0x18001e7d6  lea     rdx, [rsp+540h+var_500]
0x18001e7db  lea     r8, [rsp+540h+pv]
0x18001e7e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7e5  mov     edi, eax
0x18001e7e7  test    eax, eax
0x18001e7e9  js      loc_18001E963
0x18001e7ef  jmp     short loc_18001E84B
0x18001e7f1  mov     rax, [r9+38h]
0x18001e7f5  jmp     short loc_18001E7D6
0x18001e7f7  mov     r8, [rsp+540h+var_4E8]; struct ICommandParameterList *
0x18001e7fc  mov     rdx, r14; struct IExtensionContext *
0x18001e7ff  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x18001e804  mov     edi, eax
0x18001e806  test    eax, eax
0x18001e808  js      loc_18001E963
0x18001e80e  xor     edx, edx; EndPtr
0x18001e810  mov     rcx, r15; String
0x18001e813  lea     r8d, [rdx+0Ah]; Radix
0x18001e817  call    cs:__imp_wcstoul
0x18001e81d  mov     rcx, [r13+30h]
0x18001e821  lea     r8, [rsp+540h+pv]
0x18001e826  mov     [rsp+540h+var_4E0], eax
0x18001e82a  mov     rdx, [rcx]
0x18001e82d  mov     rax, [rdx+38h]
0x18001e831  lea     rdx, [rsp+540h+var_500]
0x18001e836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e83b  mov     edi, eax
0x18001e83d  test    eax, eax
0x18001e83f  js      loc_18001E963
0x18001e845  mov     r12d, 1
0x18001e84b  cmp     [rsp+540h+pv], rbx
0x18001e850  jz      loc_18001E9C8
0x18001e856  mov     r13d, [rsp+540h+var_4E0]
0x18001e85b  xor     r15d, r15d
0x18001e85e  mov     rsi, r15
0x18001e861  cmp     ebx, [rsp+540h+var_500]
0x18001e865  jnb     loc_18001E945
0x18001e86b  mov     r15d, ebx
0x18001e86e  test    r12d, r12d
0x18001e871  jz      short loc_18001E8A2
0x18001e873  mov     rax, [rsp+540h+pv]
0x18001e878  lea     rdx, [rsp+540h+var_4DC]
0x18001e87d  mov     rcx, [rax+r15*8]
0x18001e881  mov     rax, [rcx]
0x18001e884  mov     rax, [rax+18h]
0x18001e888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e88d  mov     edi, eax
0x18001e88f  test    eax, eax
0x18001e891  js      loc_18001E958
0x18001e897  cmp     [rsp+540h+var_4DC], r13d
0x18001e89c  jnz     loc_18001E949
0x18001e8a2  mov     ecx, 0E0h; Size
0x18001e8a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e8ac  mov     rsi, rax
0x18001e8af  test    rax, rax
0x18001e8b2  jz      loc_18001E953
0x18001e8b8  mov     rax, [rsp+540h+pv]
0x18001e8bd  mov     rcx, rsi; this
0x18001e8c0  mov     r9, [rax+r15*8]
0x18001e8c4  call    ??0COMMAND_OBJECT@@QEAA@XZ; COMMAND_OBJECT::COMMAND_OBJECT(void)
0x18001e8c9  lea     rcx, ??_7WP_OBJECT@@6B@; const WP_OBJECT::`vftable'
0x18001e8d0  mov     [rsi+0D8h], r9
0x18001e8d7  mov     [rsi], rcx
0x18001e8da  mov     rcx, r9
0x18001e8dd  mov     rax, [r9]
0x18001e8e0  mov     rax, [rax+8]
0x18001e8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8e9  mov     rcx, rsi; this
0x18001e8ec  call    ?Create@WP_OBJECT@@QEAAJXZ; WP_OBJECT::Create(void)
0x18001e8f1  xor     r15d, r15d
0x18001e8f4  mov     edi, eax
0x18001e8f6  test    eax, eax
0x18001e8f8  js      short loc_18001E945
0x18001e8fa  mov     rax, [r14]
0x18001e8fd  lea     r9, [rsp+540h+var_4F0]
0x18001e902  mov     r8, [rsp+540h+var_4E8]
0x18001e907  mov     rdx, rsi
0x18001e90a  mov     rcx, r14
0x18001e90d  mov     [rsp+540h+var_4F0], r15d
0x18001e912  mov     rax, [rax+98h]
0x18001e919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e91e  mov     edi, eax
0x18001e920  test    eax, eax
0x18001e922  js      short loc_18001E945
0x18001e924  cmp     [rsp+540h+var_4F0], r15d
0x18001e929  jz      short loc_18001E94C
0x18001e92b  mov     rcx, [rsp+540h+var_4D0]
0x18001e930  mov     rdx, rsi
0x18001e933  mov     rax, [rcx]
0x18001e936  mov     rax, [rax+18h]
0x18001e93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e93f  mov     edi, eax
0x18001e941  test    eax, eax
0x18001e943  jns     short loc_18001E94C
0x18001e945  xor     ebx, ebx
0x18001e947  jmp     short loc_18001E963
0x18001e949  xor     r15d, r15d
0x18001e94c  inc     ebx
0x18001e94e  jmp     loc_18001E85E
0x18001e953  mov     edi, 80070008h
0x18001e958  xor     ebx, ebx
0x18001e95a  mov     esi, ebx
0x18001e95c  jmp     short loc_18001E963
0x18001e95e  mov     edi, 80070057h
0x18001e963  cmp     [rsp+540h+pv], rbx
0x18001e968  jz      short loc_18001E9B4
0x18001e96a  mov     r14d, ebx
0x18001e96d  cmp     [rsp+540h+var_500], ebx
0x18001e971  jbe     short loc_18001E9A4
0x18001e973  mov     rax, [rsp+540h+pv]
0x18001e978  mov     ebx, r14d
0x18001e97b  mov     rcx, [rax+rbx*8]
0x18001e97f  mov     rax, [rcx]
0x18001e982  mov     rax, [rax+10h]
0x18001e986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e98b  mov     rax, [rsp+540h+pv]
0x18001e990  inc     r14d
0x18001e993  mov     qword ptr [rax+rbx*8], 0
0x18001e99b  cmp     r14d, [rsp+540h+var_500]
0x18001e9a0  jb      short loc_18001E973
0x18001e9a2  xor     ebx, ebx
0x18001e9a4  mov     rcx, [rsp+540h+pv]; pv
0x18001e9a9  call    cs:__imp_CoTaskMemFree
0x18001e9af  mov     [rsp+540h+pv], rbx
0x18001e9b4  test    rsi, rsi
0x18001e9b7  jz      short loc_18001E9C8
0x18001e9b9  mov     rax, [rsi]
0x18001e9bc  mov     rcx, rsi
0x18001e9bf  mov     rax, [rax+10h]
0x18001e9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9c8  mov     rcx, [rsp+540h+var_4D8]
0x18001e9cd  test    rcx, rcx
0x18001e9d0  jz      short loc_18001E9E3
0x18001e9d2  mov     rax, [rcx]
0x18001e9d5  mov     rax, [rax+10h]
0x18001e9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9de  mov     [rsp+540h+var_4D8], rbx
0x18001e9e3  mov     rcx, [rsp+540h+var_4E8]
0x18001e9e8  test    rcx, rcx
0x18001e9eb  jz      short loc_18001E9FE
0x18001e9ed  mov     rax, [rcx]
0x18001e9f0  mov     rax, [rax+10h]
0x18001e9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9f9  mov     [rsp+540h+var_4E8], rbx
0x18001e9fe  lea     rcx, [rbp+440h+var_4B8]; this
0x18001ea02  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001ea07  lea     rcx, [rbp+440h+var_480]; this
0x18001ea0b  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001ea10  mov     eax, edi
0x18001ea12  mov     rcx, [rbp+440h+var_40]
0x18001ea19  xor     rcx, rsp; StackCookie
0x18001ea1c  call    __security_check_cookie
0x18001ea21  mov     rbx, [rsp+540h+arg_8]
0x18001ea29  add     rsp, 510h
0x18001ea30  pop     r15
0x18001ea32  pop     r14
0x18001ea34  pop     r13
0x18001ea36  pop     r12
0x18001ea38  pop     rdi
0x18001ea39  pop     rsi
  ... truncated ...
```
