# PendingRequest::PendingRequest(ushort const *,bool,ulong,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x180036e08`
- end: `0x180037156`
- name: `??0PendingRequest@@QEAA@PEBG_NK00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d288`

## callees

- `0x18000ab50`
- `0x1800171b0`
- `0x180017200`
- `0x180017230`
- `0x180036e08`
- `0x18003715c`
- `0x1800682d8`
- `0x18008251f`
- `0x18008a400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180036e49`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180036e49`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800370fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800370fc`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180036e95`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180036f60`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18003700f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180036e95`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180036f60`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18003700f`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x1800370ea`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x1800370ea`

## string_xrefs

- `0x18003712c`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall PendingRequest::PendingRequest(
        __int64 a1,
        _WORD *a2,
        char a3,
        int a4,
        _WORD *Src,
        __int64 a6,
        void *a7,
        char a8)
{
  _QWORD *v10; // rbp
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // r14
  __int64 v13; // r12
  __int64 v14; // rbx
  char *v15; // rdi
  _QWORD *v16; // r14
  __int64 v17; // r12
  __int64 v18; // rbx
  char *v19; // rdi
  _QWORD *v20; // rdi
  _OWORD *v21; // r14
  unsigned __int64 v22; // rbp
  __int64 v23; // rbx
  void *v24; // rax
  HANDLE EventW; // rdi
  const char *v26; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>();
  *(_QWORD *)a1 = &PendingRequest::`vftable';
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(a1 + 16), 0, 0);
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  v10 = (_QWORD *)(a1 + 72);
  *(_OWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  if ( v12 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  v13 = 2 * v12;
  if ( v12 > 7 )
  {
    v14 = std::wstring::_Calculate_growth(v12, 7);
    v15 = (char *)std::allocator<unsigned short>::allocate(a1 + 72, v14 + 1);
    *v10 = v15;
    *(_QWORD *)(a1 + 88) = v12;
    *(_QWORD *)(a1 + 96) = v14;
    memcpy_0(v15, a2, 2 * v12);
    *(_WORD *)&v15[v13] = 0;
  }
  else
  {
    *(_QWORD *)(a1 + 88) = v12;
    *(_QWORD *)(a1 + 96) = 7;
    memcpy_0((void *)(a1 + 72), a2, 2 * v12);
    *(_WORD *)((char *)v10 + v13) = 0;
  }
  *(_OWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 7;
  *(_WORD *)(a1 + 104) = 0;
  v16 = (_QWORD *)(a1 + 136);
  *(_OWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  do
    ++v11;
  while ( Src[v11] );
  if ( v11 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  v17 = 2 * v11;
  if ( v11 > 7 )
  {
    v18 = std::wstring::_Calculate_growth(v11, 7);
    v19 = (char *)std::allocator<unsigned short>::allocate(a1 + 136, v18 + 1);
    *v16 = v19;
    *(_QWORD *)(a1 + 152) = v11;
    *(_QWORD *)(a1 + 160) = v18;
    memcpy_0(v19, Src, 2 * v11);
    *(_WORD *)&v19[v17] = 0;
  }
  else
  {
    *(_QWORD *)(a1 + 152) = v11;
    *(_QWORD *)(a1 + 160) = 7;
    memcpy_0((void *)(a1 + 136), Src, 2 * v11);
    *(_WORD *)((char *)v16 + v17) = 0;
  }
  v20 = (_QWORD *)(a1 + 168);
  *(_OWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  v21 = a7;
  v22 = *((_QWORD *)a7 + 2);
  if ( *((_QWORD *)a7 + 3) > 7u )
    v21 = *(_OWORD **)a7;
  if ( v22 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v22 > 7 )
  {
    v23 = std::wstring::_Calculate_growth(*((_QWORD *)a7 + 2), 7);
    v24 = (void *)std::allocator<unsigned short>::allocate(a1 + 168, v23 + 1);
    *v20 = v24;
    *(_QWORD *)(a1 + 184) = v22;
    *(_QWORD *)(a1 + 192) = v23;
    memcpy_0(v24, v21, 2 * v22 + 2);
  }
  else
  {
    *(_QWORD *)(a1 + 184) = v22;
    *(_QWORD *)(a1 + 192) = 7;
    *(_OWORD *)v20 = *v21;
  }
  std::set<PsmKeyCompat>::set<PsmKeyCompat>(a1 + 200);
  *(_DWORD *)(a1 + 216) = a4;
  *(_QWORD *)(a1 + 232) = 0;
  *(_QWORD *)(a1 + 224) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *(_QWORD *)(a1 + 240) = &Microsoft::WRL::Wrappers::HandleT<TimerQueueTimerTraits>::`vftable';
  *(_QWORD *)(a1 + 248) = 0;
  *(_DWORD *)(a1 + 256) = -2147418113;
  *(_BYTE *)(a1 + 260) = a3;
  *(_BYTE *)(a1 + 261) = 0;
  *(_BYTE *)(a1 + 262) = a8;
  if ( a6 )
    std::wstring::assign(a1 + 104, a6);
  GetProcessReference(a1 + 56);
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW == *(HANDLE *)(a1 + 232) )
  {
    EventW = *(HANDLE *)(a1 + 232);
  }
  else
  {
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(a1 + 224);
    *(_QWORD *)(a1 + 232) = EventW;
  }
  if ( !EventW )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x6D9,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      v26);
  return a1;
}

```

## disassembly

```asm
0x180036e08  mov     rax, rsp
0x180036e0b  mov     [rax+10h], rbx
0x180036e0f  mov     [rax+20h], r9d
0x180036e13  mov     [rax+18h], r8b
0x180036e17  mov     [rax+8], rcx
0x180036e1b  push    rbp
0x180036e1c  push    rsi
0x180036e1d  push    rdi
0x180036e1e  push    r12
0x180036e20  push    r13
0x180036e22  push    r14
0x180036e24  push    r15
0x180036e26  sub     rsp, 20h
0x180036e2a  mov     r13, rdx
0x180036e2d  mov     rsi, rcx
0x180036e30  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>(void)
0x180036e35  nop
0x180036e36  lea     rax, ??_7PendingRequest@@6B@; const PendingRequest::`vftable'
0x180036e3d  mov     [rsi], rax
0x180036e40  lea     rcx, [rsi+10h]; lpCriticalSection
0x180036e44  xor     r8d, r8d; Flags
0x180036e47  xor     edx, edx; dwSpinCount
0x180036e49  call    cs:__imp_InitializeCriticalSectionEx
0x180036e4f  nop
0x180036e50  xor     ebx, ebx
0x180036e52  mov     [rsi+38h], rbx
0x180036e56  mov     [rsi+40h], rbx
0x180036e5a  lea     rbp, [rsi+48h]
0x180036e5e  xorps   xmm0, xmm0
0x180036e61  movups  xmmword ptr [rbp+0], xmm0
0x180036e65  mov     [rbp+10h], rbx
0x180036e69  mov     [rbp+18h], rbx
0x180036e6d  or      r15, 0FFFFFFFFFFFFFFFFh
0x180036e71  mov     r14, r15
0x180036e74  inc     r14
0x180036e77  cmp     [r13+r14*2+0], bx
0x180036e7d  jnz     short loc_180036E74
0x180036e7f  mov     rax, 7FFFFFFFFFFFFFFEh
0x180036e89  cmp     r14, rax
0x180036e8c  jbe     short loc_180036E9C
0x180036e8e  lea     rcx, aStringTooLong; "string too long"
0x180036e95  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180036e9c  lea     r12, [r14+r14]
0x180036ea0  mov     edi, 7
0x180036ea5  cmp     r14, rdi
0x180036ea8  ja      short loc_180036EC7
0x180036eaa  mov     [rbp+10h], r14
0x180036eae  mov     [rbp+18h], rdi
0x180036eb2  mov     r8, r12; Size
0x180036eb5  mov     rdx, r13; Src
0x180036eb8  mov     rcx, rbp; void *
0x180036ebb  call    memcpy_0
0x180036ec0  mov     [r12+rbp], bx
0x180036ec5  jmp     short loc_180036F0B
0x180036ec7  mov     r8, rax
0x180036eca  mov     rdx, rdi
0x180036ecd  mov     rcx, r14
0x180036ed0  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x180036ed5  mov     rbx, rax
0x180036ed8  lea     rdx, [rax+1]
0x180036edc  mov     rcx, rbp
0x180036edf  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x180036ee4  mov     rdi, rax
0x180036ee7  mov     [rbp+0], rax
0x180036eeb  mov     [rbp+10h], r14
0x180036eef  mov     [rbp+18h], rbx
0x180036ef3  mov     r8, r12; Size
0x180036ef6  mov     rdx, r13; Src
0x180036ef9  mov     rcx, rax; void *
0x180036efc  call    memcpy_0
0x180036f01  xor     ebx, ebx
0x180036f03  mov     [r12+rdi], bx
0x180036f08  lea     edi, [rbx+7]
0x180036f0b  lea     r13, [rsi+68h]
0x180036f0f  xorps   xmm0, xmm0
0x180036f12  movups  xmmword ptr [r13+0], xmm0
0x180036f17  mov     [r13+10h], rbx
0x180036f1b  mov     [r13+18h], rdi
0x180036f1f  mov     [r13+0], bx
0x180036f24  lea     r14, [rsi+88h]
0x180036f2b  movups  xmmword ptr [r14], xmm0
0x180036f2f  mov     [r14+10h], rbx
0x180036f33  mov     [r14+18h], rbx
0x180036f37  mov     rbp, [rsp+58h+Src]
0x180036f3f  inc     r15
0x180036f42  cmp     [rbp+r15*2+0], bx
0x180036f48  jnz     short loc_180036F3F
0x180036f4a  mov     r8, 7FFFFFFFFFFFFFFEh
0x180036f54  cmp     r15, r8
0x180036f57  jbe     short loc_180036F67
0x180036f59  lea     rcx, aStringTooLong; "string too long"
0x180036f60  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180036f67  lea     r12, [r15+r15]
0x180036f6b  cmp     r15, rdi
0x180036f6e  ja      short loc_180036F8D
0x180036f70  mov     [r14+10h], r15
0x180036f74  mov     [r14+18h], rdi
0x180036f78  mov     r8, r12; Size
0x180036f7b  mov     rdx, rbp; Src
0x180036f7e  mov     rcx, r14; void *
0x180036f81  call    memcpy_0
0x180036f86  mov     [r12+r14], bx
0x180036f8b  jmp     short loc_180036FCA
0x180036f8d  mov     rdx, rdi
0x180036f90  mov     rcx, r15
0x180036f93  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x180036f98  mov     rbx, rax
0x180036f9b  lea     rdx, [rax+1]
0x180036f9f  mov     rcx, r14
0x180036fa2  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x180036fa7  mov     rdi, rax
0x180036faa  mov     [r14], rax
0x180036fad  mov     [r14+10h], r15
0x180036fb1  mov     [r14+18h], rbx
0x180036fb5  mov     r8, r12; Size
0x180036fb8  mov     rdx, rbp; Src
0x180036fbb  mov     rcx, rax; void *
0x180036fbe  call    memcpy_0
0x180036fc3  xor     ebx, ebx
0x180036fc5  mov     [r12+rdi], bx
0x180036fca  lea     rdi, [rsi+0A8h]
0x180036fd1  xorps   xmm0, xmm0
0x180036fd4  movups  xmmword ptr [rdi], xmm0
0x180036fd7  mov     [rdi+10h], rbx
0x180036fdb  mov     [rdi+18h], rbx
0x180036fdf  mov     r14, [rsp+58h+arg_30]
0x180036fe7  mov     rbp, [r14+10h]
0x180036feb  mov     edx, 7
0x180036ff0  cmp     [r14+18h], rdx
0x180036ff4  jbe     short loc_180036FF9
0x180036ff6  mov     r14, [r14]
0x180036ff9  mov     rax, 7FFFFFFFFFFFFFFEh
0x180037003  cmp     rbp, rax
0x180037006  jbe     short loc_180037016
0x180037008  lea     rcx, aStringTooLong; "string too long"
0x18003700f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180037016  cmp     rbp, rdx
0x180037019  ja      short loc_18003702D
0x18003701b  mov     [rdi+10h], rbp
0x18003701f  mov     [rdi+18h], rdx
0x180037023  movups  xmm0, xmmword ptr [r14]
0x180037027  movdqu  xmmword ptr [rdi], xmm0
0x18003702b  jmp     short loc_180037066
0x18003702d  mov     r8, rax
0x180037030  mov     rcx, rbp
0x180037033  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x180037038  mov     rbx, rax
0x18003703b  lea     rdx, [rax+1]
0x18003703f  mov     rcx, rdi
0x180037042  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x180037047  mov     [rdi], rax
0x18003704a  mov     [rdi+10h], rbp
0x18003704e  mov     [rdi+18h], rbx
0x180037052  lea     r8, ds:2[rbp*2]; Size
0x18003705a  mov     rdx, r14; Src
0x18003705d  mov     rcx, rax; void *
0x180037060  call    memcpy_0
0x180037065  nop
0x180037066  lea     rcx, [rsi+0C8h]
0x18003706d  call    ??0?$set@UPsmKeyCompat@@U?$less@UPsmKeyCompat@@@std@@V?$allocator@UPsmKeyCompat@@@3@@std@@QEAA@XZ; std::set<PsmKeyCompat>::set<PsmKeyCompat>(void)
0x180037072  nop
0x180037073  mov     eax, [rsp+58h+arg_18]
0x180037077  mov     [rsi+0D8h], eax
0x18003707d  lea     rbx, [rsi+0E0h]
0x180037084  xor     ebp, ebp
0x180037086  mov     [rbx+8], rbp
0x18003708a  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180037091  mov     [rbx], rax
0x180037094  lea     rax, ??_7?$HandleT@UTimerQueueTimerTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<TimerQueueTimerTraits>::`vftable'
0x18003709b  mov     [rsi+0F0h], rax
0x1800370a2  mov     [rsi+0F8h], rbp
0x1800370a9  mov     dword ptr [rsi+100h], 8000FFFFh
0x1800370b3  mov     al, [rsp+58h+arg_10]
0x1800370b7  mov     [rsi+104h], al
0x1800370bd  mov     [rsi+105h], bpl
0x1800370c4  mov     al, [rsp+58h+arg_38]
0x1800370cb  mov     [rsi+106h], al
0x1800370d1  mov     rdx, [rsp+58h+arg_28]
0x1800370d9  test    rdx, rdx
0x1800370dc  jz      short loc_1800370E6
0x1800370de  mov     rcx, r13
0x1800370e1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800370e6  lea     rcx, [rsi+38h]
0x1800370ea  call    cs:__imp_GetProcessReference
0x1800370f0  xor     r9d, r9d; lpName
0x1800370f3  xor     r8d, r8d; bInitialState
0x1800370f6  lea     edx, [r9+1]; bManualReset
0x1800370fa  xor     ecx, ecx; lpEventAttributes
0x1800370fc  call    cs:__imp_CreateEventW
0x180037102  mov     rdi, rax
0x180037105  cmp     rax, [rbx+8]
0x180037109  jz      short loc_180037119
0x18003710b  mov     rcx, rbx
0x18003710e  call    ?Close@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(void)
0x180037113  mov     [rbx+8], rdi
0x180037117  jmp     short loc_18003711D
0x180037119  mov     rdi, [rbx+8]
0x18003711d  test    rdi, rdi
0x180037120  setz    al
0x180037123  mov     rcx, [rsp+58h]; this
0x180037128  test    al, al
0x18003712a  jz      short loc_18003713E
0x18003712c  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180037133  mov     edx, 6D9h; void *
0x180037138  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003713e  mov     rax, rsi
0x180037141  mov     rbx, [rsp+58h+arg_8]
0x180037146  add     rsp, 20h
0x18003714a  pop     r15
0x18003714c  pop     r14
0x18003714e  pop     r13
0x180037150  pop     r12
0x180037152  pop     rdi
0x180037153  pop     rsi
0x180037154  pop     rbp
0x180037155  retn
```
