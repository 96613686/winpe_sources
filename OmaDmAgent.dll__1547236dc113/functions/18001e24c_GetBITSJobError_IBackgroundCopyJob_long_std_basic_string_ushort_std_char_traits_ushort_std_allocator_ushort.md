# GetBITSJobError(IBackgroundCopyJob *,long *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001e24c`
- end: `0x18001e39d`
- name: `?GetBITSJobError@@YAJPEAUIBackgroundCopyJob@@PEAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `337`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001bcd4`
- `0x18001cb10`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x1800065f8`
- `0x18001afb4`
- `0x18001e24c`
- `0x18001f420`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetBITSJobError(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdx
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v10; // [rsp+20h] [rbp-29h] BYREF
  int v11; // [rsp+28h] [rbp-21h] BYREF
  __int64 v12; // [rsp+30h] [rbp-19h] BYREF
  __int64 v13; // [rsp+38h] [rbp-11h] BYREF
  _BYTE v14[32]; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v15[32]; // [rsp+60h] [rbp+17h] BYREF

  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  std::wstring::wstring(v15, L"Unknown");
  std::wstring::wstring(v14, L"Unknown");
  if ( a1 && a2 )
  {
    std::wstring::assign(a3, &dword_180022F6C);
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 120LL))(a1, &v10);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, int *, __int64))(*(_QWORD *)v10 + 24LL))(v10, &v11, a2);
      if ( v7 >= 0 )
      {
        (*(void (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v10 + 40LL))(v10, 1033, &v12);
        (*(void (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v10 + 48LL))(v10, 1033, &v13);
        v6 = v12;
        if ( v12 )
          std::wstring::assign(a3, v12);
      }
    }
  }
  else
  {
    v7 = -2147024809;
  }
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v14, v6, 0);
  LOBYTE(v8) = 1;
  std::wstring::_Tidy(v15, v8, 0);
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(&v10);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001e24c  mov     [rsp-8+arg_18], rbx
0x18001e251  push    rbp
0x18001e252  push    rsi
0x18001e253  push    rdi
0x18001e254  lea     rbp, [rsp-47h]
0x18001e259  sub     rsp, 90h
0x18001e260  mov     rax, cs:__security_cookie
0x18001e267  xor     rax, rsp
0x18001e26a  mov     [rbp+57h+var_20], rax
0x18001e26e  mov     rsi, r8
0x18001e271  mov     rdi, rdx
0x18001e274  mov     rbx, rcx
0x18001e277  mov     [rbp+57h+var_80], 0
0x18001e27f  mov     [rbp+57h+var_78], 0
0x18001e286  mov     [rbp+57h+var_70], 0
0x18001e28e  mov     [rbp+57h+var_68], 0
0x18001e296  lea     rdx, aUnknown; "Unknown"
0x18001e29d  lea     rcx, [rbp+57h+var_40]
0x18001e2a1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001e2a6  nop
0x18001e2a7  lea     rdx, aUnknown; "Unknown"
0x18001e2ae  lea     rcx, [rbp+57h+var_60]
0x18001e2b2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001e2b7  nop
0x18001e2b8  test    rbx, rbx
0x18001e2bb  jnz     short loc_18001E2C7
0x18001e2bd  mov     ebx, 80070057h
0x18001e2c2  jmp     loc_18001E354
0x18001e2c7  test    rdi, rdi
0x18001e2ca  jz      short loc_18001E2BD
0x18001e2cc  lea     rdx, dword_180022F6C
0x18001e2d3  mov     rcx, rsi
0x18001e2d6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001e2db  mov     rax, [rbx]
0x18001e2de  lea     rdx, [rbp+57h+var_80]
0x18001e2e2  mov     rcx, rbx
0x18001e2e5  mov     rax, [rax+78h]
0x18001e2e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2ee  mov     ebx, eax
0x18001e2f0  test    eax, eax
0x18001e2f2  js      short loc_18001E354
0x18001e2f4  mov     rcx, [rbp+57h+var_80]
0x18001e2f8  mov     rax, [rcx]
0x18001e2fb  mov     r8, rdi
0x18001e2fe  lea     rdx, [rbp+57h+var_78]
0x18001e302  mov     rax, [rax+18h]
0x18001e306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e30b  mov     ebx, eax
0x18001e30d  test    eax, eax
0x18001e30f  js      short loc_18001E354
0x18001e311  mov     rcx, [rbp+57h+var_80]
0x18001e315  mov     rax, [rcx]
0x18001e318  lea     r8, [rbp+57h+var_70]
0x18001e31c  mov     edi, 409h
0x18001e321  mov     edx, edi
0x18001e323  mov     rax, [rax+28h]
0x18001e327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e32c  mov     rcx, [rbp+57h+var_80]
0x18001e330  mov     rax, [rcx]
0x18001e333  lea     r8, [rbp+57h+var_68]
0x18001e337  mov     edx, edi
0x18001e339  mov     rax, [rax+30h]
0x18001e33d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e342  mov     rdx, [rbp+57h+var_70]
0x18001e346  test    rdx, rdx
0x18001e349  jz      short loc_18001E354
0x18001e34b  mov     rcx, rsi
0x18001e34e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001e353  nop
0x18001e354  xor     r8d, r8d
0x18001e357  mov     dl, 1
0x18001e359  lea     rcx, [rbp+57h+var_60]
0x18001e35d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001e362  nop
0x18001e363  xor     r8d, r8d
0x18001e366  mov     dl, 1
0x18001e368  lea     rcx, [rbp+57h+var_40]
0x18001e36c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001e371  nop
0x18001e372  lea     rcx, [rbp+57h+var_80]
0x18001e376  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001e37b  mov     eax, ebx
0x18001e37d  mov     rcx, [rbp+57h+var_20]
0x18001e381  xor     rcx, rsp; StackCookie
0x18001e384  call    __security_check_cookie
0x18001e389  mov     rbx, [rsp+0A0h+arg_18]
0x18001e391  add     rsp, 90h
0x18001e398  pop     rdi
0x18001e399  pop     rsi
0x18001e39a  pop     rbp
0x18001e39b  retn
```
