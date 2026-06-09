# FrameWindow::OnMarkToolReady(uint,unsigned __int64,__int64,int &)

- ea: `0x1800241cc`
- end: `0x180024710`
- name: `?OnMarkToolReady@FrameWindow@@QEAA_JI_K_JAEAH@Z`
- size: `1348`
- prototype: `__int64 __fastcall(FrameWindow *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x18002b910`

## callees

- `0x180003858`
- `0x180003880`
- `0x1800045b4`
- `0x180020528`
- `0x180022f44`
- `0x180022fb4`
- `0x1800241cc`
- `0x180026d04`
- `0x1800299c8`
- `0x180029a34`
- `0x18002edec`
- `0x18002fba8`
- `0x180031ec0`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800245a3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800245b7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800245a3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800245b7`
- `OLEAUT32!__imp_SysAllocString` at `0x180024432`
- `OLEAUT32!__imp_SysAllocString` at `0x180024432`
- `OLEAUT32!__imp_SysFreeString` at `0x1800243c5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800243c5`
- `SHLWAPI!PathFindFileNameW` at `0x18002469e`
- `SHLWAPI!PathFindFileNameW` at `0x18002469e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall FrameWindow::OnMarkToolReady(FrameWindow *this, __int64 a2, unsigned int a3, const WCHAR *a4)
{
  int v5; // r11d
  int v6; // r11d
  int v7; // r11d
  int v8; // r11d
  int v9; // r11d
  int v10; // r11d
  int v11; // r11d
  int v12; // r11d
  __int16 v13; // di
  __int64 v14; // rdx
  unsigned int v15; // ebx
  OLECHAR *v16; // rdi
  WCHAR *v17; // rbx
  _QWORD *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // rdx
  OLECHAR *v23; // rdx
  char v25; // r9
  __int64 *v26; // rax
  int F12RegEntry; // eax
  __int64 v28; // rbx
  LPCWSTR v29; // rdx
  LPCWSTR v30; // rdx
  int ModuleFileNameW; // ebx
  LPWSTR FileNameW; // rax
  __int64 v33; // r8
  LPCWSTR v34; // rdx
  _BYTE v35[8]; // [rsp+20h] [rbp-20h] BYREF
  OLECHAR *psz; // [rsp+28h] [rbp-18h]
  __int64 v37; // [rsp+30h] [rbp-10h]
  unsigned int v38; // [rsp+88h] [rbp+48h] BYREF
  __int64 v39; // [rsp+90h] [rbp+50h] BYREF
  LPCWSTR pszPath; // [rsp+98h] [rbp+58h] BYREF

  pszPath = a4;
  v38 = a3;
  if ( (unsigned __int8)FrameWindow::IsPluginReady(this, a3) )
    return 0;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            v10 = v9 - 1;
            if ( v10 )
            {
              v11 = v10 - 1;
              if ( v11 )
              {
                v12 = v11 - 2;
                if ( v12 )
                {
                  if ( v12 != 1 )
                    goto LABEL_24;
                  v13 = 928;
                  v14 = 908;
                  v15 = 928;
                }
                else
                {
                  v15 = 940;
                  v13 = 940;
                  v14 = 926;
                }
              }
              else
              {
                v15 = 944;
                v13 = 944;
                v14 = 924;
              }
            }
            else
            {
              v15 = 942;
              v13 = 942;
              v14 = 922;
            }
          }
          else
          {
            v15 = 938;
            v13 = 938;
            v14 = 918;
          }
        }
        else
        {
          v15 = 936;
          v13 = 936;
          v14 = 916;
        }
      }
      else
      {
        v15 = 934;
        v13 = 934;
        v14 = 914;
      }
    }
    else
    {
      v15 = 932;
      v13 = 932;
      v14 = 912;
    }
  }
  else
  {
    v13 = 0;
    v14 = 906;
    v15 = 0;
  }
  (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 71) + 48LL))(*((_QWORD *)this + 71), v14, 0);
  if ( v13
    && (unsigned __int8)FrameWindow::WasShowToolStartFired(this, v38)
    && !(unsigned __int8)FrameWindow::WasShowToolStopFired(this) )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 71) + 48LL))(*((_QWORD *)this + 71), v15, 0);
    *(_BYTE *)(*(_QWORD *)std::map<enum PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](
                            (__int64 *)this + 56,
                            (int *)&v38)
             + 27LL) = 1;
  }
