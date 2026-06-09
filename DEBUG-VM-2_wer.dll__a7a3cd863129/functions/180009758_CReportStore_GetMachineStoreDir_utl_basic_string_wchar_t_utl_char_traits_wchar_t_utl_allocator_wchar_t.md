# CReportStore::GetMachineStoreDir(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180009758`
- end: `0x18000998a`
- name: `?GetMachineStoreDir@CReportStore@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `562`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x180008a48`
- `0x180009990`
- `0x1800678a0`
- `0x180069170`

## callees

- `0x180009758`
- `0x18000bc10`
- `0x18000dad0`
- `0x18000ea64`
- `0x180013730`
- `0x180028dac`
- `0x18002d1ec`
- `0x180030408`
- `0x18003db78`
- `0x180042918`
- `0x180050db0`
- `0x180051ff8`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009899`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009923`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009899`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009923`
- `ext-ms-win-wer-xbox-l1-1-0!XerGetMachineStorePath` at `0x1800097be`
- `ext-ms-win-wer-xbox-l1-1-0!XerGetMachineStorePath` at `0x1800097be`

## string_xrefs

- `0x1800097d2`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x1800098f9`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CReportStore::GetMachineStoreDir(__int64 (__fastcall ***a1)(_QWORD), _QWORD *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rdx
  int MachineStorePath; // eax
  const WCHAR *StorePath; // rax
  __int64 v9; // rax
  int v10; // eax
  LPCWSTR lpFileName[2]; // [rsp+20h] [rbp-E0h] BYREF
  char v13; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpMem[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v15; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Src[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 2147942487LL;
    v6 = 92;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
      (const char *)v5,
      (int)lpFileName[0]);
LABEL_29:
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
    return v4;
  }
  if ( (unsigned __int8)IsXerGetMachineIdPresent() )
  {
    MachineStorePath = XerGetMachineStorePath(Src);
    v4 = MachineStorePath;
    if ( MachineStorePath < 0 )
    {
      v6 = 101;
LABEL_6:
      v5 = (unsigned int)MachineStorePath;
      goto LABEL_7;
    }
    MachineStorePath = UtilExpandEnvironmentStrings(Src);
    v4 = MachineStorePath;
    if ( MachineStorePath < 0 )
    {
      v6 = 102;
      goto LABEL_6;
    }
  }
  else
  {
    StorePath = CSettings::GetStorePath((CSettings *)(a1 + 9));
    MachineStorePath = UtilExpandEnvironmentStrings(StorePath);
    v4 = MachineStorePath;
    if ( MachineStorePath < 0 )
    {
      v6 = 109;
      goto LABEL_6;
    }
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_c7d90b7e9c5e35268a88cfd8be5fc765_Traceguids, lpFileName[0]);
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
  if ( (unsigned int)UtilGetFinalPath(lpFileName[0]) )
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(lpFileName, lpMem);
  if ( lpMem[0] != &v15 )
    HeapFree(g_hWerheap, 0, lpMem[0]);
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_c7d90b7e9c5e35268a88cfd8be5fc765_Traceguids, lpFileName[0]);
  v9 = (**a1)(a1);
  v10 = CPath::Append(lpFileName[0], v9, a2);
  v4 = v10;
  if ( v10 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_c7d90b7e9c5e35268a88cfd8be5fc765_Traceguids, *a2);
    v4 = 0;
    goto LABEL_29;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7B,
    (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
    (const char *)(unsigned int)v10,
    (int)lpFileName[0]);
  if ( (char *)lpFileName[0] != &v13 )
    HeapFree(g_hWerheap, 0, (LPVOID)lpFileName[0]);
  return v4;
}

```

## disassembly

