# GpFontLink::CacheFontSubstitutionDataW(void)

- ea: `0x180036308`
- end: `0x1800365a8`
- name: `?CacheFontSubstitutionDataW@GpFontLink@@AEAAXXZ`
- size: `672`
- prototype: `void __fastcall(GpFontLink *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ed284`

## callees

- `0x180032af0`
- `0x180032c50`
- `0x180032d40`
- `0x180036308`
- `0x180037420`
- `0x1800ec8e8`
- `0x1800fe680`
- `0x1800fea70`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003651f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003654b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003651f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003654b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003655d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003655d`

## string_xrefs

- `0x180036544`: `RegOpenKeyExW`

## pseudocode

```c
void __fastcall GpFontLink::CacheFontSubstitutionDataW(GpFontLink *this)
{
  FARPROC ProcAddress; // rax
  unsigned int i; // edi
  struct GpFontFamily *Family; // rax
  __int64 v5; // r8
  __int16 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rax
  FARPROC v9; // rax
  __int64 v10; // rsi
  DWORD v11; // eax
  int v12; // ecx
  DWORD LastError; // eax
  int v14; // edx
  int v15; // r8d
  int v16; // r9d
  __int64 *v17; // [rsp+20h] [rbp-E0h]
  unsigned int v18; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v20; // [rsp+70h] [rbp-90h]
  int v21[3]; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned __int16 v22[264]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v23[264]; // [rsp+290h] [rbp+190h] BYREF

  ProcAddress = (FARPROC)qword_1801A56C8;
  v19 = 0;
  if ( qword_1801A56C8 )
    goto LABEL_28;
  if ( (unsigned int)DLpLoadRegistryDll() )
    return;
  ProcAddress = GetProcAddress(g_hInstRegistryDLL, "RegOpenKeyExW");
  qword_1801A56C8 = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_28:
    v17 = &v19;
    LastError = ((__int64 (__fastcall *)(__int64, const wchar_t *, _QWORD, __int64))ProcAddress)(
                  -2147483646,
                  L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\FontSubstitutes",
                  0,
                  9);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( !LastError )
  {
    v20 = 0;
    if ( !(unsigned int)DLRegQueryInfoKeyW(v19, v14, v15, v16, (_DWORD)v17) )
    {
      if ( v20 )
      {
        v8 = GpMallocItems<FontSubstitutionEntry>(v20);
        *((_QWORD *)this + 3) = v8;
        if ( v8 )
        {
          for ( i = 0; ; ++i )
          {
            v9 = (FARPROC)qword_1801A56E0;
            v10 = v19;
            v18 = 260;
            v21[0] = 260;
            if ( qword_1801A56E0 )
              goto LABEL_17;
            if ( (unsigned int)DLpLoadRegistryDll() )
              break;
            v9 = GetProcAddress(g_hInstRegistryDLL, "RegEnumValueW");
            qword_1801A56E0 = (__int64)v9;
            if ( v9 )
LABEL_17:
              v11 = ((__int64 (__fastcall *)(__int64, _QWORD, _WORD *, unsigned int *, _QWORD, _QWORD, unsigned __int16 *, int *))v9)(
                      v10,
                      i,
                      v23,
                      &v18,
                      0,
                      0,
                      v22,
                      v21);
            else
              v11 = GetLastError();
            if ( v11 )
              break;
            v12 = v21[0];
            while ( --v12 >= 0 )
            {
              if ( v22[v12] == 44 )
              {
                if ( (unsigned __int64)(2LL * v12) >= 0x208 )
                  _report_rangecheckfailure();
                v22[v12] = 0;
                break;
              }
            }
            Family = GpFontFamilyList::GetFamily(
                       *(GpFontFamilyList **)(*((_QWORD *)Globals::FontCollection + 2) + 8LL),
                       v22);
            if ( Family )
            {
              v5 = 0;
              for ( *(_QWORD *)(536LL * *((int *)this + 8) + *((_QWORD *)this + 3) + 528) = Family;
                    (unsigned int)v5 < v18;
                    *(_WORD *)(*((_QWORD *)this + 3) + 2 * (v7 + 268LL * *((int *)this + 8))) = v6 )
              {
                v6 = v23[v5];
                v7 = (unsigned int)v5;
                if ( v6 == 44 )
                  break;
                v5 = (unsigned int)(v5 + 1);
              }
              *(_WORD *)(*((_QWORD *)this + 3) + 2 * ((unsigned int)v5 + 268LL * *((int *)this + 8))) = 0;
              *(_DWORD *)(536LL * (int)(*((_DWORD *)this + 8))++ + *((_QWORD *)this + 3) + 520) = v5;
            }
          }
        }
      }
    }
    DLRegCloseKey(v19);
  }
}

