# FwEnableBuiltInSvcGroup(void *,_tag_FW_PROFILE_TYPE,_tag_FW_RULE *,ulong,int,int,int,int)

- ea: `0x18002b030`
- end: `0x18002b1c6`
- name: `?FwEnableBuiltInSvcGroup@@YAXPEAXW4_tag_FW_PROFILE_TYPE@@PEAU_tag_FW_RULE@@KHHHH@Z`
- size: `406`
- prototype: `LPCOLESTR *__fastcall(struct _tag_WF_POLICY_STORE *, unsigned int, __int64, unsigned int, int, int, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18002bc34`

## callees

- `0x180003b94`
- `0x1800049e0`
- `0x18002b030`
- `0x18002e1bc`
- `0x180031008`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b0ab`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b0cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b0ef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b115`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b131`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b0ab`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b0cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b0ef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b115`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b131`

## string_xrefs

- `0x18002b0a4`: `@FirewallAPI.dll,-32752`
- `0x18002b0c6`: `@FirewallAPI.dll,-28752`
- `0x18002b12a`: `@FirewallAPI.dll,-28752`
- `0x18002b0e8`: `@FirewallAPI.dll,-28502`
- `0x18002b10e`: `@FirewallAPI.dll,-33002`

## pseudocode

```c
LPCOLESTR *__fastcall FwEnableBuiltInSvcGroup(
        struct _tag_WF_POLICY_STORE *a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        int a6,
        int a7,
        int a8)
{
  LPCOLESTR *result; // rax
  unsigned int v13; // esi
  unsigned int i; // edi
  __int64 v15; // rcx

  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    result = (LPCOLESTR *)WPP_SF_(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            355,
                            WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
  v13 = 0;
  for ( i = a2; v13 < a4; ++v13 )
  {
    v15 = *(_QWORD *)(a3 + 312);
    if ( v15 )
    {
      if ( a5 && (result = (LPCOLESTR *)_o__wcsicmp(v15, L"@FirewallAPI.dll,-32752"), !(_DWORD)result)
        || a6 && (result = (LPCOLESTR *)_o__wcsicmp(*(_QWORD *)(a3 + 312), L"@FirewallAPI.dll,-28752"), !(_DWORD)result)
        || a7 && (result = (LPCOLESTR *)_o__wcsicmp(*(_QWORD *)(a3 + 312), L"@FirewallAPI.dll,-28502"), !(_DWORD)result)
        || a8 && (result = (LPCOLESTR *)_o__wcsicmp(*(_QWORD *)(a3 + 312), L"@FirewallAPI.dll,-33002"), !(_DWORD)result) )
      {
        if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)(a3 + 312), L"@FirewallAPI.dll,-28752") && a2 == 2 )
          i |= 4u;
        if ( (~i & *(_DWORD *)(a3 + 40)) != 0 )
        {
          result = (LPCOLESTR *)SplitAndActivateOOBRule(a1, (struct _tag_FW_RULE *)a3, i);
        }
        else
        {
          *(_WORD *)(a3 + 292) |= 1u;
          result = (LPCOLESTR *)FwSetRule(a1, 0, a3);
          if ( (int)result < 0
            && WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            result = (LPCOLESTR *)WPP_SF_Sd(
                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                    356,
                                    (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
                                    *(_QWORD *)(a3 + 24),
                                    (char)result);
          }
        }
      }
    }
    a3 = *(_QWORD *)a3;
  }
  return result;
}

```

## disassembly

