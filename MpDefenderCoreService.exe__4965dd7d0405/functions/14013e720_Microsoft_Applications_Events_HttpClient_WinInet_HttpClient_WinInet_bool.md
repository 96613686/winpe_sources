# Microsoft::Applications::Events::HttpClient_WinInet::HttpClient_WinInet(bool)

- ea: `0x14013e720`
- end: `0x14013e8b6`
- name: `??0HttpClient_WinInet@Events@Applications@Microsoft@@QEAA@_N@Z`
- size: `406`
- prototype: `__int64 __fastcall(Microsoft::Applications::Events::HttpClient_WinInet *__hidden this, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400eaa58`
- `0x14014091c`

## callees

- `0x14001cd4c`
- `0x14001cd94`
- `0x14001cdc0`
- `0x14003a0f4`
- `0x14013e720`
- `0x140166250`

## import_xrefs

- `ole32!CoCreateInstance` at `0x14013e7ef`
- `ole32!CoCreateInstance` at `0x14013e7ef`
- `WININET!InternetOpenW` at `0x14013e869`
- `WININET!InternetOpenW` at `0x14013e869`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
Microsoft::Applications::Events::HttpClient_WinInet *__fastcall Microsoft::Applications::Events::HttpClient_WinInet::HttpClient_WinInet(
        Microsoft::Applications::Events::HttpClient_WinInet *this,
        unsigned __int8 a2)
{
  int v2; // esi
  _QWORD *v4; // rax
  _QWORD *v5; // rbx

  v2 = a2;
  *(_QWORD *)this = &Microsoft::Applications::Events::HttpClient_WinInet::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 258;
  *(_OWORD *)((char *)this + 40) = 0;
  *(_OWORD *)((char *)this + 56) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 22) = -1;
  *((_DWORD *)this + 23) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  v4 = operator new(0x48u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  *((_QWORD *)this + 12) = v4;
  *((_WORD *)this + 56) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  v5 = (_QWORD *)((char *)this + 168);
  *((_QWORD *)this + 21) = 0;
  if ( pCLSID_HttpClient_WinInet_Delegate
    && CoCreateInstance(
         pCLSID_HttpClient_WinInet_Delegate,
         0,
         1u,
         &GUID_593b450b_6650_4501_ad87_b213295680a4,
         (LPVOID *)this + 21) >= 0
    && *v5 )
  {
    if ( Mtx_lock((_Mtx_t)&global_options_mtx) )
      std::_Throw_Cpp_error(5);
    if ( dword_1401D969C == 0x7FFFFFFF )
    {
      dword_1401D969C = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    if ( byte_1401E7BC8 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v5 + 120LL))(*v5, &proxy_info);
    }
    Mtx_unlock((_Mtx_t)&global_options_mtx);
  }
  else
  {
    *((_QWORD *)this + 1) = InternetOpenW(0, 4 * v2, 0, 0, 0x10000000u);
    *((_QWORD *)this + 16) = *((_QWORD *)this + 15);
  }
  return this;
}

