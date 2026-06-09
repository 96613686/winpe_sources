# MFCreateTranslatedMediaType3

- ea: `0x18000aa80`
- end: `0x18000ac0e`
- name: `MFCreateTranslatedMediaType3`
- size: `398`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000aa50`
- `0x180056dc0`
- `0x180059640`

## callees

- `0x180005fa0`
- `0x18000aa80`
- `0x18000ae14`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000aae3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000aae3`

## pseudocode

```c
__int64 __fastcall MFCreateTranslatedMediaType3(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  HRESULT v10; // ebx
  int v11; // eax
  LPVOID ppv; // [rsp+40h] [rbp-38h] BYREF

  ppv = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 43, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids);
  ppv = 0;
  v10 = CoCreateInstance(&CLSID_MFSensorGroupClassFactory, 0, 1u, &GUID_fe4f9dca_ffd8_4d38_932f_282acb3fb775, &ppv);
  if ( v10 < 0 )
  {
    if ( g_wppLevels )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v10);
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v10);
    }
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD, __int64, __int64, __int64))(*(_QWORD *)ppv + 112LL))(
            ppv,
            a1,
            a2,
            a3,
            a4,
            a5,
            a6);
    v10 = v11;
    if ( v11 < 0 && g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v11);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000aa80  push    rbx
0x18000aa82  push    rbp
0x18000aa83  push    rsi
0x18000aa84  push    rdi
0x18000aa85  push    r14
0x18000aa87  sub     rsp, 50h
0x18000aa8b  mov     r14, rcx
0x18000aa8e  mov     rdi, r9
0x18000aa91  xor     ecx, ecx
0x18000aa93  mov     esi, r8d
0x18000aa96  mov     [rsp+78h+var_38], rcx
0x18000aa9b  mov     ebp, edx
0x18000aa9d  cmp     cs:byte_18008D62D, 8
0x18000aaa4  jnb     loc_18000AB59
0x18000aaaa  mov     [rsp+78h+var_38], 0
0x18000aab3  test    rcx, rcx
0x18000aab6  jnz     loc_18000AB82
0x18000aabc  xor     edx, edx; pUnkOuter
0x18000aabe  mov     [rsp+78h+var_38], 0
0x18000aac7  lea     rax, [rsp+78h+var_38]
0x18000aacc  lea     r9, _GUID_fe4f9dca_ffd8_4d38_932f_282acb3fb775; riid
0x18000aad3  mov     [rsp+78h+ppv], rax; ppv
0x18000aad8  lea     rcx, CLSID_MFSensorGroupClassFactory; rclsid
0x18000aadf  lea     r8d, [rdx+1]; dwClsContext
0x18000aae3  call    cs:__imp_CoCreateInstance
0x18000aae9  mov     ebx, eax
0x18000aaeb  test    eax, eax
0x18000aaed  js      loc_18000AB93
0x18000aaf3  mov     rcx, [rsp+78h+var_38]
0x18000aaf8  mov     r9d, esi
0x18000aafb  mov     rdx, [rsp+78h+arg_28]
0x18000ab03  mov     r8d, ebp
0x18000ab06  mov     [rsp+78h+var_48], rdx
0x18000ab0b  mov     rdx, [rsp+78h+arg_20]
0x18000ab13  mov     rax, [rcx]
0x18000ab16  mov     [rsp+78h+var_50], rdx
0x18000ab1b  mov     rdx, r14
0x18000ab1e  mov     [rsp+78h+ppv], rdi
0x18000ab23  mov     rax, [rax+70h]
0x18000ab27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab2c  mov     ebx, eax
0x18000ab2e  test    eax, eax
0x18000ab30  js      loc_18000ABD9
0x18000ab36  mov     rcx, [rsp+78h+var_38]
0x18000ab3b  test    rcx, rcx
0x18000ab3e  jz      short loc_18000AB4C
0x18000ab40  mov     rax, [rcx]
0x18000ab43  mov     rax, [rax+10h]
0x18000ab47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab4c  mov     eax, ebx
0x18000ab4e  add     rsp, 50h
0x18000ab52  pop     r14
0x18000ab54  pop     rdi
0x18000ab55  pop     rsi
0x18000ab56  pop     rbp
0x18000ab57  pop     rbx
0x18000ab58  retn
0x18000ab59  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab60  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x18000ab67  mov     edx, 2Bh ; '+'
0x18000ab6c  mov     rcx, [rcx+0D8h]
0x18000ab73  call    WPP_SF_
0x18000ab78  mov     rcx, [rsp+78h+var_38]
0x18000ab7d  jmp     loc_18000AAAA
0x18000ab82  mov     rax, [rcx]
0x18000ab85  mov     rax, [rax+10h]
0x18000ab89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab8e  jmp     loc_18000AABC
0x18000ab93  mov     al, cs:?g_wppLevels@@3UMFWppLevels@@A; MFWppLevels g_wppLevels
0x18000ab99  cmp     al, 1
0x18000ab9b  jb      short loc_18000AB36
0x18000ab9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aba4  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x18000abab  mov     edx, 0Bh
0x18000abb0  mov     dword ptr [rsp+78h+ppv], ebx
0x18000abb4  xor     r9d, r9d
0x18000abb7  mov     rcx, [rcx+10h]
0x18000abbb  call    WPP_SF_qD
0x18000abc0  mov     al, cs:?g_wppLevels@@3UMFWppLevels@@A; MFWppLevels g_wppLevels
0x18000abc6  cmp     al, 1
0x18000abc8  jb      loc_18000AB36
0x18000abce  mov     edx, 2Ch ; ','
0x18000abd3  mov     dword ptr [rsp+78h+ppv], ebx
0x18000abd7  jmp     short loc_18000ABEF
0x18000abd9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000abe0  jb      loc_18000AB36
0x18000abe6  mov     edx, 2Dh ; '-'
0x18000abeb  mov     dword ptr [rsp+78h+ppv], eax
0x18000abef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abf6  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x18000abfd  xor     r9d, r9d
0x18000ac00  mov     rcx, [rcx+10h]
0x18000ac04  call    WPP_SF_qD
0x18000ac09  jmp     loc_18000AB36
```
