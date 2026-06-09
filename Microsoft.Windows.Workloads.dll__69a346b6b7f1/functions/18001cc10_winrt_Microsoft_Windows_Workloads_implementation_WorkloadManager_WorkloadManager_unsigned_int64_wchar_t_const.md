# winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::WorkloadManager(unsigned __int64,wchar_t const *)

- ea: `0x18001cc10`
- end: `0x18001d032`
- name: `??0WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@QEAA@_KPEB_W@Z`
- size: `1058`
- prototype: `winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *__fastcall(winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *this, __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001d320`

## callees

- `0x180001b90`
- `0x180001ca0`
- `0x1800027d0`
- `0x180002860`
- `0x180002880`
- `0x1800029d0`
- `0x1800029f0`
- `0x180004a00`
- `0x1800119b0`
- `0x180013bd0`
- `0x180014e70`
- `0x18001cc10`
- `0x18001eb00`
- `0x180028550`
- `0x180034ef0`
- `0x180035060`
- `0x180036f4c`
- `0x18003c020`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001cdbc`
- `KERNEL32!GetModuleHandleW` at `0x18001cdbc`
- `KERNEL32!GetCurrentProcessId` at `0x18001ce00`
- `KERNEL32!GetCurrentProcessId` at `0x18001ce00`
- `KERNEL32!GetProcAddress` at `0x18001cdcc`
- `KERNEL32!GetProcAddress` at `0x18001cdcc`

## string_xrefs

- `0x18001cdc5`: `g_WSAIFabricService`
- `0x18001cff4`: `Resource path empty`

## pseudocode

```c
winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *__fastcall winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::WorkloadManager(
        winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *this,
        __int64 a2,
        const wchar_t *a3)
{
  _QWORD *v6; // rcx
  unsigned __int64 v7; // r8
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  HMODULE ModuleHandleW; // rax
  const struct _tlgProvider_t *v12; // rax
  DWORD CurrentProcessId; // r8d
  _WORD *v14; // rsi
  unsigned __int64 v15; // rbx
  __int64 v16; // r15
  size_t v17; // rbx
  __int64 v18; // rcx
  size_t v19; // rbx
  __int64 v20; // rdx
  const wchar_t *v21; // rbx
  const struct _tlgProvider_t *v22; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  winrt::hresult *v26; // rax
  const wchar_t *v27; // [rsp+30h] [rbp-79h] BYREF
  __int128 pExceptionObject; // [rsp+38h] [rbp-71h] BYREF
  __m128i si128; // [rsp+48h] [rbp-61h]
  _OWORD v30[2]; // [rsp+58h] [rbp-51h] BYREF
  winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *v31; // [rsp+78h] [rbp-31h]
  _QWORD v32[9]; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v33[6]; // [rsp+CAh] [rbp+21h] BYREF

  v31 = this;
  *((_QWORD *)this + 2) = &winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager>::`vftable';
  *((_QWORD *)this + 3) = &winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager2>::`vftable';
  *((_QWORD *)this + 4) = &winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager3>::`vftable';
  *((_QWORD *)this + 5) = &winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager4>::`vftable';
  *((_QWORD *)this + 6) = &winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager5>::`vftable';
  *((_QWORD *)this + 7) = &winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager6>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)this + 1) = 1;
  *(_QWORD *)this = &winrt::impl::heap_implements<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::`vftable';
  *((_QWORD *)this + 8) = 0;
  v6 = (_QWORD *)((char *)this + 72);
  *(_OWORD *)v6 = 0;
  v6[2] = 0;
  v6[3] = 0;
  v7 = -1;
  do
    ++v7;
  while ( a3[v7] );
  std::wstring::_Construct<1,wchar_t const *>(v6, a3, v7);
  *((_QWORD *)this + 13) = a2;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  v8 = operator new(0x48u);
  *v8 = v8;
  v8[1] = v8;
  v8[2] = v8;
  *((_WORD *)v8 + 12) = 257;
  *((_QWORD *)this + 14) = v8;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  v9 = operator new(0x48u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  *((_QWORD *)this + 16) = v9;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  v10 = operator new(0x40u);
  *v10 = v10;
  v10[1] = v10;
  v10[2] = v10;
  *((_WORD *)v10 + 12) = 257;
  *((_QWORD *)this + 18) = v10;
  *((_QWORD *)this + 20) = 0;
  *((_BYTE *)this + 168) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_DWORD *)this + 46) = 0;
  *((_OWORD *)this + 12) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 15;
  *((_BYTE *)this + 192) = 0;
  *((_DWORD *)this + 56) = 4;
  if ( !*((_QWORD *)this + 11) )
  {
    winrt::param::hstring::hstring((winrt::param::hstring *)v32, L"Resource path empty");
    v26 = winrt::hresult::hresult((winrt::hresult *)&v27, -2147024809);
    winrt::hresult_error::hresult_error(&pExceptionObject, *(unsigned int *)v26, v32);
    throw (winrt::hresult_error *)&pExceptionObject;
  }
  ModuleHandleW = GetModuleHandleW(0);
  if ( GetProcAddress(ModuleHandleW, "g_WSAIFabricService") )
  {
    v12 = TraceLogger::Provider();
    if ( *(_DWORD *)v12 > 5u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)v12,
        (unsigned __int8 *)byte_18004DB3B);
    *((_DWORD *)this + 56) = 1;
  }
  else
  {
    CurrentProcessId = GetCurrentProcessId();
    v14 = v33;
    do
    {
      *--v14 = CurrentProcessId % 0xA + 48;
      CurrentProcessId /= 0xAu;
    }
    while ( CurrentProcessId );
    pExceptionObject = 0;
    si128 = 0;
    if ( v14 == (_WORD *)v33 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(pExceptionObject) = 0;
    }
    else
    {
      v15 = (v33 - (_BYTE *)v14) >> 1;
      v16 = 0x7FFFFFFFFFFFFFFELL;
      if ( v15 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      if ( v15 > 7 )
      {
        if ( (v15 | 7) <= 0x7FFFFFFFFFFFFFFELL )
        {
          v16 = v15 | 7;
          if ( (v15 | 7) < 0xA )
            v16 = 10;
          v18 = v16 + 1;
          if ( (unsigned __int64)(v16 + 1) > 0x7FFFFFFFFFFFFFFFLL )
            __scrt_throw_std_bad_array_new_length();
        }
        else
        {
          v18 = 0x7FFFFFFFFFFFFFFFLL;
        }
        _mm_lfence();
        *(_QWORD *)&pExceptionObject = std::_Allocate<16,std::_Default_allocate_traits>(2 * v18);
        si128.m128i_i64[0] = (v33 - (_BYTE *)v14) >> 1;
        si128.m128i_i64[1] = v16;
        v19 = 2 * v15;
        memmove((void *)pExceptionObject, v14, v19);
        *(_WORD *)(pExceptionObject + v19) = 0;
      }
      else
      {
        _mm_lfence();
        si128.m128i_i64[0] = (v33 - (_BYTE *)v14) >> 1;
        si128.m128i_i64[1] = 7;
        v17 = 2 * v15;
        memmove(&pExceptionObject, v14, v17);
        *(_WORD *)((char *)&pExceptionObject + v17) = 0;
      }
    }
    memset(v30, 0, sizeof(v30));
    std::wstring::_Construct<1,wchar_t const *>(v30, L"pid: ", 5u);
    std::wstring::wstring(v32, v20, v30, &pExceptionObject);
    std::wstring::_Tidy_deallocate(v30);
    std::wstring::_Tidy_deallocate(&pExceptionObject);
    v21 = (const wchar_t *)v32;
    if ( v32[3] > 7u )
      v21 = (const wchar_t *)v32[0];
    v22 = TraceLogger::Provider();
    if ( *(_DWORD *)v22 > 5u )
    {
      v27 = v21;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        (__int64)v22,
        (unsigned __int8 *)byte_18004DA75,
        v23,
        v24,
        &v27);
    }
    std::wstring::_Tidy_deallocate(v32);
  }
  winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::LoadWorkloads(this);
  return this;
}

