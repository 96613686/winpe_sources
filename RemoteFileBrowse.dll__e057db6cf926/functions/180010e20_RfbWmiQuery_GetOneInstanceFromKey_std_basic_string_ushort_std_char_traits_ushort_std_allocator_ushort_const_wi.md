# RfbWmiQuery::GetOneInstanceFromKey(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)

- ea: `0x180010e20`
- end: `0x180010f7a`
- name: `?GetOneInstanceFromKey@RfbWmiQuery@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014910`

## callees

- `0x180002030`
- `0x18000591c`
- `0x180009520`
- `0x18000cd18`
- `0x18000d5c4`
- `0x180010e20`
- `0x180017174`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall RfbWmiQuery::GetOneInstanceFromKey(__int64 a1, __int64 a2, __int64 a3)
{
  wchar_t *v5; // rdx
  const unsigned __int16 *v6; // rdx
  const struct _MI_Instance *OperationInstance; // rcx
  unsigned __int16 **v9; // rax
  RfbServer *v10; // [rsp+30h] [rbp-58h]
  volatile signed __int32 *v11; // [rsp+38h] [rbp-50h]
  _MI_Operation v12; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int16 *Src[3]; // [rsp+58h] [rbp-30h] BYREF
  unsigned __int64 v14; // [rsp+70h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v5 = (wchar_t *)(a1 + 96);
  if ( *(_QWORD *)(a1 + 120) > 7u )
    v5 = *(wchar_t **)v5;
  FormatString(Src, v5);
  RfbServerRegistrar::GetWmiConnection(*(PSRWLOCK *)(a1 + 176));
  try
  {
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
      memset(&v12, 0, sizeof(v12));
      v6 = (const unsigned __int16 *)Src;
      if ( v14 > 7 )
        v6 = Src[0];
      RfbServer::ExecQuery(v10, v6, &v12);
      OperationInstance = GetOperationInstance(&v12);
      if ( OperationInstance )
        (*(void (__fastcall **)(__int64, const struct _MI_Instance *, __int64))(*(_QWORD *)a1 + 32LL))(
          a1,
          OperationInstance,
          a3);
      if ( v12.ft )
        ((void (__fastcall *)(_MI_Operation *))v12.ft->Close)(&v12);
    }
    if ( v11 )
    {
      if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)())v11)();
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)())(*(_QWORD *)v11 + 8LL))();
      }
    }
  }
  catch ( ... )
  {
    v9 = Src;
    if ( v14 > 7 )
      v9 = (unsigned __int16 **)Src[0];
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0xF2,
      (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbwmiquery.cpp",
      "query %ls failed",
      (const char *)v9);
  }
  return std::wstring::~wstring((char **)Src);
}

