# CConnectedUserStore::InitializeSamHandles(void)

- ea: `0x18000c2a0`
- end: `0x18000c4af`
- name: `?InitializeSamHandles@CConnectedUserStore@@AEAAJXZ`
- size: `527`
- prototype: `__int64 __fastcall(CConnectedUserStore *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000412c`

## callees

- `0x18000c2a0`
- `0x18000daa0`
- `0x1800144b4`
- `0x1800191ac`
- `0x180019210`

## import_xrefs

- `SAMLIB!SamConnect` at `0x18000c340`
- `SAMLIB!SamConnect` at `0x18000c340`
- `SAMLIB!SamOpenDomain` at `0x18000c361`
- `SAMLIB!SamOpenDomain` at `0x18000c361`

## pseudocode

```c
__int64 __fastcall CConnectedUserStore::InitializeSamHandles(CConnectedUserStore *this, __int64 a2, __int64 a3)
{
  CIdentityProfileHandler *v4; // rcx
  int v5; // edx
  int v6; // ebp
  __int64 v7; // r8
  int v8; // ebp
  int v9; // edi
  CIdentityProfileHandler *v10; // rcx
  int v12; // ebp
  __int64 v13; // rdx
  __int128 v14; // [rsp+30h] [rbp-48h] BYREF
  __int128 v15; // [rsp+40h] [rbp-38h]
  __int128 v16; // [rsp+50h] [rbp-28h]

  v14 = 0;
  v15 = 0;
  v16 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CConnectedUserStore::InitializeSamHandles");
    v4 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 13) || *((_QWORD *)this + 12) )
  {
    v9 = -2147418113;
    if ( v4 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)v4 + 2), 89, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, 2147549183LL);
    goto LABEL_29;
  }
  LODWORD(v14) = 48;
  *((_QWORD *)&v14 + 1) = 0;
  DWORD2(v15) = 0;
  *(_QWORD *)&v15 = 0;
  v16 = 0;
  v6 = SamConnect(0, (char *)this + 104, 0x2000000, &v14);
  if ( v6 < 0 )
  {
    v12 = v6 | 0x10000000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v13 = 90;
LABEL_23:
      WPP_SF_d(*((_QWORD *)v10 + 2), v13, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, (unsigned int)v12);
      v10 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v8 = SamOpenDomain(*((_QWORD *)this + 13), 0x2000000, *((_QWORD *)this + 11), (char *)this + 96);
    v9 = 0;
    if ( v8 >= 0 )
    {
LABEL_8:
      v10 = WPP_GLOBAL_Control;
      goto LABEL_10;
    }
    v12 = v8 | 0x10000000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v13 = 91;
      goto LABEL_23;
    }
  }
  v9 = v12;
  if ( v12 < 0 )
  {
LABEL_29:
    CConnectedUserStore::CloseSamHandles(this);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v9 < 0 )
  {
    if ( v10 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      return (unsigned int)v9;
    if ( (*((_BYTE *)v10 + 28) & 4) != 0 )
    {
      WPP_SF_sL(*((_QWORD *)v10 + 2), v5, v7, (unsigned int)"CConnectedUserStore::InitializeSamHandles", v9);
      goto LABEL_8;
    }
  }
LABEL_10:
  if ( v10 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x400) != 0 )
    WPP_SF_s(*((_QWORD *)v10 + 2), 12, v7, "CConnectedUserStore::InitializeSamHandles");
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000c2a0  push    rbx
0x18000c2a2  push    rdi
0x18000c2a3  push    r14
0x18000c2a5  sub     rsp, 60h
0x18000c2a9  xorps   xmm0, xmm0
0x18000c2ac  mov     rbx, rcx
0x18000c2af  movups  [rsp+78h+var_48], xmm0
0x18000c2b4  movups  [rsp+78h+var_38], xmm0
0x18000c2b9  movups  [rsp+78h+var_28], xmm0
0x18000c2be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2c5  lea     r14, WPP_GLOBAL_Control
0x18000c2cc  cmp     rcx, r14
0x18000c2cf  jz      short loc_18000C2DE
0x18000c2d1  test    dword ptr [rcx+1Ch], 400h
0x18000c2d8  jnz     loc_18000C3D7
0x18000c2de  cmp     qword ptr [rbx+68h], 0
0x18000c2e3  mov     [rsp+78h+arg_0], rbp
0x18000c2eb  mov     [rsp+78h+arg_8], rsi
0x18000c2f3  mov     [rsp+78h+arg_10], r15
0x18000c2fb  jnz     loc_18000C456
0x18000c301  cmp     qword ptr [rbx+60h], 0
0x18000c306  jnz     loc_18000C456
0x18000c30c  xor     r15d, r15d
0x18000c30f  mov     dword ptr [rsp+78h+var_48], 30h ; '0'
0x18000c317  xorps   xmm0, xmm0
0x18000c31a  mov     qword ptr [rsp+78h+var_48+8], r15
0x18000c31f  lea     r9, [rsp+78h+var_48]
0x18000c324  mov     dword ptr [rsp+78h+var_38+8], r15d
0x18000c329  mov     r8d, 2000000h
0x18000c32f  mov     qword ptr [rsp+78h+var_38], r15
0x18000c334  lea     rdx, [rbx+68h]
0x18000c338  xor     ecx, ecx
0x18000c33a  movdqu  [rsp+78h+var_28], xmm0
0x18000c340  call    cs:__imp_SamConnect
0x18000c346  mov     ebp, eax
0x18000c348  test    eax, eax
0x18000c34a  js      loc_18000C3F8
0x18000c350  mov     r8, [rbx+58h]
0x18000c354  lea     r9, [rbx+60h]
0x18000c358  mov     rcx, [rbx+68h]
0x18000c35c  mov     edx, 2000000h
0x18000c361  call    cs:__imp_SamOpenDomain
0x18000c367  mov     ebp, eax
0x18000c369  mov     edi, r15d
0x18000c36c  test    eax, eax
0x18000c36e  js      loc_18000C415
0x18000c374  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c37b  jmp     short loc_18000C381
0x18000c37d  test    edi, edi
0x18000c37f  js      short loc_18000C3B6
0x18000c381  cmp     rcx, r14
0x18000c384  jz      short loc_18000C393
0x18000c386  test    dword ptr [rcx+1Ch], 400h
0x18000c38d  jnz     loc_18000C495
0x18000c393  mov     r15, [rsp+78h+arg_10]
0x18000c39b  mov     eax, edi
0x18000c39d  mov     rsi, [rsp+78h+arg_8]
0x18000c3a5  mov     rbp, [rsp+78h+arg_0]
0x18000c3ad  add     rsp, 60h
0x18000c3b1  pop     r14
0x18000c3b3  pop     rdi
0x18000c3b4  pop     rbx
0x18000c3b5  retn
0x18000c3b6  cmp     rcx, r14
0x18000c3b9  jz      short loc_18000C393
0x18000c3bb  test    byte ptr [rcx+1Ch], 4
0x18000c3bf  jz      short loc_18000C381
0x18000c3c1  mov     rcx, [rcx+10h]
0x18000c3c5  lea     r9, aCconnecteduser_2; "CConnectedUserStore::InitializeSamHandl"...
0x18000c3cc  mov     [rsp+78h+var_58], edi
0x18000c3d0  call    WPP_SF_sL
0x18000c3d5  jmp     short loc_18000C374
0x18000c3d7  mov     rcx, [rcx+10h]
0x18000c3db  lea     r9, aCconnecteduser_2; "CConnectedUserStore::InitializeSamHandl"...
0x18000c3e2  mov     edx, 0Ah
0x18000c3e7  call    WPP_SF_s
0x18000c3ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3f3  jmp     loc_18000C2DE
0x18000c3f8  bts     ebp, 1Ch
0x18000c3fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c403  cmp     rcx, r14
0x18000c406  jz      short loc_18000C44A
0x18000c408  test    byte ptr [rcx+1Ch], 4
0x18000c40c  jz      short loc_18000C44A
0x18000c40e  mov     edx, 5Ah ; 'Z'
0x18000c413  jmp     short loc_18000C430
0x18000c415  bts     ebp, 1Ch
0x18000c419  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c420  cmp     rcx, r14
0x18000c423  jz      short loc_18000C44A
0x18000c425  test    byte ptr [rcx+1Ch], 4
0x18000c429  jz      short loc_18000C44A
0x18000c42b  mov     edx, 5Bh ; '['
0x18000c430  mov     rcx, [rcx+10h]
0x18000c434  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x18000c43b  mov     r9d, ebp
0x18000c43e  call    WPP_SF_d
0x18000c443  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c44a  mov     edi, ebp
0x18000c44c  test    ebp, ebp
0x18000c44e  jns     loc_18000C37D
0x18000c454  jmp     short loc_18000C481
0x18000c456  mov     edi, 8000FFFFh
0x18000c45b  cmp     rcx, r14
0x18000c45e  jz      short loc_18000C481
0x18000c460  test    byte ptr [rcx+1Ch], 4
0x18000c464  jz      short loc_18000C481
0x18000c466  mov     rcx, [rcx+10h]
0x18000c46a  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x18000c471  mov     edx, 59h ; 'Y'
0x18000c476  mov     r9d, 8000FFFFh
0x18000c47c  call    WPP_SF_d
0x18000c481  mov     rcx, rbx; this
0x18000c484  call    ?CloseSamHandles@CConnectedUserStore@@AEAAXXZ; CConnectedUserStore::CloseSamHandles(void)
0x18000c489  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c490  jmp     loc_18000C37D
0x18000c495  mov     rcx, [rcx+10h]
0x18000c499  lea     r9, aCconnecteduser_2; "CConnectedUserStore::InitializeSamHandl"...
0x18000c4a0  mov     edx, 0Ch
0x18000c4a5  call    WPP_SF_s
0x18000c4aa  jmp     loc_18000C393
```
