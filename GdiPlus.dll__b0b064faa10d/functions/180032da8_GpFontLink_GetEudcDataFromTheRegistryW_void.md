# GpFontLink::GetEudcDataFromTheRegistryW(void)

- ea: `0x180032da8`
- end: `0x1800330e5`
- name: `?GetEudcDataFromTheRegistryW@GpFontLink@@AEAAXXZ`
- size: `829`
- prototype: `void __fastcall(GpFontLink *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1800ed284`

## callees

- `0x1800067bc`
- `0x180032c50`
- `0x180032d40`
- `0x180032da8`
- `0x180034e70`
- `0x180037420`
- `0x1800fe680`
- `0x1800fea70`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032ed0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032f5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032ed0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032f5d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032de5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032de5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032ee2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032ee2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f6f`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180032e30`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180032e30`

## string_xrefs

- `0x180032ec9`: `RegOpenKeyExW`

## pseudocode

```c
void __fastcall GpFontLink::GetEudcDataFromTheRegistryW(GpFontLink *this)
{
  _QWORD *v2; // rax
  int v3; // edi
  __int64 v4; // rcx
  int v5; // ebx
  UINT ACP; // r9d
  __int64 v7; // rax
  __int64 v8; // rcx
  FARPROC ProcAddress; // rax
  unsigned int v10; // ebx
  int RegistryDll; // eax
  int v12; // r12d
  FARPROC v13; // rax
  __int64 v14; // r14
  int v15; // edi
  DWORD LastError; // eax
  const wchar_t *v17; // r8
  unsigned __int16 *i; // r9
  unsigned __int16 v19; // dx
  wchar_t v20; // cx
  struct GpFontFamily *v21; // rax
  struct GpFontFamily *Family; // r15
  struct GpFontFamily *v23; // r14
  struct GpFontFamily **v24; // rax
  struct GpFontFamily **v25; // rcx
  __int64 v26; // rax
  struct GpFontFamily *v27; // rdx
  int v28; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+54h] [rbp-ACh] BYREF
  _QWORD v30[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v31[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v32[264]; // [rsp+280h] [rbp+180h] BYREF

  v2 = HeapAlloc(GpRuntime::GpMemHeap, 0, 0x10u);
  *((_QWORD *)this + 1) = v2;
  if ( !v2 )
    return;
  *v2 = 0;
  v3 = 0;
  *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) = 0;
  do
  {
    v4 = v3++;
    v31[v4] = aEudc[v4];
  }
  while ( aEudc[v3] );
  v5 = 0;
  ACP = GetACP();
  do
  {
    if ( !ACP )
      break;
    v7 = (unsigned int)v5++;
    *((_WORD *)&v30[1] + v7) = ACP % 0xA + 48;
    ACP /= 0xAu;
  }
  while ( v5 < 5 );
  while ( --v5 >= 0 )
  {
    v8 = v3++;
    v31[v8] = *((_WORD *)&v30[1] + (unsigned int)v5);
  }
  if ( (unsigned __int64)(2LL * v3) >= 0x208 )
    _report_rangecheckfailure();
  ProcAddress = (FARPROC)qword_1801A56C8;
  v10 = 0;
  v31[v3] = 0;
  v30[0] = 0;
  if ( ProcAddress )
    goto LABEL_15;
  RegistryDll = DLpLoadRegistryDll();
  if ( !RegistryDll )
  {
    ProcAddress = GetProcAddress(g_hInstRegistryDLL, "RegOpenKeyExW");
    qword_1801A56C8 = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      RegistryDll = GetLastError();
      goto LABEL_16;
    }
LABEL_15:
    RegistryDll = ((__int64 (__fastcall *)(__int64, unsigned __int16 *, _QWORD, __int64, _QWORD *))ProcAddress)(
                    -2147483647,
                    v31,
                    0,
                    9,
                    v30);
  }
