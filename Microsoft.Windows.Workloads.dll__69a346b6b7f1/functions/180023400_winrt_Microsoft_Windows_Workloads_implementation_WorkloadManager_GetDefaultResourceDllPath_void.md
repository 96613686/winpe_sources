# winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::GetDefaultResourceDllPath(void)

- ea: `0x180023400`
- end: `0x18002361c`
- name: `?GetDefaultResourceDllPath@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `540`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d220`
- `0x18001eb00`

## callees

- `0x1800027d0`
- `0x1800029f0`
- `0x180003db0`
- `0x18001b340`
- `0x18001b430`
- `0x18001b800`
- `0x18001c040`
- `0x180023400`
- `0x180034ef0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18002347d`
- `KERNEL32!GetModuleHandleW` at `0x18002347d`

## string_xrefs

- `0x180023438`: `Microsoft.Windows.Workloads.Resources_ec.dll`
- `0x18002343f`: `Microsoft.Windows.Workloads.Resources.dll`
- `0x180023476`: `Microsoft.Windows.Workloads.dll`

## pseudocode

```c
__int64 __fastcall winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::GetDefaultResourceDllPath(
        __int64 a1)
{
  bool v2; // al
  const wchar_t *v3; // rdx
  unsigned __int64 v4; // r8
  HMODULE ModuleHandleW; // rax
  __int64 v6; // rax
  __int128 *v7; // rdx
  const wchar_t *v8; // r8
  std::filesystem *v9; // rsi
  const wchar_t *v10; // rbx
  const wchar_t *root_name_end; // rax
  const wchar_t *v12; // rcx
  __int16 v13; // dx
  const wchar_t *v14; // rcx
  __int16 v15; // dx
  std::filesystem *v16; // rax
  __int128 v18; // [rsp+30h] [rbp-89h] BYREF
  __int64 v19; // [rsp+40h] [rbp-79h]
  __int64 v20; // [rsp+48h] [rbp-71h]
  __int128 v21; // [rsp+50h] [rbp-69h] BYREF
  __int64 v22; // [rsp+60h] [rbp-59h]
  __int64 v23; // [rsp+68h] [rbp-51h]
  _BYTE v24[32]; // [rsp+70h] [rbp-49h] BYREF
  _BYTE Src[32]; // [rsp+90h] [rbp-29h] BYREF
  std::filesystem *v26[2]; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v27; // [rsp+C0h] [rbp+7h]
  __int128 v28; // [rsp+D0h] [rbp+17h] BYREF
  __int128 v29; // [rsp+E0h] [rbp+27h]

  v2 = IsRunningOnArm64();
  v3 = L"Microsoft.Windows.Workloads.Resources.dll";
  if ( v2 )
    v3 = L"Microsoft.Windows.Workloads.Resources_ec.dll";
  v28 = 0;
  v29 = 0;
  v4 = -1;
  do
    ++v4;
  while ( v3[v4] );
  std::wstring::_Construct<1,wchar_t const *>(&v28, v3, v4);
  ModuleHandleW = GetModuleHandleW(L"Microsoft.Windows.Workloads.dll");
  v6 = wil::GetModuleFileNameW<std::wstring,128>((__int64)v24, (__int64)ModuleHandleW);
  *(_OWORD *)v26 = 0;
  v27 = 0;
  *(_OWORD *)v26 = *(_OWORD *)v6;
  v27 = *(_OWORD *)(v6 + 16);
  *(_QWORD *)(v6 + 16) = 0;
  *(_QWORD *)(v6 + 24) = 7;
  *(_WORD *)v6 = 0;
  std::wstring::_Tidy_deallocate((__int64)v24);
  v7 = &v28;
  if ( *((_QWORD *)&v29 + 1) > 7u )
    v7 = (__int128 *)v28;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v21, v7, v29);
  v9 = (std::filesystem *)v26;
  if ( *((_QWORD *)&v27 + 1) > 7u )
    v9 = v26[0];
  v10 = (const wchar_t *)((char *)v9 + 2 * v27);
  root_name_end = std::filesystem::_Find_root_name_end(v9, v10, v8);
  if ( root_name_end != v10 )
  {
    do
    {
      if ( *root_name_end != 92 && *root_name_end != 47 )
        break;
      ++root_name_end;
    }
    while ( root_name_end != v10 );
    if ( root_name_end != v10 )
    {
      while ( 1 )
      {
        v12 = v10 - 1;
        v13 = *(v10 - 1);
        if ( v13 == 92 || v13 == 47 )
          break;
        --v10;
        if ( root_name_end == v12 )
          goto LABEL_22;
      }
      if ( root_name_end != v10 )
      {
        do
        {
          v14 = v10 - 1;
          v15 = *(v10 - 1);
          if ( v15 != 92 && v15 != 47 )
            break;
          --v10;
        }
        while ( root_name_end != v14 );
      }
    }
  }
LABEL_22:
  v18 = 0;
  v19 = 0;
  v20 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v18, v9, ((char *)v10 - (char *)v9) >> 1);
  v16 = std::filesystem::operator/((std::filesystem *)Src, &v18, &v21);
  std::wstring::wstring(a1, v16);
  std::wstring::_Tidy_deallocate((__int64)Src);
  std::wstring::_Tidy_deallocate((__int64)&v18);
  std::wstring::_Tidy_deallocate((__int64)&v21);
  std::wstring::_Tidy_deallocate((__int64)v26);
  std::wstring::_Tidy_deallocate((__int64)&v28);
  return a1;
}

```

