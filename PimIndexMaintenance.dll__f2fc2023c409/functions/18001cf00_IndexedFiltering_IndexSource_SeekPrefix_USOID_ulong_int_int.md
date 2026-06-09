# IndexedFiltering::IndexSource::SeekPrefix(USOID *,ulong *,int *,int *)

- ea: `0x18001cf00`
- end: `0x18001d1e3`
- name: `?SeekPrefix@IndexSource@IndexedFiltering@@UEAAJPEAUUSOID@@PEAKPEAH2@Z`
- size: `739`
- prototype: `__int64 __fastcall(IndexedFiltering::IndexSource *__hidden this, struct USOID *, unsigned int *, int *, int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, installer_update`

## callees

- `0x1800086a0`
- `0x18000d578`
- `0x18000e670`
- `0x1800124a8`
- `0x180012618`
- `0x1800173c4`
- `0x180017638`
- `0x180017b04`
- `0x18001cb30`
- `0x18001cf00`
- `0x18001d584`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x18001d06b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexsource.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexSource::SeekPrefix(
        IndexedFiltering::IndexSource *this,
        struct USOID *a2,
        unsigned int *a3,
        int *a4,
        int *a5)
{
  int v9; // eax
  __int64 v10; // r8
  unsigned int v11; // ebx
  __int64 v12; // r8
  _WORD *v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r10
  bool v17; // zf
  JET_COLUMNID v18; // ecx
  int Next; // eax
  __int64 v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  unsigned int v25; // eax
  unsigned int v27; // [rsp+20h] [rbp-B1h]
  __int64 v28; // [rsp+38h] [rbp-99h]
  __int64 v29; // [rsp+40h] [rbp-91h]
  int v30; // [rsp+50h] [rbp-81h] BYREF
  unsigned int v31; // [rsp+54h] [rbp-7Dh] BYREF
  void *v32[4]; // [rsp+58h] [rbp-79h] BYREF
  JET_RETRIEVECOLUMN v33; // [rsp+78h] [rbp-59h] BYREF
  void *v34[4]; // [rsp+A8h] [rbp-29h] BYREF
  __int64 v35; // [rsp+C8h] [rbp-9h] BYREF
  int v36; // [rsp+D0h] [rbp-1h]

  v9 = ESESession::OpenTable(*((_QWORD *)this + 12), *((_DWORD *)this + 23));
  v11 = v9;
  if ( v9 < 0 )
  {
    Log_HREvent_7((unsigned int)v9, 1, v10, 574);
    return v11;
  }
  while ( 1 )
  {
    *a5 = 0;
    v30 = 0;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v32);
    v13 = (_WORD *)*((_QWORD *)this + 4);
    if ( !v13 || !*v13 )
    {
      v11 = -2147024809;
      v21 = 583;
      goto LABEL_34;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v32,
                             v13) )
    {
      v11 = -2147024882;
      v21 = 585;
LABEL_34:
      v23 = v11;
      v22 = 0;
      goto LABEL_35;
    }
    v15 = *((int *)this + 23);
    v16 = *((_QWORD *)this + 12);
    memset(&v33, 0, sizeof(v33));
    v31 = 0;
    v17 = *((_DWORD *)this + 20) == 0;
    v18 = *(_DWORD *)(*(_QWORD *)(v16 + 48 * v15 + 120) + 8LL);
    v33.pvData = &v31;
    v33.columnid = v18;
    v33.cbData = 4;
    v33.itagSequence = 1;
    if ( v17 )
    {
      Next = ESESession::FindNext(v16, v15, &v33, v14, &v30);
      v11 = Next;
      if ( Next >= 0 )
        goto LABEL_10;
      v21 = 620;
LABEL_18:
      v22 = 1;
      v23 = (unsigned int)Next;
LABEL_35:
      Log_HREvent_7(v23, v22, v12, v21);
      goto LABEL_36;
    }
    Next = ESESession::FindFirst(
             v16,
             v15,
             (__int64)v32[0],
             &v33,
             v27,
             v32[0],
             2 * (((char *)v32[1] - (char *)v32[0]) >> 1),
             v28,
             v29,
             &v30);
    v11 = Next;
    if ( Next < 0 )
    {
      v21 = 610;
      goto LABEL_18;
    }
    *((_DWORD *)this + 20) = 0;
