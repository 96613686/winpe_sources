# FwInitWFICFAppInfoFromReg(void *,HKEY__ *,ushort const *,_tag_WF_ICF_APP_INFO *,int *)

- ea: `0x180032780`
- end: `0x18003289f`
- name: `?FwInitWFICFAppInfoFromReg@@YAJPEAXPEAUHKEY__@@PEBGPEAU_tag_WF_ICF_APP_INFO@@PEAH@Z`
- size: `287`
- prototype: `__int64 __fastcall(unsigned int *, HKEY, const unsigned __int16 *, struct _tag_WF_ICF_APP_INFO *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800042c4`
- `0x18001f650`
- `0x180032780`

## import_xrefs

- `fwbase!FwStringCopy` at `0x1800327cd`
- `fwbase!FwStringCopy` at `0x1800327cd`
- `fwbase!FwGetAuthorizedApp` at `0x18003282b`
- `fwbase!FwGetAuthorizedApp` at `0x18003282b`

## pseudocode

```c
__int64 __fastcall FwInitWFICFAppInfoFromReg(
        unsigned int *a1,
        HKEY a2,
        const unsigned __int16 *a3,
        struct _tag_WF_ICF_APP_INFO *a4,
        int *a5)
{
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  int AuthorizedApp; // eax
  int v16; // [rsp+30h] [rbp-48h] BYREF

  v16 = 0;
  *a5 = 0;
  *((_DWORD *)a4 + 20) = 0x10000;
  v9 = FwStringCopy(a3, (char *)a4 + 72);
  v10 = v9;
  if ( v9 >= 0 )
  {
    AuthorizedApp = FwGetAuthorizedApp(a2, a3, *a1, a4, &v16);
    v13 = (unsigned int)AuthorizedApp;
    if ( AuthorizedApp == -2147024883 )
    {
      *a5 = 1;
      *((_DWORD *)a4 + 20) = 3670016;
      return v10;
    }
    v10 = AuthorizedApp;
    if ( AuthorizedApp >= 0 )
    {
      if ( v16 )
        *a5 = 1;
    }
    else if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v12 = 13;
      goto LABEL_5;
    }
  }
  else if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v12 = 12;
    v13 = (unsigned int)v9;
LABEL_5:
    WPP_SF_d(v11, v12, WPP_10622196d762368449fa8f46c322a63a_Traceguids, v13);
  }
  return v10;
}

```

## disassembly

```asm
0x180032780  push    rbx
0x180032782  push    rbp
0x180032783  push    rsi
0x180032784  push    rdi
0x180032785  push    r14
0x180032787  push    r15
0x180032789  sub     rsp, 48h
0x18003278d  mov     rax, cs:__security_cookie
0x180032794  xor     rax, rsp
0x180032797  mov     [rsp+78h+var_40], rax
0x18003279c  mov     rdi, [rsp+78h+arg_20]
0x1800327a4  mov     r15, rdx
0x1800327a7  mov     r14, rcx
0x1800327aa  mov     [rsp+78h+var_48], 0
0x1800327b2  lea     rdx, [r9+48h]
0x1800327b6  mov     rcx, r8
0x1800327b9  mov     rsi, r9
0x1800327bc  mov     rbp, r8
0x1800327bf  mov     dword ptr [rdi], 0
0x1800327c5  mov     dword ptr [r9+50h], 10000h
0x1800327cd  call    cs:__imp_FwStringCopy
0x1800327d3  mov     ebx, eax
0x1800327d5  test    eax, eax
0x1800327d7  jns     short loc_180032815
0x1800327d9  mov     r10, cs:WPP_GLOBAL_Control
0x1800327e0  lea     rcx, WPP_GLOBAL_Control
0x1800327e7  cmp     r10, rcx
0x1800327ea  jz      loc_180032883
0x1800327f0  test    byte ptr [r10+1Ch], 1
0x1800327f5  jz      loc_180032883
0x1800327fb  mov     rcx, [r10+10h]
0x1800327ff  mov     edx, 0Ch
0x180032804  mov     r9d, eax
0x180032807  lea     r8, WPP_10622196d762368449fa8f46c322a63a_Traceguids
0x18003280e  call    WPP_SF_d
0x180032813  jmp     short loc_180032883
0x180032815  mov     r8d, [r14]
0x180032818  lea     rax, [rsp+78h+var_48]
0x18003281d  mov     r9, rsi
0x180032820  mov     [rsp+78h+var_58], rax
0x180032825  mov     rdx, rbp
0x180032828  mov     rcx, r15
0x18003282b  call    cs:__imp_FwGetAuthorizedApp
0x180032831  mov     r9d, eax
0x180032834  cmp     eax, 8007000Dh
0x180032839  jnz     short loc_18003284A
0x18003283b  mov     dword ptr [rdi], 1
0x180032841  mov     dword ptr [rsi+50h], 380000h
0x180032848  jmp     short loc_180032883
0x18003284a  mov     ebx, r9d
0x18003284d  test    r9d, r9d
0x180032850  jns     short loc_180032876
0x180032852  mov     rax, cs:WPP_GLOBAL_Control
0x180032859  lea     rcx, WPP_GLOBAL_Control
0x180032860  cmp     rax, rcx
0x180032863  jz      short loc_180032883
0x180032865  test    byte ptr [rax+1Ch], 1
0x180032869  jz      short loc_180032883
0x18003286b  mov     rcx, [rax+10h]
0x18003286f  mov     edx, 0Dh
0x180032874  jmp     short loc_180032807
0x180032876  cmp     [rsp+78h+var_48], 0
0x18003287b  jz      short loc_180032883
0x18003287d  mov     dword ptr [rdi], 1
0x180032883  mov     eax, ebx
0x180032885  mov     rcx, [rsp+78h+var_40]
0x18003288a  xor     rcx, rsp; StackCookie
0x18003288d  call    __security_check_cookie
0x180032892  add     rsp, 48h
0x180032896  pop     r15
0x180032898  pop     r14
0x18003289a  pop     rdi
0x18003289b  pop     rsi
0x18003289c  pop     rbp
0x18003289d  pop     rbx
0x18003289e  retn
```
