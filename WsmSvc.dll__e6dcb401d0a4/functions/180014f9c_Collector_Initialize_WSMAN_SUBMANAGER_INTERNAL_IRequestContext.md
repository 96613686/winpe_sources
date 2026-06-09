# Collector::Initialize(_WSMAN_SUBMANAGER_INTERNAL *,IRequestContext &)

- ea: `0x180014f9c`
- end: `0x1800152b8`
- name: `?Initialize@Collector@@QEAA_NPEAU_WSMAN_SUBMANAGER_INTERNAL@@AEAVIRequestContext@@@Z`
- size: `796`
- prototype: `bool __fastcall(Collector *__hidden this, struct _WSMAN_SUBMANAGER_INTERNAL *, struct IRequestContext *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180144b44`

## callees

- `0x180008920`
- `0x180014f9c`
- `0x18001648c`
- `0x18003e680`
- `0x1800621e0`
- `0x1800973c0`
- `0x1800f8630`
- `0x1801123e8`
- `0x180121c74`
- `0x180144d24`
- `0x1801c2010`

## import_xrefs

- `msvcrt!rand` at `0x18001507d`
- `msvcrt!rand` at `0x18001507d`
- `msvcrt!srand` at `0x180015077`
- `msvcrt!srand` at `0x180015077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015254`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015211`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001522d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015211`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001522d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001506f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001506f`

## string_xrefs

- `0x18001525d`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall Collector::Initialize(
        Collector *this,
        struct _WSMAN_SUBMANAGER_INTERNAL *a2,
        struct IRequestContext *a3)
{
  char *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // r14
  __int64 v9; // rax
  unsigned int v10; // ebx
  DWORD TickCount; // eax
  unsigned int v12; // ecx
  unsigned __int64 v13; // rcx
  __int64 v14; // rax
  HANDLE EventW; // rax
  HANDLE v16; // rax
  void (__fastcall *v17)(struct IRequestContext *, __int64, const wchar_t *, _QWORD); // rbx
  DWORD LastError; // eax
  __int128 v20; // [rsp+38h] [rbp-18h] BYREF
  __int64 v21; // [rsp+48h] [rbp-8h]
  __int64 v22; // [rsp+80h] [rbp+30h] BYREF
  __int64 *v23; // [rsp+98h] [rbp+48h]

  v6 = (char *)this + 88;
  if ( !(**((unsigned __int8 (__fastcall ***)(char *, struct IRequestContext *))this + 11))((char *)this + 88, a3)
    || !(**((unsigned __int8 (__fastcall ***)(char *, struct IRequestContext *))this + 24))((char *)this + 192, a3) )
  {
    return 0;
  }
  LODWORD(v22) = 0;
  v23 = &v22;
  v7 = WSManMemory::Alloc(24, 0, 0);
  v8 = v7;
  if ( v7 )
    SafeMap_Iterator<ListenerSourceSubscription *,Empty>::SafeMap_Iterator<ListenerSourceSubscription *,Empty>(
      v7,
      (__int64)v6,
      0);
  else
    v8 = 0;
  AutoCleanup<AutoDelete<SafeSet_Iterator<ListenerSourceSubscription *>>,SafeSet_Iterator<ListenerSourceSubscription *> *>::operator=(
    (char *)this + 184,
    v8);
  v9 = *((_QWORD *)this + 23);
  if ( !v9 || !*(_QWORD *)(v9 + 16) )
  {
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a3 + 24LL))(a3);
    return 0;
  }
  v10 = *(_DWORD *)a2 >> 1;
  if ( v10 > 0x384 )
    v10 = 900;
  TickCount = GetTickCount();
  srand(TickCount);
  v12 = *(_DWORD *)a2 + rand() % v10;
  if ( v12 < *(_DWORD *)a2 )
  {
    *((_DWORD *)this + 12) = -1;
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *, int))(*(_QWORD *)a3 + 96LL))(
      a3,
      2147942934LL,
      1077134178,
      L"DWordAdd",
      -2147024362);
    return 0;
  }
  v13 = 1000LL * v12;
  if ( v13 > 0xFFFFFFFF )
  {
    *((_DWORD *)this + 12) = -1;
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *, int))(*(_QWORD *)a3 + 96LL))(
      a3,
      2147942934LL,
      1077134178,
      L"DWordMult",
      -2147024362);
  }
  else
  {
    *((_DWORD *)this + 12) = v13;
  }
  if ( !*((_QWORD *)a2 + 1) )
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a3 + 72LL))(a3, 87);
  *((_QWORD *)this + 7) = CopyString(a3, 458, *((_QWORD *)a2 + 1));
  v14 = CopyString(a3, 459, *((_QWORD *)a2 + 2));
  *((_QWORD *)this + 8) = v14;
  ParseCommaString(a3, (char *)this + 192, v14);
  if ( *((_QWORD *)this + 8) )
  {
    v22 = 0;
    v20 = 0;
    v21 = 0;
    if ( !(unsigned __int8)FindCert((struct _WSMAN_STATUS *)&v20) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_3757a1dee11230fa6624dd120cab9128_Traceguids,
          *((_QWORD *)this + 8),
          SBYTE8(v20));
      (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a3 + 72LL))(a3, DWORD2(v20));
      AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v22);
      return 0;
    }
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v22);
  }
  *((_QWORD *)this + 9) = *((_QWORD *)a2 + 3);
  *((_QWORD *)this + 10) = *((_QWORD *)a2 + 4);
  EventW = CreateEventW(0, 0, 0, 0);
  AutoHandle::operator=((char *)this + 16, EventW);
  v16 = CreateEventW(0, 0, 0, 0);
  AutoHandle::operator=((char *)this + 24, v16);
  if ( !*((_QWORD *)this + 3) || !*((_QWORD *)this + 2) )
  {
    v17 = *(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)a3 + 88LL);
    LastError = GetLastError();
    v17(a3, 1077134176, L"CreateEvent", LastError);
  }
  return (*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a3 + 144LL))(a3) == 1;
}

```

