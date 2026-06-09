# Apx::ApfDevice::CreateDevice_Remote(void)

- ea: `0x18000f664`
- end: `0x18000f825`
- name: `?CreateDevice_Remote@ApfDevice@Apx@@AEAAJXZ`
- size: `449`
- prototype: `__int64 __fastcall(Apx::ApfDevice *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000f2ac`

## callees

- `0x180001d30`
- `0x1800027c8`
- `0x18000a12c`
- `0x18000bf24`
- `0x18000f664`

## pseudocode

```c
__int64 __fastcall Apx::ApfDevice::CreateDevice_Remote(Apx::ApfDevice *this)
{
  int v2; // edx
  int v3; // r8d
  __int128 v4; // xmm0
  int v5; // ecx
  int Device_Rpc; // eax
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-29h] BYREF
  int v10; // [rsp+24h] [rbp-25h] BYREF
  __int128 v11; // [rsp+28h] [rbp-21h]
  __int128 v12; // [rsp+38h] [rbp-11h]
  __int128 v13; // [rsp+48h] [rbp-1h]
  __int16 v14; // [rsp+58h] [rbp+Fh]
  __int16 v15; // [rsp+5Ah] [rbp+11h]
  int v16; // [rsp+5Ch] [rbp+13h]
  __int16 v17; // [rsp+60h] [rbp+17h]
  char *v18; // [rsp+68h] [rbp+1Fh]
  char *v19; // [rsp+70h] [rbp+27h]
  char *v20; // [rsp+78h] [rbp+2Fh]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  memset_0(&v10, 0, 0x64u);
  v2 = *((_DWORD *)this + 8);
  v9 = 104;
  v3 = v2 & 1;
  if ( (v2 & 1) != 0 )
  {
    v4 = *(_OWORD *)((char *)this + 120);
    v5 = 1;
    v10 = 1;
    v11 = v4;
  }
  else
  {
    v5 = v10;
  }
  if ( (v2 & 2) != 0 )
  {
    v5 = v3 | 2;
    v12 = *(_OWORD *)((char *)this + 152);
    v10 = v3 | 2;
    v3 |= 2u;
  }
  if ( (v2 & 4) != 0 )
  {
    v5 = v3 | 4;
    v13 = *(_OWORD *)((char *)this + 136);
    v10 = v3 | 4;
    v3 |= 4u;
  }
  if ( (v2 & 0x40) != 0 )
  {
    v14 = *((_WORD *)this + 84);
    v5 = v3 | 0x20;
    v3 = v5;
    v15 = *((_WORD *)this + 85);
    v16 = *((_DWORD *)this + 43);
    v17 = *((_WORD *)this + 88);
    v10 = v5;
  }
  if ( (v2 & 0x80u) != 0 )
  {
    v5 = v3 | 0x40;
    v10 = v3 | 0x40;
  }
  if ( (v2 & 8) != 0 )
  {
    v5 |= 8u;
    v18 = (char *)this + 328;
    v10 = v5;
  }
  if ( (v2 & 0x20) != 0 )
  {
    v5 |= 0x10u;
    v19 = (char *)this + 1372;
    v10 = v5;
  }
  if ( *((_DWORD *)this + 474) == 1 )
  {
    v20 = (char *)this + 1900;
    v10 = v5 | 0x80;
  }
  Device_Rpc = Apx::ApfRpc::CreateDevice_Rpc((struct APF_DEVICE_RPC_CONFIG *)&v9, (void **)this + 3);
  v7 = 0;
  if ( Device_Rpc < 0 )
    v7 = Device_Rpc;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  return v7;
}

```

## disassembly

