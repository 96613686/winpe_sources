# FwDeleteHyperVVMCreatorFromRegistry

- ea: `0x18002f1c0`
- end: `0x18002f357`
- name: `FwDeleteHyperVVMCreatorFromRegistry`
- size: `407`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800042c4`
- `0x1800184b4`
- `0x18001f650`
- `0x18001ffd4`
- `0x18002f1c0`
- `0x1800379bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002f24e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002f24e`
- `fwbase!FwRegCloseKey` at `0x18002f332`
- `fwbase!FwRegCloseKey` at `0x18002f332`
- `fwbase!FwRegDeleteValue` at `0x18002f2f1`
- `fwbase!FwRegDeleteValue` at `0x18002f2f1`

## pseudocode

```c
__int64 __fastcall FwDeleteHyperVVMCreatorFromRegistry(GUID *a1)
{
  GUID v1; // xmm0
  int v2; // ebx
  LPCOLESTR v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  int v7; // [rsp+20h] [rbp-29h] BYREF
  HKEY v8; // [rsp+28h] [rbp-21h] BYREF
  GUID rguid; // [rsp+30h] [rbp-19h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-9h] BYREF

  v1 = *a1;
  v8 = 0;
  v7 = 0;
  rguid = v1;
  memset_0(sz, 0, 0x4Eu);
  v2 = FwCreateOrOpenHyperVVMCreatorsRegKey(&v8);
  if ( v2 >= 0 )
  {
    v2 = StringFromGUID2(&rguid, sz, 39);
    if ( v2 >= 0 )
    {
      v2 = FwLookForHyperVVMCreatorId(v8, sz, &v7);
      if ( v2 >= 0 )
      {
        if ( v7 )
        {
          v2 = FwRegDeleteValue(v8, 0, sz);
          if ( v2 < 0 )
          {
            v3 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v4 = 420;
              goto LABEL_21;
            }
          }
        }
        else
        {
          v2 = 0;
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v4 = 419;
            v5 = 0;
LABEL_22:
            WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v5);
          }
        }
      }
      else
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v4 = 418;
          goto LABEL_21;
        }
      }
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v4 = 417;
        goto LABEL_21;
      }
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v4 = 416;
LABEL_21:
      v5 = (unsigned int)v2;
      goto LABEL_22;
    }
  }
  FwRegCloseKey(v8);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002f1c0  mov     [rsp-8+arg_8], rbx
