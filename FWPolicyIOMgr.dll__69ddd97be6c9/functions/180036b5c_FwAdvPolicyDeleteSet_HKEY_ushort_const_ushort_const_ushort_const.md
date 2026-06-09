# FwAdvPolicyDeleteSet(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x180036b5c`
- end: `0x180036d35`
- name: `?FwAdvPolicyDeleteSet@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `473`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f360`

## callees

- `0x1800042c4`
- `0x18001e9ac`
- `0x18001ec98`
- `0x18001f650`
- `0x180036b5c`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180036c7a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180036c7a`
- `fwbase!FwFree` at `0x180036d0c`
- `fwbase!FwFree` at `0x180036d0c`
- `fwbase!FwRegOpenKey` at `0x180036bbe`
- `fwbase!FwRegOpenKey` at `0x180036bbe`
- `fwbase!FwRegCloseKey` at `0x180036d16`
- `fwbase!FwRegCloseKey` at `0x180036d16`
- `fwbase!FwRegDeleteKey` at `0x180036c92`
- `fwbase!FwRegDeleteKey` at `0x180036c92`
- `fwbase!FwRegDeleteValue` at `0x180036ccb`
- `fwbase!FwRegDeleteValue` at `0x180036ccb`

## pseudocode

```c
__int64 __fastcall FwAdvPolicyDeleteSet(
        HKEY a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int MergedGPODefaultID; // ebx
  LPCOLESTR v9; // rcx
  __int64 v10; // rdx
  int v11; // edi
  HKEY v13; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v14; // [rsp+38h] [rbp-18h] BYREF
  int v15; // [rsp+40h] [rbp-10h] BYREF

  v13 = 0;
  v15 = 0;
  v14 = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  MergedGPODefaultID = FwRegOpenKey(a1, a2, 65547, &v13, &v15);
  if ( MergedGPODefaultID >= 0 )
  {
    if ( v15 )
    {
      MergedGPODefaultID = FwGetMergedGPODefaultID(v13, a4, &v14);
      if ( MergedGPODefaultID >= 0 )
      {
        v11 = 0;
        if ( v14 && !lstrcmpiW(a4, a3) )
        {
          a3 = v14;
          v11 = 1;
        }
        MergedGPODefaultID = FwRegDeleteKey(v13, a3);
        if ( MergedGPODefaultID >= 0 )
        {
          if ( v11 )
          {
            MergedGPODefaultID = FwRegDeleteValue(v13, 0, a4);
            if ( MergedGPODefaultID < 0 )
            {
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v10 = 52;
                goto LABEL_27;
              }
            }
          }
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v10 = 51;
            goto LABEL_27;
          }
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v10 = 50;
          goto LABEL_27;
        }
      }
    }
    else
    {
      MergedGPODefaultID = -2147024894;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v10 = 49;
        goto LABEL_27;
      }
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v10 = 48;
LABEL_27:
      WPP_SF_d(
        *((_QWORD *)v9 + 2),
        v10,
        WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids,
        (unsigned int)MergedGPODefaultID);
    }
  }
  FwFree(v14);
  FwRegCloseKey(v13);
  return (unsigned int)MergedGPODefaultID;
}

