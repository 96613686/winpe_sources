# RunVirtualInfoStore<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ReadValues(appv::shared::kernel::handle &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &)

- ea: `0x180019014`
- end: `0x180019314`
- name: `?ReadValues@?$RunVirtualInfoStore@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CA_NAEAVhandle@kernel@shared@appv@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@345@AEAV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@@Z`
- size: `768`
- prototype: `char __fastcall(void **, __int64, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, registry_config`

## callers

- `0x180017c7c`

## callees

- `0x1800038fc`
- `0x180003f50`
- `0x180005178`
- `0x18000a9e4`
- `0x18000c31c`
- `0x18000cf74`
- `0x180019014`
- `0x18001a4d4`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180019224`
- `ntoskrnl!ExAllocatePool2` at `0x180019224`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800192c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x180019306`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800192c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x180019306`
- `ntoskrnl!RtlInitUnicodeString` at `0x180019108`
- `ntoskrnl!RtlInitUnicodeString` at `0x180019245`
- `ntoskrnl!RtlInitUnicodeString` at `0x180019108`
- `ntoskrnl!RtlInitUnicodeString` at `0x180019245`

## string_xrefs

- `0x180019097`: `unVirtualInfoStore::ReadValues() - Failed to enumrate registry value from registry key %s. Error: %d`
- `0x1800190e6`: `unVirtualInfoStore::ReadValues() - Failed to get moniker from value %s`
- `0x180019200`: `runVirtualInfoStore::ReadValues() - Failed to normalize absolute path from value %s. Error %d.`
- `0x1800192a4`: `unVirtualInfoStore::ReadValues() - Failed to get registry value from registry key %s. Error: %d.`

## pseudocode

```c
char __fastcall RunVirtualInfoStore<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ReadValues(
        void **a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  void *v6; // rcx
  int v8; // r8d
  unsigned int v9; // ecx
  __int16 v10; // dx
  __int16 v11; // ax
  __int64 v12; // r9
  unsigned int v14; // ecx
  __int16 v15; // dx
  __int16 v16; // ax
  __int64 v17; // r9
  __int64 v18; // r9
  unsigned int **v19; // rbx
  char v20; // si
  unsigned int v21; // eax
  unsigned int v22; // eax
  _WORD *v23; // rdx
  __int64 v24; // r8
  unsigned __int16 v25; // dx
  const WCHAR *v26; // rdx
  int v27; // eax
  PVOID v28; // r9
  __int64 Pool2; // rax
  _QWORD *v30; // r14
  unsigned int v31; // eax
  __int64 v32; // rdx
  int value; // eax
  unsigned int v34; // ecx
  __int64 v35; // r9
  PVOID v36; // rcx
  __int64 v37; // [rsp+20h] [rbp-49h]
  __int64 v38; // [rsp+30h] [rbp-39h] BYREF
  PVOID P; // [rsp+38h] [rbp-31h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  int v41; // [rsp+50h] [rbp-19h] BYREF
  __int128 v42; // [rsp+58h] [rbp-11h] BYREF
  __int128 *v43; // [rsp+68h] [rbp-1h]
  unsigned int **v44; // [rsp+70h] [rbp+7h]

  v44 = (unsigned int **)&v42;
  v6 = *a1;
  v43 = &v42;
  v41 = 0;
  v42 = 0;
  v8 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_values(
         v6,
         (__int64)&v41,
         (__int64)a3,
         a4);
  if ( v8 < 0 )
  {
    v9 = *(_DWORD *)a2 >> 1;
    if ( v9 > 0xFFFF )
      v10 = -1;
    else
      v10 = *(_DWORD *)a2 >> 1;
    v11 = 0;
    v12 = 0;
    if ( v9 <= 0xFFFF )
      v11 = v10;
    if ( v11 )
      v12 = *(_QWORD *)(a2 + 8);
    LogWrite(
      1,
      0,
      L"unVirtualInfoStore::ReadValues() - Failed to enumrate registry value from registry key %s. Error: %d",
      v12,
      v8);
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v41);
    return 0;
  }
  if ( !v41 )
  {
    v14 = *(_DWORD *)a2 >> 1;
    if ( v14 > 0xFFFF )
      v15 = -1;
    else
      v15 = *(_DWORD *)a2 >> 1;
    v16 = 0;
    v17 = 0;
    if ( v14 <= 0xFFFF )
      v16 = v15;
    if ( v16 )
      v17 = *(_QWORD *)(a2 + 8);
    LogWrite(1, 0, L"unVirtualInfoStore::ReadValues() - Failed to get moniker from value %s", v17);
LABEL_62:
    v20 = 0;
    goto LABEL_63;
  }
  v38 = 0;
  P = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v19 = v44;
  v20 = 1;
  while ( 1 )
  {
    if ( v19 == (unsigned int **)&v42 )
      goto LABEL_59;
    v21 = **v19;
    if ( v21 > 2 )
      break;
LABEL_40:
    v19 = (unsigned int **)v19[3];
  }
  v22 = v21 >> 1;
  if ( v22 <= 0xFFFF && (_WORD)v22 )
  {
    v23 = (_WORD *)*((_QWORD *)*v19 + 1);
    if ( v23 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v23[v24] );
      goto LABEL_30;
    }
  }
  else
  {
    v23 = 0;
  }
  v24 = 0;
