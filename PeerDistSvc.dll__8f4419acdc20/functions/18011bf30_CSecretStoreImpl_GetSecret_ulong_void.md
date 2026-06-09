# CSecretStoreImpl::GetSecret(ulong,void *)

- ea: `0x18011bf30`
- end: `0x18011c354`
- name: `?GetSecret@CSecretStoreImpl@@UEAAJKPEAX@Z`
- size: `1060`
- prototype: `__int64 __fastcall(CSecretStoreImpl *__hidden this, unsigned int, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800024f0`
- `0x180002d36`
- `0x180003498`
- `0x180004374`
- `0x180008290`
- `0x1800083bc`
- `0x18000e330`
- `0x18000fac0`
- `0x18011bf30`
- `0x18011c3cc`
- `0x18011c71c`
- `0x18011c9b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011c0f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011c0f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011c25f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011c25f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011c178`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011c178`

## string_xrefs

- `0x18011c171`: `SecurityManager\Restricted`

## pseudocode

```c
__int64 __fastcall CSecretStoreImpl::GetSecret(RTL_SRWLOCK *this, unsigned int a2, void *a3)
{
  unsigned __int64 v4; // rsi
  void *pvData; // rbx
  CSecretStoreImpl *v7; // rcx
  __int64 v8; // r8
  unsigned int v9; // edi
  CHostedCacheMsgEncoding *v10; // rcx
  __int64 v11; // rdx
  int SecretLengthInternal; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  LSTATUS v15; // eax
  LSTATUS ValueW; // eax
  LSTATUS v17; // eax
  __int64 v18; // rcx
  const char *v19; // r9
  HKEY hkey; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v22[24]; // [rsp+48h] [rbp-18h] BYREF
  DWORD pdwType; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v24; // [rsp+A8h] [rbp+48h] BYREF
  DWORD pcbData; // [rsp+B8h] [rbp+58h] BYREF

  v4 = a2;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 28, "z");
  }
  v24 = 0;
  pcbData = v4;
  pdwType = 0;
  pvData = 0;
  hkey = 0;
  LockSentry<ReadersWriterLock,1>::LockSentry<ReadersWriterLock,1>((__int64)v22, this + 1);
  if ( !CSecretStoreImpl::IsObjectInitialized((CSecretStoreImpl *)this) )
  {
    v9 = -2147020842;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v11 = 29;
LABEL_56:
      WPP_SF_(*((_QWORD *)v10 + 12), v11, "z");
      goto LABEL_57;
    }
    goto LABEL_58;
  }
  if ( (_DWORD)v4 && a3 )
  {
    SecretLengthInternal = CSecretStoreImpl::GetSecretLengthInternal(v7, &v24);
    v9 = SecretLengthInternal;
    if ( SecretLengthInternal >= 0 )
    {
      if ( (_DWORD)v4 != v24 )
      {
        v9 = -2147024809;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v11 = 32;
          goto LABEL_56;
        }
LABEL_58:
        if ( hkey )
        {
          v17 = RegCloseKey(hkey);
          if ( !v17 )
          {
LABEL_67:
            v10 = WPP_GLOBAL_Control;
            goto LABEL_68;
          }
          if ( v17 > 0 )
            v9 = (unsigned __int16)v17 | 0x80070000;
          else
            v9 = v17;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
          {
LABEL_74:
            LockSentry<ReadersWriterLock,1>::Unlock(v22);
            operator delete(pvData);
            return v9;
          }
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 38, "z", v9);
            goto LABEL_67;
          }
        }
