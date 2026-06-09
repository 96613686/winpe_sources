# GetExtensionVersion

- ea: `0x18000d1e0`
- end: `0x18000d3d5`
- name: `GetExtensionVersion`
- size: `501`
- prototype: `BOOL __stdcall(HSE_VERSION_INFO *pVer)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000d1e0`
- `0x18000dbb4`
- `0x18000e6e4`
- `0x18000ecf8`
- `0x18000f5f0`

## import_xrefs

- `msvcrt!free` at `0x18000d26c`
- `msvcrt!free` at `0x18000d29f`
- `msvcrt!free` at `0x18000d26c`
- `msvcrt!free` at `0x18000d29f`
- `mqsec!?GetFalconSectionName@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@Z` at `0x18000d225`
- `mqsec!?GetFalconSectionName@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@Z` at `0x18000d225`

## string_xrefs

- `0x18000d2ac`: `MSMQ ISAPI extension`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __stdcall GetExtensionVersion(HSE_VERSION_INFO *pVer)
{
  int FalconSectionName; // eax
  HKEY v3; // rcx
  unsigned int v4; // r8d
  const wchar_t *v6; // rdx
  __int64 v7; // rax
  CHAR *v8; // r8
  __int64 v9; // rcx
  CHAR *lpszExtensionDesc; // rdx
  CHAR v11; // r9
  CHAR *v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // [rsp+20h] [rbp-40h] BYREF
  _BYTE Block[24]; // [rsp+28h] [rbp-38h] BYREF
  __int64 v16; // [rsp+40h] [rbp-20h]
  unsigned __int64 v17; // [rsp+48h] [rbp-18h]

  if ( !byte_180017D18 )
  {
    v17 = 7;
    v16 = 0;
    *(_WORD *)&Block[8] = 0;
    FalconSectionName = GetFalconSectionName(Block);
    if ( FalconSectionName < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          10,
          &WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids,
          (unsigned int)FalconSectionName);
      if ( v17 >= 8 )
        free(*(void **)&Block[8]);
      return 0;
    }
    v6 = (const wchar_t *)&Block[8];
    if ( v17 >= 8 )
      v6 = *(const wchar_t **)&Block[8];
    CmInitialize(v3, v6, v4);
    byte_180017D18 = 1;
    if ( v17 >= 8 )
      free(*(void **)&Block[8]);
  }
  pVer->dwExtensionVersion = 0x80000;
  strcpy(Block, "MSMQ ISAPI extension");
  v7 = 2147483646;
  v8 = Block;
  v9 = 256;
  lpszExtensionDesc = pVer->lpszExtensionDesc;
  do
  {
    if ( !v7 )
      break;
    v11 = *v8;
    if ( !*v8 )
      break;
    ++v8;
    *lpszExtensionDesc++ = v11;
    --v7;
    --v9;
  }
  while ( v9 );
  v12 = lpszExtensionDesc - 1;
  if ( v9 )
    v12 = lpszExtensionDesc;
  *v12 = 0;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        11,
        &WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids,
        v9 == 0 ? 0x8007007A : 0);
    return 0;
  }
  *(_DWORD *)Block = 0;
  *(_QWORD *)&Block[8] = 0;
  *(_QWORD *)&Block[16] = L"MaxMemoryPercentageAllowed";
  LODWORD(v16) = 0;
  v17 = 0;
  v14 = 0;
  QueryValueInternal(Block, 4, &v14, 4);
  v13 = v14;
  if ( v14 )
  {
    if ( v14 > 0x64 )
      v13 = 100;
    if ( v13 < 0xA )
      v13 = 10;
    s_dwMemLoadAllowed = v13;
  }
  return 1;
}

