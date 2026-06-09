# Broker::RpcClientToken::GetPackageFullName(void)

- ea: `0x18000b180`
- end: `0x18000b333`
- name: `?GetPackageFullName@RpcClientToken@Broker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `435`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009340`
- `0x180009740`
- `0x18000a7d0`
- `0x18000cc40`
- `0x18000ec10`

## callees

- `0x1800030e0`
- `0x18000b180`
- `0x18001a230`
- `0x18001ab64`
- `0x18001cf50`
- `0x18001d8ae`
- `0x18001d9a0`
- `0x18001d9ac`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000b257`
- `ntdll!RtlNtStatusToDosError` at `0x18000b257`
- `ntdll!RtlQueryPackageIdentity` at `0x18000b205`
- `ntdll!RtlQueryPackageIdentity` at `0x18000b205`

## pseudocode

```c
__int64 __fastcall Broker::RpcClientToken::GetPackageFullName(__int64 a1, __int64 a2)
{
  NTSTATUS v4; // eax
  ULONG v6; // eax
  __int64 v7; // r8
  char v8[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v9; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v10[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v11; // [rsp+58h] [rbp-A8h] BYREF
  int v12; // [rsp+68h] [rbp-98h]
  ULONG v13; // [rsp+70h] [rbp-90h]
  void **pExceptionObject; // [rsp+78h] [rbp-88h] BYREF
  __int128 v15; // [rsp+80h] [rbp-80h]
  int v16; // [rsp+90h] [rbp-70h]
  ULONG v17; // [rsp+98h] [rbp-68h]
  _WORD v18[128]; // [rsp+A0h] [rbp-60h] BYREF
  char v19[144]; // [rsp+1A0h] [rbp+A0h] BYREF

  v9 = 256;
  v10[0] = 130;
  v8[0] = 0;
  memset_0(v18, 0, sizeof(v18));
  v4 = ((__int64 (__fastcall *)(_QWORD, _WORD *, __int64 *, char *, _QWORD *, char *))RtlQueryPackageIdentity)(
         *(_QWORD *)(a1 + 8),
         v18,
         &v9,
         v19,
         v10,
         v8);
  if ( v4 >= 0 )
  {
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 0;
    v7 = -1;
    do
      ++v7;
    while ( v18[v7] );
    std::wstring::_Construct<1,unsigned short const *>(a2, v18);
  }
  else
  {
    if ( v4 != -1073741275 )
    {
      v6 = RtlNtStatusToDosError(v4);
      v11 = 0;
      v12 = 1;
      v10[1] = &Broker::Win32Error::`vftable';
      v13 = v6;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v6);
      pExceptionObject = &std::exception::`vftable';
      v15 = 0;
      o___std_exception_copy_0(&v11);
      v16 = v12;
      pExceptionObject = &Broker::Win32Error::`vftable';
      v17 = v13;
      throw (Broker::Win32Error *)&pExceptionObject;
    }
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 0;
    std::wstring::_Construct_empty(a2);
  }
  return a2;
}

```

## disassembly

```asm
0x18000b180  mov     [rsp-8+arg_10], rbx
0x18000b185  push    rbp
0x18000b186  push    rsi
0x18000b187  push    rdi
0x18000b188  lea     rbp, [rsp-140h]
0x18000b190  sub     rsp, 240h
0x18000b197  mov     rax, cs:__security_cookie
0x18000b19e  xor     rax, rsp
0x18000b1a1  mov     [rbp+150h+var_20], rax
0x18000b1a8  mov     rbx, rdx
0x18000b1ab  mov     rdi, rcx
0x18000b1ae  mov     [rsp+250h+var_218], rdx
0x18000b1b3  xor     esi, esi
0x18000b1b5  mov     [rsp+250h+var_218], 100h
0x18000b1be  mov     [rsp+250h+var_208], 82h
0x18000b1c7  mov     [rsp+250h+var_220], sil
0x18000b1cc  xor     edx, edx; Val
0x18000b1ce  mov     r8d, 100h; Size
0x18000b1d4  lea     rcx, [rbp+150h+var_1B0]; void *
0x18000b1d8  call    memset_0
0x18000b1dd  lea     rax, [rsp+250h+var_220]
0x18000b1e2  mov     [rsp+250h+var_228], rax
0x18000b1e7  lea     rax, [rsp+250h+var_208]
0x18000b1ec  mov     [rsp+250h+var_230], rax
0x18000b1f1  lea     r9, [rbp+150h+var_B0]
0x18000b1f8  lea     r8, [rsp+250h+var_218]
0x18000b1fd  lea     rdx, [rbp+150h+var_1B0]
0x18000b201  mov     rcx, [rdi+8]
0x18000b205  call    cs:__imp_RtlQueryPackageIdentity
0x18000b20b  test    eax, eax
0x18000b20d  jns     loc_18000B2D4
0x18000b213  cmp     eax, 0C0000225h
0x18000b218  jnz     short loc_18000B255
0x18000b21a  xorps   xmm0, xmm0
0x18000b21d  movups  xmmword ptr [rbx], xmm0
0x18000b220  mov     [rbx+10h], rsi
0x18000b224  mov     [rbx+18h], rsi
0x18000b228  mov     rcx, rbx
0x18000b22b  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000b230  mov     rax, rbx
0x18000b233  mov     rcx, [rbp+150h+var_20]
0x18000b23a  xor     rcx, rsp; StackCookie
0x18000b23d  call    __security_check_cookie
0x18000b242  mov     rbx, [rsp+250h+arg_10]
0x18000b24a  add     rsp, 240h
0x18000b251  pop     rdi
0x18000b252  pop     rsi
0x18000b253  pop     rbp
0x18000b254  retn
0x18000b255  mov     ecx, eax; Status
0x18000b257  call    cs:__imp_RtlNtStatusToDosError
0x18000b25d  xorps   xmm0, xmm0
0x18000b260  movups  [rsp+250h+var_1F8], xmm0
0x18000b265  mov     [rsp+250h+var_1E8], 1
0x18000b26d  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000b274  mov     [rsp+250h+var_200], rbx
0x18000b279  mov     [rsp+250h+var_1E0], eax
0x18000b27d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b284  test    byte ptr [rcx+1Ch], 8
0x18000b288  jnz     loc_18000B30B
0x18000b28e  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18000b295  mov     [rsp+250h+pExceptionObject], rax
0x18000b29a  xorps   xmm0, xmm0
0x18000b29d  movups  [rbp+150h+var_1D0], xmm0
0x18000b2a1  lea     rdx, [rbp+150h+var_1D0]
0x18000b2a5  lea     rcx, [rsp+250h+var_1F8]
0x18000b2aa  call    _o___std_exception_copy_0
0x18000b2af  mov     eax, [rsp+250h+var_1E8]
0x18000b2b3  mov     [rbp+150h+var_1C0], eax
0x18000b2b6  mov     [rsp+250h+pExceptionObject], rbx
0x18000b2bb  mov     eax, [rsp+250h+var_1E0]
0x18000b2bf  mov     [rbp+150h+var_1B8], eax
0x18000b2c2  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000b2c9  lea     rcx, [rsp+250h+pExceptionObject]; pExceptionObject
0x18000b2ce  call    _CxxThrowException_0
0x18000b2d4  xorps   xmm0, xmm0
0x18000b2d7  movups  xmmword ptr [rbx], xmm0
0x18000b2da  mov     [rbx+10h], rsi
0x18000b2de  mov     [rbx+18h], rsi
0x18000b2e2  lea     rax, [rbp+150h+var_1B0]
0x18000b2e6  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000b2ed  nop     dword ptr [rax]
0x18000b2f0  inc     r8
0x18000b2f3  cmp     [rax+r8*2], si
0x18000b2f8  jnz     short loc_18000B2F0
0x18000b2fa  lea     rdx, [rbp+150h+var_1B0]
0x18000b2fe  mov     rcx, rbx
0x18000b301  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000b306  jmp     loc_18000B230
0x18000b30b  cmp     byte ptr [rcx+19h], 2
0x18000b30f  jb      loc_18000B28E
0x18000b315  mov     edx, 16h
0x18000b31a  mov     r9d, eax
0x18000b31d  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000b324  mov     rcx, [rcx+10h]
0x18000b328  call    WPP_SF_d
0x18000b32d  jmp     loc_18000B28E
```
