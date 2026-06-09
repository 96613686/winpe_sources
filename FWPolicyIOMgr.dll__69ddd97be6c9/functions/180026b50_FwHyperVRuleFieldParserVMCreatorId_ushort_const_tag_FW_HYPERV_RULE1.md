# FwHyperVRuleFieldParserVMCreatorId(ushort const *,_tag_FW_HYPERV_RULE1 *)

- ea: `0x180026b50`
- end: `0x180026be0`
- name: `?FwHyperVRuleFieldParserVMCreatorId@@YAJPEBGPEAU_tag_FW_HYPERV_RULE1@@@Z`
- size: `144`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _tag_FW_HYPERV_RULE1 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800042c4`
- `0x180026b50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180026b9b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180026b9b`

## pseudocode

```c
__int64 __fastcall FwHyperVRuleFieldParserVMCreatorId(const unsigned __int16 *a1, struct _tag_FW_HYPERV_RULE1 *a2)
{
  GUID *v2; // rdx
  __int64 v3; // rax
  HRESULT v4; // ebx
  LPCOLESTR v5; // rcx
  __int64 v6; // rdx

  v2 = (GUID *)((char *)a2 + 40);
  v3 = *(_QWORD *)&v2->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( *(_QWORD *)&v2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
    v3 = *(_QWORD *)v2->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  if ( v3 )
  {
    v4 = -2147418113;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v6 = 60;
LABEL_11:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids, (unsigned int)v4);
    }
  }
  else
  {
    v4 = CLSIDFromString(a1, v2);
    if ( v4 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v6 = 61;
        goto LABEL_11;
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180026b50  push    rbx
0x180026b52  sub     rsp, 20h
0x180026b56  add     rdx, 28h ; '('; pclsid
0x180026b5a  mov     rax, [rdx]
0x180026b5d  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180026b64  jnz     short loc_180026B71
0x180026b66  mov     rax, [rdx+8]
0x180026b6a  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180026b71  test    rax, rax
0x180026b74  jz      short loc_180026B9B
0x180026b76  mov     ebx, 8000FFFFh
0x180026b7b  mov     rcx, cs:WPP_GLOBAL_Control; lpsz
0x180026b82  lea     rax, WPP_GLOBAL_Control
0x180026b89  cmp     rcx, rax
0x180026b8c  jz      short loc_180026BD8
0x180026b8e  test    byte ptr [rcx+1Ch], 1
0x180026b92  jz      short loc_180026BD8
0x180026b94  mov     edx, 3Ch ; '<'
0x180026b99  jmp     short loc_180026BC5
0x180026b9b  call    cs:__imp_CLSIDFromString
0x180026ba1  mov     ebx, eax
0x180026ba3  test    eax, eax
0x180026ba5  jns     short loc_180026BD8
0x180026ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x180026bae  lea     rax, WPP_GLOBAL_Control
0x180026bb5  cmp     rcx, rax
0x180026bb8  jz      short loc_180026BD8
0x180026bba  test    byte ptr [rcx+1Ch], 1
0x180026bbe  jz      short loc_180026BD8
0x180026bc0  mov     edx, 3Dh ; '='
0x180026bc5  mov     rcx, [rcx+10h]
0x180026bc9  lea     r8, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids
0x180026bd0  mov     r9d, ebx
0x180026bd3  call    WPP_SF_d
0x180026bd8  mov     eax, ebx
0x180026bda  add     rsp, 20h
0x180026bde  pop     rbx
0x180026bdf  retn
```
