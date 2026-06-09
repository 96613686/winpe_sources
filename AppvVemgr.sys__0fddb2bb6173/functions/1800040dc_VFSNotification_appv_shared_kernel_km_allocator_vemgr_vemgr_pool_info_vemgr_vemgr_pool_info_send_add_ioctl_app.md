# VFSNotification<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::send_add_ioctl<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,void *,ulong,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &,ushort)

- ea: `0x1800040dc`
- end: `0x180004566`
- name: `??$send_add_ioctl@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@$$CBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@234@@?$VFSNotification@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@PEAXKAEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@234@G@Z`
- size: `1162`
- prototype: `__int64 __fastcall(__int64, __int64, const void *, unsigned int, __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180005890`
- `0x180006460`

## callees

- `0x180003bd8`
- `0x1800040dc`
- `0x18000456c`
- `0x18000e8d4`
- `0x18001bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180004380`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800044f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x180004512`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000453b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180004380`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800044f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x180004512`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000453b`

## pseudocode

```c
__int64 __fastcall VFSNotification<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::send_add_ioctl<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const>(
        __int64 a1,
        __int64 a2,
        const void *a3,
        unsigned int a4,
        __int64 a5,
        int a6)
{
  unsigned int v6; // r10d
  __int64 v8; // r9
  unsigned __int16 v9; // ax
  unsigned int v10; // edi
  unsigned int v11; // r15d
  unsigned int v12; // ecx
  signed int v13; // ebp
  __int64 v14; // rax
  __int64 v15; // r8
  unsigned int v16; // r12d
  __int64 v17; // rcx
  int v18; // r11d
  _DWORD *v19; // r10
  __int16 v20; // r9
  unsigned __int16 v21; // cx
  unsigned int v22; // edx
  unsigned int v23; // r11d
  unsigned int v24; // ebx
  __int16 v25; // si
  unsigned __int16 v26; // cx
  unsigned int v27; // esi
  unsigned int v28; // edx
  bool v29; // cf
  unsigned int v30; // r11d
  __int16 v31; // dx
  unsigned __int16 v32; // cx
  unsigned int v33; // ebx
  bool v34; // cc
  unsigned int v35; // r11d
  unsigned int v36; // edx
  __int16 v37; // dx
  unsigned __int16 v38; // cx
  unsigned int v39; // esi
  unsigned int v40; // r11d
  unsigned int v41; // edx
  __int16 v42; // dx
  unsigned __int16 v43; // cx
  unsigned int v44; // ebx
  unsigned int v45; // r11d
  unsigned int v46; // edx
  __int16 v47; // dx
  unsigned __int16 v48; // cx
  unsigned int v49; // edx
  unsigned int v50; // edx
  unsigned int v51; // r8d
  int v52; // ecx
  unsigned int v53; // r14d
  unsigned int v54; // eax
  int v55; // ebx
  char *v57; // rbx
  int v58; // esi
  unsigned int v59; // ebp
  unsigned int v60; // ecx
  unsigned int v61; // edi
  __int16 v62; // dx
  unsigned __int16 v63; // ax
  unsigned int v64; // ecx
  __int16 v65; // dx
  __int16 v66; // ax
  const void *v67; // rdx
  __int16 v68; // ax
  __int64 v69; // rdx
  unsigned int v70; // edi
  __int64 v71; // [rsp+20h] [rbp-58h] BYREF
  PVOID P; // [rsp+28h] [rbp-50h]

  v6 = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 > 0xFFFFu )
    v8 = 0xFFFF;
  else
    v8 = (unsigned __int16)v6;
  v9 = 0;
  if ( v6 <= 0xFFFF )
    v9 = v8;
  v10 = -1;
  v11 = -1;
  v12 = v9 + 24;
  v13 = 0;
  if ( v12 + a4 >= v12 )
    v11 = v12 + a4;
  if ( (unsigned int)v9 + 24 >= 0x18 )
    v13 = v12 + a4 < v12 ? 0xC0000095 : 0;
  v14 = *(_QWORD *)(a5 + 32);
  LODWORD(v15) = 0;
  v16 = 0;
  while ( v14 != a5 + 8 )
  {
    v17 = *(_QWORD *)(v14 + 8);
    v8 = 0;
    v18 = 0;
    if ( v17 )
    {
      if ( *(_DWORD *)(v17 + 8) )
      {
        v19 = *(_DWORD **)v14;
        if ( *(_QWORD *)v14 )
        {
          if ( *v19 > 0xFFFFu )
            v20 = -1;
          else
            v20 = *v19;
          v21 = 0;
          v22 = v19[8];
          if ( *v19 <= 0xFFFFu )
            v21 = v20;
          v23 = v21 + 40;
          v24 = v23;
          v8 = 0;
          if ( v22 > 0xFFFF )
            v25 = -1;
          else
            v25 = v19[8];
          v26 = 0;
          if ( v22 <= 0xFFFF )
            v26 = v25;
          v27 = -1;
          v28 = v23 + v26;
          if ( v28 >= v23 )
            v27 = v23 + v26;
          v29 = v23 < 0x28;
          v30 = v19[16];
          if ( !v29 )
            v8 = v28 < v24 ? 0xC0000095 : 0;
          if ( v30 > 0xFFFF )
            v31 = -1;
          else
            v31 = v19[16];
          v32 = 0;
          v33 = -1;
          v34 = v30 <= 0xFFFF;
          v35 = v19[24];
          if ( v34 )
            v32 = v31;
          v36 = v27 + v32;
          if ( v36 >= v27 )
            v33 = v27 + v32;
          if ( (int)v8 >= 0 )
            v8 = v36 < v27 ? 0xC0000095 : 0;
          if ( v35 > 0xFFFF )
            v37 = -1;
          else
            v37 = v19[24];
          v38 = 0;
          v39 = -1;
          v34 = v35 <= 0xFFFF;
          v40 = v19[32];
          if ( v34 )
            v38 = v37;
          v41 = v33 + v38;
          if ( v41 >= v33 )
            v39 = v33 + v38;
          if ( (int)v8 >= 0 )
            v8 = v41 < v33 ? 0xC0000095 : 0;
          if ( v40 > 0xFFFF )
            v42 = -1;
          else
            v42 = v19[32];
          v43 = 0;
          v44 = -1;
          v34 = v40 <= 0xFFFF;
          v45 = v19[40];
          if ( v34 )
            v43 = v42;
          v46 = v39 + v43;
          if ( v46 >= v39 )
            v44 = v39 + v43;
          if ( (int)v8 >= 0 )
            v8 = v46 < v39 ? 0xC0000095 : 0;
          if ( v45 > 0xFFFF )
            v47 = -1;
          else
            v47 = v19[40];
          v48 = 0;
          v34 = v45 <= 0xFFFF;
          v18 = -1;
          if ( v34 )
            v48 = v47;
          v49 = v44 + v48;
          if ( v49 >= v44 )
            v18 = v44 + v48;
          if ( (int)v8 >= 0 )
            v8 = v49 < v44 ? 0xC0000095 : 0;
        }
      }
    }
    if ( (int)v15 >= 0 )
    {
      if ( (int)v8 < 0 )
      {
        LODWORD(v15) = v8;
      }
      else
      {
        v50 = v16 + v18;
        v51 = v16;
        v52 = -1;
        if ( v16 + v18 >= v16 )
          v52 = v16 + v18;
        v16 = v52;
        LODWORD(v15) = v50 < v51 ? 0xC0000095 : 0;
      }
    }
    v14 = *(_QWORD *)(v14 + 24);
  }
  v53 = a4;
  if ( v13 < 0 )
  {
    LODWORD(v15) = v13;
    return (unsigned int)v15;
  }
  if ( (int)v15 < 0 )
    return (unsigned int)v15;
  v54 = v11 + v16;
  if ( v11 + v16 >= v11 )
    v10 = v11 + v16;
  v15 = v54 < v11 ? 0xC0000095 : 0;
  if ( v54 < v11 )
    return (unsigned int)v15;
  v71 = 0;
  P = 0;
  v55 = appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(
          &v71,
          v10,
          v15,
          v8);
  if ( v55 < 0 )
  {
    if ( P )
      ExFreePoolWithTag(P, 0);
    return (unsigned int)v55;
  }
  v57 = (char *)P;
  if ( !P )
    return 3221225473LL;
  v58 = v71;
  if ( (unsigned int)v71 < 0x18 )
  {
LABEL_120:
    ExFreePoolWithTag(v57, 0);
    return 3221225473LL;
  }
  *(_DWORD *)P = v10;
  *((_DWORD *)v57 + 1) = 1;
  *((_DWORD *)v57 + 2) = 2;
  v59 = v58 - 24;
  v60 = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 > 2u )
  {
    if ( v60 > 0xFFFF )
      v62 = -1;
    else
      v62 = *(_DWORD *)a2;
    v63 = 0;
    if ( v60 <= 0xFFFF )
      v63 = v62;
    v61 = v63 - 2;
  }
  else
  {
    v61 = 0;
  }
  v64 = v60 >> 1;
  if ( v64 > 0xFFFF )
    v65 = -1;
  else
    v65 = v64;
  v66 = 0;
  if ( v64 <= 0xFFFF )
    v66 = v65;
  if ( v66 && (v67 = *(const void **)(a2 + 8)) != 0 && v61 )
  {
    if ( v61 > v59 )
      goto LABEL_119;
    memmove(v57 + 24, v67, v61);
  }
  else
  {
    v61 = 0;
  }
  *((_WORD *)v57 + 6) = 0;
  if ( v61 > 0xFFFF )
  {
    *((_WORD *)v57 + 7) = -1;
    goto LABEL_119;
  }
  *((_WORD *)v57 + 7) = v61;
  if ( a3 && a4 )
  {
    if ( a4 > v59 - v61 )
      goto LABEL_119;
    memmove(&v57[v61 + 24], a3, a4);
    v68 = v61;
    v61 += a4;
  }
  else
  {
    v68 = 0;
    v53 = 0;
  }
  *((_WORD *)v57 + 8) = v68;
  if ( v53 > 0xFFFF )
  {
    *((_WORD *)v57 + 9) = -1;
    goto LABEL_119;
  }
  *((_WORD *)v57 + 9) = v53;
  if ( v61 <= 0xFFFF )
  {
    *((_WORD *)v57 + 10) = v61;
    a6 = 0;
    if ( (unsigned __int8)vfs_mapping_packer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::pack_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>>(
                            a5,
                            &v57[v61 + 24],
                            v58 - v61,
                            &a6) )
    {
      v70 = VFSNotification<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::send_ioctl<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
              a1,
              v69,
              &v71);
      if ( v57 )
        ExFreePoolWithTag(v57, 0);
      return v70;
    }
LABEL_119:
    if ( v57 )
      goto LABEL_120;
    return 3221225473LL;
  }
  *((_WORD *)v57 + 10) = -1;
  if ( v57 )
    ExFreePoolWithTag(v57, 0);
  return 3221225621LL;
}

```

