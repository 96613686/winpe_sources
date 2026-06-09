# EnumProfileStore(HKEY__ *,ulong,ushort *,ulong,ulong *,HKEY__ * *)

- ea: `0x18005aff0`
- end: `0x18005b1c7`
- name: `?EnumProfileStore@@YAJPEAUHKEY__@@KPEAGKPEAKPEAPEAU1@@Z`
- size: `471`
- prototype: `__int64 __fastcall(HKEY hKey, DWORD, unsigned __int16 *, __int64, unsigned int *, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800583e0`

## callees

- `0x180005fa0`
- `0x18000d1f0`
- `0x18005aff0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b159`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b159`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005b0e3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005b0e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b1aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b1aa`

## pseudocode

```c
__int64 __fastcall EnumProfileStore(HKEY hKey, DWORD a2, unsigned __int16 *a3, __int64 a4, unsigned int *a5, HKEY *a6)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  HKEY *v10; // rdi
  int v11; // eax
  __int64 v12; // rdx
  unsigned int *v13; // rsi
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  DWORD cchName; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int64 v18; // [rsp+48h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+8h] BYREF

  cchName = 260;
  phkResult = 0;
  v18 = 0;
  if ( hKey )
  {
    v10 = a6;
    if ( a6 )
    {
      v13 = a5;
      *a6 = 0;
      if ( v13 )
      {
        *v13 = 0;
        v14 = RegEnumKeyExW(hKey, a2, a3, &cchName, 0, 0, 0, 0);
        v8 = v14;
        if ( v14 )
        {
          if ( v14 > 0 )
            v8 = (unsigned __int16)v14 | 0x80070000;
          if ( (v8 & 0x80000000) != 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_30;
            v9 = 81;
            goto LABEL_4;
          }
        }
        v11 = StringCchLengthW(a3, 0x7FFFFFFFu, &v18);
        v8 = v11;
        if ( v11 >= 0 )
        {
          v15 = RegOpenKeyExW(hKey, a3, 0, 0x20119u, &phkResult);
          v8 = v15;
          if ( v15 )
          {
            if ( v15 > 0 )
              v8 = (unsigned __int16)v15 | 0x80070000;
            if ( (v8 & 0x80000000) != 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_30;
              v9 = 83;
              goto LABEL_4;
            }
          }
          else
          {
            v8 = 0;
          }
          *v10 = phkResult;
          *v13 = v18;
          phkResult = 0;
          goto LABEL_30;
        }
        if ( !g_wppLevels )
          goto LABEL_30;
        v12 = 82;
      }
      else
      {
        v11 = -2147467261;
        v8 = -2147467261;
        if ( !g_wppLevels )
          return v8;
        v12 = 80;
      }
    }
    else
    {
      v11 = -2147467261;
      v8 = -2147467261;
      if ( !g_wppLevels )
        return v8;
      v12 = (unsigned int)((_DWORD)a6 + 79);
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids, 0, v11);
    goto LABEL_30;
  }
  v8 = -2147024809;
  if ( !g_wppLevels )
    return v8;
  v9 = 78;
LABEL_4:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids, 0, v8);
LABEL_30:
  if ( phkResult )
    RegCloseKey(phkResult);
  return v8;
}

```

## disassembly

