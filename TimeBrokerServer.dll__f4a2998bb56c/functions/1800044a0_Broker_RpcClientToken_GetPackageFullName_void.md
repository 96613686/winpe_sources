# Broker::RpcClientToken::GetPackageFullName(void)

- ea: `0x1800044a0`
- end: `0x180004614`
- name: `?GetPackageFullName@RpcClientToken@Broker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `372`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800042e8`

## callees

- `0x180003800`
- `0x1800044a0`
- `0x180011240`
- `0x18001154c`
- `0x180011758`
- `0x180012dd0`
- `0x18001396c`
- `0x180013978`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000458f`
- `ntdll!RtlNtStatusToDosError` at `0x18000458f`
- `ntdll!RtlQueryPackageIdentity` at `0x180004521`
- `ntdll!RtlQueryPackageIdentity` at `0x180004521`

## pseudocode

```c
__int64 __fastcall Broker::RpcClientToken::GetPackageFullName(__int64 a1, __int64 a2)
{
  NTSTATUS v4; // eax
  __int64 v6; // r8
  ULONG v7; // eax
  char v8[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v9; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v10; // [rsp+48h] [rbp-B8h] BYREF
  void **v11; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v12; // [rsp+58h] [rbp-A8h]
  int v13; // [rsp+68h] [rbp-98h]
  ULONG v14; // [rsp+70h] [rbp-90h]
  _QWORD pExceptionObject[3]; // [rsp+78h] [rbp-88h] BYREF
  int v16; // [rsp+90h] [rbp-70h]
  ULONG v17; // [rsp+98h] [rbp-68h]
  _WORD v18[128]; // [rsp+A0h] [rbp-60h] BYREF
  char v19[144]; // [rsp+1A0h] [rbp+A0h] BYREF

  v9 = 256;
  v10 = 130;
  v8[0] = 0;
  memset_0(v18, 0, sizeof(v18));
  v4 = ((__int64 (__fastcall *)(_QWORD, _WORD *, __int64 *, char *, __int64 *, char *))RtlQueryPackageIdentity)(
         *(_QWORD *)(a1 + 8),
         v18,
         &v9,
         v19,
         &v10,
         v8);
  if ( v4 >= 0 )
  {
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 0;
    v6 = -1;
    do
      ++v6;
    while ( v18[v6] );
    std::wstring::_Construct<1,unsigned short const *>(a2, v18);
  }
  else
  {
    if ( v4 != -1073741275 )
    {
      v7 = RtlNtStatusToDosError(v4);
      v12 = 0;
      v13 = 1;
      v11 = &Broker::Win32Error::`vftable';
      v14 = v7;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v7);
      std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)&v11);
      v16 = v13;
      pExceptionObject[0] = &Broker::Win32Error::`vftable';
      v17 = v14;
      throw (Broker::Win32Error *)pExceptionObject;
    }
    std::wstring::wstring(a2);
  }
  return a2;
}

```

## disassembly

```asm
0x1800044a0  mov     [rsp-8+arg_10], rbx
0x1800044a5  push    rbp
0x1800044a6  push    rsi
0x1800044a7  push    rdi
0x1800044a8  lea     rbp, [rsp-140h]
0x1800044b0  sub     rsp, 240h
0x1800044b7  mov     rax, cs:__security_cookie
0x1800044be  xor     rax, rsp
0x1800044c1  mov     [rbp+150h+var_20], rax
0x1800044c8  mov     rdi, rdx
0x1800044cb  mov     rbx, rcx
0x1800044ce  mov     [rsp+250h+var_218], rdx
0x1800044d3  xor     esi, esi
0x1800044d5  mov     r8d, 100h; Size
0x1800044db  mov     [rsp+250h+var_218], r8
0x1800044e0  mov     [rsp+250h+var_208], 82h
0x1800044e9  mov     [rsp+250h+var_220], sil
0x1800044ee  xor     edx, edx; Val
0x1800044f0  lea     rcx, [rbp+150h+var_1B0]; void *
0x1800044f4  call    memset_0
0x1800044f9  lea     rax, [rsp+250h+var_220]
0x1800044fe  mov     [rsp+250h+var_228], rax
0x180004503  lea     rax, [rsp+250h+var_208]
0x180004508  mov     [rsp+250h+var_230], rax
0x18000450d  lea     r9, [rbp+150h+var_B0]
0x180004514  lea     r8, [rsp+250h+var_218]
0x180004519  lea     rdx, [rbp+150h+var_1B0]
0x18000451d  mov     rcx, [rbx+8]
0x180004521  call    cs:__imp_RtlQueryPackageIdentity
0x180004527  test    eax, eax
0x180004529  jns     short loc_18000455F
0x18000452b  cmp     eax, 0C0000225h
0x180004530  jnz     short loc_18000458D
0x180004532  mov     rcx, rdi
0x180004535  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000453a  mov     rax, rdi
0x18000453d  mov     rcx, [rbp+150h+var_20]
0x180004544  xor     rcx, rsp; StackCookie
0x180004547  call    __security_check_cookie
0x18000454c  mov     rbx, [rsp+250h+arg_10]
0x180004554  add     rsp, 240h
0x18000455b  pop     rdi
0x18000455c  pop     rsi
0x18000455d  pop     rbp
0x18000455e  retn
0x18000455f  xorps   xmm0, xmm0
0x180004562  movups  xmmword ptr [rdi], xmm0
0x180004565  mov     [rdi+10h], rsi
0x180004569  mov     [rdi+18h], rsi
0x18000456d  lea     rax, [rbp+150h+var_1B0]
0x180004571  or      r8, 0FFFFFFFFFFFFFFFFh
0x180004575  inc     r8
0x180004578  cmp     [rax+r8*2], si
0x18000457d  jnz     short loc_180004575
0x18000457f  lea     rdx, [rbp+150h+var_1B0]
0x180004583  mov     rcx, rdi
0x180004586  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000458b  jmp     short loc_18000453A
0x18000458d  mov     ecx, eax; Status
0x18000458f  call    cs:__imp_RtlNtStatusToDosError
0x180004595  xorps   xmm0, xmm0
0x180004598  movups  [rsp+250h+var_1F8], xmm0
0x18000459d  mov     [rsp+250h+var_1E8], 1
0x1800045a5  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800045ac  mov     [rsp+250h+var_200], rbx
0x1800045b1  mov     [rsp+250h+var_1E0], eax
0x1800045b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045bc  test    byte ptr [rcx+1Ch], 8
0x1800045c0  jz      short loc_1800045E0
0x1800045c2  cmp     byte ptr [rcx+19h], 2
0x1800045c6  jb      short loc_1800045E0
0x1800045c8  mov     edx, 16h
0x1800045cd  mov     r9d, eax
0x1800045d0  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x1800045d7  mov     rcx, [rcx+10h]
0x1800045db  call    WPP_SF_d
0x1800045e0  lea     rdx, [rsp+250h+var_200]; struct std::exception *
0x1800045e5  lea     rcx, [rsp+250h+pExceptionObject]; this
0x1800045ea  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x1800045ef  mov     eax, [rsp+250h+var_1E8]
0x1800045f3  mov     [rbp+150h+var_1C0], eax
0x1800045f6  mov     [rsp+250h+pExceptionObject], rbx
0x1800045fb  mov     eax, [rsp+250h+var_1E0]
0x1800045ff  mov     [rbp+150h+var_1B8], eax
0x180004602  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180004609  lea     rcx, [rsp+250h+pExceptionObject]; pExceptionObject
0x18000460e  call    _CxxThrowException_0
```