## disassembly

```asm
0x1800040dc  mov     rax, rsp
0x1800040df  mov     [rax+20h], r9d
0x1800040e3  mov     [rax+18h], r8
0x1800040e7  mov     [rax+10h], rdx
0x1800040eb  mov     [rax+8], rcx
0x1800040ef  push    rbx
0x1800040f0  push    rbp
0x1800040f1  push    rsi
0x1800040f2  push    rdi
0x1800040f3  push    r12
0x1800040f5  push    r13
0x1800040f7  push    r14
0x1800040f9  push    r15
0x1800040fb  sub     rsp, 38h
0x1800040ff  mov     r10d, [rdx]
0x180004102  mov     ecx, 0FFFFh
0x180004107  mov     r14d, r9d
0x18000410a  cmp     r10d, ecx
0x18000410d  ja      short loc_180004115
0x18000410f  movzx   r9d, r10w
0x180004113  jmp     short loc_180004118
0x180004115  mov     r9d, ecx
0x180004118  xor     eax, eax
0x18000411a  mov     esi, 0C0000095h
0x18000411f  cmp     r10d, ecx
0x180004122  cmovbe  ax, r9w
0x180004127  or      edi, 0FFFFFFFFh
0x18000412a  movzx   edx, ax
0x18000412d  mov     ecx, edi
0x18000412f  add     edx, 18h
0x180004132  mov     r15d, edi
0x180004135  cmp     edx, 18h
0x180004138  cmovnb  ecx, edx
0x18000413b  sbb     ebp, ebp
0x18000413d  and     ebp, esi
0x18000413f  lea     eax, [rcx+r14]
0x180004143  mov     r14d, 0FFFFh
0x180004149  cmp     eax, ecx
0x18000414b  mov     rcx, [rsp+78h+arg_20]
0x180004153  cmovnb  r15d, eax
0x180004157  sbb     eax, eax
0x180004159  and     eax, esi
0x18000415b  cmp     edx, 18h
0x18000415e  lea     r13, [rcx+8]
0x180004162  cmovnb  ebp, eax
0x180004165  mov     rax, [rcx+20h]
0x180004169  xor     r8d, r8d
0x18000416c  xor     r12d, r12d
0x18000416f  cmp     rax, r13
0x180004172  jz      loc_18000431B
0x180004178  mov     rcx, [rax+8]
0x18000417c  xor     r9d, r9d
0x18000417f  xor     r11d, r11d
0x180004182  test    rcx, rcx
0x180004185  jz      loc_1800042E8
0x18000418b  mov     ecx, [rcx+8]
0x18000418e  test    ecx, ecx
0x180004190  jz      loc_1800042E8
0x180004196  mov     r10, [rax]
0x180004199  test    r10, r10
0x18000419c  jz      loc_1800042E8
0x1800041a2  mov     edx, [r10]
0x1800041a5  cmp     edx, r14d
0x1800041a8  ja      short loc_1800041B0
0x1800041aa  movzx   r9d, dx
0x1800041ae  jmp     short loc_1800041B3
0x1800041b0  mov     r9d, r14d
0x1800041b3  xor     ecx, ecx
0x1800041b5  mov     ebx, edi
0x1800041b7  cmp     edx, r14d
0x1800041ba  mov     edx, [r10+20h]
0x1800041be  cmovbe  cx, r9w
0x1800041c3  movzx   r11d, cx
0x1800041c7  add     r11d, 28h ; '('
0x1800041cb  cmp     r11d, 28h ; '('
0x1800041cf  cmovnb  ebx, r11d
0x1800041d3  sbb     r9d, r9d
0x1800041d6  and     r9d, esi
0x1800041d9  cmp     edx, r14d
0x1800041dc  ja      short loc_1800041E3
0x1800041de  movzx   esi, dx
0x1800041e1  jmp     short loc_1800041E6
0x1800041e3  mov     esi, r14d
0x1800041e6  xor     ecx, ecx
0x1800041e8  cmp     edx, r14d
0x1800041eb  cmovbe  cx, si
0x1800041ef  mov     esi, edi
0x1800041f1  movzx   edx, cx
0x1800041f4  add     edx, ebx
0x1800041f6  cmp     edx, ebx
0x1800041f8  cmovnb  esi, edx
0x1800041fb  sbb     ecx, ecx
0x1800041fd  and     ecx, 0C0000095h
0x180004203  cmp     r11d, 28h ; '('
0x180004207  mov     r11d, [r10+40h]
0x18000420b  cmovnb  r9d, ecx
0x18000420f  cmp     r11d, r14d
0x180004212  ja      short loc_18000421A
0x180004214  movzx   edx, r11w
0x180004218  jmp     short loc_18000421D
0x18000421a  mov     edx, r14d
0x18000421d  xor     ecx, ecx
0x18000421f  mov     ebx, edi
0x180004221  cmp     r11d, r14d
0x180004224  mov     r11d, [r10+60h]
0x180004228  cmovbe  cx, dx
0x18000422c  movzx   edx, cx
0x18000422f  add     edx, esi
0x180004231  cmp     edx, esi
0x180004233  cmovnb  ebx, edx
0x180004236  sbb     ecx, ecx
0x180004238  and     ecx, 0C0000095h
0x18000423e  test    r9d, r9d
0x180004241  cmovns  r9d, ecx
0x180004245  cmp     r11d, r14d
0x180004248  ja      short loc_180004250
0x18000424a  movzx   edx, r11w
0x18000424e  jmp     short loc_180004253
0x180004250  mov     edx, r14d
0x180004253  xor     ecx, ecx
0x180004255  mov     esi, edi
0x180004257  cmp     r11d, r14d
0x18000425a  mov     r11d, [r10+80h]
0x180004261  cmovbe  cx, dx
0x180004265  movzx   edx, cx
0x180004268  add     edx, ebx
0x18000426a  cmp     edx, ebx
0x18000426c  cmovnb  esi, edx
0x18000426f  sbb     ecx, ecx
0x180004271  and     ecx, 0C0000095h
0x180004277  test    r9d, r9d
0x18000427a  cmovns  r9d, ecx
0x18000427e  cmp     r11d, r14d
0x180004281  ja      short loc_180004289
0x180004283  movzx   edx, r11w
0x180004287  jmp     short loc_18000428C
0x180004289  mov     edx, r14d
0x18000428c  xor     ecx, ecx
0x18000428e  mov     ebx, edi
0x180004290  cmp     r11d, r14d
0x180004293  mov     r11d, [r10+0A0h]
0x18000429a  cmovbe  cx, dx
0x18000429e  movzx   edx, cx
0x1800042a1  add     edx, esi
0x1800042a3  cmp     edx, esi
0x1800042a5  mov     esi, 0C0000095h
0x1800042aa  cmovnb  ebx, edx
0x1800042ad  sbb     ecx, ecx
0x1800042af  and     ecx, esi
0x1800042b1  test    r9d, r9d
0x1800042b4  cmovns  r9d, ecx
0x1800042b8  cmp     r11d, r14d
0x1800042bb  ja      short loc_1800042C3
0x1800042bd  movzx   edx, r11w
0x1800042c1  jmp     short loc_1800042C6
0x1800042c3  mov     edx, r14d
0x1800042c6  xor     ecx, ecx
0x1800042c8  cmp     r11d, r14d
0x1800042cb  mov     r11d, edi
0x1800042ce  cmovbe  cx, dx
0x1800042d2  movzx   edx, cx
0x1800042d5  add     edx, ebx
0x1800042d7  cmp     edx, ebx
0x1800042d9  cmovnb  r11d, edx
0x1800042dd  sbb     ecx, ecx
0x1800042df  and     ecx, esi
0x1800042e1  test    r9d, r9d
0x1800042e4  cmovns  r9d, ecx
0x1800042e8  test    r8d, r8d
0x1800042eb  js      short loc_180004312
0x1800042ed  test    r9d, r9d
0x1800042f0  js      short loc_18000430F
0x1800042f2  lea     edx, [r12+r11]
0x1800042f6  mov     r8d, r12d
0x1800042f9  cmp     edx, r12d
0x1800042fc  mov     ecx, edi
0x1800042fe  cmovnb  ecx, edx
0x180004301  cmp     edx, r8d
0x180004304  mov     r12d, ecx
0x180004307  sbb     r8d, r8d
0x18000430a  and     r8d, esi
0x18000430d  jmp     short loc_180004312
0x18000430f  mov     r8d, r9d
0x180004312  mov     rax, [rax+18h]
0x180004316  jmp     loc_18000416F
0x18000431b  mov     r14d, dword ptr [rsp+78h+Size]
0x180004323  mov     r13, [rsp+78h+arg_8]
0x18000432b  test    ebp, ebp
0x18000432d  js      loc_18000454E
0x180004333  test    r8d, r8d
0x180004336  js      loc_180004551
0x18000433c  lea     eax, [r15+r12]
0x180004340  cmp     eax, r15d
0x180004343  cmovnb  edi, eax
0x180004346  sbb     r8d, r8d
0x180004349  and     r8d, esi
0x18000434c  cmp     eax, r15d
0x18000434f  jb      loc_180004551
0x180004355  xor     r12d, r12d
0x180004358  lea     rcx, [rsp+78h+var_58]
0x18000435d  mov     edx, edi
0x18000435f  mov     [rsp+78h+var_58], r12
0x180004364  mov     [rsp+78h+P], r12
0x180004369  call    ?resize@?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(ulong)
0x18000436e  mov     ebx, eax
0x180004370  test    eax, eax
0x180004372  jns     short loc_180004393
0x180004374  mov     rcx, [rsp+78h+P]; P
0x180004379  test    rcx, rcx
0x18000437c  jz      short loc_18000438C
0x18000437e  xor     edx, edx; Tag
0x180004380  call    cs:__imp_ExFreePoolWithTag
0x180004387  nop     dword ptr [rax+rax+00h]
0x18000438c  mov     eax, ebx
0x18000438e  jmp     loc_180004554
0x180004393  mov     rbx, [rsp+78h+P]
0x180004398  test    rbx, rbx
0x18000439b  jz      loc_180004547
0x1800043a1  mov     esi, dword ptr [rsp+78h+var_58]
0x1800043a5  cmp     esi, 18h
0x1800043a8  jb      loc_180004536
0x1800043ae  mov     [rbx], edi
0x1800043b0  lea     r15, [rbx+18h]
0x1800043b4  mov     edx, 2
0x1800043b9  mov     dword ptr [rbx+4], 1
0x1800043c0  mov     [rbx+8], edx
0x1800043c3  lea     ebp, [rsi-18h]
0x1800043c6  mov     ecx, [r13+0]
0x1800043ca  mov     r8d, 0FFFFh
0x1800043d0  cmp     ecx, edx
0x1800043d2  ja      short loc_1800043D9
0x1800043d4  mov     edi, r12d
0x1800043d7  jmp     short loc_1800043F3
0x1800043d9  cmp     ecx, r8d
0x1800043dc  ja      short loc_1800043E3
0x1800043de  movzx   edx, cx
0x1800043e1  jmp     short loc_1800043E6
0x1800043e3  mov     edx, r8d
0x1800043e6  mov     eax, r12d
0x1800043e9  cmovbe  ax, dx
0x1800043ed  movzx   edi, ax
0x1800043f0  add     edi, 0FFFFFFFEh
0x1800043f3  shr     ecx, 1
0x1800043f5  cmp     ecx, r8d
0x1800043f8  ja      short loc_1800043FF
0x1800043fa  movzx   edx, cx
0x1800043fd  jmp     short loc_180004402
0x1800043ff  mov     edx, r8d
0x180004402  mov     eax, r12d
0x180004405  cmovbe  ax, dx
0x180004409  test    ax, ax
0x18000440c  jz      short loc_180004436
0x18000440e  mov     rdx, [r13+8]; Src
0x180004412  test    rdx, rdx
0x180004415  jz      short loc_180004436
0x180004417  test    edi, edi
0x180004419  jz      short loc_180004436
0x18000441b  cmp     edi, ebp
0x18000441d  ja      loc_180004531
0x180004423  mov     r8d, edi; Size
0x180004426  mov     rcx, r15; void *
0x180004429  call    memmove
0x18000442e  mov     r8d, 0FFFFh
0x180004434  jmp     short loc_180004439
0x180004436  mov     edi, r12d
0x180004439  mov     [rbx+0Ch], r12w
0x18000443e  cmp     edi, r8d
0x180004441  ja      loc_18000452C
0x180004447  mov     [rbx+0Eh], di
0x18000444b  mov     rax, [rsp+78h+Src]
0x180004453  test    rax, rax
0x180004456  jz      short loc_180004485
0x180004458  test    r14d, r14d
0x18000445b  jz      short loc_180004485
0x18000445d  sub     ebp, edi
0x18000445f  cmp     r14d, ebp
0x180004462  ja      loc_180004531
0x180004468  mov     ecx, edi
0x18000446a  mov     r8, r14; Size
0x18000446d  add     rcx, r15; void *
0x180004470  mov     rdx, rax; Src
0x180004473  call    memmove
0x180004478  mov     eax, edi
0x18000447a  mov     r8d, 0FFFFh
0x180004480  add     edi, r14d
0x180004483  jmp     short loc_18000448B
0x180004485  mov     eax, r12d
0x180004488  mov     r14d, r12d
0x18000448b  mov     [rbx+10h], ax
0x18000448f  cmp     r14d, r8d
0x180004492  ja      loc_180004525
0x180004498  mov     [rbx+12h], r14w
0x18000449d  cmp     edi, r8d
0x1800044a0  ja      short loc_180004503
0x1800044a2  mov     rcx, [rsp+78h+arg_20]
0x1800044aa  lea     r9, [rsp+78h+arg_28]
0x1800044b2  mov     [rbx+14h], di
0x1800044b6  sub     esi, edi
0x1800044b8  mov     edx, edi
0x1800044ba  mov     r8d, esi
  ... truncated ...
```