LABEL_30:
  appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
    (__int64)&v38,
    v23,
    v24,
    v18);
  if ( DestinationString.Buffer && DestinationString.Length >= 2u && DestinationString.Length >> 1 )
  {
    v25 = 0;
    while ( DestinationString.Buffer[v25] != 58 )
    {
      if ( ++v25 >= (unsigned __int16)(DestinationString.Length >> 1) )
        goto LABEL_36;
    }
    v27 = appv::vemgr::path_normalizer::normalize_path<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
            (__int64)&v38,
            0);
    if ( v27 < 0 )
    {
      if ( (unsigned int)v38 >> 1 > 0xFFFF || (v28 = P, !(unsigned __int16)((unsigned int)v38 >> 1)) )
        v28 = 0;
      LODWORD(v37) = v27;
      LogWrite(
        1,
        0,
        L"runVirtualInfoStore::ReadValues() - Failed to normalize absolute path from value %s. Error %d.",
        v28,
        v37);
      goto LABEL_40;
    }
  }
LABEL_36:
  if ( (unsigned int)v38 >> 1 > 0xFFFF || (v26 = (const WCHAR *)P, !(unsigned __int16)((unsigned int)v38 >> 1)) )
    v26 = 0;
  if ( !appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::iends_in(
          a2,
          v26) )
    goto LABEL_40;
  Pool2 = ExAllocatePool2(64, 32, 1715758931);
  v30 = (_QWORD *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = 0;
    *(_QWORD *)(Pool2 + 8) = 0;
    RtlInitUnicodeString((PUNICODE_STRING)(Pool2 + 16), 0);
  }
  else
  {
    v30 = 0;
  }
  kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
    a3,
    v30);
  v31 = **v19 >> 1;
  if ( v31 <= 0xFFFF && (_WORD)v31 )
    v32 = *((_QWORD *)*v19 + 1);
  else
    v32 = 0;
  value = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
            *a1,
            v32,
            *a3);
  if ( value < 0 )
  {
    v34 = **v19 >> 1;
    if ( v34 <= 0xFFFF && (_WORD)v34 )
      v35 = *((_QWORD *)*v19 + 1);
    else
      v35 = 0;
    LODWORD(v37) = value;
    LogWrite(
      1,
      0,
      L"unVirtualInfoStore::ReadValues() - Failed to get registry value from registry key %s. Error: %d.",
      v35,
      v37);
LABEL_59:
    v36 = P;
LABEL_60:
    if ( v36 )
      ExFreePoolWithTag(v36, 0);
    goto LABEL_62;
  }
  v36 = P;
  if ( *(_DWORD *)*a3 <= 2u )
    goto LABEL_60;
  if ( P )
    ExFreePoolWithTag(P, 0);
