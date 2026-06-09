# _dynamic_initializer_for__g_pNetworkBlockPluginMappings___4

- ea: `0x140002160`
- end: `0x1400021f7`
- name: `_dynamic_initializer_for__g_pNetworkBlockPluginMappings___4`
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
int dynamic_initializer_for__g_pNetworkBlockPluginMappings___4()
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
  std::vector<std::vector<wchar_t const *>>::vector<std::vector<wchar_t const *>>(qword_14003DA48, &v2);
  `eh vector destructor iterator'(v4, 0x18u, 2u, std::vector<wchar_t const *>::~vector<wchar_t const *>);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_pNetworkBlockPluginMappings___4);
}

```

## disassembly

```asm
0x140002160  push    rbp
0x140002162  mov     rbp, rsp
0x140002165  sub     rsp, 70h
0x140002169  lea     rax, aBruteforceprot_0; "BruteForceProtectionLocalNetworkBlockin"...
0x140002170  mov     [rbp+var_50], rax
0x140002174  lea     rax, aBruteforceprot; "BruteForceProtectionSkipLearningPeriod"
0x14000217b  mov     [rbp+var_48], rax
0x14000217f  lea     rax, [rbp+var_50]
0x140002183  mov     [rbp+var_40], rax
0x140002187  lea     rax, [rbp+var_40]
0x14000218b  mov     [rbp+var_38], rax
0x14000218f  lea     rdx, [rbp+var_40]
0x140002193  lea     rcx, [rbp+var_30]
0x140002197  call    ??0?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAA@V?$initializer_list@PEB_W@1@AEBV?$allocator@PEB_W@1@@Z; std::vector<wchar_t const *>::vector<wchar_t const *>(std::initializer_list<wchar_t const *>,std::allocator<wchar_t const *> const &)
0x14000219c  xorps   xmm0, xmm0
0x14000219f  movdqu  [rbp+var_18], xmm0
0x1400021a4  mov     [rbp+var_8], 0
0x1400021ac  lea     rax, [rbp+var_30]
0x1400021b0  mov     [rbp+var_40], rax
0x1400021b4  lea     rax, [rbp+var_s0]
0x1400021b8  mov     [rbp+var_38], rax
0x1400021bc  lea     rdx, [rbp+var_40]
0x1400021c0  lea     rcx, qword_14003DA48
0x1400021c7  call    ??0?$vector@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@V?$allocator@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@@2@@std@@QEAA@V?$initializer_list@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@@1@AEBV?$allocator@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@@1@@Z; std::vector<std::vector<wchar_t const *>>::vector<std::vector<wchar_t const *>>(std::initializer_list<std::vector<wchar_t const *>>,std::allocator<std::vector<wchar_t const *>> const &)
0x1400021cc  nop
0x1400021cd  lea     r9, ??1?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAA@XZ; void (*)(void *)
0x1400021d4  mov     edx, 18h; unsigned __int64
0x1400021d9  lea     r8d, [rdx-16h]; unsigned __int64
0x1400021dd  lea     rcx, [rbp+var_30]; void *
0x1400021e1  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400021e6  lea     rcx, _dynamic_atexit_destructor_for__g_pNetworkBlockPluginMappings___4
0x1400021ed  add     rsp, 70h
0x1400021f1  pop     rbp
0x1400021f2  jmp     atexit
```
