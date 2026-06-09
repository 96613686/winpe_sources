# Microsoft::Applications::Experimentation::ExpCommon::handleMessageTask(void)

- ea: `0x140152ca0`
- end: `0x140152f97`
- name: `?handleMessageTask@ExpCommon@Experimentation@Applications@Microsoft@@QEAAXXZ`
- size: `759`
- prototype: `void __fastcall(Microsoft::Applications::Experimentation::ExpCommon *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x14001cd4c`
- `0x14001cd94`
- `0x14001cdc0`
- `0x14003a0f4`
- `0x14003a5c0`
- `0x1400ff188`
- `0x140150138`
- `0x140152458`
- `0x140152ca0`
- `0x140166250`

## string_xrefs

- `0x140152ce3`: `MATSDK.ExpCommonClient`
- `0x140152d12`: `MATSDK.ExpCommonClient`
- `0x140152eca`: `MATSDK.ExpCommonClient`
- `0x140152f14`: `MATSDK.ExpCommonClient`
- `0x140152cdc`: `handleMessageTask: `
- `0x140152d0b`: `handleMessageTask: [Status=%d]`
- `0x140152ec3`: `handleMessageTask: [Status=%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Microsoft::Applications::Experimentation::ExpCommon::handleMessageTask(
        Microsoft::Applications::Experimentation::ExpCommon *this)
{
  int v2; // eax
  int v3; // r9d
  _QWORD *v4; // rax
  _QWORD *v5; // r8
  __int64 v6; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // r9
  int v16; // r9d
  __int64 v17; // rcx
  __int64 v18[2]; // [rsp+40h] [rbp-9h] BYREF
  char v19; // [rsp+50h] [rbp+7h] BYREF
  __int16 v20; // [rsp+51h] [rbp+8h] BYREF
  char v21; // [rsp+53h] [rbp+Ah]
  __int128 v22; // [rsp+58h] [rbp+Fh] BYREF
  __int128 v23; // [rsp+68h] [rbp+1Fh]
  __int64 v24; // [rsp+78h] [rbp+2Fh]

  v2 = Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel;
  if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
  {
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      4,
      "MATSDK.ExpCommonClient",
      "handleMessageTask: ");
    v2 = Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel;
  }
  v3 = *((_DWORD *)this + 6);
  if ( v3 == 2 )
  {
    v18[1] = (__int64)this + 32;
    if ( Mtx_lock((Microsoft::Applications::Experimentation::ExpCommon *)((char *)this + 32)) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)this + 27) == 0x7FFFFFFF )
    {
      *((_DWORD *)this + 27) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v21 = 0;
    v20 = 0;
    v19 = 0;
    v18[0] = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v4 = operator new(0x10u);
    v4[1] = 0;
    *(_QWORD *)&v22 = v4;
    *v4 = &v22;
    if ( Mtx_lock((Microsoft::Applications::Experimentation::ExpCommon *)((char *)this + 112)) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)this + 47) == 0x7FFFFFFF )
    {
      *((_DWORD *)this + 47) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v5 = (_QWORD *)((char *)this + 368);
    if ( &v22 != (__int128 *)((char *)this + 368) )
    {
      v6 = v22;
      *(_QWORD *)&v22 = *v5;
      v7 = (_QWORD *)v22;
      *v5 = v6;
      if ( v7 )
        *v7 = &v22;
      if ( *v5 )
        *(_QWORD *)*v5 = v5;
      v8 = *((_QWORD *)&v22 + 1);
      *((_QWORD *)&v22 + 1) = *((_QWORD *)this + 47);
      *((_QWORD *)this + 47) = v8;
      v9 = v23;
      *(_QWORD *)&v23 = *((_QWORD *)this + 48);
      *((_QWORD *)this + 48) = v9;
      v10 = *((_QWORD *)&v23 + 1);
      *((_QWORD *)&v23 + 1) = *((_QWORD *)this + 49);
      *((_QWORD *)this + 49) = v10;
      v11 = v24;
      v24 = *((_QWORD *)this + 50);
      *((_QWORD *)this + 50) = v11;
    }
    Mtx_unlock((Microsoft::Applications::Experimentation::ExpCommon *)((char *)this + 112));
    Microsoft::Applications::Experimentation::ExpCommon::_HandleMessages(
      this,
      (__int64)&v20,
      (__int64)&v19,
      (__int64)v18 + 4,
      (__int64)v18);
    v14 = *((_QWORD *)this + 69);
    if ( v14 )
    {
      LOBYTE(v12) = HIBYTE(v20);
      LOBYTE(v13) = v20;
      if ( v20 )
      {
        v15 = HIDWORD(v18[0]);
        LOBYTE(v15) = v19;
        (*(void (__fastcall **)(__int64, __int64, __int64, __int64, _DWORD, _DWORD, const char *))(*(_QWORD *)v14 + 32LL))(
          v14,
          v12,
          v13,
          v15,
          HIDWORD(v18[0]),
          v18[0],
          qword_140194AF8);
      }
    }
    v16 = *((_DWORD *)this + 6);
    if ( v16 == 2 )
    {
      v17 = *((_QWORD *)this + 69);
      if ( v17 )
      {
        LOBYTE(v13) = v19;
        LOBYTE(v12) = v21;
        if ( v21 || v19 )
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v17 + 24LL))(v17, v12, v13);
      }
      if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
        Microsoft::Applications::Events::PlatformAbstraction::detail::log(
          4,
          "MATSDK.ExpCommonClient",
          "OnTimerElapsed: messages handled, lock released.");
    }
    else if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
    {
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        4,
        "MATSDK.ExpCommonClient",
        "handleMessageTask: [Status=%d]",
        v16);
    }
    std::deque<Microsoft::Applications::Experimentation::Message>::~deque<Microsoft::Applications::Experimentation::Message>(&v22);
    Mtx_unlock((Microsoft::Applications::Experimentation::ExpCommon *)((char *)this + 32));
  }
  else if ( v2 >= 4 )
  {
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      4,
      "MATSDK.ExpCommonClient",
      "handleMessageTask: [Status=%d]",
      v3);
  }
}

```