## disassembly

```asm
0x180023400  mov     [rsp-8+arg_8], rbx
0x180023405  mov     [rsp-8+arg_10], rsi
0x18002340a  push    rbp
0x18002340b  push    rdi
0x18002340c  push    r14
0x18002340e  lea     rbp, [rsp-47h]
0x180023413  sub     rsp, 100h
0x18002341a  mov     rax, cs:__security_cookie
0x180023421  xor     rax, rsp
0x180023424  mov     [rbp+57h+var_20], rax
0x180023428  mov     rdi, rcx
0x18002342b  mov     [rsp+110h+var_F0], rcx
0x180023430  xor     r14d, r14d
0x180023433  call    ?IsRunningOnArm64@@YA_NXZ; IsRunningOnArm64(void)
0x180023438  lea     rcx, aMicrosoftWindo_0; "Microsoft.Windows.Workloads.Resources_e"...
0x18002343f  lea     rdx, aMicrosoftWindo_21; "Microsoft.Windows.Workloads.Resources.d"...
0x180023446  test    al, al
0x180023448  cmovnz  rdx, rcx
0x18002344c  xorps   xmm0, xmm0
0x18002344f  movups  [rbp+57h+var_40], xmm0
0x180023453  xorps   xmm1, xmm1
0x180023456  movdqu  [rbp+57h+var_30], xmm1
0x18002345b  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180023462  inc     r8
0x180023465  cmp     [rdx+r8*2], r14w
0x18002346a  jnz     short loc_180023462
0x18002346c  lea     rcx, [rbp+57h+var_40]
0x180023470  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180023475  nop
0x180023476  lea     rcx, aMicrosoftWindo_26; "Microsoft.Windows.Workloads.dll"
0x18002347d  call    cs:__imp_GetModuleHandleW
0x180023483  mov     rdx, rax
0x180023486  lea     rcx, [rbp+57h+var_A0]
0x18002348a  call    ??$GetModuleFileNameW@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0IA@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@@Z; wil::GetModuleFileNameW<std::wstring,128>(HINSTANCE__ *)
0x18002348f  xorps   xmm0, xmm0
0x180023492  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180023496  xorps   xmm1, xmm1
0x180023499  movdqu  [rbp+57h+var_50], xmm1
0x18002349e  movups  xmm0, xmmword ptr [rax]
0x1800234a1  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800234a5  movups  xmm1, xmmword ptr [rax+10h]
0x1800234a9  movups  [rbp+57h+var_50], xmm1
0x1800234ad  mov     [rax+10h], r14
0x1800234b1  mov     qword ptr [rax+18h], 7
0x1800234b9  mov     [rax], r14w
0x1800234bd  lea     rcx, [rbp+57h+var_A0]
0x1800234c1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800234c6  lea     rdx, [rbp+57h+var_40]
0x1800234ca  cmp     qword ptr [rbp+57h+var_30+8], 7
0x1800234cf  cmova   rdx, qword ptr [rbp+57h+var_40]
0x1800234d4  xorps   xmm0, xmm0
0x1800234d7  movups  [rbp+57h+var_C0], xmm0
0x1800234db  mov     [rbp+57h+var_B0], r14
0x1800234df  mov     [rbp+57h+var_A8], r14
0x1800234e3  mov     r8, qword ptr [rbp+57h+var_30]
0x1800234e7  lea     rcx, [rbp+57h+var_C0]
0x1800234eb  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800234f0  nop
0x1800234f1  lea     rsi, [rbp+57h+var_60]
0x1800234f5  cmp     qword ptr [rbp+57h+var_50+8], 7
0x1800234fa  cmova   rsi, [rbp+57h+var_60]
0x1800234ff  mov     rax, qword ptr [rbp+57h+var_50]
0x180023503  lea     rbx, [rsi+rax*2]
0x180023507  mov     rdx, rbx; wchar_t *
0x18002350a  mov     rcx, rsi; this
0x18002350d  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x180023512  cmp     rax, rbx
0x180023515  jz      short loc_18002357D
0x180023517  movzx   ecx, word ptr [rax]
0x18002351a  cmp     cx, 5Ch ; '\'
0x18002351e  jz      short loc_180023526
0x180023520  cmp     cx, 2Fh ; '/'
0x180023524  jnz     short loc_18002352F
0x180023526  add     rax, 2
0x18002352a  cmp     rax, rbx
0x18002352d  jnz     short loc_180023517
0x18002352f  cmp     rax, rbx
0x180023532  jz      short loc_18002357D
0x180023534  nop     dword ptr [rax+00h]
0x180023538  nop     dword ptr [rax+rax+00000000h]
0x180023540  lea     rcx, [rbx-2]
0x180023544  movzx   edx, word ptr [rcx]
0x180023547  cmp     dx, 5Ch ; '\'
0x18002354b  jz      short loc_18002355D
0x18002354d  cmp     dx, 2Fh ; '/'
0x180023551  jz      short loc_18002355D
0x180023553  mov     rbx, rcx
0x180023556  cmp     rax, rcx
0x180023559  jnz     short loc_180023540
0x18002355b  jmp     short loc_18002357D
0x18002355d  cmp     rax, rbx
0x180023560  jz      short loc_18002357D
0x180023562  lea     rcx, [rbx-2]
0x180023566  movzx   edx, word ptr [rcx]
0x180023569  cmp     dx, 5Ch ; '\'
0x18002356d  jz      short loc_180023575
0x18002356f  cmp     dx, 2Fh ; '/'
0x180023573  jnz     short loc_18002357D
0x180023575  mov     rbx, rcx
0x180023578  cmp     rax, rcx
0x18002357b  jnz     short loc_180023562
0x18002357d  sub     rbx, rsi
0x180023580  sar     rbx, 1
0x180023583  xorps   xmm0, xmm0
0x180023586  movups  [rsp+110h+var_E0], xmm0
0x18002358b  mov     [rbp+57h+var_D0], r14
0x18002358f  mov     [rbp+57h+var_C8], r14
0x180023593  mov     r8, rbx
0x180023596  mov     rdx, rsi
0x180023599  lea     rcx, [rsp+110h+var_E0]
0x18002359e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800235a3  nop
0x1800235a4  lea     r8, [rbp+57h+var_C0]; void *
0x1800235a8  lea     rdx, [rsp+110h+var_E0]; void *
0x1800235ad  lea     rcx, [rbp+57h+Src]; Src
0x1800235b1  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800235b6  nop
0x1800235b7  mov     rdx, rax
0x1800235ba  mov     rcx, rdi
0x1800235bd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800235c2  nop
0x1800235c3  lea     rcx, [rbp+57h+Src]
0x1800235c7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800235cc  nop
0x1800235cd  lea     rcx, [rsp+110h+var_E0]
0x1800235d2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800235d7  nop
0x1800235d8  lea     rcx, [rbp+57h+var_C0]
0x1800235dc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800235e1  nop
0x1800235e2  lea     rcx, [rbp+57h+var_60]
0x1800235e6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800235eb  nop
0x1800235ec  lea     rcx, [rbp+57h+var_40]
0x1800235f0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800235f5  mov     rax, rdi
0x1800235f8  mov     rcx, [rbp+57h+var_20]
0x1800235fc  xor     rcx, rsp; StackCookie
0x1800235ff  call    __security_check_cookie
0x180023604  lea     r11, [rsp+110h+var_10]
0x18002360c  mov     rbx, [r11+28h]
0x180023610  mov     rsi, [r11+30h]
0x180023614  mov     rsp, r11
0x180023617  pop     r14
0x180023619  pop     rdi
0x18002361a  pop     rbp
0x18002361b  retn
```
