# SettingsCopier::CopyATSettings(ATL::CRegKey &,ATL::CRegKey &)

- ea: `0x140011c60`
- end: `0x140011f00`
- name: `?CopyATSettings@SettingsCopier@@AEAAJAEAVCRegKey@ATL@@0@Z`
- size: `672`
- prototype: `__int64 __fastcall(SettingsCopier *this, HKEY *, struct ATL::CRegKey *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012640`
- `0x14001271c`

## callees

- `0x140006a78`
- `0x140009384`
- `0x14000ab98`
- `0x14000bf04`
- `0x140011c60`
- `0x140011f08`
- `0x140012340`
- `0x140012ae8`
- `0x140015b00`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140011d8b`
- `msvcrt!_wcsnicmp` at `0x140011d8b`
- `msvcrt!free` at `0x140011dd3`
- `msvcrt!free` at `0x140011e5c`
- `msvcrt!free` at `0x140011ec1`
- `msvcrt!free` at `0x140011dd3`
- `msvcrt!free` at `0x140011e5c`
- `msvcrt!free` at `0x140011ec1`

## string_xrefs

- `0x140011cb1`: `enduser\ezap\easeofaccess\atmanager\settingscopier.cpp`

## pseudocode

```c
__int64 __fastcall SettingsCopier::CopyATSettings(SettingsCopier *this, HKEY *a2, struct ATL::CRegKey *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v9; // rcx
  _QWORD *v10; // r15
  __int64 v11; // r14
  int v12; // edi
  int RegKeyValue; // eax
  unsigned int v14; // esi
  int *v15; // rbx
  const wchar_t *v16; // rdx
  __int64 v17; // r8
  BYTE *v18; // rbx
  int v19; // eax
  BYTE *v20; // rcx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  DWORD lpData; // [rsp+20h] [rbp-E0h]
  DWORD dwType[2]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *v26[7]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t String1[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v6 = SettingsCopier::DeleteATSettings(a3);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"enduser\\ezap\\easeofaccess\\atmanager\\settingscopier.cpp",
      (const char *)(unsigned int)v6,
      lpData);
    return v7;
  }
  v9 = *(_QWORD **)ATManager::GetAccommodations(*(_QWORD *)this);
  if ( !v9 )
    return 0;
  do
  {
    v10 = (_QWORD *)*v9;
    v11 = v9[2];
    if ( !*(_DWORD *)(v11 + 68) )
      goto LABEL_34;
    memset(&v26[1], 0, 48);
    v12 = 0;
    while ( 1 )
    {
      dwType[1] = 0;
      dwType[0] = 0;
      v26[0] = 0;
      RegKeyValue = SettingsCopier::GetRegKeyValue(
                      *a2,
                      *(LPCWSTR *)v11,
                      lpData,
                      (__int64)&dwType[1],
                      (__int64)v26,
                      (__int64)dwType);
      v14 = RegKeyValue;
      if ( RegKeyValue == 1 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_33;
        v22 = 10;
        v23 = 1;
        goto LABEL_32;
      }
      if ( RegKeyValue < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_33;
        v22 = 11;
        v23 = (unsigned int)RegKeyValue;
LABEL_32:
        WPP_SF_D(v21[2], v22, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids, v23);
LABEL_33:
        free(v26[0]);
        goto LABEL_34;
      }
      if ( !IsInteractiveUser() )
      {
        v15 = (int *)off_1400180E0;
        while ( 1 )
        {
          v16 = *(const wchar_t **)v15;
          v17 = -1;
          do
            ++v17;
          while ( v16[v17] );
          if ( !_wcsnicmp(String1, v16, v17 + 1) )
            break;
          v15 += 2;
          if ( v15 == &load_config_used )
            goto LABEL_14;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids, v14);
        v20 = v26[0];
        goto LABEL_16;
      }
LABEL_14:
      v18 = v26[0];
      v19 = SettingsCopier::SetRegKeyValue(*(HKEY *)a3, *(LPCWSTR *)v11, String1, dwType[1], v26[0], dwType[0]);
      if ( v19 < 0 )
        break;
      v20 = v18;
LABEL_16:
      free(v20);
      if ( (unsigned int)++v12 > 0x64 )
        goto LABEL_34;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids,
        (unsigned int)v19);
    free(v18);
LABEL_34:
    v9 = v10;
  }
  while ( v10 );
  return 0;
}

