# CSwitchThumbnailDeviceManager::_LoadPVLInfoForTarget(DCompThumbnailAnimation,int,int)

- ea: `0x1800561e8`
- end: `0x1800565c9`
- name: `?_LoadPVLInfoForTarget@CSwitchThumbnailDeviceManager@@AEAAJW4DCompThumbnailAnimation@@HH@Z`
- size: `993`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180056000`

## callees

- `0x1800561e8`
- `0x1800565d0`
- `0x1800565fc`
- `0x180142e34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056318`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800563b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005644c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005646b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800564e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800564fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056318`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800563b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005644c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005646b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800564e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800564fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180056307`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800563a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180056307`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800563a2`
- `UxTheme!GetThemeAnimationTransform` at `0x1800562ea`
- `UxTheme!GetThemeAnimationTransform` at `0x180056351`
- `UxTheme!GetThemeAnimationTransform` at `0x1800562ea`
- `UxTheme!GetThemeAnimationTransform` at `0x180056351`
- `UxTheme!OpenThemeData` at `0x180056226`
- `UxTheme!OpenThemeData` at `0x18005624e`
- `UxTheme!OpenThemeData` at `0x180056226`
- `UxTheme!OpenThemeData` at `0x18005624e`
- `UxTheme!GetThemeAnimationProperty` at `0x180056298`
- `UxTheme!GetThemeAnimationProperty` at `0x180056298`
- `UxTheme!GetThemeTimingFunction` at `0x180056385`
- `UxTheme!GetThemeTimingFunction` at `0x1800563e2`
- `UxTheme!GetThemeTimingFunction` at `0x180056385`
- `UxTheme!GetThemeTimingFunction` at `0x1800563e2`
- `UxTheme!CloseThemeData` at `0x180056521`
- `UxTheme!CloseThemeData` at `0x180056530`
- `UxTheme!CloseThemeData` at `0x180056521`
- `UxTheme!CloseThemeData` at `0x180056530`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSwitchThumbnailDeviceManager::_LoadPVLInfoForTarget(
        __int64 a1,
        int a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v4; // r12d
  unsigned int v5; // esi
  int ThemeAnimationProperty; // r14d
  HTHEME v7; // rdi
  HTHEME v8; // r15
  unsigned int v9; // ebx
  unsigned int *v10; // r13
  void *v11; // rsi
  LPVOID v12; // r12
  void *v13; // rdi
  _QWORD *v14; // rax
  _QWORD *v15; // r15
  void *v16; // rcx
  void *v17; // rcx
  __int64 v18; // rdx
  _QWORD *v19; // rdx
  __int64 v21; // rax
  unsigned int cb; // [rsp+48h] [rbp-29h] BYREF
  unsigned int cb_4; // [rsp+4Ch] [rbp-25h] BYREF
  unsigned int v24; // [rsp+50h] [rbp-21h] BYREF
  int i; // [rsp+54h] [rbp-1Dh]
  int v26; // [rsp+58h] [rbp-19h] BYREF
  HTHEME v27; // [rsp+60h] [rbp-11h]
  HTHEME v28; // [rsp+68h] [rbp-9h]
  _QWORD *v29; // [rsp+70h] [rbp-1h]
  __int64 v30; // [rsp+78h] [rbp+7h]
  __int64 v31; // [rsp+80h] [rbp+Fh]

  v4 = a4;
  v5 = a3;
  ThemeAnimationProperty = -2147467259;
  v7 = OpenThemeData(0, L"ANIMATIONS");
  v28 = v7;
  if ( v7 )
  {
    v8 = OpenThemeData(0, L"TIMINGFUNCTION");
    v27 = v8;
    if ( v8 )
    {
      v26 = 0;
      v24 = 0;
      ThemeAnimationProperty = GetThemeAnimationProperty(v7, v5, v4, 1, &v24, 4, &v26);
      if ( ThemeAnimationProperty >= 0 )
      {
        v9 = 0;
        for ( i = 0; v9 < v24; i = ++v9 )
        {
          if ( ThemeAnimationProperty < 0 )
            break;
          cb = 0;
          ThemeAnimationProperty = GetThemeAnimationTransform(v7, v5, v4, v9, 0, 0, &cb);
          if ( ThemeAnimationProperty == -2147024662 )
          {
            v10 = (unsigned int *)CoTaskMemAlloc(cb);
            CoTaskMemFree(0);
            v11 = v10;
            if ( v10 )
            {
              ThemeAnimationProperty = GetThemeAnimationTransform(v7, a3, v4, v9, v10, cb, &cb);
              if ( ThemeAnimationProperty >= 0 )
              {
                cb_4 = 0;
                ThemeAnimationProperty = GetThemeTimingFunction(v8, v10[1], 0, 0, &cb_4);
                if ( ThemeAnimationProperty == -2147024662 )
                {
                  v12 = CoTaskMemAlloc(cb_4);
                  CoTaskMemFree(0);
                  v13 = v12;
                  if ( v12 )
                  {
                    ThemeAnimationProperty = GetThemeTimingFunction(v8, v10[1], v12, cb_4, &cb_4);
                    if ( ThemeAnimationProperty >= 0 )
                    {
                      v14 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
                      v15 = v14;
                      v29 = v14;
                      ThemeAnimationProperty = 0;
                      if ( v14 )
                      {
                        *(_OWORD *)v14 = 0;
                        v14[1] = 0;
                        v14[2] = 0;
                      }
                      else
                      {
                        v15 = 0;
                      }
                      if ( v15 )
                      {
                        *(_DWORD *)v15 = a2;
                        v11 = 0;
                        v29 = 0;
                        v16 = (void *)v15[1];
                        v15[1] = 0;
                        CoTaskMemFree(v16);
                        v15[1] = v10;
                        v13 = 0;
                        v30 = 0;
                        v17 = (void *)v15[2];
                        v15[2] = 0;
                        CoTaskMemFree(v17);
                        v15[2] = v12;
                        if ( *(_BYTE *)(a1 + 258) )
                        {
                          v21 = v15[1];
                          if ( *(_DWORD *)v21 == 260 )
                          {
                            *(float *)(v21 + 36) = *(float *)(v21 + 36) * -1.0;
                            *(float *)(v21 + 44) = 1.0 - *(float *)(v21 + 44);
                            *(float *)(v21 + 24) = *(float *)(v21 + 24) * -1.0;
                          }
                        }
                        v31 = 0;
                        v18 = *(_QWORD *)(a1 + 168);
                        if ( v18 != *(_QWORD *)(a1 + 184)
                          || (ThemeAnimationProperty = CTSimpleArray<CSwitchThumbnailDeviceManager::AnimationPVLInfo *,4294967294,CTPolicyCoTaskMem<CSwitchThumbnailDeviceManager::AnimationPVLInfo *>,CSimpleArrayStandardCompareHelper<CSwitchThumbnailDeviceManager::AnimationPVLInfo *>,CSimpleArrayStandardMergeHelper<CSwitchThumbnailDeviceManager::AnimationPVLInfo *>>::_EnsureCapacity(
                                                         a1 + 160,
                                                         v18 + 1),
                              ThemeAnimationProperty >= 0) )
                        {
                          v19 = (_QWORD *)(*(_QWORD *)(a1 + 160) + 8 * (*(_QWORD *)(a1 + 168))++);
                          if ( v19 )
                            *v19 = v15;
                        }
                      }
                      else
                      {
                        ThemeAnimationProperty = -2147024882;
                      }
                      CTContainer_PolicyNewMem::Destroy<CSwitchThumbnailDeviceManager::AnimationPVLInfo>(0);
                      v9 = i;
                      v8 = v27;
                    }
                  }
                  else
                  {
                    ThemeAnimationProperty = -2147024882;
                  }
                  CoTaskMemFree(v13);
                  v7 = v28;
                  v4 = a4;
                }
              }
            }
            else
            {
              ThemeAnimationProperty = -2147024882;
            }
            CoTaskMemFree(v11);
            v5 = a3;
          }
        }
      }
      CloseThemeData(v8);
    }
    CloseThemeData(v7);
  }
  return (unsigned int)ThemeAnimationProperty;
}

```

