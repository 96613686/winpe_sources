# FwCopyWFAddressesContents

- ea: `0x1800088a0`
- end: `0x180008a2d`
- name: `FwCopyWFAddressesContents`
- size: `397`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180007200`
- `0x180007a30`
- `0x180007e80`
- `0x1800228f0`

## callees

- `0x1800042c4`
- `0x1800088a0`
- `0x180008a40`

## import_xrefs

- `fwbase!FwArrayCopy` at `0x1800088df`
- `fwbase!FwArrayCopy` at `0x18000890f`
- `fwbase!FwArrayCopy` at `0x18000893f`
- `fwbase!FwArrayCopy` at `0x18000896f`
- `fwbase!FwArrayCopy` at `0x1800088df`
- `fwbase!FwArrayCopy` at `0x18000890f`
- `fwbase!FwArrayCopy` at `0x18000893f`
- `fwbase!FwArrayCopy` at `0x18000896f`

## pseudocode

```c
__int64 __fastcall FwCopyWFAddressesContents(_DWORD *a1, _DWORD *a2)
{
  int v4; // ebx
  __int64 result; // rax
  LPCOLESTR v6; // rcx
  __int64 v7; // rdx

  *a2 = *a1;
  a2[1] = a1[1];
  v4 = FwArrayCopy(
         8,
         FwCopyIPv4SubNet,
         wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
         a1 + 2,
         a2 + 2);
  if ( v4 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_7;
    v7 = 19;
    goto LABEL_19;
  }
  v4 = FwArrayCopy(
         8,
         FwCopyIPv4SubNet,
         wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
         a1 + 6,
         a2 + 6);
  if ( v4 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_7;
    v7 = 20;
    goto LABEL_19;
  }
  v4 = FwArrayCopy(
         20,
         FwCopyIPv6SubNet,
         wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
         a1 + 10,
         a2 + 10);
  if ( v4 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_7;
    v7 = 21;
    goto LABEL_19;
  }
  result = FwArrayCopy(
             32,
             FwCopyIPv6Range,
             wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
             a1 + 14,
             a2 + 14);
  v4 = result;
  if ( (int)result < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_7;
    v7 = 22;
LABEL_19:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, (unsigned int)v4);
LABEL_7:
    FwEmptyWFAddresses(a2);
    return (unsigned int)v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800088a0  mov     [rsp+arg_0], rbx
0x1800088a5  mov     [rsp+arg_8], rsi
0x1800088aa  push    rdi
0x1800088ab  sub     rsp, 30h
0x1800088af  mov     eax, [rcx]
0x1800088b1  lea     r9, [rcx+8]
0x1800088b5  mov     [rdx], eax
0x1800088b7  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x1800088be  mov     eax, [rcx+4]
0x1800088c1  mov     rdi, rdx
0x1800088c4  mov     [rdx+4], eax
0x1800088c7  mov     rsi, rcx
0x1800088ca  lea     rax, [rdx+8]
0x1800088ce  mov     ecx, 8
0x1800088d3  lea     rdx, FwCopyIPv4SubNet
0x1800088da  mov     [rsp+38h+var_18], rax
0x1800088df  call    cs:__imp_FwArrayCopy
0x1800088e5  mov     ebx, eax
0x1800088e7  test    eax, eax
0x1800088e9  js      loc_18000898B
0x1800088ef  lea     rax, [rdi+18h]
0x1800088f3  mov     ecx, 8
0x1800088f8  lea     r9, [rsi+18h]
0x1800088fc  mov     [rsp+38h+var_18], rax
0x180008901  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180008908  lea     rdx, FwCopyIPv4SubNet
0x18000890f  call    cs:__imp_FwArrayCopy
0x180008915  mov     ebx, eax
0x180008917  test    eax, eax
0x180008919  js      loc_1800089B7
0x18000891f  lea     rax, [rdi+28h]
0x180008923  mov     ecx, 14h
0x180008928  lea     r9, [rsi+28h]
0x18000892c  mov     [rsp+38h+var_18], rax
0x180008931  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180008938  lea     rdx, FwCopyIPv6SubNet
0x18000893f  call    cs:__imp_FwArrayCopy
0x180008945  mov     ebx, eax
0x180008947  test    eax, eax
0x180008949  js      loc_1800089D7
0x18000894f  lea     rax, [rdi+38h]
0x180008953  mov     ecx, 20h ; ' '
0x180008958  lea     r9, [rsi+38h]
0x18000895c  mov     [rsp+38h+var_18], rax
0x180008961  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180008968  lea     rdx, FwCopyIPv6Range
0x18000896f  call    cs:__imp_FwArrayCopy
0x180008975  mov     ebx, eax
0x180008977  test    eax, eax
0x180008979  js      short loc_1800089F7
0x18000897b  mov     rbx, [rsp+38h+arg_0]
0x180008980  mov     rsi, [rsp+38h+arg_8]
0x180008985  add     rsp, 30h
0x180008989  pop     rdi
0x18000898a  retn
0x18000898b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008992  lea     rax, WPP_GLOBAL_Control
0x180008999  cmp     rcx, rax
0x18000899c  jnz     short loc_1800089AA
0x18000899e  mov     rcx, rdi
0x1800089a1  call    FwEmptyWFAddresses
0x1800089a6  mov     eax, ebx
0x1800089a8  jmp     short loc_18000897B
0x1800089aa  test    byte ptr [rcx+1Ch], 1
0x1800089ae  jz      short loc_18000899E
0x1800089b0  mov     edx, 13h
0x1800089b5  jmp     short loc_180008A15
0x1800089b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089be  lea     rax, WPP_GLOBAL_Control
0x1800089c5  cmp     rcx, rax
0x1800089c8  jz      short loc_18000899E
0x1800089ca  test    byte ptr [rcx+1Ch], 1
0x1800089ce  jz      short loc_18000899E
0x1800089d0  mov     edx, 14h
0x1800089d5  jmp     short loc_180008A15
0x1800089d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089de  lea     rax, WPP_GLOBAL_Control
0x1800089e5  cmp     rcx, rax
0x1800089e8  jz      short loc_18000899E
0x1800089ea  test    byte ptr [rcx+1Ch], 1
0x1800089ee  jz      short loc_18000899E
0x1800089f0  mov     edx, 15h
0x1800089f5  jmp     short loc_180008A15
0x1800089f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089fe  lea     rax, WPP_GLOBAL_Control
0x180008a05  cmp     rcx, rax
0x180008a08  jz      short loc_18000899E
0x180008a0a  test    byte ptr [rcx+1Ch], 1
0x180008a0e  jz      short loc_18000899E
0x180008a10  mov     edx, 16h
0x180008a15  mov     rcx, [rcx+10h]
0x180008a19  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x180008a20  mov     r9d, ebx
0x180008a23  call    WPP_SF_d
0x180008a28  jmp     loc_18000899E
```
