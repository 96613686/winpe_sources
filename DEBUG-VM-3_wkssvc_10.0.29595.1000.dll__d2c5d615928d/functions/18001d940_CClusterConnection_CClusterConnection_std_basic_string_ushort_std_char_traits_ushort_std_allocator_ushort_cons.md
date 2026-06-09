# CClusterConnection::CClusterConnection(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_GUID const *,ulong,ulong,CProtocolHandler *,ulong,void *)

- ea: `0x18001d940`
- end: `0x18001db5c`
- name: `??0CClusterConnection@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000PEBU_GUID@@KKPEAVCProtocolHandler@@KPEAX@Z`
- size: `540`
- prototype: `__int64 __usercall@<rax>(char@<cl>, __int64, __int64, int, char, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c120`

## callees

- `0x18001c7f0`
- `0x18001ccec`
- `0x18001d940`
- `0x18001db64`
- `0x180032464`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001db45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001db45`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001db3b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001db3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001db1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001db1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CClusterConnection::CClusterConnection(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _OWORD *a6,
        int a7,
        int a8,
        __int64 a9,
        int a10,
        __int64 a11)
{
  _QWORD *v12; // rbp
  _QWORD *v13; // r15
  _QWORD *v14; // rbx
  __int64 v15; // rbx

  *(_QWORD *)a1 = &RefCountObject::`vftable';
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &CClusterConnection::`vftable';
  *(_DWORD *)(a1 + 16) = 1;
  std::wstring::wstring(a1 + 24);
  v12 = (_QWORD *)(a1 + 56);
  std::wstring::wstring(a1 + 56);
  v13 = (_QWORD *)(a1 + 88);
  std::wstring::wstring(a1 + 88);
  *(_WORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  std::wstring::wstring(a1 + 152, &base);
  *(_QWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 208) = 0;
  v14 = (_QWORD *)(a1 + 216);
  std::wstring::wstring(a1 + 216);
  *(_QWORD *)(a1 + 248) = 0;
  *(_QWORD *)(a1 + 256) = 0;
  std::list<CWitnessServer *>::_Alloc_sentinel_and_proxy();
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 392) = 0;
  *(_QWORD *)(a1 + 400) = 0;
  *(_QWORD *)(a1 + 408) = a11;
  *(_QWORD *)(a1 + 416) = 0;
  *(_DWORD *)(a1 + 424) = 0;
  *(_QWORD *)(a1 + 440) = -1;
  *(_DWORD *)(a1 + 448) = a7;
  *(_DWORD *)(a1 + 452) = a8;
  *(_QWORD *)(a1 + 456) = a9;
  *(_DWORD *)(a1 + 464) = a10;
  *(_QWORD *)(a1 + 472) = 0;
  *(_QWORD *)(a1 + 480) = 0;
  if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
  {
    if ( *(_QWORD *)(a1 + 240) > 7u )
      v14 = (_QWORD *)*v14;
    if ( *(_QWORD *)(a1 + 112) > 7u )
      v13 = (_QWORD *)*v13;
    if ( *(_QWORD *)(a1 + 80) > 7u )
      v12 = (_QWORD *)*v12;
    WPP_SF_SSSSdq(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), (__int64)v12, (__int64)v13, (__int64)v14, a8, a1);
  }
  *(_OWORD *)(a1 + 120) = *a6;
  *(_OWORD *)(a1 + 184) = 0;
  v15 = *(_QWORD *)(a1 + 456);
  EnterCriticalSection(*(LPCRITICAL_SECTION *)(v15 + 80));
  if ( ++*(_DWORD *)(v15 + 132) == 1 )
    ResetEvent(*(HANDLE *)(v15 + 136));
  LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v15 + 80));
  return a1;
}

```

## disassembly

