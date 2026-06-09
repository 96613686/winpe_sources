# UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)

- ea: `0x180008174`
- end: `0x180008382`
- name: `?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z`
- size: `526`
- prototype: `__int64 __usercall@<rax>(HKEY hkey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, __int64, char, char)`
- caller_count: `15`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x180009298`
- `0x180017a18`
- `0x18001919c`
- `0x1800222c4`
- `0x180030950`
- `0x180037434`
- `0x1800395bc`
- `0x18003d858`
- `0x18003e888`
- `0x180042398`
- `0x1800426e0`
- `0x18004aa70`
- `0x18008ff54`
- `0x1800911ac`
- `0x1800a5698`

## callees

- `0x180008174`
- `0x180009b40`
- `0x180009bb4`
- `0x18000bc10`
- `0x18000c390`
- `0x18000dad0`
- `0x18000ea64`
- `0x18001c6d8`
- `0x18001f8c8`
- `0x180042918`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008352`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008352`
- `ntdll!wcsnlen` at `0x1800082f7`
- `ntdll!wcsnlen` at `0x1800082f7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008286`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800082dd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008286`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800082dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008361`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008361`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008224`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008224`

## pseudocode

```c
__int64 __fastcall UtilRegGetString(
        HKEY hkey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValue,
        __int64 a4,
        __int64 a5,
        char a6,
        unsigned __int8 a7)
{
  __int64 v11; // rsi
  unsigned int v13; // ebx
  int v14; // ebx
  HKEY *phkResult; // rax
  LSTATUS ValueW; // eax
  bool v17; // cc
  size_t v18; // rax
  _WORD *v19; // rcx
  HKEY hKey; // [rsp+40h] [rbp-30h] BYREF
  PVOID lpMem[2]; // [rsp+48h] [rbp-28h] BYREF
  char v22; // [rsp+58h] [rbp-18h] BYREF
  DWORD pcbData; // [rsp+A0h] [rbp+30h] BYREF

  pcbData = 0;
  hKey = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
  v11 = a5;
  if ( !a5 )
  {
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpMem);
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    return 2147942487LL;
  }
  if ( a4
    && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(lpMem, a4) )
  {
    goto LABEL_5;
  }
  v14 = a7;
  if ( lpSubKey || a7 )
  {
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    ValueW = RegOpenKeyExW(hkey, lpSubKey, 0, (v14 << 8) | 1, phkResult);
    v13 = ValueW;
    if ( ValueW )
      goto LABEL_9;
    hkey = hKey;
  }
  pcbData = 0;
  ValueW = RegGetValueW(hkey, 0, lpValue, 2u, 0, 0, &pcbData);
  v13 = ValueW;
  if ( ValueW )
  {
LABEL_9:
    if ( !a4 )
    {
      v17 = ValueW <= 0;
      goto LABEL_11;
    }
    goto LABEL_18;
  }
  lpMem[1] = lpMem[0];
  *(_WORD *)lpMem[0] = 0;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                          lpMem,
                          ((unsigned __int64)pcbData >> 1) + 1) )
  {
    ValueW = RegGetValueW(hkey, 0, lpValue, 2u, 0, lpMem[0], &pcbData);
    v13 = ValueW;
    v17 = ValueW <= 0;
    if ( ValueW )
    {
LABEL_11:
      if ( !v17 )
        v13 = (unsigned __int16)ValueW | 0x80070000;
      goto LABEL_22;
    }
    v18 = wcsnlen((const wchar_t *)lpMem[0], (unsigned __int64)pcbData >> 1);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(lpMem, v18);
LABEL_18:
    v13 = 0;
    if ( a6 )
      v13 = UtilExpandEnvironmentStrings((LPCWSTR)lpMem[0]);
    else
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v11, lpMem);
    if ( !v13 )
      goto LABEL_23;
    goto LABEL_22;
  }
LABEL_5:
  v13 = -2147024882;
LABEL_22:
  v19 = *(_WORD **)v11;
  *(_QWORD *)(v11 + 8) = *(_QWORD *)v11;
  *v19 = 0;
LABEL_23:
  if ( lpMem[0] != &v22 )
    HeapFree(g_hWerheap, 0, lpMem[0]);
  if ( hKey )
    RegCloseKey(hKey);
  return v13;
}

```

## disassembly