## disassembly

```asm
0x180014f9c  mov     [rsp-28h+arg_8], rbx
0x180014fa1  mov     [rsp-28h+arg_10], rsi
0x180014fa6  push    rbp
0x180014fa7  push    rdi
0x180014fa8  push    r12
0x180014faa  push    r14
0x180014fac  push    r15
0x180014fae  mov     rbp, rsp
0x180014fb1  sub     rsp, 50h
0x180014fb5  mov     rdi, r8
0x180014fb8  mov     r15, rdx
0x180014fbb  mov     rsi, rcx
0x180014fbe  lea     rbx, [rcx+58h]
0x180014fc2  mov     rax, [rbx]
0x180014fc5  mov     rdx, r8
0x180014fc8  mov     rcx, rbx
0x180014fcb  mov     rax, [rax]
0x180014fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fd3  test    al, al
0x180014fd5  jz      loc_18001529D
0x180014fdb  lea     r12, [rsi+0C0h]
0x180014fe2  mov     rax, [r12]
0x180014fe6  mov     rdx, rdi
0x180014fe9  mov     rcx, r12
0x180014fec  mov     rax, [rax]
0x180014fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ff4  test    al, al
0x180014ff6  jz      loc_18001529D
0x180014ffc  mov     dword ptr [rbp+arg_0], 0
0x180015003  lea     rax, [rbp+arg_0]
0x180015007  mov     [rbp+arg_18], rax
0x18001500b  xor     r8d, r8d
0x18001500e  xor     edx, edx
0x180015010  lea     ecx, [rdx+18h]
0x180015013  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180015018  mov     r14, rax
0x18001501b  mov     [rbp+var_20], rax
0x18001501f  test    rax, rax
0x180015022  jz      short loc_180015034
0x180015024  xor     r8d, r8d
0x180015027  mov     rdx, rbx
0x18001502a  mov     rcx, rax
0x18001502d  call    ??0?$SafeMap_Iterator@PEAVListenerSourceSubscription@@UEmpty@@@@QEAA@AEAV?$SafeMap@PEAVListenerSourceSubscription@@UEmpty@@V?$SafeMap_Iterator@PEAVListenerSourceSubscription@@UEmpty@@@@@@_N@Z; SafeMap_Iterator<ListenerSourceSubscription *,Empty>::SafeMap_Iterator<ListenerSourceSubscription *,Empty>(SafeMap<ListenerSourceSubscription *,Empty,SafeMap_Iterator<ListenerSourceSubscription *,Empty>> &,bool)
0x180015032  jmp     short loc_180015037
0x180015034  xor     r14d, r14d
0x180015037  lea     rbx, [rsi+0B8h]
0x18001503e  mov     rdx, r14
0x180015041  mov     rcx, rbx
0x180015044  call    ??4?$AutoCleanup@V?$AutoDelete@V?$SafeSet_Iterator@PEAVListenerSourceSubscription@@@@@@PEAV?$SafeSet_Iterator@PEAVListenerSourceSubscription@@@@@@QEAAAEAV?$AutoDelete@V?$SafeSet_Iterator@PEAVListenerSourceSubscription@@@@@@PEAV?$SafeSet_Iterator@PEAVListenerSourceSubscription@@@@@Z; AutoCleanup<AutoDelete<SafeSet_Iterator<ListenerSourceSubscription *>>,SafeSet_Iterator<ListenerSourceSubscription *> *>::operator=(SafeSet_Iterator<ListenerSourceSubscription *> *)
0x180015049  mov     rax, [rbx]
0x18001504c  test    rax, rax
0x18001504f  jz      loc_18001528E
0x180015055  cmp     qword ptr [rax+10h], 0
0x18001505a  jz      loc_18001528E
0x180015060  mov     ebx, [r15]
0x180015063  shr     ebx, 1
0x180015065  mov     eax, 384h
0x18001506a  cmp     ebx, eax
0x18001506c  cmova   ebx, eax
0x18001506f  call    cs:__imp_GetTickCount
0x180015075  mov     ecx, eax; Seed
0x180015077  call    cs:__imp_srand
0x18001507d  call    cs:__imp_rand
0x180015083  xor     edx, edx
0x180015085  div     ebx
0x180015087  mov     eax, [r15]
0x18001508a  lea     ecx, [rax+rdx]
0x18001508d  cmp     ecx, eax
0x18001508f  jnb     short loc_1800150C6
0x180015091  mov     dword ptr [rsi+30h], 0FFFFFFFFh
0x180015098  mov     rax, [rdi]
0x18001509b  mov     [rsp+50h+var_30], 80070216h
0x1800150a3  lea     r9, aDwordadd; "DWordAdd"
0x1800150aa  mov     edx, 80070216h
0x1800150af  mov     r8d, 4033C362h
0x1800150b5  mov     rcx, rdi
0x1800150b8  mov     rax, [rax+60h]
0x1800150bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150c1  jmp     loc_18001529D
0x1800150c6  mov     eax, ecx
0x1800150c8  imul    rcx, rax, 3E8h
0x1800150cf  mov     eax, 0FFFFFFFFh
0x1800150d4  cmp     rcx, rax
0x1800150d7  ja      short loc_1800150DE
0x1800150d9  mov     [rsi+30h], ecx
0x1800150dc  jmp     short loc_18001510A
0x1800150de  mov     [rsi+30h], eax
0x1800150e1  mov     rax, [rdi]
0x1800150e4  mov     [rsp+50h+var_30], 80070216h
0x1800150ec  lea     r9, aDwordmult; "DWordMult"
0x1800150f3  mov     edx, 80070216h
0x1800150f8  mov     r8d, 4033C362h
0x1800150fe  mov     rcx, rdi
0x180015101  mov     rax, [rax+60h]
0x180015105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001510a  cmp     qword ptr [r15+8], 0
0x18001510f  jnz     short loc_180015125
0x180015111  mov     rax, [rdi]
0x180015114  mov     edx, 57h ; 'W'
0x180015119  mov     rcx, rdi
0x18001511c  mov     rax, [rax+48h]
0x180015120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015125  mov     r8, [r15+8]
0x180015129  mov     edx, 1CAh
0x18001512e  mov     rcx, rdi
0x180015131  call    ?CopyString@@YAPEAGPEAVIRequestContext@@W4CallSiteId@@PEBG@Z; CopyString(IRequestContext *,CallSiteId,ushort const *)
0x180015136  mov     [rsi+38h], rax
0x18001513a  mov     r8, [r15+10h]
0x18001513e  mov     edx, 1CBh
0x180015143  mov     rcx, rdi
0x180015146  call    ?CopyString@@YAPEAGPEAVIRequestContext@@W4CallSiteId@@PEBG@Z; CopyString(IRequestContext *,CallSiteId,ushort const *)
0x18001514b  mov     [rsi+40h], rax
0x18001514f  mov     r8, rax
0x180015152  mov     rdx, r12
0x180015155  mov     rcx, rdi
0x180015158  call    ?ParseCommaString@@YA_NAEAVIRequestContext@@AEAV?$SafeSet@VStringKeyCI@@@@PEAG@Z; ParseCommaString(IRequestContext &,SafeSet<StringKeyCI> &,ushort *)
0x18001515d  cmp     qword ptr [rsi+40h], 0
0x180015162  jz      loc_1800151F7
0x180015168  mov     [rbp+arg_0], 0
0x180015170  xorps   xmm0, xmm0
0x180015173  xor     eax, eax
0x180015175  movups  [rbp+var_18], xmm0
0x180015179  mov     [rbp+var_8], rax
0x18001517d  mov     r8, r12
0x180015180  lea     rdx, [rbp+arg_0]
0x180015184  lea     rcx, [rbp+var_18]; struct _WSMAN_STATUS *
0x180015188  call    FindCert
0x18001518d  test    al, al
0x18001518f  jnz     short loc_1800151EE
0x180015191  lea     rax, WPP_GLOBAL_Control
0x180015198  mov     rcx, cs:WPP_GLOBAL_Control
0x18001519f  cmp     rcx, rax
0x1800151a2  jz      short loc_1800151CD
0x1800151a4  test    dword ptr [rcx+1Ch], 8000h
0x1800151ab  jz      short loc_1800151CD
0x1800151ad  mov     edx, 0Bh
0x1800151b2  mov     eax, dword ptr [rbp+var_18+8]
0x1800151b5  mov     [rsp+50h+var_30], eax
0x1800151b9  mov     r9, [rsi+40h]
0x1800151bd  lea     r8, WPP_3757a1dee11230fa6624dd120cab9128_Traceguids
0x1800151c4  mov     rcx, [rcx+10h]
0x1800151c8  call    WPP_SF_Sd
0x1800151cd  mov     rax, [rdi]
0x1800151d0  mov     edx, dword ptr [rbp+var_18+8]
0x1800151d3  mov     rcx, rdi
0x1800151d6  mov     rax, [rax+48h]
0x1800151da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151df  nop
0x1800151e0  lea     rcx, [rbp+arg_0]
0x1800151e4  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800151e9  jmp     loc_18001529D
0x1800151ee  lea     rcx, [rbp+arg_0]
0x1800151f2  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800151f7  mov     rax, [r15+18h]
0x1800151fb  mov     [rsi+48h], rax
0x1800151ff  mov     rax, [r15+20h]
0x180015203  mov     [rsi+50h], rax
0x180015207  xor     r9d, r9d; lpName
0x18001520a  xor     r8d, r8d; bInitialState
0x18001520d  xor     edx, edx; bManualReset
0x18001520f  xor     ecx, ecx; lpEventAttributes
0x180015211  call    cs:__imp_CreateEventW
0x180015217  mov     rdx, rax
0x18001521a  lea     rcx, [rsi+10h]
0x18001521e  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x180015223  xor     r9d, r9d; lpName
0x180015226  xor     r8d, r8d; bInitialState
0x180015229  xor     edx, edx; bManualReset
0x18001522b  xor     ecx, ecx; lpEventAttributes
0x18001522d  call    cs:__imp_CreateEventW
0x180015233  mov     rdx, rax
0x180015236  lea     rcx, [rsi+18h]
0x18001523a  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x18001523f  cmp     qword ptr [rsi+18h], 0
0x180015244  jz      short loc_18001524D
0x180015246  cmp     qword ptr [rsi+10h], 0
0x18001524b  jnz     short loc_180015274
0x18001524d  mov     rax, [rdi]
0x180015250  mov     rbx, [rax+58h]
0x180015254  call    cs:__imp_GetLastError
0x18001525a  mov     r9d, eax
0x18001525d  lea     r8, aCreateevent; "CreateEvent"
0x180015264  mov     edx, 4033C360h
0x180015269  mov     rcx, rdi
0x18001526c  mov     rax, rbx
0x18001526f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015274  mov     rax, [rdi]
0x180015277  mov     rcx, rdi
0x18001527a  mov     rax, [rax+90h]
0x180015281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015286  cmp     eax, 1
0x180015289  setz    al
0x18001528c  jmp     short loc_18001529F
0x18001528e  mov     rax, [rdi]
0x180015291  mov     rcx, rdi
0x180015294  mov     rax, [rax+18h]
0x180015298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001529d  xor     al, al
0x18001529f  lea     r11, [rsp+50h+var_s0]
0x1800152a4  mov     rbx, [r11+38h]
0x1800152a8  mov     rsi, [r11+40h]
0x1800152ac  mov     rsp, r11
0x1800152af  pop     r15
0x1800152b1  pop     r14
0x1800152b3  pop     r12
0x1800152b5  pop     rdi
0x1800152b6  pop     rbp
0x1800152b7  retn
```
