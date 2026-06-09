# ApplyExternalDMAPolicy(void)

- ea: `0x18001ba30`
- end: `0x18001bd31`
- name: `?ApplyExternalDMAPolicy@@YAXXZ`
- size: `769`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18001b8c0`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18001ba30`
- `0x18001bd38`
- `0x18001c170`
- `0x180024280`
- `0x180034070`
- `0x18003447c`
- `0x1800686d0`
- `0x180068824`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001bc98`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001bc98`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001bbbe`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001bbbe`

## string_xrefs

- `0x18001bbb0`: `AllowDirectMemoryAccess`

## pseudocode

```c
void ApplyExternalDMAPolicy(void)
{
  CFvePolicyImpl *v0; // rdi
  int v1; // r14d
  CFvePolicyImpl *v2; // rax
  CFvePolicyImpl *v3; // rax
  CFvePolicyImpl *v4; // rbx
  unsigned int v5; // edx
  int v6; // esi
  int DefaultPolicyDword; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  int PolicyInt; // eax
  unsigned int v12; // edx
  unsigned int v13; // ebx
  int v14; // esi
  PVOID *v15; // rcx
  __int64 v16; // rdx
  LSTATUS v17; // eax
  unsigned int v18; // [rsp+30h] [rbp-30h] BYREF
  int v19; // [rsp+34h] [rbp-2Ch] BYREF
  int v20; // [rsp+38h] [rbp-28h] BYREF
  void **v21; // [rsp+40h] [rbp-20h]
  CFvePolicyImpl *v22; // [rsp+48h] [rbp-18h]
  int Data; // [rsp+50h] [rbp-10h] BYREF
  int v24; // [rsp+54h] [rbp-Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
  Data = 0;
  v21 = &CFvePolicy::`vftable';
  v0 = 0;
  v22 = 0;
  v20 = 0;
  v19 = 0;
  v24 = 1;
  v1 = 0;
  v2 = (CFvePolicyImpl *)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 && (v3 = CFvePolicyImpl::CFvePolicyImpl(v2), (v4 = v3) != 0) )
  {
    v6 = (**(__int64 (__fastcall ***)(CFvePolicyImpl *, _QWORD))v3)(v3, 0);
    if ( v6 >= 0 )
    {
      v0 = v4;
      v22 = v4;
      v4 = 0;
    }
    if ( v4 )
      CFvePolicyImpl::`scalar deleting destructor'(v4, v5);
    if ( v6 >= 0 )
    {
      v18 = 0;
      DefaultPolicyDword = CFvePolicySettings::ReadPolicyDword((char *)v0 + 160, 165, &v18, &v19);
      if ( DefaultPolicyDword >= 0 )
      {
        if ( (int)CFvePolicySettings::DwordToBool(v18, &v20) >= 0 )
        {
LABEL_16:
          v1 = 1;
          goto LABEL_25;
        }
        DefaultPolicyDword = CFvePolicySettings::GetDefaultPolicyDword(165, &v18);
        if ( DefaultPolicyDword >= 0 )
        {
          DefaultPolicyDword = CFvePolicySettings::DwordToBool(v18, &v20);
          if ( DefaultPolicyDword >= 0 )
          {
            v19 = 0;
            goto LABEL_16;
          }
        }
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v9 = 139;
        v10 = (unsigned int)DefaultPolicyDword;
LABEL_24:
        WPP_SF_d(v8[2], v9, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v10);
        goto LABEL_25;
      }
      goto LABEL_25;
    }
  }
  else
  {
    v6 = -2147024882;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v9 = 138;
    v10 = (unsigned int)v6;
    goto LABEL_24;
  }
LABEL_25:
  PolicyInt = PolicyManager_GetPolicyInt(L"DataProtection", L"AllowDirectMemoryAccess", &v24);
  v13 = PolicyInt;
  if ( PolicyInt >= 0 )
  {
    v14 = 1;
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v14 = 0;
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        140,
        WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
        (unsigned int)PolicyInt);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    v13 = 0;
  }
  if ( v1 && v19 && v20 || v14 && !v24 )
  {
    Data = 1;
    if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 8) == 0 )
      goto LABEL_45;
    v16 = 141;
LABEL_44:
    WPP_SF_(v15[2], v16, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
LABEL_45:
    v17 = RegSetKeyValueW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Control\\pnp\\pci",
            L"DisableExternalDMAUnderLock",
            4u,
            &Data,
            4u);
    if ( v17 > 0 )
    {
      v13 = (unsigned __int16)v17 | 0x80070000;
    }
    else if ( v17 )
    {
      v13 = v17;
    }
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_54;
  }
  if ( v1 && v14 )
  {
    Data = 0;
    if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 8) == 0 )
      goto LABEL_45;
    v16 = 142;
    goto LABEL_44;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
  {
    WPP_SF_(v15[2], 143, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  v13 = 1;
LABEL_54:
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x20) != 0 )
    WPP_SF_d(v15[2], 144, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v13);
  if ( v0 )
    CFvePolicyImpl::`scalar deleting destructor'(v0, v12);
}