LABEL_24:
  if ( !*((_BYTE *)this + 437) && v38 == *((_DWORD *)this + 136) )
  {
    psz = (OLECHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    v37 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( (unsigned int)F12::GetScriptToolInitializeInfo(v38, v35) )
    {
      v22 = (_QWORD *)(v37 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v37 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v22 + 8LL))(*v22);
      v23 = psz - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)psz - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 8LL))(*(_QWORD *)v23);
      return -1;
    }
    v16 = psz;
    if ( psz )
    {
      v17 = SysAllocString(psz);
      pszPath = v17;
      if ( !v17 )
        ATL::AtlThrowImpl(-2147024882);
    }
    else
    {
      v17 = 0;
      pszPath = 0;
    }
    (*(void (__fastcall **)(_QWORD, __int64, WCHAR *))(**((_QWORD **)this + 71) + 48LL))(
      *((_QWORD *)this + 71),
      904,
      v17);
    *((_BYTE *)this + 437) = 1;
    SysFreeString(v17);
    v18 = (_QWORD *)(v37 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v37 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
    if ( _InterlockedDecrement((volatile signed __int32 *)v16 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v16 - 3) + 8LL))(*((_QWORD *)v16 - 3));
  }
  v19 = *((_QWORD *)this + 56);
  v20 = *(_QWORD *)(v19 + 8);
  HIDWORD(psz) = 0;
  v21 = v19;
  while ( !*(_BYTE *)(v20 + 25) )
  {
    if ( *(_DWORD *)(v20 + 32) >= (signed int)v38 )
    {
      v25 = 0;
      v21 = v20;
    }
    else
    {
      v25 = 1;
    }
    v26 = (__int64 *)(v20 + 16);
    if ( !v25 )
      v26 = (__int64 *)v20;
    v20 = *v26;
  }
  if ( !*(_BYTE *)(v21 + 25) && (signed int)v38 >= *(_DWORD *)(v21 + 32) && v21 != v19 )
    *(_BYTE *)(*(_QWORD *)std::map<enum PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](
                            (__int64 *)this + 56,
                            (int *)&v38)
             + 25LL) = 1;
  if ( (unsigned __int8)FrameWindow::IsPluginLoaded(this, v38) )
    *(_BYTE *)(*(_QWORD *)std::map<enum PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](
                            (__int64 *)this + 56,
                            (int *)&v38)
             + 24LL) = 1;
  if ( v38 == *((_DWORD *)this + 136) )
  {
    pszPath = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (wchar_t **)&pszPath,
            (__int64)L"DisablePreload") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&pszPath, L"DisablePreload", 14);
    v39 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    F12RegEntry = F12::GetF12RegEntry(&pszPath, &v39);
    v28 = v39;
    if ( !F12RegEntry && (!(unsigned int)_o__wcsicmp(v39, L"true") || !(unsigned int)_o__wcsicmp(v28, L"yes")) )
    {
      if ( _InterlockedDecrement((volatile signed __int32 *)(v28 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v28 - 24) + 8LL))(*(_QWORD *)(v28 - 24));
LABEL_62:
      v29 = pszPath - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v29 + 8LL))(*(_QWORD *)v29);
      return 0;
    }
    FrameWindow::PreloadAllPlugins(this);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v28 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v28 - 24) + 8LL))(*(_QWORD *)(v28 - 24));
    v30 = pszPath - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v30 + 8LL))(*(_QWORD *)v30);
  }
  pszPath = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  ModuleFileNameW = Win32Helpers::GetModuleFileNameW(0);
  if ( !ModuleFileNameW )
  {
    FileNameW = PathFindFileNameW(pszPath);
    if ( FileNameW )
    {
      v33 = -1;
      do
        ++v33;
      while ( FileNameW[v33] );
    }
    else
    {
      v33 = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(&pszPath, FileNameW, v33);
    goto LABEL_62;
  }
  if ( ModuleFileNameW >= 0 )
    ModuleFileNameW = -2147467259;
  v34 = pszPath - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v34 + 8LL))(*(_QWORD *)v34);
  return ModuleFileNameW;
}