```asm
0x18005aff0  mov     rax, rsp
0x18005aff3  mov     [rax+10h], rbx
0x18005aff7  mov     [rax+18h], rbp
0x18005affb  push    rsi
0x18005affc  push    rdi
0x18005affd  push    r14
0x18005afff  sub     rsp, 50h
0x18005b003  mov     dword ptr [rax-28h], 104h
0x18005b00a  mov     r14, r8
0x18005b00d  mov     qword ptr [rax+8], 0
0x18005b015  mov     rbp, rcx
0x18005b018  mov     qword ptr [rax-20h], 0
0x18005b020  test    rcx, rcx
0x18005b023  jnz     short loc_18005B05D
0x18005b025  mov     ebx, 80070057h
0x18005b02a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005b031  jb      loc_18005B1B0
0x18005b037  lea     edx, [rcx+4Eh]
0x18005b03a  mov     dword ptr [rsp+68h+lpReserved], ebx
0x18005b03e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b045  lea     r8, WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids
0x18005b04c  xor     r9d, r9d
0x18005b04f  mov     rcx, [rcx+10h]
0x18005b053  call    WPP_SF_qD
0x18005b058  jmp     loc_18005B1A0
0x18005b05d  mov     rdi, [rsp+68h+arg_28]
0x18005b065  test    rdi, rdi
0x18005b068  jnz     short loc_18005B087
0x18005b06a  mov     eax, 80004003h
0x18005b06f  mov     ebx, eax
0x18005b071  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005b078  jb      loc_18005B1B0
0x18005b07e  lea     edx, [rdi+4Fh]
0x18005b081  mov     dword ptr [rsp+68h+lpReserved], eax
0x18005b085  jmp     short loc_18005B03E
0x18005b087  mov     rsi, [rsp+68h+arg_20]
0x18005b08f  mov     qword ptr [rdi], 0
0x18005b096  test    rsi, rsi
0x18005b099  jnz     short loc_18005B0B4
0x18005b09b  mov     eax, 80004003h
0x18005b0a0  mov     ebx, eax
0x18005b0a2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005b0a9  jb      loc_18005B1B0
0x18005b0af  lea     edx, [rsi+50h]; dwIndex
0x18005b0b2  jmp     short loc_18005B081
0x18005b0b4  mov     [rsp+68h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18005b0bd  lea     r9, [rsp+68h+cchName]; lpcchName
0x18005b0c2  mov     [rsp+68h+lpcchClass], 0; lpcchClass
0x18005b0cb  mov     [rsp+68h+lpClass], 0; lpClass
0x18005b0d4  mov     [rsp+68h+lpReserved], 0; lpReserved
0x18005b0dd  mov     dword ptr [rsi], 0
0x18005b0e3  call    cs:__imp_RegEnumKeyExW
0x18005b0e9  mov     ebx, eax
0x18005b0eb  test    eax, eax
0x18005b0ed  jz      short loc_18005B115
0x18005b0ef  jle     short loc_18005B0FA
0x18005b0f1  movzx   ebx, ax
0x18005b0f4  or      ebx, 80070000h
0x18005b0fa  test    ebx, ebx
0x18005b0fc  jns     short loc_18005B115
0x18005b0fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005b105  jb      loc_18005B1A0
0x18005b10b  mov     edx, 51h ; 'Q'
0x18005b110  jmp     loc_18005B03A
0x18005b115  lea     r8, [rsp+68h+var_20]; unsigned __int64 *
0x18005b11a  mov     edx, 7FFFFFFFh; unsigned __int64
0x18005b11f  mov     rcx, r14; unsigned __int16 *
0x18005b122  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005b127  mov     ebx, eax
0x18005b129  test    eax, eax
0x18005b12b  jns     short loc_18005B140
0x18005b12d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005b134  jb      short loc_18005B1A0
0x18005b136  mov     edx, 52h ; 'R'
0x18005b13b  jmp     loc_18005B081
0x18005b140  lea     rax, [rsp+68h+phkResult]
0x18005b145  mov     r9d, 20119h; samDesired
0x18005b14b  xor     r8d, r8d; ulOptions
0x18005b14e  mov     [rsp+68h+lpReserved], rax; phkResult
0x18005b153  mov     rdx, r14; lpSubKey
0x18005b156  mov     rcx, rbp; hKey
0x18005b159  call    cs:__imp_RegOpenKeyExW
0x18005b15f  mov     ebx, eax
0x18005b161  test    eax, eax
0x18005b163  jz      short loc_18005B187
0x18005b165  jle     short loc_18005B170
0x18005b167  movzx   ebx, ax
0x18005b16a  or      ebx, 80070000h
0x18005b170  test    ebx, ebx
0x18005b172  jns     short loc_18005B189
0x18005b174  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005b17b  jb      short loc_18005B1A0
0x18005b17d  mov     edx, 53h ; 'S'
0x18005b182  jmp     loc_18005B03A
0x18005b187  xor     ebx, ebx
0x18005b189  mov     rax, [rsp+68h+phkResult]
0x18005b18e  mov     [rdi], rax
0x18005b191  mov     eax, dword ptr [rsp+68h+var_20]
0x18005b195  mov     [rsi], eax
0x18005b197  mov     [rsp+68h+phkResult], 0
0x18005b1a0  mov     rcx, [rsp+68h+phkResult]; hKey
0x18005b1a5  test    rcx, rcx
0x18005b1a8  jz      short loc_18005B1B0
0x18005b1aa  call    cs:__imp_RegCloseKey
0x18005b1b0  lea     r11, [rsp+68h+var_18]
0x18005b1b5  mov     eax, ebx
0x18005b1b7  mov     rbx, [r11+28h]
0x18005b1bb  mov     rbp, [r11+30h]
0x18005b1bf  mov     rsp, r11
0x18005b1c2  pop     r14
0x18005b1c4  pop     rdi
0x18005b1c5  pop     rsi
0x18005b1c6  retn
```