## disassembly

```asm
0x140152ca0  mov     [rsp-8+arg_8], rbx
0x140152ca5  mov     [rsp-8+arg_10], rsi
0x140152caa  push    rbp
0x140152cab  push    rdi
0x140152cac  push    r15
0x140152cae  lea     rbp, [rsp-47h]
0x140152cb3  sub     rsp, 90h
0x140152cba  mov     rax, cs:__security_cookie
0x140152cc1  xor     rax, rsp
0x140152cc4  mov     [rbp+57h+var_20], rax
0x140152cc8  mov     rdi, rcx
0x140152ccb  mov     eax, cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140152cd1  mov     r15d, 4
0x140152cd7  cmp     eax, r15d
0x140152cda  jl      short loc_140152CF8
0x140152cdc  lea     r8, aHandlemessaget_0; "handleMessageTask: "
0x140152ce3  lea     rdx, aMatsdkExpcommo; "MATSDK.ExpCommonClient"
0x140152cea  mov     ecx, r15d
0x140152ced  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140152cf2  mov     eax, cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140152cf8  mov     r9d, [rdi+18h]
0x140152cfc  cmp     r9d, 2
0x140152d00  jz      short loc_140152D26
0x140152d02  cmp     eax, r15d
0x140152d05  jl      loc_140152F36
0x140152d0b  lea     r8, aHandlemessaget; "handleMessageTask: [Status=%d]"
0x140152d12  lea     rdx, aMatsdkExpcommo; "MATSDK.ExpCommonClient"
0x140152d19  mov     ecx, r15d
0x140152d1c  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140152d21  jmp     loc_140152F36
0x140152d26  lea     rbx, [rdi+20h]
0x140152d2a  mov     [rbp-1], rbx
0x140152d2e  mov     rcx, rbx; _Mtx_t
0x140152d31  call    _Mtx_lock
0x140152d36  test    eax, eax
0x140152d38  jnz     loc_140152F6F
0x140152d3e  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x140152d45  jz      loc_140152F7A
0x140152d4b  mov     byte ptr [rbp+57h+var_50+2], al
0x140152d4e  mov     byte ptr [rbp+57h+var_50+3], al
0x140152d51  mov     byte ptr [rbp+57h+var_50+1], al
0x140152d54  mov     byte ptr [rbp+57h+var_50], al
0x140152d57  mov     dword ptr [rbp+57h+var_60+4], eax
0x140152d5a  mov     dword ptr [rbp+57h+var_60], eax
0x140152d5d  xorps   xmm0, xmm0
0x140152d60  xor     eax, eax
0x140152d62  movdqu  [rbp+57h+var_48], xmm0
0x140152d67  xorps   xmm1, xmm1
0x140152d6a  movdqu  [rbp+57h+var_38], xmm1
0x140152d6f  mov     [rbp+57h+var_28], rax
0x140152d73  lea     ecx, [rax+10h]; Size
0x140152d76  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140152d7b  mov     qword ptr [rax+8], 0
0x140152d83  mov     qword ptr [rbp+57h+var_48], rax
0x140152d87  lea     rcx, [rbp+57h+var_48]
0x140152d8b  mov     [rax], rcx
0x140152d8e  lea     rcx, [rdi+70h]; _Mtx_t
0x140152d92  call    _Mtx_lock
0x140152d97  test    eax, eax
0x140152d99  jnz     loc_140152F8C
0x140152d9f  cmp     dword ptr [rdi+0BCh], 7FFFFFFFh
0x140152da9  jz      loc_140152F5A
0x140152daf  lea     r8, [rdi+170h]
0x140152db6  lea     rax, [rbp+57h+var_48]
0x140152dba  cmp     rax, r8
0x140152dbd  jz      short loc_140152E24
0x140152dbf  mov     rax, qword ptr [rbp+57h+var_48]
0x140152dc3  mov     rcx, [r8]
0x140152dc6  mov     qword ptr [rbp+57h+var_48], rcx
0x140152dca  mov     [r8], rax
0x140152dcd  test    rcx, rcx
0x140152dd0  jz      short loc_140152DD9
0x140152dd2  lea     rax, [rbp+57h+var_48]
0x140152dd6  mov     [rcx], rax
0x140152dd9  mov     rax, [r8]
0x140152ddc  test    rax, rax
0x140152ddf  jz      short loc_140152DE4
0x140152de1  mov     [rax], r8
0x140152de4  mov     rcx, qword ptr [rbp+57h+var_48+8]
0x140152de8  mov     rax, [r8+8]
0x140152dec  mov     qword ptr [rbp+57h+var_48+8], rax
0x140152df0  mov     [r8+8], rcx
0x140152df4  mov     rdx, qword ptr [rbp+57h+var_38]
0x140152df8  mov     rax, [r8+10h]
0x140152dfc  mov     qword ptr [rbp+57h+var_38], rax
0x140152e00  mov     [r8+10h], rdx
0x140152e04  mov     rdx, qword ptr [rbp+57h+var_38+8]
0x140152e08  mov     rax, [r8+18h]
0x140152e0c  mov     qword ptr [rbp+57h+var_38+8], rax
0x140152e10  mov     [r8+18h], rdx
0x140152e14  mov     rdx, [rbp+57h+var_28]
0x140152e18  mov     rax, [r8+20h]
0x140152e1c  mov     [rbp+57h+var_28], rax
0x140152e20  mov     [r8+20h], rdx
0x140152e24  lea     rcx, [rdi+70h]; _Mtx_t
0x140152e28  call    _Mtx_unlock
0x140152e2d  lea     rax, [rbp+57h+var_60]
0x140152e31  mov     [rsp+0A0h+var_68], rax; __int64
0x140152e36  lea     rax, [rbp+57h+var_60+4]
0x140152e3a  mov     [rsp+0A0h+var_70], rax; __int64
0x140152e3f  lea     rax, [rbp+57h+var_50]
0x140152e43  mov     [rsp+0A0h+var_78], rax; __int64
0x140152e48  lea     rax, [rbp+57h+var_50+1]
0x140152e4c  mov     [rsp+0A0h+var_80], rax; __int64
0x140152e51  lea     r9, [rbp+57h+var_50+3]
0x140152e55  lea     r8, [rbp+57h+var_50+2]
0x140152e59  lea     rdx, [rbp+57h+var_48]
0x140152e5d  mov     rcx, rdi; this
0x140152e60  call    ?_HandleMessages@ExpCommon@Experimentation@Applications@Microsoft@@QEAAXAEAV?$queue@UMessage@Experimentation@Applications@Microsoft@@V?$deque@UMessage@Experimentation@Applications@Microsoft@@V?$allocator@UMessage@Experimentation@Applications@Microsoft@@@std@@@std@@@std@@AEA_N111AEAH2@Z; Microsoft::Applications::Experimentation::ExpCommon::_HandleMessages(std::queue<Microsoft::Applications::Experimentation::Message> &,bool &,bool &,bool &,bool &,int &,int &)
0x140152e65  mov     rcx, [rdi+228h]
0x140152e6c  test    rcx, rcx
0x140152e6f  jz      short loc_140152EB0
0x140152e71  mov     r8b, byte ptr [rbp+57h+var_50+1]
0x140152e75  mov     dl, byte ptr [rbp+57h+var_50+2]
0x140152e78  test    dl, dl
0x140152e7a  jnz     short loc_140152E81
0x140152e7c  test    r8b, r8b
0x140152e7f  jz      short loc_140152EB0
0x140152e81  mov     rax, [rcx]
0x140152e84  lea     r9, qword_140194AF8
0x140152e8b  mov     [rsp+0A0h+var_70], r9
0x140152e90  mov     r9d, dword ptr [rbp+57h+var_60]
0x140152e94  mov     dword ptr [rsp+0A0h+var_78], r9d
0x140152e99  mov     r9d, dword ptr [rbp+57h+var_60+4]
0x140152e9d  mov     dword ptr [rsp+0A0h+var_80], r9d
0x140152ea2  mov     r9b, byte ptr [rbp+57h+var_50]
0x140152ea6  mov     rax, [rax+20h]
0x140152eaa  call    cs:__guard_dispatch_icall_fptr
0x140152eb0  mov     r9d, [rdi+18h]
0x140152eb4  cmp     r9d, 2
0x140152eb8  jz      short loc_140152EDB
0x140152eba  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, r15d; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140152ec1  jl      short loc_140152F24
0x140152ec3  lea     r8, aHandlemessaget; "handleMessageTask: [Status=%d]"
0x140152eca  lea     rdx, aMatsdkExpcommo; "MATSDK.ExpCommonClient"
0x140152ed1  mov     ecx, r15d
0x140152ed4  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140152ed9  jmp     short loc_140152F24
0x140152edb  mov     rcx, [rdi+228h]
0x140152ee2  test    rcx, rcx
0x140152ee5  jz      short loc_140152F04
0x140152ee7  mov     r8b, byte ptr [rbp+57h+var_50]
0x140152eeb  mov     dl, byte ptr [rbp+57h+var_50+3]
0x140152eee  test    dl, dl
0x140152ef0  jnz     short loc_140152EF7
0x140152ef2  test    r8b, r8b
0x140152ef5  jz      short loc_140152F04
0x140152ef7  mov     rax, [rcx]
0x140152efa  mov     rax, [rax+18h]
0x140152efe  call    cs:__guard_dispatch_icall_fptr
0x140152f04  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, r15d; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140152f0b  jl      short loc_140152F24
0x140152f0d  lea     r8, aOntimerelapsed; "OnTimerElapsed: messages handled, lock "...
0x140152f14  lea     rdx, aMatsdkExpcommo; "MATSDK.ExpCommonClient"
0x140152f1b  mov     ecx, r15d
0x140152f1e  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140152f23  nop
0x140152f24  lea     rcx, [rbp+57h+var_48]
0x140152f28  call    ??1?$deque@UMessage@Experimentation@Applications@Microsoft@@V?$allocator@UMessage@Experimentation@Applications@Microsoft@@@std@@@std@@QEAA@XZ; std::deque<Microsoft::Applications::Experimentation::Message>::~deque<Microsoft::Applications::Experimentation::Message>(void)
0x140152f2d  nop
0x140152f2e  mov     rcx, rbx; _Mtx_t
0x140152f31  call    _Mtx_unlock
0x140152f36  mov     rcx, [rbp+57h+var_20]
0x140152f3a  xor     rcx, rsp; StackCookie
0x140152f3d  call    __security_check_cookie
0x140152f42  lea     r11, [rsp+0A0h+var_10]
0x140152f4a  mov     rbx, [r11+28h]
0x140152f4e  mov     rsi, [r11+30h]
0x140152f52  mov     rsp, r11
0x140152f55  pop     r15
0x140152f57  pop     rdi
0x140152f58  pop     rbp
0x140152f59  retn
0x140152f5a  mov     dword ptr [rdi+0BCh], 7FFFFFFEh
0x140152f64  mov     ecx, 6; int
0x140152f69  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x140152f6f  mov     ecx, 5; int
0x140152f74  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x140152f7a  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x140152f81  mov     ecx, 6; int
0x140152f86  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x140152f8c  mov     ecx, 5; int
0x140152f91  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
