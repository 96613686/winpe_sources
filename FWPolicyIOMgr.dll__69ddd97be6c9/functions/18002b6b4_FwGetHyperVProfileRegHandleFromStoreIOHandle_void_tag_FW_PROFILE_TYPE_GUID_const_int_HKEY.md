# FwGetHyperVProfileRegHandleFromStoreIOHandle(void *,_tag_FW_PROFILE_TYPE,_GUID const &,int,HKEY__ * *)

- ea: `0x18002b6b4`
- end: `0x18002b928`
- name: `?FwGetHyperVProfileRegHandleFromStoreIOHandle@@YAJPEAXW4_tag_FW_PROFILE_TYPE@@AEBU_GUID@@HPEAPEAUHKEY__@@@Z`
- size: `628`
- prototype: `__int64 __fastcall(__int64, unsigned int, const GUID *, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002dcb0`

## callees

- `0x1800042c4`
- `0x18001f650`
- `0x18001ffd4`
- `0x18002b6b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b76a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b76a`
- `fwbase!FwRegOpenKey` at `0x18002b86b`
- `fwbase!FwRegOpenKey` at `0x18002b8a0`
- `fwbase!FwRegOpenKey` at `0x18002b86b`
- `fwbase!FwRegOpenKey` at `0x18002b8a0`
- `fwbase!FwGetProfileIndexFromProfileType` at `0x18002b708`
- `fwbase!FwGetProfileIndexFromProfileType` at `0x18002b708`
- `fwbase!FwRegCreateKey` at `0x18002b7ca`
- `fwbase!FwRegCreateKey` at `0x18002b828`
- `fwbase!FwRegCreateKey` at `0x18002b7ca`
- `fwbase!FwRegCreateKey` at `0x18002b828`

## pseudocode

