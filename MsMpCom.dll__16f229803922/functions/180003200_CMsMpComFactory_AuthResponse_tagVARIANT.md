# CMsMpComFactory::AuthResponse(tagVARIANT)

- ea: `0x180003200`
- end: `0x1800032f2`
- name: `?AuthResponse@CMsMpComFactory@@UEAAJUtagVARIANT@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(CMsMpComFactory *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002c08`
- `0x180003200`
- `0x180004b54`
- `0x180009440`
- `0x18000a010`

## import_xrefs

- `mpclient!MpUtilsExportFunctions` at `0x1800032bd`
- `mpclient!MpUtilsExportFunctions` at `0x1800032bd`

## pseudocode

```c
__int64 __fastcall CMsMpComFactory::AuthResponse(CMsMpComFactory *this, struct tagVARIANT *a2)
{
  __int64 result; // rax
  __int64 v4; // rax
  __int128 v5; // [rsp+20h] [rbp-28h] BYREF

  if ( a2->vt == 8209 )
  {
    v5 = 0;
    result = CommonUtil::UnserializeFromVariantBinaryBuffer<_GUID>(&v5, (CommonUtil *)a2);
    if ( (int)result >= 0 )
    {
      if ( *((_OWORD *)this + 1) == v5 )
      {
        *((_BYTE *)this + 32) = 1;
        return 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_142e9f78c9ff30724e8ad65b92a2bbe6_Traceguids);
        v4 = MpUtilsExportFunctions();
        (*(void (__fastcall **)(__int64, char *))(v4 + 80))(16, (char *)this + 16);
        return 2147942405LL;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_142e9f78c9ff30724e8ad65b92a2bbe6_Traceguids);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180003200  mov     [rsp+arg_10], rbx
0x180003205  push    rdi
0x180003206  sub     rsp, 40h
0x18000320a  mov     rax, cs:__security_cookie
0x180003211  xor     rax, rsp
0x180003214  mov     [rsp+48h+var_18], rax
0x180003219  mov     eax, 2011h
0x18000321e  mov     rdi, rcx
0x180003221  cmp     [rdx], ax
0x180003224  jz      short loc_18000325B
0x180003226  mov     rcx, cs:WPP_GLOBAL_Control
0x18000322d  lea     rax, WPP_GLOBAL_Control
0x180003234  cmp     rcx, rax
0x180003237  jz      short loc_180003254
0x180003239  test    byte ptr [rcx+1Ch], 1
0x18000323d  jz      short loc_180003254
0x18000323f  mov     rcx, [rcx+10h]
0x180003243  lea     r8, WPP_142e9f78c9ff30724e8ad65b92a2bbe6_Traceguids
0x18000324a  mov     edx, 0Dh
0x18000324f  call    WPP_SF_
0x180003254  mov     eax, 80070057h
0x180003259  jmp     short loc_1800032DA
0x18000325b  xorps   xmm0, xmm0
0x18000325e  lea     rcx, [rsp+48h+var_28]; void *
0x180003263  movups  [rsp+48h+var_28], xmm0
0x180003268  call    ??$UnserializeFromVariantBinaryBuffer@U_GUID@@@CommonUtil@@YAJPEAU_GUID@@AEBUtagVARIANT@@@Z; CommonUtil::UnserializeFromVariantBinaryBuffer<_GUID>(_GUID *,tagVARIANT const &)
0x18000326d  test    eax, eax
0x18000326f  js      short loc_1800032DA
0x180003271  mov     rax, [rdi+10h]
0x180003275  cmp     rax, qword ptr [rsp+48h+var_28]
0x18000327a  jnz     short loc_18000328F
0x18000327c  mov     rax, [rdi+18h]
0x180003280  cmp     rax, qword ptr [rsp+48h+var_28+8]
0x180003285  jnz     short loc_18000328F
0x180003287  mov     byte ptr [rdi+20h], 1
0x18000328b  xor     eax, eax
0x18000328d  jmp     short loc_1800032DA
0x18000328f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003296  lea     rax, WPP_GLOBAL_Control
0x18000329d  cmp     rcx, rax
0x1800032a0  jz      short loc_1800032BD
0x1800032a2  test    byte ptr [rcx+1Ch], 1
0x1800032a6  jz      short loc_1800032BD
0x1800032a8  mov     rcx, [rcx+10h]
0x1800032ac  lea     r8, WPP_142e9f78c9ff30724e8ad65b92a2bbe6_Traceguids
0x1800032b3  mov     edx, 0Eh
0x1800032b8  call    WPP_SF_
0x1800032bd  call    cs:__imp_MpUtilsExportFunctions
0x1800032c3  lea     rdx, [rdi+10h]
0x1800032c7  mov     ecx, 10h
0x1800032cc  mov     rax, [rax+50h]
0x1800032d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032d5  mov     eax, 80070005h
0x1800032da  mov     rcx, [rsp+48h+var_18]
0x1800032df  xor     rcx, rsp; StackCookie
0x1800032e2  call    __security_check_cookie
0x1800032e7  mov     rbx, [rsp+48h+arg_10]
0x1800032ec  add     rsp, 40h
0x1800032f0  pop     rdi
0x1800032f1  retn
```
