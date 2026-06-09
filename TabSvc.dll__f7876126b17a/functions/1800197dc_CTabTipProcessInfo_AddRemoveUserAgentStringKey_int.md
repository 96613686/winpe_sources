# CTabTipProcessInfo::_AddRemoveUserAgentStringKey(int)

- ea: `0x1800197dc`
- end: `0x1800198b6`
- name: `?_AddRemoveUserAgentStringKey@CTabTipProcessInfo@@CAXH@Z`
- size: `218`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180013b64`
- `0x18002638c`

## callees

- `0x180013560`
- `0x1800197dc`
- `0x1800198bc`
- `0x18001a174`
- `0x18002b3a8`

## string_xrefs

- `0x180019822`: `PENSERVICE_CTabTipProcessInfo::_AddRemoveUserAgentStringKey`
- `0x180019876`: `PENSERVICE_CTabTipProcessInfo::_AddRemoveUserAgentStringKey`

## pseudocode

```c
void __fastcall CTabTipProcessInfo::_AddRemoveUserAgentStringKey(int a1)
{
  struct _GUID *v2; // rcx
  unsigned __int64 v3; // r8
  const struct _GUID *v4; // rcx
  struct _GUID *v5; // rax
  unsigned __int64 v6; // r8

  v2 = WPP_GLOBAL_Control;
  v3 = *(_QWORD *)WPP_GLOBAL_Control[3].Data4;
  if ( v3 )
  {
    PrivateTraceEvent(WPP_GLOBAL_Control, 0x617u, v3, 1u);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (struct _GUID *)&WPP_GLOBAL_Control && (v2[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&v2[1].Data1,
      22,
      WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids,
      "PENSERVICE_CTabTipProcessInfo::_AddRemoveUserAgentStringKey");
  if ( a1 )
  {
    AddUserAgentString(0);
    AddUserAgentString(512);
  }
  else
  {
    RemoveUserAgentString(0);
    RemoveUserAgentString(0x200u);
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      23,
      WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids,
      "PENSERVICE_CTabTipProcessInfo::_AddRemoveUserAgentStringKey");
    v5 = WPP_GLOBAL_Control;
  }
  v6 = *(_QWORD *)v5[3].Data4;
  if ( v6 )
    PrivateTraceEvent(v4, 0x617u, v6, 2u);
}

```

## disassembly

```asm
0x1800197dc  mov     [rsp+arg_0], rbx
0x1800197e1  push    rsi
0x1800197e2  sub     rsp, 20h
0x1800197e6  mov     ebx, ecx
0x1800197e8  mov     rcx, cs:WPP_GLOBAL_Control; struct _GUID *
0x1800197ef  mov     r8, [rcx+38h]; unsigned __int64
0x1800197f3  test    r8, r8
0x1800197f6  jz      short loc_18001980C
0x1800197f8  mov     r9b, 1; unsigned __int8
0x1800197fb  mov     edx, 617h; unsigned int
0x180019800  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180019805  mov     rcx, cs:WPP_GLOBAL_Control
0x18001980c  lea     rsi, WPP_GLOBAL_Control
0x180019813  cmp     rcx, rsi
0x180019816  jz      short loc_18001983A
0x180019818  test    byte ptr [rcx+1Ch], 10h
0x18001981c  jz      short loc_18001983A
0x18001981e  mov     rcx, [rcx+10h]
0x180019822  lea     r9, aPenserviceCtab; "PENSERVICE_CTabTipProcessInfo::_AddRemo"...
0x180019829  mov     edx, 16h
0x18001982e  lea     r8, WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids
0x180019835  call    WPP_SF_s
0x18001983a  xor     ecx, ecx; samDesired
0x18001983c  test    ebx, ebx
0x18001983e  jz      short loc_180019851
0x180019840  call    ?AddUserAgentString@@YAJK@Z; AddUserAgentString(ulong)
0x180019845  mov     ecx, 200h; unsigned int
0x18001984a  call    ?AddUserAgentString@@YAJK@Z; AddUserAgentString(ulong)
0x18001984f  jmp     short loc_180019860
0x180019851  call    ?RemoveUserAgentString@@YAJK@Z; RemoveUserAgentString(ulong)
0x180019856  mov     ecx, 200h; samDesired
0x18001985b  call    ?RemoveUserAgentString@@YAJK@Z; RemoveUserAgentString(ulong)
0x180019860  mov     rax, cs:WPP_GLOBAL_Control
0x180019867  cmp     rax, rsi
0x18001986a  jz      short loc_180019895
0x18001986c  test    byte ptr [rax+1Ch], 10h
0x180019870  jz      short loc_180019895
0x180019872  mov     rcx, [rax+10h]
0x180019876  lea     r9, aPenserviceCtab; "PENSERVICE_CTabTipProcessInfo::_AddRemo"...
0x18001987d  mov     edx, 17h
0x180019882  lea     r8, WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids
0x180019889  call    WPP_SF_s
0x18001988e  mov     rax, cs:WPP_GLOBAL_Control
0x180019895  mov     r8, [rax+38h]; unsigned __int64
0x180019899  test    r8, r8
0x18001989c  jz      short loc_1800198AB
0x18001989e  mov     r9b, 2; unsigned __int8
0x1800198a1  mov     edx, 617h; unsigned int
0x1800198a6  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x1800198ab  mov     rbx, [rsp+28h+arg_0]
0x1800198b0  add     rsp, 20h
0x1800198b4  pop     rsi
0x1800198b5  retn
```