## disassembly

```asm
0x1800561e8  mov     rax, rsp
0x1800561eb  mov     [rax+20h], r9d
0x1800561ef  mov     [rax+18h], r8d
0x1800561f3  mov     [rax+10h], edx
0x1800561f6  mov     [rax+8], rcx
0x1800561fa  push    rbp
0x1800561fb  push    rbx
0x1800561fc  push    rsi
0x1800561fd  push    rdi
0x1800561fe  push    r12
0x180056200  push    r13
0x180056202  push    r14
0x180056204  push    r15
0x180056206  lea     rbp, [rax-5Fh]
0x18005620a  sub     rsp, 88h
0x180056211  mov     r12d, r9d
0x180056214  mov     esi, r8d
0x180056217  mov     r14d, 80004005h
0x18005621d  lea     rdx, aAnimations; "ANIMATIONS"
0x180056224  xor     ecx, ecx; hwnd
0x180056226  call    cs:__imp_OpenThemeData
0x18005622d  nop     dword ptr [rax+rax+00h]
0x180056232  mov     rdi, rax
0x180056235  mov     [rbp+57h+var_60], rax
0x180056239  xor     r13d, r13d
0x18005623c  test    rax, rax
0x18005623f  jz      loc_18005653C
0x180056245  lea     rdx, aTimingfunction; "TIMINGFUNCTION"
0x18005624c  xor     ecx, ecx; hwnd
0x18005624e  call    cs:__imp_OpenThemeData
0x180056255  nop     dword ptr [rax+rax+00h]
0x18005625a  mov     r15, rax
0x18005625d  mov     [rbp+57h+var_68], rax
0x180056261  test    rax, rax
0x180056264  jz      loc_18005652D
0x18005626a  mov     [rbp+57h+var_70], r13d
0x18005626e  mov     [rbp+57h+var_78], r13d
0x180056272  lea     rax, [rbp+57h+var_70]
0x180056276  mov     [rsp+30h], rax
0x18005627b  mov     dword ptr [rsp+0C0h+var_98], 4
0x180056283  lea     rax, [rbp+57h+var_78]
0x180056287  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18005628c  lea     r9d, [r13+1]
0x180056290  mov     r8d, r12d
0x180056293  mov     edx, esi
0x180056295  mov     rcx, rdi
0x180056298  call    cs:__imp_GetThemeAnimationProperty
0x18005629f  nop     dword ptr [rax+rax+00h]
0x1800562a4  mov     r14d, eax
0x1800562a7  test    eax, eax
0x1800562a9  js      loc_18005651E
0x1800562af  mov     ebx, r13d
0x1800562b2  mov     [rbp+57h+var_74], ebx
0x1800562b5  cmp     [rbp+57h+var_78], r13d
0x1800562b9  jbe     loc_18005651E
0x1800562bf  test    r14d, r14d
0x1800562c2  js      loc_18005651E
0x1800562c8  mov     dword ptr [rbp+57h+cb], r13d
0x1800562cc  lea     rax, [rbp+57h+cb]
0x1800562d0  mov     [rsp+30h], rax
0x1800562d5  mov     dword ptr [rsp+0C0h+var_98], r13d
0x1800562da  mov     qword ptr [rsp+0C0h+var_A0], r13
0x1800562df  mov     r9d, ebx
0x1800562e2  mov     r8d, r12d
0x1800562e5  mov     edx, esi
0x1800562e7  mov     rcx, rdi
0x1800562ea  call    cs:__imp_GetThemeAnimationTransform
0x1800562f1  nop     dword ptr [rax+rax+00h]
0x1800562f6  mov     r14d, eax
0x1800562f9  cmp     eax, 800700EAh
0x1800562fe  jnz     loc_180056510
0x180056304  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x180056307  call    cs:__imp_CoTaskMemAlloc
0x18005630e  nop     dword ptr [rax+rax+00h]
0x180056313  mov     r13, rax
0x180056316  xor     ecx, ecx; pv
0x180056318  call    cs:__imp_CoTaskMemFree
0x18005631f  nop     dword ptr [rax+rax+00h]
0x180056324  mov     rsi, r13
0x180056327  test    r13, r13
0x18005632a  jz      loc_1800565BD
0x180056330  mov     ecx, dword ptr [rbp+57h+cb]
0x180056333  lea     rax, [rbp+57h+cb]
0x180056337  mov     [rsp+30h], rax
0x18005633c  mov     dword ptr [rsp+0C0h+var_98], ecx
0x180056340  mov     qword ptr [rsp+0C0h+var_A0], r13
0x180056345  mov     r9d, ebx
0x180056348  mov     r8d, r12d
0x18005634b  mov     edx, [rbp+57h+arg_10]
0x18005634e  mov     rcx, rdi
0x180056351  call    cs:__imp_GetThemeAnimationTransform
0x180056358  nop     dword ptr [rax+rax+00h]
0x18005635d  mov     r14d, eax
0x180056360  test    eax, eax
0x180056362  js      loc_1800564FB
0x180056368  mov     dword ptr [rbp+57h+cb+4], 0
0x18005636f  lea     rax, [rbp+57h+cb+4]
0x180056373  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180056378  xor     r9d, r9d
0x18005637b  xor     r8d, r8d
0x18005637e  mov     edx, [r13+4]
0x180056382  mov     rcx, r15
0x180056385  call    cs:__imp_GetThemeTimingFunction
0x18005638c  nop     dword ptr [rax+rax+00h]
0x180056391  mov     r14d, eax
0x180056394  cmp     eax, 800700EAh
0x180056399  jnz     loc_1800564FB
0x18005639f  mov     ecx, dword ptr [rbp+57h+cb+4]; cb
0x1800563a2  call    cs:__imp_CoTaskMemAlloc
0x1800563a9  nop     dword ptr [rax+rax+00h]
0x1800563ae  mov     r12, rax
0x1800563b1  xor     ecx, ecx; pv
0x1800563b3  call    cs:__imp_CoTaskMemFree
0x1800563ba  nop     dword ptr [rax+rax+00h]
0x1800563bf  mov     rdi, r12
0x1800563c2  test    r12, r12
0x1800563c5  jz      loc_1800565B2
0x1800563cb  lea     rax, [rbp+57h+cb+4]
0x1800563cf  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800563d4  mov     r9d, dword ptr [rbp+57h+cb+4]
0x1800563d8  mov     r8, r12
0x1800563db  mov     edx, [r13+4]
0x1800563df  mov     rcx, r15
0x1800563e2  call    cs:__imp_GetThemeTimingFunction
0x1800563e9  nop     dword ptr [rax+rax+00h]
0x1800563ee  mov     r14d, eax
0x1800563f1  test    eax, eax
0x1800563f3  js      loc_1800564E4
0x1800563f9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180056400  mov     ecx, 18h; unsigned __int64
0x180056405  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005640a  mov     r15, rax
0x18005640d  mov     [rbp+57h+var_58], rax
0x180056411  xor     r14d, r14d
0x180056414  test    rax, rax
0x180056417  jz      loc_180056554
0x18005641d  xorps   xmm0, xmm0
0x180056420  movups  xmmword ptr [rax], xmm0
0x180056423  mov     [rax+8], r14
0x180056427  mov     [rax+10h], r14
0x18005642b  mov     rbx, r15
0x18005642e  test    r15, r15
0x180056431  jz      loc_1800565A7
0x180056437  mov     eax, [rbp+57h+arg_8]
0x18005643a  mov     [r15], eax
0x18005643d  mov     rsi, r14
0x180056440  mov     [rbp+57h+var_58], r14
0x180056444  mov     rcx, [r15+8]; pv
0x180056448  mov     [r15+8], r14
0x18005644c  call    cs:__imp_CoTaskMemFree
0x180056453  nop     dword ptr [rax+rax+00h]
0x180056458  mov     [r15+8], r13
0x18005645c  mov     rdi, r14
0x18005645f  mov     [rbp+57h+var_50], r14
0x180056463  mov     rcx, [r15+10h]; pv
0x180056467  mov     [r15+10h], r14
0x18005646b  call    cs:__imp_CoTaskMemFree
0x180056472  nop     dword ptr [rax+rax+00h]
0x180056477  mov     [r15+10h], r12
0x18005647b  mov     rcx, [rbp+57h+arg_0]
0x18005647f  cmp     [rcx+102h], r14b
0x180056486  jnz     loc_18005655C
0x18005648c  lea     r12, [rcx+0A0h]
0x180056493  mov     rbx, r14
0x180056496  mov     [rbp+57h+var_48], rbx
0x18005649a  mov     rdx, [r12+8]
0x18005649f  cmp     rdx, [r12+18h]
0x1800564a4  jnz     short loc_1800564B8
0x1800564a6  inc     rdx
0x1800564a9  mov     rcx, r12
0x1800564ac  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUAnimationPVLInfo@CSwitchThumbnailDeviceManager@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUAnimationPVLInfo@CSwitchThumbnailDeviceManager@@@@V?$CSimpleArrayStandardCompareHelper@PEAUAnimationPVLInfo@CSwitchThumbnailDeviceManager@@@@V?$CSimpleArrayStandardMergeHelper@PEAUAnimationPVLInfo@CSwitchThumbnailDeviceManager@@@@@@QEAAJ_K0@Z; CTSimpleArray<CSwitchThumbnailDeviceManager::AnimationPVLInfo *,4294967294,CTPolicyCoTaskMem<CSwitchThumbnailDeviceManager::AnimationPVLInfo *>,CSimpleArrayStandardCompareHelper<CSwitchThumbnailDeviceManager::AnimationPVLInfo *>,CSimpleArrayStandardMergeHelper<CSwitchThumbnailDeviceManager::AnimationPVLInfo *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800564b1  mov     r14d, eax
0x1800564b4  test    eax, eax
0x1800564b6  js      short loc_1800564D5
0x1800564b8  inc     qword ptr [r12+8]
0x1800564bd  mov     rdx, [r12+8]
0x1800564c2  mov     rax, [r12]
0x1800564c6  dec     rdx
0x1800564c9  lea     rdx, [rax+rdx*8]
0x1800564cd  test    rdx, rdx
0x1800564d0  jz      short loc_1800564D5
0x1800564d2  mov     [rdx], r15
0x1800564d5  mov     rcx, rbx; void *
0x1800564d8  call    ??$Destroy@UAnimationPVLInfo@CSwitchThumbnailDeviceManager@@@CTContainer_PolicyNewMem@@SAXPEAUAnimationPVLInfo@CSwitchThumbnailDeviceManager@@@Z; CTContainer_PolicyNewMem::Destroy<CSwitchThumbnailDeviceManager::AnimationPVLInfo>(CSwitchThumbnailDeviceManager::AnimationPVLInfo *)
0x1800564dd  mov     ebx, [rbp+57h+var_74]
0x1800564e0  mov     r15, [rbp+57h+var_68]
0x1800564e4  mov     rcx, rdi; pv
0x1800564e7  call    cs:__imp_CoTaskMemFree
0x1800564ee  nop     dword ptr [rax+rax+00h]
0x1800564f3  mov     rdi, [rbp+57h+var_60]
0x1800564f7  mov     r12d, [rbp+57h+arg_18]
0x1800564fb  mov     rcx, rsi; pv
0x1800564fe  call    cs:__imp_CoTaskMemFree
0x180056505  nop     dword ptr [rax+rax+00h]
0x18005650a  mov     esi, [rbp+57h+arg_10]
0x18005650d  xor     r13d, r13d
0x180056510  inc     ebx
0x180056512  mov     [rbp+57h+var_74], ebx
0x180056515  cmp     ebx, [rbp+57h+var_78]
0x180056518  jb      loc_1800562BF
0x18005651e  mov     rcx, r15; hTheme
0x180056521  call    cs:__imp_CloseThemeData
0x180056528  nop     dword ptr [rax+rax+00h]
0x18005652d  mov     rcx, rdi; hTheme
0x180056530  call    cs:__imp_CloseThemeData
0x180056537  nop     dword ptr [rax+rax+00h]
0x18005653c  mov     eax, r14d
0x18005653f  add     rsp, 88h
0x180056546  pop     r15
0x180056548  pop     r14
0x18005654a  pop     r13
0x18005654c  pop     r12
0x18005654e  pop     rdi
0x18005654f  pop     rsi
0x180056550  pop     rbx
0x180056551  pop     rbp
0x180056552  retn
0x180056554  mov     r15, r14
0x180056557  jmp     loc_18005642B
0x18005655c  mov     rax, [r15+8]
0x180056560  cmp     dword ptr [rax], 104h
0x180056566  jnz     loc_18005648C
0x18005656c  movss   xmm0, dword ptr [rax+24h]
0x180056571  mulss   xmm0, cs:__real@bf800000
0x180056579  movss   dword ptr [rax+24h], xmm0
0x18005657e  movss   xmm1, cs:__real@3f800000
0x180056586  subss   xmm1, dword ptr [rax+2Ch]
0x18005658b  movss   dword ptr [rax+2Ch], xmm1
0x180056590  movss   xmm0, dword ptr [rax+18h]
0x180056595  mulss   xmm0, cs:__real@bf800000
0x18005659d  movss   dword ptr [rax+18h], xmm0
0x1800565a2  jmp     loc_18005648C
0x1800565a7  mov     r14d, 8007000Eh
0x1800565ad  jmp     loc_1800564D5
0x1800565b2  mov     r14d, 8007000Eh
0x1800565b8  jmp     loc_1800564E4
0x1800565bd  mov     r14d, 8007000Eh
0x1800565c3  jmp     loc_1800564FB
```
