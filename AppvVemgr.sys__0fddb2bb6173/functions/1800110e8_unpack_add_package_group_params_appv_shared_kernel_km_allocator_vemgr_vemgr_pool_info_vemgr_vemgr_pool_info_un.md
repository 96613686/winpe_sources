# unpack_add_package_group_params<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::unpack<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(uchar const *,ulong,kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x1800110e8`
- end: `0x18001152f`
- name: `??$unpack@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$unpack_add_package_group_params@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEBEKAEAV?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `1095`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180012924`

## callees

- `0x18000129c`
- `0x18000a9e4`
- `0x18000d37c`
- `0x1800110e8`
- `0x1800134a8`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180011116`
- `ntoskrnl!ExAllocatePool2` at `0x180011116`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011235`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011373`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800113ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011403`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001142e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011490`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011235`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011373`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800113ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011403`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001142e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180011490`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800111a3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800112d4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800111a3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800112d4`

## pseudocode

```c
__int64 __fastcall unpack_add_package_group_params<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::unpack<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3)
{
  _QWORD *v4; // r15
  _QWORD *Pool2; // rax
  int v7; // r12d
  _QWORD *v8; // rdx
  _QWORD *v9; // rax
  __int64 v10; // r14
  volatile signed __int32 *v11; // rbx
  unsigned __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // esi
  PVOID v16; // rdx
  unsigned int v18; // esi
  unsigned int *v19; // r15
  unsigned __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rdx
  unsigned int v23; // r14d
  __int64 v24; // r8
  PVOID v25; // rdx
  int v26; // eax
  PVOID v27; // rcx
  PVOID v28; // rcx
  volatile signed __int32 *v29; // rsi
  __int64 v30; // [rsp+20h] [rbp-58h] BYREF
  volatile signed __int32 *v31; // [rsp+28h] [rbp-50h]
  __int64 v32; // [rsp+30h] [rbp-48h] BYREF
  PVOID P; // [rsp+38h] [rbp-40h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF
  __int64 v35; // [rsp+50h] [rbp-28h] BYREF
  PVOID v36; // [rsp+58h] [rbp-20h]
  struct _UNICODE_STRING v37; // [rsp+60h] [rbp-18h] BYREF

  v4 = a3;
  Pool2 = (_QWORD *)ExAllocatePool2(64, 64, 1715758931);
  v7 = 0;
  v8 = Pool2;
  if ( Pool2 )
  {
    Pool2[2] = 0;
    Pool2[7] = 0;
    *Pool2 = 0;
    Pool2[1] = 0;
    v9 = Pool2 + 3;
    *v9 = 0;
    v9[1] = 0;
    v9[3] = v9;
    v9[2] = v9;
  }
  else
  {
    v8 = 0;
  }
  kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
    &v30,
    v8);
  v10 = v30;
  v11 = v31;
  if ( !v30 )
    goto LABEL_78;
  if ( !v31 )
    return 3221225626LL;
  if ( !*((_DWORD *)v31 + 2) )
  {
LABEL_78:
    if ( v31 )
    {
      if ( _InterlockedExchangeAdd(v31 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
    return 3221225626LL;
  }
  if ( a1 && a2 >= 0x14 )
  {
    v32 = 0;
    P = 0;
    RtlInitUnicodeString(&DestinationString, 0);
    v12 = *(unsigned __int16 *)(a1 + 6);
    v13 = *(unsigned __int16 *)(a1 + 4);
    if ( __PAIR32__(v12, v13) )
    {
      if ( (unsigned int)v13 > a2 - 20 || (int)v13 + (int)v12 > a2 - 20 )
      {
        v15 = -1073741811;
        goto LABEL_64;
      }
      v14 = v13 + a1 + 20;
    }
    else
    {
      v14 = 0;
    }
    v15 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
            &v32,
            v14,
            v12 >> 1);
    if ( v15 >= 0 )
    {
      if ( (unsigned int)v32 >> 1 > 0xFFFF || (v16 = P, !(unsigned __int16)((unsigned int)v32 >> 1)) )
        v16 = 0;
      if ( !(unsigned __int8)Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(
                               v10,
                               v16,
                               *(unsigned int *)(a1 + 16)) )
      {
        if ( P )
          ExFreePoolWithTag(P, 0);
        if ( v11 && _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
          if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 16LL))(v11);
        }
        return 3221225485LL;
      }
      v18 = *(_DWORD *)(a1 + 8);
      if ( !*(_WORD *)(a1 + 12) )
      {
LABEL_44:
        v28 = P;
        v29 = (volatile signed __int32 *)v4[1];
        *v4 = v10;
        v4[1] = v11;
        if ( v28 )
          ExFreePoolWithTag(v28, 0);
        if ( v29 )
        {
          if ( _InterlockedExchangeAdd(v29 + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
            if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 16LL))(v29);
          }
        }
        return 0;
      }
      while ( v18 + 20 <= a2 )
      {
        v19 = (unsigned int *)(a1 + v18 + 20LL);
        if ( !v19 || a2 - v18 < 8 )
          break;
        v36 = 0;
        v35 = 0;
        RtlInitUnicodeString(&v37, 0);
        v20 = *((unsigned __int16 *)v19 + 3);
        v21 = *((unsigned __int16 *)v19 + 2);
        if ( __PAIR32__(v20, v21) )
        {
          v23 = a2 - v18 - 8;
          if ( (unsigned int)v21 > v23 || (int)v21 + (int)v20 > v23 )
          {
            v15 = -1073741811;
LABEL_54:
            v27 = v36;
            if ( v36 )
            {
LABEL_52:
              ExFreePoolWithTag(v27, 0);
              goto LABEL_64;
            }
            goto LABEL_64;
          }
          v22 = (__int64)v19 + v21 + 8;
        }
        else
        {
          v22 = 0;
        }
        v15 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
                &v35,
                v22,
                v20 >> 1);
        if ( v15 < 0 )
          goto LABEL_54;
        if ( (unsigned int)v35 >> 1 > 0xFFFF || (v25 = v36, !(unsigned __int16)((unsigned int)v35 >> 1)) )
          v25 = 0;
        v10 = v30;
        v26 = Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::add_package(
                v30,
                v25,
                v24,
                0);
        v27 = v36;
        v15 = v26;
        if ( v26 < 0 )
        {
          if ( !v36 )
            goto LABEL_64;
          goto LABEL_52;
        }
        v18 = *v19;
        if ( v36 )
          ExFreePoolWithTag(v36, 0);
        if ( ++v7 >= *(unsigned __int16 *)(a1 + 12) )
        {
          v4 = a3;
          goto LABEL_44;
        }
      }
      if ( P )
        ExFreePoolWithTag(P, 0);
      if ( !v11 )
        return 3221225990LL;
      goto LABEL_59;
    }
LABEL_64:
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v11 )
    {
      if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
    return (unsigned int)v15;
  }
LABEL_59:
  if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return 3221225990LL;
}

```

