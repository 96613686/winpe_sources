# GetDeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222_

- ea: `0x18000a700`
- end: `0x18000a9b5`
- name: `GetDeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222___`
- size: `693`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000a504`
- `0x18000a5d0`

## callees

- `0x18000a700`
- `0x1800112a4`
- `0x18001af70`
- `0x18003f2d0`
- `0x18003f368`
- `0x1800419a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a837`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a837`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000a77b`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000a77b`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000a7d4`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000a88e`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000a931`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000a989`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000a9a5`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000a7d4`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000a88e`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000a931`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000a989`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000a9a5`

## pseudocode

```c
__int64 __fastcall GetDeviceObjectCustomProperty__lambda_b0ff62bd7f6cc623e314bba05d117222_(
        __int64 a1,
        __int64 a2,
        __int128 *a3,
        int a4,
        _QWORD **a5)
{
  __int128 v6; // xmm0
  __int64 v8; // r8
  int ObjectProperties; // eax
  int v11; // r8d
  unsigned int v12; // ebx
  __int64 v14; // rcx
  __int64 v15; // rax
  int v16; // edx
  const void *v17; // rsi
  size_t v18; // rbp
  SIZE_T v19; // rdi
  _WORD *v20; // rax
  void *v21; // rbx
  _WORD *i; // rcx
  int v23; // r8d
  int v24; // [rsp+20h] [rbp-88h]
  unsigned int v25; // [rsp+40h] [rbp-68h] BYREF
  __int64 v26; // [rsp+48h] [rbp-60h] BYREF
  __int128 v27; // [rsp+50h] [rbp-58h] BYREF
  int v28; // [rsp+60h] [rbp-48h]
  int v29; // [rsp+64h] [rbp-44h]
  __int64 v30; // [rsp+68h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v6 = *a3;
  v28 = *((_DWORD *)a3 + 4);
  v29 = 0;
  v26 = 0;
  v8 = 4;
  v25 = 0;
  v27 = v6;
  v30 = 0;
  if ( a4 != 18 )
    v8 = 0;
  ObjectProperties = DevGetObjectProperties(a1, a2, v8, 1, &v27, &v25, &v26);
  v12 = ObjectProperties;
  if ( ObjectProperties < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF__guid_dSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        v11,
        (_DWORD)a3,
        *((_DWORD *)a3 + 4),
        a2,
        ObjectProperties);
    if ( v25 )
    {
      if ( v26 )
        DevFreeObjectProperties(v25, v26);
    }
    return v12;
  }
  v14 = v25;
  v15 = v26;
  if ( !v25 )
    return 2147943568LL;
  v16 = *(_DWORD *)(v26 + 32);
  if ( !v16 )
  {
    if ( v26 )
      DevFreeObjectProperties(v25, v26);
    return 2147943568LL;
  }
  if ( v25 == 1 && v16 == a4 && (v17 = *(const void **)(v26 + 40)) != 0 )
  {
    v18 = *(unsigned int *)(v26 + 36);
    v19 = (unsigned int)v18 & 0xFFFFFFFE;
    v20 = CoTaskMemAlloc(v19);
    v21 = v20;
    if ( v20 )
    {
      for ( i = (_WORD *)((char *)v20 + v19); v20 != i; ++v20 )
        *v20 = 0;
      memcpy_0(v21, v17, v18);
      **a5 = v21;
      if ( v25 && v26 )
        DevFreeObjectProperties(v25, v26);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
        (const char *)0x8007000ELL,
        v24);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF__guid_dSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v23, (_DWORD)a3, *((_DWORD *)a3 + 4), a2, 14);
      if ( v25 && v26 )
        DevFreeObjectProperties(v25, v26);
      return 2147942414LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF__guid_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        (_DWORD)WPP_GLOBAL_Control,
        (_DWORD)a3,
        *((_DWORD *)a3 + 4),
        a2);
      v15 = v26;
      v14 = v25;
    }
    if ( (_DWORD)v14 && v15 )
      DevFreeObjectProperties(v14, v15);
    return 2147942413LL;
  }
}

```

## disassembly

