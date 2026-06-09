# DnsZtRuleMap::CreateInstance(DnsZtRuleMap * *)

- ea: `0x180007414`
- end: `0x18000748a`
- name: `?CreateInstance@DnsZtRuleMap@@SAJPEAPEAV1@@Z`
- size: `118`
- prototype: `__int64 __fastcall(struct DnsZtRuleMap **)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180007b64`
- `0x1800111cc`
- `0x180011548`

## callees

- `0x1800014d4`
- `0x180007414`
- `0x1800074f8`
- `0x180007630`

## pseudocode

```c
__int64 __fastcall DnsZtRuleMap::CreateInstance(struct DnsZtRuleMap **a1)
{
  DnsZtRuleMap *v2; // rbx
  int v3; // esi

  if ( a1 )
  {
    *a1 = 0;
    v2 = (DnsZtRuleMap *)operator new(0x18u);
    *(_QWORD *)v2 = 0;
    *((_DWORD *)v2 + 2) = 1;
    *((_DWORD *)v2 + 4) = 1;
    v3 = CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::FinalConstruct(v2);
    if ( v3 < 0 )
    {
      if ( v2 )
        DnsZtRuleMap::Release(v2);
    }
    else
    {
      *a1 = v2;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180007414  mov     [rsp+arg_0], rbx
0x180007419  mov     [rsp+arg_8], rsi
0x18000741e  push    rdi
0x18000741f  sub     rsp, 20h
0x180007423  mov     rdi, rcx
0x180007426  test    rcx, rcx
0x180007429  jz      short loc_180007473
0x18000742b  mov     qword ptr [rcx], 0
0x180007432  mov     ecx, 18h; Size
0x180007437  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000743c  mov     rbx, rax
0x18000743f  mov     rcx, rbx
0x180007442  mov     qword ptr [rax], 0
0x180007449  mov     eax, 1
0x18000744e  mov     [rbx+8], eax
0x180007451  mov     [rbx+10h], eax
0x180007454  call    ?FinalConstruct@?$CWxRefMap@VDnsZtRuleMap@@VDnsZtRuleNode@@@@AEAAJXZ; CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::FinalConstruct(void)
0x180007459  mov     esi, eax
0x18000745b  test    eax, eax
0x18000745d  js      short loc_180007464
0x18000745f  mov     [rdi], rbx
0x180007462  jmp     short loc_180007478
0x180007464  test    rbx, rbx
0x180007467  jz      short loc_180007478
0x180007469  mov     rcx, rbx; this
0x18000746c  call    ?Release@DnsZtRuleMap@@QEAAKXZ; DnsZtRuleMap::Release(void)
0x180007471  jmp     short loc_180007478
0x180007473  mov     esi, 80070057h
0x180007478  mov     rbx, [rsp+28h+arg_0]
0x18000747d  mov     eax, esi
0x18000747f  mov     rsi, [rsp+28h+arg_8]
0x180007484  add     rsp, 20h
0x180007488  pop     rdi
0x180007489  retn
```
