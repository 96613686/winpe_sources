# FSMDeviceWatcher::InternalAddToDeviceList(utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &,ushort const *)

- ea: `0x1800115e0`
- end: `0x180011729`
- name: `?InternalAddToDeviceList@FSMDeviceWatcher@@MEAAJAEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@PEBG@Z`
- size: `329`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x1800060f8`
- `0x180006a98`
- `0x180006d1c`
- `0x18000cffc`
- `0x18000d088`
- `0x1800115e0`
- `0x180017b70`
- `0x180041474`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001167f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001167f`

## pseudocode

```c
__int64 __fastcall FSMDeviceWatcher::InternalAddToDeviceList(__int64 a1, __int64 ***a2, const unsigned __int16 *a3)
{
  int v6; // esi
  __int64 v7; // rdx
  __int64 **v8; // rbx
  __int64 v9; // rdi
  void *v11[4]; // [rsp+30h] [rbp-268h] BYREF
  WCHAR String1[264]; // [rsp+50h] [rbp-248h] BYREF

  memset_0(String1, 0, 0x208u);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v11);
  v6 = FSGetUniqueSymbolicName(a3, String1, 0x104u, 0);
  if ( v6 >= 0 )
  {
    v8 = *a2;
    v9 = -1;
    while ( v8 != (__int64 **)a2 )
    {
      if ( CompareStringOrdinal(String1, -1, (LPCWCH)v8[2], -1, 1) == 2 )
        goto LABEL_14;
      v8 = (__int64 **)*v8;
    }
    do
      ++v9;
    while ( String1[v9] );
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v11,
                             String1,
                             v9)
      || !(unsigned __int8)utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::push_back(
                             a2,
                             v11) )
    {
      v6 = -2147024882;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v7 = 260;
        goto LABEL_13;
      }
    }
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v7 = 259;
LABEL_13:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, a1, v6);
  }
LABEL_14:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v11);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800115e0  mov     [rsp+arg_18], rbx
0x1800115e5  push    rbp
0x1800115e6  push    rsi
0x1800115e7  push    rdi
0x1800115e8  push    r14
0x1800115ea  push    r15
0x1800115ec  sub     rsp, 270h
0x1800115f3  mov     rax, cs:__security_cookie
0x1800115fa  xor     rax, rsp
0x1800115fd  mov     [rsp+298h+var_38], rax
0x180011605  mov     rbx, r8
0x180011608  mov     r14, rdx
0x18001160b  mov     rbp, rcx
0x18001160e  xor     edx, edx; Val
0x180011610  mov     r8d, 208h; Size
0x180011616  lea     rcx, [rsp+298h+String1]; void *
0x18001161b  call    memset_0
0x180011620  lea     rcx, [rsp+298h+var_268]
0x180011625  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001162a  lea     rdx, [rsp+298h+String1]; unsigned __int16 *
0x18001162f  xor     r9d, r9d; unsigned int *
0x180011632  mov     r8d, 104h; unsigned int
0x180011638  mov     rcx, rbx; unsigned __int16 *
0x18001163b  call    ?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z; FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)
0x180011640  xor     r15d, r15d
0x180011643  mov     esi, eax
0x180011645  test    eax, eax
0x180011647  jns     short loc_18001165D
0x180011649  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001164e  cmp     al, 1
0x180011650  jb      loc_1800116F6
0x180011656  mov     edx, 103h
0x18001165b  jmp     short loc_1800116D8
0x18001165d  mov     rbx, [r14]
0x180011660  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011664  cmp     rbx, r14
0x180011667  jz      short loc_18001168F
0x180011669  mov     r8, [rbx+10h]; lpString2
0x18001166d  lea     rcx, [rsp+298h+String1]; lpString1
0x180011672  mov     r9d, edi; cchCount2
0x180011675  mov     [rsp+298h+bIgnoreCase], 1; bIgnoreCase
0x18001167d  mov     edx, edi; cchCount1
0x18001167f  call    cs:__imp_CompareStringOrdinal
0x180011685  cmp     eax, 2
0x180011688  jz      short loc_1800116F6
0x18001168a  mov     rbx, [rbx]
0x18001168d  jmp     short loc_180011664
0x18001168f  lea     rax, [rsp+298h+String1]
0x180011694  inc     rdi
0x180011697  cmp     [rax+rdi*2], r15w
0x18001169c  jnz     short loc_180011694
0x18001169e  mov     r8, rdi
0x1800116a1  lea     rdx, [rsp+298h+String1]
0x1800116a6  lea     rcx, [rsp+298h+var_268]
0x1800116ab  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800116b0  test    al, al
0x1800116b2  jz      short loc_1800116C5
0x1800116b4  lea     rdx, [rsp+298h+var_268]
0x1800116b9  mov     rcx, r14
0x1800116bc  call    ?push_back@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@Z; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::push_back(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x1800116c1  test    al, al
0x1800116c3  jnz     short loc_1800116F6
0x1800116c5  mov     esi, 8007000Eh
0x1800116ca  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800116cf  cmp     al, 1
0x1800116d1  jb      short loc_1800116F6
0x1800116d3  mov     edx, 104h
0x1800116d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116df  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x1800116e6  mov     r9, rbp
0x1800116e9  mov     [rsp+298h+bIgnoreCase], esi
0x1800116ed  mov     rcx, [rcx+10h]
0x1800116f1  call    WPP_SF_qD
0x1800116f6  lea     rcx, [rsp+298h+var_268]
0x1800116fb  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180011700  mov     eax, esi
0x180011702  mov     rcx, [rsp+298h+var_38]
0x18001170a  xor     rcx, rsp; StackCookie
0x18001170d  call    __security_check_cookie
0x180011712  mov     rbx, [rsp+298h+arg_18]
0x18001171a  add     rsp, 270h
0x180011721  pop     r15
0x180011723  pop     r14
0x180011725  pop     rdi
0x180011726  pop     rsi
0x180011727  pop     rbp
0x180011728  retn
```
