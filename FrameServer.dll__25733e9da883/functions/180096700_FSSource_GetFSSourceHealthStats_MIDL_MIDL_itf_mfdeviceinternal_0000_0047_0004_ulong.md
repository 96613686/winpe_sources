# FSSource::GetFSSourceHealthStats(__MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004 * *,ulong *)

- ea: `0x180096700`
- end: `0x180096947`
- name: `?GetFSSourceHealthStats@FSSource@@UEAAJPEAPEAU__MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004@@PEAK@Z`
- size: `583`
- prototype: `__int64 __fastcall(FSSource *__hidden this, struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004 **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000478c`
- `0x180009608`
- `0x18004fd84`
- `0x180096700`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800967ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800967ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180096738`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180096738`

## pseudocode

```c
__int64 __fastcall FSSource::GetFSSourceHealthStats(
        FSSource *this,
        struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004 **a2,
        unsigned int *a3)
{
  unsigned int v3; // r14d
  SIZE_T v5; // r15
  char *v7; // rax
  struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004 *v8; // rbx
  char *v9; // rsi
  char *v10; // rdi
  int v11; // eax
  unsigned int v12; // esi
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // edi
  __int64 v16; // r15
  __int64 v17; // r12
  char *v18; // r13
  __int64 v19; // rcx
  __int64 v20; // rcx
  _QWORD *v22; // [rsp+30h] [rbp-48h]
  int v23; // [rsp+80h] [rbp+8h] BYREF
  struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004 **v24; // [rsp+88h] [rbp+10h]
  __int64 v25; // [rsp+98h] [rbp+20h] BYREF

  v24 = a2;
  v3 = *((_DWORD *)this + 74);
  v5 = 352LL * v3;
  v23 = 0;
  v7 = (char *)CoTaskMemAlloc(v5);
  v8 = (struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004 *)v7;
  if ( v7 )
  {
    v9 = &v7[v5];
    v10 = v7;
    if ( v7 != &v7[v5] )
    {
      do
      {
        memset_0(v10, 0, 0x160u);
        v10 += 352;
      }
      while ( v10 != v9 );
      v10 = (char *)v8;
    }
    if ( !a3 )
    {
      v11 = -2147024882;
      v12 = -2147024882;
      if ( g_wppLevels )
      {
        v13 = 254;
LABEL_12:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids, this, v11);
        goto LABEL_13;
      }
      goto LABEL_13;
    }
    *a3 = v3;
    v12 = 0;
    memset_0(v10, 0, v5);
    v14 = *((_QWORD *)this + 22);
    if ( v14 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004 *, int *))(*(_QWORD *)v14 + 24LL))(
              v14,
              v3,
              v8,
              &v23);
      v12 = v11;
      if ( v11 < 0 )
      {
        if ( g_wppLevels )
        {
          v13 = 255;
          goto LABEL_12;
        }
LABEL_13:
        CoTaskMemFree(v10);
        return v12;
      }
    }
    v15 = 0;
    if ( v3 )
    {
      v16 = 0;
      do
      {
        v17 = 352 * v16;
        v25 = 0;
        *(_DWORD *)((char *)v8 + v17) = 352;
        v18 = (char *)v8 + 352 * v16;
        *(_DWORD *)((char *)v8 + v17 + 4) = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 36) + 8 * v16) + 92LL);
        v22 = *(_QWORD **)(*((_QWORD *)this + 36) + 8 * v16);
        FSStatTracker::GetStats(
          (FSStatTracker *)(v22 + 71),
          (struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0004 *)((char *)v8 + 352 * v16 + 304));
        v19 = v22[48];
        if ( v19 )
        {
          (*(void (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v19 + 80LL))(
            v19,
            (__int64)v8 + v17 + 208,
            v18 + 256);
        }
        else
        {
          *(_WORD *)((char *)v8 + v17 + 208) = 0;
          *((_WORD *)v18 + 128) = 0;
        }
        _InterlockedExchange64(&v25, v22[89]);
        v20 = v25;
        if ( v25 < 0 )
          v20 = 0;
        ++v15;
        ++v16;
        *(_QWORD *)((char *)v8 + v17 + 8) = v20;
      }
      while ( v15 < v3 );
    }
    *v24 = v8;
  }
  else
  {
    v12 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        253,
        &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids,
        this,
        -2147024882);
  }
  return v12;
}

```

## disassembly