```

## disassembly

```asm
0x14013e720  mov     rax, rsp
0x14013e723  mov     [rax+10h], rbx
0x14013e727  mov     [rax+18h], rbp
0x14013e72b  mov     [rax+20h], rsi
0x14013e72f  push    rdi
0x14013e730  sub     rsp, 40h
0x14013e734  movzx   esi, dl
0x14013e737  mov     rdi, rcx
0x14013e73a  mov     [rax-10h], rcx
0x14013e73e  lea     rax, ??_7HttpClient_WinInet@Events@Applications@Microsoft@@6B@; const Microsoft::Applications::Events::HttpClient_WinInet::`vftable'
0x14013e745  mov     [rcx], rax
0x14013e748  xor     ebp, ebp
0x14013e74a  mov     [rcx+8], rbp
0x14013e74e  mov     qword ptr [rcx+10h], 102h
0x14013e756  xorps   xmm0, xmm0
0x14013e759  movups  xmmword ptr [rcx+28h], xmm0
0x14013e75d  movups  xmmword ptr [rcx+38h], xmm0
0x14013e761  movups  xmmword ptr [rcx+48h], xmm0
0x14013e765  mov     [rcx+18h], rbp
0x14013e769  mov     [rcx+20h], rbp
0x14013e76d  mov     dword ptr [rcx+58h], 0FFFFFFFFh
0x14013e774  mov     [rcx+5Ch], ebp
0x14013e777  mov     [rcx+60h], rbp
0x14013e77b  mov     [rcx+68h], rbp
0x14013e77f  lea     ecx, [rbp+48h]; Size
0x14013e782  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14013e787  mov     [rax], rax
0x14013e78a  mov     [rax+8], rax
0x14013e78e  mov     [rax+10h], rax
0x14013e792  mov     word ptr [rax+18h], 101h
0x14013e798  mov     [rdi+60h], rax
0x14013e79c  mov     [rdi+70h], bp
0x14013e7a0  mov     [rdi+78h], rbp
0x14013e7a4  mov     [rdi+80h], rbp
0x14013e7ab  mov     [rdi+88h], rbp
0x14013e7b2  mov     [rdi+90h], rbp
0x14013e7b9  mov     [rdi+98h], rbp
0x14013e7c0  mov     [rdi+0A0h], rbp
0x14013e7c7  lea     rbx, [rdi+0A8h]
0x14013e7ce  mov     [rbx], rbp
0x14013e7d1  mov     rcx, cs:pCLSID_HttpClient_WinInet_Delegate; rclsid
0x14013e7d8  test    rcx, rcx
0x14013e7db  jz      short loc_14013E854
0x14013e7dd  mov     [rsp+48h+ppv], rbx; ppv
0x14013e7e2  lea     r9, _GUID_593b450b_6650_4501_ad87_b213295680a4; riid
0x14013e7e9  xor     edx, edx; pUnkOuter
0x14013e7eb  lea     r8d, [rbp+1]; dwClsContext
0x14013e7ef  call    cs:__imp_CoCreateInstance
0x14013e7f5  test    eax, eax
0x14013e7f7  js      short loc_14013E854
0x14013e7f9  cmp     [rbx], rbp
0x14013e7fc  jz      short loc_14013E854
0x14013e7fe  lea     rsi, ?global_options_mtx@@3Vmutex@std@@A; std::mutex global_options_mtx
0x14013e805  mov     [rsp+48h+var_18], rsi
0x14013e80a  mov     rcx, rsi; _Mtx_t
0x14013e80d  call    _Mtx_lock
0x14013e812  test    eax, eax
0x14013e814  jnz     loc_14013E8AB
0x14013e81a  cmp     cs:dword_1401D969C, 7FFFFFFFh
0x14013e824  jz      short loc_14013E896
0x14013e826  cmp     cs:byte_1401E7BC8, bpl
0x14013e82d  jz      short loc_14013E84A
0x14013e82f  lfence
0x14013e832  mov     rcx, [rbx]
0x14013e835  mov     rax, [rcx]
0x14013e838  lea     rdx, ?proxy_info@@3V?$optional@Uproxy_info_t@@@std@@A; std::optional<proxy_info_t> proxy_info
0x14013e83f  mov     rax, [rax+78h]
0x14013e843  call    cs:__guard_dispatch_icall_fptr
0x14013e849  nop
0x14013e84a  mov     rcx, rsi; _Mtx_t
0x14013e84d  call    _Mtx_unlock
0x14013e852  jmp     short loc_14013E87E
0x14013e854  mov     edx, esi
0x14013e856  shl     edx, 2; dwAccessType
0x14013e859  mov     dword ptr [rsp+48h+ppv], 10000000h; dwFlags
0x14013e861  xor     r9d, r9d; lpszProxyBypass
0x14013e864  xor     r8d, r8d; lpszProxy
0x14013e867  xor     ecx, ecx; lpszAgent
0x14013e869  call    cs:__imp_InternetOpenW
0x14013e86f  mov     [rdi+8], rax
0x14013e873  mov     rcx, [rdi+78h]
0x14013e877  mov     [rdi+80h], rcx
0x14013e87e  mov     rax, rdi
0x14013e881  mov     rbx, [rsp+48h+arg_8]
0x14013e886  mov     rbp, [rsp+48h+arg_10]
0x14013e88b  mov     rsi, [rsp+48h+arg_18]
0x14013e890  add     rsp, 40h
0x14013e894  pop     rdi
0x14013e895  retn
0x14013e896  mov     cs:dword_1401D969C, 7FFFFFFEh
0x14013e8a0  mov     ecx, 6; int
0x14013e8a5  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14013e8ab  mov     ecx, 5; int
0x14013e8b0  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
