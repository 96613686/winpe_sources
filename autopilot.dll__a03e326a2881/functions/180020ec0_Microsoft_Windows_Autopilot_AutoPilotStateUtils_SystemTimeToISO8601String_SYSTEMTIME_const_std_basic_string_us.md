# Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(_SYSTEMTIME const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180020ec0`
- end: `0x180020fd0`
- name: `?SystemTimeToISO8601String@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBU_SYSTEMTIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001c894`
- `0x180026b60`

## callees

- `0x1800045b0`
- `0x180009957`
- `0x1800105f4`
- `0x180011224`
- `0x180018cd0`
- `0x180020ec0`

## string_xrefs

- `0x180020f42`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(
        unsigned __int16 *a1,
        char **a2)
{
  int v3; // eax
  __int64 v4; // r8
  unsigned int v5; // edi
  unsigned __int64 v7; // rdx
  char *v8; // rdi
  __int64 v9; // rbx
  int v10; // [rsp+20h] [rbp-118h]
  unsigned __int16 Src[104]; // [rsp+50h] [rbp-E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v10 = a1[1];
  v3 = StringCchPrintfW(Src, 0x64u, L"%04u-%02u-%02uT%02u:%02u:%02uZ", *a1);
  v5 = v3;
  if ( v3 >= 0 )
  {
    v7 = -1;
    do
      ++v7;
    while ( Src[v7] );
    if ( v7 > (unsigned __int64)a2[3] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a2, v7, v4, Src);
    }
    else
    {
      if ( (unsigned __int64)a2[3] <= 7 )
        v8 = (char *)a2;
      else
        v8 = *a2;
      a2[2] = (char *)v7;
      v9 = 2 * v7;
      memmove_0(v8, Src, 2 * v7);
      *(_WORD *)&v8[v9] = 0;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
      (const char *)(unsigned int)v3,
      v10);
    return v5;
  }
}

```

## disassembly

```asm
0x180020ec0  mov     [rsp+arg_10], rbx
0x180020ec5  mov     [rsp+arg_18], rsi
0x180020eca  push    rdi
0x180020ecb  sub     rsp, 130h
0x180020ed2  mov     rax, cs:__security_cookie
0x180020ed9  xor     rax, rsp
0x180020edc  mov     [rsp+138h+var_18], rax
0x180020ee4  mov     rbx, rdx
0x180020ee7  movzx   eax, word ptr [rcx+0Ch]
0x180020eeb  movzx   edx, word ptr [rcx+0Ah]
0x180020eef  movzx   r8d, word ptr [rcx+8]
0x180020ef4  movzx   r10d, word ptr [rcx+6]
0x180020ef9  movzx   r11d, word ptr [rcx+2]
0x180020efe  movzx   r9d, word ptr [rcx]
0x180020f02  mov     [rsp+138h+var_F8], eax
0x180020f06  mov     [rsp+138h+var_100], edx
0x180020f0a  mov     [rsp+138h+var_108], r8d
0x180020f0f  mov     [rsp+138h+var_110], r10d
0x180020f14  mov     [rsp+138h+var_118], r11d; int
0x180020f19  lea     r8, a04u02u02ut02u0; "%04u-%02u-%02uT%02u:%02u:%02uZ"
0x180020f20  mov     edx, 64h ; 'd'; unsigned __int64
0x180020f25  lea     rcx, [rsp+138h+Src]; unsigned __int16 *
0x180020f2a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020f2f  mov     edi, eax
0x180020f31  xor     esi, esi
0x180020f33  test    eax, eax
0x180020f35  jns     short loc_180020F57
0x180020f37  mov     rcx, [rsp+138h]; this
0x180020f3f  mov     r9d, eax; char *
0x180020f42  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180020f49  mov     edx, 89h; void *
0x180020f4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020f53  mov     eax, edi
0x180020f55  jmp     short loc_180020FAB
0x180020f57  lea     rax, [rsp+138h+Src]
0x180020f5c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180020f60  inc     rdx
0x180020f63  cmp     [rax+rdx*2], si
0x180020f67  jnz     short loc_180020F60
0x180020f69  cmp     rdx, [rbx+18h]
0x180020f6d  ja      short loc_180020F9C
0x180020f6f  cmp     qword ptr [rbx+18h], 7
0x180020f74  jbe     short loc_180020F7B
0x180020f76  mov     rdi, [rbx]
0x180020f79  jmp     short loc_180020F7E
0x180020f7b  mov     rdi, rbx
0x180020f7e  mov     [rbx+10h], rdx
0x180020f82  lea     rbx, [rdx+rdx]
0x180020f86  mov     r8, rbx; Size
0x180020f89  lea     rdx, [rsp+138h+Src]; Src
0x180020f8e  mov     rcx, rdi; void *
0x180020f91  call    memmove_0
0x180020f96  mov     [rbx+rdi], si
0x180020f9a  jmp     short loc_180020FA9
0x180020f9c  lea     r9, [rsp+138h+Src]
0x180020fa1  mov     rcx, rbx
0x180020fa4  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180020fa9  xor     eax, eax
0x180020fab  mov     rcx, [rsp+138h+var_18]
0x180020fb3  xor     rcx, rsp; StackCookie
0x180020fb6  call    __security_check_cookie
0x180020fbb  lea     r11, [rsp+138h+var_8]
0x180020fc3  mov     rbx, [r11+20h]
0x180020fc7  mov     rsi, [r11+28h]
0x180020fcb  mov     rsp, r11
0x180020fce  pop     rdi
0x180020fcf  retn
```
