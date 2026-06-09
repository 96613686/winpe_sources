# _lambda_56aeb2e009693073d2cb3c1d409578e1_::operator()(void)

- ea: `0x180035fc4`
- end: `0x1800360cc`
- name: `??R_lambda_56aeb2e009693073d2cb3c1d409578e1_@@QEBA@XZ`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180034d3c`

## callees

- `0x1800039c0`
- `0x180007c64`
- `0x18000e0c0`
- `0x180019c68`
- `0x180035188`
- `0x180035fc4`
- `0x18003a24c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035ff4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035ff4`

## pseudocode

```c
PVOID *__fastcall _lambda_56aeb2e009693073d2cb3c1d409578e1_::operator()(__int64 *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  const unsigned __int16 *v4; // rax
  __int64 v5; // rdx
  unsigned __int16 *v6; // r9
  int v7; // eax
  __int64 v8; // rcx
  _OWORD *v9; // rdx
  PVOID *result; // rax
  unsigned int v11; // eax
  int v12[4]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  v12[0] = *(_DWORD *)v2;
  LOWORD(v12[1]) = *(_WORD *)(v2 + 4);
  v3 = *(_QWORD *)(v2 + 24);
  HIWORD(v12[1]) = v3;
  *(_QWORD *)&v12[2] = CoTaskMemAlloc(2 * v3 + 2);
  if ( !*(_QWORD *)&v12[2] )
  {
    v11 = wil::verify_hresult<long>(2147942414LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\tg\\npsmmediacontroller\\lib\\npsmmediacontroller.cpp",
      (const char *)v11,
      v12[0]);
  }
  v4 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*a1 + 8);
  v7 = StringCchCopyW(v6, *(_QWORD *)(v5 + 24) + 1LL, v4);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\tg\\npsmmediacontroller\\lib\\npsmmediacontroller.cpp",
      (const char *)(unsigned int)v7,
      v12[0]);
  v8 = a1[1];
  v9 = *(_OWORD **)(v8 + 8);
  if ( v9 == *(_OWORD **)(v8 + 16) )
  {
    std::vector<BthAvMediaItemAttribute>::_Emplace_reallocate<BthAvMediaItemAttribute const &>(v8, v9, v12);
  }
  else
  {
    *v9 = *(_OWORD *)v12;
    *(_QWORD *)(v8 + 8) += 16LL;
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    return (PVOID *)WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), 24);
  }
  return result;
}

```

## disassembly

```asm
0x180035fc4  push    rbx
0x180035fc6  sub     rsp, 30h
0x180035fca  mov     rbx, rcx
0x180035fcd  mov     rcx, [rcx]
0x180035fd0  mov     eax, [rcx]
0x180035fd2  mov     [rsp+38h+var_18], eax; int
0x180035fd6  movzx   eax, word ptr [rcx+4]
0x180035fda  mov     word ptr [rsp+38h+var_18+4], ax
0x180035fdf  movzx   eax, word ptr [rcx+18h]
0x180035fe3  mov     rcx, [rcx+18h]
0x180035fe7  mov     word ptr [rsp+38h+var_18+6], ax
0x180035fec  lea     rcx, ds:2[rcx*2]; cb
0x180035ff4  call    cs:__imp_CoTaskMemAlloc
0x180035ffa  mov     qword ptr [rsp+38h+var_18+8], rax
0x180035fff  mov     r9, rax
0x180036002  test    rax, rax
0x180036005  jz      loc_1800360A8
0x18003600b  mov     rdx, [rbx]
0x18003600e  lea     rcx, [rdx+8]
0x180036012  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180036017  mov     rdx, [rdx+18h]
0x18003601b  mov     r8, rax; unsigned __int16 *
0x18003601e  inc     rdx; unsigned __int64
0x180036021  mov     rcx, r9; unsigned __int16 *
0x180036024  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036029  test    eax, eax
0x18003602b  js      short loc_18003608E
0x18003602d  mov     rcx, [rbx+8]
0x180036031  mov     rdx, [rcx+8]
0x180036035  cmp     rdx, [rcx+10h]
0x180036039  jz      short loc_18003604B
0x18003603b  movups  xmm0, xmmword ptr [rsp+38h+var_18]
0x180036040  movdqu  xmmword ptr [rdx], xmm0
0x180036044  add     qword ptr [rcx+8], 10h
0x180036049  jmp     short loc_180036055
0x18003604b  lea     r8, [rsp+38h+var_18]
0x180036050  call    ??$_Emplace_reallocate@AEBUBthAvMediaItemAttribute@@@?$vector@UBthAvMediaItemAttribute@@V?$allocator@UBthAvMediaItemAttribute@@@std@@@std@@AEAAPEAUBthAvMediaItemAttribute@@QEAU2@AEBU2@@Z; std::vector<BthAvMediaItemAttribute>::_Emplace_reallocate<BthAvMediaItemAttribute const &>(BthAvMediaItemAttribute * const,BthAvMediaItemAttribute const &)
0x180036055  mov     rcx, cs:WPP_GLOBAL_Control
0x18003605c  lea     rax, WPP_GLOBAL_Control
0x180036063  cmp     rcx, rax
0x180036066  jz      short loc_180036088
0x180036068  test    byte ptr [rcx+1Ch], 1
0x18003606c  jz      short loc_180036088
0x18003606e  cmp     byte ptr [rcx+19h], 5
0x180036072  jb      short loc_180036088
0x180036074  mov     r9, [rbx]
0x180036077  mov     edx, 18h
0x18003607c  mov     rcx, [rcx+10h]
0x180036080  mov     r9d, [r9]
0x180036083  call    WPP_SF_l
0x180036088  add     rsp, 30h
0x18003608c  pop     rbx
0x18003608d  retn
0x18003608e  mov     rcx, [rsp+38h]; this
0x180036093  lea     r8, aOnecoreDrivers_39; "onecore\\drivers\\bluetooth\\profiles\\"...
0x18003609a  mov     r9d, eax; char *
0x18003609d  mov     edx, 0C1h; void *
0x1800360a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800360a8  mov     ecx, 8007000Eh
0x1800360ad  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800360b2  mov     rcx, [rsp+38h]; this
0x1800360b7  lea     r8, aOnecoreDrivers_39; "onecore\\drivers\\bluetooth\\profiles\\"...
0x1800360be  mov     r9d, eax; char *
0x1800360c1  mov     edx, 0BEh; void *
0x1800360c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
