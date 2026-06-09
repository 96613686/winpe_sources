# CreateXpstoGdiConverter

- ea: `0x18000d1b0`
- end: `0x18000d3d1`
- name: `CreateXpstoGdiConverter`
- size: `545`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008854`
- `0x180009de0`
- `0x18000d1b0`
- `0x18000d3d8`
- `0x18000d428`
- `0x18000d468`
- `0x18000d4b0`
- `0x18000e25c`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateXpstoGdiConverter(_QWORD *a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  PVOID *v6; // rcx
  __int64 v8; // rax
  CXgcLight *v9; // rcx
  int v10; // edi
  CXgcLight *v11; // r14
  __int64 v12; // rdx
  __int64 v13; // r8
  CXgcLight *v14; // [rsp+30h] [rbp-38h]
  const xpsrdr::hr_error *v15; // [rsp+38h] [rbp-30h] BYREF

  v3 = a3;
  v4 = a2;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, &WPP_427dfabe8dae3508bd814f2717b0f6f5_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v3 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 57) & 0x200) != 0 )
      WPP_SF_sd(
        (unsigned int)v6[27],
        11,
        (unsigned int)&WPP_427dfabe8dae3508bd814f2717b0f6f5_Traceguids,
        (unsigned int)"POINTER",
        3);
    return 2147500035LL;
  }
  v8 = *a1 - *(_QWORD *)&CLSID_XGC.Data1;
  if ( *a1 == *(_QWORD *)&CLSID_XGC.Data1 )
    v8 = a1[1] - *(_QWORD *)CLSID_XGC.Data4;
  if ( !v8 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 57) & 0x200) != 0 )
      WPP_SF__guid__guid_((unsigned int)v6[27], a2, (_DWORD)a3, (_DWORD)a1, v4);
    try
    {
      *v3 = 0;
      v9 = (CXgcLight *)operator new(0x3A8u);
      v11 = CXgcLight::CXgcLight(v9);
      v14 = v11;
    }
    catch ( std::bad_alloc )
    {
      v10 = -2147024882;
      goto LABEL_25;
    }
    catch ( const xpsrdr::hr_error *v15 )
    {
      v10 = *((_DWORD *)v15 + 6);
      if ( v10 < 0 )
        goto LABEL_25;
      v3 = a3;
      v4 = a2;
      v11 = v14;
    }
    catch ( std::exception )
    {
      v10 = -2147467259;
      goto LABEL_25;
    }
    catch ( ... )
    {
      v10 = -2147418113;
      goto LABEL_25;
    }
    v10 = (**(__int64 (__fastcall ***)(CXgcLight *, __int64, _QWORD *))v11)(v11, v4, v3);
    (*(void (__fastcall **)(CXgcLight *))(*(_QWORD *)v11 + 16LL))(v11);
    if ( v10 >= 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return (unsigned int)v10;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), v12, v13, *v3);
    }
LABEL_25:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        15,
        &WPP_427dfabe8dae3508bd814f2717b0f6f5_Traceguids,
        (unsigned int)v10);
    return (unsigned int)v10;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 57) & 0x200) != 0 )
    WPP_SF_sd(
      (unsigned int)v6[27],
      12,
      (unsigned int)&WPP_427dfabe8dae3508bd814f2717b0f6f5_Traceguids,
      (unsigned int)"EXP",
      17);
  return 2147746065LL;
}

```

## disassembly

