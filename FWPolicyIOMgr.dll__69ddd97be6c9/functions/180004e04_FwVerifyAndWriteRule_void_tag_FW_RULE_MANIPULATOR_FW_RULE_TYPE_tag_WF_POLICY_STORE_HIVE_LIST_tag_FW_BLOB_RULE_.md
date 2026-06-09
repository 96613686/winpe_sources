# FwVerifyAndWriteRule(void *,_tag_FW_RULE_MANIPULATOR *,FW_RULE_TYPE,_tag_WF_POLICY_STORE_HIVE_LIST *,_tag_FW_BLOB_RULE *,long (*)(_tag_FW_RULE_MANIPULATOR *,void *,ushort const *,_tag_FW_BLOB_RULE *),long (*)(_tag_FW_RULE_MANIPULATOR *,void *,ushort const *,_tag_FW_BLOB_RULE *),long (*)(_tag_FW_RULE_MANIPULATOR *,void *,ushort const *,_tag_FW_BLOB_RULE *),_tag_WF_RULE_SOURCE_TYPE,int)

- ea: `0x180004e04`
- end: `0x180004f93`
- name: `?FwVerifyAndWriteRule@@YAJPEAXPEAU_tag_FW_RULE_MANIPULATOR@@W4FW_RULE_TYPE@@PEAU_tag_WF_POLICY_STORE_HIVE_LIST@@PEAU_tag_FW_BLOB_RULE@@P6AJ10PEBG4@Z66W4_tag_WF_RULE_SOURCE_TYPE@@H@Z`
- size: `399`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, struct _tag_FW_RULE *, __int64 (__fastcall *)(__int64, __int64, _QWORD, struct _tag_FW_RULE *), __int64, __int64, int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004320`
- `0x1800049e0`

## callees

- `0x180003b94`
- `0x180004e04`
- `0x18001e9ac`
- `0x180032a28`
- `0x180032bcc`
- `0x18003b010`

## import_xrefs

- `fwbase!IsRuleOldGlobalOpenPort` at `0x180004f0c`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180004f0c`
- `fwbase!IsRuleOldAuthApp` at `0x180004f1e`
- `fwbase!IsRuleOldAuthApp` at `0x180004f1e`
- `fwbase!IsRuleOldv1Compliant` at `0x180004eff`
- `fwbase!IsRuleOldv1Compliant` at `0x180004eff`

## pseudocode