```

## disassembly

```asm
0x18000d1e0  mov     [rsp-8+arg_8], rbx
0x18000d1e5  push    rbp
0x18000d1e6  mov     rbp, rsp
0x18000d1e9  sub     rsp, 60h
0x18000d1ed  mov     rax, cs:__security_cookie
0x18000d1f4  xor     rax, rsp
0x18000d1f7  mov     [rbp+var_10], rax
0x18000d1fb  mov     rbx, rcx
0x18000d1fe  cmp     cs:byte_180017D18, 0
0x18000d205  jnz     loc_18000D2A6
0x18000d20b  mov     [rbp+var_18], 7
0x18000d213  mov     [rbp+var_20], 0
0x18000d21b  xor     eax, eax
0x18000d21d  mov     word ptr [rbp+Block+8], ax
0x18000d221  lea     rcx, [rbp+Block]
0x18000d225  call    cs:__imp_?GetFalconSectionName@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@Z; GetFalconSectionName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> &)
0x18000d22b  mov     r9d, eax
0x18000d22e  test    eax, eax
0x18000d230  jns     short loc_18000D27A
0x18000d232  lea     rax, WPP_GLOBAL_Control
0x18000d239  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d240  cmp     rcx, rax
0x18000d243  jz      short loc_18000D261
0x18000d245  test    byte ptr [rcx+6Ch], 1
0x18000d249  jz      short loc_18000D261
0x18000d24b  mov     edx, 0Ah
0x18000d250  lea     r8, WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids
0x18000d257  mov     rcx, [rcx+60h]
0x18000d25b  call    WPP_SF_d
0x18000d260  nop
0x18000d261  cmp     [rbp+var_18], 8
0x18000d266  jb      short loc_18000D273
0x18000d268  mov     rcx, [rbp+Block+8]; Block
0x18000d26c  call    cs:__imp_free
0x18000d272  nop
0x18000d273  xor     eax, eax
0x18000d275  jmp     loc_18000D3BE
0x18000d27a  lea     rdx, [rbp+Block+8]
0x18000d27e  cmp     [rbp+var_18], 8
0x18000d283  cmovnb  rdx, [rbp+Block+8]; wchar_t *
0x18000d288  call    ?CmInitialize@@YAXPEAUHKEY__@@PEB_WK@Z; CmInitialize(HKEY__ *,wchar_t const *,ulong)
0x18000d28d  mov     cs:byte_180017D18, 1
0x18000d294  cmp     [rbp+var_18], 8
0x18000d299  jb      short loc_18000D2A6
0x18000d29b  mov     rcx, [rbp+Block+8]; Block
0x18000d29f  call    cs:__imp_free
0x18000d2a5  nop
0x18000d2a6  mov     dword ptr [rbx], 80000h
0x18000d2ac  movups  xmm0, xmmword ptr cs:aMsmqIsapiExten; "MSMQ ISAPI extension"
0x18000d2b3  movups  xmmword ptr [rbp+Block], xmm0
0x18000d2b7  movsd   xmm1, qword ptr cs:aMsmqIsapiExten+0Dh; "tension"
0x18000d2bf  movsd   [rbp+Block+0Dh], xmm1
0x18000d2c4  mov     eax, 7FFFFFFEh
0x18000d2c9  lea     r8, [rbp+Block]
0x18000d2cd  mov     ecx, 100h
0x18000d2d2  lea     rdx, [rbx+4]
0x18000d2d6  test    rax, rax
0x18000d2d9  jz      short loc_18000D2F5
0x18000d2db  mov     r9b, [r8]
0x18000d2de  test    r9b, r9b
0x18000d2e1  jz      short loc_18000D2F5
0x18000d2e3  inc     r8
0x18000d2e6  mov     [rdx], r9b
0x18000d2e9  inc     rdx
0x18000d2ec  dec     rax
0x18000d2ef  sub     rcx, 1
0x18000d2f3  jnz     short loc_18000D2D6
0x18000d2f5  mov     rax, rcx
0x18000d2f8  neg     rax
0x18000d2fb  sbb     r9d, r9d
0x18000d2fe  not     r9d
0x18000d301  and     r9d, 8007007Ah
0x18000d308  lea     rax, [rdx-1]
0x18000d30c  test    rcx, rcx
0x18000d30f  cmovnz  rax, rdx
0x18000d313  mov     byte ptr [rax], 0
0x18000d316  jnz     short loc_18000D353
0x18000d318  lea     rax, WPP_GLOBAL_Control
0x18000d31f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d326  cmp     rcx, rax
0x18000d329  jz      loc_18000D273
0x18000d32f  test    byte ptr [rcx+6Ch], 1
0x18000d333  jz      loc_18000D273
0x18000d339  mov     edx, 0Bh
0x18000d33e  lea     r8, WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids
0x18000d345  mov     rcx, [rcx+60h]
0x18000d349  call    WPP_SF_d
0x18000d34e  jmp     loc_18000D273
0x18000d353  mov     dword ptr [rbp+Block], 0
0x18000d35a  mov     [rbp+Block+8], 0
0x18000d362  lea     rax, aMaxmemoryperce; "MaxMemoryPercentageAllowed"
0x18000d369  mov     [rbp+var_28], rax
0x18000d36d  mov     dword ptr [rbp+var_20], 0
0x18000d374  mov     [rbp+var_18], 0
0x18000d37c  mov     [rbp+var_40], 0
0x18000d383  mov     edx, 4
0x18000d388  mov     r9d, edx
0x18000d38b  lea     r8, [rbp+var_40]
0x18000d38f  lea     rcx, [rbp+Block]
0x18000d393  call    QueryValueInternal
0x18000d398  mov     eax, [rbp+var_40]
0x18000d39b  test    eax, eax
0x18000d39d  jz      short loc_18000D3B9
0x18000d39f  cmp     eax, 64h ; 'd'
0x18000d3a2  jbe     short loc_18000D3A9
0x18000d3a4  mov     eax, 64h ; 'd'
0x18000d3a9  cmp     eax, 0Ah
0x18000d3ac  jnb     short loc_18000D3B3
0x18000d3ae  mov     eax, 0Ah
0x18000d3b3  mov     cs:?s_dwMemLoadAllowed@@3KA, eax; ulong s_dwMemLoadAllowed
0x18000d3b9  mov     eax, 1
0x18000d3be  mov     rcx, [rbp+var_10]
0x18000d3c2  xor     rcx, rsp; StackCookie
0x18000d3c5  call    __security_check_cookie
0x18000d3ca  mov     rbx, [rsp+60h+arg_8]
0x18000d3cf  add     rsp, 60h
0x18000d3d3  pop     rbp
0x18000d3d4  retn
```