```asm
0x18000d1b0  mov     [rsp+arg_10], r8
0x18000d1b5  mov     [rsp+arg_8], rdx
0x18000d1ba  push    rbx
0x18000d1bb  push    rsi
0x18000d1bc  push    rdi
0x18000d1bd  push    r14
0x18000d1bf  push    r15
0x18000d1c1  sub     rsp, 40h
0x18000d1c5  mov     rsi, r8
0x18000d1c8  mov     r15, rdx
0x18000d1cb  mov     rdi, rcx
0x18000d1ce  lea     rbx, WPP_GLOBAL_Control
0x18000d1d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1dc  cmp     rcx, rbx
0x18000d1df  jz      short loc_18000D20C
0x18000d1e1  test    dword ptr [rcx+0E4h], 200h
0x18000d1eb  jz      short loc_18000D20C
0x18000d1ed  mov     edx, 0Ah
0x18000d1f2  lea     r8, WPP_427dfabe8dae3508bd814f2717b0f6f5_Traceguids
0x18000d1f9  mov     rcx, [rcx+0D8h]
0x18000d200  call    WPP_SF_
0x18000d205  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d20c  test    rsi, rsi
0x18000d20f  jnz     short loc_18000D251
0x18000d211  cmp     rcx, rbx
0x18000d214  jz      short loc_18000D247
0x18000d216  test    dword ptr [rcx+0E4h], 200h
0x18000d220  jz      short loc_18000D247
0x18000d222  lea     edx, [rsi+0Bh]
0x18000d225  mov     dword ptr [rsp+68h+var_48], 80004003h
0x18000d22d  lea     r9, aPointer; "POINTER"
0x18000d234  lea     r8, WPP_427dfabe8dae3508bd814f2717b0f6f5_Traceguids
0x18000d23b  mov     rcx, [rcx+0D8h]
0x18000d242  call    WPP_SF_sd
0x18000d247  mov     eax, 80004003h
0x18000d24c  jmp     loc_18000D3C5
0x18000d251  mov     rax, [rdi]
0x18000d254  sub     rax, qword ptr cs:CLSID_XGC.Data1
0x18000d25b  jnz     short loc_18000D268
0x18000d25d  mov     rax, [rdi+8]
0x18000d261  sub     rax, qword ptr cs:CLSID_XGC.Data4
0x18000d268  test    rax, rax
0x18000d26b  jz      short loc_18000D2AF
0x18000d26d  cmp     rcx, rbx
0x18000d270  jz      short loc_18000D2A5
0x18000d272  test    dword ptr [rcx+0E4h], 200h
0x18000d27c  jz      short loc_18000D2A5
0x18000d27e  mov     edx, 0Ch
0x18000d283  mov     dword ptr [rsp+68h+var_48], 80040111h
0x18000d28b  lea     r9, aExp; "EXP"
0x18000d292  lea     r8, WPP_427dfabe8dae3508bd814f2717b0f6f5_Traceguids
0x18000d299  mov     rcx, [rcx+0D8h]
0x18000d2a0  call    WPP_SF_sd
0x18000d2a5  mov     eax, 80040111h
0x18000d2aa  jmp     loc_18000D3C5
0x18000d2af  cmp     rcx, rbx
0x18000d2b2  jz      short loc_18000D2D4
0x18000d2b4  test    dword ptr [rcx+0E4h], 200h
0x18000d2be  jz      short loc_18000D2D4
0x18000d2c0  mov     [rsp+68h+var_48], r15
0x18000d2c5  mov     r9, rdi
0x18000d2c8  mov     rcx, [rcx+0D8h]
0x18000d2cf  call    WPP_SF__guid__guid_
0x18000d2d4  mov     qword ptr [rsi], 0
0x18000d2db  mov     [rsp+68h+var_38], 0
0x18000d2e4  mov     ecx, 3A8h; Size
0x18000d2e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d2ee  mov     [rsp+68h+arg_18], rax
0x18000d2f6  mov     rcx, rax; this
0x18000d2f9  call    ??0CXgcLight@@QEAA@XZ; CXgcLight::CXgcLight(void)
0x18000d2fe  mov     r14, rax
0x18000d301  mov     [rsp+68h+var_38], rax
0x18000d306  jmp     short loc_18000D32E
0x18000d308  jmp     short loc_18000D382
0x18000d30a  mov     edi, dword ptr [rsp+68h+arg_18]
0x18000d311  lea     rbx, WPP_GLOBAL_Control
0x18000d318  test    edi, edi
0x18000d31a  js      short loc_18000D390
0x18000d31c  mov     rsi, [rsp+68h+arg_10]
0x18000d324  mov     r15, [rsp+68h+arg_8]
0x18000d329  mov     r14, [rsp+68h+var_38]
0x18000d32e  mov     rax, [r14]
0x18000d331  mov     r8, rsi
0x18000d334  mov     rdx, r15
0x18000d337  mov     rcx, r14
0x18000d33a  mov     rax, [rax]
0x18000d33d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d342  mov     edi, eax
0x18000d344  mov     rdx, [r14]
0x18000d347  mov     rcx, r14
0x18000d34a  mov     rax, [rdx+10h]
0x18000d34e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d353  test    edi, edi
0x18000d355  js      short loc_18000D390
0x18000d357  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d35e  cmp     rcx, rbx
0x18000d361  jz      short loc_18000D3C3
0x18000d363  test    dword ptr [rcx+0E4h], 200h
0x18000d36d  jz      short loc_18000D390
0x18000d36f  mov     r9, [rsi]
0x18000d372  mov     rcx, [rcx+0D8h]
0x18000d379  call    WPP_SF_q
0x18000d37e  jmp     short loc_18000D390
0x18000d380  jmp     short $+2
0x18000d382  lea     rbx, WPP_GLOBAL_Control
0x18000d389  mov     edi, dword ptr [rsp+68h+arg_18]
0x18000d390  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d397  cmp     rcx, rbx
0x18000d39a  jz      short loc_18000D3C3
0x18000d39c  test    dword ptr [rcx+0E4h], 200h
0x18000d3a6  jz      short loc_18000D3C3
0x18000d3a8  mov     edx, 0Fh
0x18000d3ad  mov     r9d, edi
0x18000d3b0  lea     r8, WPP_427dfabe8dae3508bd814f2717b0f6f5_Traceguids
0x18000d3b7  mov     rcx, [rcx+0D8h]
0x18000d3be  call    WPP_SF_d
0x18000d3c3  mov     eax, edi
0x18000d3c5  add     rsp, 40h
0x18000d3c9  pop     r15
0x18000d3cb  pop     r14
0x18000d3cd  pop     rdi
0x18000d3ce  pop     rsi
0x18000d3cf  pop     rbx
0x18000d3d0  retn
```