```asm
0x18002b030  push    rbx
0x18002b032  push    rbp
0x18002b033  push    rsi
0x18002b034  push    rdi
0x18002b035  push    r13
0x18002b037  push    r14
0x18002b039  push    r15
0x18002b03b  sub     rsp, 30h
0x18002b03f  mov     ebp, r9d
0x18002b042  mov     rbx, r8
0x18002b045  mov     r14d, edx
0x18002b048  mov     r15, rcx
0x18002b04b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b052  lea     rax, WPP_GLOBAL_Control
0x18002b059  cmp     rcx, rax
0x18002b05c  jz      short loc_18002B079
0x18002b05e  test    byte ptr [rcx+1Ch], 8
0x18002b062  jz      short loc_18002B079
0x18002b064  mov     rcx, [rcx+10h]
0x18002b068  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002b06f  mov     edx, 163h
0x18002b074  call    WPP_SF_
0x18002b079  xor     esi, esi
0x18002b07b  mov     edi, r14d
0x18002b07e  test    ebp, ebp
0x18002b080  jz      loc_18002B1B7
0x18002b086  lea     r13d, [rsi+1]
0x18002b08a  mov     rcx, [rbx+138h]
0x18002b091  test    rcx, rcx
0x18002b094  jz      loc_18002B1A9
0x18002b09a  cmp     [rsp+68h+arg_20], 0
0x18002b0a2  jz      short loc_18002B0B5
0x18002b0a4  lea     rdx, aFirewallapiDll_3; "@FirewallAPI.dll,-32752"
0x18002b0ab  call    cs:__imp__o__wcsicmp
0x18002b0b1  test    eax, eax
0x18002b0b3  jz      short loc_18002B123
0x18002b0b5  cmp     [rsp+68h+arg_28], 0
0x18002b0bd  jz      short loc_18002B0D7
0x18002b0bf  mov     rcx, [rbx+138h]
0x18002b0c6  lea     rdx, aFirewallapiDll_2; "@FirewallAPI.dll,-28752"
0x18002b0cd  call    cs:__imp__o__wcsicmp
0x18002b0d3  test    eax, eax
0x18002b0d5  jz      short loc_18002B123
0x18002b0d7  cmp     [rsp+68h+arg_30], 0
0x18002b0df  jz      short loc_18002B0F9
0x18002b0e1  mov     rcx, [rbx+138h]
0x18002b0e8  lea     rdx, aFirewallapiDll_4; "@FirewallAPI.dll,-28502"
0x18002b0ef  call    cs:__imp__o__wcsicmp
0x18002b0f5  test    eax, eax
0x18002b0f7  jz      short loc_18002B123
0x18002b0f9  cmp     [rsp+68h+arg_38], 0
0x18002b101  jz      loc_18002B1A9
0x18002b107  mov     rcx, [rbx+138h]
0x18002b10e  lea     rdx, aFirewallapiDll; "@FirewallAPI.dll,-33002"
0x18002b115  call    cs:__imp__o__wcsicmp
0x18002b11b  test    eax, eax
0x18002b11d  jnz     loc_18002B1A9
0x18002b123  mov     rcx, [rbx+138h]
0x18002b12a  lea     rdx, aFirewallapiDll_2; "@FirewallAPI.dll,-28752"
0x18002b131  call    cs:__imp__o__wcsicmp
0x18002b137  test    eax, eax
0x18002b139  jnz     short loc_18002B144
0x18002b13b  cmp     r14d, 2
0x18002b13f  jnz     short loc_18002B144
0x18002b141  or      edi, 4
0x18002b144  mov     eax, edi
0x18002b146  mov     rcx, r15; struct _tag_WF_POLICY_STORE *
0x18002b149  not     eax
0x18002b14b  test    [rbx+28h], eax
0x18002b14e  jz      short loc_18002B15D
0x18002b150  mov     r8d, edi; unsigned int
0x18002b153  mov     rdx, rbx; struct _tag_FW_RULE *
0x18002b156  call    ?SplitAndActivateOOBRule@@YAJPEAXPEAU_tag_FW_RULE@@K@Z; SplitAndActivateOOBRule(void *,_tag_FW_RULE *,ulong)
0x18002b15b  jmp     short loc_18002B1A9
0x18002b15d  or      [rbx+124h], r13w
0x18002b165  mov     r8, rbx
0x18002b168  xor     edx, edx
0x18002b16a  call    FwSetRule
0x18002b16f  test    eax, eax
0x18002b171  jns     short loc_18002B1A9
0x18002b173  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b17a  lea     rdx, WPP_GLOBAL_Control
0x18002b181  cmp     rcx, rdx
0x18002b184  jz      short loc_18002B1A9
0x18002b186  test    [rcx+1Ch], r13b
0x18002b18a  jz      short loc_18002B1A9
0x18002b18c  mov     r9, [rbx+18h]
0x18002b190  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002b197  mov     rcx, [rcx+10h]
0x18002b19b  mov     edx, 164h
0x18002b1a0  mov     [rsp+68h+var_48], eax
0x18002b1a4  call    WPP_SF_Sd
0x18002b1a9  mov     rbx, [rbx]
0x18002b1ac  add     esi, r13d
0x18002b1af  cmp     esi, ebp
0x18002b1b1  jb      loc_18002B08A
0x18002b1b7  add     rsp, 30h
0x18002b1bb  pop     r15
0x18002b1bd  pop     r14
0x18002b1bf  pop     r13
0x18002b1c1  pop     rdi
0x18002b1c2  pop     rsi
0x18002b1c3  pop     rbp
0x18002b1c4  pop     rbx
0x18002b1c5  retn
```