LABEL_10:
    if ( v30 )
    {
      *a5 = 1;
      v11 = 0;
      goto LABEL_36;
    }
    if ( v33.cbActual != v33.cbData )
      Log_AssertionEvent(
        v20,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexsource.cpp",
        629);
    if ( !*((_QWORD *)this + 5) )
      goto LABEL_22;
    v35 = 0;
    v36 = 0;
    Next = CreateAggregateOLITEMIDFromContactId(v31, (struct OLITEMID *)&v35);
    v11 = Next;
    if ( Next < 0 )
    {
      v21 = 636;
      goto LABEL_18;
    }
    Next = (*(__int64 (__fastcall **)(_QWORD, __int64 *, unsigned int *))(**((_QWORD **)this + 5) + 40LL))(
             *((_QWORD *)this + 5),
             &v35,
             a3);
    v11 = Next;
    if ( Next != -2147023728 )
      break;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v32);
  }
  if ( Next < 0 )
  {
    v21 = 646;
    goto LABEL_18;
  }
LABEL_22:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v34);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v34,
                           *((_QWORD *)this + 4)) )
  {
    v11 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, v24, 653);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v34);
LABEL_36:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v32);
    return v11;
  }
  if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
         v34,
         L"ss") != -1
    || utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
         v34,
         &dword_1800278BC) != -1 )
  {
    *((_DWORD *)this + 22) = 1;
  }
  if ( a2 )
  {
    v25 = v31;
    *(_QWORD *)a2 = 0;
    *((_DWORD *)a2 + 2) = v25;
  }
  *a4 = *((_DWORD *)this + 22);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v34);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v32);
  return 0;
}

