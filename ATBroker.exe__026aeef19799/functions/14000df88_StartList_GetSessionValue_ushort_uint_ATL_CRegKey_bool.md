# StartList::GetSessionValue(ushort *,uint,ATL::CRegKey &,bool)

- ea: `0x14000df88`
- end: `0x14000e0b7`
- name: `?GetSessionValue@StartList@@AEBAXPEAGIAEAVCRegKey@ATL@@_N@Z`
- size: `303`
- prototype: `void __fastcall(StartList *this, unsigned __int16 *, unsigned int, HKEY *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000d3a0`
- `0x14000ee8c`

## callees

- `0x140007708`
- `0x14000df88`
- `0x1400111c0`
- `0x140015830`
- `0x140017010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000dfd8`
- `ADVAPI32!RegOpenKeyExW` at `0x14000dfd8`
- `ADVAPI32!RegCloseKey` at `0x14000dfec`
- `ADVAPI32!RegCloseKey` at `0x14000dfec`

## string_xrefs

- `0x14000e05e`: `SecureConfiguration`
- `0x14000e057`: `Configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall StartList::GetSessionValue(StartList *this, unsigned __int16 *a2, unsigned int a3, HKEY *a4, bool a5)
{
  LPCWSTR *v7; // rax
  unsigned int v8; // ebx
  __int64 v9; // r8
  _QWORD *v10; // rdx
  const unsigned __int16 *v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // r8
  HKEY phkResult; // [rsp+50h] [rbp+8h] BYREF
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v16; // [rsp+60h] [rbp+18h] BYREF

  v16 = a3;
  phkResult = (HKEY)this;
  *a2 = 0;
  v7 = (LPCWSTR *)CATUtils::SessionKeyString((__int64)&v15);
  phkResult = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, *v7, 0, 0x2001Fu, &phkResult);
  if ( !v8 )
  {
    if ( *a4 )
      v8 = RegCloseKey(*a4);
    *a4 = phkResult;
  }
  v10 = (_QWORD *)(v15 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
  if ( v8 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, v9, v8);
  v16 = 1024;
  v11 = L"SecureConfiguration";
  if ( !a5 )
    v11 = L"Configuration";
  v12 = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)a4, v11, a2, &v16);
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, v13, v12);
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x14000df88  mov     r11, rsp
0x14000df8b  mov     [r11+20h], rbx
0x14000df8f  mov     [r11+18h], r8d
0x14000df93  mov     [r11+8], rcx
0x14000df97  push    rbp
0x14000df98  push    rsi
0x14000df99  push    rdi
0x14000df9a  sub     rsp, 30h
0x14000df9e  mov     rdi, r9
0x14000dfa1  mov     rsi, rdx
0x14000dfa4  xor     eax, eax
0x14000dfa6  mov     [rdx], ax
0x14000dfa9  lea     rcx, [r11+10h]
0x14000dfad  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x14000dfb2  mov     [rsp+48h+arg_0], 0
0x14000dfbb  lea     rcx, [rsp+48h+arg_0]
0x14000dfc0  mov     [rsp+48h+phkResult], rcx; phkResult
0x14000dfc5  mov     r9d, 2001Fh; samDesired
0x14000dfcb  xor     r8d, r8d; ulOptions
0x14000dfce  mov     rdx, [rax]; lpSubKey
0x14000dfd1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000dfd8  call    cs:__imp_RegOpenKeyExW
0x14000dfde  mov     ebx, eax
0x14000dfe0  test    eax, eax
0x14000dfe2  jnz     short loc_14000DFFC
0x14000dfe4  mov     rcx, [rdi]; hKey
0x14000dfe7  test    rcx, rcx
0x14000dfea  jz      short loc_14000DFF4
0x14000dfec  call    cs:__imp_RegCloseKey
0x14000dff2  mov     ebx, eax
0x14000dff4  mov     rax, [rsp+48h+arg_0]
0x14000dff9  mov     [rdi], rax
0x14000dffc  mov     rdx, [rsp+48h+arg_8]
0x14000e001  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000e005  or      eax, 0FFFFFFFFh
0x14000e008  lock xadd [rdx+10h], eax
0x14000e00d  sub     eax, 1
0x14000e010  jg      short loc_14000E021
0x14000e012  mov     rcx, [rdx]
0x14000e015  mov     rax, [rcx]
0x14000e018  mov     rax, [rax+8]
0x14000e01c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e021  lea     rbp, WPP_GLOBAL_Control
0x14000e028  test    ebx, ebx
0x14000e02a  jz      short loc_14000E04F
0x14000e02c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e033  cmp     rcx, rbp
0x14000e036  jz      short loc_14000E04F
0x14000e038  test    byte ptr [rcx+1Ch], 8
0x14000e03c  jz      short loc_14000E04F
0x14000e03e  mov     edx, 20h ; ' '
0x14000e043  mov     r9d, ebx
0x14000e046  mov     rcx, [rcx+10h]
0x14000e04a  call    WPP_SF_d
0x14000e04f  mov     [rsp+48h+arg_10], 400h
0x14000e057  lea     rax, aConfiguration_0; "Configuration"
0x14000e05e  lea     rdx, aSecureconfigur; "SecureConfiguration"
0x14000e065  cmp     [rsp+48h+arg_20], 0
0x14000e06a  cmovz   rdx, rax; unsigned __int16 *
0x14000e06e  lea     r9, [rsp+48h+arg_10]; unsigned int *
0x14000e073  mov     r8, rsi; unsigned __int16 *
0x14000e076  mov     rcx, rdi; this
0x14000e079  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14000e07e  test    eax, eax
0x14000e080  jz      short loc_14000E0AA
0x14000e082  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e089  cmp     rcx, rbp
0x14000e08c  jz      short loc_14000E0A5
0x14000e08e  test    byte ptr [rcx+1Ch], 8
0x14000e092  jz      short loc_14000E0A5
0x14000e094  mov     edx, 21h ; '!'
0x14000e099  mov     r9d, eax
0x14000e09c  mov     rcx, [rcx+10h]
0x14000e0a0  call    WPP_SF_d
0x14000e0a5  xor     eax, eax
0x14000e0a7  mov     [rsi], ax
0x14000e0aa  mov     rbx, [rsp+48h+arg_18]
0x14000e0af  add     rsp, 30h
0x14000e0b3  pop     rdi
0x14000e0b4  pop     rsi
0x14000e0b5  pop     rbp
0x14000e0b6  retn
```
