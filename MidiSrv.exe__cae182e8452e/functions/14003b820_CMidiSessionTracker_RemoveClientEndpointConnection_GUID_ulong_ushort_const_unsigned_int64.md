# CMidiSessionTracker::RemoveClientEndpointConnection(_GUID,ulong,ushort const *,unsigned __int64)

- ea: `0x14003b820`
- end: `0x14003babf`
- name: `?RemoveClientEndpointConnection@CMidiSessionTracker@@UEAAJU_GUID@@KPEBG_K@Z`
- size: `671`
- prototype: `__int64 __fastcall(CMidiSessionTracker *__hidden this, struct _GUID *, unsigned int, const unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task`

## callees

- `0x14000179c`
- `0x1400054c0`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x140013a38`
- `0x14001dccc`
- `0x14001f95c`
- `0x1400360c8`
- `0x14003a5e0`
- `0x14003b820`
- `0x14003c36c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003ba5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003ba97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003ba5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003ba97`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003b94c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003b94c`

## string_xrefs

- `0x14003ba34`: `avcore\midi2\service\exe\midisessiontracker.cpp`
- `0x14003b900`: `CMidiSessionTracker::RemoveClientEndpointConnection`

## pseudocode

```c
__int64 __fastcall CMidiSessionTracker::RemoveClientEndpointConnection(
        CMidiSessionTracker *this,
        struct _GUID *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned __int64 a5)
{
  unsigned __int64 v9; // rbx
  _DWORD *v10; // r10
  const wchar_t *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  struct _RTL_CRITICAL_SECTION *v14; // rdi
  __int64 v15; // rax
  _QWORD *v16; // rsi
  __int64 v17; // rbx
  const wchar_t *v18; // rdx
  size_t v19; // r14
  const wchar_t *v20; // rcx
  size_t v21; // r15
  size_t v22; // r8
  int v23; // eax
  int v26; // [rsp+20h] [rbp-E0h]
  unsigned int v27; // [rsp+30h] [rbp-D0h] BYREF
  CMidiSessionTracker *v28; // [rsp+38h] [rbp-C8h] BYREF
  char v29[32]; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID v30; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v31; // [rsp+70h] [rbp-90h]
  wchar_t *S1[2]; // [rsp+80h] [rbp-80h] BYREF
  size_t v33; // [rsp+90h] [rbp-70h]
  unsigned __int64 v34; // [rsp+98h] [rbp-68h]
  struct _EVENT_DATA_DESCRIPTOR v35; // [rsp+A0h] [rbp-60h] BYREF
  const char *v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+C8h] [rbp-38h]
  CMidiSessionTracker **v38; // [rsp+D0h] [rbp-30h]
  __int64 v39; // [rsp+D8h] [rbp-28h]
  const wchar_t *v40; // [rsp+E0h] [rbp-20h]
  __int64 v41; // [rsp+E8h] [rbp-18h]
  struct _GUID *v42; // [rsp+F0h] [rbp-10h]
  __int64 v43; // [rsp+F8h] [rbp-8h]
  int *v44; // [rsp+100h] [rbp+0h]
  __int64 v45; // [rsp+108h] [rbp+8h]
  const wchar_t *v46; // [rsp+110h] [rbp+10h]
  int v47; // [rsp+118h] [rbp+18h]
  int v48; // [rsp+11Ch] [rbp+1Ch]
  struct _GUID *v49; // [rsp+120h] [rbp+20h]
  __int64 v50; // [rsp+128h] [rbp+28h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v9 = -1;
  v10 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v10 > 4u )
  {
    *(_QWORD *)&v30.Data1 = a5;
    v49 = &v30;
    v27 = a3;
    v28 = this;
    v50 = 8;
    if ( a4 )
    {
      v11 = a4;
      v12 = -1;
      do
        ++v12;
      while ( a4[v12] );
      v13 = 2 * v12 + 2;
    }
    else
    {
      v11 = &S2;
      v13 = 2;
    }
    v47 = v13;
    v46 = v11;
    v44 = (int *)&v27;
    v48 = 0;
    v40 = L"Enter";
    v45 = 4;
    v38 = &v28;
    v42 = a2;
    v36 = "CMidiSessionTracker::RemoveClientEndpointConnection";
    v43 = 16;
    v41 = 12;
    v39 = 8;
    v37 = 52;
    tlgWriteTransfer_EventWriteTransfer((__int64)v10, (unsigned __int8 *)word_14008AE8A, 0, 0, 9u, &v35);
  }
  v14 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v30 = 0;
  v31 = 0;
  do
    ++v9;
  while ( a4[v9] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v30, a4, v9);
  v15 = std::wstring::wstring((__int64)v29, (__int64)&v30);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(S1, v15);
  std::wstring::~wstring((char **)&v30);
  v30 = *a2;
  CMidiSessionTracker::FindSession(this, &v28, &v30, a3);
  if ( v28 != *((CMidiSessionTracker **)this + 4) )
  {
    v16 = (_QWORD *)((char *)v28 + 104);
    std::_Tree<std::_Tmap_traits<std::wstring,MidiSessionConnectionEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiSessionConnectionEntry>>,0>>::_Find_lower_bound<std::wstring>(
      (char *)v28 + 104,
      &v30,
      S1);
    v17 = v31;
    if ( *(_BYTE *)(v31 + 25) )
    {
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x220,
        (unsigned int)"avcore\\midi2\\service\\exe\\midisessiontracker.cpp",
        (const char *)0x80070490LL,
        v26);
      std::wstring::~wstring((char **)S1);
      if ( v14 )
        LeaveCriticalSection(v14);
      return 2147943568LL;
    }
    v18 = (const wchar_t *)(v31 + 32);
    v19 = *(_QWORD *)(v31 + 48);
    if ( *(_QWORD *)(v31 + 56) > 7u )
      v18 = *(const wchar_t **)v18;
    v20 = (const wchar_t *)S1;
    v21 = v33;
    if ( v34 > 7 )
      v20 = S1[0];
    v22 = v33;
    if ( v19 < v33 )
      v22 = *(_QWORD *)(v31 + 48);
    v23 = wmemcmp(v20, v18, v22);
    if ( v23 )
    {
      if ( v23 < 0 )
        goto LABEL_20;
    }
    else if ( v21 < v19 )
    {
      goto LABEL_20;
    }
    if ( v17 == *v16 )
      goto LABEL_20;
    if ( (*(_WORD *)(v17 + 104))-- == 1 )
      std::_Tree<std::_Tmap_traits<std::wstring,MidiSessionConnectionEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiSessionConnectionEntry>>,0>>::erase(
        v16,
        S1);
  }
  std::wstring::~wstring((char **)S1);
  if ( v14 )
    LeaveCriticalSection(v14);
  return 0;
}

```

