# AreAllInterfacesEnabled(void *,int *,_tag_FW_PROFILE_TYPE)

- ea: `0x180007130`
- end: `0x18000745e`
- name: `?AreAllInterfacesEnabled@@YAJPEAXPEAHW4_tag_FW_PROFILE_TYPE@@@Z`
- size: `814`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180006394`

## callees

- `0x180005954`
- `0x180007130`
- `0x180008b30`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800071b2`
- `ntdll!EtwEventWrite` at `0x180007235`
- `ntdll!EtwEventWrite` at `0x1800071b2`
- `ntdll!EtwEventWrite` at `0x180007235`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800071ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800071ce`
- `fwbase!FwBaseAlloc` at `0x180007266`
- `fwbase!FwBaseAlloc` at `0x180007266`
- `fwbase!FwBaseFree` at `0x1800072bb`
- `fwbase!FwBaseFree` at `0x18000738a`
- `fwbase!FwBaseFree` at `0x1800073e1`
- `fwbase!FwBaseFree` at `0x1800072bb`
- `fwbase!FwBaseFree` at `0x18000738a`
- `fwbase!FwBaseFree` at `0x1800073e1`

## pseudocode

```c
__int64 __fastcall AreAllInterfacesEnabled(__int64 a1, _DWORD *a2, unsigned int a3)
{
  unsigned int v6; // esi
  FwPolicy2 *v7; // rax
  unsigned int v8; // ebp
  __int64 v9; // rcx
  _DWORD *v10; // rdi
  int v11; // ebx
  int v13[2]; // [rsp+40h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids);
  *a2 = 0;
  v6 = 0;
  v7 = WPP_GLOBAL_Control;
  v8 = 0;
  v9 = g_Provider;
  v10 = 0;
  v13[0] = 0;
  while ( 1 )
  {
    v13[1] = 0;
    if ( v9 )
    {
      EtwEventWrite(v9, MPS_CLNT_API_Enter_GetConfig, 0, 0);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)v7 + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
    GetTickCount64();
    v11 = Int_FWGetOrSetConfig(1u, a1, 0xFu, a3, 1, (__int64)v10, v13);
    if ( !v11 )
      goto LABEL_11;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids,
        (unsigned int)v11);
LABEL_11:
      v7 = WPP_GLOBAL_Control;
    }
    v9 = g_Provider;
    if ( g_Provider )
    {
      EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
      v7 = WPP_GLOBAL_Control;
      v9 = g_Provider;
    }
    if ( !v11 )
      goto LABEL_20;
    if ( v11 != 234 )
      break;
    if ( v10 )
      FwBaseFree(v10);
    v10 = (_DWORD *)FwBaseAlloc((unsigned int)v13[0]);
    if ( !v10 )
    {
      v6 = -2147024882;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_428964b663db31776494a5e8e5edd24b_Traceguids, 2147942414LL);
        goto LABEL_38;
      }
      goto LABEL_39;
    }
    v7 = WPP_GLOBAL_Control;
    v9 = g_Provider;
LABEL_20:
    if ( v8 <= 5 && !v11 )
      goto LABEL_22;
    ++v8;
  }
  if ( v11 > 0 )
    v6 = (unsigned __int16)v11 | 0x80070000;
  else
    v6 = v11;
  if ( v7 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v7 + 2), 14, WPP_428964b663db31776494a5e8e5edd24b_Traceguids, v6);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v10 )
  {
    FwBaseFree(v10);
LABEL_38:
    v7 = WPP_GLOBAL_Control;
  }
LABEL_39:
  v10 = 0;
LABEL_22:
  if ( v6 == -2147024894 )
  {
    *a2 = 1;
    v6 = 0;
  }
  else if ( (v6 & 0x80000000) != 0 )
  {
    if ( v7 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v7 + 2), 33, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids, v6);
  }
  else
  {
    *a2 = *v10 == 0;
  }
  FwBaseFree(v10);
  return v6;
}