LABEL_63:
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v41);
  return v20;
}

```

## disassembly

```asm
0x180019014  push    rbp
0x180019016  push    rbx
0x180019017  push    rsi
0x180019018  push    rdi
0x180019019  push    r12
0x18001901b  push    r13
0x18001901d  push    r14
0x18001901f  push    r15
0x180019021  lea     rbp, [rsp-1Fh]
0x180019026  sub     rsp, 88h
0x18001902d  lea     rax, [rbp+57h+var_68]
0x180019031  mov     r14, rdx
0x180019034  mov     [rbp+57h+var_50], rax
0x180019038  lea     rdx, [rbp+57h+var_70]
0x18001903c  lea     rax, [rbp+57h+var_68]
0x180019040  mov     r12, rcx
0x180019043  mov     rcx, [rcx]; KeyHandle
0x180019046  xorps   xmm0, xmm0
0x180019049  xor     r13d, r13d
0x18001904c  mov     [rbp+57h+var_58], rax
0x180019050  mov     r15, r8
0x180019053  mov     [rbp+57h+var_70], r13d
0x180019057  movdqu  [rbp+57h+var_68], xmm0
0x18001905c  call    ?enum_values@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_values(void *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x180019061  mov     r8d, eax
0x180019064  test    eax, eax
0x180019066  jns     short loc_1800190B6
0x180019068  mov     ecx, [r14]
0x18001906b  mov     edi, 0FFFFh
0x180019070  shr     ecx, 1
0x180019072  cmp     ecx, edi
0x180019074  ja      short loc_18001907B
0x180019076  movzx   edx, cx
0x180019079  jmp     short loc_18001907D
0x18001907b  mov     edx, edi
0x18001907d  mov     eax, r13d
0x180019080  mov     r9, r13
0x180019083  cmovbe  ax, dx
0x180019087  test    ax, ax
0x18001908a  jz      short loc_180019090
0x18001908c  mov     r9, [r14+8]
0x180019090  xor     edx, edx
0x180019092  mov     [rsp+0C0h+var_A0], r8d
0x180019097  lea     r8, aUnvirtualinfos_3; "unVirtualInfoStore::ReadValues() - Fail"...
0x18001909e  lea     ecx, [rdx+1]
0x1800190a1  call    LogWrite
0x1800190a6  lea     rcx, [rbp+57h+var_70]
0x1800190aa  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x1800190af  xor     al, al
0x1800190b1  jmp     loc_1800192DE
0x1800190b6  cmp     [rbp+57h+var_70], r13d
0x1800190ba  jnz     short loc_1800190FA
0x1800190bc  mov     ecx, [r14]
0x1800190bf  mov     edi, 0FFFFh
0x1800190c4  shr     ecx, 1
0x1800190c6  cmp     ecx, edi
0x1800190c8  ja      short loc_1800190CF
0x1800190ca  movzx   edx, cx
0x1800190cd  jmp     short loc_1800190D1
0x1800190cf  mov     edx, edi
0x1800190d1  mov     eax, r13d
0x1800190d4  mov     r9, r13
0x1800190d7  cmovbe  ax, dx
0x1800190db  test    ax, ax
0x1800190de  jz      short loc_1800190E4
0x1800190e0  mov     r9, [r14+8]
0x1800190e4  xor     edx, edx
0x1800190e6  lea     r8, aUnvirtualinfos_5; "unVirtualInfoStore::ReadValues() - Fail"...
0x1800190ed  lea     ecx, [rdx+1]
0x1800190f0  call    LogWrite
0x1800190f5  jmp     loc_1800192CF
0x1800190fa  xor     edx, edx; SourceString
0x1800190fc  mov     [rbp+57h+var_90], r13
0x180019100  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180019104  mov     [rbp+57h+P], r13
0x180019108  call    cs:__imp_RtlInitUnicodeString
0x18001910f  nop     dword ptr [rax+rax+00h]
0x180019114  mov     rbx, [rbp+57h+var_50]
0x180019118  mov     esi, 1
0x18001911d  mov     edi, 0FFFFh
0x180019122  lea     ecx, [rsi+1]
0x180019125  lea     rax, [rbp+57h+var_68]
0x180019129  cmp     rbx, rax
0x18001912c  jz      loc_1800192B8
0x180019132  mov     rdx, [rbx]
0x180019135  mov     eax, [rdx]
0x180019137  cmp     eax, ecx
0x180019139  jbe     loc_1800191D3
0x18001913f  shr     eax, 1
0x180019141  cmp     eax, edi
0x180019143  ja      short loc_180019163
0x180019145  test    ax, ax
0x180019148  jz      short loc_180019163
0x18001914a  mov     rdx, [rdx+8]
0x18001914e  test    rdx, rdx
0x180019151  jz      short loc_180019166
0x180019153  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019157  inc     r8
0x18001915a  cmp     [rdx+r8*2], r13w
0x18001915f  jnz     short loc_180019157
0x180019161  jmp     short loc_180019169
0x180019163  mov     rdx, r13
0x180019166  mov     r8, r13
0x180019169  lea     rcx, [rbp+57h+var_90]
0x18001916d  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x180019172  mov     r8, [rbp+57h+DestinationString.Buffer]
0x180019176  test    r8, r8
0x180019179  jz      short loc_1800191AD
0x18001917b  movzx   ecx, [rbp+57h+DestinationString.Length]
0x18001917f  mov     eax, 2
0x180019184  cmp     cx, ax
0x180019187  jb      short loc_1800191AD
0x180019189  shr     cx, 1
0x18001918c  cmp     r13w, cx
0x180019190  jnb     short loc_1800191AD
0x180019192  mov     edx, r13d
0x180019195  movzx   eax, dx
0x180019198  mov     r9d, 3Ah ; ':'
0x18001919e  cmp     r9w, [r8+rax*2]
0x1800191a3  jz      short loc_1800191DC
0x1800191a5  add     dx, si
0x1800191a8  cmp     dx, cx
0x1800191ab  jb      short loc_180019195
0x1800191ad  mov     eax, dword ptr [rbp+57h+var_90]
0x1800191b0  shr     eax, 1
0x1800191b2  cmp     eax, edi
0x1800191b4  ja      short loc_1800191BF
0x1800191b6  mov     rdx, [rbp+57h+P]
0x1800191ba  test    ax, ax
0x1800191bd  jnz     short loc_1800191C2
0x1800191bf  mov     rdx, r13
0x1800191c2  mov     rcx, r14
0x1800191c5  call    ?iends_in@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEBA_NPEB_W@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::iends_in(wchar_t const *)
0x1800191ca  test    al, al
0x1800191cc  jnz     short loc_180019216
0x1800191ce  mov     ecx, 2
0x1800191d3  mov     rbx, [rbx+18h]
0x1800191d7  jmp     loc_180019125
0x1800191dc  xor     edx, edx
0x1800191de  lea     rcx, [rbp+57h+var_90]
0x1800191e2  call    ??$normalize_path@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@path_normalizer@vemgr@appv@@SAJAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@2@_N@Z; appv::vemgr::path_normalizer::normalize_path<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,bool)
0x1800191e7  test    eax, eax
0x1800191e9  jns     short loc_1800191AD
0x1800191eb  mov     ecx, dword ptr [rbp+57h+var_90]
0x1800191ee  shr     ecx, 1
0x1800191f0  cmp     ecx, edi
0x1800191f2  ja      short loc_1800191FD
0x1800191f4  mov     r9, [rbp+57h+P]
0x1800191f8  test    cx, cx
0x1800191fb  jnz     short loc_180019200
0x1800191fd  mov     r9, r13
0x180019200  lea     r8, aRunvirtualinfo; "runVirtualInfoStore::ReadValues() - Fai"...
0x180019207  mov     [rsp+0C0h+var_A0], eax
0x18001920b  xor     edx, edx
0x18001920d  mov     ecx, esi
0x18001920f  call    LogWrite
0x180019214  jmp     short loc_1800191CE
0x180019216  mov     edx, 20h ; ' '
0x18001921b  mov     r8d, 66446753h
0x180019221  lea     ecx, [rdx+20h]
0x180019224  call    cs:__imp_ExAllocatePool2
0x18001922b  nop     dword ptr [rax+rax+00h]
0x180019230  mov     r14, rax
0x180019233  test    rax, rax
0x180019236  jz      short loc_180019253
0x180019238  lea     rcx, [rax+10h]; DestinationString
0x18001923c  mov     [rax], r13
0x18001923f  xor     edx, edx; SourceString
0x180019241  mov     [rax+8], r13
0x180019245  call    cs:__imp_RtlInitUnicodeString
0x18001924c  nop     dword ptr [rax+rax+00h]
0x180019251  jmp     short loc_180019256
0x180019253  mov     r14, r13
0x180019256  mov     rdx, r14
0x180019259  mov     rcx, r15
0x18001925c  call    ??$reset@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAAXPEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x180019261  mov     rdx, [rbx]
0x180019264  mov     r8, [r15]
0x180019267  mov     eax, [rdx]
0x180019269  shr     eax, 1
0x18001926b  cmp     eax, edi
0x18001926d  ja      short loc_18001927A
0x18001926f  test    ax, ax
0x180019272  jz      short loc_18001927A
0x180019274  mov     rdx, [rdx+8]
0x180019278  jmp     short loc_18001927D
0x18001927a  mov     rdx, r13
0x18001927d  mov     rcx, [r12]
0x180019281  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x180019286  test    eax, eax
0x180019288  jns     short loc_1800192F3
0x18001928a  mov     r9, [rbx]
0x18001928d  mov     ecx, [r9]
0x180019290  shr     ecx, 1
0x180019292  cmp     ecx, edi
0x180019294  ja      short loc_1800192A1
0x180019296  test    cx, cx
0x180019299  jz      short loc_1800192A1
0x18001929b  mov     r9, [r9+8]
0x18001929f  jmp     short loc_1800192A4
0x1800192a1  mov     r9, r13
0x1800192a4  lea     r8, aUnvirtualinfos_7; "unVirtualInfoStore::ReadValues() - Fail"...
0x1800192ab  mov     [rsp+0C0h+var_A0], eax
0x1800192af  xor     edx, edx
0x1800192b1  mov     ecx, esi
0x1800192b3  call    LogWrite
0x1800192b8  mov     rcx, [rbp+57h+P]; P
0x1800192bc  test    rcx, rcx
0x1800192bf  jz      short loc_1800192CF
0x1800192c1  xor     edx, edx; Tag
0x1800192c3  call    cs:__imp_ExFreePoolWithTag
0x1800192ca  nop     dword ptr [rax+rax+00h]
0x1800192cf  mov     sil, r13b
0x1800192d2  lea     rcx, [rbp+57h+var_70]
0x1800192d6  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x1800192db  mov     al, sil
0x1800192de  add     rsp, 88h
0x1800192e5  pop     r15
0x1800192e7  pop     r14
0x1800192e9  pop     r13
0x1800192eb  pop     r12
0x1800192ed  pop     rdi
0x1800192ee  pop     rsi
0x1800192ef  pop     rbx
0x1800192f0  pop     rbp
0x1800192f1  retn
0x1800192f3  mov     rax, [r15]
0x1800192f6  mov     rcx, [rbp+57h+P]; P
0x1800192fa  cmp     dword ptr [rax], 2
0x1800192fd  jbe     short loc_1800192BC
0x1800192ff  test    rcx, rcx
0x180019302  jz      short loc_1800192D2
0x180019304  xor     edx, edx; Tag
0x180019306  call    cs:__imp_ExFreePoolWithTag
0x18001930d  nop     dword ptr [rax+rax+00h]
0x180019312  jmp     short loc_1800192D2
```