```asm
0x180009758  mov     [rsp-8+arg_10], rbx
0x18000975d  mov     [rsp-8+arg_18], rsi
0x180009762  push    rbp
0x180009763  push    rdi
0x180009764  push    r15
0x180009766  lea     rbp, [rsp-180h]
0x18000976e  sub     rsp, 280h
0x180009775  mov     rax, cs:__security_cookie
0x18000977c  xor     rax, rsp
0x18000977f  mov     [rbp+190h+var_20], rax
0x180009786  mov     rdi, rdx
0x180009789  mov     rsi, rcx
0x18000978c  lea     rcx, [rsp+290h+lpFileName]; void *
0x180009791  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180009796  nop
0x180009797  test    rdi, rdi
0x18000979a  jnz     short loc_1800097A9
0x18000979c  mov     ebx, 80070057h
0x1800097a1  mov     r9d, ebx
0x1800097a4  lea     edx, [rdi+5Ch]
0x1800097a7  jmp     short loc_1800097D2
0x1800097a9  call    IsXerGetMachineIdPresent
0x1800097ae  lea     r15, WPP_GLOBAL_Control
0x1800097b5  test    al, al
0x1800097b7  jz      short loc_180009806
0x1800097b9  lea     rcx, [rsp+290h+Src]
0x1800097be  call    cs:__imp_XerGetMachineStorePath
0x1800097c4  mov     ebx, eax
0x1800097c6  test    eax, eax
0x1800097c8  jns     short loc_1800097EA
0x1800097ca  mov     edx, 65h ; 'e'; void *
0x1800097cf  mov     r9d, eax; char *
0x1800097d2  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x1800097d9  mov     rcx, [rbp+198h]; this
0x1800097e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800097e5  jmp     loc_180009957
0x1800097ea  lea     rdx, [rsp+290h+lpFileName]
0x1800097ef  lea     rcx, [rsp+290h+Src]; lpSrc
0x1800097f4  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800097f9  mov     ebx, eax
0x1800097fb  test    eax, eax
0x1800097fd  jns     short loc_180009855
0x1800097ff  mov     edx, 66h ; 'f'
0x180009804  jmp     short loc_1800097CF
0x180009806  lea     rcx, [rsi+48h]; this
0x18000980a  call    ?GetStorePath@CSettings@@QEBAPEB_WXZ; CSettings::GetStorePath(void)
0x18000980f  mov     rcx, rax; lpSrc
0x180009812  lea     rdx, [rsp+290h+lpFileName]
0x180009817  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18000981c  mov     ebx, eax
0x18000981e  test    eax, eax
0x180009820  jns     short loc_180009829
0x180009822  mov     edx, 6Dh ; 'm'
0x180009827  jmp     short loc_1800097CF
0x180009829  mov     rcx, cs:WPP_GLOBAL_Control
0x180009830  cmp     rcx, r15
0x180009833  jz      short loc_180009855
0x180009835  test    byte ptr [rcx+1Ch], 4
0x180009839  jz      short loc_180009855
0x18000983b  mov     edx, 0Ah
0x180009840  mov     r9, [rsp+290h+lpFileName]
0x180009845  lea     r8, WPP_c7d90b7e9c5e35268a88cfd8be5fc765_Traceguids
0x18000984c  mov     rcx, [rcx+10h]
0x180009850  call    WPP_SF_S
0x180009855  lea     rcx, [rsp+290h+lpMem]; void *
0x18000985a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18000985f  lea     rdx, [rsp+290h+lpMem]
0x180009864  mov     rcx, [rsp+290h+lpFileName]; lpFileName
0x180009869  call    ?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18000986e  test    eax, eax
0x180009870  jz      short loc_180009881
0x180009872  lea     rdx, [rsp+290h+lpMem]
0x180009877  lea     rcx, [rsp+290h+lpFileName]
0x18000987c  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x180009881  lea     rax, [rsp+290h+var_240]
0x180009886  mov     r8, [rsp+290h+lpMem]; lpMem
0x18000988b  cmp     r8, rax
0x18000988e  jz      short loc_18000989F
0x180009890  xor     edx, edx; dwFlags
0x180009892  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180009899  call    cs:__imp_HeapFree
0x18000989f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098a6  cmp     rcx, r15
0x1800098a9  jz      short loc_1800098CB
0x1800098ab  test    byte ptr [rcx+1Ch], 4
0x1800098af  jz      short loc_1800098CB
0x1800098b1  mov     edx, 0Bh
0x1800098b6  mov     r9, [rsp+290h+lpFileName]
0x1800098bb  lea     r8, WPP_c7d90b7e9c5e35268a88cfd8be5fc765_Traceguids
0x1800098c2  mov     rcx, [rcx+10h]
0x1800098c6  call    WPP_SF_S
0x1800098cb  mov     rax, [rsi]
0x1800098ce  mov     rcx, rsi
0x1800098d1  mov     rax, [rax]
0x1800098d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098d9  mov     r8, rdi
0x1800098dc  mov     rdx, rax
0x1800098df  mov     rcx, [rsp+290h+lpFileName]
0x1800098e4  call    ?Append@CPath@@SAJPEB_W0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CPath::Append(wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800098e9  mov     ebx, eax
0x1800098eb  test    eax, eax
0x1800098ed  jns     short loc_18000992B
0x1800098ef  mov     rcx, [rbp+198h]; this
0x1800098f6  mov     r9d, eax; char *
0x1800098f9  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180009900  mov     edx, 7Bh ; '{'; void *
0x180009905  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000990a  nop
0x18000990b  lea     rax, [rsp+290h+var_260]
0x180009910  mov     r8, [rsp+290h+lpFileName]; lpMem
0x180009915  cmp     r8, rax
0x180009918  jz      short loc_180009961
0x18000991a  xor     edx, edx; dwFlags
0x18000991c  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180009923  call    cs:__imp_HeapFree
0x180009929  jmp     short loc_180009961
0x18000992b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009932  cmp     rcx, r15
0x180009935  jz      short loc_180009955
0x180009937  test    byte ptr [rcx+1Ch], 4
0x18000993b  jz      short loc_180009955
0x18000993d  mov     edx, 0Ch
0x180009942  mov     r9, [rdi]
0x180009945  lea     r8, WPP_c7d90b7e9c5e35268a88cfd8be5fc765_Traceguids
0x18000994c  mov     rcx, [rcx+10h]
0x180009950  call    WPP_SF_S
0x180009955  xor     ebx, ebx
0x180009957  lea     rcx, [rsp+290h+lpFileName]; void *
0x18000995c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180009961  mov     eax, ebx
0x180009963  mov     rcx, [rbp+190h+var_20]
0x18000996a  xor     rcx, rsp; StackCookie
0x18000996d  call    __security_check_cookie
0x180009972  lea     r11, [rsp+290h+var_10]
0x18000997a  mov     rbx, [r11+30h]
0x18000997e  mov     rsi, [r11+38h]
0x180009982  mov     rsp, r11
0x180009985  pop     r15
0x180009987  pop     rdi
0x180009988  pop     rbp
0x180009989  retn
```