```asm
0x18000f664  mov     [rsp-8+arg_8], rbx
0x18000f669  mov     [rsp-8+arg_10], rsi
0x18000f66e  push    rbp
0x18000f66f  lea     rbp, [rsp-57h]
0x18000f674  sub     rsp, 0A0h
0x18000f67b  mov     rax, cs:__security_cookie
0x18000f682  xor     rax, rsp
0x18000f685  mov     [rbp+57h+var_10], rax
0x18000f689  mov     rbx, rcx
0x18000f68c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f693  lea     rsi, WPP_GLOBAL_Control
0x18000f69a  cmp     rcx, rsi
0x18000f69d  jz      short loc_18000F6C0
0x18000f69f  test    byte ptr [rcx+1Ch], 1
0x18000f6a3  jz      short loc_18000F6C0
0x18000f6a5  cmp     byte ptr [rcx+19h], 5
0x18000f6a9  jb      short loc_18000F6C0
0x18000f6ab  mov     rcx, [rcx+10h]
0x18000f6af  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000f6b6  mov     edx, 1Ah
0x18000f6bb  call    WPP_SF_
0x18000f6c0  xor     edx, edx; Val
0x18000f6c2  lea     rcx, [rbp+57h+var_7C]; void *
0x18000f6c6  lea     r8d, [rdx+64h]; Size
0x18000f6ca  call    memset_0
0x18000f6cf  mov     edx, [rbx+20h]
0x18000f6d2  mov     r8d, edx
0x18000f6d5  mov     [rbp+57h+var_80], 68h ; 'h'
0x18000f6dc  and     r8d, 1
0x18000f6e0  jz      short loc_18000F6F5
0x18000f6e2  movups  xmm0, xmmword ptr [rbx+78h]
0x18000f6e6  mov     ecx, 1
0x18000f6eb  mov     [rbp+57h+var_7C], ecx
0x18000f6ee  movdqu  [rbp+57h+var_78], xmm0
0x18000f6f3  jmp     short loc_18000F6F8
0x18000f6f5  mov     ecx, [rbp+57h+var_7C]
0x18000f6f8  test    dl, 2
0x18000f6fb  jz      short loc_18000F715
0x18000f6fd  movups  xmm0, xmmword ptr [rbx+98h]
0x18000f704  mov     ecx, r8d
0x18000f707  or      ecx, 2
0x18000f70a  movdqu  [rbp+57h+var_68], xmm0
0x18000f70f  mov     [rbp+57h+var_7C], ecx
0x18000f712  mov     r8d, ecx
0x18000f715  test    dl, 4
0x18000f718  jz      short loc_18000F732
0x18000f71a  movups  xmm0, xmmword ptr [rbx+88h]
0x18000f721  mov     ecx, r8d
0x18000f724  or      ecx, 4
0x18000f727  movdqu  [rbp+57h+var_58], xmm0
0x18000f72c  mov     [rbp+57h+var_7C], ecx
0x18000f72f  mov     r8d, ecx
0x18000f732  test    dl, 40h
0x18000f735  jz      short loc_18000F76D
0x18000f737  movzx   eax, word ptr [rbx+0A8h]
0x18000f73e  mov     ecx, r8d
0x18000f741  mov     [rbp+57h+var_48], ax
0x18000f745  or      ecx, 20h
0x18000f748  movzx   eax, word ptr [rbx+0AAh]
0x18000f74f  mov     r8d, ecx
0x18000f752  mov     [rbp+57h+var_46], ax
0x18000f756  mov     eax, [rbx+0ACh]
0x18000f75c  mov     [rbp+57h+var_44], eax
0x18000f75f  movzx   eax, word ptr [rbx+0B0h]
0x18000f766  mov     [rbp+57h+var_40], ax
0x18000f76a  mov     [rbp+57h+var_7C], ecx
0x18000f76d  test    dl, dl
0x18000f76f  jns     short loc_18000F77A
0x18000f771  mov     ecx, r8d
0x18000f774  or      ecx, 40h
0x18000f777  mov     [rbp+57h+var_7C], ecx
0x18000f77a  test    dl, 8
0x18000f77d  jz      short loc_18000F790
0x18000f77f  lea     rax, [rbx+148h]
0x18000f786  or      ecx, 8
0x18000f789  mov     [rbp+57h+var_38], rax
0x18000f78d  mov     [rbp+57h+var_7C], ecx
0x18000f790  test    dl, 20h
0x18000f793  jz      short loc_18000F7A6
0x18000f795  lea     rax, [rbx+55Ch]
0x18000f79c  or      ecx, 10h
0x18000f79f  mov     [rbp+57h+var_30], rax
0x18000f7a3  mov     [rbp+57h+var_7C], ecx
0x18000f7a6  cmp     dword ptr [rbx+768h], 1
0x18000f7ad  jnz     short loc_18000F7C1
0x18000f7af  lea     rax, [rbx+76Ch]
0x18000f7b6  bts     ecx, 7
0x18000f7ba  mov     [rbp+57h+var_28], rax
0x18000f7be  mov     [rbp+57h+var_7C], ecx
0x18000f7c1  lea     rdx, [rbx+18h]; void **
0x18000f7c5  lea     rcx, [rbp+57h+var_80]; struct APF_DEVICE_RPC_CONFIG *
0x18000f7c9  call    ?CreateDevice_Rpc@ApfRpc@Apx@@SAJPEAUAPF_DEVICE_RPC_CONFIG@@PEAPEAX@Z; Apx::ApfRpc::CreateDevice_Rpc(APF_DEVICE_RPC_CONFIG *,void * *)
0x18000f7ce  xor     ebx, ebx
0x18000f7d0  test    eax, eax
0x18000f7d2  cmovs   ebx, eax
0x18000f7d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7dc  cmp     rcx, rsi
0x18000f7df  jz      short loc_18000F802
0x18000f7e1  test    byte ptr [rcx+1Ch], 1
0x18000f7e5  jz      short loc_18000F802
0x18000f7e7  cmp     byte ptr [rcx+19h], 5
0x18000f7eb  jb      short loc_18000F802
0x18000f7ed  mov     rcx, [rcx+10h]
0x18000f7f1  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000f7f8  mov     edx, 1Bh
0x18000f7fd  call    WPP_SF_
0x18000f802  mov     eax, ebx
0x18000f804  mov     rcx, [rbp+57h+var_10]
0x18000f808  xor     rcx, rsp; StackCookie
0x18000f80b  call    __security_check_cookie
0x18000f810  lea     r11, [rsp+0A0h+var_s0]
0x18000f818  mov     rbx, [r11+18h]
0x18000f81c  mov     rsi, [r11+20h]
0x18000f820  mov     rsp, r11
0x18000f823  pop     rbp
0x18000f824  retn
```