```

## disassembly

```asm
0x180007130  mov     [rsp+arg_18], rbx
0x180007135  push    rbp
0x180007136  push    rsi
0x180007137  push    rdi
0x180007138  push    r12
0x18000713a  push    r13
0x18000713c  push    r14
0x18000713e  push    r15
0x180007140  sub     rsp, 50h
0x180007144  mov     rax, cs:__security_cookie
0x18000714b  xor     rax, rsp
0x18000714e  mov     [rsp+88h+var_40], rax
0x180007153  mov     r12d, r8d
0x180007156  mov     r14, rdx
0x180007159  mov     r15, rcx
0x18000715c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007163  lea     rbx, WPP_GLOBAL_Control
0x18000716a  cmp     rcx, rbx
0x18000716d  jz      short loc_180007179
0x18000716f  test    byte ptr [rcx+1Ch], 8
0x180007173  jnz     loc_1800073AA
0x180007179  xor     r13d, r13d
0x18000717c  mov     [r14], r13d
0x18000717f  mov     esi, r13d
0x180007182  mov     rax, cs:WPP_GLOBAL_Control
0x180007189  mov     ebp, r13d
0x18000718c  mov     rcx, cs:g_Provider
0x180007193  mov     edi, r13d
0x180007196  mov     [rsp+88h+var_48], r13d
0x18000719b  mov     [rsp+88h+var_44], r13d
0x1800071a0  test    rcx, rcx
0x1800071a3  jz      short loc_1800071BF
0x1800071a5  xor     r9d, r9d
0x1800071a8  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x1800071af  xor     r8d, r8d
0x1800071b2  call    cs:__imp_EtwEventWrite
0x1800071b8  mov     rax, cs:WPP_GLOBAL_Control
0x1800071bf  cmp     rax, rbx
0x1800071c2  jz      short loc_1800071CE
0x1800071c4  test    byte ptr [rax+1Ch], 8
0x1800071c8  jnz     loc_1800073C4
0x1800071ce  call    cs:__imp_GetTickCount64
0x1800071d4  lea     rax, [rsp+88h+var_44]
0x1800071d9  mov     r9d, r12d
0x1800071dc  mov     [rsp+88h+var_50], rax
0x1800071e1  mov     r8d, 0Fh
0x1800071e7  lea     rax, [rsp+88h+var_48]
0x1800071ec  mov     rdx, r15
0x1800071ef  mov     [rsp+88h+var_58], rax
0x1800071f4  mov     ecx, 1
0x1800071f9  mov     [rsp+88h+var_60], rdi
0x1800071fe  mov     [rsp+88h+var_68], 1
0x180007206  call    Int_FWGetOrSetConfig
0x18000720b  mov     ebx, eax
0x18000720d  test    eax, eax
0x18000720f  jnz     loc_1800072F6
0x180007215  mov     rax, cs:WPP_GLOBAL_Control
0x18000721c  mov     rcx, cs:g_Provider
0x180007223  test    rcx, rcx
0x180007226  jz      short loc_180007249
0x180007228  xor     r9d, r9d
0x18000722b  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x180007232  xor     r8d, r8d
0x180007235  call    cs:__imp_EtwEventWrite
0x18000723b  mov     rax, cs:WPP_GLOBAL_Control
0x180007242  mov     rcx, cs:g_Provider
0x180007249  test    ebx, ebx
0x18000724b  jz      short loc_180007286
0x18000724d  cmp     ebx, 0EAh
0x180007253  jnz     loc_180007343
0x180007259  test    rdi, rdi
0x18000725c  jnz     loc_1800073DE
0x180007262  mov     ecx, [rsp+88h+var_48]
0x180007266  call    cs:__imp_FwBaseAlloc
0x18000726c  mov     rdi, rax
0x18000726f  test    rax, rax
0x180007272  jz      loc_1800073EC
0x180007278  mov     rax, cs:WPP_GLOBAL_Control
0x18000727f  mov     rcx, cs:g_Provider
0x180007286  cmp     ebp, 5
0x180007289  ja      short loc_1800072E8
0x18000728b  mov     edx, esi
0x18000728d  test    ebx, ebx
0x18000728f  jnz     short loc_1800072E8
0x180007291  test    edx, edx
0x180007293  js      loc_180007382
0x180007299  cmp     esi, 80070002h
0x18000729f  jz      loc_180007334
0x1800072a5  test    esi, esi
0x1800072a7  js      loc_180007427
0x1800072ad  mov     edx, r13d
0x1800072b0  cmp     [rdi], edx
0x1800072b2  setbe   dl
0x1800072b5  mov     [r14], edx
0x1800072b8  mov     rcx, rdi
0x1800072bb  call    cs:__imp_FwBaseFree
0x1800072c1  mov     eax, esi
0x1800072c3  mov     rcx, [rsp+88h+var_40]
0x1800072c8  xor     rcx, rsp; StackCookie
0x1800072cb  call    __security_check_cookie
0x1800072d0  mov     rbx, [rsp+88h+arg_18]
0x1800072d8  add     rsp, 50h
0x1800072dc  pop     r15
0x1800072de  pop     r14
0x1800072e0  pop     r13
0x1800072e2  pop     r12
0x1800072e4  pop     rdi
0x1800072e5  pop     rsi
0x1800072e6  pop     rbp
0x1800072e7  retn
0x1800072e8  inc     ebp
0x1800072ea  lea     rbx, WPP_GLOBAL_Control
0x1800072f1  jmp     loc_18000719B
0x1800072f6  mov     rax, cs:WPP_GLOBAL_Control
0x1800072fd  lea     rcx, WPP_GLOBAL_Control
0x180007304  cmp     rax, rcx
0x180007307  jz      loc_18000721C
0x18000730d  test    byte ptr [rax+1Ch], 1
0x180007311  jz      loc_18000721C
0x180007317  mov     rcx, [rax+10h]
0x18000731b  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180007322  mov     edx, 6Bh ; 'k'
0x180007327  mov     r9d, ebx
0x18000732a  call    WPP_SF_d
0x18000732f  jmp     loc_180007215
0x180007334  mov     dword ptr [r14], 1
0x18000733b  mov     esi, r13d
0x18000733e  jmp     loc_1800072B8
0x180007343  test    ebx, ebx
0x180007345  jg      short loc_18000739F
0x180007347  mov     esi, ebx
0x180007349  test    esi, esi
0x18000734b  jns     loc_180007286
0x180007351  lea     rcx, WPP_GLOBAL_Control
0x180007358  cmp     rax, rcx
0x18000735b  jz      short loc_180007382
0x18000735d  test    byte ptr [rax+1Ch], 1
0x180007361  jz      short loc_180007382
0x180007363  mov     rcx, [rax+10h]
0x180007367  lea     r8, WPP_428964b663db31776494a5e8e5edd24b_Traceguids
0x18000736e  mov     edx, 0Eh
0x180007373  mov     r9d, esi
0x180007376  call    WPP_SF_d
0x18000737b  mov     rax, cs:WPP_GLOBAL_Control
0x180007382  test    rdi, rdi
0x180007385  jz      short loc_180007397
0x180007387  mov     rcx, rdi
0x18000738a  call    cs:__imp_FwBaseFree
0x180007390  mov     rax, cs:WPP_GLOBAL_Control
0x180007397  mov     rdi, r13
0x18000739a  jmp     loc_180007299
0x18000739f  movzx   esi, bx
0x1800073a2  or      esi, 80070000h
0x1800073a8  jmp     short loc_180007349
0x1800073aa  mov     rcx, [rcx+10h]
0x1800073ae  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x1800073b5  mov     edx, 20h ; ' '
0x1800073ba  call    WPP_SF_
0x1800073bf  jmp     loc_180007179
0x1800073c4  mov     rcx, [rax+10h]
0x1800073c8  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800073cf  mov     edx, 6Ah ; 'j'
0x1800073d4  call    WPP_SF_
0x1800073d9  jmp     loc_1800071CE
0x1800073de  mov     rcx, rdi
0x1800073e1  call    cs:__imp_FwBaseFree
0x1800073e7  jmp     loc_180007262
0x1800073ec  mov     esi, 8007000Eh
0x1800073f1  mov     rax, cs:WPP_GLOBAL_Control
0x1800073f8  lea     rcx, WPP_GLOBAL_Control
0x1800073ff  cmp     rax, rcx
0x180007402  jz      short loc_180007397
0x180007404  test    byte ptr [rax+1Ch], 1
0x180007408  jz      short loc_180007397
0x18000740a  mov     rcx, [rax+10h]
0x18000740e  lea     r8, WPP_428964b663db31776494a5e8e5edd24b_Traceguids
0x180007415  mov     edx, 0Dh
0x18000741a  mov     r9d, esi
0x18000741d  call    WPP_SF_d
0x180007422  jmp     loc_180007390
0x180007427  lea     rcx, WPP_GLOBAL_Control
0x18000742e  cmp     rax, rcx
0x180007431  jz      loc_1800072B8
0x180007437  test    byte ptr [rax+1Ch], 1
0x18000743b  jz      loc_1800072B8
0x180007441  mov     rcx, [rax+10h]
0x180007445  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x18000744c  mov     edx, 21h ; '!'
0x180007451  mov     r9d, esi
0x180007454  call    WPP_SF_d
0x180007459  jmp     loc_1800072B8
```
