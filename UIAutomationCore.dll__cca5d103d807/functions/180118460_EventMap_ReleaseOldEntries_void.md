# EventMap::ReleaseOldEntries(void)

- ea: `0x180118460`
- end: `0x18011891d`
- name: `?ReleaseOldEntries@EventMap@@QEAAXXZ`
- size: `1213`
- prototype: `void __fastcall(EventMap *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180118450`

## callees

- `0x18002f580`
- `0x180065704`
- `0x180118460`
- `0x1801e8344`
- `0x1801e8350`
- `0x1801e83c4`
- `0x1801e88a0`
- `0x1801ef098`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801184a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801184a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180118670`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180118852`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180118670`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180118852`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180118477`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180118477`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180118907`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180118907`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180118862`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180118862`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801188c4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801188c4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180118895`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180118895`

## string_xrefs

- `0x18011883d`: `onecore\windows\accessibletech\uiautomationcore\SmartPointers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall EventMap::ReleaseOldEntries(EventMap *this)
{
  ULONGLONG v2; // rdi
  unsigned int v3; // r13d
  int v4; // ebp
  signed int i; // edx
  ULONGLONG v6; // r8
  ULONGLONG v7; // r8
  ULONGLONG v8; // r8
  ULONGLONG v9; // r8
  ULONGLONG v10; // r8
  ULONGLONG v11; // r8
  ULONGLONG v12; // r8
  ULONGLONG v13; // r8
  ULONGLONG v14; // r8
  ULONGLONG v15; // rcx
  unsigned __int64 v16; // rax
  bool v17; // cf
  unsigned __int64 v18; // rax
  _QWORD *v19; // rax
  char *v20; // r15
  unsigned int v21; // r12d
  unsigned int j; // esi
  char *v23; // r14
  ULONGLONG v24; // rax
  unsigned __int64 v25; // rcx
  void *v26; // rcx
  __int64 v27; // rcx
  HRESULT v28; // edi
  EventMap *v29; // rcx
  unsigned int k; // ebx
  void *v31; // rdx
  int ppv; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  struct IGlobalInterfaceTable *v34; // [rsp+88h] [rbp+10h] BYREF
  _QWORD *v35; // [rsp+90h] [rbp+18h]

  v2 = GetTickCount64() - 60000;
  v34 = (struct IGlobalInterfaceTable *)&EventMap::_lock;
  EnterCriticalSection(&EventMap::_lock);
  v3 = 0;
  v4 = 0;
  for ( i = 0; (unsigned int)i < 0x64; i += 10 )
  {
    v6 = *((_QWORD *)this + 8 * (__int64)i + 2);
    if ( v6 )
    {
      if ( v6 < v2 )
        ++v3;
      else
        ++v4;
    }
    v7 = *((_QWORD *)this + 8 * (__int64)i + 10);
    if ( v7 )
    {
      if ( v7 < v2 )
        ++v3;
      else
        ++v4;
    }
    v8 = *((_QWORD *)this + 8 * (__int64)i + 18);
    if ( v8 )
    {
      if ( v8 < v2 )
        ++v3;
      else
        ++v4;
    }
    v9 = *((_QWORD *)this + 8 * (__int64)i + 26);
    if ( v9 )
    {
      if ( v9 < v2 )
        ++v3;
      else
        ++v4;
    }
    v10 = *((_QWORD *)this + 8 * (__int64)i + 34);
    if ( v10 )
    {
      if ( v10 < v2 )
        ++v3;
      else
        ++v4;
    }
    v11 = *((_QWORD *)this + 8 * (__int64)i + 42);
    if ( v11 )
    {
      if ( v11 < v2 )
        ++v3;
      else
        ++v4;
    }
    v12 = *((_QWORD *)this + 8 * (__int64)i + 50);
    if ( v12 )
    {
      if ( v12 < v2 )
        ++v3;
      else
        ++v4;
    }
    v13 = *((_QWORD *)this + 8 * (__int64)i + 58);
    if ( v13 )
    {
      if ( v13 < v2 )
        ++v3;
      else
        ++v4;
    }
    v14 = *((_QWORD *)this + 8 * (__int64)i + 66);
    if ( v14 )
    {
      if ( v14 < v2 )
        ++v3;
      else
        ++v4;
    }
    v15 = *((_QWORD *)this + 8 * (__int64)i + 74);
    if ( v15 )
    {
      if ( v15 < v2 )
        ++v3;
      else
        ++v4;
    }
  }
  v16 = (unsigned __int64)v3 << 6;
  if ( !is_mul_ok(v3, 0x40u) )
    v16 = -1;
  v17 = __CFADD__(v16, 8);
  v18 = v16 + 8;
  if ( v17 )
    v18 = -1;
  v19 = operator new[](v18, (const struct std::nothrow_t *)std::nothrow);
  v35 = v19;
  if ( v19 )
  {
    *v19 = v3;
    v20 = (char *)(v19 + 1);
    `eh vector constructor iterator'(
      v19 + 1,
      0x40u,
      v3,
      (void (*)(void *))EventMap::EventMapEntry::EventMapEntry,
      (void (*)(void *))EventMap::EventMapEntry::~EventMapEntry);
  }
  else
  {
    v20 = 0;
  }
  if ( v20 )
  {
    v21 = 0;
    for ( j = 0; j < 0x64; ++j )
    {
      v23 = (char *)this + 64 * (__int64)(int)j;
      v24 = *((_QWORD *)v23 + 2);
      if ( v24 && v24 < v2 )
      {
        v25 = (unsigned __int64)v21 << 6;
        *(_QWORD *)&v20[v25 + 40] = *((_QWORD *)v23 + 5);
        *(_DWORD *)&v20[v25 + 56] = *((_DWORD *)v23 + 14);
        *(_DWORD *)&v20[v25 + 60] = *((_DWORD *)v23 + 15);
        ++v21;
        *(_QWORD *)v23 = 0;
        *((_DWORD *)v23 + 2) = 0;
        *((_QWORD *)v23 + 2) = 0;
        *((_QWORD *)v23 + 5) = 0;
        *((_QWORD *)v23 + 7) = 0;
        v26 = (void *)*((_QWORD *)v23 + 4);
        if ( v26 )
          operator delete(v26);
        *((_DWORD *)v23 + 6) = 0;
        *((_QWORD *)v23 + 4) = 0;
        v27 = *((_QWORD *)v23 + 6);
        if ( v27 )
        {
          *((_QWORD *)v23 + 6) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
      }
    }
    if ( !v4 )
    {
      v31 = (void *)*((_QWORD *)this + 801);
      if ( v31 )
      {
        DeleteTimerQueueTimer(0, v31, 0);
        *((_QWORD *)this + 801) = 0;
      }
    }
    LeaveCriticalSection(&EventMap::_lock);
    if ( v3 )
    {
      v28 = CoInitializeEx(0, 0);
      v34 = 0;
      CoCreateInstance(
        &CLSID_StdGlobalInterfaceTable,
        0,
        1u,
        &GUID_00000146_0000_0000_c000_000000000046,
        (LPVOID *)&v34);
      for ( k = 0; k < v3; ++k )
        EventMap::ReleaseOneEntry(v29, (struct EventMapEntry *)&v20[64 * (unsigned __int64)k], v34, 1);
      if ( v28 >= 0 )
        CoUninitialize();
      if ( v34 )
        ((void (__fastcall *)(struct IGlobalInterfaceTable *))v34->lpVtbl->Release)(v34);
    }
    `eh vector destructor iterator'(
      v20,
      0x40u,
      *((_QWORD *)v20 - 1),
      (void (*)(void *))EventMap::EventMapEntry::~EventMapEntry);
    operator delete[](v20 - 8);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FE,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SmartPointers.h",
      (const char *)0x8007000ELL,
      ppv);
    LeaveCriticalSection(&EventMap::_lock);
  }
}

```

## disassembly

```asm
0x180118460  mov     [rsp+arg_0], rbx
0x180118465  push    rbp
0x180118466  push    rsi
0x180118467  push    rdi
0x180118468  push    r12
0x18011846a  push    r13
0x18011846c  push    r14
0x18011846e  push    r15
0x180118470  sub     rsp, 40h
0x180118474  mov     rbx, rcx
0x180118477  call    cs:__imp_GetTickCount64
0x18011847d  lea     rdi, [rax-0EA60h]
0x180118484  xor     r14d, r14d
0x180118487  mov     [rsp+78h+var_48], r14d
0x18011848c  mov     [rsp+78h+var_40], r14
0x180118491  lea     r12, ?_lock@EventMap@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION EventMap::_lock
0x180118498  mov     [rsp+78h+arg_8], r12
0x1801184a0  mov     rcx, r12; lpCriticalSection
0x1801184a3  call    cs:__imp_EnterCriticalSection
0x1801184a9  nop
0x1801184aa  mov     r13d, r14d
0x1801184ad  mov     ebp, r14d
0x1801184b0  mov     edx, r14d
0x1801184b3  nop     dword ptr [rax+00h]
0x1801184b7  nop     word ptr [rax+rax+00000000h]
0x1801184c0  movsxd  rax, edx
0x1801184c3  mov     rcx, rax
0x1801184c6  shl     rcx, 6
0x1801184ca  mov     r8, [rcx+rbx+10h]
0x1801184cf  test    r8, r8
0x1801184d2  jnz     loc_1801186C5
0x1801184d8  mov     rcx, rax
0x1801184db  shl     rcx, 6
0x1801184df  mov     r8, [rcx+rbx+50h]
0x1801184e4  test    r8, r8
0x1801184e7  jnz     loc_1801186D5
0x1801184ed  mov     rcx, rax
0x1801184f0  shl     rcx, 6
0x1801184f4  mov     r8, [rcx+rbx+90h]
0x1801184fc  test    r8, r8
0x1801184ff  jnz     loc_1801186E5
0x180118505  mov     rcx, rax
0x180118508  shl     rcx, 6
0x18011850c  mov     r8, [rcx+rbx+0D0h]
0x180118514  test    r8, r8
0x180118517  jnz     loc_1801186F5
0x18011851d  mov     rcx, rax
0x180118520  shl     rcx, 6
0x180118524  mov     r8, [rcx+rbx+110h]
0x18011852c  test    r8, r8
0x18011852f  jnz     loc_180118705
0x180118535  mov     rcx, rax
0x180118538  shl     rcx, 6
0x18011853c  mov     r8, [rcx+rbx+150h]
0x180118544  test    r8, r8
0x180118547  jnz     loc_180118715
0x18011854d  mov     rcx, rax
0x180118550  shl     rcx, 6
0x180118554  mov     r8, [rcx+rbx+190h]
0x18011855c  test    r8, r8
0x18011855f  jnz     loc_180118725
0x180118565  mov     rcx, rax
0x180118568  shl     rcx, 6
0x18011856c  mov     r8, [rcx+rbx+1D0h]
0x180118574  test    r8, r8
0x180118577  jnz     loc_180118735
0x18011857d  mov     rcx, rax
0x180118580  shl     rcx, 6
0x180118584  mov     r8, [rcx+rbx+210h]
0x18011858c  test    r8, r8
0x18011858f  jnz     loc_180118745
0x180118595  shl     rax, 6
0x180118599  mov     rcx, [rax+rbx+250h]
0x1801185a1  test    rcx, rcx
0x1801185a4  jnz     loc_180118755
0x1801185aa  add     edx, 0Ah
0x1801185ad  cmp     edx, 64h ; 'd'
0x1801185b0  jb      loc_1801184C0
0x1801185b6  mov     esi, r13d
0x1801185b9  mov     eax, 40h ; '@'
0x1801185be  mul     rsi
0x1801185c1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1801185c8  cmovb   rax, rcx
0x1801185cc  add     rax, 8
0x1801185d0  cmovb   rax, rcx
0x1801185d4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801185db  mov     rcx, rax; unsigned __int64
0x1801185de  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801185e3  mov     [rsp+78h+arg_10], rax
0x1801185eb  lea     rcx, ??1EventMapEntry@EventMap@@QEAA@XZ; EventMap::EventMapEntry::~EventMapEntry(void)
0x1801185f2  test    rax, rax
0x1801185f5  jz      loc_1801188EA
0x1801185fb  mov     [rax], rsi
0x1801185fe  lea     r15, [rax+8]
0x180118602  mov     qword ptr [rsp+78h+ppv], rcx; int
0x180118607  lea     r9, ??0EventMapEntry@EventMap@@QEAA@XZ; void (*)(void *)
0x18011860e  mov     r8d, esi; unsigned __int64
0x180118611  mov     edx, 40h ; '@'; unsigned __int64
0x180118616  mov     rcx, r15; void *
0x180118619  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18011861e  nop
0x18011861f  mov     [rsp+78h+var_40], r15
0x180118624  test    r15, r15
0x180118627  jz      loc_180118832
0x18011862d  mov     [rsp+78h+var_48], r13d
0x180118632  xor     edx, edx
0x180118634  mov     r12d, edx
0x180118637  mov     esi, edx
0x180118639  nop     dword ptr [rax+00000000h]
0x180118640  movsxd  r14, esi
0x180118643  shl     r14, 6
0x180118647  add     r14, rbx
0x18011864a  mov     rax, [r14+10h]
0x18011864e  test    rax, rax
0x180118651  jnz     loc_180118765
0x180118657  inc     esi
0x180118659  cmp     esi, 64h ; 'd'
0x18011865c  jb      short loc_180118640
0x18011865e  test    ebp, ebp
0x180118660  jz      loc_1801188F2
0x180118666  xor     r14d, r14d
0x180118669  lea     rcx, ?_lock@EventMap@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180118670  call    cs:__imp_LeaveCriticalSection
0x180118676  test    r13d, r13d
0x180118679  jnz     loc_18011885E
0x18011867f  lea     r9, ??1EventMapEntry@EventMap@@QEAA@XZ; void (*)(void *)
0x180118686  mov     r8, [r15-8]; unsigned __int64
0x18011868a  mov     edx, 40h ; '@'; unsigned __int64
0x18011868f  mov     rcx, r15; void *
0x180118692  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180118697  mov     rdx, [r15-8]
0x18011869b  shl     rdx, 6
0x18011869f  add     rdx, 8
0x1801186a3  lea     rcx, [r15-8]; Block
0x1801186a7  call    ??_V@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete[](void *,std::nothrow_t const &)
0x1801186ac  nop
0x1801186ad  mov     rbx, [rsp+78h+arg_0]
0x1801186b5  add     rsp, 40h
0x1801186b9  pop     r15
0x1801186bb  pop     r14
0x1801186bd  pop     r13
0x1801186bf  pop     r12
0x1801186c1  pop     rdi
0x1801186c2  pop     rsi
0x1801186c3  pop     rbp
0x1801186c4  retn
0x1801186c5  cmp     r8, rdi
0x1801186c8  jb      loc_1801187E2
0x1801186ce  inc     ebp
0x1801186d0  jmp     loc_1801184D8
0x1801186d5  cmp     r8, rdi
0x1801186d8  jb      loc_1801187EA
0x1801186de  inc     ebp
0x1801186e0  jmp     loc_1801184ED
0x1801186e5  cmp     r8, rdi
0x1801186e8  jb      loc_1801187F2
0x1801186ee  inc     ebp
0x1801186f0  jmp     loc_180118505
0x1801186f5  cmp     r8, rdi
0x1801186f8  jb      loc_1801187FA
0x1801186fe  inc     ebp
0x180118700  jmp     loc_18011851D
0x180118705  cmp     r8, rdi
0x180118708  jb      loc_180118802
0x18011870e  inc     ebp
0x180118710  jmp     loc_180118535
0x180118715  cmp     r8, rdi
0x180118718  jb      loc_18011880A
0x18011871e  inc     ebp
0x180118720  jmp     loc_18011854D
0x180118725  cmp     r8, rdi
0x180118728  jb      loc_180118812
0x18011872e  inc     ebp
0x180118730  jmp     loc_180118565
0x180118735  cmp     r8, rdi
0x180118738  jb      loc_18011881A
0x18011873e  inc     ebp
0x180118740  jmp     loc_18011857D
0x180118745  cmp     r8, rdi
0x180118748  jb      loc_180118822
0x18011874e  inc     ebp
0x180118750  jmp     loc_180118595
0x180118755  cmp     rcx, rdi
0x180118758  jb      loc_18011882A
0x18011875e  inc     ebp
0x180118760  jmp     loc_1801185AA
0x180118765  cmp     rax, rdi
0x180118768  jnb     loc_180118657
0x18011876e  mov     ecx, r12d
0x180118771  shl     rcx, 6
0x180118775  mov     rax, [r14+28h]
0x180118779  mov     [rcx+r15+28h], rax
0x18011877e  mov     eax, [r14+38h]
0x180118782  mov     [rcx+r15+38h], eax
0x180118787  mov     eax, [r14+3Ch]
0x18011878b  mov     [rcx+r15+3Ch], eax
0x180118790  inc     r12d
0x180118793  mov     [r14], rdx
0x180118796  mov     [r14+8], edx
0x18011879a  mov     [r14+10h], rdx
0x18011879e  mov     [r14+28h], rdx
0x1801187a2  mov     qword ptr [r14+38h], 0
0x1801187aa  mov     rcx, [r14+20h]; Block
0x1801187ae  test    rcx, rcx
0x1801187b1  jz      short loc_1801187BA
0x1801187b3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801187b8  xor     edx, edx
0x1801187ba  mov     [r14+18h], edx
0x1801187be  mov     [r14+20h], rdx
0x1801187c2  mov     rcx, [r14+30h]
0x1801187c6  test    rcx, rcx
0x1801187c9  jz      short loc_1801187DD
0x1801187cb  mov     [r14+30h], rdx
0x1801187cf  mov     rax, [rcx]
0x1801187d2  mov     rax, [rax+10h]
0x1801187d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801187db  xor     edx, edx
0x1801187dd  jmp     loc_180118657
0x1801187e2  inc     r13d
0x1801187e5  jmp     loc_1801184D8
0x1801187ea  inc     r13d
0x1801187ed  jmp     loc_1801184ED
0x1801187f2  inc     r13d
0x1801187f5  jmp     loc_180118505
0x1801187fa  inc     r13d
0x1801187fd  jmp     loc_18011851D
0x180118802  inc     r13d
0x180118805  jmp     loc_180118535
0x18011880a  inc     r13d
0x18011880d  jmp     loc_18011854D
0x180118812  inc     r13d
0x180118815  jmp     loc_180118565
0x18011881a  inc     r13d
0x18011881d  jmp     loc_18011857D
0x180118822  inc     r13d
0x180118825  jmp     loc_180118595
0x18011882a  inc     r13d
0x18011882d  jmp     loc_1801185AA
0x180118832  mov     rcx, [rsp+78h]; this
0x180118837  mov     r9d, 8007000Eh; char *
0x18011883d  lea     r8, aOnecoreWindows_87; "onecore\\windows\\accessibletech\\uiaut"...
0x180118844  mov     edx, 1FEh; void *
0x180118849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011884e  nop
0x18011884f  mov     rcx, r12; lpCriticalSection
0x180118852  call    cs:__imp_LeaveCriticalSection
0x180118858  nop
0x180118859  jmp     loc_1801186AD
0x18011885e  xor     edx, edx; dwCoInit
0x180118860  xor     ecx, ecx; pvReserved
0x180118862  call    cs:__imp_CoInitializeEx
0x180118868  mov     edi, eax
0x18011886a  mov     [rsp+78h+arg_8], r14
0x180118872  lea     rax, [rsp+78h+arg_8]
0x18011887a  mov     qword ptr [rsp+78h+ppv], rax; ppv
0x18011887f  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180118886  xor     edx, edx; pUnkOuter
0x180118888  mov     r8d, 1; dwClsContext
0x18011888e  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180118895  call    cs:__imp_CoCreateInstance
0x18011889b  mov     ebx, r14d
0x18011889e  xchg    ax, ax
0x1801188a0  mov     edx, ebx
0x1801188a2  shl     rdx, 6
0x1801188a6  add     rdx, r15; struct EventMapEntry *
0x1801188a9  mov     r9b, 1; bool
0x1801188ac  mov     r8, [rsp+78h+arg_8]; struct IGlobalInterfaceTable *
0x1801188b4  call    ?ReleaseOneEntry@EventMap@@AEAAXPEAUEventMapEntry@1@PEAUIGlobalInterfaceTable@@_N@Z; EventMap::ReleaseOneEntry(EventMap::EventMapEntry *,IGlobalInterfaceTable *,bool)
0x1801188b9  inc     ebx
0x1801188bb  cmp     ebx, r13d
0x1801188be  jb      short loc_1801188A0
0x1801188c0  test    edi, edi
0x1801188c2  js      short loc_1801188CB
0x1801188c4  call    cs:__imp_CoUninitialize
0x1801188ca  nop
0x1801188cb  mov     rcx, [rsp+78h+arg_8]
0x1801188d3  test    rcx, rcx
0x1801188d6  jz      short loc_1801188E5
0x1801188d8  mov     rax, [rcx]
0x1801188db  mov     rax, [rax+10h]
0x1801188df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801188e4  nop
0x1801188e5  jmp     loc_18011867F
0x1801188ea  mov     r15, r14
0x1801188ed  jmp     loc_18011861F
0x1801188f2  mov     rdx, [rbx+1908h]; Timer
0x1801188f9  test    rdx, rdx
0x1801188fc  jz      loc_180118666
0x180118902  xor     r8d, r8d; CompletionEvent
0x180118905  xor     ecx, ecx; TimerQueue
0x180118907  call    cs:__imp_DeleteTimerQueueTimer
0x18011890d  xor     r14d, r14d
0x180118910  mov     [rbx+1908h], r14
0x180118917  jmp     loc_180118669
```