```

## disassembly

```asm
0x18001cf00  push    rbp
0x18001cf02  push    rbx
0x18001cf03  push    rsi
0x18001cf04  push    rdi
0x18001cf05  push    r12
0x18001cf07  push    r13
0x18001cf09  push    r14
0x18001cf0b  push    r15
0x18001cf0d  lea     rbp, [rsp-17h]
0x18001cf12  sub     rsp, 0E8h
0x18001cf19  mov     rax, cs:__security_cookie
0x18001cf20  xor     rax, rsp
0x18001cf23  mov     [rbp+4Fh+var_48], rax
0x18001cf27  mov     r15, [rbp+4Fh+arg_20]
0x18001cf2b  mov     r14, rdx
0x18001cf2e  mov     edx, [rcx+5Ch]
0x18001cf31  mov     rsi, rcx
0x18001cf34  mov     rcx, [rcx+60h]
0x18001cf38  mov     r12, r9
0x18001cf3b  mov     r13, r8
0x18001cf3e  call    ?OpenTable@ESESession@@QEAAJW4_INDEXTABLE_ID@@@Z; ESESession::OpenTable(_INDEXTABLE_ID)
0x18001cf43  mov     ebx, eax
0x18001cf45  test    eax, eax
0x18001cf47  jns     short loc_18001CF60
0x18001cf49  mov     edx, 1
0x18001cf4e  mov     r9d, 23Eh
0x18001cf54  mov     ecx, eax
0x18001cf56  call    Log_HREvent_7
0x18001cf5b  jmp     loc_18001D1C1
0x18001cf60  mov     edi, 1
0x18001cf65  lea     rcx, [rbp+4Fh+var_C8]
0x18001cf69  mov     dword ptr [r15], 0
0x18001cf70  mov     [rsp+120h+var_D0], 0
0x18001cf78  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001cf7d  mov     rdx, [rsi+20h]
0x18001cf81  test    rdx, rdx
0x18001cf84  jz      loc_18001D1A4
0x18001cf8a  xor     eax, eax
0x18001cf8c  cmp     ax, [rdx]
0x18001cf8f  jz      loc_18001D1A4
0x18001cf95  lea     rcx, [rbp+4Fh+var_C8]
0x18001cf99  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18001cf9e  test    al, al
0x18001cfa0  jz      loc_18001D197
0x18001cfa6  movsxd  rdx, dword ptr [rsi+5Ch]
0x18001cfaa  xorps   xmm0, xmm0
0x18001cfad  mov     r10, [rsi+60h]
0x18001cfb1  movups  [rbp+4Fh+var_A8], xmm0
0x18001cfb5  mov     [rbp+4Fh+var_CC], 0
0x18001cfbc  movups  [rbp+4Fh+var_98], xmm0
0x18001cfc0  lea     rax, [rdx+rdx*2]
0x18001cfc4  add     rax, rax
0x18001cfc7  cmp     dword ptr [rsi+50h], 0
0x18001cfcb  movups  [rbp+4Fh+var_88], xmm0
0x18001cfcf  mov     rax, [r10+rax*8+78h]
0x18001cfd4  mov     ecx, [rax+8]
0x18001cfd7  lea     rax, [rbp+4Fh+var_CC]
0x18001cfdb  mov     qword ptr [rbp+4Fh+var_A8+8], rax
0x18001cfdf  mov     dword ptr [rbp+4Fh+var_A8], ecx
0x18001cfe2  mov     dword ptr [rbp+4Fh+var_98], 4
0x18001cfe9  mov     dword ptr [rbp+4Fh+var_88], edi
0x18001cfec  jz      short loc_18001D032
0x18001cfee  mov     r8, [rbp+4Fh+var_C8]
0x18001cff2  lea     rcx, [rsp+120h+var_D0]
0x18001cff7  mov     rax, [rbp+4Fh+var_C0]
0x18001cffb  lea     r9, [rbp+4Fh+var_A8]
0x18001cfff  mov     [rsp+120h+var_D8], rcx
0x18001d004  sub     rax, r8
0x18001d007  sar     rax, 1
0x18001d00a  mov     rcx, r10
0x18001d00d  add     rax, rax
0x18001d010  mov     [rsp+120h+var_F0], rax
0x18001d015  mov     [rsp+120h+var_F8], r8
0x18001d01a  call    ?FindFirst@ESESession@@QEAAJW4_INDEXTABLE_ID@@PEBDPEAUJET_RETRIEVECOLUMN@@KPEAX_KHKPEAH@Z; ESESession::FindFirst(_INDEXTABLE_ID,char const *,JET_RETRIEVECOLUMN *,ulong,void *,unsigned __int64,int,ulong,int *)
0x18001d01f  mov     ebx, eax
0x18001d021  test    eax, eax
0x18001d023  js      loc_18001D0C7
0x18001d029  mov     dword ptr [rsi+50h], 0
0x18001d030  jmp     short loc_18001D052
0x18001d032  lea     rax, [rsp+120h+var_D0]
0x18001d037  mov     rcx, r10
0x18001d03a  lea     r8, [rbp+4Fh+var_A8]
0x18001d03e  mov     [rsp+120h+var_100], rax
0x18001d043  call    ?FindNext@ESESession@@QEAAJW4_INDEXTABLE_ID@@PEAUJET_RETRIEVECOLUMN@@KPEAH@Z; ESESession::FindNext(_INDEXTABLE_ID,JET_RETRIEVECOLUMN *,ulong,int *)
0x18001d048  mov     ebx, eax
0x18001d04a  test    eax, eax
0x18001d04c  js      loc_18001D18C
0x18001d052  cmp     [rsp+120h+var_D0], 0
0x18001d057  jnz     loc_18001D185
0x18001d05d  mov     eax, dword ptr [rbp+4Fh+var_98]
0x18001d060  cmp     dword ptr [rbp+4Fh+var_98+4], eax
0x18001d063  jz      short loc_18001D077
0x18001d065  mov     r8d, 275h
0x18001d06b  lea     rdx, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001d072  call    Log_AssertionEvent
0x18001d077  cmp     qword ptr [rsi+28h], 0
0x18001d07c  jz      short loc_18001D0EA
0x18001d07e  mov     ecx, [rbp+4Fh+var_CC]; unsigned int
0x18001d081  lea     rdx, [rbp+4Fh+var_58]; struct OLITEMID *
0x18001d085  xor     eax, eax
0x18001d087  mov     [rbp+4Fh+var_58], rax
0x18001d08b  mov     [rbp+4Fh+var_50], eax
0x18001d08e  call    ?CreateAggregateOLITEMIDFromContactId@@YAJKPEAUOLITEMID@@@Z; CreateAggregateOLITEMIDFromContactId(ulong,OLITEMID *)
0x18001d093  mov     ebx, eax
0x18001d095  test    eax, eax
0x18001d097  js      short loc_18001D0E2
0x18001d099  mov     rcx, [rsi+28h]
0x18001d09d  lea     rdx, [rbp+4Fh+var_58]
0x18001d0a1  mov     r8, r13
0x18001d0a4  mov     rax, [rcx]
0x18001d0a7  mov     rax, [rax+28h]
0x18001d0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0b0  mov     ebx, eax
0x18001d0b2  cmp     eax, 80070490h
0x18001d0b7  jnz     short loc_18001D0D6
0x18001d0b9  lea     rcx, [rbp+4Fh+var_C8]
0x18001d0bd  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001d0c2  jmp     loc_18001CF65
0x18001d0c7  mov     r9d, 262h
0x18001d0cd  mov     edx, edi
0x18001d0cf  mov     ecx, eax
0x18001d0d1  jmp     loc_18001D1B3
0x18001d0d6  test    eax, eax
0x18001d0d8  jns     short loc_18001D0EA
0x18001d0da  mov     r9d, 286h
0x18001d0e0  jmp     short loc_18001D0CD
0x18001d0e2  mov     r9d, 27Ch
0x18001d0e8  jmp     short loc_18001D0CD
0x18001d0ea  lea     rcx, [rbp+4Fh+var_78]
0x18001d0ee  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001d0f3  mov     rdx, [rsi+20h]
0x18001d0f7  lea     rcx, [rbp+4Fh+var_78]
0x18001d0fb  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18001d100  test    al, al
0x18001d102  jnz     short loc_18001D126
0x18001d104  mov     ebx, 8007000Eh
0x18001d109  xor     edx, edx
0x18001d10b  mov     ecx, ebx
0x18001d10d  mov     r9d, 28Dh
0x18001d113  call    Log_HREvent_7
0x18001d118  lea     rcx, [rbp+4Fh+var_78]
0x18001d11c  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001d121  jmp     loc_18001D1B8
0x18001d126  lea     rdx, aSs; "ss"
0x18001d12d  lea     rcx, [rbp+4Fh+var_78]
0x18001d131  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18001d136  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d13a  jnz     short loc_18001D152
0x18001d13c  lea     rdx, dword_1800278BC
0x18001d143  lea     rcx, [rbp+4Fh+var_78]
0x18001d147  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18001d14c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d150  jz      short loc_18001D155
0x18001d152  mov     [rsi+58h], edi
0x18001d155  test    r14, r14
0x18001d158  jz      short loc_18001D168
0x18001d15a  mov     eax, [rbp+4Fh+var_CC]
0x18001d15d  mov     qword ptr [r14], 0
0x18001d164  mov     [r14+8], eax
0x18001d168  mov     eax, [rsi+58h]
0x18001d16b  lea     rcx, [rbp+4Fh+var_78]
0x18001d16f  mov     [r12], eax
0x18001d173  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001d178  lea     rcx, [rbp+4Fh+var_C8]
0x18001d17c  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001d181  xor     eax, eax
0x18001d183  jmp     short loc_18001D1C3
0x18001d185  mov     [r15], edi
0x18001d188  xor     ebx, ebx
0x18001d18a  jmp     short loc_18001D1B8
0x18001d18c  mov     r9d, 26Ch
0x18001d192  jmp     loc_18001D0CD
0x18001d197  mov     ebx, 8007000Eh
0x18001d19c  mov     r9d, 249h
0x18001d1a2  jmp     short loc_18001D1AF
0x18001d1a4  mov     ebx, 80070057h
0x18001d1a9  mov     r9d, 247h
0x18001d1af  mov     ecx, ebx
0x18001d1b1  xor     edx, edx
0x18001d1b3  call    Log_HREvent_7
0x18001d1b8  lea     rcx, [rbp+4Fh+var_C8]
0x18001d1bc  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001d1c1  mov     eax, ebx
0x18001d1c3  mov     rcx, [rbp+4Fh+var_48]
0x18001d1c7  xor     rcx, rsp; StackCookie
0x18001d1ca  call    __security_check_cookie
0x18001d1cf  add     rsp, 0E8h
0x18001d1d6  pop     r15
0x18001d1d8  pop     r14
0x18001d1da  pop     r13
0x18001d1dc  pop     r12
0x18001d1de  pop     rdi
0x18001d1df  pop     rsi
0x18001d1e0  pop     rbx
0x18001d1e1  pop     rbp
0x18001d1e2  retn
```
