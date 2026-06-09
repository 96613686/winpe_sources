# KerbIumUpdateSharedConfiguration

- ea: `0x1400197a0`
- end: `0x14001987d`
- name: `KerbIumUpdateSharedConfiguration`
- size: `221`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x140004ca8`
- `0x14001212c`
- `0x1400197a0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400197c3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400197c3`
- `KerbClientShared!KerbClientUpdateSharedConfiguration` at `0x14001982d`
- `KerbClientShared!KerbClientUpdateSharedConfiguration` at `0x14001982d`

## string_xrefs

- `0x1400197f0`: `KerbIumUpdateSharedConfiguration`
- `0x14001984f`: `KerbIumUpdateSharedConfiguration`

## pseudocode

```c
__int64 __fastcall KerbIumUpdateSharedConfiguration(
        __int64 a1,
        struct _KerbSharedConfiguration *a2,
        struct _KerbSharedConfiguration *a3)
{
  PVOID *v6; // rcx
  int updated; // ebx

  if ( qword_140052C40 != a1 )
  {
    Sleep(5u);
    return 3221225506LL;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      76,
      WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
      "KerbIumUpdateSharedConfiguration");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    updated = -1073741584;
    goto LABEL_12;
  }
  if ( !a3 )
  {
    updated = -1073741583;
    goto LABEL_12;
  }
  updated = KerbClientUpdateSharedConfiguration(a2, a3);
  if ( updated < 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_12:
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
      WPP_SF_sd(
        (unsigned int)v6[2],
        77,
        (unsigned int)WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
        (unsigned int)"KerbIumUpdateSharedConfiguration",
        updated);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1400197a0  mov     [rsp+arg_0], rbx
0x1400197a5  mov     [rsp+arg_8], rsi
0x1400197aa  push    rdi
0x1400197ab  sub     rsp, 30h
0x1400197af  cmp     cs:qword_140052C40, rcx
0x1400197b6  mov     rbx, r8
0x1400197b9  mov     rdi, rdx
0x1400197bc  jz      short loc_1400197D3
0x1400197be  mov     ecx, 5; dwMilliseconds
0x1400197c3  call    cs:__imp_Sleep
0x1400197c9  mov     eax, 0C0000022h
0x1400197ce  jmp     loc_14001986D
0x1400197d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400197da  lea     rsi, WPP_GLOBAL_Control
0x1400197e1  cmp     rcx, rsi
0x1400197e4  jz      short loc_14001980F
0x1400197e6  test    byte ptr [rcx+1Ch], 4
0x1400197ea  jz      short loc_14001980F
0x1400197ec  mov     rcx, [rcx+10h]
0x1400197f0  lea     r9, aKerbiumupdates; "KerbIumUpdateSharedConfiguration"
0x1400197f7  mov     edx, 4Ch ; 'L'
0x1400197fc  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140019803  call    WPP_SF_s
0x140019808  mov     rcx, cs:WPP_GLOBAL_Control
0x14001980f  test    rdi, rdi
0x140019812  jnz     short loc_14001981B
0x140019814  mov     ebx, 0C00000F0h
0x140019819  jmp     short loc_140019840
0x14001981b  test    rbx, rbx
0x14001981e  jnz     short loc_140019827
0x140019820  mov     ebx, 0C00000F1h
0x140019825  jmp     short loc_140019840
0x140019827  mov     rdx, rbx
0x14001982a  mov     rcx, rdi
0x14001982d  call    cs:__imp_?KerbClientUpdateSharedConfiguration@@YAJPEAU_KerbSharedConfiguration@@0@Z; KerbClientUpdateSharedConfiguration(_KerbSharedConfiguration *,_KerbSharedConfiguration *)
0x140019833  mov     ebx, eax
0x140019835  test    eax, eax
0x140019837  jns     short loc_14001986B
0x140019839  mov     rcx, cs:WPP_GLOBAL_Control
0x140019840  cmp     rcx, rsi
0x140019843  jz      short loc_14001986B
0x140019845  test    byte ptr [rcx+1Ch], 1
0x140019849  jz      short loc_14001986B
0x14001984b  mov     rcx, [rcx+10h]
0x14001984f  lea     r9, aKerbiumupdates; "KerbIumUpdateSharedConfiguration"
0x140019856  mov     edx, 4Dh ; 'M'
0x14001985b  mov     [rsp+38h+var_18], ebx
0x14001985f  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140019866  call    WPP_SF_sd
0x14001986b  mov     eax, ebx
0x14001986d  mov     rbx, [rsp+38h+arg_0]
0x140019872  mov     rsi, [rsp+38h+arg_8]
0x140019877  add     rsp, 30h
0x14001987b  pop     rdi
0x14001987c  retn
```
