# wil::GetModuleFileNameW<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,128>(HINSTANCE__ *)

- ea: `0x18001c040`
- end: `0x18001c100`
- name: `??$GetModuleFileNameW@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0IA@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180023400`

## callees

- `0x180013330`
- `0x18001bbb0`
- `0x18001c040`
- `0x180034ef0`

## string_xrefs

- `0x18001c0ee`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.2.162\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall wil::GetModuleFileNameW<std::wstring,128>(__int64 a1, __int64 a2)
{
  int v3; // eax
  _BYTE v5[8]; // [rsp+30h] [rbp-98h] BYREF
  _QWORD v6[14]; // [rsp+38h] [rbp-90h] BYREF
  __int64 v7; // [rsp+A8h] [rbp-20h] BYREF
  __int64 v8; // [rsp+B0h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  v8 = a2;
  v7 = 0;
  v6[0] = &wistd::__function::__func<_lambda_2d860dc2582dcbaaba41b7ebab4cc740_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v6[1] = &v7;
  v6[2] = &v8;
  v6[13] = v6;
  v3 = wil::AdaptFixedSizeToAllocatedResult<std::wstring,128>(a1, (__int64)v5);
  _mm_lfence();
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x26C,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.2.162\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      (const char *)(unsigned int)v3,
      1);
  return a1;
}

```

## disassembly

```asm
0x18001c040  mov     r11, rsp
0x18001c043  push    rbx
0x18001c044  sub     rsp, 0C0h
0x18001c04b  mov     rax, cs:__security_cookie
0x18001c052  xor     rax, rsp
0x18001c055  mov     [rsp+0C8h+var_10], rax
0x18001c05d  mov     rbx, rcx
0x18001c060  mov     [rsp+0C8h+var_A0], rcx
0x18001c065  xor     eax, eax
0x18001c067  mov     [rsp+0C8h+var_A8], eax
0x18001c06b  xorps   xmm0, xmm0
0x18001c06e  movups  xmmword ptr [rcx], xmm0
0x18001c071  mov     [rcx+10h], rax
0x18001c075  mov     qword ptr [rcx+18h], 7
0x18001c07d  mov     [rcx], ax
0x18001c080  mov     [rsp+0C8h+var_A8], 1; int
0x18001c088  mov     [r11-18h], rdx
0x18001c08c  mov     [r11-20h], rax
0x18001c090  lea     rax, ??_7?$__func@V_lambda_2d860dc2582dcbaaba41b7ebab4cc740_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_2d860dc2582dcbaaba41b7ebab4cc740_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18001c097  mov     [rsp+0C8h+var_90], rax
0x18001c09c  lea     rax, [r11-20h]
0x18001c0a0  mov     [rsp+0C8h+var_88], rax
0x18001c0a5  lea     rax, [r11-18h]
0x18001c0a9  mov     [r11-80h], rax
0x18001c0ad  lea     rax, [rsp+0C8h+var_90]
0x18001c0b2  mov     [r11-28h], rax
0x18001c0b6  lea     rdx, [rsp+0C8h+var_98]
0x18001c0bb  call    ??$AdaptFixedSizeToAllocatedResult@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0IA@@wil@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<std::wstring,128>(std::wstring &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)
0x18001c0c0  lfence
0x18001c0c3  test    eax, eax
0x18001c0c5  js      short loc_18001C0E3
0x18001c0c7  mov     rax, rbx
0x18001c0ca  mov     rcx, [rsp+0C8h+var_10]
0x18001c0d2  xor     rcx, rsp; StackCookie
0x18001c0d5  call    __security_check_cookie
0x18001c0da  add     rsp, 0C0h
0x18001c0e1  pop     rbx
0x18001c0e2  retn
0x18001c0e3  mov     rcx, [rsp+0C8h]; this
0x18001c0eb  mov     r9d, eax; char *
0x18001c0ee  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18001c0f5  mov     edx, 26Ch; void *
0x18001c0fa  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