LABEL_68:
        if ( v10 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)v10 + 27) & 0x800000) != 0
          && *((_BYTE *)v10 + 105) >= 4u )
        {
          v18 = *((_QWORD *)v10 + 12);
          v19 = "success";
          if ( (v9 & 0x80000000) != 0 )
            v19 = "failure";
          WPP_SF_sd(v18, 39, (unsigned int)"z", (_DWORD)v19, v9);
        }
        goto LABEL_74;
      }
      pvData = operator new[](v4, (const struct std::nothrow_t *)std::nothrow);
      operator delete(0);
      if ( !pvData )
      {
        v9 = -2147024882;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v11 = 33;
          goto LABEL_56;
        }
        goto LABEL_58;
      }
      v15 = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist",
              0,
              0x20119u,
              &hkey);
      if ( v15 )
      {
        if ( v15 > 0 )
          v9 = (unsigned __int16)v15 | 0x80070000;
        else
          v9 = v15;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_58;
        }
        v13 = 34;
      }
      else
      {
        ValueW = RegGetValueW(hkey, L"SecurityManager\\Restricted", L"Seed", 0x1000FFFFu, &pdwType, pvData, &pcbData);
        if ( !ValueW )
        {
          if ( pdwType != 3 )
          {
            v9 = -2147020833;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              v11 = 36;
              goto LABEL_56;
            }
            goto LABEL_58;
          }
          if ( pcbData != (_DWORD)v4 )
          {
            v9 = -2147418113;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              v11 = 37;
              goto LABEL_56;
            }
            goto LABEL_58;
          }
          memcpy_0(a3, pvData, v4);
LABEL_57:
          v10 = WPP_GLOBAL_Control;
          goto LABEL_58;
        }
        if ( ValueW > 0 )
          v9 = (unsigned __int16)ValueW | 0x80070000;
        else
          v9 = ValueW;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_58;
        }
        v13 = 35;
      }
      v14 = v9;
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_58;
      }
      v13 = 31;
      v14 = (unsigned int)SecretLengthInternal;
    }
    WPP_SF_d(*((_QWORD *)v10 + 12), v13, "z", v14);
    goto LABEL_57;
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 12), 30, v8, (unsigned int)v4, a3);
  }
  LockSentry<ReadersWriterLock,1>::Unlock(v22);
  operator delete(0);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18011bf30  push    rbp
