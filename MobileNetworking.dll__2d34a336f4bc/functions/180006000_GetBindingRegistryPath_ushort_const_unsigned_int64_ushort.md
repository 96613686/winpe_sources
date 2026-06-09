# GetBindingRegistryPath(ushort const *,unsigned __int64,ushort *)

- ea: `0x180006000`
- end: `0x180006337`
- name: `?GetBindingRegistryPath@@YAJPEBG_KPEAG@Z`
- size: `823`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180005c20`
- `0x180005e30`
- `0x180008ce0`
- `0x18000dc90`
- `0x18000eda0`
- `0x18000f160`

## callees

- `0x180006000`
- `0x180006630`
- `0x180007570`
- `0x180008ff0`
- `0x18000b6f4`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800062d2`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800062d2`

## pseudocode

```c
__int64 __fastcall GetBindingRegistryPath(const unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  wchar_t *v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rdx
  unsigned __int16 *v9; // r8
  unsigned __int16 *v10; // rcx
  signed int PersistedRegistryLocationW; // esi
  int v12; // r9d
  __int64 v13; // rcx
  unsigned __int16 *v14; // rax
  int v15; // r8d
  __int64 v16; // rdx
  const wchar_t *v17; // rax
  unsigned __int16 *v18; // r9
  __int64 v19; // r8
  unsigned __int16 *v20; // rcx
  _WORD *v22; // rcx
  bool v23; // sf
  unsigned int v24; // eax
  __int64 v25; // rdx
  wchar_t *v26; // rax
  __int64 v27; // rcx
  _WORD *v28; // r8
  const wchar_t *v29; // r9
  __int64 v30; // rcx
  const wchar_t *v31; // rax
  __int64 v32; // [rsp+58h] [rbp+10h] BYREF

  v32 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids);
  if ( !a1 )
    return 2147942487LL;
  v5 = &psz;
  v6 = 2147483646;
  if ( psz )
    goto LABEL_4;
  LODWORD(v32) = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(L"WwanSvc", RegistryPaths[0], &psz, 520, &v32);
  if ( aMobilebroadban[0] )
  {
    v30 = 0x7FFFFFFF;
    v31 = L"MobileBroadbandAccounts";
    do
    {
      if ( !*v31 )
      {
        v24 = ((unsigned int)v32 >> 1) - v30 + 0x80000000;
        goto LABEL_41;
      }
      ++v31;
      --v30;
    }
    while ( v30 );
    LOWORD(PersistedRegistryLocationW) = 87;
    goto LABEL_48;
  }
  v24 = (unsigned int)v32 >> 1;
LABEL_41:
  v23 = PersistedRegistryLocationW < 0;
  if ( !PersistedRegistryLocationW )
  {
    if ( v24 <= 0x104 )
    {
      if ( aMobilebroadban[0] )
      {
        v25 = 260;
        v26 = &psz;
        while ( *v26 )
        {
          ++v26;
          if ( !--v25 )
            goto LABEL_47;
        }
        v27 = 2147483646;
        v28 = (_WORD *)&wil::details_abi::g_pProcessLocalData - v25;
        v29 = L"\\";
        do
        {
          if ( !v27 )
            break;
          if ( !*v29 )
            break;
          *v28++ = *v29++;
          --v27;
          --v25;
        }
        while ( v25 );
        v22 = v28 - 1;
        if ( v25 )
          v22 = v28;
        *v22 = 0;
        if ( !v25 || StringCchCatW(&psz, 0x104u, L"MobileBroadbandAccounts") < 0 )
        {
LABEL_47:
          LOWORD(PersistedRegistryLocationW) = 31;
          goto LABEL_48;
        }
      }
      goto LABEL_37;
    }
    LOWORD(PersistedRegistryLocationW) = 234;
LABEL_48:
    PersistedRegistryLocationW = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
LABEL_37:
    v23 = PersistedRegistryLocationW < 0;
    goto LABEL_38;
  }
  if ( PersistedRegistryLocationW > 0 )
    goto LABEL_48;