```

## disassembly

```asm
0x180010e20  mov     [rsp+arg_18], rbx
0x180010e25  push    rsi
0x180010e26  sub     rsp, 80h
0x180010e2d  mov     rax, cs:__security_cookie
0x180010e34  xor     rax, rsp
0x180010e37  mov     [rsp+88h+var_10], rax
0x180010e3c  mov     rsi, r8
0x180010e3f  mov     r8, rdx
0x180010e42  mov     rbx, rcx
0x180010e45  cmp     qword ptr [rdx+18h], 7
0x180010e4a  jbe     short loc_180010E4F
0x180010e4c  mov     r8, [rdx]
0x180010e4f  lea     rdx, [rcx+60h]
0x180010e53  cmp     qword ptr [rdx+18h], 7
0x180010e58  jbe     short loc_180010E5D
0x180010e5a  mov     rdx, [rdx]; Format
0x180010e5d  lea     rcx, [rsp+88h+Src]; Src
0x180010e62  call    ?FormatString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; FormatString(ushort const *,...)
0x180010e67  nop
0x180010e68  lea     r8, [rbx+90h]
0x180010e6f  lea     rdx, [rsp+88h+var_58]
0x180010e74  mov     rcx, [rbx+0B0h]; SRWLock
0x180010e7b  call    ?GetWmiConnection@RfbServerRegistrar@@QEBA?AV?$shared_ptr@VRfbServer@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; RfbServerRegistrar::GetWmiConnection(std::wstring const &)
0x180010e80  nop
0x180010e81  cmp     [rsp+88h+var_58], 0
0x180010e87  jz      loc_180010F10
0x180010e8d  mov     rax, [rbx]
0x180010e90  mov     rdx, [rsp+88h+var_58]
0x180010e95  mov     rcx, rbx
0x180010e98  mov     rax, [rax+18h]
0x180010e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ea1  xorps   xmm0, xmm0
0x180010ea4  xor     eax, eax
0x180010ea6  movups  xmmword ptr [rsp+88h+var_48.reserved1], xmm0
0x180010eab  mov     [rsp+88h+var_48.ft], rax
0x180010eb0  lea     rdx, [rsp+88h+Src]
0x180010eb5  cmp     [rsp+88h+var_18], 7
0x180010ebb  cmova   rdx, [rsp+88h+Src]; unsigned __int16 *
0x180010ec1  lea     r8, [rsp+88h+var_48]; struct _MI_Operation *
0x180010ec6  mov     rcx, [rsp+88h+var_58]; this
0x180010ecb  call    ?ExecQuery@RfbServer@@QEAAXPEBGPEAU_MI_Operation@@@Z; RfbServer::ExecQuery(ushort const *,_MI_Operation *)
0x180010ed0  lea     rcx, [rsp+88h+var_48]; struct _MI_Operation *
0x180010ed5  call    ?GetOperationInstance@@YAPEBU_MI_Instance@@PEAU_MI_Operation@@@Z; GetOperationInstance(_MI_Operation *)
0x180010eda  mov     rcx, rax
0x180010edd  test    rax, rax
0x180010ee0  jz      short loc_180010EF8
0x180010ee2  mov     rdx, [rbx]
0x180010ee5  mov     rax, [rdx+20h]
0x180010ee9  mov     r8, rsi
0x180010eec  mov     rdx, rcx
0x180010eef  mov     rcx, rbx
0x180010ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ef7  nop
0x180010ef8  mov     rax, [rsp+88h+var_48.ft]
0x180010efd  test    rax, rax
0x180010f00  jz      short loc_180010F10
0x180010f02  lea     rcx, [rsp+88h+var_48]
0x180010f07  mov     rax, [rax]
0x180010f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f0f  nop
0x180010f10  mov     rbx, [rsp+88h+var_50]
0x180010f15  test    rbx, rbx
0x180010f18  jz      short loc_180010F52
0x180010f1a  or      eax, 0FFFFFFFFh
0x180010f1d  lock xadd [rbx+8], eax
0x180010f22  cmp     eax, 1
0x180010f25  jnz     short loc_180010F52
0x180010f27  mov     rax, [rbx]
0x180010f2a  mov     rcx, rbx
0x180010f2d  mov     rax, [rax]
0x180010f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f35  or      eax, 0FFFFFFFFh
0x180010f38  lock xadd [rbx+0Ch], eax
0x180010f3d  cmp     eax, 1
0x180010f40  jnz     short loc_180010F52
0x180010f42  mov     rax, [rbx]
0x180010f45  mov     rcx, rbx
0x180010f48  mov     rax, [rax+8]
0x180010f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f51  nop
0x180010f52  lea     rcx, [rsp+88h+Src]
0x180010f57  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010f5c  mov     rcx, [rsp+88h+var_10]
0x180010f61  xor     rcx, rsp; StackCookie
0x180010f64  call    __security_check_cookie
0x180010f69  mov     rbx, [rsp+88h+arg_18]
0x180010f71  add     rsp, 80h
0x180010f78  pop     rsi
0x180010f79  retn
```
