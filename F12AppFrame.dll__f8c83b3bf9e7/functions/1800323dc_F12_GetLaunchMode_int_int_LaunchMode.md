# F12::GetLaunchMode(int,int,LaunchMode &)

- ea: `0x1800323dc`
- end: `0x1800325c9`
- name: `?GetLaunchMode@F12@@YAXHHAEAW4LaunchMode@@@Z`
- size: `493`
- prototype: `void __fastcall(F12 *__hidden this, int, int, enum LaunchMode *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180016710`

## callees

- `0x180003338`
- `0x180003858`
- `0x1800042a4`
- `0x1800323dc`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x1800324cb`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x1800324cb`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180032513`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180032545`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180032572`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180032513`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180032545`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180032572`
- `KERNEL32!GetLastError` at `0x180032490`
- `KERNEL32!GetLastError` at `0x180032490`
- `KERNEL32!SetLastError` at `0x1800323f9`
- `KERNEL32!SetLastError` at `0x1800323f9`
- `KERNEL32!GetModuleFileNameW` at `0x180032464`
- `KERNEL32!GetModuleFileNameW` at `0x180032464`

## string_xrefs

- `0x180032568`: `f12Attach.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall F12::GetLaunchMode(F12 *this, __int64 a2, int *a3, enum LaunchMode *a4)
{
  int v5; // ebp
  __int64 v6; // rax
  wchar_t *v7; // rbx
  signed int ModuleFileNameW; // eax
  __int64 v9; // rdi
  wchar_t *v10; // rax
  int v11; // eax
  wchar_t *v12; // rax
  wchar_t *v13; // rax
  wchar_t *Str; // [rsp+60h] [rbp+18h] BYREF

  v5 = (int)this;
  *a3 = ((_DWORD)this != 0) + 1;
  SetLastError(0);
  v6 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  v7 = (wchar_t *)(v6 + 24);
  Str = (wchar_t *)(v6 + 24);
  if ( ((*(_DWORD *)(v6 + 12) - 260) | (1 - *(_DWORD *)(v6 + 16))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&Str);
    v7 = Str;
  }
  if ( *((int *)v7 - 3) < 260 )
    goto LABEL_31;
  *((_DWORD *)v7 - 4) = 260;
  v7[260] = 0;
  ModuleFileNameW = GetModuleFileNameW(0, v7, 0x104u);
  if ( ModuleFileNameW < 0 || ModuleFileNameW > *((_DWORD *)v7 - 3) )
    goto LABEL_31;
  *((_DWORD *)v7 - 4) = ModuleFileNameW;
  v7[ModuleFileNameW] = 0;
  if ( *((int *)v7 - 4) <= 0 || GetLastError() )
    goto LABEL_28;
  v9 = *((int *)v7 - 4);
  if ( (int)((*((_DWORD *)v7 - 3) - v9) | (1 - *((_DWORD *)v7 - 2))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&Str);
    v7 = Str;
  }
  _wcslwr_s(v7, (int)v9 + 1);
  if ( (int)v9 < 0 || (int)v9 > *((_DWORD *)v7 - 3) )
LABEL_31:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)v7 - 4) = v9;
  v7[v9] = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(&Str, &Str);
  v7 = Str;
  if ( v5 )
  {
    if ( *((int *)Str - 4) >= 0 && (v10 = wcsstr(Str, L"iechooser.exe")) != 0 && (int)(v10 - v7) >= 0 )
      v11 = 0;
    else
      v11 = 3;
    *a3 = v11;
  }
  else
  {
    if ( *((int *)Str - 4) < 0 )
      goto LABEL_27;
    v12 = wcsstr(Str, L"iexplore.exe");
    if ( v12 && (int)(v12 - v7) >= 0 )
    {
      *a3 = 1;
      goto LABEL_28;
    }
    if ( *((int *)v7 - 4) >= 0 && (v13 = wcsstr(v7, L"f12Attach.dll")) != 0 && (int)(v13 - v7) >= 0 )
      *a3 = 0;
    else
LABEL_27:
      *a3 = 3;
  }
LABEL_28:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
}

```

## disassembly

