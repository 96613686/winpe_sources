# RedistributableMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x180028330`
- end: `0x1800286be`
- name: `?RedistributableMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `910`
- prototype: `__int64 __fastcall(int *, void *, struct _DB *, unsigned int, unsigned int, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001cf0`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000e428`
- `0x180026790`
- `0x180026920`
- `0x180026f78`
- `0x180027b94`
- `0x180028330`
- `0x1800430f8`
- `0x1800475fc`
- `0x1800514a8`
- `0x1800543c0`
- `0x18005ec2c`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18002837d`
- `KERNEL32!GetTickCount64` at `0x18002864c`
- `KERNEL32!GetTickCount64` at `0x18002837d`
- `KERNEL32!GetTickCount64` at `0x18002864c`

## string_xrefs

- `0x1800283a2`: `RedistributableMatchingPlugin, Parent Tag %d, TAG_BACKUP_APPLICATION expected`
- `0x1800283c6`: `RedistributableMatchingPlugin`
- `0x1800284dc`: `RedistributableMatchingPlugin`
- `0x180028529`: `RedistributableMatchingPlugin`
- `0x18002867f`: `RedistributableMatchingPlugin`
- `0x1800283b9`: `RedistributableMatchingPlugin, Context is NULL`
- `0x1800284cf`: `RedistributableMatchingPlugin started, ARP registry name: %ws, publisher %ws`
- `0x18002851c`: `Failed to parse Registry Key String. [0x%x]`
- `0x18002866e`: `RedistributableMatchingPlugin Matched = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall RedistributableMatchingPlugin(
        int *a1,
        void *a2,
        struct _DB *a3,
        unsigned int a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        _QWORD *a7)
{
  ULONGLONG TickCount64; // r15
  int v11; // eax
  const char *v12; // r9
  __int64 v13; // r8
  const OLECHAR *v14; // rdi
  const OLECHAR *v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // r8
  __int128 *v18; // rcx
  __int128 *v19; // rax
  __int64 v20; // rax
  int v21; // eax
  const struct VSDependenciesHelper *SingletonInstance; // rax
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // r8
  __int64 v27; // [rsp+20h] [rbp-1A8h]
  _QWORD v28[6]; // [rsp+30h] [rbp-198h] BYREF
  _BYTE v29[32]; // [rsp+60h] [rbp-168h] BYREF
  _BYTE v30[32]; // [rsp+80h] [rbp-148h] BYREF
  _BYTE v31[24]; // [rsp+A0h] [rbp-128h] BYREF
  _BYTE v32[16]; // [rsp+B8h] [rbp-110h] BYREF
  _BYTE v33[48]; // [rsp+C8h] [rbp-100h] BYREF
  _BYTE v34[16]; // [rsp+F8h] [rbp-D0h] BYREF
  _BYTE v35[40]; // [rsp+108h] [rbp-C0h] BYREF
  __int128 v36; // [rsp+130h] [rbp-98h] BYREF
  __int128 v37; // [rsp+140h] [rbp-88h]
  __int128 v38; // [rsp+150h] [rbp-78h] BYREF
  __int128 v39; // [rsp+160h] [rbp-68h]
  _OWORD v40[2]; // [rsp+170h] [rbp-58h] BYREF

  v28[4] = -2;
  v28[2] = a1;
  *a1 = 0;
  TickCount64 = GetTickCount64();
  v28[1] = TickCount64;
  LOWORD(v11) = SdbGetTagFromTagID(a3, a4);
  if ( (_WORD)v11 != 28757 )
  {
    v11 = (unsigned __int16)v11;
    v12 = "RedistributableMatchingPlugin, Parent Tag %d, TAG_BACKUP_APPLICATION expected";
    v13 = 158;
LABEL_20:
    LODWORD(v27) = v11;
    AslLogCallPrintf(3, "RedistributableMatchingPlugin", v13, v12, v27);
    return 1;
  }
  if ( a7 )
  {
    v28[0] = 0;
    v14 = &psz;
    v15 = &psz;
    if ( a7[6] )
      v15 = (const OLECHAR *)a7[6];
    v38 = 0;
    v39 = 0;
    v16 = -1;
    v17 = -1;
    do
      ++v17;
    while ( v15[v17] );
    std::wstring::_Construct<1,unsigned short const *>(&v38, v15, v17);
    memset(v40, 0, sizeof(v40));
    std::wstring::_Construct<1,unsigned short const *>(v40, &psz, 0);
    if ( a7[2] )
      v14 = (const OLECHAR *)a7[2];
    v36 = 0;
    v37 = 0;
    do
      ++v16;
    while ( v14[v16] );
    std::wstring::_Construct<1,unsigned short const *>(&v36, v14, v16);
    v18 = &v36;
    if ( *((_QWORD *)&v37 + 1) > 7u )
      v18 = (__int128 *)v36;
    v19 = &v38;
    if ( *((_QWORD *)&v39 + 1) > 7u )
      v19 = (__int128 *)v38;
    AslLogCallPrintf(
      3,
      "RedistributableMatchingPlugin",
      175,
      "RedistributableMatchingPlugin started, ARP registry name: %ws, publisher %ws",
      v19,
      v18);
    v20 = std::wstring::wstring(v29, &v38);
    v21 = AppCompatUtility::ParseRegistryKeyString(v28, v40, v20);
    if ( v21 )
    {
      AslLogCallPrintf(1, "RedistributableMatchingPlugin", 179, "Failed to parse Registry Key String. [0x%x]", v21);
      std::wstring::~wstring(&v36);
      std::wstring::~wstring(v40);
      std::wstring::~wstring(&v38);
      return 1;
    }
    SingletonInstance = VSDependenciesHelper::GetSingletonInstance();
    VSDependenciesHelper::VSDependenciesHelper((VSDependenciesHelper *)v31, SingletonInstance);
    v28[3] = v29;
    v24 = std::wstring::wstring(v29, &v36);
    v25 = std::wstring::wstring(v30, v40);
    *a1 = IsRedistributable(v31, v28[0], v25, v24);
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(v35);
    std::list<std::wstring>::~list<std::wstring>(v34);
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(v33);
    std::list<std::wstring>::~list<std::wstring>(v32);
    std::list<std::wstring>::~list<std::wstring>(v31);
    std::wstring::~wstring(&v36);
    std::wstring::~wstring(v40);
    std::wstring::~wstring(&v38);
    v26 = (unsigned int)GetTickCount64() - (unsigned int)TickCount64;
    AslTelemetryTrackMetric(P, "RedistributableMatching_Ms", v26);
    v11 = *a1;
    v12 = "RedistributableMatchingPlugin Matched = %d";
    v13 = 192;
    goto LABEL_20;
  }
  AslLogCallPrintf(3, "RedistributableMatchingPlugin", 164, "RedistributableMatchingPlugin, Context is NULL");
  return 1;
}

```

## disassembly

```asm
0x180028330  mov     rax, rsp
0x180028333  push    rsi
0x180028334  push    rdi
0x180028335  push    r12
0x180028337  push    r14
0x180028339  push    r15
0x18002833b  sub     rsp, 1A0h
0x180028342  mov     [rsp+1C8h+var_178], 0FFFFFFFFFFFFFFFEh
0x18002834b  mov     [rax+10h], rbx
0x18002834f  mov     rax, cs:__security_cookie
0x180028356  xor     rax, rsp
0x180028359  mov     [rsp+1C8h+var_38], rax
0x180028361  mov     edi, r9d
0x180028364  mov     rbx, r8
0x180028367  mov     r14, rcx
0x18002836a  mov     [rsp+1C8h+var_188], rcx
0x18002836f  mov     rsi, [rsp+1C8h+arg_30]
0x180028377  xor     r12d, r12d
0x18002837a  mov     [rcx], r12d
0x18002837d  call    cs:__imp_GetTickCount64
0x180028383  mov     r15, rax
0x180028386  mov     [rsp+1C8h+var_190], rax
0x18002838b  mov     edx, edi
0x18002838d  mov     rcx, rbx
0x180028390  call    SdbGetTagFromTagID
0x180028395  mov     ecx, 7055h
0x18002839a  cmp     ax, cx
0x18002839d  jz      short loc_1800283B4
0x18002839f  movzx   eax, ax
0x1800283a2  lea     r9, aRedistributabl_3; "RedistributableMatchingPlugin, Parent T"...
0x1800283a9  mov     r8d, 9Eh
0x1800283af  jmp     loc_18002867B
0x1800283b4  test    rsi, rsi
0x1800283b7  jnz     short loc_1800283DA
0x1800283b9  lea     r9, aRedistributabl; "RedistributableMatchingPlugin, Context "...
0x1800283c0  mov     r8d, 0A4h
0x1800283c6  lea     rdx, aRedistributabl_1; "RedistributableMatchingPlugin"
0x1800283cd  lea     ecx, [rsi+3]
0x1800283d0  call    AslLogCallPrintf
0x1800283d5  jmp     loc_180028690
0x1800283da  mov     [rsp+1C8h+var_198], r12
0x1800283df  lea     rdi, psz
0x1800283e6  mov     rdx, rdi
0x1800283e9  cmp     [rsi+30h], r12
0x1800283ed  cmovnz  rdx, [rsi+30h]
0x1800283f2  xorps   xmm0, xmm0
0x1800283f5  movups  [rsp+1C8h+var_78], xmm0
0x1800283fd  xorps   xmm1, xmm1
0x180028400  movdqu  [rsp+1C8h+var_68], xmm1
0x180028409  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002840d  mov     r8, rbx
0x180028410  inc     r8
0x180028413  cmp     [rdx+r8*2], r12w
0x180028418  jnz     short loc_180028410
0x18002841a  lea     rcx, [rsp+1C8h+var_78]
0x180028422  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180028427  nop
0x180028428  xorps   xmm0, xmm0
0x18002842b  movups  [rsp+1C8h+var_58], xmm0
0x180028433  xorps   xmm1, xmm1
0x180028436  movdqu  [rsp+1C8h+var_48], xmm1
0x18002843f  xor     r8d, r8d
0x180028442  mov     rdx, rdi
0x180028445  lea     rcx, [rsp+1C8h+var_58]
0x18002844d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180028452  nop
0x180028453  cmp     [rsi+10h], r12
0x180028457  cmovnz  rdi, [rsi+10h]
0x18002845c  xorps   xmm0, xmm0
0x18002845f  movups  [rsp+1C8h+var_98], xmm0
0x180028467  xorps   xmm1, xmm1
0x18002846a  movdqu  [rsp+1C8h+var_88], xmm1
0x180028473  inc     rbx
0x180028476  cmp     [rdi+rbx*2], r12w
0x18002847b  jnz     short loc_180028473
0x18002847d  mov     r8, rbx
0x180028480  mov     rdx, rdi
0x180028483  lea     rcx, [rsp+1C8h+var_98]
0x18002848b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180028490  nop
0x180028491  lea     rcx, [rsp+1C8h+var_98]
0x180028499  cmp     qword ptr [rsp+1C8h+var_88+8], 7
0x1800284a2  cmova   rcx, qword ptr [rsp+1C8h+var_98]
0x1800284ab  lea     rax, [rsp+1C8h+var_78]
0x1800284b3  cmp     qword ptr [rsp+1C8h+var_68+8], 7
0x1800284bc  cmova   rax, qword ptr [rsp+1C8h+var_78]
0x1800284c5  mov     [rsp+1C8h+var_1A0], rcx
0x1800284ca  mov     [rsp+1C8h+var_1A8], rax
0x1800284cf  lea     r9, aRedistributabl_2; "RedistributableMatchingPlugin started, "...
0x1800284d6  mov     r8d, 0AFh
0x1800284dc  lea     rdx, aRedistributabl_1; "RedistributableMatchingPlugin"
0x1800284e3  mov     ecx, 3
0x1800284e8  call    AslLogCallPrintf
0x1800284ed  lea     rdx, [rsp+1C8h+var_78]
0x1800284f5  lea     rcx, [rsp+1C8h+var_168]
0x1800284fa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800284ff  mov     r8, rax
0x180028502  lea     rdx, [rsp+1C8h+var_58]
0x18002850a  lea     rcx, [rsp+1C8h+var_198]
0x18002850f  call    ?ParseRegistryKeyString@AppCompatUtility@@YAJPEAPEAUHKEY__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V34@@Z; AppCompatUtility::ParseRegistryKeyString(HKEY__ * *,std::wstring &,std::wstring)
0x180028514  test    eax, eax
0x180028516  jz      short loc_18002856E
0x180028518  mov     dword ptr [rsp+1C8h+var_1A8], eax
0x18002851c  lea     r9, aFailedToParseR_0; "Failed to parse Registry Key String. [0"...
0x180028523  mov     r8d, 0B3h
0x180028529  lea     rdx, aRedistributabl_1; "RedistributableMatchingPlugin"
0x180028530  mov     ecx, 1
0x180028535  call    AslLogCallPrintf
0x18002853a  nop
0x18002853b  lea     rcx, [rsp+1C8h+var_98]; void *
0x180028543  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028548  nop
0x180028549  lea     rcx, [rsp+1C8h+var_58]; void *
0x180028551  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028556  nop
0x180028557  lea     rcx, [rsp+1C8h+var_78]; void *
0x18002855f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028564  mov     eax, 1
0x180028569  jmp     loc_180028695
0x18002856e  call    ?GetSingletonInstance@VSDependenciesHelper@@SAAEAV1@XZ; VSDependenciesHelper::GetSingletonInstance(void)
0x180028573  mov     rdx, rax; struct VSDependenciesHelper *
0x180028576  lea     rcx, [rsp+1C8h+var_128]; this
0x18002857e  call    ??0VSDependenciesHelper@@QEAA@AEBV0@@Z; VSDependenciesHelper::VSDependenciesHelper(VSDependenciesHelper const &)
0x180028583  nop
0x180028584  lea     rax, [rsp+1C8h+var_168]
0x180028589  mov     [rsp+1C8h+var_180], rax
0x18002858e  lea     rdx, [rsp+1C8h+var_98]
0x180028596  lea     rcx, [rsp+1C8h+var_168]
0x18002859b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800285a0  mov     rbx, rax
0x1800285a3  lea     rdx, [rsp+1C8h+var_58]
0x1800285ab  lea     rcx, [rsp+1C8h+var_148]
0x1800285b3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800285b8  nop
0x1800285b9  mov     r9, rbx
0x1800285bc  mov     r8, rax
0x1800285bf  mov     rdx, [rsp+1C8h+var_198]
0x1800285c4  lea     rcx, [rsp+1C8h+var_128]
0x1800285cc  call    ?IsRedistributable@@YAHAEAVVSDependenciesHelper@@QEAUHKEY__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; IsRedistributable(VSDependenciesHelper &,HKEY__ * const,std::wstring,std::wstring)
0x1800285d1  mov     [r14], eax
0x1800285d4  lea     rcx, [rsp+1C8h+var_C0]
0x1800285dc  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(void)
0x1800285e1  lea     rcx, [rsp+1C8h+var_D0]
0x1800285e9  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x1800285ee  lea     rcx, [rsp+1C8h+var_100]
0x1800285f6  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(void)
0x1800285fb  lea     rcx, [rsp+1C8h+var_110]
0x180028603  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x180028608  lea     rcx, [rsp+1C8h+var_128]
0x180028610  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x180028615  nop
0x180028616  lea     rcx, [rsp+1C8h+var_98]; void *
0x18002861e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028623  nop
0x180028624  lea     rcx, [rsp+1C8h+var_58]; void *
0x18002862c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028631  nop
0x180028632  lea     rcx, [rsp+1C8h+var_78]; void *
0x18002863a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002863f  nop
0x180028640  jmp     short loc_18002864C
0x180028642  mov     r15, [rsp+1C8h+var_190]
0x180028647  mov     r14, [rsp+1C8h+var_188]
0x18002864c  call    cs:__imp_GetTickCount64
0x180028652  sub     eax, r15d
0x180028655  mov     r8d, eax
0x180028658  lea     rdx, aRedistributabl_0; "RedistributableMatching_Ms"
0x18002865f  mov     rcx, cs:P
0x180028666  call    AslTelemetryTrackMetric
0x18002866b  mov     eax, [r14]
0x18002866e  lea     r9, aRedistributabl_5; "RedistributableMatchingPlugin Matched ="...
0x180028675  mov     r8d, 0C0h
0x18002867b  mov     dword ptr [rsp+1C8h+var_1A8], eax
0x18002867f  lea     rdx, aRedistributabl_1; "RedistributableMatchingPlugin"
0x180028686  mov     ecx, 3
0x18002868b  call    AslLogCallPrintf
0x180028690  mov     eax, 1
0x180028695  mov     rcx, [rsp+1C8h+var_38]
0x18002869d  xor     rcx, rsp; StackCookie
0x1800286a0  call    __security_check_cookie
0x1800286a5  mov     rbx, [rsp+1C8h+arg_8]
0x1800286ad  add     rsp, 1A0h
0x1800286b4  pop     r15
0x1800286b6  pop     r14
0x1800286b8  pop     r12
0x1800286ba  pop     rdi
0x1800286bb  pop     rsi
0x1800286bc  retn
```