LABEL_16:
  v29 = 0;
  v12 = 1;
  v28 = 0;
  if ( !RegistryDll )
  {
    while ( 1 )
    {
      v13 = (FARPROC)qword_1801A56E0;
      v14 = v30[0];
      v29 = 260;
      v28 = 260;
      if ( qword_1801A56E0 )
        goto LABEL_21;
      v15 = DLpLoadRegistryDll();
      if ( v15 )
        goto LABEL_23;
      v13 = GetProcAddress(g_hInstRegistryDLL, "RegEnumValueW");
      qword_1801A56E0 = (__int64)v13;
      if ( v13 )
LABEL_21:
        LastError = ((__int64 (__fastcall *)(__int64, _QWORD, unsigned __int16 *, int *, _QWORD, _QWORD, unsigned __int16 *, int *))v13)(
                      v14,
                      v10,
                      v32,
                      &v29,
                      0,
                      0,
                      v31,
                      &v28);
      else
        LastError = GetLastError();
      v15 = LastError;
LABEL_23:
      if ( v15 )
        goto LABEL_45;
      if ( !v12 )
        goto LABEL_38;
      v17 = L"SystemDefaultEUDCFont";
      for ( i = v32; ; ++i )
      {
        v19 = *i;
        v20 = *v17;
        if ( !*i )
          break;
        if ( !v20 )
          goto LABEL_38;
        if ( (unsigned __int16)(v19 - 97) <= 0x19u )
          v19 -= 32;
        if ( (unsigned __int16)(v20 - 97) <= 0x19u )
          v20 -= 32;
        if ( v19 < v20 || v19 > v20 )
          goto LABEL_38;
        ++v17;
      }
      if ( v20 )
      {
LABEL_38:
        Family = GpFontFamilyList::GetFamily(
                   *(GpFontFamilyList **)(*((_QWORD *)Globals::FontCollection + 2) + 8LL),
                   v32);
        if ( Family )
        {
          v23 = GpFontLink::CheckAndLoadTheFile(this, v31);
          if ( v23 )
          {
            v24 = (struct GpFontFamily **)GpMallocEx(24, 0);
            v25 = v24;
            if ( v24 )
            {
              *v24 = Family;
              v24[1] = v23;
              v26 = *((_QWORD *)this + 1);
              v27 = *(struct GpFontFamily **)(v26 + 8);
              if ( v27 )
              {
                v25[2] = v27;
                *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) = v25;
              }
              else
              {
                *(_QWORD *)(v26 + 8) = v25;
                v25[2] = 0;
              }
              goto LABEL_43;
            }
          }
        }
LABEL_45:
        ++v10;
        if ( v15 )
          break;
      }
      else
      {
        v12 = 0;
        v21 = GpFontLink::CheckAndLoadTheFile(this, v31);
        if ( v21 )
          **((_QWORD **)this + 1) = v21;
LABEL_43:
        ++v10;
      }
    }
  }
  if ( v30[0] )
    DLRegCloseKey(v30[0]);
}

