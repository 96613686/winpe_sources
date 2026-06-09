# FwCopyHyperVRule

- ea: `0x180007e80`
- end: `0x180008196`
- name: `FwCopyHyperVRule`
- size: `790`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800042c4`
- `0x180007e80`
- `0x1800087b0`
- `0x1800088a0`
- `0x18001ffd4`

## import_xrefs

- `fwbase!FwAlloc` at `0x180007ea3`
- `fwbase!FwAlloc` at `0x180007ea3`
- `fwbase!FwArrayCopy` at `0x180007feb`
- `fwbase!FwArrayCopy` at `0x18000805c`
- `fwbase!FwArrayCopy` at `0x180007feb`
- `fwbase!FwArrayCopy` at `0x18000805c`
- `fwbase!FwStringCopy` at `0x180007f0e`
- `fwbase!FwStringCopy` at `0x180007f50`
- `fwbase!FwStringCopy` at `0x180007f0e`
- `fwbase!FwStringCopy` at `0x180007f50`

## pseudocode

```c
__int64 __fastcall FwCopyHyperVRule(__int64 a1, void **a2)
{
  void *v4; // rax
  int v5; // ebx
  LPCOLESTR v6; // rcx
  __int64 v7; // rdx

  *a2 = 0;
  v4 = (void *)FwAlloc(296);
  *a2 = v4;
  if ( !v4 )
  {
    v5 = -2147024882;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_30;
    v7 = 214;
    goto LABEL_29;
  }
  memset_0(v4, 0, 0x128u);
  *(_QWORD *)*a2 = 0;
  *((_WORD *)*a2 + 4) = *(_WORD *)(a1 + 8);
  v5 = FwStringCopy(*(_QWORD *)(a1 + 16), (char *)*a2 + 16);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_30;
    v7 = 215;
    goto LABEL_29;
  }
  v5 = FwStringCopy(*(_QWORD *)(a1 + 24), (char *)*a2 + 24);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_30;
    v7 = 216;
    goto LABEL_29;
  }
  *((_WORD *)*a2 + 16) = *(_WORD *)(a1 + 32);
  *((_DWORD *)*a2 + 9) = *(_DWORD *)(a1 + 36);
  *(_OWORD *)((char *)*a2 + 40) = *(_OWORD *)(a1 + 40);
  *((_WORD *)*a2 + 28) = *(_WORD *)(a1 + 56);
  *((_WORD *)*a2 + 68) = *(_WORD *)(a1 + 136);
  v5 = FwArrayCopy(
         4,
         FwCopyPlatform,
         wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
         a1 + 144,
         (char *)*a2 + 144);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_30;
    v7 = 217;
    goto LABEL_29;
  }
  *((_WORD *)*a2 + 116) = *(_WORD *)(a1 + 232);
  v5 = FwArrayCopy(
         4,
         FwCopyPlatform,
         wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
         a1 + 240,
         (char *)*a2 + 240);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_30;
    v7 = 218;
    goto LABEL_29;
  }
  v5 = FwCopyWFAddressesContents(a1 + 64, (char *)*a2 + 64);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_30;
    v7 = 219;
    goto LABEL_29;
  }
  v5 = FwCopyWFAddressesContents(a1 + 160, (char *)*a2 + 160);
  if ( v5 >= 0 )
  {
    *((_DWORD *)*a2 + 64) = *(_DWORD *)(a1 + 256);
    *((_WORD *)*a2 + 130) = *(_WORD *)(a1 + 260);
    *((_DWORD *)*a2 + 66) = *(_DWORD *)(a1 + 264);
    *((_DWORD *)*a2 + 67) = *(_DWORD *)(a1 + 268);
    *((_DWORD *)*a2 + 72) = *(_DWORD *)(a1 + 288);
    *((_OWORD *)*a2 + 17) = 0;
    return (unsigned int)v5;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v7 = 220;
LABEL_29:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, (unsigned int)v5);
  }
LABEL_30:
  FwFreeHyperVRulesBySchemaVersion(*a2);
  *a2 = 0;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007e80  mov     [rsp+arg_0], rbx