```asm
0x180096700  mov     rax, rsp
0x180096703  mov     [rax+18h], rbx
0x180096707  mov     [rax+10h], rdx
0x18009670b  push    rbp
0x18009670c  push    rsi
0x18009670d  push    rdi
0x18009670e  push    r12
0x180096710  push    r13
0x180096712  push    r14
0x180096714  push    r15
0x180096716  sub     rsp, 40h
0x18009671a  mov     r14d, [rcx+128h]
0x180096721  mov     rbp, rcx
0x180096724  imul    r15, r14, 160h
0x18009672b  mov     r12, r8
0x18009672e  mov     dword ptr [rax+8], 0
0x180096735  mov     rcx, r15; cb
0x180096738  call    cs:__imp_CoTaskMemAlloc
0x18009673e  mov     rbx, rax
0x180096741  test    rax, rax
0x180096744  jz      loc_1800968FA
0x18009674a  lea     rsi, [r15+rax]
0x18009674e  mov     rdi, rax
0x180096751  cmp     rax, rsi
0x180096754  jz      short loc_180096775
0x180096756  xor     edx, edx; Val
0x180096758  mov     r8d, 160h; Size
0x18009675e  mov     rcx, rdi; void *
0x180096761  call    memset_0
0x180096766  add     rdi, 160h
0x18009676d  cmp     rdi, rsi
0x180096770  jnz     short loc_180096756
0x180096772  mov     rdi, rbx
0x180096775  test    r12, r12
0x180096778  jnz     short loc_180096791
0x18009677a  mov     eax, 8007000Eh
0x18009677f  mov     esi, eax
0x180096781  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180096788  jb      short loc_1800967FC
0x18009678a  mov     edx, 0FEh
0x18009678f  jmp     short loc_1800967DE
0x180096791  mov     r8, r15; Size
0x180096794  mov     [r12], r14d
0x180096798  xor     edx, edx; Val
0x18009679a  mov     rcx, rdi; void *
0x18009679d  xor     esi, esi
0x18009679f  call    memset_0
0x1800967a4  mov     rcx, [rbp+0B0h]
0x1800967ab  test    rcx, rcx
0x1800967ae  jz      short loc_18009680A
0x1800967b0  mov     rax, [rcx]
0x1800967b3  lea     r9, [rsp+78h+arg_0]
0x1800967bb  mov     r8, rbx
0x1800967be  mov     edx, r14d
0x1800967c1  mov     rax, [rax+18h]
0x1800967c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800967ca  mov     esi, eax
0x1800967cc  test    eax, eax
0x1800967ce  jns     short loc_18009680A
0x1800967d0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800967d7  jb      short loc_1800967FC
0x1800967d9  mov     edx, 0FFh
0x1800967de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800967e5  lea     r8, WPP_adf67030a59d332a335e13d5925f79fa_Traceguids
0x1800967ec  mov     r9, rbp
0x1800967ef  mov     [rsp+78h+var_58], eax
0x1800967f3  mov     rcx, [rcx+10h]
0x1800967f7  call    WPP_SF_qD
0x1800967fc  mov     rcx, rdi; pv
0x1800967ff  call    cs:__imp_CoTaskMemFree
0x180096805  jmp     loc_18009692D
0x18009680a  xor     edi, edi
0x18009680c  test    r14d, r14d
0x18009680f  jz      loc_1800968ED
0x180096815  xor     r15d, r15d
0x180096818  imul    r12, r15, 160h
0x18009681f  lea     rdx, [rbx+130h]
0x180096826  mov     [rsp+78h+arg_18], 0
0x180096832  add     rdx, r12; struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0003 *
0x180096835  mov     dword ptr [r12+rbx], 160h
0x18009683d  lea     r13, [r12+rbx]
0x180096841  mov     rax, [rbp+120h]
0x180096848  mov     rcx, [rax+r15*8]
0x18009684c  mov     eax, [rcx+5Ch]
0x18009684f  mov     [r12+rbx+4], eax
0x180096854  mov     rax, [rbp+120h]
0x18009685b  mov     rax, [rax+r15*8]
0x18009685f  mov     [rsp+78h+var_48], rax
0x180096864  lea     rcx, [rax+238h]; this
0x18009686b  call    ?GetStats@FSStatTracker@@QEAAXAEAU__MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0003@@@Z; FSStatTracker::GetStats(__MIDL___MIDL_itf_mfdeviceinternal_0000_0047_0003 &)
0x180096870  mov     rax, [rsp+78h+var_48]
0x180096875  mov     rcx, [rax+180h]
0x18009687c  test    rcx, rcx
0x18009687f  jz      short loc_1800968A0
0x180096881  mov     rax, [rcx]
0x180096884  lea     rdx, [rbx+0D0h]
0x18009688b  lea     r8, [r13+100h]
0x180096892  add     rdx, r12
0x180096895  mov     rax, [rax+50h]
0x180096899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009689e  jmp     short loc_1800968B5
0x1800968a0  xor     eax, eax
0x1800968a2  lea     rdx, [r12+rbx]
0x1800968a6  mov     [rdx+0D0h], ax
0x1800968ad  mov     [r13+100h], ax
0x1800968b5  mov     rax, [rsp+78h+var_48]
0x1800968ba  mov     rax, [rax+2C8h]
0x1800968c1  xchg    rax, [rsp+78h+arg_18]
0x1800968c9  mov     rcx, [rsp+78h+arg_18]
0x1800968d1  xor     eax, eax
0x1800968d3  test    rcx, rcx
0x1800968d6  cmovs   rcx, rax
0x1800968da  inc     edi
0x1800968dc  inc     r15
0x1800968df  mov     [r12+rbx+8], rcx
0x1800968e4  cmp     edi, r14d
0x1800968e7  jb      loc_180096818
0x1800968ed  mov     rax, [rsp+78h+arg_8]
0x1800968f5  mov     [rax], rbx
0x1800968f8  jmp     short loc_18009692D
0x1800968fa  mov     eax, 8007000Eh
0x1800968ff  mov     esi, eax
0x180096901  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180096908  jb      short loc_18009692D
0x18009690a  mov     rcx, cs:WPP_GLOBAL_Control
0x180096911  lea     r8, WPP_adf67030a59d332a335e13d5925f79fa_Traceguids
0x180096918  mov     edx, 0FDh
0x18009691d  mov     [rsp+78h+var_58], eax
0x180096921  mov     r9, rbp
0x180096924  mov     rcx, [rcx+10h]
0x180096928  call    WPP_SF_qD
0x18009692d  mov     rbx, [rsp+78h+arg_10]
0x180096935  mov     eax, esi
0x180096937  add     rsp, 40h
0x18009693b  pop     r15
0x18009693d  pop     r14
0x18009693f  pop     r13
0x180096941  pop     r12
0x180096943  pop     rdi
0x180096944  pop     rsi
0x180096945  pop     rbp
0x180096946  retn
```
