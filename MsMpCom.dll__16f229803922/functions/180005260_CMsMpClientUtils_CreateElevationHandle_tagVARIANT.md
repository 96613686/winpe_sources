# CMsMpClientUtils::CreateElevationHandle(tagVARIANT *)

- ea: `0x180005260`
- end: `0x18000537f`
- name: `?CreateElevationHandle@CMsMpClientUtils@@UEAAJPEAUtagVARIANT@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(CMsMpClientUtils *this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002b54`
- `0x180005260`
- `0x180005b0c`
- `0x180009440`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800052c6`
- `OLEAUT32!__imp_VariantInit` at `0x1800052c6`
- `mpclient!MpElevationHandleOpen` at `0x1800052fc`
- `mpclient!MpElevationHandleOpen` at `0x1800052fc`
- `mpclient!MpHandleClose` at `0x180005312`
- `mpclient!MpHandleClose` at `0x180005339`
- `mpclient!MpHandleClose` at `0x18000535a`
- `mpclient!MpHandleClose` at `0x180005312`
- `mpclient!MpHandleClose` at `0x180005339`
- `mpclient!MpHandleClose` at `0x18000535a`

## pseudocode

```c
__int64 __fastcall CMsMpClientUtils::CreateElevationHandle(CMsMpClientUtils *this, struct tagVARIANT *a2)
{
  __int64 v5; // rcx
  int v6; // esi
  int v7; // edi
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // [rsp+30h] [rbp-28h] BYREF
  __int128 v11; // [rsp+38h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 19);
  if ( !a2 )
    return 2147500035LL;
  VariantInit(a2);
  if ( *((_QWORD *)this + 2) )
    return 2147947423LL;
  v5 = *((_QWORD *)this + 1);
  v10 = 0;
  v11 = 0;
  v6 = MpElevationHandleOpen(v5, &v11, &v10);
  if ( v6 >= 0 )
  {
    v7 = CommonUtil::SerializeToVariantBinaryBuffer<_GUID>(a2, &v11);
    if ( v7 >= 0 )
    {
      v9 = v10;
      v10 = *((_QWORD *)this + 2);
      v8 = v10;
      *((_QWORD *)this + 2) = v9;
      if ( v8 )
        MpHandleClose();
      return 0;
    }
    else
    {
      if ( v10 )
        MpHandleClose();
      return (unsigned int)v7;
    }
  }
  else
  {
    if ( v10 )
      MpHandleClose();
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x180005260  mov     [rsp+arg_10], rbx
0x180005265  mov     [rsp+arg_18], rsi
0x18000526a  push    rdi
0x18000526b  sub     rsp, 50h
0x18000526f  mov     rax, cs:__security_cookie
0x180005276  xor     rax, rsp
0x180005279  mov     [rsp+58h+var_10], rax
0x18000527e  mov     rdi, rdx
0x180005281  mov     rbx, rcx
0x180005284  mov     rcx, cs:WPP_GLOBAL_Control
0x18000528b  lea     rax, WPP_GLOBAL_Control
0x180005292  cmp     rcx, rax
0x180005295  jz      short loc_1800052B4
0x180005297  test    byte ptr [rcx+1Ch], 8
0x18000529b  jz      short loc_1800052B4
0x18000529d  mov     rcx, [rcx+10h]
0x1800052a1  lea     rax, [rbx-40h]
0x1800052a5  mov     edx, 13h
0x1800052aa  mov     [rsp+58h+var_38], rax
0x1800052af  call    WPP_SF_sq
0x1800052b4  test    rdi, rdi
0x1800052b7  jnz     short loc_1800052C3
0x1800052b9  mov     eax, 80004003h
0x1800052be  jmp     loc_180005362
0x1800052c3  mov     rcx, rdi; pvarg
0x1800052c6  call    cs:__imp_VariantInit
0x1800052cc  cmp     qword ptr [rbx+10h], 0
0x1800052d1  jz      short loc_1800052DD
0x1800052d3  mov     eax, 8007139Fh
0x1800052d8  jmp     loc_180005362
0x1800052dd  mov     rcx, [rbx+8]
0x1800052e1  lea     r8, [rsp+58h+var_28]
0x1800052e6  xorps   xmm0, xmm0
0x1800052e9  mov     [rsp+58h+var_28], 0
0x1800052f2  lea     rdx, [rsp+58h+var_20]
0x1800052f7  movups  [rsp+58h+var_20], xmm0
0x1800052fc  call    cs:__imp_MpElevationHandleOpen
0x180005302  mov     esi, eax
0x180005304  test    eax, eax
0x180005306  jns     short loc_18000531C
0x180005308  mov     rcx, [rsp+58h+var_28]
0x18000530d  test    rcx, rcx
0x180005310  jz      short loc_180005318
0x180005312  call    cs:__imp_MpHandleClose
0x180005318  mov     eax, esi
0x18000531a  jmp     short loc_180005362
0x18000531c  lea     rdx, [rsp+58h+var_20]
0x180005321  mov     rcx, rdi
0x180005324  call    ??$SerializeToVariantBinaryBuffer@U_GUID@@@CommonUtil@@YAJPEAUtagVARIANT@@AEBU_GUID@@@Z; CommonUtil::SerializeToVariantBinaryBuffer<_GUID>(tagVARIANT *,_GUID const &)
0x180005329  mov     edi, eax
0x18000532b  test    eax, eax
0x18000532d  jns     short loc_180005343
0x18000532f  mov     rcx, [rsp+58h+var_28]
0x180005334  test    rcx, rcx
0x180005337  jz      short loc_18000533F
0x180005339  call    cs:__imp_MpHandleClose
0x18000533f  mov     eax, edi
0x180005341  jmp     short loc_180005362
0x180005343  mov     rcx, [rbx+10h]
0x180005347  mov     rax, [rsp+58h+var_28]
0x18000534c  mov     [rsp+58h+var_28], rcx
0x180005351  mov     [rbx+10h], rax
0x180005355  test    rcx, rcx
0x180005358  jz      short loc_180005360
0x18000535a  call    cs:__imp_MpHandleClose
0x180005360  xor     eax, eax
0x180005362  mov     rcx, [rsp+58h+var_10]
0x180005367  xor     rcx, rsp; StackCookie
0x18000536a  call    __security_check_cookie
0x18000536f  mov     rbx, [rsp+58h+arg_10]
0x180005374  mov     rsi, [rsp+58h+arg_18]
0x180005379  add     rsp, 50h
0x18000537d  pop     rdi
0x18000537e  retn
```
