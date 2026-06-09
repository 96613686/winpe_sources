# _dynamic_initializer_for__g_pNetworkBlockPluginMappings___0

- ea: `0x140001e20`
- end: `0x140001eb7`
- name: `_dynamic_initializer_for__g_pNetworkBlockPluginMappings___0`
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
int dynamic_initializer_for__g_pNetworkBlockPluginMappings___0()
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
  std::vector<std::vector<wchar_t const *>>::vector<std::vector<wchar_t const *>>(qword_14003D968, &v2);
  `eh vector destructor iterator'(v4, 0x18u, 2u, std::vector<wchar_t const *>::~vector<wchar_t const *>);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_pNetworkBlockPluginMappings___0);
}

```

## disassembly

```asm
0x140001e20  push    rbp
0x140001e22  mov     rbp, rsp
0x140001e25  sub     rsp, 70h
0x140001e29  lea     rax, aBruteforceprot_0; "BruteForceProtectionLocalNetworkBlockin"...
0x140001e30  mov     [rbp+var_50], rax
0x140001e34  lea     rax, aBruteforceprot; "BruteForceProtectionSkipLearningPeriod"
0x140001e3b  mov     [rbp+var_48], rax
0x140001e3f  lea     rax, [rbp+var_50]
0x140001e43  mov     [rbp+var_40], rax
0x140001e47  lea     rax, [rbp+var_40]
0x140001e4b  mov     [rbp+var_38], rax
0x140001e4f  lea     rdx, [rbp+var_40]
0x140001e53  lea     rcx, [rbp+var_30]
0x140001e57  call    ??0?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAA@V?$initializer_list@PEB_W@1@AEBV?$allocator@PEB_W@1@@Z; std::vector<wchar_t const *>::vector<wchar_t const *>(std::initializer_list<wchar_t const *>,std::allocator<wchar_t const *> const &)
0x140001e5c  xorps   xmm0, xmm0
0x140001e5f  movdqu  [rbp+var_18], xmm0
0x140001e64  mov     [rbp+var_8], 0
0x140001e6c  lea     rax, [rbp+var_30]
0x140001e70  mov     [rbp+var_40], rax
0x140001e74  lea     rax, [rbp+var_s0]
0x140001e78  mov     [rbp+var_38], rax
0x140001e7c  lea     rdx, [rbp+var_40]
0x140001e80  lea     rcx, qword_14003D968
0x140001e87  call    ??0?$vector@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@V?$allocator@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@@2@@std@@QEAA@V?$initializer_list@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@@1@AEBV?$allocator@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@@1@@Z; std::vector<std::vector<wchar_t const *>>::vector<std::vector<wchar_t const *>>(std::initializer_list<std::vector<wchar_t const *>>,std::allocator<std::vector<wchar_t const *>> const &)
0x140001e8c  nop
0x140001e8d  lea     r9, ??1?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAA@XZ; void (*)(void *)
0x140001e94  mov     edx, 18h; unsigned __int64
0x140001e99  lea     r8d, [rdx-16h]; unsigned __int64
0x140001e9d  lea     rcx, [rbp+var_30]; void *
0x140001ea1  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x140001ea6  lea     rcx, _dynamic_atexit_destructor_for__g_pNetworkBlockPluginMappings___0
0x140001ead  add     rsp, 70h
0x140001eb1  pop     rbp
0x140001eb2  jmp     atexit
```
