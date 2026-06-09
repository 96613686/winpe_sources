# CIdentityProfileHandler::_CreateAndACLRegKey(HKEY__ *,ushort const *,ushort const *)

- ea: `0x1800022d0`
- end: `0x1800024f6`
- name: `?_CreateAndACLRegKey@CIdentityProfileHandler@@AEAAJPEAUHKEY__@@PEBG1@Z`
- size: `550`
- prototype: `__int64 __fastcall(CIdentityProfileHandler *this, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180001c60`

## callees

- `0x180002030`
- `0x1800022d0`
- `0x180003560`
- `0x18001448c`
- `0x1800144b4`
- `0x1800145a0`
- `0x180014974`
- `0x1800191ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800023ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800023ea`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002398`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002398`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023d9`

## string_xrefs

- `0x1800022f2`: `CIdentityProfileHandler::_CreateAndACLRegKey`

## pseudocode

```c
__int64 __fastcall CIdentityProfileHandler::_CreateAndACLRegKey(
        CIdentityProfileHandler *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  CIdentityProfileHandler *v6; // rcx
  int PathKey; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  WCHAR *v10; // rbx
  signed int v11; // edi
  LSTATUS v12; // eax
  CIdentityProfileHandler *v13; // rcx
  int v15; // eax
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-30h] BYREF
  _QWORD v18[2]; // [rsp+60h] [rbp-28h] BYREF
  CIdentityProfileHandler *dwDisposition; // [rsp+90h] [rbp+8h] BYREF
  signed int v20; // [rsp+98h] [rbp+10h] BYREF
  int v21; // [rsp+9Ch] [rbp+14h]

  v21 = HIDWORD(a2);
  dwDisposition = this;
  v18[1] = "CIdentityProfileHandler::_CreateAndACLRegKey";
  v20 = 0;
  v18[0] = &v20;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CIdentityProfileHandler::_CreateAndACLRegKey");
  }
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  LODWORD(dwDisposition) = 0;
  lpSubKey = 0;
  PathKey = CIdentityProfileHandler::_CreatePathKey(v6, a3, a4, (void **)&lpSubKey);
  v10 = (WCHAR *)lpSubKey;
  v11 = PathKey;
  v20 = PathKey;
  if ( PathKey >= 0 )
  {
    v12 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, (LPDWORD)&dwDisposition);
    v11 = v12;
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)WPP_0955e053d70b3b28b837838791dca877_Traceguids,
          (_DWORD)v10,
          v12);
      }
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      v20 = v11;
    }
    else
    {
      if ( (_DWORD)dwDisposition != 1 )
      {
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_0955e053d70b3b28b837838791dca877_Traceguids);
        }
        goto LABEL_10;
      }
      v15 = CIdentityProfileHandler::_AdjustRegSidKeyForUser(v13, hKey, a4);
      v20 = v15;
      v11 = v15;
      if ( v15 >= 0 )
      {
LABEL_10:
        v11 = 0;
        v20 = 0;
        goto LABEL_11;
      }
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_0955e053d70b3b28b837838791dca877_Traceguids,
          (unsigned int)v15);
        v11 = v20;
      }
    }
  }
