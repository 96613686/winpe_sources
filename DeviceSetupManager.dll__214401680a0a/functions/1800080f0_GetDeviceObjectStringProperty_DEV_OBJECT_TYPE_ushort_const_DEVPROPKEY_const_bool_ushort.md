# GetDeviceObjectStringProperty(_DEV_OBJECT_TYPE,ushort const *,_DEVPROPKEY const &,bool,ushort * *)

- ea: `0x1800080f0`
- end: `0x1800083d5`
- name: `?GetDeviceObjectStringProperty@@YAJW4_DEV_OBJECT_TYPE@@PEBGAEBU_DEVPROPKEY@@_NPEAPEAG@Z`
- size: `741`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180007dc0`
- `0x180009928`
- `0x180010f48`
- `0x1800173ac`
- `0x1800191b0`
- `0x180033d80`
- `0x180036680`
- `0x180036cd8`

## callees

- `0x1800080f0`
- `0x1800112a4`
- `0x18001af70`
- `0x18003f2d0`
- `0x18003f368`
- `0x1800419a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008223`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008223`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180008173`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180008173`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800081a8`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180008279`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800082a0`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800082c2`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800082d8`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800081a8`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180008279`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800082a0`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800082c2`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800082d8`

## pseudocode

```c
__int64 __fastcall GetDeviceObjectStringProperty(__int64 a1, __int64 a2, __int128 *a3, unsigned __int8 a4, _QWORD *a5)
{
  __int128 v5; // xmm0
  __int64 v7; // r8
  int v8; // edi
  int ObjectProperties; // ebx
  int v11; // r8d
  __int64 v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  const void *v16; // rsi
  size_t v17; // rbp
  SIZE_T v18; // rdi
  _WORD *v19; // rax
  void *v20; // rbx
  _WORD *i; // rcx
  int v22; // r8d
  int v23; // [rsp+20h] [rbp-98h]
  unsigned int v24; // [rsp+40h] [rbp-78h] BYREF
  __int64 v25; // [rsp+48h] [rbp-70h] BYREF
  __int128 v26; // [rsp+50h] [rbp-68h] BYREF
  int v27; // [rsp+60h] [rbp-58h]
  int v28; // [rsp+64h] [rbp-54h]
  __int64 v29; // [rsp+68h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v5 = *a3;
  v27 = *((_DWORD *)a3 + 4);
  v7 = 4;
  v8 = (a4 << 13) + 18;
  v26 = v5;
  v25 = 0;
  v24 = 0;
  if ( a4 << 13 )
    v7 = 0;
  v28 = 0;
  v29 = 0;
  ObjectProperties = DevGetObjectProperties(a1, a2, v7, 1, &v26, &v24, &v25);
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
    if ( v24 )
    {
      if ( v25 )
        DevFreeObjectProperties(v24, v25);
    }
    return (unsigned int)ObjectProperties;
  }
  v13 = v24;
  v14 = v25;
  if ( !v24 )
    return 2147943568LL;
  v15 = *(_DWORD *)(v25 + 32);
  if ( !v15 )
  {
    if ( v25 )
      DevFreeObjectProperties(v24, v25);
    return 2147943568LL;
  }
  if ( v24 == 1 && v15 == v8 && (v16 = *(const void **)(v25 + 40)) != 0 )
  {
    v17 = *(unsigned int *)(v25 + 36);
    v18 = (unsigned int)v17 & 0xFFFFFFFE;
    v19 = CoTaskMemAlloc(v18);
    v20 = v19;
    if ( v19 )
    {
      for ( i = (_WORD *)((char *)v19 + v18); v19 != i; ++v19 )
        *v19 = 0;
      memcpy_0(v20, v16, v17);
      *a5 = v20;
      if ( v24 && v25 )
        DevFreeObjectProperties(v24, v25);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
        (const char *)0x8007000ELL,
        v23);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF__guid_dSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v22, (_DWORD)a3, *((_DWORD *)a3 + 4), a2, 14);
      if ( v24 && v25 )
        DevFreeObjectProperties(v24, v25);
      return 2147942414LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF__guid_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v25,
        (_DWORD)WPP_GLOBAL_Control,
        (_DWORD)a3,
        *((_DWORD *)a3 + 4),
        a2);
      v14 = v25;
      v13 = v24;
    }
    if ( (_DWORD)v13 && v14 )
      DevFreeObjectProperties(v13, v14);
    return 2147942413LL;
  }
}

```

## disassembly