```asm
0x18001d940  mov     [rsp+arg_0], rcx
0x18001d945  push    rbx
0x18001d946  push    rbp
0x18001d947  push    rsi
0x18001d948  push    rdi
0x18001d949  push    r14
0x18001d94b  push    r15
0x18001d94d  sub     rsp, 58h
0x18001d951  mov     rdi, r9
0x18001d954  mov     rbx, r8
0x18001d957  mov     rsi, rcx
0x18001d95a  lea     rax, ??_7RefCountObject@@6B@; const RefCountObject::`vftable'
0x18001d961  mov     [rcx], rax
0x18001d964  mov     dword ptr [rcx+8], 1
0x18001d96b  lea     rax, ??_7CClusterConnection@@6B@; const CClusterConnection::`vftable'
0x18001d972  mov     [rcx], rax
0x18001d975  mov     dword ptr [rcx+10h], 1
0x18001d97c  lea     r14, [rcx+18h]
0x18001d980  mov     rcx, r14
0x18001d983  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d988  nop
0x18001d989  lea     rbp, [rsi+38h]
0x18001d98d  mov     rdx, rbx
0x18001d990  mov     rcx, rbp
0x18001d993  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d998  nop
0x18001d999  lea     r15, [rsi+58h]
0x18001d99d  mov     rdx, rdi
0x18001d9a0  mov     rcx, r15
0x18001d9a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d9a8  nop
0x18001d9a9  xor     edi, edi
0x18001d9ab  mov     [rsi+88h], di
0x18001d9b2  mov     [rsi+90h], rdi
0x18001d9b9  lea     rcx, [rsi+98h]
0x18001d9c0  lea     rdx, base
0x18001d9c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d9cc  nop
0x18001d9cd  mov     [rsi+0C8h], rdi
0x18001d9d4  mov     [rsi+0D0h], rdi
0x18001d9db  lea     rbx, [rsi+0D8h]
0x18001d9e2  mov     rdx, [rsp+88h+arg_20]
0x18001d9ea  mov     rcx, rbx
0x18001d9ed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d9f2  nop
0x18001d9f3  lea     rcx, [rsi+0F8h]
0x18001d9fa  mov     [rcx], rdi
0x18001d9fd  mov     [rcx+8], rdi
0x18001da01  call    ?_Alloc_sentinel_and_proxy@?$list@PEAVCWitnessServer@@V?$allocator@PEAVCWitnessServer@@@std@@@std@@AEAAXXZ; std::list<CWitnessServer *>::_Alloc_sentinel_and_proxy(void)
0x18001da06  nop
0x18001da07  mov     [rsi+108h], rdi
0x18001da0e  mov     [rsi+110h], rdi
0x18001da15  mov     [rsi+188h], rdi
0x18001da1c  mov     [rsi+190h], rdi
0x18001da23  mov     rax, [rsp+88h+arg_50]
0x18001da2b  mov     [rsi+198h], rax
0x18001da32  mov     [rsi+1A0h], rdi
0x18001da39  mov     [rsi+1A8h], edi
0x18001da3f  mov     qword ptr [rsi+1B8h], 0FFFFFFFFFFFFFFFFh
0x18001da4a  mov     eax, [rsp+88h+arg_30]
0x18001da51  mov     [rsi+1C0h], eax
0x18001da57  mov     edx, dword ptr [rsp+88h+arg_38]
0x18001da5e  mov     [rsi+1C4h], edx
0x18001da64  mov     rax, [rsp+88h+arg_40]
0x18001da6c  mov     [rsi+1C8h], rax
0x18001da73  mov     eax, [rsp+88h+arg_48]
0x18001da7a  mov     [rsi+1D0h], eax
0x18001da80  mov     [rsi+1D8h], rdi
0x18001da87  mov     [rsi+1E0h], rdi
0x18001da8e  lea     rax, WPP_witness_GLOBAL_Control
0x18001da95  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001da9c  cmp     rcx, rax
0x18001da9f  jz      short loc_18001DAFA
0x18001daa1  test    byte ptr [rcx+1Ch], 1
0x18001daa5  jz      short loc_18001DAFA
0x18001daa7  cmp     byte ptr [rcx+19h], 3
0x18001daab  jb      short loc_18001DAFA
0x18001daad  cmp     qword ptr [rbx+18h], 7
0x18001dab2  jbe     short loc_18001DAB7
0x18001dab4  mov     rbx, [rbx]
0x18001dab7  cmp     qword ptr [r15+18h], 7
0x18001dabc  jbe     short loc_18001DAC1
0x18001dabe  mov     r15, [r15]
0x18001dac1  cmp     qword ptr [rbp+18h], 7
0x18001dac6  jbe     short loc_18001DACC
0x18001dac8  mov     rbp, [rbp+0]
0x18001dacc  cmp     qword ptr [r14+18h], 7
0x18001dad1  jbe     short loc_18001DAD6
0x18001dad3  mov     r14, [r14]
0x18001dad6  mov     qword ptr [rsp+88h+var_48], rsi; char
0x18001dadb  mov     dword ptr [rsp+88h+var_50], edx; char
0x18001dadf  mov     [rsp+88h+var_58], rbx; __int64
0x18001dae4  mov     [rsp+88h+var_60], r15; __int64
0x18001dae9  mov     [rsp+88h+var_68], rbp; __int64
0x18001daee  mov     r9, r14
0x18001daf1  mov     rcx, [rcx+10h]; LoggerHandle
0x18001daf5  call    WPP_SF_SSSSdq
0x18001dafa  mov     rax, [rsp+88h+arg_28]
0x18001db02  movups  xmm0, xmmword ptr [rax]
0x18001db05  movdqu  xmmword ptr [rsi+78h], xmm0
0x18001db0a  xorps   xmm1, xmm1
0x18001db0d  movups  xmmword ptr [rsi+0B8h], xmm1
0x18001db14  mov     rbx, [rsi+1C8h]
0x18001db1b  mov     rcx, [rbx+50h]; lpCriticalSection
0x18001db1f  call    cs:__imp_EnterCriticalSection
0x18001db25  inc     dword ptr [rbx+84h]
0x18001db2b  cmp     dword ptr [rbx+84h], 1
0x18001db32  jnz     short loc_18001DB41
0x18001db34  mov     rcx, [rbx+88h]; hEvent
0x18001db3b  call    cs:__imp_ResetEvent
0x18001db41  mov     rcx, [rbx+50h]; lpCriticalSection
0x18001db45  call    cs:__imp_LeaveCriticalSection
0x18001db4b  nop
0x18001db4c  mov     rax, rsi
0x18001db4f  add     rsp, 58h
0x18001db53  pop     r15
0x18001db55  pop     r14
0x18001db57  pop     rdi
0x18001db58  pop     rsi
0x18001db59  pop     rbp
0x18001db5a  pop     rbx
0x18001db5b  retn
```
