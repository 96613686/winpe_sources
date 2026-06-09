# CEventSystem2::Query(__MIDL___MIDL_itf_esstruct_0000_0000_0001,ushort const *,int,int *,IEnumUnknown * *)

- ea: `0x180012700`
- end: `0x180012b8f`
- name: `?Query@CEventSystem2@@UEAAJW4__MIDL___MIDL_itf_esstruct_0000_0000_0001@@PEBGHPEAHPEAPEAUIEnumUnknown@@@Z`
- size: `1167`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003c40`
- `0x180003d54`
- `0x180012700`
- `0x180012b98`
- `0x180012bcc`
- `0x18003ecb0`
- `0x180043496`
- `0x1800434c6`
- `0x180046010`

## import_xrefs

- `msvcrt!malloc` at `0x18001288a`
- `msvcrt!malloc` at `0x18001288a`
- `msvcrt!free` at `0x180012b3a`
- `msvcrt!free` at `0x18004421e`
- `msvcrt!free` at `0x180012b3a`
- `msvcrt!free` at `0x18004421e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800128fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800128fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012aeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800441d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012aeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800441d0`

## string_xrefs

- `0x18001286f`: `com\complus\src\events\tier2\eventsystem2.cpp`
- `0x180012a43`: `com\complus\src\events\tier2\eventsystem2.cpp`

## pseudocode

```c
__int64 __fastcall CEventSystem2::Query(
        __int64 a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        CEnumEventObject2 **a6)
{
  _QWORD *v6; // r15
  int v9; // r12d
  CEnumEventObject2 **v10; // rbx
  char *v11; // rsi
  __int64 v12; // r13
  CEnumEventObject2 *v13; // rax
  CEnumEventObject2 *v14; // rax
  size_t v15; // rdi
  char *v16; // rax
  __int64 v17; // r14
  char *v18; // rdi
  unsigned int v19; // edi
  __int64 v20; // rcx
  __int64 v22; // [rsp+0h] [rbp-B8h] BYREF
  int v23; // [rsp+30h] [rbp-88h]
  unsigned int v24; // [rsp+34h] [rbp-84h]
  __int64 v25; // [rsp+38h] [rbp-80h] BYREF
  __int64 *v26; // [rsp+40h] [rbp-78h]
  struct IEventObjectTable *v27; // [rsp+48h] [rbp-70h] BYREF
  _QWORD *v28; // [rsp+50h] [rbp-68h]
  int v29; // [rsp+58h] [rbp-60h]
  int v30; // [rsp+5Ch] [rbp-5Ch]
  int v31; // [rsp+60h] [rbp-58h]
  int v32; // [rsp+64h] [rbp-54h]
  int v33; // [rsp+68h] [rbp-50h]
  int v34; // [rsp+6Ch] [rbp-4Ch]
  int v35; // [rsp+70h] [rbp-48h]
  char *v36; // [rsp+78h] [rbp-40h]
  int v37; // [rsp+80h] [rbp-38h]
  unsigned int v38; // [rsp+C0h] [rbp+8h] BYREF

  v26 = &v22;
  v9 = 0;
  v23 = 0;
  v10 = a6;
  *a6 = 0;
  if ( *(_DWORD *)(a1 + 400) )
    return 2147549448LL;
  v27 = 0;
  v25 = 0;
  v11 = 0;
  v36 = 0;
  v12 = 24LL * a2;
  v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, struct IEventObjectTable **))(**(_QWORD **)(a1 + 24)
                                                                                               + 40LL))(
          *(_QWORD *)(a1 + 24),
          *(unsigned int *)((char *)&g_objectInfo + v12 + 8),
          *(unsigned int *)((char *)&g_objectInfo + v12 + 12),
          *(struct ObjectInfo near **)((char *)&g_objectInfo + v12 + 16),
          &v27);
  if ( v23 < 0 )
  {
    v29 = v23;
    local_unwind_0(v26, &loc_180012B71);
    goto LABEL_29;
  }
  v23 = (*(__int64 (__fastcall **)(struct IEventObjectTable *, __int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v27 + 40LL))(
          v27,
          a3,
          a4,
          a5,
          &v25);
  if ( v23 < 0 )
  {
LABEL_29:
    v30 = v23;
    local_unwind_0(v26, &loc_180012B77);
LABEL_30:
    v31 = v23;
    local_unwind_0(v26, &loc_180012B7D);
    goto LABEL_31;
  }
  v38 = 0;
  v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 24LL))(v25);
  if ( !v23 )
  {
    v23 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v25 + 32LL))(v25, &v38);
    if ( v23 < 0 )
      goto LABEL_30;
  }
  v28 = 0;
  LODWORD(a6) = 0;
  if ( v38 )
  {
    v15 = 8LL * v38;
    v16 = (char *)malloc(v15);
    v11 = v16;
    v36 = v16;
    if ( v16 )
    {
      memset_0(v16, 0, v15);
      v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, CEnumEventObject2 ***))(*(_QWORD *)v25 + 40LL))(
              v25,
              v38,
              v11,
              &a6);
      if ( v23 < 0 )
      {
LABEL_31:
        v32 = v23;
        local_unwind_0(v26, &loc_180012B83);
LABEL_32:
        v19 = 0;
        v24 = 0;
        while ( v19 < (unsigned int)a6 )
        {
          v20 = v6[v19];
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          v24 = ++v19;
        }
        CoTaskMemFree(v6);
        goto LABEL_7;
      }
      v6 = CoTaskMemAlloc(saturated_mul((unsigned int)a6, 8u));
      v28 = v6;
      if ( v6 )
      {
LABEL_14:
        memset_0(v6, 0, 8LL * (unsigned int)a6);
        v34 = 0;
        v17 = 0;
        while ( 1 )
        {
          v35 = v17;
          if ( (unsigned int)v17 >= (unsigned int)a6 )
            break;
          if ( accessAllowed(8, 0) )
          {
            v18 = &v11[8 * v17];
            v23 = (*(__int64 (__fastcall **)(struct IEventObjectTable *, _QWORD, GUID *, _QWORD *))((char *)&g_objectInfo
                                                                                                  + v12))(
                    v27,
                    *(_QWORD *)v18,
                    &IID_IUnknown,
                    &v6[v9]);
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 16LL))(*(_QWORD *)v18);
            if ( v23 < 0 )
            {
              v33 = v23;
              local_unwind_0(v26, &loc_180012B89);
              break;
            }
            v34 = ++v9;
            v17 = (unsigned int)(v17 + 1);
          }
          else
          {
            v17 = (unsigned int)(v17 + 1);
          }
        }
        LODWORD(a6) = v9;
        if ( v23 >= 0 )
          goto LABEL_7;
        goto LABEL_32;
      }
    }
    else
    {
      v37 = -2147024882;
      local_unwind_0(v26, &loc_180012B63);
    }
    InternalError(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x4D3u, 0xC0001204, 0x11u);
    goto LABEL_14;
  }
  v6 = 0;
  v28 = 0;
