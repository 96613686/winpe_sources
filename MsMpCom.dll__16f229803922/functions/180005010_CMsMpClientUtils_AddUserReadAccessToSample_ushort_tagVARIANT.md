# CMsMpClientUtils::AddUserReadAccessToSample(ushort *,tagVARIANT)

- ea: `0x180005010`
- end: `0x1800050ed`
- name: `?AddUserReadAccessToSample@CMsMpClientUtils@@UEAAJPEAGUtagVARIANT@@@Z`
- size: `221`
- prototype: `__int64 __fastcall(CMsMpClientUtils *this, unsigned __int16 *, struct tagVARIANT *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004b7c`
- `0x180005010`
- `0x1800057f4`
- `0x180005b0c`
- `0x180008de0`
- `0x1800090e4`

## import_xrefs

- `ADVAPI32!IsValidSid` at `0x180005091`
- `ADVAPI32!IsValidSid` at `0x180005091`

## pseudocode

```c
__int64 __fastcall CMsMpClientUtils::AddUserReadAccessToSample(
        CMsMpClientUtils *this,
        unsigned __int16 *a2,
        struct tagVARIANT *a3,
        unsigned __int64 *a4)
{
  __int64 result; // rax
  __int64 v7; // rcx
  unsigned int LastFailure; // eax
  unsigned int v9; // ebx
  char *v10; // [rsp+20h] [rbp-18h]
  struct tagVARIANT pSid; // [rsp+40h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v10 = (char *)this - 64;
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 21);
  }
  if ( !a2 )
    return 2147942487LL;
  *(_OWORD *)&pSid.vt = 0u;
  result = CommonUtil::VariantExtractBinaryBuffer((CommonUtil *)a3, &pSid, (const void **)&pSid.bstrVal, a4);
  if ( (int)result >= 0 )
  {
    if ( IsValidSid(*(PSID *)&pSid.vt) )
    {
      return UtilAddUserReadAccessToSample(a2);
    }
    else
    {
      LastFailure = HrGetLastFailure(v7);
      v9 = LastFailure;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          &WPP_85f567f30ac03a1b1e78961f0afc6072_Traceguids,
          LastFailure,
          v10);
      return v9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005010  mov     [rsp+arg_10], rbx
0x180005015  mov     [rsp+arg_18], rsi
0x18000501a  push    rdi
0x18000501b  sub     rsp, 30h
0x18000501f  mov     rdi, r8
0x180005022  mov     rbx, rdx
0x180005025  mov     rax, rcx
0x180005028  mov     rcx, cs:WPP_GLOBAL_Control
0x18000502f  lea     rsi, WPP_GLOBAL_Control
0x180005036  cmp     rcx, rsi
0x180005039  jz      short loc_180005058
0x18000503b  test    byte ptr [rcx+1Ch], 8
0x18000503f  jz      short loc_180005058
0x180005041  mov     rcx, [rcx+10h]
0x180005045  add     rax, 0FFFFFFFFFFFFFFC0h
0x180005049  mov     edx, 15h
0x18000504e  mov     [rsp+38h+var_18], rax
0x180005053  call    WPP_SF_sq
0x180005058  test    rbx, rbx
0x18000505b  jnz     short loc_180005064
0x18000505d  mov     eax, 80070057h
0x180005062  jmp     short loc_1800050DD
0x180005064  lea     r8, [rsp+38h+arg_8]; void **
0x180005069  mov     [rsp+38h+pSid], 0
0x180005072  lea     rdx, [rsp+38h+pSid]; struct tagVARIANT *
0x180005077  mov     [rsp+38h+arg_8], 0
0x180005080  mov     rcx, rdi; this
0x180005083  call    ?VariantExtractBinaryBuffer@CommonUtil@@YAJAEBUtagVARIANT@@PEAPEBXPEA_K@Z; CommonUtil::VariantExtractBinaryBuffer(tagVARIANT const &,void const * *,unsigned __int64 *)
0x180005088  test    eax, eax
0x18000508a  js      short loc_1800050DD
0x18000508c  mov     rcx, [rsp+38h+pSid]; pSid
0x180005091  call    cs:__imp_IsValidSid
0x180005097  test    eax, eax
0x180005099  jnz     short loc_1800050D0
0x18000509b  call    HrGetLastFailure
0x1800050a0  mov     ebx, eax
0x1800050a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050a9  cmp     rcx, rsi
0x1800050ac  jz      short loc_1800050CC
0x1800050ae  test    byte ptr [rcx+1Ch], 1
0x1800050b2  jz      short loc_1800050CC
0x1800050b4  mov     rcx, [rcx+10h]
0x1800050b8  lea     r8, WPP_85f567f30ac03a1b1e78961f0afc6072_Traceguids
0x1800050bf  mov     edx, 16h
0x1800050c4  mov     r9d, eax
0x1800050c7  call    WPP_SF_d
0x1800050cc  mov     eax, ebx
0x1800050ce  jmp     short loc_1800050DD
0x1800050d0  mov     rdx, [rsp+38h+pSid]
0x1800050d5  mov     rcx, rbx; Str
0x1800050d8  call    UtilAddUserReadAccessToSample
0x1800050dd  mov     rbx, [rsp+38h+arg_10]
0x1800050e2  mov     rsi, [rsp+38h+arg_18]
0x1800050e7  add     rsp, 30h
0x1800050eb  pop     rdi
0x1800050ec  retn
```