```asm
0x1800323dc  push    rbx
0x1800323de  push    rbp
0x1800323df  push    rsi
0x1800323e0  push    rdi
0x1800323e1  sub     rsp, 28h
0x1800323e5  mov     rsi, r8
0x1800323e8  mov     ebp, ecx
0x1800323ea  mov     eax, ecx
0x1800323ec  neg     eax
0x1800323ee  sbb     edx, edx
0x1800323f0  neg     edx
0x1800323f2  inc     edx
0x1800323f4  mov     [r8], edx
0x1800323f7  xor     ecx, ecx; dwErrCode
0x1800323f9  call    cs:__imp_SetLastError
0x1800323ff  nop
0x180032400  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180032407  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18003240e  mov     rax, [rax+18h]
0x180032412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032417  lea     rbx, [rax+18h]
0x18003241b  mov     [rsp+48h+Str], rbx
0x180032420  mov     ecx, 1
0x180032425  sub     ecx, [rbx-8]
0x180032428  mov     eax, [rbx-0Ch]
0x18003242b  mov     edi, 104h
0x180032430  sub     eax, edi
0x180032432  or      ecx, eax
0x180032434  jge     short loc_180032447
0x180032436  mov     edx, edi
0x180032438  lea     rcx, [rsp+48h+Str]
0x18003243d  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180032442  mov     rbx, [rsp+48h+Str]
0x180032447  cmp     [rbx-0Ch], edi
0x18003244a  jl      loc_1800325BE
0x180032450  mov     [rbx-10h], edi
0x180032453  xor     eax, eax
0x180032455  mov     [rbx+208h], ax
0x18003245c  mov     r8d, edi; nSize
0x18003245f  mov     rdx, rbx; lpFilename
0x180032462  xor     ecx, ecx; hModule
0x180032464  call    cs:__imp_GetModuleFileNameW
0x18003246a  test    eax, eax
0x18003246c  js      loc_1800325BE
0x180032472  cmp     eax, [rbx-0Ch]
0x180032475  jg      loc_1800325BE
0x18003247b  mov     [rbx-10h], eax
0x18003247e  movsxd  rcx, eax
0x180032481  xor     eax, eax
0x180032483  mov     [rbx+rcx*2], ax
0x180032487  cmp     [rbx-10h], eax
0x18003248a  jle     loc_180032595
0x180032490  call    cs:__imp_GetLastError
0x180032496  test    eax, eax
0x180032498  jnz     loc_180032595
0x18003249e  movsxd  rdi, dword ptr [rbx-10h]
0x1800324a2  lea     ecx, [rax+1]
0x1800324a5  sub     ecx, [rbx-8]
0x1800324a8  mov     eax, [rbx-0Ch]
0x1800324ab  sub     eax, edi
0x1800324ad  or      ecx, eax
0x1800324af  jge     short loc_1800324C2
0x1800324b1  mov     edx, edi
0x1800324b3  lea     rcx, [rsp+48h+Str]
0x1800324b8  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800324bd  mov     rbx, [rsp+48h+Str]
0x1800324c2  lea     eax, [rdi+1]
0x1800324c5  movsxd  rdx, eax; SizeInWords
0x1800324c8  mov     rcx, rbx; String
0x1800324cb  call    cs:__imp__wcslwr_s
0x1800324d1  test    edi, edi
0x1800324d3  js      loc_1800325BE
0x1800324d9  cmp     edi, [rbx-0Ch]
0x1800324dc  jg      loc_1800325BE
0x1800324e2  mov     [rbx-10h], edi
0x1800324e5  xor     eax, eax
0x1800324e7  mov     [rbx+rdi*2], ax
0x1800324eb  lea     rdx, [rsp+48h+Str]
0x1800324f0  lea     rcx, [rsp+48h+Str]
0x1800324f5  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800324fa  mov     rbx, [rsp+48h+Str]
0x1800324ff  test    ebp, ebp
0x180032501  jz      short loc_180032535
0x180032503  cmp     dword ptr [rbx-10h], 0
0x180032507  jl      short loc_18003252C
0x180032509  lea     rdx, aIechooserExe; "iechooser.exe"
0x180032510  mov     rcx, rbx; Str
0x180032513  call    cs:__imp_wcsstr
0x180032519  test    rax, rax
0x18003251c  jz      short loc_18003252C
0x18003251e  sub     rax, rbx
0x180032521  sar     rax, 1
0x180032524  test    eax, eax
0x180032526  js      short loc_18003252C
0x180032528  xor     eax, eax
0x18003252a  jmp     short loc_180032531
0x18003252c  mov     eax, 3
0x180032531  mov     [rsi], eax
0x180032533  jmp     short loc_180032595
0x180032535  cmp     dword ptr [rbx-10h], 0
0x180032539  jl      short loc_18003258F
0x18003253b  lea     rdx, aIexploreExe; "iexplore.exe"
0x180032542  mov     rcx, rbx; Str
0x180032545  call    cs:__imp_wcsstr
0x18003254b  test    rax, rax
0x18003254e  jz      short loc_180032562
0x180032550  sub     rax, rbx
0x180032553  sar     rax, 1
0x180032556  test    eax, eax
0x180032558  js      short loc_180032562
0x18003255a  mov     dword ptr [rsi], 1
0x180032560  jmp     short loc_180032595
0x180032562  cmp     dword ptr [rbx-10h], 0
0x180032566  jl      short loc_18003258F
0x180032568  lea     rdx, aF12attachDll; "f12Attach.dll"
0x18003256f  mov     rcx, rbx; Str
0x180032572  call    cs:__imp_wcsstr
0x180032578  test    rax, rax
0x18003257b  jz      short loc_18003258F
0x18003257d  sub     rax, rbx
0x180032580  sar     rax, 1
0x180032583  test    eax, eax
0x180032585  js      short loc_18003258F
0x180032587  mov     dword ptr [rsi], 0
0x18003258d  jmp     short loc_180032595
0x18003258f  mov     dword ptr [rsi], 3
0x180032595  lea     rdx, [rbx-18h]
0x180032599  or      eax, 0FFFFFFFFh
0x18003259c  lock xadd [rdx+10h], eax
0x1800325a1  sub     eax, 1
0x1800325a4  jg      short loc_1800325B5
0x1800325a6  mov     rcx, [rdx]
0x1800325a9  mov     rax, [rcx]
0x1800325ac  mov     rax, [rax+8]
0x1800325b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325b5  add     rsp, 28h
0x1800325b9  pop     rdi
0x1800325ba  pop     rsi
0x1800325bb  pop     rbp
0x1800325bc  pop     rbx
0x1800325bd  retn
0x1800325be  mov     ecx, 80070057h; int
0x1800325c3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
