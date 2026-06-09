# Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(_SYSTEMTIME const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800218f0`
- end: `0x180021a01`
- name: `?SystemTimeToISO8601String@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBU_SYSTEMTIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001cff4`
- `0x180027b00`

## callees

- `0x1800045d0`
- `0x1800098e7`
- `0x180010764`
- `0x180011220`
- `0x1800192a4`
- `0x1800218f0`

## string_xrefs

- `0x180021972`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(
        unsigned __int16 *a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // r8
  unsigned int v5; // edi
  unsigned __int64 v7; // rdx
  char *v8; // rdi
  __int64 v9; // rbx
  int v10; // [rsp+20h] [rbp-118h]
  int v11; // [rsp+28h] [rbp-110h]
  int v12; // [rsp+30h] [rbp-108h]
  int v13; // [rsp+38h] [rbp-100h]
  int v14; // [rsp+40h] [rbp-F8h]
  unsigned __int16 Src[104]; // [rsp+50h] [rbp-E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v14 = a1[6];
  v13 = a1[5];
  v12 = a1[4];
  v11 = a1[3];
  v10 = a1[1];
  v3 = StringCchPrintfW(Src, 0x64u, L"%04u-%02u-%02uT%02u:%02u:%02uZ", *a1, v10, v11, v12, v13, v14);
  v5 = v3;
  if ( v3 >= 0 )
  {
    v7 = -1;
    do
      ++v7;
    while ( Src[v7] );
    if ( v7 > *(_QWORD *)(a2 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)a2,
        v7,
        v4,
        Src);
    }
    else
    {
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v8 = (char *)a2;
      else
        v8 = *(char **)a2;
      *(_QWORD *)(a2 + 16) = v7;
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
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
      (const char *)(unsigned int)v3);
    return v5;
  }
}

```

## disassembly

```asm
0x1800218f0  mov     [rsp+arg_10], rbx
0x1800218f5  mov     [rsp+arg_18], rsi
0x1800218fa  push    rdi
0x1800218fb  sub     rsp, 130h
0x180021902  mov     rax, cs:__security_cookie
0x180021909  xor     rax, rsp
0x18002190c  mov     [rsp+138h+var_18], rax
0x180021914  mov     rbx, rdx
0x180021917  movzx   eax, word ptr [rcx+0Ch]
0x18002191b  movzx   edx, word ptr [rcx+0Ah]
0x18002191f  movzx   r8d, word ptr [rcx+8]
0x180021924  movzx   r10d, word ptr [rcx+6]
0x180021929  movzx   r11d, word ptr [rcx+2]
0x18002192e  movzx   r9d, word ptr [rcx]
0x180021932  mov     [rsp+138h+var_F8], eax
0x180021936  mov     [rsp+138h+var_100], edx
0x18002193a  mov     [rsp+138h+var_108], r8d
0x18002193f  mov     [rsp+138h+var_110], r10d
0x180021944  mov     [rsp+138h+var_118], r11d; int
0x180021949  lea     r8, a04u02u02ut02u0; "%04u-%02u-%02uT%02u:%02u:%02uZ"
0x180021950  mov     edx, 64h ; 'd'; unsigned __int64
0x180021955  lea     rcx, [rsp+138h+Src]; unsigned __int16 *
0x18002195a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002195f  mov     edi, eax
0x180021961  xor     esi, esi
0x180021963  test    eax, eax
0x180021965  jns     short loc_180021987
0x180021967  mov     rcx, [rsp+138h]; this
0x18002196f  mov     r9d, eax; char *
0x180021972  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180021979  mov     edx, 89h; void *
0x18002197e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021983  mov     eax, edi
0x180021985  jmp     short loc_1800219DB
0x180021987  lea     rax, [rsp+138h+Src]
0x18002198c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180021990  inc     rdx
0x180021993  cmp     [rax+rdx*2], si
0x180021997  jnz     short loc_180021990
0x180021999  cmp     rdx, [rbx+18h]
0x18002199d  ja      short loc_1800219CC
0x18002199f  cmp     qword ptr [rbx+18h], 7
0x1800219a4  jbe     short loc_1800219AB
0x1800219a6  mov     rdi, [rbx]
0x1800219a9  jmp     short loc_1800219AE
0x1800219ab  mov     rdi, rbx
0x1800219ae  mov     [rbx+10h], rdx
0x1800219b2  lea     rbx, [rdx+rdx]
0x1800219b6  mov     r8, rbx; Size
0x1800219b9  lea     rdx, [rsp+138h+Src]; Src
0x1800219be  mov     rcx, rdi; void *
0x1800219c1  call    memmove_0
0x1800219c6  mov     [rbx+rdi], si
0x1800219ca  jmp     short loc_1800219D9
0x1800219cc  lea     r9, [rsp+138h+Src]
0x1800219d1  mov     rcx, rbx
0x1800219d4  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800219d9  xor     eax, eax
0x1800219db  mov     rcx, [rsp+138h+var_18]
0x1800219e3  xor     rcx, rsp; StackCookie
0x1800219e6  call    __security_check_cookie
0x1800219eb  lea     r11, [rsp+138h+var_8]
0x1800219f3  mov     rbx, [r11+20h]
0x1800219f7  mov     rsi, [r11+28h]
0x1800219fb  mov     rsp, r11
0x1800219fe  pop     rdi
0x1800219ff  retn
```