```

## disassembly

```asm
0x18001cc10  mov     [rsp-8+arg_8], rbx
0x18001cc15  mov     [rsp-8+arg_18], rsi
0x18001cc1a  push    rbp
0x18001cc1b  push    rdi
0x18001cc1c  push    r12
0x18001cc1e  push    r14
0x18001cc20  push    r15
0x18001cc22  lea     rbp, [rsp-37h]
0x18001cc27  sub     rsp, 0E0h
0x18001cc2e  mov     rax, cs:__security_cookie
0x18001cc35  xor     rax, rsp
0x18001cc38  mov     [rbp+57h+var_30], rax
0x18001cc3c  mov     rax, r8
0x18001cc3f  mov     rbx, rdx
0x18001cc42  mov     r14, rcx
0x18001cc45  mov     [rbp+57h+var_88], rcx
0x18001cc49  xor     r12d, r12d
0x18001cc4c  lea     rcx, ??_7?$produce@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@UIWorkloadManager@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager>::`vftable'
0x18001cc53  mov     [r14+10h], rcx
0x18001cc57  lea     rcx, ??_7?$produce@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@UIWorkloadManager2@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager2>::`vftable'
0x18001cc5e  mov     [r14+18h], rcx
0x18001cc62  lea     rcx, ??_7?$produce@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@UIWorkloadManager3@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager3>::`vftable'
0x18001cc69  mov     [r14+20h], rcx
0x18001cc6d  lea     rcx, ??_7?$produce@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@UIWorkloadManager4@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager4>::`vftable'
0x18001cc74  mov     [r14+28h], rcx
0x18001cc78  lea     rcx, ??_7?$produce@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@UIWorkloadManager5@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager5>::`vftable'
0x18001cc7f  mov     [r14+30h], rcx
0x18001cc83  lea     rcx, ??_7?$produce@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@UIWorkloadManager6@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager6>::`vftable'
0x18001cc8a  mov     [r14+38h], rcx
0x18001cc8e  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001cc95  mov     qword ptr [r14+8], 1
0x18001cc9d  lea     rcx, ??_7?$heap_implements@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::`vftable'
0x18001cca4  mov     [r14], rcx
0x18001cca7  mov     [r14+40h], r12
0x18001ccab  lea     rcx, [r14+48h]
0x18001ccaf  xorps   xmm0, xmm0
0x18001ccb2  movups  xmmword ptr [rcx], xmm0
0x18001ccb5  mov     [rcx+10h], r12
0x18001ccb9  mov     [rcx+18h], r12
0x18001ccbd  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001ccc4  inc     r8
0x18001ccc7  cmp     word ptr [rax+r8*2], 0
0x18001cccd  jnz     short loc_18001CCC4
0x18001cccf  mov     rdx, rax
0x18001ccd2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001ccd7  nop
0x18001ccd8  mov     [r14+68h], rbx
0x18001ccdc  mov     [r14+70h], r12
0x18001cce0  mov     [r14+78h], r12
0x18001cce4  mov     ecx, 48h ; 'H'; Size
0x18001cce9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ccee  mov     [rax], rax
0x18001ccf1  mov     [rax+8], rax
0x18001ccf5  mov     [rax+10h], rax
0x18001ccf9  mov     word ptr [rax+18h], 101h
0x18001ccff  mov     [r14+70h], rax
0x18001cd03  mov     [r14+80h], r12
0x18001cd0a  mov     [r14+88h], r12
0x18001cd11  mov     ecx, 48h ; 'H'; Size
0x18001cd16  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cd1b  mov     [rax], rax
0x18001cd1e  mov     [rax+8], rax
0x18001cd22  mov     [rax+10h], rax
0x18001cd26  mov     word ptr [rax+18h], 101h
0x18001cd2c  mov     [r14+80h], rax
0x18001cd33  mov     [r14+90h], r12
0x18001cd3a  mov     [r14+98h], r12
0x18001cd41  mov     ecx, 40h ; '@'; Size
0x18001cd46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cd4b  mov     [rax], rax
0x18001cd4e  mov     [rax+8], rax
0x18001cd52  mov     [rax+10h], rax
0x18001cd56  mov     word ptr [rax+18h], 101h
0x18001cd5c  mov     [r14+90h], rax
0x18001cd63  xor     eax, eax
0x18001cd65  mov     [r14+0A0h], rax
0x18001cd6c  mov     [r14+0A8h], al
0x18001cd73  mov     [r14+0B0h], r12
0x18001cd7a  mov     [r14+0B8h], r12d
0x18001cd81  xorps   xmm0, xmm0
0x18001cd84  movups  xmmword ptr [r14+0C0h], xmm0
0x18001cd8c  mov     [r14+0D0h], r12
0x18001cd93  mov     qword ptr [r14+0D8h], 0Fh
0x18001cd9e  mov     [r14+0C0h], al
0x18001cda5  mov     dword ptr [r14+0E0h], 4
0x18001cdb0  cmp     [r14+58h], rax
0x18001cdb4  jz      loc_18001CFF4
0x18001cdba  xor     ecx, ecx; lpModuleName
0x18001cdbc  call    cs:__imp_GetModuleHandleW
0x18001cdc2  mov     rcx, rax; hModule
0x18001cdc5  lea     rdx, aGWsaifabricser; "g_WSAIFabricService"
0x18001cdcc  call    cs:__imp_GetProcAddress
0x18001cdd2  test    rax, rax
0x18001cdd5  jz      short loc_18001CE00
0x18001cdd7  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18001cddc  cmp     dword ptr [rax], 5
0x18001cddf  jbe     short loc_18001CDF0
0x18001cde1  lea     rdx, byte_18004DB3B
0x18001cde8  mov     rcx, rax
0x18001cdeb  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001cdf0  mov     dword ptr [r14+0E0h], 1
0x18001cdfb  jmp     loc_18001CF8D
0x18001ce00  call    cs:__imp_GetCurrentProcessId
0x18001ce06  mov     r8d, eax
0x18001ce09  lea     rsi, [rbp+57h+var_36]
0x18001ce0d  nop     dword ptr [rax]
0x18001ce10  sub     rsi, 2
0x18001ce14  mov     eax, 0CCCCCCCDh
0x18001ce19  mul     r8d
0x18001ce1c  shr     edx, 3
0x18001ce1f  movzx   eax, dx
0x18001ce22  shl     ax, 2
0x18001ce26  lea     ecx, [rax+rdx]
0x18001ce29  add     cx, cx
0x18001ce2c  sub     r8w, cx
0x18001ce30  add     r8w, 30h ; '0'
0x18001ce35  mov     [rsi], r8w
0x18001ce39  mov     r8d, edx
0x18001ce3c  test    edx, edx
0x18001ce3e  jnz     short loc_18001CE10
0x18001ce40  xorps   xmm0, xmm0
0x18001ce43  movups  [rbp+57h+pExceptionObject], xmm0
0x18001ce47  xorps   xmm1, xmm1
0x18001ce4a  movdqu  [rbp+57h+var_B8], xmm1
0x18001ce4f  lea     rax, [rbp+57h+var_36]
0x18001ce53  cmp     rsi, rax
0x18001ce56  jnz     short loc_18001CE6F
0x18001ce58  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001ce60  movdqu  [rbp+57h+var_B8], xmm0
0x18001ce65  mov     word ptr [rbp+57h+pExceptionObject], r12w
0x18001ce6a  jmp     loc_18001CF05
0x18001ce6f  lea     rbx, [rbp+57h+var_36]
0x18001ce73  sub     rbx, rsi
0x18001ce76  sar     rbx, 1
0x18001ce79  mov     r15, 7FFFFFFFFFFFFFFEh
0x18001ce83  cmp     rbx, r15
0x18001ce86  ja      loc_18001CFE8
0x18001ce8c  cmp     rbx, 7
0x18001ce90  ja      short loc_18001CEBB
0x18001ce92  lfence
0x18001ce95  mov     qword ptr [rbp+57h+var_B8], rbx
0x18001ce99  mov     qword ptr [rbp+57h+var_B8+8], 7
0x18001cea1  add     rbx, rbx
0x18001cea4  mov     r8, rbx; Size
0x18001cea7  mov     rdx, rsi; Src
0x18001ceaa  lea     rcx, [rbp+57h+pExceptionObject]; void *
0x18001ceae  call    memmove
0x18001ceb3  mov     word ptr [rbp+rbx+57h+pExceptionObject], r12w
0x18001ceb9  jmp     short loc_18001CF05
0x18001cebb  mov     rax, rbx
0x18001cebe  or      rax, 7
0x18001cec2  cmp     rax, r15
0x18001cec5  jbe     loc_18001CFC1
0x18001cecb  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18001ced5  lfence
0x18001ced8  add     rcx, rcx
0x18001cedb  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001cee0  mov     rdi, rax
0x18001cee3  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x18001cee7  mov     qword ptr [rbp+57h+var_B8], rbx
0x18001ceeb  mov     qword ptr [rbp+57h+var_B8+8], r15
0x18001ceef  add     rbx, rbx
0x18001cef2  mov     r8, rbx; Size
0x18001cef5  mov     rdx, rsi; Src
0x18001cef8  mov     rcx, rax; void *
0x18001cefb  call    memmove
0x18001cf00  mov     [rdi+rbx], r12w
0x18001cf05  xorps   xmm0, xmm0
0x18001cf08  movups  [rbp+57h+var_A8], xmm0
0x18001cf0c  xorps   xmm1, xmm1
0x18001cf0f  movdqu  [rbp+57h+var_98], xmm1
0x18001cf14  mov     r8d, 5
0x18001cf1a  lea     rdx, aPid; "pid: "
0x18001cf21  lea     rcx, [rbp+57h+var_A8]
0x18001cf25  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001cf2a  nop
0x18001cf2b  lea     r9, [rbp+57h+pExceptionObject]
0x18001cf2f  lea     r8, [rbp+57h+var_A8]
0x18001cf33  lea     rcx, [rbp+57h+var_80]
0x18001cf37  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x18001cf3c  nop
0x18001cf3d  lea     rcx, [rbp+57h+var_A8]
0x18001cf41  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cf46  nop
0x18001cf47  lea     rcx, [rbp+57h+pExceptionObject]
0x18001cf4b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cf50  lea     rbx, [rbp+57h+var_80]
0x18001cf54  cmp     [rbp+57h+var_68], 7
0x18001cf59  cmova   rbx, [rbp+57h+var_80]
0x18001cf5e  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18001cf63  cmp     dword ptr [rax], 5
0x18001cf66  jbe     short loc_18001CF84
0x18001cf68  mov     [rbp+57h+var_D0], rbx
0x18001cf6c  lea     rcx, [rbp+57h+var_D0]
0x18001cf70  mov     [rsp+100h+var_E0], rcx
0x18001cf75  lea     rdx, byte_18004DA75
0x18001cf7c  mov     rcx, rax
0x18001cf7f  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18001cf84  lea     rcx, [rbp+57h+var_80]
0x18001cf88  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cf8d  mov     rcx, r14; this
0x18001cf90  call    ?LoadWorkloads@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@AEAAXXZ; winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::LoadWorkloads(void)
0x18001cf95  nop
0x18001cf96  mov     rax, r14
0x18001cf99  mov     rcx, [rbp+57h+var_30]
0x18001cf9d  xor     rcx, rsp; StackCookie
0x18001cfa0  call    __security_check_cookie
0x18001cfa5  lea     r11, [rsp+100h+var_20]
0x18001cfad  mov     rbx, [r11+38h]
0x18001cfb1  mov     rsi, [r11+48h]
0x18001cfb5  mov     rsp, r11
0x18001cfb8  pop     r15
0x18001cfba  pop     r14
0x18001cfbc  pop     r12
0x18001cfbe  pop     rdi
0x18001cfbf  pop     rbp
0x18001cfc0  retn
0x18001cfc1  mov     r15, rax
0x18001cfc4  mov     ecx, 0Ah
0x18001cfc9  cmp     rax, rcx
0x18001cfcc  cmovb   r15, rcx
0x18001cfd0  lea     rcx, [r15+1]
0x18001cfd4  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001cfde  cmp     rcx, rax
0x18001cfe1  ja      short loc_18001CFEE
0x18001cfe3  jmp     loc_18001CED5
0x18001cfe8  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18001cfee  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x18001cff4  lea     rdx, aResourcePathEm; "Resource path empty"
0x18001cffb  lea     rcx, [rbp+57h+var_80]; this
0x18001cfff  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18001d004  mov     edx, 80070057h; int
0x18001d009  lea     rcx, [rbp+57h+var_D0]; this
0x18001d00d  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18001d012  lea     r8, [rbp+57h+var_80]
0x18001d016  mov     edx, [rax]
0x18001d018  lea     rcx, [rbp+57h+pExceptionObject]
0x18001d01c  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &)
0x18001d021  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18001d028  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001d02c  call    _CxxThrowException
```