```

## disassembly

```asm
0x180032da8  push    rbp
0x180032daa  push    rbx
0x180032dab  push    rsi
0x180032dac  push    rdi
0x180032dad  push    r12
0x180032daf  push    r13
0x180032db1  push    r14
0x180032db3  push    r15
0x180032db5  lea     rbp, [rsp-3A8h]
0x180032dbd  sub     rsp, 4A8h
0x180032dc4  mov     rax, cs:__security_cookie
0x180032dcb  xor     rax, rsp
0x180032dce  mov     [rbp+3E0h+var_50], rax
0x180032dd5  xor     edx, edx; dwFlags
0x180032dd7  mov     rsi, rcx
0x180032dda  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180032de1  lea     r8d, [rdx+10h]; dwBytes
0x180032de5  call    cs:__imp_HeapAlloc
0x180032deb  xor     r13d, r13d
0x180032dee  mov     [rsi+8], rax
0x180032df2  test    rax, rax
0x180032df5  jz      loc_1800330BC
0x180032dfb  mov     [rax], r13
0x180032dfe  lea     rdx, aEudc; "EUDC\\"
0x180032e05  mov     rax, [rsi+8]
0x180032e09  lea     r14d, [r13+1]
0x180032e0d  mov     edi, r13d
0x180032e10  mov     [rax+8], r13
0x180032e14  movsxd  rcx, edi
0x180032e17  add     edi, r14d
0x180032e1a  movzx   eax, word ptr [rdx+rcx*2]
0x180032e1e  mov     [rsp+rcx*2+4E0h+var_470], ax
0x180032e23  movsxd  rax, edi
0x180032e26  cmp     [rdx+rax*2], r13w
0x180032e2b  jnz     short loc_180032E14
0x180032e2d  mov     ebx, r13d
0x180032e30  call    cs:__imp_GetACP
0x180032e36  mov     r9d, eax
0x180032e39  test    r9d, r9d
0x180032e3c  jz      short loc_180032E86
0x180032e3e  mov     eax, 0CCCCCCCDh
0x180032e43  mul     r9d
0x180032e46  mov     eax, ebx
0x180032e48  add     ebx, r14d
0x180032e4b  shr     edx, 3
0x180032e4e  movzx   ecx, dx
0x180032e51  shl     cx, 2
0x180032e55  lea     r8d, [rcx+rdx]
0x180032e59  add     r8w, r8w
0x180032e5d  sub     r9w, r8w
0x180032e61  add     r9w, 30h ; '0'
0x180032e66  mov     [rsp+rax*2+4E0h+var_480], r9w
0x180032e6c  mov     r9d, edx
0x180032e6f  cmp     ebx, 5
0x180032e72  jl      short loc_180032E39
0x180032e74  jmp     short loc_180032E86
0x180032e76  movzx   eax, [rsp+rbx*2+4E0h+var_480]
0x180032e7b  movsxd  rcx, edi
0x180032e7e  add     edi, r14d
0x180032e81  mov     [rsp+rcx*2+4E0h+var_470], ax
0x180032e86  sub     ebx, r14d
0x180032e89  jns     short loc_180032E76
0x180032e8b  movsxd  rax, edi
0x180032e8e  lea     rcx, [rax+rax]
0x180032e92  cmp     rcx, 208h
0x180032e99  jnb     loc_1800330DF
0x180032e9f  mov     rax, cs:qword_1801A56C8
0x180032ea6  mov     ebx, r13d
0x180032ea9  mov     [rsp+rcx+4E0h+var_470], r13w
0x180032eaf  mov     [rsp+4E0h+var_488], r13
0x180032eb4  test    rax, rax
0x180032eb7  jnz     short loc_180032EEA
0x180032eb9  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x180032ebe  test    eax, eax
0x180032ec0  jnz     short loc_180032F0E
0x180032ec2  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180032ec9  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180032ed0  call    cs:__imp_GetProcAddress
0x180032ed6  mov     cs:qword_1801A56C8, rax
0x180032edd  test    rax, rax
0x180032ee0  jnz     short loc_180032EEA
0x180032ee2  call    cs:__imp_GetLastError
0x180032ee8  jmp     short loc_180032F0E
0x180032eea  lea     rcx, [rsp+4E0h+var_488]
0x180032eef  mov     r9d, 9
0x180032ef5  mov     [rsp+4E0h+var_4C0], rcx
0x180032efa  lea     rdx, [rsp+4E0h+var_470]
0x180032eff  mov     rcx, 0FFFFFFFF80000001h
0x180032f06  xor     r8d, r8d
0x180032f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f0e  mov     [rsp+4E0h+var_48C], r13d
0x180032f13  mov     r12d, r14d
0x180032f16  mov     [rsp+4E0h+var_490], r13d
0x180032f1b  test    eax, eax
0x180032f1d  jnz     loc_1800330AD
0x180032f23  mov     rax, cs:qword_1801A56E0
0x180032f2a  mov     r14, [rsp+4E0h+var_488]
0x180032f2f  mov     [rsp+4E0h+var_48C], 104h
0x180032f37  mov     [rsp+4E0h+var_490], 104h
0x180032f3f  test    rax, rax
0x180032f42  jnz     short loc_180032F77
0x180032f44  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x180032f49  mov     edi, eax
0x180032f4b  test    eax, eax
0x180032f4d  jnz     short loc_180032FAD
0x180032f4f  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180032f56  lea     rdx, aRegenumvaluew; "RegEnumValueW"
0x180032f5d  call    cs:__imp_GetProcAddress
0x180032f63  mov     cs:qword_1801A56E0, rax
0x180032f6a  test    rax, rax
0x180032f6d  jnz     short loc_180032F77
0x180032f6f  call    cs:__imp_GetLastError
0x180032f75  jmp     short loc_180032FAB
0x180032f77  lea     rcx, [rsp+4E0h+var_490]
0x180032f7c  mov     edx, ebx
0x180032f7e  mov     [rsp+4E0h+var_4A8], rcx
0x180032f83  lea     r9, [rsp+4E0h+var_48C]
0x180032f88  lea     rcx, [rsp+4E0h+var_470]
0x180032f8d  mov     [rsp+4E0h+var_4B0], rcx
0x180032f92  lea     r8, [rbp+3E0h+var_260]
0x180032f99  mov     [rsp+4E0h+var_4B8], r13
0x180032f9e  mov     rcx, r14
0x180032fa1  mov     [rsp+4E0h+var_4C0], r13
0x180032fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032fab  mov     edi, eax
0x180032fad  test    edi, edi
0x180032faf  jnz     loc_1800330A3
0x180032fb5  test    r12d, r12d
0x180032fb8  jz      short loc_180033028
0x180032fba  lea     r8, aSystemdefaulte; "SystemDefaultEUDCFont"
0x180032fc1  lea     r9, [rbp+3E0h+var_260]
0x180032fc8  movzx   edx, word ptr [r9]
0x180032fcc  movzx   ecx, word ptr [r8]
0x180032fd0  test    dx, dx
0x180032fd3  jz      short loc_180033005
0x180032fd5  test    cx, cx
0x180032fd8  jz      short loc_180033028
0x180032fda  lea     eax, [rdx-61h]
0x180032fdd  cmp     ax, 19h
0x180032fe1  ja      short loc_180032FE7
0x180032fe3  sub     dx, 20h ; ' '
0x180032fe7  lea     eax, [rcx-61h]
0x180032fea  cmp     ax, 19h
0x180032fee  ja      short loc_180032FF4
0x180032ff0  sub     cx, 20h ; ' '
0x180032ff4  cmp     dx, cx
0x180032ff7  jb      short loc_180033028
0x180032ff9  ja      short loc_180033028
0x180032ffb  add     r9, 2
0x180032fff  add     r8, 2
0x180033003  jmp     short loc_180032FC8
0x180033005  test    cx, cx
0x180033008  jnz     short loc_180033028
0x18003300a  lea     rdx, [rsp+4E0h+var_470]; unsigned __int16 *
0x18003300f  mov     rcx, rsi; this
0x180033012  mov     r12d, r13d
0x180033015  call    ?CheckAndLoadTheFile@GpFontLink@@AEAAPEAVGpFontFamily@@PEBG@Z; GpFontLink::CheckAndLoadTheFile(ushort const *)
0x18003301a  test    rax, rax
0x18003301d  jz      short loc_18003308E
0x18003301f  mov     rcx, [rsi+8]
0x180033023  mov     [rcx], rax
0x180033026  jmp     short loc_18003308E
0x180033028  mov     rax, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x18003302f  lea     rdx, [rbp+3E0h+var_260]; unsigned __int16 *
0x180033036  mov     rcx, [rax+10h]
0x18003303a  mov     rcx, [rcx+8]; this
0x18003303e  call    ?GetFamily@GpFontFamilyList@@QEBAPEAVGpFontFamily@@PEBG@Z; GpFontFamilyList::GetFamily(ushort const *)
0x180033043  mov     r15, rax
0x180033046  test    rax, rax
0x180033049  jz      short loc_1800330A3
0x18003304b  lea     rdx, [rsp+4E0h+var_470]; unsigned __int16 *
0x180033050  mov     rcx, rsi; this
0x180033053  call    ?CheckAndLoadTheFile@GpFontLink@@AEAAPEAVGpFontFamily@@PEBG@Z; GpFontLink::CheckAndLoadTheFile(ushort const *)
0x180033058  mov     r14, rax
0x18003305b  test    rax, rax
0x18003305e  jz      short loc_1800330A3
0x180033060  xor     edx, edx
0x180033062  lea     ecx, [rdx+18h]
0x180033065  call    GpMallocEx
0x18003306a  mov     rcx, rax
0x18003306d  test    rax, rax
0x180033070  jz      short loc_1800330A3
0x180033072  mov     [rax], r15
0x180033075  mov     [rax+8], r14
0x180033079  mov     rax, [rsi+8]
0x18003307d  mov     rdx, [rax+8]
0x180033081  test    rdx, rdx
0x180033084  jnz     short loc_180033095
0x180033086  mov     [rax+8], rcx
0x18003308a  mov     [rcx+10h], r13
0x18003308e  inc     ebx
0x180033090  jmp     loc_180032F23
0x180033095  mov     [rcx+10h], rdx
0x180033099  mov     rax, [rsi+8]
0x18003309d  mov     [rax+8], rcx
0x1800330a1  jmp     short loc_18003308E
0x1800330a3  inc     ebx
0x1800330a5  test    edi, edi
0x1800330a7  jz      loc_180032F23
0x1800330ad  mov     rcx, [rsp+4E0h+var_488]
0x1800330b2  test    rcx, rcx
0x1800330b5  jz      short loc_1800330BC
0x1800330b7  call    DLRegCloseKey
0x1800330bc  mov     rcx, [rbp+3E0h+var_50]
0x1800330c3  xor     rcx, rsp; StackCookie
0x1800330c6  call    __security_check_cookie
0x1800330cb  add     rsp, 4A8h
0x1800330d2  pop     r15
0x1800330d4  pop     r14
0x1800330d6  pop     r13
0x1800330d8  pop     r12
0x1800330da  pop     rdi
0x1800330db  pop     rsi
0x1800330dc  pop     rbx
0x1800330dd  pop     rbp
0x1800330de  retn
0x1800330df  call    __report_rangecheckfailure
```
