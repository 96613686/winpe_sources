# FwInitWFICFPortInfoFromReg(void *,HKEY__ *,ushort const *,_tag_WF_ICF_PORT_INFO *,int *)

- ea: `0x180032900`
- end: `0x180032a1f`
- name: `?FwInitWFICFPortInfoFromReg@@YAJPEAXPEAUHKEY__@@PEBGPEAU_tag_WF_ICF_PORT_INFO@@PEAH@Z`
- size: `287`
- prototype: `__int64 __fastcall(unsigned int *, HKEY, const unsigned __int16 *, struct _tag_WF_ICF_PORT_INFO *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800042c4`
- `0x18001f650`
- `0x180032900`

## import_xrefs

- `fwbase!FwStringCopy` at `0x18003294d`
- `fwbase!FwStringCopy` at `0x18003294d`
- `fwbase!FwGetStaticFwPort` at `0x1800329ab`
- `fwbase!FwGetStaticFwPort` at `0x1800329ab`

## pseudocode

```c
__int64 __fastcall FwInitWFICFPortInfoFromReg(
        unsigned int *a1,
        HKEY a2,
        const unsigned __int16 *a3,
        struct _tag_WF_ICF_PORT_INFO *a4,
        int *a5)
{
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  int StaticFwPort; // eax
  int v16; // [rsp+30h] [rbp-48h] BYREF

  v16 = 0;
  *a5 = 0;
  *((_DWORD *)a4 + 20) = 0x10000;
  v9 = FwStringCopy(a3, (char *)a4 + 72);
  v10 = v9;
  if ( v9 >= 0 )
  {
    StaticFwPort = FwGetStaticFwPort(a2, a3, *a1, a4, &v16);
    v13 = (unsigned int)StaticFwPort;
    if ( StaticFwPort == -2147024883 )
    {
      *a5 = 1;
      *((_DWORD *)a4 + 20) = 3670016;
      return v10;
    }
    v10 = StaticFwPort;
    if ( StaticFwPort >= 0 )
    {
      if ( v16 )
        *a5 = 1;
    }
    else if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v12 = 11;
      goto LABEL_5;
    }
  }
  else if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v12 = 10;
    v13 = (unsigned int)v9;
LABEL_5:
    WPP_SF_d(v11, v12, WPP_10622196d762368449fa8f46c322a63a_Traceguids, v13);
  }
  return v10;
}

```

## disassembly

```asm
0x180032900  push    rbx
0x180032902  push    rbp
0x180032903  push    rsi
0x180032904  push    rdi
0x180032905  push    r14
0x180032907  push    r15
0x180032909  sub     rsp, 48h
0x18003290d  mov     rax, cs:__security_cookie
0x180032914  xor     rax, rsp
0x180032917  mov     [rsp+78h+var_40], rax
0x18003291c  mov     rdi, [rsp+78h+arg_20]
0x180032924  mov     r15, rdx
0x180032927  mov     r14, rcx
0x18003292a  mov     [rsp+78h+var_48], 0
0x180032932  lea     rdx, [r9+48h]
0x180032936  mov     rcx, r8
0x180032939  mov     rsi, r9
0x18003293c  mov     rbp, r8
0x18003293f  mov     dword ptr [rdi], 0
0x180032945  mov     dword ptr [r9+50h], 10000h
0x18003294d  call    cs:__imp_FwStringCopy
0x180032953  mov     ebx, eax
0x180032955  test    eax, eax
0x180032957  jns     short loc_180032995
0x180032959  mov     r10, cs:WPP_GLOBAL_Control
0x180032960  lea     rcx, WPP_GLOBAL_Control
0x180032967  cmp     r10, rcx
0x18003296a  jz      loc_180032A03
0x180032970  test    byte ptr [r10+1Ch], 1
0x180032975  jz      loc_180032A03
0x18003297b  mov     rcx, [r10+10h]
0x18003297f  mov     edx, 0Ah
0x180032984  mov     r9d, eax
0x180032987  lea     r8, WPP_10622196d762368449fa8f46c322a63a_Traceguids
0x18003298e  call    WPP_SF_d
0x180032993  jmp     short loc_180032A03
0x180032995  mov     r8d, [r14]
0x180032998  lea     rax, [rsp+78h+var_48]
0x18003299d  mov     r9, rsi
0x1800329a0  mov     [rsp+78h+var_58], rax
0x1800329a5  mov     rdx, rbp
0x1800329a8  mov     rcx, r15
0x1800329ab  call    cs:__imp_FwGetStaticFwPort
0x1800329b1  mov     r9d, eax
0x1800329b4  cmp     eax, 8007000Dh
0x1800329b9  jnz     short loc_1800329CA
0x1800329bb  mov     dword ptr [rdi], 1
0x1800329c1  mov     dword ptr [rsi+50h], 380000h
0x1800329c8  jmp     short loc_180032A03
0x1800329ca  mov     ebx, r9d
0x1800329cd  test    r9d, r9d
0x1800329d0  jns     short loc_1800329F6
0x1800329d2  mov     rax, cs:WPP_GLOBAL_Control
0x1800329d9  lea     rcx, WPP_GLOBAL_Control
0x1800329e0  cmp     rax, rcx
0x1800329e3  jz      short loc_180032A03
0x1800329e5  test    byte ptr [rax+1Ch], 1
0x1800329e9  jz      short loc_180032A03
0x1800329eb  mov     rcx, [rax+10h]
0x1800329ef  mov     edx, 0Bh
0x1800329f4  jmp     short loc_180032987
0x1800329f6  cmp     [rsp+78h+var_48], 0
0x1800329fb  jz      short loc_180032A03
0x1800329fd  mov     dword ptr [rdi], 1
0x180032a03  mov     eax, ebx
0x180032a05  mov     rcx, [rsp+78h+var_40]
0x180032a0a  xor     rcx, rsp; StackCookie
0x180032a0d  call    __security_check_cookie
0x180032a12  add     rsp, 48h
0x180032a16  pop     r15
0x180032a18  pop     r14
0x180032a1a  pop     rdi
0x180032a1b  pop     rsi
0x180032a1c  pop     rbp
0x180032a1d  pop     rbx
0x180032a1e  retn
```
