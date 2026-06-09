# OfficeAddinMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x18002fdd0`
- end: `0x180030167`
- name: `?OfficeAddinMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `919`
- prototype: `__int64 __fastcall(int *, void *, struct _DB *, unsigned int, unsigned int, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001cf0`
- `0x180002120`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000e428`
- `0x1800265d0`
- `0x180026920`
- `0x180026f78`
- `0x180029198`
- `0x18002f680`
- `0x18002f8c4`
- `0x18002fbd4`
- `0x18002fdd0`
- `0x1800430f8`
- `0x180048a08`
- `0x18004b0d8`
- `0x18004c6a8`
- `0x1800543c0`
- `0x18005ec2c`

## string_xrefs

- `0x18002ff1e`: `Failed to parse Registry Key String. [0x%x]`
- `0x18002fe3e`: `OfficeAddinMatchingPlugin`
- `0x18002fe67`: `OfficeAddinMatchingPlugin`
- `0x18002ff0f`: `OfficeAddinMatchingPlugin`
- `0x18002ff78`: `OfficeAddinMatchingPlugin started, ARP registry name: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall OfficeAddinMatchingPlugin(
        int *a1,
        void *a2,
        struct _DB *a3,
        unsigned int a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        _QWORD *a7)
{
  unsigned __int16 TagFromTagID; // ax
  const OLECHAR *v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rax
  int v14; // eax
  __int128 *v15; // rax
  struct OfficeAddinPathAccessor *SingletonInstance; // rax
  struct OfficeMsiHelper *v17; // rbx
  _QWORD *v18; // r8
  _QWORD **v19; // rdi
  _QWORD *i; // rbx
  _QWORD v21[2]; // [rsp+30h] [rbp-1B8h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-1A8h] BYREF
  int v23; // [rsp+50h] [rbp-198h] BYREF
  _QWORD v24[2]; // [rsp+58h] [rbp-190h] BYREF
  __int64 v25; // [rsp+68h] [rbp-180h] BYREF
  __int128 v26; // [rsp+70h] [rbp-178h]
  __int64 v27; // [rsp+80h] [rbp-168h]
  __int64 v28; // [rsp+88h] [rbp-160h]
  __int64 v29; // [rsp+90h] [rbp-158h]
  void **v30; // [rsp+A0h] [rbp-148h] BYREF
  _BYTE v31[8]; // [rsp+A8h] [rbp-140h] BYREF
  _BYTE v32[16]; // [rsp+B0h] [rbp-138h] BYREF
  _BYTE v33[48]; // [rsp+C0h] [rbp-128h] BYREF
  _BYTE v34[32]; // [rsp+F0h] [rbp-F8h] BYREF
  __int128 v35; // [rsp+110h] [rbp-D8h] BYREF
  __m128i si128; // [rsp+120h] [rbp-C8h]
  _OWORD v37[2]; // [rsp+130h] [rbp-B8h] BYREF
  _BYTE v38[8]; // [rsp+150h] [rbp-98h] BYREF
  _BYTE v39[32]; // [rsp+158h] [rbp-90h] BYREF
  _BYTE v40[32]; // [rsp+178h] [rbp-70h] BYREF
  _BYTE v41[40]; // [rsp+198h] [rbp-50h] BYREF

  v29 = -2;
  *a1 = 0;
  TagFromTagID = SdbGetTagFromTagID(a3, a4);
  if ( TagFromTagID != 28757 )
  {
    AslLogCallPrintf(1, "OfficeAddinMatchingPlugin", 94, "Invalid parent tag id: 0x%x (tag: 0x%x)", a4, TagFromTagID);
    return 1;
  }
  if ( !a7 )
  {
    AslLogCallPrintf(1, "OfficeAddinMatchingPlugin", 100, "Context should not be nullptr.");
    return 1;
  }
  v21[0] = 0;
  v35 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v35) = 0;
  v11 = &psz;
  if ( a7[6] )
    v11 = (const OLECHAR *)a7[6];
  memset(v37, 0, sizeof(v37));
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  std::wstring::_Construct<1,unsigned short const *>(v37, v11, v12);
  v13 = std::wstring::wstring(v34, v37);
  v14 = AppCompatUtility::ParseRegistryKeyString(v21, &v35, v13);
  if ( v14 )
  {
    AslLogCallPrintf(1, "OfficeAddinMatchingPlugin", 114, "Failed to parse Registry Key String. [0x%x]", v14);
    std::wstring::~wstring(v37);
    std::wstring::~wstring(&v35);
    return 1;
  }
  else
  {
    v15 = &v35;
    if ( si128.m128i_i64[1] > 7uLL )
      v15 = (__int128 *)v35;
    AslLogCallPrintf(
      3,
      "OfficeAddinMatchingPlugin",
      117,
      "OfficeAddinMatchingPlugin started, ARP registry name: %ws",
      v15);
    SingletonInstance = OfficeAddinPathAccessor::GetSingletonInstance();
    v30 = &OfficeAddinPathAccessor::`vftable';
    std::unordered_set<std::wstring>::unordered_set<std::wstring>(v31, (char *)SingletonInstance + 8);
    v17 = OfficeMsiHelper::GetSingletonInstance((struct IOfficeAddinPathAccessor *)&v30);
    v22[0] = &OfficeMsiHelper::`vftable';
    v22[1] = *((_QWORD *)v17 + 1);
    v21[1] = &v23;
    v23 = *((_DWORD *)v17 + 4);
    v24[0] = 0;
    v24[1] = 0;
    v18 = operator new(0x48u);
    *v18 = v18;
    v18[1] = v18;
    v24[0] = v18;
    v25 = 0;
    v26 = 0;
    v27 = *((_QWORD *)v17 + 8);
    v28 = *((_QWORD *)v17 + 9);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
      &v25,
      (__int64)(*((_QWORD *)v17 + 6) - *((_QWORD *)v17 + 5)) >> 3,
      v18);
    v19 = (_QWORD **)*((_QWORD *)v17 + 3);
    for ( i = *v19; i != v19; i = (_QWORD *)*i )
      std::_Hash<std::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::emplace<std::pair<std::wstring const,std::vector<std::wstring>> const &>(
        &v23,
        v34,
        i + 2);
    ARPEntry::ARPEntry(v38, v21[0], &v35);
    *a1 = IsOfficeAddin(
            (const struct ARPEntry *)v38,
            (struct IOfficeAddinPathAccessor *)&v30,
            (struct IOfficeMsiHelper *)v22);
    std::wstring::~wstring(v41);
    std::wstring::~wstring(v40);
    std::wstring::~wstring(v39);
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(&v25);
    std::list<std::pair<std::wstring const,std::vector<std::wstring>>>::~list<std::pair<std::wstring const,std::vector<std::wstring>>>(v24);
    v22[0] = &IOfficeMsiHelper::`vftable';
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(v33);
    std::list<std::wstring>::~list<std::wstring>(v32);
    v30 = &IOfficeMsiHelper::`vftable';
    std::wstring::~wstring(v37);
    std::wstring::~wstring(&v35);
    return 1;
  }
}

```

## disassembly

```asm
0x18002fdd0  mov     rax, rsp
0x18002fdd3  push    rsi
0x18002fdd4  push    rdi
0x18002fdd5  push    r14
0x18002fdd7  sub     rsp, 1D0h
0x18002fdde  mov     qword ptr [rax-158h], 0FFFFFFFFFFFFFFFEh
0x18002fde9  mov     [rax+10h], rbx
0x18002fded  mov     rax, cs:__security_cookie
0x18002fdf4  xor     rax, rsp
0x18002fdf7  mov     [rsp+1E8h+var_28], rax
0x18002fdff  mov     edi, r9d
0x18002fe02  mov     rsi, rcx
0x18002fe05  mov     rbx, [rsp+1E8h+arg_30]
0x18002fe0d  xor     r14d, r14d
0x18002fe10  mov     [rcx], r14d
0x18002fe13  mov     edx, r9d
0x18002fe16  mov     rcx, r8
0x18002fe19  call    SdbGetTagFromTagID
0x18002fe1e  mov     ecx, 7055h
0x18002fe23  cmp     ax, cx
0x18002fe26  jz      short loc_18002FE57
0x18002fe28  movzx   eax, ax
0x18002fe2b  mov     [rsp+1E8h+var_1C0], eax
0x18002fe2f  mov     dword ptr [rsp+1E8h+var_1C8], edi
0x18002fe33  lea     r9, aInvalidParentT; "Invalid parent tag id: 0x%x (tag: 0x%x)"
0x18002fe3a  lea     r8d, [r14+5Eh]
0x18002fe3e  lea     rdx, aOfficeaddinmat_2; "OfficeAddinMatchingPlugin"
0x18002fe45  lea     ebx, [r14+1]
0x18002fe49  mov     ecx, ebx
0x18002fe4b  call    AslLogCallPrintf
0x18002fe50  mov     eax, ebx
0x18002fe52  jmp     loc_180030123
0x18002fe57  test    rbx, rbx
0x18002fe5a  jnz     short loc_18002FE7B
0x18002fe5c  lea     r9, aContextShouldN; "Context should not be nullptr."
0x18002fe63  lea     r8d, [rbx+64h]
0x18002fe67  lea     rdx, aOfficeaddinmat_2; "OfficeAddinMatchingPlugin"
0x18002fe6e  lea     ebx, [r8-63h]
0x18002fe72  mov     ecx, ebx
0x18002fe74  call    AslLogCallPrintf
0x18002fe79  jmp     short loc_18002FE50
0x18002fe7b  mov     [rsp+1E8h+var_1B8], r14
0x18002fe80  xorps   xmm0, xmm0
0x18002fe83  movups  [rsp+1E8h+var_D8], xmm0
0x18002fe8b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002fe93  movdqu  [rsp+1E8h+var_C8], xmm1
0x18002fe9c  mov     word ptr [rsp+1E8h+var_D8], r14w
0x18002fea5  lea     rdx, psz
0x18002feac  cmp     [rbx+30h], r14
0x18002feb0  cmovnz  rdx, [rbx+30h]
0x18002feb5  movups  [rsp+1E8h+var_B8], xmm0
0x18002febd  xorps   xmm1, xmm1
0x18002fec0  movdqu  [rsp+1E8h+var_A8], xmm1
0x18002fec9  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002fecd  inc     r8
0x18002fed0  cmp     [rdx+r8*2], r14w
0x18002fed5  jnz     short loc_18002FECD
0x18002fed7  lea     rcx, [rsp+1E8h+var_B8]
0x18002fedf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002fee4  nop
0x18002fee5  lea     rdx, [rsp+1E8h+var_B8]
0x18002feed  lea     rcx, [rsp+1E8h+var_F8]
0x18002fef5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002fefa  mov     r8, rax
0x18002fefd  lea     rdx, [rsp+1E8h+var_D8]
0x18002ff05  lea     rcx, [rsp+1E8h+var_1B8]
0x18002ff0a  call    ?ParseRegistryKeyString@AppCompatUtility@@YAJPEAPEAUHKEY__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V34@@Z; AppCompatUtility::ParseRegistryKeyString(HKEY__ * *,std::wstring &,std::wstring)
0x18002ff0f  lea     rdx, aOfficeaddinmat_2; "OfficeAddinMatchingPlugin"
0x18002ff16  test    eax, eax
0x18002ff18  jz      short loc_18002FF59
0x18002ff1a  mov     dword ptr [rsp+1E8h+var_1C8], eax
0x18002ff1e  lea     r9, aFailedToParseR_0; "Failed to parse Registry Key String. [0"...
0x18002ff25  mov     r8d, 72h ; 'r'
0x18002ff2b  lea     ebx, [r8-71h]
0x18002ff2f  mov     ecx, ebx
0x18002ff31  call    AslLogCallPrintf
0x18002ff36  nop
0x18002ff37  lea     rcx, [rsp+1E8h+var_B8]; void *
0x18002ff3f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ff44  nop
0x18002ff45  lea     rcx, [rsp+1E8h+var_D8]; void *
0x18002ff4d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ff52  mov     eax, ebx
0x18002ff54  jmp     loc_180030123
0x18002ff59  lea     rax, [rsp+1E8h+var_D8]
0x18002ff61  cmp     qword ptr [rsp+1E8h+var_C8+8], 7
0x18002ff6a  cmova   rax, qword ptr [rsp+1E8h+var_D8]
0x18002ff73  mov     [rsp+1E8h+var_1C8], rax
0x18002ff78  lea     r9, aOfficeaddinmat; "OfficeAddinMatchingPlugin started, ARP "...
0x18002ff7f  mov     r8d, 75h ; 'u'
0x18002ff85  lea     ecx, [r8-72h]
0x18002ff89  call    AslLogCallPrintf
0x18002ff8e  call    ?GetSingletonInstance@OfficeAddinPathAccessor@@SAAEAV1@XZ; OfficeAddinPathAccessor::GetSingletonInstance(void)
0x18002ff93  nop
0x18002ff94  lea     rcx, ??_7OfficeAddinPathAccessor@@6B@; const OfficeAddinPathAccessor::`vftable'
0x18002ff9b  mov     [rsp+1E8h+var_148], rcx
0x18002ffa3  lea     rdx, [rax+8]
0x18002ffa7  lea     rcx, [rsp+1E8h+var_140]
0x18002ffaf  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::unordered_set<std::wstring>::unordered_set<std::wstring>(std::unordered_set<std::wstring> const &)
0x18002ffb4  nop
0x18002ffb5  lea     rcx, [rsp+1E8h+var_148]; struct IOfficeAddinPathAccessor *
0x18002ffbd  call    ?GetSingletonInstance@OfficeMsiHelper@@SAAEAV1@AEAVIOfficeAddinPathAccessor@@@Z; OfficeMsiHelper::GetSingletonInstance(IOfficeAddinPathAccessor &)
0x18002ffc2  mov     rbx, rax
0x18002ffc5  lea     rax, ??_7OfficeMsiHelper@@6B@; const OfficeMsiHelper::`vftable'
0x18002ffcc  mov     [rsp+1E8h+var_1A8], rax
0x18002ffd1  mov     rcx, [rbx+8]
0x18002ffd5  mov     [rsp+1E8h+var_1A0], rcx
0x18002ffda  lea     rax, [rsp+1E8h+var_198]
0x18002ffdf  mov     [rsp+1E8h+var_1B0], rax
0x18002ffe4  mov     ecx, [rbx+10h]
0x18002ffe7  mov     [rsp+1E8h+var_198], ecx
0x18002ffeb  mov     [rsp+1E8h+var_190], r14
0x18002fff0  mov     [rsp+1E8h+var_188], r14
0x18002fff5  mov     ecx, 48h ; 'H'; Size
0x18002fffa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ffff  mov     r8, rax
0x180030002  mov     [rax], rax
0x180030005  mov     [rax+8], rax
0x180030009  mov     [rsp+1E8h+var_190], rax
0x18003000e  mov     [rsp+1E8h+var_180], r14
0x180030013  xorps   xmm0, xmm0
0x180030016  movdqa  [rsp+1E8h+var_178], xmm0
0x18003001c  mov     rcx, [rbx+40h]
0x180030020  mov     [rsp+1E8h+var_168], rcx
0x180030028  mov     rax, [rbx+48h]
0x18003002c  mov     [rsp+1E8h+var_160], rax
0x180030034  mov     rdx, [rbx+30h]
0x180030038  sub     rdx, [rbx+28h]
0x18003003c  sar     rdx, 3
0x180030040  lea     rcx, [rsp+1E8h+var_180]
0x180030045  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18003004a  mov     rdi, [rbx+18h]
0x18003004e  mov     rbx, [rdi]
0x180030051  cmp     rbx, rdi
0x180030054  jnz     loc_180030147
0x18003005a  lea     r8, [rsp+1E8h+var_D8]
0x180030062  mov     rdx, [rsp+1E8h+var_1B8]
0x180030067  lea     rcx, [rsp+1E8h+var_98]
0x18003006f  call    ??0ARPEntry@@QEAA@PEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ARPEntry::ARPEntry(HKEY__ *,std::wstring const &)
0x180030074  nop
0x180030075  lea     r8, [rsp+1E8h+var_1A8]; struct IOfficeMsiHelper *
0x18003007a  lea     rdx, [rsp+1E8h+var_148]; struct IOfficeAddinPathAccessor *
0x180030082  lea     rcx, [rsp+1E8h+var_98]; struct ARPEntry *
0x18003008a  call    ?IsOfficeAddin@@YAHAEBUARPEntry@@AEAVIOfficeAddinPathAccessor@@AEAVIOfficeMsiHelper@@@Z; IsOfficeAddin(ARPEntry const &,IOfficeAddinPathAccessor &,IOfficeMsiHelper &)
0x18003008f  mov     [rsi], eax
0x180030091  lea     rcx, [rsp+1E8h+var_50]; void *
0x180030099  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003009e  lea     rcx, [rsp+1E8h+var_70]; void *
0x1800300a6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800300ab  lea     rcx, [rsp+1E8h+var_90]; void *
0x1800300b3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800300b8  nop
0x1800300b9  lea     rcx, [rsp+1E8h+var_180]
0x1800300be  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(void)
0x1800300c3  lea     rcx, [rsp+1E8h+var_190]
0x1800300c8  call    ??1?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring const,std::vector<std::wstring>>>::~list<std::pair<std::wstring const,std::vector<std::wstring>>>(void)
0x1800300cd  lea     rax, ??_7IOfficeMsiHelper@@6B@; const IOfficeMsiHelper::`vftable'
0x1800300d4  mov     [rsp+1E8h+var_1A8], rax
0x1800300d9  lea     rcx, [rsp+1E8h+var_128]
0x1800300e1  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(void)
0x1800300e6  lea     rcx, [rsp+1E8h+var_138]
0x1800300ee  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x1800300f3  lea     rax, ??_7IOfficeMsiHelper@@6B@; const IOfficeMsiHelper::`vftable'
0x1800300fa  mov     [rsp+1E8h+var_148], rax
0x180030102  lea     rcx, [rsp+1E8h+var_B8]; void *
0x18003010a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003010f  nop
0x180030110  lea     rcx, [rsp+1E8h+var_D8]; void *
0x180030118  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003011d  nop
0x18003011e  mov     eax, 1
0x180030123  mov     rcx, [rsp+1E8h+var_28]
0x18003012b  xor     rcx, rsp; StackCookie
0x18003012e  call    __security_check_cookie
0x180030133  mov     rbx, [rsp+1E8h+arg_8]
0x18003013b  add     rsp, 1D0h
0x180030142  pop     r14
0x180030144  pop     rdi
0x180030145  pop     rsi
0x180030146  retn
0x180030147  lea     r8, [rbx+10h]
0x18003014b  lea     rdx, [rsp+1E8h+var_F8]
0x180030153  lea     rcx, [rsp+1E8h+var_198]
0x180030158  call    ??$emplace@AEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@std@@@std@@@std@@_N@1@AEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@1@@Z
0x18003015d  mov     rbx, [rbx]
0x180030160  jmp     loc_180030051
```