```asm
0x1800080f0  mov     r11, rsp
0x1800080f3  push    rbx
0x1800080f4  push    rdi
0x1800080f5  push    r12
0x1800080f7  push    r14
0x1800080f9  push    r15
0x1800080fb  sub     rsp, 90h
0x180008102  mov     rax, cs:__security_cookie
0x180008109  xor     rax, rsp
0x18000810c  mov     [rsp+0B8h+var_48], rax
0x180008111  mov     eax, [r8+10h]
0x180008115  xor     r12d, r12d
0x180008118  movups  xmm0, xmmword ptr [r8]
0x18000811c  mov     [rsp+0B8h+var_58], eax
0x180008120  mov     r14, r8
0x180008123  movzx   edi, r9b
0x180008127  lea     rax, [r11-70h]
0x18000812b  mov     [rsp+0B8h+var_88], rax
0x180008130  mov     r8d, 4
0x180008136  lea     rax, [r11-78h]
0x18000813a  shl     edi, 0Dh
0x18000813d  mov     [rsp+0B8h+var_90], rax
0x180008142  add     edi, 12h
0x180008145  movups  [rsp+0B8h+var_68], xmm0
0x18000814a  lea     rax, [r11-68h]
0x18000814e  mov     [r11-70h], r12
0x180008152  cmp     edi, 12h
0x180008155  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x18000815a  mov     r9d, 1
0x180008160  mov     [r11-78h], r12d
0x180008164  cmovnz  r8d, r12d
0x180008168  mov     [r11-54h], r12d
0x18000816c  mov     r15, rdx
0x18000816f  mov     [r11-50h], r12
0x180008173  call    cs:__imp_DevGetObjectProperties
0x180008179  mov     ebx, eax
0x18000817b  test    eax, eax
0x18000817d  jns     short loc_1800081CD
0x18000817f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008186  lea     rax, WPP_GLOBAL_Control
0x18000818d  cmp     rcx, rax
0x180008190  jnz     loc_1800082F0
0x180008196  mov     ecx, [rsp+0B8h+var_78]
0x18000819a  test    ecx, ecx
0x18000819c  jz      short loc_1800081AE
0x18000819e  mov     rdx, [rsp+0B8h+var_70]
0x1800081a3  test    rdx, rdx
0x1800081a6  jz      short loc_1800081AE
0x1800081a8  call    cs:__imp_DevFreeObjectProperties
0x1800081ae  mov     eax, ebx
0x1800081b0  mov     rcx, [rsp+0B8h+var_48]
0x1800081b5  xor     rcx, rsp; StackCookie
0x1800081b8  call    __security_check_cookie
0x1800081bd  add     rsp, 90h
0x1800081c4  pop     r15
0x1800081c6  pop     r14
0x1800081c8  pop     r12
0x1800081ca  pop     rdi
0x1800081cb  pop     rbx
0x1800081cc  retn
0x1800081cd  mov     ecx, [rsp+0B8h+var_78]
0x1800081d1  mov     rdx, [rsp+0B8h+var_70]
0x1800081d6  test    ecx, ecx
0x1800081d8  jz      loc_1800082A6
0x1800081de  mov     eax, [rdx+20h]
0x1800081e1  test    eax, eax
0x1800081e3  jz      loc_180008297
0x1800081e9  mov     [rsp+0B8h+var_38], rsi
0x1800081f1  cmp     ecx, 1
0x1800081f4  jnz     loc_18000838C
0x1800081fa  cmp     eax, edi
0x1800081fc  jnz     loc_18000838C
0x180008202  mov     rsi, [rdx+28h]
0x180008206  test    rsi, rsi
0x180008209  jz      loc_18000838C
0x18000820f  mov     [rsp+0B8h+var_30], rbp
0x180008217  mov     ebp, [rdx+24h]
0x18000821a  mov     edi, ebp
0x18000821c  and     rdi, 0FFFFFFFFFFFFFFFEh
0x180008220  mov     rcx, rdi; cb
0x180008223  call    cs:__imp_CoTaskMemAlloc
0x180008229  mov     rbx, rax
0x18000822c  test    rax, rax
0x18000822f  jz      loc_180008321
0x180008235  lea     rcx, [rdi+rax]
0x180008239  cmp     rax, rcx
0x18000823c  jz      short loc_18000824E
0x18000823e  xchg    ax, ax
0x180008240  xor     edx, edx
0x180008242  mov     [rax], dx
0x180008245  add     rax, 2
0x180008249  cmp     rax, rcx
0x18000824c  jnz     short loc_180008240
0x18000824e  mov     r8, rbp; Size
0x180008251  mov     rdx, rsi; Src
0x180008254  mov     rcx, rbx; void *
0x180008257  call    memcpy_0
0x18000825c  mov     rax, [rsp+0B8h+arg_20]
0x180008264  mov     [rax], rbx
0x180008267  mov     ecx, [rsp+0B8h+var_78]
0x18000826b  test    ecx, ecx
0x18000826d  jz      short loc_18000827F
0x18000826f  mov     rdx, [rsp+0B8h+var_70]
0x180008274  test    rdx, rdx
0x180008277  jz      short loc_18000827F
0x180008279  call    cs:__imp_DevFreeObjectProperties
0x18000827f  mov     eax, r12d
0x180008282  mov     rbp, [rsp+0B8h+var_30]
0x18000828a  mov     rsi, [rsp+0B8h+var_38]
0x180008292  jmp     loc_1800081B0
0x180008297  test    ecx, ecx
0x180008299  jz      short loc_1800082A6
0x18000829b  test    rdx, rdx
0x18000829e  jz      short loc_1800082A6
0x1800082a0  call    cs:__imp_DevFreeObjectProperties
0x1800082a6  mov     eax, 80070490h
0x1800082ab  jmp     loc_1800081B0
0x1800082b0  mov     ecx, [rsp+0B8h+var_78]
0x1800082b4  test    ecx, ecx
0x1800082b6  jz      short loc_1800082C8
0x1800082b8  mov     rdx, [rsp+0B8h+var_70]
0x1800082bd  test    rdx, rdx
0x1800082c0  jz      short loc_1800082C8
0x1800082c2  call    cs:__imp_DevFreeObjectProperties
0x1800082c8  mov     eax, 8007000Eh
0x1800082cd  jmp     short loc_180008282
0x1800082cf  test    ecx, ecx
0x1800082d1  jz      short loc_1800082DE
0x1800082d3  test    rdx, rdx
0x1800082d6  jz      short loc_1800082DE
0x1800082d8  call    cs:__imp_DevFreeObjectProperties
0x1800082de  mov     rsi, [rsp+0B8h+var_38]
0x1800082e6  mov     eax, 8007000Dh
0x1800082eb  jmp     loc_1800081B0
0x1800082f0  test    byte ptr [rcx+1Ch], 1
0x1800082f4  jz      loc_180008196
0x1800082fa  mov     eax, [r14+10h]
0x1800082fe  mov     edx, 0Bh
0x180008303  mov     rcx, [rcx+10h]
0x180008307  mov     r9, r14
0x18000830a  mov     dword ptr [rsp+0B8h+var_88], ebx
0x18000830e  mov     [rsp+0B8h+var_90], r15
0x180008313  mov     [rsp+0B8h+var_98], eax
0x180008317  call    WPP_SF__guid_dSd
0x18000831c  jmp     loc_180008196
0x180008321  mov     rcx, [rsp+0B8h]; this
0x180008329  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x180008330  mov     r9d, 8007000Eh; char *
0x180008336  mov     edx, 8Bh; void *
0x18000833b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008340  mov     rcx, cs:WPP_GLOBAL_Control
0x180008347  lea     rax, WPP_GLOBAL_Control
0x18000834e  cmp     rcx, rax
0x180008351  jz      loc_1800082B0
0x180008357  test    byte ptr [rcx+1Ch], 1
0x18000835b  jz      loc_1800082B0
0x180008361  mov     eax, [r14+10h]
0x180008365  mov     edx, 0Dh
0x18000836a  mov     rcx, [rcx+10h]
0x18000836e  mov     r9, r14
0x180008371  mov     dword ptr [rsp+0B8h+var_88], 8007000Eh
0x180008379  mov     [rsp+0B8h+var_90], r15
0x18000837e  mov     [rsp+0B8h+var_98], eax
0x180008382  call    WPP_SF__guid_dSd
0x180008387  jmp     loc_1800082B0
0x18000838c  mov     r8, cs:WPP_GLOBAL_Control
0x180008393  lea     rax, WPP_GLOBAL_Control
0x18000839a  cmp     r8, rax
0x18000839d  jz      loc_1800082CF
0x1800083a3  test    byte ptr [r8+1Ch], 1
0x1800083a8  jz      loc_1800082CF
0x1800083ae  mov     eax, [r14+10h]
0x1800083b2  mov     r9, r14
0x1800083b5  mov     rcx, [r8+10h]
0x1800083b9  mov     [rsp+0B8h+var_90], r15
0x1800083be  mov     [rsp+0B8h+var_98], eax
0x1800083c2  call    WPP_SF__guid_dS
0x1800083c7  mov     rdx, [rsp+0B8h+var_70]
0x1800083cc  mov     ecx, [rsp+0B8h+var_78]
0x1800083d0  jmp     loc_1800082CF
```