0x18011bf32  push    rbx
0x18011bf33  push    rsi
0x18011bf34  push    rdi
0x18011bf35  push    r13
0x18011bf37  push    r14
0x18011bf39  push    r15
0x18011bf3b  mov     rbp, rsp
0x18011bf3e  sub     rsp, 60h
0x18011bf42  mov     r14, r8
0x18011bf45  mov     esi, edx
0x18011bf47  mov     rdi, rcx
0x18011bf4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18011bf51  lea     r15, WPP_GLOBAL_Control
0x18011bf58  mov     r13d, 800000h
0x18011bf5e  cmp     rcx, r15
0x18011bf61  jz      short loc_18011BF84
0x18011bf63  test    [rcx+6Ch], r13d
0x18011bf67  jz      short loc_18011BF84
0x18011bf69  cmp     byte ptr [rcx+69h], 4
0x18011bf6d  jb      short loc_18011BF84
0x18011bf6f  mov     rcx, [rcx+60h]
0x18011bf73  lea     r8, WPP_1049007aec7c3d5a044c075193d085a0_Traceguids; "z"
0x18011bf7a  mov     edx, 1Ch
0x18011bf7f  call    WPP_SF_
0x18011bf84  lea     rdx, [rdi+8]
0x18011bf88  mov     [rbp+arg_8], 0
0x18011bf8f  lea     rcx, [rbp+var_18]
0x18011bf93  mov     [rbp+arg_18], esi
0x18011bf96  mov     [rbp+pdwType], 0
0x18011bf9d  xor     ebx, ebx
0x18011bf9f  mov     [rbp+hkey], 0
0x18011bfa7  call    ??0?$LockSentry@VReadersWriterLock@@$00@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,1>::LockSentry<ReadersWriterLock,1>(ReadersWriterLock &)
0x18011bfac  mov     rcx, rdi; this
0x18011bfaf  call    ?IsObjectInitialized@CSecretStoreImpl@@AEAA_NXZ; CSecretStoreImpl::IsObjectInitialized(void)
0x18011bfb4  test    al, al
0x18011bfb6  jnz     short loc_18011BFE9
0x18011bfb8  mov     edi, 80070FD6h
0x18011bfbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18011bfc4  cmp     rcx, r15
0x18011bfc7  jz      loc_18011C253
0x18011bfcd  test    [rcx+6Ch], r13d
0x18011bfd1  jz      loc_18011C253
0x18011bfd7  cmp     byte ptr [rcx+69h], 1
0x18011bfdb  jb      loc_18011C253
0x18011bfe1  lea     edx, [rbx+1Dh]
0x18011bfe4  jmp     loc_18011C23C
0x18011bfe9  test    esi, esi
0x18011bfeb  jz      loc_18011C302
0x18011bff1  test    r14, r14
0x18011bff4  jz      loc_18011C302
0x18011bffa  lea     rdx, [rbp+arg_8]; unsigned int *
0x18011bffe  call    ?GetSecretLengthInternal@CSecretStoreImpl@@AEAAJPEAK@Z; CSecretStoreImpl::GetSecretLengthInternal(ulong *)
0x18011c003  mov     edi, eax
0x18011c005  test    eax, eax
0x18011c007  jns     short loc_18011C04A
0x18011c009  mov     rcx, cs:WPP_GLOBAL_Control
0x18011c010  cmp     rcx, r15
0x18011c013  jz      loc_18011C253
0x18011c019  test    [rcx+6Ch], r13d
0x18011c01d  jz      loc_18011C253
0x18011c023  cmp     byte ptr [rcx+69h], 1
0x18011c027  jb      loc_18011C253
0x18011c02d  mov     edx, 1Fh
0x18011c032  mov     r9d, eax
0x18011c035  mov     rcx, [rcx+60h]
0x18011c039  lea     r8, WPP_1049007aec7c3d5a044c075193d085a0_Traceguids; "z"
0x18011c040  call    WPP_SF_d
0x18011c045  jmp     loc_18011C24C
0x18011c04a  cmp     esi, [rbp+arg_8]
0x18011c04d  jz      short loc_18011C082
0x18011c04f  mov     edi, 80070057h
0x18011c054  mov     rcx, cs:WPP_GLOBAL_Control
0x18011c05b  cmp     rcx, r15
0x18011c05e  jz      loc_18011C253
0x18011c064  test    [rcx+6Ch], r13d
0x18011c068  jz      loc_18011C253
0x18011c06e  cmp     byte ptr [rcx+69h], 1
0x18011c072  jb      loc_18011C253
0x18011c078  mov     edx, 20h ; ' '
0x18011c07d  jmp     loc_18011C23C
0x18011c082  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18011c089  mov     rcx, rsi; unsigned __int64
0x18011c08c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18011c091  xor     ecx, ecx; Block
0x18011c093  mov     rbx, rax
0x18011c096  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011c09b  test    rbx, rbx
0x18011c09e  jnz     short loc_18011C0D8
0x18011c0a0  mov     edi, 8007000Eh
0x18011c0a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18011c0ac  lea     r15, WPP_GLOBAL_Control
0x18011c0b3  cmp     rcx, r15
0x18011c0b6  jz      loc_18011C253
0x18011c0bc  test    [rcx+6Ch], r13d
0x18011c0c0  jz      loc_18011C253
0x18011c0c6  cmp     byte ptr [rcx+69h], 1
0x18011c0ca  jb      loc_18011C253
0x18011c0d0  lea     edx, [rbx+21h]
0x18011c0d3  jmp     loc_18011C23C
0x18011c0d8  lea     rax, [rbp+hkey]
0x18011c0dc  mov     r9d, 20119h; samDesired
0x18011c0e2  xor     r8d, r8d; ulOptions
0x18011c0e5  mov     [rsp+60h+phkResult], rax; phkResult
0x18011c0ea  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x18011c0f1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18011c0f8  call    cs:__imp_RegOpenKeyExW
0x18011c0fe  test    eax, eax
0x18011c100  jz      short loc_18011C149
0x18011c102  jg      short loc_18011C108
0x18011c104  mov     edi, eax
0x18011c106  jmp     short loc_18011C111
0x18011c108  movzx   edi, ax
0x18011c10b  or      edi, 80070000h
0x18011c111  mov     rcx, cs:WPP_GLOBAL_Control
0x18011c118  lea     r15, WPP_GLOBAL_Control
0x18011c11f  cmp     rcx, r15
0x18011c122  jz      loc_18011C253
0x18011c128  test    [rcx+6Ch], r13d
0x18011c12c  jz      loc_18011C253
0x18011c132  cmp     byte ptr [rcx+69h], 1
0x18011c136  jb      loc_18011C253
0x18011c13c  mov     edx, 22h ; '"'
0x18011c141  mov     r9d, edi
0x18011c144  jmp     loc_18011C035
0x18011c149  mov     rcx, [rbp+hkey]; hkey
0x18011c14d  lea     rax, [rbp+arg_18]
0x18011c151  mov     [rsp+60h+pcbData], rax; pcbData
0x18011c156  lea     r8, Value; "Seed"
0x18011c15d  lea     rax, [rbp+pdwType]
0x18011c161  mov     [rsp+60h+pvData], rbx; pvData
0x18011c166  mov     r9d, 1000FFFFh; dwFlags
0x18011c16c  mov     [rsp+60h+phkResult], rax; pdwType
0x18011c171  lea     rdx, aSecuritymanage_1; "SecurityManager\\Restricted"
0x18011c178  call    cs:__imp_RegGetValueW
0x18011c17e  test    eax, eax
0x18011c180  jz      short loc_18011C1C6
0x18011c182  jg      short loc_18011C188
0x18011c184  mov     edi, eax
0x18011c186  jmp     short loc_18011C191
0x18011c188  movzx   edi, ax
0x18011c18b  or      edi, 80070000h
0x18011c191  mov     rcx, cs:WPP_GLOBAL_Control
0x18011c198  lea     r15, WPP_GLOBAL_Control
0x18011c19f  cmp     rcx, r15
0x18011c1a2  jz      loc_18011C253
0x18011c1a8  test    [rcx+6Ch], r13d
0x18011c1ac  jz      loc_18011C253
0x18011c1b2  cmp     byte ptr [rcx+69h], 1
0x18011c1b6  jb      loc_18011C253
0x18011c1bc  mov     edx, 23h ; '#'
0x18011c1c1  jmp     loc_18011C141
0x18011c1c6  cmp     [rbp+pdwType], 3
0x18011c1ca  jz      short loc_18011C1F7
0x18011c1cc  mov     edi, 80070FDFh
0x18011c1d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18011c1d8  lea     r15, WPP_GLOBAL_Control
0x18011c1df  cmp     rcx, r15
0x18011c1e2  jz      short loc_18011C253
0x18011c1e4  test    [rcx+6Ch], r13d
0x18011c1e8  jz      short loc_18011C253
0x18011c1ea  cmp     byte ptr [rcx+69h], 1
0x18011c1ee  jb      short loc_18011C253
0x18011c1f0  mov     edx, 24h ; '$'
0x18011c1f5  jmp     short loc_18011C23C
0x18011c1f7  cmp     [rbp+arg_18], esi
0x18011c1fa  jnz     short loc_18011C213
0x18011c1fc  mov     r8, rsi; Size
0x18011c1ff  mov     rdx, rbx; Src
0x18011c202  mov     rcx, r14; void *
0x18011c205  call    memcpy_0
0x18011c20a  lea     r15, WPP_GLOBAL_Control
0x18011c211  jmp     short loc_18011C24C
0x18011c213  mov     edi, 8000FFFFh
0x18011c218  mov     rcx, cs:WPP_GLOBAL_Control
0x18011c21f  lea     r15, WPP_GLOBAL_Control
0x18011c226  cmp     rcx, r15
0x18011c229  jz      short loc_18011C253
0x18011c22b  test    [rcx+6Ch], r13d
0x18011c22f  jz      short loc_18011C253
0x18011c231  cmp     byte ptr [rcx+69h], 1
0x18011c235  jb      short loc_18011C253
0x18011c237  mov     edx, 25h ; '%'
0x18011c23c  mov     rcx, [rcx+60h]
0x18011c240  lea     r8, WPP_1049007aec7c3d5a044c075193d085a0_Traceguids; "z"
0x18011c247  call    WPP_SF_
0x18011c24c  mov     rcx, cs:WPP_GLOBAL_Control
0x18011c253  mov     rax, [rbp+hkey]
0x18011c257  test    rax, rax
0x18011c25a  jz      short loc_18011C2AF
0x18011c25c  mov     rcx, rax; hKey
0x18011c25f  call    cs:__imp_RegCloseKey
0x18011c265  test    eax, eax
0x18011c267  jz      short loc_18011C2A8
0x18011c269  jg      short loc_18011C26F
0x18011c26b  mov     edi, eax
0x18011c26d  jmp     short loc_18011C278
0x18011c26f  movzx   edi, ax
0x18011c272  or      edi, 80070000h
0x18011c278  mov     rcx, cs:WPP_GLOBAL_Control
0x18011c27f  cmp     rcx, r15
0x18011c282  jz      short loc_18011C2ED
0x18011c284  test    [rcx+6Ch], r13d
0x18011c288  jz      short loc_18011C2AF
0x18011c28a  cmp     byte ptr [rcx+69h], 1
0x18011c28e  jb      short loc_18011C2AF
0x18011c290  mov     rcx, [rcx+60h]
0x18011c294  lea     r8, WPP_1049007aec7c3d5a044c075193d085a0_Traceguids; "z"
0x18011c29b  mov     edx, 26h ; '&'
0x18011c2a0  mov     r9d, edi
0x18011c2a3  call    WPP_SF_d
0x18011c2a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18011c2af  cmp     rcx, r15
0x18011c2b2  jz      short loc_18011C2ED
0x18011c2b4  test    [rcx+6Ch], r13d
0x18011c2b8  jz      short loc_18011C2ED
0x18011c2ba  cmp     byte ptr [rcx+69h], 4
0x18011c2be  jb      short loc_18011C2ED
0x18011c2c0  mov     rcx, [rcx+60h]
0x18011c2c4  lea     rax, aFailure; "failure"
0x18011c2cb  test    edi, edi
0x18011c2cd  mov     dword ptr [rsp+60h+phkResult], edi
0x18011c2d1  lea     r9, aSuccess; "success"
0x18011c2d8  mov     edx, 27h ; '''
0x18011c2dd  cmovs   r9, rax
0x18011c2e1  lea     r8, WPP_1049007aec7c3d5a044c075193d085a0_Traceguids; "z"
0x18011c2e8  call    WPP_SF_sd
0x18011c2ed  lea     rcx, [rbp+var_18]
0x18011c2f1  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$00@@QEAAXXZ; LockSentry<ReadersWriterLock,1>::Unlock(void)
0x18011c2f6  mov     rcx, rbx; Block
0x18011c2f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011c2fe  mov     eax, edi
0x18011c300  jmp     short loc_18011C345
0x18011c302  mov     rcx, cs:WPP_GLOBAL_Control
0x18011c309  cmp     rcx, r15
0x18011c30c  jz      short loc_18011C330
0x18011c30e  test    [rcx+6Ch], r13d
0x18011c312  jz      short loc_18011C330
0x18011c314  cmp     byte ptr [rcx+69h], 1
0x18011c318  jb      short loc_18011C330
0x18011c31a  mov     rcx, [rcx+60h]
0x18011c31e  mov     edx, 1Eh
0x18011c323  mov     r9d, esi
0x18011c326  mov     [rsp+60h+phkResult], r14
0x18011c32b  call    WPP_SF_Lq
0x18011c330  lea     rcx, [rbp+var_18]
0x18011c334  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$00@@QEAAXXZ; LockSentry<ReadersWriterLock,1>::Unlock(void)
0x18011c339  xor     ecx, ecx; Block
0x18011c33b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011c340  mov     eax, 80070057h
0x18011c345  add     rsp, 60h
0x18011c349  pop     r15
0x18011c34b  pop     r14
0x18011c34d  pop     r13
0x18011c34f  pop     rdi
0x18011c350  pop     rsi
0x18011c351  pop     rbx
0x18011c352  pop     rbp
0x18011c353  retn
```