LABEL_38:
  if ( !v23 )
  {
LABEL_4:
    v7 = 2147483646;
    v8 = 260;
    v9 = a3;
    do
    {
      if ( !v7 )
        break;
      if ( !*v5 )
        break;
      *v9++ = *v5++;
      --v7;
      --v8;
    }
    while ( v8 );
    v10 = v9 - 1;
    PersistedRegistryLocationW = -2147024774;
    v12 = -2147024774;
    if ( v8 )
    {
      v10 = v9;
      v12 = 0;
    }
    *v10 = 0;
    if ( v8 )
    {
      v13 = 260;
      v14 = a3;
      do
      {
        if ( !*v14 )
          break;
        ++v14;
        --v13;
      }
      while ( v13 );
      v15 = -2147024809;
      if ( v13 )
        v15 = 0;
      v16 = 260 - v13;
      if ( v13 )
      {
        v17 = L"\\NetworkInterfaceBindings\\";
        v18 = &a3[v16];
        v19 = v13;
        if ( v16 != 260 )
        {
          do
          {
            if ( !v6 )
              break;
            if ( !*v17 )
              break;
            *v18++ = *v17++;
            --v6;
            --v19;
          }
          while ( v19 );
        }
        v20 = v18 - 1;
        if ( v19 )
        {
          v20 = v18;
          PersistedRegistryLocationW = 0;
        }
        *v20 = 0;
        if ( v19 )
          PersistedRegistryLocationW = StringCchCatW(a3, 0x104u, a1);
      }
      else
      {
        PersistedRegistryLocationW = v15;
      }
    }
    else
    {
      PersistedRegistryLocationW = v12;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids,
      (unsigned int)PersistedRegistryLocationW);
  return (unsigned int)PersistedRegistryLocationW;
}