```

## disassembly

```asm
0x180036b5c  push    rbp
0x180036b5e  push    rbx
0x180036b5f  push    rsi
0x180036b60  push    rdi
0x180036b61  push    r14
0x180036b63  mov     rbp, rsp
0x180036b66  sub     rsp, 50h
0x180036b6a  mov     rax, cs:__security_cookie
0x180036b71  xor     rax, rsp
0x180036b74  mov     [rbp+var_8], rax
0x180036b78  mov     [rbp+var_20], 0
0x180036b80  mov     r14, r9
0x180036b83  mov     [rbp+var_10], 0
0x180036b8a  mov     rsi, r8
0x180036b8d  mov     [rbp+var_18], 0
0x180036b95  mov     rdi, rdx
0x180036b98  mov     rbx, rcx
0x180036b9b  test    rcx, rcx
0x180036b9e  jnz     short loc_180036BA5
0x180036ba0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180036ba5  lea     rax, [rbp+var_10]
0x180036ba9  mov     r8d, 1000Bh
0x180036baf  lea     r9, [rbp+var_20]
0x180036bb3  mov     [rsp+50h+var_30], rax
0x180036bb8  mov     rdx, rdi
0x180036bbb  mov     rcx, rbx
0x180036bbe  call    cs:__imp_FwRegOpenKey
0x180036bc4  mov     ebx, eax
0x180036bc6  test    eax, eax
0x180036bc8  jns     short loc_180036BF5
0x180036bca  mov     rcx, cs:WPP_GLOBAL_Control
0x180036bd1  lea     rax, WPP_GLOBAL_Control
0x180036bd8  cmp     rcx, rax
0x180036bdb  jz      loc_180036D08
0x180036be1  test    byte ptr [rcx+1Ch], 1
0x180036be5  jz      loc_180036D08
0x180036beb  mov     edx, 30h ; '0'
0x180036bf0  jmp     loc_180036CF5
0x180036bf5  cmp     [rbp+var_10], 0
0x180036bf9  jnz     short loc_180036C2B
0x180036bfb  mov     ebx, 80070002h
0x180036c00  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c07  lea     rax, WPP_GLOBAL_Control
0x180036c0e  cmp     rcx, rax
0x180036c11  jz      loc_180036D08
0x180036c17  test    byte ptr [rcx+1Ch], 1
0x180036c1b  jz      loc_180036D08
0x180036c21  mov     edx, 31h ; '1'
0x180036c26  jmp     loc_180036CF5
0x180036c2b  mov     rcx, [rbp+var_20]; HKEY
0x180036c2f  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180036c33  mov     rdx, r14; unsigned __int16 *
0x180036c36  call    ?FwGetMergedGPODefaultID@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; FwGetMergedGPODefaultID(HKEY__ *,ushort const *,ushort * *)
0x180036c3b  mov     ebx, eax
0x180036c3d  test    eax, eax
0x180036c3f  jns     short loc_180036C6C
0x180036c41  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c48  lea     rax, WPP_GLOBAL_Control
0x180036c4f  cmp     rcx, rax
0x180036c52  jz      loc_180036D08
0x180036c58  test    byte ptr [rcx+1Ch], 1
0x180036c5c  jz      loc_180036D08
0x180036c62  mov     edx, 32h ; '2'
0x180036c67  jmp     loc_180036CF5
0x180036c6c  xor     edi, edi
0x180036c6e  cmp     [rbp+var_18], rdi
0x180036c72  jz      short loc_180036C8B
0x180036c74  mov     rdx, rsi; lpString2
0x180036c77  mov     rcx, r14; lpString1
0x180036c7a  call    cs:__imp_lstrcmpiW
0x180036c80  test    eax, eax
0x180036c82  jnz     short loc_180036C8B
0x180036c84  mov     rsi, [rbp+var_18]
0x180036c88  lea     edi, [rax+1]
0x180036c8b  mov     rcx, [rbp+var_20]
0x180036c8f  mov     rdx, rsi
0x180036c92  call    cs:__imp_FwRegDeleteKey
0x180036c98  mov     ebx, eax
0x180036c9a  test    eax, eax
0x180036c9c  jns     short loc_180036CBE
0x180036c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ca5  lea     rax, WPP_GLOBAL_Control
0x180036cac  cmp     rcx, rax
0x180036caf  jz      short loc_180036D08
0x180036cb1  test    byte ptr [rcx+1Ch], 1
0x180036cb5  jz      short loc_180036D08
0x180036cb7  mov     edx, 33h ; '3'
0x180036cbc  jmp     short loc_180036CF5
0x180036cbe  test    edi, edi
0x180036cc0  jz      short loc_180036D08
0x180036cc2  mov     rcx, [rbp+var_20]
0x180036cc6  mov     r8, r14
0x180036cc9  xor     edx, edx
0x180036ccb  call    cs:__imp_FwRegDeleteValue
0x180036cd1  mov     ebx, eax
0x180036cd3  test    eax, eax
0x180036cd5  jns     short loc_180036D08
0x180036cd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180036cde  lea     rax, WPP_GLOBAL_Control
0x180036ce5  cmp     rcx, rax
0x180036ce8  jz      short loc_180036D08
0x180036cea  test    byte ptr [rcx+1Ch], 1
0x180036cee  jz      short loc_180036D08
0x180036cf0  mov     edx, 34h ; '4'
0x180036cf5  mov     rcx, [rcx+10h]
0x180036cf9  lea     r8, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids
0x180036d00  mov     r9d, ebx
0x180036d03  call    WPP_SF_d
0x180036d08  mov     rcx, [rbp+var_18]
0x180036d0c  call    cs:__imp_FwFree
0x180036d12  mov     rcx, [rbp+var_20]
0x180036d16  call    cs:__imp_FwRegCloseKey
0x180036d1c  mov     eax, ebx
0x180036d1e  mov     rcx, [rbp+var_8]
0x180036d22  xor     rcx, rsp; StackCookie
0x180036d25  call    __security_check_cookie
0x180036d2a  add     rsp, 50h
0x180036d2e  pop     r14
0x180036d30  pop     rdi
0x180036d31  pop     rsi
0x180036d32  pop     rbx
0x180036d33  pop     rbp
0x180036d34  retn
```