```asm
0x18000a700  mov     r11, rsp
0x18000a703  push    rbx
0x18000a704  push    rdi
0x18000a705  push    r14
0x18000a707  push    r15
0x18000a709  sub     rsp, 88h
0x18000a710  mov     rax, cs:__security_cookie
0x18000a717  xor     rax, rsp
0x18000a71a  mov     [rsp+0A8h+var_38], rax
0x18000a71f  mov     eax, [r8+10h]
0x18000a723  mov     r15, rdx
0x18000a726  movups  xmm0, xmmword ptr [r8]
0x18000a72a  xor     edx, edx
0x18000a72c  mov     [rsp+0A8h+var_48], eax
0x18000a730  lea     rax, [r11-60h]
0x18000a734  mov     [rsp+0A8h+var_44], edx
0x18000a738  mov     [r11-78h], rax
0x18000a73c  mov     r14, r8
0x18000a73f  lea     rax, [r11-68h]
0x18000a743  mov     [r11-60h], rdx
0x18000a747  cmp     r9d, 12h
0x18000a74b  mov     [r11-80h], rax
0x18000a74f  mov     r8d, 4
0x18000a755  mov     [rsp+0A8h+var_68], edx
0x18000a759  movups  [rsp+0A8h+var_58], xmm0
0x18000a75e  lea     rax, [r11-58h]
0x18000a762  mov     [r11-40h], rdx
0x18000a766  mov     edi, r9d
0x18000a769  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18000a76e  cmovnz  r8d, edx
0x18000a772  mov     r9d, 1
0x18000a778  mov     rdx, r15
0x18000a77b  call    cs:__imp_DevGetObjectProperties
0x18000a781  mov     ebx, eax
0x18000a783  test    eax, eax
0x18000a785  jns     short loc_18000A7E1
0x18000a787  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a78e  lea     rdx, WPP_GLOBAL_Control
0x18000a795  cmp     rcx, rdx
0x18000a798  jz      short loc_18000A7C2
0x18000a79a  test    byte ptr [rcx+1Ch], 1
0x18000a79e  jz      short loc_18000A7C2
0x18000a7a0  mov     rcx, [rcx+10h]
0x18000a7a4  mov     edx, 0Bh
0x18000a7a9  mov     [rsp+0A8h+var_78], eax
0x18000a7ad  mov     r9, r14
0x18000a7b0  mov     eax, [r14+10h]
0x18000a7b4  mov     [rsp+0A8h+var_80], r15
0x18000a7b9  mov     [rsp+0A8h+var_88], eax
0x18000a7bd  call    WPP_SF__guid_dSd
0x18000a7c2  mov     ecx, [rsp+0A8h+var_68]
0x18000a7c6  test    ecx, ecx
0x18000a7c8  jz      short loc_18000A7DA
0x18000a7ca  mov     rdx, [rsp+0A8h+var_60]
0x18000a7cf  test    rdx, rdx
0x18000a7d2  jz      short loc_18000A7DA
0x18000a7d4  call    cs:__imp_DevFreeObjectProperties
0x18000a7da  mov     eax, ebx
0x18000a7dc  jmp     loc_18000A8A6
0x18000a7e1  mov     ecx, [rsp+0A8h+var_68]
0x18000a7e5  mov     rax, [rsp+0A8h+var_60]
0x18000a7ea  test    ecx, ecx
0x18000a7ec  jz      loc_18000A9AB
0x18000a7f2  mov     edx, [rax+20h]
0x18000a7f5  test    edx, edx
0x18000a7f7  jz      loc_18000A999
0x18000a7fd  mov     [rsp+0A8h+var_28], rsi
0x18000a805  cmp     ecx, 1
0x18000a808  jnz     loc_18000A941
0x18000a80e  cmp     edx, edi
0x18000a810  jnz     loc_18000A941
0x18000a816  mov     rsi, [rax+28h]
0x18000a81a  test    rsi, rsi
0x18000a81d  jz      loc_18000A941
0x18000a823  mov     [rsp+0A8h+arg_18], rbp
0x18000a82b  mov     ebp, [rax+24h]
0x18000a82e  mov     edi, ebp
0x18000a830  and     rdi, 0FFFFFFFFFFFFFFFEh
0x18000a834  mov     rcx, rdi; cb
0x18000a837  call    cs:__imp_CoTaskMemAlloc
0x18000a83d  mov     rbx, rax
0x18000a840  test    rax, rax
0x18000a843  jz      loc_18000A8C1
0x18000a849  lea     rcx, [rdi+rax]
0x18000a84d  cmp     rax, rcx
0x18000a850  jz      short loc_18000A860
0x18000a852  xor     edx, edx
0x18000a854  mov     [rax], dx
0x18000a857  add     rax, 2
0x18000a85b  cmp     rax, rcx
0x18000a85e  jnz     short loc_18000A852
0x18000a860  mov     r8, rbp; Size
0x18000a863  mov     rdx, rsi; Src
0x18000a866  mov     rcx, rbx; void *
0x18000a869  call    memcpy_0
0x18000a86e  mov     rax, [rsp+0A8h+arg_20]
0x18000a876  mov     rcx, [rax]
0x18000a879  mov     [rcx], rbx
0x18000a87c  mov     ecx, [rsp+0A8h+var_68]
0x18000a880  test    ecx, ecx
0x18000a882  jz      short loc_18000A894
0x18000a884  mov     rdx, [rsp+0A8h+var_60]
0x18000a889  test    rdx, rdx
0x18000a88c  jz      short loc_18000A894
0x18000a88e  call    cs:__imp_DevFreeObjectProperties
0x18000a894  xor     eax, eax
0x18000a896  mov     rbp, [rsp+0A8h+arg_18]
0x18000a89e  mov     rsi, [rsp+0A8h+var_28]
0x18000a8a6  mov     rcx, [rsp+0A8h+var_38]
0x18000a8ab  xor     rcx, rsp; StackCookie
0x18000a8ae  call    __security_check_cookie
0x18000a8b3  add     rsp, 88h
0x18000a8ba  pop     r15
0x18000a8bc  pop     r14
0x18000a8be  pop     rdi
0x18000a8bf  pop     rbx
0x18000a8c0  retn
0x18000a8c1  mov     rcx, [rsp+0A8h]; this
0x18000a8c9  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x18000a8d0  mov     r9d, 8007000Eh; char *
0x18000a8d6  mov     edx, 8Bh; void *
0x18000a8db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a8e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8e7  lea     rdx, WPP_GLOBAL_Control
0x18000a8ee  cmp     rcx, rdx
0x18000a8f1  jz      short loc_18000A91F
0x18000a8f3  test    byte ptr [rcx+1Ch], 1
0x18000a8f7  jz      short loc_18000A91F
0x18000a8f9  mov     eax, [r14+10h]
0x18000a8fd  mov     edx, 0Dh
0x18000a902  mov     rcx, [rcx+10h]
0x18000a906  mov     r9, r14
0x18000a909  mov     [rsp+0A8h+var_78], 8007000Eh
0x18000a911  mov     [rsp+0A8h+var_80], r15
0x18000a916  mov     [rsp+0A8h+var_88], eax
0x18000a91a  call    WPP_SF__guid_dSd
0x18000a91f  mov     ecx, [rsp+0A8h+var_68]
0x18000a923  test    ecx, ecx
0x18000a925  jz      short loc_18000A937
0x18000a927  mov     rdx, [rsp+0A8h+var_60]
0x18000a92c  test    rdx, rdx
0x18000a92f  jz      short loc_18000A937
0x18000a931  call    cs:__imp_DevFreeObjectProperties
0x18000a937  mov     eax, 8007000Eh
0x18000a93c  jmp     loc_18000A896
0x18000a941  mov     r8, cs:WPP_GLOBAL_Control
0x18000a948  lea     rdx, WPP_GLOBAL_Control
0x18000a94f  cmp     r8, rdx
0x18000a952  jz      short loc_18000A97D
0x18000a954  test    byte ptr [r8+1Ch], 1
0x18000a959  jz      short loc_18000A97D
0x18000a95b  mov     eax, [r14+10h]
0x18000a95f  mov     r9, r14
0x18000a962  mov     rcx, [r8+10h]
0x18000a966  mov     [rsp+0A8h+var_80], r15
0x18000a96b  mov     [rsp+0A8h+var_88], eax
0x18000a96f  call    WPP_SF__guid_dS
0x18000a974  mov     rax, [rsp+0A8h+var_60]
0x18000a979  mov     ecx, [rsp+0A8h+var_68]
0x18000a97d  test    ecx, ecx
0x18000a97f  jz      short loc_18000A98F
0x18000a981  test    rax, rax
0x18000a984  jz      short loc_18000A98F
0x18000a986  mov     rdx, rax
0x18000a989  call    cs:__imp_DevFreeObjectProperties
0x18000a98f  mov     eax, 8007000Dh
0x18000a994  jmp     loc_18000A89E
0x18000a999  test    ecx, ecx
0x18000a99b  jz      short loc_18000A9AB
0x18000a99d  test    rax, rax
0x18000a9a0  jz      short loc_18000A9AB
0x18000a9a2  mov     rdx, rax
0x18000a9a5  call    cs:__imp_DevFreeObjectProperties
0x18000a9ab  mov     eax, 80070490h
0x18000a9b0  jmp     loc_18000A8A6
```