0x18002f1c5  push    rbp
0x18002f1c6  lea     rbp, [rsp-57h]
0x18002f1cb  sub     rsp, 0A0h
0x18002f1d2  mov     rax, cs:__security_cookie
0x18002f1d9  xor     rax, rsp
0x18002f1dc  mov     [rbp+57h+var_10], rax
0x18002f1e0  movups  xmm0, xmmword ptr [rcx]
0x18002f1e3  xor     edx, edx; Val
0x18002f1e5  mov     [rbp+57h+var_78], 0
0x18002f1ed  lea     rcx, [rbp+57h+sz]; void *
0x18002f1f1  mov     [rbp+57h+var_80], 0
0x18002f1f8  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x18002f1fd  lea     r8d, [rdx+4Eh]; Size
0x18002f201  call    memset_0
0x18002f206  lea     rcx, [rbp+57h+var_78]; HKEY *
0x18002f20a  call    ?FwCreateOrOpenHyperVVMCreatorsRegKey@@YAJPEAPEAUHKEY__@@@Z; FwCreateOrOpenHyperVVMCreatorsRegKey(HKEY__ * *)
0x18002f20f  mov     ebx, eax
0x18002f211  test    eax, eax
0x18002f213  jns     short loc_18002F240
0x18002f215  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f21c  lea     rax, WPP_GLOBAL_Control
0x18002f223  cmp     rcx, rax
0x18002f226  jz      loc_18002F32E
0x18002f22c  test    byte ptr [rcx+1Ch], 1
0x18002f230  jz      loc_18002F32E
0x18002f236  mov     edx, 1A0h
0x18002f23b  jmp     loc_18002F31B
0x18002f240  mov     r8d, 27h ; '''; cchMax
0x18002f246  lea     rdx, [rbp+57h+sz]; lpsz
0x18002f24a  lea     rcx, [rbp+57h+rguid]; rguid
0x18002f24e  call    cs:__imp_StringFromGUID2
0x18002f254  mov     ebx, eax
0x18002f256  test    eax, eax
0x18002f258  jns     short loc_18002F285
0x18002f25a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f261  lea     rax, WPP_GLOBAL_Control
0x18002f268  cmp     rcx, rax
0x18002f26b  jz      loc_18002F32E
0x18002f271  test    byte ptr [rcx+1Ch], 1
0x18002f275  jz      loc_18002F32E
0x18002f27b  mov     edx, 1A1h
0x18002f280  jmp     loc_18002F31B
0x18002f285  mov     rcx, [rbp+57h+var_78]
0x18002f289  lea     r8, [rbp+57h+var_80]
0x18002f28d  lea     rdx, [rbp+57h+sz]
0x18002f291  call    FwLookForHyperVVMCreatorId
0x18002f296  mov     ebx, eax
0x18002f298  test    eax, eax
0x18002f29a  jns     short loc_18002F2BC
0x18002f29c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f2a3  lea     rax, WPP_GLOBAL_Control
0x18002f2aa  cmp     rcx, rax
0x18002f2ad  jz      short loc_18002F32E
0x18002f2af  test    byte ptr [rcx+1Ch], 1
0x18002f2b3  jz      short loc_18002F32E
0x18002f2b5  mov     edx, 1A2h
0x18002f2ba  jmp     short loc_18002F31B
0x18002f2bc  cmp     [rbp+57h+var_80], 0
0x18002f2c0  jnz     short loc_18002F2E7
0x18002f2c2  xor     ebx, ebx
0x18002f2c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f2cb  lea     rax, WPP_GLOBAL_Control
0x18002f2d2  cmp     rcx, rax
0x18002f2d5  jz      short loc_18002F32E
0x18002f2d7  test    byte ptr [rcx+1Ch], 1
0x18002f2db  jz      short loc_18002F32E
0x18002f2dd  mov     edx, 1A3h
0x18002f2e2  xor     r9d, r9d
0x18002f2e5  jmp     short loc_18002F31E
0x18002f2e7  mov     rcx, [rbp+57h+var_78]
0x18002f2eb  lea     r8, [rbp+57h+sz]
0x18002f2ef  xor     edx, edx
0x18002f2f1  call    cs:__imp_FwRegDeleteValue
0x18002f2f7  mov     ebx, eax
0x18002f2f9  test    eax, eax
0x18002f2fb  jns     short loc_18002F32E
0x18002f2fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f304  lea     rax, WPP_GLOBAL_Control
0x18002f30b  cmp     rcx, rax
0x18002f30e  jz      short loc_18002F32E
0x18002f310  test    byte ptr [rcx+1Ch], 1
0x18002f314  jz      short loc_18002F32E
0x18002f316  mov     edx, 1A4h
0x18002f31b  mov     r9d, ebx
0x18002f31e  mov     rcx, [rcx+10h]
0x18002f322  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002f329  call    WPP_SF_d
0x18002f32e  mov     rcx, [rbp+57h+var_78]
0x18002f332  call    cs:__imp_FwRegCloseKey
0x18002f338  mov     eax, ebx
0x18002f33a  mov     rcx, [rbp+57h+var_10]
0x18002f33e  xor     rcx, rsp; StackCookie
0x18002f341  call    __security_check_cookie
0x18002f346  mov     rbx, [rsp+0A0h+arg_8]
0x18002f34e  add     rsp, 0A0h
0x18002f355  pop     rbp
0x18002f356  retn
```
