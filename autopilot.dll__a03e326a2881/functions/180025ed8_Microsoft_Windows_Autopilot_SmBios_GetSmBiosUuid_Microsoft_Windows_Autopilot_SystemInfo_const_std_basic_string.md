# Microsoft::Windows::Autopilot::SmBios::GetSmBiosUuid(Microsoft::Windows::Autopilot::SystemInfo const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180025ed8`
- end: `0x180025fd3`
- name: `?GetSmBiosUuid@SmBios@Autopilot@Windows@Microsoft@@SAJPEBUSystemInfo@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180025b90`

## callees

- `0x1800045b0`
- `0x180005374`
- `0x180009957`
- `0x1800105f4`
- `0x180018cd0`
- `0x180025ed8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180025f29`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180025f29`

## string_xrefs

- `0x180025f3d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\smbios.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::SmBios::GetSmBiosUuid(__int64 a1, char **a2)
{
  __int64 v3; // r8
  unsigned __int64 v5; // rdx
  char *v6; // rdi
  __int64 v7; // rbx
  GUID rguid; // [rsp+20h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  rguid = *(GUID *)(a1 + 8);
  memset_0(sz, 0, 0x4Eu);
  if ( StringFromGUID2(&rguid, sz, 39) )
  {
    v5 = -1;
    do
      ++v5;
    while ( sz[v5] );
    if ( v5 > (unsigned __int64)a2[3] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a2, v5, v3, sz);
    }
    else
    {
      if ( (unsigned __int64)a2[3] <= 7 )
        v6 = (char *)a2;
      else
        v6 = *a2;
      a2[2] = (char *)v5;
      v7 = 2 * v5;
      memmove_0(v6, sz, 2 * v5);
      *(_WORD *)&v6[v7] = 0;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\smbios.cpp",
      (const char *)0x8000FFFFLL,
      rguid.Data1);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x180025ed8  mov     [rsp+arg_10], rbx
0x180025edd  mov     [rsp+arg_18], rsi
0x180025ee2  push    rdi
0x180025ee3  sub     rsp, 90h
0x180025eea  mov     rax, cs:__security_cookie
0x180025ef1  xor     rax, rsp
0x180025ef4  mov     [rsp+98h+var_18], rax
0x180025efc  movups  xmm0, xmmword ptr [rcx+8]
0x180025f00  mov     rbx, rdx
0x180025f03  lea     rcx, [rsp+98h+sz]; void *
0x180025f08  xor     edx, edx; Val
0x180025f0a  movdqu  xmmword ptr [rsp+98h+rguid.Data1], xmm0; int
0x180025f10  lea     r8d, [rdx+4Eh]; Size
0x180025f14  call    memset_0
0x180025f19  mov     r8d, 27h ; '''; cchMax
0x180025f1f  lea     rdx, [rsp+98h+sz]; lpsz
0x180025f24  lea     rcx, [rsp+98h+rguid]; rguid
0x180025f29  call    cs:__imp_StringFromGUID2
0x180025f2f  xor     esi, esi
0x180025f31  test    eax, eax
0x180025f33  jnz     short loc_180025F5A
0x180025f35  mov     rcx, [rsp+98h]; this
0x180025f3d  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025f44  mov     ebx, 8000FFFFh
0x180025f49  mov     edx, 132h; void *
0x180025f4e  mov     r9d, ebx; char *
0x180025f51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025f56  mov     eax, ebx
0x180025f58  jmp     short loc_180025FAE
0x180025f5a  lea     rax, [rsp+98h+sz]
0x180025f5f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180025f63  inc     rdx
0x180025f66  cmp     [rax+rdx*2], si
0x180025f6a  jnz     short loc_180025F63
0x180025f6c  cmp     rdx, [rbx+18h]
0x180025f70  ja      short loc_180025F9F
0x180025f72  cmp     qword ptr [rbx+18h], 7
0x180025f77  jbe     short loc_180025F7E
0x180025f79  mov     rdi, [rbx]
0x180025f7c  jmp     short loc_180025F81
0x180025f7e  mov     rdi, rbx
0x180025f81  mov     [rbx+10h], rdx
0x180025f85  mov     rcx, rdi; void *
0x180025f88  lea     rbx, [rdx+rdx]
0x180025f8c  mov     r8, rbx; Size
0x180025f8f  lea     rdx, [rsp+98h+sz]; Src
0x180025f94  call    memmove_0
0x180025f99  mov     [rbx+rdi], si
0x180025f9d  jmp     short loc_180025FAC
0x180025f9f  lea     r9, [rsp+98h+sz]
0x180025fa4  mov     rcx, rbx
0x180025fa7  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180025fac  xor     eax, eax
0x180025fae  mov     rcx, [rsp+98h+var_18]
0x180025fb6  xor     rcx, rsp; StackCookie
0x180025fb9  call    __security_check_cookie
0x180025fbe  lea     r11, [rsp+98h+var_8]
0x180025fc6  mov     rbx, [r11+20h]
0x180025fca  mov     rsi, [r11+28h]
0x180025fce  mov     rsp, r11
0x180025fd1  pop     rdi
0x180025fd2  retn
```
