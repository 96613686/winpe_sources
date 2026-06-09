# FwAppCFieldParserBinary(ushort const *,_tag_FW_APPCONTAINER *)

- ea: `0x180014890`
- end: `0x180014954`
- name: `?FwAppCFieldParserBinary@@YAJPEBGPEAU_tag_FW_APPCONTAINER@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _tag_FW_APPCONTAINER *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800042c4`
- `0x180014890`
- `0x18001f650`

## import_xrefs

- `fwbase!FwStringCopy` at `0x1800148ba`
- `fwbase!FwStringCopy` at `0x1800148ba`
- `fwbase!FwArrayAppend` at `0x1800148db`
- `fwbase!FwArrayAppend` at `0x1800148db`

## pseudocode

```c
__int64 __fastcall FwAppCFieldParserBinary(const unsigned __int16 *a1, struct _tag_FW_APPCONTAINER *a2)
{
  int v3; // ebx
  LPCOLESTR v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF

  v7 = 0;
  v3 = FwStringCopy(a1, &v7);
  if ( v3 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v6 = 52;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids, (unsigned int)v3);
    }
  }
  else
  {
    v3 = FwArrayAppend(8, FwCopyIPv4SubNet, (char *)a2 + 80, &v7);
    if ( v3 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v6 = 53;
        goto LABEL_10;
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180014890  mov     [rsp+arg_10], rbx
0x180014895  push    rdi
0x180014896  sub     rsp, 30h
0x18001489a  mov     rax, cs:__security_cookie
0x1800148a1  xor     rax, rsp
0x1800148a4  mov     [rsp+38h+var_10], rax
0x1800148a9  mov     rdi, rdx
0x1800148ac  mov     [rsp+38h+var_18], 0
0x1800148b5  lea     rdx, [rsp+38h+var_18]
0x1800148ba  call    cs:__imp_FwStringCopy
0x1800148c0  mov     ebx, eax
0x1800148c2  test    eax, eax
0x1800148c4  js      short loc_180014901
0x1800148c6  lea     r8, [rdi+50h]
0x1800148ca  mov     ecx, 8
0x1800148cf  lea     r9, [rsp+38h+var_18]
0x1800148d4  lea     rdx, FwCopyIPv4SubNet
0x1800148db  call    cs:__imp_FwArrayAppend
0x1800148e1  mov     ebx, eax
0x1800148e3  test    eax, eax
0x1800148e5  js      short loc_180014921
0x1800148e7  mov     eax, ebx
0x1800148e9  mov     rcx, [rsp+38h+var_10]
0x1800148ee  xor     rcx, rsp; StackCookie
0x1800148f1  call    __security_check_cookie
0x1800148f6  mov     rbx, [rsp+38h+arg_10]
0x1800148fb  add     rsp, 30h
0x1800148ff  pop     rdi
0x180014900  retn
0x180014901  mov     rcx, cs:WPP_GLOBAL_Control
0x180014908  lea     rax, WPP_GLOBAL_Control
0x18001490f  cmp     rcx, rax
0x180014912  jz      short loc_1800148E7
0x180014914  test    byte ptr [rcx+1Ch], 1
0x180014918  jz      short loc_1800148E7
0x18001491a  mov     edx, 34h ; '4'
0x18001491f  jmp     short loc_18001493F
0x180014921  mov     rcx, cs:WPP_GLOBAL_Control
0x180014928  lea     rax, WPP_GLOBAL_Control
0x18001492f  cmp     rcx, rax
0x180014932  jz      short loc_1800148E7
0x180014934  test    byte ptr [rcx+1Ch], 1
0x180014938  jz      short loc_1800148E7
0x18001493a  mov     edx, 35h ; '5'
0x18001493f  mov     rcx, [rcx+10h]
0x180014943  lea     r8, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids
0x18001494a  mov     r9d, ebx
0x18001494d  call    WPP_SF_d
0x180014952  jmp     short loc_1800148E7
```