```

## disassembly

```asm
0x140011c60  mov     [rsp-8+arg_18], rbx
0x140011c65  push    rbp
0x140011c66  push    rsi
0x140011c67  push    rdi
0x140011c68  push    r12
0x140011c6a  push    r13
0x140011c6c  push    r14
0x140011c6e  push    r15
0x140011c70  lea     rbp, [rsp-1A0h]
0x140011c78  sub     rsp, 2A0h
0x140011c7f  mov     rax, cs:__security_cookie
0x140011c86  xor     rax, rsp
0x140011c89  mov     [rbp+1D0h+var_40], rax
0x140011c90  mov     r12, r8
0x140011c93  mov     r13, rdx
0x140011c96  mov     rdi, rcx
0x140011c99  mov     rcx, r8; struct ATL::CRegKey *
0x140011c9c  call    ?DeleteATSettings@SettingsCopier@@CAJAEAVCRegKey@ATL@@@Z; SettingsCopier::DeleteATSettings(ATL::CRegKey &)
0x140011ca1  mov     ebx, eax
0x140011ca3  test    eax, eax
0x140011ca5  jns     short loc_140011CC9
0x140011ca7  mov     rcx, [rbp+1D8h]; this
0x140011cae  mov     r9d, eax; char *
0x140011cb1  lea     r8, aEnduserEzapEas; "enduser\\ezap\\easeofaccess\\atmanager"...
0x140011cb8  mov     edx, 1FCh; void *
0x140011cbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011cc2  mov     eax, ebx
0x140011cc4  jmp     loc_140011ED6
0x140011cc9  mov     rcx, [rdi]
0x140011ccc  call    ?GetAccommodations@ATManager@@QEAAAEBV?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@XZ; ATManager::GetAccommodations(void)
0x140011cd1  mov     rcx, [rax]
0x140011cd4  xor     ebx, ebx
0x140011cd6  test    rcx, rcx
0x140011cd9  jz      loc_140011ED4
0x140011cdf  mov     r15, [rcx]
0x140011ce2  mov     r14, [rcx+10h]
0x140011ce6  cmp     [r14+44h], ebx
0x140011cea  jz      loc_140011EC8
0x140011cf0  mov     [rsp+2D0h+var_280], rbx
0x140011cf5  mov     [rsp+2D0h+var_278], rbx
0x140011cfa  mov     [rsp+2D0h+var_270], rbx
0x140011cff  mov     [rsp+2D0h+var_268], rbx
0x140011d04  mov     [rsp+2D0h+var_260], rbx
0x140011d09  mov     [rsp+2D0h+var_258], rbx
0x140011d0e  mov     edi, ebx
0x140011d10  mov     [rsp+2D0h+dwType+4], ebx
0x140011d14  mov     [rsp+2D0h+dwType], ebx
0x140011d18  mov     [rsp+2D0h+var_288], rbx
0x140011d1d  lea     rax, [rsp+2D0h+dwType]
0x140011d22  mov     [rsp+2D0h+var_298], rax; __int64
0x140011d27  lea     rax, [rsp+2D0h+var_288]
0x140011d2c  mov     [rsp+2D0h+var_2A0], rax; __int64
0x140011d31  lea     rax, [rsp+2D0h+dwType+4]
0x140011d36  mov     qword ptr [rsp+2D0h+var_2A8], rax; __int64
0x140011d3b  lea     r9, [rbp+1D0h+String1]
0x140011d3f  mov     r8d, edi
0x140011d42  mov     rdx, [r14]; lpSubKey
0x140011d45  mov     rcx, [r13+0]; hKey
0x140011d49  call    ?GetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBGKPEAGKPEAKAEAV?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@3@Z; SettingsCopier::GetRegKeyValue(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong *,ATL::CHeapPtr<uchar,ATL::CCRTAllocator> &,ulong *)
0x140011d4e  mov     esi, eax
0x140011d50  cmp     eax, 1
0x140011d53  jz      loc_140011E89
0x140011d59  test    eax, eax
0x140011d5b  js      loc_140011E66
0x140011d61  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x140011d66  test    eax, eax
0x140011d68  jnz     short loc_140011DA5
0x140011d6a  lea     rbx, off_1400180E0; "StartExe"
0x140011d71  mov     rdx, [rbx]; String2
0x140011d74  or      r8, 0FFFFFFFFFFFFFFFFh
0x140011d78  xor     eax, eax
0x140011d7a  inc     r8
0x140011d7d  cmp     [rdx+r8*2], ax
0x140011d82  jnz     short loc_140011D7A
0x140011d84  inc     r8; MaxCount
0x140011d87  lea     rcx, [rbp+1D0h+String1]; String1
0x140011d8b  call    cs:__imp__wcsnicmp
0x140011d91  test    eax, eax
0x140011d93  jz      short loc_140011DEE
0x140011d95  add     rbx, 8
0x140011d99  lea     rax, _load_config_used
0x140011da0  cmp     rbx, rax
0x140011da3  jnz     short loc_140011D71
0x140011da5  mov     eax, [rsp+2D0h+dwType]
0x140011da9  mov     [rsp+2D0h+var_2A8], eax; DWORD
0x140011dad  mov     rbx, [rsp+2D0h+var_288]
0x140011db2  mov     [rsp+2D0h+lpData], rbx; lpData
0x140011db7  mov     r9d, [rsp+2D0h+dwType+4]; dwType
0x140011dbc  lea     r8, [rbp+1D0h+String1]; lpValueName
0x140011dc0  mov     rdx, [r14]; lpSubKey
0x140011dc3  mov     rcx, [r12]; hKey
0x140011dc7  call    ?SetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBG1KPEBEK@Z; SettingsCopier::SetRegKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar const *,ulong)
0x140011dcc  test    eax, eax
0x140011dce  js      short loc_140011E27
0x140011dd0  mov     rcx, rbx; Block
0x140011dd3  call    cs:__imp_free
0x140011dd9  inc     edi
0x140011ddb  cmp     edi, 64h ; 'd'
0x140011dde  mov     ebx, 0
0x140011de3  jbe     loc_140011D10
0x140011de9  jmp     loc_140011EC8
0x140011dee  mov     rcx, cs:WPP_GLOBAL_Control
0x140011df5  lea     rax, WPP_GLOBAL_Control
0x140011dfc  cmp     rcx, rax
0x140011dff  jz      short loc_140011E20
0x140011e01  test    byte ptr [rcx+1Ch], 10h
0x140011e05  jz      short loc_140011E20
0x140011e07  mov     edx, 0Ch
0x140011e0c  mov     r9d, esi
0x140011e0f  lea     r8, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids
0x140011e16  mov     rcx, [rcx+10h]
0x140011e1a  call    WPP_SF_D
0x140011e1f  nop
0x140011e20  mov     rcx, [rsp+2D0h+var_288]
0x140011e25  jmp     short loc_140011DD3
0x140011e27  mov     rcx, cs:WPP_GLOBAL_Control
0x140011e2e  lea     rdx, WPP_GLOBAL_Control
0x140011e35  cmp     rcx, rdx
0x140011e38  jz      short loc_140011E59
0x140011e3a  test    byte ptr [rcx+1Ch], 8
0x140011e3e  jz      short loc_140011E59
0x140011e40  mov     edx, 0Dh
0x140011e45  mov     r9d, eax
0x140011e48  lea     r8, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids
0x140011e4f  mov     rcx, [rcx+10h]
0x140011e53  call    WPP_SF_D
0x140011e58  nop
0x140011e59  mov     rcx, rbx; Block
0x140011e5c  call    cs:__imp_free
0x140011e62  xor     ebx, ebx
0x140011e64  jmp     short loc_140011EC8
0x140011e66  mov     rcx, cs:WPP_GLOBAL_Control
0x140011e6d  lea     rax, WPP_GLOBAL_Control
0x140011e74  cmp     rcx, rax
0x140011e77  jz      short loc_140011EBC
0x140011e79  test    byte ptr [rcx+1Ch], 8
0x140011e7d  jz      short loc_140011EBC
0x140011e7f  mov     edx, 0Bh
0x140011e84  mov     r9d, esi
0x140011e87  jmp     short loc_140011EAB
0x140011e89  mov     rcx, cs:WPP_GLOBAL_Control
0x140011e90  lea     rax, WPP_GLOBAL_Control
0x140011e97  cmp     rcx, rax
0x140011e9a  jz      short loc_140011EBC
0x140011e9c  test    byte ptr [rcx+1Ch], 10h
0x140011ea0  jz      short loc_140011EBC
0x140011ea2  mov     edx, 0Ah
0x140011ea7  lea     r9d, [rdx-9]
0x140011eab  lea     r8, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids
0x140011eb2  mov     rcx, [rcx+10h]
0x140011eb6  call    WPP_SF_D
0x140011ebb  nop
0x140011ebc  mov     rcx, [rsp+2D0h+var_288]; Block
0x140011ec1  call    cs:__imp_free
0x140011ec7  nop
0x140011ec8  mov     rcx, r15
0x140011ecb  test    r15, r15
0x140011ece  jnz     loc_140011CDF
0x140011ed4  xor     eax, eax
0x140011ed6  mov     rcx, [rbp+1D0h+var_40]
0x140011edd  xor     rcx, rsp; StackCookie
0x140011ee0  call    __security_check_cookie
0x140011ee5  mov     rbx, [rsp+2D0h+arg_18]
0x140011eed  add     rsp, 2A0h
0x140011ef4  pop     r15
0x140011ef6  pop     r14
0x140011ef8  pop     r13
0x140011efa  pop     r12
0x140011efc  pop     rdi
0x140011efd  pop     rsi
0x140011efe  pop     rbp
0x140011eff  retn
```