```

## disassembly

```asm
0x1800241cc  mov     [rsp-38h+pszPath], r9
0x1800241d1  mov     [rsp-38h+arg_8], edx
0x1800241d5  push    rbp
0x1800241d6  push    rbx
0x1800241d7  push    rsi
0x1800241d8  push    rdi
0x1800241d9  push    r12
0x1800241db  push    r14
0x1800241dd  push    r15
0x1800241df  mov     rbp, rsp
0x1800241e2  sub     rsp, 40h
0x1800241e6  mov     r11, r8
0x1800241e9  mov     rsi, rcx
0x1800241ec  mov     [rbp+arg_8], r11d
0x1800241f0  mov     edx, r8d
0x1800241f3  call    ?IsPluginReady@FrameWindow@@AEBA_NW4PluginId@@@Z; FrameWindow::IsPluginReady(PluginId)
0x1800241f8  xor     r14d, r14d
0x1800241fb  test    al, al
0x1800241fd  jnz     loc_18002460A
0x180024203  test    r11d, r11d
0x180024206  jz      loc_1800242AB
0x18002420c  sub     r11d, 1
0x180024210  jz      loc_18002429E
0x180024216  sub     r11d, 1
0x18002421a  jz      short loc_180024291
0x18002421c  sub     r11d, 1
0x180024220  jz      short loc_180024284
0x180024222  sub     r11d, 1
0x180024226  jz      short loc_180024277
0x180024228  sub     r11d, 1
0x18002422c  jz      short loc_18002426A
0x18002422e  sub     r11d, 1
0x180024232  jz      short loc_18002425D
0x180024234  sub     r11d, 2
0x180024238  jz      short loc_180024250
0x18002423a  cmp     r11d, 1
0x18002423e  jnz     loc_18002431B
0x180024244  mov     edi, 3A0h
0x180024249  lea     edx, [rdi-14h]
0x18002424c  mov     ebx, edi
0x18002424e  jmp     short loc_1800242B6
0x180024250  mov     ebx, 3ACh
0x180024255  movzx   edi, bx
0x180024258  lea     edx, [rbx-0Eh]
0x18002425b  jmp     short loc_1800242B6
0x18002425d  mov     ebx, 3B0h
0x180024262  movzx   edi, bx
0x180024265  lea     edx, [rbx-14h]
0x180024268  jmp     short loc_1800242B6
0x18002426a  mov     ebx, 3AEh
0x18002426f  movzx   edi, bx
0x180024272  lea     edx, [rbx-14h]
0x180024275  jmp     short loc_1800242B6
0x180024277  mov     ebx, 3AAh
0x18002427c  movzx   edi, bx
0x18002427f  lea     edx, [rbx-14h]
0x180024282  jmp     short loc_1800242B6
0x180024284  mov     ebx, 3A8h
0x180024289  movzx   edi, bx
0x18002428c  lea     edx, [rbx-14h]
0x18002428f  jmp     short loc_1800242B6
0x180024291  mov     ebx, 3A6h
0x180024296  movzx   edi, bx
0x180024299  lea     edx, [rbx-14h]
0x18002429c  jmp     short loc_1800242B6
0x18002429e  mov     ebx, 3A4h
0x1800242a3  movzx   edi, bx
0x1800242a6  lea     edx, [rbx-14h]
0x1800242a9  jmp     short loc_1800242B6
0x1800242ab  mov     edi, r14d
0x1800242ae  mov     edx, 38Ah
0x1800242b3  mov     ebx, r14d
0x1800242b6  mov     rcx, [rsi+238h]
0x1800242bd  mov     rax, [rcx]
0x1800242c0  xor     r8d, r8d
0x1800242c3  mov     rax, [rax+30h]
0x1800242c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242cc  test    di, di
0x1800242cf  jz      short loc_18002431B
0x1800242d1  mov     edx, [rbp+arg_8]
0x1800242d4  mov     rcx, rsi
0x1800242d7  call    ?WasShowToolStartFired@FrameWindow@@AEBA_NW4PluginId@@@Z; FrameWindow::WasShowToolStartFired(PluginId)
0x1800242dc  test    al, al
0x1800242de  jz      short loc_18002431B
0x1800242e0  mov     rcx, rsi
0x1800242e3  call    ?WasShowToolStopFired@FrameWindow@@AEBA_NW4PluginId@@@Z; FrameWindow::WasShowToolStopFired(PluginId)
0x1800242e8  test    al, al
0x1800242ea  jnz     short loc_18002431B
0x1800242ec  mov     rcx, [rsi+238h]
0x1800242f3  mov     rax, [rcx]
0x1800242f6  xor     r8d, r8d
0x1800242f9  mov     edx, ebx
0x1800242fb  mov     rax, [rax+30h]
0x1800242ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024304  lea     rcx, [rsi+1C0h]
0x18002430b  lea     rdx, [rbp+arg_8]
0x18002430f  call    ??A?$map@W4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@U?$less@W4PluginId@@@3@V?$allocator@U?$pair@$$CBW4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@@std@@@3@@std@@QEAAAEAV?$shared_ptr@UBrowserToolThreadInfo@@@1@AEBW4PluginId@@@Z; std::map<PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](PluginId const &)
0x180024314  mov     rcx, [rax]
0x180024317  mov     byte ptr [rcx+1Bh], 1
0x18002431b  lea     r12, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180024322  or      r15, 0FFFFFFFFFFFFFFFFh
0x180024326  cmp     [rsi+1B5h], r14b
0x18002432d  jnz     loc_180024414
0x180024333  mov     eax, [rsi+220h]
0x180024339  cmp     [rbp+arg_8], eax
0x18002433c  jnz     loc_180024414
0x180024342  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180024349  mov     rcx, r12
0x18002434c  mov     rax, [rax+18h]
0x180024350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024355  add     rax, 18h
0x180024359  mov     [rbp+psz], rax
0x18002435d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180024364  mov     rcx, r12
0x180024367  mov     rax, [rax+18h]
0x18002436b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024370  add     rax, 18h
0x180024374  mov     [rbp+var_10], rax
0x180024378  lea     rdx, [rbp+var_20]
0x18002437c  mov     ecx, [rbp+arg_8]
0x18002437f  call    ?GetScriptToolInitializeInfo@F12@@YAJW4PluginId@@AEAUScriptToolInitializeInfo@@@Z; F12::GetScriptToolInitializeInfo(PluginId,ScriptToolInitializeInfo &)
0x180024384  test    eax, eax
0x180024386  jnz     loc_18002444D
0x18002438c  mov     rdi, [rbp+psz]
0x180024390  test    rdi, rdi
0x180024393  jnz     loc_18002442F
0x180024399  mov     rbx, r14
0x18002439c  mov     [rbp+pszPath], rbx
0x1800243a0  mov     rcx, [rsi+238h]
0x1800243a7  mov     rax, [rcx]
0x1800243aa  mov     r8, rbx
0x1800243ad  mov     edx, 388h
0x1800243b2  mov     rax, [rax+30h]
0x1800243b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243bb  mov     byte ptr [rsi+1B5h], 1
0x1800243c2  mov     rcx, rbx; bstrString
0x1800243c5  call    cs:__imp_SysFreeString
0x1800243cb  nop
0x1800243cc  mov     rdx, [rbp+var_10]
0x1800243d0  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800243d4  mov     eax, r15d
0x1800243d7  lock xadd [rdx+10h], eax
0x1800243dc  add     eax, r15d
0x1800243df  test    eax, eax
0x1800243e1  jg      short loc_1800243F2
0x1800243e3  mov     rcx, [rdx]
0x1800243e6  mov     rax, [rcx]
0x1800243e9  mov     rax, [rax+8]
0x1800243ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243f2  lea     rdx, [rdi-18h]
0x1800243f6  mov     eax, r15d
0x1800243f9  lock xadd [rdx+10h], eax
0x1800243fe  add     eax, r15d
0x180024401  test    eax, eax
0x180024403  jg      short loc_180024414
0x180024405  mov     rcx, [rdx]
0x180024408  mov     rax, [rcx]
0x18002440b  mov     rax, [rax+8]
0x18002440f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024414  lea     rbx, [rsi+1C0h]
0x18002441b  mov     r8, [rbx]
0x18002441e  mov     rcx, [r8+8]
0x180024422  xor     eax, eax
0x180024424  mov     dword ptr [rbp+psz+4], eax
0x180024427  mov     rdx, r8
0x18002442a  jmp     loc_1800244C2
0x18002442f  mov     rcx, rdi; psz
0x180024432  call    cs:__imp_SysAllocString
0x180024438  mov     rbx, rax
0x18002443b  mov     [rbp+pszPath], rax
0x18002443f  test    rax, rax
0x180024442  jz      loc_180024705
0x180024448  jmp     loc_1800243A0
0x18002444d  mov     rdx, [rbp+var_10]
0x180024451  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180024455  mov     eax, r15d
0x180024458  lock xadd [rdx+10h], eax
0x18002445d  add     eax, r15d
0x180024460  test    eax, eax
0x180024462  jg      short loc_180024473
0x180024464  mov     rcx, [rdx]
0x180024467  mov     rax, [rcx]
0x18002446a  mov     rax, [rax+8]
0x18002446e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024473  mov     rdx, [rbp+psz]
0x180024477  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002447b  mov     ecx, r15d
0x18002447e  lock xadd [rdx+10h], ecx
0x180024483  add     ecx, r15d
0x180024486  test    ecx, ecx
0x180024488  jg      short loc_180024499
0x18002448a  mov     rcx, [rdx]
0x18002448d  mov     r8, [rcx]
0x180024490  mov     rax, [r8+8]
0x180024494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024499  mov     rax, r15
0x18002449c  jmp     loc_18002460C
0x1800244a1  mov     eax, [rbp+arg_8]
0x1800244a4  cmp     [rcx+20h], eax
0x1800244a7  jge     short loc_1800244AE
0x1800244a9  mov     r9b, 1
0x1800244ac  jmp     short loc_1800244B4
0x1800244ae  mov     r9b, r14b
0x1800244b1  mov     rdx, rcx
0x1800244b4  lea     rax, [rcx+10h]
0x1800244b8  test    r9b, r9b
0x1800244bb  cmovz   rax, rcx
0x1800244bf  mov     rcx, [rax]
0x1800244c2  cmp     [rcx+19h], r14b
0x1800244c6  jz      short loc_1800244A1
0x1800244c8  cmp     [rdx+19h], r14b
0x1800244cc  jnz     short loc_1800244EE
0x1800244ce  mov     eax, [rdx+20h]
0x1800244d1  cmp     [rbp+arg_8], eax
0x1800244d4  jl      short loc_1800244EE
0x1800244d6  cmp     rdx, r8
0x1800244d9  jz      short loc_1800244EE
0x1800244db  lea     rdx, [rbp+arg_8]
0x1800244df  mov     rcx, rbx
0x1800244e2  call    ??A?$map@W4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@U?$less@W4PluginId@@@3@V?$allocator@U?$pair@$$CBW4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@@std@@@3@@std@@QEAAAEAV?$shared_ptr@UBrowserToolThreadInfo@@@1@AEBW4PluginId@@@Z; std::map<PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](PluginId const &)
0x1800244e7  mov     rdx, [rax]
0x1800244ea  mov     byte ptr [rdx+19h], 1
0x1800244ee  mov     edx, [rbp+arg_8]
0x1800244f1  mov     rcx, rsi
0x1800244f4  call    ?IsPluginLoaded@FrameWindow@@AEBA_NW4PluginId@@@Z; FrameWindow::IsPluginLoaded(PluginId)
0x1800244f9  test    al, al
0x1800244fb  jz      short loc_180024510
0x1800244fd  lea     rdx, [rbp+arg_8]
0x180024501  mov     rcx, rbx
0x180024504  call    ??A?$map@W4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@U?$less@W4PluginId@@@3@V?$allocator@U?$pair@$$CBW4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@@std@@@3@@std@@QEAAAEAV?$shared_ptr@UBrowserToolThreadInfo@@@1@AEBW4PluginId@@@Z; std::map<PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](PluginId const &)
0x180024509  mov     rcx, [rax]
0x18002450c  mov     byte ptr [rcx+18h], 1
0x180024510  mov     eax, [rsi+220h]
0x180024516  cmp     [rbp+arg_8], eax
0x180024519  jnz     loc_18002466E
0x18002451f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180024526  mov     rcx, r12
0x180024529  mov     rax, [rax+18h]
0x18002452d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024532  add     rax, 18h
0x180024536  mov     [rbp+pszPath], rax
0x18002453a  lea     rdx, aDisablepreload; "DisablePreload"
0x180024541  lea     rcx, [rbp+pszPath]
0x180024545  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x18002454a  test    al, al
0x18002454c  jnz     short loc_180024565
0x18002454e  mov     r8d, 0Eh
0x180024554  lea     rdx, aDisablepreload; "DisablePreload"
0x18002455b  lea     rcx, [rbp+pszPath]
0x18002455f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180024564  nop
0x180024565  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002456c  mov     rcx, r12
0x18002456f  mov     rax, [rax+18h]
0x180024573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024578  add     rax, 18h
0x18002457c  mov     [rbp+arg_10], rax
0x180024580  lea     rdx, [rbp+arg_10]
0x180024584  lea     rcx, [rbp+pszPath]
0x180024588  call    ?GetF12RegEntry@F12@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; F12::GetF12RegEntry(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18002458d  mov     rbx, [rbp+arg_10]
0x180024591  test    eax, eax
0x180024593  jnz     loc_18002461B
0x180024599  lea     rdx, aTrue; "true"
0x1800245a0  mov     rcx, rbx
0x1800245a3  call    cs:__imp__o__wcsicmp
0x1800245a9  test    eax, eax
0x1800245ab  jz      short loc_1800245C1
0x1800245ad  lea     rdx, aYes; "yes"
0x1800245b4  mov     rcx, rbx
0x1800245b7  call    cs:__imp__o__wcsicmp
0x1800245bd  test    eax, eax
0x1800245bf  jnz     short loc_18002461B
0x1800245c1  lea     rdx, [rbx-18h]
0x1800245c5  mov     eax, r15d
0x1800245c8  lock xadd [rdx+10h], eax
0x1800245cd  add     eax, r15d
0x1800245d0  test    eax, eax
0x1800245d2  jg      short loc_1800245E4
0x1800245d4  mov     rcx, [rdx]
0x1800245d7  mov     rax, [rcx]
0x1800245da  mov     rax, [rax+8]
0x1800245de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245e3  nop
0x1800245e4  mov     rdx, [rbp+pszPath]
0x1800245e8  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800245ec  mov     eax, r15d
0x1800245ef  lock xadd [rdx+10h], eax
0x1800245f4  add     eax, r15d
0x1800245f7  test    eax, eax
0x1800245f9  jg      short loc_18002460A
0x1800245fb  mov     rcx, [rdx]
0x1800245fe  mov     rax, [rcx]
0x180024601  mov     rax, [rax+8]
0x180024605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002460a  xor     eax, eax
0x18002460c  add     rsp, 40h
0x180024610  pop     r15
0x180024612  pop     r14
0x180024614  pop     r12
  ... truncated ...
```
