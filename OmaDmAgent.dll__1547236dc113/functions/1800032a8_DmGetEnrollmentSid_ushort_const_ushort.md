# DmGetEnrollmentSid(ushort const *,ushort * *)

- ea: `0x1800032a8`
- end: `0x180003309`
- name: `?DmGetEnrollmentSid@@YAJPEBGPEAPEAG@Z`
- size: `97`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180004950`

## callees

- `0x180003204`
- `0x1800032a8`
- `0x18001f420`

## import_xrefs

- `dmEnrollEngine!GetEnrollmentSID` at `0x1800032e9`
- `dmEnrollEngine!GetEnrollmentSID` at `0x1800032e9`

## pseudocode

```c
int __fastcall DmGetEnrollmentSid(unsigned __int16 *a1, unsigned __int16 **a2)
{
  int result; // eax
  struct _GUID v4; // [rsp+20h] [rbp-38h] BYREF
  struct _GUID v5; // [rsp+30h] [rbp-28h] BYREF

  v5 = 0;
  result = DmConvertInternalAccountIdToEnrollmentId(a1, &v5);
  if ( result >= 0 )
  {
    v4 = v5;
    return GetEnrollmentSID(&v4, a2);
  }
  return result;
}

```

## disassembly

```asm
0x1800032a8  push    rbx
0x1800032aa  sub     rsp, 50h
0x1800032ae  mov     rax, cs:__security_cookie
0x1800032b5  xor     rax, rsp
0x1800032b8  mov     [rsp+58h+var_18], rax
0x1800032bd  mov     rbx, rdx
0x1800032c0  xorps   xmm0, xmm0
0x1800032c3  lea     rdx, [rsp+58h+var_28]; struct _GUID *
0x1800032c8  movups  xmmword ptr [rsp+58h+var_28.Data1], xmm0
0x1800032cd  call    ?DmConvertInternalAccountIdToEnrollmentId@@YAJPEAGPEAU_GUID@@@Z; DmConvertInternalAccountIdToEnrollmentId(ushort *,_GUID *)
0x1800032d2  test    eax, eax
0x1800032d4  js      short loc_1800032F5
0x1800032d6  movaps  xmm0, xmmword ptr [rsp+58h+var_28.Data1]
0x1800032db  lea     rcx, [rsp+58h+var_38]
0x1800032e0  mov     rdx, rbx
0x1800032e3  movdqa  [rsp+58h+var_38], xmm0
0x1800032e9  call    cs:__imp_GetEnrollmentSID
0x1800032f0  nop     dword ptr [rax+rax+00h]
0x1800032f5  mov     rcx, [rsp+58h+var_18]
0x1800032fa  xor     rcx, rsp; StackCookie
0x1800032fd  call    __security_check_cookie
0x180003302  add     rsp, 50h
0x180003306  pop     rbx
0x180003307  retn
```