LABEL_7:
  v13 = (CEnumEventObject2 *)CoTaskMemAlloc(0x20u);
  if ( v13 )
    v14 = CEnumEventObject2::CEnumEventObject2(v13, (struct IUnknown **const)v6, (unsigned int)a6);
  else
    v14 = 0;
  *v10 = v14;
  if ( !v14 )
    InternalError(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x4FDu, 0xC0001204, 0x11u);
  (*(void (__fastcall **)(CEnumEventObject2 *))(*(_QWORD *)*v10 + 8LL))(*v10);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v27 )
    (*(void (__fastcall **)(struct IEventObjectTable *))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v11 )
    free(v11);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x180012700  mov     [rsp+arg_8], rbx
0x180012705  mov     [rsp+arg_10], rsi
0x18001270a  push    rdi
0x18001270b  push    r12
0x18001270d  push    r13
0x18001270f  push    r14
0x180012711  push    r15
0x180012713  sub     rsp, 90h
0x18001271a  mov     [rsp+0B8h+var_78], rsp
0x18001271f  mov     edi, r9d
0x180012722  mov     r14, r8
0x180012725  xor     r12d, r12d
0x180012728  mov     [rsp+0B8h+var_88], r12d
0x18001272d  mov     rbx, [rsp+0B8h+arg_28]
0x180012735  mov     [rbx], r12
0x180012738  cmp     [rcx+190h], r12d
0x18001273f  jnz     loc_180012B6A
0x180012745  mov     [rsp+0B8h+var_70], r12
0x18001274a  mov     [rsp+0B8h+var_80], r12
0x18001274f  mov     esi, r12d
0x180012752  mov     [rsp+0B8h+var_40], r12
0x180012757  mov     r10, [rcx+18h]
0x18001275b  movsxd  rax, edx
0x18001275e  lea     rcx, [rax+rax*2]
0x180012762  lea     r13, ds:0[rcx*8]
0x18001276a  mov     rax, [r10]
0x18001276d  lea     rdx, ?g_objectInfo@@3PAUObjectInfo@@A; ObjectInfo near * g_objectInfo
0x180012774  lea     rcx, [rsp+0B8h+var_70]
0x180012779  mov     [rsp+0B8h+var_98], rcx
0x18001277e  mov     r9, [rdx+r13+10h]
0x180012783  mov     r8d, [rdx+r13+0Ch]
0x180012788  mov     edx, [rdx+r13+8]
0x18001278d  mov     rcx, r10
0x180012790  mov     rax, [rax+28h]
0x180012794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012799  mov     [rsp+0B8h+var_88], eax
0x18001279d  mov     eax, [rsp+0B8h+var_88]
0x1800127a1  test    eax, eax
0x1800127a3  js      loc_180012A54
0x1800127a9  mov     rcx, [rsp+0B8h+var_70]
0x1800127ae  mov     rax, [rcx]
0x1800127b1  lea     rdx, [rsp+0B8h+var_80]
0x1800127b6  mov     [rsp+0B8h+var_98], rdx
0x1800127bb  mov     r9, [rsp+0B8h+arg_20]
0x1800127c3  mov     r8d, edi
0x1800127c6  mov     rdx, r14
0x1800127c9  mov     rax, [rax+28h]
0x1800127cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127d2  mov     [rsp+0B8h+var_88], eax
0x1800127d6  mov     eax, [rsp+0B8h+var_88]
0x1800127da  test    eax, eax
0x1800127dc  js      loc_180012A6D
0x1800127e2  mov     [rsp+0B8h+arg_0], r12d
0x1800127ea  mov     rcx, [rsp+0B8h+var_80]
0x1800127ef  mov     rax, [rcx]
0x1800127f2  mov     rax, [rax+18h]
0x1800127f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127fb  mov     [rsp+0B8h+var_88], eax
0x1800127ff  mov     eax, [rsp+0B8h+var_88]
0x180012803  test    eax, eax
0x180012805  jz      loc_1800129EB
0x18001280b  mov     [rsp+0B8h+var_68], r12
0x180012810  mov     dword ptr [rsp+0B8h+arg_28], r12d
0x180012818  mov     eax, [rsp+0B8h+arg_0]
0x18001281f  test    eax, eax
0x180012821  jnz     short loc_180012880
0x180012823  mov     r15, r12
0x180012826  mov     [rsp+0B8h+var_68], r12
0x18001282b  mov     ecx, 20h ; ' '; cb
0x180012830  call    cs:__imp_CoTaskMemAlloc
0x180012836  test    rax, rax
0x180012839  jz      loc_1800129E3
0x18001283f  mov     r8d, dword ptr [rsp+0B8h+arg_28]; unsigned int
0x180012847  mov     rdx, r15; struct IUnknown **
0x18001284a  mov     rcx, rax; this
0x18001284d  call    ??0CEnumEventObject2@@QEAA@QEAPEAUIUnknown@@K@Z; CEnumEventObject2::CEnumEventObject2(IUnknown * * const,ulong)
0x180012852  mov     [rbx], rax
0x180012855  test    rax, rax
0x180012858  jnz     loc_180012AF6
0x18001285e  mov     edx, 4FDh; unsigned int
0x180012863  mov     r9d, 11h; unsigned __int16
0x180012869  mov     r8d, 0C0001204h; unsigned int
0x18001286f  lea     rcx, aComComplusSrcE_18; "com\\complus\\src\\events\\tier2\\event"...
0x180012876  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001287b  jmp     loc_180012AF6
0x180012880  mov     rdi, rax
0x180012883  shl     rdi, 3
0x180012887  mov     rcx, rdi; Size
0x18001288a  call    cs:__imp_malloc
0x180012890  mov     rsi, rax
0x180012893  mov     [rsp+0B8h+var_40], rax
0x180012898  test    rax, rax
0x18001289b  jz      loc_180012A16
0x1800128a1  mov     r8, rdi; Size
0x1800128a4  xor     edx, edx; Val
0x1800128a6  mov     rcx, rax; void *
0x1800128a9  call    memset_0
0x1800128ae  mov     rcx, [rsp+0B8h+var_80]
0x1800128b3  mov     rax, [rcx]
0x1800128b6  lea     r9, [rsp+0B8h+arg_28]
0x1800128be  mov     r8, rsi
0x1800128c1  mov     edx, [rsp+0B8h+arg_0]
0x1800128c8  mov     rax, [rax+28h]
0x1800128cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128d1  mov     [rsp+0B8h+var_88], eax
0x1800128d5  mov     eax, [rsp+0B8h+var_88]
0x1800128d9  test    eax, eax
0x1800128db  js      loc_180012A9F
0x1800128e1  mov     ecx, dword ptr [rsp+0B8h+arg_28]
0x1800128e8  mov     eax, 8
0x1800128ed  mul     rcx
0x1800128f0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800128f7  cmovb   rax, rcx
0x1800128fb  mov     rcx, rax; cb
0x1800128fe  call    cs:__imp_CoTaskMemAlloc
0x180012904  mov     r15, rax
0x180012907  mov     [rsp+0B8h+var_68], rax
0x18001290c  test    rax, rax
0x18001290f  jz      loc_180012A32
0x180012915  mov     r8d, dword ptr [rsp+0B8h+arg_28]
0x18001291d  shl     r8, 3; Size
0x180012921  xor     edx, edx; Val
0x180012923  mov     rcx, r15; void *
0x180012926  call    memset_0
0x18001292b  nop
0x18001292c  mov     [rsp+0B8h+var_4C], r12d
0x180012931  xor     r14d, r14d
0x180012934  mov     [rsp+0B8h+var_48], r14d
0x180012939  cmp     r14d, dword ptr [rsp+0B8h+arg_28]
0x180012941  jnb     loc_1800129C7
0x180012947  xor     edx, edx; unsigned __int16 *
0x180012949  mov     ecx, 8; unsigned int
0x18001294e  call    ?accessAllowed@@YA_NKPEBG@Z; accessAllowed(ulong,ushort const *)
0x180012953  test    al, al
0x180012955  jz      short loc_1800129A9
0x180012957  lea     rdi, [rsi+r14*8]
0x18001295b  mov     eax, r12d
0x18001295e  lea     r9, [r15+rax*8]; void **
0x180012962  lea     r8, IID_IUnknown; struct _GUID *
0x180012969  mov     rdx, [rdi]; struct IEventObjectRow *
0x18001296c  mov     rcx, [rsp+0B8h+var_70]; struct IEventObjectTable *
0x180012971  lea     rax, ?g_objectInfo@@3PAUObjectInfo@@A; ObjectInfo near * g_objectInfo
0x180012978  mov     rax, (?g_objectInfo@@3PAUObjectInfo@@A - 180063600h)[rax+r13]; ObjectInfo near * g_objectInfo
0x18001297c  call    _guard_dispatch_icall$thunk$10345483385596137414; CEventClass2::Create(IEventObjectTable *,IEventObjectRow *,_GUID const &,void * *) ...
0x180012981  mov     [rsp+0B8h+var_88], eax
0x180012985  mov     rcx, [rdi]
0x180012988  mov     rax, [rcx]
0x18001298b  mov     rax, [rax+10h]
0x18001298f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012994  mov     eax, [rsp+0B8h+var_88]
0x180012998  test    eax, eax
0x18001299a  js      short loc_1800129AE
0x18001299c  inc     r12d
0x18001299f  mov     [rsp+0B8h+var_4C], r12d
0x1800129a4  inc     r14d
0x1800129a7  jmp     short loc_180012934
0x1800129a9  inc     r14d
0x1800129ac  jmp     short loc_180012934
0x1800129ae  mov     eax, [rsp+0B8h+var_88]
0x1800129b2  mov     [rsp+0B8h+var_50], eax
0x1800129b6  lea     rdx, loc_180012B89
0x1800129bd  mov     rcx, [rsp+0B8h+var_78]
0x1800129c2  call    _local_unwind_0
0x1800129c7  mov     dword ptr [rsp+0B8h+arg_28], r12d
0x1800129cf  mov     eax, [rsp+0B8h+var_88]
0x1800129d3  xor     r12d, r12d
0x1800129d6  test    eax, eax
0x1800129d8  jns     loc_18001282B
0x1800129de  jmp     loc_180012AB8
0x1800129e3  mov     rax, r12
0x1800129e6  jmp     loc_180012852
0x1800129eb  mov     rcx, [rsp+0B8h+var_80]
0x1800129f0  mov     rax, [rcx]
0x1800129f3  lea     rdx, [rsp+0B8h+arg_0]
0x1800129fb  mov     rax, [rax+20h]
0x1800129ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a04  mov     [rsp+0B8h+var_88], eax
0x180012a08  mov     eax, [rsp+0B8h+var_88]
0x180012a0c  test    eax, eax
0x180012a0e  jns     loc_18001280B
0x180012a14  jmp     short loc_180012A86
0x180012a16  mov     [rsp+0B8h+var_38], 8007000Eh
0x180012a21  lea     rdx, loc_180012B63
0x180012a28  mov     rcx, [rsp+0B8h+var_78]
0x180012a2d  call    _local_unwind_0
0x180012a32  mov     edx, 4D3h; unsigned int
0x180012a37  mov     r9d, 11h; unsigned __int16
0x180012a3d  mov     r8d, 0C0001204h; unsigned int
0x180012a43  lea     rcx, aComComplusSrcE_18; "com\\complus\\src\\events\\tier2\\event"...
0x180012a4a  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180012a4f  jmp     loc_180012915
0x180012a54  mov     eax, [rsp+0B8h+var_88]
0x180012a58  mov     [rsp+0B8h+var_60], eax
0x180012a5c  lea     rdx, loc_180012B71
0x180012a63  mov     rcx, [rsp+0B8h+var_78]
0x180012a68  call    _local_unwind_0
0x180012a6d  mov     eax, [rsp+0B8h+var_88]
0x180012a71  mov     [rsp+0B8h+var_5C], eax
0x180012a75  lea     rdx, loc_180012B77
0x180012a7c  mov     rcx, [rsp+0B8h+var_78]
0x180012a81  call    _local_unwind_0
0x180012a86  mov     eax, [rsp+0B8h+var_88]
0x180012a8a  mov     [rsp+0B8h+var_58], eax
0x180012a8e  lea     rdx, loc_180012B7D
0x180012a95  mov     rcx, [rsp+0B8h+var_78]
0x180012a9a  call    _local_unwind_0
0x180012a9f  mov     eax, [rsp+0B8h+var_88]
0x180012aa3  mov     [rsp+0B8h+var_54], eax
0x180012aa7  lea     rdx, loc_180012B83
0x180012aae  mov     rcx, [rsp+0B8h+var_78]
0x180012ab3  call    _local_unwind_0
0x180012ab8  mov     edi, r12d
0x180012abb  mov     [rsp+0B8h+var_84], r12d
0x180012ac0  cmp     edi, dword ptr [rsp+0B8h+arg_28]
0x180012ac7  jnb     short loc_180012AE8
0x180012ac9  mov     eax, edi
0x180012acb  mov     rcx, [r15+rax*8]
0x180012acf  test    rcx, rcx
0x180012ad2  jz      short loc_180012AE0
0x180012ad4  mov     rax, [rcx]
0x180012ad7  mov     rax, [rax+10h]
0x180012adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ae0  inc     edi
0x180012ae2  mov     [rsp+0B8h+var_84], edi
0x180012ae6  jmp     short loc_180012AC0
0x180012ae8  mov     rcx, r15; pv
0x180012aeb  call    cs:__imp_CoTaskMemFree
0x180012af1  jmp     loc_18001282B
0x180012af6  mov     rcx, [rbx]
0x180012af9  mov     rax, [rcx]
0x180012afc  mov     rax, [rax+8]
0x180012b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b05  nop
0x180012b06  mov     rcx, [rsp+0B8h+var_80]
0x180012b0b  test    rcx, rcx
0x180012b0e  jz      short loc_180012B1C
0x180012b10  mov     rax, [rcx]
0x180012b13  mov     rax, [rax+10h]
0x180012b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b1c  mov     rcx, [rsp+0B8h+var_70]
0x180012b21  test    rcx, rcx
0x180012b24  jz      short loc_180012B32
0x180012b26  mov     rax, [rcx]
0x180012b29  mov     rax, [rax+10h]
0x180012b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b32  test    rsi, rsi
0x180012b35  jz      short loc_180012B40
0x180012b37  mov     rcx, rsi; Block
0x180012b3a  call    cs:__imp_free
0x180012b40  jmp     short $+2
0x180012b42  mov     eax, [rsp+0B8h+var_88]
0x180012b46  lea     r11, [rsp+0B8h+var_28]
0x180012b4e  mov     rbx, [r11+38h]
0x180012b52  mov     rsi, [r11+40h]
0x180012b56  mov     rsp, r11
0x180012b59  pop     r15
0x180012b5b  pop     r14
0x180012b5d  pop     r13
0x180012b5f  pop     r12
0x180012b61  pop     rdi
0x180012b62  retn
0x180012b63  mov     eax, 8007000Eh
0x180012b68  jmp     short loc_180012B46
0x180012b6a  mov     eax, 80010108h
0x180012b6f  jmp     short loc_180012B46
0x180012b71  mov     eax, [rsp+0B8h+var_60]
0x180012b75  jmp     short loc_180012B46
0x180012b77  mov     eax, [rsp+0B8h+var_5C]
0x180012b7b  jmp     short loc_180012B46
0x180012b7d  mov     eax, [rsp+0B8h+var_58]
0x180012b81  jmp     short loc_180012B46
0x180012b83  mov     eax, [rsp+0B8h+var_54]
0x180012b87  jmp     short loc_180012B46
0x180012b89  mov     eax, [rsp+0B8h+var_50]
0x180012b8d  jmp     short loc_180012B46
0x180044180  push    rbx
0x180044182  push    rbp
0x180044183  push    rdi
0x180044184  sub     rsp, 30h
0x180044188  mov     rbp, rdx
0x18004418b  mov     eax, [rbp+30h]
0x18004418e  test    eax, eax
0x180044190  jns     short loc_1800441D7
0x180044192  xor     ebx, ebx
0x180044194  mov     [rbp+34h], ebx
0x180044197  mov     ecx, [rbp+0E8h]
0x18004419d  mov     rdi, [rbp+50h]
0x1800441a1  test    ecx, ecx
0x1800441a3  jz      short loc_1800441CD
0x1800441a5  mov     eax, ebx
0x1800441a7  cmp     qword ptr [rdi+rbx*8], 0
0x1800441ac  jz      short loc_1800441C4
0x1800441ae  mov     rcx, [rdi+rbx*8]
0x1800441b2  mov     rax, [rcx]
0x1800441b5  mov     rax, [rax+10h]
0x1800441b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441be  mov     ecx, [rbp+0E8h]
0x1800441c4  inc     ebx
0x1800441c6  mov     [rbp+34h], ebx
0x1800441c9  cmp     ebx, ecx
  ... truncated ...
```