## disassembly

```asm
0x1800110e8  mov     [rsp-40h+arg_10], r8
0x1800110ed  push    rbp
0x1800110ee  push    rbx
0x1800110ef  push    rsi
0x1800110f0  push    rdi
0x1800110f1  push    r12
0x1800110f3  push    r13
0x1800110f5  push    r14
0x1800110f7  push    r15
0x1800110f9  mov     rbp, rsp
0x1800110fc  sub     rsp, 78h
0x180011100  mov     rdi, rcx
0x180011103  mov     r15, r8
0x180011106  mov     ecx, 40h ; '@'
0x18001110b  mov     r13d, edx
0x18001110e  mov     edx, ecx
0x180011110  mov     r8d, 66446753h
0x180011116  call    cs:__imp_ExAllocatePool2
0x18001111d  nop     dword ptr [rax+rax+00h]
0x180011122  xor     r12d, r12d
0x180011125  mov     rdx, rax
0x180011128  test    rax, rax
0x18001112b  jz      short loc_180011151
0x18001112d  mov     [rax+10h], r12
0x180011131  mov     [rax+38h], r12
0x180011135  mov     [rax], r12
0x180011138  mov     [rax+8], r12
0x18001113c  add     rax, 18h
0x180011140  mov     [rax], r12
0x180011143  mov     [rax+8], r12
0x180011147  mov     [rax+18h], rax
0x18001114b  mov     [rax+10h], rax
0x18001114f  jmp     short loc_180011154
0x180011151  mov     rdx, r12
0x180011154  lea     rcx, [rbp+var_58]
0x180011158  call    ??$?0V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAA@PEAV?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> *)
0x18001115d  mov     r14, [rbp+var_58]
0x180011161  mov     rbx, [rbp+var_50]
0x180011165  test    r14, r14
0x180011168  jz      loc_1800114DC
0x18001116e  test    rbx, rbx
0x180011171  jz      loc_180011518
0x180011177  mov     eax, [rbx+8]
0x18001117a  test    eax, eax
0x18001117c  jz      loc_1800114DC
0x180011182  test    rdi, rdi
0x180011185  jz      loc_18001143F
0x18001118b  cmp     r13d, 14h
0x18001118f  jb      loc_18001143F
0x180011195  xor     edx, edx; SourceString
0x180011197  mov     [rbp+var_48], r12
0x18001119b  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001119f  mov     [rbp+P], r12
0x1800111a3  call    cs:__imp_RtlInitUnicodeString
0x1800111aa  nop     dword ptr [rax+rax+00h]
0x1800111af  movzx   edx, word ptr [rdi+6]
0x1800111b3  movzx   ecx, word ptr [rdi+4]
0x1800111b7  test    dx, dx
0x1800111ba  jnz     short loc_1800111C6
0x1800111bc  test    cx, cx
0x1800111bf  jnz     short loc_1800111C6
0x1800111c1  mov     rax, r12
0x1800111c4  jmp     short loc_1800111E6
0x1800111c6  lea     r8d, [r13-14h]
0x1800111ca  cmp     ecx, r8d
0x1800111cd  ja      loc_180011480
0x1800111d3  lea     eax, [rcx+rdx]
0x1800111d6  cmp     eax, r8d
0x1800111d9  ja      loc_180011480
0x1800111df  lea     rax, [rdi+14h]
0x1800111e3  add     rax, rcx
0x1800111e6  mov     r8, rdx
0x1800111e9  lea     rcx, [rbp+var_48]
0x1800111ed  shr     r8, 1
0x1800111f0  mov     rdx, rax
0x1800111f3  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x1800111f8  mov     esi, eax
0x1800111fa  test    eax, eax
0x1800111fc  js      loc_180011485
0x180011202  mov     eax, dword ptr [rbp+var_48]
0x180011205  mov     r8d, [rdi+10h]
0x180011209  shr     eax, 1
0x18001120b  cmp     eax, 0FFFFh
0x180011210  ja      short loc_18001121B
0x180011212  mov     rdx, [rbp+P]
0x180011216  test    ax, ax
0x180011219  jnz     short loc_18001121E
0x18001121b  mov     rdx, r12
0x18001121e  mov     rcx, r14
0x180011221  call    ?init@?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA_NPEB_WI@Z; Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(wchar_t const *,uint)
0x180011226  test    al, al
0x180011228  jnz     short loc_180011287
0x18001122a  mov     rcx, [rbp+P]; P
0x18001122e  test    rcx, rcx
0x180011231  jz      short loc_180011241
0x180011233  xor     edx, edx; Tag
0x180011235  call    cs:__imp_ExFreePoolWithTag
0x18001123c  nop     dword ptr [rax+rax+00h]
0x180011241  test    rbx, rbx
0x180011244  jz      short loc_18001127D
0x180011246  or      edi, 0FFFFFFFFh
0x180011249  mov     eax, edi
0x18001124b  lock xadd [rbx+8], eax
0x180011250  add     eax, edi
0x180011252  jnz     short loc_18001127D
0x180011254  mov     rax, [rbx]
0x180011257  mov     rcx, rbx
0x18001125a  mov     rax, [rax+8]
0x18001125e  call    _guard_dispatch_icall
0x180011263  mov     eax, edi
0x180011265  lock xadd [rbx+0Ch], eax
0x18001126a  add     eax, edi
0x18001126c  jnz     short loc_18001127D
0x18001126e  mov     rax, [rbx]
0x180011271  mov     rcx, rbx
0x180011274  mov     rax, [rax+10h]
0x180011278  call    _guard_dispatch_icall
0x18001127d  mov     eax, 0C000000Dh
0x180011282  jmp     loc_18001151D
0x180011287  mov     esi, [rdi+8]
0x18001128a  xor     edx, edx
0x18001128c  cmp     dx, [rdi+0Ch]
0x180011290  jnb     loc_180011395
0x180011296  lea     eax, [rsi+14h]
0x180011299  cmp     eax, r13d
0x18001129c  ja      loc_180011423
0x1800112a2  mov     r15d, esi
0x1800112a5  add     r15, 14h
0x1800112a9  add     r15, rdi
0x1800112ac  jz      loc_180011423
0x1800112b2  mov     r14d, r13d
0x1800112b5  sub     r14d, esi
0x1800112b8  cmp     r14d, 8
0x1800112bc  jb      loc_180011423
0x1800112c2  mov     [rbp+var_20], rdx
0x1800112c6  lea     rcx, [rbp+var_18]; DestinationString
0x1800112ca  xor     edx, edx; SourceString
0x1800112cc  mov     [rbp+var_28], 0
0x1800112d4  call    cs:__imp_RtlInitUnicodeString
0x1800112db  nop     dword ptr [rax+rax+00h]
0x1800112e0  movzx   r8d, word ptr [r15+6]
0x1800112e5  xor     r9d, r9d
0x1800112e8  movzx   ecx, word ptr [r15+4]
0x1800112ed  test    r8w, r8w
0x1800112f1  jnz     short loc_1800112FD
0x1800112f3  test    cx, cx
0x1800112f6  jnz     short loc_1800112FD
0x1800112f8  mov     edx, r9d
0x1800112fb  jmp     short loc_18001131E
0x1800112fd  add     r14d, 0FFFFFFF8h
0x180011301  cmp     ecx, r14d
0x180011304  ja      loc_180011411
0x18001130a  lea     eax, [rcx+r8]
0x18001130e  cmp     eax, r14d
0x180011311  ja      loc_180011411
0x180011317  lea     rdx, [rcx+8]
0x18001131b  add     rdx, r15
0x18001131e  shr     r8, 1
0x180011321  lea     rcx, [rbp+var_28]
0x180011325  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18001132a  xor     r9d, r9d
0x18001132d  mov     esi, eax
0x18001132f  test    eax, eax
0x180011331  js      loc_180011416
0x180011337  mov     eax, dword ptr [rbp+var_28]
0x18001133a  shr     eax, 1
0x18001133c  cmp     eax, 0FFFFh
0x180011341  ja      short loc_18001134C
0x180011343  mov     rdx, [rbp+var_20]
0x180011347  test    ax, ax
0x18001134a  jnz     short loc_18001134F
0x18001134c  mov     rdx, r9
0x18001134f  mov     r14, [rbp+var_58]
0x180011353  mov     rcx, r14
0x180011356  call    ?add_package@?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJPEB_W@Z; Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::add_package(wchar_t const *)
0x18001135b  mov     rcx, [rbp+var_20]; P
0x18001135f  xor     edx, edx; Tag
0x180011361  mov     esi, eax
0x180011363  test    eax, eax
0x180011365  js      loc_1800113FA
0x18001136b  mov     esi, [r15]
0x18001136e  test    rcx, rcx
0x180011371  jz      short loc_180011381
0x180011373  call    cs:__imp_ExFreePoolWithTag
0x18001137a  nop     dword ptr [rax+rax+00h]
0x18001137f  xor     edx, edx
0x180011381  movzx   eax, word ptr [rdi+0Ch]
0x180011385  inc     r12d
0x180011388  cmp     r12d, eax
0x18001138b  jl      loc_180011296
0x180011391  mov     r15, [rbp+arg_10]
0x180011395  mov     rcx, [rbp+P]; P
0x180011399  mov     rsi, [r15+8]
0x18001139d  mov     [r15], r14
0x1800113a0  mov     [r15+8], rbx
0x1800113a4  test    rcx, rcx
0x1800113a7  jz      short loc_1800113B7
0x1800113a9  xor     edx, edx; Tag
0x1800113ab  call    cs:__imp_ExFreePoolWithTag
0x1800113b2  nop     dword ptr [rax+rax+00h]
0x1800113b7  test    rsi, rsi
0x1800113ba  jz      short loc_1800113F3
0x1800113bc  or      edi, 0FFFFFFFFh
0x1800113bf  mov     eax, edi
0x1800113c1  lock xadd [rsi+8], eax
0x1800113c6  add     eax, edi
0x1800113c8  jnz     short loc_1800113F3
0x1800113ca  mov     rax, [rsi]
0x1800113cd  mov     rcx, rsi
0x1800113d0  mov     rax, [rax+8]
0x1800113d4  call    _guard_dispatch_icall
0x1800113d9  mov     eax, edi
0x1800113db  lock xadd [rsi+0Ch], eax
0x1800113e0  add     eax, edi
0x1800113e2  jnz     short loc_1800113F3
0x1800113e4  mov     rax, [rsi]
0x1800113e7  mov     rcx, rsi
0x1800113ea  mov     rax, [rax+10h]
0x1800113ee  call    _guard_dispatch_icall
0x1800113f3  xor     eax, eax
0x1800113f5  jmp     loc_18001151D
0x1800113fa  test    rcx, rcx
0x1800113fd  jz      loc_180011485
0x180011403  call    cs:__imp_ExFreePoolWithTag
0x18001140a  nop     dword ptr [rax+rax+00h]
0x18001140f  jmp     short loc_180011485
0x180011411  mov     esi, 0C000000Dh
0x180011416  mov     rcx, [rbp+var_20]
0x18001141a  test    rcx, rcx
0x18001141d  jz      short loc_180011485
0x18001141f  xor     edx, edx
0x180011421  jmp     short loc_180011403
0x180011423  mov     rcx, [rbp+P]; P
0x180011427  test    rcx, rcx
0x18001142a  jz      short loc_18001143A
0x18001142c  xor     edx, edx; Tag
0x18001142e  call    cs:__imp_ExFreePoolWithTag
0x180011435  nop     dword ptr [rax+rax+00h]
0x18001143a  test    rbx, rbx
0x18001143d  jz      short loc_180011476
0x18001143f  or      edi, 0FFFFFFFFh
0x180011442  mov     eax, edi
0x180011444  lock xadd [rbx+8], eax
0x180011449  add     eax, edi
0x18001144b  jnz     short loc_180011476
0x18001144d  mov     rax, [rbx]
0x180011450  mov     rcx, rbx
0x180011453  mov     rax, [rax+8]
0x180011457  call    _guard_dispatch_icall
0x18001145c  mov     eax, edi
0x18001145e  lock xadd [rbx+0Ch], eax
0x180011463  add     eax, edi
0x180011465  jnz     short loc_180011476
0x180011467  mov     rax, [rbx]
0x18001146a  mov     rcx, rbx
0x18001146d  mov     rax, [rax+10h]
0x180011471  call    _guard_dispatch_icall
0x180011476  mov     eax, 0C0000206h
0x18001147b  jmp     loc_18001151D
0x180011480  mov     esi, 0C000000Dh
0x180011485  mov     rcx, [rbp+P]; P
0x180011489  test    rcx, rcx
0x18001148c  jz      short loc_18001149C
0x18001148e  xor     edx, edx; Tag
0x180011490  call    cs:__imp_ExFreePoolWithTag
0x180011497  nop     dword ptr [rax+rax+00h]
0x18001149c  test    rbx, rbx
0x18001149f  jz      short loc_1800114D8
0x1800114a1  or      edi, 0FFFFFFFFh
0x1800114a4  mov     eax, edi
0x1800114a6  lock xadd [rbx+8], eax
0x1800114ab  add     eax, edi
0x1800114ad  jnz     short loc_1800114D8
0x1800114af  mov     rax, [rbx]
0x1800114b2  mov     rcx, rbx
0x1800114b5  mov     rax, [rax+8]
0x1800114b9  call    _guard_dispatch_icall
0x1800114be  mov     eax, edi
0x1800114c0  lock xadd [rbx+0Ch], eax
0x1800114c5  add     eax, edi
0x1800114c7  jnz     short loc_1800114D8
0x1800114c9  mov     rax, [rbx]
0x1800114cc  mov     rcx, rbx
0x1800114cf  mov     rax, [rax+10h]
0x1800114d3  call    _guard_dispatch_icall
0x1800114d8  mov     eax, esi
0x1800114da  jmp     short loc_18001151D
0x1800114dc  test    rbx, rbx
0x1800114df  jz      short loc_180011518
0x1800114e1  or      edi, 0FFFFFFFFh
0x1800114e4  mov     eax, edi
0x1800114e6  lock xadd [rbx+8], eax
0x1800114eb  add     eax, edi
0x1800114ed  jnz     short loc_180011518
0x1800114ef  mov     rax, [rbx]
0x1800114f2  mov     rcx, rbx
0x1800114f5  mov     rax, [rax+8]
0x1800114f9  call    _guard_dispatch_icall
0x1800114fe  mov     eax, edi
0x180011500  lock xadd [rbx+0Ch], eax
  ... truncated ...
```
