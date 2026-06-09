# FwGetHyperVRegHandleFromStoreIOHandle(void *,_GUID const &,int,HKEY__ * *)

- ea: `0x18002b930`
- end: `0x18002baec`
- name: `?FwGetHyperVRegHandleFromStoreIOHandle@@YAJPEAXAEBU_GUID@@HPEAPEAUHKEY__@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(int *, const struct _GUID *, int, HKEY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002df3c`

## callees

- `0x1800042c4`
- `0x18001f650`
- `0x18001ffd4`
- `0x18002b930`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b9cf`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b9cf`
- `fwbase!FwRegOpenKey` at `0x18002ba5e`
- `fwbase!FwRegOpenKey` at `0x18002ba5e`
- `fwbase!FwRegCreateKey` at `0x18002ba26`
- `fwbase!FwRegCreateKey` at `0x18002ba26`

## pseudocode

```c
__int64 __fastcall FwGetHyperVRegHandleFromStoreIOHandle(int *a1, const struct _GUID *a2, int a3, HKEY *a4)
{
  __int64 v8; // rax
  int Key; // ebx
  LPCOLESTR v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  _DWORD v15[4]; // [rsp+30h] [rbp-88h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-78h] BYREF

  v15[0] = 0;
  memset_0(sz, 0, 0x4Eu);
  v8 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
    v8 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  if ( v8 )
  {
    Key = StringFromGUID2(a2, sz, 39);
    if ( Key >= 0 )
    {
      v12 = *((_QWORD *)a1 + 6);
      v13 = *((unsigned int *)&FWPolicyAcessRightMap + a1[3]);
      if ( a3 == 1 )
      {
        Key = FwRegCreateKey(v12, sz, v13, a4);
        if ( Key < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v11 = 69;
            goto LABEL_24;
          }
        }
      }
      else
      {
        Key = FwRegOpenKey(v12, sz, v13, a4, v15);
        if ( Key >= 0 )
        {
          if ( !v15[0] )
          {
            Key = -2147024894;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v11 = 71;
              goto LABEL_24;
            }
          }
        }
        else
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v11 = 70;
            goto LABEL_24;
          }
        }
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v11 = 68;
        goto LABEL_24;
      }
    }
  }
  else
  {
    Key = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v11 = 67;
LABEL_24:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, (unsigned int)Key);
    }
  }
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x18002b930  mov     [rsp+arg_10], rbx
0x18002b935  push    rbp
0x18002b936  push    rsi
0x18002b937  push    rdi
0x18002b938  sub     rsp, 0A0h
0x18002b93f  mov     rax, cs:__security_cookie
0x18002b946  xor     rax, rsp
0x18002b949  mov     [rsp+0B8h+var_28], rax
0x18002b951  mov     rbx, rdx
0x18002b954  mov     [rsp+0B8h+var_88], 0
0x18002b95c  xor     edx, edx; Val
0x18002b95e  mov     ebp, r8d
0x18002b961  mov     rdi, rcx
0x18002b964  mov     rsi, r9
0x18002b967  lea     rcx, [rsp+0B8h+sz]; void *
0x18002b96c  lea     r8d, [rdx+4Eh]; Size
0x18002b970  call    memset_0
0x18002b975  mov     rax, [rbx]
0x18002b978  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002b97f  jnz     short loc_18002B98C
0x18002b981  mov     rax, [rbx+8]
0x18002b985  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18002b98c  test    rax, rax
0x18002b98f  jnz     short loc_18002B9C1
0x18002b991  mov     ebx, 80070057h
0x18002b996  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b99d  lea     rax, WPP_GLOBAL_Control
0x18002b9a4  cmp     rcx, rax
0x18002b9a7  jz      loc_18002BAC7
0x18002b9ad  test    byte ptr [rcx+1Ch], 1
0x18002b9b1  jz      loc_18002BAC7
0x18002b9b7  mov     edx, 43h ; 'C'
0x18002b9bc  jmp     loc_18002BAB4
0x18002b9c1  mov     r8d, 27h ; '''; cchMax
0x18002b9c7  lea     rdx, [rsp+0B8h+sz]; lpsz
0x18002b9cc  mov     rcx, rbx; rguid
0x18002b9cf  call    cs:__imp_StringFromGUID2
0x18002b9d5  mov     ebx, eax
0x18002b9d7  test    eax, eax
0x18002b9d9  jns     short loc_18002BA06
0x18002b9db  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9e2  lea     rax, WPP_GLOBAL_Control
0x18002b9e9  cmp     rcx, rax
0x18002b9ec  jz      loc_18002BAC7
0x18002b9f2  test    byte ptr [rcx+1Ch], 1
0x18002b9f6  jz      loc_18002BAC7
0x18002b9fc  mov     edx, 44h ; 'D'
0x18002ba01  jmp     loc_18002BAB4
0x18002ba06  movsxd  r8, dword ptr [rdi+0Ch]
0x18002ba0a  lea     rdx, ?FWPolicyAcessRightMap@@3PAKA; ulong near * FWPolicyAcessRightMap
0x18002ba11  mov     rcx, [rdi+30h]
0x18002ba15  mov     r9, rsi
0x18002ba18  mov     r8d, [rdx+r8*4]
0x18002ba1c  lea     rdx, [rsp+0B8h+sz]
0x18002ba21  cmp     ebp, 1
0x18002ba24  jnz     short loc_18002BA54
0x18002ba26  call    cs:__imp_FwRegCreateKey
0x18002ba2c  mov     ebx, eax
0x18002ba2e  test    eax, eax
0x18002ba30  jns     loc_18002BAC7
0x18002ba36  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba3d  lea     rax, WPP_GLOBAL_Control
0x18002ba44  cmp     rcx, rax
0x18002ba47  jz      short loc_18002BAC7
0x18002ba49  test    [rcx+1Ch], bpl
0x18002ba4d  jz      short loc_18002BAC7
0x18002ba4f  lea     edx, [rbp+44h]
0x18002ba52  jmp     short loc_18002BAB4
0x18002ba54  lea     rax, [rsp+0B8h+var_88]
0x18002ba59  mov     [rsp+0B8h+var_98], rax
0x18002ba5e  call    cs:__imp_FwRegOpenKey
0x18002ba64  mov     ebx, eax
0x18002ba66  test    eax, eax
0x18002ba68  jns     short loc_18002BA8A
0x18002ba6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba71  lea     rax, WPP_GLOBAL_Control
0x18002ba78  cmp     rcx, rax
0x18002ba7b  jz      short loc_18002BAC7
0x18002ba7d  test    byte ptr [rcx+1Ch], 1
0x18002ba81  jz      short loc_18002BAC7
0x18002ba83  mov     edx, 46h ; 'F'
0x18002ba88  jmp     short loc_18002BAB4
0x18002ba8a  cmp     [rsp+0B8h+var_88], 0
0x18002ba8f  jnz     short loc_18002BAC7
0x18002ba91  mov     ebx, 80070002h
0x18002ba96  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba9d  lea     rax, WPP_GLOBAL_Control
0x18002baa4  cmp     rcx, rax
0x18002baa7  jz      short loc_18002BAC7
0x18002baa9  test    byte ptr [rcx+1Ch], 1
0x18002baad  jz      short loc_18002BAC7
0x18002baaf  mov     edx, 47h ; 'G'
0x18002bab4  mov     rcx, [rcx+10h]
0x18002bab8  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002babf  mov     r9d, ebx
0x18002bac2  call    WPP_SF_d
0x18002bac7  mov     eax, ebx
0x18002bac9  mov     rcx, [rsp+0B8h+var_28]
0x18002bad1  xor     rcx, rsp; StackCookie
0x18002bad4  call    __security_check_cookie
0x18002bad9  mov     rbx, [rsp+0B8h+arg_10]
0x18002bae1  add     rsp, 0A0h
0x18002bae8  pop     rdi
0x18002bae9  pop     rsi
0x18002baea  pop     rbp
0x18002baeb  retn
```