```

## disassembly

```asm
0x180036308  push    rbp
0x18003630a  push    rbx
0x18003630b  push    rsi
0x18003630c  push    rdi
0x18003630d  lea     rbp, [rsp-3B8h]
0x180036315  sub     rsp, 4B8h
0x18003631c  mov     rax, cs:__security_cookie
0x180036323  xor     rax, rsp
0x180036326  mov     [rbp+3D0h+var_30], rax
0x18003632d  mov     rax, cs:qword_1801A56C8
0x180036334  mov     rbx, rcx
0x180036337  mov     [rsp+4D0h+var_468], 0
0x180036340  test    rax, rax
0x180036343  jnz     loc_180036568
0x180036349  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18003634e  test    eax, eax
0x180036350  jz      loc_18003653D
0x180036356  mov     rcx, [rbp+3D0h+var_30]
0x18003635d  xor     rcx, rsp; StackCookie
0x180036360  call    __security_check_cookie
0x180036365  add     rsp, 4B8h
0x18003636c  pop     rdi
0x18003636d  pop     rsi
0x18003636e  pop     rbx
0x18003636f  pop     rbp
0x180036370  retn
0x180036371  cmp     rdx, 208h
0x180036378  jnb     loc_180036593
0x18003637e  xor     eax, eax
0x180036380  mov     [rbp+rdx+3D0h+var_450], ax
0x180036385  mov     rax, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x18003638c  lea     rdx, [rbp+3D0h+var_450]; unsigned __int16 *
0x180036390  inc     edi
0x180036392  mov     rcx, [rax+10h]
0x180036396  mov     rcx, [rcx+8]; this
0x18003639a  call    ?GetFamily@GpFontFamilyList@@QEBAPEAVGpFontFamily@@PEBG@Z; GpFontFamilyList::GetFamily(ushort const *)
0x18003639f  test    rax, rax
0x1800363a2  jz      loc_18003647E
0x1800363a8  movsxd  rcx, dword ptr [rbx+20h]
0x1800363ac  xor     r8d, r8d
0x1800363af  imul    rdx, rcx, 218h
0x1800363b6  mov     rcx, [rbx+18h]
0x1800363ba  mov     [rdx+rcx+210h], rax
0x1800363c2  cmp     [rsp+4D0h+var_470], r8d
0x1800363c7  jbe     short loc_1800363FD
0x1800363c9  movzx   r9d, [rbp+r8*2+3D0h+var_240]
0x1800363d2  mov     edx, r8d
0x1800363d5  cmp     r9w, 2Ch ; ','
0x1800363da  jz      short loc_1800363FD
0x1800363dc  movsxd  rax, dword ptr [rbx+20h]
0x1800363e0  inc     r8d
0x1800363e3  imul    rcx, rax, 10Ch
0x1800363ea  mov     rax, [rbx+18h]
0x1800363ee  add     rcx, rdx
0x1800363f1  mov     [rax+rcx*2], r9w
0x1800363f6  cmp     r8d, [rsp+4D0h+var_470]
0x1800363fb  jb      short loc_1800363C9
0x1800363fd  movsxd  rax, dword ptr [rbx+20h]
0x180036401  mov     rcx, [rbx+18h]
0x180036405  imul    rdx, rax, 10Ch
0x18003640c  mov     eax, r8d
0x18003640f  add     rdx, rax
0x180036412  xor     eax, eax
0x180036414  mov     [rcx+rdx*2], ax
0x180036418  movsxd  rax, dword ptr [rbx+20h]
0x18003641c  imul    rcx, rax, 218h
0x180036423  mov     rax, [rbx+18h]
0x180036427  mov     [rcx+rax+208h], r8d
0x18003642f  inc     dword ptr [rbx+20h]
0x180036432  jmp     short loc_18003647E
0x180036434  test    eax, eax
0x180036436  jnz     loc_180036356
0x18003643c  mov     rcx, [rsp+4D0h+var_468]
0x180036441  mov     [rsp+4D0h+var_460], eax
0x180036445  lea     rax, [rsp+4D0h+var_460]
0x18003644a  mov     [rsp+4D0h+var_498], rax
0x18003644f  call    DLRegQueryInfoKeyW
0x180036454  test    eax, eax
0x180036456  jnz     loc_180036599
0x18003645c  mov     eax, [rsp+4D0h+var_460]
0x180036460  test    eax, eax
0x180036462  jz      loc_180036599
0x180036468  mov     ecx, eax
0x18003646a  call    ??$GpMallocItems@UFontSubstitutionEntry@@@@YAPEAUFontSubstitutionEntry@@_K@Z; GpMallocItems<FontSubstitutionEntry>(unsigned __int64)
0x18003646f  mov     [rbx+18h], rax
0x180036473  test    rax, rax
0x180036476  jz      loc_180036599
0x18003647c  xor     edi, edi
0x18003647e  mov     rax, cs:qword_1801A56E0
0x180036485  mov     rsi, [rsp+4D0h+var_468]
0x18003648a  mov     [rsp+4D0h+var_470], 104h
0x180036492  mov     [rsp+4D0h+var_45C], 104h
0x18003649a  test    rax, rax
0x18003649d  jz      short loc_180036504
0x18003649f  lea     rcx, [rsp+4D0h+var_45C]
0x1800364a4  mov     edx, edi
0x1800364a6  mov     [rsp+4D0h+var_498], rcx
0x1800364ab  lea     r9, [rsp+4D0h+var_470]
0x1800364b0  lea     rcx, [rbp+3D0h+var_450]
0x1800364b4  mov     [rsp+4D0h+var_4A0], rcx
0x1800364b9  lea     r8, [rbp+3D0h+var_240]
0x1800364c0  mov     [rsp+4D0h+var_4A8], 0
0x1800364c9  mov     rcx, rsi
0x1800364cc  mov     [rsp+4D0h+var_4B0], 0
0x1800364d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364da  test    eax, eax
0x1800364dc  jnz     loc_180036599
0x1800364e2  mov     ecx, [rsp+4D0h+var_45C]
0x1800364e6  dec     ecx
0x1800364e8  test    ecx, ecx
0x1800364ea  js      loc_180036385
0x1800364f0  movsxd  rax, ecx
0x1800364f3  lea     rdx, [rax+rax]
0x1800364f7  cmp     [rbp+rdx+3D0h+var_450], 2Ch ; ','
0x1800364fd  jnz     short loc_1800364E6
0x1800364ff  jmp     loc_180036371
0x180036504  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x180036509  test    eax, eax
0x18003650b  jnz     loc_180036599
0x180036511  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180036518  lea     rdx, aRegenumvaluew; "RegEnumValueW"
0x18003651f  call    cs:__imp_GetProcAddress
0x180036525  mov     cs:qword_1801A56E0, rax
0x18003652c  test    rax, rax
0x18003652f  jnz     loc_18003649F
0x180036535  call    cs:__imp_GetLastError
0x18003653b  jmp     short loc_1800364DA
0x18003653d  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180036544  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18003654b  call    cs:__imp_GetProcAddress
0x180036551  mov     cs:qword_1801A56C8, rax
0x180036558  test    rax, rax
0x18003655b  jnz     short loc_180036568
0x18003655d  call    cs:__imp_GetLastError
0x180036563  jmp     loc_180036434
0x180036568  lea     rcx, [rsp+4D0h+var_468]
0x18003656d  mov     r9d, 9
0x180036573  mov     [rsp+4D0h+var_4B0], rcx
0x180036578  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003657f  mov     rcx, 0FFFFFFFF80000002h
0x180036586  xor     r8d, r8d
0x180036589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003658e  jmp     loc_180036434
0x180036593  call    __report_rangecheckfailure
0x180036599  mov     rcx, [rsp+4D0h+var_468]
0x18003659e  call    DLRegCloseKey
0x1800365a3  jmp     loc_180036356
```