0x180007e85  mov     [rsp+arg_8], rsi
0x180007e8a  push    rdi
0x180007e8b  sub     rsp, 30h
0x180007e8f  mov     rsi, rcx
0x180007e92  mov     qword ptr [rdx], 0
0x180007e99  mov     ebx, 128h
0x180007e9e  mov     rdi, rdx
0x180007ea1  mov     ecx, ebx
0x180007ea3  call    cs:__imp_FwAlloc
0x180007ea9  mov     [rdi], rax
0x180007eac  test    rax, rax
0x180007eaf  jnz     short loc_180007EE1
0x180007eb1  mov     ebx, 8007000Eh
0x180007eb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ebd  lea     rax, WPP_GLOBAL_Control
0x180007ec4  cmp     rcx, rax
0x180007ec7  jz      loc_180008113
0x180007ecd  test    byte ptr [rcx+1Ch], 1
0x180007ed1  jz      loc_180008113
0x180007ed7  mov     edx, 0D6h
0x180007edc  jmp     loc_180008100
0x180007ee1  mov     r8, rbx; Size
0x180007ee4  xor     edx, edx; Val
0x180007ee6  mov     rcx, rax; void *
0x180007ee9  call    memset_0
0x180007eee  mov     rax, [rdi]
0x180007ef1  mov     qword ptr [rax], 0
0x180007ef8  mov     rcx, [rdi]
0x180007efb  movzx   eax, word ptr [rsi+8]
0x180007eff  mov     [rcx+8], ax
0x180007f03  mov     rdx, [rdi]
0x180007f06  mov     rcx, [rsi+10h]
0x180007f0a  add     rdx, 10h
0x180007f0e  call    cs:__imp_FwStringCopy
0x180007f14  mov     ebx, eax
0x180007f16  test    eax, eax
0x180007f18  jns     short loc_180007F45
0x180007f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f21  lea     rax, WPP_GLOBAL_Control
0x180007f28  cmp     rcx, rax
0x180007f2b  jz      loc_180008113
0x180007f31  test    byte ptr [rcx+1Ch], 1
0x180007f35  jz      loc_180008113
0x180007f3b  mov     edx, 0D7h
0x180007f40  jmp     loc_180008100
0x180007f45  mov     rdx, [rdi]
0x180007f48  mov     rcx, [rsi+18h]
0x180007f4c  add     rdx, 18h
0x180007f50  call    cs:__imp_FwStringCopy
0x180007f56  mov     ebx, eax
0x180007f58  test    eax, eax
0x180007f5a  jns     short loc_180007F87
0x180007f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f63  lea     rax, WPP_GLOBAL_Control
0x180007f6a  cmp     rcx, rax
0x180007f6d  jz      loc_180008113
0x180007f73  test    byte ptr [rcx+1Ch], 1
0x180007f77  jz      loc_180008113
0x180007f7d  mov     edx, 0D8h
0x180007f82  jmp     loc_180008100
0x180007f87  movzx   eax, word ptr [rsi+20h]
0x180007f8b  lea     r9, [rsi+90h]
0x180007f92  mov     rcx, [rdi]
0x180007f95  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180007f9c  lea     rdx, FwCopyPlatform
0x180007fa3  mov     [rcx+20h], ax
0x180007fa7  mov     rcx, [rdi]
0x180007faa  mov     eax, [rsi+24h]
0x180007fad  mov     [rcx+24h], eax
0x180007fb0  mov     rax, [rdi]
0x180007fb3  movups  xmm0, xmmword ptr [rsi+28h]
0x180007fb7  movdqu  xmmword ptr [rax+28h], xmm0
0x180007fbc  movzx   eax, word ptr [rsi+38h]
0x180007fc0  mov     rcx, [rdi]
0x180007fc3  mov     [rcx+38h], ax
0x180007fc7  mov     rcx, [rdi]
0x180007fca  movzx   eax, word ptr [rsi+88h]
0x180007fd1  mov     [rcx+88h], ax
0x180007fd8  mov     ecx, 4
0x180007fdd  mov     rax, [rdi]
0x180007fe0  add     rax, 90h
0x180007fe6  mov     [rsp+38h+var_18], rax
0x180007feb  call    cs:__imp_FwArrayCopy
0x180007ff1  mov     ebx, eax
0x180007ff3  test    eax, eax
0x180007ff5  jns     short loc_180008022
0x180007ff7  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ffe  lea     rax, WPP_GLOBAL_Control
0x180008005  cmp     rcx, rax
0x180008008  jz      loc_180008113
0x18000800e  test    byte ptr [rcx+1Ch], 1
0x180008012  jz      loc_180008113
0x180008018  mov     edx, 0D9h
0x18000801d  jmp     loc_180008100
0x180008022  mov     r9, [rdi]
0x180008025  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18000802c  movzx   eax, word ptr [rsi+0E8h]
0x180008033  lea     rdx, FwCopyPlatform
0x18000803a  mov     ecx, 4
0x18000803f  mov     [r9+0E8h], ax
0x180008047  lea     r9, [rsi+0F0h]
0x18000804e  mov     rax, [rdi]
0x180008051  add     rax, 0F0h
0x180008057  mov     [rsp+38h+var_18], rax
0x18000805c  call    cs:__imp_FwArrayCopy
0x180008062  mov     ebx, eax
0x180008064  test    eax, eax
0x180008066  jns     short loc_180008090
0x180008068  mov     rcx, cs:WPP_GLOBAL_Control
0x18000806f  lea     rax, WPP_GLOBAL_Control
0x180008076  cmp     rcx, rax
0x180008079  jz      loc_180008113
0x18000807f  test    byte ptr [rcx+1Ch], 1
0x180008083  jz      loc_180008113
0x180008089  mov     edx, 0DAh
0x18000808e  jmp     short loc_180008100
0x180008090  mov     rdx, [rdi]
0x180008093  lea     rcx, [rsi+40h]
0x180008097  add     rdx, 40h ; '@'
0x18000809b  call    FwCopyWFAddressesContents
0x1800080a0  mov     ebx, eax
0x1800080a2  test    eax, eax
0x1800080a4  jns     short loc_1800080C6
0x1800080a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080ad  lea     rax, WPP_GLOBAL_Control
0x1800080b4  cmp     rcx, rax
0x1800080b7  jz      short loc_180008113
0x1800080b9  test    byte ptr [rcx+1Ch], 1
0x1800080bd  jz      short loc_180008113
0x1800080bf  mov     edx, 0DBh
0x1800080c4  jmp     short loc_180008100
0x1800080c6  mov     rdx, [rdi]
0x1800080c9  lea     rcx, [rsi+0A0h]
0x1800080d0  add     rdx, 0A0h
0x1800080d7  call    FwCopyWFAddressesContents
0x1800080dc  mov     ebx, eax
0x1800080de  test    eax, eax
0x1800080e0  jns     short loc_180008129
0x1800080e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080e9  lea     rax, WPP_GLOBAL_Control
0x1800080f0  cmp     rcx, rax
0x1800080f3  jz      short loc_180008113
0x1800080f5  test    byte ptr [rcx+1Ch], 1
0x1800080f9  jz      short loc_180008113
0x1800080fb  mov     edx, 0DCh
0x180008100  mov     rcx, [rcx+10h]
0x180008104  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x18000810b  mov     r9d, ebx
0x18000810e  call    WPP_SF_d
0x180008113  mov     rcx, [rdi]; void *
0x180008116  mov     edx, 221h
0x18000811b  call    FwFreeHyperVRulesBySchemaVersion
0x180008120  mov     qword ptr [rdi], 0
0x180008127  jmp     short loc_180008184
0x180008129  mov     eax, [rsi+100h]
0x18000812f  xorps   xmm0, xmm0
0x180008132  mov     rcx, [rdi]
0x180008135  mov     [rcx+100h], eax
0x18000813b  movzx   eax, word ptr [rsi+104h]
0x180008142  mov     rcx, [rdi]
0x180008145  mov     [rcx+104h], ax
0x18000814c  mov     eax, [rsi+108h]
0x180008152  mov     rcx, [rdi]
0x180008155  mov     [rcx+108h], eax
0x18000815b  mov     eax, [rsi+10Ch]
0x180008161  mov     rcx, [rdi]
0x180008164  mov     [rcx+10Ch], eax
0x18000816a  mov     eax, [rsi+120h]
0x180008170  mov     rcx, [rdi]
0x180008173  mov     [rcx+120h], eax
0x180008179  mov     rax, [rdi]
0x18000817c  movdqu  xmmword ptr [rax+110h], xmm0
0x180008184  mov     rsi, [rsp+38h+arg_8]
0x180008189  mov     eax, ebx
0x18000818b  mov     rbx, [rsp+38h+arg_0]
0x180008190  add     rsp, 30h
0x180008194  pop     rdi
0x180008195  retn
```