LABEL_11:
  if ( v10 )
    LocalFree(v10);
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    RegCloseKey(hKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  CLogBlock::~CLogBlock((CLogBlock *)v18, v8, v9);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800022d0  mov     rax, rsp
0x1800022d3  mov     [rax+18h], rbx
0x1800022d7  mov     [rax+20h], rbp
0x1800022db  mov     [rax+10h], rdx
0x1800022df  mov     [rax+8], rcx
0x1800022e3  push    rsi
0x1800022e4  push    rdi
0x1800022e5  push    r14
0x1800022e7  sub     rsp, 70h
0x1800022eb  mov     rsi, r9
0x1800022ee  lea     rax, [rax+10h]
0x1800022f2  lea     r9, aCidentityprofi_4; "CIdentityProfileHandler::_CreateAndACLR"...
0x1800022f9  xor     ebp, ebp
0x1800022fb  mov     [rax-30h], r9
0x1800022ff  mov     rbx, r8
0x180002302  mov     [rax], ebp
0x180002304  mov     [rsp+88h+var_28], rax
0x180002309  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180002310  lea     r14, WPP_GLOBAL_Control
0x180002317  cmp     rcx, r14
0x18000231a  jz      short loc_180002329
0x18000231c  test    dword ptr [rcx+1Ch], 400h
0x180002323  jnz     loc_180002442
0x180002329  lea     r9, [rsp+88h+lpSubKey]; void **
0x18000232e  mov     [rsp+88h+hKey], 0FFFFFFFFFFFFFFFFh
0x180002337  mov     r8, rsi; unsigned __int16 *
0x18000233a  mov     dword ptr [rsp+88h+dwDisposition], ebp
0x180002341  mov     rdx, rbx; unsigned __int16 *
0x180002344  mov     [rsp+88h+lpSubKey], rbp
0x180002349  call    ?_CreatePathKey@CIdentityProfileHandler@@AEAAJPEBG0PEAPEAX@Z; CIdentityProfileHandler::_CreatePathKey(ushort const *,ushort const *,void * *)
0x18000234e  mov     rbx, [rsp+88h+lpSubKey]
0x180002353  mov     edi, eax
0x180002355  mov     [rsp+88h+arg_8], eax
0x18000235c  test    eax, eax
0x18000235e  js      short loc_1800023D1
0x180002360  lea     rax, [rsp+88h+dwDisposition]
0x180002368  xor     r9d, r9d; lpClass
0x18000236b  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x180002370  xor     r8d, r8d; Reserved
0x180002373  lea     rax, [rsp+88h+hKey]
0x180002378  mov     rdx, rbx; lpSubKey
0x18000237b  mov     [rsp+88h+phkResult], rax; phkResult
0x180002380  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002387  mov     [rsp+88h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x18000238c  mov     [rsp+88h+samDesired], 0F003Fh; samDesired
0x180002394  mov     [rsp+88h+dwOptions], ebp; dwOptions
0x180002398  call    cs:__imp_RegCreateKeyExW
0x18000239e  mov     edi, eax
0x1800023a0  test    eax, eax
0x1800023a2  jnz     short loc_18000241A
0x1800023a4  cmp     dword ptr [rsp+88h+dwDisposition], 1
0x1800023ac  jz      loc_180002455
0x1800023b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023b9  cmp     rcx, r14
0x1800023bc  jz      short loc_1800023C8
0x1800023be  test    byte ptr [rcx+1Ch], 8
0x1800023c2  jnz     loc_1800024B1
0x1800023c8  mov     edi, ebp
0x1800023ca  mov     [rsp+88h+arg_8], ebp
0x1800023d1  test    rbx, rbx
0x1800023d4  jz      short loc_1800023DF
0x1800023d6  mov     rcx, rbx; hMem
0x1800023d9  call    cs:__imp_LocalFree
0x1800023df  mov     rcx, [rsp+88h+hKey]; hKey
0x1800023e4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800023e8  jz      short loc_1800023F9
0x1800023ea  call    cs:__imp_RegCloseKey
0x1800023f0  mov     [rsp+88h+hKey], 0FFFFFFFFFFFFFFFFh
0x1800023f9  lea     rcx, [rsp+88h+var_28]; this
0x1800023fe  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x180002403  lea     r11, [rsp+88h+var_18]
0x180002408  mov     eax, edi
0x18000240a  mov     rbx, [r11+30h]
0x18000240e  mov     rbp, [r11+38h]
0x180002412  mov     rsp, r11
0x180002415  pop     r14
0x180002417  pop     rdi
0x180002418  pop     rsi
0x180002419  retn
0x18000241a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002421  cmp     rcx, r14
0x180002424  jnz     loc_1800024CB
0x18000242a  test    edi, edi
0x18000242c  jg      short loc_180002437
0x18000242e  mov     [rsp+88h+arg_8], edi
0x180002435  jmp     short loc_1800023D1
0x180002437  movzx   edi, di
0x18000243a  or      edi, 80070000h
0x180002440  jmp     short loc_18000242E
0x180002442  mov     rcx, [rcx+10h]
0x180002446  mov     edx, 0Ah
0x18000244b  call    WPP_SF_s
0x180002450  jmp     loc_180002329
0x180002455  mov     rdx, [rsp+88h+hKey]; HKEY
0x18000245a  mov     r8, rsi; unsigned __int16 *
0x18000245d  call    ?_AdjustRegSidKeyForUser@CIdentityProfileHandler@@AEAAJPEAUHKEY__@@PEBG@Z; CIdentityProfileHandler::_AdjustRegSidKeyForUser(HKEY__ *,ushort const *)
0x180002462  mov     [rsp+88h+arg_8], eax
0x180002469  mov     edi, eax
0x18000246b  test    eax, eax
0x18000246d  jns     loc_1800023C8
0x180002473  mov     rcx, cs:WPP_GLOBAL_Control
0x18000247a  cmp     rcx, r14
0x18000247d  jz      loc_1800023D1
0x180002483  test    byte ptr [rcx+1Ch], 4
0x180002487  jz      loc_1800023D1
0x18000248d  mov     rcx, [rcx+10h]
0x180002491  lea     r8, WPP_0955e053d70b3b28b837838791dca877_Traceguids
0x180002498  mov     edx, 15h
0x18000249d  mov     r9d, eax
0x1800024a0  call    WPP_SF_d
0x1800024a5  mov     edi, [rsp+88h+arg_8]
0x1800024ac  jmp     loc_1800023D1
0x1800024b1  mov     rcx, [rcx+10h]
0x1800024b5  lea     r8, WPP_0955e053d70b3b28b837838791dca877_Traceguids
0x1800024bc  mov     edx, 16h
0x1800024c1  call    WPP_SF_
0x1800024c6  jmp     loc_1800023C8
0x1800024cb  test    byte ptr [rcx+1Ch], 4
0x1800024cf  jz      loc_18000242A
0x1800024d5  mov     rcx, [rcx+10h]
0x1800024d9  lea     r8, WPP_0955e053d70b3b28b837838791dca877_Traceguids
0x1800024e0  mov     edx, 17h
0x1800024e5  mov     [rsp+88h+dwOptions], edi
0x1800024e9  mov     r9, rbx
0x1800024ec  call    WPP_SF_Sd
0x1800024f1  jmp     loc_18000242A
```
