# FSMSession::InternalInitialize(ushort const *,void *,__MIDL___MIDL_itf_mfdeviceinternal_0000_0053_0004,uchar *,ulong)

- ea: `0x18001b82c`
- end: `0x18001ba44`
- name: `?InternalInitialize@FSMSession@@IEAAJPEBGPEAXW4__MIDL___MIDL_itf_mfdeviceinternal_0000_0053_0004@@PEAEK@Z`
- size: `536`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a448`

## callees

- `0x180006a98`
- `0x180006ae8`
- `0x18000cadc`
- `0x18000d1e0`
- `0x18000d890`
- `0x18001b38c`
- `0x18001b82c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b912`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b912`
- `MFPlat!MFGetSystemTime` at `0x18001b857`
- `MFPlat!MFGetSystemTime` at `0x18001b857`

## pseudocode

```c
__int64 __fastcall FSMSession::InternalInitialize(
        __int64 *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6)
{
  MFTIME v10; // r14
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  int v14; // eax
  unsigned __int64 v16; // [rsp+40h] [rbp-38h] BYREF
  __int64 v17; // [rsp+88h] [rbp+10h] BYREF

  v17 = 0;
  v10 = MFGetSystemTime();
  if ( !a2 )
  {
    v11 = -2147024809;
    v12 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_23;
    v13 = 102;
    goto LABEL_4;
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qqdS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      103,
      (unsigned int)&WPP_dda53059c67a34537508687cb55acb7f_Traceguids,
      (_DWORD)a1,
      a3,
      a4,
      (__int64)a2);
  v11 = StringCchLengthW(a2, 0x7FFFFFFFu, &v16);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( g_wppLevels )
    {
      v13 = 104;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_dda53059c67a34537508687cb55acb7f_Traceguids, a1, v11);
      goto LABEL_23;
    }
    goto LABEL_23;
  }
  if ( a4 == 1 || a4 == 3 )
  {
    v10 = 0;
  }
  else if ( a4 == 4
         && CompareStringOrdinal(a2, -1, L"FSMSessionName_SettingsApp_{238C2508-8F66-4E23-9670-FC85F170CD63}", -1, 1) != 2 )
  {
    v11 = -2147024809;
    v12 = -2147024809;
    if ( g_wppLevels )
    {
      v13 = 105;
      goto LABEL_4;
    }
LABEL_23:
    if ( byte_18005E5A5 )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 108, &WPP_dda53059c67a34537508687cb55acb7f_Traceguids, a1, v12);
    goto LABEL_27;
  }
  v11 = FSMSession::InternalAddClientType(a1, a3, a4, a5, a6);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( g_wppLevels )
    {
      v13 = 106;
      goto LABEL_4;
    }
    goto LABEL_23;
  }
  v14 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, MFTIME))(*a1 + 8))(a1, a2, v10);
  v12 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_dda53059c67a34537508687cb55acb7f_Traceguids, a1, v14);
    goto LABEL_23;
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qDS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      109,
      (unsigned int)&WPP_dda53059c67a34537508687cb55acb7f_Traceguids,
      (_DWORD)a1,
      v14,
      a1[1]);
LABEL_27:
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v17);
  return v12;
}

```

## disassembly

