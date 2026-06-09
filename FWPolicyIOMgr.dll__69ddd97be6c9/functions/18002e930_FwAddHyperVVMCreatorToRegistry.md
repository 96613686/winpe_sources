# FwAddHyperVVMCreatorToRegistry

- ea: `0x18002e930`
- end: `0x18002eb26`
- name: `FwAddHyperVVMCreatorToRegistry`
- size: `502`
- prototype: `__int64 __fastcall(struct _tag_FW_HYPERV_VM_CREATOR0 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800042c4`
- `0x1800184b4`
- `0x18001f650`
- `0x18001ffd4`
- `0x18002e930`
- `0x18003779c`
- `0x1800379bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002e9c6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002e9c6`
- `fwbase!FwFree` at `0x18002eafd`
- `fwbase!FwFree` at `0x18002eafd`
- `fwbase!FwRegCloseKey` at `0x18002eaf3`
- `fwbase!FwRegCloseKey` at `0x18002eaf3`
- `fwbase!FwRegSetString` at `0x18002eab2`
- `fwbase!FwRegSetString` at `0x18002eab2`

## pseudocode

```c
__int64 __fastcall FwAddHyperVVMCreatorToRegistry(struct _tag_FW_HYPERV_VM_CREATOR0 *a1)
{
  int v2; // ebx
  LPCOLESTR v3; // rcx
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-29h] BYREF
  HKEY v7; // [rsp+28h] [rbp-21h] BYREF
  __int64 v8; // [rsp+30h] [rbp-19h]
  OLECHAR sz[40]; // [rsp+40h] [rbp-9h] BYREF

  v7 = 0;
  v6 = 0;
  memset_0(sz, 0, 0x4Eu);
  v8 = 0;
  v2 = FwCreateOrOpenHyperVVMCreatorsRegKey(&v7);
  if ( v2 >= 0 )
  {
    v2 = StringFromGUID2((const GUID *const)((char *)a1 + 12), sz, 39);
    if ( v2 >= 0 )
    {
      v2 = FwLookForHyperVVMCreatorId(v7, sz, &v6);
      if ( v2 >= 0 )
      {
        if ( v6 )
        {
          v2 = -2147024713;
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v4 = 413;
            goto LABEL_25;
          }
        }
        else
        {
          v2 = FwEncodeHyperVVMCreator(a1);
          if ( v2 >= 0 )
          {
            v2 = FwRegSetString(v7, 0, sz, v8);
            if ( v2 < 0 )
            {
              v3 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v4 = 415;
                goto LABEL_25;
              }
            }
          }
          else
          {
            v3 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v4 = 414;
              goto LABEL_25;
            }
          }
        }
      }
      else
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v4 = 412;
          goto LABEL_25;
        }
      }
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v4 = 411;
        goto LABEL_25;
      }
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v4 = 410;
LABEL_25:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, (unsigned int)v2);
    }
  }
  FwRegCloseKey(v7);
  FwFree(v8);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002e930  mov     [rsp-8+arg_8], rbx
0x18002e935  mov     [rsp-8+arg_10], rdi
0x18002e93a  push    rbp
0x18002e93b  lea     rbp, [rsp-57h]
0x18002e940  sub     rsp, 0A0h
0x18002e947  mov     rax, cs:__security_cookie
0x18002e94e  xor     rax, rsp
0x18002e951  mov     [rbp+57h+var_10], rax
0x18002e955  xor     edx, edx; Val
0x18002e957  mov     [rbp+57h+var_78], 0
0x18002e95f  mov     rdi, rcx
0x18002e962  mov     [rbp+57h+var_80], 0
0x18002e969  lea     rcx, [rbp+57h+sz]; void *
0x18002e96d  lea     r8d, [rdx+4Eh]; Size
0x18002e971  call    memset_0
0x18002e976  lea     rcx, [rbp+57h+var_78]; HKEY *
0x18002e97a  mov     [rbp+57h+var_70], 0
0x18002e982  call    ?FwCreateOrOpenHyperVVMCreatorsRegKey@@YAJPEAPEAUHKEY__@@@Z; FwCreateOrOpenHyperVVMCreatorsRegKey(HKEY__ * *)
0x18002e987  mov     ebx, eax
0x18002e989  test    eax, eax
0x18002e98b  jns     short loc_18002E9B8
0x18002e98d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e994  lea     rax, WPP_GLOBAL_Control
0x18002e99b  cmp     rcx, rax
0x18002e99e  jz      loc_18002EAEF
0x18002e9a4  test    byte ptr [rcx+1Ch], 1
0x18002e9a8  jz      loc_18002EAEF
0x18002e9ae  mov     edx, 19Ah
0x18002e9b3  jmp     loc_18002EADC
0x18002e9b8  lea     rcx, [rdi+0Ch]; rguid
0x18002e9bc  mov     r8d, 27h ; '''; cchMax
0x18002e9c2  lea     rdx, [rbp+57h+sz]; lpsz
0x18002e9c6  call    cs:__imp_StringFromGUID2
0x18002e9cc  mov     ebx, eax
0x18002e9ce  test    eax, eax
0x18002e9d0  jns     short loc_18002E9FD
0x18002e9d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e9d9  lea     rax, WPP_GLOBAL_Control
0x18002e9e0  cmp     rcx, rax
0x18002e9e3  jz      loc_18002EAEF
0x18002e9e9  test    byte ptr [rcx+1Ch], 1
0x18002e9ed  jz      loc_18002EAEF
0x18002e9f3  mov     edx, 19Bh
0x18002e9f8  jmp     loc_18002EADC
0x18002e9fd  mov     rcx, [rbp+57h+var_78]
0x18002ea01  lea     r8, [rbp+57h+var_80]
0x18002ea05  lea     rdx, [rbp+57h+sz]
0x18002ea09  call    FwLookForHyperVVMCreatorId
0x18002ea0e  mov     ebx, eax
0x18002ea10  test    eax, eax
0x18002ea12  jns     short loc_18002EA3F
0x18002ea14  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea1b  lea     rax, WPP_GLOBAL_Control
0x18002ea22  cmp     rcx, rax
0x18002ea25  jz      loc_18002EAEF
0x18002ea2b  test    byte ptr [rcx+1Ch], 1
0x18002ea2f  jz      loc_18002EAEF
0x18002ea35  mov     edx, 19Ch
0x18002ea3a  jmp     loc_18002EADC
0x18002ea3f  cmp     [rbp+57h+var_80], 0
0x18002ea43  jz      short loc_18002EA72
0x18002ea45  mov     ebx, 800700B7h
0x18002ea4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea51  lea     rax, WPP_GLOBAL_Control
0x18002ea58  cmp     rcx, rax
0x18002ea5b  jz      loc_18002EAEF
0x18002ea61  test    byte ptr [rcx+1Ch], 1
0x18002ea65  jz      loc_18002EAEF
0x18002ea6b  mov     edx, 19Dh
0x18002ea70  jmp     short loc_18002EADC
0x18002ea72  lea     rdx, [rbp+57h+var_70]
0x18002ea76  mov     rcx, rdi; struct _tag_FW_HYPERV_VM_CREATOR0 *
0x18002ea79  call    FwEncodeHyperVVMCreator
0x18002ea7e  mov     ebx, eax
0x18002ea80  test    eax, eax
0x18002ea82  jns     short loc_18002EAA4
0x18002ea84  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea8b  lea     rax, WPP_GLOBAL_Control
0x18002ea92  cmp     rcx, rax
0x18002ea95  jz      short loc_18002EAEF
0x18002ea97  test    byte ptr [rcx+1Ch], 1
0x18002ea9b  jz      short loc_18002EAEF
0x18002ea9d  mov     edx, 19Eh
0x18002eaa2  jmp     short loc_18002EADC
0x18002eaa4  mov     r9, [rbp+57h+var_70]
0x18002eaa8  lea     r8, [rbp+57h+sz]
0x18002eaac  mov     rcx, [rbp+57h+var_78]
0x18002eab0  xor     edx, edx
0x18002eab2  call    cs:__imp_FwRegSetString
0x18002eab8  mov     ebx, eax
0x18002eaba  test    eax, eax
0x18002eabc  jns     short loc_18002EAEF
0x18002eabe  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eac5  lea     rax, WPP_GLOBAL_Control
0x18002eacc  cmp     rcx, rax
0x18002eacf  jz      short loc_18002EAEF
0x18002ead1  test    byte ptr [rcx+1Ch], 1
0x18002ead5  jz      short loc_18002EAEF
0x18002ead7  mov     edx, 19Fh
0x18002eadc  mov     rcx, [rcx+10h]
0x18002eae0  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002eae7  mov     r9d, ebx
0x18002eaea  call    WPP_SF_d
0x18002eaef  mov     rcx, [rbp+57h+var_78]
0x18002eaf3  call    cs:__imp_FwRegCloseKey
0x18002eaf9  mov     rcx, [rbp+57h+var_70]
0x18002eafd  call    cs:__imp_FwFree
0x18002eb03  mov     eax, ebx
0x18002eb05  mov     rcx, [rbp+57h+var_10]
0x18002eb09  xor     rcx, rsp; StackCookie
0x18002eb0c  call    __security_check_cookie
0x18002eb11  lea     r11, [rsp+0A0h+var_s0]
0x18002eb19  mov     rbx, [r11+18h]
0x18002eb1d  mov     rdi, [r11+20h]
0x18002eb21  mov     rsp, r11
0x18002eb24  pop     rbp
0x18002eb25  retn
```