## disassembly

```asm
0x14003b820  push    rbp
0x14003b822  push    rbx
0x14003b823  push    rsi
0x14003b824  push    rdi
0x14003b825  push    r12
0x14003b827  push    r13
0x14003b829  push    r14
0x14003b82b  push    r15
0x14003b82d  lea     rbp, [rsp-48h]
0x14003b832  sub     rsp, 148h
0x14003b839  mov     rax, cs:__security_cookie
0x14003b840  xor     rax, rsp
0x14003b843  mov     [rbp+80h+var_50], rax
0x14003b847  mov     rsi, r9
0x14003b84a  mov     r15d, r8d
0x14003b84d  mov     r12, rdx
0x14003b850  mov     r14, rcx
0x14003b853  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003b858  xor     r13d, r13d
0x14003b85b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14003b85f  mov     r10, [rax+8]
0x14003b863  mov     eax, [r10]
0x14003b866  cmp     eax, 4
0x14003b869  jbe     loc_14003B945
0x14003b86f  mov     rax, [rbp+80h+arg_20]
0x14003b876  mov     qword ptr [rsp+180h+var_120], rax
0x14003b87b  lea     rax, [rsp+180h+var_120]
0x14003b880  mov     [rbp+80h+var_60], rax
0x14003b884  mov     [rsp+180h+var_150], r15d
0x14003b889  mov     [rsp+180h+var_148], r14
0x14003b88e  mov     [rbp+80h+var_58], 8
0x14003b896  test    rsi, rsi
0x14003b899  jz      short loc_14003B8B4
0x14003b89b  mov     rcx, rsi
0x14003b89e  mov     rax, rbx
0x14003b8a1  inc     rax
0x14003b8a4  cmp     [rsi+rax*2], r13w
0x14003b8a9  jnz     short loc_14003B8A1
0x14003b8ab  lea     eax, ds:2[rax*2]
0x14003b8b2  jmp     short loc_14003B8C0
0x14003b8b4  lea     rcx, S2
0x14003b8bb  mov     eax, 2
0x14003b8c0  mov     [rbp+80h+var_68], eax
0x14003b8c3  lea     rdx, word_14008AE8A
0x14003b8ca  lea     rax, [rsp+180h+var_150]
0x14003b8cf  mov     [rbp+80h+var_70], rcx
0x14003b8d3  mov     [rbp+80h+var_80], rax
0x14003b8d7  xor     r9d, r9d
0x14003b8da  lea     rax, aEnter; "Enter"
0x14003b8e1  mov     [rbp+80h+var_64], r13d
0x14003b8e5  mov     [rbp+80h+var_A0], rax
0x14003b8e9  xor     r8d, r8d
0x14003b8ec  lea     rax, [rsp+180h+var_148]
0x14003b8f1  mov     [rbp+80h+var_78], 4
0x14003b8f9  mov     [rbp+80h+var_B0], rax
0x14003b8fd  mov     rcx, r10
0x14003b900  lea     rax, aCmidisessiontr_10; "CMidiSessionTracker::RemoveClientEndpoi"...
0x14003b907  mov     [rbp+80h+var_90], r12
0x14003b90b  mov     [rbp+80h+var_C0], rax
0x14003b90f  lea     rax, [rbp+80h+var_E0]
0x14003b913  mov     [rsp+180h+var_158], rax
0x14003b918  mov     [rsp+180h+var_160], 9; int
0x14003b920  mov     [rbp+80h+var_88], 10h
0x14003b928  mov     [rbp+80h+var_98], 0Ch
0x14003b930  mov     [rbp+80h+var_A8], 8
0x14003b938  mov     [rbp+80h+var_B8], 34h ; '4'
0x14003b940  call    _tlgWriteTransfer_EventWriteTransfer
0x14003b945  lea     rdi, [r14+30h]
0x14003b949  mov     rcx, rdi; lpCriticalSection
0x14003b94c  call    cs:__imp_EnterCriticalSection
0x14003b952  xorps   xmm0, xmm0
0x14003b955  xorps   xmm1, xmm1
0x14003b958  movups  [rsp+180h+var_120], xmm0
0x14003b95d  movdqu  [rsp+180h+var_110], xmm1
0x14003b963  inc     rbx
0x14003b966  cmp     [rsi+rbx*2], r13w
0x14003b96b  jnz     short loc_14003B963
0x14003b96d  mov     r8, rbx
0x14003b970  lea     rcx, [rsp+180h+var_120]
0x14003b975  mov     rdx, rsi
0x14003b978  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003b97d  lea     rdx, [rsp+180h+var_120]
0x14003b982  lea     rcx, [rsp+180h+var_140]
0x14003b987  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14003b98c  mov     rdx, rax
0x14003b98f  lea     rcx, [rbp+80h+S1]
0x14003b993  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x14003b998  lea     rcx, [rsp+180h+var_120]; void *
0x14003b99d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003b9a2  movups  xmm0, xmmword ptr [r12]
0x14003b9a7  mov     r9d, r15d
0x14003b9aa  lea     r8, [rsp+180h+var_120]
0x14003b9af  lea     rdx, [rsp+180h+var_148]
0x14003b9b4  mov     rcx, r14
0x14003b9b7  movdqu  [rsp+180h+var_120], xmm0
0x14003b9bd  call    ?FindSession@CMidiSessionTracker@@AEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UMidiSessionEntry@@@std@@@std@@@std@@U_GUID@@K@Z; CMidiSessionTracker::FindSession(_GUID,ulong)
0x14003b9c2  mov     rax, [rsp+180h+var_148]
0x14003b9c7  cmp     rax, [r14+20h]
0x14003b9cb  jz      loc_14003BA86
0x14003b9d1  lea     rsi, [rax+68h]
0x14003b9d5  mov     rcx, rsi
0x14003b9d8  lea     r8, [rbp+80h+S1]
0x14003b9dc  lea     rdx, [rsp+180h+var_120]
0x14003b9e1  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,MidiSessionConnectionEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiSessionConnectionEntry>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x14003b9e6  mov     rbx, qword ptr [rsp+180h+var_110]
0x14003b9eb  cmp     [rbx+19h], r13b
0x14003b9ef  jnz     short loc_14003BA2D
0x14003b9f1  lea     rdx, [rbx+20h]
0x14003b9f5  cmp     qword ptr [rdx+18h], 7
0x14003b9fa  mov     r14, [rdx+10h]
0x14003b9fe  jbe     short loc_14003BA03
0x14003ba00  mov     rdx, [rdx]; S2
0x14003ba03  cmp     [rbp+80h+var_E8], 7
0x14003ba08  lea     rcx, [rbp+80h+S1]
0x14003ba0c  mov     r15, [rbp+80h+var_F0]
0x14003ba10  cmova   rcx, [rbp+80h+S1]; S1
0x14003ba15  mov     r8, r15
0x14003ba18  cmp     r14, r15
0x14003ba1b  cmovb   r8, r14; N
0x14003ba1f  call    wmemcmp
0x14003ba24  test    eax, eax
0x14003ba26  jnz     short loc_14003BA68
0x14003ba28  cmp     r15, r14
0x14003ba2b  jnb     short loc_14003BA6A
0x14003ba2d  mov     rcx, [rbp+88h]; this
0x14003ba34  lea     r8, aAvcoreMidi2Ser_5; "avcore\\midi2\\service\\exe\\midisessio"...
0x14003ba3b  mov     ebx, 80070490h
0x14003ba40  mov     edx, 220h; void *
0x14003ba45  mov     r9d, ebx; char *
0x14003ba48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003ba4d  lea     rcx, [rbp+80h+S1]; void *
0x14003ba51  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003ba56  test    rdi, rdi
0x14003ba59  jz      short loc_14003BA64
0x14003ba5b  mov     rcx, rdi; lpCriticalSection
0x14003ba5e  call    cs:__imp_LeaveCriticalSection
0x14003ba64  mov     eax, ebx
0x14003ba66  jmp     short loc_14003BA9F
0x14003ba68  js      short loc_14003BA2D
0x14003ba6a  cmp     rbx, [rsi]
0x14003ba6d  jz      short loc_14003BA2D
0x14003ba6f  mov     eax, 0FFFFh
0x14003ba74  add     [rbx+68h], ax
0x14003ba78  jnz     short loc_14003BA86
0x14003ba7a  lea     rdx, [rbp+80h+S1]
0x14003ba7e  mov     rcx, rsi
0x14003ba81  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,MidiSessionConnectionEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiSessionConnectionEntry>>,0>>::erase(std::wstring const &)
0x14003ba86  lea     rcx, [rbp+80h+S1]; void *
0x14003ba8a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003ba8f  test    rdi, rdi
0x14003ba92  jz      short loc_14003BA9D
0x14003ba94  mov     rcx, rdi; lpCriticalSection
0x14003ba97  call    cs:__imp_LeaveCriticalSection
0x14003ba9d  xor     eax, eax
0x14003ba9f  mov     rcx, [rbp+80h+var_50]
0x14003baa3  xor     rcx, rsp; StackCookie
0x14003baa6  call    __security_check_cookie
0x14003baab  add     rsp, 148h
0x14003bab2  pop     r15
0x14003bab4  pop     r14
0x14003bab6  pop     r13
0x14003bab8  pop     r12
0x14003baba  pop     rdi
0x14003babb  pop     rsi
0x14003babc  pop     rbx
0x14003babd  pop     rbp
0x14003babe  retn
```