```

## disassembly

```asm
0x180006000  mov     [rsp+arg_8], rdx
0x180006005  push    rbp
0x180006006  push    r14
0x180006008  push    r15
0x18000600a  sub     rsp, 30h
0x18000600e  mov     r14, r8
0x180006011  mov     rbp, rcx
0x180006014  mov     rcx, cs:WPP_GLOBAL_Control
0x18000601b  lea     r15, WPP_GLOBAL_Control
0x180006022  cmp     rcx, r15
0x180006025  jnz     loc_180006164
0x18000602b  test    rbp, rbp
0x18000602e  jz      loc_180006310
0x180006034  cmp     cs:psz, 0
0x18000603c  mov     [rsp+48h+arg_0], rbx
0x180006041  lea     rbx, psz
0x180006048  mov     [rsp+48h+arg_10], rsi
0x18000604d  mov     [rsp+48h+arg_18], rdi
0x180006052  mov     edi, 7FFFFFFEh
0x180006057  jz      loc_1800062A9
0x18000605d  mov     rax, rdi
0x180006060  mov     edx, 104h
0x180006065  mov     r8, r14
0x180006068  test    rax, rax
0x18000606b  jz      short loc_18000608A
0x18000606d  movzx   ecx, word ptr [rbx]
0x180006070  test    cx, cx
0x180006073  jz      short loc_18000608A
0x180006075  mov     [r8], cx
0x180006079  add     rbx, 2
0x18000607d  add     r8, 2
0x180006081  dec     rax
0x180006084  sub     rdx, 1
0x180006088  jnz     short loc_180006068
0x18000608a  xor     eax, eax
0x18000608c  lea     rcx, [r8-2]
0x180006090  test    rdx, rdx
0x180006093  mov     esi, 8007007Ah
0x180006098  mov     r9d, esi
0x18000609b  cmovnz  rcx, r8
0x18000609f  cmovnz  r9d, eax
0x1800060a3  mov     [rcx], ax
0x1800060a6  jz      loc_18000632F
0x1800060ac  mov     ecx, 104h
0x1800060b1  mov     rax, r14
0x1800060b4  cmp     word ptr [rax], 0
0x1800060b8  jz      short loc_1800060C4
0x1800060ba  add     rax, 2
0x1800060be  sub     rcx, 1
0x1800060c2  jnz     short loc_1800060B4
0x1800060c4  xor     eax, eax
0x1800060c6  mov     r8d, 80070057h
0x1800060cc  test    rcx, rcx
0x1800060cf  mov     edx, 104h
0x1800060d4  cmovnz  r8d, eax
0x1800060d8  sub     rdx, rcx
0x1800060db  test    rcx, rcx
0x1800060de  cmovz   rdx, rax
0x1800060e2  jz      loc_180006188
0x1800060e8  mov     r8d, 104h
0x1800060ee  lea     rax, aNetworkinterfa; "\\NetworkInterfaceBindings\\"
0x1800060f5  lea     r9, [r14+rdx*2]
0x1800060f9  sub     r8, rdx
0x1800060fc  jnz     short loc_180006140
0x1800060fe  xor     eax, eax
0x180006100  lea     rcx, [r9-2]
0x180006104  test    r8, r8
0x180006107  cmovnz  rcx, r9
0x18000610b  cmovnz  esi, eax
0x18000610e  mov     [rcx], ax
0x180006111  jnz     loc_1800061AD
0x180006117  mov     rcx, cs:WPP_GLOBAL_Control
0x18000611e  mov     rdi, [rsp+48h+arg_18]
0x180006123  mov     rbx, [rsp+48h+arg_0]
0x180006128  cmp     rcx, r15
0x18000612b  jnz     short loc_18000618D
0x18000612d  mov     eax, esi
0x18000612f  mov     rsi, [rsp+48h+arg_10]
0x180006134  add     rsp, 30h
0x180006138  pop     r15
0x18000613a  pop     r14
0x18000613c  pop     rbp
0x18000613d  retn
0x180006140  test    rdi, rdi
0x180006143  jz      short loc_1800060FE
0x180006145  movzx   ecx, word ptr [rax]
0x180006148  test    cx, cx
0x18000614b  jz      short loc_1800060FE
0x18000614d  mov     [r9], cx
0x180006151  add     rax, 2
0x180006155  add     r9, 2
0x180006159  dec     rdi
0x18000615c  sub     r8, 1
0x180006160  jnz     short loc_180006140
0x180006162  jmp     short loc_1800060FE
0x180006164  test    byte ptr [rcx+1Ch], 10h
0x180006168  jz      loc_18000602B
0x18000616e  mov     rcx, [rcx+10h]
0x180006172  lea     r8, WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids
0x180006179  mov     edx, 12h
0x18000617e  call    WPP_SF_
0x180006183  jmp     loc_18000602B
0x180006188  mov     esi, r8d
0x18000618b  jmp     short loc_180006117
0x18000618d  test    byte ptr [rcx+1Ch], 10h
0x180006191  jz      short loc_18000612D
0x180006193  mov     rcx, [rcx+10h]
0x180006197  lea     r8, WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids
0x18000619e  mov     edx, 13h
0x1800061a3  mov     r9d, esi
0x1800061a6  call    WPP_SF_d
0x1800061ab  jmp     short loc_18000612D
0x1800061ad  mov     r8, rbp; unsigned __int16 *
0x1800061b0  mov     edx, 104h; unsigned __int64
0x1800061b5  mov     rcx, r14; unsigned __int16 *
0x1800061b8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800061bd  mov     esi, eax
0x1800061bf  jmp     loc_180006117
0x1800061c4  test    rdx, rdx
0x1800061c7  lea     rcx, [r8-2]
0x1800061cb  cmovnz  rcx, r8
0x1800061cf  xor     eax, eax
0x1800061d1  mov     [rcx], ax
0x1800061d4  test    rdx, rdx
0x1800061d7  jz      short loc_180006240
0x1800061d9  lea     r8, aMobilebroadban; "MobileBroadbandAccounts"
0x1800061e0  mov     edx, 104h; cchDest
0x1800061e5  mov     rcx, rbx; pszDest
0x1800061e8  call    StringCchCatW
0x1800061ed  test    eax, eax
0x1800061ef  js      short loc_180006240
0x1800061f1  test    esi, esi
0x1800061f3  js      loc_180006117
0x1800061f9  jmp     loc_18000605D
0x1800061fe  mov     eax, dword ptr [rsp+48h+arg_8]
0x180006202  shr     eax, 1
0x180006204  sub     eax, ecx
0x180006206  add     eax, 80000000h
0x18000620b  test    esi, esi
0x18000620d  jnz     loc_1800062A1
0x180006213  cmp     eax, 104h
0x180006218  ja      loc_180006325
0x18000621e  test    dx, dx
0x180006221  jz      short loc_1800061F1
0x180006223  mov     edx, 104h
0x180006228  mov     rax, rbx
0x18000622b  nop     dword ptr [rax+rax+00h]
0x180006230  cmp     word ptr [rax], 0
0x180006234  jz      short loc_180006250
0x180006236  add     rax, 2
0x18000623a  sub     rdx, 1
0x18000623e  jnz     short loc_180006230
0x180006240  mov     esi, 1Fh
0x180006245  movzx   esi, si
0x180006248  or      esi, 80070000h
0x18000624e  jmp     short loc_1800061F1
0x180006250  lea     rax, [rdx+rdx]
0x180006254  mov     rcx, rdi
0x180006257  lea     r8, ?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000625e  sub     r8, rax
0x180006261  lea     r9, asc_180013DE4; "\\"
0x180006268  test    rdx, rdx
0x18000626b  jz      loc_1800061C4
0x180006271  test    rcx, rcx
0x180006274  jz      loc_1800061C4
0x18000627a  movzx   eax, word ptr [r9]
0x18000627e  test    ax, ax
0x180006281  jz      loc_1800061C4
0x180006287  mov     [r8], ax
0x18000628b  add     r9, 2
0x18000628f  add     r8, 2
0x180006293  dec     rcx
0x180006296  sub     rdx, 1
0x18000629a  jnz     short loc_180006271
0x18000629c  jmp     loc_1800061C4
0x1800062a1  jle     loc_1800061F3
0x1800062a7  jmp     short loc_180006245
0x1800062a9  mov     rdx, cs:RegistryPaths
0x1800062b0  lea     rax, [rsp+48h+arg_8]
0x1800062b5  mov     rcx, cs:off_180013008; "WwanSvc"
0x1800062bc  mov     r9d, 208h
0x1800062c2  mov     r8, rbx
0x1800062c5  mov     [rsp+48h+var_28], rax
0x1800062ca  mov     dword ptr [rsp+48h+arg_8], 0
0x1800062d2  call    cs:__imp_GetPersistedRegistryLocationW
0x1800062d8  movzx   edx, word ptr cs:aMobilebroadban; "MobileBroadbandAccounts"
0x1800062df  mov     esi, eax
0x1800062e1  test    dx, dx
0x1800062e4  jz      short loc_18000631A
0x1800062e6  mov     ecx, 7FFFFFFFh
0x1800062eb  lea     rax, aMobilebroadban; "MobileBroadbandAccounts"
0x1800062f2  cmp     word ptr [rax], 0
0x1800062f6  jz      loc_1800061FE
0x1800062fc  add     rax, 2
0x180006300  sub     rcx, 1
0x180006304  jnz     short loc_1800062F2
0x180006306  mov     esi, 57h ; 'W'
0x18000630b  jmp     loc_180006245
0x180006310  mov     eax, 80070057h
0x180006315  jmp     loc_180006134
0x18000631a  mov     eax, dword ptr [rsp+48h+arg_8]
0x18000631e  shr     eax, 1
0x180006320  jmp     loc_18000620B
0x180006325  mov     esi, 0EAh
0x18000632a  jmp     loc_180006245
0x18000632f  mov     esi, r9d
0x180006332  jmp     loc_180006117
```