```

## disassembly

```asm
0x18001ba30  push    rbp
0x18001ba32  push    rbx
0x18001ba33  push    rsi
0x18001ba34  push    rdi
0x18001ba35  push    r12
0x18001ba37  push    r13
0x18001ba39  push    r14
0x18001ba3b  mov     rbp, rsp
0x18001ba3e  sub     rsp, 60h
0x18001ba42  mov     rax, cs:__security_cookie
0x18001ba49  xor     rax, rsp
0x18001ba4c  mov     [rbp+var_8], rax
0x18001ba50  lea     r12, WPP_GLOBAL_Control
0x18001ba57  lea     r13, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18001ba5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba65  cmp     rcx, r12
0x18001ba68  jz      short loc_18001BA81
0x18001ba6a  test    byte ptr [rcx+1Ch], 20h
0x18001ba6e  jz      short loc_18001BA81
0x18001ba70  mov     edx, 89h
0x18001ba75  mov     r8, r13
0x18001ba78  mov     rcx, [rcx+10h]
0x18001ba7c  call    WPP_SF_
0x18001ba81  mov     [rbp+Data], 0
0x18001ba88  lea     rax, ??_7CFvePolicy@@6B@; const CFvePolicy::`vftable'
0x18001ba8f  mov     [rbp+var_20], rax
0x18001ba93  xor     edi, edi
0x18001ba95  mov     [rbp+var_18], rdi
0x18001ba99  mov     [rbp+var_28], edi
0x18001ba9c  mov     [rbp+var_2C], edi
0x18001ba9f  mov     [rbp+var_C], 1
0x18001baa6  xor     r14d, r14d
0x18001baa9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bab0  mov     ecx, 0B8h; unsigned __int64
0x18001bab5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001baba  test    rax, rax
0x18001babd  jz      loc_18001BB81
0x18001bac3  mov     rcx, rax; this
0x18001bac6  call    ??0CFvePolicyImpl@@QEAA@XZ; CFvePolicyImpl::CFvePolicyImpl(void)
0x18001bacb  mov     rbx, rax
0x18001bace  test    rax, rax
0x18001bad1  jz      loc_18001BB81
0x18001bad7  mov     rax, [rax]
0x18001bada  xor     edx, edx
0x18001badc  mov     rcx, rbx
0x18001badf  mov     rax, [rax]
0x18001bae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bae7  mov     esi, eax
0x18001bae9  test    eax, eax
0x18001baeb  js      short loc_18001BAF6
0x18001baed  mov     rdi, rbx
0x18001baf0  mov     [rbp+var_18], rbx
0x18001baf4  xor     ebx, ebx
0x18001baf6  test    rbx, rbx
0x18001baf9  jz      short loc_18001BB03
0x18001bafb  mov     rcx, rbx; this
0x18001bafe  call    ??_GCFvePolicyImpl@@QEAAPEAXI@Z; CFvePolicyImpl::`scalar deleting destructor'(uint)
0x18001bb03  test    esi, esi
0x18001bb05  js      short loc_18001BB86
0x18001bb07  mov     [rbp+var_30], r14d
0x18001bb0b  lea     rcx, [rdi+0A0h]
0x18001bb12  lea     r9, [rbp+var_2C]
0x18001bb16  lea     r8, [rbp+var_30]
0x18001bb1a  mov     ebx, 0A5h
0x18001bb1f  mov     edx, ebx
0x18001bb21  call    ?ReadPolicyDword@CFvePolicySettings@@IEBAJW4eFveGpDwSetting@@PEAKPEAH@Z; CFvePolicySettings::ReadPolicyDword(eFveGpDwSetting,ulong *,int *)
0x18001bb26  test    eax, eax
0x18001bb28  js      short loc_18001BB65
0x18001bb2a  lea     rdx, [rbp+var_28]; int *
0x18001bb2e  mov     ecx, [rbp+var_30]; unsigned int
0x18001bb31  call    ?DwordToBool@CFvePolicySettings@@KAJKPEAH@Z; CFvePolicySettings::DwordToBool(ulong,int *)
0x18001bb36  test    eax, eax
0x18001bb38  jns     short loc_18001BB5D
0x18001bb3a  lea     rdx, [rbp+var_30]
0x18001bb3e  mov     ecx, ebx
0x18001bb40  call    ?GetDefaultPolicyDword@CFvePolicySettings@@KAJW4eFveGpDwSetting@@PEAK@Z; CFvePolicySettings::GetDefaultPolicyDword(eFveGpDwSetting,ulong *)
0x18001bb45  test    eax, eax
0x18001bb47  js      short loc_18001BB65
0x18001bb49  lea     rdx, [rbp+var_28]; int *
0x18001bb4d  mov     ecx, [rbp+var_30]; unsigned int
0x18001bb50  call    ?DwordToBool@CFvePolicySettings@@KAJKPEAH@Z; CFvePolicySettings::DwordToBool(ulong,int *)
0x18001bb55  test    eax, eax
0x18001bb57  js      short loc_18001BB65
0x18001bb59  mov     [rbp+var_2C], r14d
0x18001bb5d  mov     r14d, 1
0x18001bb63  jmp     short loc_18001BBAC
0x18001bb65  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb6c  cmp     rcx, r12
0x18001bb6f  jz      short loc_18001BBAC
0x18001bb71  test    byte ptr [rcx+1Ch], 2
0x18001bb75  jz      short loc_18001BBAC
0x18001bb77  mov     edx, 8Bh
0x18001bb7c  mov     r9d, eax
0x18001bb7f  jmp     short loc_18001BBA0
0x18001bb81  mov     esi, 8007000Eh
0x18001bb86  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb8d  cmp     rcx, r12
0x18001bb90  jz      short loc_18001BBAC
0x18001bb92  test    byte ptr [rcx+1Ch], 2
0x18001bb96  jz      short loc_18001BBAC
0x18001bb98  mov     edx, 8Ah
0x18001bb9d  mov     r9d, esi
0x18001bba0  mov     r8, r13
0x18001bba3  mov     rcx, [rcx+10h]
0x18001bba7  call    WPP_SF_d
0x18001bbac  lea     r8, [rbp+var_C]
0x18001bbb0  lea     rdx, aAllowdirectmem; "AllowDirectMemoryAccess"
0x18001bbb7  lea     rcx, aDataprotection; "DataProtection"
0x18001bbbe  call    cs:__imp_PolicyManager_GetPolicyInt
0x18001bbc5  nop     dword ptr [rax+rax+00h]
0x18001bbca  mov     ebx, eax
0x18001bbcc  test    eax, eax
0x18001bbce  jns     short loc_18001BC03
0x18001bbd0  xor     esi, esi
0x18001bbd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbd9  cmp     rcx, r12
0x18001bbdc  jz      short loc_18001BBFF
0x18001bbde  test    byte ptr [rcx+1Ch], 2
0x18001bbe2  jz      short loc_18001BBFF
0x18001bbe4  mov     edx, 8Ch
0x18001bbe9  mov     r9d, eax
0x18001bbec  mov     r8, r13
0x18001bbef  mov     rcx, [rcx+10h]
0x18001bbf3  call    WPP_SF_d
0x18001bbf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbff  xor     ebx, ebx
0x18001bc01  jmp     short loc_18001BC0F
0x18001bc03  mov     esi, 1
0x18001bc08  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc0f  test    r14d, r14d
0x18001bc12  jz      short loc_18001BC20
0x18001bc14  cmp     [rbp+var_2C], 0
0x18001bc18  jz      short loc_18001BC20
0x18001bc1a  cmp     [rbp+var_28], 0
0x18001bc1e  jnz     short loc_18001BC2A
0x18001bc20  test    esi, esi
0x18001bc22  jz      short loc_18001BC43
0x18001bc24  cmp     [rbp+var_C], 0
0x18001bc28  jnz     short loc_18001BC43
0x18001bc2a  mov     [rbp+Data], 1
0x18001bc31  cmp     rcx, r12
0x18001bc34  jz      short loc_18001BC6F
0x18001bc36  test    byte ptr [rcx+1Ch], 8
0x18001bc3a  jz      short loc_18001BC6F
0x18001bc3c  mov     edx, 8Dh
0x18001bc41  jmp     short loc_18001BC63
0x18001bc43  test    r14d, r14d
0x18001bc46  jz      short loc_18001BCC0
0x18001bc48  test    esi, esi
0x18001bc4a  jz      short loc_18001BCC0
0x18001bc4c  mov     [rbp+Data], 0
0x18001bc53  cmp     rcx, r12
0x18001bc56  jz      short loc_18001BC6F
0x18001bc58  test    byte ptr [rcx+1Ch], 8
0x18001bc5c  jz      short loc_18001BC6F
0x18001bc5e  mov     edx, 8Eh
0x18001bc63  mov     r8, r13
0x18001bc66  mov     rcx, [rcx+10h]
0x18001bc6a  call    WPP_SF_
0x18001bc6f  mov     r9d, 4; dwType
0x18001bc75  mov     [rsp+60h+cbData], r9d; cbData
0x18001bc7a  lea     rax, [rbp+Data]
0x18001bc7e  mov     [rsp+60h+lpData], rax; lpData
0x18001bc83  lea     r8, ValueName; "DisableExternalDMAUnderLock"
0x18001bc8a  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Control\\pnp"...
0x18001bc91  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001bc98  call    cs:__imp_RegSetKeyValueW
0x18001bc9f  nop     dword ptr [rax+rax+00h]
0x18001bca4  test    eax, eax
0x18001bca6  jg      short loc_18001BCAE
0x18001bca8  jz      short loc_18001BCB7
0x18001bcaa  mov     ebx, eax
0x18001bcac  jmp     short loc_18001BCB7
0x18001bcae  movzx   ebx, ax
0x18001bcb1  or      ebx, 80070000h
0x18001bcb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bcbe  jmp     short loc_18001BCE8
0x18001bcc0  cmp     rcx, r12
0x18001bcc3  jz      short loc_18001BCE3
0x18001bcc5  test    byte ptr [rcx+1Ch], 8
0x18001bcc9  jz      short loc_18001BCE3
0x18001bccb  mov     edx, 8Fh
0x18001bcd0  mov     r8, r13
0x18001bcd3  mov     rcx, [rcx+10h]
0x18001bcd7  call    WPP_SF_
0x18001bcdc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bce3  mov     ebx, 1
0x18001bce8  cmp     rcx, r12
0x18001bceb  jz      short loc_18001BD08
0x18001bced  test    byte ptr [rcx+1Ch], 20h
0x18001bcf1  jz      short loc_18001BD08
0x18001bcf3  mov     edx, 90h
0x18001bcf8  mov     r9d, ebx
0x18001bcfb  mov     r8, r13
0x18001bcfe  mov     rcx, [rcx+10h]
0x18001bd02  call    WPP_SF_d
0x18001bd07  nop
0x18001bd08  test    rdi, rdi
0x18001bd0b  jz      short loc_18001BD15
0x18001bd0d  mov     rcx, rdi; this
0x18001bd10  call    ??_GCFvePolicyImpl@@QEAAPEAXI@Z; CFvePolicyImpl::`scalar deleting destructor'(uint)
0x18001bd15  mov     rcx, [rbp+var_8]
0x18001bd19  xor     rcx, rsp; StackCookie
0x18001bd1c  call    __security_check_cookie
0x18001bd21  add     rsp, 60h
0x18001bd25  pop     r14
0x18001bd27  pop     r13
0x18001bd29  pop     r12
0x18001bd2b  pop     rdi
0x18001bd2c  pop     rsi
0x18001bd2d  pop     rbx
0x18001bd2e  pop     rbp
0x18001bd2f  retn
```