```c
__int64 __fastcall FwGetHyperVProfileRegHandleFromStoreIOHandle(
        __int64 a1,
        unsigned int a2,
        const GUID *a3,
        int a4,
        __int64 a5)
{
  int ProfileIndexFromProfileType; // eax
  __int64 v10; // rcx
  __int64 v11; // r12
  int Key; // ebx
  LPCOLESTR v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  wchar_t *v17; // rdx
  __int64 v18; // r8
  __int64 v20; // [rsp+30h] [rbp-51h] BYREF
  int v21; // [rsp+38h] [rbp-49h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-41h] BYREF

  v21 = 0;
  v20 = 0;
  memset_0(sz, 0, 0x4Eu);
  ProfileIndexFromProfileType = FwGetProfileIndexFromProfileType(a2);
  v10 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  v11 = ProfileIndexFromProfileType;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
    v10 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  if ( v10 )
  {
    Key = StringFromGUID2(a3, sz, 39);
    if ( Key >= 0 )
    {
      v15 = *(_QWORD *)(a1 + 48);
      v16 = *((unsigned int *)&FWPolicyAcessRightMap + *(int *)(a1 + 12));
      if ( a4 == 1 )
      {
        Key = FwRegCreateKey(v15, sz, v16, &v20);
        if ( Key < 0 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v14 = 74;
            goto LABEL_34;
          }
          return (unsigned int)Key;
        }
        v21 = 1;
      }
      else
      {
        Key = FwRegOpenKey(v15, sz, v16, &v20, &v21);
        if ( Key < 0 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v14 = 75;
            goto LABEL_34;
          }
          return (unsigned int)Key;
        }
      }
      v17 = off_18003C100[v11];
      v18 = *((unsigned int *)&FWPolicyAcessRightMap + *(int *)(a1 + 12));
      if ( a4 == 1 )
      {
        Key = FwRegCreateKey(v20, v17, v18, a5);
        if ( Key < 0 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v14 = 76;
            goto LABEL_34;
          }
        }
      }
      else
      {
        Key = FwRegOpenKey(v20, v17, v18, a5, &v21);
        if ( Key >= 0 )
        {
          if ( !v21 )
          {
            Key = -2147024894;
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v14 = 78;
              goto LABEL_34;
            }
          }
        }
        else
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v14 = 77;
            goto LABEL_34;
          }
        }
      }
      return (unsigned int)Key;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v14 = 73;
      goto LABEL_34;
    }
  }
  else
  {
    Key = -2147024809;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v14 = 72;
LABEL_34:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, (unsigned int)Key);
    }
  }
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x18002b6b4  push    rbp
0x18002b6b6  push    rbx
0x18002b6b7  push    rsi
0x18002b6b8  push    rdi
0x18002b6b9  push    r12
0x18002b6bb  push    r14
0x18002b6bd  push    r15
0x18002b6bf  lea     rbp, [rsp-1Fh]
0x18002b6c4  sub     rsp, 0A0h
0x18002b6cb  mov     rax, cs:__security_cookie
0x18002b6d2  xor     rax, rsp
0x18002b6d5  mov     [rbp+4Fh+var_40], rax
0x18002b6d9  mov     r14, [rbp+4Fh+arg_20]
0x18002b6dd  mov     ebx, edx
0x18002b6df  xor     edx, edx; Val
0x18002b6e1  mov     [rbp+4Fh+var_98], 0
0x18002b6e8  mov     rdi, r8
0x18002b6eb  mov     [rbp+4Fh+var_A0], 0
0x18002b6f3  mov     rsi, rcx
0x18002b6f6  mov     r15d, r9d
0x18002b6f9  lea     rcx, [rbp+4Fh+sz]; void *
0x18002b6fd  lea     r8d, [rdx+4Eh]; Size
0x18002b701  call    memset_0
0x18002b706  mov     ecx, ebx
0x18002b708  call    cs:__imp_FwGetProfileIndexFromProfileType
0x18002b70e  mov     rcx, [rdi]
0x18002b711  sub     rcx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002b718  movsxd  r12, eax
0x18002b71b  jnz     short loc_18002B728
0x18002b71d  mov     rcx, [rdi+8]
0x18002b721  sub     rcx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18002b728  test    rcx, rcx
0x18002b72b  jnz     short loc_18002B75D
0x18002b72d  mov     ebx, 80070057h
0x18002b732  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b739  lea     rax, WPP_GLOBAL_Control
0x18002b740  cmp     rcx, rax
0x18002b743  jz      loc_18002B908
0x18002b749  test    byte ptr [rcx+1Ch], 1
0x18002b74d  jz      loc_18002B908
0x18002b753  mov     edx, 48h ; 'H'
0x18002b758  jmp     loc_18002B8F5
0x18002b75d  mov     r8d, 27h ; '''; cchMax
0x18002b763  lea     rdx, [rbp+4Fh+sz]; lpsz
0x18002b767  mov     rcx, rdi; rguid
0x18002b76a  call    cs:__imp_StringFromGUID2
0x18002b770  mov     ebx, eax
0x18002b772  test    eax, eax
0x18002b774  jns     short loc_18002B7A1
0x18002b776  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b77d  lea     rax, WPP_GLOBAL_Control
0x18002b784  cmp     rcx, rax
0x18002b787  jz      loc_18002B908
0x18002b78d  test    byte ptr [rcx+1Ch], 1
0x18002b791  jz      loc_18002B908
0x18002b797  mov     edx, 49h ; 'I'
0x18002b79c  jmp     loc_18002B8F5
0x18002b7a1  movsxd  r8, dword ptr [rsi+0Ch]
0x18002b7a5  lea     rdi, __ImageBase
0x18002b7ac  mov     rcx, [rsi+30h]
0x18002b7b0  lea     r9, [rbp+4Fh+var_A0]
0x18002b7b4  lea     rdx, [rbp+4Fh+sz]
0x18002b7b8  mov     r8d, ds:rva ?FWPolicyAcessRightMap@@3PAKA[rdi+r8*4]; ulong near * FWPolicyAcessRightMap ...
0x18002b7c0  cmp     r15d, 1
0x18002b7c4  jnz     loc_18002B862
0x18002b7ca  call    cs:__imp_FwRegCreateKey
0x18002b7d0  mov     ebx, eax
0x18002b7d2  test    eax, eax
0x18002b7d4  jns     short loc_18002B800
0x18002b7d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b7dd  lea     rax, WPP_GLOBAL_Control
0x18002b7e4  cmp     rcx, rax
0x18002b7e7  jz      loc_18002B908
0x18002b7ed  test    [rcx+1Ch], r15b
0x18002b7f1  jz      loc_18002B908
0x18002b7f7  lea     edx, [r15+49h]
0x18002b7fb  jmp     loc_18002B8F5
0x18002b800  mov     [rbp+4Fh+var_98], 1
0x18002b807  movsxd  r8, dword ptr [rsi+0Ch]
0x18002b80b  mov     r9, r14
0x18002b80e  mov     rdx, ds:rva off_18003C100[rdi+r12*8]; "DomainProfile" ...
0x18002b816  mov     rcx, [rbp+4Fh+var_A0]
0x18002b81a  mov     r8d, ds:rva ?FWPolicyAcessRightMap@@3PAKA[rdi+r8*4]; ulong near * FWPolicyAcessRightMap ...
0x18002b822  cmp     r15d, 1
0x18002b826  jnz     short loc_18002B897
0x18002b828  call    cs:__imp_FwRegCreateKey
0x18002b82e  mov     ebx, eax
0x18002b830  test    eax, eax
0x18002b832  jns     loc_18002B908
0x18002b838  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b83f  lea     rax, WPP_GLOBAL_Control
0x18002b846  cmp     rcx, rax
0x18002b849  jz      loc_18002B908
0x18002b84f  test    [rcx+1Ch], r15b
0x18002b853  jz      loc_18002B908
0x18002b859  lea     edx, [r15+4Bh]
0x18002b85d  jmp     loc_18002B8F5
0x18002b862  lea     rax, [rbp+4Fh+var_98]
0x18002b866  mov     [rsp+0D0h+var_B0], rax
0x18002b86b  call    cs:__imp_FwRegOpenKey
0x18002b871  mov     ebx, eax
0x18002b873  test    eax, eax
0x18002b875  jns     short loc_18002B807
0x18002b877  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b87e  lea     rax, WPP_GLOBAL_Control
0x18002b885  cmp     rcx, rax
0x18002b888  jz      short loc_18002B908
0x18002b88a  test    byte ptr [rcx+1Ch], 1
0x18002b88e  jz      short loc_18002B908
0x18002b890  mov     edx, 4Bh ; 'K'
0x18002b895  jmp     short loc_18002B8F5
0x18002b897  lea     rax, [rbp+4Fh+var_98]
0x18002b89b  mov     [rsp+0D0h+var_B0], rax
0x18002b8a0  call    cs:__imp_FwRegOpenKey
0x18002b8a6  mov     ebx, eax
0x18002b8a8  test    eax, eax
0x18002b8aa  jns     short loc_18002B8CC
0x18002b8ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8b3  lea     rax, WPP_GLOBAL_Control
0x18002b8ba  cmp     rcx, rax
0x18002b8bd  jz      short loc_18002B908
0x18002b8bf  test    byte ptr [rcx+1Ch], 1
0x18002b8c3  jz      short loc_18002B908
0x18002b8c5  mov     edx, 4Dh ; 'M'
0x18002b8ca  jmp     short loc_18002B8F5
0x18002b8cc  cmp     [rbp+4Fh+var_98], 0
0x18002b8d0  jnz     short loc_18002B908
0x18002b8d2  mov     ebx, 80070002h
0x18002b8d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8de  lea     rax, WPP_GLOBAL_Control
0x18002b8e5  cmp     rcx, rax
0x18002b8e8  jz      short loc_18002B908
0x18002b8ea  test    byte ptr [rcx+1Ch], 1
0x18002b8ee  jz      short loc_18002B908
0x18002b8f0  mov     edx, 4Eh ; 'N'
0x18002b8f5  mov     rcx, [rcx+10h]
0x18002b8f9  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002b900  mov     r9d, ebx
0x18002b903  call    WPP_SF_d
0x18002b908  mov     eax, ebx
0x18002b90a  mov     rcx, [rbp+4Fh+var_40]
0x18002b90e  xor     rcx, rsp; StackCookie
0x18002b911  call    __security_check_cookie
0x18002b916  add     rsp, 0A0h
0x18002b91d  pop     r15
0x18002b91f  pop     r14
0x18002b921  pop     r12
0x18002b923  pop     rdi
0x18002b924  pop     rsi
0x18002b925  pop     rbx
0x18002b926  pop     rbp
0x18002b927  retn
```