```asm
0x180008174  mov     [rsp-28h+arg_8], rbx
0x180008179  mov     [rsp-28h+arg_10], rsi
0x18000817e  push    rbp
0x18000817f  push    rdi
0x180008180  push    r12
0x180008182  push    r14
0x180008184  push    r15
0x180008186  mov     rbp, rsp
0x180008189  sub     rsp, 70h
0x18000818d  mov     r14, rcx
0x180008190  mov     [rbp+arg_0], 0
0x180008197  lea     rcx, [rbp+lpMem]; void *
0x18000819b  mov     [rbp+hKey], 0
0x1800081a3  mov     rdi, r9
0x1800081a6  mov     r12, r8
0x1800081a9  mov     r15, rdx
0x1800081ac  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800081b1  mov     rsi, [rbp+arg_20]
0x1800081b5  test    rsi, rsi
0x1800081b8  jnz     short loc_1800081D6
0x1800081ba  lea     rcx, [rbp+lpMem]; void *
0x1800081be  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800081c3  lea     rcx, [rbp+hKey]
0x1800081c7  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800081cc  mov     eax, 80070057h
0x1800081d1  jmp     loc_180008369
0x1800081d6  test    rdi, rdi
0x1800081d9  jz      short loc_1800081F5
0x1800081db  mov     rdx, rdi
0x1800081de  lea     rcx, [rbp+lpMem]
0x1800081e2  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800081e7  test    al, al
0x1800081e9  jnz     short loc_1800081F5
0x1800081eb  mov     ebx, 8007000Eh
0x1800081f0  jmp     loc_180008330
0x1800081f5  movzx   ebx, [rbp+arg_30]
0x1800081f9  test    r15, r15
0x1800081fc  jnz     short loc_180008202
0x1800081fe  test    bl, bl
0x180008200  jz      short loc_180008253
0x180008202  lea     rcx, [rbp+hKey]
0x180008206  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000820b  mov     r9d, ebx
0x18000820e  mov     [rsp+70h+phkResult], rax; phkResult
0x180008213  shl     r9d, 8
0x180008217  xor     r8d, r8d; ulOptions
0x18000821a  or      r9d, 1; samDesired
0x18000821e  mov     rdx, r15; lpSubKey
0x180008221  mov     rcx, r14; hKey
0x180008224  call    cs:__imp_RegOpenKeyExW
0x18000822a  mov     ebx, eax
0x18000822c  test    eax, eax
0x18000822e  jz      short loc_18000824F
0x180008230  test    rdi, rdi
0x180008233  jnz     loc_180008309
0x180008239  test    eax, eax
0x18000823b  jle     loc_180008330
0x180008241  movzx   ebx, ax
0x180008244  or      ebx, 80070000h
0x18000824a  jmp     loc_180008330
0x18000824f  mov     r14, [rbp+hKey]
0x180008253  lea     rax, [rbp+arg_0]
0x180008257  mov     [rbp+arg_0], 0
0x18000825e  mov     [rsp+70h+pcbData], rax; pcbData
0x180008263  mov     r15d, 2
0x180008269  mov     [rsp+70h+pvData], 0; pvData
0x180008272  mov     r9d, r15d; dwFlags
0x180008275  mov     r8, r12; lpValue
0x180008278  mov     [rsp+70h+phkResult], 0; pdwType
0x180008281  xor     edx, edx; lpSubKey
0x180008283  mov     rcx, r14; hkey
0x180008286  call    cs:__imp_RegGetValueW
0x18000828c  mov     ebx, eax
0x18000828e  test    eax, eax
0x180008290  jnz     short loc_180008230
0x180008292  mov     rcx, [rbp+lpMem]
0x180008296  mov     [rbp+var_20], rcx
0x18000829a  mov     [rcx], ax
0x18000829d  lea     rcx, [rbp+lpMem]
0x1800082a1  mov     edx, [rbp+arg_0]
0x1800082a4  shr     rdx, 1
0x1800082a7  inc     rdx
0x1800082aa  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x1800082af  test    al, al
0x1800082b1  jz      loc_1800081EB
0x1800082b7  lea     rax, [rbp+arg_0]
0x1800082bb  mov     r9d, r15d; dwFlags
0x1800082be  mov     [rsp+70h+pcbData], rax; pcbData
0x1800082c3  mov     r8, r12; lpValue
0x1800082c6  mov     rax, [rbp+lpMem]
0x1800082ca  xor     edx, edx; lpSubKey
0x1800082cc  mov     [rsp+70h+pvData], rax; pvData
0x1800082d1  mov     rcx, r14; hkey
0x1800082d4  mov     [rsp+70h+phkResult], 0; pdwType
0x1800082dd  call    cs:__imp_RegGetValueW
0x1800082e3  mov     ebx, eax
0x1800082e5  test    eax, eax
0x1800082e7  jnz     loc_18000823B
0x1800082ed  mov     edx, [rbp+arg_0]
0x1800082f0  mov     rcx, [rbp+lpMem]; Source
0x1800082f4  shr     rdx, 1; MaxCount
0x1800082f7  call    cs:__imp_wcsnlen
0x1800082fd  mov     rdx, rax
0x180008300  lea     rcx, [rbp+lpMem]
0x180008304  call    ?erase@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV12@_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(unsigned __int64)
0x180008309  xor     ebx, ebx
0x18000830b  cmp     [rbp+arg_28], bl
0x18000830e  jz      short loc_180008320
0x180008310  mov     rcx, [rbp+lpMem]; lpSrc
0x180008314  mov     rdx, rsi
0x180008317  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18000831c  mov     ebx, eax
0x18000831e  jmp     short loc_18000832C
0x180008320  lea     rdx, [rbp+lpMem]
0x180008324  mov     rcx, rsi
0x180008327  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18000832c  test    ebx, ebx
0x18000832e  jz      short loc_18000833C
0x180008330  mov     rcx, [rsi]
0x180008333  xor     eax, eax
0x180008335  mov     [rsi+8], rcx
0x180008339  mov     [rcx], ax
0x18000833c  mov     r8, [rbp+lpMem]; lpMem
0x180008340  lea     rax, [rbp+var_18]
0x180008344  cmp     r8, rax
0x180008347  jz      short loc_180008358
0x180008349  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180008350  xor     edx, edx; dwFlags
0x180008352  call    cs:__imp_HeapFree
0x180008358  mov     rcx, [rbp+hKey]; hKey
0x18000835c  test    rcx, rcx
0x18000835f  jz      short loc_180008367
0x180008361  call    cs:__imp_RegCloseKey
0x180008367  mov     eax, ebx
0x180008369  lea     r11, [rsp+70h+var_s0]
0x18000836e  mov     rbx, [r11+38h]
0x180008372  mov     rsi, [r11+40h]
0x180008376  mov     rsp, r11
0x180008379  pop     r15
0x18000837b  pop     r14
0x18000837d  pop     r12
0x18000837f  pop     rdi
0x180008380  pop     rbp
0x180008381  retn
```