```c
__int64 __fastcall FwVerifyAndWriteRule(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        struct _tag_FW_RULE *a5,
        __int64 (__fastcall *a6)(__int64, __int64, _QWORD, struct _tag_FW_RULE *),
        __int64 a7,
        __int64 a8,
        int a9,
        int a10)
{
  __int64 result; // rax
  unsigned int i; // eax
  __int64 v16; // rcx
  int v17; // ecx
  unsigned int j; // edx
  __int64 v19; // rax

  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
  if ( a3 >= 5 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  result = (*(__int64 (__fastcall **)(struct _tag_FW_RULE *))(a2 + 72))(a5);
  if ( (int)result >= 0 )
  {
    if ( *(_WORD *)(*(__int64 (__fastcall **)(struct _tag_FW_RULE *))(a2 + 40))(a5) >= 0x200u )
    {
      for ( i = 0; i < *(_DWORD *)a4; ++i )
      {
        v16 = *(_QWORD *)(a4 + 8);
        if ( !*(_DWORD *)(v16 + 16LL * i + 8) )
        {
          if ( !a10 || !a9 )
            return a6(a2, a1, *(_QWORD *)(v16 + 16LL * i), a5);
          return 2147942487LL;
        }
      }
      return 2147942487LL;
    }
    if ( !a3 && (unsigned int)IsRuleOldv1Compliant(a5) )
    {
      if ( (unsigned int)IsRuleOldGlobalOpenPort(a5) == 1 )
      {
        v17 = 1;
LABEL_23:
        if ( !a10 || a9 == v17 )
        {
          for ( j = 0; j < *(_DWORD *)(a1 + 56); ++j )
          {
            v19 = *(_QWORD *)(a1 + 64);
            if ( *(_DWORD *)(v19 + 16LL * j + 8) == v17 )
            {
              if ( v17 == 1 )
                return FwWriteGlobalOpenPorts(
                         (struct _tag_FW_RULE_MANIPULATOR *)a2,
                         (void *)a1,
                         *(const unsigned __int16 **)(v19 + 16LL * j),
                         a5);
              else
                return FwWriteAuthApps(
                         (struct _tag_FW_RULE_MANIPULATOR *)a2,
                         (void *)a1,
                         *(const unsigned __int16 **)(v19 + 16LL * j),
                         a5);
            }
          }
        }
        return 2147942487LL;
      }
      if ( (unsigned int)IsRuleOldAuthApp(a5) == 1 )
      {
        v17 = 2;
        goto LABEL_23;
      }
    }
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180004e04  push    rbx
0x180004e06  push    rbp
0x180004e07  push    rsi
0x180004e08  push    rdi
0x180004e09  push    r14
0x180004e0b  sub     rsp, 30h
0x180004e0f  mov     rbp, r9
0x180004e12  mov     edi, r8d
0x180004e15  mov     r14, rdx
0x180004e18  mov     rsi, rcx
0x180004e1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e22  lea     rax, WPP_GLOBAL_Control
0x180004e29  cmp     rcx, rax
0x180004e2c  jnz     loc_180004EB5
0x180004e32  cmp     edi, 5
0x180004e35  jge     loc_180004ED9
0x180004e3b  mov     rbx, [rsp+58h+arg_20]
0x180004e43  mov     rax, [r14+48h]
0x180004e47  mov     rcx, rbx
0x180004e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e4f  test    eax, eax
0x180004e51  js      short loc_180004EAA
0x180004e53  mov     rax, [r14+28h]
0x180004e57  mov     rcx, rbx
0x180004e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e5f  mov     ecx, 200h
0x180004e64  cmp     [rax], cx
0x180004e67  jb      loc_180004EF8
0x180004e6d  xor     eax, eax
0x180004e6f  cmp     eax, [rbp+0]
0x180004e72  jnb     short loc_180004EF1
0x180004e74  mov     rcx, [rbp+8]
0x180004e78  mov     r8d, eax
0x180004e7b  add     r8, r8
0x180004e7e  cmp     dword ptr [rcx+r8*8+8], 0
0x180004e84  jnz     short loc_180004EE3
0x180004e86  cmp     [rsp+58h+arg_48], 0
0x180004e8e  jnz     short loc_180004EE7
0x180004e90  mov     r8, [rcx+r8*8]
0x180004e94  mov     r9, rbx
0x180004e97  mov     rax, [rsp+58h+arg_28]
0x180004e9f  mov     rcx, r14
0x180004ea2  mov     rdx, rsi
0x180004ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eaa  add     rsp, 30h
0x180004eae  pop     r14
0x180004eb0  pop     rdi
0x180004eb1  pop     rsi
0x180004eb2  pop     rbp
0x180004eb3  pop     rbx
0x180004eb4  retn
0x180004eb5  test    byte ptr [rcx+1Ch], 8
0x180004eb9  jz      loc_180004E32
0x180004ebf  mov     rcx, [rcx+10h]
0x180004ec3  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180004eca  mov     edx, 0E5h
0x180004ecf  call    WPP_SF_
0x180004ed4  jmp     loc_180004E32
0x180004ed9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180004ede  jmp     loc_180004E3B
0x180004ee3  inc     eax
0x180004ee5  jmp     short loc_180004E6F
0x180004ee7  cmp     [rsp+58h+arg_40], 0
0x180004eef  jz      short loc_180004E90
0x180004ef1  mov     eax, 80070057h
0x180004ef6  jmp     short loc_180004EAA
0x180004ef8  test    edi, edi
0x180004efa  jnz     short loc_180004EF1
0x180004efc  mov     rcx, rbx
0x180004eff  call    cs:__imp_IsRuleOldv1Compliant
0x180004f05  test    eax, eax
0x180004f07  jz      short loc_180004EF1
0x180004f09  mov     rcx, rbx
0x180004f0c  call    cs:__imp_IsRuleOldGlobalOpenPort
0x180004f12  cmp     eax, 1
0x180004f15  jnz     short loc_180004F1B
0x180004f17  mov     ecx, eax
0x180004f19  jmp     short loc_180004F2C
0x180004f1b  mov     rcx, rbx
0x180004f1e  call    cs:__imp_IsRuleOldAuthApp
0x180004f24  cmp     eax, 1
0x180004f27  jnz     short loc_180004EF1
0x180004f29  lea     ecx, [rax+1]
0x180004f2c  cmp     [rsp+58h+arg_48], 0
0x180004f34  jz      short loc_180004F3F
0x180004f36  cmp     [rsp+58h+arg_40], ecx
0x180004f3d  jnz     short loc_180004EF1
0x180004f3f  xor     edx, edx
0x180004f41  cmp     edx, [rsi+38h]
0x180004f44  jnb     short loc_180004EF1
0x180004f46  mov     rax, [rsi+40h]
0x180004f4a  mov     r10d, edx
0x180004f4d  add     r10, r10
0x180004f50  cmp     [rax+r10*8+8], ecx
0x180004f55  jnz     short loc_180004F78
0x180004f57  cmp     ecx, 1
0x180004f5a  jz      short loc_180004F7C
0x180004f5c  cmp     ecx, 2
0x180004f5f  jnz     short loc_180004F78
0x180004f61  mov     r8, [rax+r10*8]; unsigned __int16 *
0x180004f65  mov     r9, rbx; struct _tag_FW_RULE *
0x180004f68  mov     rdx, rsi; void *
0x180004f6b  mov     rcx, r14; struct _tag_FW_RULE_MANIPULATOR *
0x180004f6e  call    ?FwWriteAuthApps@@YAJPEAU_tag_FW_RULE_MANIPULATOR@@PEAXPEBGPEAU_tag_FW_RULE@@@Z; FwWriteAuthApps(_tag_FW_RULE_MANIPULATOR *,void *,ushort const *,_tag_FW_RULE *)
0x180004f73  jmp     loc_180004EAA
0x180004f78  inc     edx
0x180004f7a  jmp     short loc_180004F41
0x180004f7c  mov     r8, [rax+r10*8]; unsigned __int16 *
0x180004f80  mov     r9, rbx; struct _tag_FW_RULE *
0x180004f83  mov     rdx, rsi; void *
0x180004f86  mov     rcx, r14; struct _tag_FW_RULE_MANIPULATOR *
0x180004f89  call    ?FwWriteGlobalOpenPorts@@YAJPEAU_tag_FW_RULE_MANIPULATOR@@PEAXPEBGPEAU_tag_FW_RULE@@@Z; FwWriteGlobalOpenPorts(_tag_FW_RULE_MANIPULATOR *,void *,ushort const *,_tag_FW_RULE *)
0x180004f8e  jmp     loc_180004EAA
```