```asm
0x18001b82c  mov     rax, rsp
0x18001b82f  mov     [rax+8], rbx
0x18001b833  mov     [rax+18h], rbp
0x18001b837  push    rsi
0x18001b838  push    rdi
0x18001b839  push    r12
0x18001b83b  push    r14
0x18001b83d  push    r15
0x18001b83f  sub     rsp, 50h
0x18001b843  mov     ebp, r9d
0x18001b846  mov     qword ptr [rax+10h], 0
0x18001b84e  mov     r15, r8
0x18001b851  mov     rsi, rdx
0x18001b854  mov     rdi, rcx
0x18001b857  call    cs:__imp_MFGetSystemTime
0x18001b85d  lea     r12, WPP_dda53059c67a34537508687cb55acb7f_Traceguids
0x18001b864  mov     r14, rax
0x18001b867  test    rsi, rsi
0x18001b86a  jnz     short loc_18001B88C
0x18001b86c  mov     eax, 80070057h
0x18001b871  mov     ebx, eax
0x18001b873  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001b87a  jb      loc_18001B9BB
0x18001b880  lea     edx, [rsi+66h]
0x18001b883  mov     [rsp+78h+bIgnoreCase], eax
0x18001b887  jmp     loc_18001B9A5
0x18001b88c  cmp     cs:byte_18005E5A5, 8
0x18001b893  jb      short loc_18001B8C1
0x18001b895  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b89c  mov     edx, 67h ; 'g'
0x18001b8a1  mov     [rsp+78h+var_48], rsi
0x18001b8a6  mov     r9, rdi
0x18001b8a9  mov     dword ptr [rsp+78h+var_50], ebp
0x18001b8ad  mov     r8, r12
0x18001b8b0  mov     qword ptr [rsp+78h+bIgnoreCase], r15
0x18001b8b5  mov     rcx, [rcx+0D8h]
0x18001b8bc  call    WPP_SF_qqdS
0x18001b8c1  lea     r8, [rsp+78h+var_38]; unsigned __int64 *
0x18001b8c6  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001b8cb  mov     rcx, rsi; unsigned __int16 *
0x18001b8ce  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001b8d3  mov     ebx, eax
0x18001b8d5  test    eax, eax
0x18001b8d7  jns     short loc_18001B8ED
0x18001b8d9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001b8e0  jb      loc_18001B9BB
0x18001b8e6  mov     edx, 68h ; 'h'
0x18001b8eb  jmp     short loc_18001B883
0x18001b8ed  mov     ecx, ebp
0x18001b8ef  sub     ecx, 1
0x18001b8f2  jz      short loc_18001B93B
0x18001b8f4  sub     ecx, 2
0x18001b8f7  jz      short loc_18001B93B
0x18001b8f9  cmp     ecx, 1
0x18001b8fc  jnz     short loc_18001B93E
0x18001b8fe  or      edx, 0FFFFFFFFh; cchCount1
0x18001b901  mov     [rsp+78h+bIgnoreCase], ecx; bIgnoreCase
0x18001b905  mov     r9d, edx; cchCount2
0x18001b908  lea     r8, String2; "FSMSessionName_SettingsApp_{238C2508-8F"...
0x18001b90f  mov     rcx, rsi; lpString1
0x18001b912  call    cs:__imp_CompareStringOrdinal
0x18001b918  cmp     eax, 2
0x18001b91b  jz      short loc_18001B93E
0x18001b91d  mov     eax, 80070057h
0x18001b922  mov     ebx, eax
0x18001b924  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001b92b  jb      loc_18001B9BB
0x18001b931  mov     edx, 69h ; 'i'
0x18001b936  jmp     loc_18001B883
0x18001b93b  xor     r14d, r14d
0x18001b93e  mov     eax, [rsp+78h+arg_28]
0x18001b945  mov     r8d, ebp
0x18001b948  mov     r9, [rsp+78h+arg_20]
0x18001b950  mov     rdx, r15
0x18001b953  mov     rcx, rdi
0x18001b956  mov     [rsp+78h+bIgnoreCase], eax
0x18001b95a  call    ?InternalAddClientType@FSMSession@@IEAAJPEAXW4__MIDL___MIDL_itf_mfdeviceinternal_0000_0053_0004@@PEAEK@Z; FSMSession::InternalAddClientType(void *,__MIDL___MIDL_itf_mfdeviceinternal_0000_0053_0004,uchar *,ulong)
0x18001b95f  mov     ebx, eax
0x18001b961  test    eax, eax
0x18001b963  jns     short loc_18001B978
0x18001b965  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001b96c  jb      short loc_18001B9BB
0x18001b96e  mov     edx, 6Ah ; 'j'
0x18001b973  jmp     loc_18001B883
0x18001b978  mov     rax, [rdi]
0x18001b97b  mov     r8, r14
0x18001b97e  mov     rdx, rsi
0x18001b981  mov     rcx, rdi
0x18001b984  mov     rax, [rax+8]
0x18001b988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b98d  mov     ebx, eax
0x18001b98f  test    eax, eax
0x18001b991  jns     short loc_18001B9E8
0x18001b993  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001b99a  jb      short loc_18001B9BB
0x18001b99c  mov     edx, 6Bh ; 'k'
0x18001b9a1  mov     [rsp+78h+bIgnoreCase], eax
0x18001b9a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9ac  mov     r9, rdi
0x18001b9af  mov     r8, r12
0x18001b9b2  mov     rcx, [rcx+10h]
0x18001b9b6  call    WPP_SF_qD
0x18001b9bb  cmp     cs:byte_18005E5A5, 1
0x18001b9c2  jb      short loc_18001BA1C
0x18001b9c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9cb  mov     edx, 6Ch ; 'l'
0x18001b9d0  mov     r9, rdi
0x18001b9d3  mov     [rsp+78h+bIgnoreCase], ebx
0x18001b9d7  mov     r8, r12
0x18001b9da  mov     rcx, [rcx+0D8h]
0x18001b9e1  call    WPP_SF_qD
0x18001b9e6  jmp     short loc_18001BA1C
0x18001b9e8  cmp     cs:byte_18005E5A5, 8
0x18001b9ef  jb      short loc_18001BA1C
0x18001b9f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9f8  mov     edx, 6Dh ; 'm'
0x18001b9fd  mov     rax, [rdi+8]
0x18001ba01  mov     r9, rdi
0x18001ba04  mov     [rsp+78h+var_50], rax
0x18001ba09  mov     r8, r12
0x18001ba0c  mov     [rsp+78h+bIgnoreCase], ebx
0x18001ba10  mov     rcx, [rcx+0D8h]
0x18001ba17  call    WPP_SF_qDS
0x18001ba1c  lea     rcx, [rsp+78h+arg_8]
0x18001ba24  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18001ba29  lea     r11, [rsp+78h+var_28]
0x18001ba2e  mov     eax, ebx
0x18001ba30  mov     rbx, [r11+30h]
0x18001ba34  mov     rbp, [r11+40h]
0x18001ba38  mov     rsp, r11
0x18001ba3b  pop     r15
0x18001ba3d  pop     r14
0x18001ba3f  pop     r12
0x18001ba41  pop     rdi
0x18001ba42  pop     rsi
0x18001ba43  retn
```
