# _dynamic_initializer_for__g_pNetworkBlockPluginMappings__

- ea: `0x140001d50`
- end: `0x140001de7`
- name: `_dynamic_initializer_for__g_pNetworkBlockPluginMappings__`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140006010`
- `0x1400060a8`
- `0x140022064`
- `0x140022138`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int dynamic_initializer_for__g_pNetworkBlockPluginMappings__()
{
  _QWORD v1[2]; // [rsp+20h] [rbp-50h] BYREF
  _BYTE *v2; // [rsp+30h] [rbp-40h] BYREF
  char *v3; // [rsp+38h] [rbp-38h]
  _BYTE v4[24]; // [rsp+40h] [rbp-30h] BYREF
  __int128 v5; // [rsp+58h] [rbp-18h]
  __int64 v6; // [rsp+68h] [rbp-8h]
  char vars0; // [rsp+70h] [rbp+0h] BYREF

  v1[0] = L"BruteForceProtectionLocalNetworkBlocking";
  v1[1] = L"BruteForceProtectionSkipLearningPeriod";
  v2 = v1;
  v3 = (char *)&v2;
  std::vector<wchar_t const *>::vector<wchar_t const *>(v4, &v2);
  v5 = 0;
  v6 = 0;
  v2 = v4;
  v3 = &vars0;
  std::vector<std::vector<wchar_t const *>>::vector<std::vector<wchar_t const *>>(qword_14003D930, &v2);
  `eh vector destructor iterator'(v4, 0x18u, 2u, std::vector<wchar_t const *>::~vector<wchar_t const *>);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_pNetworkBlockPluginMappings__);
}

```

## disassembly

```asm
0x140001d50  push    rbp
0x140001d52  mov     rbp, rsp
0x140001d55  sub     rsp, 70h
0x140001d59  lea     rax, aBruteforceprot_0; "BruteForceProtectionLocalNetworkBlockin"...
0x140001d60  mov     [rbp+var_50], rax
0x140001d64  lea     rax, aBruteforceprot; "BruteForceProtectionSkipLearningPeriod"
0x140001d6b  mov     [rbp+var_48], rax
0x140001d6f  lea     rax, [rbp+var_50]
0x140001d73  mov     [rbp+var_40], rax
0x140001d77  lea     rax, [rbp+var_40]
0x140001d7b  mov     [rbp+var_38], rax
0x140001d7f  lea     rdx, [rbp+var_40]
0x140001d83  lea     rcx, [rbp+var_30]
0x140001d87  call    ??0?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAA@V?$initializer_list@PEB_W@1@AEBV?$allocator@PEB_W@1@@Z; std::vector<wchar_t const *>::vector<wchar_t const *>(std::initializer_list<wchar_t const *>,std::allocator<wchar_t const *> const &)
0x140001d8c  xorps   xmm0, xmm0
0x140001d8f  movdqu  [rbp+var_18], xmm0
0x140001d94  mov     [rbp+var_8], 0
0x140001d9c  lea     rax, [rbp+var_30]
0x140001da0  mov     [rbp+var_40], rax
0x140001da4  lea     rax, [rbp+var_s0]
0x140001da8  mov     [rbp+var_38], rax
0x140001dac  lea     rdx, [rbp+var_40]
0x140001db0  lea     rcx, qword_14003D930
0x140001db7  call    ??0?$vector@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@V?$allocator@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@@2@@std@@QEAA@V?$initializer_list@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@@1@AEBV?$allocator@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@@1@@Z; std::vector<std::vector<wchar_t const *>>::vector<std::vector<wchar_t const *>>(std::initializer_list<std::vector<wchar_t const *>>,std::allocator<std::vector<wchar_t const *>> const &)
0x140001dbc  nop
0x140001dbd  lea     r9, ??1?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAA@XZ; void (*)(void *)
0x140001dc4  mov     edx, 18h; unsigned __int64
0x140001dc9  lea     r8d, [rdx-16h]; unsigned __int64
0x140001dcd  lea     rcx, [rbp+var_30]; void *
0x140001dd1  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x140001dd6  lea     rcx, _dynamic_atexit_destructor_for__g_pNetworkBlockPluginMappings__
0x140001ddd  add     rsp, 70h
0x140001de1  pop     rbp
0x140001de2  jmp     atexit
```
